# CMsftDiscFormat2Erase::CheckRecorderSupportsErase(IDiscRecorder2Ex *,uchar)

- ea: `0x18000c2ac`
- end: `0x18000c739`
- name: `?CheckRecorderSupportsErase@CMsftDiscFormat2Erase@@AEAAEPEAUIDiscRecorder2Ex@@E@Z`
- size: `1165`
- prototype: `unsigned __int8 __fastcall(CMsftDiscFormat2Erase *__hidden this, struct IDiscRecorder2Ex *, unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180026ff0`
- `0x180027170`

## callees

- `0x180007df8`
- `0x18000c2ac`
- `0x180014134`
- `0x180016778`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000c6c5`
- `ole32!CoTaskMemFree` at `0x18000c6cf`
- `ole32!CoTaskMemFree` at `0x18000c6d9`
- `ole32!CoTaskMemFree` at `0x18000c6e3`
- `ole32!CoTaskMemFree` at `0x18000c6ed`
- `ole32!CoTaskMemFree` at `0x18000c6f7`
- `ole32!CoTaskMemFree` at `0x18000c701`
- `ole32!CoTaskMemFree` at `0x18000c70b`
- `ole32!CoTaskMemFree` at `0x18000c715`
- `ole32!CoTaskMemFree` at `0x18000c6c5`
- `ole32!CoTaskMemFree` at `0x18000c6cf`
- `ole32!CoTaskMemFree` at `0x18000c6d9`
- `ole32!CoTaskMemFree` at `0x18000c6e3`
- `ole32!CoTaskMemFree` at `0x18000c6ed`
- `ole32!CoTaskMemFree` at `0x18000c6f7`
- `ole32!CoTaskMemFree` at `0x18000c701`
- `ole32!CoTaskMemFree` at `0x18000c70b`
- `ole32!CoTaskMemFree` at `0x18000c715`

## pseudocode

```c
bool __fastcall CMsftDiscFormat2Erase::CheckRecorderSupportsErase(
        struct IDiscRecorder2Vtbl *this,
        struct IDiscRecorder2Ex *a2,
        char a3)
{
  struct IDiscRecorder2ExVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IDiscRecorder2Ex *, const IID *const, void **); // rax
  unsigned __int8 *v7; // r8
  bool v9; // bl
  void *v10; // rcx
  LPVOID v11; // rax
  LPVOID pv; // [rsp+38h] [rbp-39h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-2Dh] BYREF
  int v15; // [rsp+48h] [rbp-29h] BYREF
  int v16; // [rsp+4Ch] [rbp-25h] BYREF
  int v17; // [rsp+50h] [rbp-21h] BYREF
  int v18; // [rsp+54h] [rbp-1Dh] BYREF
  int v19; // [rsp+58h] [rbp-19h] BYREF
  LPVOID v20; // [rsp+60h] [rbp-11h] BYREF
  LPVOID v21; // [rsp+68h] [rbp-9h] BYREF
  LPVOID v22; // [rsp+70h] [rbp-1h] BYREF
  LPVOID v23; // [rsp+78h] [rbp+7h] BYREF
  LPVOID v24; // [rsp+80h] [rbp+Fh] BYREF
  LPVOID v25; // [rsp+88h] [rbp+17h] BYREF
  LPVOID v26; // [rsp+90h] [rbp+1Fh] BYREF
  LPVOID v27[2]; // [rsp+98h] [rbp+27h] BYREF
  struct IDiscRecorder2 v28; // [rsp+D8h] [rbp+67h] BYREF
  unsigned int v29; // [rsp+F0h] [rbp+7Fh] BYREF

  v28.lpVtbl = this;
  lpVtbl = a2->lpVtbl;
  v21 = 0;
  v16 = 0;
  v26 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v19 = 0;
  v27[0] = 0;
  v14 = 0;
  v20 = 0;
  v15 = 0;
  v22 = 0;
  v17 = 0;
  v23 = 0;
  v18 = 0;
  v24 = 0;
  v29 = 0;
  v25 = 0;
  v13 = 0;
  pv = 0;
  if ( ((int (__fastcall *)(struct IDiscRecorder2Ex *, GUID *, LPVOID *))QueryInterface)(
         a2,
         &GUID_27354133_7f64_5b0f_8f00_5d77afbe261e,
         &pv) < 0
    || (LOBYTE(v28.lpVtbl) = 0, (int)Imapi2Utility::IsRecorderSupported((Imapi2Utility *)pv, &v28, v7) < 0)
    || LOBYTE(v28.lpVtbl) )
  {
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      33,
      0,
      &v20,
      &v15);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      32,
      0,
      &v21,
      &v16);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      38,
      0,
      &v22,
      &v17);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      45,
      0,
      &v23,
      &v18);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      44,
      0,
      &v24,
      &v29);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      47,
      0,
      &v25,
      &v13);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      65,
      0,
      &v26,
      &v19);
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned int *))a2->lpVtbl->GetFeaturePage)(
      a2,
      42,
      0,
      v27,
      &v14);
    v9 = 0;
    if ( v20 && ((*((_BYTE *)v20 + 2) & 1) != 0 || !a3) )
      v9 = 1;
    if ( v21 && ((*((_BYTE *)v21 + 2) & 1) != 0 || !a3) )
      v9 = (*((unsigned __int8 *)v21 + 11)
          | ((*((unsigned __int8 *)v21 + 10)
            | ((*((unsigned __int8 *)v21 + 9) | (*((unsigned __int8 *)v21 + 8) << 8)) << 8)) << 8)) == 2048;
    if ( v22 && ((*((_BYTE *)v22 + 2) & 1) != 0 || !a3) )
      v9 = 1;
    if ( v23 && ((*((_BYTE *)v23 + 2) & 1) != 0 || !a3) )
      v9 = 1;
    if ( v24 && ((*((_BYTE *)v24 + 2) & 1) != 0 || !a3) && v29 >= 8 && (*((_BYTE *)v24 + 4) & 1) != 0 )
      v9 = 1;
    if ( v25 && ((*((_BYTE *)v25 + 2) & 1) != 0 || !a3) && v13 >= 8 && (*((_BYTE *)v25 + 4) & 2) != 0 )
      v9 = 1;
    if ( v26 && ((*((_BYTE *)v26 + 2) & 1) != 0 || !a3) )
      v9 = 1;
    if ( v27[0] && ((*((_BYTE *)v27[0] + 2) & 1) != 0 || !a3) && v14 >= 0xC && (*((_BYTE *)v27[0] + 4) & 1) != 0 )
    {
      v9 = 1;
    }
    else
    {
      if ( v9 )
        goto LABEL_68;
      pv = 0;
      LODWORD(v28.lpVtbl) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 46, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
      }
      if ( ((int (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, struct IDiscRecorder2 *))a2->lpVtbl->GetModePage)(
             a2,
             42,
             0,
             &pv,
             &v28) < 0 )
        goto LABEL_68;
      if ( LODWORD(v28.lpVtbl) >= 0xC )
      {
        v11 = pv;
        if ( (*((_BYTE *)pv + 3) & 2) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 47, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
            v11 = pv;
          }
          v9 = 1;
        }
        v10 = v11;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 32),
            34,
            &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
            12,
            v28.lpVtbl);
        }
        v10 = pv;
        if ( !pv )
          goto LABEL_68;
      }
      CoTaskMemFree(v10);
    }
