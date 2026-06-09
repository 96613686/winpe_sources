# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x18005b480`
- end: `0x18005bbac`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `1836`
- prototype: `__int64 __usercall@<rax>(const struct Common::StateSeparationRedirectionMapping *@<rcx>, const unsigned __int16 **@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct Common::RegistryKey *)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019df0`
- `0x18005bbc0`
- `0x1800c9a00`

## callees

- `0x1800116ec`
- `0x1800393f0`
- `0x18004cc30`
- `0x18004ce20`
- `0x180056dc0`
- `0x180057fa4`
- `0x180058da8`
- `0x18005b2c4`
- `0x18005b2f0`
- `0x18005b400`
- `0x18005b480`
- `0x18005ca00`
- `0x18005e040`
- `0x18005e320`
- `0x1800ad890`
- `0x180194eb9`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18005b4d1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005b8d2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005b4d1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18005b8d2`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005b4aa`
- `ntdll!RtlAcquireSRWLockShared` at `0x18005b4aa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b8e5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b8e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b924`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b924`
- `ntdll!RtlFreeHeap` at `0x18005b5d0`
- `ntdll!RtlFreeHeap` at `0x18005b67b`
- `ntdll!RtlFreeHeap` at `0x18005b5d0`
- `ntdll!RtlFreeHeap` at `0x18005b67b`

## string_xrefs

- `0x18005b8fc`: `ntdll.dll`
- `0x18005b544`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005b781`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005b791`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005b87e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005b896`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005bb8e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18005b9c8`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x18005b5aa`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18005b9a0`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18005b9e0`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18005ba7f`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18005bb52`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetRegKeyContainingValue(
        const struct Common::StateSeparationRedirectionMapping *a1,
        const unsigned __int16 **a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        HANDLE *a6)
{
  char v9; // di
  const WCHAR *v10; // r15
  const WCHAR *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // r14
  unsigned int v15; // eax
  __int64 result; // rax
  __int64 i; // rbx
  PHANDLE v18; // rdi
  const WCHAR *v19; // rbx
  int v20; // eax
  unsigned int j; // edi
  int v22; // eax
  unsigned int v23; // r8d
  PHANDLE v24; // rdi
  int v25; // eax
  signed int v26; // ecx
  __int64 v27; // r9
  __int64 v28; // rdx
  int PersistedRegKeyPath; // eax
  unsigned int v30; // ebx
  WCHAR *v31; // rbx
  int v32; // eax
  unsigned int v33; // edi
  HKEY v34; // rcx
  int v35; // eax
  HMODULE Library; // rax
  HMODULE v37; // rbx
  __int64 (*RtlIsStateSeparationEnabled)(void); // rax
  char v39; // al
  int appended; // eax
  unsigned int v41; // edi
  void *v42; // rcx
  LSTATUS Value; // eax
  HKEY v44; // rdi
  HKEY v45; // rcx
  HKEY v46; // rdx
  bool v47; // sf
  int lpData; // [rsp+20h] [rbp-40h]
  int lpDataa; // [rsp+20h] [rbp-40h]
  int lpDatab; // [rsp+20h] [rbp-40h]
  int lpDatac; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-18h]
  PCWSTR SourceString; // [rsp+50h] [rbp-10h] BYREF
  PHANDLE v56; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v56 = a6;
  RtlAcquireSRWLockShared(&qword_1803A7518);
  if ( byte_1803A7514 )
  {
    v9 = byte_1803A7515;
    RtlReleaseSRWLockShared(&qword_1803A7518);
  }
  else
  {
    RtlReleaseSRWLockShared(&qword_1803A7518);
    RtlAcquireSRWLockExclusive(&qword_1803A7518);
    if ( !byte_1803A7514 && (Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u), (v37 = Library) != 0) )
    {
      RtlIsStateSeparationEnabled = GetProcAddress(Library, "RtlIsStateSeparationEnabled");
      if ( RtlIsStateSeparationEnabled )
      {
        v39 = RtlIsStateSeparationEnabled();
        byte_1803A7514 = 1;
        v9 = v39 != 0;
        byte_1803A7515 = v39 != 0;
      }
      else
      {
        v9 = byte_1803A7515;
      }
      FreeLibrary(v37);
    }
    else
    {
      v9 = byte_1803A7515;
    }
    RtlReleaseSRWLockExclusive(&qword_1803A7518);
  }
  if ( !v9 )
    goto LABEL_4;
  SourceString = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, a2, 1u, (unsigned __int16 **)&SourceString);
  v30 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      lpData);
    Common::GlobalHeap::Free((void *)SourceString);
    return v30;
  }
  v31 = (WCHAR *)SourceString;
  hKey = 0;
  v32 = Common::RegistryKey::Open((PHANDLE)&hKey, HKEY_LOCAL_MACHINE, SourceString, a5 | 0x20019);
  v33 = v32;
  if ( v32 <= -2147024895 || (unsigned int)(v32 + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)v32,
      lpData);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)v33,
      lpDatac);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    goto LABEL_79;
  }
  v34 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    Value = RegQueryValueExW(hKey, a4, 0, 0, 0, 0);
    v33 = Value;
    if ( !Value || Value == 234 )
    {
      v44 = hKey;
      v45 = 0;
      v46 = (HKEY)*a6;
      hKey = 0;
      if ( v46 != v44 )
      {
        if ( (unsigned __int64)v46 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          RegCloseKey(v46);
          v45 = hKey;
        }
        *a6 = v44;
      }
      if ( (unsigned __int64)v45 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(v45);
      Common::GlobalHeap::Free(v31);
      return 0;
    }
    if ( (unsigned int)(Value - 2) <= 1 )
      goto LABEL_93;
    v47 = Value < 0;
    if ( Value > 0 )
    {
      v33 = (unsigned __int16)Value | 0x80070000;
      v47 = 1;
    }
    if ( !v47 )
    {
LABEL_93:
      v34 = hKey;
      goto LABEL_61;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)v33,
      lpData);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
