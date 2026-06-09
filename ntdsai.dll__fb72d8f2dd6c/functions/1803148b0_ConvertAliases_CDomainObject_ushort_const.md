# ConvertAliases(CDomainObject &,ushort const *)

- ea: `0x1803148b0`
- end: `0x180314f9a`
- name: `?ConvertAliases@@YAJAEAVCDomainObject@@PEBG@Z`
- size: `1770`
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
- `0x180312f04`
- `0x180313930`
- `0x180313e90`
- `0x180314350`
- `0x180314488`
- `0x180314648`
- `0x1803148b0`
- `0x180316480`
- `0x180316564`
- `0x180316648`
- `0x18031666c`
- `0x1803dedec`
- `0x180453340`
- `0x1804533ac`

## import_xrefs

- `ntdll!RtlpNtQueryValueKey` at `0x180314ad0`
- `ntdll!RtlpNtQueryValueKey` at `0x180314ad0`
- `ntdll!NtEnumerateKey` at `0x1803149e8`
- `ntdll!NtEnumerateKey` at `0x180314b86`
- `ntdll!NtEnumerateKey` at `0x1803149e8`
- `ntdll!NtEnumerateKey` at `0x180314b86`
- `ntdll!RtlAllocateHeap` at `0x180314d2f`
- `ntdll!RtlAllocateHeap` at `0x180314d2f`
- `ntdll!RtlFreeHeap` at `0x180314f17`
- `ntdll!RtlFreeHeap` at `0x180471afc`
- `ntdll!RtlFreeHeap` at `0x180314f17`
- `ntdll!RtlFreeHeap` at `0x180471afc`
- `ntdll!NtQueryKey` at `0x1803149a0`
- `ntdll!NtQueryKey` at `0x180314a93`
- `ntdll!NtQueryKey` at `0x1803149a0`
- `ntdll!NtQueryKey` at `0x180314a93`
- `ntdll!RtlInitUnicodeString` at `0x180314d8c`
- `ntdll!RtlInitUnicodeString` at `0x180314e49`
- `ntdll!RtlInitUnicodeString` at `0x180314e91`
- `ntdll!RtlInitUnicodeString` at `0x180471a3c`
- `ntdll!RtlInitUnicodeString` at `0x180471a7c`
- `ntdll!RtlInitUnicodeString` at `0x180314d8c`
- `ntdll!RtlInitUnicodeString` at `0x180314e49`
- `ntdll!RtlInitUnicodeString` at `0x180314e91`
- `ntdll!RtlInitUnicodeString` at `0x180471a3c`
- `ntdll!RtlInitUnicodeString` at `0x180471a7c`
- `SAMSRV!SampWriteEventLog` at `0x180314ebd`
- `SAMSRV!SampWriteEventLog` at `0x180314ede`
- `SAMSRV!SampWriteEventLog` at `0x180471aa6`
- `SAMSRV!SampWriteEventLog` at `0x180471ac6`
- `SAMSRV!SampWriteEventLog` at `0x180314ebd`
- `SAMSRV!SampWriteEventLog` at `0x180314ede`
- `SAMSRV!SampWriteEventLog` at `0x180471aa6`
- `SAMSRV!SampWriteEventLog` at `0x180471ac6`

## pseudocode

