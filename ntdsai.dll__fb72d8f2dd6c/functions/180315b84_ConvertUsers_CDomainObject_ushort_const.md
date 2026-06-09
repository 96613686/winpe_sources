# ConvertUsers(CDomainObject &,ushort const *)

- ea: `0x180315b84`
- end: `0x1803162f7`
- name: `?ConvertUsers@@YAJAEAVCDomainObject@@PEBG@Z`
- size: `1907`
- prototype: `__int64 __fastcall(HANDLE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x180314fa0`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180312e18`
- `0x180312ea8`
- `0x180313904`
- `0x180313d50`
- `0x180313e90`
- `0x180314350`
- `0x180314430`
- `0x1803145b8`
- `0x180314780`
- `0x180315b84`
- `0x180316480`
- `0x180316564`
- `0x180316648`
- `0x18031666c`
- `0x1803dedec`
- `0x180453340`
- `0x1804533ac`

## import_xrefs

- `ntdll!RtlpNtQueryValueKey` at `0x180315d92`
- `ntdll!RtlpNtQueryValueKey` at `0x180315d92`
- `ntdll!NtEnumerateKey` at `0x180315cac`
- `ntdll!NtEnumerateKey` at `0x180315e46`
- `ntdll!NtEnumerateKey` at `0x180315cac`
- `ntdll!NtEnumerateKey` at `0x180315e46`
- `ntdll!RtlAllocateHeap` at `0x180315fbf`
- `ntdll!RtlAllocateHeap` at `0x180315fbf`
- `ntdll!RtlFreeHeap` at `0x180316274`
- `ntdll!RtlFreeHeap` at `0x180471d0a`
- `ntdll!RtlFreeHeap` at `0x180316274`
- `ntdll!RtlFreeHeap` at `0x180471d0a`
- `ntdll!NtQueryKey` at `0x180315c61`
- `ntdll!NtQueryKey` at `0x180315d55`
- `ntdll!NtQueryKey` at `0x180315c61`
- `ntdll!NtQueryKey` at `0x180315d55`
- `ntdll!RtlInitUnicodeString` at `0x180316026`
- `ntdll!RtlInitUnicodeString` at `0x1803160c7`
- `ntdll!RtlInitUnicodeString` at `0x180316129`
- `ntdll!RtlInitUnicodeString` at `0x1803161a6`
- `ntdll!RtlInitUnicodeString` at `0x1803161ee`
- `ntdll!RtlInitUnicodeString` at `0x180471c4a`
- `ntdll!RtlInitUnicodeString` at `0x180471c8a`
- `ntdll!RtlInitUnicodeString` at `0x180316026`
- `ntdll!RtlInitUnicodeString` at `0x1803160c7`
- `ntdll!RtlInitUnicodeString` at `0x180316129`
- `ntdll!RtlInitUnicodeString` at `0x1803161a6`
- `ntdll!RtlInitUnicodeString` at `0x1803161ee`
- `ntdll!RtlInitUnicodeString` at `0x180471c4a`
- `ntdll!RtlInitUnicodeString` at `0x180471c8a`
- `SAMSRV!SampWriteEventLog` at `0x1803160f3`
- `SAMSRV!SampWriteEventLog` at `0x180316155`
- `SAMSRV!SampWriteEventLog` at `0x18031621a`
- `SAMSRV!SampWriteEventLog` at `0x18031623b`
- `SAMSRV!SampWriteEventLog` at `0x180471cb4`
- `SAMSRV!SampWriteEventLog` at `0x180471cd4`
- `SAMSRV!SampWriteEventLog` at `0x1803160f3`
- `SAMSRV!SampWriteEventLog` at `0x180316155`
- `SAMSRV!SampWriteEventLog` at `0x18031621a`
- `SAMSRV!SampWriteEventLog` at `0x18031623b`
- `SAMSRV!SampWriteEventLog` at `0x180471cb4`
- `SAMSRV!SampWriteEventLog` at `0x180471cd4`

## pseudocode

```c
__int64 __fastcall ConvertUsers(HANDLE *a1, const unsigned __int16 *a2)
{
  ULONG v4; // r15d
  NTSTATUS v5; // ebx
  ULONG v6; // edi
  int v8; // r14d
  char v9; // si
  WCHAR *Heap; // rdi
  struct CDomainObject *v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // rdx
  int AccountObjectDsName; // ecx
  int v15; // eax
  int RdnForSamObject; // eax
  struct _DSNAME *v17; // rbx
  struct _UNICODE_STRING *v18; // r8
  __int64 *v19; // rcx
  PULONG ResultLength; // [rsp+48h] [rbp-2288h]
  int v21; // [rsp+68h] [rbp-2268h] BYREF
  char v22; // [rsp+6Ch] [rbp-2264h]
  ULONG DataLength; // [rsp+70h] [rbp-2260h] BYREF
  ULONG Unused[2]; // [rsp+78h] [rbp-2258h] BYREF
  ULONG v25; // [rsp+80h] [rbp-2250h] BYREF
  int v26; // [rsp+84h] [rbp-224Ch]
  WCHAR *v27; // [rsp+88h] [rbp-2248h]
  HANDLE KeyHandle; // [rsp+90h] [rbp-2240h] BYREF
  int v29; // [rsp+98h] [rbp-2238h]
  __int64 v30; // [rsp+A0h] [rbp-2230h]
  int v31; // [rsp+A8h] [rbp-2228h]
  ULONG v32; // [rsp+B0h] [rbp-2220h] BYREF
  ULONG v33; // [rsp+B4h] [rbp-221Ch] BYREF
  ULONG Type; // [rsp+B8h] [rbp-2218h] BYREF
  ULONG v35; // [rsp+BCh] [rbp-2214h] BYREF
  int v36; // [rsp+C0h] [rbp-2210h] BYREF
  struct _UNICODE_STRING v37; // [rsp+C8h] [rbp-2208h] BYREF
  struct _UNICODE_STRING v38; // [rsp+D8h] [rbp-21F8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-21E8h] BYREF
  struct _UNICODE_STRING v40; // [rsp+F8h] [rbp-21D8h] BYREF
  struct _UNICODE_STRING v41; // [rsp+108h] [rbp-21C8h] BYREF
  _BYTE v42[8]; // [rsp+118h] [rbp-21B8h] BYREF
  _BYTE v43[64]; // [rsp+120h] [rbp-21B0h] BYREF
  _BYTE v44[56]; // [rsp+160h] [rbp-2170h] BYREF
  _BYTE v45[16]; // [rsp+198h] [rbp-2138h] BYREF
  PCWSTR v46; // [rsp+1A8h] [rbp-2128h]
  int v47; // [rsp+1B0h] [rbp-2120h]
  int v48; // [rsp+1B4h] [rbp-211Ch]
  int v49; // [rsp+1B8h] [rbp-2118h]
  WCHAR SourceString[24]; // [rsp+1C8h] [rbp-2108h] BYREF
  _BYTE v51[12]; // [rsp+1F8h] [rbp-20D8h] BYREF
  unsigned __int16 v52[4]; // [rsp+204h] [rbp-20CCh] BYREF
  _BYTE KeyInformation[20]; // [rsp+618h] [rbp-1CB8h] BYREF
  ULONG v54; // [rsp+62Ch] [rbp-1CA4h]
  _BYTE v55[16]; // [rsp+A48h] [rbp-1888h] BYREF
  wchar_t String1[520]; // [rsp+A58h] [rbp-1878h] BYREF
  _BYTE v57[20]; // [rsp+E68h] [rbp-1468h] BYREF
  ULONG v58; // [rsp+E7Ch] [rbp-1454h]
  unsigned __int16 v59[1024]; // [rsp+1298h] [rbp-1038h] BYREF
  unsigned __int16 v60[1024]; // [rsp+1A98h] [rbp-838h] BYREF

  v4 = 0;
  v21 = 0;
  v32 = 0;
  v33 = 0;
  KeyHandle = (HANDLE)-1LL;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  Type = -1;
  memset_0(KeyInformation, 0, 0x430u);
  memset_0(v55, 0, 0x418u);
  memset_0(v60, 0, sizeof(v60));
  v5 = NtQueryKey(a1[1], KeyFullInformation, KeyInformation, 0x430u, &v32);
  v21 = v5;
  if ( v5 >= 0 )
  {
    v6 = 0;
    if ( !v54 )
      goto LABEL_11;
    while ( 1 )
    {
      v5 = NtEnumerateKey(a1[1], v6, KeyBasicInformation, v55, 0x418u, &v33);
      v21 = v5;
      if ( v5 < 0 )
        goto LABEL_63;
      if ( !wcsncmp_0(String1, L"Users", 5u) )
        break;
      if ( ++v6 >= v54 )
        goto LABEL_11;
    }
    v5 = RtlStringCbPrintfW(v60, 0x800u, L"%ws\\Users", a2);
    v21 = v5;
    if ( v5 >= 0 )
    {
      v5 = CRegistryObject::Open((CRegistryObject *)&KeyHandle, v60);
      v21 = v5;
      if ( v5 >= 0 )
      {
        v5 = NtQueryKey(KeyHandle, KeyFullInformation, v57, 0x430u, &v25);
        v21 = v5;
        if ( v5 >= 0 )
        {
          DataLength = 0;
          *(_QWORD *)Unused = 0;
          v5 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, &DataLength, (ULONG)Unused);
          v21 = v5;
          if ( v5 >= 0 )
          {
LABEL_11:
            if ( !v25 )
            {
              CRegistryObject::Close(&KeyHandle);
              return 3221225816LL;
            }
            v8 = 0;
            v9 = 0;
            v22 = 0;
            Heap = 0;
            v27 = 0;
            while ( 1 )
            {
              if ( v4 >= v58 )
              {
LABEL_61:
                if ( v5 >= 0 )
                  *((_DWORD *)a1 + 40) = v8;
                goto LABEL_63;
              }
              v35 = 0;
              *(_QWORD *)Unused = 0;
              memset_0(v51, 0, 0x418u);
              memset_0(v59, 0, sizeof(v59));
              v5 = NtEnumerateKey(KeyHandle, v4, KeyBasicInformation, v51, 0x418u, &v35);
              v21 = v5;
              if ( v5 < 0 )
                goto LABEL_63;
              if ( wcsncmp_0(&v52[2], L"Names", 5u) )
                break;
LABEL_65:
              ++v4;
            }
            CUserObject::CUserObject((CUserObject *)v42, v11, (struct CDomainObject *)a1);
            v12 = RtlStringCbPrintfW(v59, 0x800u, L"%ws\\Users\\", a2);
            AccountObjectDsName = v12;
            v21 = v12;
            if ( v12 >= 0 )
            {
              v12 = RtlStringCbCatNW(v59, v13, &v52[2], *(unsigned int *)v52);
              AccountObjectDsName = v12;
              v21 = v12;
            }
            if ( v12 >= 0 )
            {
              AccountObjectDsName = CRegistryObject::Open((CRegistryObject *)v43, v59);
              v21 = AccountObjectDsName;
              if ( AccountObjectDsName >= 0 )
              {
                AccountObjectDsName = CUserObject::Fill((CUserObject *)v42);
                v21 = AccountObjectDsName;
                if ( AccountObjectDsName >= 0 )
                {
                  v9 = 1;
                  v22 = 1;
                  v15 = 0;
                  v26 = 0;
                  if ( (*((_BYTE *)a1 + 116) & 1) == 0 && (v48 == 503 || v48 == 504) )
                  {
                    v15 = 1;
                    v26 = 1;
                  }
                  if ( !v15 )
                    v15 = v49;
                  v26 = v15;
                  if ( v15 )
                  {
                    AccountObjectDsName = 0;
LABEL_30:
                    v21 = AccountObjectDsName;
                    goto LABEL_45;
                  }
                  Heap = SourceString;
                  v27 = SourceString;
                  DataLength = 42;
                  RdnForSamObject = GetRdnForSamObject(v46);
                  AccountObjectDsName = RdnForSamObject;
                  v21 = RdnForSamObject;
                  if ( RdnForSamObject == -1073741789 )
                  {
                    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataLength);
                    v27 = Heap;
                    if ( !Heap )
                    {
                      AccountObjectDsName = -1073741670;
                      goto LABEL_30;
                    }
                    RdnForSamObject = GetRdnForSamObject(v46);
                    AccountObjectDsName = RdnForSamObject;
                    v21 = RdnForSamObject;
                  }
                  if ( RdnForSamObject >= 0 )
                  {
                    v36 = v47;
                    DestinationString = 0;
                    RtlInitUnicodeString(&DestinationString, Heap);
                    AccountObjectDsName = SampDsCreateAccountObjectDsName(
                                            (unsigned int)a1[10],
                                            0,
                                            4,
                                            (unsigned int)&DestinationString,
                                            0,
                                            (__int64)&v36,
                                            *((_BYTE *)a1 + 116) & 1,
                                            (__int64)Unused);
                    v21 = AccountObjectDsName;
                    if ( AccountObjectDsName >= 0 )
                    {
                      AccountObjectDsName = CConversionObject::Convert((CConversionObject *)v45);
                      v21 = AccountObjectDsName;
                      if ( AccountObjectDsName >= 0 )
                      {
                        v21 = CConversionObject::UpgradeUserParms((CConversionObject *)v45);
                        if ( v21 < 0 )
                        {
                          v40 = 0;
                          RtlInitUnicodeString(&v40, v46);
                          SampWriteEventLog(SAMMSG_ACCEPTABLE_ERROR_UPGRADE_USER, L"ub", &v40, 4, &v21);
                        }
                        v21 = CConversionObject::CopySupplementalCreds((CConversionObject *)v45);
                        if ( v21 < 0 )
                        {
                          v41 = 0;
                          RtlInitUnicodeString(&v41, v46);
                          SampWriteEventLog(SAMMSG_ACCEPTABLE_ERROR_UPGRADE_USER, L"ub", &v41, 4, &v21);
                        }
                        v17 = *(struct _DSNAME **)Unused;
                        AccountObjectDsName = CDsSamObject::Flush((CDsSamObject *)v44, *(struct _DSNAME **)Unused);
                        v21 = AccountObjectDsName;
                        if ( AccountObjectDsName >= 0 )
                          v17 = 0;
                        *(_QWORD *)Unused = v17;
                      }
                    }
                  }
                }
              }
            }
LABEL_45:
            if ( AccountObjectDsName == -1073741725 )
            {
              v37 = 0;
              RtlInitUnicodeString(&v37, v46);
              v18 = &v37;
              v19 = SAMMSG_DUPLICATE_ACCOUNT;
              goto LABEL_51;
            }
            if ( AccountObjectDsName >= 0 )
              goto LABEL_55;
            if ( !SampIsNtStatusResourceError(AccountObjectDsName) )
            {
              if ( !v9 )
              {
                SampWriteEventLog(SAMMSG_UNKNOWN_USER_NOT_UPGRADED, L"b", 4, &v21, ResultLength);
                goto LABEL_53;
              }
              v38 = 0;
              RtlInitUnicodeString(&v38, v46);
              v18 = &v38;
              v19 = SAMMSG_USER_NOT_UPGRADED;
LABEL_51:
              SampWriteEventLog(v19, L"ub", v18, 4, &v21);
LABEL_53:
              AccountObjectDsName = 0;
              v21 = 0;
              goto LABEL_56;
            }
            if ( AccountObjectDsName >= 0 )
LABEL_55:
              ++v8;
LABEL_56:
            if ( Heap && Heap != SourceString )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              Heap = 0;
              v27 = 0;
              AccountObjectDsName = v21;
            }
            if ( AccountObjectDsName < 0 )
            {
              CUserObject::~CUserObject((CUserObject *)v42);
              v5 = v21;
              goto LABEL_61;
            }
            v9 = 0;
            v22 = 0;
            CUserObject::~CUserObject((CUserObject *)v42);
            v5 = v21;
            goto LABEL_65;
          }
        }
      }
    }
  }