LABEL_79:
    Common::GlobalHeap::Free(v31);
    return v33;
  }
LABEL_61:
  if ( (unsigned __int64)v34 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v34);
  Common::GlobalHeap::Free(v31);
LABEL_4:
  v10 = (const WCHAR *)*((_QWORD *)a1 + 1);
  if ( !a2 )
  {
    v24 = v56;
    if ( (char *)*v56 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      RegCloseKey((HKEY)*v56);
    *v24 = 0;
    v25 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v10, v24, 0);
    v26 = v25;
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    result = 0;
    if ( v26 < 0 )
      return (unsigned int)v26;
    return result;
  }
  v54 = 0;
  *(_OWORD *)P = 0;
  if ( !v10 )
  {
    LODWORD(P[0]) = 0;
LABEL_22:
    for ( i = 0; !i && *a2; i = 1 )
    {
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)P, *a2);
      v41 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          lpData);
        if ( P[1] )
          Common::GlobalHeap::Free(P[1]);
        return v41;
      }
    }
    v18 = v56;
    v19 = (const WCHAR *)P[1];
    if ( (char *)*v56 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      RegCloseKey((HKEY)*v56);
    *v18 = 0;
    v20 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v19, v18, 0);
    v13 = v20;
    if ( v20 > 0 )
      v13 = (unsigned __int16)v20 | 0x80070000;
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( !P[1] )
        return v13;
      Common::GlobalHeap::Free(P[1]);
      return v13;
    }
    else
    {
      if ( P[1] )
        RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
      return 0;
    }
  }
  v11 = v10;
  v12 = 1073741822;
  while ( *v11 )
  {
    ++v11;
    if ( !--v12 )
    {
      v13 = -2147024809;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        lpData);
      goto LABEL_18;
    }
  }
  v14 = (unsigned int)(1073741822 - v12);
  if ( (unsigned int)v14 > 0x7FFFFFFF )
  {
    v13 = -2147024362;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070216LL,
      lpData);
  }
  else
  {
    if ( !(_DWORD)v14 )
      goto LABEL_12;
    if ( (unsigned int)v14 <= 0x20 )
    {
      for ( j = 8; j < (unsigned int)v14; j *= 2 )
        ;
    }
    else
    {
      j = 1073741822 - v12;
    }
    if ( j > 0x3FFFFFFF )
    {
      v13 = -2147023613;
      v28 = 425;
      v27 = 2147943683LL;
    }
    else
    {
      if ( !j )
      {
        v42 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        P[1] = v42;
        if ( v42 )
        {
          Common::GlobalHeap::Free(v42);
          P[1] = 0;
          LODWORD(P[0]) = 0;
        }
        v23 = 0;
        v54 = 0;
        goto LABEL_43;
      }
      SourceString = 0;
      v22 = CommonHeapReAllocDefault(P[1], 0, 2LL * (j + 1), (void **)&SourceString);
      v13 = v22;
      if ( v22 >= 0 )
      {
        v23 = j + 1;
        P[1] = (PVOID)SourceString;
        v54 = j + 1;
        if ( LODWORD(P[0]) > j )
        {
          LODWORD(P[0]) = j;
          SourceString[j] = 0;
          goto LABEL_42;
        }
        if ( LODWORD(P[0]) < j && !LODWORD(P[0]) )
        {
          *SourceString = 0;
LABEL_42:
          v23 = v54;
        }
LABEL_43:
        if ( v23 )
        {
          v15 = v23 - 1;
          goto LABEL_13;
        }
LABEL_12:
        v15 = 0;
LABEL_13:
        if ( (unsigned int)v14 <= v15
          || (v35 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)P, v14), v13 = v35, v35 >= 0) )
        {
          LODWORD(P[0]) = v14;
          if ( (_DWORD)v14 )
            *((_WORD *)P[1] + v14) = 0;
          memcpy_0(P[1], v10, (unsigned int)(2 * v14));
          v13 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v35,
            lpData);
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)v13,
            lpDatab);
        }
        goto LABEL_17;
      }
      v27 = (unsigned int)v22;
      v28 = 458;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v27,
      lpData);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v13,
      lpDataa);
  }
