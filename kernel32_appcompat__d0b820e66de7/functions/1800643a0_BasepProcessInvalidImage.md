# BasepProcessInvalidImage

- ea: `0x1800643a0`
- end: `0x180064ade`
- name: `BasepProcessInvalidImage`
- size: `1854`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ccf0`
- `0x18001b1cc`
- `0x180023220`
- `0x180033ac4`
- `0x180043664`
- `0x180043e44`
- `0x180044c64`
- `0x18005c2f0`
- `0x1800643a0`
- `0x180064df0`
- `0x180067668`
- `0x1800722e0`
- `0x1800827c0`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x18006480a`
- `ntdll!EtwEventWriteNoRegistration` at `0x180064a73`
- `ntdll!EtwEventWriteNoRegistration` at `0x18006480a`
- `ntdll!EtwEventWriteNoRegistration` at `0x180064a73`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800646c3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800646c3`
- `ntdll!NtQueryInformationToken` at `0x18006454a`
- `ntdll!NtQueryInformationToken` at `0x18006454a`
- `ntdll!RtlQueryPackageIdentity` at `0x18006451a`
- `ntdll!RtlQueryPackageIdentity` at `0x18006451a`
- `ntdll!wcslen` at `0x1800647d9`
- `ntdll!wcslen` at `0x180064a3f`
- `ntdll!wcslen` at `0x1800647d9`
- `ntdll!wcslen` at `0x180064a3f`
- `ntdll!RtlFreeUnicodeString` at `0x1800646fd`
- `ntdll!RtlFreeUnicodeString` at `0x1800646fd`
- `ntdll!RtlSetLastWin32Error` at `0x1800647be`
- `ntdll!RtlSetLastWin32Error` at `0x1800647be`
- `ntdll!RtlFreeHeap` at `0x180064639`
- `ntdll!RtlFreeHeap` at `0x180064688`
- `ntdll!RtlFreeHeap` at `0x1800646ab`
- `ntdll!RtlFreeHeap` at `0x1800646e7`
- `ntdll!RtlFreeHeap` at `0x18006474e`
- `ntdll!RtlFreeHeap` at `0x180064639`
- `ntdll!RtlFreeHeap` at `0x180064688`
- `ntdll!RtlFreeHeap` at `0x1800646ab`
- `ntdll!RtlFreeHeap` at `0x1800646e7`
- `ntdll!RtlFreeHeap` at `0x18006474e`
- `ntdll!RtlAllocateHeap` at `0x18006459b`
- `ntdll!RtlAllocateHeap` at `0x180064613`
- `ntdll!RtlAllocateHeap` at `0x18006459b`
- `ntdll!RtlAllocateHeap` at `0x180064613`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006457a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800645eb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006457a`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800645eb`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800645ba`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800645ba`

## string_xrefs

- `0x1800645d7`: `\system32\csrstub.exe`

## pseudocode

```c
__int64 __fastcall BasepProcessInvalidImage(
        NTSTATUS a1,
        void *a2,
        const WCHAR *a3,
        _QWORD *a4,
        PWSTR *a5,
        __int64 a6,
        unsigned int *a7,
        _DWORD *a8,
        __int64 a9,
        _BYTE *a10,
        _QWORD *a11,
        __int64 a12,
        __int64 a13,
        unsigned int *a14,
        PUNICODE_STRING UnicodeString,
        __int64 a16,
        __int64 a17,
        _DWORD *a18,
        _DWORD *a19,
        _DWORD *a20,
        _QWORD *a21)
{
  NTSTATUS inited; // ebx
  NTSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 SessionId; // rcx
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rbx
  DWORD EnvironmentVariableW; // esi
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  ULONG *v37; // rax
  __int64 v38; // r14
  PVOID v39; // rsi
  int v40; // r14d
  ULONG v42; // ecx
  int v43; // eax
  _BYTE *v44; // rax
  void *v45; // rbx
  ULONG v46; // eax
  _DWORD *v47; // rsi
  __int64 v48; // r14
  __int64 v49; // r12
  __int64 v50; // rcx
  int v51; // eax
  int v52; // ebx
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  _QWORD *v55; // rcx
  int v56; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  _BYTE v58[12]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v59; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE *v60; // [rsp+60h] [rbp-A0h]
  _QWORD *v61; // [rsp+68h] [rbp-98h]
  _QWORD *v62; // [rsp+70h] [rbp-90h]
  __int64 v63; // [rsp+78h] [rbp-88h]
  void *v64; // [rsp+80h] [rbp-80h]
  _DWORD *v65; // [rsp+88h] [rbp-78h]
  unsigned int *v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h]
  _QWORD *v68; // [rsp+A0h] [rbp-60h]
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  _DWORD *v74; // [rsp+D0h] [rbp-30h]
  _DWORD *v75; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v77; // [rsp+F0h] [rbp-10h] BYREF
  char v78[256]; // [rsp+100h] [rbp+0h] BYREF

  inited = a1;
  v73 = a6;
  v75 = a8;
  v60 = a10;
  v68 = a11;
  v72 = a12;
  v71 = a13;
  v66 = a14;
  v63 = a16;
  v67 = a17;
  v65 = a18;
  v70 = a19;
  v74 = a20;
  v62 = a21;
  v61 = a4;
  v64 = a2;
  v59 = 0;
  memset(v58, 0, sizeof(v58));
  v69 = 256;
  DestinationString = 0;
  v77 = 0;
  if ( a2 )
  {
    if ( a1 == -1073741541 || (unsigned int)(a1 + 1073741520) <= 1 )
    {
LABEL_6:
      if ( (int)RtlQueryPackageIdentity(a2, v78, &v69, 0, 0, 0) >= 0 )
      {
LABEL_17:
        v28 = (unsigned int)inited;
        goto LABEL_58;
      }
      v24 = NtQueryInformationToken(a2, TokenSessionId, &v58[8], 4u, &v59);
      if ( v24 < 0 )
      {
        v28 = (unsigned int)v24;
LABEL_58:
        BaseSetLastNTError(v28);
        return 0;
      }
      SessionId = NtCurrentPeb()->SessionId;
      if ( *(_DWORD *)&v58[8] != (_DWORD)SessionId )
      {
        GlobalData = (ULONG *)KernelBaseGetGlobalData(SessionId, v25, v26, v27);
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 0x208u);
        EnvironmentVariableW = GetEnvironmentVariableW(L"SystemRoot", Heap, 0xEFu);
        if ( EnvironmentVariableW - 1 > 0xED )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v28 = 3221225731LL;
          goto LABEL_58;
        }
        RtlStringCchCatW(Heap, 260, L"\\system32\\csrstub.exe");
        v37 = (ULONG *)KernelBaseGetGlobalData(v34, v33, v35, v36);
        v38 = EnvironmentVariableW + 281;
        v39 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v37, 2 * v38);
        if ( !v39 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v28 = 3221225495LL;
          goto LABEL_58;
        }
        LODWORD(ReturnLength) = *a7;
        v40 = RtlStringCchPrintfW(v39, v38, L"%ws %d -P %ws", Heap, ReturnLength, *a5);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( v40 < 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v39);
