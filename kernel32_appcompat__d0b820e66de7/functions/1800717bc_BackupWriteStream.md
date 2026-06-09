# BackupWriteStream

- ea: `0x1800717bc`
- end: `0x180071904`
- name: `BackupWriteStream`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180059380`
- `0x180070ff0`

## callees

- `0x180032c5c`
- `0x1800717bc`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18007183c`
- `ntdll!NtFsControlFile` at `0x18007183c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180071869`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180071869`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007185a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180071889`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007185a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180071889`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800718d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800718d1`

## pseudocode

```c
int __fastcall BackupWriteStream(HANDLE hFile, __int64 a2, __int64 a3)
{
  bool v3; // zf
  int result; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-10h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+88h] [rbp+28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+30h] BYREF
  __int64 DistanceToMoveHigh; // [rsp+98h] [rbp+38h] BYREF

  v3 = *(_BYTE *)(a2 + 1129) == 0;
  IoStatusBlock = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  DistanceToMoveHigh = 0;
  if ( !v3 )
  {
    if ( (*(_BYTE *)(a2 + 4) & 8) != 0 )
      NtFsControlFile(hFile, 0, 0, 0, &IoStatusBlock, 0x900C4u, 0, 0, 0, 0);
    DistanceToMoveHigh = *(_QWORD *)(a2 + 8);
    SetFilePointer(hFile, DistanceToMoveHigh, (PLONG)&DistanceToMoveHigh + 1, 0);
    SetEndOfFile(hFile);
    DistanceToMoveHigh = 0;
    SetFilePointer(hFile, 0, (PLONG)&DistanceToMoveHigh + 1, 0);
    *(_BYTE *)(a2 + 1129) = 0;
  }
  result = ComputeRequestSize(a2, *(unsigned int *)(a3 + 16), &nNumberOfBytesToWrite);
  if ( result )
  {
    if ( nNumberOfBytesToWrite )
    {
      result = WriteFile(hFile, *(LPCVOID *)a3, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      v8 = NumberOfBytesWritten;
      *(_QWORD *)(a2 + 1056) += NumberOfBytesWritten;
      v9 = *(_DWORD **)(a3 + 8);
      *(_DWORD *)(a3 + 16) -= v8;
      *v9 += v8;
      *(_QWORD *)a3 += v8;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800717bc  mov     rax, rsp
0x1800717bf  mov     [rax+8], rbx
0x1800717c3  push    rbp
0x1800717c4  push    rsi
0x1800717c5  push    rdi
0x1800717c6  mov     rbp, rsp
0x1800717c9  sub     rsp, 60h
0x1800717cd  cmp     byte ptr [rdx+469h], 0
0x1800717d4  xorps   xmm0, xmm0
0x1800717d7  movups  xmmword ptr [rbp+var_10], xmm0
0x1800717db  mov     rdi, r8
0x1800717de  mov     [rbp+nNumberOfBytesToWrite], 0
0x1800717e5  mov     rbx, rdx
0x1800717e8  mov     [rbp+NumberOfBytesWritten], 0
0x1800717ef  mov     rsi, rcx
0x1800717f2  mov     qword ptr [rbp+DistanceToMoveHigh], 0
0x1800717fa  jz      loc_18007189C
0x180071800  test    byte ptr [rdx+4], 8
0x180071804  jz      short loc_180071848
0x180071806  mov     dword ptr [rax-30h], 0
0x18007180d  xor     r9d, r9d; ApcContext
0x180071810  mov     qword ptr [rax-38h], 0
0x180071818  xor     r8d, r8d; ApcRoutine
0x18007181b  mov     dword ptr [rax-40h], 0
0x180071822  xor     edx, edx; Event
0x180071824  mov     qword ptr [rax-48h], 0
0x18007182c  mov     dword ptr [rax-50h], 900C4h
0x180071833  lea     rax, [rbp+var_10]
0x180071837  mov     [rsp+60h+IoStatusBlock], rax; IoStatusBlock
0x18007183c  call    cs:__imp_NtFsControlFile
0x180071843  nop     dword ptr [rax+rax+00h]
0x180071848  mov     rdx, [rbx+8]; lDistanceToMove
0x18007184c  lea     r8, [rbp+arg_1C]; lpDistanceToMoveHigh
0x180071850  xor     r9d, r9d; dwMoveMethod
0x180071853  mov     qword ptr [rbp+DistanceToMoveHigh], rdx
0x180071857  mov     rcx, rsi; hFile
0x18007185a  call    cs:__imp_SetFilePointer
0x180071861  nop     dword ptr [rax+rax+00h]
0x180071866  mov     rcx, rsi; hFile
0x180071869  call    cs:__imp_SetEndOfFile
0x180071870  nop     dword ptr [rax+rax+00h]
0x180071875  xor     r9d, r9d; dwMoveMethod
0x180071878  mov     qword ptr [rbp+DistanceToMoveHigh], 0
0x180071880  lea     r8, [rbp+arg_1C]; lpDistanceToMoveHigh
0x180071884  xor     edx, edx; lDistanceToMove
0x180071886  mov     rcx, rsi; hFile
0x180071889  call    cs:__imp_SetFilePointer
0x180071890  nop     dword ptr [rax+rax+00h]
0x180071895  mov     byte ptr [rbx+469h], 0
0x18007189c  mov     edx, [rdi+10h]
0x18007189f  lea     r8, [rbp+nNumberOfBytesToWrite]
0x1800718a3  mov     rcx, rbx
0x1800718a6  call    ComputeRequestSize
0x1800718ab  test    eax, eax
0x1800718ad  jz      short loc_1800718F3
0x1800718af  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800718b3  test    r8d, r8d
0x1800718b6  jnz     short loc_1800718BE
0x1800718b8  lea     eax, [r8+1]
0x1800718bc  jmp     short loc_1800718F3
0x1800718be  mov     rdx, [rdi]; lpBuffer
0x1800718c1  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800718c5  mov     rcx, rsi; hFile
0x1800718c8  mov     [rsp+60h+IoStatusBlock], 0; lpOverlapped
0x1800718d1  call    cs:__imp_WriteFile
0x1800718d8  nop     dword ptr [rax+rax+00h]
0x1800718dd  mov     edx, [rbp+NumberOfBytesWritten]
0x1800718e0  add     [rbx+420h], rdx
0x1800718e7  mov     rcx, [rdi+8]
0x1800718eb  sub     [rdi+10h], edx
0x1800718ee  add     [rcx], edx
0x1800718f0  add     [rdi], rdx
0x1800718f3  mov     rbx, [rsp+60h+arg_0]
0x1800718fb  add     rsp, 60h
0x1800718ff  pop     rdi
0x180071900  pop     rsi
0x180071901  pop     rbp
0x180071902  retn
```
