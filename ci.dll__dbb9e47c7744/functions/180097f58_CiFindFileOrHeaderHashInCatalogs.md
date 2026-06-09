# CiFindFileOrHeaderHashInCatalogs

- ea: `0x180097f58`
- end: `0x1800985cb`
- name: `CiFindFileOrHeaderHashInCatalogs`
- size: `1651`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005e480`
- `0x180061404`
- `0x180097998`
- `0x180097ab0`
- `0x180097c10`

## callees

- `0x18000c52c`
- `0x18002bf20`
- `0x180061984`
- `0x18008f2bc`
- `0x180097f58`
- `0x1800985d4`
- `0x180098634`
- `0x1800a2f98`
- `0x1800e2e48`
- `0x1800e8b74`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18009808d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18009808d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18009850a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18009850a`
- `ntoskrnl!KeStackAttachProcess` at `0x1800980ea`
- `ntoskrnl!KeStackAttachProcess` at `0x1800980ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800984de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800984de`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180098585`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180098585`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180098427`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800980cf`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800980cf`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180098595`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180098595`
- `ntoskrnl!ZwQueryInformationThread` at `0x180098117`
- `ntoskrnl!ZwQueryInformationThread` at `0x180098117`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800980ac`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800981e9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800980ac`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800981e9`
- `ntoskrnl!ZwSetInformationThread` at `0x180098140`
- `ntoskrnl!ZwSetInformationThread` at `0x18009856f`
- `ntoskrnl!ZwSetInformationThread` at `0x180098140`
- `ntoskrnl!ZwSetInformationThread` at `0x18009856f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800981ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009841b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800981ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009841b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800980c0`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800980c0`

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
0x180097f58  mov     [rsp-8+arg_18], rbx
0x180097f5d  push    rbp
0x180097f5e  push    rsi
0x180097f5f  push    rdi
0x180097f60  push    r12
0x180097f62  push    r13
0x180097f64  push    r14
0x180097f66  push    r15
0x180097f68  lea     rbp, [rsp-40h]
0x180097f6d  sub     rsp, 140h
0x180097f74  mov     rax, cs:__security_cookie
0x180097f7b  xor     rax, rsp
0x180097f7e  mov     [rbp+70h+var_40], rax
0x180097f82  mov     rax, [rbp+70h+arg_90]
0x180097f89  xorps   xmm0, xmm0
0x180097f8c  mov     r12, [rbp+70h+arg_60]
0x180097f93  mov     r14, rdx
0x180097f96  mov     ebx, [rbp+70h+arg_40]
0x180097f9c  mov     r13d, r9d
0x180097f9f  mov     [rbp+70h+var_A0], rax
0x180097fa3  mov     r15d, r8d
0x180097fa6  mov     rax, [rbp+70h+arg_68]
0x180097fad  mov     rsi, rcx
0x180097fb0  mov     [rbp+70h+var_C8], rax
0x180097fb4  mov     rax, [rbp+70h+arg_70]
0x180097fbb  mov     [rbp+70h+var_B8], rax
0x180097fbf  mov     rax, [rbp+70h+arg_80]
0x180097fc6  mov     [rbp+70h+var_B0], rax
0x180097fca  mov     rax, [rbp+70h+arg_88]
0x180097fd1  mov     [rbp+70h+UnicodeString], rax
0x180097fd5  mov     rax, [rbp+70h+arg_98]
0x180097fdc  mov     [rbp+70h+var_98], rax
0x180097fe0  mov     rax, [rbp+70h+arg_A0]
0x180097fe7  mov     qword ptr [rbp+70h+var_78], rdx
0x180097feb  mov     rdx, [rbp+70h+arg_20]
0x180097ff2  mov     [rbp+70h+var_90], rax
0x180097ff6  mov     [rbp+70h+var_DC], r9d
0x180097ffa  mov     [rbp+70h+var_D8], r8d
0x180097ffe  mov     qword ptr [rbp+70h+var_88], rdx
0x180098002  mov     [rbp+70h+var_D0], r12
0x180098006  mov     dword ptr [rbp+70h+var_EC], ebx
0x180098009  mov     [rbp+70h+var_E0], 0
0x180098010  mov     [rbp+70h+ThreadInformation], 0
0x180098017  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink], xmm0
0x18009801b  mov     [rbp+70h+var_F0], 0
0x18009801f  movups  xmmword ptr [rbp+70h+ApcState.ApcListHead.Flink+10h], xmm0
0x180098023  movups  xmmword ptr [rbp+70h+ApcState.Process], xmm0
0x180098027  call    CiGetCurrentSiloState
0x18009802c  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x180098033  mov     rdi, rax
0x180098036  jnb     short loc_180098042
0x180098038  mov     eax, 0C0000428h
0x18009803d  jmp     loc_1800985A3
0x180098042  mov     r8d, r15d
0x180098045  mov     rdx, r14
0x180098048  mov     ecx, r13d
0x18009804b  call    MinCryptIsFileRevoked
0x180098050  xor     ecx, ecx
0x180098052  test    eax, eax
0x180098054  js      loc_1800985A3
0x18009805a  mov     byte ptr [rbp+70h+var_EC+4], cl
0x18009805d  mov     r15d, ecx
0x180098060  mov     [rbp+70h+var_EF], cl
0x180098063  mov     r14d, ecx
0x180098066  mov     [rbp+70h+var_80], rcx
0x18009806a  test    rsi, rsi
0x18009806d  jz      short loc_18009807B
0x18009806f  mov     r15, [rsi]
0x180098072  bts     dword ptr [r15+938h], 0Eh
0x18009807b  test    ebx, ebx
0x18009807d  jz      short loc_18009808D
0x18009807f  test    r12, r12
0x180098082  jnz     short loc_18009808D
0x180098084  lea     rcx, [rbp+70h+var_F0]
0x180098088  call    CipReloadCatalogStores
0x18009808d  call    cs:__imp_KeEnterCriticalRegion
0x180098094  nop     dword ptr [rax+rax+00h]
0x180098099  lea     rax, [rdi+18h]
0x18009809d  mov     edi, 1
0x1800980a2  mov     dl, dil; Wait
0x1800980a5  mov     [rbp+70h+Resource], rax
0x1800980a9  mov     rcx, rax; Resource
0x1800980ac  call    cs:__imp_ExAcquireResourceSharedLite
0x1800980b3  nop     dword ptr [rax+rax+00h]
0x1800980b8  test    ebx, ebx
0x1800980ba  jz      loc_180098244
0x1800980c0  call    cs:__imp_PsGetCurrentServerSilo
0x1800980c7  nop     dword ptr [rax+rax+00h]
0x1800980cc  mov     rcx, rax
0x1800980cf  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800980d6  nop     dword ptr [rax+rax+00h]
0x1800980db  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x1800980e2  lea     rdx, [rbp+70h+ApcState]; ApcState
0x1800980e6  mov     [rbp+70h+var_80], rax
0x1800980ea  call    cs:__imp_KeStackAttachProcess
0x1800980f1  nop     dword ptr [rax+rax+00h]
0x1800980f6  mov     [rsp+170h+ReturnLength], r14; ReturnLength
0x1800980fb  lea     ebx, [rdi+3]
0x1800980fe  lea     r14d, [rdi+17h]
0x180098102  mov     [rbp+70h+var_EF], dil
0x180098106  mov     edx, r14d; ThreadInformationClass
0x180098109  lea     r8, [rbp+70h+ThreadInformation]; ThreadInformation
0x18009810d  mov     r9d, ebx; ThreadInformationLength
0x180098110  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180098117  call    cs:__imp_ZwQueryInformationThread
0x18009811e  nop     dword ptr [rax+rax+00h]
0x180098123  test    eax, eax
0x180098125  js      short loc_18009815A
0x180098127  cmp     [rbp+70h+ThreadInformation], edi
0x18009812a  jz      short loc_18009815A
0x18009812c  mov     r9d, ebx; ThreadInformationLength
0x18009812f  mov     [rbp+70h+var_E0], edi
0x180098132  lea     r8, [rbp+70h+var_E0]; ThreadInformation
0x180098136  mov     edx, r14d; ThreadInformationClass
0x180098139  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180098140  call    cs:__imp_ZwSetInformationThread
0x180098147  nop     dword ptr [rax+rax+00h]
0x18009814c  mov     ecx, dword ptr [rbp+70h+var_EC+4]
0x18009814f  test    eax, eax
0x180098151  movzx   ecx, cl
0x180098154  cmovns  ecx, edi
0x180098157  mov     dword ptr [rbp+70h+var_EC+4], ecx
0x18009815a  test    r12, r12
0x18009815d  jz      loc_180098209
0x180098163  mov     edi, [rbp+70h+arg_48]
0x180098169  xor     bl, bl
0x18009816b  mov     r8d, [rbp+70h+arg_38]; int
0x180098172  lea     rax, [rbp+70h+var_EC]
0x180098176  mov     [rsp+170h+var_118], rax; __int64
0x18009817b  mov     r9d, edi; int
0x18009817e  mov     rax, [rbp+70h+var_C8]
0x180098182  xor     edx, edx; int
0x180098184  mov     [rsp+170h+var_120], 0; __int64
0x18009818d  mov     rcx, r15; int
0x180098190  mov     [rsp+170h+var_128], 0; __int64
0x180098199  mov     [rsp+170h+var_130], 0; int
0x1800981a2  mov     [rsp+170h+var_138], 0; int
0x1800981ab  mov     [rsp+170h+String1], rax; PCUNICODE_STRING
0x1800981b0  mov     [rsp+170h+SourceString], r12; SourceString
0x1800981b5  mov     dword ptr [rsp+170h+ReturnLength], r13d; int
0x1800981ba  call    I_ReloadCatalog
0x1800981bf  mov     r14d, eax
0x1800981c2  test    eax, eax
0x1800981c4  jns     short loc_180098205
0x1800981c6  test    bl, bl
0x1800981c8  jnz     short loc_180098205
0x1800981ca  mov     rcx, [rbp+70h+Resource]; Resource
0x1800981ce  call    cs:__imp_ExReleaseResourceLite
0x1800981d5  nop     dword ptr [rax+rax+00h]
0x1800981da  lea     rcx, [rbp+70h+var_F0]
0x1800981de  call    CipReloadCatalogStores
0x1800981e3  mov     rcx, [rbp+70h+Resource]; Resource
0x1800981e7  mov     dl, 1; Wait
0x1800981e9  call    cs:__imp_ExAcquireResourceSharedLite
0x1800981f0  nop     dword ptr [rax+rax+00h]
0x1800981f5  cmp     [rbp+70h+var_F0], bl
0x1800981f8  jz      short loc_180098205
0x1800981fa  inc     bl
0x1800981fc  cmp     bl, 2
0x1800981ff  jb      loc_18009816B
0x180098205  mov     ebx, edi
0x180098207  jmp     short loc_18009824A
0x180098209  mov     ebx, [rbp+70h+arg_48]
0x18009820f  lea     rax, [rbp+70h+var_EC]
0x180098213  mov     r9d, [rbp+70h+arg_38]; int
0x18009821a  mov     dl, dil; int
0x18009821d  mov     [rsp+170h+var_138], rax; __int64
0x180098222  mov     rcx, r15; int
0x180098225  mov     rax, [rbp+70h+var_C8]
0x180098229  mov     [rsp+170h+String1], rax; String1
0x18009822e  mov     dword ptr [rsp+170h+SourceString], r13d; int
0x180098233  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x180098237  call    I_ReloadCatalogs
0x18009823c  mov     r14d, eax
0x18009823f  mov     dword ptr [rbp+70h+var_EC], edi
0x180098242  jmp     short loc_18009824A
0x180098244  mov     ebx, [rbp+70h+arg_48]
0x18009824a  mov     r13d, [rbp+70h+arg_30]
0x180098251  xor     r12b, r12b
0x180098254  mov     edi, 0C0000428h
0x180098259  mov     rax, [rbp+70h+var_A0]
0x18009825d  test    rax, rax
0x180098260  jz      short loc_180098269
0x180098262  mov     qword ptr [rax], 0
0x180098269  mov     rcx, [rbp+70h+var_90]
0x18009826d  mov     r9d, [rbp+70h+var_D8]; int
0x180098271  mov     r8d, [rbp+70h+var_DC]; int
0x180098275  mov     rdx, qword ptr [rbp+70h+var_78]; int
0x180098279  mov     [rsp+170h+var_100], rcx; __int64
0x18009827e  mov     rcx, [rbp+70h+var_98]
0x180098282  mov     [rsp+170h+var_108], rcx; __int64
0x180098287  mov     rcx, rsi; int
0x18009828a  mov     [rsp+170h+var_110], rax; __int64
0x18009828f  mov     rax, [rbp+70h+UnicodeString]
0x180098293  mov     [rsp+170h+var_118], rax; UnicodeString
0x180098298  mov     rax, [rbp+70h+var_B0]
0x18009829c  mov     [rsp+170h+var_120], rax; __int64
0x1800982a1  mov     rax, [rbp+70h+var_B8]
0x1800982a5  mov     [rsp+170h+var_128], rax; __int64
0x1800982aa  mov     rax, [rbp+70h+var_D0]
0x1800982ae  mov     [rsp+170h+var_130], rax; __int64
0x1800982b3  mov     eax, [rbp+70h+arg_58]
0x1800982b9  mov     dword ptr [rsp+170h+var_138], eax; int
0x1800982bd  mov     eax, [rbp+70h+arg_50]
0x1800982c3  mov     dword ptr [rsp+170h+String1], eax; int
0x1800982c7  mov     eax, [rbp+70h+arg_38]
0x1800982cd  mov     dword ptr [rsp+170h+SourceString], ebx; int
0x1800982d1  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x1800982d5  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x1800982da  mov     ebx, eax
0x1800982dc  cmp     eax, edi
0x1800982de  jnz     loc_180098417
0x1800982e4  mov     rax, qword ptr [rbp+70h+var_88]
0x1800982e8  test    rax, rax
0x1800982eb  jz      loc_1800983A9
0x1800982f1  cmp     r13d, cs:g_CatalogFileHashAlgorithm
0x1800982f8  jb      loc_1800983A9
0x1800982fe  mov     r8d, [rbp+70h+arg_28]
0x180098305  mov     rdx, rax
0x180098308  mov     ecx, r13d
0x18009830b  call    MinCryptIsFileRevoked
0x180098310  mov     ebx, eax
0x180098312  test    eax, eax
0x180098314  js      loc_180098417
0x18009831a  mov     rax, [rbp+70h+var_A0]
0x18009831e  test    rax, rax
0x180098321  jz      short loc_18009832A
0x180098323  mov     qword ptr [rax], 0
0x18009832a  mov     rcx, [rbp+70h+var_90]
0x18009832e  mov     r8d, r13d; int
0x180098331  mov     r9d, [rbp+70h+arg_28]; int
0x180098338  mov     rdx, qword ptr [rbp+70h+var_88]; int
0x18009833c  mov     [rsp+170h+var_100], rcx; __int64
0x180098341  mov     rcx, [rbp+70h+var_98]
0x180098345  mov     [rsp+170h+var_108], rcx; __int64
0x18009834a  mov     rcx, rsi; int
0x18009834d  mov     [rsp+170h+var_110], rax; __int64
0x180098352  mov     rax, [rbp+70h+UnicodeString]
0x180098356  mov     [rsp+170h+var_118], rax; UnicodeString
0x18009835b  mov     rax, [rbp+70h+var_B0]
0x18009835f  mov     [rsp+170h+var_120], rax; __int64
0x180098364  mov     rax, [rbp+70h+var_B8]
0x180098368  mov     [rsp+170h+var_128], rax; __int64
0x18009836d  mov     rax, [rbp+70h+var_D0]
0x180098371  mov     [rsp+170h+var_130], rax; __int64
0x180098376  mov     eax, [rbp+70h+arg_58]
0x18009837c  mov     dword ptr [rsp+170h+var_138], eax; int
0x180098380  mov     eax, [rbp+70h+arg_50]
0x180098386  mov     dword ptr [rsp+170h+String1], eax; int
0x18009838a  mov     eax, [rbp+70h+arg_48]
0x180098390  mov     dword ptr [rsp+170h+SourceString], eax; int
0x180098394  mov     eax, [rbp+70h+arg_38]
0x18009839a  mov     dword ptr [rsp+170h+ReturnLength], eax; int
0x18009839e  call    I_FindFileOrHeaderHashInLoadedCatalogs
0x1800983a3  mov     ebx, eax
0x1800983a5  cmp     eax, edi
0x1800983a7  jnz     short loc_180098417
0x1800983a9  cmp     [rbp+70h+var_D0], 0
0x1800983ae  jnz     loc_180098470
0x1800983b4  inc     r12b
0x1800983b7  cmp     r12b, 1
0x1800983bb  ja      loc_180098470
0x1800983c1  test    r14d, r14d
0x1800983c4  js      loc_180098475
0x1800983ca  cmp     dword ptr [rbp+70h+var_EC], 0
0x1800983ce  mov     ebx, [rbp+70h+arg_48]
0x1800983d4  jz      short loc_180098415
0x1800983d6  mov     r9d, [rbp+70h+arg_38]; int
0x1800983dd  lea     rax, [rbp+70h+var_EC]
0x1800983e1  mov     [rsp+170h+var_138], rax; __int64
0x1800983e6  xor     edx, edx; int
0x1800983e8  mov     rax, [rbp+70h+var_C8]
0x1800983ec  mov     rcx, r15; int
0x1800983ef  mov     [rsp+170h+String1], rax; String1
0x1800983f4  mov     eax, [rbp+70h+var_DC]
0x1800983f7  mov     dword ptr [rsp+170h+SourceString], eax; int
0x1800983fb  mov     dword ptr [rsp+170h+ReturnLength], ebx; int
0x1800983ff  call    I_ReloadCatalogs
0x180098404  mov     r14d, eax
0x180098407  test    eax, eax
0x180098409  js      short loc_180098475
0x18009840b  cmp     dword ptr [rbp+70h+var_EC], 0
0x18009840f  jnz     loc_180098259
0x180098415  mov     ebx, edi
0x180098417  mov     rcx, [rbp+70h+Resource]; Resource
0x18009841b  call    cs:__imp_ExReleaseResourceLite
0x180098422  nop     dword ptr [rax+rax+00h]
0x180098427  call    cs:__imp_KeLeaveCriticalRegion
0x18009842e  nop     dword ptr [rax+rax+00h]
0x180098433  xor     r14d, r14d
0x180098436  test    rsi, rsi
0x180098439  jz      loc_180098554
0x18009843f  mov     r15d, 0FFFFBFFFh
0x180098445  test    ebx, ebx
0x180098447  js      loc_18009853F
0x18009844d  mov     rdx, [rsi]
0x180098450  mov     ecx, [rdx+938h]
0x180098456  bt      ecx, 0Fh
0x18009845a  jnb     loc_18009853F
0x180098460  mov     eax, [rdx+20h]
  ... truncated ...
```
