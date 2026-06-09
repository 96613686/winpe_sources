# DomainV2Store::AddRootTarget(ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,uchar,uchar)

- ea: `0x140045478`
- end: `0x140045ae6`
- name: `?AddRootTarget@DomainV2Store@@QEAAKPEBG00K00EE@Z`
- size: `1646`
- prototype: `unsigned int __fastcall(DomainV2Store *__hidden this, const unsigned __int16 *, const unsigned __int16 *, PCWSTR SourceString, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140010614`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b28`
- `0x140005b90`
- `0x140005c10`
- `0x140005f20`
- `0x140006bf0`
- `0x14000971c`
- `0x14000abc4`
- `0x14000cbb0`
- `0x14000e228`
- `0x140028098`
- `0x14002ccc4`
- `0x14002e1b8`
- `0x14002fbb0`
- `0x140038abc`
- `0x14003df3c`
- `0x14003e714`
- `0x14003e7fc`
- `0x140045478`
- `0x140045aec`
- `0x1400475a4`
- `0x14004a414`
- `0x14004ad44`
- `0x140057f64`
- `0x1400586a8`
- `0x140059044`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400458ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400458ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400458a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004599c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400458a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004599c`

## pseudocode

```c
__int64 __fastcall DomainV2Store::AddRootTarget(
        DomainV2Store *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        WCHAR *SourceString,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int8 a8,
        unsigned __int8 a9)
{
  char v9; // si
  DomainV2Store *v13; // r14
  __int64 v14; // rdx
  unsigned int inited; // ebx
  const unsigned __int16 *AdDomainName; // rax
  unsigned int v17; // eax
  _UNKNOWN **v18; // rdx
  unsigned int *v19; // rcx
  char v20; // r14
  DfsGeneric *v21; // rbx
  __int64 (__fastcall *v22)(DomainV2Store *, const unsigned __int16 *, WCHAR *, const unsigned __int16 *, int, LPCWSTR, DfsGeneric *, DfsRootFolder **); // r14
  const unsigned __int16 *v23; // rax
  unsigned int v24; // eax
  DfsRootFolder *v25; // rax
  DfsRootFolder *v26; // rcx
  DfsRootFolder *v27; // rax
  unsigned __int8 v28; // r8
  __int64 v29; // r9
  int v31; // [rsp+28h] [rbp-A1h]
  char v32; // [rsp+58h] [rbp-71h]
  unsigned __int8 v33[7]; // [rsp+59h] [rbp-70h] BYREF
  DfsRootFolder *v34; // [rsp+60h] [rbp-69h] BYREF
  DfsGeneric *v35; // [rsp+68h] [rbp-61h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v37; // [rsp+74h] [rbp-55h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-49h] BYREF
  unsigned int v40; // [rsp+88h] [rbp-41h]
  struct _UNICODE_STRING v41; // [rsp+90h] [rbp-39h] BYREF
  struct _UNICODE_STRING v42; // [rsp+A0h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v44[24]; // [rsp+C0h] [rbp-9h] BYREF

  v34 = 0;
  v41 = 0;
  v35 = 0;
  v9 = 0;
  v42 = 0;
  hKey = 0;
  String2 = 0;
  v40 = 0;
  v32 = 0;
  v33[0] = 0;
  v13 = this;
  lpSubKey = 0;
  v36 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 14, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, SourceString);
  }
  inited = DfsRtlInitUnicodeStringEx(&v41, SourceString);
  if ( inited
    || (inited = DfsRtlInitUnicodeStringEx(&v42, a3)) != 0
    || (inited = DfsRtlInitUnicodeStringEx(v44, a2)) != 0 )
  {
LABEL_65:
    v26 = v34;
    if ( v34 )
    {
      v33[0] = 0;
      DomainV2Store::RemoveRootTargetFromMetadata(v13, v34, a2, a3, v33);
      if ( v33[0] )
        DfsDeleteNamespaceEntry(SourceString, a6, 1u);
      *((_DWORD *)v34 + 68) |= 0x4000u;
      v27 = v34;
      ++*((_DWORD *)v34 + 30);
      ReleaseSRWLockExclusive((PSRWLOCK)v27 + 14);
      DfsStore::RemoveRootFolder(v13, v34, v28);
      v29 = DfsRootFolder::ReleaseRootShareDirectory(v34);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( pWppControl )
        {
          v14 = (_DWORD)v29 != 0 ? 11 : 31;
          if ( (((1 << ((_DWORD)v29 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
            && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 19, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v29);
          }
        }
      }
      v26 = v34;
    }
    if ( !v9 )
      goto LABEL_76;
    goto LABEL_75;
  }
  if ( a9 )
    AdDomainName = a2;
  else
    AdDomainName = DfsGetAdDomainName();
  inited = DfsRtlInitUnicodeStringEx(&String2, AdDomainName);
  if ( inited )
  {
LABEL_64:
    v9 = v32;
    goto LABEL_65;
  }
  if ( DfsIsSpecialDomainShare(&v41) || DfsIsSpecialDomainShare(&v42) )
  {
    inited = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_SD(
        *((_QWORD *)pWppControl + 2),
        15,
        (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
        (_DWORD)SourceString,
        87);
    }
    goto LABEL_64;
  }
  v17 = DfsStore::LookupRoot(v13, &String2, &v41, a9, &v35, a3, 1u, v33);
  inited = v17;
  v18 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v19 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 16, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v35, v17);
    v18 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v19 = pWppControl;
  }
  if ( !inited )
  {
    if ( !v33[0] )
    {
      if ( *((_DWORD *)v35 + 78) == 512 )
      {
        inited = 183;
        if ( v18 != &WPP_GLOBAL_Control && v19 && (v19[7] & 0x820) != 0 && *((_BYTE *)v19 + 25) >= 3u )
          WPP_SF_SD(
            *((_QWORD *)v19 + 2),
            18,
            (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
            (_DWORD)SourceString,
            183);
      }
      else
      {
        if ( v18 != &WPP_GLOBAL_Control && v19 && (v19[7] & 0x40) != 0 && *((_BYTE *)v19 + 25) >= 2u )
          WPP_SF_SS(
            *((_QWORD *)v19 + 2),
            17,
            (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
            (_DWORD)a2,
            (__int64)a3);
        inited = 87;
      }
      DfsGeneric::ReleaseReference(v35);
      goto LABEL_87;
    }
    v33[0] = 1;
    v20 = *((_BYTE *)CConfigurationSettings::_GetInstance(v19) + 66);
    inited = DfsGetAdFunctionalLevel(&v36, &v37);
    if ( !inited )
    {
      if ( v36 < 3 - (unsigned int)(v20 != 0) || v37 < 2 )
      {
        inited = 8567;
      }
      else
      {
        inited = DfsGetNamespaceRegistrySubkeyName(a2, SourceString, a9, &lpSubKey);
        if ( !inited )
        {
          CRegistry::OpenKey(
            (CRegistry *)&hKey,
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Dfs\\Roots\\domainV2",
            0x20006u);
          inited = v40;
          if ( !v40 )
          {
            inited = DfsCreateNamespaceStateInRegistry(
                       hKey,
                       lpSubKey,
                       a2,
                       (const BYTE *)a3,
                       (BYTE *)SourceString,
                       a9,
                       0);
            if ( !inited )
            {
              v21 = v35;
              v22 = *(__int64 (__fastcall **)(DomainV2Store *, const unsigned __int16 *, WCHAR *, const unsigned __int16 *, int, LPCWSTR, DfsGeneric *, DfsRootFolder **))(*(_QWORD *)this + 64LL);
              if ( a9 )
                v23 = a2;
              else
                v23 = DfsGetAdDomainName();
              LOBYTE(v31) = a9;
              inited = v22(this, v23, SourceString, a3, v31, lpSubKey, v21, &v34);
              if ( inited
                || (v33[0] = 0,
                    (inited = (*(__int64 (__fastcall **)(DfsRootFolder *, unsigned __int16 *))(*(_QWORD *)v34 + 104LL))(
                                v34,
                                a6)) != 0)
                || (v32 = 1, a9)
                && (inited = (*(__int64 (__fastcall **)(DfsRootFolder *, unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v34 + 168LL))(
                               v34,
                               a6,
                               a2)) != 0 )
              {
                v13 = this;
              }
              else
              {
                v13 = this;
                v24 = DomainV2Store::AddRootTargetToMetadata(this, v34, a8, a2, a3, SourceString, a5, a7);
                inited = v24;
                if ( v24 == 80 || v24 == 183 || !v24 )
                {
                  inited = DfsRootFolder::AcquireRootShareDirectory(v34);
                  if ( !inited )
                  {
                    DfsRootFolder::MakeDfsShareOnline(v34);
                    DfsRootFolder::SetRootFolderSynchronized(v34);
                    v25 = v34;
                    ++*((_DWORD *)v34 + 30);
                    ReleaseSRWLockExclusive((PSRWLOCK)v25 + 14);
                    v26 = v34;
LABEL_75:
                    LOBYTE(v14) = 1;
                    (*(void (__fastcall **)(DfsRootFolder *, __int64, _QWORD))(*(_QWORD *)v26 + 128LL))(
                      v26,
                      v14,
                      inited);
                    v26 = v34;
LABEL_76:
                    if ( v35 )
                    {
                      DfsGeneric::ReleaseReference(v35);
                      v26 = v34;
                    }
                    if ( v26 )
                      DfsGeneric::ReleaseReference(v26);
                    if ( inited == 183 )
                      inited = 50;
                    operator delete((void *)lpSubKey);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && pWppControl
                      && (((1 << (inited != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                      && *((_BYTE *)pWppControl + 25) >= 3u )
                    {
                      WPP_SF_SD(
                        *((_QWORD *)pWppControl + 2),
                        20,
                        (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
                        (_DWORD)SourceString,
                        inited);
                    }
                    goto LABEL_87;
                  }
                }
              }
              RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
              if ( !v33[0] )
                goto LABEL_64;
              goto LABEL_58;
            }
          }
        }
      }
    }
    v13 = this;
LABEL_58:
    DfsStore::DeleteRootFolder(v13, v35);
    goto LABEL_64;
  }
LABEL_87:
  CRegistry::~CRegistry((CRegistry *)&hKey);
  return inited;
}

```

