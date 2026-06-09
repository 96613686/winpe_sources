# CiFindFileOrHeaderHashInCatalogs

- ea: `0x18008e728`
- end: `0x18008ed9b`
- name: `CiFindFileOrHeaderHashInCatalogs`
- size: `1651`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, int, int, int, int, int, int, int, PCUNICODE_STRING, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005e420`
- `0x180061568`
- `0x18008e168`
- `0x18008e280`
- `0x18008e3e0`

## callees

- `0x18000c53c`
- `0x18002c0d0`
- `0x180061ae8`
- `0x18008b730`
- `0x18008c1a0`
- `0x18008d0c8`
- `0x18008e728`
- `0x18008eda4`
- `0x180094c1c`
- `0x1800e2e18`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18008e85d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008e85d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18008ecda`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18008ecda`
- `ntoskrnl!KeStackAttachProcess` at `0x18008e8ba`
- `ntoskrnl!KeStackAttachProcess` at `0x18008e8ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008ecae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008ecae`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18008ed55`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18008ed55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008ebf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008ebf7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18008e89f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18008e89f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18008ed65`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18008ed65`
- `ntoskrnl!ZwQueryInformationThread` at `0x18008e8e7`
- `ntoskrnl!ZwQueryInformationThread` at `0x18008e8e7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008e87c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008e9b9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008e87c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18008e9b9`
- `ntoskrnl!ZwSetInformationThread` at `0x18008e910`
- `ntoskrnl!ZwSetInformationThread` at `0x18008ed3f`
- `ntoskrnl!ZwSetInformationThread` at `0x18008e910`
- `ntoskrnl!ZwSetInformationThread` at `0x18008ed3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008e99e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008ebeb`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008e99e`
- `ntoskrnl!ExReleaseResourceLite` at `0x18008ebeb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18008e890`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18008e890`

## pseudocode