LABEL_17:
  if ( (v13 & 0x80000000) == 0 )
    goto LABEL_22;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)v13,
    lpData);
  if ( P[1] )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
  return v13;
}

```

## disassembly

```asm
0x18005b480  push    rbp
0x18005b482  push    rbx
0x18005b483  push    rsi
0x18005b484  push    rdi
0x18005b485  push    r13
0x18005b487  push    r14
0x18005b489  push    r15
0x18005b48b  mov     rbp, rsp
0x18005b48e  sub     rsp, 60h
0x18005b492  mov     r15, [rbp+arg_28]
0x18005b496  mov     rsi, rcx
0x18005b499  lea     rcx, qword_1803A7518
0x18005b4a0  mov     [rbp+var_8], r15
0x18005b4a4  mov     r14, r9
0x18005b4a7  mov     r13, rdx
0x18005b4aa  call    cs:__imp_RtlAcquireSRWLockShared
0x18005b4b1  nop     dword ptr [rax+rax+00h]
0x18005b4b6  cmp     cs:byte_1803A7514, 0
0x18005b4bd  lea     rcx, qword_1803A7518
0x18005b4c4  jz      loc_18005B8D2
0x18005b4ca  movzx   edi, cs:byte_1803A7515
0x18005b4d1  call    cs:__imp_RtlReleaseSRWLockShared
0x18005b4d8  nop     dword ptr [rax+rax+00h]
0x18005b4dd  mov     [rsp+60h+arg_10], r12
0x18005b4e5  test    dil, dil
0x18005b4e8  jnz     loc_18005B7C4
0x18005b4ee  mov     r12d, [rbp+arg_20]
0x18005b4f2  or      r12d, 20019h
0x18005b4f9  mov     r15, [rsi+8]
0x18005b4fd  test    r13, r13
0x18005b500  jz      loc_18005B71B
0x18005b506  xor     r8d, r8d
0x18005b509  xor     eax, eax
0x18005b50b  mov     [rbp+var_18], r8d
0x18005b50f  xorps   xmm0, xmm0
0x18005b512  movups  xmmword ptr [rbp+P], xmm0
0x18005b516  test    r15, r15
0x18005b519  jz      loc_18005B5F6
0x18005b51f  mov     r14d, 3FFFFFFEh
0x18005b525  mov     rax, r15
0x18005b528  mov     ecx, r14d
0x18005b52b  nop     dword ptr [rax+rax+00h]
0x18005b530  cmp     [rax], r8w
0x18005b534  jz      short loc_18005B55F
0x18005b536  add     rax, 2
0x18005b53a  sub     rcx, 1
0x18005b53e  jnz     short loc_18005B530
0x18005b540  mov     rcx, [rbp+38h]; this
0x18005b544  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18005b54b  mov     ebx, 80070057h
0x18005b550  mov     edx, 249h; void *
0x18005b555  mov     r9d, ebx; char *
0x18005b558  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b55d  jmp     short loc_18005B5A6
0x18005b55f  sub     r14d, ecx
0x18005b562  cmp     r14d, 7FFFFFFFh
0x18005b569  ja      loc_18005BB8A
0x18005b56f  test    r14d, r14d
0x18005b572  jnz     loc_18005B68E
0x18005b578  xor     eax, eax
0x18005b57a  cmp     r14d, eax
0x18005b57d  ja      loc_18005B864
0x18005b583  mov     dword ptr [rbp+P], r14d
0x18005b587  test    r14d, r14d
0x18005b58a  jnz     loc_18005B98C
0x18005b590  mov     rcx, [rbp+P+8]; void *
0x18005b594  lea     r8d, [r14+r14]; Size
0x18005b598  mov     rdx, r15; Src
0x18005b59b  call    memcpy_0
0x18005b5a0  xor     ebx, ebx
0x18005b5a2  test    ebx, ebx
0x18005b5a4  jns     short loc_18005B5F9
0x18005b5a6  mov     rcx, [rbp+38h]; this
0x18005b5aa  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\common\\states"...
0x18005b5b1  mov     r9d, ebx; char *
0x18005b5b4  mov     edx, 0A7h; void *
0x18005b5b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b5be  mov     r8, [rbp+P+8]; P
0x18005b5c2  test    r8, r8
0x18005b5c5  jz      short loc_18005B5DC
0x18005b5c7  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18005b5ce  xor     edx, edx; Flags
0x18005b5d0  call    cs:__imp_RtlFreeHeap
0x18005b5d7  nop     dword ptr [rax+rax+00h]
0x18005b5dc  mov     eax, ebx
0x18005b5de  mov     r12, [rsp+60h+arg_10]
0x18005b5e6  add     rsp, 60h
0x18005b5ea  pop     r15
0x18005b5ec  pop     r14
0x18005b5ee  pop     r13
0x18005b5f0  pop     rdi
0x18005b5f1  pop     rsi
0x18005b5f2  pop     rbx
0x18005b5f3  pop     rbp
0x18005b5f4  retn
0x18005b5f6  mov     dword ptr [rbp+P], eax
0x18005b5f9  xor     ebx, ebx
0x18005b5fb  cmp     rbx, 1
0x18005b5ff  jnb     short loc_18005B60F
0x18005b601  mov     rdx, [r13+rbx*8+0]; unsigned __int16 *
0x18005b606  test    rdx, rdx
0x18005b609  jnz     loc_18005BA15
0x18005b60f  mov     rdi, [rbp+var_8]
0x18005b613  mov     rbx, [rbp+P+8]
0x18005b617  mov     rcx, [rdi]; hKey
0x18005b61a  lea     rax, [rcx-1]
0x18005b61e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b622  jbe     loc_18005B711
0x18005b628  mov     [rsp+60h+lpcbData], 0; __int64
0x18005b631  mov     r9d, r12d
0x18005b634  xor     r8d, r8d
0x18005b637  mov     [rsp+60h+lpData], rdi; PHANDLE
0x18005b63c  mov     rdx, rbx; SourceString
0x18005b63f  mov     qword ptr [rdi], 0
0x18005b646  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b64d  call    RegOpenKeyExInternalW
0x18005b652  mov     ebx, eax
0x18005b654  test    eax, eax
0x18005b656  jle     short loc_18005B661
0x18005b658  movzx   ebx, ax
0x18005b65b  or      ebx, 80070000h
0x18005b661  test    ebx, ebx
0x18005b663  js      loc_18005B8AF
0x18005b669  mov     r8, [rbp+P+8]; P
0x18005b66d  test    r8, r8
0x18005b670  jz      short loc_18005B687
0x18005b672  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18005b679  xor     edx, edx; Flags
0x18005b67b  call    cs:__imp_RtlFreeHeap
0x18005b682  nop     dword ptr [rax+rax+00h]
0x18005b687  xor     eax, eax
0x18005b689  jmp     loc_18005B5DE
0x18005b68e  cmp     r14d, 20h ; ' '
0x18005b692  jbe     loc_18005B7AA
0x18005b698  mov     edi, r14d
0x18005b69b  cmp     edi, 3FFFFFFFh
0x18005b6a1  ja      loc_18005B97A
0x18005b6a7  test    edi, edi
0x18005b6a9  jz      loc_18005BA38
0x18005b6af  lea     esi, [rdi+1]
0x18005b6b2  test    esi, esi
0x18005b6b4  jz      short loc_18005B6FF
0x18005b6b6  mov     rcx, [rbp+P+8]; Ptr
0x18005b6ba  lea     r9, [rbp+SourceString]; void **
0x18005b6be  mov     [rbp+SourceString], r8
0x18005b6c2  xor     edx, edx; unsigned __int64
0x18005b6c4  mov     r8d, esi
0x18005b6c7  add     r8, r8; unsigned __int64
0x18005b6ca  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x18005b6cf  mov     ebx, eax
0x18005b6d1  test    eax, eax
0x18005b6d3  js      loc_18005B775
0x18005b6d9  mov     rdx, [rbp+SourceString]
0x18005b6dd  mov     r8d, esi
0x18005b6e0  mov     eax, dword ptr [rbp+P]
0x18005b6e3  mov     [rbp+P+8], rdx
0x18005b6e7  mov     [rbp+var_18], esi
0x18005b6ea  cmp     eax, edi
0x18005b6ec  ja      loc_18005BA6B
0x18005b6f2  jnb     short loc_18005B6FF
0x18005b6f4  test    eax, eax
0x18005b6f6  jnz     short loc_18005B6FF
0x18005b6f8  mov     [rdx], ax
0x18005b6fb  mov     r8d, [rbp+var_18]
0x18005b6ff  test    r8d, r8d
0x18005b702  jz      loc_18005B578
0x18005b708  lea     eax, [r8-1]
0x18005b70c  jmp     loc_18005B57A
0x18005b711  call    RegCloseKey
0x18005b716  jmp     loc_18005B628
0x18005b71b  mov     rdi, [rbp+var_8]
0x18005b71f  mov     rcx, [rdi]; hKey
0x18005b722  lea     rax, [rcx-1]
0x18005b726  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b72a  jbe     loc_18005B8C8
0x18005b730  mov     [rsp+60h+lpcbData], 0; __int64
0x18005b739  mov     r9d, r12d
0x18005b73c  xor     r8d, r8d
0x18005b73f  mov     [rsp+60h+lpData], rdi; PHANDLE
0x18005b744  mov     rdx, r15; SourceString
0x18005b747  mov     qword ptr [rdi], 0
0x18005b74e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b755  call    RegOpenKeyExInternalW
0x18005b75a  mov     ecx, eax
0x18005b75c  test    eax, eax
0x18005b75e  jle     short loc_18005B769
0x18005b760  movzx   ecx, ax
0x18005b763  or      ecx, 80070000h
0x18005b769  xor     eax, eax
0x18005b76b  test    ecx, ecx
0x18005b76d  cmovs   eax, ecx
0x18005b770  jmp     loc_18005B5DE
0x18005b775  mov     r9d, eax; char *
0x18005b778  mov     edx, 1CAh; void *
0x18005b77d  mov     rcx, [rbp+38h]; this
0x18005b781  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18005b788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b78d  mov     rcx, [rbp+38h]; this
0x18005b791  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18005b798  mov     r9d, ebx; char *
0x18005b79b  mov     edx, 232h; void *
0x18005b7a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b7a5  jmp     loc_18005B5A2
0x18005b7aa  mov     edi, 8
0x18005b7af  cmp     r14d, edi
0x18005b7b2  jbe     loc_18005B69B
0x18005b7b8  add     edi, edi
0x18005b7ba  cmp     edi, r14d
0x18005b7bd  jb      short loc_18005B7B8
0x18005b7bf  jmp     loc_18005B69B
0x18005b7c4  lea     r9, [rbp+SourceString]; unsigned __int16 **
0x18005b7c8  mov     [rbp+SourceString], 0
0x18005b7d0  mov     r8d, 1; unsigned __int64
0x18005b7d6  mov     rdx, r13; unsigned __int16 **
0x18005b7d9  mov     rcx, rsi; struct Common::StateSeparationRedirectionMapping *
0x18005b7dc  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x18005b7e1  mov     ebx, eax
0x18005b7e3  test    eax, eax
0x18005b7e5  js      loc_18005B99C
0x18005b7eb  mov     r12d, [rbp+arg_20]
0x18005b7ef  lea     rcx, [rbp+hKey]; this
0x18005b7f3  mov     rbx, [rbp+SourceString]
0x18005b7f7  or      r12d, 20019h
0x18005b7fe  mov     r9d, r12d; unsigned int
0x18005b801  mov     [rbp+hKey], 0
0x18005b809  mov     r8, rbx; SourceString
0x18005b80c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18005b813  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18005b818  mov     edi, eax
0x18005b81a  cmp     eax, 80070001h
0x18005b81f  jle     loc_18005B9C4
0x18005b825  lea     ecx, [rax+7FF8FFFCh]
0x18005b82b  cmp     ecx, 7FF8FFFBh
0x18005b831  jbe     loc_18005B9C4
0x18005b837  mov     rcx, [rbp+hKey]; hKey
0x18005b83b  lea     rax, [rcx-1]
0x18005b83f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b843  jbe     loc_18005BAB2
0x18005b849  lea     rax, [rcx-1]
0x18005b84d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b851  jbe     loc_18005B970
0x18005b857  mov     rcx, rbx; void *
0x18005b85a  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005b85f  jmp     loc_18005B4F9
0x18005b864  mov     edx, r14d; unsigned int
0x18005b867  lea     rcx, [rbp+P]; this
0x18005b86b  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x18005b870  mov     ebx, eax
0x18005b872  test    eax, eax
0x18005b874  jns     loc_18005B583
0x18005b87a  mov     rcx, [rbp+38h]; this
0x18005b87e  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18005b885  mov     r9d, eax; char *
0x18005b888  mov     edx, 20Ch; void *
0x18005b88d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b892  mov     rcx, [rbp+38h]; this
0x18005b896  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18005b89d  mov     r9d, ebx; char *
0x18005b8a0  mov     edx, 235h; void *
0x18005b8a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b8aa  jmp     loc_18005B5A2
0x18005b8af  mov     rcx, [rbp+P+8]; void *
0x18005b8b3  test    rcx, rcx
0x18005b8b6  jz      loc_18005B5DC
0x18005b8bc  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18005b8c1  mov     eax, ebx
0x18005b8c3  jmp     loc_18005B5DE
0x18005b8c8  call    RegCloseKey
0x18005b8cd  jmp     loc_18005B730
0x18005b8d2  call    cs:__imp_RtlReleaseSRWLockShared
0x18005b8d9  nop     dword ptr [rax+rax+00h]
0x18005b8de  lea     rcx, qword_1803A7518
0x18005b8e5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005b8ec  nop     dword ptr [rax+rax+00h]
0x18005b8f1  cmp     cs:byte_1803A7514, 0
0x18005b8f8  jnz     short loc_18005B916
0x18005b8fa  xor     edx, edx; hFile
0x18005b8fc  lea     rcx, ModuleName; "ntdll.dll"
0x18005b903  mov     r8d, 800h; dwFlags
0x18005b909  call    LoadLibraryExW
0x18005b90e  mov     rbx, rax
0x18005b911  test    rax, rax
0x18005b914  jnz     short loc_18005B935
0x18005b916  movzx   edi, cs:byte_1803A7515
0x18005b91d  lea     rcx, qword_1803A7518
0x18005b924  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005b92b  nop     dword ptr [rax+rax+00h]
0x18005b930  jmp     loc_18005B4DD
0x18005b935  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18005b93c  mov     rcx, rbx; hModule
0x18005b93f  call    GetProcAddress
0x18005b944  test    rax, rax
0x18005b947  jz      loc_18005BA2C
0x18005b94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b952  test    al, al
0x18005b954  mov     cs:byte_1803A7514, 1
0x18005b95b  setnz   dil
0x18005b95f  mov     cs:byte_1803A7515, dil
0x18005b966  mov     rcx, rbx; hLibModule
0x18005b969  call    FreeLibrary
  ... truncated ...
```
