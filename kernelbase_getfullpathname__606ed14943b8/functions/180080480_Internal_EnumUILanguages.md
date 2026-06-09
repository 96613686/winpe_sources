# Internal_EnumUILanguages

- ea: `0x180080480`
- end: `0x180080e1b`
- name: `Internal_EnumUILanguages`
- size: `2459`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007ef34`
- `0x180080460`

## callees

- `0x18001cd34`
- `0x180076cd0`
- `0x18007a6f0`
- `0x180080340`
- `0x180080394`
- `0x180080480`
- `0x180080e30`
- `0x18008102c`
- `0x1800810a0`
- `0x1801369c9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800809f9`
- `ntdll!RtlInitUnicodeString` at `0x180080c61`
- `ntdll!RtlInitUnicodeString` at `0x1800809f9`
- `ntdll!RtlInitUnicodeString` at `0x180080c61`
- `ntdll!RtlNtStatusToDosError` at `0x180080b85`
- `ntdll!RtlNtStatusToDosError` at `0x180080dc9`
- `ntdll!RtlNtStatusToDosError` at `0x180080b85`
- `ntdll!RtlNtStatusToDosError` at `0x180080dc9`
- `ntdll!RtlpLoadUserUIByPolicy` at `0x1800806ac`
- `ntdll!RtlpLoadUserUIByPolicy` at `0x1800806ac`
- `ntdll!RtlpLoadMachineUIByPolicy` at `0x180080660`
- `ntdll!RtlpLoadMachineUIByPolicy` at `0x180080660`
- `ntdll!RtlpGetLCIDFromLangInfoNode` at `0x18008088f`
- `ntdll!RtlpGetLCIDFromLangInfoNode` at `0x18008088f`
- `ntdll!qsort` at `0x180080541`
- `ntdll!qsort` at `0x180080541`
- `ntdll!RtlpCreateProcessRegistryInfo` at `0x18008093c`
- `ntdll!RtlpCreateProcessRegistryInfo` at `0x18008093c`
- `ntdll!RtlLCIDToCultureName` at `0x18008075c`
- `ntdll!RtlLCIDToCultureName` at `0x180080d59`
- `ntdll!RtlLCIDToCultureName` at `0x18008075c`
- `ntdll!RtlLCIDToCultureName` at `0x180080d59`
- `ntdll!RtlpGetNameFromLangInfoNode` at `0x180080867`
- `ntdll!RtlpGetNameFromLangInfoNode` at `0x180080867`
- `ntdll!NtQueryInstallUILanguage` at `0x180080702`
- `ntdll!NtQueryInstallUILanguage` at `0x180080702`
- `ntdll!RtlpMuiFreeLangRegistryInfo` at `0x1800809a1`
- `ntdll!RtlpMuiFreeLangRegistryInfo` at `0x1800809a1`
- `ntdll!RtlpInitializeLangRegistryInfo` at `0x180080623`
- `ntdll!RtlpInitializeLangRegistryInfo` at `0x180080623`
- `ntdll!RtlpIsQualifiedLanguage` at `0x1800808bb`
- `ntdll!RtlpIsQualifiedLanguage` at `0x1800808bb`
- `ntdll!RtlCultureNameToLCID` at `0x180080a0e`
- `ntdll!RtlCultureNameToLCID` at `0x180080a0e`
- `ntdll!RtlFreeHeap` at `0x180080580`
- `ntdll!RtlFreeHeap` at `0x1800805ab`
- `ntdll!RtlFreeHeap` at `0x18008068f`
- `ntdll!RtlFreeHeap` at `0x1800806dd`
- `ntdll!RtlFreeHeap` at `0x180080b4f`
- `ntdll!RtlFreeHeap` at `0x180080bfd`
- `ntdll!RtlFreeHeap` at `0x180080d17`
- `ntdll!RtlFreeHeap` at `0x180080dab`
- `ntdll!RtlFreeHeap` at `0x180080580`
- `ntdll!RtlFreeHeap` at `0x1800805ab`
- `ntdll!RtlFreeHeap` at `0x18008068f`
- `ntdll!RtlFreeHeap` at `0x1800806dd`
- `ntdll!RtlFreeHeap` at `0x180080b4f`
- `ntdll!RtlFreeHeap` at `0x180080bfd`
- `ntdll!RtlFreeHeap` at `0x180080d17`
- `ntdll!RtlFreeHeap` at `0x180080dab`
- `ntdll!RtlAllocateHeap` at `0x1800807b5`
- `ntdll!RtlAllocateHeap` at `0x1800808f9`
- `ntdll!RtlAllocateHeap` at `0x1800807b5`
- `ntdll!RtlAllocateHeap` at `0x1800808f9`

## pseudocode

```c
__int64 __fastcall Internal_EnumUILanguages(__int64 (__fastcall *a1)(PVOID, __int64), int a2, __int64 a3, int a4)
{
  unsigned int v4; // r15d
  int v5; // r14d
  int v9; // edi
  ULONG v10; // ecx
  unsigned int v12; // r12d
  _QWORD *v13; // r14
  unsigned int j; // edi
  void *v15; // r8
  unsigned int v16; // r12d
  int v17; // ecx
  unsigned int v18; // ebx
  NTSTATUS v19; // eax
  int v20; // eax
  LANGID SystemDefaultUILanguage; // cx
  int v22; // edi
  WCHAR *v23; // rcx
  bool v24; // zf
  PVOID Heap; // rsi
  unsigned int i; // r14d
  __int64 v27; // r12
  _WORD *v28; // r12
  __int64 v29; // r8
  PVOID v30; // rax
  WCHAR *v31; // r14
  int v32; // eax
  unsigned __int16 v33; // ax
  __int64 v34; // rdx
  unsigned int v35; // eax
  UINT CodePageFromLocale; // eax
  PVOID v37; // rdi
  int v38; // r14d
  PWSTR v39; // r14
  UINT v40; // eax
  WCHAR *v41; // rdx
  __int64 v42; // rdx
  PVOID v43; // rsi
  int v44; // r14d
  __int64 v45; // rdx
  WCHAR *Buffer; // rcx
  int v47; // eax
  UINT v48; // eax
  PVOID v49; // r14
  ULONG v50; // eax
  LANGID LanguageId; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v54; // [rsp+68h] [rbp-98h] BYREF
  PVOID v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+94h] [rbp-6Ch]
  __int128 v60; // [rsp+98h] [rbp-68h] BYREF
  __int64 v61; // [rsp+A8h] [rbp-58h]
  WCHAR WideCharStr[264]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v63[176]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v64[176]; // [rsp+370h] [rbp+270h] BYREF

  v4 = 0;
  v58 = a4;
  v61 = a3;
  LanguageId = 0;
  v54 = 0;
  v5 = a4;
  v56 = 0;
  v53 = 0;
  DestinationString = 0;
  v60 = 0;
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_7;
  }
  if ( (a2 & 0xFFFFFF03) != 0
    || (v9 = a2 & 0xC, v9 == 12)
    || (a2 & 0x10) != 0 && ((a2 & 0x20) != 0 || (a2 & 0x40) != 0)
    || (a2 & 0x60) == 0x60 )
  {
    v10 = 1004;
LABEL_7:
    SetLastError_0(v10);
    return 0;
  }
  if ( !gpSysLocHashN )
    SetupSystemLocaleHashNode(0);
  v17 = a2 | 4;
  if ( v9 )
    v17 = a2;
  v18 = v17 | 0x20;
  if ( (v17 & 0x70) != 0 )
    v18 = v17;
  if ( (v18 & 0x80u) == 0 )
    v19 = RtlpCreateProcessRegistryInfo(&v53);
  else
    v19 = RtlpInitializeLangRegistryInfo(&v53);
  if ( v19 < 0 )
  {
    v10 = RtlNtStatusToDosError(v19);
    goto LABEL_7;
  }
  v16 = 1;
  v59 = 1;
  if ( (v18 & 0x40) != 0 )
  {
    P = 0;
    v20 = RtlpLoadMachineUIByPolicy(0, v53, &P);
    if ( P )
    {
      if ( !v20 )
        goto LABEL_75;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      P = 0;
    }
    if ( (unsigned int)RtlpLoadUserUIByPolicy(0, v53, &P) )
    {
LABEL_30:
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( (_BYTE)v4 == 1 )
        goto LABEL_14;
      v4 = 0;
      goto LABEL_34;
    }
    if ( !P )
    {
LABEL_34:
      v18 |= 0x20u;
      goto LABEL_35;
    }
LABEL_75:
    LOBYTE(v4) = 1;
    v34 = 28LL * *(__int16 *)(*((_QWORD *)P + 3) + 4LL);
    v35 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 24) + 16LL) + v34 + 4);
    LanguageId = v35;
    if ( !(_WORD)v35 )
      goto LABEL_30;
    if ( (v18 & 4) != 0 )
    {
      if ( (_WORD)v35 == 5120 )
      {
        LOWORD(v35) = 4096;
        LanguageId = 4096;
      }
      if ( (unsigned int)NlsConvertIntegerToString((unsigned __int16)v35, 16, 4, (unsigned int)WideCharStr, 260) )
        goto LABEL_30;
      if ( !v5 )
      {
        v55 = 0;
        CodePageFromLocale = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !CodePageFromLocale || !(unsigned int)NlsEnumUnicodeToAnsi(CodePageFromLocale, WideCharStr) )
          return v16;
        v37 = v55;
        v38 = a1(v55, a3);
        if ( v37 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
        if ( v38 != 1 )
          return v16;
        v5 = v58;
        goto LABEL_30;
      }
      Buffer = WideCharStr;
    }
    else
    {
      if ( (_WORD)v35 == 4096 )
      {
        v45 = *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 24) + 16LL) + v34 + 6);
        if ( (__int16)v45 <= 0 )
          goto LABEL_30;
        RtlInitUnicodeString(
          &DestinationString,
          (PCWSTR)(*(_QWORD *)(*(_QWORD *)(v53 + 32) + 24LL)
                 + 2LL * *(__int16 *)(*(_QWORD *)(*(_QWORD *)(v53 + 32) + 16LL) + 2 * v45)));
      }
      else
      {
        DestinationString.Buffer = (PWSTR)v63;
        DestinationString.MaximumLength = 170;
        if ( !(unsigned __int8)RtlLCIDToCultureName(v35, &DestinationString) )
          goto LABEL_30;
      }
      if ( !v5 )
      {
        v47 = NlsDispatchAnsiEnumProc(*(unsigned int *)gpSysLocHashN, a1, v18, DestinationString.Buffer, 0, 0, 0, a3, 4);
LABEL_103:
        if ( v47 != 1 )
          return v16;
        goto LABEL_30;
      }
      Buffer = DestinationString.Buffer;
    }
    v47 = a1(Buffer, a3);
    goto LABEL_103;
  }
