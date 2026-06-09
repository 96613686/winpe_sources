# BasepProcessInvalidImage

- ea: `0x18005e780`
- end: `0x18005ee4b`
- name: `BasepProcessInvalidImage`
- size: `1739`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f920`
- `0x18001d438`
- `0x1800253c0`
- `0x180031a50`
- `0x18003fb7c`
- `0x1800402f0`
- `0x180040fb0`
- `0x180056ed0`
- `0x18005e780`
- `0x18005f110`
- `0x180060dac`
- `0x18006afb0`
- `0x18007a840`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x18005eb8a`
- `ntdll!EtwEventWriteNoRegistration` at `0x18005ede7`
- `ntdll!EtwEventWriteNoRegistration` at `0x18005eb8a`
- `ntdll!EtwEventWriteNoRegistration` at `0x18005ede7`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ea67`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ea67`
- `ntdll!NtQueryInformationToken` at `0x18005e924`
- `ntdll!NtQueryInformationToken` at `0x18005e924`
- `ntdll!RtlQueryPackageIdentity` at `0x18005e8fa`
- `ntdll!RtlQueryPackageIdentity` at `0x18005e8fa`
- `ntdll!wcslen` at `0x18005eb5f`
- `ntdll!wcslen` at `0x18005edb9`
- `ntdll!wcslen` at `0x18005eb5f`
- `ntdll!wcslen` at `0x18005edb9`
- `ntdll!RtlFreeUnicodeString` at `0x18005ea95`
- `ntdll!RtlFreeUnicodeString` at `0x18005ea95`
- `ntdll!RtlSetLastWin32Error` at `0x18005eb4a`
- `ntdll!RtlSetLastWin32Error` at `0x18005eb4a`
- `ntdll!RtlFreeHeap` at `0x18005e9ef`
- `ntdll!RtlFreeHeap` at `0x18005ea38`
- `ntdll!RtlFreeHeap` at `0x18005ea55`
- `ntdll!RtlFreeHeap` at `0x18005ea85`
- `ntdll!RtlFreeHeap` at `0x18005eae0`
- `ntdll!RtlFreeHeap` at `0x18005e9ef`
- `ntdll!RtlFreeHeap` at `0x18005ea38`
- `ntdll!RtlFreeHeap` at `0x18005ea55`
- `ntdll!RtlFreeHeap` at `0x18005ea85`
- `ntdll!RtlFreeHeap` at `0x18005eae0`
- `ntdll!RtlAllocateHeap` at `0x18005e969`
- `ntdll!RtlAllocateHeap` at `0x18005e9cf`
- `ntdll!RtlAllocateHeap` at `0x18005e969`
- `ntdll!RtlAllocateHeap` at `0x18005e9cf`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e94e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e9ad`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e94e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005e9ad`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18005e982`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18005e982`

## string_xrefs

