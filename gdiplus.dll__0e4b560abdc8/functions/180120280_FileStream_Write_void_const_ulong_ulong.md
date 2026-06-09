# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x180120280`
- end: `0x1801203b3`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `307`
- prototype: `int(FileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180120280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801202c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801202c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012038b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012038b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012034b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012034b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18012033b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18012033b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801202f6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801202f6`

## pseudocode

```c
__int64 __fastcall FileStream::Write(FileStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  void *v9; // rcx
  signed int v10; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  DWORD v13; // eax
  LONG lDistanceToMove; // [rsp+30h] [rbp-28h]
  LONG DistanceToMoveHigh; // [rsp+34h] [rbp-24h] BYREF
  __int64 v16; // [rsp+38h] [rbp-20h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  lDistanceToMove = *((_DWORD *)this + 22);
  DistanceToMoveHigh = *((_DWORD *)this + 23);
  if ( DistanceToMoveHigh < 0 )
    return 2147649733LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v9 = (void *)*((_QWORD *)this + 9);
  if ( v9 == (void *)-1LL )
  {
    v10 = -2147286782;
  }
  else
  {
    v10 = 0;
    if ( SetFilePointer(v9, lDistanceToMove, &DistanceToMoveHigh, 0) != -1 )
      goto LABEL_12;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_12:
      if ( WriteFile(*((HANDLE *)this + 9), a2, a3, &NumberOfBytesWritten, 0) )
        goto LABEL_13;
      v12 = GetLastError();
      v10 = v12;
      if ( v12 > 0 )
        v10 = (unsigned __int16)v12 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_13:
        v13 = NumberOfBytesWritten;
        v16 = NumberOfBytesWritten;
        *((_QWORD *)this + 11) += NumberOfBytesWritten;
        if ( a4 )
          *a4 = v13;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180120280  mov     rax, rsp
0x180120283  mov     [rax+10h], rbx
0x180120287  mov     [rax+18h], rbp
0x18012028b  mov     [rax+20h], rsi
0x18012028f  push    rdi
0x180120290  push    r14
0x180120292  push    r15
0x180120294  sub     rsp, 40h
0x180120298  and     dword ptr [rax+8], 0
0x18012029c  mov     rsi, r9
0x18012029f  mov     eax, [rcx+58h]
0x1801202a2  mov     r14d, r8d
0x1801202a5  mov     [rsp+58h+lDistanceToMove], eax
0x1801202a9  mov     r15, rdx
0x1801202ac  mov     eax, [rcx+5Ch]
0x1801202af  mov     rdi, rcx
0x1801202b2  mov     [rsp+58h+DistanceToMoveHigh], eax
0x1801202b6  test    eax, eax
0x1801202b8  jns     short loc_1801202C4
0x1801202ba  mov     eax, 800288C5h
0x1801202bf  jmp     loc_180120399
0x1801202c4  add     rcx, 8; lpCriticalSection
0x1801202c8  call    cs:__imp_EnterCriticalSection
0x1801202cf  nop     dword ptr [rax+rax+00h]
0x1801202d4  mov     rcx, [rdi+48h]; hFile
0x1801202d8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801202dc  jnz     short loc_1801202E8
0x1801202de  mov     ebx, 80030102h
0x1801202e3  jmp     loc_180120387
0x1801202e8  mov     edx, [rsp+58h+lDistanceToMove]; lDistanceToMove
0x1801202ec  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1801202f1  xor     r9d, r9d; dwMoveMethod
0x1801202f4  xor     ebx, ebx
0x1801202f6  call    cs:__imp_SetFilePointer
0x1801202fd  nop     dword ptr [rax+rax+00h]
0x180120302  cmp     eax, 0FFFFFFFFh
0x180120305  jnz     short loc_180120326
0x180120307  call    cs:__imp_GetLastError
0x18012030e  nop     dword ptr [rax+rax+00h]
0x180120313  mov     ebx, eax
0x180120315  test    eax, eax
0x180120317  jle     short loc_180120322
0x180120319  movzx   ebx, ax
0x18012031c  or      ebx, 80070000h
0x180120322  test    ebx, ebx
0x180120324  js      short loc_180120387
0x180120326  mov     rcx, [rdi+48h]; hFile
0x18012032a  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18012032f  and     [rsp+58h+var_38], 0
0x180120335  mov     r8d, r14d; nNumberOfBytesToWrite
0x180120338  mov     rdx, r15; lpBuffer
0x18012033b  call    cs:__imp_WriteFile
0x180120342  nop     dword ptr [rax+rax+00h]
0x180120347  test    eax, eax
0x180120349  jnz     short loc_18012036A
0x18012034b  call    cs:__imp_GetLastError
0x180120352  nop     dword ptr [rax+rax+00h]
0x180120357  mov     ebx, eax
0x180120359  test    eax, eax
0x18012035b  jle     short loc_180120366
0x18012035d  movzx   ebx, ax
0x180120360  or      ebx, 80070000h
0x180120366  test    ebx, ebx
0x180120368  js      short loc_180120387
0x18012036a  and     dword ptr [rsp+58h+var_20+4], 0
0x18012036f  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x180120373  mov     dword ptr [rsp+58h+var_20], eax
0x180120377  mov     rdx, [rsp+58h+var_20]
0x18012037c  add     [rdi+58h], rdx
0x180120380  test    rsi, rsi
0x180120383  jz      short loc_180120387
0x180120385  mov     [rsi], eax
0x180120387  lea     rcx, [rdi+8]; lpCriticalSection
0x18012038b  call    cs:__imp_LeaveCriticalSection
0x180120392  nop     dword ptr [rax+rax+00h]
0x180120397  mov     eax, ebx
0x180120399  mov     rbx, [rsp+58h+arg_8]
0x18012039e  mov     rbp, [rsp+58h+arg_10]
0x1801203a3  mov     rsi, [rsp+58h+arg_18]
0x1801203a8  add     rsp, 40h
0x1801203ac  pop     r15
0x1801203ae  pop     r14
0x1801203b0  pop     rdi
0x1801203b1  retn
```