LABEL_35:
  if ( (NtQueryInstallUILanguage(&LanguageId) & 0xC0000000) == 0xC0000000 )
  {
    SystemDefaultUILanguage = GetSystemDefaultUILanguage();
    LanguageId = SystemDefaultUILanguage;
  }
  else
  {
    SystemDefaultUILanguage = LanguageId;
  }
  if ( ((SystemDefaultUILanguage - 4096) & 0xFBFF) != 0 )
  {
    v22 = v18 & 4;
    if ( (v18 & 4) != 0 )
    {
      if ( !(unsigned int)NlsConvertIntegerToString(SystemDefaultUILanguage, 16, 4, (unsigned int)WideCharStr, 260) )
      {
        if ( v5 )
        {
          v23 = WideCharStr;
          goto LABEL_42;
        }
        v55 = 0;
        v40 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !v40 )
          return v16;
        v41 = WideCharStr;
LABEL_91:
        if ( !(unsigned int)NlsEnumUnicodeToAnsi(v40, v41) )
          return v16;
        v42 = a3;
        v43 = v55;
        v44 = a1(v55, v42);
        if ( v43 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
        v24 = v44 == 1;
        goto LABEL_43;
      }
    }
    else
    {
      DestinationString.Buffer = (PWSTR)v63;
      DestinationString.MaximumLength = 170;
      if ( (unsigned __int8)RtlLCIDToCultureName(SystemDefaultUILanguage, &DestinationString) )
      {
        if ( v5 )
        {
          v23 = DestinationString.Buffer;
LABEL_42:
          v24 = (unsigned int)a1(v23, a3) == 1;
LABEL_43:
          if ( !v24 )
            return v16;
          goto LABEL_44;
        }
        v39 = DestinationString.Buffer;
        v55 = 0;
        v40 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
        if ( !v40 )
          return v16;
        v41 = v39;
        goto LABEL_91;
      }
    }
  }
  else
  {
    v22 = v18 & 4;
  }
  WideCharStr[0] = 0;
