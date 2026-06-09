# CSimpStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180031a60`
- end: `0x180031b60`
- name: `?Seek@CSimpStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `256`
- prototype: `int(CSimpStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180031a60`
- `0x180031b68`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031ac0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031b3a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031ac0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031b3a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031b23`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180031b23`

## pseudocode

```c
__int64 __fastcall CSimpStream::Seek(HANDLE *this, union _LARGE_INTEGER a2, unsigned int a3, union _ULARGE_INTEGER *a4)
{
  __int64 result; // rax
  int v7; // r10d
  unsigned int v8; // esi
  signed int LowPart; // ebx
  DWORD FileSize; // eax
  LONG v11; // eax
  int v12; // r10d
  DWORD v13; // eax

  result = CExpParameterValidate::Seek((union _LARGE_INTEGER)this, a3, a4);
  v8 = result;
  if ( (int)result < 0 )
    return result;
  if ( v7 )
  {
    v11 = 0;
    if ( a2.HighPart <= 0 && ((LowPart = a2.LowPart, a2.HighPart) || a2.LowPart < 0x80000000) )
    {
      if ( a2.QuadPart <= (__int64)0xFFFFFFFF7FFFFFFFuLL )
        LowPart = 0x80000000;
    }
    else
    {
      LowPart = 0x7FFFFFFF;
    }
    v12 = v7 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
        goto LABEL_9;
      FileSize = GetFileSize(this[5], 0);
    }
    else
    {
      FileSize = SetFilePointer(this[5], 0, 0, 1u);
    }
    if ( LowPart < 0 && -LowPart > FileSize - *((_DWORD *)this + 5) )
      return 2147680257LL;
  }
  else
  {
    LowPart = a2.LowPart;
    if ( a2.HighPart )
      LowPart = -1;
    FileSize = *((_DWORD *)this + 5);
  }
  v11 = LowPart + FileSize;
LABEL_9:
  v13 = SetFilePointer(this[5], v11, 0, 0);
  if ( a4 )
  {
    a4->HighPart = 0;
    a4->LowPart = v13 - *((_DWORD *)this + 5);
  }
  *((_DWORD *)this + 6) = v13;
  return v8;
}

```

## disassembly

```asm
0x180031a60  mov     [rsp+arg_8], rdx
0x180031a65  push    rbx
0x180031a66  push    rsi
0x180031a67  push    rdi
0x180031a68  push    r14
0x180031a6a  sub     rsp, 28h
0x180031a6e  mov     r10d, r8d
0x180031a71  mov     r14, r9
0x180031a74  mov     edx, r10d; unsigned int
0x180031a77  mov     r8, r9; union _ULARGE_INTEGER *
0x180031a7a  mov     rdi, rcx
0x180031a7d  call    ?Seek@CExpParameterValidate@@SAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; CExpParameterValidate::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x180031a82  mov     esi, eax
0x180031a84  test    eax, eax
0x180031a86  js      short loc_180031AE0
0x180031a88  test    r10d, r10d
0x180031a8b  jnz     short loc_180031AEA
0x180031a8d  mov     ebx, dword ptr [rsp+48h+arg_8]
0x180031a91  or      eax, 0FFFFFFFFh
0x180031a94  cmp     dword ptr [rsp+48h+arg_8+4], r10d
0x180031a99  cmovnz  ebx, eax
0x180031a9c  mov     eax, [rdi+14h]
0x180031a9f  add     eax, ebx
0x180031aa1  jmp     short loc_180031AB4
0x180031aa3  test    r10d, r10d
0x180031aa6  jz      short loc_180031A9C
0x180031aa8  sub     r10d, 1
0x180031aac  jz      short loc_180031B2B
0x180031aae  cmp     r10d, 1
0x180031ab2  jz      short loc_180031B1D
0x180031ab4  mov     rcx, [rdi+28h]; hFile
0x180031ab8  xor     r9d, r9d; dwMoveMethod
0x180031abb  xor     r8d, r8d; lpDistanceToMoveHigh
0x180031abe  mov     edx, eax; lDistanceToMove
0x180031ac0  call    cs:__imp_SetFilePointer
0x180031ac6  test    r14, r14
0x180031ac9  jz      short loc_180031ADB
0x180031acb  mov     ecx, eax
0x180031acd  mov     dword ptr [r14+4], 0
0x180031ad5  sub     ecx, [rdi+14h]
0x180031ad8  mov     [r14], ecx
0x180031adb  mov     [rdi+18h], eax
0x180031ade  mov     eax, esi
0x180031ae0  add     rsp, 28h
0x180031ae4  pop     r14
0x180031ae6  pop     rdi
0x180031ae7  pop     rsi
0x180031ae8  pop     rbx
0x180031ae9  retn
0x180031aea  mov     ecx, dword ptr [rsp+48h+arg_8+4]
0x180031aee  xor     eax, eax
0x180031af0  test    ecx, ecx
0x180031af2  jg      short loc_180031B16
0x180031af4  mov     ebx, dword ptr [rsp+48h+arg_8]
0x180031af8  mov     edx, 80000000h
0x180031afd  jnz     short loc_180031B03
0x180031aff  cmp     ebx, edx
0x180031b01  jnb     short loc_180031B16
0x180031b03  cmp     ecx, 0FFFFFFFFh
0x180031b06  jl      short loc_180031B12
0x180031b08  jnz     short loc_180031AA3
0x180031b0a  cmp     ebx, 7FFFFFFFh
0x180031b10  ja      short loc_180031AA3
0x180031b12  mov     ebx, edx
0x180031b14  jmp     short loc_180031AA3
0x180031b16  mov     ebx, 7FFFFFFFh
0x180031b1b  jmp     short loc_180031AA3
0x180031b1d  mov     rcx, [rdi+28h]; hFile
0x180031b21  xor     edx, edx; lpFileSizeHigh
0x180031b23  call    cs:__imp_GetFileSize
0x180031b29  jmp     short loc_180031B40
0x180031b2b  mov     rcx, [rdi+28h]; hFile
0x180031b2f  mov     r9d, 1; dwMoveMethod
0x180031b35  xor     r8d, r8d; lpDistanceToMoveHigh
0x180031b38  xor     edx, edx; lDistanceToMove
0x180031b3a  call    cs:__imp_SetFilePointer
0x180031b40  test    ebx, ebx
0x180031b42  jns     loc_180031A9F
0x180031b48  mov     edx, eax
0x180031b4a  mov     ecx, ebx
0x180031b4c  sub     edx, [rdi+14h]
0x180031b4f  neg     ecx
0x180031b51  cmp     ecx, edx
0x180031b53  jbe     loc_180031A9F
0x180031b59  mov     eax, 80030001h
0x180031b5e  jmp     short loc_180031AE0
```