LABEL_57:
          v28 = (unsigned int)v40;
          goto LABEL_58;
        }
        inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)v39);
        if ( inited < 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v39);
          goto LABEL_17;
        }
        RtlFreeUnicodeString(UnicodeString);
        *UnicodeString = DestinationString;
        *a5 = UnicodeString->Buffer;
        *v61 = 0;
        *a7 &= 0x404u;
        *a7 |= 0xC000000u;
        return 1;
      }
      goto LABEL_21;
    }
    if ( a1 == -1073741521 )
    {
      if ( !(unsigned int)BaseIsDosApplication(a9, 3221225775LL) )
        goto LABEL_22;
      goto LABEL_6;
    }
  }
LABEL_21:
  v40 = -1073741792;
  if ( inited == -1073741792 )
  {
    Upload16BitUTCData(a3);
    goto LABEL_57;
  }
LABEL_22:
  if ( inited != -1073741541 )
  {
    if ( inited != -1073741521 )
    {
      if ( inited == -1073741520 )
        goto LABEL_53;
      if ( inited != -1073741519 )
      {
        if ( inited == -1073741209 )
        {
          v42 = 4350;
        }
        else
        {
          if ( inited != -1073740760 )
            goto LABEL_17;
          v42 = 577;
        }
        goto LABEL_29;
      }
      v43 = wcslen(a3);
      *(_QWORD *)&v77 = a3;
      *((_QWORD *)&v77 + 1) = (unsigned int)(2 * v43);
      EtwEventWriteNoRegistration(UserLoaderGuid, Launch16BitApp, 1, &v77);
      if ( (*a7 & 0x2000) == 0 )
      {
        v44 = v60;
        v45 = v64;
        LODWORD(v60) = 1;
        *v44 = 1;
        v46 = CheckElevation((__int64)a3, (__int64)&v58[4]);
        if ( v46 )
        {
          v42 = v46;
LABEL_29:
          RtlSetLastWin32Error(v42);
          return 0;
        }
        if ( !(unsigned int)BaseCreateVDMEnvironment(*v68, v63, v67) )
          return 0;
        v47 = v70;
        v48 = v71;
        v49 = v72;
        v50 = (*a7 & 0x800) != 0 ? 64 : 32;
        *v70 = v50;
        while ( 1 )
        {
          v51 = BaseCheckVDM(v50, *v61, *a5, v73, v63, v48, v66, *a7, v49, v45, *(_QWORD *)v58);
          v52 = v51;
          if ( v51 >= 0 )
            break;
          BaseSetLastNTError((unsigned int)v51);
          if ( v52 == -1073740780 || *v47 != 32 || NtCurrentTeb()->LastErrorValue != 5 )
            return 0;
          *a7 |= 0x800u;
          v45 = v64;
          v50 = 128;
          *v47 = 128;
        }
        v53 = (*(unsigned __int16 *)(v48 + 238) & 7u) - 1;
        if ( (*(_WORD *)(v48 + 238) & 7) == 1 )
        {
          *v65 = 1;
          if ( !(unsigned int)BaseGetVdmConfigInfo(v53, *v66, (unsigned int)*v47, UnicodeString) )
          {
            v28 = 3221225777LL;
            goto LABEL_58;
          }
          v54 = v62;
          *v74 = 1;
          *a5 = UnicodeString->Buffer;
          *v61 = 0;
          *a7 = *a7 & 0xF7FFFFE7 | 0x8000000;
          *(_DWORD *)(v49 + 60) |= 0x40u;
        }
        else
        {
          if ( (*(_WORD *)(v48 + 238) & 7) == 2 )
          {
            v42 = 21;
            goto LABEL_29;
          }
          v54 = v62;
          if ( (*(_WORD *)(v48 + 238) & 7) == 4 )
          {
            *v65 = 4;
            *v54 = *(_QWORD *)(v48 + 88);
          }
        }
        if ( !*v54 )
        {
          v55 = v68;
          *v75 = 0;
          *v55 = *(_QWORD *)(v67 + 8);
        }
        return 1;
      }
    }
    if ( !(unsigned int)BaseIsDosApplication(a9, (unsigned int)inited) )
    {
      v42 = 193;
      goto LABEL_29;
    }
  }
