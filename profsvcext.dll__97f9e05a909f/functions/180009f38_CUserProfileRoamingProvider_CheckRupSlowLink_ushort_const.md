# CUserProfileRoamingProvider::_CheckRupSlowLink(ushort const *)

- ea: `0x180009f38`
- end: `0x18000a026`
- name: `?_CheckRupSlowLink@CUserProfileRoamingProvider@@AEAAJPEBG@Z`
- size: `238`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *this, roaming *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009dfc`
- `0x180011880`

## callees

- `0x180006a9c`
- `0x180009f38`
- `0x18000fed8`
- `0x180020010`

## string_xrefs

- `0x180009fd5`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_CheckRupSlowLink(CUserProfileRoamingProvider *this, roaming *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 (__fastcall ***v6)(_QWORD); // rcx
  void *v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 *v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-28h]
  unsigned int v15[6]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v17; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v19; // [rsp+68h] [rbp+20h] BYREF

  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x10001) == 0 )
  {
    v4 = *((_QWORD *)this + 1);
    v17 = 0;
    v19 = 0;
    v18 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 176LL))(v4);
    v6 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)this + 1);
    v15[0] = v5;
    v7 = (void *)(**v6)(v6);
    v8 = CheckSlowLink(v7, a2, v15, &v17, &v19, &v18);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F3,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v8,
        v14);
      return v9;
    }
    if ( v17 )
    {
      v11 = (__int64 *)*((_QWORD *)this + 1);
      v12 = *v11;
      v13 = (*(__int64 (__fastcall **)(__int64 *))(*v11 + 16))(v11);
      (*(void (__fastcall **)(__int64 *, _QWORD))(v12 + 24))(v11, v13 | 0x400u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009f38  mov     [rsp+arg_8], rbx
0x180009f3d  push    rdi
0x180009f3e  sub     rsp, 40h
0x180009f42  mov     rdi, rcx
0x180009f45  mov     rbx, rdx
0x180009f48  mov     rcx, [rcx+8]
0x180009f4c  mov     rax, [rcx]
0x180009f4f  mov     rax, [rax+10h]
0x180009f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f58  test    eax, 10001h
0x180009f5d  jnz     loc_18000A019
0x180009f63  mov     rcx, [rdi+8]
0x180009f67  mov     [rsp+48h+arg_0], 0
0x180009f6f  mov     [rsp+48h+arg_18], 0
0x180009f77  mov     [rsp+48h+arg_10], 0
0x180009f7f  mov     rax, [rcx]
0x180009f82  mov     rax, [rax+0B0h]
0x180009f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8e  mov     rcx, [rdi+8]
0x180009f92  mov     [rsp+48h+var_18], eax
0x180009f96  mov     rax, [rcx]
0x180009f99  mov     rax, [rax]
0x180009f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa1  mov     rcx, rax; void *
0x180009fa4  lea     r9, [rsp+48h+arg_0]; int *
0x180009fa9  lea     rax, [rsp+48h+arg_10]
0x180009fae  mov     rdx, rbx; this
0x180009fb1  mov     [rsp+48h+var_20], rax; unsigned int *
0x180009fb6  lea     r8, [rsp+48h+var_18]; unsigned int *
0x180009fbb  lea     rax, [rsp+48h+arg_18]
0x180009fc0  mov     [rsp+48h+var_28], rax; int
0x180009fc5  call    ?CheckSlowLink@@YAJPEAXPEBGPEAKPEAH22@Z; CheckSlowLink(void *,ushort const *,ulong *,int *,ulong *,ulong *)
0x180009fca  mov     ebx, eax
0x180009fcc  test    eax, eax
0x180009fce  jns     short loc_180009FED
0x180009fd0  mov     rcx, [rsp+48h]; this
0x180009fd5  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180009fdc  mov     r9d, eax; char *
0x180009fdf  mov     edx, 3F3h; void *
0x180009fe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fe9  mov     eax, ebx
0x180009feb  jmp     short loc_18000A01B
0x180009fed  cmp     [rsp+48h+arg_0], 0
0x180009ff2  jz      short loc_18000A019
0x180009ff4  mov     rdi, [rdi+8]
0x180009ff8  mov     rcx, rdi
0x180009ffb  mov     rbx, [rdi]
0x180009ffe  mov     rax, [rbx+10h]
0x18000a002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a007  bts     eax, 0Ah
0x18000a00b  mov     rcx, rdi
0x18000a00e  mov     edx, eax
0x18000a010  mov     rax, [rbx+18h]
0x18000a014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a019  xor     eax, eax
0x18000a01b  mov     rbx, [rsp+48h+arg_8]
0x18000a020  add     rsp, 40h
0x18000a024  pop     rdi
0x18000a025  retn
```