```c
__int64 __fastcall CiFindFileOrHeaderHashInCatalogs(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        PCUNICODE_STRING SourceString,
        const UNICODE_STRING *a14,
        __int64 a15,
        int a16,
        __int64 a17,
        struct _UNICODE_STRING *a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  __int64 CurrentSiloState; // rdi
  __int64 result; // rax
  __int64 v27; // r15
  int v28; // r14d
  __int64 CurrentServerSilo; // rax
  int v30; // edx
  int v31; // r8d
  NTSTATUS v32; // eax
  int v33; // ecx
  char i; // bl
  int v35; // ebx
  char v36; // r12
  __int64 v37; // rax
  int FileOrHeaderHashInLoadedCatalogs; // ebx
  int v39; // r8d
  __int64 v40; // rax
  bool v41; // cf
  int v42; // r9d
  __int64 v43; // rdx
  int v44; // ecx
  int v45; // eax
  __int64 v46; // rax
  _QWORD *v47; // rdi
  char String1; // [rsp+30h] [rbp-D0h]
  char v49; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+81h] [rbp-7Fh]
  int v51; // [rsp+84h] [rbp-7Ch] BYREF
  int v52; // [rsp+88h] [rbp-78h]
  int ThreadInformation; // [rsp+8Ch] [rbp-74h] BYREF
  int v54; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+94h] [rbp-6Ch]
  int v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  PCUNICODE_STRING v58; // [rsp+A8h] [rbp-58h]
  PERESOURCE Resource; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  PUNICODE_STRING UnicodeString; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+D8h] [rbp-28h]
  __int64 v65; // [rsp+E0h] [rbp-20h]
  int v66[2]; // [rsp+E8h] [rbp-18h]
  __int64 v67; // [rsp+F0h] [rbp-10h]
  int v68[2]; // [rsp+F8h] [rbp-8h]
  struct _KAPC_STATE ApcState; // [rsp+100h] [rbp+0h] BYREF

  v63 = a19;
  v58 = a14;
  v60 = a15;
  v61 = a17;
  UnicodeString = a18;
  v64 = a20;
  *(_QWORD *)v68 = a2;
  v65 = a21;
  v55 = a4;
  v56 = a3;
  *(_QWORD *)v66 = a5;
  v57 = (__int64)SourceString;
  v51 = a9;
  v54 = 0;
  ThreadInformation = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v49 = 0;
  CurrentSiloState = CiGetCurrentSiloState();
  if ( a4 < g_CatalogFileHashAlgorithm )
    return 3221226536LL;
  result = MinCryptIsFileRevoked(a4, a2, a3);
  if ( (int)result >= 0 )
  {
    LOBYTE(v52) = 0;
    LODWORD(v27) = 0;
    v50 = 0;
    v28 = 0;
    v67 = 0;
    if ( a1 )
    {
      v27 = *a1;
      *(_DWORD *)(*a1 + 2368) |= 0x4000u;
    }
    if ( a9 && !SourceString )
      CipReloadCatalogStores(&v49);
    KeEnterCriticalRegion();
    Resource = (PERESOURCE)(CurrentSiloState + 24);
    ExAcquireResourceSharedLite((PERESOURCE)(CurrentSiloState + 24), 1u);
    if ( a9 )
    {
      CurrentServerSilo = PsGetCurrentServerSilo();
      v67 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      KeStackAttachProcess(g_CiSystemProcess, &ApcState);
      v50 = 1;
      if ( ZwQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &ThreadInformation, 4u, 0) >= 0
        && ThreadInformation != 1 )
      {
        v54 = 1;
        v32 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &v54, 4u);
        v33 = (unsigned __int8)v52;
        if ( v32 >= 0 )
          v33 = 1;
        v52 = v33;
      }
      if ( SourceString )
      {
        for ( i = 0; ; i = 1 )
        {
          v28 = I_ReloadCatalog(v27, 0, a8, a10, a4, SourceString, v58, 0, 0, 0, 0, (__int64)&v51);
          if ( v28 >= 0 )
            break;
          if ( i )
            break;
          ExReleaseResourceLite(Resource);
          CipReloadCatalogStores(&v49);
          ExAcquireResourceSharedLite(Resource, 1u);
          if ( !v49 )
            break;
        }
        v35 = a10;
      }
      else
      {
        v35 = a10;
        LOBYTE(v30) = 1;
        v28 = I_ReloadCatalogs(v27, v30, v31, a8, a10, a4, v58, (__int64)&v51);
        v51 = 1;
      }
    }
    else
    {
      v35 = a10;
    }
    v36 = 0;
    while ( 1 )
    {
      v37 = v63;
      if ( v63 )
        *(_QWORD *)v63 = 0;
      FileOrHeaderHashInLoadedCatalogs = I_FindFileOrHeaderHashInLoadedCatalogs(
                                           (int)a1,
                                           v68[0],
                                           v55,
                                           v56,
                                           a8,
                                           v35,
                                           a11,
                                           a12,
                                           v57,
                                           v60,
                                           v61,
                                           UnicodeString,
                                           v37,
                                           v64,
                                           v65);
      if ( FileOrHeaderHashInLoadedCatalogs != -1073740760 )
        break;
      if ( *(_QWORD *)v66 && a7 >= g_CatalogFileHashAlgorithm )
      {
        FileOrHeaderHashInLoadedCatalogs = MinCryptIsFileRevoked(a7, *(_QWORD *)v66, a6);
        if ( FileOrHeaderHashInLoadedCatalogs < 0 )
          break;
        v40 = v63;
        if ( v63 )
          *(_QWORD *)v63 = 0;
        FileOrHeaderHashInLoadedCatalogs = I_FindFileOrHeaderHashInLoadedCatalogs(
                                             (int)a1,
                                             v66[0],
                                             a7,
                                             a6,
                                             a8,
                                             a10,
                                             a11,
                                             a12,
                                             v57,
                                             v60,
                                             v61,
                                             UnicodeString,
                                             v40,
                                             v64,
                                             v65);
        if ( FileOrHeaderHashInLoadedCatalogs != -1073740760 )
          break;
      }
      if ( v57 || (v41 = v36 == -1, ++v36, !v41 && v36 != 1) )
      {
        if ( v28 >= 0 )
        {
LABEL_40:
          FileOrHeaderHashInLoadedCatalogs = -1073740760;
          break;
        }
LABEL_47:
        FileOrHeaderHashInLoadedCatalogs = v28;
        break;
      }
      if ( v28 < 0 )
        goto LABEL_47;
      v35 = a10;
      if ( v51 )
      {
        v28 = I_ReloadCatalogs(v27, 0, v39, a8, a10, v55, v58, (__int64)&v51);
        if ( v28 < 0 )
          goto LABEL_47;
        if ( v51 )
          continue;
      }
      goto LABEL_40;
    }
    ExReleaseResourceLite(Resource);
    KeLeaveCriticalRegion();
    if ( a1 )
    {
      if ( FileOrHeaderHashInLoadedCatalogs >= 0 )
      {
        v43 = *a1;
        v44 = *(_DWORD *)(*a1 + 2368);
        if ( (v44 & 0x8000) != 0 )
        {
          v45 = *(_DWORD *)(v43 + 32);
          v49 = 0;
          v46 = v45 ? (unsigned __int8)(v45 - 1) & 3u : 0LL;
          *(_DWORD *)(v43 + 2368) = v44 & 0xFFFFBFFF;
          LOBYTE(v42) = *((_BYTE *)a1 + 12);
          FileOrHeaderHashInLoadedCatalogs = CiEvaluatePolicyInfo(
                                               *a1,
                                               *((_DWORD *)a1 + 2),
                                               *((_DWORD *)a1 + 4),
                                               v42,
                                               v43 + 160 * v46 + 40,
                                               0,
                                               String1,
                                               0,
                                               (__int64)&v49);
          if ( FileOrHeaderHashInLoadedCatalogs < 0 )
          {
            v47 = (_QWORD *)v60;
            if ( v60 && *(_QWORD *)v60 )
            {
              ExFreePoolWithTag(*(PVOID *)v60, 0x72634943u);
              *v47 = 0;
            }
            if ( v61 )
              MincryptFreePolicyInfo(v61);
            if ( UnicodeString )
              RtlFreeUnicodeString(UnicodeString);
            if ( v63 )
              *(_QWORD *)v63 = 0;
            if ( v64 )
              MincryptFreePolicyInfo(v64);
            if ( v65 )
              *(_DWORD *)v65 = 0;
          }
        }
      }
      *(_DWORD *)(*a1 + 2368) &= ~0x4000u;
      *(_DWORD *)(*a1 + 2368) &= ~0x8000u;
    }
    if ( (_BYTE)v52 )
      ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, &ThreadInformation, 4u);
    if ( v50 )
    {
      KeUnstackDetachProcess(&ApcState);
      PsDetachSiloFromCurrentThread(v67);
    }
    return (unsigned int)FileOrHeaderHashInLoadedCatalogs;
  }
  return result;
}

```

