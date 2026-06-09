# Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)

- ea: `0x140022d64`
- end: `0x140022e61`
- name: `?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z`
- size: `253`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001d310`
- `0x14001dd28`
- `0x140022aa8`

## callees

- `0x14000d7bc`
- `0x140022d64`
- `0x140023c20`
- `0x140024760`
- `0x140025f20`

## string_xrefs

- `0x140022dbc`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022e18`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::OfflineHive::SetValue(
        Csl::OfflineHive *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // [rsp+20h] [rbp-28h]
  unsigned int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  v20 = 0;
  if ( !a2 )
    goto LABEL_10;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( !v10 )
    goto LABEL_10;
  v11 = OROpenKey(*((_QWORD *)this + 1), a2, &v20);
  if ( v11 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1FB,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v11,
            v17);
    if ( v20 )
      ORCloseKey(v20);
    return v12;
  }
  v9 = v20;
  v14 = v20;
  if ( !v20 )
LABEL_10:
    v14 = *((_QWORD *)this + 1);
  v18 = a5;
  v15 = ORSetValueInternal(v14, a3, a6, a4);
  if ( v15 )
  {
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x203,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v15,
            v18);
    if ( v9 )
      ORCloseKey(v9);
    return v16;
  }
  else
  {
    if ( v9 )
      ORCloseKey(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x140022d64  mov     [rsp+arg_0], rbx
0x140022d69  mov     [rsp+arg_10], rbp
0x140022d6e  push    rsi
0x140022d6f  push    rdi
0x140022d70  push    r14
0x140022d72  sub     rsp, 30h
0x140022d76  mov     rsi, r9
0x140022d79  mov     rbp, r8
0x140022d7c  mov     rdi, rcx
0x140022d7f  xor     r14d, r14d
0x140022d82  mov     ebx, r14d
0x140022d85  mov     [rsp+48h+arg_8], rbx
0x140022d8a  test    rdx, rdx
0x140022d8d  jz      short loc_140022DF0
0x140022d8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022d93  inc     rax
0x140022d96  cmp     [rdx+rax*2], r14w
0x140022d9b  jnz     short loc_140022D93
0x140022d9d  test    rax, rax
0x140022da0  jz      short loc_140022DF0
0x140022da2  lea     r8, [rsp+48h+arg_8]
0x140022da7  mov     rcx, [rcx+8]
0x140022dab  call    OROpenKey
0x140022db0  test    eax, eax
0x140022db2  jz      short loc_140022DE3
0x140022db4  mov     rcx, [rsp+48h]; this
0x140022db9  mov     r9d, eax; char *
0x140022dbc  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022dc3  mov     edx, 1FBh; void *
0x140022dc8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022dcd  mov     ebx, eax
0x140022dcf  mov     rcx, [rsp+48h+arg_8]
0x140022dd4  test    rcx, rcx
0x140022dd7  jz      short loc_140022DDF
0x140022dd9  call    ORCloseKey
0x140022dde  nop
0x140022ddf  mov     eax, ebx
0x140022de1  jmp     short loc_140022E4D
0x140022de3  mov     rbx, [rsp+48h+arg_8]
0x140022de8  test    rbx, rbx
0x140022deb  mov     rcx, rbx
0x140022dee  jnz     short loc_140022DF4
0x140022df0  mov     rcx, [rdi+8]
0x140022df4  mov     eax, [rsp+48h+arg_20]
0x140022df8  mov     [rsp+48h+var_28], eax; unsigned int
0x140022dfc  mov     r9, rsi
0x140022dff  mov     r8d, [rsp+48h+arg_28]
0x140022e04  mov     rdx, rbp
0x140022e07  call    ORSetValueInternal
0x140022e0c  test    eax, eax
0x140022e0e  jz      short loc_140022E3D
0x140022e10  mov     rcx, [rsp+48h]; this
0x140022e15  mov     r9d, eax; char *
0x140022e18  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022e1f  mov     edx, 203h; void *
0x140022e24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022e29  mov     edi, eax
0x140022e2b  test    rbx, rbx
0x140022e2e  jz      short loc_140022E39
0x140022e30  mov     rcx, rbx
0x140022e33  call    ORCloseKey
0x140022e38  nop
0x140022e39  mov     eax, edi
0x140022e3b  jmp     short loc_140022E4D
0x140022e3d  test    rbx, rbx
0x140022e40  jz      short loc_140022E4B
0x140022e42  mov     rcx, rbx
0x140022e45  call    ORCloseKey
0x140022e4a  nop
0x140022e4b  xor     eax, eax
0x140022e4d  mov     rbx, [rsp+48h+arg_0]
0x140022e52  mov     rbp, [rsp+48h+arg_10]
0x140022e57  add     rsp, 30h
0x140022e5b  pop     r14
0x140022e5d  pop     rdi
0x140022e5e  pop     rsi
0x140022e5f  retn
```