LABEL_63:
  CRegistryObject::Close(&KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180315b84  mov     [rsp+arg_10], rbx
0x180315b89  mov     [rsp+arg_18], rsi
0x180315b8e  push    rdi
0x180315b8f  push    r12
0x180315b91  push    r13
0x180315b93  push    r14
0x180315b95  push    r15
0x180315b97  mov     eax, 2280h
0x180315b9c  call    _alloca_probe
0x180315ba1  sub     rsp, rax
0x180315ba4  mov     rax, cs:__security_cookie
0x180315bab  xor     rax, rsp
0x180315bae  mov     [rsp+22A8h+var_38], rax
0x180315bb6  mov     r12, rdx
0x180315bb9  mov     r13, rcx
0x180315bbc  xor     r15d, r15d
0x180315bbf  mov     [rsp+22A8h+var_2268], r15d
0x180315bc4  mov     [rsp+22A8h+var_2220], r15d
0x180315bcc  mov     [rsp+22A8h+var_221C], r15d
0x180315bd4  mov     [rsp+22A8h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x180315bdd  mov     [rsp+22A8h+var_2238], r15d
0x180315be2  mov     [rsp+22A8h+var_2230], r15
0x180315be7  mov     [rsp+22A8h+var_2228], r15d
0x180315bef  mov     [rsp+22A8h+var_2250], r15d
0x180315bf4  mov     [rsp+22A8h+Type], 0FFFFFFFFh
0x180315bff  mov     esi, 430h
0x180315c04  mov     r8d, esi; Size
0x180315c07  xor     edx, edx; Val
0x180315c09  lea     rcx, [rsp+22A8h+KeyInformation]; void *
0x180315c11  call    memset_0
0x180315c16  xor     edx, edx; Val
0x180315c18  lea     r8d, [rsi-18h]; Size
0x180315c1c  lea     rcx, [rsp+22A8h+var_1888]; void *
0x180315c24  call    memset_0
0x180315c29  xor     edx, edx; Val
0x180315c2b  mov     r8d, 800h; Size
0x180315c31  lea     rcx, [rsp+22A8h+var_838]; void *
0x180315c39  call    memset_0
0x180315c3e  lea     rax, [rsp+22A8h+var_2220]
0x180315c46  mov     [rsp+22A8h+ResultLength], rax; ResultLength
0x180315c4b  mov     r9d, esi; Length
0x180315c4e  lea     r8, [rsp+22A8h+KeyInformation]; KeyInformation
0x180315c56  lea     r14d, [r15+2]
0x180315c5a  mov     edx, r14d; KeyInformationClass
0x180315c5d  mov     rcx, [r13+8]; KeyHandle
0x180315c61  call    cs:__imp_NtQueryKey
0x180315c67  mov     ebx, eax
0x180315c69  mov     [rsp+22A8h+var_2268], eax
0x180315c6d  test    eax, eax
0x180315c6f  js      loc_1803162A5
0x180315c75  mov     edi, r15d
0x180315c78  cmp     [rsp+22A8h+var_1CA4], r15d
0x180315c80  jbe     loc_180315DA6
0x180315c86  lea     rax, [rsp+22A8h+var_221C]
0x180315c8e  mov     [rsp+22A8h+var_2280], rax; ResultLength
0x180315c93  mov     dword ptr [rsp+22A8h+ResultLength], 418h; Length
0x180315c9b  lea     r9, [rsp+22A8h+var_1888]; KeyInformation
0x180315ca3  xor     r8d, r8d; KeyInformationClass
0x180315ca6  mov     edx, edi; Index
0x180315ca8  mov     rcx, [r13+8]; KeyHandle
0x180315cac  call    cs:__imp_NtEnumerateKey
0x180315cb2  mov     ebx, eax
0x180315cb4  mov     [rsp+22A8h+var_2268], eax
0x180315cb8  test    eax, eax
0x180315cba  js      loc_1803162A5
0x180315cc0  mov     r8d, 5; MaxCount
0x180315cc6  lea     rdx, aUsers; "Users"
0x180315ccd  lea     rcx, [rsp+22A8h+String1]; String1
0x180315cd5  call    wcsncmp_0
0x180315cda  test    eax, eax
0x180315cdc  jz      short loc_180315CEE
0x180315cde  inc     edi
0x180315ce0  cmp     edi, [rsp+22A8h+var_1CA4]
0x180315ce7  jb      short loc_180315C86
0x180315ce9  jmp     loc_180315DA6
0x180315cee  mov     r9, r12
0x180315cf1  lea     r8, aWsUsers; "%ws\\Users"
0x180315cf8  mov     edx, 800h; unsigned __int64
0x180315cfd  lea     rcx, [rsp+22A8h+var_838]; unsigned __int16 *
0x180315d05  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180315d0a  mov     ebx, eax
0x180315d0c  mov     [rsp+22A8h+var_2268], eax
0x180315d10  lea     rcx, [rsp+22A8h+KeyHandle]; this
0x180315d15  test    eax, eax
0x180315d17  js      loc_1803162AA
0x180315d1d  lea     rdx, [rsp+22A8h+var_838]; unsigned __int16 *
0x180315d25  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180315d2a  mov     ebx, eax
0x180315d2c  mov     [rsp+22A8h+var_2268], eax
0x180315d30  test    eax, eax
0x180315d32  js      loc_1803162A5
0x180315d38  lea     rax, [rsp+22A8h+var_2250]
0x180315d3d  mov     [rsp+22A8h+ResultLength], rax; ResultLength
0x180315d42  mov     r9d, esi; Length
0x180315d45  lea     r8, [rsp+22A8h+var_1468]; KeyInformation
0x180315d4d  mov     edx, r14d; KeyInformationClass
0x180315d50  mov     rcx, [rsp+22A8h+KeyHandle]; KeyHandle
0x180315d55  call    cs:__imp_NtQueryKey
0x180315d5b  mov     ebx, eax
0x180315d5d  mov     [rsp+22A8h+var_2268], eax
0x180315d61  test    eax, eax
0x180315d63  js      loc_1803162A5
0x180315d69  mov     [rsp+22A8h+DataLength], r15d
0x180315d6e  mov     qword ptr [rsp+22A8h+Unused], r15
0x180315d73  lea     rax, [rsp+22A8h+Unused]
0x180315d78  mov     [rsp+22A8h+ResultLength], rax; Unused
0x180315d7d  lea     r9, [rsp+22A8h+DataLength]; DataLength
0x180315d82  xor     r8d, r8d; Data
0x180315d85  lea     rdx, [rsp+22A8h+Type]; Type
0x180315d8d  mov     rcx, [rsp+22A8h+KeyHandle]; KeyHandle
0x180315d92  call    cs:__imp_RtlpNtQueryValueKey
0x180315d98  mov     ebx, eax
0x180315d9a  mov     [rsp+22A8h+var_2268], eax
0x180315d9e  test    eax, eax
0x180315da0  js      loc_1803162A5
0x180315da6  cmp     [rsp+22A8h+var_2250], r15d
0x180315dab  jnz     short loc_180315DC1
0x180315dad  lea     rcx, [rsp+22A8h+KeyHandle]; this
0x180315db2  call    ?Close@CRegistryObject@@QEAAJXZ; CRegistryObject::Close(void)
0x180315db7  mov     eax, 0C0000158h
0x180315dbc  jmp     loc_1803162B1
0x180315dc1  mov     r14d, r15d
0x180315dc4  mov     sil, r15b
0x180315dc7  mov     [rsp+22A8h+var_2264], r15b
0x180315dcc  mov     rdi, r15
0x180315dcf  mov     [rsp+22A8h+var_2248], r15
0x180315dd4  cmp     r15d, [rsp+22A8h+var_1454]
0x180315ddc  jnb     loc_18031629A
0x180315de2  mov     [rsp+22A8h+var_2214], 0
0x180315ded  mov     qword ptr [rsp+22A8h+Unused], 0
0x180315df6  mov     ebx, 418h
0x180315dfb  mov     r8d, ebx; Size
0x180315dfe  xor     edx, edx; Val
0x180315e00  lea     rcx, [rsp+22A8h+var_20D8]; void *
0x180315e08  call    memset_0
0x180315e0d  xor     edx, edx; Val
0x180315e0f  mov     r8d, 800h; Size
0x180315e15  lea     rcx, [rsp+22A8h+var_1038]; void *
0x180315e1d  call    memset_0
0x180315e22  lea     rax, [rsp+22A8h+var_2214]
0x180315e2a  mov     [rsp+22A8h+var_2280], rax; ResultLength
0x180315e2f  mov     dword ptr [rsp+22A8h+ResultLength], ebx; Length
0x180315e33  lea     r9, [rsp+22A8h+var_20D8]; KeyInformation
0x180315e3b  xor     r8d, r8d; KeyInformationClass
0x180315e3e  mov     edx, r15d; Index
0x180315e41  mov     rcx, [rsp+22A8h+KeyHandle]; KeyHandle
0x180315e46  call    cs:__imp_NtEnumerateKey
0x180315e4c  mov     ebx, eax
0x180315e4e  mov     [rsp+22A8h+var_2268], eax
0x180315e52  test    eax, eax
0x180315e54  js      loc_1803162A5
0x180315e5a  mov     r8d, 5; MaxCount
0x180315e60  lea     rdx, aNames; "Names"
0x180315e67  lea     rcx, [rsp+22A8h+var_20CC+4]; String1
0x180315e6f  call    wcsncmp_0
0x180315e74  test    eax, eax
0x180315e76  jz      loc_1803162EF
0x180315e7c  mov     r8, r13; struct CDomainObject *
0x180315e7f  lea     rcx, [rsp+22A8h+var_21B8]; this
0x180315e87  call    ??0CUserObject@@QEAA@AEAVCDomainObject@@0@Z; CUserObject::CUserObject(CDomainObject &,CDomainObject &)
0x180315e8c  mov     r9, r12
0x180315e8f  lea     r8, aWsUsers_0; "%ws\\Users\\"
0x180315e96  mov     edx, 800h; unsigned __int64
0x180315e9b  lea     rcx, [rsp+22A8h+var_1038]; unsigned __int16 *
0x180315ea3  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180315ea8  mov     ecx, eax
0x180315eaa  mov     [rsp+22A8h+var_2268], eax
0x180315eae  test    eax, eax
0x180315eb0  js      short loc_180315ED5
0x180315eb2  mov     r9d, dword ptr [rsp+22A8h+var_20CC]; unsigned __int64
0x180315eba  lea     r8, [rsp+22A8h+var_20CC+4]; unsigned __int16 *
0x180315ec2  lea     rcx, [rsp+22A8h+var_1038]; unsigned __int16 *
0x180315eca  call    ?RtlStringCbCatNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180315ecf  mov     ecx, eax
0x180315ed1  mov     [rsp+22A8h+var_2268], eax
0x180315ed5  test    eax, eax
0x180315ed7  js      loc_180316183
0x180315edd  lea     rdx, [rsp+22A8h+var_1038]; unsigned __int16 *
0x180315ee5  lea     rcx, [rsp+22A8h+var_21B0]; this
0x180315eed  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180315ef2  mov     ecx, eax
0x180315ef4  mov     [rsp+22A8h+var_2268], eax
0x180315ef8  test    eax, eax
0x180315efa  js      loc_180316183
0x180315f00  lea     rcx, [rsp+22A8h+var_21B8]; this
0x180315f08  call    ?Fill@CUserObject@@UEAAJXZ; CUserObject::Fill(void)
0x180315f0d  mov     ecx, eax
0x180315f0f  mov     [rsp+22A8h+var_2268], eax
0x180315f13  test    eax, eax
0x180315f15  js      loc_180316183
0x180315f1b  mov     sil, 1
0x180315f1e  mov     [rsp+22A8h+var_2264], sil
0x180315f23  xor     eax, eax
0x180315f25  mov     [rsp+22A8h+var_224C], eax
0x180315f29  test    [r13+74h], sil
0x180315f2d  jnz     short loc_180315F4D
0x180315f2f  mov     rcx, qword ptr [rsp+22A8h+var_211C]
0x180315f37  sub     ecx, 1F7h
0x180315f3d  jz      short loc_180315F44
0x180315f3f  cmp     ecx, 1
0x180315f42  jnz     short loc_180315F4D
0x180315f44  mov     eax, 1
0x180315f49  mov     [rsp+22A8h+var_224C], eax
0x180315f4d  test    eax, eax
0x180315f4f  cmovz   eax, [rsp+22A8h+var_211C+4]
0x180315f57  mov     [rsp+22A8h+var_224C], eax
0x180315f5b  test    eax, eax
0x180315f5d  jz      short loc_180315F6A
0x180315f5f  xor     ecx, ecx
0x180315f61  mov     [rsp+22A8h+var_2268], ecx
0x180315f65  jmp     loc_180316183
0x180315f6a  lea     rdi, [rsp+22A8h+SourceString]
0x180315f72  mov     [rsp+22A8h+var_2248], rdi
0x180315f77  mov     [rsp+22A8h+DataLength], 2Ah ; '*'
0x180315f7f  lea     r9, [rsp+22A8h+DataLength]
0x180315f84  lea     r8, [rsp+22A8h+SourceString]
0x180315f8c  mov     edx, 4
0x180315f91  mov     rcx, [rsp+22A8h+var_2128]; SourceString
0x180315f99  call    GetRdnForSamObject
0x180315f9e  mov     ecx, eax
0x180315fa0  mov     [rsp+22A8h+var_2268], eax
0x180315fa4  cmp     eax, 0C0000023h
0x180315fa9  jnz     short loc_180315FF9
0x180315fab  mov     r8d, [rsp+22A8h+DataLength]; Size
0x180315fb0  mov     rcx, gs:60h
0x180315fb9  xor     edx, edx; Flags
0x180315fbb  mov     rcx, [rcx+30h]; HeapHandle
0x180315fbf  call    cs:__imp_RtlAllocateHeap
0x180315fc5  mov     rdi, rax
0x180315fc8  mov     [rsp+22A8h+var_2248], rax
0x180315fcd  test    rax, rax
0x180315fd0  jnz     short loc_180315FD9
0x180315fd2  mov     ecx, 0C000009Ah
0x180315fd7  jmp     short loc_180315F61
0x180315fd9  lea     r9, [rsp+22A8h+DataLength]
0x180315fde  mov     r8, rax
0x180315fe1  mov     edx, 4
0x180315fe6  mov     rcx, [rsp+22A8h+var_2128]; SourceString
0x180315fee  call    GetRdnForSamObject
0x180315ff3  mov     ecx, eax
0x180315ff5  mov     [rsp+22A8h+var_2268], eax
0x180315ff9  test    eax, eax
0x180315ffb  js      loc_180316183
0x180316001  mov     rax, [rsp+188h]
0x180316009  mov     [rsp+22A8h+var_2210], eax
0x180316010  xorps   xmm0, xmm0
0x180316013  movups  xmmword ptr [rsp+22A8h+DestinationString.Length], xmm0
0x18031601b  mov     rdx, rdi; SourceString
0x18031601e  lea     rcx, [rsp+22A8h+DestinationString]; DestinationString
0x180316026  call    cs:__imp_RtlInitUnicodeString
0x18031602c  mov     al, [r13+74h]
0x180316030  and     al, sil
0x180316033  lea     rcx, [rsp+22A8h+Unused]
0x180316038  mov     [rsp+22A8h+var_2270], rcx
0x18031603d  mov     [rsp+22A8h+var_2278], al
0x180316041  lea     rax, [rsp+22A8h+var_2210]
0x180316049  mov     [rsp+22A8h+var_2280], rax
0x18031604e  mov     [rsp+22A8h+ResultLength], 0
0x180316057  lea     r9, [rsp+22A8h+DestinationString]
0x18031605f  xor     edx, edx
0x180316061  lea     r8d, [rdx+4]
0x180316065  mov     rcx, [r13+50h]
0x180316069  call    SampDsCreateAccountObjectDsName
0x18031606e  mov     ecx, eax
0x180316070  mov     [rsp+22A8h+var_2268], eax
0x180316074  test    eax, eax
0x180316076  js      loc_180316183
0x18031607c  lea     rcx, [rsp+22A8h+var_2138]; this
0x180316084  call    ?Convert@CConversionObject@@QEAAJXZ; CConversionObject::Convert(void)
0x180316089  mov     ecx, eax
0x18031608b  mov     [rsp+22A8h+var_2268], eax
0x18031608f  test    eax, eax
0x180316091  js      loc_180316183
0x180316097  lea     rcx, [rsp+22A8h+var_2138]; this
0x18031609f  call    ?UpgradeUserParms@CConversionObject@@QEAAJXZ; CConversionObject::UpgradeUserParms(void)
0x1803160a4  mov     [rsp+22A8h+var_2268], eax
0x1803160a8  test    eax, eax
0x1803160aa  jns     short loc_1803160F9
0x1803160ac  xorps   xmm0, xmm0
0x1803160af  movups  xmmword ptr [rsp+22A8h+var_21D8.Length], xmm0
0x1803160b7  mov     rdx, [rsp+22A8h+var_2128]; SourceString
0x1803160bf  lea     rcx, [rsp+22A8h+var_21D8]; DestinationString
0x1803160c7  call    cs:__imp_RtlInitUnicodeString
0x1803160cd  lea     rax, [rsp+22A8h+var_2268]
0x1803160d2  mov     [rsp+22A8h+ResultLength], rax
0x1803160d7  mov     r9d, 4
0x1803160dd  lea     r8, [rsp+22A8h+var_21D8]
0x1803160e5  lea     rdx, aUb; "ub"
0x1803160ec  lea     rcx, SAMMSG_ACCEPTABLE_ERROR_UPGRADE_USER
0x1803160f3  call    cs:__imp_SampWriteEventLog
0x1803160f9  lea     rcx, [rsp+22A8h+var_2138]; this
0x180316101  call    ?CopySupplementalCreds@CConversionObject@@QEAAJXZ; CConversionObject::CopySupplementalCreds(void)
0x180316106  mov     [rsp+22A8h+var_2268], eax
0x18031610a  test    eax, eax
0x18031610c  jns     short loc_18031615B
0x18031610e  xorps   xmm0, xmm0
0x180316111  movups  xmmword ptr [rsp+22A8h+var_21C8.Length], xmm0
0x180316119  mov     rdx, [rsp+22A8h+var_2128]; SourceString
0x180316121  lea     rcx, [rsp+22A8h+var_21C8]; DestinationString
0x180316129  call    cs:__imp_RtlInitUnicodeString
  ... truncated ...
```
