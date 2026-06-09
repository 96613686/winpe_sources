# GetInterfaceHelperClsid(_GUID const &,_GUID *,int *)

- ea: `0x1800126bc`
- end: `0x180012a9c`
- name: `?GetInterfaceHelperClsid@@YAJAEBU_GUID@@PEAU1@PEAH@Z`
- size: `992`
- prototype: `HRESULT __fastcall(const _GUID *iid, _GUID *pClsid, int *pfDisableTypelib)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800112ac`
- `0x1800121a0`

## callees

- `0x180010ed0`
- `0x180010efc`
- `0x1800126bc`
- `0x180013304`
- `0x180013a58`
- `0x180013b8c`
- `0x18001581c`
- `0x180020874`
- `0x18002091c`
- `0x180020b10`
- `0x180043cd4`
- `0x180046460`
- `0x1800d8010`

## import_xrefs

- `ntdll!ZwClose` at `0x1800129ce`
- `ntdll!ZwClose` at `0x1800129ce`
- `ntdll!RtlInitUnicodeString` at `0x180012917`
- `ntdll!RtlInitUnicodeString` at `0x180012917`
- `ntdll!ZwOpenKey` at `0x180012959`
- `ntdll!ZwOpenKey` at `0x180012959`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001286e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001286e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012a8b`

## string_xrefs

- `0x1800128b1`: `\Registry\Machine\Software\Classes\`

## pseudocode

```c
__int64 __fastcall GetInterfaceHelperClsid(const _GUID *iid, _GUID *pClsid, int *pfDisableTypelib)
{
  CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *v3; // rsi
  unsigned int v4; // edi
  int v8; // r14d
  Map<MAP_KEY_GUID,INTERFACE_HELPER_CLSID *,MAP_HASHER<MAP_KEY_GUID>,AllocateThrow>::Assoc **i; // rbx
  Map<MAP_KEY_GUID,INTERFACE_HELPER_CLSID *,MAP_HASHER<MAP_KEY_GUID>,AllocateThrow>::Assoc *v10; // rbx
  unsigned __int64 v11; // rax
  INTERFACE_HELPER_CLSID *m_r; // rbx
  __int64 result; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  wchar_t v16; // ax
  wchar_t *v17; // rax
  HANDLE v18; // rcx
  char *v19; // rax
  char *v20; // rsi
  unsigned int RegistryValue; // r14d
  void (__fastcall ***v22)(_QWORD, __int64); // rbx
  NTSTATUS v23; // eax
  unsigned int v24; // r9d
  CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *v25; // rdx
  void *v26; // rbx
  HRESULT v27; // eax
  HREG hkey; // [rsp+20h] [rbp-B9h] BYREF
  wchar_t *wszFullKeyName; // [rsp+28h] [rbp-B1h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-A9h] BYREF
  _GUID pinfo; // [rsp+60h] [rbp-79h] BYREF
  wchar_t wszKey[64]; // [rsp+70h] [rbp-69h] BYREF

  v3 = g_pihCache;
  v4 = 0;
  v8 = 0;
  if ( g_pihCache->m_fCsInitialized )
    XSLOCK::LockShared(&g_pihCache->m_lock, (int)pClsid);
  pinfo = *iid;
  for ( i = &v3->m_map.m_rgpAssoc[(214013 * pinfo.Data1 + 2531011) % v3->m_map.m_cAssoc]; ; i = &v10->m_pAssocNext )
  {
    v10 = *i;
    if ( !v10 )
      break;
    v11 = *(_QWORD *)&v10->m_d.guid.Data1 - *(_QWORD *)&pinfo.Data1;
    if ( !v11 )
      v11 = *(_QWORD *)v10->m_d.guid.Data4 - *(_QWORD *)pinfo.Data4;
    if ( !v11 )
    {
      m_r = v10->m_r;
      _InterlockedIncrement(&m_r->m_refs);
      m_r->m_dwReleaseTime = -1;
      goto LABEL_9;
    }
  }
  v8 = -2147467262;
  m_r = 0;
LABEL_9:
  if ( v3->m_fCsInitialized )
    XSLOCK::ReleaseLock(&v3->m_lock);
  if ( v8 )
  {
    v14 = 59;
    v15 = wszKey;
    do
    {
      if ( v14 == -2147483587 )
        break;
      v16 = *(wchar_t *)((char *)v15 + (char *)L"Interface\\" - (char *)wszKey);
      if ( !v16 )
        break;
      *v15++ = v16;
      --v14;
    }
    while ( v14 );
    v17 = v15 - 1;
    if ( v14 )
      v17 = v15;
    *v17 = 0;
    result = v14 == 0 ? 0x8007007A : 0;
    if ( v14 )
    {
      StringFromGuid(iid, &wszKey[10]);
      v18 = g_hHeap;
      hkey.h = 0;
      wszFullKeyName = 0;
      *pfDisableTypelib = 0;
      v19 = (char *)HeapAlloc(v18, 0, 0x50u);
      v20 = v19;
      if ( v19 )
      {
        *((_DWORD *)v19 + 2) = -1;
        *(_QWORD *)v19 = CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable';
        *((_DWORD *)v19 + 6) = 1;
        *((_QWORD *)v19 + 2) = 0;
        *(_QWORD *)v19 = INTERFACE_HELPER_CLSID::`vftable';
        *(GUID *)(v19 + 28) = GUID_NULL;
        *((_QWORD *)v19 + 8) = 0;
        *((_DWORD *)v19 + 18) = 0;
        *((GUID *)v19 + 3) = GUID_NULL;
        *(_GUID *)(v19 + 28) = *iid;
        RegistryValue = StringCat(&wszFullKeyName, L"\\Registry\\Machine\\Software\\Classes\\", wszKey, 0);
        v22 = (void (__fastcall ***)(_QWORD, __int64))v20;
        if ( RegistryValue )
          goto LABEL_40;
        *(&ObjectAttributes.Length + 1) = 0;
        pinfo = 0;
        *(&ObjectAttributes.Attributes + 1) = 0;
        RtlInitUnicodeString((PUNICODE_STRING)&pinfo, wszFullKeyName);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (_UNICODE_STRING *)&pinfo;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v23 = ZwOpenKey(&hkey.h, 0x20019u, &ObjectAttributes);
        RegistryValue = HrNt(v23);
        if ( !RegistryValue )
        {
          if ( FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableTypeLib") )
          {
            *pfDisableTypelib = 1;
            *((_DWORD *)v20 + 16) = 1;
          }
          if ( FDisableAssociatedInterceptor(hkey, L"InterfaceHelperDisableAll") )
          {
            RegistryValue = -2147023838;
            *((_DWORD *)v20 + 17) = 1;
          }
          else
          {
            *(_QWORD *)&pinfo.Data1 = 0;
            RegistryValue = GetRegistryValue(hkey, L"InterfaceHelperUser", (_KEY_VALUE_FULL_INFORMATION **)&pinfo, v24);
            if ( !RegistryValue )
            {
              v26 = *(void **)&pinfo.Data1;
              v27 = GuidFromString(
                      (const wchar_t *)(*(_QWORD *)&pinfo.Data1 + *(unsigned int *)(*(_QWORD *)&pinfo.Data1 + 8LL)),
                      pClsid);
              *((_DWORD *)v20 + 18) = 1;
              RegistryValue = v27;
              *((_GUID *)v20 + 3) = *pClsid;
              CoTaskMemFree(v26);
            }
          }
          ZwClose(hkey.h);
        }
        CoTaskMemFree(wszFullKeyName);
        v22 = (void (__fastcall ***)(_QWORD, __int64))v20;
        if ( CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::AddToCache(
               (CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID> *)v20,
               v25) < 0 )
LABEL_40:
          (**v22)(v22, 1);
        else
          CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(
            (CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID> *)v20,
            1);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
      return RegistryValue;
    }
  }
  else
  {
    *pfDisableTypelib = m_r->m_fDisableTypeLib;
    if ( m_r->m_fDisableAll )
    {
      v4 = -2147023838;
    }
    else if ( m_r->m_fFoundHelper )
    {
      *pClsid = m_r->m_clsid;
    }
    else
    {
      v4 = -2147024894;
    }
    CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(m_r, 1);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800126bc  mov     [rsp-8+arg_18], rbx
0x1800126c1  push    rbp
0x1800126c2  push    rsi
0x1800126c3  push    rdi
0x1800126c4  push    r12
0x1800126c6  push    r13
0x1800126c8  push    r14
0x1800126ca  push    r15
0x1800126cc  lea     rbp, [rsp-27h]
0x1800126d1  sub     rsp, 100h
0x1800126d8  mov     rax, cs:__security_cookie
0x1800126df  xor     rax, rsp
0x1800126e2  mov     [rbp+57h+var_40], rax
0x1800126e6  mov     rsi, cs:?g_pihCache@@3PEAV?$CALLFRAME_CACHE@UINTERFACE_HELPER_CLSID@@@@EA; CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> * g_pihCache
0x1800126ed  xor     edi, edi
0x1800126ef  mov     r15, pfDisableTypelib
0x1800126f2  mov     r12, pClsid
0x1800126f5  mov     r13, iid
0x1800126f8  mov     r14d, edi
0x1800126fb  cmp     [rsi+0B0h], edi
0x180012701  jz      short loc_18001270C
0x180012703  lea     iid, [rsi+8]; this
0x180012707  call    ?LockShared@XSLOCK@@QEAAHH@Z; XSLOCK::LockShared(int)
0x18001270c  movups  xmm0, xmmword ptr [r13+0]
0x180012711  xor     edx, edx
0x180012713  movq    pfDisableTypelib, xmm0
0x180012718  imul    eax, r8d, 343FDh
0x18001271f  movups  [rbp+57h+pinfo], xmm0
0x180012723  add     eax, 269EC3h
0x180012728  div     dword ptr [rsi+90h]
0x18001272e  mov     rax, [rsi+88h]
0x180012735  lea     rbx, [rax+pClsid*8]
0x180012739  mov     rbx, [rbx]
0x18001273c  test    rbx, rbx
0x18001273f  jz      loc_1800127DD
0x180012745  mov     rax, [rbx+1Ch]
0x180012749  sub     rax, pfDisableTypelib
0x18001274c  jnz     short loc_180012756
0x18001274e  mov     rax, [rbx+24h]
0x180012752  sub     rax, qword ptr [rbp+57h+pinfo+8]
0x180012756  test    rax, rax
0x180012759  jnz     short loc_1800127D4
0x18001275b  mov     rbx, [rbx+30h]
0x18001275f  lock inc dword ptr [rbx+18h]
0x180012763  mov     eax, [rbx+18h]
0x180012766  or      dword ptr [rbx+8], 0FFFFFFFFh
0x18001276a  cmp     [rsi+0B0h], edi
0x180012770  jz      short loc_18001277B
0x180012772  lea     iid, [rsi+8]; this
0x180012776  call    ?ReleaseLock@XSLOCK@@QEAAXXZ; XSLOCK::ReleaseLock(void)
0x18001277b  test    r14d, r14d
0x18001277e  jnz     short loc_1800127E8
0x180012780  mov     eax, [rbx+40h]
0x180012783  mov     [r15], eax
0x180012786  cmp     [rbx+44h], edi
0x180012789  jnz     loc_180012A0F
0x18001278f  cmp     [rbx+48h], edi
0x180012792  jnz     loc_180012A2E
0x180012798  mov     edi, 80070002h
0x18001279d  mov     edx, 1; bAgeOutOldEntries
0x1800127a2  mov     iid, rbx; this
0x1800127a5  call    ?Release@?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@QEAAKH@Z; CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(int)
0x1800127aa  mov     eax, edi
0x1800127ac  mov     iid, [rbp+57h+var_40]
0x1800127b0  xor     iid, rsp; StackCookie
0x1800127b3  call    __security_check_cookie
0x1800127b8  mov     rbx, [rsp+130h+arg_18]
0x1800127c0  add     rsp, 100h
0x1800127c7  pop     r15
0x1800127c9  pop     r14
0x1800127cb  pop     r13
0x1800127cd  pop     r12
0x1800127cf  pop     rdi
0x1800127d0  pop     rsi
0x1800127d1  pop     rbp
0x1800127d2  retn
0x1800127d4  add     rbx, 10h
0x1800127d8  jmp     loc_180012739
0x1800127dd  mov     r14d, 80004002h
0x1800127e3  mov     rbx, rdi
0x1800127e6  jmp     short loc_18001276A
0x1800127e8  lea     pfDisableTypelib, aInterface; "Interface\\"
0x1800127ef  mov     edx, 3Bh ; ';'
0x1800127f4  lea     rax, [rbp+57h+wszKey]
0x1800127f8  sub     pfDisableTypelib, rax
0x1800127fb  lea     iid, [rbp+57h+wszKey]
0x1800127ff  lea     rax, [pClsid+7FFFFFC3h]
0x180012806  test    rax, rax
0x180012809  jz      short loc_180012822
0x18001280b  movzx   eax, word ptr [pfDisableTypelib+iid]
0x180012810  test    ax, ax
0x180012813  jz      short loc_180012822
0x180012815  mov     [iid], ax
0x180012818  add     iid, 2
0x18001281c  sub     pClsid, 1
0x180012820  jnz     short loc_1800127FF
0x180012822  test    pClsid, pClsid
0x180012825  lea     rax, [iid-2]
0x180012829  cmovnz  rax, iid
0x18001282d  mov     [rax], di
0x180012830  mov     rax, pClsid
0x180012833  neg     rax
0x180012836  sbb     eax, eax
0x180012838  not     eax
0x18001283a  and     eax, 8007007Ah
0x18001283f  test    pClsid, pClsid
0x180012842  jz      loc_1800127AC
0x180012848  lea     pClsid, [rbp+57h+wszKey+14h]; pwsz
0x18001284c  mov     iid, r13; guid
0x18001284f  call    ?StringFromGuid@@YAXAEBU_GUID@@PEAG@Z; StringFromGuid(_GUID const &,ushort *)
0x180012854  mov     iid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001285b  xor     edx, edx; dwFlags
0x18001285d  mov     [rsp+130h+hkey.h], rdi
0x180012862  mov     [rsp+130h+wszFullKeyName], rdi
0x180012867  mov     [r15], edi
0x18001286a  lea     r8d, [pClsid+50h]; dwBytes
0x18001286e  call    cs:__imp_HeapAlloc
0x180012875  nop     dword ptr [rax+rax+00h]
0x18001287a  mov     rsi, rax
0x18001287d  test    rax, rax
0x180012880  jnz     short loc_18001288D
0x180012882  mov     r14d, 8007000Eh
0x180012888  jmp     loc_180012A07
0x18001288d  or      dword ptr [rsi+8], 0FFFFFFFFh
0x180012891  lea     rax, ??_7?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@6B@; const CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable'
0x180012898  mov     [rsi], rax
0x18001289b  lea     pfDisableTypelib, [rbp+57h+wszKey]
0x18001289f  mov     dword ptr [rsi+18h], 1
0x1800128a6  lea     rax, ??_7INTERFACE_HELPER_CLSID@@6B@; const INTERFACE_HELPER_CLSID::`vftable'
0x1800128ad  mov     [rsi+10h], rdi
0x1800128b1  lea     pClsid, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Classes"...
0x1800128b8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800128bf  mov     [rsi], rax
0x1800128c2  lea     iid, [rsp+130h+wszFullKeyName]; pwsz
0x1800128c7  xor     r9d, r9d
0x1800128ca  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x1800128cf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800128d6  mov     [rsi+40h], rdi
0x1800128da  mov     [rsi+48h], edi
0x1800128dd  movdqu  xmmword ptr [rsi+30h], xmm0
0x1800128e2  movups  xmm0, xmmword ptr [r13+0]
0x1800128e7  movdqu  xmmword ptr [rsi+1Ch], xmm0
0x1800128ec  call    ?StringCat@@YAJPEAPEAGZZ; StringCat(ushort * *,...)
0x1800128f1  mov     r14d, eax
0x1800128f4  mov     rbx, rsi
0x1800128f7  test    eax, eax
0x1800128f9  jnz     loc_180012A19
0x1800128ff  mov     pClsid, [rsp+130h+wszFullKeyName]; SourceString
0x180012904  lea     iid, [rbp+57h+pinfo]; DestinationString
0x180012908  xorps   xmm0, xmm0
0x18001290b  mov     dword ptr [rsp+130h+ObjectAttributes+4], edi
0x18001290f  movups  [rbp+57h+pinfo], xmm0
0x180012913  mov     dword ptr [rsp+130h+ObjectAttributes+1Ch], edi
0x180012917  call    cs:__imp_RtlInitUnicodeString
0x18001291e  nop     dword ptr [rax+rax+00h]
0x180012923  lea     rax, [rbp+57h+pinfo]
0x180012927  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18001292f  xorps   xmm0, xmm0
0x180012932  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x180012937  lea     pfDisableTypelib, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18001293c  mov     [rsp+130h+ObjectAttributes.RootDirectory], rdi
0x180012941  mov     edx, 20019h; DesiredAccess
0x180012946  mov     [rsp+130h+ObjectAttributes.Attributes], 40h ; '@'
0x18001294e  lea     iid, [rsp+130h+hkey]; KeyHandle
0x180012953  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x180012959  call    cs:__imp_ZwOpenKey
0x180012960  nop     dword ptr [rax+rax+00h]
0x180012965  mov     ecx, eax; status
0x180012967  call    HrNt
0x18001296c  mov     r14d, eax
0x18001296f  test    eax, eax
0x180012971  jnz     short loc_1800129DA
0x180012973  mov     iid, [rsp+130h+hkey.h]; hkey
0x180012978  lea     pClsid, aInterfacehelpe; "InterfaceHelperDisableTypeLib"
0x18001297f  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x180012984  test    eax, eax
0x180012986  jnz     loc_180012A3D
0x18001298c  mov     iid, [rsp+130h+hkey.h]; hkey
0x180012991  lea     pClsid, aInterfacehelpe_1; "InterfaceHelperDisableAll"
0x180012998  call    ?FDisableAssociatedInterceptor@@YAHUHREG@@PEBG@Z; FDisableAssociatedInterceptor(HREG,ushort const *)
0x18001299d  test    eax, eax
0x18001299f  jnz     loc_180012A50
0x1800129a5  mov     iid, [rsp+130h+hkey.h]; hkey
0x1800129aa  lea     pfDisableTypelib, [rbp+57h+pinfo]; ppinfo
0x1800129ae  lea     pClsid, aInterfacehelpe_2; "InterfaceHelperUser"
0x1800129b5  mov     qword ptr [rbp+57h+pinfo], rdi
0x1800129b9  call    GetRegistryValue
0x1800129be  mov     r14d, eax
0x1800129c1  test    eax, eax
0x1800129c3  jz      loc_180012A62
0x1800129c9  mov     iid, [rsp+130h+hkey.h]; Handle
0x1800129ce  call    cs:__imp_ZwClose
0x1800129d5  nop     dword ptr [rax+rax+00h]
0x1800129da  mov     iid, [rsp+130h+wszFullKeyName]; pv
0x1800129df  call    cs:__imp_CoTaskMemFree
0x1800129e6  nop     dword ptr [rax+rax+00h]
0x1800129eb  mov     iid, rsi; this
0x1800129ee  mov     rbx, rsi
0x1800129f1  call    ?AddToCache@?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@QEAAJPEAV?$CALLFRAME_CACHE@UINTERFACE_HELPER_CLSID@@@@@Z; CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::AddToCache(CALLFRAME_CACHE<INTERFACE_HELPER_CLSID> *)
0x1800129f6  test    eax, eax
0x1800129f8  js      short loc_180012A19
0x1800129fa  mov     edx, 1; bAgeOutOldEntries
0x1800129ff  mov     iid, rsi; this
0x180012a02  call    ?Release@?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@QEAAKH@Z; CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::Release(int)
0x180012a07  mov     eax, r14d
0x180012a0a  jmp     loc_1800127AC
0x180012a0f  mov     edi, 80070422h
0x180012a14  jmp     loc_18001279D
0x180012a19  mov     rax, [rbx]
0x180012a1c  mov     edx, 1
0x180012a21  mov     iid, rbx
0x180012a24  mov     rax, [rax]
0x180012a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a2c  jmp     short loc_180012A07
0x180012a2e  movups  xmm0, xmmword ptr [rbx+30h]
0x180012a32  movdqu  xmmword ptr [r12], xmm0
0x180012a38  jmp     loc_18001279D
0x180012a3d  mov     dword ptr [r15], 1
0x180012a44  mov     dword ptr [rsi+40h], 1
0x180012a4b  jmp     loc_18001298C
0x180012a50  mov     r14d, 80070422h
0x180012a56  mov     dword ptr [rsi+44h], 1
0x180012a5d  jmp     loc_1800129C9
0x180012a62  mov     rbx, qword ptr [rbp+57h+pinfo]
0x180012a66  mov     pClsid, r12; pguid
0x180012a69  mov     ecx, [rbx+8]
0x180012a6c  add     iid, rbx; lpsz
0x180012a6f  call    ?GuidFromString@@YAJPEBGPEAU_GUID@@@Z; GuidFromString(ushort const *,_GUID *)
0x180012a74  mov     dword ptr [rsi+48h], 1
0x180012a7b  mov     iid, rbx; pv
0x180012a7e  movups  xmm0, xmmword ptr [r12]
0x180012a83  mov     r14d, eax
0x180012a86  movdqu  xmmword ptr [rsi+30h], xmm0
0x180012a8b  call    cs:__imp_CoTaskMemFree
0x180012a92  nop     dword ptr [rax+rax+00h]
0x180012a97  jmp     loc_1800129C9
```
