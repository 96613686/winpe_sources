# EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)

- ea: `0x180012c14`
- end: `0x180012cba`
- name: `?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z`
- size: `166`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, struct _OVERLAPPED *, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800052b4`
- `0x180010db8`
- `0x180010ed8`
- `0x18001118c`
- `0x180014e88`
- `0x18001502c`
- `0x180015328`

## callees

- `0x180001eb2`
- `0x180012c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c9a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012c4f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012c4f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012c77`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012c77`

## pseudocode

```c
__int64 __fastcall EtwpSynchReadFile(
        HANDLE hFile,
        char *a2,
        DWORD a3,
        unsigned int *a4,
        struct _OVERLAPPED *lpOverlapped,
        void *a6)
{
  unsigned int File; // esi

  lpOverlapped->Pointer = a6;
  File = ReadFile(hFile, a2, a3, 0, lpOverlapped);
  if ( !File && GetLastError() != 997 )
    goto LABEL_7;
  File = GetOverlappedResult(hFile, lpOverlapped, a4, 1);
  if ( !File )
  {
    if ( GetLastError() != 38 )
      return File;
LABEL_7:
    *a4 = 0;
    return File;
  }
  if ( a3 > *a4 )
    memset_0(&a2[*a4], 0, a3 - *a4);
  return File;
}

```

## disassembly

```asm
0x180012c14  push    rbx
0x180012c16  push    rbp
0x180012c17  push    rsi
0x180012c18  push    rdi
0x180012c19  push    r14
0x180012c1b  push    r15
0x180012c1d  sub     rsp, 38h
0x180012c21  mov     rbp, [rsp+68h+arg_20]
0x180012c29  mov     rbx, r9
0x180012c2c  mov     rax, [rsp+68h+arg_28]
0x180012c34  xor     r9d, r9d; lpNumberOfBytesRead
0x180012c37  mov     edi, r8d
0x180012c3a  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180012c3f  mov     r14, rdx
0x180012c42  mov     r15, rcx
0x180012c45  mov     [rbp+10h], eax
0x180012c48  shr     rax, 20h
0x180012c4c  mov     [rbp+14h], eax
0x180012c4f  call    cs:__imp_ReadFile
0x180012c55  mov     esi, eax
0x180012c57  test    eax, eax
0x180012c59  jnz     short loc_180012C68
0x180012c5b  call    cs:__imp_GetLastError
0x180012c61  cmp     eax, 3E5h
0x180012c66  jnz     short loc_180012CA5
0x180012c68  mov     r9d, 1; bWait
0x180012c6e  mov     r8, rbx; lpNumberOfBytesTransferred
0x180012c71  mov     rdx, rbp; lpOverlapped
0x180012c74  mov     rcx, r15; hFile
0x180012c77  call    cs:__imp_GetOverlappedResult
0x180012c7d  mov     esi, eax
0x180012c7f  test    eax, eax
0x180012c81  jz      short loc_180012C9A
0x180012c83  cmp     edi, [rbx]
0x180012c85  jbe     short loc_180012CAB
0x180012c87  sub     edi, [rbx]
0x180012c89  xor     edx, edx; Val
0x180012c8b  mov     ecx, [rbx]
0x180012c8d  mov     r8d, edi; Size
0x180012c90  add     rcx, r14; void *
0x180012c93  call    memset_0
0x180012c98  jmp     short loc_180012CAB
0x180012c9a  call    cs:__imp_GetLastError
0x180012ca0  cmp     eax, 26h ; '&'
0x180012ca3  jnz     short loc_180012CAB
0x180012ca5  mov     dword ptr [rbx], 0
0x180012cab  mov     eax, esi
0x180012cad  add     rsp, 38h
0x180012cb1  pop     r15
0x180012cb3  pop     r14
0x180012cb5  pop     rdi
0x180012cb6  pop     rsi
0x180012cb7  pop     rbp
0x180012cb8  pop     rbx
0x180012cb9  retn
```
