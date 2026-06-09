# PackageIdFromUri

- ea: `0x1800088a4`
- end: `0x180008954`
- name: `PackageIdFromUri`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008ab0`
- `0x180008d50`

## callees

- `0x1800088a4`
- `0x1800090e0`
- `0x180038010`

## string_xrefs

- `0x180008908`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x180008922`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x18000893c`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
__int64 __fastcall PackageIdFromUri(__int64 *a1)
{
  __int64 v1; // rax
  int v3; // eax
  int v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  v1 = *a1;
  v8 = 0;
  v9 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, int *))(v1 + 136))(a1, &v8);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)(unsigned int)v3,
      v6);
  if ( v8 != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)0x80070057LL,
      v6);
  v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*a1 + 88))(a1, 0, &v9);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)(unsigned int)v4,
      v6);
  return v9;
}

```

## disassembly

```asm
0x1800088a4  push    rbx; int
0x1800088a6  sub     rsp, 20h
0x1800088aa  mov     rax, [rcx]
0x1800088ad  lea     rdx, [rsp+28h+arg_0]
0x1800088b2  mov     rbx, rcx
0x1800088b5  mov     [rsp+28h+arg_0], 0
0x1800088bd  mov     [rsp+28h+arg_8], 0
0x1800088c6  mov     rax, [rax+88h]
0x1800088cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d2  test    eax, eax
0x1800088d4  js      short loc_18000891D
0x1800088d6  cmp     [rsp+28h+arg_0], 1
0x1800088db  jnz     short loc_180008937
0x1800088dd  mov     rax, [rbx]
0x1800088e0  lea     r8, [rsp+28h+arg_8]
0x1800088e5  xor     edx, edx
0x1800088e7  mov     rcx, rbx
0x1800088ea  mov     rax, [rax+58h]
0x1800088ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f3  test    eax, eax
0x1800088f5  js      short loc_180008903
0x1800088f7  mov     rax, [rsp+28h+arg_8]
0x1800088fc  add     rsp, 20h
0x180008900  pop     rbx
0x180008901  retn
0x180008903  mov     rcx, [rsp+28h]; this
0x180008908  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x18000890f  mov     r9d, eax; char *
0x180008912  mov     edx, 27h ; '''; void *
0x180008917  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000891d  mov     rcx, [rsp+28h]; this
0x180008922  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008929  mov     r9d, eax; char *
0x18000892c  mov     edx, 25h ; '%'; void *
0x180008931  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008937  mov     rcx, [rsp+28h]; this
0x18000893c  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008943  mov     r9d, 80070057h; char *
0x180008949  mov     edx, 26h ; '&'; void *
0x18000894e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
