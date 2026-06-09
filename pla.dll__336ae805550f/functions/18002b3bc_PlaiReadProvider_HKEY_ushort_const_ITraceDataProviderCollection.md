# PlaiReadProvider(HKEY__ *,ushort const *,ITraceDataProviderCollection *)

- ea: `0x18002b3bc`
- end: `0x18002bd15`
- name: `?PlaiReadProvider@@YAJPEAUHKEY__@@PEBGPEAUITraceDataProviderCollection@@@Z`
- size: `2393`
- prototype: `int(HKEY, const unsigned __int16 *, struct ITraceDataProviderCollection *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029388`

## callees

- `0x180002bd0`
- `0x180002ee4`
- `0x180004e98`
- `0x18002b3a0`
- `0x18002b3bc`
- `0x18002d17c`
- `0x18002d37c`
- `0x18002d558`
- `0x18002d6bc`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b571`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b41d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b41d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bcba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bcba`

## string_xrefs

- `0x18002bc73`: `PlaiReadProvider`

## pseudocode

```c
__int64 __fastcall PlaiReadProvider(HKEY a1, const unsigned __int16 *a2, struct ITraceDataProviderCollection *a3)
{
  __int64 Class; // rbx
  LSTATUS v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int *v9; // rcx
  int *v10; // r9
  __int64 v11; // rax
  HRESULT v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  int v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  GUID v42; // [rsp+A0h] [rbp-60h] BYREF
  GUID pclsid; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v44[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v45[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v46[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v47[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v48[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v49[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v50[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v51[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v52[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v53[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v54[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v55[64]; // [rsp+640h] [rbp+540h] BYREF
  unsigned __int16 v56[64]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v38 = 0;
  v41 = 0;
  hKey = 0;
  v39 = 0;
  pclsid = 0;
  Class = 0;
  v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v7 = PlaiHResultFromWin32(v6);
  if ( v7 >= 0 )
  {
    if ( PlaiGetRegDword(hKey, L"Enabled", &v38) >= 0 && !v38 )
      goto LABEL_113;
    Class = CreateClassObject<TraceDataProvider>(byte_180147320, 0);
    if ( !Class )
    {
      v37 = 0;
      v36 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_113;
      }
      PlaiWhoAmI(v45, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v45[v11] );
      goto LABEL_111;
    }
    if ( a2 )
    {
      v12 = CLSIDFromString(a2, &pclsid);
      if ( v12 >= 0 )
      {
        v13 = *(_QWORD *)Class;
        v42 = pclsid;
        v14 = (*(__int64 (__fastcall **)(__int64, GUID *))(v13 + 80))(Class, &v42);
        if ( v14 < 0 )
        {
          v37 = 0;
          v36 = v14;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_113;
          }
          PlaiWhoAmI(v46, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v46[v15] );
          goto LABEL_111;
        }
        if ( PlaiGetRegDword(hKey, L"EnableLevel", &v38) >= 0 )
        {
          if ( v39 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            v39 = 0;
          }
          v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Class + 88LL))(Class, &v39);
          if ( v16 < 0 )
          {
            v37 = 0;
            v36 = v16;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_113;
            }
            PlaiWhoAmI(v47, 0x4000000000000800uLL);
            v17 = -1;
            do
              ++v17;
            while ( v47[v17] );
            goto LABEL_111;
          }
          v18 = PlaiPutUlValue<IValueMap>(v39, v38);
          if ( v18 < 0 )
          {
            v37 = 0;
            v36 = v18;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_113;
            }
            PlaiWhoAmI(v48, 0x4000000000000800uLL);
            v19 = -1;
            do
              ++v19;
            while ( v48[v19] );
            goto LABEL_111;
          }
        }
        if ( PlaiGetRegDword(hKey, L"EnableProperty", &v38) >= 0 )
        {
          if ( v39 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            v39 = 0;
          }
          v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Class + 112LL))(Class, &v39);
          if ( v20 < 0 )
          {
            v37 = 0;
            v36 = v20;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_113;
            }
            PlaiWhoAmI(v49, 0x4000000000000800uLL);
            v21 = -1;
            do
              ++v21;
            while ( v49[v21] );
            goto LABEL_111;
          }
          v22 = PlaiPutUlValue<IValueMap>(v39, v38);
          if ( v22 < 0 )
          {
            v37 = 0;
            v36 = v22;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_113;
            }
            PlaiWhoAmI(v50, 0x4000000000000800uLL);
            v23 = -1;
            do
              ++v23;
            while ( v50[v23] );
            goto LABEL_111;
          }
        }
        if ( PlaiGetRegQword(hKey, L"MatchAllKeyword", &v41) < 0 )
          goto LABEL_78;
        if ( v39 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          v39 = 0;
        }
        v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Class + 104LL))(Class, &v39);
        if ( v24 < 0 )
        {
          v37 = 0;
          v36 = v24;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_113;
          }
          PlaiWhoAmI(v51, 0x4000000000000800uLL);
          v25 = -1;
          do
            ++v25;
          while ( v51[v25] );
          goto LABEL_111;
        }
        v26 = PlaiPutUllValue<IValueMap>(v39, v41);
        if ( v26 >= 0 )
        {
LABEL_78:
          if ( PlaiGetRegQword(hKey, L"MatchAnyKeyword", &v41) < 0 || !v41 )
          {
            if ( PlaiGetRegDword(hKey, L"EnableFlags", &v38) < 0 )
              v41 = 0;
            else
              v41 = v38;
          }
          if ( v39 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            v39 = 0;
          }
          v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Class + 96LL))(Class, &v39);
          if ( v28 >= 0 )
          {
            v30 = PlaiPutUllValue<IValueMap>(v39, v41);
            if ( v30 >= 0 )
            {
              v32 = ((__int64 (__fastcall *)(struct ITraceDataProviderCollection *, __int64))a3->lpVtbl->Add)(a3, Class);
              if ( v32 >= 0 )
                goto LABEL_113;
              v37 = 0;
              v36 = v32;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_113;
              }
              PlaiWhoAmI(v55, 0x4000000000000800uLL);
              v33 = -1;
              do
                ++v33;
              while ( v55[v33] );
            }
            else
            {
              v37 = 0;
              v36 = v30;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_113;
              }
              PlaiWhoAmI(v54, 0x4000000000000800uLL);
              v31 = -1;
              do
                ++v31;
              while ( v54[v31] );
            }
          }
          else
          {
            v37 = 0;
            v36 = v28;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_113;
            }
            PlaiWhoAmI(v53, 0x4000000000000800uLL);
            v29 = -1;
            do
              ++v29;
            while ( v53[v29] );
          }
        }
        else
        {
          v37 = 0;
          v36 = v26;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_113;
          }
          PlaiWhoAmI(v52, 0x4000000000000800uLL);
          v27 = -1;
          do
            ++v27;
          while ( v52[v27] );
        }
LABEL_111:
        v10 = &v36;
        v9 = &v37;
LABEL_112:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v10, 4, byte_180147320, 1, v9, 4);
        goto LABEL_113;
      }
    }
    else
    {
      v12 = -2147024809;
    }
    v37 = 0;
    v36 = v12;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_113;
    }
    PlaiWhoAmI(v56, 0x4000000000000800uLL);
    v34 = -1;
    do
      ++v34;
    while ( v56[v34] );
    goto LABEL_111;
  }
  v36 = 0;
  v37 = v7;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v44, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v44[v8] );
    v9 = &v36;
    v10 = &v37;
    goto LABEL_112;
  }
LABEL_113:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Class )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)Class + 16LL))(Class);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return 0;
}

```