- `0x18005e999`: `\system32\csrstub.exe`

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
  __int64 v45; // rbx
  __int64 v46; // r8
  ULONG v47; // eax
  _DWORD *v48; // rsi
  __int64 v49; // r14
  __int64 v50; // r12
  __int64 v51; // rcx
  int v52; // eax
  int v53; // ebx
  __int64 v54; // rcx
  _QWORD *v55; // rcx
  _QWORD *v56; // rcx
  int v57; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  _BYTE v59[12]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v60; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE *v61; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v62; // [rsp+68h] [rbp-98h]
  _QWORD *v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h]
  _DWORD *v66; // [rsp+88h] [rbp-78h]
  unsigned int *v67; // [rsp+90h] [rbp-70h]
  __int64 v68; // [rsp+98h] [rbp-68h]
  _QWORD *v69; // [rsp+A0h] [rbp-60h]
  __int64 v70; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v71; // [rsp+B0h] [rbp-50h]
  __int64 v72; // [rsp+B8h] [rbp-48h]
  __int64 v73; // [rsp+C0h] [rbp-40h]
  __int64 v74; // [rsp+C8h] [rbp-38h]
  _DWORD *v75; // [rsp+D0h] [rbp-30h]
  _DWORD *v76; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h] BYREF
  char v79[256]; // [rsp+100h] [rbp+0h] BYREF

  inited = a1;
  v74 = a6;
  v76 = a8;
  v61 = a10;
  v69 = a11;
  v73 = a12;
  v72 = a13;
  v67 = a14;
  v64 = a16;
  v68 = a17;
  v66 = a18;
  v71 = a19;
  v75 = a20;
  v63 = a21;
  v62 = a4;
  v65 = (__int64)a2;
  v60 = 0;
  memset(v59, 0, sizeof(v59));
  v70 = 256;
  DestinationString = 0;
  v78 = 0;
  if ( a2 )
  {
    if ( a1 == -1073741541 || (unsigned int)(a1 + 1073741520) <= 1 )
    {
LABEL_6:
      if ( (int)RtlQueryPackageIdentity(a2, v79, &v70, 0, 0, 0) >= 0 )
      {
LABEL_17:
        v28 = (unsigned int)inited;
        goto LABEL_58;
      }
      v24 = NtQueryInformationToken(a2, TokenSessionId, &v59[8], 4u, &v60);
      if ( v24 < 0 )
      {
        v28 = (unsigned int)v24;
LABEL_58:
        BaseSetLastNTError(v28);
        return 0;
      }
      SessionId = NtCurrentPeb()->SessionId;
      if ( *(_DWORD *)&v59[8] != (_DWORD)SessionId )
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
        *v62 = 0;
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
      *(_QWORD *)&v78 = a3;
      *((_QWORD *)&v78 + 1) = (unsigned int)(2 * v43);
      EtwEventWriteNoRegistration(UserLoaderGuid, Launch16BitApp, 1, &v78);
      if ( (*a7 & 0x2000) == 0 )
      {
        v44 = v61;
        v45 = v65;
        v46 = v65;
        LODWORD(v61) = 1;
        *v44 = 1;
        v47 = CheckElevation(a3, (__int64)&v61, v46, (__int64)v59, (__int64)&v59[4]);
        if ( v47 )
        {
          v42 = v47;
LABEL_29:
          RtlSetLastWin32Error(v42);
          return 0;
        }
        if ( !(unsigned int)BaseCreateVDMEnvironment(*v69, v64, v68) )
          return 0;
        v48 = v71;
        v49 = v72;
        v50 = v73;
        v51 = (*a7 & 0x800) != 0 ? 64 : 32;
        *v71 = v51;
        while ( 1 )
        {
          v52 = BaseCheckVDM(v51, *v62, *a5, v74, v64, v49, v67, *a7, v50, v45, *(_QWORD *)v59);
          v53 = v52;
          if ( v52 >= 0 )
            break;
          BaseSetLastNTError((unsigned int)v52);
          if ( v53 == -1073740780 || *v48 != 32 || NtCurrentTeb()->LastErrorValue != 5 )
            return 0;
          *a7 |= 0x800u;
          v45 = v65;
          v51 = 128;
          *v48 = 128;
        }
        v54 = (*(unsigned __int16 *)(v49 + 238) & 7u) - 1;
        if ( (*(_WORD *)(v49 + 238) & 7) == 1 )
        {
          *v66 = 1;
          if ( !(unsigned int)BaseGetVdmConfigInfo(v54, *v67, (unsigned int)*v48, UnicodeString) )
          {
            v28 = 3221225777LL;
            goto LABEL_58;
          }
          v55 = v63;
          *v75 = 1;
          *a5 = UnicodeString->Buffer;
          *v62 = 0;
          *a7 = *a7 & 0xF7FFFFE7 | 0x8000000;
          *(_DWORD *)(v50 + 60) |= 0x40u;
        }
        else
        {
          if ( (*(_WORD *)(v49 + 238) & 7) == 2 )
          {
            v42 = 21;
            goto LABEL_29;
          }
          v55 = v63;
          if ( (*(_WORD *)(v49 + 238) & 7) == 4 )
          {
            *v66 = 4;
            *v55 = *(_QWORD *)(v49 + 88);
          }
        }
        if ( !*v55 )
        {
          v56 = v69;
          *v76 = 0;
          *v56 = *(_QWORD *)(v68 + 8);
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
  *(_DWORD *)&v59[4] = 0;
  *(_DWORD *)v59 = 0;
  if ( (unsigned int)IsDOSFileCorrupted(a3) )
  {
    Upload16BitUTCData(a3);
    v28 = 3221225730LL;
    goto LABEL_58;
  }
  v57 = wcslen(a3);
  *(_QWORD *)&v78 = a3;
  *((_QWORD *)&v78 + 1) = (unsigned int)(2 * v57);
  EtwEventWriteNoRegistration(UserLoaderGuid, Launch16BitApp, 1, &v78);
  Upload16BitUTCData(a3);
  RaiseInvalid16BitExeError(a9);
  return 0;
}

```

## disassembly

```asm
0x18005e780  push    rbp
0x18005e782  push    rbx
0x18005e783  push    rsi
0x18005e784  push    rdi
0x18005e785  push    r12
0x18005e787  push    r13
0x18005e789  push    r14
0x18005e78b  push    r15
0x18005e78d  lea     rbp, [rsp-118h]
0x18005e795  sub     rsp, 218h
0x18005e79c  mov     rax, cs:__security_cookie
0x18005e7a3  xor     rax, rsp
0x18005e7a6  mov     [rbp+150h+var_50], rax
0x18005e7ad  mov     rax, [rbp+150h+arg_28]
0x18005e7b4  xorps   xmm0, xmm0
0x18005e7b7  mov     r13, [rbp+150h+arg_20]
0x18005e7be  mov     ebx, ecx
0x18005e7c0  mov     rdi, [rbp+150h+arg_30]
0x18005e7c7  mov     rsi, r8
0x18005e7ca  mov     r12, [rbp+150h+arg_40]
0x18005e7d1  mov     r14, rdx
0x18005e7d4  mov     r15, [rbp+150h+UnicodeString]
0x18005e7db  mov     ecx, 0C000012Fh
0x18005e7e0  mov     [rbp+150h+var_188], rax
0x18005e7e4  mov     rax, [rbp+150h+arg_38]
0x18005e7eb  mov     [rbp+150h+var_178], rax
0x18005e7ef  mov     rax, [rbp+150h+arg_48]
0x18005e7f6  mov     [rsp+250h+var_1F0], rax
0x18005e7fb  mov     rax, [rbp+150h+arg_50]
0x18005e802  mov     [rbp+150h+var_1B0], rax
0x18005e806  mov     rax, [rbp+150h+arg_58]
0x18005e80d  mov     [rbp+150h+var_190], rax
0x18005e811  mov     rax, [rbp+150h+arg_60]
0x18005e818  mov     [rbp+150h+var_198], rax
0x18005e81c  mov     rax, [rbp+150h+arg_68]
0x18005e823  mov     [rbp+150h+var_1C0], rax
0x18005e827  mov     rax, [rbp+150h+arg_78]
0x18005e82e  mov     [rsp+250h+var_1D8], rax
0x18005e833  mov     rax, [rbp+150h+arg_80]
0x18005e83a  mov     [rbp+150h+var_1B8], rax
0x18005e83e  mov     rax, [rbp+150h+arg_88]
0x18005e845  mov     [rbp+150h+var_1C8], rax
0x18005e849  mov     rax, [rbp+150h+arg_90]
0x18005e850  mov     [rbp+150h+var_1A0], rax
0x18005e854  mov     rax, [rbp+150h+arg_98]
0x18005e85b  mov     [rbp+150h+var_180], rax
0x18005e85f  mov     rax, [rbp+150h+arg_A0]
0x18005e866  mov     [rsp+250h+var_1E0], rax
0x18005e86b  mov     [rsp+250h+var_1E8], r9
0x18005e870  mov     [rbp+150h+var_1D0], rdx
0x18005e874  mov     dword ptr [rsp+250h+var_1FC+4], 0
0x18005e87c  mov     [rsp+250h+var_1F4], 0
0x18005e884  mov     [rsp+250h+var_200], 0
0x18005e88c  mov     dword ptr [rsp+250h+var_1FC], 0
0x18005e894  mov     [rbp+150h+var_1A8], 100h
0x18005e89c  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x18005e8a0  movups  [rbp+150h+var_160], xmm0
0x18005e8a4  test    rdx, rdx
0x18005e8a7  jz      loc_18005EAF0
0x18005e8ad  cmp     ebx, 0C000011Bh
0x18005e8b3  jz      short loc_18005E8DA
0x18005e8b5  lea     eax, [rbx+3FFFFED0h]
0x18005e8bb  cmp     eax, 1
0x18005e8be  jbe     short loc_18005E8DA
0x18005e8c0  cmp     ebx, ecx
0x18005e8c2  jnz     loc_18005EAF0
0x18005e8c8  mov     edx, ecx
0x18005e8ca  mov     rcx, r12
0x18005e8cd  call    BaseIsDosApplication
0x18005e8d2  test    eax, eax
0x18005e8d4  jz      loc_18005EAFF
0x18005e8da  mov     [rsp+250h+var_228], 0
0x18005e8e3  lea     r8, [rbp+150h+var_1A8]
0x18005e8e7  xor     r9d, r9d
0x18005e8ea  mov     [rsp+250h+ReturnLength], 0
0x18005e8f3  lea     rdx, [rbp+150h+var_150]
0x18005e8f7  mov     rcx, r14
0x18005e8fa  call    cs:__imp_RtlQueryPackageIdentity
0x18005e900  test    eax, eax
0x18005e902  jns     loc_18005EA8B
0x18005e908  mov     r9d, 4; TokenInformationLength
0x18005e90e  lea     rax, [rsp+250h+var_1F4]
0x18005e913  lea     r8, [rsp+250h+var_1FC+4]; TokenInformation
0x18005e918  mov     [rsp+250h+ReturnLength], rax; ReturnLength
0x18005e91d  mov     rcx, r14; TokenHandle
0x18005e920  lea     edx, [r9+8]; TokenInformationClass
0x18005e924  call    cs:__imp_NtQueryInformationToken
0x18005e92a  test    eax, eax
0x18005e92c  jns     short loc_18005E935
0x18005e92e  mov     ecx, eax
0x18005e930  jmp     loc_18005EE21
0x18005e935  mov     rax, gs:60h
0x18005e93e  mov     ecx, [rax+2C0h]
0x18005e944  cmp     dword ptr [rsp+250h+var_1FC+4], ecx
0x18005e948  jz      loc_18005EAF0
0x18005e94e  call    cs:__imp_KernelBaseGetGlobalData
0x18005e954  mov     rcx, gs:60h
0x18005e95d  mov     r8d, 208h; Size
0x18005e963  mov     edx, [rax]; Flags
0x18005e965  mov     rcx, [rcx+30h]; HeapHandle
0x18005e969  call    cs:__imp_RtlAllocateHeap
0x18005e96f  mov     r8d, 0EFh; nSize
0x18005e975  lea     rcx, aSystemroot; "SystemRoot"
0x18005e97c  mov     rdx, rax; lpBuffer
0x18005e97f  mov     rbx, rax
0x18005e982  call    cs:__imp_GetEnvironmentVariableW
0x18005e988  mov     esi, eax
0x18005e98a  lea     ecx, [rax-1]
0x18005e98d  cmp     ecx, 0EDh
0x18005e993  ja      loc_18005EACE
0x18005e999  lea     r8, aSystem32Csrstu; "\\system32\\csrstub.exe"
0x18005e9a0  mov     edx, 104h
0x18005e9a5  mov     rcx, rbx
0x18005e9a8  call    RtlStringCchCatW
0x18005e9ad  call    cs:__imp_KernelBaseGetGlobalData
0x18005e9b3  lea     ecx, [rsi+119h]
0x18005e9b9  mov     r14d, ecx
0x18005e9bc  lea     r8, [rcx+rcx]; Size
0x18005e9c0  mov     rcx, gs:60h
0x18005e9c9  mov     edx, [rax]; Flags
0x18005e9cb  mov     rcx, [rcx+30h]; HeapHandle
0x18005e9cf  call    cs:__imp_RtlAllocateHeap
0x18005e9d5  mov     rsi, rax
0x18005e9d8  test    rax, rax
0x18005e9db  jnz     short loc_18005E9FF
0x18005e9dd  mov     rcx, gs:60h
0x18005e9e6  mov     r8, rbx; P
0x18005e9e9  xor     edx, edx; Flags
0x18005e9eb  mov     rcx, [rcx+30h]; HeapHandle
0x18005e9ef  call    cs:__imp_RtlFreeHeap
0x18005e9f5  mov     ecx, 0C0000017h
0x18005e9fa  jmp     loc_18005EE21
0x18005e9ff  mov     rax, [r13+0]
0x18005ea03  lea     r8, aWsDPWs; "%ws %d -P %ws"
0x18005ea0a  mov     [rsp+250h+var_228], rax
0x18005ea0f  mov     r9, rbx
0x18005ea12  mov     eax, [rdi]
0x18005ea14  mov     rdx, r14
0x18005ea17  mov     rcx, rsi
0x18005ea1a  mov     dword ptr [rsp+250h+ReturnLength], eax
0x18005ea1e  call    RtlStringCchPrintfW
0x18005ea23  mov     rcx, gs:60h
0x18005ea2c  mov     r8, rbx; P
0x18005ea2f  xor     edx, edx; Flags
0x18005ea31  mov     r14d, eax
0x18005ea34  mov     rcx, [rcx+30h]; HeapHandle
0x18005ea38  call    cs:__imp_RtlFreeHeap
0x18005ea3e  test    r14d, r14d
0x18005ea41  jns     short loc_18005EA60
0x18005ea43  mov     rcx, gs:60h
0x18005ea4c  mov     r8, rsi; P
0x18005ea4f  xor     edx, edx; Flags
0x18005ea51  mov     rcx, [rcx+30h]; HeapHandle
0x18005ea55  call    cs:__imp_RtlFreeHeap
0x18005ea5b  jmp     loc_18005EE1E
0x18005ea60  mov     rdx, rsi; SourceString
0x18005ea63  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x18005ea67  call    cs:__imp_RtlInitUnicodeStringEx
0x18005ea6d  mov     ebx, eax
0x18005ea6f  test    eax, eax
0x18005ea71  jns     short loc_18005EA92
0x18005ea73  mov     rcx, gs:60h
0x18005ea7c  mov     r8, rsi; P
0x18005ea7f  xor     edx, edx; Flags
0x18005ea81  mov     rcx, [rcx+30h]; HeapHandle
0x18005ea85  call    cs:__imp_RtlFreeHeap
0x18005ea8b  mov     ecx, ebx
0x18005ea8d  jmp     loc_18005EE21
0x18005ea92  mov     rcx, r15; UnicodeString
0x18005ea95  call    cs:__imp_RtlFreeUnicodeString
0x18005ea9b  movups  xmm0, xmmword ptr [rbp+150h+DestinationString.Length]
0x18005ea9f  movdqu  xmmword ptr [r15], xmm0
0x18005eaa4  mov     rcx, [r15+8]
0x18005eaa8  mov     [r13+0], rcx
0x18005eaac  mov     rcx, [rsp+250h+var_1E8]
0x18005eab1  mov     qword ptr [rcx], 0
0x18005eab8  and     dword ptr [rdi], 404h
0x18005eabe  or      dword ptr [rdi], 0C000000h
0x18005eac4  mov     eax, 1
0x18005eac9  jmp     loc_18005EE28
0x18005eace  mov     rcx, gs:60h
0x18005ead7  mov     r8, rbx; P
0x18005eada  xor     edx, edx; Flags
0x18005eadc  mov     rcx, [rcx+30h]; HeapHandle
0x18005eae0  call    cs:__imp_RtlFreeHeap
0x18005eae6  mov     ecx, 0C0000103h
0x18005eaeb  jmp     loc_18005EE21
0x18005eaf0  mov     r14d, 0C0000020h
0x18005eaf6  cmp     ebx, r14d
0x18005eaf9  jz      loc_18005EE0B
0x18005eaff  mov     r14d, 1
0x18005eb05  cmp     ebx, 0C000011Bh
0x18005eb0b  jz      loc_18005ED75
0x18005eb11  cmp     ebx, 0C000012Fh
0x18005eb17  jz      loc_18005ED5A
0x18005eb1d  cmp     ebx, 0C0000130h
0x18005eb23  jz      loc_18005ED75
0x18005eb29  cmp     ebx, 0C0000131h
0x18005eb2f  jz      short loc_18005EB5C
0x18005eb31  cmp     ebx, 0C0000267h
0x18005eb37  jz      short loc_18005EB55
0x18005eb39  cmp     ebx, 0C0000428h
0x18005eb3f  jnz     loc_18005EA8B
0x18005eb45  mov     ecx, 241h; LastError
0x18005eb4a  call    cs:__imp_RtlSetLastWin32Error
0x18005eb50  jmp     loc_18005EE26
0x18005eb55  mov     ecx, 10FEh
0x18005eb5a  jmp     short loc_18005EB4A
0x18005eb5c  mov     rcx, rsi; String
0x18005eb5f  call    cs:__imp_wcslen
0x18005eb65  lea     r9, [rbp+150h+var_160]
0x18005eb69  mov     qword ptr [rbp+150h+var_160], rsi
0x18005eb6d  add     eax, eax
0x18005eb6f  mov     dword ptr [rbp+150h+var_160+0Ch], 0
0x18005eb76  mov     r8d, r14d
0x18005eb79  mov     dword ptr [rbp+150h+var_160+8], eax
0x18005eb7c  lea     rdx, Launch16BitApp
0x18005eb83  lea     rcx, UserLoaderGuid
0x18005eb8a  call    cs:__imp_EtwEventWriteNoRegistration
0x18005eb90  test    dword ptr [rdi], 2000h
0x18005eb96  jnz     loc_18005ED5A
0x18005eb9c  mov     rax, [rsp+250h+var_1F0]
0x18005eba1  lea     r9, [rsp+250h+var_200]
0x18005eba6  mov     rbx, [rbp+150h+var_1D0]
0x18005ebaa  lea     rdx, [rsp+250h+var_1F0]
0x18005ebaf  mov     r8, rbx
0x18005ebb2  mov     dword ptr [rsp+250h+var_1F0], r14d
0x18005ebb7  mov     rcx, rsi; __int64
0x18005ebba  mov     [rax], r14b
0x18005ebbd  lea     rax, [rsp+250h+var_1FC]
0x18005ebc2  mov     [rsp+250h+ReturnLength], rax; __int64
0x18005ebc7  call    CheckElevation
0x18005ebcc  test    eax, eax
0x18005ebce  jz      short loc_18005EBD7
0x18005ebd0  mov     ecx, eax
0x18005ebd2  jmp     loc_18005EB4A
0x18005ebd7  mov     rax, [rbp+150h+var_1B0]
0x18005ebdb  mov     r8, [rbp+150h+var_1B8]
0x18005ebdf  mov     rdx, [rsp+250h+var_1D8]
0x18005ebe4  mov     rcx, [rax]
0x18005ebe7  call    BaseCreateVDMEnvironment
0x18005ebec  test    eax, eax
0x18005ebee  jz      loc_18005EE26
0x18005ebf4  mov     eax, [rdi]
0x18005ebf6  mov     rsi, [rbp+150h+var_1A0]
0x18005ebfa  and     eax, 800h
0x18005ebff  mov     r14, [rbp+150h+var_198]
0x18005ec03  neg     eax
0x18005ec05  mov     r12, [rbp+150h+var_190]
0x18005ec09  sbb     ecx, ecx
0x18005ec0b  and     ecx, 20h
0x18005ec0e  add     ecx, 20h ; ' '
0x18005ec11  mov     [rsi], ecx
0x18005ec13  mov     eax, [rdi]
0x18005ec15  mov     r9, [rbp+150h+var_188]
0x18005ec19  mov     r8, [r13+0]
0x18005ec1d  mov     [rsp+250h+var_208], rbx
0x18005ec22  mov     [rsp+250h+var_210], r12
0x18005ec27  mov     [rsp+250h+var_218], eax
0x18005ec2b  mov     rax, [rbp+150h+var_1C0]
0x18005ec2f  mov     [rsp+250h+var_220], rax
0x18005ec34  mov     rax, [rsp+250h+var_1D8]
0x18005ec39  mov     [rsp+250h+var_228], r14
0x18005ec3e  mov     [rsp+250h+ReturnLength], rax
0x18005ec43  mov     rax, [rsp+250h+var_1E8]
0x18005ec48  mov     rdx, [rax]
0x18005ec4b  call    BaseCheckVDM
0x18005ec50  mov     ebx, eax
0x18005ec52  test    eax, eax
0x18005ec54  jns     short loc_18005EC99
0x18005ec56  mov     ecx, eax
0x18005ec58  call    BaseSetLastNTError
0x18005ec5d  cmp     ebx, 0C0000414h
0x18005ec63  jz      loc_18005EE26
0x18005ec69  cmp     dword ptr [rsi], 20h ; ' '
0x18005ec6c  jnz     loc_18005EE26
0x18005ec72  mov     eax, gs:68h
0x18005ec7a  cmp     eax, 5
0x18005ec7d  jnz     loc_18005EE26
0x18005ec83  bts     dword ptr [rdi], 0Bh
0x18005ec87  mov     eax, 80h
0x18005ec8c  mov     rbx, [rbp+150h+var_1D0]
0x18005ec90  mov     ecx, eax
0x18005ec92  mov     [rsi], eax
0x18005ec94  jmp     loc_18005EC13
0x18005ec99  movzx   ecx, word ptr [r14+0EEh]
0x18005eca1  and     ecx, 7
0x18005eca4  sub     ecx, 1
0x18005eca7  jz      short loc_18005ECD5
0x18005eca9  sub     ecx, 1
0x18005ecac  jz      short loc_18005ECCB
0x18005ecae  cmp     ecx, 2
0x18005ecb1  mov     rcx, [rsp+250h+var_1E0]
0x18005ecb6  jnz     short loc_18005ED32
0x18005ecb8  mov     rax, [rbp+150h+var_1C8]
0x18005ecbc  mov     dword ptr [rax], 4
0x18005ecc2  mov     rax, [r14+58h]
0x18005ecc6  mov     [rcx], rax
0x18005ecc9  jmp     short loc_18005ED32
0x18005eccb  mov     ecx, 15h
  ... truncated ...
```