LABEL_68:
    CoTaskMemFree(v20);
    CoTaskMemFree(v21);
    CoTaskMemFree(v22);
    CoTaskMemFree(v23);
    CoTaskMemFree(v24);
    CoTaskMemFree(v25);
    CoTaskMemFree(v26);
    CoTaskMemFree(v27[0]);
    return v9;
  }
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  return 0;
}

```

## disassembly

```asm
0x18000c2ac  mov     rax, rsp
0x18000c2af  mov     [rax+10h], rbx
0x18000c2b3  mov     [rax+18h], rsi
0x18000c2b7  mov     [rax+8], rcx
0x18000c2bb  push    rbp
0x18000c2bc  push    rdi
0x18000c2bd  push    r12
0x18000c2bf  push    r14
0x18000c2c1  push    r15
0x18000c2c3  lea     rbp, [rax-5Fh]
0x18000c2c7  sub     rsp, 0A0h
0x18000c2ce  mov     rax, [rdx]
0x18000c2d1  xor     r14d, r14d
0x18000c2d4  mov     rsi, rdx
0x18000c2d7  mov     [rbp+57h+var_60], r14
0x18000c2db  mov     dil, r8b
0x18000c2de  mov     [rbp+57h+var_7C], r14d
0x18000c2e2  lea     r8, [rbp+57h+pv]
0x18000c2e6  mov     [rbp+57h+var_38], r14
0x18000c2ea  mov     rax, [rax]
0x18000c2ed  lea     rdx, _GUID_27354133_7f64_5b0f_8f00_5d77afbe261e
0x18000c2f4  mov     rcx, rsi
0x18000c2f7  mov     [rbp+57h+var_70], r14d
0x18000c2fb  mov     [rbp+57h+var_30], r14
0x18000c2ff  mov     [rbp+57h+var_84], r14d
0x18000c303  mov     [rbp+57h+var_68], r14
0x18000c307  mov     [rbp+57h+var_80], r14d
0x18000c30b  mov     [rbp+57h+var_58], r14
0x18000c30f  mov     [rbp+57h+var_78], r14d
0x18000c313  mov     [rbp+57h+var_50], r14
0x18000c317  mov     [rbp+57h+var_74], r14d
0x18000c31b  mov     [rbp+57h+var_48], r14
0x18000c31f  mov     [rbp+57h+arg_18], r14d
0x18000c323  mov     [rbp+57h+var_40], r14
0x18000c327  mov     [rbp+57h+var_88], r14d
0x18000c32b  mov     [rbp+57h+pv], r14
0x18000c32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c334  test    eax, eax
0x18000c336  js      short loc_18000C36F
0x18000c338  mov     rcx, [rbp+57h+pv]; this
0x18000c33c  lea     rdx, [rbp+57h+arg_0]; struct IDiscRecorder2 *
0x18000c340  mov     byte ptr [rbp+57h+arg_0.lpVtbl], r14b
0x18000c344  call    ?IsRecorderSupported@Imapi2Utility@@YAJPEAUIDiscRecorder2@@PEAE@Z; Imapi2Utility::IsRecorderSupported(IDiscRecorder2 *,uchar *)
0x18000c349  test    eax, eax
0x18000c34b  js      short loc_18000C36F
0x18000c34d  cmp     byte ptr [rbp+57h+arg_0.lpVtbl], r14b
0x18000c351  jnz     short loc_18000C36F
0x18000c353  mov     rcx, [rbp+57h+pv]
0x18000c357  test    rcx, rcx
0x18000c35a  jz      short loc_18000C368
0x18000c35c  mov     rax, [rcx]
0x18000c35f  mov     rax, [rax+10h]
0x18000c363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c368  xor     al, al
0x18000c36a  jmp     loc_18000C71D
0x18000c36f  mov     rcx, [rbp+57h+pv]
0x18000c373  test    rcx, rcx
0x18000c376  jz      short loc_18000C384
0x18000c378  mov     rax, [rcx]
0x18000c37b  mov     rax, [rax+10h]
0x18000c37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c384  mov     rax, [rsi]
0x18000c387  lea     rcx, [rbp+57h+var_80]
0x18000c38b  xor     r8d, r8d
0x18000c38e  mov     [rsp+0C0h+var_A0], rcx
0x18000c393  lea     r9, [rbp+57h+var_68]
0x18000c397  mov     rcx, rsi
0x18000c39a  mov     rax, [rax+60h]
0x18000c39e  lea     edx, [r8+21h]
0x18000c3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3a7  mov     rax, [rsi]
0x18000c3aa  lea     rcx, [rbp+57h+var_7C]
0x18000c3ae  xor     r8d, r8d
0x18000c3b1  mov     [rsp+0C0h+var_A0], rcx
0x18000c3b6  lea     r9, [rbp+57h+var_60]
0x18000c3ba  mov     rcx, rsi
0x18000c3bd  mov     rax, [rax+60h]
0x18000c3c1  lea     edx, [r8+20h]
0x18000c3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ca  mov     rax, [rsi]
0x18000c3cd  lea     rcx, [rbp+57h+var_78]
0x18000c3d1  xor     r8d, r8d
0x18000c3d4  mov     [rsp+0C0h+var_A0], rcx
0x18000c3d9  lea     r9, [rbp+57h+var_58]
0x18000c3dd  mov     rcx, rsi
0x18000c3e0  mov     rax, [rax+60h]
0x18000c3e4  lea     edx, [r8+26h]
0x18000c3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ed  mov     rax, [rsi]
0x18000c3f0  lea     rcx, [rbp+57h+var_74]
0x18000c3f4  xor     r8d, r8d
0x18000c3f7  mov     [rsp+0C0h+var_A0], rcx
0x18000c3fc  lea     r9, [rbp+57h+var_50]
0x18000c400  mov     rcx, rsi
0x18000c403  mov     rax, [rax+60h]
0x18000c407  lea     edx, [r8+2Dh]
0x18000c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c410  mov     rax, [rsi]
0x18000c413  lea     rcx, [rbp+57h+arg_18]
0x18000c417  xor     r8d, r8d
0x18000c41a  mov     [rsp+0C0h+var_A0], rcx
0x18000c41f  lea     r9, [rbp+57h+var_48]
0x18000c423  mov     rcx, rsi
0x18000c426  mov     rax, [rax+60h]
0x18000c42a  lea     edx, [r8+2Ch]
0x18000c42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c433  mov     rax, [rsi]
0x18000c436  lea     rcx, [rbp+57h+var_88]
0x18000c43a  xor     r8d, r8d
0x18000c43d  mov     [rsp+0C0h+var_A0], rcx
0x18000c442  lea     r9, [rbp+57h+var_40]
0x18000c446  mov     rcx, rsi
0x18000c449  mov     rax, [rax+60h]
0x18000c44d  lea     edx, [r8+2Fh]
0x18000c451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c456  mov     rax, [rsi]
0x18000c459  lea     rcx, [rbp+57h+var_70]
0x18000c45d  xor     r8d, r8d
0x18000c460  mov     [rsp+0C0h+var_A0], rcx
0x18000c465  lea     r9, [rbp+57h+var_38]
0x18000c469  mov     rcx, rsi
0x18000c46c  mov     rax, [rax+60h]
0x18000c470  lea     edx, [r8+41h]
0x18000c474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c479  mov     rax, [rsi]
0x18000c47c  lea     rcx, [rbp+57h+var_84]
0x18000c480  xor     r8d, r8d
0x18000c483  mov     [rsp+0C0h+var_A0], rcx
0x18000c488  lea     r9, [rbp+57h+var_30]
0x18000c48c  mov     rcx, rsi
0x18000c48f  mov     rax, [rax+60h]
0x18000c493  lea     edx, [r8+2Ah]
0x18000c497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c49c  mov     rax, [rbp+57h+var_68]
0x18000c4a0  mov     bl, r14b
0x18000c4a3  mov     r15d, 1
0x18000c4a9  test    rax, rax
0x18000c4ac  jz      short loc_18000C4BC
0x18000c4ae  test    [rax+2], r15b
0x18000c4b2  jnz     short loc_18000C4B9
0x18000c4b4  test    dil, dil
0x18000c4b7  jnz     short loc_18000C4BC
0x18000c4b9  mov     bl, r15b
0x18000c4bc  mov     rdx, [rbp+57h+var_60]
0x18000c4c0  test    rdx, rdx
0x18000c4c3  jz      short loc_18000C4F8
0x18000c4c5  test    [rdx+2], r15b
0x18000c4c9  jnz     short loc_18000C4D0
0x18000c4cb  test    dil, dil
0x18000c4ce  jnz     short loc_18000C4F8
0x18000c4d0  movzx   eax, byte ptr [rdx+9]
0x18000c4d4  movzx   ecx, byte ptr [rdx+8]
0x18000c4d8  shl     ecx, 8
0x18000c4db  or      ecx, eax
0x18000c4dd  movzx   eax, byte ptr [rdx+0Ah]
0x18000c4e1  shl     ecx, 8
0x18000c4e4  or      ecx, eax
0x18000c4e6  movzx   eax, byte ptr [rdx+0Bh]
0x18000c4ea  shl     ecx, 8
0x18000c4ed  or      ecx, eax
0x18000c4ef  cmp     ecx, 800h
0x18000c4f5  setz    bl
0x18000c4f8  mov     rax, [rbp+57h+var_58]
0x18000c4fc  test    rax, rax
0x18000c4ff  jz      short loc_18000C50F
0x18000c501  test    [rax+2], r15b
0x18000c505  jnz     short loc_18000C50C
0x18000c507  test    dil, dil
0x18000c50a  jnz     short loc_18000C50F
0x18000c50c  mov     bl, r15b
0x18000c50f  mov     rax, [rbp+57h+var_50]
0x18000c513  test    rax, rax
0x18000c516  jz      short loc_18000C526
0x18000c518  test    [rax+2], r15b
0x18000c51c  jnz     short loc_18000C523
0x18000c51e  test    dil, dil
0x18000c521  jnz     short loc_18000C526
0x18000c523  mov     bl, r15b
0x18000c526  mov     rax, [rbp+57h+var_48]
0x18000c52a  test    rax, rax
0x18000c52d  jz      short loc_18000C54B
0x18000c52f  test    [rax+2], r15b
0x18000c533  jnz     short loc_18000C53A
0x18000c535  test    dil, dil
0x18000c538  jnz     short loc_18000C54B
0x18000c53a  cmp     [rbp+57h+arg_18], 8
0x18000c53e  jb      short loc_18000C54B
0x18000c540  test    [rax+4], r15b
0x18000c544  movzx   ebx, bl
0x18000c547  cmovnz  ebx, r15d
0x18000c54b  mov     rax, [rbp+57h+var_40]
0x18000c54f  test    rax, rax
0x18000c552  jz      short loc_18000C570
0x18000c554  test    [rax+2], r15b
0x18000c558  jnz     short loc_18000C55F
0x18000c55a  test    dil, dil
0x18000c55d  jnz     short loc_18000C570
0x18000c55f  cmp     [rbp+57h+var_88], 8
0x18000c563  jb      short loc_18000C570
0x18000c565  test    byte ptr [rax+4], 2
0x18000c569  movzx   ebx, bl
0x18000c56c  cmovnz  ebx, r15d
0x18000c570  mov     rax, [rbp+57h+var_38]
0x18000c574  test    rax, rax
0x18000c577  jz      short loc_18000C587
0x18000c579  test    [rax+2], r15b
0x18000c57d  jnz     short loc_18000C584
0x18000c57f  test    dil, dil
0x18000c582  jnz     short loc_18000C587
0x18000c584  mov     bl, r15b
0x18000c587  mov     rax, [rbp+57h+var_30]
0x18000c58b  test    rax, rax
0x18000c58e  jz      short loc_18000C5AF
0x18000c590  test    [rax+2], r15b
0x18000c594  jnz     short loc_18000C59B
0x18000c596  test    dil, dil
0x18000c599  jnz     short loc_18000C5AF
0x18000c59b  cmp     [rbp+57h+var_84], 0Ch
0x18000c59f  jb      short loc_18000C5AF
0x18000c5a1  test    [rax+4], r15b
0x18000c5a5  jz      short loc_18000C5AF
0x18000c5a7  mov     bl, r15b
0x18000c5aa  jmp     loc_18000C6CB
0x18000c5af  test    bl, bl
0x18000c5b1  jnz     loc_18000C6CB
0x18000c5b7  mov     [rbp+57h+pv], r14
0x18000c5bb  mov     dword ptr [rbp+57h+arg_0.lpVtbl], r14d
0x18000c5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c6  lea     r12, WPP_GLOBAL_Control
0x18000c5cd  mov     dil, 4
0x18000c5d0  cmp     rcx, r12
0x18000c5d3  jz      short loc_18000C5FF
0x18000c5d5  test    [rcx+10Ch], dil
0x18000c5dc  jz      short loc_18000C5FF
0x18000c5de  cmp     [rcx+109h], dil
0x18000c5e5  jb      short loc_18000C5FF
0x18000c5e7  mov     rcx, [rcx+100h]
0x18000c5ee  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18000c5f5  mov     edx, 2Eh ; '.'
0x18000c5fa  call    WPP_SF_
0x18000c5ff  mov     rax, [rsi]
0x18000c602  lea     rcx, [rbp+57h+arg_0]
0x18000c606  xor     r8d, r8d
0x18000c609  mov     [rsp+0C0h+var_A0], rcx
0x18000c60e  lea     r9, [rbp+57h+pv]
0x18000c612  mov     rcx, rsi
0x18000c615  mov     rax, [rax+68h]
0x18000c619  lea     edx, [r8+2Ah]
0x18000c61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c622  test    eax, eax
0x18000c624  js      loc_18000C6CB
0x18000c62a  mov     eax, dword ptr [rbp+57h+arg_0.lpVtbl]
0x18000c62d  cmp     eax, 0Ch
0x18000c630  jnb     short loc_18000C67B
0x18000c632  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c639  cmp     rcx, r12
0x18000c63c  jz      short loc_18000C670
0x18000c63e  test    [rcx+10Ch], dil
0x18000c645  jz      short loc_18000C670
0x18000c647  cmp     byte ptr [rcx+109h], 3
0x18000c64e  jb      short loc_18000C670
0x18000c650  mov     rcx, [rcx+100h]
0x18000c657  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18000c65e  mov     edx, 22h ; '"'
0x18000c663  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000c667  lea     r9d, [rdx-16h]
0x18000c66b  call    WPP_SF_Dd
0x18000c670  mov     rcx, [rbp+57h+pv]
0x18000c674  test    rcx, rcx
0x18000c677  jnz     short loc_18000C6C5
0x18000c679  jmp     short loc_18000C6CB
0x18000c67b  mov     rax, [rbp+57h+pv]
0x18000c67f  test    byte ptr [rax+3], 2
0x18000c683  jz      short loc_18000C6C2
0x18000c685  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c68c  cmp     rcx, r12
0x18000c68f  jz      short loc_18000C6BF
0x18000c691  test    [rcx+10Ch], dil
0x18000c698  jz      short loc_18000C6BF
0x18000c69a  cmp     [rcx+109h], dil
0x18000c6a1  jb      short loc_18000C6BF
0x18000c6a3  mov     rcx, [rcx+100h]
0x18000c6aa  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18000c6b1  mov     edx, 2Fh ; '/'
0x18000c6b6  call    WPP_SF_
0x18000c6bb  mov     rax, [rbp+57h+pv]
0x18000c6bf  mov     bl, r15b
0x18000c6c2  mov     rcx, rax; pv
0x18000c6c5  call    cs:__imp_CoTaskMemFree
0x18000c6cb  mov     rcx, [rbp+57h+var_68]; pv
0x18000c6cf  call    cs:__imp_CoTaskMemFree
0x18000c6d5  mov     rcx, [rbp+57h+var_60]; pv
0x18000c6d9  call    cs:__imp_CoTaskMemFree
0x18000c6df  mov     rcx, [rbp+57h+var_58]; pv
0x18000c6e3  call    cs:__imp_CoTaskMemFree
0x18000c6e9  mov     rcx, [rbp+57h+var_50]; pv
0x18000c6ed  call    cs:__imp_CoTaskMemFree
0x18000c6f3  mov     rcx, [rbp+57h+var_48]; pv
0x18000c6f7  call    cs:__imp_CoTaskMemFree
0x18000c6fd  mov     rcx, [rbp+57h+var_40]; pv
  ... truncated ...
```
