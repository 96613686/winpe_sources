# CiFindFileOrHeaderHashInCatalogs

- ea: `0x180096928`
- end: `0x180096f9b`
- name: `CiFindFileOrHeaderHashInCatalogs`
- size: `1651`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005dd80`
- `0x180060c48`
- `0x180096368`
- `0x180096480`
- `0x1800965e0`

## callees

- `0x18000c52c`
- `0x18002bef0`
- `0x180061140`
- `0x18008dc8c`
- `0x180096928`
- `0x180096fa4`
- `0x180097004`
- `0x1800a1968`
- `0x1800e1e58`
- `0x1800e75c8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180096a5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180096a5d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180096eda`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180096eda`
- `ntoskrnl!KeStackAttachProcess` at `0x180096aba`
- `ntoskrnl!KeStackAttachProcess` at `0x180096aba`
- `ntoskrnl!ExFreePoolWithTag` at `0x180096eae`
- `ntoskrnl!ExFreePoolWithTag` at `0x180096eae`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180096f55`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180096f55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180096df7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180096df7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180096a9f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180096a9f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180096f65`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180096f65`
- `ntoskrnl!ZwQueryInformationThread` at `0x180096ae7`
- `ntoskrnl!ZwQueryInformationThread` at `0x180096ae7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180096a7c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180096bb9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180096a7c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180096bb9`
- `ntoskrnl!ZwSetInformationThread` at `0x180096b10`
- `ntoskrnl!ZwSetInformationThread` at `0x180096f3f`
- `ntoskrnl!ZwSetInformationThread` at `0x180096b10`
- `ntoskrnl!ZwSetInformationThread` at `0x180096f3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x180096b9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180096deb`
- `ntoskrnl!ExReleaseResourceLite` at `0x180096b9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x180096deb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180096a90`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180096a90`

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
      *(_DWORD *)(*a1 + 2360) |= 0x4000u;
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
        v44 = *(_DWORD *)(*a1 + 2360);
        if ( (v44 & 0x8000) != 0 )
        {
          v45 = *(_DWORD *)(v43 + 32);
          v49 = 0;
          v46 = v45 ? (unsigned __int8)(v45 - 1) & 3u : 0LL;
          *(_DWORD *)(v43 + 2360) = v44 & 0xFFFFBFFF;
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
      *(_DWORD *)(*a1 + 2360) &= ~0x4000u;
      *(_DWORD *)(*a1 + 2360) &= ~0x8000u;
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
0x180096928  mov     [rsp-8+arg_18], rbx
0x18009692d  push    rbp
0x18009692e  push    rsi
0x18009692f  push    rdi
0x180096930  push    r12
0x180096932  push    r13
0x180096934  push    r14
0x180096936  push    r15
0x180096938  lea     rbp, [rsp-40h]
0x18009693d  sub     rsp, 140h
0x180096944  mov     rax, cs:__security_cookie
0x18009694b  xor     rax, rsp
0x18009694e  mov     [rbp+70h+var_40], rax
0x180096952  mov     rax, [rbp+70h+arg_90]
0x180096959  xorps   xmm0, xmm0
0x18009695c  mov     r12, [rbp+70h+arg_60]
0x180096963  mov     r14, rdx
0x180096966  mov     ebx, [rbp+70h+arg_40]
0x18009696c  mov     r13d, r9d
0x18009696f  mov     [rbp+70h+var_A0], rax
0x180096973  mov     r15d, r8d
0x180096976  mov     rax, [rbp+70h+arg_68]
0x18009697d  mov     rsi, rcx
0x180096980  mov     [rbp+70h+var_C8], rax
0x180096984  mov     rax, [rbp+70h+arg_70]
0x18009698b  mov     [rbp+70h+var_B8], rax
0x18009698f  mov     rax, [rbp+70h+arg_80]
0x180096996  mov     [rbp+70h+var_B0], rax
0x18009699a  mov     rax, [rbp+70h+arg_88]
0x1800969a1  mov     [rbp+70h+UnicodeString], rax
0x1800969a5  mov     rax, [rbp+70h+arg_98]
0x1800969ac  mov     [rbp+70h+var_98], rax
0x1800969b0  mov     rax, [rbp+70h+arg_A0]
0x1800969b7  mov     qword ptr [rbp+70h+var_78], rdx
0x1800969bb  mov     rdx, [rbp+70h+arg_20]
0x1800969c2  mov     [rbp+70h+var_90], rax
0x1800969c6  mov     [rbp+70h+var_DC], r9d
0x1800969ca  mov     [rbp+70h+var_D8], r8d
0x1800969ce  mov     qword ptr [rbp+70h+var_88], rdx
0x1800969d2  mov     [rbp+70h+var_D0], r12
0x1800969d6  mov     dword ptr [rbp+70h+var_EC], ebx
0x1800969d9  mov     [rbp+70h+var_E0], 0
0x1800969e0  mov     [rbp+70h+ThreadInformation], 0
0x1800969e7  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink], xmm0
0x1800969eb  mov     [rbp+70h+var_F0], 0
0x1800969ef  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink+10h], xmm0
0x1800969f3  movups  xmmword ptr [rbp+70h+ApcState.Process], xmm0
0x1800969f7  call    CiGetCurrentSiloState
0x1800969fc  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x180096a03  mov     rdi, rax
0x180096a06  jnb     short loc_180096A12
0x180096a08  mov     eax, 0C0000428h
0x180096a0d  jmp     loc_180096F73
0x180096a12  mov     r8d, r15d
0x180096a15  mov     rdx, r14
0x180096a18  mov     ecx, r13d
0x180096a1b  call    MinCryptIsFileRevoked
0x180096a20  xor     ecx, ecx
0x180096a22  test    eax, eax
0x180096a24  js      loc_180096F73
0x180096a2a  mov     byte ptr [rbp+70h+var_EC+4], cl
0x180096a2d  mov     r15d, ecx
0x180096a30  mov     [rbp+70h+var_EF], cl
0x180096a33  mov     r14d, ecx
0x180096a36  mov     [rbp+70h+var_80], rcx
0x180096a3a  test    rsi, rsi
0x180096a3d  jz      short loc_180096A4B
0x180096a3f  mov     r15, [rsi]
0x180096a42  bts     dword ptr [r15+938h], 0Eh
0x180096a4b  test    ebx, ebx
0x180096a4d  jz      short loc_180096A5D
0x180096a4f  test    r12, r12
0x180096a52  jnz     short loc_180096A5D
0x180096a54  lea     rcx, [rbp+70h+var_F0]
0x180096a58  call    CipReloadCatalogStores
0x180096a5d  call    cs:__imp_KeEnterCriticalRegion
0x180096a64  nop     dword ptr [rax+rax+00h]
0x180096a69  lea     rax, [rdi+18h]
0x180096a6d  mov     edi, 1
0x180096a72  mov     dl, dil; Wait
0x180096a75  mov     [rbp+70h+Resource], rax
0x180096a79  mov     rcx, rax; Resource
0x180096a7c  call    cs:__imp_ExAcquireResourceSharedLite
0x180096a83  nop     dword ptr [rax+rax+00h]
0x180096a88  test    ebx, ebx
0x180096a8a  jz      loc_180096C14
0x180096a90  call    cs:__imp_PsGetCurrentServerSilo
0x180096a97  nop     dword ptr [rax+rax+00h]
0x180096a9c  mov     rcx, rax
0x180096a9f  call    cs:__imp_PsAttachSiloToCurrentThread
0x180096aa6  nop     dword ptr [rax+rax+00h]
0x180096aab  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180096ab2  lea     rdx, [rbp+70h+ApcState]; ApcState
0x180096ab6  mov     [rbp+70h+var_80], rax
0x180096aba  call    cs:__imp_KeStackAttachProcess
0x180096ac1  nop     dword ptr [rax+rax+00h]
0x180096ac6  mov     [rsp+170h+ReturnLength], r14; ReturnLength
0x180096acb  lea     ebx, [rdi+3]
0x180096ace  lea     r14d, [rdi+17h]
0x180096ad2  mov     [rbp+70h+var_EF], dil
0x180096ad6  mov     edx, r14d; ThreadInformationClass
0x180096ad9  lea     r8, [rbp+70h+ThreadInformation]; ThreadInformation
0x180096add  mov     r9d, ebx; ThreadInformationLength
0x180096ae0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180096ae7  call    cs:__imp_ZwQueryInformationThread
0x180096aee  nop     dword ptr [rax+rax+00h]
0x180096af3  test    eax, eax
0x180096af5  js      short loc_180096B2A
0x180096af7  cmp     [rbp+70h+ThreadInformation], edi
0x180096afa  jz      short loc_180096B2A
0x180096afc  mov     r9d, ebx; ThreadInformationLength
0x180096aff  mov     [rbp+70h+var_E0], edi
0x180096b02  lea     r8, [rbp+70h+var_E0]; ThreadInformation
0x180096b06  mov     edx, r14d; ThreadInformationClass
0x180096b09  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180096b10  call    cs:__imp_ZwSetInformationThread
0x180096b17  nop     dword ptr [rax+rax+00h]
0x180096b1c  mov     ecx, dword ptr [rbp+70h+var_EC+4]
0x180096b1f  test    eax, eax
0x180096b21  movzx   ecx, cl
0x180096b24  cmovns  ecx, edi
0x180096b27  mov     dword ptr [rbp+70h+var_EC+4], ecx
0x180096b2a  test    r12, r12
0x180096b2d  jz      loc_180096BD9
0x180096b33  mov     edi, [rbp+70h+arg_48]
0x180096b39  xor     bl, bl
0x180096b3b  mov     r8d, [rbp+70h+arg_38]; int
0x180096b42  lea     rax, [rbp+70h+var_EC]
0x180096b46  mov     [rsp+170h+var_118], rax; __int64
0x180096b4b  mov     r9d, edi; int
0x180096b4e  mov     rax, [rbp+70h+var_C8]
0x180096b52  xor     edx, edx; int
0x180096b54  mov     [rsp+170h+var_120], 0; __int64
0x180096b5d  mov     rcx, r15; int
0x180096b60  mov     [rsp+170h+var_128], 0; __int64
0x180096b69  mov     [rsp+170h+var_130], 0; int
0x180096b72  mov     [rsp+170h+var_138], 0; int
0x180096b7b  mov     [rsp+170h+String1], rax; PCUNICODE_STRING
0x180096b80  mov     [rsp+170h+SourceString], r12; SourceString
0x180096b85  mov     dword ptr [rsp+170h+ReturnLength], r13d; int
0x180096b8a  call    I_ReloadCatalog
0x180096b8f  mov     r14d, eax
0x180096b92  test    eax, eax
0x180096b94  jns     short loc_180096BD5
0x180096b96  test    bl, bl
0x180096b98  jnz     short loc_180096BD5
0x180096b9a  mov     rcx, [rbp+70h+Resource]; Resource
0x180096b9e  call    cs:__imp_ExReleaseResourceLite
0x180096ba5  nop     dword ptr [rax+rax+00h]
0x180096baa  lea     rcx, [rbp+70h+var_F0]
0x180096bae  call    CipReloadCatalogStores
0x180096bb3  mov     rcx, [rbp+70h+Resource]; Resource
0x180096bb7  mov     dl, 1; Wait
0x180096bb9  call    cs:__imp_ExAcquireResourceSharedLite
0x180096bc0  nop     dword ptr [rax+rax+00h]
0x180096bc5  cmp     [rbp+70h+var_F0], bl
0x180096bc8  jz      short loc_180096BD5
0x180096bca  inc     bl
0x180096bcc  cmp     bl, 2
0x180096bcf  jb      loc_180096B3B
0x180096bd5  mov     ebx, edi
0x180096bd7  jmp     short loc_180096C1A
0x180096bd9  mov     ebx, [rbp+70h+arg_48]
0x180096bdf  lea     rax, [rbp+70h+var_EC]
0x180096be3  mov     r9d, [rbp+70h+arg_38]; int
0x180096bea  mov     dl, dil; int
0x180096bed  mov     [rsp+170h+var_138], rax; __int64
0x180096bf2  mov     rcx, r15; int
0x180096bf5  mov     rax, [rbp+70h+var_C8]
0x180096bf9  mov     [rsp+170h+String1], rax; String1
0x180096bfe  mov     dword ptr [rsp+170h+SourceString], r13d; int
0x180096c03  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x180096c07  call    I_ReloadCatalogs
0x180096c0c  mov     r14d, eax
0x180096c0f  mov     dword ptr [rbp+70h+var_EC], edi
0x180096c12  jmp     short loc_180096C1A
0x180096c14  mov     ebx, [rbp+70h+arg_48]
0x180096c1a  mov     r13d, [rbp+70h+arg_30]
0x180096c21  xor     r12b, r12b
0x180096c24  mov     edi, 0C0000428h
0x180096c29  mov     rax, [rbp+70h+var_A0]
0x180096c2d  test    rax, rax
0x180096c30  jz      short loc_180096C39
0x180096c32  mov     qword ptr [rax], 0
0x180096c39  mov     rcx, [rbp+70h+var_90]
0x180096c3d  mov     r9d, [rbp+70h+var_D8]; int
0x180096c41  mov     r8d, [rbp+70h+var_DC]; int
0x180096c45  mov     rdx, qword ptr [rbp+70h+var_78]; int
0x180096c49  mov     [rsp+170h+var_100], rcx; __int64
0x180096c4e  mov     rcx, [rbp+70h+var_98]
0x180096c52  mov     [rsp+170h+var_108], rcx; __int64
0x180096c57  mov     rcx, rsi; int
0x180096c5a  mov     [rsp+170h+var_110], rax; __int64
0x180096c5f  mov     rax, [rbp+70h+UnicodeString]
0x180096c63  mov     [rsp+170h+var_118], rax; UnicodeString
0x180096c68  mov     rax, [rbp+70h+var_B0]
0x180096c6c  mov     [rsp+170h+var_120], rax; __int64
0x180096c71  mov     rax, [rbp+70h+var_B8]
0x180096c75  mov     [rsp+170h+var_128], rax; __int64
0x180096c7a  mov     rax, [rbp+70h+var_D0]
0x180096c7e  mov     [rsp+170h+var_130], rax; __int64
0x180096c83  mov     eax, [rbp+70h+arg_58]
0x180096c89  mov     dword ptr [rsp+170h+var_138], eax; int
0x180096c8d  mov     eax, [rbp+70h+arg_50]
0x180096c93  mov     dword ptr [rsp+170h+String1], eax; int
0x180096c97  mov     eax, [rbp+70h+arg_38]
0x180096c9d  mov     dword ptr [rsp+170h+SourceString], ebx; int
0x180096ca1  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x180096ca5  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x180096caa  mov     ebx, eax
0x180096cac  cmp     eax, edi
0x180096cae  jnz     loc_180096DE7
0x180096cb4  mov     rax, qword ptr [rbp+70h+var_88]
0x180096cb8  test    rax, rax
0x180096cbb  jz      loc_180096D79
0x180096cc1  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x180096cc8  jb      loc_180096D79
0x180096cce  mov     r8d, [rbp+70h+arg_28]
0x180096cd5  mov     rdx, rax
0x180096cd8  mov     ecx, r13d
0x180096cdb  call    MinCryptIsFileRevoked
0x180096ce0  mov     ebx, eax
0x180096ce2  test    eax, eax
0x180096ce4  js      loc_180096DE7
0x180096cea  mov     rax, [rbp+70h+var_A0]
0x180096cee  test    rax, rax
0x180096cf1  jz      short loc_180096CFA
0x180096cf3  mov     qword ptr [rax], 0
0x180096cfa  mov     rcx, [rbp+70h+var_90]
0x180096cfe  mov     r8d, r13d; int
0x180096d01  mov     r9d, [rbp+70h+arg_28]; int
0x180096d08  mov     rdx, qword ptr [rbp+70h+var_88]; int
0x180096d0c  mov     [rsp+170h+var_100], rcx; __int64
0x180096d11  mov     rcx, [rbp+70h+var_98]
0x180096d15  mov     [rsp+170h+var_108], rcx; __int64
0x180096d1a  mov     rcx, rsi; int
0x180096d1d  mov     [rsp+170h+var_110], rax; __int64
0x180096d22  mov     rax, [rbp+70h+UnicodeString]
0x180096d26  mov     [rsp+170h+var_118], rax; UnicodeString
0x180096d2b  mov     rax, [rbp+70h+var_B0]
0x180096d2f  mov     [rsp+170h+var_120], rax; __int64
0x180096d34  mov     rax, [rbp+70h+var_B8]
0x180096d38  mov     [rsp+170h+var_128], rax; __int64
0x180096d3d  mov     rax, [rbp+70h+var_D0]
0x180096d41  mov     [rsp+170h+var_130], rax; __int64
0x180096d46  mov     eax, [rbp+70h+arg_58]
0x180096d4c  mov     dword ptr [rsp+170h+var_138], eax; int
0x180096d50  mov     eax, [rbp+70h+arg_50]
0x180096d56  mov     dword ptr [rsp+170h+String1], eax; int
0x180096d5a  mov     eax, [rbp+70h+arg_48]
0x180096d60  mov     dword ptr [rsp+170h+SourceString], eax; int
0x180096d64  mov     eax, [rbp+70h+arg_38]
0x180096d6a  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x180096d6e  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x180096d73  mov     ebx, eax
0x180096d75  cmp     eax, edi
0x180096d77  jnz     short loc_180096DE7
0x180096d79  cmp     [rbp+70h+var_D0], 0
0x180096d7e  jnz     loc_180096E40
0x180096d84  inc     r12b
0x180096d87  cmp     r12b, 1
0x180096d8b  ja      loc_180096E40
0x180096d91  test    r14d, r14d
0x180096d94  js      loc_180096E45
0x180096d9a  cmp     dword ptr [rbp+70h+var_EC], 0
0x180096d9e  mov     ebx, [rbp+70h+arg_48]
0x180096da4  jz      short loc_180096DE5
0x180096da6  mov     r9d, [rbp+70h+arg_38]; int
0x180096dad  lea     rax, [rbp+70h+var_EC]
0x180096db1  mov     [rsp+170h+var_138], rax; __int64
0x180096db6  xor     edx, edx; int
0x180096db8  mov     rax, [rbp+70h+var_C8]
0x180096dbc  mov     rcx, r15; int
0x180096dbf  mov     [rsp+170h+String1], rax; String1
0x180096dc4  mov     eax, [rbp+70h+var_DC]
0x180096dc7  mov     dword ptr [rsp+170h+SourceString], eax; int
0x180096dcb  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x180096dcf  call    I_ReloadCatalogs
0x180096dd4  mov     r14d, eax
0x180096dd7  test    eax, eax
0x180096dd9  js      short loc_180096E45
0x180096ddb  cmp     dword ptr [rbp+70h+var_EC], 0
0x180096ddf  jnz     loc_180096C29
0x180096de5  mov     ebx, edi
0x180096de7  mov     rcx, [rbp+70h+Resource]; Resource
0x180096deb  call    cs:__imp_ExReleaseResourceLite
0x180096df2  nop     dword ptr [rax+rax+00h]
0x180096df7  call    cs:__imp_KeLeaveCriticalRegion
0x180096dfe  nop     dword ptr [rax+rax+00h]
0x180096e03  xor     r14d, r14d
0x180096e06  test    rsi, rsi
0x180096e09  jz      loc_180096F24
0x180096e0f  mov     r15d, 0FFFFBFFFh
0x180096e15  test    ebx, ebx
0x180096e17  js      loc_180096F0F
0x180096e1d  mov     rdx, [rsi]
0x180096e20  mov     ecx, [rdx+938h]
0x180096e26  bt      ecx, 0Fh
0x180096e2a  jnb     loc_180096F0F
0x180096e30  mov     eax, [rdx+20h]
  ... truncated ...
```
