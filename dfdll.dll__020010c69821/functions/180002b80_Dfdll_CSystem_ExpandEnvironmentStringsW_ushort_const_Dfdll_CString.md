# Dfdll::CSystem::ExpandEnvironmentStringsW(ushort const *,Dfdll::CString &)

- ea: `0x180002b80`
- end: `0x180002cdd`
- name: `?ExpandEnvironmentStringsW@CSystem@Dfdll@@SAJPEBGAEAVCString@2@@Z`
- size: `349`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, struct Dfdll::CString *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800037a0`

## callees

- `0x180001fc8`
- `0x180002238`
- `0x1800026bc`
- `0x180002b80`
- `0x180012b30`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002bb0`
- `KERNEL32!GetLastError` at `0x180002c1b`
- `KERNEL32!GetLastError` at `0x180002bb0`
- `KERNEL32!GetLastError` at `0x180002c1b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002ba6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002c11`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002ba6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002c11`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall Dfdll::CSystem::ExpandEnvironmentStringsW(LPCWSTR lpSrc, struct Dfdll::CString *this)
{
  DWORD v4; // eax
  signed int LastError; // eax
  int v6; // ebx
  const struct std::nothrow_t *v7; // rdx
  signed int v8; // eax
  const struct std::nothrow_t *v9; // rdx
  DWORD v10; // r14d
  struct std::nothrow_t *v11; // rsi
  const struct std::nothrow_t *v12; // rdx
  void **v14; // [rsp+20h] [rbp-20h] BYREF
  LPWSTR lpDst; // [rsp+28h] [rbp-18h]
  DWORD nSize; // [rsp+30h] [rbp-10h]

  v4 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
    return (unsigned int)v6;
  }
  lpDst = 0;
  nSize = 0;
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v6 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v14, v4);
  if ( v6 < 0 )
  {
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpDst )
      operator delete(lpDst, v7);
    return (unsigned int)v6;
  }
  if ( !ExpandEnvironmentStringsW(lpSrc, lpDst, nSize) )
  {
    v8 = GetLastError();
    v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v6 = v8;
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpDst )
      operator delete(lpDst, v9);
    return (unsigned int)v6;
  }
  v10 = nSize;
  v11 = (struct std::nothrow_t *)lpDst;
  if ( !lpDst )
  {
    v6 = Dfdll::CString::AssignNULL(this);
LABEL_20:
    if ( v6 < 0 )
      goto LABEL_21;
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 8) )
  {
    v6 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8, 0);
    if ( v6 < 0 )
    {
LABEL_21:
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpDst )
        operator delete(lpDst, v12);
      return (unsigned int)v6;
    }
  }
  *((_DWORD *)this + 8) = 0;
  v6 = Dfdll::CString::Append(this, v11, v10);
  if ( v6 < 0 )
    goto LABEL_20;
LABEL_24:
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpDst )
    operator delete(lpDst, v12);
  return 0;
}

```

## disassembly

