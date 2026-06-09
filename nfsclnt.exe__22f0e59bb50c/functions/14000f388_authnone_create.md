# authnone_create

- ea: `0x14000f388`
- end: `0x14000f491`
- name: `authnone_create`
- size: `265`
- prototype: `HGLOBAL()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000dcf0`
- `0x14000e9e4`

## callees

- `0x14000c5f4`
- `0x14000f388`
- `0x14001830e`
- `0x140019010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000f3c3`
- `KERNEL32!GlobalAlloc` at `0x14000f3c3`

## pseudocode

```c
HGLOBAL authnone_create()
{
  __int64 v0; // rdi
  __int64 v1; // r8
  int v2; // r9d
  HGLOBAL result; // rax
  __int128 v4; // xmm1
  __int64 v5; // xmm0_8
  __int64 v6; // r8
  int v7; // r9d
  __int64 (__fastcall *v8)(); // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall **v10)(); // [rsp+28h] [rbp-58h]
  __int64 v11; // [rsp+38h] [rbp-48h]
  __int64 v12; // [rsp+40h] [rbp-40h]
  int v13; // [rsp+48h] [rbp-38h]

  v0 = qword_140021B30;
  v9[1] = 0;
  memset_0(v9, 0, 0x54u);
  if ( !v0 )
  {
    result = GlobalAlloc(0x40u, 0x60u);
    v0 = (__int64)result;
    if ( !result )
      return result;
    qword_140021B30 = (__int64)result;
  }
  if ( !*(_DWORD *)(v0 + 92) )
  {
    v4 = null_auth;
    v5 = qword_140022270;
    *(_OWORD *)(v0 + 24) = null_auth;
    *(_QWORD *)(v0 + 56) = off_140020110;
    *(_OWORD *)v0 = v4;
    *(_QWORD *)(v0 + 40) = v5;
    *(_QWORD *)(v0 + 16) = v5;
    v10 = off_140020030;
    v9[0] = 0;
    v12 = v0 + 72;
    v11 = v0 + 72;
    v13 = 20;
    xdr_opaque_auth((__int64)v9, v0, v1, v2);
    xdr_opaque_auth((__int64)v9, v0 + 24, v6, v7);
    *(_DWORD *)(v0 + 92) = ((__int64 (__fastcall *)(_DWORD *))v10[4])(v9);
    v8 = v10[7];
    if ( v8 )
      ((void (__fastcall *)(_DWORD *))v8)(v9);
  }
  return (HGLOBAL)v0;
}

```

## disassembly

```asm
0x14000f388  mov     [rsp-8+arg_0], rbx
0x14000f38d  mov     [rsp-8+arg_8], rdi
0x14000f392  push    rbp
0x14000f393  mov     rbp, rsp
0x14000f396  sub     rsp, 80h
0x14000f39d  mov     rdi, cs:qword_140021B30
0x14000f3a4  lea     rcx, [rbp+var_60]; void *
0x14000f3a8  xor     eax, eax
0x14000f3aa  xor     edx, edx; Val
0x14000f3ac  mov     [rbp+var_5C], eax
0x14000f3af  lea     r8d, [rax+54h]; Size
0x14000f3b3  call    memset_0
0x14000f3b8  test    rdi, rdi
0x14000f3bb  jnz     short loc_14000F3DC
0x14000f3bd  lea     edx, [rdi+60h]; dwBytes
0x14000f3c0  lea     ecx, [rdi+40h]; uFlags
0x14000f3c3  call    cs:__imp_GlobalAlloc
0x14000f3c9  mov     rdi, rax
0x14000f3cc  test    rax, rax
0x14000f3cf  jz      loc_14000F47C
0x14000f3d5  mov     cs:qword_140021B30, rax
0x14000f3dc  cmp     dword ptr [rdi+5Ch], 0
0x14000f3e0  jnz     loc_14000F479
0x14000f3e6  movups  xmm1, cs:_null_auth
0x14000f3ed  lea     rax, off_140020110
0x14000f3f4  mov     rdx, rdi
0x14000f3f7  movsd   xmm0, cs:qword_140022270
0x14000f3ff  lea     rcx, off_140020030
0x14000f406  movups  xmmword ptr [rdi+18h], xmm1
0x14000f40a  mov     [rdi+38h], rax
0x14000f40e  lea     rax, [rdi+48h]
0x14000f412  movups  xmmword ptr [rdi], xmm1
0x14000f415  movsd   qword ptr [rdi+28h], xmm0
0x14000f41a  movsd   qword ptr [rdi+10h], xmm0
0x14000f41f  mov     [rbp+var_58], rcx
0x14000f423  lea     rcx, [rbp+var_60]
0x14000f427  mov     [rbp+var_60], 0
0x14000f42e  mov     [rbp+var_40], rax
0x14000f432  mov     [rbp+var_48], rax
0x14000f436  mov     [rbp+var_38], 14h
0x14000f43d  call    xdr_opaque_auth
0x14000f442  lea     rdx, [rdi+18h]
0x14000f446  lea     rcx, [rbp+var_60]
0x14000f44a  call    xdr_opaque_auth
0x14000f44f  mov     rax, [rbp+var_58]
0x14000f453  lea     rcx, [rbp+var_60]
0x14000f457  mov     rax, [rax+20h]
0x14000f45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f460  mov     [rdi+5Ch], eax
0x14000f463  mov     rax, [rbp+var_58]
0x14000f467  mov     rax, [rax+38h]
0x14000f46b  test    rax, rax
0x14000f46e  jz      short loc_14000F479
0x14000f470  lea     rcx, [rbp+var_60]
0x14000f474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f479  mov     rax, rdi
0x14000f47c  lea     r11, [rsp+80h+var_s0]
0x14000f484  mov     rbx, [r11+10h]
0x14000f488  mov     rdi, [r11+18h]
0x14000f48c  mov     rsp, r11
0x14000f48f  pop     rbp
0x14000f490  retn
```