```c
__int64 __fastcall ConvertAliases(HANDLE *a1, const unsigned __int16 *a2)
{
  ULONG v4; // r12d
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
  int v16; // ecx
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
  int v36; // [rsp+C0h] [rbp-25F0h]
  struct _UNICODE_STRING v37; // [rsp+C8h] [rbp-25E8h] BYREF
  struct _UNICODE_STRING v38; // [rsp+D8h] [rbp-25D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-25C8h] BYREF
  _BYTE v40[8]; // [rsp+F8h] [rbp-25B8h] BYREF
  _BYTE v41[64]; // [rsp+100h] [rbp-25B0h] BYREF
  _BYTE v42[56]; // [rsp+140h] [rbp-2570h] BYREF
  _BYTE v43[16]; // [rsp+178h] [rbp-2538h] BYREF
  PCWSTR v44; // [rsp+188h] [rbp-2528h]
  __int64 v45; // [rsp+190h] [rbp-2520h]
  WCHAR SourceString[24]; // [rsp+1A8h] [rbp-2508h] BYREF
  _BYTE KeyInformation[20]; // [rsp+1D8h] [rbp-24D8h] BYREF
  ULONG v48; // [rsp+1ECh] [rbp-24C4h]
  _BYTE v49[16]; // [rsp+608h] [rbp-20A8h] BYREF
  wchar_t String1[520]; // [rsp+618h] [rbp-2098h] BYREF
  _BYTE v51[20]; // [rsp+A28h] [rbp-1C88h] BYREF
  ULONG v52; // [rsp+A3Ch] [rbp-1C74h]
  _BYTE v53[12]; // [rsp+E58h] [rbp-1858h] BYREF
  unsigned __int16 v54[4]; // [rsp+E64h] [rbp-184Ch] BYREF
  unsigned __int16 v55[1024]; // [rsp+1678h] [rbp-1038h] BYREF
  unsigned __int16 v56[1024]; // [rsp+1E78h] [rbp-838h] BYREF

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
  memset_0(v49, 0, 0x418u);
  memset_0(v51, 0, 0x430u);
  memset_0(v56, 0, sizeof(v56));
  v5 = NtQueryKey(a1[1], KeyFullInformation, KeyInformation, 0x430u, &v32);
  v22 = v5;
  if ( v5 >= 0 )
  {
    v6 = 0;
    if ( !v48 )
      goto LABEL_11;
    while ( 1 )
    {
      v5 = NtEnumerateKey(a1[1], v6, KeyBasicInformation, v49, 0x418u, &v33);
      v22 = v5;
      if ( v5 < 0 )
        goto LABEL_61;
      if ( !wcsncmp_0(String1, L"Aliases", 7u) )
        break;
      if ( ++v6 >= v48 )
        goto LABEL_11;
    }
    v5 = RtlStringCbPrintfW(v56, 0x800u, L"%ws\\Aliases", a2);
    v22 = v5;
    if ( v5 >= 0 )
    {
      v5 = CRegistryObject::Open((CRegistryObject *)&KeyHandle, v56);
      v22 = v5;
      if ( v5 >= 0 )
      {
        v5 = NtQueryKey(KeyHandle, KeyFullInformation, v51, 0x430u, &v26);
        v22 = v5;
        if ( v5 >= 0 )
        {
          DataLength = 0;
          *(_QWORD *)Unused = 0;
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
            v9 = 1;
            v23 = 1;
            Heap = 0;
            v27 = 0;
            while ( 1 )
            {
              if ( v4 >= v52 )
              {
LABEL_59:
                if ( v5 >= 0 )
                  *((_DWORD *)a1 + 42) = v8;
                goto LABEL_61;
              }
              v35 = 0;
              *(_QWORD *)Unused = 0;
              memset_0(v53, 0, 0x818u);
              memset_0(v55, 0, sizeof(v55));
              v5 = NtEnumerateKey(KeyHandle, v4, KeyBasicInformation, v53, 0x818u, &v35);
              v22 = v5;
              if ( v5 < 0 )
                goto LABEL_61;
              if ( wcsncmp_0(&v54[2], L"Names", 5u) && wcsncmp_0(&v54[2], L"Members", 7u) )
                break;
LABEL_63:
              ++v4;
            }
            CAliasObject::CAliasObject((CAliasObject *)v40, v11, (struct CDomainObject *)a1);
            v12 = RtlStringCbPrintfW(v55, 0x800u, L"%ws\\Aliases\\", a2);
            v13 = v12;
            v22 = v12;
            v14 = v12;
            if ( v12 >= 0 )
            {
              v13 = RtlStringCbCatNW(v55, (unsigned int)v12, &v54[2], *(unsigned int *)v54);
              v22 = v13;
              v14 = v13;
            }
            if ( v14 < 0 )
            {
LABEL_43:
              if ( v14 == -1073741484 )
              {
                v37 = 0;
                RtlInitUnicodeString(&v37, v44);
                v18 = &v37;
                v19 = SAMMSG_DUPLICATE_ACCOUNT;
                goto LABEL_49;
              }
              if ( v14 >= 0 )
                goto LABEL_53;
              if ( !SampIsNtStatusResourceError(v14) )
              {
                if ( !v9 )
                {
                  SampWriteEventLog(SAMMSG_UNKNOWN_ALIAS_NOT_UPGRADED, L"b", 4, &v22, ResultLength);
                  goto LABEL_51;
                }
                v38 = 0;
                RtlInitUnicodeString(&v38, v44);
                v18 = &v38;
                v19 = SAMMSG_ALIAS_NOT_UPGRADED;
LABEL_49:
                SampWriteEventLog(v19, L"ub", v18, 4, &v22);
LABEL_51:
                v13 = 0;
                v22 = 0;
                goto LABEL_54;
              }
              if ( v20 >= 0 )
LABEL_53:
                ++v8;
LABEL_54:
              if ( Heap && Heap != SourceString )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
                Heap = 0;
                v27 = 0;
                v13 = v22;
              }
              if ( v13 < 0 )
              {
                CAliasObject::~CAliasObject((CAliasObject *)v40);
                v5 = v22;
                goto LABEL_59;
              }
              v9 = 0;
              v23 = 0;
              CAliasObject::~CAliasObject((CAliasObject *)v40);
              v5 = v22;
              goto LABEL_63;
            }
            AccountObjectDsName = CRegistryObject::Open((CRegistryObject *)v41, v55);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0
              || (AccountObjectDsName = CAliasObject::Fill((CAliasObject *)v40),
                  v13 = AccountObjectDsName,
                  v22 = AccountObjectDsName,
                  AccountObjectDsName < 0) )
            {
LABEL_42:
              v14 = AccountObjectDsName;
              goto LABEL_43;
            }
            v9 = 1;
            v23 = 1;
            v16 = 0;
            v36 = 0;
            if ( (*((_BYTE *)a1 + 116) & 1) != 0
              && ((_DWORD)v45 == 547
               || (_DWORD)v45 == 581
               || (_DWORD)v45 == 583
               || (_DWORD)v45 == 584
               || (_DWORD)v45 == 586) )
            {
              v16 = 1;
              v36 = 1;
            }
            if ( v16 )
            {
              v13 = 0;
              v22 = 0;
              v14 = 0;
              goto LABEL_43;
            }
            Heap = SourceString;
            v27 = SourceString;
            DataLength = 42;
            RdnForSamObject = GetRdnForSamObject(v44);
            v13 = RdnForSamObject;
            v22 = RdnForSamObject;
            if ( RdnForSamObject == -1073741789 )
            {
              Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataLength);
              v27 = Heap;
              if ( !Heap )
              {
                AccountObjectDsName = -1073741670;
LABEL_41:
                v22 = AccountObjectDsName;
                v13 = AccountObjectDsName;
                goto LABEL_42;
              }
              RdnForSamObject = GetRdnForSamObject(v44);
              v13 = RdnForSamObject;
              v22 = RdnForSamObject;
            }
            v14 = RdnForSamObject;
            if ( RdnForSamObject < 0 )
              goto LABEL_43;
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, Heap);
            AccountObjectDsName = SampDsCreateAccountObjectDsName(
                                    (unsigned int)a1[10],
                                    (unsigned int)a1[18],
                                    3,
                                    (unsigned int)&DestinationString,
                                    0,
                                    0,
                                    *((_BYTE *)a1 + 116) & 1,
                                    (__int64)Unused);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_42;
            AccountObjectDsName = CConversionObject::Convert((CConversionObject *)v43);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_42;
            AccountObjectDsName = CDsSamObject::Flush((CDsSamObject *)v42, *(struct _DSNAME **)Unused);
            v13 = AccountObjectDsName;
            v22 = AccountObjectDsName;
            if ( AccountObjectDsName < 0 )
              goto LABEL_42;
            *(_QWORD *)Unused = 0;
            AccountObjectDsName = CAliasObject::ConvertMembers((CAliasObject *)v40);
            goto LABEL_41;
          }
        }
      }
    }
  }
LABEL_61:
  CRegistryObject::Close(&KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1803148b0  mov     [rsp+arg_10], rbx
0x1803148b5  mov     [rsp+arg_18], rsi
0x1803148ba  push    rdi
0x1803148bb  push    r12
0x1803148bd  push    r13
0x1803148bf  push    r14
0x1803148c1  push    r15
0x1803148c3  mov     eax, 2660h
0x1803148c8  call    _alloca_probe
0x1803148cd  sub     rsp, rax
0x1803148d0  mov     rax, cs:__security_cookie
0x1803148d7  xor     rax, rsp
0x1803148da  mov     [rsp+2688h+var_38], rax
0x1803148e2  mov     r13, rdx
0x1803148e5  mov     r15, rcx
0x1803148e8  xor     r12d, r12d
0x1803148eb  mov     [rsp+2688h+var_2648], r12d
0x1803148f0  mov     [rsp+2688h+var_2600], r12d
0x1803148f8  mov     [rsp+2688h+var_25FC], r12d
0x180314900  mov     [rsp+2688h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x180314909  mov     [rsp+2688h+var_2618], r12d
0x18031490e  mov     [rsp+2688h+var_2610], r12
0x180314913  mov     [rsp+2688h+var_2608], r12d
0x18031491b  mov     [rsp+2688h+var_2630], r12d
0x180314920  mov     [rsp+2688h+Type], 0FFFFFFFFh
0x18031492b  mov     esi, 430h
0x180314930  mov     r8d, esi; Size
0x180314933  xor     edx, edx; Val
0x180314935  lea     rcx, [rsp+2688h+KeyInformation]; void *
0x18031493d  call    memset_0
0x180314942  lea     r14d, [rsi-18h]
0x180314946  mov     r8d, r14d; Size
0x180314949  xor     edx, edx; Val
0x18031494b  lea     rcx, [rsp+2688h+var_20A8]; void *
0x180314953  call    memset_0
0x180314958  mov     r8d, esi; Size
0x18031495b  xor     edx, edx; Val
0x18031495d  lea     rcx, [rsp+2688h+var_1C88]; void *
0x180314965  call    memset_0
0x18031496a  xor     edx, edx; Val
0x18031496c  mov     r8d, 800h; Size
0x180314972  lea     rcx, [rsp+2688h+var_838]; void *
0x18031497a  call    memset_0
0x18031497f  lea     rax, [rsp+2688h+var_2600]
0x180314987  mov     [rsp+2688h+ResultLength], rax; ResultLength
0x18031498c  mov     r9d, esi; Length
0x18031498f  lea     r8, [rsp+2688h+KeyInformation]; KeyInformation
0x180314997  lea     edx, [r12+2]; KeyInformationClass
0x18031499c  mov     rcx, [r15+8]; KeyHandle
0x1803149a0  call    cs:__imp_NtQueryKey
0x1803149a6  mov     ebx, eax
0x1803149a8  mov     [rsp+2688h+var_2648], eax
0x1803149ac  test    eax, eax
0x1803149ae  js      loc_180314F49
0x1803149b4  mov     edi, r12d
0x1803149b7  cmp     [rsp+2688h+var_24C4], r12d
0x1803149bf  jbe     loc_180314AE4
0x1803149c5  lea     rax, [rsp+2688h+var_25FC]
0x1803149cd  mov     [rsp+2688h+var_2660], rax; ResultLength
0x1803149d2  mov     dword ptr [rsp+2688h+ResultLength], r14d; Length
0x1803149d7  lea     r9, [rsp+2688h+var_20A8]; KeyInformation
0x1803149df  xor     r8d, r8d; KeyInformationClass
0x1803149e2  mov     edx, edi; Index
0x1803149e4  mov     rcx, [r15+8]; KeyHandle
0x1803149e8  call    cs:__imp_NtEnumerateKey
0x1803149ee  mov     ebx, eax
0x1803149f0  mov     [rsp+2688h+var_2648], eax
0x1803149f4  test    eax, eax
0x1803149f6  js      loc_180314F49
0x1803149fc  mov     r8d, 7; MaxCount
0x180314a02  lea     rdx, aAliases; "Aliases"
0x180314a09  lea     rcx, [rsp+2688h+String1]; String1
0x180314a11  call    wcsncmp_0
0x180314a16  test    eax, eax
0x180314a18  jz      short loc_180314A2A
0x180314a1a  inc     edi
0x180314a1c  cmp     edi, [rsp+2688h+var_24C4]
0x180314a23  jb      short loc_1803149C5
0x180314a25  jmp     loc_180314AE4
0x180314a2a  mov     r9, r13
0x180314a2d  lea     r8, aWsAliases; "%ws\\Aliases"
0x180314a34  mov     edx, 800h; unsigned __int64
0x180314a39  lea     rcx, [rsp+2688h+var_838]; unsigned __int16 *
0x180314a41  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180314a46  mov     ebx, eax
0x180314a48  mov     [rsp+2688h+var_2648], eax
0x180314a4c  lea     rcx, [rsp+2688h+KeyHandle]; this
0x180314a51  test    eax, eax
0x180314a53  js      loc_180314F4E
0x180314a59  lea     rdx, [rsp+2688h+var_838]; unsigned __int16 *
0x180314a61  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180314a66  mov     ebx, eax
0x180314a68  mov     [rsp+2688h+var_2648], eax
0x180314a6c  test    eax, eax
0x180314a6e  js      loc_180314F49
0x180314a74  lea     rax, [rsp+2688h+var_2630]
0x180314a79  mov     [rsp+2688h+ResultLength], rax; ResultLength
0x180314a7e  mov     r9d, esi; Length
0x180314a81  lea     r8, [rsp+2688h+var_1C88]; KeyInformation
0x180314a89  mov     edx, 2; KeyInformationClass
0x180314a8e  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x180314a93  call    cs:__imp_NtQueryKey
0x180314a99  mov     ebx, eax
0x180314a9b  mov     [rsp+2688h+var_2648], eax
0x180314a9f  test    eax, eax
0x180314aa1  js      loc_180314F49
0x180314aa7  mov     [rsp+2688h+DataLength], r12d
0x180314aac  mov     qword ptr [rsp+2688h+Unused], r12
0x180314ab1  lea     rax, [rsp+2688h+Unused]
0x180314ab6  mov     [rsp+2688h+ResultLength], rax; Unused
0x180314abb  lea     r9, [rsp+2688h+DataLength]; DataLength
0x180314ac0  xor     r8d, r8d; Data
0x180314ac3  lea     rdx, [rsp+2688h+Type]; Type
0x180314acb  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x180314ad0  call    cs:__imp_RtlpNtQueryValueKey
0x180314ad6  mov     ebx, eax
0x180314ad8  mov     [rsp+2688h+var_2648], eax
0x180314adc  test    eax, eax
0x180314ade  js      loc_180314F49
0x180314ae4  cmp     [rsp+2688h+var_2630], r12d
0x180314ae9  jnz     short loc_180314AFF
0x180314aeb  lea     rcx, [rsp+2688h+KeyHandle]; this
0x180314af0  call    ?Close@CRegistryObject@@QEAAJXZ; CRegistryObject::Close(void)
0x180314af5  mov     eax, 0C0000158h
0x180314afa  jmp     loc_180314F55
0x180314aff  mov     r14d, r12d
0x180314b02  mov     sil, 1
0x180314b05  mov     [rsp+2688h+var_2644], sil
0x180314b0a  mov     rdi, r12
0x180314b0d  mov     [rsp+2688h+var_2628], r12
0x180314b12  cmp     r12d, [rsp+2688h+var_1C74]
0x180314b1a  jnb     loc_180314F3E
0x180314b20  mov     [rsp+2688h+var_25F4], 0
0x180314b2b  mov     qword ptr [rsp+2688h+Unused], 0
0x180314b34  xor     edx, edx; Val
0x180314b36  mov     r8d, 818h; Size
0x180314b3c  lea     rcx, [rsp+2688h+var_1858]; void *
0x180314b44  call    memset_0
0x180314b49  xor     edx, edx; Val
0x180314b4b  mov     r8d, 800h; Size
0x180314b51  lea     rcx, [rsp+2688h+var_1038]; void *
0x180314b59  call    memset_0
0x180314b5e  lea     rax, [rsp+2688h+var_25F4]
0x180314b66  mov     [rsp+2688h+var_2660], rax; ResultLength
0x180314b6b  mov     dword ptr [rsp+2688h+ResultLength], 818h; Length
0x180314b73  lea     r9, [rsp+2688h+var_1858]; KeyInformation
0x180314b7b  xor     r8d, r8d; KeyInformationClass
0x180314b7e  mov     edx, r12d; Index
0x180314b81  mov     rcx, [rsp+2688h+KeyHandle]; KeyHandle
0x180314b86  call    cs:__imp_NtEnumerateKey
0x180314b8c  mov     ebx, eax
0x180314b8e  mov     [rsp+2688h+var_2648], eax
0x180314b92  test    eax, eax
0x180314b94  js      loc_180314F49
0x180314b9a  mov     r8d, 5; MaxCount
0x180314ba0  lea     rdx, aNames; "Names"
0x180314ba7  lea     rcx, [rsp+2688h+var_184C+4]; String1
0x180314baf  call    wcsncmp_0
0x180314bb4  test    eax, eax
0x180314bb6  jz      loc_180314F92
0x180314bbc  mov     r8d, 7; MaxCount
0x180314bc2  lea     rdx, aMembers; "Members"
0x180314bc9  lea     rcx, [rsp+2688h+var_184C+4]; String1
0x180314bd1  call    wcsncmp_0
0x180314bd6  test    eax, eax
0x180314bd8  jz      loc_180314F92
0x180314bde  mov     r8, r15; struct CDomainObject *
0x180314be1  lea     rcx, [rsp+2688h+var_25B8]; this
0x180314be9  call    ??0CAliasObject@@QEAA@AEAVCDomainObject@@0@Z; CAliasObject::CAliasObject(CDomainObject &,CDomainObject &)
0x180314bee  mov     r9, r13
0x180314bf1  lea     r8, aWsAliases_0; "%ws\\Aliases\\"
0x180314bf8  mov     edx, 800h; unsigned __int64
0x180314bfd  lea     rcx, [rsp+2688h+var_1038]; unsigned __int16 *
0x180314c05  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180314c0a  mov     edx, eax; unsigned __int64
0x180314c0c  mov     [rsp+2688h+var_2648], eax
0x180314c10  mov     ecx, eax
0x180314c12  xor     ebx, ebx
0x180314c14  test    eax, eax
0x180314c16  js      short loc_180314C3D
0x180314c18  mov     r9d, dword ptr [rsp+2688h+var_184C]; unsigned __int64
0x180314c20  lea     r8, [rsp+2688h+var_184C+4]; unsigned __int16 *
0x180314c28  lea     rcx, [rsp+2688h+var_1038]; unsigned __int16 *
0x180314c30  call    ?RtlStringCbCatNW@@YAJPEAG_KPEBG1@Z; RtlStringCbCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180314c35  mov     edx, eax
0x180314c37  mov     [rsp+2688h+var_2648], eax
0x180314c3b  mov     ecx, eax
0x180314c3d  test    ecx, ecx
0x180314c3f  js      loc_180314E26
0x180314c45  lea     rdx, [rsp+2688h+var_1038]; unsigned __int16 *
0x180314c4d  lea     rcx, [rsp+2688h+var_25B0]; this
0x180314c55  call    ?Open@CRegistryObject@@QEAAJPEBG@Z; CRegistryObject::Open(ushort const *)
0x180314c5a  mov     edx, eax
0x180314c5c  mov     [rsp+2688h+var_2648], eax
0x180314c60  test    eax, eax
0x180314c62  js      loc_180314E24
0x180314c68  lea     rcx, [rsp+2688h+var_25B8]; this
0x180314c70  call    ?Fill@CAliasObject@@UEAAJXZ; CAliasObject::Fill(void)
0x180314c75  mov     edx, eax
0x180314c77  mov     [rsp+2688h+var_2648], eax
0x180314c7b  test    eax, eax
0x180314c7d  js      loc_180314E24
0x180314c83  mov     sil, 1
0x180314c86  mov     [rsp+2688h+var_2644], sil
0x180314c8b  mov     ecx, ebx
0x180314c8d  mov     [rsp+2688h+var_25F0], ebx
0x180314c94  test    [r15+74h], sil
0x180314c98  jz      short loc_180314CC9
0x180314c9a  mov     rax, [rsp+2688h+var_2520]
0x180314ca2  sub     eax, 223h
0x180314ca7  jz      short loc_180314CBD
0x180314ca9  sub     eax, 22h ; '"'
0x180314cac  jz      short loc_180314CBD
0x180314cae  sub     eax, 2
0x180314cb1  jz      short loc_180314CBD
0x180314cb3  sub     eax, 1
0x180314cb6  jz      short loc_180314CBD
0x180314cb8  sub     eax, 2
0x180314cbb  jnz     short loc_180314CC9
0x180314cbd  mov     ecx, 1
0x180314cc2  mov     [rsp+2688h+var_25F0], ecx
0x180314cc9  test    ecx, ecx
0x180314ccb  jz      short loc_180314CDA
0x180314ccd  mov     edx, ebx
0x180314ccf  mov     [rsp+2688h+var_2648], ebx
0x180314cd3  mov     ecx, ebx
0x180314cd5  jmp     loc_180314E26
0x180314cda  lea     rdi, [rsp+2688h+SourceString]
0x180314ce2  mov     [rsp+2688h+var_2628], rdi
0x180314ce7  mov     [rsp+2688h+DataLength], 2Ah ; '*'
0x180314cef  lea     r9, [rsp+2688h+DataLength]
0x180314cf4  lea     r8, [rsp+2688h+SourceString]
0x180314cfc  mov     edx, 3
0x180314d01  mov     rcx, [rsp+2688h+var_2528]; SourceString
0x180314d09  call    GetRdnForSamObject
0x180314d0e  mov     edx, eax
0x180314d10  mov     [rsp+2688h+var_2648], eax
0x180314d14  cmp     eax, 0C0000023h
0x180314d19  jnz     short loc_180314D6C
0x180314d1b  mov     r8d, [rsp+2688h+DataLength]; Size
0x180314d20  mov     rcx, gs:60h
0x180314d29  xor     edx, edx; Flags
0x180314d2b  mov     rcx, [rcx+30h]; HeapHandle
0x180314d2f  call    cs:__imp_RtlAllocateHeap
0x180314d35  mov     rdi, rax
0x180314d38  mov     [rsp+2688h+var_2628], rax
0x180314d3d  test    rax, rax
0x180314d40  jnz     short loc_180314D4C
0x180314d42  mov     eax, 0C000009Ah
0x180314d47  jmp     loc_180314E1E
0x180314d4c  lea     r9, [rsp+2688h+DataLength]
0x180314d51  mov     r8, rax
0x180314d54  mov     edx, 4
0x180314d59  mov     rcx, [rsp+2688h+var_2528]; SourceString
0x180314d61  call    GetRdnForSamObject
0x180314d66  mov     edx, eax
0x180314d68  mov     [rsp+2688h+var_2648], eax
0x180314d6c  mov     ecx, eax
0x180314d6e  test    eax, eax
0x180314d70  js      loc_180314E26
0x180314d76  xorps   xmm0, xmm0
0x180314d79  movups  xmmword ptr [rsp+2688h+DestinationString.Length], xmm0
0x180314d81  mov     rdx, rdi; SourceString
0x180314d84  lea     rcx, [rsp+2688h+DestinationString]; DestinationString
0x180314d8c  call    cs:__imp_RtlInitUnicodeString
0x180314d92  mov     al, [r15+74h]
0x180314d96  and     al, sil
0x180314d99  lea     rcx, [rsp+2688h+Unused]
0x180314d9e  mov     [rsp+2688h+var_2650], rcx
0x180314da3  mov     [rsp+2688h+var_2658], al
0x180314da7  mov     [rsp+2688h+var_2660], rbx
0x180314dac  mov     [rsp+2688h+ResultLength], rbx
0x180314db1  lea     r9, [rsp+2688h+DestinationString]
0x180314db9  mov     r8d, 3
0x180314dbf  mov     rdx, [r15+90h]
0x180314dc6  mov     rcx, [r15+50h]
0x180314dca  call    SampDsCreateAccountObjectDsName
0x180314dcf  mov     edx, eax
0x180314dd1  mov     [rsp+2688h+var_2648], eax
0x180314dd5  test    eax, eax
0x180314dd7  js      short loc_180314E24
0x180314dd9  lea     rcx, [rsp+2688h+var_2538]; this
0x180314de1  call    ?Convert@CConversionObject@@QEAAJXZ; CConversionObject::Convert(void)
0x180314de6  mov     edx, eax
0x180314de8  mov     [rsp+2688h+var_2648], eax
0x180314dec  test    eax, eax
0x180314dee  js      short loc_180314E24
0x180314df0  mov     rdx, qword ptr [rsp+2688h+Unused]; struct _DSNAME *
0x180314df5  lea     rcx, [rsp+2688h+var_2570]; this
0x180314dfd  call    ?Flush@CDsSamObject@@UEAAJPEAU_DSNAME@@@Z; CDsSamObject::Flush(_DSNAME *)
0x180314e02  mov     edx, eax
0x180314e04  mov     [rsp+2688h+var_2648], eax
0x180314e08  test    eax, eax
0x180314e0a  js      short loc_180314E24
0x180314e0c  mov     qword ptr [rsp+2688h+Unused], rbx
0x180314e11  lea     rcx, [rsp+2688h+var_25B8]; this
0x180314e19  call    ?ConvertMembers@CAliasObject@@QEAAJXZ; CAliasObject::ConvertMembers(void)
0x180314e1e  mov     [rsp+2688h+var_2648], eax
0x180314e22  mov     edx, eax
0x180314e24  mov     ecx, eax; int
  ... truncated ...
```
