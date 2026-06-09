# BootTraceSessionCollection::GetDataCollectorSets(ushort *,ushort *)

- ea: `0x1800b74e0`
- end: `0x1800b7c96`
- name: `?GetDataCollectorSets@BootTraceSessionCollection@@UEAAJPEAG0@Z`
- size: `1974`
- prototype: `__int64 __fastcall(BootTraceSessionCollection *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x1800b74e0`
- `0x18010c2fc`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b7c23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b7c23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b75c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b75c8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b792f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b792f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b76df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b76df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7c3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7c3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b77d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b77d1`

## pseudocode

```c
__int64 __fastcall BootTraceSessionCollection::GetDataCollectorSets(
        BootTraceSessionCollection *this,
        __int64 a2,
        unsigned __int16 *a3)
{
  int v3; // eax
  unsigned __int16 *v4; // r12
  OLECHAR *v6; // rdi
  WCHAR *v7; // r13
  TraceSession *Class; // rsi
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rax
  BootTraceSessionCollection **v12; // r9
  LSTATUS v13; // eax
  int v14; // eax
  __int64 v15; // rax
  LSTATUS v16; // eax
  int v17; // eax
  __int64 v18; // rax
  SIZE_T v19; // rcx
  __int64 v20; // rax
  LSTATUS v21; // eax
  const char *v22; // rdx
  int v23; // r8d
  OLECHAR *v24; // rcx
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+70h] [rbp-90h] BYREF
  BootTraceSessionCollection *v33; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h]
  DWORD cbMaxSubKeyLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v39[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v40[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v41[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v42[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v43[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v44[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v45[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v46[64]; // [rsp+420h] [rbp+320h] BYREF

  v3 = *((_DWORD *)this + 14);
  v4 = (unsigned __int16 *)a2;
  cSubKeys = 0;
  cchName = 0;
  v6 = 0;
  cbMaxSubKeyLen = 0;
  v7 = 0;
  bstrString = 0;
  Class = 0;
  hKey = 0;
  v32 = v3;
  v33 = this;
  if ( (_DWORD)xmmword_180169738 )
  {
    a2 = 0x4000000000000400LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent(
        (__int64)&g_Eventing,
        (__int64)PLA_EVENT_METHOD,
        3,
        (__int64)"BootTraceSessionCollection::GetDataCollectorSets");
    }
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = (*(__int64 (__fastcall **)(BootTraceSessionCollection *, __int64, unsigned __int16 *))(*(_QWORD *)this + 96LL))(
         this,
         a2,
         a3);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\WMI\\AutoLogger", 0, 0x20019u, &hKey);
    v14 = PlaiHResultFromWin32(v13);
    v10 = v14;
    if ( v14 >= 0 )
    {
      v16 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v17 = PlaiHResultFromWin32(v16);
      v10 = v17;
      if ( v17 >= 0 )
      {
        v19 = 2LL * ++cbMaxSubKeyLen;
        v7 = (WCHAR *)PlaiAlloc(v19, 1, 0, qword_180147320, phkResult);
        if ( v7 )
        {
          while ( 1 )
          {
            if ( (unsigned int)v6 >= cSubKeys )
              goto LABEL_70;
            cchName = cbMaxSubKeyLen;
            v21 = RegEnumKeyExW(hKey, (DWORD)v6, v7, &cchName, 0, 0, 0, 0);
            v10 = PlaiHResultFromWin32(v21);
            if ( v10 < 0 )
            {
              LODWORD(v33) = 0;
              v32 = v10;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v46, 0x4000000000000800uLL);
                v29 = -1;
                do
                  ++v29;
                while ( v46[v29] );
                goto LABEL_69;
              }
              goto LABEL_70;
            }
            if ( Class )
              (*(void (__fastcall **)(TraceSession *))(*(_QWORD *)Class + 16LL))(Class);
            Class = CreateClassObject<BootTraceSession>((char *)qword_180147320, 0);
            if ( !Class )
              break;
            PlaiFreeString(bstrString);
            v24 = PlaiAllocStringEx(v7, v22, v23);
            bstrString = v24;
            if ( !v24 )
            {
              v10 = -2147024882;
              v32 = -2147024882;
              LODWORD(v33) = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_70;
              }
              PlaiWhoAmI(v44, 0x4000000000000800uLL);
              v27 = -1;
              do
                ++v27;
              while ( v44[v27] );
LABEL_69:
              EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v32);
              goto LABEL_70;
            }
            if ( (*(int (__fastcall **)(TraceSession *, OLECHAR *, unsigned __int16 *))(*(_QWORD *)Class + 472LL))(
                   Class,
                   v24,
                   v4) >= 0 )
            {
              v25 = (*(__int64 (__fastcall **)(BootTraceSessionCollection *, TraceSession *))(*(_QWORD *)this + 80LL))(
                      this,
                      Class);
              v10 = v25;
              if ( v25 < 0 )
              {
                LODWORD(v33) = 0;
                v32 = v25;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_70;
                }
                PlaiWhoAmI(v43, 0x4000000000000800uLL);
                v26 = -1;
                do
                  ++v26;
                while ( v43[v26] );
                goto LABEL_69;
              }
            }
            else
            {
              v10 = 0;
            }
            LODWORD(v6) = (_DWORD)v6 + 1;
          }
          v10 = -2147024882;
          v32 = -2147024882;
          LODWORD(v33) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v45, 0x4000000000000800uLL);
            v28 = -1;
            do
              ++v28;
            while ( v45[v28] );
            goto LABEL_69;
          }
LABEL_70:
          v6 = bstrString;
          goto LABEL_71;
        }
        v10 = -2147024882;
        v32 = -2147024882;
        LODWORD(v33) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_71;
        }
        PlaiWhoAmI(v42, 0x4000000000000800uLL);
        v20 = -1;
        do
          ++v20;
        while ( v42[v20] );
      }
      else
      {
        LODWORD(v33) = 0;
        v32 = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_71;
        }
        PlaiWhoAmI(v41, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v41[v18] );
      }
    }
    else
    {
      LODWORD(v33) = 0;
      v32 = v14;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_71;
      }
      PlaiWhoAmI(v40, 0x4000000000000800uLL);
      v15 = -1;
      do
        ++v15;
      while ( v40[v15] );
    }
    v12 = (BootTraceSessionCollection **)&v32;
