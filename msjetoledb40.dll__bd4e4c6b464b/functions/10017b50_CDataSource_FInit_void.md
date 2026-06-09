# CDataSource::FInit(void)

- ea: `0x10017b50`
- end: `0x10018215`
- name: `?FInit@CDataSource@@QAEJXZ`
- size: `1733`
- prototype: `int __thiscall(CDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1000fa40`

## callees

- `0x1000ba90`
- `0x10017b50`
- `0x1001c6d0`
- `0x100204c0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10017b9d`
- `KERNEL32!LeaveCriticalSection` at `0x10017ef6`
- `KERNEL32!LeaveCriticalSection` at `0x100181db`
- `KERNEL32!LeaveCriticalSection` at `0x10018209`
- `KERNEL32!LeaveCriticalSection` at `0x10017b9d`
- `KERNEL32!LeaveCriticalSection` at `0x10017ef6`
- `KERNEL32!LeaveCriticalSection` at `0x100181db`
- `KERNEL32!LeaveCriticalSection` at `0x10018209`
- `KERNEL32!EnterCriticalSection` at `0x10017b8b`
- `KERNEL32!EnterCriticalSection` at `0x10017e9e`
- `KERNEL32!EnterCriticalSection` at `0x10017b8b`
- `KERNEL32!EnterCriticalSection` at `0x10017e9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10017ee4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10017ee4`

## pseudocode

