# ConvertGroups(CDomainObject &,ushort const *)

- ea: `0x1803154e0`
- end: `0x180315b7c`
- name: `?ConvertGroups@@YAJAEAVCDomainObject@@PEBG@Z`
- size: `1692`
- prototype: `__int64 __fastcall(HANDLE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x180314fa0`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180312e18`
- `0x180312ea8`
- `0x1803134a8`
- `0x180313af0`
- `0x180313e90`
- `0x180314350`
- `0x180314520`
- `0x1803146d0`
- `0x1803154e0`
- `0x180316480`
- `0x180316564`
- `0x180316648`
- `0x18031666c`
- `0x1803dedec`
- `0x180453340`
- `0x1804533ac`

## import_xrefs

- `ntdll!RtlpNtQueryValueKey` at `0x1803156ff`
- `ntdll!RtlpNtQueryValueKey` at `0x1803156ff`
- `ntdll!NtEnumerateKey` at `0x180315617`
- `ntdll!NtEnumerateKey` at `0x1803157b5`
- `ntdll!NtEnumerateKey` at `0x180315617`
- `ntdll!NtEnumerateKey` at `0x1803157b5`
- `ntdll!RtlAllocateHeap` at `0x180315911`
- `ntdll!RtlAllocateHeap` at `0x180315911`
- `ntdll!RtlFreeHeap` at `0x180315af9`
- `ntdll!RtlFreeHeap` at `0x180471c03`
- `ntdll!RtlFreeHeap` at `0x180315af9`
- `ntdll!RtlFreeHeap` at `0x180471c03`
- `ntdll!NtQueryKey` at `0x1803155cf`
- `ntdll!NtQueryKey` at `0x1803156c2`
- `ntdll!NtQueryKey` at `0x1803155cf`
- `ntdll!NtQueryKey` at `0x1803156c2`
- `ntdll!RtlInitUnicodeString` at `0x18031596e`
- `ntdll!RtlInitUnicodeString` at `0x180315a2b`
- `ntdll!RtlInitUnicodeString` at `0x180315a73`
- `ntdll!RtlInitUnicodeString` at `0x180471b43`
- `ntdll!RtlInitUnicodeString` at `0x180471b83`
- `ntdll!RtlInitUnicodeString` at `0x18031596e`
- `ntdll!RtlInitUnicodeString` at `0x180315a2b`
- `ntdll!RtlInitUnicodeString` at `0x180315a73`
- `ntdll!RtlInitUnicodeString` at `0x180471b43`
- `ntdll!RtlInitUnicodeString` at `0x180471b83`
- `SAMSRV!SampWriteEventLog` at `0x180315a9f`
- `SAMSRV!SampWriteEventLog` at `0x180315ac0`
- `SAMSRV!SampWriteEventLog` at `0x180471bad`
- `SAMSRV!SampWriteEventLog` at `0x180471bcd`
- `SAMSRV!SampWriteEventLog` at `0x180315a9f`
- `SAMSRV!SampWriteEventLog` at `0x180315ac0`
- `SAMSRV!SampWriteEventLog` at `0x180471bad`
- `SAMSRV!SampWriteEventLog` at `0x180471bcd`
- `SAMSRV!SampGetNT4UpgradeInProgress` at `0x1803158a5`
- `SAMSRV!SampGetNT4UpgradeInProgress` at `0x1803158a5`

## pseudocode

```c
__int64 __fastcall ConvertGroups(HANDLE *a1, const unsigned __int16 *a2)
{
  ULONG v4; // r15d
  NTSTATUS v5; // ebx
  ULONG v6; // edi
  int v8; // r14d
  char v9; // si
  WCHAR *Heap; // rdi
  struct CDomainObject *v11; // rdx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int AccountObjectDsName; // eax
  __int64 v16; // rcx
  int RdnForSamObject; // eax
  struct _UNICODE_STRING *v18; // r8
  __int64 *v19; // rcx
  int v20; // ecx
  PULONG ResultLength; // [rsp+48h] [rbp-2668h]
  NTSTATUS v22; // [rsp+68h] [rbp-2648h] BYREF
  char v23; // [rsp+6Ch] [rbp-2644h]
  ULONG DataLength; // [rsp+70h] [rbp-2640h] BYREF
  ULONG Unused[2]; // [rsp+78h] [rbp-2638h] BYREF
  ULONG v26; // [rsp+80h] [rbp-2630h] BYREF
  WCHAR *v27; // [rsp+88h] [rbp-2628h]
  HANDLE KeyHandle; // [rsp+90h] [rbp-2620h] BYREF
  int v29; // [rsp+98h] [rbp-2618h]
  __int64 v30; // [rsp+A0h] [rbp-2610h]
  int v31; // [rsp+A8h] [rbp-2608h]
  ULONG v32; // [rsp+B0h] [rbp-2600h] BYREF
  ULONG v33; // [rsp+B4h] [rbp-25FCh] BYREF
  ULONG Type; // [rsp+B8h] [rbp-25F8h] BYREF
  ULONG v35; // [rsp+BCh] [rbp-25F4h] BYREF
  struct _UNICODE_STRING v36; // [rsp+C0h] [rbp-25F0h] BYREF
  struct _UNICODE_STRING v37; // [rsp+D0h] [rbp-25E0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-25D0h] BYREF
  _BYTE v39[8]; // [rsp+F8h] [rbp-25B8h] BYREF
  _BYTE v40[64]; // [rsp+100h] [rbp-25B0h] BYREF
  _BYTE v41[56]; // [rsp+140h] [rbp-2570h] BYREF
  _BYTE v42[16]; // [rsp+178h] [rbp-2538h] BYREF
  PCWSTR v43; // [rsp+188h] [rbp-2528h]
  int v44; // [rsp+190h] [rbp-2520h]
  WCHAR SourceString[24]; // [rsp+1A8h] [rbp-2508h] BYREF
  _BYTE KeyInformation[20]; // [rsp+1D8h] [rbp-24D8h] BYREF
  ULONG v47; // [rsp+1ECh] [rbp-24C4h]
  _BYTE v48[16]; // [rsp+608h] [rbp-20A8h] BYREF
  wchar_t String1[520]; // [rsp+618h] [rbp-2098h] BYREF
  _BYTE v50[20]; // [rsp+A28h] [rbp-1C88h] BYREF
  ULONG v51; // [rsp+A3Ch] [rbp-1C74h]
  _BYTE v52[12]; // [rsp+E58h] [rbp-1858h] BYREF
  unsigned __int16 v53[4]; // [rsp+E64h] [rbp-184Ch] BYREF
  unsigned __int16 v54[1024]; // [rsp+1678h] [rbp-1038h] BYREF
  unsigned __int16 v55[1024]; // [rsp+1E78h] [rbp-838h] BYREF

  v4 = 0;
  v22 = 0;
  v32 = 0;
  v33 = 0;
  KeyHandle = (HANDLE)-1LL;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v26 = 0;
  Type = -1;
  memset_0(KeyInformation, 0, 0x430u);
  memset_0(v48, 0, 0x418u);
  memset_0(v50, 0, 0x430u);
  memset_0(v55, 0, sizeof(v55));
  v5 = NtQueryKey(a1[1], KeyFullInformation, KeyInformation, 0x430u, &v32);
  v22 = v5;
  if ( v5 >= 0 )
  {
    v6 = 0;
    if ( !v47 )
      goto LABEL_11;
    while ( 1 )
    {
      v5 = NtEnumerateKey(a1[1], v6, KeyBasicInformation, v48, 0x418u, &v33);
      v22 = v5;
      if ( v5 < 0 )
        goto LABEL_54;
      if ( !wcsncmp_0(String1, L"Groups", 6u) )
        break;
      if ( ++v6 >= v47 )
        goto LABEL_11;
    }
    v5 = RtlStringCbPrintfW(v55, 0x800u, L"%ws\\Groups", a2);
    v22 = v5;
    if ( v5 >= 0 )
    {
      v5 = CRegistryObject::Open((CRegistryObject *)&KeyHandle, v55);
      v22 = v5;
      if ( v5 >= 0 )
      {
        v5 = NtQueryKey(KeyHandle, KeyFullInformation, v50, 0x430u, &v26);
        v22 = v5;
        if ( v5 >= 0 )
        {
          *(_QWORD *)Unused = 0;
          DataLength = 0;
          v5 = RtlpNtQueryValueKey(KeyHandle, &Type, 0, &DataLength, (ULONG)Unused);
          v22 = v5;
          if ( v5 >= 0 )
          {
LABEL_11:
            if ( !v26 )
            {
              CRegistryObject::Close(&KeyHandle);
              return 3221225816LL;
            }
            v8 = 0;
            v9 = 0;
            v23 = 0;
            Heap = 0;
            v27 = 0;
            while ( 1 )
            {
              if ( v4 >= v51 )
              {
LABEL_52:
                if ( v5 >= 0 )
                  *((_DWORD *)a1 + 41) = v8;
                goto LABEL_54;
              }
              v35 = 0;
              *(_QWORD *)Unused = 0;
              memset_0(v52, 0, 0x818u);
              memset_0(v54, 0, sizeof(v54));
              v5 = NtEnumerateKey(KeyHandle, v4, KeyBasicInformation, v52, 0x818u, &v35);
              v22 = v5;
              if ( v5 < 0 )
                goto LABEL_54;
              if ( wcsncmp_0(&v53[2], L"Names", 5u) )
                break;
LABEL_56:
              ++v4;
            }
            CGroupObject::CGroupObject((CGroupObject *)v39, v11, (struct CDomainObject *)a1);
            v12 = RtlStringCbPrintfW(v54, 0x800u, L"%ws\\Groups\\", a2);
            v13 = v12;
            v22 = v12;
            v14 = v12;
            if ( v12 >= 0 )
            {
              v13 = RtlStringCbCatNW(v54, (unsigned int)v12, &v53[2], *(unsigned int *)v53);
              v22 = v13;
              v14 = v13;
            }
            if ( v14 < 0 )
            {
LABEL_36:
              if ( v14 == -1073741723 )
              {
                v36 = 0;
                RtlInitUnicodeString(&v36, v43);
                v18 = &v36;
                v19 = SAMMSG_DUPLICATE_ACCOUNT;
                goto LABEL_42;
              }
              if ( v14 >= 0 )
                goto LABEL_46;
              if ( !SampIsNtStatusResourceError(v14) )
              {
                if ( !v9 )
                {
                  SampWriteEventLog(SAMMSG_UNKNOWN_GROUP_NOT_UPGRADED, L"b", 4, &v22, ResultLength);
                  goto LABEL_44;
                }
                v37 = 0;
                RtlInitUnicodeString(&v37, v43);
                v18 = &v37;
                v19 = SAMMSG_GROUP_NOT_UPGRADED;
LABEL_42:
                SampWriteEventLog(v19, L"ub", v18, 4, &v22);
LABEL_44:
                v13 = 0;
                v22 = 0;
                goto LABEL_47;
              }
              if ( v20 >= 0 )
LABEL_46:
                ++v8;
LABEL_47:
              if ( Heap && Heap != SourceString )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
                Heap = 0;
                v27 = 0;
                v13 = v22;
              }
              if ( v13 < 0 )
              {
                CGroupObject::~CGroupObject((CGroupObject *)v39);
                v5 = v22;
                goto LABEL_52;
              }
              v9 = 0;
              v23 = 0;
              CGroupObject::~CGroupObject((CGroupObject *)v39);
              v5 = v22;
              goto LABEL_56;
            }
            AccountObjectDsName = CRegistryObject::Open((CRegistryObject *)v40, v54);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0
              || (AccountObjectDsName = CGroupObject::Fill((CGroupObject *)v39),
                  v13 = AccountObjectDsName,
                  v22 = AccountObjectDsName,
                  AccountObjectDsName < 0) )
            {
LABEL_35:
              v14 = AccountObjectDsName;
              goto LABEL_36;
            }
            v9 = 1;
            v23 = 1;
            if ( v44 == 513 && !(unsigned __int8)SampGetNT4UpgradeInProgress(v16, (unsigned int)AccountObjectDsName) )
            {
              v13 = 0;
              v22 = 0;
              v14 = 0;
              goto LABEL_36;
            }
            Heap = SourceString;
            v27 = SourceString;
            DataLength = 42;
            RdnForSamObject = GetRdnForSamObject(v43);
            v13 = RdnForSamObject;
            v22 = RdnForSamObject;
            if ( RdnForSamObject == -1073741789 )
            {
              Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataLength);
              v27 = Heap;
              if ( !Heap )
              {
                AccountObjectDsName = -1073741670;
LABEL_34:
                v22 = AccountObjectDsName;
                v13 = AccountObjectDsName;
                goto LABEL_35;
              }
              RdnForSamObject = GetRdnForSamObject(v43);
              v13 = RdnForSamObject;
              v22 = RdnForSamObject;
            }
            v14 = RdnForSamObject;
            if ( RdnForSamObject < 0 )
              goto LABEL_36;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, Heap);
            AccountObjectDsName = SampDsCreateAccountObjectDsName(
                                    (unsigned int)a1[10],
                                    (unsigned int)a1[18],
                                    2,
                                    (unsigned int)&DestinationString,
                                    0,
                                    0,
                                    *((_BYTE *)a1 + 116) & 1,
                                    (__int64)Unused);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_35;
            AccountObjectDsName = CConversionObject::Convert((CConversionObject *)v42);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_35;
            AccountObjectDsName = CDsSamObject::Flush((CDsSamObject *)v41, *(struct _DSNAME **)Unused);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_35;
            *(_QWORD *)Unused = 0;
            AccountObjectDsName = CGroupObject::ConvertMembers((CGroupObject *)v39);
            goto LABEL_34;
          }
        }
      }
    }
  }