```asm
0x180002b80  mov     [rsp-18h+arg_0], rbx
0x180002b85  mov     [rsp-18h+arg_8], rsi
0x180002b8a  mov     [rsp-18h+arg_10], rdi
0x180002b8f  push    rbp
0x180002b90  push    r12
0x180002b92  push    r14
0x180002b94  mov     rbp, rsp
0x180002b97  sub     rsp, 40h
0x180002b9b  mov     rdi, rdx
0x180002b9e  mov     rsi, rcx
0x180002ba1  xor     r8d, r8d; nSize
0x180002ba4  xor     edx, edx; lpDst
0x180002ba6  call    cs:__imp_ExpandEnvironmentStringsW
0x180002bac  test    eax, eax
0x180002bae  jnz     short loc_180002BC9
0x180002bb0  call    cs:__imp_GetLastError
0x180002bb6  movzx   ebx, ax
0x180002bb9  or      ebx, 80070000h
0x180002bbf  test    eax, eax
0x180002bc1  cmovle  ebx, eax
0x180002bc4  jmp     loc_180002CC2
0x180002bc9  and     [rbp+lpDst], 0
0x180002bce  and     [rbp+nSize], 0
0x180002bd2  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180002bd9  mov     [rbp+var_20], r12
0x180002bdd  mov     edx, eax; unsigned int
0x180002bdf  lea     rcx, [rbp+var_20]; this
0x180002be3  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180002be8  mov     ebx, eax
0x180002bea  test    eax, eax
0x180002bec  jns     short loc_180002C06
0x180002bee  mov     [rbp+var_20], r12
0x180002bf2  mov     rcx, [rbp+lpDst]; void *
0x180002bf6  test    rcx, rcx
0x180002bf9  jz      short loc_180002C01
0x180002bfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002c00  nop
0x180002c01  jmp     loc_180002CC2
0x180002c06  mov     r8d, [rbp+nSize]; nSize
0x180002c0a  mov     rdx, [rbp+lpDst]; lpDst
0x180002c0e  mov     rcx, rsi; lpSrc
0x180002c11  call    cs:__imp_ExpandEnvironmentStringsW
0x180002c17  test    eax, eax
0x180002c19  jnz     short loc_180002C44
0x180002c1b  call    cs:__imp_GetLastError
0x180002c21  movzx   ebx, ax
0x180002c24  or      ebx, 80070000h
0x180002c2a  test    eax, eax
0x180002c2c  cmovle  ebx, eax
0x180002c2f  mov     [rbp+var_20], r12
0x180002c33  mov     rcx, [rbp+lpDst]; void *
0x180002c37  test    rcx, rcx
0x180002c3a  jz      short loc_180002C42
0x180002c3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002c41  nop
0x180002c42  jmp     short loc_180002CC2
0x180002c44  mov     r14d, [rbp+nSize]
0x180002c48  mov     rsi, [rbp+lpDst]
0x180002c4c  test    rsi, rsi
0x180002c4f  jnz     short loc_180002C5D
0x180002c51  mov     rcx, rdi; this
0x180002c54  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x180002c59  mov     ebx, eax
0x180002c5b  jmp     short loc_180002C94
0x180002c5d  cmp     dword ptr [rdi+20h], 0
0x180002c61  jbe     short loc_180002C7C
0x180002c63  lea     rcx, [rdi+8]
0x180002c67  mov     rax, [rcx]
0x180002c6a  xor     edx, edx
0x180002c6c  mov     rax, [rax+28h]
0x180002c70  call    cs:__guard_dispatch_icall_fptr
0x180002c76  mov     ebx, eax
0x180002c78  test    eax, eax
0x180002c7a  js      short loc_180002C98
0x180002c7c  and     dword ptr [rdi+20h], 0
0x180002c80  mov     r8d, r14d; unsigned int
0x180002c83  mov     rdx, rsi; unsigned __int16 *
0x180002c86  mov     rcx, rdi; this
0x180002c89  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180002c8e  mov     ebx, eax
0x180002c90  test    eax, eax
0x180002c92  jns     short loc_180002CAD
0x180002c94  test    ebx, ebx
0x180002c96  jns     short loc_180002CAD
0x180002c98  mov     [rbp+var_20], r12
0x180002c9c  mov     rcx, [rbp+lpDst]; void *
0x180002ca0  test    rcx, rcx
0x180002ca3  jz      short loc_180002CAB
0x180002ca5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002caa  nop
0x180002cab  jmp     short loc_180002CC2
0x180002cad  mov     [rbp+var_20], r12
0x180002cb1  mov     rcx, [rbp+lpDst]; void *
0x180002cb5  test    rcx, rcx
0x180002cb8  jz      short loc_180002CC0
0x180002cba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002cbf  nop
0x180002cc0  xor     ebx, ebx
0x180002cc2  mov     eax, ebx
0x180002cc4  mov     rbx, [rsp+40h+arg_0]
0x180002cc9  mov     rsi, [rsp+40h+arg_8]
0x180002cce  mov     rdi, [rsp+40h+arg_10]
0x180002cd3  add     rsp, 40h
0x180002cd7  pop     r14
0x180002cd9  pop     r12
0x180002cdb  pop     rbp
0x180002cdc  retn
```