## disassembly

```asm
0x140045478  mov     rax, rsp
0x14004547b  mov     [rax+10h], rbx
0x14004547f  mov     [rax+18h], rsi
0x140045483  mov     [rax+20h], rdi
0x140045487  mov     [rax+8], rcx
0x14004548b  push    rbp
0x14004548c  push    r12
0x14004548e  push    r13
0x140045490  push    r14
0x140045492  push    r15
0x140045494  lea     rbp, [rax-37h]
0x140045498  sub     rsp, 0D0h
0x14004549f  xor     eax, eax
0x1400454a1  xorps   xmm0, xmm0
0x1400454a4  xorps   xmm1, xmm1
0x1400454a7  mov     [rbp+2Fh+var_98], rax
0x1400454ab  movups  xmmword ptr [rbp+2Fh+var_68.Length], xmm0
0x1400454af  mov     [rbp+2Fh+var_90], rax
0x1400454b3  mov     sil, al
0x1400454b6  movups  xmmword ptr [rbp+2Fh+var_58.Length], xmm1
0x1400454ba  mov     [rbp+2Fh+hKey], rax
0x1400454be  mov     r12, r9
0x1400454c1  movups  xmmword ptr [rbp+2Fh+String2.Length], xmm0
0x1400454c5  mov     [rbp+2Fh+var_70], eax
0x1400454c8  mov     r13, r8
0x1400454cb  mov     [rbp+2Fh+var_A0], al
0x1400454ce  mov     r15, rdx
0x1400454d1  mov     [rbp+2Fh+var_9F], al
0x1400454d4  mov     r14, rcx
0x1400454d7  mov     [rbp+2Fh+lpSubKey], rax
0x1400454db  mov     [rbp+2Fh+var_88], eax
0x1400454de  mov     [rbp+2Fh+var_84], eax
0x1400454e1  lea     rcx, WPP_GLOBAL_Control
0x1400454e8  cmp     cs:WPP_GLOBAL_Control, rcx
0x1400454ef  lea     edi, [rax+20h]
0x1400454f2  jz      short loc_14004551F
0x1400454f4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400454fb  test    rcx, rcx
0x1400454fe  jz      short loc_14004551F
0x140045500  test    [rcx+1Ch], dil
0x140045504  jz      short loc_14004551F
0x140045506  cmp     byte ptr [rcx+19h], 3
0x14004550a  jb      short loc_14004551F
0x14004550c  mov     rcx, [rcx+10h]
0x140045510  lea     edx, [rax+0Eh]
0x140045513  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x14004551a  call    WPP_SF_S
0x14004551f  mov     rdx, r12
0x140045522  lea     rcx, [rbp+2Fh+var_68]
0x140045526  call    DfsRtlInitUnicodeStringEx
0x14004552b  mov     ebx, eax
0x14004552d  test    eax, eax
0x14004552f  jnz     loc_140045945
0x140045535  mov     rdx, r13
0x140045538  lea     rcx, [rbp+2Fh+var_58]
0x14004553c  call    DfsRtlInitUnicodeStringEx
0x140045541  mov     ebx, eax
0x140045543  test    eax, eax
0x140045545  jnz     loc_140045945
0x14004554b  mov     rdx, r15
0x14004554e  lea     rcx, [rbp+2Fh+var_38]
0x140045552  call    DfsRtlInitUnicodeStringEx
0x140045557  mov     ebx, eax
0x140045559  test    eax, eax
0x14004555b  jnz     loc_140045945
0x140045561  mov     sil, [rbp+2Fh+arg_40]
0x140045565  test    sil, sil
0x140045568  jz      short loc_14004556F
0x14004556a  mov     rax, r15
0x14004556d  jmp     short loc_140045574
0x14004556f  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x140045574  mov     rdx, rax
0x140045577  lea     rcx, [rbp+2Fh+String2]
0x14004557b  call    DfsRtlInitUnicodeStringEx
0x140045580  mov     ebx, eax
0x140045582  test    eax, eax
0x140045584  jnz     loc_140045941
0x14004558a  lea     rcx, [rbp+2Fh+var_68]; struct _UNICODE_STRING *
0x14004558e  call    ?DfsIsSpecialDomainShare@@YAEPEAU_UNICODE_STRING@@@Z; DfsIsSpecialDomainShare(_UNICODE_STRING *)
0x140045593  test    al, al
0x140045595  jnz     loc_1400458F5
0x14004559b  lea     rcx, [rbp+2Fh+var_58]; struct _UNICODE_STRING *
0x14004559f  call    ?DfsIsSpecialDomainShare@@YAEPEAU_UNICODE_STRING@@@Z; DfsIsSpecialDomainShare(_UNICODE_STRING *)
0x1400455a4  test    al, al
0x1400455a6  jnz     loc_1400458F5
0x1400455ac  lea     rax, [rbp+2Fh+var_9F]
0x1400455b0  mov     r9b, sil; unsigned __int8
0x1400455b3  mov     [rsp+0F0h+var_B8], rax; unsigned __int8 *
0x1400455b8  lea     r8, [rbp+2Fh+var_68]; struct _UNICODE_STRING *
0x1400455bc  mov     byte ptr [rsp+0F0h+var_C0], 1; HKEY *
0x1400455c1  lea     rax, [rbp+2Fh+var_90]
0x1400455c5  mov     [rsp+0F0h+var_C8], r13; unsigned __int16 *
0x1400455ca  lea     rdx, [rbp+2Fh+String2]; String2
0x1400455ce  mov     rcx, r14; this
0x1400455d1  mov     [rsp+0F0h+var_D0], rax; struct DfsRootFolder **
0x1400455d6  call    ?LookupRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@PEBGEPEAE@Z; DfsStore::LookupRoot(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *,ushort const *,uchar,uchar *)
0x1400455db  mov     ebx, eax
0x1400455dd  mov     rdx, cs:WPP_GLOBAL_Control
0x1400455e4  lea     r8, WPP_GLOBAL_Control
0x1400455eb  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400455f2  cmp     rdx, r8
0x1400455f5  jz      short loc_14004563A
0x1400455f7  test    rcx, rcx
0x1400455fa  jz      short loc_14004563A
0x1400455fc  test    [rcx+1Ch], dil
0x140045600  jz      short loc_14004563A
0x140045602  cmp     byte ptr [rcx+19h], 3
0x140045606  jb      short loc_14004563A
0x140045608  mov     r9, [rbp+2Fh+var_90]
0x14004560c  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140045613  mov     rcx, [rcx+10h]
0x140045617  mov     edx, 10h
0x14004561c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140045620  call    WPP_SF_qd
0x140045625  mov     rdx, cs:WPP_GLOBAL_Control
0x14004562c  lea     r8, WPP_GLOBAL_Control
0x140045633  mov     rcx, cs:?pWppControl@@3PEAXEA; unsigned int *
0x14004563a  test    ebx, ebx
0x14004563c  jnz     loc_140045AB9
0x140045642  cmp     [rbp+2Fh+var_9F], bl
0x140045645  jnz     loc_1400456DD
0x14004564b  mov     rax, [rbp+2Fh+var_90]
0x14004564f  cmp     dword ptr [rax+138h], 200h
0x140045659  jz      short loc_140045693
0x14004565b  cmp     rdx, r8
0x14004565e  jz      short loc_14004568C
0x140045660  test    rcx, rcx
0x140045663  jz      short loc_14004568C
0x140045665  test    byte ptr [rcx+1Ch], 40h
0x140045669  jz      short loc_14004568C
0x14004566b  cmp     byte ptr [rcx+19h], 2
0x14004566f  jb      short loc_14004568C
0x140045671  mov     rcx, [rcx+10h]
0x140045675  lea     edx, [rbx+11h]
0x140045678  mov     r9, r15
0x14004567b  mov     [rsp+0F0h+var_D0], r13
0x140045680  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140045687  call    WPP_SF_SS
0x14004568c  mov     ebx, 57h ; 'W'
0x140045691  jmp     short loc_1400456CF
0x140045693  mov     eax, 0B7h
0x140045698  mov     ebx, eax
0x14004569a  cmp     rdx, r8
0x14004569d  jz      short loc_1400456CF
0x14004569f  test    rcx, rcx
0x1400456a2  jz      short loc_1400456CF
0x1400456a4  bts     edi, 0Bh
0x1400456a8  test    [rcx+1Ch], edi
0x1400456ab  jz      short loc_1400456CF
0x1400456ad  cmp     byte ptr [rcx+19h], 3
0x1400456b1  jb      short loc_1400456CF
0x1400456b3  mov     rcx, [rcx+10h]
0x1400456b7  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x1400456be  mov     edx, 12h
0x1400456c3  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400456c7  mov     r9, r12
0x1400456ca  call    WPP_SF_SD
0x1400456cf  mov     rcx, [rbp+2Fh+var_90]; this
0x1400456d3  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x1400456d8  jmp     loc_140045AB9
0x1400456dd  mov     [rbp+2Fh+var_9F], 1
0x1400456e1  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x1400456e6  lea     rdx, [rbp+2Fh+var_84]; unsigned int *
0x1400456ea  lea     rcx, [rbp+2Fh+var_88]; unsigned int *
0x1400456ee  mov     r14b, [rax+42h]
0x1400456f2  call    ?DfsGetAdFunctionalLevel@@YAKPEAK0@Z; DfsGetAdFunctionalLevel(ulong *,ulong *)
0x1400456f7  mov     ebx, eax
0x1400456f9  test    eax, eax
0x1400456fb  jnz     loc_1400458E3
0x140045701  neg     r14b
0x140045704  sbb     eax, eax
0x140045706  add     eax, 3
0x140045709  cmp     [rbp+2Fh+var_88], eax
0x14004570c  jb      loc_1400458DE
0x140045712  cmp     [rbp+2Fh+var_84], 2
0x140045716  jb      loc_1400458DE
0x14004571c  lea     r9, [rbp+2Fh+lpSubKey]; unsigned __int16 **
0x140045720  mov     r8b, sil; unsigned __int8
0x140045723  mov     rdx, r12; unsigned __int16 *
0x140045726  mov     rcx, r15; unsigned __int16 *
0x140045729  call    ?DfsGetNamespaceRegistrySubkeyName@@YAKPEBG0EPEAPEBG@Z; DfsGetNamespaceRegistrySubkeyName(ushort const *,ushort const *,uchar,ushort const * *)
0x14004572e  mov     ebx, eax
0x140045730  test    eax, eax
0x140045732  jnz     loc_1400458E3
0x140045738  mov     r9d, 20006h; unsigned int
0x14004573e  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Dfs\\Roots\\domain"...
0x140045745  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14004574c  lea     rcx, [rbp+2Fh+hKey]; this
0x140045750  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x140045755  mov     ebx, [rbp+2Fh+var_70]
0x140045758  test    ebx, ebx
0x14004575a  jnz     loc_1400458E3
0x140045760  and     [rsp+0F0h+var_C0], 0
0x140045766  mov     r9, r13; unsigned __int16 *
0x140045769  mov     rdx, [rbp+2Fh+lpSubKey]; unsigned __int16 *
0x14004576d  mov     r8, r15; unsigned __int16 *
0x140045770  mov     rcx, [rbp+2Fh+hKey]; HKEY
0x140045774  mov     byte ptr [rsp+0F0h+var_C8], sil; unsigned __int8
0x140045779  mov     [rsp+0F0h+var_D0], r12; unsigned __int16 *
0x14004577e  call    ?DfsCreateNamespaceStateInRegistry@@YAKPEAUHKEY__@@PEBG111EPEAPEAU1@@Z; DfsCreateNamespaceStateInRegistry(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,HKEY__ * *)
0x140045783  mov     ebx, eax
0x140045785  test    eax, eax
0x140045787  jnz     loc_1400458E3
0x14004578d  mov     rax, [rbp+2Fh+arg_0]
0x140045791  mov     rbx, [rbp+2Fh+var_90]
0x140045795  mov     rax, [rax]
0x140045798  mov     r14, [rax+40h]
0x14004579c  test    sil, sil
0x14004579f  jz      short loc_1400457A6
0x1400457a1  mov     rax, r15
0x1400457a4  jmp     short loc_1400457AB
0x1400457a6  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x1400457ab  lea     rcx, [rbp+2Fh+var_98]
0x1400457af  mov     rdx, rax
0x1400457b2  mov     [rsp+0F0h+var_B8], rcx
0x1400457b7  mov     r9, r13
0x1400457ba  mov     rcx, [rbp+2Fh+lpSubKey]
0x1400457be  mov     r8, r12
0x1400457c1  mov     [rsp+0F0h+var_C0], rbx
0x1400457c6  mov     rax, r14
0x1400457c9  mov     [rsp+0F0h+var_C8], rcx
0x1400457ce  mov     rcx, [rbp+2Fh+arg_0]
0x1400457d2  mov     byte ptr [rsp+0F0h+var_D0], sil
0x1400457d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400457dc  mov     ebx, eax
0x1400457de  test    eax, eax
0x1400457e0  jnz     loc_1400458B8
0x1400457e6  mov     rcx, [rbp+2Fh+var_98]
0x1400457ea  mov     rdx, [rbp+2Fh+arg_28]
0x1400457ee  mov     [rbp+2Fh+var_9F], al
0x1400457f1  mov     rax, [rcx]
0x1400457f4  mov     rax, [rax+68h]
0x1400457f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400457fd  mov     ebx, eax
0x1400457ff  test    eax, eax
0x140045801  jnz     loc_1400458B8
0x140045807  mov     [rbp+2Fh+var_A0], 1
0x14004580b  test    sil, sil
0x14004580e  jz      short loc_140045834
0x140045810  mov     rcx, [rbp+2Fh+var_98]
0x140045814  mov     r8, r15
0x140045817  mov     rdx, [rbp+2Fh+arg_28]
0x14004581b  mov     rax, [rcx]
0x14004581e  mov     rax, [rax+0A8h]
0x140045825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004582a  mov     ebx, eax
0x14004582c  test    eax, eax
0x14004582e  jnz     loc_1400458B8
0x140045834  mov     rax, [rbp+2Fh+arg_30]
0x140045838  mov     r9, r15; unsigned __int16 *
0x14004583b  mov     r14, [rbp+2Fh+arg_0]
0x14004583f  mov     r8b, [rbp+2Fh+arg_38]; unsigned __int8
0x140045843  mov     rcx, r14; this
0x140045846  mov     rdx, [rbp+2Fh+var_98]; struct DfsRootFolder *
0x14004584a  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x14004584f  mov     eax, [rbp+2Fh+arg_20]
0x140045852  mov     dword ptr [rsp+0F0h+var_C0], eax; unsigned int
0x140045856  mov     [rsp+0F0h+var_C8], r12; unsigned __int16 *
0x14004585b  mov     [rsp+0F0h+var_D0], r13; unsigned __int16 *
0x140045860  call    ?AddRootTargetToMetadata@DomainV2Store@@AEAAKPEAVDfsRootFolder@@EPEBG11K1@Z; DomainV2Store::AddRootTargetToMetadata(DfsRootFolder *,uchar,ushort const *,ushort const *,ushort const *,ulong,ushort const *)
0x140045865  mov     ebx, eax
0x140045867  cmp     eax, 50h ; 'P'
0x14004586a  jz      short loc_140045877
0x14004586c  cmp     eax, 0B7h
0x140045871  jz      short loc_140045877
0x140045873  test    eax, eax
0x140045875  jnz     short loc_1400458BC
0x140045877  mov     rcx, [rbp+2Fh+var_98]; this
0x14004587b  call    ?AcquireRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::AcquireRootShareDirectory(void)
0x140045880  mov     ebx, eax
0x140045882  test    eax, eax
0x140045884  jnz     short loc_1400458BC
0x140045886  mov     rcx, [rbp+2Fh+var_98]; this
0x14004588a  call    ?MakeDfsShareOnline@DfsRootFolder@@QEAAKXZ; DfsRootFolder::MakeDfsShareOnline(void)
0x14004588f  mov     rcx, [rbp+2Fh+var_98]; this
0x140045893  call    ?SetRootFolderSynchronized@DfsRootFolder@@QEAAXXZ; DfsRootFolder::SetRootFolderSynchronized(void)
0x140045898  mov     rax, [rbp+2Fh+var_98]
0x14004589c  inc     dword ptr [rax+78h]
0x14004589f  lea     rcx, [rax+70h]; SRWLock
0x1400458a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400458aa  nop     dword ptr [rax+rax+00h]
0x1400458af  mov     rcx, [rbp+2Fh+var_98]
0x1400458b3  jmp     loc_140045A19
0x1400458b8  mov     r14, [rbp+2Fh+arg_0]
0x1400458bc  mov     rdx, [rbp+2Fh+lpSubKey]; lpSubKey
0x1400458c0  xor     r9d, r9d; Reserved
0x1400458c3  mov     rcx, [rbp+2Fh+hKey]; hKey
0x1400458c7  xor     r8d, r8d; samDesired
0x1400458ca  call    cs:__imp_RegDeleteKeyExW
0x1400458d1  nop     dword ptr [rax+rax+00h]
0x1400458d6  cmp     [rbp+2Fh+var_9F], 0
0x1400458da  jz      short loc_140045941
0x1400458dc  jmp     short loc_1400458E7
0x1400458de  mov     ebx, 2177h
0x1400458e3  mov     r14, [rbp+2Fh+arg_0]
0x1400458e7  mov     rdx, [rbp+2Fh+var_90]; struct DfsRootFolder *
0x1400458eb  mov     rcx, r14; this
0x1400458ee  call    ?DeleteRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@@Z; DfsStore::DeleteRootFolder(DfsRootFolder *)
0x1400458f3  jmp     short loc_140045941
0x1400458f5  mov     ebx, 57h ; 'W'
  ... truncated ...
```