LABEL_54:
  CRegistryObject::Close(&KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1803154e0  mov     [rsp+arg_10], rbx
0x1803154e5  mov     [rsp+arg_18], rsi
0x1803154ea  push    rdi
0x1803154eb  push    r12
0x1803154ed  push    r13
0x1803154ef  push    r14
0x1803154f1  push    r15
0x1803154f3  mov     eax, 2660h
0x1803154f8  call    _alloca_probe
0x1803154fd  sub     rsp, rax
0x180315500  mov     rax, cs:__security_cookie
0x180315507  xor     rax, rsp
0x18031550a  mov     [rsp+2688h+var_38], rax
0x180315512  mov     r12, rdx
0x180315515  mov     r13, rcx
0x180315518  xor     r15d, r15d
0x18031551b  mov     [rsp+2688h+var_2648], r15d
0x180315520  mov     [rsp+2688h+var_2600], r15d
0x180315528  mov     [rsp+2688h+var_25FC], r15d
0x180315530  mov     [rsp+2688h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x180315539  mov     [rsp+2688h+var_2618], r15d
0x18031553e  mov     [rsp+2688h+var_2610], r15
0x180315543  mov     [rsp+2688h+var_2608], r15d
0x18031554b  mov     [rsp+2688h+var_2630], r15d
0x180315550  mov     [rsp+2688h+Type], 0FFFFFFFFh
0x18031555b  mov     esi, 430h
0x180315560  mov     r8d, esi; Size
0x180315563  xor     edx, edx; Val
0x180315565  lea     rcx, [rsp+2688h+KeyInformation]; void *
0x18031556d  call    memset_0
0x180315572  lea     r14d, [rsi-18h]
0x180315576  mov     r8d, r14d; Size
0x180315579  xor     edx, edx; Val
0x18031557b  lea     rcx, [rsp+2688h+var_20A8]; void *
0x180315583  call    memset_0
0x180315588  mov     r8d, esi; Size
0x18031558b  xor     edx, edx; Val
0x18031558d  lea     rcx, [rsp+2688h+var_1C88]; void *
0x180315595  call    memset_0
0x18031559a  xor     edx, edx; Val
0x18031559c  mov     r8d, 800h; Size
0x1803155a2  lea     rcx, [rsp+2688h+var_838]; void *
0x1803155aa  call    memset_0
0x1803155af  lea     rax, [rsp+2688h+var_2600]
0x1803155b7  mov     [rsp+2688h+ResultLength], rax; ResultLength
0x1803155bc  mov     r9d, esi; Length
0x1803155bf  lea     r8, [rsp+2688h+KeyInformation]; KeyInformation
0x1803155c7  lea     edx, [r15+2]; KeyInformationClass
0x1803155cb  mov     rcx, [r13+8]; KeyHandle
0x1803155cf  call    cs:__imp_NtQueryKey
0x1803155d5  mov     ebx, eax
0x1803155d7  mov     [rsp+2688h+var_2648], eax
0x1803155db  test    eax, eax
0x1803155dd  js      loc_180315B2B
0x1803155e3  mov     edi, r15d
0x1803155e6  cmp     [rsp+2688h+var_24C4], r15d
0x1803155ee  jbe     loc_180315713
0x1803155f4  lea     rax, [rsp+2688h+var_25FC]
0x1803155fc  mov     [rsp+2688h+var_2660], rax; ResultLength
0x180315601  mov     dword ptr [rsp+2688h+ResultLength], r14d; Length
0x180315606  lea     r9, [rsp+2688h+var_20A8]; KeyInformation
0x18031560e  xor     r8d, r8d; KeyInformationClass
0x180315611  mov     edx, edi; Index
0x180315613  mov     rcx, [r13+8]; KeyHandle
0x180315617  call    cs:__imp_NtEnumerateKey
0x18031561d  mov     ebx, eax
0x18031561f  mov     [rsp+2688h+var_2648], eax
0x180315623  test    eax, eax
0x180315625  js      loc_180315B2B
0x18031562b  mov     r8d, 6; MaxCount
0x180315631  lea     rdx, aGroups; "Groups"
0x180315638  lea     rcx, [rsp+2688h+String1]; String1
0x180315640  call    wcsncmp_0
0x180315645  test    eax, eax
0x180315647  jz      short loc_180315659
0x180315649  inc     edi
0x18031564b  cmp     edi, [rsp+2688h+var_24C4]
0x180315652  jb      short loc_1803155F4
0x180315654  jmp     loc_180315713
0x180315659  mov     r9, r12
0x18031565c  lea     r8, aWsGroups_0; "%ws\\Groups"
0x180315663  mov     edx, 800h; unsigned __int64
0x180315668  lea     rcx, [rsp+2688h+var_838]; unsigned __int16 *
0x180315670  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180315675  mov     ebx, eax
0x180315677  mov     [rsp+2688h+var_2648], eax
0x18031567b  lea     rcx, [rsp+2688h+KeyHandle]; this
0x180315680  test    eax, eax
0x180315682  js      loc_180315B30
0x180315688  lea     rdx, [rsp+2688h+var_838]; unsigned __int16 *
0x180315690  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180315695  mov     ebx, eax
0x180315697  mov     [rsp+2688h+var_2648], eax
0x18031569b  test    eax, eax
0x18031569d  js      loc_180315B2B
0x1803156a3  lea     rax, [rsp+2688h+var_2630]
0x1803156a8  mov     [rsp+2688h+ResultLength], rax; ResultLength
0x1803156ad  mov     r9d, esi; Length
0x1803156b0  lea     r8, [rsp+2688h+var_1C88]; KeyInformation
0x1803156b8  mov     edx, 2; KeyInformationClass
0x1803156bd  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x1803156c2  call    cs:__imp_NtQueryKey
0x1803156c8  mov     ebx, eax
0x1803156ca  mov     [rsp+2688h+var_2648], eax
0x1803156ce  test    eax, eax
0x1803156d0  js      loc_180315B2B
0x1803156d6  mov     qword ptr [rsp+2688h+Unused], r15
0x1803156db  mov     [rsp+2688h+DataLength], r15d
0x1803156e0  lea     rax, [rsp+2688h+Unused]
0x1803156e5  mov     [rsp+2688h+ResultLength], rax; Unused
0x1803156ea  lea     r9, [rsp+2688h+DataLength]; DataLength
0x1803156ef  xor     r8d, r8d; Data
0x1803156f2  lea     rdx, [rsp+2688h+Type]; Type
0x1803156fa  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x1803156ff  call    cs:__imp_RtlpNtQueryValueKey
0x180315705  mov     ebx, eax
0x180315707  mov     [rsp+2688h+var_2648], eax
0x18031570b  test    eax, eax
0x18031570d  js      loc_180315B2B
0x180315713  cmp     [rsp+2688h+var_2630], r15d
0x180315718  jnz     short loc_18031572E
0x18031571a  lea     rcx, [rsp+2688h+KeyHandle]; this
0x18031571f  call    ?Close@CRegistryObject@@QEAAJXZ; CRegistryObject::Close(void)
0x180315724  mov     eax, 0C0000158h
0x180315729  jmp     loc_180315B37
0x18031572e  mov     r14d, r15d
0x180315731  mov     sil, r15b
0x180315734  mov     [rsp+2688h+var_2644], r15b
0x180315739  mov     rdi, r15
0x18031573c  mov     [rsp+2688h+var_2628], r15
0x180315741  cmp     r15d, [rsp+2688h+var_1C74]
0x180315749  jnb     loc_180315B20
0x18031574f  mov     [rsp+2688h+var_25F4], 0
0x18031575a  mov     qword ptr [rsp+2688h+Unused], 0
0x180315763  xor     edx, edx; Val
0x180315765  mov     r8d, 818h; Size
0x18031576b  lea     rcx, [rsp+2688h+var_1858]; void *
0x180315773  call    memset_0
0x180315778  xor     edx, edx; Val
0x18031577a  mov     r8d, 800h; Size
0x180315780  lea     rcx, [rsp+2688h+var_1038]; void *
0x180315788  call    memset_0
0x18031578d  lea     rax, [rsp+2688h+var_25F4]
0x180315795  mov     [rsp+2688h+var_2660], rax; ResultLength
0x18031579a  mov     dword ptr [rsp+2688h+ResultLength], 818h; Length
0x1803157a2  lea     r9, [rsp+2688h+var_1858]; KeyInformation
0x1803157aa  xor     r8d, r8d; KeyInformationClass
0x1803157ad  mov     edx, r15d; Index
0x1803157b0  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x1803157b5  call    cs:__imp_NtEnumerateKey
0x1803157bb  mov     ebx, eax
0x1803157bd  mov     [rsp+2688h+var_2648], eax
0x1803157c1  test    eax, eax
0x1803157c3  js      loc_180315B2B
0x1803157c9  mov     r8d, 5; MaxCount
0x1803157cf  lea     rdx, aNames; "Names"
0x1803157d6  lea     rcx, [rsp+2688h+var_184C+4]; String1
0x1803157de  call    wcsncmp_0
0x1803157e3  test    eax, eax
0x1803157e5  jz      loc_180315B74
0x1803157eb  mov     r8, r13; struct CDomainObject *
0x1803157ee  lea     rcx, [rsp+2688h+var_25B8]; this
0x1803157f6  call    ??0CGroupObject@@QEAA@AEAVCDomainObject@@0@Z; CGroupObject::CGroupObject(CDomainObject &,CDomainObject &)
0x1803157fb  mov     r9, r12
0x1803157fe  lea     r8, aWsGroups; "%ws\\Groups\\"
0x180315805  mov     edx, 800h; unsigned __int64
0x18031580a  lea     rcx, [rsp+2688h+var_1038]; unsigned __int16 *
0x180315812  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180315817  mov     edx, eax; unsigned __int64
0x180315819  mov     [rsp+2688h+var_2648], eax
0x18031581d  mov     ecx, eax
0x18031581f  xor     ebx, ebx
0x180315821  test    eax, eax
0x180315823  js      short loc_18031584A
0x180315825  mov     r9d, dword ptr [rsp+2688h+var_184C]; unsigned __int64
0x18031582d  lea     r8, [rsp+2688h+var_184C+4]; unsigned __int16 *
0x180315835  lea     rcx, [rsp+2688h+var_1038]; unsigned __int16 *
0x18031583d  call    ?RtlStringCbCatNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180315842  mov     edx, eax
0x180315844  mov     [rsp+2688h+var_2648], eax
0x180315848  mov     ecx, eax
0x18031584a  test    ecx, ecx
0x18031584c  js      loc_180315A08
0x180315852  lea     rdx, [rsp+2688h+var_1038]; unsigned __int16 *
0x18031585a  lea     rcx, [rsp+2688h+var_25B0]; this
0x180315862  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180315867  mov     edx, eax
0x180315869  mov     [rsp+2688h+var_2648], eax
0x18031586d  test    eax, eax
0x18031586f  js      loc_180315A06
0x180315875  lea     rcx, [rsp+2688h+var_25B8]; this
0x18031587d  call    ?Fill@CGroupObject@@UEAAJXZ; CGroupObject::Fill(void)
0x180315882  mov     edx, eax
0x180315884  mov     [rsp+2688h+var_2648], eax
0x180315888  test    eax, eax
0x18031588a  js      loc_180315A06
0x180315890  mov     sil, 1
0x180315893  mov     [rsp+2688h+var_2644], sil
0x180315898  cmp     [rsp+2688h+var_2520], 201h
0x1803158a3  jnz     short loc_1803158BC
0x1803158a5  call    cs:__imp_SampGetNT4UpgradeInProgress
0x1803158ab  test    al, al
0x1803158ad  jnz     short loc_1803158BC
0x1803158af  mov     edx, ebx
0x1803158b1  mov     [rsp+2688h+var_2648], ebx
0x1803158b5  mov     ecx, ebx
0x1803158b7  jmp     loc_180315A08
0x1803158bc  lea     rdi, [rsp+2688h+SourceString]
0x1803158c4  mov     [rsp+2688h+var_2628], rdi
0x1803158c9  mov     [rsp+2688h+DataLength], 2Ah ; '*'
0x1803158d1  lea     r9, [rsp+2688h+DataLength]
0x1803158d6  lea     r8, [rsp+2688h+SourceString]
0x1803158de  mov     edx, 2
0x1803158e3  mov     rcx, [rsp+2688h+var_2528]; SourceString
0x1803158eb  call    GetRdnForSamObject
0x1803158f0  mov     edx, eax
0x1803158f2  mov     [rsp+2688h+var_2648], eax
0x1803158f6  cmp     eax, 0C0000023h
0x1803158fb  jnz     short loc_18031594E
0x1803158fd  mov     r8d, [rsp+2688h+DataLength]; Size
0x180315902  mov     rcx, gs:60h
0x18031590b  xor     edx, edx; Flags
0x18031590d  mov     rcx, [rcx+30h]; HeapHandle
0x180315911  call    cs:__imp_RtlAllocateHeap
0x180315917  mov     rdi, rax
0x18031591a  mov     [rsp+2688h+var_2628], rax
0x18031591f  test    rax, rax
0x180315922  jnz     short loc_18031592E
0x180315924  mov     eax, 0C000009Ah
0x180315929  jmp     loc_180315A00
0x18031592e  lea     r9, [rsp+2688h+DataLength]
0x180315933  mov     r8, rax
0x180315936  mov     edx, 2
0x18031593b  mov     rcx, [rsp+2688h+var_2528]; SourceString
0x180315943  call    GetRdnForSamObject
0x180315948  mov     edx, eax
0x18031594a  mov     [rsp+2688h+var_2648], eax
0x18031594e  mov     ecx, eax
0x180315950  test    eax, eax
0x180315952  js      loc_180315A08
0x180315958  xorps   xmm0, xmm0
0x18031595b  movups  xmmword ptr [rsp+2688h+DestinationString.Length], xmm0
0x180315963  mov     rdx, rdi; SourceString
0x180315966  lea     rcx, [rsp+2688h+DestinationString]; DestinationString
0x18031596e  call    cs:__imp_RtlInitUnicodeString
0x180315974  mov     al, [r13+74h]
0x180315978  and     al, sil
0x18031597b  lea     rcx, [rsp+2688h+Unused]
0x180315980  mov     [rsp+2688h+var_2650], rcx
0x180315985  mov     [rsp+2688h+var_2658], al
0x180315989  mov     [rsp+2688h+var_2660], rbx
0x18031598e  mov     [rsp+2688h+ResultLength], rbx
0x180315993  lea     r9, [rsp+2688h+DestinationString]
0x18031599b  mov     r8d, 2
0x1803159a1  mov     rdx, [r13+90h]
0x1803159a8  mov     rcx, [r13+50h]
0x1803159ac  call    SampDsCreateAccountObjectDsName
0x1803159b1  mov     edx, eax
0x1803159b3  mov     [rsp+2688h+var_2648], eax
0x1803159b7  test    eax, eax
0x1803159b9  js      short loc_180315A06
0x1803159bb  lea     rcx, [rsp+2688h+var_2538]; this
0x1803159c3  call    ?Convert@CConversionObject@@QEAAJXZ; CConversionObject::Convert(void)
0x1803159c8  mov     edx, eax
0x1803159ca  mov     [rsp+2688h+var_2648], eax
0x1803159ce  test    eax, eax
0x1803159d0  js      short loc_180315A06
0x1803159d2  mov     rdx, qword ptr [rsp+2688h+Unused]; struct _DSNAME *
0x1803159d7  lea     rcx, [rsp+2688h+var_2570]; this
0x1803159df  call    ?Flush@CDsSamObject@@UEAAJPEAU_DSNAME@@@Z; CDsSamObject::Flush(_DSNAME *)
0x1803159e4  mov     edx, eax
0x1803159e6  mov     [rsp+2688h+var_2648], eax
0x1803159ea  test    eax, eax
0x1803159ec  js      short loc_180315A06
0x1803159ee  mov     qword ptr [rsp+2688h+Unused], rbx
0x1803159f3  lea     rcx, [rsp+2688h+var_25B8]; this
0x1803159fb  call    ?ConvertMembers@CGroupObject@@QEAAJXZ; CGroupObject::ConvertMembers(void)
0x180315a00  mov     [rsp+2688h+var_2648], eax
0x180315a04  mov     edx, eax
0x180315a06  mov     ecx, eax; int
0x180315a08  cmp     ecx, 0C0000065h
0x180315a0e  jnz     short loc_180315A42
0x180315a10  xorps   xmm0, xmm0
0x180315a13  movups  xmmword ptr [rsp+2688h+var_25F0.Length], xmm0
0x180315a1b  mov     rdx, [rsp+2688h+var_2528]; SourceString
0x180315a23  lea     rcx, [rsp+2688h+var_25F0]; DestinationString
0x180315a2b  call    cs:__imp_RtlInitUnicodeString
0x180315a31  lea     r8, [rsp+2688h+var_25F0]
0x180315a39  lea     rcx, SAMMSG_DUPLICATE_ACCOUNT
0x180315a40  jmp     short loc_180315A88
0x180315a42  test    ecx, ecx
0x180315a44  jns     loc_180315AD2
0x180315a4a  call    ?SampIsNtStatusResourceError@@YAEJ@Z; SampIsNtStatusResourceError(long)
0x180315a4f  test    al, al
0x180315a51  jnz     short loc_180315ACE
0x180315a53  test    sil, sil
0x180315a56  jz      short loc_180315AA7
0x180315a58  xorps   xmm0, xmm0
0x180315a5b  movups  xmmword ptr [rsp+2688h+var_25E0.Length], xmm0
0x180315a63  mov     rdx, [rsp+2688h+var_2528]; SourceString
  ... truncated ...
```