LABEL_53:
  *(_DWORD *)&v58[4] = 0;
  if ( (unsigned int)IsDOSFileCorrupted(a3) )
  {
    Upload16BitUTCData(a3);
    v28 = 3221225730LL;
    goto LABEL_58;
  }
  v56 = wcslen(a3);
  *(_QWORD *)&v77 = a3;
  *((_QWORD *)&v77 + 1) = (unsigned int)(2 * v56);
  EtwEventWriteNoRegistration(UserLoaderGuid, Launch16BitApp, 1, &v77);
  Upload16BitUTCData(a3);
  RaiseInvalid16BitExeError(a9);
  return 0;
}

```

## disassembly

```asm
0x1800643a0  push    rbp
0x1800643a2  push    rbx
0x1800643a3  push    rsi
0x1800643a4  push    rdi
0x1800643a5  push    r12
0x1800643a7  push    r13
0x1800643a9  push    r14
0x1800643ab  push    r15
0x1800643ad  lea     rbp, [rsp-118h]
0x1800643b5  sub     rsp, 218h
0x1800643bc  mov     rax, cs:__security_cookie
0x1800643c3  xor     rax, rsp
0x1800643c6  mov     [rbp+150h+var_50], rax
0x1800643cd  mov     rax, [rbp+150h+arg_28]
0x1800643d4  xorps   xmm0, xmm0
0x1800643d7  mov     r13, [rbp+150h+arg_20]
0x1800643de  mov     ebx, ecx
0x1800643e0  mov     rdi, [rbp+150h+arg_30]
0x1800643e7  mov     rsi, r8
0x1800643ea  mov     r12, [rbp+150h+arg_40]
0x1800643f1  mov     r14, rdx
0x1800643f4  mov     r15, [rbp+150h+UnicodeString]
0x1800643fb  mov     ecx, 0C000012Fh
0x180064400  mov     [rbp+150h+var_188], rax
0x180064404  mov     rax, [rbp+150h+arg_38]
0x18006440b  mov     [rbp+150h+var_178], rax
0x18006440f  mov     rax, [rbp+150h+arg_48]
0x180064416  mov     [rsp+250h+var_1F0], rax
0x18006441b  mov     rax, [rbp+150h+arg_50]
0x180064422  mov     [rbp+150h+var_1B0], rax
0x180064426  mov     rax, [rbp+150h+arg_58]
0x18006442d  mov     [rbp+150h+var_190], rax
0x180064431  mov     rax, [rbp+150h+arg_60]
0x180064438  mov     [rbp+150h+var_198], rax
0x18006443c  mov     rax, [rbp+150h+arg_68]
0x180064443  mov     [rbp+150h+var_1C0], rax
0x180064447  mov     rax, [rbp+150h+arg_78]
0x18006444e  mov     [rsp+250h+var_1D8], rax
0x180064453  mov     rax, [rbp+150h+arg_80]
0x18006445a  mov     [rbp+150h+var_1B8], rax
0x18006445e  mov     rax, [rbp+150h+arg_88]
0x180064465  mov     [rbp+150h+var_1C8], rax
0x180064469  mov     rax, [rbp+150h+arg_90]
0x180064470  mov     [rbp+150h+var_1A0], rax
0x180064474  mov     rax, [rbp+150h+arg_98]
0x18006447b  mov     [rbp+150h+var_180], rax
0x18006447f  mov     rax, [rbp+150h+arg_A0]
0x180064486  mov     [rsp+250h+var_1E0], rax
0x18006448b  mov     [rsp+250h+var_1E8], r9
0x180064490  mov     [rbp+150h+var_1D0], rdx
0x180064494  mov     dword ptr [rsp+250h+var_1FC+4], 0
0x18006449c  mov     [rsp+250h+var_1F4], 0
0x1800644a4  mov     [rsp+250h+var_200], 0
0x1800644ac  mov     dword ptr [rsp+250h+var_1FC], 0
0x1800644b4  mov     [rbp+150h+var_1A8], 100h
0x1800644bc  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x1800644c0  movups  [rbp+150h+var_160], xmm0
0x1800644c4  test    rdx, rdx
0x1800644c7  jz      loc_180064764
0x1800644cd  cmp     ebx, 0C000011Bh
0x1800644d3  jz      short loc_1800644FA
0x1800644d5  lea     eax, [rbx+3FFFFED0h]
0x1800644db  cmp     eax, 1
0x1800644de  jbe     short loc_1800644FA
0x1800644e0  cmp     ebx, ecx
0x1800644e2  jnz     loc_180064764
0x1800644e8  mov     edx, ecx
0x1800644ea  mov     rcx, r12
0x1800644ed  call    BaseIsDosApplication
0x1800644f2  test    eax, eax
0x1800644f4  jz      loc_180064773
0x1800644fa  mov     [rsp+250h+var_228], 0
0x180064503  lea     r8, [rbp+150h+var_1A8]
0x180064507  xor     r9d, r9d
0x18006450a  mov     [rsp+250h+ReturnLength], 0
0x180064513  lea     rdx, [rbp+150h+var_150]
0x180064517  mov     rcx, r14
0x18006451a  call    cs:__imp_RtlQueryPackageIdentity
0x180064521  nop     dword ptr [rax+rax+00h]
0x180064526  test    eax, eax
0x180064528  jns     loc_1800646F3
0x18006452e  mov     r9d, 4; TokenInformationLength
0x180064534  lea     rax, [rsp+250h+var_1F4]
0x180064539  lea     r8, [rsp+250h+var_1FC+4]; TokenInformation
0x18006453e  mov     [rsp+250h+ReturnLength], rax; ReturnLength
0x180064543  mov     rcx, r14; TokenHandle
0x180064546  lea     edx, [r9+8]; TokenInformationClass
0x18006454a  call    cs:__imp_NtQueryInformationToken
0x180064551  nop     dword ptr [rax+rax+00h]
0x180064556  test    eax, eax
0x180064558  jns     short loc_180064561
0x18006455a  mov     ecx, eax
0x18006455c  jmp     loc_180064AB3
0x180064561  mov     rax, gs:60h
0x18006456a  mov     ecx, [rax+2C0h]
0x180064570  cmp     dword ptr [rsp+250h+var_1FC+4], ecx
0x180064574  jz      loc_180064764
0x18006457a  call    cs:__imp_KernelBaseGetGlobalData
0x180064581  nop     dword ptr [rax+rax+00h]
0x180064586  mov     rcx, gs:60h
0x18006458f  mov     r8d, 208h; Size
0x180064595  mov     edx, [rax]; Flags
0x180064597  mov     rcx, [rcx+30h]; HeapHandle
0x18006459b  call    cs:__imp_RtlAllocateHeap
0x1800645a2  nop     dword ptr [rax+rax+00h]
0x1800645a7  mov     r8d, 0EFh; nSize
0x1800645ad  lea     rcx, aSystemroot; "SystemRoot"
0x1800645b4  mov     rdx, rax; lpBuffer
0x1800645b7  mov     rbx, rax
0x1800645ba  call    cs:__imp_GetEnvironmentVariableW
0x1800645c1  nop     dword ptr [rax+rax+00h]
0x1800645c6  mov     esi, eax
0x1800645c8  lea     ecx, [rax-1]
0x1800645cb  cmp     ecx, 0EDh
0x1800645d1  ja      loc_18006473C
0x1800645d7  lea     r8, aSystem32Csrstu; "\\system32\\csrstub.exe"
0x1800645de  mov     edx, 104h
0x1800645e3  mov     rcx, rbx
0x1800645e6  call    RtlStringCchCatW
0x1800645eb  call    cs:__imp_KernelBaseGetGlobalData
0x1800645f2  nop     dword ptr [rax+rax+00h]
0x1800645f7  lea     ecx, [rsi+119h]
0x1800645fd  mov     r14d, ecx
0x180064600  lea     r8, [rcx+rcx]; Size
0x180064604  mov     rcx, gs:60h
0x18006460d  mov     edx, [rax]; Flags
0x18006460f  mov     rcx, [rcx+30h]; HeapHandle
0x180064613  call    cs:__imp_RtlAllocateHeap
0x18006461a  nop     dword ptr [rax+rax+00h]
0x18006461f  mov     rsi, rax
0x180064622  test    rax, rax
0x180064625  jnz     short loc_18006464F
0x180064627  mov     rcx, gs:60h
0x180064630  mov     r8, rbx; P
0x180064633  xor     edx, edx; Flags
0x180064635  mov     rcx, [rcx+30h]; HeapHandle
0x180064639  call    cs:__imp_RtlFreeHeap
0x180064640  nop     dword ptr [rax+rax+00h]
0x180064645  mov     ecx, 0C0000017h
0x18006464a  jmp     loc_180064AB3
0x18006464f  mov     rax, [r13+0]
0x180064653  lea     r8, aWsDPWs; "%ws %d -P %ws"
0x18006465a  mov     [rsp+250h+var_228], rax
0x18006465f  mov     r9, rbx
0x180064662  mov     eax, [rdi]
0x180064664  mov     rdx, r14
0x180064667  mov     rcx, rsi
0x18006466a  mov     dword ptr [rsp+250h+ReturnLength], eax
0x18006466e  call    RtlStringCchPrintfW
0x180064673  mov     rcx, gs:60h
0x18006467c  mov     r8, rbx; P
0x18006467f  xor     edx, edx; Flags
0x180064681  mov     r14d, eax
0x180064684  mov     rcx, [rcx+30h]; HeapHandle
0x180064688  call    cs:__imp_RtlFreeHeap
0x18006468f  nop     dword ptr [rax+rax+00h]
0x180064694  test    r14d, r14d
0x180064697  jns     short loc_1800646BC
0x180064699  mov     rcx, gs:60h
0x1800646a2  mov     r8, rsi; P
0x1800646a5  xor     edx, edx; Flags
0x1800646a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800646ab  call    cs:__imp_RtlFreeHeap
0x1800646b2  nop     dword ptr [rax+rax+00h]
0x1800646b7  jmp     loc_180064AB0
0x1800646bc  mov     rdx, rsi; SourceString
0x1800646bf  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x1800646c3  call    cs:__imp_RtlInitUnicodeStringEx
0x1800646ca  nop     dword ptr [rax+rax+00h]
0x1800646cf  mov     ebx, eax
0x1800646d1  test    eax, eax
0x1800646d3  jns     short loc_1800646FA
0x1800646d5  mov     rcx, gs:60h
0x1800646de  mov     r8, rsi; P
0x1800646e1  xor     edx, edx; Flags
0x1800646e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800646e7  call    cs:__imp_RtlFreeHeap
0x1800646ee  nop     dword ptr [rax+rax+00h]
0x1800646f3  mov     ecx, ebx
0x1800646f5  jmp     loc_180064AB3
0x1800646fa  mov     rcx, r15; UnicodeString
0x1800646fd  call    cs:__imp_RtlFreeUnicodeString
0x180064704  nop     dword ptr [rax+rax+00h]
0x180064709  movups  xmm0, xmmword ptr [rbp+150h+DestinationString.Length]
0x18006470d  movdqu  xmmword ptr [r15], xmm0
0x180064712  mov     rcx, [r15+8]
0x180064716  mov     [r13+0], rcx
0x18006471a  mov     rcx, [rsp+250h+var_1E8]
0x18006471f  mov     qword ptr [rcx], 0
0x180064726  and     dword ptr [rdi], 404h
0x18006472c  or      dword ptr [rdi], 0C000000h
0x180064732  mov     eax, 1
0x180064737  jmp     loc_180064ABA
0x18006473c  mov     rcx, gs:60h
0x180064745  mov     r8, rbx; P
0x180064748  xor     edx, edx; Flags
0x18006474a  mov     rcx, [rcx+30h]; HeapHandle
0x18006474e  call    cs:__imp_RtlFreeHeap
0x180064755  nop     dword ptr [rax+rax+00h]
0x18006475a  mov     ecx, 0C0000103h
0x18006475f  jmp     loc_180064AB3
0x180064764  mov     r14d, 0C0000020h
0x18006476a  cmp     ebx, r14d
0x18006476d  jz      loc_180064A9D
0x180064773  mov     r14d, 1
0x180064779  cmp     ebx, 0C000011Bh
0x18006477f  jz      loc_1800649FB
0x180064785  cmp     ebx, 0C000012Fh
0x18006478b  jz      loc_1800649E0
0x180064791  cmp     ebx, 0C0000130h
0x180064797  jz      loc_1800649FB
0x18006479d  cmp     ebx, 0C0000131h
0x1800647a3  jz      short loc_1800647D6
0x1800647a5  cmp     ebx, 0C0000267h
0x1800647ab  jz      short loc_1800647CF
0x1800647ad  cmp     ebx, 0C0000428h
0x1800647b3  jnz     loc_1800646F3
0x1800647b9  mov     ecx, 241h; LastError
0x1800647be  call    cs:__imp_RtlSetLastWin32Error
0x1800647c5  nop     dword ptr [rax+rax+00h]
0x1800647ca  jmp     loc_180064AB8
0x1800647cf  mov     ecx, 10FEh
0x1800647d4  jmp     short loc_1800647BE
0x1800647d6  mov     rcx, rsi; String
0x1800647d9  call    cs:__imp_wcslen
0x1800647e0  nop     dword ptr [rax+rax+00h]
0x1800647e5  lea     r9, [rbp+150h+var_160]
0x1800647e9  mov     qword ptr [rbp+150h+var_160], rsi
0x1800647ed  add     eax, eax
0x1800647ef  mov     dword ptr [rbp+150h+var_160+0Ch], 0
0x1800647f6  mov     r8d, r14d
0x1800647f9  mov     dword ptr [rbp+150h+var_160+8], eax
0x1800647fc  lea     rdx, Launch16BitApp
0x180064803  lea     rcx, UserLoaderGuid
0x18006480a  call    cs:__imp_EtwEventWriteNoRegistration
0x180064811  nop     dword ptr [rax+rax+00h]
0x180064816  test    dword ptr [rdi], 2000h
0x18006481c  jnz     loc_1800649E0
0x180064822  mov     rax, [rsp+250h+var_1F0]
0x180064827  lea     r9, [rsp+250h+var_200]
0x18006482c  mov     rbx, [rbp+150h+var_1D0]
0x180064830  lea     rdx, [rsp+250h+var_1F0]
0x180064835  mov     r8, rbx
0x180064838  mov     dword ptr [rsp+250h+var_1F0], r14d
0x18006483d  mov     rcx, rsi; __int64
0x180064840  mov     [rax], r14b
0x180064843  lea     rax, [rsp+250h+var_1FC]
0x180064848  mov     [rsp+250h+ReturnLength], rax; __int64
0x18006484d  call    CheckElevation
0x180064852  test    eax, eax
0x180064854  jz      short loc_18006485D
0x180064856  mov     ecx, eax
0x180064858  jmp     loc_1800647BE
0x18006485d  mov     rax, [rbp+150h+var_1B0]
0x180064861  mov     r8, [rbp+150h+var_1B8]
0x180064865  mov     rdx, [rsp+250h+var_1D8]
0x18006486a  mov     rcx, [rax]
0x18006486d  call    BaseCreateVDMEnvironment
0x180064872  test    eax, eax
0x180064874  jz      loc_180064AB8
0x18006487a  mov     eax, [rdi]
0x18006487c  mov     rsi, [rbp+150h+var_1A0]
0x180064880  and     eax, 800h
0x180064885  mov     r14, [rbp+150h+var_198]
0x180064889  neg     eax
0x18006488b  mov     r12, [rbp+150h+var_190]
0x18006488f  sbb     ecx, ecx
0x180064891  and     ecx, 20h
0x180064894  add     ecx, 20h ; ' '
0x180064897  mov     [rsi], ecx
0x180064899  mov     eax, [rdi]
0x18006489b  mov     r9, [rbp+150h+var_188]
0x18006489f  mov     r8, [r13+0]
0x1800648a3  mov     [rsp+250h+var_208], rbx
0x1800648a8  mov     [rsp+250h+var_210], r12
0x1800648ad  mov     [rsp+250h+var_218], eax
0x1800648b1  mov     rax, [rbp+150h+var_1C0]
0x1800648b5  mov     [rsp+250h+var_220], rax
0x1800648ba  mov     rax, [rsp+250h+var_1D8]
0x1800648bf  mov     [rsp+250h+var_228], r14
0x1800648c4  mov     [rsp+250h+ReturnLength], rax
0x1800648c9  mov     rax, [rsp+250h+var_1E8]
0x1800648ce  mov     rdx, [rax]
0x1800648d1  call    BaseCheckVDM
0x1800648d6  mov     ebx, eax
0x1800648d8  test    eax, eax
0x1800648da  jns     short loc_18006491F
0x1800648dc  mov     ecx, eax
0x1800648de  call    BaseSetLastNTError
0x1800648e3  cmp     ebx, 0C0000414h
0x1800648e9  jz      loc_180064AB8
0x1800648ef  cmp     dword ptr [rsi], 20h ; ' '
0x1800648f2  jnz     loc_180064AB8
0x1800648f8  mov     eax, gs:68h
0x180064900  cmp     eax, 5
0x180064903  jnz     loc_180064AB8
0x180064909  bts     dword ptr [rdi], 0Bh
0x18006490d  mov     eax, 80h
0x180064912  mov     rbx, [rbp+150h+var_1D0]
0x180064916  mov     ecx, eax
  ... truncated ...
```