LABEL_44:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8LL * *(unsigned __int16 *)(*(_QWORD *)(v53 + 24) + 6LL));
  if ( !Heap )
  {
    v50 = RtlNtStatusToDosError(-1073741801);
    SetLastError_0(v50);
    v16 = 0;
    goto LABEL_14;
  }
  for ( i = 0; ; ++i )
  {
    v27 = *(_QWORD *)(v53 + 24);
    if ( i >= *(unsigned __int16 *)(v27 + 6) )
    {
      qsort(Heap, v4, 8u, QsortStringcompareFunc);
      v12 = 0;
      if ( !v4 )
        goto LABEL_9;
      while ( 1 )
      {
        v31 = (WCHAR *)*((_QWORD *)Heap + v12);
        if ( v22 )
        {
          RtlInitUnicodeString(&DestinationString, *((PCWSTR *)Heap + v12));
          if ( !(unsigned __int8)RtlCultureNameToLCID(&DestinationString, &v56) )
            goto LABEL_67;
          v33 = v56;
          if ( v56 == 5120 )
          {
            v33 = 4096;
            v56 = 4096;
          }
          if ( (unsigned int)NlsConvertIntegerToString(v33, 16, 4, (unsigned int)WideCharStr, 260) )
            goto LABEL_67;
          v31 = WideCharStr;
        }
        if ( v58 )
        {
          v32 = a1(v31, v61);
        }
        else
        {
          v55 = 0;
          v48 = NlsGetCodePageFromLocale(*(unsigned int *)gpSysLocHashN, v18);
          if ( !v48 || !(unsigned int)NlsEnumUnicodeToAnsi(v48, v31) )
          {
LABEL_68:
            v13 = Heap;
            j = 0;
            goto LABEL_10;
          }
          v49 = v55;
          v32 = a1(v55, v61);
          LODWORD(P) = v32;
          if ( v49 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
            v32 = (int)P;
          }
        }
        if ( v32 != 1 )
          goto LABEL_9;
LABEL_67:
        if ( ++v12 >= v4 )
          goto LABEL_68;
      }
    }
    memset_0(v64, 0, 0xAAu);
    v28 = (_WORD *)(28LL * i + *(_QWORD *)(v27 + 16));
    LODWORD(P) = v18 & 0x10;
    *((_QWORD *)&v60 + 1) = v64;
    WORD1(v60) = 170;
    if ( (((_DWORD)P != 0 ? 34848 : 2080) & (unsigned __int16)*v28) != 0
      && (*v28 & 0x1000) == 0
      && (RtlpGetNameFromLangInfoNode(v53, v28, &v60) & 0xC0000000) != 0xC0000000
      && (RtlpGetLCIDFromLangInfoNode(v53, v28, &v54) & 0xC0000000) != 0xC0000000 )
    {
      LOBYTE(v29) = (_DWORD)P == 0;
      if ( (RtlpIsQualifiedLanguage(v53, v28, v29) & 0xC0000000) != 0xC0000000 && LanguageId != v54 )
        break;
    }
LABEL_55:
    ;
  }
  v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)v60 + 2LL);
  *((_QWORD *)Heap + v4) = v30;
  if ( v30 )
  {
    if ( (int)RtlStringCbCopyW(v30, (unsigned __int16)v60 + 2LL, *((_QWORD *)&v60 + 1)) < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)Heap + v4));
      *((_QWORD *)Heap + v4) = 0;
    }
    else
    {
      ++v4;
    }
    goto LABEL_55;
  }
  SetLastError_0(8u);
  v59 = 0;