## disassembly

```asm
0x18008e728  mov     [rsp-8+arg_18], rbx
0x18008e72d  push    rbp
0x18008e72e  push    rsi
0x18008e72f  push    rdi
0x18008e730  push    r12
0x18008e732  push    r13
0x18008e734  push    r14
0x18008e736  push    r15
0x18008e738  lea     rbp, [rsp-40h]
0x18008e73d  sub     rsp, 140h
0x18008e744  mov     rax, cs:__security_cookie
0x18008e74b  xor     rax, rsp
0x18008e74e  mov     [rbp+70h+var_40], rax
0x18008e752  mov     rax, [rbp+70h+arg_90]
0x18008e759  xorps   xmm0, xmm0
0x18008e75c  mov     r12, [rbp+70h+arg_60]
0x18008e763  mov     r14, rdx
0x18008e766  mov     ebx, [rbp+70h+arg_40]
0x18008e76c  mov     r13d, r9d
0x18008e76f  mov     [rbp+70h+var_A0], rax
0x18008e773  mov     r15d, r8d
0x18008e776  mov     rax, [rbp+70h+arg_68]
0x18008e77d  mov     rsi, rcx
0x18008e780  mov     [rbp+70h+var_C8], rax
0x18008e784  mov     rax, [rbp+70h+arg_70]
0x18008e78b  mov     [rbp+70h+var_B8], rax
0x18008e78f  mov     rax, [rbp+70h+arg_80]
0x18008e796  mov     [rbp+70h+var_B0], rax
0x18008e79a  mov     rax, [rbp+70h+arg_88]
0x18008e7a1  mov     [rbp+70h+UnicodeString], rax
0x18008e7a5  mov     rax, [rbp+70h+arg_98]
0x18008e7ac  mov     [rbp+70h+var_98], rax
0x18008e7b0  mov     rax, [rbp+70h+arg_A0]
0x18008e7b7  mov     qword ptr [rbp+70h+var_78], rdx
0x18008e7bb  mov     rdx, [rbp+70h+arg_20]
0x18008e7c2  mov     [rbp+70h+var_90], rax
0x18008e7c6  mov     [rbp+70h+var_DC], r9d
0x18008e7ca  mov     [rbp+70h+var_D8], r8d
0x18008e7ce  mov     qword ptr [rbp+70h+var_88], rdx
0x18008e7d2  mov     [rbp+70h+var_D0], r12
0x18008e7d6  mov     dword ptr [rbp+70h+var_EC], ebx
0x18008e7d9  mov     [rbp+70h+var_E0], 0
0x18008e7e0  mov     [rbp+70h+ThreadInformation], 0
0x18008e7e7  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink], xmm0
0x18008e7eb  mov     [rbp+70h+var_F0], 0
0x18008e7ef  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink+10h], xmm0
0x18008e7f3  movups  xmmword ptr [rbp+70h+ApcState.Process], xmm0
0x18008e7f7  call    CiGetCurrentSiloState
0x18008e7fc  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x18008e803  mov     rdi, rax
0x18008e806  jnb     short loc_18008E812
0x18008e808  mov     eax, 0C0000428h
0x18008e80d  jmp     loc_18008ED73
0x18008e812  mov     r8d, r15d
0x18008e815  mov     rdx, r14
0x18008e818  mov     ecx, r13d
0x18008e81b  call    MinCryptIsFileRevoked
0x18008e820  xor     ecx, ecx
0x18008e822  test    eax, eax
0x18008e824  js      loc_18008ED73
0x18008e82a  mov     byte ptr [rbp+70h+var_EC+4], cl
0x18008e82d  mov     r15d, ecx
0x18008e830  mov     [rbp+70h+var_EF], cl
0x18008e833  mov     r14d, ecx
0x18008e836  mov     [rbp+70h+var_80], rcx
0x18008e83a  test    rsi, rsi
0x18008e83d  jz      short loc_18008E84B
0x18008e83f  mov     r15, [rsi]
0x18008e842  bts     dword ptr [r15+940h], 0Eh
0x18008e84b  test    ebx, ebx
0x18008e84d  jz      short loc_18008E85D
0x18008e84f  test    r12, r12
0x18008e852  jnz     short loc_18008E85D
0x18008e854  lea     rcx, [rbp+70h+var_F0]
0x18008e858  call    CipReloadCatalogStores
0x18008e85d  call    cs:__imp_KeEnterCriticalRegion
0x18008e864  nop     dword ptr [rax+rax+00h]
0x18008e869  lea     rax, [rdi+18h]
0x18008e86d  mov     edi, 1
0x18008e872  mov     dl, dil; Wait
0x18008e875  mov     [rbp+70h+Resource], rax
0x18008e879  mov     rcx, rax; Resource
0x18008e87c  call    cs:__imp_ExAcquireResourceSharedLite
0x18008e883  nop     dword ptr [rax+rax+00h]
0x18008e888  test    ebx, ebx
0x18008e88a  jz      loc_18008EA14
0x18008e890  call    cs:__imp_PsGetCurrentServerSilo
0x18008e897  nop     dword ptr [rax+rax+00h]
0x18008e89c  mov     rcx, rax
0x18008e89f  call    cs:__imp_PsAttachSiloToCurrentThread
0x18008e8a6  nop     dword ptr [rax+rax+00h]
0x18008e8ab  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18008e8b2  lea     rdx, [rbp+70h+ApcState]; ApcState
0x18008e8b6  mov     [rbp+70h+var_80], rax
0x18008e8ba  call    cs:__imp_KeStackAttachProcess
0x18008e8c1  nop     dword ptr [rax+rax+00h]
0x18008e8c6  mov     [rsp+170h+ReturnLength], r14; ReturnLength
0x18008e8cb  lea     ebx, [rdi+3]
0x18008e8ce  lea     r14d, [rdi+17h]
0x18008e8d2  mov     [rbp+70h+var_EF], dil
0x18008e8d6  mov     edx, r14d; ThreadInformationClass
0x18008e8d9  lea     r8, [rbp+70h+ThreadInformation]; ThreadInformation
0x18008e8dd  mov     r9d, ebx; ThreadInformationLength
0x18008e8e0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18008e8e7  call    cs:__imp_ZwQueryInformationThread
0x18008e8ee  nop     dword ptr [rax+rax+00h]
0x18008e8f3  test    eax, eax
0x18008e8f5  js      short loc_18008E92A
0x18008e8f7  cmp     [rbp+70h+ThreadInformation], edi
0x18008e8fa  jz      short loc_18008E92A
0x18008e8fc  mov     r9d, ebx; ThreadInformationLength
0x18008e8ff  mov     [rbp+70h+var_E0], edi
0x18008e902  lea     r8, [rbp+70h+var_E0]; ThreadInformation
0x18008e906  mov     edx, r14d; ThreadInformationClass
0x18008e909  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18008e910  call    cs:__imp_ZwSetInformationThread
0x18008e917  nop     dword ptr [rax+rax+00h]
0x18008e91c  mov     ecx, dword ptr [rbp+70h+var_EC+4]
0x18008e91f  test    eax, eax
0x18008e921  movzx   ecx, cl
0x18008e924  cmovns  ecx, edi
0x18008e927  mov     dword ptr [rbp+70h+var_EC+4], ecx
0x18008e92a  test    r12, r12
0x18008e92d  jz      loc_18008E9D9
0x18008e933  mov     edi, [rbp+70h+arg_48]
0x18008e939  xor     bl, bl
0x18008e93b  mov     r8d, [rbp+70h+arg_38]; int
0x18008e942  lea     rax, [rbp+70h+var_EC]
0x18008e946  mov     [rsp+170h+var_118], rax; __int64
0x18008e94b  mov     r9d, edi; int
0x18008e94e  mov     rax, [rbp+70h+var_C8]
0x18008e952  xor     edx, edx; int
0x18008e954  mov     [rsp+170h+var_120], 0; __int64
0x18008e95d  mov     rcx, r15; int
0x18008e960  mov     [rsp+170h+var_128], 0; __int64
0x18008e969  mov     [rsp+170h+var_130], 0; int
0x18008e972  mov     [rsp+170h+var_138], 0; int
0x18008e97b  mov     [rsp+170h+String1], rax; PCUNICODE_STRING
0x18008e980  mov     [rsp+170h+SourceString], r12; SourceString
0x18008e985  mov     dword ptr [rsp+170h+ReturnLength], r13d; int
0x18008e98a  call    I_ReloadCatalog
0x18008e98f  mov     r14d, eax
0x18008e992  test    eax, eax
0x18008e994  jns     short loc_18008E9D5
0x18008e996  test    bl, bl
0x18008e998  jnz     short loc_18008E9D5
0x18008e99a  mov     rcx, [rbp+70h+Resource]; Resource
0x18008e99e  call    cs:__imp_ExReleaseResourceLite
0x18008e9a5  nop     dword ptr [rax+rax+00h]
0x18008e9aa  lea     rcx, [rbp+70h+var_F0]
0x18008e9ae  call    CipReloadCatalogStores
0x18008e9b3  mov     rcx, [rbp+70h+Resource]; Resource
0x18008e9b7  mov     dl, 1; Wait
0x18008e9b9  call    cs:__imp_ExAcquireResourceSharedLite
0x18008e9c0  nop     dword ptr [rax+rax+00h]
0x18008e9c5  cmp     [rbp+70h+var_F0], bl
0x18008e9c8  jz      short loc_18008E9D5
0x18008e9ca  inc     bl
0x18008e9cc  cmp     bl, 2
0x18008e9cf  jb      loc_18008E93B
0x18008e9d5  mov     ebx, edi
0x18008e9d7  jmp     short loc_18008EA1A
0x18008e9d9  mov     ebx, [rbp+70h+arg_48]
0x18008e9df  lea     rax, [rbp+70h+var_EC]
0x18008e9e3  mov     r9d, [rbp+70h+arg_38]; int
0x18008e9ea  mov     dl, dil; int
0x18008e9ed  mov     [rsp+170h+var_138], rax; __int64
0x18008e9f2  mov     rcx, r15; int
0x18008e9f5  mov     rax, [rbp+70h+var_C8]
0x18008e9f9  mov     [rsp+170h+String1], rax; String1
0x18008e9fe  mov     dword ptr [rsp+170h+SourceString], r13d; int
0x18008ea03  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x18008ea07  call    I_ReloadCatalogs
0x18008ea0c  mov     r14d, eax
0x18008ea0f  mov     dword ptr [rbp+70h+var_EC], edi
0x18008ea12  jmp     short loc_18008EA1A
0x18008ea14  mov     ebx, [rbp+70h+arg_48]
0x18008ea1a  mov     r13d, [rbp+70h+arg_30]
0x18008ea21  xor     r12b, r12b
0x18008ea24  mov     edi, 0C0000428h
0x18008ea29  mov     rax, [rbp+70h+var_A0]
0x18008ea2d  test    rax, rax
0x18008ea30  jz      short loc_18008EA39
0x18008ea32  mov     qword ptr [rax], 0
0x18008ea39  mov     rcx, [rbp+70h+var_90]
0x18008ea3d  mov     r9d, [rbp+70h+var_D8]; int
0x18008ea41  mov     r8d, [rbp+70h+var_DC]; int
0x18008ea45  mov     rdx, qword ptr [rbp+70h+var_78]; int
0x18008ea49  mov     [rsp+170h+var_100], rcx; __int64
0x18008ea4e  mov     rcx, [rbp+70h+var_98]
0x18008ea52  mov     [rsp+170h+var_108], rcx; __int64
0x18008ea57  mov     rcx, rsi; int
0x18008ea5a  mov     [rsp+170h+var_110], rax; __int64
0x18008ea5f  mov     rax, [rbp+70h+UnicodeString]
0x18008ea63  mov     [rsp+170h+var_118], rax; UnicodeString
0x18008ea68  mov     rax, [rbp+70h+var_B0]
0x18008ea6c  mov     [rsp+170h+var_120], rax; __int64
0x18008ea71  mov     rax, [rbp+70h+var_B8]
0x18008ea75  mov     [rsp+170h+var_128], rax; __int64
0x18008ea7a  mov     rax, [rbp+70h+var_D0]
0x18008ea7e  mov     [rsp+170h+var_130], rax; __int64
0x18008ea83  mov     eax, [rbp+70h+arg_58]
0x18008ea89  mov     dword ptr [rsp+170h+var_138], eax; int
0x18008ea8d  mov     eax, [rbp+70h+arg_50]
0x18008ea93  mov     dword ptr [rsp+170h+String1], eax; int
0x18008ea97  mov     eax, [rbp+70h+arg_38]
0x18008ea9d  mov     dword ptr [rsp+170h+SourceString], ebx; int
0x18008eaa1  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x18008eaa5  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x18008eaaa  mov     ebx, eax
0x18008eaac  cmp     eax, edi
0x18008eaae  jnz     loc_18008EBE7
0x18008eab4  mov     rax, qword ptr [rbp+70h+var_88]
0x18008eab8  test    rax, rax
0x18008eabb  jz      loc_18008EB79
0x18008eac1  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x18008eac8  jb      loc_18008EB79
0x18008eace  mov     r8d, [rbp+70h+arg_28]
0x18008ead5  mov     rdx, rax
0x18008ead8  mov     ecx, r13d
0x18008eadb  call    MinCryptIsFileRevoked
0x18008eae0  mov     ebx, eax
0x18008eae2  test    eax, eax
0x18008eae4  js      loc_18008EBE7
0x18008eaea  mov     rax, [rbp+70h+var_A0]
0x18008eaee  test    rax, rax
0x18008eaf1  jz      short loc_18008EAFA
0x18008eaf3  mov     qword ptr [rax], 0
0x18008eafa  mov     rcx, [rbp+70h+var_90]
0x18008eafe  mov     r8d, r13d; int
0x18008eb01  mov     r9d, [rbp+70h+arg_28]; int
0x18008eb08  mov     rdx, qword ptr [rbp+70h+var_88]; int
0x18008eb0c  mov     [rsp+170h+var_100], rcx; __int64
0x18008eb11  mov     rcx, [rbp+70h+var_98]
0x18008eb15  mov     [rsp+170h+var_108], rcx; __int64
0x18008eb1a  mov     rcx, rsi; int
0x18008eb1d  mov     [rsp+170h+var_110], rax; __int64
0x18008eb22  mov     rax, [rbp+70h+UnicodeString]
0x18008eb26  mov     [rsp+170h+var_118], rax; UnicodeString
0x18008eb2b  mov     rax, [rbp+70h+var_B0]
0x18008eb2f  mov     [rsp+170h+var_120], rax; __int64
0x18008eb34  mov     rax, [rbp+70h+var_B8]
0x18008eb38  mov     [rsp+170h+var_128], rax; __int64
0x18008eb3d  mov     rax, [rbp+70h+var_D0]
0x18008eb41  mov     [rsp+170h+var_130], rax; __int64
0x18008eb46  mov     eax, [rbp+70h+arg_58]
0x18008eb4c  mov     dword ptr [rsp+170h+var_138], eax; int
0x18008eb50  mov     eax, [rbp+70h+arg_50]
0x18008eb56  mov     dword ptr [rsp+170h+String1], eax; int
0x18008eb5a  mov     eax, [rbp+70h+arg_48]
0x18008eb60  mov     dword ptr [rsp+170h+SourceString], eax; int
0x18008eb64  mov     eax, [rbp+70h+arg_38]
0x18008eb6a  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x18008eb6e  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x18008eb73  mov     ebx, eax
0x18008eb75  cmp     eax, edi
0x18008eb77  jnz     short loc_18008EBE7
0x18008eb79  cmp     [rbp+70h+var_D0], 0
0x18008eb7e  jnz     loc_18008EC40
0x18008eb84  inc     r12b
0x18008eb87  cmp     r12b, 1
0x18008eb8b  ja      loc_18008EC40
0x18008eb91  test    r14d, r14d
0x18008eb94  js      loc_18008EC45
0x18008eb9a  cmp     dword ptr [rbp+70h+var_EC], 0
0x18008eb9e  mov     ebx, [rbp+70h+arg_48]
0x18008eba4  jz      short loc_18008EBE5
0x18008eba6  mov     r9d, [rbp+70h+arg_38]; int
0x18008ebad  lea     rax, [rbp+70h+var_EC]
0x18008ebb1  mov     [rsp+170h+var_138], rax; __int64
0x18008ebb6  xor     edx, edx; int
0x18008ebb8  mov     rax, [rbp+70h+var_C8]
0x18008ebbc  mov     rcx, r15; int
0x18008ebbf  mov     [rsp+170h+String1], rax; String1
0x18008ebc4  mov     eax, [rbp+70h+var_DC]
0x18008ebc7  mov     dword ptr [rsp+170h+SourceString], eax; int
0x18008ebcb  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x18008ebcf  call    I_ReloadCatalogs
0x18008ebd4  mov     r14d, eax
0x18008ebd7  test    eax, eax
0x18008ebd9  js      short loc_18008EC45
0x18008ebdb  cmp     dword ptr [rbp+70h+var_EC], 0
0x18008ebdf  jnz     loc_18008EA29
0x18008ebe5  mov     ebx, edi
0x18008ebe7  mov     rcx, [rbp+70h+Resource]; Resource
0x18008ebeb  call    cs:__imp_ExReleaseResourceLite
0x18008ebf2  nop     dword ptr [rax+rax+00h]
0x18008ebf7  call    cs:__imp_KeLeaveCriticalRegion
0x18008ebfe  nop     dword ptr [rax+rax+00h]
0x18008ec03  xor     r14d, r14d
0x18008ec06  test    rsi, rsi
0x18008ec09  jz      loc_18008ED24
0x18008ec0f  mov     r15d, 0FFFFBFFFh
0x18008ec15  test    ebx, ebx
0x18008ec17  js      loc_18008ED0F
0x18008ec1d  mov     rdx, [rsi]
0x18008ec20  mov     ecx, [rdx+940h]
0x18008ec26  bt      ecx, 0Fh
0x18008ec2a  jnb     loc_18008ED0F
0x18008ec30  mov     eax, [rdx+20h]
  ... truncated ...
```
