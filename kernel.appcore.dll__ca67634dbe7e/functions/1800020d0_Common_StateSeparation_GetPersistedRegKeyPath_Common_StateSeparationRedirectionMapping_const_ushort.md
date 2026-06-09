# Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)

- ea: `0x1800020d0`
- end: `0x180002730`
- name: `?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z`
- size: `1632`
- prototype: `static int(const struct Common::StateSeparationRedirectionMapping *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001ef0`
- `0x1800020d0`
- `0x180002740`
- `0x180002850`
- `0x1800029c0`
- `0x180002ad0`
- `0x1800058d0`
- `0x180006324`
- `0x1800064d0`
- `0x180009a9c`
- `0x180009b48`
- `0x180009c30`
- `0x180009c4c`
- `0x180009d92`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180002498`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000253b`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800025a4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002498`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000253b`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800025a4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000250f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000250f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002548`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002548`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002289`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800023d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002578`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025fa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002289`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800023d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002578`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025fa`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800026f2`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000269b`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000269b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800022ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800022ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000227c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800023ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000227c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800023ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800026e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000230b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000230b`

## string_xrefs

- `0x18000220c`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180002232`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000224e`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800023a9`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800023e8`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180002412`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000244a`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000255d`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180002589`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800025df`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x18000260b`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180002715`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x1800021f4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800022af`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800022c7`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800024b5`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800024ef`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800022e2`: `kernelbase.dll`
- `0x180002301`: `GetPersistedRegistryLocationW`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetPersistedRegKeyPath(
        const struct Common::StateSeparationRedirectionMapping *a1,
        unsigned __int16 **a2)
{
  int IsStateSeparationEnabled; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdi
  unsigned int i; // edx
  int v10; // eax
  unsigned int v11; // eax
  int v13; // eax
  HMODULE Library; // rax
  HMODULE v15; // rbx
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v17)(_QWORD, _QWORD, _QWORD, _QWORD); // rsi
  void *v18; // rdi
  unsigned int v19; // eax
  unsigned int v20; // esi
  void *v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  Common *v25; // rax
  unsigned __int16 **v26; // r8
  Common *v27; // rcx
  int CacheMapIfNeeded; // eax
  __int64 v29; // rcx
  unsigned int v30; // ebx
  Common *v31; // rax
  unsigned __int16 **v32; // r8
  int v33; // eax
  unsigned int v34; // ebx
  unsigned int v35; // edi
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  void *v39; // rsi
  void *v40; // r14
  unsigned __int16 **v41; // r8
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // [rsp+20h] [rbp-50h]
  int v45; // [rsp+20h] [rbp-50h]
  int v46; // [rsp+20h] [rbp-50h]
  void *Buffer[2]; // [rsp+30h] [rbp-40h] BYREF
  int v48; // [rsp+40h] [rbp-30h]
  void *v49[2]; // [rsp+48h] [rbp-28h] BYREF
  int v50; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  void *NewElement; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v53; // [rsp+A0h] [rbp+30h] BYREF

  NewElement = a1;
  LOBYTE(NewElement) = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&NewElement);
  v4 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      v44);
    return v4;
  }
  if ( (_BYTE)NewElement )
  {
    RtlAcquireSRWLockShared(&qword_180015738);
    if ( Table )
    {
      v25 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(
                        v24,
                        Common::StateSeparation::AdvertisingIdPolicy);
      if ( v25 )
      {
        v22 = Common::CopyStringToOutput(v25, (const unsigned __int16 *)a2, v26);
        v23 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x122,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v22,
            v44);
          RtlReleaseSRWLockShared(&qword_180015738);
          return v23;
        }
        RtlReleaseSRWLockShared(&qword_180015738);
        return 0;
      }
    }
    RtlReleaseSRWLockShared(&qword_180015738);
    RtlAcquireSRWLockExclusive(&qword_180015738);
    CacheMapIfNeeded = Common::CreateCacheMapIfNeeded(v27);
    v30 = CacheMapIfNeeded;
    if ( CacheMapIfNeeded < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)CacheMapIfNeeded,
        v44);
      RtlReleaseSRWLockExclusive(&qword_180015738);
      return v30;
    }
    v31 = (Common *)Common::GenericMap<unsigned short const *,unsigned short const *>::Find(
                      v29,
                      Common::StateSeparation::AdvertisingIdPolicy);
    if ( v31 )
    {
      v33 = Common::CopyStringToOutput(v31, (const unsigned __int16 *)a2, v32);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)v33,
          v44);
        RtlReleaseSRWLockExclusive(&qword_180015738);
        return v34;
      }
      goto LABEL_72;
    }
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v15 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetPersistedRegistryLocationW");
      v17 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
      if ( ProcAddress )
      {
        v53 = 0;
        v18 = 0;
        v19 = ((__int64 (__fastcall *)(unsigned __int16 *const, const wchar_t *, _QWORD, _QWORD))ProcAddress)(
                Common::StateSeparation::AdvertisingIdPolicy,
                L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo",
                0,
                0);
        if ( v19 == 234 )
        {
          NewElement = 0;
          Common::GlobalHeap::Alloc(v53, &NewElement);
          v18 = NewElement;
          if ( !NewElement )
          {
            v35 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14A,
              (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
              (const char *)0x8007000ELL,
              (int)&v53);
            goto LABEL_30;
          }
          Common::GlobalHeap::Free(0);
          v19 = v17(
                  Common::StateSeparation::AdvertisingIdPolicy,
                  L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo",
                  v18,
                  v53);
        }
        if ( v19 )
        {
          v20 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x153,
                  (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
                  (const char *)v19,
                  (unsigned int)&v53);
          Common::GlobalHeap::Free(v18);
          FreeLibrary(v15);
          RtlReleaseSRWLockExclusive(&qword_180015738);
          return v20;
        }
        *a2 = (unsigned __int16 *)v18;
        *(_OWORD *)Buffer = 0;
        v48 = 0;
        v36 = Common::StringBuffer::SetValueFromString(
                (Common::StringBuffer *)Buffer,
                Common::StateSeparation::AdvertisingIdPolicy);
        v35 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
            (const char *)(unsigned int)v36,
            (int)&v53);
          v21 = Buffer[1];
          if ( !Buffer[1] )
            goto LABEL_30;
        }
        else
        {
          v37 = *a2;
          v50 = 0;
          *(_OWORD *)v49 = 0;
          v38 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v49, v37);
          v35 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x15A,
              (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
              (const char *)(unsigned int)v38,
              (int)&v53);
            if ( v49[1] )
              Common::GlobalHeap::Free(v49[1]);
            v21 = Buffer[1];
            if ( !Buffer[1] )
              goto LABEL_30;
          }
          else
          {
            v39 = Buffer[1];
            v40 = v49[1];
            Buffer[0] = Buffer[1];
            Buffer[1] = v49[1];
            LOBYTE(NewElement) = 0;
            if ( RtlInsertElementGenericTableAvl(Table, Buffer, 0x10u, (PBOOLEAN)&NewElement) )
            {
              if ( (_BYTE)NewElement )
              {
                Common::GlobalHeap::Free(0);
                FreeLibrary(v15);
LABEL_72:
                RtlReleaseSRWLockExclusive(&qword_180015738);
                return 0;
              }
              v35 = -2147024198;
            }
            else
            {
              v35 = -2147024882;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x15B,
              (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
              (const char *)v35,
              (int)&v53);
            if ( v40 )
              Common::GlobalHeap::Free(v40);
            if ( !v39 )
            {
LABEL_30:
              Common::GlobalHeap::Free(0);
              FreeLibrary(v15);
              RtlReleaseSRWLockExclusive(&qword_180015738);
              return v35;
            }
            v21 = v39;
          }
        }
        Common::GlobalHeap::Free(v21);
        goto LABEL_30;
      }
      FreeLibrary(v15);
    }
    RtlReleaseSRWLockExclusive(&qword_180015738);
    v42 = Common::CopyStringToOutput(
            (Common *)L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo",
            (const unsigned __int16 *)a2,
            v41);
    v43 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v42,
        v44);
      return v43;
    }
    return 0;
  }
  v48 = 0;
  *(_OWORD *)Buffer = 0;
  if ( !L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo" )
  {
    Common::StringBuffer::Clear((Common::StringBuffer *)Buffer);
    goto LABEL_21;
  }
  v5 = L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo";
  v6 = 1073741822;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = -2147024809;
  if ( !v6 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      v44);
    goto LABEL_25;
  }
  v8 = (unsigned int)(1073741822 - v6);
  if ( (unsigned int)v8 > 0x7FFFFFFF )
  {
    v7 = -2147024362;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070216LL,
      v44);
    goto LABEL_20;
  }
  if ( !(_DWORD)v8 )
    goto LABEL_15;
  if ( (unsigned int)v8 <= 0x20 )
  {
    for ( i = 8; i < (unsigned int)v8; i *= 2 )
      ;
  }
  else
  {
    i = 1073741822 - v6;
  }
  v10 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)Buffer, i);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v10,
      v44);
    goto LABEL_20;
  }
  if ( v48 )
    v11 = v48 - 1;
  else