## disassembly

```asm
0x18002b3bc  mov     [rsp-8+arg_18], rbx
0x18002b3c1  push    rbp
0x18002b3c2  push    rsi
0x18002b3c3  push    rdi
0x18002b3c4  push    r14
0x18002b3c6  push    r15
0x18002b3c8  lea     rbp, [rsp-650h]
0x18002b3d0  sub     rsp, 750h
0x18002b3d7  mov     rax, cs:__security_cookie
0x18002b3de  xor     rax, rsp
0x18002b3e1  mov     [rbp+670h+var_30], rax
0x18002b3e8  xor     r15d, r15d
0x18002b3eb  lea     rax, [rbp+670h+hKey]
0x18002b3ef  mov     rsi, r8
0x18002b3f2  mov     [rbp+670h+var_6F0], r15d
0x18002b3f6  xorps   xmm0, xmm0
0x18002b3f9  mov     [rbp+670h+var_6D8], r15
0x18002b3fd  xor     r8d, r8d; ulOptions
0x18002b400  mov     [rbp+670h+hKey], r15
0x18002b404  mov     r9d, 20019h; samDesired
0x18002b40a  mov     [rbp+670h+var_6E8], r15
0x18002b40e  movups  xmmword ptr [rbp+670h+pclsid.Data1], xmm0
0x18002b412  mov     ebx, r15d
0x18002b415  mov     [rsp+770h+phkResult], rax; phkResult
0x18002b41a  mov     rdi, rdx
0x18002b41d  call    cs:__imp_RegOpenKeyExW
0x18002b423  mov     ecx, eax; unsigned int
0x18002b425  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18002b42a  test    eax, eax
0x18002b42c  jns     loc_18002B4B7
0x18002b432  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b439  mov     [rsp+770h+var_700], r15d
0x18002b43e  mov     [rsp+770h+var_6F8], eax
0x18002b442  jz      loc_18002BCB1
0x18002b448  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b452  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b459  jz      loc_18002BCB1
0x18002b45f  mov     rax, cs:qword_180169748
0x18002b466  and     rax, rdx
0x18002b469  cmp     cs:qword_180169748, rax
0x18002b470  jnz     loc_18002BCB1
0x18002b476  lea     rcx, [rbp+670h+var_6B0]; unsigned __int16 *
0x18002b47a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b47f  lea     rcx, [rbp+670h+var_6B0]
0x18002b483  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b487  inc     rax
0x18002b48a  cmp     [rcx+rax*2], r15w
0x18002b48f  jnz     short loc_18002B487
0x18002b491  lea     ecx, [rax+rax]
0x18002b494  add     rcx, 2
0x18002b498  lea     rax, [rbp+670h+var_6B0]
0x18002b49c  mov     [rsp+770h+var_710], rcx
0x18002b4a1  lea     r14, byte_180147320
0x18002b4a8  lea     rcx, [rsp+770h+var_700]
0x18002b4ad  lea     r9, [rsp+770h+var_6F8]
0x18002b4b2  jmp     loc_18002BC5E
0x18002b4b7  mov     rcx, [rbp+670h+hKey]; HKEY
0x18002b4bb  lea     r8, [rbp+670h+var_6F0]; unsigned int *
0x18002b4bf  lea     rdx, aEnabled; "Enabled"
0x18002b4c6  call    ?PlaiGetRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaiGetRegDword(HKEY__ *,ushort const *,ulong *)
0x18002b4cb  test    eax, eax
0x18002b4cd  js      short loc_18002B4D9
0x18002b4cf  cmp     [rbp+670h+var_6F0], r15d
0x18002b4d3  jz      loc_18002BCB1
0x18002b4d9  lea     r14, byte_180147320
0x18002b4e0  xor     edx, edx
0x18002b4e2  mov     rcx, r14
0x18002b4e5  call    ??$CreateClassObject@VTraceDataProvider@@@@YAPEAVTraceDataProvider@@PEBDH@Z; CreateClassObject<TraceDataProvider>(char const *,int)
0x18002b4ea  mov     rbx, rax
0x18002b4ed  test    rax, rax
0x18002b4f0  jnz     short loc_18002B561
0x18002b4f2  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b4f9  mov     [rsp+770h+var_6F8], r15d
0x18002b4fe  mov     [rsp+770h+var_700], 8007000Eh
0x18002b506  jz      loc_18002BCB1
0x18002b50c  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b516  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b51d  jz      loc_18002BCB1
0x18002b523  mov     rax, cs:qword_180169748
0x18002b52a  and     rax, rdx
0x18002b52d  cmp     cs:qword_180169748, rax
0x18002b534  jnz     loc_18002BCB1
0x18002b53a  lea     rcx, [rbp+670h+var_630]; unsigned __int16 *
0x18002b53e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b543  lea     rcx, [rbp+670h+var_630]
0x18002b547  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b54b  inc     rax
0x18002b54e  cmp     [rcx+rax*2], r15w
0x18002b553  jnz     short loc_18002B54B
0x18002b555  lea     ecx, [rax+rax]
0x18002b558  lea     rax, [rbp+670h+var_630]
0x18002b55c  jmp     loc_18002BC4B
0x18002b561  test    rdi, rdi
0x18002b564  jz      loc_18002BBD7
0x18002b56a  lea     rdx, [rbp+670h+pclsid]; pclsid
0x18002b56e  mov     rcx, rdi; lpsz
0x18002b571  call    cs:__imp_CLSIDFromString
0x18002b577  test    eax, eax
0x18002b579  js      loc_18002BBDC
0x18002b57f  mov     rax, [rbx]
0x18002b582  lea     rdx, [rbp+670h+var_6D0]
0x18002b586  movaps  xmm0, xmmword ptr [rbp+670h+pclsid.Data1]
0x18002b58a  mov     rcx, rbx
0x18002b58d  movdqa  [rbp+670h+var_6D0], xmm0
0x18002b592  mov     rax, [rax+50h]
0x18002b596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b59b  test    eax, eax
0x18002b59d  jns     short loc_18002B613
0x18002b59f  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b5a6  mov     [rsp+770h+var_6F8], r15d
0x18002b5ab  mov     [rsp+770h+var_700], eax
0x18002b5af  jz      loc_18002BCB1
0x18002b5b5  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b5bf  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b5c6  jz      loc_18002BCB1
0x18002b5cc  mov     rax, cs:qword_180169748
0x18002b5d3  and     rax, rdx
0x18002b5d6  cmp     cs:qword_180169748, rax
0x18002b5dd  jnz     loc_18002BCB1
0x18002b5e3  lea     rcx, [rbp+670h+var_5B0]; unsigned __int16 *
0x18002b5ea  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b5ef  lea     rcx, [rbp+670h+var_5B0]
0x18002b5f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b5fa  inc     rax
0x18002b5fd  cmp     [rcx+rax*2], r15w
0x18002b602  jnz     short loc_18002B5FA
0x18002b604  lea     ecx, [rax+rax]
0x18002b607  lea     rax, [rbp+670h+var_5B0]
0x18002b60e  jmp     loc_18002BC4B
0x18002b613  mov     rcx, [rbp+670h+hKey]; HKEY
0x18002b617  lea     r8, [rbp+670h+var_6F0]; unsigned int *
0x18002b61b  lea     rdx, aEnablelevel; "EnableLevel"
0x18002b622  call    ?PlaiGetRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaiGetRegDword(HKEY__ *,ushort const *,ulong *)
0x18002b627  test    eax, eax
0x18002b629  js      loc_18002B757
0x18002b62f  mov     rcx, [rbp+670h+var_6E8]
0x18002b633  test    rcx, rcx
0x18002b636  jz      short loc_18002B648
0x18002b638  mov     rax, [rcx]
0x18002b63b  mov     rax, [rax+10h]
0x18002b63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b644  mov     [rbp+670h+var_6E8], r15
0x18002b648  mov     rax, [rbx]
0x18002b64b  lea     rdx, [rbp+670h+var_6E8]
0x18002b64f  mov     rcx, rbx
0x18002b652  mov     rax, [rax+58h]
0x18002b656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b65b  test    eax, eax
0x18002b65d  jns     short loc_18002B6D3
0x18002b65f  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b666  mov     [rsp+770h+var_6F8], r15d
0x18002b66b  mov     [rsp+770h+var_700], eax
0x18002b66f  jz      loc_18002BCB1
0x18002b675  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b67f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b686  jz      loc_18002BCB1
0x18002b68c  mov     rax, cs:qword_180169748
0x18002b693  and     rax, rdx
0x18002b696  cmp     cs:qword_180169748, rax
0x18002b69d  jnz     loc_18002BCB1
0x18002b6a3  lea     rcx, [rbp+670h+var_530]; unsigned __int16 *
0x18002b6aa  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b6af  lea     rcx, [rbp+670h+var_530]
0x18002b6b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b6ba  inc     rax
0x18002b6bd  cmp     [rcx+rax*2], r15w
0x18002b6c2  jnz     short loc_18002B6BA
0x18002b6c4  lea     ecx, [rax+rax]
0x18002b6c7  lea     rax, [rbp+670h+var_530]
0x18002b6ce  jmp     loc_18002BC4B
0x18002b6d3  mov     edx, [rbp+670h+var_6F0]
0x18002b6d6  mov     rcx, [rbp+670h+var_6E8]
0x18002b6da  call    ??$PlaiPutUlValue@UIValueMap@@@@YAJPEAUIValueMap@@K@Z; PlaiPutUlValue<IValueMap>(IValueMap *,ulong)
0x18002b6df  test    eax, eax
0x18002b6e1  jns     short loc_18002B757
0x18002b6e3  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b6ea  mov     [rsp+770h+var_6F8], r15d
0x18002b6ef  mov     [rsp+770h+var_700], eax
0x18002b6f3  jz      loc_18002BCB1
0x18002b6f9  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b703  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b70a  jz      loc_18002BCB1
0x18002b710  mov     rax, cs:qword_180169748
0x18002b717  and     rax, rdx
0x18002b71a  cmp     cs:qword_180169748, rax
0x18002b721  jnz     loc_18002BCB1
0x18002b727  lea     rcx, [rbp+670h+var_4B0]; unsigned __int16 *
0x18002b72e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b733  lea     rcx, [rbp+670h+var_4B0]
0x18002b73a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b73e  inc     rax
0x18002b741  cmp     [rcx+rax*2], r15w
0x18002b746  jnz     short loc_18002B73E
0x18002b748  lea     ecx, [rax+rax]
0x18002b74b  lea     rax, [rbp+670h+var_4B0]
0x18002b752  jmp     loc_18002BC4B
0x18002b757  mov     rcx, [rbp+670h+hKey]; HKEY
0x18002b75b  lea     r8, [rbp+670h+var_6F0]; unsigned int *
0x18002b75f  lea     rdx, aEnableproperty; "EnableProperty"
0x18002b766  call    ?PlaiGetRegDword@@YAJPEAUHKEY__@@PEBGPEAK@Z; PlaiGetRegDword(HKEY__ *,ushort const *,ulong *)
0x18002b76b  test    eax, eax
0x18002b76d  js      loc_18002B89B
0x18002b773  mov     rcx, [rbp+670h+var_6E8]
0x18002b777  test    rcx, rcx
0x18002b77a  jz      short loc_18002B78C
0x18002b77c  mov     rax, [rcx]
0x18002b77f  mov     rax, [rax+10h]
0x18002b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b788  mov     [rbp+670h+var_6E8], r15
0x18002b78c  mov     rax, [rbx]
0x18002b78f  lea     rdx, [rbp+670h+var_6E8]
0x18002b793  mov     rcx, rbx
0x18002b796  mov     rax, [rax+70h]
0x18002b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b79f  test    eax, eax
0x18002b7a1  jns     short loc_18002B817
0x18002b7a3  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b7aa  mov     [rsp+770h+var_6F8], r15d
0x18002b7af  mov     [rsp+770h+var_700], eax
0x18002b7b3  jz      loc_18002BCB1
0x18002b7b9  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b7c3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b7ca  jz      loc_18002BCB1
0x18002b7d0  mov     rax, cs:qword_180169748
0x18002b7d7  and     rax, rdx
0x18002b7da  cmp     cs:qword_180169748, rax
0x18002b7e1  jnz     loc_18002BCB1
0x18002b7e7  lea     rcx, [rbp+670h+var_430]; unsigned __int16 *
0x18002b7ee  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b7f3  lea     rcx, [rbp+670h+var_430]
0x18002b7fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b7fe  inc     rax
0x18002b801  cmp     [rcx+rax*2], r15w
0x18002b806  jnz     short loc_18002B7FE
0x18002b808  lea     ecx, [rax+rax]
0x18002b80b  lea     rax, [rbp+670h+var_430]
0x18002b812  jmp     loc_18002BC4B
0x18002b817  mov     edx, [rbp+670h+var_6F0]
0x18002b81a  mov     rcx, [rbp+670h+var_6E8]
0x18002b81e  call    ??$PlaiPutUlValue@UIValueMap@@@@YAJPEAUIValueMap@@K@Z; PlaiPutUlValue<IValueMap>(IValueMap *,ulong)
0x18002b823  test    eax, eax
0x18002b825  jns     short loc_18002B89B
0x18002b827  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b82e  mov     [rsp+770h+var_6F8], r15d
0x18002b833  mov     [rsp+770h+var_700], eax
0x18002b837  jz      loc_18002BCB1
0x18002b83d  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b847  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b84e  jz      loc_18002BCB1
0x18002b854  mov     rax, cs:qword_180169748
0x18002b85b  and     rax, rdx
0x18002b85e  cmp     cs:qword_180169748, rax
0x18002b865  jnz     loc_18002BCB1
0x18002b86b  lea     rcx, [rbp+670h+var_3B0]; unsigned __int16 *
0x18002b872  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b877  lea     rcx, [rbp+670h+var_3B0]
0x18002b87e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b882  inc     rax
0x18002b885  cmp     [rcx+rax*2], r15w
0x18002b88a  jnz     short loc_18002B882
0x18002b88c  lea     ecx, [rax+rax]
0x18002b88f  lea     rax, [rbp+670h+var_3B0]
0x18002b896  jmp     loc_18002BC4B
0x18002b89b  mov     rcx, [rbp+670h+hKey]; HKEY
0x18002b89f  lea     r8, [rbp+670h+var_6D8]; unsigned __int64 *
0x18002b8a3  lea     rdx, aMatchallkeywor; "MatchAllKeyword"
0x18002b8aa  call    ?PlaiGetRegQword@@YAJPEAUHKEY__@@PEBGPEA_K@Z; PlaiGetRegQword(HKEY__ *,ushort const *,unsigned __int64 *)
0x18002b8af  test    eax, eax
0x18002b8b1  js      loc_18002B9E0
0x18002b8b7  mov     rcx, [rbp+670h+var_6E8]
0x18002b8bb  test    rcx, rcx
0x18002b8be  jz      short loc_18002B8D0
0x18002b8c0  mov     rax, [rcx]
0x18002b8c3  mov     rax, [rax+10h]
0x18002b8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8cc  mov     [rbp+670h+var_6E8], r15
0x18002b8d0  mov     rax, [rbx]
0x18002b8d3  lea     rdx, [rbp+670h+var_6E8]
0x18002b8d7  mov     rcx, rbx
0x18002b8da  mov     rax, [rax+68h]
0x18002b8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8e3  test    eax, eax
0x18002b8e5  jns     short loc_18002B95B
0x18002b8e7  cmp     dword ptr cs:xmmword_180169738, r15d
0x18002b8ee  mov     [rsp+770h+var_6F8], r15d
0x18002b8f3  mov     [rsp+770h+var_700], eax
0x18002b8f7  jz      loc_18002BCB1
0x18002b8fd  mov     rdx, 4000000000000800h; unsigned __int64
0x18002b907  test    qword ptr cs:xmmword_180169738+8, rdx
0x18002b90e  jz      loc_18002BCB1
0x18002b914  mov     rax, cs:qword_180169748
0x18002b91b  and     rax, rdx
0x18002b91e  cmp     cs:qword_180169748, rax
0x18002b925  jnz     loc_18002BCB1
0x18002b92b  lea     rcx, [rbp+670h+var_330]; unsigned __int16 *
0x18002b932  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002b937  lea     rcx, [rbp+670h+var_330]
0x18002b93e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b942  inc     rax
0x18002b945  cmp     [rcx+rax*2], r15w
  ... truncated ...
```
