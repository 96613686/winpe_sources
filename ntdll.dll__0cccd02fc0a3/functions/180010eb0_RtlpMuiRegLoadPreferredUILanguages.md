# RtlpMuiRegLoadPreferredUILanguages

- ea: `0x180010eb0`
- end: `0x180011c5d`
- name: `RtlpMuiRegLoadPreferredUILanguages`
- size: `3501`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d0c0`
- `0x18000d3e0`
- `0x18000e160`
- `0x18000e650`
- `0x180010320`

## callees

- `0x1800094d0`
- `0x180010280`
- `0x180010770`
- `0x180010870`
- `0x180010b80`
- `0x180010eb0`
- `0x18001228c`
- `0x1800122d0`
- `0x18001861c`
- `0x18001b984`
- `0x1800d8a80`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180163a80`

## string_xrefs

- `0x180010f1c`: `\Registry\Machine\Software\Policies\Microsoft\MUI\Settings`
- `0x1800111b9`: `\Registry\Machine\Software\Policies\Microsoft\MUI\Settings`
- `0x1800112ad`: `Control Panel\Desktop\MuiCached`
- `0x1800116f1`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings`

## pseudocode

```c
__int64 __fastcall RtlpMuiRegLoadPreferredUILanguages(
        __int64 a1,
        int a2,
        unsigned int a3,
        int a4,
        _BYTE *a5,
        __int64 *a6)
{
  int v6; // ebx
  unsigned int v7; // r12d
  __int64 v9; // rdi
  __int64 *v10; // r13
  void *v11; // r14
  size_t v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  HANDLE v17; // rbx
  size_t v18; // rax
  __int64 Heap_0; // rsi
  int v20; // ebx
  __int64 v22; // rax
  HANDLE v23; // rcx
  size_t v24; // rax
  int v25; // esi
  __int64 v26; // rdx
  __int64 LanguageList; // rax
  int v28; // esi
  size_t v29; // rax
  size_t v30; // rax
  HANDLE v31; // rbx
  __int64 v32; // rsi
  int v33; // eax
  unsigned int v34; // ebx
  void *v35; // rax
  int v36; // eax
  _DWORD *v37; // rax
  size_t v38; // rax
  int v39; // esi
  size_t v40; // rax
  const wchar_t *v41; // rcx
  unsigned int v42; // edx
  _BYTE *v43; // rbx
  size_t v44; // rax
  HANDLE v45; // rbx
  size_t v46; // rax
  void *v47; // rax
  int v48; // eax
  int v49; // esi
  unsigned int v50; // ebx
  HANDLE v51; // r8
  void *v52; // rax
  void *v53; // rax
  int v54; // eax
  _DWORD *v55; // rax
  unsigned int v56; // edx
  void *v57; // rdx
  int v58; // eax
  unsigned int v59; // ecx
  __int64 v60; // rax
  int v61; // eax
  __int64 v62; // rdx
  int v63; // eax
  int v64; // eax
  HANDLE v65; // [rsp+40h] [rbp-89h] BYREF
  HANDLE v66; // [rsp+48h] [rbp-81h] BYREF
  void *v67; // [rsp+50h] [rbp-79h] BYREF
  __int128 v68; // [rsp+58h] [rbp-71h] BYREF
  __int64 v69; // [rsp+68h] [rbp-61h] BYREF
  const wchar_t *v70; // [rsp+70h] [rbp-59h]
  __int64 v71; // [rsp+78h] [rbp-51h] BYREF
  HANDLE v72; // [rsp+80h] [rbp-49h]
  __int64 *v73; // [rsp+88h] [rbp-41h]
  __int64 v74; // [rsp+90h] [rbp-39h]
  __int128 v75; // [rsp+98h] [rbp-31h]
  HANDLE Handle; // [rsp+A8h] [rbp-21h] BYREF
  HANDLE v77; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-11h] BYREF
  HANDLE v79; // [rsp+C0h] [rbp-9h] BYREF
  HANDLE v80; // [rsp+C8h] [rbp-1h]
  int v81; // [rsp+120h] [rbp+57h]
  int v82; // [rsp+128h] [rbp+5Fh] BYREF
  int v83; // [rsp+130h] [rbp+67h] BYREF
  int v84; // [rsp+138h] [rbp+6Fh]

  v84 = a4;
  v82 = a2;
  v6 = a4;
  v77 = 0;
  v7 = a3;
  Handle = 0;
  v79 = 0;
  v9 = 0;
  v78 = 0;
  if ( !a1 )
    return 3221225485LL;
  if ( !a5 )
    return 3221225485LL;
  v10 = a6;
  if ( !a6 )
    return 3221225485LL;
  *a5 = 0;
  if ( a3 > 1 )
    return 3221225485LL;
  v69 = 0;
  v11 = 0;
  v70 = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings";
  v12 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings");
  v71 = 48;
  v74 = 64;
  v79 = 0;
  if ( v12 >= 0xFFFE )
    LOWORD(v12) = -4;
  v72 = 0;
  LOWORD(v69) = v12;
  WORD1(v69) = v12 + 2;
  v73 = &v69;
  v75 = 0;
  v81 = 7;
  if ( (int)NtOpenKey(&v79, 131097, &v71) < 0 )
  {
    v79 = 0;
    goto LABEL_9;
  }
  v23 = v79;
  v65 = 0;
  LOBYTE(v82) = 0;
  LOWORD(v83) = 0;
  v68 = 0;
  if ( v79 )
    goto LABEL_41;
  *((_QWORD *)&v68 + 1) = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings";
  v24 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings");
  v71 = 48;
  v74 = 64;
  v65 = 0;
  if ( v24 >= 0xFFFE )
    LOWORD(v24) = -4;
  v72 = 0;
  LOWORD(v68) = v24;
  WORD1(v68) = v24 + 2;
  v73 = (__int64 *)&v68;
  v75 = 0;
  v25 = NtOpenKey(&v65, 131097, &v71);
  if ( v25 >= 0 )
  {
    v23 = v65;
LABEL_41:
    v25 = RtlpLoadPolicyLanguageSpec(v23, a1, &v82, &v83);
    if ( !v25 )
    {
      LOBYTE(v26) = 1;
      LanguageList = RtlpMuiRegCreateLanguageList(1, v26, a1);
      v78 = LanguageList;
      v9 = LanguageList;
      if ( LanguageList )
      {
        *(_WORD *)(*(_QWORD *)(LanguageList + 24) + 6LL * *(unsigned __int16 *)(LanguageList + 4)) = (unsigned __int8)v82;
        *(_WORD *)(*(_QWORD *)(LanguageList + 24) + 6LL * (unsigned __int16)(*(_WORD *)(LanguageList + 4))++ + 4) = v83;
      }
      else
      {
        v25 = -1073741801;
      }
    }
  }
  if ( v65 )
    NtClose(v65);
  if ( !v25 && v9 )
  {
    v43 = a5;
    goto LABEL_119;
  }