LABEL_14:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v12);
    goto LABEL_71;
  }
  v32 = 0;
  LODWORD(v33) = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v39, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v39[v11] );
    v12 = &v33;
    goto LABEL_14;
  }
LABEL_71:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiFreeString(v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( Class )
    (*(void (__fastcall **)(TraceSession *))(*(_QWORD *)Class + 16LL))(Class);
  if ( v7 )
    PlaiFree(v7, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b74e0  mov     [rsp-8+arg_10], rbx
0x1800b74e5  push    rbp
0x1800b74e6  push    rsi
0x1800b74e7  push    rdi
0x1800b74e8  push    r12
0x1800b74ea  push    r13
0x1800b74ec  push    r14
0x1800b74ee  push    r15
0x1800b74f0  lea     rbp, [rsp-3B0h]
0x1800b74f8  sub     rsp, 4B0h
0x1800b74ff  mov     rax, cs:__security_cookie
0x1800b7506  xor     rax, rsp
0x1800b7509  mov     [rbp+3E0h+var_40], rax
0x1800b7510  mov     eax, [rcx+38h]
0x1800b7513  xor     r15d, r15d
0x1800b7516  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800b751d  mov     r12, rdx
0x1800b7520  mov     r14, rcx
0x1800b7523  mov     [rbp+3E0h+cSubKeys], r15d
0x1800b7527  mov     [rbp+3E0h+cchName], r15d
0x1800b752b  mov     edi, r15d
0x1800b752e  mov     [rbp+3E0h+cbMaxSubKeyLen], r15d
0x1800b7532  mov     r13d, r15d
0x1800b7535  mov     [rbp+3E0h+bstrString], r15
0x1800b7539  mov     esi, r15d
0x1800b753c  mov     [rbp+3E0h+hKey], r15
0x1800b7540  mov     [rsp+4E0h+var_470], eax
0x1800b7544  mov     [rsp+4E0h+var_468], rcx
0x1800b7549  jz      short loc_1800B75BE
0x1800b754b  mov     rdx, 4000000000000400h
0x1800b7555  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b755c  jz      short loc_1800B75BE
0x1800b755e  mov     rax, cs:qword_180169748
0x1800b7565  and     rax, rdx
0x1800b7568  cmp     cs:qword_180169748, rax
0x1800b756f  jnz     short loc_1800B75BE
0x1800b7571  mov     [rsp+4E0h+lpcbMaxValueNameLen], 4
0x1800b757a  lea     rax, [rsp+4E0h+var_470]
0x1800b757f  mov     [rsp+4E0h+lpcValues], rax
0x1800b7584  lea     r9, aBoottracesessi_5; "BootTraceSessionCollection::GetDataColl"...
0x1800b758b  lea     rax, [rsp+4E0h+var_468]
0x1800b7590  mov     [rsp+4E0h+lpcbMaxClassLen], 8
0x1800b7599  mov     [rsp+4E0h+lpcbMaxSubKeyLen], rax
0x1800b759e  lea     r8d, [r15+3]
0x1800b75a2  lea     rdx, PLA_EVENT_METHOD
0x1800b75a9  mov     [rsp+4E0h+phkResult], 31h ; '1'
0x1800b75b2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b75b9  call    EventingWriteEvent
0x1800b75be  cmp     [r14+8], r15d
0x1800b75c2  jz      short loc_1800B75CE
0x1800b75c4  lea     rcx, [r14+10h]; lpCriticalSection
0x1800b75c8  call    cs:__imp_EnterCriticalSection
0x1800b75ce  mov     rax, [r14]
0x1800b75d1  mov     rcx, r14
0x1800b75d4  mov     rax, [rax+60h]
0x1800b75d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b75dd  mov     ebx, eax
0x1800b75df  test    eax, eax
0x1800b75e1  jns     loc_1800B76BF
0x1800b75e7  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800b75ee  mov     [rsp+4E0h+var_470], r15d
0x1800b75f3  mov     dword ptr [rsp+4E0h+var_468], eax
0x1800b75f7  jz      loc_1800B7C19
0x1800b75fd  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b7607  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b760e  jz      loc_1800B7C19
0x1800b7614  mov     rax, cs:qword_180169748
0x1800b761b  and     rax, rdx
0x1800b761e  cmp     cs:qword_180169748, rax
0x1800b7625  jnz     loc_1800B7C19
0x1800b762b  lea     rcx, [rbp+3E0h+var_440]; unsigned __int16 *
0x1800b762f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b7634  lea     rcx, [rbp+3E0h+var_440]
0x1800b7638  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b763c  inc     rax
0x1800b763f  cmp     [rcx+rax*2], r15w
0x1800b7644  jnz     short loc_1800B763C
0x1800b7646  lea     ecx, [rax+rax]
0x1800b7649  lea     rax, [rbp+3E0h+var_440]
0x1800b764d  add     rcx, 2
0x1800b7651  mov     [rsp+4E0h+var_480], rcx
0x1800b7656  lea     r15, qword_180147320
0x1800b765d  mov     [rsp+4E0h+lpftLastWriteTime], rax
0x1800b7662  lea     r9, [rsp+4E0h+var_468]
0x1800b7667  lea     rax, aBoottracesessi_5; "BootTraceSessionCollection::GetDataColl"...
0x1800b766e  mov     [rsp+4E0h+lpcbSecurityDescriptor], 31h ; '1'
0x1800b7677  mov     [rsp+4E0h+lpcbMaxValueLen], rax
0x1800b767c  lea     rax, [rsp+4E0h+var_470]
0x1800b7681  mov     edx, 4
0x1800b7686  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800b768d  mov     [rsp+4E0h+lpcbMaxValueNameLen], rdx
0x1800b7692  mov     [rsp+4E0h+lpcValues], rax
0x1800b7697  mov     [rsp+4E0h+lpcbMaxClassLen], 1
0x1800b76a0  lea     r8d, [rdx+1]
0x1800b76a4  mov     [rsp+4E0h+lpcbMaxSubKeyLen], r15
0x1800b76a9  mov     [rsp+4E0h+phkResult], rdx
0x1800b76ae  lea     rdx, PLA_EVENT_ERROR
0x1800b76b5  call    EventingWriteEvent
0x1800b76ba  jmp     loc_1800B7C16
0x1800b76bf  lea     rax, [rbp+3E0h+hKey]
0x1800b76c3  mov     r9d, 20019h; samDesired
0x1800b76c9  xor     r8d, r8d; ulOptions
0x1800b76cc  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1800b76d1  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\WMI"...
0x1800b76d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b76df  call    cs:__imp_RegOpenKeyExW
0x1800b76e5  mov     ecx, eax; unsigned int
0x1800b76e7  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800b76ec  mov     ebx, eax
0x1800b76ee  test    eax, eax
0x1800b76f0  jns     loc_1800B7795
0x1800b76f6  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800b76fd  mov     dword ptr [rsp+4E0h+var_468], r15d
0x1800b7702  mov     [rsp+4E0h+var_470], eax
0x1800b7706  jz      loc_1800B7C19
0x1800b770c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b7716  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b771d  jz      loc_1800B7C19
0x1800b7723  mov     rax, cs:qword_180169748
0x1800b772a  and     rax, rdx
0x1800b772d  cmp     cs:qword_180169748, rax
0x1800b7734  jnz     loc_1800B7C19
0x1800b773a  lea     rcx, [rbp+3E0h+var_3C0]; unsigned __int16 *
0x1800b773e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b7743  lea     rcx, [rbp+3E0h+var_3C0]
0x1800b7747  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b774b  inc     rax
0x1800b774e  cmp     [rcx+rax*2], r15w
0x1800b7753  jnz     short loc_1800B774B
0x1800b7755  lea     ecx, [rax+rax]
0x1800b7758  lea     rax, [rbp+3E0h+var_3C0]
0x1800b775c  lea     r15, qword_180147320
0x1800b7763  add     rcx, 2
0x1800b7767  lea     r9, [rsp+4E0h+var_470]
0x1800b776c  mov     [rsp+4E0h+var_480], rcx
0x1800b7771  mov     [rsp+4E0h+lpftLastWriteTime], rax
0x1800b7776  lea     rax, aBoottracesessi_5; "BootTraceSessionCollection::GetDataColl"...
0x1800b777d  mov     [rsp+4E0h+lpcbSecurityDescriptor], 31h ; '1'
0x1800b7786  mov     [rsp+4E0h+lpcbMaxValueLen], rax
0x1800b778b  lea     rax, [rsp+4E0h+var_468]
0x1800b7790  jmp     loc_1800B7681
0x1800b7795  mov     rcx, [rbp+3E0h+hKey]; hKey
0x1800b7799  lea     rax, [rbp+3E0h+cbMaxSubKeyLen]
0x1800b779d  mov     [rsp+4E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800b77a2  xor     r9d, r9d; lpReserved
0x1800b77a5  mov     [rsp+4E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800b77aa  xor     r8d, r8d; lpcchClass
0x1800b77ad  mov     [rsp+4E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800b77b2  xor     edx, edx; lpClass
0x1800b77b4  mov     [rsp+4E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800b77b9  mov     [rsp+4E0h+lpcValues], r15; lpcValues
0x1800b77be  mov     [rsp+4E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800b77c3  mov     [rsp+4E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800b77c8  lea     rax, [rbp+3E0h+cSubKeys]
0x1800b77cc  mov     [rsp+4E0h+phkResult], rax; int
0x1800b77d1  call    cs:__imp_RegQueryInfoKeyW
0x1800b77d7  mov     ecx, eax; unsigned int
0x1800b77d9  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800b77de  mov     ebx, eax
0x1800b77e0  test    eax, eax
0x1800b77e2  jns     short loc_1800B7858
0x1800b77e4  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800b77eb  mov     dword ptr [rsp+4E0h+var_468], r15d
0x1800b77f0  mov     [rsp+4E0h+var_470], eax
0x1800b77f4  jz      loc_1800B7C19
0x1800b77fa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b7804  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b780b  jz      loc_1800B7C19
0x1800b7811  mov     rax, cs:qword_180169748
0x1800b7818  and     rax, rdx
0x1800b781b  cmp     cs:qword_180169748, rax
0x1800b7822  jnz     loc_1800B7C19
0x1800b7828  lea     rcx, [rbp+3E0h+var_340]; unsigned __int16 *
0x1800b782f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b7834  lea     rcx, [rbp+3E0h+var_340]
0x1800b783b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b783f  inc     rax
0x1800b7842  cmp     [rcx+rax*2], r15w
0x1800b7847  jnz     short loc_1800B783F
0x1800b7849  lea     ecx, [rax+rax]
0x1800b784c  lea     rax, [rbp+3E0h+var_340]
0x1800b7853  jmp     loc_1800B775C
0x1800b7858  mov     eax, [rbp+3E0h+cbMaxSubKeyLen]
0x1800b785b  lea     r15, qword_180147320
0x1800b7862  inc     eax
0x1800b7864  xor     r8d, r8d; int
0x1800b7867  mov     ecx, eax
0x1800b7869  mov     r9, r15; char *
0x1800b786c  add     rcx, rcx; dwBytes
0x1800b786f  mov     [rbp+3E0h+cbMaxSubKeyLen], eax
0x1800b7872  lea     edx, [r8+1]; int
0x1800b7876  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800b787b  xor     edx, edx
0x1800b787d  mov     r13, rax
0x1800b7880  test    rax, rax
0x1800b7883  jnz     short loc_1800B78FF
0x1800b7885  cmp     dword ptr cs:xmmword_180169738, edx
0x1800b788b  mov     ecx, 8007000Eh
0x1800b7890  mov     ebx, ecx
0x1800b7892  mov     [rsp+4E0h+var_470], ecx
0x1800b7896  mov     dword ptr [rsp+4E0h+var_468], edx
0x1800b789a  jz      loc_1800B7C16
0x1800b78a0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b78aa  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b78b1  jz      loc_1800B7C16
0x1800b78b7  mov     rax, cs:qword_180169748
0x1800b78be  and     rax, rdx
0x1800b78c1  cmp     cs:qword_180169748, rax
0x1800b78c8  jnz     loc_1800B7C16
0x1800b78ce  lea     rcx, [rbp+3E0h+var_2C0]; unsigned __int16 *
0x1800b78d5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b78da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b78de  lea     rdx, [rbp+3E0h+var_2C0]
0x1800b78e5  xor     ecx, ecx
0x1800b78e7  inc     rax
0x1800b78ea  cmp     [rdx+rax*2], cx
0x1800b78ee  jnz     short loc_1800B78E7
0x1800b78f0  lea     ecx, [rax+rax]
0x1800b78f3  lea     rax, [rbp+3E0h+var_2C0]
0x1800b78fa  jmp     loc_1800B7763
0x1800b78ff  cmp     edi, [rbp+3E0h+cSubKeys]
0x1800b7902  jnb     loc_1800B7C12
0x1800b7908  mov     eax, [rbp+3E0h+cbMaxSubKeyLen]
0x1800b790b  lea     r9, [rbp+3E0h+cchName]; lpcchName
0x1800b790f  mov     rcx, [rbp+3E0h+hKey]; hKey
0x1800b7913  mov     r8, r13; lpName
0x1800b7916  mov     [rsp+4E0h+lpcValues], rdx; lpftLastWriteTime
0x1800b791b  mov     [rsp+4E0h+lpcbMaxClassLen], rdx; lpcchClass
0x1800b7920  mov     [rsp+4E0h+lpcbMaxSubKeyLen], rdx; lpClass
0x1800b7925  mov     [rsp+4E0h+phkResult], rdx; lpReserved
0x1800b792a  mov     edx, edi; dwIndex
0x1800b792c  mov     [rbp+3E0h+cchName], eax
0x1800b792f  call    cs:__imp_RegEnumKeyExW
0x1800b7935  mov     ecx, eax; unsigned int
0x1800b7937  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800b793c  mov     ebx, eax
0x1800b793e  xor     eax, eax
0x1800b7940  test    ebx, ebx
0x1800b7942  js      loc_1800B7B3E
0x1800b7948  test    rsi, rsi
0x1800b794b  jz      short loc_1800B795C
0x1800b794d  mov     rax, [rsi]
0x1800b7950  mov     rcx, rsi
0x1800b7953  mov     rax, [rax+10h]
0x1800b7957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b795c  xor     edx, edx; int
0x1800b795e  mov     rcx, r15; char *
0x1800b7961  call    ??$CreateClassObject@VBootTraceSession@@@@YAPEAVBootTraceSession@@PEBDH@Z; CreateClassObject<BootTraceSession>(char const *,int)
0x1800b7966  mov     rsi, rax
0x1800b7969  xor     eax, eax
0x1800b796b  test    rsi, rsi
0x1800b796e  jz      loc_1800B7AC7
0x1800b7974  mov     rcx, [rbp+3E0h+bstrString]; bstrString
0x1800b7978  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800b797d  mov     rcx, r13; unsigned __int16 *
0x1800b7980  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800b7985  mov     rcx, rax
0x1800b7988  mov     [rbp+3E0h+bstrString], rax
0x1800b798c  xor     eax, eax
0x1800b798e  test    rcx, rcx
0x1800b7991  jz      loc_1800B7A4D
0x1800b7997  mov     rax, [rsi]
0x1800b799a  mov     rdx, rcx
0x1800b799d  mov     r8, r12
0x1800b79a0  mov     rcx, rsi
0x1800b79a3  mov     rax, [rax+1D8h]
0x1800b79aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b79af  xor     edx, edx
0x1800b79b1  test    eax, eax
0x1800b79b3  jns     short loc_1800B79B9
0x1800b79b5  mov     ebx, edx
0x1800b79b7  jmp     short loc_1800B79D3
0x1800b79b9  mov     rax, [r14]
0x1800b79bc  mov     rdx, rsi
0x1800b79bf  mov     rcx, r14
0x1800b79c2  mov     rax, [rax+50h]
0x1800b79c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b79cb  xor     edx, edx
0x1800b79cd  mov     ebx, eax
0x1800b79cf  test    eax, eax
0x1800b79d1  js      short loc_1800B79DA
0x1800b79d3  inc     edi
0x1800b79d5  jmp     loc_1800B78FF
0x1800b79da  cmp     dword ptr cs:xmmword_180169738, edx
0x1800b79e0  mov     dword ptr [rsp+4E0h+var_468], edx
0x1800b79e4  mov     [rsp+4E0h+var_470], eax
0x1800b79e8  jz      loc_1800B7C12
0x1800b79ee  mov     rdx, 4000000000000800h; unsigned __int64
0x1800b79f8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800b79ff  jz      loc_1800B7C12
0x1800b7a05  mov     rax, cs:qword_180169748
0x1800b7a0c  and     rax, rdx
0x1800b7a0f  cmp     cs:qword_180169748, rax
0x1800b7a16  jnz     loc_1800B7C12
0x1800b7a1c  lea     rcx, [rbp+3E0h+var_240]; unsigned __int16 *
0x1800b7a23  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800b7a28  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b7a2c  lea     rdx, [rbp+3E0h+var_240]
0x1800b7a33  xor     ecx, ecx
0x1800b7a35  inc     rax
  ... truncated ...
```