LABEL_9:
  v13 = Heap;
  for ( j = 0; j < v4; ++j )
  {
LABEL_10:
    v15 = (void *)v13[j];
    if ( v15 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      v13[j] = 0;
    }
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  v16 = v59;
LABEL_14:
  if ( (v18 & 0x80u) != 0 && v53 )
    RtlpMuiFreeLangRegistryInfo();
  return v16;
}

```

## disassembly

```asm
0x180080480  mov     [rsp-8+arg_18], rbx
0x180080485  push    rbp
0x180080486  push    rsi
0x180080487  push    rdi
0x180080488  push    r12
0x18008048a  push    r13
0x18008048c  push    r14
0x18008048e  push    r15
0x180080490  lea     rbp, [rsp-330h]
0x180080498  sub     rsp, 430h
0x18008049f  mov     rax, cs:__security_cookie
0x1800804a6  xor     rax, rsp
0x1800804a9  mov     [rbp+360h+var_40], rax
0x1800804b0  xor     r15d, r15d
0x1800804b3  mov     [rbp+360h+var_3D0], r9d
0x1800804b7  mov     [rbp+360h+var_3B8], r8
0x1800804bb  xorps   xmm0, xmm0
0x1800804be  mov     [rsp+460h+LanguageId], r15w
0x1800804c4  xorps   xmm1, xmm1
0x1800804c7  mov     [rsp+460h+var_3F8], r15w
0x1800804cd  mov     r14d, r9d
0x1800804d0  mov     [rsp+460h+var_3E8], r15d
0x1800804d5  mov     rsi, r8
0x1800804d8  mov     [rsp+460h+var_400], r15
0x1800804dd  mov     ebx, edx
0x1800804df  mov     r13, rcx
0x1800804e2  movups  xmmword ptr [rbp+360h+DestinationString.Length], xmm0
0x1800804e6  movups  [rbp+360h+var_3C8], xmm1
0x1800804ea  test    rcx, rcx
0x1800804ed  jz      loc_180080D2C
0x1800804f3  test    edx, 0FFFFFF03h
0x1800804f9  jnz     short loc_18008051D
0x1800804fb  lea     eax, [r15+0Ch]
0x1800804ff  mov     edi, edx
0x180080501  and     edi, eax
0x180080503  cmp     edi, eax
0x180080505  jz      short loc_18008051D
0x180080507  test    bl, 10h
0x18008050a  jnz     loc_180080C93
0x180080510  mov     eax, ebx
0x180080512  and     eax, 60h
0x180080515  cmp     al, 60h ; '`'
0x180080517  jnz     loc_1800805F1
0x18008051d  mov     ecx, 3ECh; dwErrCode
0x180080522  call    SetLastError_0
0x180080527  xor     eax, eax
0x180080529  jmp     loc_1800805C6
0x18008052e  mov     edx, r15d; NumOfElements
0x180080531  lea     r9, QsortStringcompareFunc; CompareFunction
0x180080538  mov     r8d, 8; SizeOfElements
0x18008053e  mov     rcx, rsi; Base
0x180080541  call    cs:__imp_qsort
0x180080548  nop     dword ptr [rax+rax+00h]
0x18008054d  xor     ecx, ecx
0x18008054f  mov     r12d, ecx
0x180080552  test    r15d, r15d
0x180080555  jnz     loc_1800809B2
0x18008055b  mov     r14, rsi
0x18008055e  mov     edi, ecx
0x180080560  test    r15d, r15d
0x180080563  jz      short loc_180080599
0x180080565  mov     r12d, edi
0x180080568  mov     r8, [r14+r12*8]; P
0x18008056c  test    r8, r8
0x18008056f  jz      short loc_180080592
0x180080571  mov     rcx, gs:60h
0x18008057a  xor     edx, edx; Flags
0x18008057c  mov     rcx, [rcx+30h]; HeapHandle
0x180080580  call    cs:__imp_RtlFreeHeap
0x180080587  nop     dword ptr [rax+rax+00h]
0x18008058c  xor     ecx, ecx
0x18008058e  mov     [r14+r12*8], rcx
0x180080592  inc     edi
0x180080594  cmp     edi, r15d
0x180080597  jb      short loc_180080565
0x180080599  mov     rcx, gs:60h
0x1800805a2  mov     r8, rsi; P
0x1800805a5  xor     edx, edx; Flags
0x1800805a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800805ab  call    cs:__imp_RtlFreeHeap
0x1800805b2  nop     dword ptr [rax+rax+00h]
0x1800805b7  mov     r12d, [rbp+360h+var_3CC]
0x1800805bb  test    bl, bl
0x1800805bd  js      loc_180080993
0x1800805c3  mov     eax, r12d
0x1800805c6  mov     rcx, [rbp+360h+var_40]
0x1800805cd  xor     rcx, rsp; StackCookie
0x1800805d0  call    __security_check_cookie
0x1800805d5  mov     rbx, [rsp+460h+arg_18]
0x1800805dd  add     rsp, 430h
0x1800805e4  pop     r15
0x1800805e6  pop     r14
0x1800805e8  pop     r13
0x1800805ea  pop     r12
0x1800805ec  pop     rdi
0x1800805ed  pop     rsi
0x1800805ee  pop     rbp
0x1800805ef  retn
0x1800805f1  cmp     cs:gpSysLocHashN, r15
0x1800805f8  jnz     short loc_180080601
0x1800805fa  xor     ecx, ecx
0x1800805fc  call    SetupSystemLocaleHashNode
0x180080601  mov     ecx, ebx
0x180080603  or      ecx, 4
0x180080606  test    edi, edi
0x180080608  cmovnz  ecx, ebx
0x18008060b  mov     ebx, ecx
0x18008060d  or      ebx, 20h
0x180080610  test    cl, 70h
0x180080613  cmovnz  ebx, ecx
0x180080616  lea     rcx, [rsp+460h+var_400]
0x18008061b  test    bl, bl
0x18008061d  jns     loc_18008093C
0x180080623  call    cs:__imp_RtlpInitializeLangRegistryInfo
0x18008062a  nop     dword ptr [rax+rax+00h]
0x18008062f  test    eax, eax
0x180080631  js      loc_180080B83
0x180080637  mov     r12d, 1
0x18008063d  mov     edi, 1000h
0x180080642  mov     [rbp+360h+var_3CC], r12d
0x180080646  test    bl, 40h
0x180080649  jz      loc_1800806FD
0x18008064f  mov     rdx, [rsp+460h+var_400]
0x180080654  lea     r8, [rsp+460h+P]
0x180080659  xor     ecx, ecx
0x18008065b  mov     [rsp+460h+P], r15
0x180080660  call    cs:__imp_RtlpLoadMachineUIByPolicy
0x180080667  nop     dword ptr [rax+rax+00h]
0x18008066c  cmp     [rsp+460h+P], r15
0x180080671  jz      short loc_1800806A0
0x180080673  test    eax, eax
0x180080675  jz      loc_180080A6B
0x18008067b  mov     rcx, gs:60h
0x180080684  xor     edx, edx; Flags
0x180080686  mov     r8, [rsp+460h+P]; P
0x18008068b  mov     rcx, [rcx+30h]; HeapHandle
0x18008068f  call    cs:__imp_RtlFreeHeap
0x180080696  nop     dword ptr [rax+rax+00h]
0x18008069b  mov     [rsp+460h+P], r15
0x1800806a0  mov     rdx, [rsp+460h+var_400]
0x1800806a5  lea     r8, [rsp+460h+P]
0x1800806aa  xor     ecx, ecx
0x1800806ac  call    cs:__imp_RtlpLoadUserUIByPolicy
0x1800806b3  nop     dword ptr [rax+rax+00h]
0x1800806b8  xor     edi, edi
0x1800806ba  test    eax, eax
0x1800806bc  jz      loc_180080A60
0x1800806c2  cmp     [rsp+460h+P], rdi
0x1800806c7  jz      short loc_1800806E9
0x1800806c9  mov     rcx, gs:60h
0x1800806d2  xor     edx, edx; Flags
0x1800806d4  mov     r8, [rsp+460h+P]; P
0x1800806d9  mov     rcx, [rcx+30h]; HeapHandle
0x1800806dd  call    cs:__imp_RtlFreeHeap
0x1800806e4  nop     dword ptr [rax+rax+00h]
0x1800806e9  cmp     r15b, r12b
0x1800806ec  jz      loc_1800805BB
0x1800806f2  xor     r15d, r15d
0x1800806f5  or      ebx, 20h
0x1800806f8  mov     edi, 1000h
0x1800806fd  lea     rcx, [rsp+460h+LanguageId]; LanguageId
0x180080702  call    cs:__imp_NtQueryInstallUILanguage
0x180080709  nop     dword ptr [rax+rax+00h]
0x18008070e  mov     ecx, 0C0000000h
0x180080713  and     eax, ecx
0x180080715  cmp     eax, ecx
0x180080717  jz      loc_180080981
0x18008071d  movzx   ecx, [rsp+460h+LanguageId]
0x180080722  movzx   eax, cx
0x180080725  mov     edx, 0FBFFh
0x18008072a  sub     ax, di
0x18008072d  mov     edi, ebx
0x18008072f  test    dx, ax
0x180080732  jz      loc_180080C11
0x180080738  movzx   ecx, cx
0x18008073b  and     edi, 4
0x18008073e  jnz     loc_18008094D
0x180080744  lea     rax, [rbp+360h+var_1A0]
0x18008074b  mov     [rbp+360h+DestinationString.Buffer], rax
0x18008074f  lea     rdx, [rbp+360h+DestinationString]
0x180080753  mov     eax, 0AAh
0x180080758  mov     [rbp+360h+DestinationString.MaximumLength], ax
0x18008075c  call    cs:__imp_RtlLCIDToCultureName
0x180080763  nop     dword ptr [rax+rax+00h]
0x180080768  test    al, al
0x18008076a  jz      loc_180080C14
0x180080770  test    r14d, r14d
0x180080773  jz      loc_180080B98
0x180080779  mov     rcx, [rbp+360h+DestinationString.Buffer]
0x18008077d  mov     rdx, rsi
0x180080780  mov     rax, r13
0x180080783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080788  cmp     eax, r12d
0x18008078b  jnz     loc_1800805C3
0x180080791  mov     rax, [rsp+460h+var_400]
0x180080796  mov     edx, 8; Flags
0x18008079b  mov     rcx, [rax+18h]
0x18008079f  movzx   r8d, word ptr [rcx+6]
0x1800807a4  mov     rcx, gs:60h
0x1800807ad  shl     r8, 3; Size
0x1800807b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800807b5  call    cs:__imp_RtlAllocateHeap
0x1800807bc  nop     dword ptr [rax+rax+00h]
0x1800807c1  mov     rsi, rax
0x1800807c4  test    rax, rax
0x1800807c7  jz      loc_180080DC4
0x1800807cd  xor     r11d, r11d
0x1800807d0  mov     r14d, r11d
0x1800807d3  mov     rax, [rsp+460h+var_400]
0x1800807d8  mov     r12, [rax+18h]
0x1800807dc  movzx   eax, word ptr [r12+6]
0x1800807e2  cmp     r14d, eax
0x1800807e5  jnb     loc_18008052E
0x1800807eb  xor     edx, edx; Val
0x1800807ed  lea     rcx, [rbp+360h+var_F0]; void *
0x1800807f4  mov     r8d, 0AAh; Size
0x1800807fa  call    memset_0
0x1800807ff  mov     r12, [r12+10h]
0x180080804  mov     eax, r14d
0x180080807  imul    rcx, rax, 1Ch
0x18008080b  mov     eax, ebx
0x18008080d  and     eax, 10h
0x180080810  add     r12, rcx
0x180080813  mov     dword ptr [rsp+460h+P], eax
0x180080817  lea     rcx, [rbp+360h+var_F0]
0x18008081e  neg     eax
0x180080820  mov     qword ptr [rbp+360h+var_3C8+8], rcx
0x180080824  mov     eax, 0Ch
0x180080829  mov     ecx, 0AAh
0x18008082e  sbb     edx, edx
0x180080830  mov     word ptr [rbp+360h+var_3C8+2], cx
0x180080834  movzx   r8d, word ptr [r12]
0x180080839  and     edx, 8000h
0x18008083f  add     edx, 820h
0x180080845  test    r8d, edx
0x180080848  setnz   dl
0x18008084b  bt      r8w, ax
0x180080850  setnb   al
0x180080853  test    al, dl
0x180080855  jz      loc_180080934
0x18008085b  mov     rcx, [rsp+460h+var_400]
0x180080860  lea     r8, [rbp+360h+var_3C8]
0x180080864  mov     rdx, r12
0x180080867  call    cs:__imp_RtlpGetNameFromLangInfoNode
0x18008086e  nop     dword ptr [rax+rax+00h]
0x180080873  mov     ecx, 0C0000000h
0x180080878  and     eax, ecx
0x18008087a  cmp     eax, ecx
0x18008087c  jz      loc_180080934
0x180080882  mov     rcx, [rsp+460h+var_400]
0x180080887  lea     r8, [rsp+460h+var_3F8]
0x18008088c  mov     rdx, r12
0x18008088f  call    cs:__imp_RtlpGetLCIDFromLangInfoNode
0x180080896  nop     dword ptr [rax+rax+00h]
0x18008089b  mov     ecx, 0C0000000h
0x1800808a0  and     eax, ecx
0x1800808a2  cmp     eax, ecx
0x1800808a4  jz      loc_180080934
0x1800808aa  cmp     dword ptr [rsp+460h+P], 0
0x1800808af  mov     rdx, r12
0x1800808b2  mov     rcx, [rsp+460h+var_400]
0x1800808b7  setz    r8b
0x1800808bb  call    cs:__imp_RtlpIsQualifiedLanguage
0x1800808c2  nop     dword ptr [rax+rax+00h]
0x1800808c7  mov     ecx, 0C0000000h
0x1800808cc  and     eax, ecx
0x1800808ce  cmp     eax, ecx
0x1800808d0  jz      short loc_180080934
0x1800808d2  movzx   eax, [rsp+460h+var_3F8]
0x1800808d7  cmp     [rsp+460h+LanguageId], ax
0x1800808dc  jz      short loc_180080934
0x1800808de  mov     rcx, gs:60h
0x1800808e7  mov     edx, 8; Flags
0x1800808ec  movzx   r8d, word ptr [rbp+360h+var_3C8]
0x1800808f1  add     r8, 2; Size
0x1800808f5  mov     rcx, [rcx+30h]; HeapHandle
0x1800808f9  call    cs:__imp_RtlAllocateHeap
0x180080900  nop     dword ptr [rax+rax+00h]
0x180080905  mov     r12d, r15d
0x180080908  mov     [rsi+r12*8], rax
0x18008090c  test    rax, rax
0x18008090f  jz      loc_180080B6F
0x180080915  movzx   edx, word ptr [rbp+360h+var_3C8]
0x180080919  mov     rcx, rax
0x18008091c  mov     r8, qword ptr [rbp+360h+var_3C8+8]
0x180080920  add     rdx, 2
0x180080924  call    RtlStringCbCopyW
0x180080929  test    eax, eax
0x18008092b  js      loc_180080D98
0x180080931  inc     r15d
0x180080934  inc     r14d
0x180080937  jmp     loc_1800807D3
0x18008093c  call    cs:__imp_RtlpCreateProcessRegistryInfo
0x180080943  nop     dword ptr [rax+rax+00h]
0x180080948  jmp     loc_18008062F
0x18008094d  mov     edx, 10h
0x180080952  mov     dword ptr [rsp+460h+var_440], 104h
0x18008095a  lea     r9, [rbp+360h+WideCharStr]
0x18008095e  lea     r8d, [rdx-0Ch]
0x180080962  call    NlsConvertIntegerToString
  ... truncated ...
```
