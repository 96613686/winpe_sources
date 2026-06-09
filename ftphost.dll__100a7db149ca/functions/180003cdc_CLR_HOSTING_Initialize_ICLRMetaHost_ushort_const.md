# CLR_HOSTING::Initialize(ICLRMetaHost *,ushort const *)

- ea: `0x180003cdc`
- end: `0x180003e20`
- name: `?Initialize@CLR_HOSTING@@QEAAJPEAUICLRMetaHost@@PEBG@Z`
- size: `324`
- prototype: `__int64 __fastcall(CLR_HOSTING *__hidden this, struct ICLRMetaHost *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003afc`

## callees

- `0x180003cdc`
- `0x180005010`

## string_xrefs

- `0x180003db9`: `ClrCreateManagedInstance`

## pseudocode

```c
__int64 __fastcall CLR_HOSTING::Initialize(CLR_HOSTING *this, struct ICLRMetaHost *a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp-10h] BYREF
  __int64 v7; // [rsp+38h] [rbp-8h] BYREF
  int v8; // [rsp+58h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+28h] BYREF

  v9 = 0;
  v8 = 0;
  v7 = 0;
  v6 = 0;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(struct ICLRMetaHost *, const unsigned __int16 *, GUID *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           a3,
           &IID_ICLRRuntimeInfo,
           &v9);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 80LL))(v9, &v8);
      if ( v4 >= 0 )
      {
        if ( v8 )
        {
          v4 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v9 + 72LL))(
                 v9,
                 &CLSID_CLRRuntimeHost,
                 &IID_ICLRRuntimeHost,
                 &v6);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, const CHAR *, __int64 *))(*(_QWORD *)v9 + 64LL))(
                     v9,
                     "ClrCreateManagedInstance",
                     &v7);
              if ( v4 >= 0 )
              {
                v4 = 0;
                *((_QWORD *)this + 3) = v7;
              }
            }
          }
        }
        else
        {
          v4 = -2147024846;
        }
      }
    }
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v9 = 0;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003cdc  mov     [rsp-8+arg_0], rbx
0x180003ce1  mov     [rsp-8+arg_10], rdi
0x180003ce6  push    rbp
0x180003ce7  mov     rbp, rsp
0x180003cea  sub     rsp, 40h
0x180003cee  mov     [rbp+arg_18], 0
0x180003cf6  mov     r11, r8
0x180003cf9  mov     [rbp+arg_8], 0
0x180003d00  mov     r10, rdx
0x180003d03  mov     [rbp+var_8], 0
0x180003d0b  mov     rdi, rcx
0x180003d0e  mov     [rbp+var_10], 0
0x180003d16  test    rdx, rdx
0x180003d19  jnz     short loc_180003D25
0x180003d1b  mov     ebx, 80070057h
0x180003d20  jmp     loc_180003E0E
0x180003d25  mov     rax, [rdx]
0x180003d28  lea     r9, [rbp+arg_18]
0x180003d2c  lea     r8, IID_ICLRRuntimeInfo
0x180003d33  mov     rdx, r11
0x180003d36  mov     rcx, r10
0x180003d39  mov     rax, [rax+18h]
0x180003d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d42  mov     ebx, eax
0x180003d44  test    eax, eax
0x180003d46  js      loc_180003DDC
0x180003d4c  mov     rcx, [rbp+arg_18]
0x180003d50  lea     rdx, [rbp+arg_8]
0x180003d54  mov     rax, [rcx]
0x180003d57  mov     rax, [rax+50h]
0x180003d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d60  mov     ebx, eax
0x180003d62  test    eax, eax
0x180003d64  js      short loc_180003DDC
0x180003d66  cmp     [rbp+arg_8], 0
0x180003d6a  jnz     short loc_180003D73
0x180003d6c  mov     ebx, 80070032h
0x180003d71  jmp     short loc_180003DDC
0x180003d73  mov     rcx, [rbp+arg_18]
0x180003d77  lea     r9, [rbp+var_10]
0x180003d7b  lea     r8, IID_ICLRRuntimeHost
0x180003d82  lea     rdx, CLSID_CLRRuntimeHost
0x180003d89  mov     rax, [rcx]
0x180003d8c  mov     rax, [rax+48h]
0x180003d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d95  mov     ebx, eax
0x180003d97  test    eax, eax
0x180003d99  js      short loc_180003DDC
0x180003d9b  mov     rcx, [rbp+var_10]
0x180003d9f  mov     rax, [rcx]
0x180003da2  mov     rax, [rax+18h]
0x180003da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dab  mov     ebx, eax
0x180003dad  test    eax, eax
0x180003daf  js      short loc_180003DDC
0x180003db1  mov     rcx, [rbp+arg_18]
0x180003db5  lea     r8, [rbp+var_8]
0x180003db9  lea     rdx, aClrcreatemanag; "ClrCreateManagedInstance"
0x180003dc0  mov     rax, [rcx]
0x180003dc3  mov     rax, [rax+40h]
0x180003dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dcc  mov     ebx, eax
0x180003dce  test    eax, eax
0x180003dd0  js      short loc_180003DDC
0x180003dd2  mov     rax, [rbp+var_8]
0x180003dd6  xor     ebx, ebx
0x180003dd8  mov     [rdi+18h], rax
0x180003ddc  mov     rcx, [rbp+arg_18]
0x180003de0  test    rcx, rcx
0x180003de3  jz      short loc_180003DF9
0x180003de5  mov     rax, [rcx]
0x180003de8  mov     rax, [rax+10h]
0x180003dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df1  mov     [rbp+arg_18], 0
0x180003df9  mov     rcx, [rbp+var_10]
0x180003dfd  test    rcx, rcx
0x180003e00  jz      short loc_180003E0E
0x180003e02  mov     rax, [rcx]
0x180003e05  mov     rax, [rax+10h]
0x180003e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0e  mov     rdi, [rsp+40h+arg_10]
0x180003e13  mov     eax, ebx
0x180003e15  mov     rbx, [rsp+40h+arg_0]
0x180003e1a  add     rsp, 40h
0x180003e1e  pop     rbp
0x180003e1f  retn
```