```c
HRESULT __thiscall CDataSource::FInit(CDataSource *this)
{
  CDataSource *v1; // edi
  struct _RTL_CRITICAL_SECTION *v2; // esi
  _DWORD *v3; // eax
  _DWORD *v4; // eax
  _DWORD *v5; // eax
  _DWORD *v6; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // eax
  _DWORD *v11; // eax
  _DWORD *v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // eax
  struct _RTL_CRITICAL_SECTION *v15; // eax
  int v16; // eax
  _DWORD *v17; // eax
  _DWORD *v18; // eax
  _DWORD *v19; // eax
  _DWORD *v20; // eax
  _DWORD *v21; // eax
  _DWORD *v22; // eax
  _DWORD *v23; // eax
  _DWORD *v24; // eax
  _DWORD *v25; // eax
  _DWORD *v26; // eax
  _DWORD *v27; // eax
  _DWORD *v28; // eax
  _DWORD *v29; // eax
  HRESULT v30; // edi
  void *v32; // [esp-4h] [ebp-44h]
  void *v33; // [esp-4h] [ebp-44h]
  void *v34; // [esp-4h] [ebp-44h]
  void *v35; // [esp-4h] [ebp-44h]
  void *v36; // [esp-4h] [ebp-44h]
  void *v37; // [esp-4h] [ebp-44h]
  void *v38; // [esp-4h] [ebp-44h]
  void *v39; // [esp-4h] [ebp-44h]
  void *v40; // [esp-4h] [ebp-44h]
  void *v41; // [esp-4h] [ebp-44h]
  void *v42; // [esp-4h] [ebp-44h]
  void *v43; // [esp-4h] [ebp-44h]
  void *v44; // [esp-4h] [ebp-44h]
  _DWORD v45[6]; // [esp+Ch] [ebp-34h] BYREF
  struct _RTL_CRITICAL_SECTION *v46; // [esp+24h] [ebp-1Ch]
  _DWORD *v47; // [esp+28h] [ebp-18h] BYREF
  CDataSource *v48; // [esp+2Ch] [ebp-14h]
  HRESULT Instance; // [esp+30h] [ebp-10h]
  int v50; // [esp+3Ch] [ebp-4h]

  v1 = this;
  v48 = this;
  v2 = 0;
  v46 = 0;
  v50 = 0;
  EnterCriticalSection(&g_CriticalSection);
  _InterlockedIncrement(&g_cObj);
  LeaveCriticalSection(&g_CriticalSection);
  Instance = CSettableProperties::FInit((CDataSource *)((char *)v1 + 152));
  if ( Instance < 0 )
    goto LABEL_64;
  v47 = (_DWORD *)*((_DWORD *)v1 + 40);
  Instance = (*(int (__thiscall **)(_DWORD *, const struct DBInfoProps *const *, int, int, unsigned int, _DWORD, _DWORD, _DWORD))(*v47 + 4))(
               v47,
               &rgDBInfoProps,
               57,
               11,
               DBPROPSET_DBINIT.Data1,
               *(_DWORD *)&DBPROPSET_DBINIT.Data2,
               *(_DWORD *)DBPROPSET_DBINIT.Data4,
               *(_DWORD *)&DBPROPSET_DBINIT.Data4[4]);
  if ( Instance < 0 )
    goto LABEL_63;
  v47 = (_DWORD *)*((_DWORD *)v48 + 41);
  v1 = v48;
  Instance = (*(int (__thiscall **)(_DWORD *, const struct DBInfoProps *const *, int, int, int, int, int, int))(*v47 + 4))(
               v47,
               &rgDBInfoProps,
               186,
               14,
               -2100330154,
               298883904,
               -1073693282,
               -524107185);
  if ( Instance >= 0 )
  {
    *((_DWORD *)v48 + 20) = v48;
    *((_DWORD *)v1 + 22) = v1;
    if ( !*((_DWORD *)v1 + 3) )
    {
      v3 = operator new(0xCu);
      v47 = v3;
      if ( !v3 )
      {
        *((_DWORD *)v1 + 3) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v3 = &CImpIDBCreateSession::`vftable';
      v3[1] = 0;
      v3[2] = v1;
      *((_DWORD *)v1 + 3) = v3;
    }
    if ( !*((_DWORD *)v1 + 4) )
    {
      v4 = operator new(0xCu);
      v47 = v4;
      if ( !v4 )
      {
        *((_DWORD *)v1 + 4) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v4 = &CImpIDBInitialize::`vftable';
      v4[1] = 0;
      v4[2] = v1;
      *((_DWORD *)v1 + 4) = v4;
    }
    if ( !*((_DWORD *)v1 + 5) )
    {
      v5 = operator new(0xCu);
      v47 = v5;
      if ( !v5 )
      {
        *((_DWORD *)v1 + 5) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v5 = &CImpIDBProperties::`vftable';
      v5[1] = 0;
      v5[2] = v1;
      *((_DWORD *)v1 + 5) = v5;
    }
    if ( !*((_DWORD *)v1 + 6) )
    {
      v6 = operator new(0xCu);
      v47 = v6;
      if ( !v6 )
      {
        *((_DWORD *)v1 + 6) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v6 = &CImpIDBDataSourceAdmin::`vftable';
      v6[1] = 0;
      v6[2] = v1;
      *((_DWORD *)v1 + 6) = v6;
    }
    if ( !*((_DWORD *)v1 + 7) )
    {
      v7 = operator new(0xCu);
      v47 = v7;
      if ( !v7 )
      {
        *((_DWORD *)v1 + 7) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v7 = &CImpIDBInfo::`vftable';
      v7[1] = 0;
      v7[2] = v1;
      *((_DWORD *)v1 + 7) = v7;
    }
    if ( !*((_DWORD *)v1 + 8) )
    {
      v8 = operator new(0xCu);
      v47 = v8;
      if ( !v8 )
      {
        *((_DWORD *)v1 + 8) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v8 = &CImpIPersist::`vftable';
      v8[1] = 0;
      v8[2] = v1;
      *((_DWORD *)v1 + 8) = v8;
    }
    if ( !*((_DWORD *)v1 + 9) )
    {
      v9 = operator new(0xCu);
      v47 = v9;
      if ( !v9 )
      {
        *((_DWORD *)v1 + 9) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v9 = &CImpIJetCompact::`vftable';
      v9[1] = 0;
      v9[2] = v1;
      *((_DWORD *)v1 + 9) = v9;
    }
    if ( !*((_DWORD *)v1 + 10) )
    {
      v10 = operator new(0xCu);
      v47 = v10;
      if ( !v10 )
      {
        *((_DWORD *)v1 + 10) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v10 = &CImpIWrapJetTokens::`vftable';
      v10[1] = 0;
      v10[2] = v1;
      *((_DWORD *)v1 + 10) = v10;
    }
    if ( !*((_DWORD *)v1 + 11) )
    {
      v11 = operator new(0xCu);
      v47 = v11;
      if ( !v11 )
      {
        *((_DWORD *)v1 + 11) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v11 = &CImpIWrapJetInstance::`vftable';
      v11[1] = 0;
      v11[2] = v1;
      *((_DWORD *)v1 + 11) = v11;
    }
    if ( !*((_DWORD *)v1 + 12) )
    {
      v12 = operator new(0xCu);
      v47 = v12;
      if ( !v12 )
      {
        *((_DWORD *)v1 + 12) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v12 = &CImpITrusteeAdmin::`vftable';
      v12[1] = 0;
      v12[2] = v1;
      *((_DWORD *)v1 + 12) = v12;
    }
    if ( !*((_DWORD *)v1 + 13) )
    {
      v13 = operator new(0xCu);
      v47 = v13;
      if ( !v13 )
      {
        *((_DWORD *)v1 + 13) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v13 = &CImpITrusteeGroupAdmin::`vftable';
      v13[1] = 0;
      v13[2] = v1;
      *((_DWORD *)v1 + 13) = v13;
    }
    if ( !*((_DWORD *)v1 + 14) )
    {
      v14 = operator new(0xCu);
      v47 = v14;
      if ( !v14 )
      {
        *((_DWORD *)v1 + 14) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      *v14 = &CImpISecurityInfo::`vftable';
      v14[1] = 0;
      v14[2] = v1;
      *((_DWORD *)v1 + 14) = v14;
    }
    if ( !*((_DWORD *)v1 + 15) )
    {
      v15 = (struct _RTL_CRITICAL_SECTION *)operator new(0xCu);
      v46 = v15;
      if ( !v15 )
      {
        *((_DWORD *)v1 + 15) = 0;
        Instance = -2147467259;
        goto LABEL_64;
      }
      v15->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpIObjectAccessControl::`vftable';
      v15->LockCount = 0;
      v15->RecursionCount = (LONG)v1;
      *((_DWORD *)v1 + 15) = v15;
    }
    v2 = &g_CriticalSection;
    v46 = &g_CriticalSection;
    EnterCriticalSection(&g_CriticalSection);
    if ( g_pIDataConvert )
    {
      (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)g_pIDataConvert + 4))(
        *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 4),
        g_pIDataConvert);
    }
    else
    {
      v47 = 0;
      v45[0] = 1;
      v45[2] = 19;
      v45[3] = 0;
      v45[4] = 512;
      v45[5] = 0;
      Instance = CoCreateInstance(&CLSID_OLEDB_CONVERSIONLIBRARY, 0, 1u, &IID_IDataConvert, &g_pIDataConvert);
      if ( Instance < 0 )
      {
        LeaveCriticalSection(&g_CriticalSection);
        v2 = 0;
        goto LABEL_64;
      }
      Instance = (**(int (__thiscall ***)(_DWORD, LPVOID, GUID *, _DWORD **))g_pIDataConvert)(
                   **(_DWORD **)g_pIDataConvert,
                   g_pIDataConvert,
                   &IID_IDCInfo,
                   &v47);
      if ( Instance < 0 )
        goto LABEL_63;
      v16 = (*(int (__thiscall **)(_DWORD, _DWORD *, int, _DWORD *))(*v47 + 16))(*(_DWORD *)(*v47 + 16), v47, 1, v45);
      Instance = v16;
      if ( v47 )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD *))(*v47 + 8))(*(_DWORD *)(*v47 + 8), v47);
        v16 = Instance;
      }
      if ( v16 < 0 )
      {
LABEL_63:
        v1 = v48;
        goto LABEL_64;
      }
    }
    LeaveCriticalSection(&g_CriticalSection);
    v2 = 0;
    v30 = 0;
    goto LABEL_91;
  }