LABEL_9:
  if ( v7 == 1 )
  {
    v17 = v79;
    if ( !v79 )
      goto LABEL_22;
    v82 = -1;
    *((_QWORD *)&v68 + 1) = L"MachineUILock";
    *(_QWORD *)&v68 = 0;
    v18 = 2 * wcslen(L"MachineUILock");
    v83 = 0;
    if ( v18 >= 0xFFFE )
      LOWORD(v18) = -4;
    LOWORD(v68) = v18;
    WORD1(v68) = v18 + 2;
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 16);
    if ( !Heap_0 )
      goto LABEL_22;
    v20 = NtQueryValueKey(v17, &v68, 2, Heap_0, 16, &v83);
    if ( v20 >= 0 )
    {
      v59 = *(_DWORD *)(Heap_0 + 8);
      if ( v59 > 4 )
        v20 = -2147483643;
      else
        memmove(&v82, (const void *)(Heap_0 + 12), v59);
    }
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
    if ( v20 >= 0 )
    {
      v6 = v84;
      if ( v82 == 1 )
        v7 = 0;
    }
    else
    {
LABEL_22:
      v6 = v84;
    }
  }
  v13 = GetGlobalizationUserModelType() - 1;
  if ( v13 )
  {
    v15 = v13 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
      {
        v28 = -1073741595;
        goto LABEL_122;
      }
      v82 = 0;
      v16 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000, v14, &v77, &v82);
    }
    else
    {
      v16 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000, &v77);
    }
  }
  else
  {
    v16 = RtlOpenCurrentUser(0x2000000, &v77);
  }
  v28 = v16;
  if ( v16 < 0 )
  {
LABEL_122:
    *a5 = 1;
    goto LABEL_29;
  }
  if ( v7 == 1 )
  {
    v65 = 0;
    v66 = 0;
    LOBYTE(v82) = 0;
    LOWORD(v83) = 0;
    *(_QWORD *)&v68 = 0;
    *((_QWORD *)&v68 + 1) = L"Software\\Policies\\Microsoft\\Control Panel\\Desktop";
    v38 = 2 * wcslen(L"Software\\Policies\\Microsoft\\Control Panel\\Desktop");
    if ( v38 >= 0xFFFE )
      LOWORD(v38) = -4;
    LOWORD(v68) = v38;
    WORD1(v68) = v38 + 2;
    if ( v77 )
    {
      v72 = v77;
      v66 = 0;
    }
    else
    {
      v61 = GetGlobalizationUserModelType() - 1;
      if ( v61 )
      {
        v63 = v61 - 1;
        if ( v63 )
        {
          if ( v63 != 1 )
          {
            v39 = -1073741595;
            goto LABEL_74;
          }
          LODWORD(v67) = 0;
          v64 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000, v62, &v65, &v67);
        }
        else
        {
          v64 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000, &v65);
        }
      }
      else
      {
        v64 = RtlOpenCurrentUser(0x2000000, &v65);
      }
      v39 = v64;
      if ( v64 < 0 )
      {
LABEL_74:
        if ( v66 )
        {
          NtClose(v66);
          v66 = 0;
        }
        if ( v65 )
          NtClose(v65);
        if ( !v39 && v9 )
        {
          v28 = 0;
          goto LABEL_27;
        }
        v69 = 0;
        v70 = L"Control Panel\\Desktop";
        v40 = 2 * wcslen(L"Control Panel\\Desktop");
        v71 = 48;
        v74 = 64;
        Handle = 0;
        if ( v40 >= 0xFFFE )
          LOWORD(v40) = -4;
        LOWORD(v69) = v40;
        WORD1(v69) = v40 + 2;
        v72 = v77;
        v73 = &v69;
        v75 = 0;
        v28 = NtOpenKey(&Handle, 131097, &v71);
        if ( v28 < 0 )
        {
          *a5 = 1;
          goto LABEL_29;
        }
        v69 = 0;
        v41 = L"PreferredUILanguages";
        if ( v6 != 3 )
          v41 = L"PreferredUILanguagesPending";
        v70 = v41;
        v30 = 2 * wcslen(v41);
        if ( v30 >= 0xFFFE )
          LOWORD(v30) = -4;
        goto LABEL_57;
      }
      v66 = 0;
      v72 = v65;
    }
    v71 = 48;
    v73 = (__int64 *)&v68;
    v74 = 64;
    v75 = 0;
    v39 = NtOpenKey(&v66, 131097, &v71);
    if ( v39 < 0 )
      goto LABEL_74;
    v39 = RtlpLoadPolicyLanguageSpec(v66, a1, &v82, &v83);
    if ( v39 )
      goto LABEL_74;
    if ( v9 )
    {
      if ( *(_WORD *)(v9 + 4) < *(_WORD *)(v9 + 6) )
        goto LABEL_160;
      v60 = RtlpMuiRegGrowLanguageList(v9);
    }
    else
    {
      v60 = RtlpMuiRegCreateLanguageList(1, 0, a1);
    }
    v78 = v60;
    v9 = v60;
    if ( !v60 )
    {
      v39 = -1073741801;
      goto LABEL_74;
    }
