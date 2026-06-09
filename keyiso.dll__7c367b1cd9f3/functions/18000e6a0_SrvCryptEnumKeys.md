# SrvCryptEnumKeys

- ea: `0x18000e6a0`
- end: `0x18000eb35`
- name: `SrvCryptEnumKeys`
- size: `1173`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180002d20`
- `0x180002d40`
- `0x180003cf0`
- `0x1800048f0`
- `0x180005510`
- `0x180006280`
- `0x180006a10`
- `0x180006e60`
- `0x180007210`
- `0x180009a74`
- `0x18000a0a8`
- `0x18000d0ac`
- `0x18000e6a0`
- `0x18001136c`
- `0x180019010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000eaff`
- `ntdll!RtlLeaveCriticalSection` at `0x18000eaff`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ea52`
- `ntdll!RtlInitializeCriticalSection` at `0x18000ea52`

## string_xrefs

- `0x18000e6eb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e7cf`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000ea8e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptEnumKeys(__int64 a1, __int64 a2, __int64 a3, wchar_t ***a4, _QWORD *a5, int a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 v7; // r13
  __int64 v11; // r15
  __int64 v12; // r9
  int v13; // ebx
  __int64 v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  wchar_t **v20; // rsi
  HRESULT v21; // edi
  __int64 v22; // r9
  STRSAFE_PCNZWCH *v23; // rax
  const char *v24; // rdx
  size_t v25; // rbx
  wchar_t *v26; // rax
  size_t v27; // rbx
  wchar_t *v28; // rax
  wchar_t *v29; // rcx
  int v30; // eax
  int v31; // eax
  STRSAFE_PCNZWCH *v33; // [rsp+30h] [rbp-20h] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-18h] BYREF
  ULONGLONG pullResult; // [rsp+40h] [rbp-10h] BYREF
  __int64 v36; // [rsp+48h] [rbp-8h] BYREF
  ULONG pulResult; // [rsp+90h] [rbp+40h] BYREF
  wchar_t ***v38; // [rsp+A8h] [rbp+58h]

  v38 = a4;
  v6 = 0;
  v7 = 0;
  v36 = 0;
  v33 = 0;
  if ( !a1 )
  {
    v11 = 0;
    v12 = 1205;
LABEL_3:
    v13 = -2146893786;
    v14 = 2148073510LL;
LABEL_4:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v12);
    goto LABEL_53;
  }
  v11 = SrvLookupAndReferenceProvider(a1, a2, 0);
  if ( !v11 )
  {
    v12 = 1214;
    goto LABEL_3;
  }
  if ( !a4 || !a5 )
  {
    v20 = 0;
    v13 = -2146893785;
    v21 = -2146893785;
    v22 = 1221;
    goto LABEL_46;
  }
  if ( *a5 )
  {
    v17 = SrvLookupMemoryBufferFromList(a1, *a5, 0);
    v7 = v17;
    if ( !v17 )
    {
      v13 = -2146893785;
      v12 = 1255;
      v14 = 2148073511LL;
      goto LABEL_4;
    }
    v16 = *(_QWORD *)(v17 + 48);
  }
  else
  {
    v15 = (struct _RTL_CRITICAL_SECTION *)MSCryptAlloc(80);
    v6 = v15;
    if ( !v15 )
    {
      v13 = -2146893810;
      v12 = 1238;
      v14 = 2148073486LL;
      goto LABEL_4;
    }
    memset_0(v15, 0, 0x50u);
    v16 = 0;
  }
  v36 = v16;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, STRSAFE_PCNZWCH **, __int64 *, int))(v11 + 176))(
          *(_QWORD *)(v11 + 296),
          a3,
          &v33,
          &v36,
          a6);
  v19 = v18;
  if ( v18 )
  {
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1275);
    v13 = NormalizeNteStatus(v19);
    goto LABEL_53;
  }
  pcchLength = 0;
  pullResult = 0;
  pulResult = 0;
  v20 = (wchar_t **)MSCryptAlloc(24);
  if ( v20 )
  {
    v23 = v33;
    *(_OWORD *)v20 = *(_OWORD *)v33;
    v20[2] = (wchar_t *)v23[2];
    v20[1] = 0;
    *v20 = 0;
    v21 = StringCchLengthW(*v33, 0x200u, &pcchLength);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1321;
      goto LABEL_47;
    }
    v25 = pcchLength;
    v21 = ULongLongMult(pcchLength + 1, 2u, &pullResult);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1330;
      goto LABEL_47;
    }
    v21 = ULongLongToULong(pullResult, &pulResult);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1339;
      goto LABEL_47;
    }
    v26 = (wchar_t *)MSCryptAlloc(pulResult);
    *v20 = v26;
    if ( !v26 )
    {
      v13 = -2146893810;
      v24 = "hr";
      v22 = 1349;
      goto LABEL_47;
    }
    v21 = StringCchCopyW(v26, v25 + 1, *v33);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1357;
      goto LABEL_47;
    }
    v21 = StringCchLengthW(v33[1], 0x200u, &pcchLength);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1369;
      goto LABEL_47;
    }
    v27 = pcchLength;
    v21 = ULongLongMult(pcchLength + 1, 2u, &pullResult);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1378;
      goto LABEL_47;
    }
    v21 = ULongLongToULong(pullResult, &pulResult);
    if ( v21 < 0 )
    {
      v13 = -2146893792;
      v24 = "hr";
      v22 = 1387;
      goto LABEL_47;
    }
    v28 = (wchar_t *)MSCryptAlloc(pulResult);
    v20[1] = v28;
    if ( v28 )
    {
      v21 = StringCchCopyW(v28, v27 + 1, v33[1]);
      if ( v21 < 0 )
      {
        v13 = -2146893792;
        v24 = "hr";
        v22 = 1405;
        goto LABEL_47;
      }
      if ( v6 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v11 + 8));
        v6[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v11;
        *(_QWORD *)&v6[1].LockCount = v36;
        RtlInitializeCriticalSection(v6);
        SrvAddMemoryBufferToList(a1, v6, a5);
        v6 = 0;
      }
      else if ( v36 != *(_QWORD *)(v7 + 48) )
      {
        v13 = -2146893792;
        v21 = -2146893792;
        v22 = 1423;
        goto LABEL_46;
      }
      v13 = 0;
      *v38 = v20;
      goto LABEL_53;
    }
    v13 = -2146893810;
    v21 = -2146893810;
    v22 = 1397;
  }
  else
  {
    v13 = -2146893810;
    v21 = -2146893810;
    v22 = 1305;
  }