LABEL_64:
  v17 = (_DWORD *)*((_DWORD *)v1 + 3);
  if ( v17 )
  {
    v32 = (void *)*((_DWORD *)v1 + 3);
    *v17 = &CImpIDBCreateSession::`vftable';
    operator delete(v32);
    *((_DWORD *)v1 + 3) = 0;
  }
  v18 = (_DWORD *)*((_DWORD *)v1 + 4);
  if ( v18 )
  {
    v33 = (void *)*((_DWORD *)v1 + 4);
    *v18 = &CImpIDBInitialize::`vftable';
    operator delete(v33);
    *((_DWORD *)v1 + 4) = 0;
  }
  v19 = (_DWORD *)*((_DWORD *)v1 + 5);
  if ( v19 )
  {
    v34 = (void *)*((_DWORD *)v1 + 5);
    *v19 = &CImpIDBProperties::`vftable';
    operator delete(v34);
    *((_DWORD *)v1 + 5) = 0;
  }
  v20 = (_DWORD *)*((_DWORD *)v1 + 6);
  if ( v20 )
  {
    v35 = (void *)*((_DWORD *)v1 + 6);
    *v20 = &CImpIDBDataSourceAdmin::`vftable';
    operator delete(v35);
    *((_DWORD *)v1 + 6) = 0;
  }
  v21 = (_DWORD *)*((_DWORD *)v1 + 7);
  if ( v21 )
  {
    v36 = (void *)*((_DWORD *)v1 + 7);
    *v21 = &CImpIDBInfo::`vftable';
    operator delete(v36);
    *((_DWORD *)v1 + 7) = 0;
  }
  v22 = (_DWORD *)*((_DWORD *)v1 + 8);
  if ( v22 )
  {
    v37 = (void *)*((_DWORD *)v1 + 8);
    *v22 = &CImpIPersist::`vftable';
    operator delete(v37);
    *((_DWORD *)v1 + 8) = 0;
  }
  v23 = (_DWORD *)*((_DWORD *)v1 + 9);
  if ( v23 )
  {
    v38 = (void *)*((_DWORD *)v1 + 9);
    *v23 = &CImpIJetCompact::`vftable';
    operator delete(v38);
    *((_DWORD *)v1 + 9) = 0;
  }
  v24 = (_DWORD *)*((_DWORD *)v1 + 10);
  if ( v24 )
  {
    v39 = (void *)*((_DWORD *)v1 + 10);
    *v24 = &CImpIWrapJetTokens::`vftable';
    operator delete(v39);
    *((_DWORD *)v1 + 10) = 0;
  }
  v25 = (_DWORD *)*((_DWORD *)v1 + 11);
  if ( v25 )
  {
    v40 = (void *)*((_DWORD *)v1 + 11);
    *v25 = &CImpIWrapJetInstance::`vftable';
    operator delete(v40);
    *((_DWORD *)v1 + 11) = 0;
  }
  v26 = (_DWORD *)*((_DWORD *)v1 + 12);
  if ( v26 )
  {
    v41 = (void *)*((_DWORD *)v1 + 12);
    *v26 = &CImpITrusteeAdmin::`vftable';
    operator delete(v41);
    *((_DWORD *)v1 + 12) = 0;
  }
  v27 = (_DWORD *)*((_DWORD *)v1 + 13);
  if ( v27 )
  {
    v42 = (void *)*((_DWORD *)v1 + 13);
    *v27 = &CImpITrusteeGroupAdmin::`vftable';
    operator delete(v42);
    *((_DWORD *)v1 + 13) = 0;
  }
  v28 = (_DWORD *)*((_DWORD *)v1 + 14);
  if ( v28 )
  {
    v43 = (void *)*((_DWORD *)v1 + 14);
    *v28 = &CImpISecurityInfo::`vftable';
    operator delete(v43);
    *((_DWORD *)v1 + 14) = 0;
  }
  v29 = (_DWORD *)*((_DWORD *)v1 + 15);
  if ( v29 )
  {
    v44 = (void *)*((_DWORD *)v1 + 15);
    *v29 = &CImpIObjectAccessControl::`vftable';
    operator delete(v44);
    *((_DWORD *)v1 + 15) = 0;
  }
  v30 = Instance;
LABEL_91:
  if ( v2 )
    LeaveCriticalSection(v2);
  return v30;
}

```

## disassembly

```asm
0x10017b50  mov     edi, edi
0x10017b52  push    ebp
0x10017b53  mov     ebp, esp
0x10017b55  push    0FFFFFFFFh
0x10017b57  push    offset ?FInit@CDataSource@@QAEJXZ_SEH
0x10017b5c  mov     eax, large fs:0
0x10017b62  push    eax
0x10017b63  sub     esp, 28h
0x10017b66  push    esi
0x10017b67  push    edi
0x10017b68  mov     eax, ___security_cookie
0x10017b6d  xor     eax, ebp
0x10017b6f  push    eax
0x10017b70  lea     eax, [ebp+var_C]
0x10017b73  mov     large fs:0, eax
0x10017b79  mov     edi, ecx
0x10017b7b  mov     [ebp+var_14], edi
0x10017b7e  xor     esi, esi
0x10017b80  mov     [ebp+var_1C], esi
0x10017b83  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017b88  mov     [ebp+var_4], esi
0x10017b8b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10017b91  lock inc ?g_cObj@@3JA; long g_cObj
0x10017b98  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017b9d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10017ba3  lea     ecx, [edi+98h]; this
0x10017ba9  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x10017bae  mov     [ebp+var_10], eax
0x10017bb1  test    eax, eax
0x10017bb3  js      loc_1001805A
0x10017bb9  mov     eax, [edi+0A0h]
0x10017bbf  sub     esp, 10h
0x10017bc2  movups  xmm0, xmmword ptr ds:_DBPROPSET_DBINIT.Data1
0x10017bc9  mov     [ebp+var_18], eax
0x10017bcc  mov     eax, [eax]
0x10017bce  mov     edi, [eax+4]
0x10017bd1  mov     eax, esp
0x10017bd3  push    0Bh
0x10017bd5  push    39h ; '9'
0x10017bd7  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10017bdc  mov     ecx, edi
0x10017bde  movups  xmmword ptr [eax], xmm0
0x10017be1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10017be7  mov     ecx, [ebp+var_18]
0x10017bea  call    edi
0x10017bec  mov     [ebp+var_10], eax
0x10017bef  test    eax, eax
0x10017bf1  js      loc_10018057
0x10017bf7  mov     eax, [ebp+var_14]
0x10017bfa  sub     esp, 10h
0x10017bfd  movups  xmm0, ds:xmmword_10004DF0
0x10017c04  mov     eax, [eax+0A4h]
0x10017c0a  mov     [ebp+var_18], eax
0x10017c0d  mov     eax, [eax]
0x10017c0f  mov     edi, [eax+4]
0x10017c12  mov     eax, esp
0x10017c14  push    0Eh
0x10017c16  push    0BAh
0x10017c1b  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; DBInfoProps const * const rgDBInfoProps
0x10017c20  mov     ecx, edi
0x10017c22  movups  xmmword ptr [eax], xmm0
0x10017c25  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10017c2b  mov     ecx, [ebp+var_18]
0x10017c2e  call    edi
0x10017c30  mov     edi, [ebp+var_14]
0x10017c33  mov     [ebp+var_10], eax
0x10017c36  test    eax, eax
0x10017c38  js      loc_1001805A
0x10017c3e  mov     [edi+50h], edi
0x10017c41  mov     [edi+58h], edi
0x10017c44  cmp     [edi+0Ch], esi
0x10017c47  jnz     short loc_10017C6D
0x10017c49  push    0Ch; Size
0x10017c4b  call    ??2@YAPAXI@Z; operator new(uint)
0x10017c50  add     esp, 4
0x10017c53  mov     [ebp+var_18], eax
0x10017c56  test    eax, eax
0x10017c58  jz      loc_10017F03
0x10017c5e  mov     dword ptr [eax], offset ??_7CImpIDBCreateSession@@6B@; const CImpIDBCreateSession::`vftable'
0x10017c64  mov     [eax+4], esi
0x10017c67  mov     [eax+8], edi
0x10017c6a  mov     [edi+0Ch], eax
0x10017c6d  cmp     dword ptr [edi+10h], 0
0x10017c71  jnz     short loc_10017C9B
0x10017c73  push    0Ch; Size
0x10017c75  call    ??2@YAPAXI@Z; operator new(uint)
0x10017c7a  add     esp, 4
0x10017c7d  mov     [ebp+var_18], eax
0x10017c80  test    eax, eax
0x10017c82  jz      loc_10017F16
0x10017c88  mov     dword ptr [eax], offset ??_7CImpIDBInitialize@@6B@; const CImpIDBInitialize::`vftable'
0x10017c8e  mov     dword ptr [eax+4], 0
0x10017c95  mov     [eax+8], edi
0x10017c98  mov     [edi+10h], eax
0x10017c9b  cmp     dword ptr [edi+14h], 0
0x10017c9f  jnz     short loc_10017CC9
0x10017ca1  push    0Ch; Size
0x10017ca3  call    ??2@YAPAXI@Z; operator new(uint)
0x10017ca8  add     esp, 4
0x10017cab  mov     [ebp+var_18], eax
0x10017cae  test    eax, eax
0x10017cb0  jz      loc_10017F29
0x10017cb6  mov     dword ptr [eax], offset ??_7CImpIDBProperties@@6B@; const CImpIDBProperties::`vftable'
0x10017cbc  mov     dword ptr [eax+4], 0
0x10017cc3  mov     [eax+8], edi
0x10017cc6  mov     [edi+14h], eax
0x10017cc9  cmp     dword ptr [edi+18h], 0
0x10017ccd  jnz     short loc_10017CF7
0x10017ccf  push    0Ch; Size
0x10017cd1  call    ??2@YAPAXI@Z; operator new(uint)
0x10017cd6  add     esp, 4
0x10017cd9  mov     [ebp+var_18], eax
0x10017cdc  test    eax, eax
0x10017cde  jz      loc_10017F3C
0x10017ce4  mov     dword ptr [eax], offset ??_7CImpIDBDataSourceAdmin@@6B@; const CImpIDBDataSourceAdmin::`vftable'
0x10017cea  mov     dword ptr [eax+4], 0
0x10017cf1  mov     [eax+8], edi
0x10017cf4  mov     [edi+18h], eax
0x10017cf7  cmp     dword ptr [edi+1Ch], 0
0x10017cfb  jnz     short loc_10017D25
0x10017cfd  push    0Ch; Size
0x10017cff  call    ??2@YAPAXI@Z; operator new(uint)
0x10017d04  add     esp, 4
0x10017d07  mov     [ebp+var_18], eax
0x10017d0a  test    eax, eax
0x10017d0c  jz      loc_10017F4F
0x10017d12  mov     dword ptr [eax], offset ??_7CImpIDBInfo@@6B@; const CImpIDBInfo::`vftable'
0x10017d18  mov     dword ptr [eax+4], 0
0x10017d1f  mov     [eax+8], edi
0x10017d22  mov     [edi+1Ch], eax
0x10017d25  cmp     dword ptr [edi+20h], 0
0x10017d29  jnz     short loc_10017D53
0x10017d2b  push    0Ch; Size
0x10017d2d  call    ??2@YAPAXI@Z; operator new(uint)
0x10017d32  add     esp, 4
0x10017d35  mov     [ebp+var_18], eax
0x10017d38  test    eax, eax
0x10017d3a  jz      loc_10017F62
0x10017d40  mov     dword ptr [eax], offset ??_7CImpIPersist@@6B@; const CImpIPersist::`vftable'
0x10017d46  mov     dword ptr [eax+4], 0
0x10017d4d  mov     [eax+8], edi
0x10017d50  mov     [edi+20h], eax
0x10017d53  cmp     dword ptr [edi+24h], 0
0x10017d57  jnz     short loc_10017D81
0x10017d59  push    0Ch; Size
0x10017d5b  call    ??2@YAPAXI@Z; operator new(uint)
0x10017d60  add     esp, 4
0x10017d63  mov     [ebp+var_18], eax
0x10017d66  test    eax, eax
0x10017d68  jz      loc_10017F75
0x10017d6e  mov     dword ptr [eax], offset ??_7CImpIJetCompact@@6B@; const CImpIJetCompact::`vftable'
0x10017d74  mov     dword ptr [eax+4], 0
0x10017d7b  mov     [eax+8], edi
0x10017d7e  mov     [edi+24h], eax
0x10017d81  cmp     dword ptr [edi+28h], 0
0x10017d85  jnz     short loc_10017DAF
0x10017d87  push    0Ch; Size
0x10017d89  call    ??2@YAPAXI@Z; operator new(uint)
0x10017d8e  add     esp, 4
0x10017d91  mov     [ebp+var_18], eax
0x10017d94  test    eax, eax
0x10017d96  jz      loc_10017F88
0x10017d9c  mov     dword ptr [eax], offset ??_7CImpIWrapJetTokens@@6B@; const CImpIWrapJetTokens::`vftable'
0x10017da2  mov     dword ptr [eax+4], 0
0x10017da9  mov     [eax+8], edi
0x10017dac  mov     [edi+28h], eax
0x10017daf  cmp     dword ptr [edi+2Ch], 0
0x10017db3  jnz     short loc_10017DDD
0x10017db5  push    0Ch; Size
0x10017db7  call    ??2@YAPAXI@Z; operator new(uint)
0x10017dbc  add     esp, 4
0x10017dbf  mov     [ebp+var_18], eax
0x10017dc2  test    eax, eax
0x10017dc4  jz      loc_10017F9B
0x10017dca  mov     dword ptr [eax], offset ??_7CImpIWrapJetInstance@@6B@; const CImpIWrapJetInstance::`vftable'
0x10017dd0  mov     dword ptr [eax+4], 0
0x10017dd7  mov     [eax+8], edi
0x10017dda  mov     [edi+2Ch], eax
0x10017ddd  cmp     dword ptr [edi+30h], 0
0x10017de1  jnz     short loc_10017E0B
0x10017de3  push    0Ch; Size
0x10017de5  call    ??2@YAPAXI@Z; operator new(uint)
0x10017dea  add     esp, 4
0x10017ded  mov     [ebp+var_18], eax
0x10017df0  test    eax, eax
0x10017df2  jz      loc_10017FAE
0x10017df8  mov     dword ptr [eax], offset ??_7CImpITrusteeAdmin@@6B@; const CImpITrusteeAdmin::`vftable'
0x10017dfe  mov     dword ptr [eax+4], 0
0x10017e05  mov     [eax+8], edi
0x10017e08  mov     [edi+30h], eax
0x10017e0b  cmp     dword ptr [edi+34h], 0
0x10017e0f  jnz     short loc_10017E39
0x10017e11  push    0Ch; Size
0x10017e13  call    ??2@YAPAXI@Z; operator new(uint)
0x10017e18  add     esp, 4
0x10017e1b  mov     [ebp+var_18], eax
0x10017e1e  test    eax, eax
0x10017e20  jz      loc_10017FC1
0x10017e26  mov     dword ptr [eax], offset ??_7CImpITrusteeGroupAdmin@@6B@; const CImpITrusteeGroupAdmin::`vftable'
0x10017e2c  mov     dword ptr [eax+4], 0
0x10017e33  mov     [eax+8], edi
0x10017e36  mov     [edi+34h], eax
0x10017e39  cmp     dword ptr [edi+38h], 0
0x10017e3d  jnz     short loc_10017E67
0x10017e3f  push    0Ch; Size
0x10017e41  call    ??2@YAPAXI@Z; operator new(uint)
0x10017e46  add     esp, 4
0x10017e49  mov     [ebp+var_18], eax
0x10017e4c  test    eax, eax
0x10017e4e  jz      loc_10017FD4
0x10017e54  mov     dword ptr [eax], offset ??_7CImpISecurityInfo@@6B@; const CImpISecurityInfo::`vftable'
0x10017e5a  mov     dword ptr [eax+4], 0
0x10017e61  mov     [eax+8], edi
0x10017e64  mov     [edi+38h], eax
0x10017e67  cmp     dword ptr [edi+3Ch], 0
0x10017e6b  jnz     short loc_10017E95
0x10017e6d  push    0Ch; Size
0x10017e6f  call    ??2@YAPAXI@Z; operator new(uint)
0x10017e74  add     esp, 4
0x10017e77  mov     [ebp+var_1C], eax
0x10017e7a  test    eax, eax
0x10017e7c  jz      loc_10017FE4
0x10017e82  mov     dword ptr [eax], offset ??_7CImpIObjectAccessControl@@6B@; const CImpIObjectAccessControl::`vftable'
0x10017e88  mov     dword ptr [eax+4], 0
0x10017e8f  mov     [eax+8], edi
0x10017e92  mov     [edi+3Ch], eax
0x10017e95  mov     esi, offset ?g_CriticalSection@@3VCriticalSection@@A; CriticalSection g_CriticalSection
0x10017e9a  push    esi; lpCriticalSection
0x10017e9b  mov     [ebp+var_1C], esi
0x10017e9e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10017ea4  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x10017eaa  test    ecx, ecx
0x10017eac  jnz     loc_100181F4
0x10017eb2  push    offset ?g_pIDataConvert@@3PAUIDataConvert@@A; ppv
0x10017eb7  push    offset _IID_IDataConvert; riid
0x10017ebc  xor     eax, eax
0x10017ebe  mov     [ebp+var_18], ecx
0x10017ec1  push    1; dwClsContext
0x10017ec3  push    eax; pUnkOuter
0x10017ec4  push    offset ?CLSID_OLEDB_CONVERSIONLIBRARY@@3U_GUID@@B; rclsid
0x10017ec9  mov     [ebp+var_34], 1
0x10017ed0  mov     [ebp+var_2C], 13h
0x10017ed7  mov     [ebp+var_28], eax
0x10017eda  mov     [ebp+var_24], 200h
0x10017ee1  mov     [ebp+var_20], eax
0x10017ee4  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10017eea  mov     [ebp+var_10], eax
0x10017eed  test    eax, eax
0x10017eef  jns     loc_10017FF4
0x10017ef5  push    esi; lpCriticalSection
0x10017ef6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10017efc  xor     esi, esi
0x10017efe  jmp     loc_1001805A
0x10017f03  mov     dword ptr [edi+0Ch], 0
0x10017f0a  mov     [ebp+var_10], 80004005h
0x10017f11  jmp     loc_1001805A
0x10017f16  mov     dword ptr [edi+10h], 0
0x10017f1d  mov     [ebp+var_10], 80004005h
0x10017f24  jmp     loc_1001805A
0x10017f29  mov     dword ptr [edi+14h], 0
0x10017f30  mov     [ebp+var_10], 80004005h
0x10017f37  jmp     loc_1001805A
0x10017f3c  mov     dword ptr [edi+18h], 0
0x10017f43  mov     [ebp+var_10], 80004005h
0x10017f4a  jmp     loc_1001805A
0x10017f4f  mov     dword ptr [edi+1Ch], 0
0x10017f56  mov     [ebp+var_10], 80004005h
0x10017f5d  jmp     loc_1001805A
0x10017f62  mov     dword ptr [edi+20h], 0
0x10017f69  mov     [ebp+var_10], 80004005h
0x10017f70  jmp     loc_1001805A
0x10017f75  mov     dword ptr [edi+24h], 0
0x10017f7c  mov     [ebp+var_10], 80004005h
0x10017f83  jmp     loc_1001805A
0x10017f88  mov     dword ptr [edi+28h], 0
0x10017f8f  mov     [ebp+var_10], 80004005h
0x10017f96  jmp     loc_1001805A
0x10017f9b  mov     dword ptr [edi+2Ch], 0
0x10017fa2  mov     [ebp+var_10], 80004005h
0x10017fa9  jmp     loc_1001805A
0x10017fae  mov     dword ptr [edi+30h], 0
0x10017fb5  mov     [ebp+var_10], 80004005h
0x10017fbc  jmp     loc_1001805A
0x10017fc1  mov     dword ptr [edi+34h], 0
0x10017fc8  mov     [ebp+var_10], 80004005h
0x10017fcf  jmp     loc_1001805A
0x10017fd4  mov     dword ptr [edi+38h], 0
0x10017fdb  mov     [ebp+var_10], 80004005h
0x10017fe2  jmp     short loc_1001805A
0x10017fe4  mov     dword ptr [edi+3Ch], 0
0x10017feb  mov     [ebp+var_10], 80004005h
0x10017ff2  jmp     short loc_1001805A
0x10017ff4  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x10017ffa  mov     eax, [ecx]
0x10017ffc  mov     edi, [eax]
0x10017ffe  lea     eax, [ebp+var_18]
0x10018001  push    eax
0x10018002  push    offset _IID_IDCInfo
0x10018007  push    ecx
0x10018008  mov     ecx, edi
  ... truncated ...
```