LABEL_160:
    *(_WORD *)(*(_QWORD *)(v9 + 24) + 6LL * *(unsigned __int16 *)(v9 + 4)) = (unsigned __int8)v82;
    *(_WORD *)(*(_QWORD *)(v9 + 24) + 6LL * (unsigned __int16)(*(_WORD *)(v9 + 4))++ + 4) = v83;
    goto LABEL_74;
  }
  v69 = 0;
  v70 = L"Control Panel\\Desktop\\MuiCached";
  v29 = 2 * wcslen(L"Control Panel\\Desktop\\MuiCached");
  v71 = 48;
  v74 = 64;
  Handle = 0;
  if ( v29 >= 0xFFFE )
    LOWORD(v29) = -4;
  LOWORD(v69) = v29;
  WORD1(v69) = v29 + 2;
  v72 = v77;
  v73 = &v69;
  v75 = 0;
  if ( (int)NtOpenKey(&Handle, 131097, &v71) < 0 )
  {
    v28 = 0;
    v43 = a5;
    *a5 = 1;
    goto LABEL_97;
  }
  v69 = 0;
  v70 = L"MachinePreferredUILanguages";
  v30 = 2 * wcslen(L"MachinePreferredUILanguages");
  if ( v30 >= 0xFFFE )
    LOWORD(v30) = -4;