LABEL_46:
  v24 = "Status";
LABEL_47:
  DebugTraceError((unsigned int)v21, v24, "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v22);
  if ( v20 )
  {
    v29 = v20[1];
    if ( v29 )
      MSCryptFree(v29);
    if ( *v20 )
      MSCryptFree(*v20);
    MSCryptFree(v20);
  }
LABEL_53:
  if ( v33 )
  {
    v30 = (*(__int64 (**)(void))(v11 + 136))();
    if ( v30 < 0 && v13 >= 0 )
      v13 = NormalizeNteStatus((unsigned int)v30);
  }
  if ( v6 )
    SrvCryptLocalFree(v6);
  if ( v7 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v7);
  if ( v11 )
  {
    v31 = SrvDereferenceProvider(v11);
    if ( v31 < 0 && v13 >= 0 )
      return (unsigned int)v31;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000e6a0  mov     [rsp-38h+arg_8], rbx
0x18000e6a5  mov     [rsp-38h+arg_18], r9
0x18000e6aa  push    rbp
0x18000e6ab  push    rsi
0x18000e6ac  push    rdi
0x18000e6ad  push    r12
0x18000e6af  push    r13
0x18000e6b1  push    r14
0x18000e6b3  push    r15
0x18000e6b5  mov     rbp, rsp
0x18000e6b8  sub     rsp, 50h
0x18000e6bc  xor     r14d, r14d
0x18000e6bf  xor     r13d, r13d
0x18000e6c2  mov     [rbp+var_8], r14
0x18000e6c6  mov     rbx, r9
0x18000e6c9  mov     [rbp+var_20], r14
0x18000e6cd  mov     rdi, r8
0x18000e6d0  mov     r12, rcx
0x18000e6d3  test    rcx, rcx
0x18000e6d6  jnz     short loc_18000E703
0x18000e6d8  xor     r15d, r15d
0x18000e6db  mov     r9d, 4B5h
0x18000e6e1  mov     ebx, 80090026h
0x18000e6e6  mov     ecx, 80090026h
0x18000e6eb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e6f2  lea     rdx, aStatus; "Status"
0x18000e6f9  call    DebugTraceError
0x18000e6fe  jmp     loc_18000EAC4
0x18000e703  xor     r8d, r8d
0x18000e706  call    SrvLookupAndReferenceProvider
0x18000e70b  mov     r15, rax
0x18000e70e  test    rax, rax
0x18000e711  jnz     short loc_18000E71B
0x18000e713  mov     r9d, 4BEh
0x18000e719  jmp     short loc_18000E6E1
0x18000e71b  test    rbx, rbx
0x18000e71e  jz      loc_18000EA75
0x18000e724  mov     rax, [rbp+arg_20]
0x18000e728  test    rax, rax
0x18000e72b  jz      loc_18000EA75
0x18000e731  mov     rdx, [rax]
0x18000e734  test    rdx, rdx
0x18000e737  jnz     short loc_18000E76E
0x18000e739  lea     ebx, [rdx+50h]
0x18000e73c  mov     ecx, ebx
0x18000e73e  call    MSCryptAlloc
0x18000e743  mov     r14, rax
0x18000e746  test    rax, rax
0x18000e749  jnz     short loc_18000E75D
0x18000e74b  mov     ebx, 8009000Eh
0x18000e750  mov     r9d, 4D6h
0x18000e756  mov     ecx, 8009000Eh
0x18000e75b  jmp     short loc_18000E6EB
0x18000e75d  mov     r8, rbx; Size
0x18000e760  xor     edx, edx; Val
0x18000e762  mov     rcx, rax; void *
0x18000e765  call    memset_0
0x18000e76a  xor     eax, eax
0x18000e76c  jmp     short loc_18000E79A
0x18000e76e  xor     r8d, r8d
0x18000e771  mov     rcx, r12
0x18000e774  call    SrvLookupMemoryBufferFromList
0x18000e779  mov     r13, rax
0x18000e77c  test    rax, rax
0x18000e77f  jnz     short loc_18000E796
0x18000e781  mov     ebx, 80090027h
0x18000e786  mov     r9d, 4E7h
0x18000e78c  mov     ecx, 80090027h
0x18000e791  jmp     loc_18000E6EB
0x18000e796  mov     rax, [rax+30h]
0x18000e79a  mov     ecx, [rbp+arg_28]
0x18000e79d  lea     r9, [rbp+var_8]
0x18000e7a1  mov     [rbp+var_8], rax
0x18000e7a5  lea     r8, [rbp+var_20]
0x18000e7a9  mov     rax, [r15+0B0h]
0x18000e7b0  mov     rdx, rdi
0x18000e7b3  mov     [rsp+50h+var_30], ecx
0x18000e7b7  mov     rcx, [r15+128h]
0x18000e7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c3  mov     ebx, eax
0x18000e7c5  test    eax, eax
0x18000e7c7  jz      short loc_18000E7F2
0x18000e7c9  mov     r9d, 4FBh
0x18000e7cf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e7d6  lea     rdx, aStatus; "Status"
0x18000e7dd  mov     ecx, eax
0x18000e7df  call    DebugTraceError
0x18000e7e4  mov     ecx, ebx
0x18000e7e6  call    NormalizeNteStatus
0x18000e7eb  mov     ebx, eax
0x18000e7ed  jmp     loc_18000EAC4
0x18000e7f2  mov     ecx, 18h
0x18000e7f7  mov     [rbp+pcchLength], 0
0x18000e7ff  mov     [rbp+pullResult], 0
0x18000e807  mov     [rbp+pulResult], 0
0x18000e80e  call    MSCryptAlloc
0x18000e813  mov     rsi, rax
0x18000e816  test    rax, rax
0x18000e819  jnz     short loc_18000E830
0x18000e81b  mov     ebx, 8009000Eh
0x18000e820  mov     edi, 8009000Eh
0x18000e825  mov     r9d, 519h
0x18000e82b  jmp     loc_18000EA87
0x18000e830  mov     rax, [rbp+var_20]
0x18000e834  lea     r8, [rbp+pcchLength]; pcchLength
0x18000e838  mov     edx, 200h; cchMax
0x18000e83d  movups  xmm0, xmmword ptr [rax]
0x18000e840  movups  xmmword ptr [rsi], xmm0
0x18000e843  movsd   xmm1, qword ptr [rax+10h]
0x18000e848  movsd   qword ptr [rsi+10h], xmm1
0x18000e84d  mov     qword ptr [rsi+8], 0
0x18000e855  mov     qword ptr [rsi], 0
0x18000e85c  mov     rcx, [rbp+var_20]
0x18000e860  mov     rcx, [rcx]; psz
0x18000e863  call    StringCchLengthW
0x18000e868  mov     edi, eax
0x18000e86a  test    eax, eax
0x18000e86c  jns     short loc_18000E885
0x18000e86e  mov     ebx, 80090020h
0x18000e873  lea     rdx, aHr; "hr"
0x18000e87a  mov     r9d, 529h
0x18000e880  jmp     loc_18000EA8E
0x18000e885  mov     rbx, [rbp+pcchLength]
0x18000e889  lea     r8, [rbp+pullResult]; pullResult
0x18000e88d  mov     edx, 2; ullMultiplier
0x18000e892  lea     rcx, [rbx+1]; ullMultiplicand
0x18000e896  call    ULongLongMult
0x18000e89b  mov     edi, eax
0x18000e89d  test    eax, eax
0x18000e89f  jns     short loc_18000E8B8
0x18000e8a1  mov     ebx, 80090020h
0x18000e8a6  lea     rdx, aHr; "hr"
0x18000e8ad  mov     r9d, 532h
0x18000e8b3  jmp     loc_18000EA8E
0x18000e8b8  mov     rcx, [rbp+pullResult]; ullOperand
0x18000e8bc  lea     rdx, [rbp+pulResult]; pulResult
0x18000e8c0  call    ULongLongToULong
0x18000e8c5  mov     edi, eax
0x18000e8c7  test    eax, eax
0x18000e8c9  jns     short loc_18000E8E2
0x18000e8cb  mov     ebx, 80090020h
0x18000e8d0  lea     rdx, aHr; "hr"
0x18000e8d7  mov     r9d, 53Bh
0x18000e8dd  jmp     loc_18000EA8E
0x18000e8e2  mov     ecx, [rbp+pulResult]
0x18000e8e5  call    MSCryptAlloc
0x18000e8ea  mov     [rsi], rax
0x18000e8ed  test    rax, rax
0x18000e8f0  jnz     short loc_18000E909
0x18000e8f2  mov     ebx, 8009000Eh
0x18000e8f7  lea     rdx, aHr; "hr"
0x18000e8fe  mov     r9d, 545h
0x18000e904  jmp     loc_18000EA8E
0x18000e909  mov     r8, [rbp+var_20]
0x18000e90d  lea     rdx, [rbx+1]; cchDest
0x18000e911  mov     rcx, rax; pszDest
0x18000e914  mov     r8, [r8]; pszSrc
0x18000e917  call    StringCchCopyW
0x18000e91c  mov     edi, eax
0x18000e91e  test    eax, eax
0x18000e920  jns     short loc_18000E939
0x18000e922  mov     ebx, 80090020h
0x18000e927  lea     rdx, aHr; "hr"
0x18000e92e  mov     r9d, 54Dh
0x18000e934  jmp     loc_18000EA8E
0x18000e939  mov     rcx, [rbp+var_20]
0x18000e93d  lea     r8, [rbp+pcchLength]; pcchLength
0x18000e941  mov     edx, 200h; cchMax
0x18000e946  mov     rcx, [rcx+8]; psz
0x18000e94a  call    StringCchLengthW
0x18000e94f  mov     edi, eax
0x18000e951  test    eax, eax
0x18000e953  jns     short loc_18000E96C
0x18000e955  mov     ebx, 80090020h
0x18000e95a  lea     rdx, aHr; "hr"
0x18000e961  mov     r9d, 559h
0x18000e967  jmp     loc_18000EA8E
0x18000e96c  mov     rbx, [rbp+pcchLength]
0x18000e970  lea     r8, [rbp+pullResult]; pullResult
0x18000e974  mov     edx, 2; ullMultiplier
0x18000e979  lea     rcx, [rbx+1]; ullMultiplicand
0x18000e97d  call    ULongLongMult
0x18000e982  mov     edi, eax
0x18000e984  test    eax, eax
0x18000e986  jns     short loc_18000E99F
0x18000e988  mov     ebx, 80090020h
0x18000e98d  lea     rdx, aHr; "hr"
0x18000e994  mov     r9d, 562h
0x18000e99a  jmp     loc_18000EA8E
0x18000e99f  mov     rcx, [rbp+pullResult]; ullOperand
0x18000e9a3  lea     rdx, [rbp+pulResult]; pulResult
0x18000e9a7  call    ULongLongToULong
0x18000e9ac  mov     edi, eax
0x18000e9ae  test    eax, eax
0x18000e9b0  jns     short loc_18000E9C9
0x18000e9b2  mov     ebx, 80090020h
0x18000e9b7  lea     rdx, aHr; "hr"
0x18000e9be  mov     r9d, 56Bh
0x18000e9c4  jmp     loc_18000EA8E
0x18000e9c9  mov     ecx, [rbp+pulResult]
0x18000e9cc  call    MSCryptAlloc
0x18000e9d1  mov     [rsi+8], rax
0x18000e9d5  test    rax, rax
0x18000e9d8  jnz     short loc_18000E9EF
0x18000e9da  mov     ebx, 8009000Eh
0x18000e9df  mov     edi, 8009000Eh
0x18000e9e4  mov     r9d, 575h
0x18000e9ea  jmp     loc_18000EA87
0x18000e9ef  mov     r8, [rbp+var_20]
0x18000e9f3  lea     rdx, [rbx+1]; cchDest
0x18000e9f7  mov     rcx, rax; pszDest
0x18000e9fa  mov     r8, [r8+8]; pszSrc
0x18000e9fe  call    StringCchCopyW
0x18000ea03  mov     edi, eax
0x18000ea05  test    eax, eax
0x18000ea07  jns     short loc_18000EA1D
0x18000ea09  mov     ebx, 80090020h
0x18000ea0e  lea     rdx, aHr; "hr"
0x18000ea15  mov     r9d, 57Dh
0x18000ea1b  jmp     short loc_18000EA8E
0x18000ea1d  test    r14, r14
0x18000ea20  jnz     short loc_18000EA3E
0x18000ea22  mov     rax, [r13+30h]
0x18000ea26  cmp     [rbp+var_8], rax
0x18000ea2a  jz      short loc_18000EA6A
0x18000ea2c  mov     ebx, 80090020h
0x18000ea31  mov     edi, 80090020h
0x18000ea36  mov     r9d, 58Fh
0x18000ea3c  jmp     short loc_18000EA87
0x18000ea3e  lock inc qword ptr [r15+8]
0x18000ea43  mov     [r14+28h], r15
0x18000ea47  mov     rcx, r14; CriticalSection
0x18000ea4a  mov     rax, [rbp+var_8]
0x18000ea4e  mov     [r14+30h], rax
0x18000ea52  call    cs:__imp_RtlInitializeCriticalSection
0x18000ea58  mov     r8, [rbp+arg_20]
0x18000ea5c  mov     rdx, r14
0x18000ea5f  mov     rcx, r12
0x18000ea62  call    SrvAddMemoryBufferToList
0x18000ea67  xor     r14d, r14d
0x18000ea6a  mov     rax, [rbp+arg_18]
0x18000ea6e  xor     ebx, ebx
0x18000ea70  mov     [rax], rsi
0x18000ea73  jmp     short loc_18000EAC4
0x18000ea75  xor     esi, esi
0x18000ea77  mov     ebx, 80090027h
0x18000ea7c  mov     edi, 80090027h
0x18000ea81  mov     r9d, 4C5h
0x18000ea87  lea     rdx, aStatus; "Status"
0x18000ea8e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ea95  mov     ecx, edi
0x18000ea97  call    DebugTraceError
0x18000ea9c  test    rsi, rsi
0x18000ea9f  jz      short loc_18000EAC4
0x18000eaa1  mov     rcx, [rsi+8]
0x18000eaa5  test    rcx, rcx
0x18000eaa8  jz      short loc_18000EAAF
0x18000eaaa  call    MSCryptFree
0x18000eaaf  mov     rcx, [rsi]
0x18000eab2  test    rcx, rcx
0x18000eab5  jz      short loc_18000EABC
0x18000eab7  call    MSCryptFree
0x18000eabc  mov     rcx, rsi
0x18000eabf  call    MSCryptFree
0x18000eac4  mov     rcx, [rbp+var_20]
0x18000eac8  test    rcx, rcx
0x18000eacb  jz      short loc_18000EAEA
0x18000eacd  mov     rax, [r15+88h]
0x18000ead4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead9  test    eax, eax
0x18000eadb  jns     short loc_18000EAEA
0x18000eadd  test    ebx, ebx
0x18000eadf  js      short loc_18000EAEA
0x18000eae1  mov     ecx, eax
0x18000eae3  call    NormalizeNteStatus
0x18000eae8  mov     ebx, eax
0x18000eaea  test    r14, r14
0x18000eaed  jz      short loc_18000EAF7
0x18000eaef  mov     rcx, r14; P
0x18000eaf2  call    SrvCryptLocalFree
0x18000eaf7  test    r13, r13
0x18000eafa  jz      short loc_18000EB05
0x18000eafc  mov     rcx, r13; CriticalSection
0x18000eaff  call    cs:__imp_RtlLeaveCriticalSection
0x18000eb05  test    r15, r15
0x18000eb08  jz      short loc_18000EB1B
0x18000eb0a  mov     rcx, r15
0x18000eb0d  call    SrvDereferenceProvider
0x18000eb12  test    eax, eax
0x18000eb14  jns     short loc_18000EB1B
0x18000eb16  test    ebx, ebx
0x18000eb18  cmovns  ebx, eax
0x18000eb1b  mov     eax, ebx
0x18000eb1d  mov     rbx, [rsp+50h+arg_8]
0x18000eb25  add     rsp, 50h
0x18000eb29  pop     r15
0x18000eb2b  pop     r14
0x18000eb2d  pop     r13
0x18000eb2f  pop     r12
0x18000eb31  pop     rdi
  ... truncated ...
```
