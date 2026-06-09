# CFontFolderBase::AggregateRegFolder(void)

- ea: `0x180014de0`
- end: `0x180014ef8`
- name: `?AggregateRegFolder@CFontFolderBase@@QEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(LPUNKNOWN pUnkOuter)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x180014de0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e1a`

## pseudocode

```c
__int64 __fastcall CFontFolderBase::AggregateRegFolder(LPUNKNOWN pUnkOuter)
{
  LPUNKNOWN v1; // rbx
  struct IUnknownVtbl *lpVtbl; // rcx
  int v3; // edi
  _QWORD v5[2]; // [rsp+30h] [rbp-50h] BYREF
  char v6; // [rsp+40h] [rbp-40h]
  __int16 v7; // [rsp+41h] [rbp-3Fh]
  char v8; // [rsp+43h] [rbp-3Dh]
  int v9; // [rsp+44h] [rbp-3Ch]
  __int64 v10; // [rsp+48h] [rbp-38h]
  __int64 v11; // [rsp+50h] [rbp-30h]
  __int64 v12; // [rsp+58h] [rbp-28h]
  __int64 v13; // [rsp+60h] [rbp-20h]
  int v14; // [rsp+68h] [rbp-18h]
  char v15; // [rsp+6Ch] [rbp-14h]
  __int16 v16; // [rsp+6Dh] [rbp-13h]
  char v17; // [rsp+6Fh] [rbp-11h]
  __int64 v18; // [rsp+70h] [rbp-10h]
  __int64 v19; // [rsp+78h] [rbp-8h]
  __int64 v20; // [rsp+90h] [rbp+10h] BYREF

  v1 = pUnkOuter + 16;
  if ( CoCreateInstance(
         &CLSID_RegFolder,
         pUnkOuter,
         1u,
         &GUID_00000000_0000_0000_c000_000000000046,
         (LPVOID *)&pUnkOuter[16].lpVtbl) < 0 )
    goto LABEL_4;
  lpVtbl = v1->lpVtbl;
  v20 = 0;
  if ( (*(int (__fastcall **)(struct IUnknownVtbl *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         lpVtbl,
         &GUID_94727de2_b2ed_41b5_9eb5_0939ea9d0efc,
         &v20) < 0 )
    goto LABEL_4;
  v5[0] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\FontsFolder\\NameSpace";
  v5[1] = 0;
  v7 = 0;
  v8 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v6 = 113;
  v9 = -1;
  v10 = 4;
  v12 = 1;
  v15 = 112;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v20 + 24LL))(v20, v5);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v3 < 0 )
  {
LABEL_4:
    v3 = 0;
    if ( v1->lpVtbl )
    {
      (*((void (__fastcall **)(struct IUnknownVtbl *))v1->lpVtbl->QueryInterface + 2))(v1->lpVtbl);
      v1->lpVtbl = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014de0  mov     [rsp-8+arg_8], rbx
0x180014de5  mov     [rsp-8+arg_10], rdi
0x180014dea  push    rbp
0x180014deb  mov     rbp, rsp
0x180014dee  sub     rsp, 80h
0x180014df5  lea     rbx, [rcx+80h]
0x180014dfc  mov     rdx, rcx; pUnkOuter
0x180014dff  mov     edi, 1
0x180014e04  mov     [rsp+80h+ppv], rbx; ppv
0x180014e09  mov     r8d, edi; dwClsContext
0x180014e0c  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180014e13  lea     rcx, CLSID_RegFolder; rclsid
0x180014e1a  call    cs:__imp_CoCreateInstance
0x180014e20  test    eax, eax
0x180014e22  js      loc_180014EC8
0x180014e28  mov     rcx, [rbx]
0x180014e2b  lea     r8, [rbp+arg_0]
0x180014e2f  mov     [rbp+arg_0], 0
0x180014e37  lea     rdx, _GUID_94727de2_b2ed_41b5_9eb5_0939ea9d0efc
0x180014e3e  mov     rax, [rcx]
0x180014e41  mov     rax, [rax]
0x180014e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e49  test    eax, eax
0x180014e4b  js      short loc_180014EC8
0x180014e4d  mov     rcx, [rbp+arg_0]
0x180014e51  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014e58  mov     [rbp+var_50], rax
0x180014e5c  lea     rdx, [rbp+var_50]
0x180014e60  xor     eax, eax
0x180014e62  mov     [rbp+var_48], 0
0x180014e6a  mov     [rbp+var_3F], ax
0x180014e6e  mov     [rbp+var_3D], al
0x180014e71  mov     [rbp+var_30], rax
0x180014e75  mov     [rbp+var_20], rax
0x180014e79  mov     [rbp+var_18], eax
0x180014e7c  mov     [rbp+var_13], ax
0x180014e80  mov     [rbp+var_11], al
0x180014e83  mov     [rbp+var_10], rax
0x180014e87  mov     [rbp+var_8], rax
0x180014e8b  mov     [rbp+var_40], 71h ; 'q'
0x180014e8f  mov     [rbp+var_3C], 0FFFFFFFFh
0x180014e96  mov     [rbp+var_38], 4
0x180014e9e  mov     [rbp+var_28], rdi
0x180014ea2  mov     [rbp+var_14], 70h ; 'p'
0x180014ea6  mov     rax, [rcx]
0x180014ea9  mov     rax, [rax+18h]
0x180014ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb2  mov     rcx, [rbp+arg_0]
0x180014eb6  mov     edi, eax
0x180014eb8  mov     rdx, [rcx]
0x180014ebb  mov     rax, [rdx+10h]
0x180014ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec4  test    edi, edi
0x180014ec6  jns     short loc_180014EE1
0x180014ec8  mov     rcx, [rbx]
0x180014ecb  xor     edi, edi
0x180014ecd  test    rcx, rcx
0x180014ed0  jz      short loc_180014EE1
0x180014ed2  mov     rax, [rcx]
0x180014ed5  mov     rax, [rax+10h]
0x180014ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ede  mov     [rbx], rdi
0x180014ee1  lea     r11, [rsp+80h+var_s0]
0x180014ee9  mov     eax, edi
0x180014eeb  mov     rbx, [r11+18h]
0x180014eef  mov     rdi, [r11+20h]
0x180014ef3  mov     rsp, r11
0x180014ef6  pop     rbp
0x180014ef7  retn
```