LABEL_57:
  v31 = Handle;
  LOWORD(v69) = v30;
  v83 = 0;
  WORD1(v69) = v30 + 2;
  v32 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 12);
  if ( !v32 )
    goto LABEL_118;
  v33 = NtQueryValueKey(v31, &v69, 2, v32, 12, &v83);
  LODWORD(v67) = v33;
  if ( v33 >= 0 || (v34 = 0, v82 = 7, v33 == -2147483643) )
  {
    v34 = *(_DWORD *)(v32 + 8);
    v82 = *(_DWORD *)(v32 + 4);
  }
  RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v32);
  if ( (_DWORD)v67 == -1073741772 || !v34 )
  {
LABEL_118:
    v43 = a5;
    *a5 = 1;
LABEL_119:
    v28 = 0;
    goto LABEL_97;
  }
  if ( (_DWORD)v67 != -2147483643 )
  {
    v28 = -1073741772;
    goto LABEL_29;
  }
  v11 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v34 + 2);
  if ( !v11 )
  {
    v28 = -1073741801;
    goto LABEL_29;
  }
  v83 = 0;
  if ( v34 == -12
    || (v66 = Handle, v35 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v34 + 12), (v65 = v35) == 0) )
  {
    v28 = -1073741670;
    goto LABEL_28;
  }
  v36 = NtQueryValueKey(v66, &v69, 2, v35, v34 + 12, &v83);
  v28 = v36;
  if ( v36 < 0 )
  {
    if ( v36 != -2147483643 )
    {
      v37 = v65;
      goto LABEL_93;
    }
    goto LABEL_91;
  }
  v37 = v65;
  v42 = *((_DWORD *)v65 + 2);
  if ( v42 > v34 )
  {
    v28 = -2147483643;
    goto LABEL_92;
  }
  if ( v42 <= v34 + 12 )
  {
    memmove(v11, (char *)v65 + 12, v42);
LABEL_91:
    v37 = v65;
  }
LABEL_92:
  v34 = v37[2];
  v82 = v37[1];
LABEL_93:
  RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v37);
  if ( v28 < 0 )
    goto LABEL_28;
  if ( v82 != 1 && v82 != 7 )
    goto LABEL_118;
  v28 = RtlpMuiRegAddMultiSzToLangFallbackList(a1, v11, v34 >> 1, 8, (unsigned int)(v7 != 1) + 2, 1, &v78);
  if ( v28 )
    goto LABEL_28;
  v9 = v78;
  v43 = a5;
LABEL_97:
  if ( v7 || v9 && *(_WORD *)(v9 + 4) )
  {
LABEL_24:
    if ( !v9 )
    {
      v22 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 70);
      v9 = v22;
      if ( v22 )
      {
        *(_DWORD *)v22 = 70;
        *(_DWORD *)(v22 + 4) = 0x10000;
        *(_DWORD *)(v22 + 40) = 0;
        *(_BYTE *)(v22 + 8) = v7 != 1;
        *(_QWORD *)(v22 + 24) = v22 + 64;
        *(_QWORD *)(v22 + 16) = a1;
      }
      else
      {
        v9 = 0;
        v28 = -1073741801;
      }
    }
    goto LABEL_27;
  }
  v28 = 0;
  v65 = 0;
  v67 = 0;
  *(_QWORD *)&v68 = 0;
  *((_QWORD *)&v68 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings";
  v44 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings");
  v71 = 48;
  v74 = 64;
  v65 = 0;
  if ( v44 >= 0xFFFE )
    LOWORD(v44) = -4;
  v72 = 0;
  LOWORD(v68) = v44;
  WORD1(v68) = v44 + 2;
  v73 = (__int64 *)&v68;
  v75 = 0;
  if ( (int)NtOpenKey(&v65, 131097, &v71) < 0 )
  {
    *v43 = 1;
    v52 = 0;
  }
  else
  {
    *(_QWORD *)&v68 = 0;
    *((_QWORD *)&v68 + 1) = L"PreferredUILanguages";
    v45 = v65;
    v46 = 2 * wcslen(L"PreferredUILanguages");
    v82 = 0;
    if ( v46 >= 0xFFFE )
      LOWORD(v46) = -4;
    LOWORD(v68) = v46;
    WORD1(v68) = v46 + 2;
    v47 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 12);
    v66 = v47;
    if ( !v47 )
      goto LABEL_152;
    v48 = NtQueryValueKey(v45, &v68, 2, v47, 12, &v82);
    v49 = v48;
    if ( v48 >= 0 || (v50 = 0, v48 == -2147483643) )
    {
      v51 = v66;
      v50 = *((_DWORD *)v66 + 2);
      v81 = *((_DWORD *)v66 + 1);
    }
    else
    {
      v51 = v66;
    }
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v51);
    if ( v49 == -1073741772 || !v50 )
    {
      v28 = 0;
      goto LABEL_152;
    }
    if ( v49 != -2147483643 )
    {
      v28 = -1073741772;
      goto LABEL_134;
    }
    v52 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v50 + 2);
    v67 = v52;
    if ( v52 )
    {
      v82 = 0;
      if ( v50 == -12
        || (v80 = v65, v53 = (void *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v50 + 12), (v66 = v53) == 0) )
      {
        v28 = -1073741670;
        goto LABEL_134;
      }
      v54 = NtQueryValueKey(v80, &v68, 2, v53, v50 + 12, &v82);
      v28 = v54;
      if ( v54 >= 0 )
      {
        v55 = v66;
        v56 = *((_DWORD *)v66 + 2);
        if ( v56 > v50 )
        {
          v28 = -2147483643;
          goto LABEL_130;
        }
        if ( v56 > v50 + 12 )
        {
LABEL_130:
          v50 = v55[2];
          v81 = v55[1];
LABEL_131:
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v55);
          if ( v28 >= 0 )
          {
            if ( v81 != 7 && v81 != 1 )
            {
              v28 = 0;
LABEL_152:
              *a5 = 1;
              goto LABEL_134;
            }
            v57 = v67;
            *a5 = 0;
            v58 = RtlpMuiRegAddMultiSzToLangFallbackList(a1, v57, v50 >> 1, 8, 3, 1, &v78);
            v9 = v78;
            v28 = v58;
          }
LABEL_134:
          v52 = v67;
          goto LABEL_135;
        }
        memmove(v67, (char *)v66 + 12, v56);
      }
      else if ( v54 != -2147483643 )
      {
        v55 = v66;
        goto LABEL_131;
      }
      v55 = v66;
      goto LABEL_130;
    }
    v28 = -1073741801;
  }
