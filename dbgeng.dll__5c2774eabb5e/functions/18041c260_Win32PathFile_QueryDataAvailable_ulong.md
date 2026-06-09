# Win32PathFile::QueryDataAvailable(ulong *)

- ea: `0x18041c260`
- end: `0x18041c349`
- name: `?QueryDataAvailable@Win32PathFile@@UEAAJPEAK@Z`
- size: `233`
- prototype: `__int64 __fastcall(Win32PathFile *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18041c260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041c30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041c323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041c30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041c323`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c295`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c2bb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c2dc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c295`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c2bb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18041c2dc`

## pseudocode

```c
signed int __fastcall Win32PathFile::QueryDataAvailable(HANDLE *this, unsigned int *a2)
{
  unsigned int v4; // ecx
  signed int result; // eax
  __int64 DistanceToMoveHigh; // [rsp+40h] [rbp+20h] BYREF
  __int64 v7; // [rsp+50h] [rbp+30h] BYREF

  HIDWORD(DistanceToMoveHigh) = 0;
  v7 = 0;
  LODWORD(DistanceToMoveHigh) = SetFilePointer(this[2], 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
  if ( (_DWORD)DistanceToMoveHigh != -1 )
  {
    LODWORD(v7) = SetFilePointer(this[2], 0, (PLONG)&v7 + 1, 2u);
    if ( (_DWORD)v7 != -1 && SetFilePointer(this[2], DistanceToMoveHigh, (PLONG)&DistanceToMoveHigh + 1, 0) != -1 )
    {
      v7 -= DistanceToMoveHigh;
      if ( v7 >= 0 )
      {
        v4 = v7;
        if ( SHIDWORD(v7) > 0 )
          v4 = -1;
        result = 0;
        *a2 = v4;
        return result;
      }
      return -2147467259;
    }
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18041c260  mov     [rsp-18h+arg_8], rbx
0x18041c265  push    rbp
0x18041c266  push    rsi
0x18041c267  push    rdi
0x18041c268  mov     rbp, rsp
0x18041c26b  sub     rsp, 20h
0x18041c26f  mov     rdi, rdx
0x18041c272  mov     qword ptr [rbp+DistanceToMoveHigh], 0
0x18041c27a  mov     rbx, rcx
0x18041c27d  mov     [rbp+arg_10], 0
0x18041c285  mov     rcx, [rcx+10h]; hFile
0x18041c289  lea     r8, [rbp+arg_4]; lpDistanceToMoveHigh
0x18041c28d  xor     edx, edx; lDistanceToMove
0x18041c28f  mov     r9d, 1; dwMoveMethod
0x18041c295  call    cs:__imp_SetFilePointer
0x18041c29c  nop     dword ptr [rax+rax+00h]
0x18041c2a1  or      esi, 0FFFFFFFFh
0x18041c2a4  mov     [rbp+DistanceToMoveHigh], eax
0x18041c2a7  cmp     eax, esi
0x18041c2a9  jz      short loc_18041C30C
0x18041c2ab  mov     rcx, [rbx+10h]; hFile
0x18041c2af  lea     r8, [rbp+arg_10+4]; lpDistanceToMoveHigh
0x18041c2b3  mov     r9d, 2; dwMoveMethod
0x18041c2b9  xor     edx, edx; lDistanceToMove
0x18041c2bb  call    cs:__imp_SetFilePointer
0x18041c2c2  nop     dword ptr [rax+rax+00h]
0x18041c2c7  mov     dword ptr [rbp+arg_10], eax
0x18041c2ca  cmp     eax, esi
0x18041c2cc  jz      short loc_18041C30C
0x18041c2ce  mov     edx, [rbp+DistanceToMoveHigh]; lDistanceToMove
0x18041c2d1  lea     r8, [rbp+arg_4]; lpDistanceToMoveHigh
0x18041c2d5  mov     rcx, [rbx+10h]; hFile
0x18041c2d9  xor     r9d, r9d; dwMoveMethod
0x18041c2dc  call    cs:__imp_SetFilePointer
0x18041c2e3  nop     dword ptr [rax+rax+00h]
0x18041c2e8  cmp     eax, esi
0x18041c2ea  jz      short loc_18041C30C
0x18041c2ec  mov     rax, [rbp+arg_10]
0x18041c2f0  sub     rax, qword ptr [rbp+DistanceToMoveHigh]
0x18041c2f4  mov     [rbp+arg_10], rax
0x18041c2f8  shr     rax, 20h
0x18041c2fc  test    eax, eax
0x18041c2fe  js      short loc_18041C31C
0x18041c300  mov     ecx, dword ptr [rbp+arg_10]
0x18041c303  cmovg   ecx, esi
0x18041c306  xor     eax, eax
0x18041c308  mov     [rdi], ecx
0x18041c30a  jmp     short loc_18041C33B
0x18041c30c  call    cs:__imp_GetLastError
0x18041c313  nop     dword ptr [rax+rax+00h]
0x18041c318  test    eax, eax
0x18041c31a  jnz     short loc_18041C323
0x18041c31c  mov     eax, 80004005h
0x18041c321  jmp     short loc_18041C33B
0x18041c323  call    cs:__imp_GetLastError
0x18041c32a  nop     dword ptr [rax+rax+00h]
0x18041c32f  test    eax, eax
0x18041c331  jle     short loc_18041C33B
0x18041c333  movzx   eax, ax
0x18041c336  or      eax, 80070000h
0x18041c33b  mov     rbx, [rsp+20h+arg_8]
0x18041c340  add     rsp, 20h
0x18041c344  pop     rdi
0x18041c345  pop     rsi
0x18041c346  pop     rbp
0x18041c347  retn
```