LABEL_15:
    v11 = 0;
  if ( (unsigned int)v8 <= v11
    || (v13 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)Buffer, v8), v7 = v13, v13 >= 0) )
  {
    if ( (_DWORD)v8 )
      *((_WORD *)Buffer[1] + v8) = 0;
    memcpy_0(Buffer[1], L"Software\\Policies\\Microsoft\\Windows\\AdvertisingInfo", (unsigned int)(2 * v8));
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v13,
      v44);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v7,
      v46);
  }
LABEL_20:
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_21:
    *a2 = (unsigned __int16 *)Buffer[1];
    return 0;
  }
LABEL_25:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)v7,
    v44);
  if ( Buffer[1] )
    Common::GlobalHeap::Free(Buffer[1]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x119,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)v7,
    v45);
  return v7;
}

```

## disassembly

```asm
0x1800020d0  mov     [rsp-18h+NewElement], rcx
0x1800020d5  push    rbp
0x1800020d6  push    rbx
0x1800020d7  push    r15
0x1800020d9  mov     rbp, rsp
0x1800020dc  sub     rsp, 70h
0x1800020e0  lea     rcx, [rbp+NewElement]; bool *
0x1800020e4  mov     byte ptr [rbp+NewElement], 0
0x1800020e8  mov     r15, rdx
0x1800020eb  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800020f0  mov     ebx, eax
0x1800020f2  test    eax, eax
0x1800020f4  js      loc_18000224A
0x1800020fa  cmp     byte ptr [rbp+NewElement], 0
0x1800020fe  mov     [rsp+70h+arg_8], rsi
0x180002106  mov     [rsp+70h+var_8], rdi
0x18000210b  mov     [rsp+70h+var_10], r14
0x180002110  jnz     loc_180002508
0x180002116  mov     rsi, cs:Src
0x18000211d  xor     r14d, r14d
0x180002120  mov     [rbp+var_30], r14d
0x180002124  xorps   xmm0, xmm0
0x180002127  movups  xmmword ptr [rbp+Buffer], xmm0
0x18000212b  test    rsi, rsi
0x18000212e  jz      loc_1800024A3
0x180002134  mov     edi, 3FFFFFFEh
0x180002139  mov     rax, rsi
0x18000213c  mov     ecx, edi
0x18000213e  xchg    ax, ax
0x180002140  cmp     [rax], r14w
0x180002144  jz      short loc_180002150
0x180002146  add     rax, 2
0x18000214a  sub     rcx, 1
0x18000214e  jnz     short loc_180002140
0x180002150  test    rcx, rcx
0x180002153  mov     ebx, 80070057h
0x180002158  cmovnz  ebx, r14d
0x18000215c  jz      loc_1800021F0
0x180002162  sub     edi, ecx
0x180002164  cmp     edi, 7FFFFFFFh
0x18000216a  ja      loc_1800024B1
0x180002170  test    edi, edi
0x180002172  jz      short loc_18000219D
0x180002174  cmp     edi, 20h ; ' '
0x180002177  jbe     loc_1800024D3
0x18000217d  mov     edx, edi; unsigned int
0x18000217f  lea     rcx, [rbp+Buffer]; this
0x180002183  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180002188  mov     ebx, eax
0x18000218a  test    eax, eax
0x18000218c  js      loc_1800024EB
0x180002192  mov     eax, [rbp+var_30]
0x180002195  test    eax, eax
0x180002197  jz      short loc_18000219D
0x180002199  dec     eax
0x18000219b  jmp     short loc_1800021A0
0x18000219d  mov     eax, r14d
0x1800021a0  cmp     edi, eax
0x1800021a2  ja      loc_180002296
0x1800021a8  test    edi, edi
0x1800021aa  jz      short loc_1800021B5
0x1800021ac  mov     rax, [rbp+Buffer+8]
0x1800021b0  mov     [rax+rdi*2], r14w
0x1800021b5  mov     rcx, [rbp+Buffer+8]; void *
0x1800021b9  lea     r8d, [rdi+rdi]; Size
0x1800021bd  mov     rdx, rsi; Src
0x1800021c0  call    memcpy_0
0x1800021c5  mov     ebx, r14d
0x1800021c8  test    ebx, ebx
0x1800021ca  js      short loc_180002208
0x1800021cc  mov     rax, [rbp+Buffer+8]
0x1800021d0  mov     [r15], rax
0x1800021d3  xor     eax, eax
0x1800021d5  mov     rdi, [rsp+70h+var_8]
0x1800021da  mov     rsi, [rsp+70h+arg_8]
0x1800021e2  mov     r14, [rsp+70h+var_10]
0x1800021e7  add     rsp, 70h
0x1800021eb  pop     r15
0x1800021ed  pop     rbx
0x1800021ee  pop     rbp
0x1800021ef  retn
0x1800021f0  mov     rcx, [rbp+18h]; this
0x1800021f4  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800021fb  mov     r9d, ebx; char *
0x1800021fe  mov     edx, 249h; void *
0x180002203  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002208  mov     rcx, [rbp+18h]; this
0x18000220c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002213  mov     r9d, ebx; char *
0x180002216  mov     edx, 31h ; '1'; void *
0x18000221b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002220  mov     rcx, [rbp+Buffer+8]; void *
0x180002224  test    rcx, rcx
0x180002227  jz      short loc_18000222E
0x180002229  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000222e  mov     rcx, [rbp+18h]; this
0x180002232  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002239  mov     r9d, ebx; char *
0x18000223c  mov     edx, 119h; void *
0x180002241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002246  mov     eax, ebx
0x180002248  jmp     short loc_1800021D5
0x18000224a  mov     rcx, [rbp+18h]; this
0x18000224e  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002255  mov     r9d, ebx; char *
0x180002258  mov     edx, 115h; void *
0x18000225d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002262  mov     eax, ebx
0x180002264  add     rsp, 70h
0x180002268  pop     r15
0x18000226a  pop     rbx
0x18000226b  pop     rbp
0x18000226c  retn
0x18000226d  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002272  xor     ecx, ecx; void *
0x180002274  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002279  mov     rcx, rbx; hLibModule
0x18000227c  call    cs:__imp_FreeLibrary
0x180002282  lea     rcx, qword_180015738
0x180002289  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000228f  mov     eax, edi
0x180002291  jmp     loc_1800021D5
0x180002296  mov     edx, edi; unsigned int
0x180002298  lea     rcx, [rbp+Buffer]; this
0x18000229c  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x1800022a1  mov     ebx, eax
0x1800022a3  test    eax, eax
0x1800022a5  jns     loc_1800021A8
0x1800022ab  mov     rcx, [rbp+18h]; this
0x1800022af  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800022b6  mov     r9d, eax; char *
0x1800022b9  mov     edx, 20Ch; void *
0x1800022be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800022c3  mov     rcx, [rbp+18h]; this
0x1800022c7  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800022ce  mov     r9d, ebx; char *
0x1800022d1  mov     edx, 235h; void *
0x1800022d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800022db  jmp     loc_1800021C8
0x1800022e0  xor     edx, edx; hFile
0x1800022e2  lea     rcx, LibFileName; "kernelbase.dll"
0x1800022e9  mov     r8d, 800h; dwFlags
0x1800022ef  call    cs:__imp_LoadLibraryExW
0x1800022f5  mov     rbx, rax
0x1800022f8  test    rax, rax
0x1800022fb  jz      loc_1800026EB
0x180002301  lea     rdx, ProcName; "GetPersistedRegistryLocationW"
0x180002308  mov     rcx, rax; hModule
0x18000230b  call    cs:__imp_GetProcAddress
0x180002311  mov     rsi, rax
0x180002314  test    rax, rax
0x180002317  jz      loc_1800026E2
0x18000231d  mov     rdx, cs:Src
0x180002324  lea     rax, [rbp+arg_10]
0x180002328  mov     rcx, cs:?AdvertisingIdPolicy@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AdvertisingIdPolicy
0x18000232f  xor     r14d, r14d
0x180002332  mov     qword ptr [rsp+70h+var_50], rax; int
0x180002337  xor     r9d, r9d
0x18000233a  mov     rax, rsi
0x18000233d  mov     [rbp+arg_10], r14d
0x180002341  xor     r8d, r8d
0x180002344  mov     edi, r14d
0x180002347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000234c  cmp     eax, 0EAh
0x180002351  jnz     short loc_18000239D
0x180002353  mov     ecx, [rbp+arg_10]; unsigned __int64
0x180002356  lea     rdx, [rbp+NewElement]; void **
0x18000235a  mov     [rbp+NewElement], r14
0x18000235e  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180002363  mov     rdi, [rbp+NewElement]
0x180002367  test    rdi, rdi
0x18000236a  jz      loc_180002607
0x180002370  xor     ecx, ecx; void *
0x180002372  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002377  mov     r9d, [rbp+arg_10]
0x18000237b  lea     rax, [rbp+arg_10]
0x18000237f  mov     rdx, cs:Src
0x180002386  mov     r8, rdi
0x180002389  mov     rcx, cs:?AdvertisingIdPolicy@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AdvertisingIdPolicy
0x180002390  mov     qword ptr [rsp+70h+var_50], rax; int
0x180002395  mov     rax, rsi
0x180002398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239d  test    eax, eax
0x18000239f  jz      loc_180002629
0x1800023a5  mov     rcx, [rbp+18h]; this
0x1800023a9  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x1800023b0  mov     r9d, eax; char *
0x1800023b3  mov     edx, 153h; void *
0x1800023b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800023bd  mov     rcx, rdi; void *
0x1800023c0  mov     esi, eax
0x1800023c2  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800023c7  mov     rcx, rbx; hLibModule
0x1800023ca  call    cs:__imp_FreeLibrary
0x1800023d0  lea     rcx, qword_180015738
0x1800023d7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800023dd  mov     eax, esi
0x1800023df  jmp     loc_1800021D5
0x1800023e4  mov     rcx, [rbp+18h]; this
0x1800023e8  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x1800023ef  mov     r9d, edi; char *
0x1800023f2  mov     edx, 158h; void *
0x1800023f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800023fc  mov     rcx, [rbp+Buffer+8]; void *
0x180002400  test    rcx, rcx
0x180002403  jz      loc_180002272
0x180002409  jmp     loc_18000226D
0x18000240e  mov     rcx, [rbp+18h]; this
0x180002412  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002419  mov     r9d, edi; char *
0x18000241c  mov     edx, 15Ah; void *
0x180002421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002426  mov     rcx, [rbp+var_28+8]; void *
0x18000242a  test    rcx, rcx
0x18000242d  jz      short loc_180002434
0x18000242f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002434  mov     rcx, [rbp+Buffer+8]
0x180002438  test    rcx, rcx
0x18000243b  jz      loc_180002272
0x180002441  jmp     loc_18000226D
0x180002446  mov     rcx, [rbp+18h]; this
0x18000244a  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002451  mov     r9d, edi; char *
0x180002454  mov     edx, 15Bh; void *
0x180002459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000245e  test    r14, r14
0x180002461  jz      short loc_18000246B
0x180002463  mov     rcx, r14; void *
0x180002466  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000246b  test    rsi, rsi
0x18000246e  jz      loc_180002272
0x180002474  mov     rcx, rsi
0x180002477  jmp     loc_18000226D
0x18000247c  mov     rdx, r15; unsigned __int16 *
0x18000247f  mov     rcx, rax; this
0x180002482  call    ?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z; Common::CopyStringToOutput(ushort const *,ushort * *)
0x180002487  mov     ebx, eax
0x180002489  test    eax, eax
0x18000248b  js      loc_180002585
0x180002491  lea     rcx, qword_180015738
0x180002498  call    cs:__imp_RtlReleaseSRWLockShared
0x18000249e  jmp     loc_1800021D3
0x1800024a3  lea     rcx, [rbp+Buffer]; this
0x1800024a7  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x1800024ac  jmp     loc_1800021CC
0x1800024b1  mov     rcx, [rbp+18h]; this
0x1800024b5  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800024bc  mov     ebx, 80070216h
0x1800024c1  mov     edx, 22Fh; void *
0x1800024c6  mov     r9d, ebx; char *
0x1800024c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800024ce  jmp     loc_1800021C8
0x1800024d3  mov     edx, 8
0x1800024d8  cmp     edi, edx
0x1800024da  jbe     loc_18000217F
0x1800024e0  add     edx, edx
0x1800024e2  cmp     edx, edi
0x1800024e4  jb      short loc_1800024E0
0x1800024e6  jmp     loc_18000217F
0x1800024eb  mov     rcx, [rbp+18h]; this
0x1800024ef  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800024f6  mov     r9d, eax; char *
0x1800024f9  mov     edx, 232h; void *
0x1800024fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002503  jmp     loc_1800021C8
0x180002508  lea     rcx, qword_180015738
0x18000250f  call    cs:__imp_RtlAcquireSRWLockShared
0x180002515  cmp     cs:Table, 0
0x18000251d  jz      short loc_180002534
0x18000251f  mov     rdx, cs:?AdvertisingIdPolicy@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AdvertisingIdPolicy
0x180002526  call    ?Find@?$GenericMap@PEBGPEBG@Common@@QEAAPEBGPEBG@Z; Common::GenericMap<ushort const *,ushort const *>::Find(ushort const *)
0x18000252b  test    rax, rax
0x18000252e  jnz     loc_18000247C
0x180002534  lea     rcx, qword_180015738
0x18000253b  call    cs:__imp_RtlReleaseSRWLockShared
0x180002541  lea     rcx, qword_180015738
0x180002548  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000254e  call    ?CreateCacheMapIfNeeded@Common@@YAJXZ; Common::CreateCacheMapIfNeeded(void)
0x180002553  mov     ebx, eax
0x180002555  test    eax, eax
0x180002557  jns     short loc_1800025B1
0x180002559  mov     rcx, [rbp+18h]; this
0x18000255d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002564  mov     r9d, eax; char *
0x180002567  mov     edx, 129h; void *
0x18000256c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002571  lea     rcx, qword_180015738
0x180002578  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000257e  mov     eax, ebx
0x180002580  jmp     loc_1800021D5
0x180002585  mov     rcx, [rbp+18h]; this
0x180002589  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180002590  mov     r9d, ebx; char *
0x180002593  mov     edx, 122h; void *
0x180002598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000259d  lea     rcx, qword_180015738
0x1800025a4  call    cs:__imp_RtlReleaseSRWLockShared
0x1800025aa  mov     eax, ebx
0x1800025ac  jmp     loc_1800021D5
0x1800025b1  mov     rdx, cs:?AdvertisingIdPolicy@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; Common::StateSeparationRedirectionMapping const Common::StateSeparation::AdvertisingIdPolicy
  ... truncated ...
```