LABEL_135:
  if ( v65 )
  {
    NtClose(v65);
    v52 = v67;
  }
  if ( v52 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v52);
  if ( !v28 )
    goto LABEL_24;
LABEL_27:
  *v10 = v9;
  if ( v11 )
LABEL_28:
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v11);
LABEL_29:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v77 )
  {
    NtClose(v77);
    v77 = 0;
  }
  if ( v79 )
    NtClose(v79);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180010eb0  mov     [rsp-8+arg_18], r9d
0x180010eb5  mov     [rsp-8+arg_8], edx
0x180010eb9  push    rbp
0x180010eba  push    rbx
0x180010ebb  push    rsi
0x180010ebc  push    rdi
0x180010ebd  push    r12
0x180010ebf  push    r13
0x180010ec1  push    r15
0x180010ec3  lea     rbp, [rsp-17h]
0x180010ec8  sub     rsp, 0E0h
0x180010ecf  xor     esi, esi
0x180010ed1  mov     ebx, r9d
0x180010ed4  mov     [rbp+47h+var_60], rsi
0x180010ed8  mov     r12d, r8d
0x180010edb  mov     [rbp+47h+Handle], rsi
0x180010edf  mov     r15, rcx
0x180010ee2  mov     [rbp+47h+var_50], rsi
0x180010ee6  mov     edi, esi
0x180010ee8  mov     [rbp+47h+var_58], rsi
0x180010eec  test    rcx, rcx
0x180010eef  jz      loc_1800110C0
0x180010ef5  mov     rax, [rbp+47h+arg_20]
0x180010ef9  test    rax, rax
0x180010efc  jz      loc_1800110C0
0x180010f02  mov     r13, [rbp+47h+arg_28]
0x180010f06  test    r13, r13
0x180010f09  jz      loc_1800110C0
0x180010f0f  mov     [rax], sil
0x180010f12  cmp     r8d, 1
0x180010f16  ja      loc_1800110C0
0x180010f1c  lea     rax, aRegistryMachin_23; "\\Registry\\Machine\\Software\\Policies"...
0x180010f23  mov     [rsp+110h+var_38], r14
0x180010f2b  mov     rcx, rax; String
0x180010f2e  mov     [rbp+47h+var_A8], rsi
0x180010f32  mov     r14d, esi
0x180010f35  mov     [rbp+47h+var_A0], rax
0x180010f39  call    wcslen
0x180010f3e  add     rax, rax
0x180010f41  mov     [rbp+47h+var_98], 30h ; '0'
0x180010f49  cmp     rax, 0FFFEh
0x180010f4f  mov     [rbp+47h+var_80], 40h ; '@'
0x180010f57  mov     ecx, 0FFFCh
0x180010f5c  mov     [rbp+47h+var_50], rsi
0x180010f60  cmovnb  rax, rcx
0x180010f64  mov     [rbp+47h+var_90], rsi
0x180010f68  mov     word ptr [rbp+47h+var_A8], ax
0x180010f6c  lea     r8, [rbp+47h+var_98]
0x180010f70  add     ax, 2
0x180010f74  lea     rcx, [rbp+47h+var_50]
0x180010f78  mov     word ptr [rbp+47h+var_A8+2], ax
0x180010f7c  xorps   xmm0, xmm0
0x180010f7f  lea     rax, [rbp+47h+var_A8]
0x180010f83  mov     edx, 20019h
0x180010f88  mov     [rbp+47h+var_88], rax
0x180010f8c  movdqu  [rbp+47h+var_78], xmm0
0x180010f91  call    NtOpenKey
0x180010f96  mov     [rbp+47h+arg_0], 7
0x180010f9d  test    eax, eax
0x180010f9f  jns     loc_18001119C
0x180010fa5  mov     [rbp+47h+var_50], rsi
0x180010fa9  cmp     r12d, 1
0x180010fad  jz      short loc_180010FEA
0x180010faf  call    GetGlobalizationUserModelType
0x180010fb4  sub     eax, 1
0x180010fb7  jz      loc_180011920
0x180010fbd  sub     eax, 1
0x180010fc0  jz      loc_18001128B
0x180010fc6  cmp     eax, 1
0x180010fc9  jnz     loc_18001190F
0x180010fcf  lea     r9, [rbp+47h+arg_8]
0x180010fd3  mov     [rbp+47h+arg_8], r14d
0x180010fd7  lea     r8, [rbp+47h+var_60]
0x180010fdb  mov     ecx, 2000000h
0x180010fe0  call    OpenGlobalizationUserSettingsKey_ForMua
0x180010fe5  jmp     loc_180011299
0x180010fea  mov     rbx, [rbp+47h+var_50]
0x180010fee  test    rbx, rbx
0x180010ff1  jz      loc_1800110B8
0x180010ff7  lea     rcx, aMachineuilock; "MachineUILock"
0x180010ffe  mov     [rbp+47h+arg_8], 0FFFFFFFFh
0x180011005  mov     qword ptr [rbp+47h+var_B8+8], rcx
0x180011009  mov     qword ptr [rbp+47h+var_B8], rsi
0x18001100d  call    wcslen
0x180011012  add     rax, rax
0x180011015  mov     [rbp+47h+arg_10], esi
0x180011018  cmp     rax, 0FFFEh
0x18001101e  mov     ecx, 0FFFCh
0x180011023  mov     edx, 8
0x180011028  mov     r8d, 10h
0x18001102e  cmovnb  rax, rcx
0x180011032  mov     word ptr [rbp+47h+var_B8], ax
0x180011036  add     ax, 2
0x18001103a  mov     word ptr [rbp+47h+var_B8+2], ax
0x18001103e  mov     rcx, gs:60h
0x180011047  mov     rcx, [rcx+30h]
0x18001104b  call    RtlAllocateHeap_0
0x180011050  mov     rsi, rax
0x180011053  test    rax, rax
0x180011056  jz      short loc_1800110B8
0x180011058  lea     rax, [rbp+47h+arg_10]
0x18001105c  mov     r9, rsi
0x18001105f  mov     [rsp+110h+var_E8], rax
0x180011064  lea     rdx, [rbp+47h+var_B8]
0x180011068  mov     r8d, 2
0x18001106e  mov     [rsp+110h+var_F0], 10h
0x180011076  mov     rcx, rbx
0x180011079  call    NtQueryValueKey
0x18001107e  mov     ebx, eax
0x180011080  test    eax, eax
0x180011082  jns     loc_180011A49
0x180011088  mov     rcx, gs:60h
0x180011091  mov     r8, rsi
0x180011094  xor     edx, edx
0x180011096  mov     rcx, [rcx+30h]
0x18001109a  call    RtlFreeHeap_0
0x18001109f  test    ebx, ebx
0x1800110a1  js      short loc_1800110B8
0x1800110a3  cmp     [rbp+47h+arg_8], 1
0x1800110a7  mov     ebx, [rbp+47h+arg_18]
0x1800110aa  jnz     loc_180010FAF
0x1800110b0  xor     r12d, r12d
0x1800110b3  jmp     loc_180010FAF
0x1800110b8  mov     ebx, [rbp+47h+arg_18]
0x1800110bb  jmp     loc_180010FAF
0x1800110c0  mov     eax, 0C000000Dh
0x1800110c5  jmp     loc_180011189
0x1800110ca  test    rdi, rdi
0x1800110cd  jnz     short loc_180011122
0x1800110cf  mov     rcx, gs:60h
0x1800110d8  mov     edx, 8
0x1800110dd  mov     r8d, 46h ; 'F'
0x1800110e3  mov     rcx, [rcx+30h]
0x1800110e7  call    RtlAllocateHeap_0
0x1800110ec  mov     rdi, rax
0x1800110ef  test    rax, rax
0x1800110f2  jz      loc_180011BA4
0x1800110f8  mov     dword ptr [rax], 46h ; 'F'
0x1800110fe  cmp     r12d, 1
0x180011102  mov     dword ptr [rax+4], 10000h
0x180011109  setnz   al
0x18001110c  mov     dword ptr [rdi+28h], 0
0x180011113  mov     [rdi+8], al
0x180011116  lea     rax, [rdi+40h]
0x18001111a  mov     [rdi+18h], rax
0x18001111e  mov     [rdi+10h], r15
0x180011122  mov     [r13+0], rdi
0x180011126  test    r14, r14
0x180011129  jz      short loc_180011142
0x18001112b  mov     rcx, gs:60h
0x180011134  mov     r8, r14
0x180011137  xor     edx, edx
0x180011139  mov     rcx, [rcx+30h]
0x18001113d  call    RtlFreeHeap_0
0x180011142  mov     rcx, [rbp+47h+Handle]; Handle
0x180011146  mov     r14, [rsp+110h+var_38]
0x18001114e  test    rcx, rcx
0x180011151  jz      short loc_180011160
0x180011153  call    NtClose
0x180011158  mov     [rbp+47h+Handle], 0
0x180011160  mov     rcx, [rbp+47h+var_60]; Handle
0x180011164  test    rcx, rcx
0x180011167  jz      short loc_180011176
0x180011169  call    NtClose
0x18001116e  mov     [rbp+47h+var_60], 0
0x180011176  mov     rbx, [rbp+47h+var_50]
0x18001117a  test    rbx, rbx
0x18001117d  jz      short loc_180011187
0x18001117f  mov     rcx, rbx; Handle
0x180011182  call    NtClose
0x180011187  mov     eax, esi
0x180011189  add     rsp, 0E0h
0x180011190  pop     r15
0x180011192  pop     r13
0x180011194  pop     r12
0x180011196  pop     rdi
0x180011197  pop     rsi
0x180011198  pop     rbx
0x180011199  pop     rbp
0x18001119a  retn
0x18001119c  mov     rcx, [rbp+47h+var_50]
0x1800111a0  xorps   xmm0, xmm0
0x1800111a3  mov     [rsp+110h+var_D0], rsi
0x1800111a8  mov     byte ptr [rbp+47h+arg_8], sil
0x1800111ac  mov     word ptr [rbp+47h+arg_10], si
0x1800111b0  movups  [rbp+47h+var_B8], xmm0
0x1800111b4  test    rcx, rcx
0x1800111b7  jnz     short loc_18001122E
0x1800111b9  lea     rcx, aRegistryMachin_23; "\\Registry\\Machine\\Software\\Policies"...
0x1800111c0  mov     qword ptr [rbp+47h+var_B8+8], rcx
0x1800111c4  call    wcslen
0x1800111c9  add     rax, rax
0x1800111cc  mov     [rbp+47h+var_98], 30h ; '0'
0x1800111d4  cmp     rax, 0FFFEh
0x1800111da  mov     [rbp+47h+var_80], 40h ; '@'
0x1800111e2  mov     ecx, 0FFFCh
0x1800111e7  mov     [rsp+110h+var_D0], rsi
0x1800111ec  cmovnb  rax, rcx
0x1800111f0  mov     [rbp+47h+var_90], rsi
0x1800111f4  mov     word ptr [rbp+47h+var_B8], ax
0x1800111f8  lea     r8, [rbp+47h+var_98]
0x1800111fc  add     ax, 2
0x180011200  lea     rcx, [rsp+110h+var_D0]
0x180011205  mov     word ptr [rbp+47h+var_B8+2], ax
0x180011209  xorps   xmm0, xmm0
0x18001120c  lea     rax, [rbp+47h+var_B8]
0x180011210  mov     edx, 20019h
0x180011215  mov     [rbp+47h+var_88], rax
0x180011219  movdqu  [rbp+47h+var_78], xmm0
0x18001121e  call    NtOpenKey
0x180011223  mov     esi, eax
0x180011225  test    eax, eax
0x180011227  js      short loc_180011268
0x180011229  mov     rcx, [rsp+110h+var_D0]
0x18001122e  lea     r9, [rbp+47h+arg_10]
0x180011232  mov     rdx, r15
0x180011235  lea     r8, [rbp+47h+arg_8]
0x180011239  call    RtlpLoadPolicyLanguageSpec
0x18001123e  mov     esi, eax
0x180011240  test    eax, eax
0x180011242  jnz     short loc_180011268
0x180011244  mov     r8, r15
0x180011247  mov     dl, 1
0x180011249  mov     ecx, 1
0x18001124e  call    RtlpMuiRegCreateLanguageList
0x180011253  mov     [rbp+47h+var_58], rax
0x180011257  mov     rdi, rax
0x18001125a  test    rax, rax
0x18001125d  jnz     loc_180011A17
0x180011263  mov     esi, 0C0000017h
0x180011268  mov     rcx, [rsp+110h+var_D0]; Handle
0x18001126d  test    rcx, rcx
0x180011270  jz      short loc_180011277
0x180011272  call    NtClose
0x180011277  test    esi, esi
0x180011279  jnz     short loc_180011284
0x18001127b  test    rdi, rdi
0x18001127e  jnz     loc_180011C3C
0x180011284  xor     esi, esi
0x180011286  jmp     loc_180010FA9
0x18001128b  lea     rdx, [rbp+47h+var_60]
0x18001128f  mov     ecx, 2000000h
0x180011294  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180011299  mov     esi, eax
0x18001129b  test    eax, eax
0x18001129d  js      loc_180011914
0x1800112a3  cmp     r12d, 1
0x1800112a7  jz      loc_1800114AF
0x1800112ad  lea     rcx, aControlPanelDe; "Control Panel\\Desktop\\MuiCached"
0x1800112b4  xor     ebx, ebx
0x1800112b6  mov     [rbp+47h+var_A8], rbx
0x1800112ba  mov     [rbp+47h+var_A0], rcx
0x1800112be  call    wcslen
0x1800112c3  add     rax, rax
0x1800112c6  mov     [rbp+47h+var_98], 30h ; '0'
0x1800112ce  cmp     rax, 0FFFEh
0x1800112d4  mov     [rbp+47h+var_80], 40h ; '@'
0x1800112dc  xorps   xmm0, xmm0
0x1800112df  mov     [rbp+47h+Handle], rbx
0x1800112e3  mov     esi, 0FFFCh
0x1800112e8  lea     r8, [rbp+47h+var_98]
0x1800112ec  cmovnb  rax, rsi
0x1800112f0  lea     rcx, [rbp+47h+Handle]
0x1800112f4  mov     word ptr [rbp+47h+var_A8], ax
0x1800112f8  mov     edx, 20019h
0x1800112fd  add     ax, 2
0x180011301  mov     word ptr [rbp+47h+var_A8+2], ax
0x180011305  mov     rax, [rbp+47h+var_60]
0x180011309  mov     [rbp+47h+var_90], rax
0x18001130d  lea     rax, [rbp+47h+var_A8]
0x180011311  mov     [rbp+47h+var_88], rax
0x180011315  movdqu  [rbp+47h+var_78], xmm0
0x18001131a  call    NtOpenKey
0x18001131f  test    eax, eax
0x180011321  js      loc_180011C0D
0x180011327  lea     rcx, aMachinepreferr; "MachinePreferredUILanguages"
0x18001132e  mov     [rbp+47h+var_A8], rbx
0x180011332  mov     [rbp+47h+var_A0], rcx
0x180011336  call    wcslen
0x18001133b  add     rax, rax
0x18001133e  cmp     rax, 0FFFEh
0x180011344  cmovnb  rax, rsi
0x180011348  mov     rbx, [rbp+47h+Handle]
0x18001134c  mov     edx, 8
0x180011351  mov     word ptr [rbp+47h+var_A8], ax
0x180011355  mov     r8d, 0Ch
0x18001135b  mov     [rbp+47h+arg_10], r14d
0x18001135f  add     ax, 2
0x180011363  mov     word ptr [rbp+47h+var_A8+2], ax
0x180011367  mov     rcx, gs:60h
0x180011370  mov     rcx, [rcx+30h]
0x180011374  call    RtlAllocateHeap_0
0x180011379  mov     rsi, rax
0x18001137c  test    rax, rax
0x18001137f  jz      loc_1800118F3
0x180011385  lea     rax, [rbp+47h+arg_10]
0x180011389  mov     r9, rsi
0x18001138c  mov     [rsp+110h+var_E8], rax
0x180011391  lea     rdx, [rbp+47h+var_A8]
0x180011395  mov     r8d, 2
  ... truncated ...
```
