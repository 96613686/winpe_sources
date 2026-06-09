# CASFReader::GetMarkerName(long,ushort * *)

- ea: `0x180009b40`
- end: `0x180009c45`
- name: `?GetMarkerName@CASFReader@@EEAAJJPEAPEAG@Z`
- size: `261`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x180009b40`
- `0x18001f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009bdd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180009bdd`

## pseudocode

```c
__int64 __fastcall CASFReader::GetMarkerName(CASFReader *this, unsigned __int16 a2, unsigned __int16 **a3)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned __int16 v9; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF

  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27);
  if ( !v3 )
    return 2147500037LL;
  v10 = 0;
  v7 = (**v3)(v3, &IID_IWMHeaderInfo, &v10);
  if ( v7 >= 0 )
  {
    v11 = 0;
    v9 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *, __int64 *))(*(_QWORD *)v10 + 64LL))(
           v10,
           a2,
           0,
           &v9,
           &v11);
    if ( v7 >= 0 )
    {
      v8 = SysAllocStringLen(0, v9);
      *a3 = v8;
      if ( v8 )
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)v10 + 64LL))(
               v10,
               a2,
               v8,
               &v9,
               &v11);
      else
        v7 = -2147024882;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009b40  mov     [rsp-18h+arg_18], rbx
0x180009b45  push    rbp
0x180009b46  push    rsi
0x180009b47  push    rdi
0x180009b48  mov     rbp, rsp
0x180009b4b  sub     rsp, 50h
0x180009b4f  mov     rax, cs:__security_cookie
0x180009b56  xor     rax, rsp
0x180009b59  mov     [rbp+var_8], rax
0x180009b5d  mov     rcx, [rcx+0D8h]
0x180009b64  mov     rdi, r8
0x180009b67  mov     esi, edx
0x180009b69  test    rcx, rcx
0x180009b6c  jnz     short loc_180009B78
0x180009b6e  mov     eax, 80004005h
0x180009b73  jmp     loc_180009C29
0x180009b78  mov     [rbp+var_18], 0
0x180009b80  lea     r8, [rbp+var_18]
0x180009b84  mov     rax, [rcx]
0x180009b87  lea     rdx, IID_IWMHeaderInfo
0x180009b8e  mov     rax, [rax]
0x180009b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b96  mov     ebx, eax
0x180009b98  test    eax, eax
0x180009b9a  js      loc_180009C27
0x180009ba0  mov     rcx, [rbp+var_18]
0x180009ba4  lea     rdx, [rbp+var_10]
0x180009ba8  xor     eax, eax
0x180009baa  mov     [rbp+var_10], 0
0x180009bb2  mov     [rbp+var_20], ax
0x180009bb6  lea     r9, [rbp+var_20]
0x180009bba  mov     [rsp+50h+var_30], rdx
0x180009bbf  xor     r8d, r8d
0x180009bc2  mov     rax, [rcx]
0x180009bc5  movzx   edx, si
0x180009bc8  mov     rax, [rax+40h]
0x180009bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd1  mov     ebx, eax
0x180009bd3  test    eax, eax
0x180009bd5  js      short loc_180009C17
0x180009bd7  movzx   edx, [rbp+var_20]; ui
0x180009bdb  xor     ecx, ecx; strIn
0x180009bdd  call    cs:__imp_SysAllocStringLen
0x180009be3  mov     [rdi], rax
0x180009be6  mov     r8, rax
0x180009be9  test    rax, rax
0x180009bec  jnz     short loc_180009BF5
0x180009bee  mov     ebx, 8007000Eh
0x180009bf3  jmp     short loc_180009C17
0x180009bf5  mov     rcx, [rbp+var_18]
0x180009bf9  lea     rdx, [rbp+var_10]
0x180009bfd  mov     [rsp+50h+var_30], rdx
0x180009c02  lea     r9, [rbp+var_20]
0x180009c06  movzx   edx, si
0x180009c09  mov     rax, [rcx]
0x180009c0c  mov     rax, [rax+40h]
0x180009c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c15  mov     ebx, eax
0x180009c17  mov     rcx, [rbp+var_18]
0x180009c1b  mov     rax, [rcx]
0x180009c1e  mov     rax, [rax+10h]
0x180009c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c27  mov     eax, ebx
0x180009c29  mov     rcx, [rbp+var_8]
0x180009c2d  xor     rcx, rsp; StackCookie
0x180009c30  call    __security_check_cookie
0x180009c35  mov     rbx, [rsp+50h+arg_18]
0x180009c3d  add     rsp, 50h
0x180009c41  pop     rdi
0x180009c42  pop     rsi
0x180009c43  pop     rbp
0x180009c44  retn
```
