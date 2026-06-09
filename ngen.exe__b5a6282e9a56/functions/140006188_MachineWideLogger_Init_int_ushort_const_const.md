# MachineWideLogger::Init(int,ushort const * * const)

- ea: `0x140006188`
- end: `0x1400068e9`
- name: `?Init@MachineWideLogger@@QEAA_NHQEAPEBG@Z`
- size: `1889`
- prototype: `char __fastcall(MachineWideLogger *this, int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140009104`

## callees

- `0x140001214`
- `0x1400012c0`
- `0x1400060bc`
- `0x140006188`
- `0x14000a10c`
- `0x14000a3bc`
- `0x14000aabc`
- `0x14000ad80`
- `0x14000aedc`
- `0x14000b010`
- `0x14000b578`
- `0x14000b6e8`
- `0x14000b7d8`
- `0x14000c51c`
- `0x14000e4f4`
- `0x14000e708`
- `0x1400102cc`
- `0x14001070c`
- `0x140013200`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x140006819`
- `KERNEL32!CreateDirectoryW` at `0x140006819`
- `KERNEL32!GetModuleHandleW` at `0x1400062a5`
- `KERNEL32!GetModuleHandleW` at `0x1400062a5`
- `KERNEL32!GetFileAttributesW` at `0x1400067f9`
- `KERNEL32!GetFileAttributesW` at `0x1400067f9`
- `KERNEL32!GetModuleFileNameW` at `0x1400062c8`
- `KERNEL32!GetModuleFileNameW` at `0x1400062c8`
- `KERNEL32!HeapFree` at `0x14000689f`
- `KERNEL32!HeapFree` at `0x14000689f`
- `KERNEL32!GetProcessHeap` at `0x14000688a`
- `KERNEL32!GetProcessHeap` at `0x14000688a`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140006249`
- `ucrtbase_clr0400!_wcsnicmp` at `0x14000626b`
- `ucrtbase_clr0400!_wcsnicmp` at `0x140006249`
- `ucrtbase_clr0400!_wcsnicmp` at `0x14000626b`

## pseudocode

```c
char __fastcall MachineWideLogger::Init(MachineWideLogger *this, int a2, const unsigned __int16 **const a3)
{
  const unsigned __int16 **v3; // r12
  char v5; // r15
  char v6; // si
  int v7; // r13d
  int v8; // edi
  const wchar_t **v9; // rbx
  HMODULE ModuleHandleW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD v12; // r14d
  unsigned __int16 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r9
  int ConfigValue; // eax
  int v17; // ebx
  unsigned __int16 v18; // r8
  __int64 v19; // rdi
  __int64 v20; // rdi
  unsigned __int16 *v21; // rsi
  int v22; // edi
  __int64 v23; // rcx
  int v24; // eax
  CircularLog *v25; // rcx
  const unsigned __int16 *v26; // r8
  WCHAR *v27; // rbx
  HANDLE ProcessHeap; // rax
  bool v30; // [rsp+28h] [rbp-E0h] BYREF
  bool v31[16]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C8h]
  __int128 v33; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-B0h]
  const unsigned __int16 **v35; // [rsp+60h] [rbp-A8h]
  unsigned int v36; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v37; // [rsp+6Ch] [rbp-9Ch]
  __int64 v38; // [rsp+70h] [rbp-98h]
  void *lpMem; // [rsp+78h] [rbp-90h]
  unsigned int v40; // [rsp+288h] [rbp+180h] BYREF
  __int64 v41; // [rsp+28Ch] [rbp+184h]
  LPCWSTR lpFileName; // [rsp+298h] [rbp+190h]
  __int16 v43; // [rsp+2A0h] [rbp+198h] BYREF
  wchar_t v44[12]; // [rsp+4A8h] [rbp+3A0h] BYREF
  wchar_t String2[20]; // [rsp+4C0h] [rbp+3B8h] BYREF
  WCHAR Filename[264]; // [rsp+4E8h] [rbp+3E0h] BYREF

  v3 = a3;
  v35 = a3;
  v5 = 1;
  v6 = 0;
  v7 = 0;
  wcscpy(String2, L"/LocalAppData:");
  wcscpy(v44, L"/verbose");
  v8 = 1;
  if ( a2 > 1 )
  {
    v9 = a3 + 1;
    do
    {
      if ( _wcsnicmp(*v9, String2, 0xEu) )
      {
        if ( !_wcsnicmp(*v9, v44, 8u) )
          v6 = 1;
      }
      else
      {
        v7 = v8;
        v5 = 0;
      }
      ++v8;
      ++v9;
    }
    while ( v8 < a2 );
    v3 = v35;
    if ( !v6 )
      byte_1400270D0 = v5 != 0 ? byte_1400270D0 : 0;
  }
  ModuleHandleW = GetModuleHandleW(L"ngen.exe");
  if ( !ModuleHandleW
    || (ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, Filename, 0x104u), (v12 = ModuleFileNameW) == 0) )
  {
    ThrowLastError();
  }
  if ( ModuleFileNameW == 260 )
    ThrowHR(-2147418113);
  v41 = 512;
  lpFileName = (LPCWSTR)&v43;
  v40 = 2;
  v43 = 0;
  SString::Set((SString *)&v40, Filename);
  if ( (~(HIDWORD(v41) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v40) )
    SString::ConvertToUnicode((SString *)&v40);
  if ( (v41 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v40, (unsigned int)v41, 1);
  if ( (v41 & 0x200000000LL) != 0
    && ((BYTE4(v41) & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)&v40) )
  {
    SString::ConvertToUnicode((SString *)&v40);
  }
  *(_QWORD *)v31 = (char *)lpFileName
                 + (int)(((v40 >> ((v41 & 0x100000000LL) == 0)) - 1) << ((v41 & 0x100000000LL) == 0));
  *(_DWORD *)&v31[8] = (v41 & 0x100000000LL) == 0;
  SString::FindBack((SString *)&v40, (struct SString::CIterator *)v31, v13);
  SString::Truncate((SString *)&v40, (const struct SString::Iterator *)v31);
  ConfigValue = CLRConfig::GetConfigValue(
                  (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGenMaxLogSize,
                  v14,
                  &v30,
                  v15);
  v17 = ConfigValue;
  if ( v5 )
  {
    if ( !ConfigValue )
      v17 = 0x100000;
  }
  else
  {
    InlineSString<512>::InlineSString<512>(&v36, &v40);
    if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
      SString::ConvertToUnicode((SString *)&v36);
    if ( (v38 & 0x10) != 0 )
      SBuffer::ReallocateBuffer(&v36, v37, 1);
    if ( (v38 & 2) != 0
      && ((v38 & 7) != 7 || SString::s_IsANSIMultibyte)
      && !(unsigned int)SString::ScanASCII((SString *)&v36) )
    {
      SString::ConvertToUnicode((SString *)&v36);
    }
    *(_QWORD *)&v33 = (char *)lpMem + (int)(((v36 >> ((v38 & 1) == 0)) - 1) << ((v38 & 1) == 0));
    DWORD2(v33) = (v38 & 1) == 0;
    *(_OWORD *)v31 = v33;
    v32 = v34;
    if ( (unsigned int)SString::FindBack((SString *)&v36, (struct SString::CIterator *)v31, v18) )
    {
      v19 = *(_QWORD *)v31 + (1 << v31[8]);
      if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
        SString::ConvertToUnicode((SString *)&v36);
      if ( (v38 & 0x10) != 0 )
        SBuffer::ReallocateBuffer(&v36, v37, 1);
      v20 = (v19 - (__int64)lpMem) >> v31[8];
      if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
        SString::ConvertToUnicode((SString *)&v36);
      if ( (v38 & 0x10) != 0 )
        SBuffer::ReallocateBuffer(&v36, v37, 1);
      *(_QWORD *)&v33 = lpMem;
      DWORD2(v33) = (v38 & 1) == 0;
      SString::Replace(
        (SString *)&v36,
        (const struct SString::Iterator *)&v33,
        v20,
        *(const struct SString **)&SString::s_Empty);
    }
    if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
      SString::ConvertToUnicode((SString *)&v36);
    if ( (v38 & 0x10) != 0 )
      SBuffer::ReallocateBuffer(&v36, v37, 1);
    v21 = (unsigned __int16 *)lpMem;
    v22 = (v38 & 1) == 0;
    if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
      SString::ConvertToUnicode((SString *)&v36);
    if ( (v38 & 2) != 0
      && ((v38 & 7) != 7 || SString::s_IsANSIMultibyte)
      && !(unsigned int)SString::ScanASCII((SString *)&v36) )
    {
      SString::ConvertToUnicode((SString *)&v36);
    }
    if ( (int)(((char *)v21 - (int)(((v36 >> ((v38 & 1) == 0)) - 1) << ((v38 & 1) == 0)) - (_BYTE *)lpMem) >> v22) < 0 )
    {
      v23 = v22 ? *v21 : (unsigned int)*(char *)v21;
      if ( (_WORD)v23 == 118 )
        goto LABEL_98;
      if ( (v23 & 0xFF80) != 0 )
      {
        v24 = (unsigned __int16)MapChar(v23);
      }
      else
      {
        v24 = (unsigned __int16)v23 - 32;
        if ( (unsigned __int16)(v23 - 97) > 0x19u )
          v24 = (unsigned __int16)v23;
      }
      if ( v24 == 86 )
      {
LABEL_98:
        if ( (~((unsigned int)v38 >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v36) )
          SString::ConvertToUnicode((SString *)&v36);
        if ( (v38 & 0x10) != 0 )
          SBuffer::ReallocateBuffer(&v36, v37, 1);
        *(_QWORD *)&v33 = lpMem;
        DWORD2(v33) = (v38 & 1) == 0;
        *(_OWORD *)v31 = v33;
        v32 = v34;
        if ( (unsigned int)SString::Find((SString *)&v36, (struct SString::CIterator *)v31, 0x2Eu) )
        {
          *(_QWORD *)v31 += 1 << v31[8];
          if ( (unsigned int)SString::Find((SString *)&v36, (struct SString::CIterator *)v31, 0x2Eu) )
            SString::Truncate((SString *)&v36, (const struct SString::Iterator *)v31);
        }
      }
    }
    if ( v12 - 1 <= 0x102 )
    {
      SString::Set((SString *)&v40, v3[v7] + 14);
      SString::Append((SString *)&v40, L"\\Microsoft\\CLR_");
      SString::Append((SString *)&v40, (const struct SString *)&v36);
    }
    SString::ConvertToUnicode((SString *)&v40);
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      SString::ConvertToUnicode((SString *)&v40);
      CreateDirectoryW(lpFileName, 0);
    }
    if ( !v17 )
      v17 = 102400;
    if ( (v38 & 8) != 0 )
      operator delete(lpMem);
  }
  SString::Append((SString *)&v40, L"\\ngen");
  SString::ConvertToUnicode((SString *)&v40);
  CircularLog::Init(v25, lpFileName, v26, v17);
  if ( (v41 & 0x800000000LL) != 0 )
  {
    v27 = (WCHAR *)lpFileName;
    if ( lpFileName )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v27);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140006188  mov     rax, rsp
0x14000618b  mov     [rax+8], rbx
0x14000618f  mov     [rax+10h], rsi
0x140006193  mov     [rax+20h], rdi
0x140006197  push    rbp
0x140006198  push    r12
0x14000619a  push    r13
0x14000619c  push    r14
0x14000619e  push    r15
0x1400061a0  lea     rbp, [rax-628h]
0x1400061a7  sub     rsp, 700h
0x1400061ae  mov     rax, cs:__security_cookie
0x1400061b5  xor     rax, rsp
0x1400061b8  mov     [rbp+620h+var_30], rax
0x1400061bf  mov     r12, r8
0x1400061c2  mov     [rsp+720h+var_6C8], r8
0x1400061c7  mov     r14d, edx
0x1400061ca  mov     ecx, 1
0x1400061cf  mov     r15b, cl
0x1400061d2  xor     sil, sil
0x1400061d5  xor     r13d, r13d
0x1400061d8  movups  xmm0, xmmword ptr cs:aLocalappdata_0; "/LocalAppData:"
0x1400061df  movups  xmmword ptr [rbp+620h+String2], xmm0
0x1400061e6  movsd   xmm1, qword ptr cs:aLocalappdata_0+10h; "pData:"
0x1400061ee  movsd   [rbp+620h+var_258], xmm1
0x1400061f6  mov     eax, dword ptr cs:aLocalappdata_0+18h; "a:"
0x1400061fc  mov     [rbp+620h+var_250], eax
0x140006202  movzx   eax, word ptr cs:aLocalappdata_0+1Ch; ""
0x140006209  mov     [rbp+620h+var_24C], ax
0x140006210  movups  xmm0, xmmword ptr cs:aVerbose_0; "/verbose"
0x140006217  movups  xmmword ptr [rbp+620h+var_280], xmm0
0x14000621e  movzx   eax, word ptr cs:aVerbose_0+10h; ""
0x140006225  mov     [rbp+620h+var_270], ax
0x14000622c  mov     edi, ecx
0x14000622e  cmp     edx, ecx
0x140006230  jle     short loc_14000629E
0x140006232  lea     rbx, [r8+8]
0x140006236  mov     r12d, ecx
0x140006239  mov     r8d, 0Eh; MaxCount
0x14000623f  lea     rdx, [rbp+620h+String2]; String2
0x140006246  mov     rcx, [rbx]; String1
0x140006249  call    cs:__imp__wcsnicmp
0x14000624f  test    eax, eax
0x140006251  jnz     short loc_14000625B
0x140006253  mov     r13d, edi
0x140006256  xor     r15b, r15b
0x140006259  jmp     short loc_14000627B
0x14000625b  mov     r8d, 8; MaxCount
0x140006261  lea     rdx, [rbp+620h+var_280]; String2
0x140006268  mov     rcx, [rbx]; String1
0x14000626b  call    cs:__imp__wcsnicmp
0x140006271  movzx   esi, sil
0x140006275  test    eax, eax
0x140006277  cmovz   esi, r12d
0x14000627b  add     edi, r12d
0x14000627e  add     rbx, 8
0x140006282  cmp     edi, r14d
0x140006285  jl      short loc_140006239
0x140006287  test    sil, sil
0x14000628a  mov     r12, [rsp+720h+var_6C8]
0x14000628f  jnz     short loc_14000629E
0x140006291  mov     al, r15b
0x140006294  neg     al
0x140006296  sbb     cl, cl
0x140006298  and     cs:byte_1400270D0, cl
0x14000629e  lea     rcx, ModuleName; "ngen.exe"
0x1400062a5  call    cs:__imp_GetModuleHandleW
0x1400062ab  xor     esi, esi
0x1400062ad  test    rax, rax
0x1400062b0  jz      loc_1400068E3
0x1400062b6  mov     ebx, 104h
0x1400062bb  mov     r8d, ebx; nSize
0x1400062be  lea     rdx, [rbp+620h+Filename]; lpFilename
0x1400062c5  mov     rcx, rax; hModule
0x1400062c8  call    cs:__imp_GetModuleFileNameW
0x1400062ce  mov     r14d, eax
0x1400062d1  test    eax, eax
0x1400062d3  jz      loc_1400068E3
0x1400062d9  cmp     eax, ebx
0x1400062db  jz      loc_1400068D8
0x1400062e1  mov     [rbp+620h+var_4A0], rsi
0x1400062e8  mov     [rbp+620h+var_4A0+4], 200h
0x1400062f3  mov     [rbp+620h+lpFileName], rsi
0x1400062fa  lea     rax, [rbp+620h+var_488]
0x140006301  mov     [rbp+620h+lpFileName], rax
0x140006308  mov     dword ptr [rbp+620h+var_4A0], 2
0x140006312  mov     rax, [rbp+620h+lpFileName]
0x140006319  mov     [rax], si
0x14000631c  lea     rdx, [rbp+620h+Filename]; unsigned __int16 *
0x140006323  lea     rcx, [rbp+620h+var_4A0]; this
0x14000632a  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x14000632f  nop
0x140006330  mov     eax, [rbp+620h+var_498]
0x140006336  shr     eax, 1
0x140006338  not     eax
0x14000633a  lea     edi, [rsi+1]
0x14000633d  test    dil, al
0x140006340  jnz     short loc_14000635E
0x140006342  lea     rcx, [rbp+620h+var_4A0]; this
0x140006349  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x14000634e  test    eax, eax
0x140006350  jnz     short loc_14000635E
0x140006352  lea     rcx, [rbp+620h+var_4A0]; this
0x140006359  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000635e  test    byte ptr [rbp+620h+var_498], 10h
0x140006365  jz      short loc_14000637C
0x140006367  mov     r8d, edi
0x14000636a  mov     edx, dword ptr [rbp+620h+var_4A0+4]
0x140006370  lea     rcx, [rbp+620h+var_4A0]
0x140006377  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x14000637c  mov     eax, [rbp+620h+var_498]
0x140006382  test    al, 2
0x140006384  jz      short loc_1400063B1
0x140006386  and     eax, 7
0x140006389  cmp     al, 7
0x14000638b  jnz     short loc_140006395
0x14000638d  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x140006393  jz      short loc_1400063B1
0x140006395  lea     rcx, [rbp+620h+var_4A0]; this
0x14000639c  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1400063a1  test    eax, eax
0x1400063a3  jnz     short loc_1400063B1
0x1400063a5  lea     rcx, [rbp+620h+var_4A0]; this
0x1400063ac  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400063b1  mov     ecx, [rbp+620h+var_498]
0x1400063b7  not     ecx
0x1400063b9  and     ecx, edi
0x1400063bb  mov     eax, dword ptr [rbp+620h+var_4A0]
0x1400063c1  shr     eax, cl
0x1400063c3  sub     eax, edi
0x1400063c5  shl     eax, cl
0x1400063c7  cdqe
0x1400063c9  add     rax, [rbp+620h+lpFileName]
0x1400063d0  mov     qword ptr [rsp+720h+var_700+8], rax
0x1400063d5  mov     dword ptr [rsp+720h+var_6F0], ecx
0x1400063d9  lea     rdx, [rsp+720h+var_700+8]; struct SString::CIterator *
0x1400063de  lea     rcx, [rbp+620h+var_4A0]; this
0x1400063e5  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@G@Z; SString::FindBack(SString::CIterator &,ushort)
0x1400063ea  lea     rdx, [rsp+720h+var_700+8]; struct SString::Iterator *
0x1400063ef  lea     rcx, [rbp+620h+var_4A0]; this
0x1400063f6  call    ?Truncate@SString@@QEAAXAEBVIterator@1@@Z; SString::Truncate(SString::Iterator const &)
0x1400063fb  lea     r8, [rsp+720h+var_700]; bool *
0x140006400  lea     rcx, ?UNSUPPORTED_NGenMaxLogSize@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x140006407  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x14000640c  mov     ebx, eax
0x14000640e  test    r15b, r15b
0x140006411  jz      short loc_140006425
0x140006413  test    eax, eax
0x140006415  jnz     loc_14000683A
0x14000641b  mov     ebx, 100000h
0x140006420  jmp     loc_14000683A
0x140006425  lea     rdx, [rbp+620h+var_4A0]
0x14000642c  lea     rcx, [rsp+720h+var_6C0]
0x140006431  call    ??0?$InlineSString@$0CAA@@@QEAA@AEBV0@@Z; InlineSString<512>::InlineSString<512>(InlineSString<512> const &)
0x140006436  nop
0x140006437  mov     eax, dword ptr [rsp+720h+var_6B8]
0x14000643b  shr     eax, 1
0x14000643d  not     eax
0x14000643f  test    dil, al
0x140006442  jnz     short loc_14000645C
0x140006444  lea     rcx, [rsp+720h+var_6C0]; this
0x140006449  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x14000644e  test    eax, eax
0x140006450  jnz     short loc_14000645C
0x140006452  lea     rcx, [rsp+720h+var_6C0]; this
0x140006457  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000645c  test    byte ptr [rsp+720h+var_6B8], 10h
0x140006461  jz      short loc_140006474
0x140006463  mov     r8d, edi
0x140006466  mov     edx, [rsp+720h+var_6BC]
0x14000646a  lea     rcx, [rsp+720h+var_6C0]
0x14000646f  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140006474  mov     eax, dword ptr [rsp+720h+var_6B8]
0x140006478  test    al, 2
0x14000647a  jz      short loc_1400064A3
0x14000647c  and     eax, 7
0x14000647f  cmp     al, 7
0x140006481  jnz     short loc_14000648B
0x140006483  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x140006489  jz      short loc_1400064A3
0x14000648b  lea     rcx, [rsp+720h+var_6C0]; this
0x140006490  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006495  test    eax, eax
0x140006497  jnz     short loc_1400064A3
0x140006499  lea     rcx, [rsp+720h+var_6C0]; this
0x14000649e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400064a3  mov     ecx, dword ptr [rsp+720h+var_6B8]
0x1400064a7  not     ecx
0x1400064a9  and     ecx, edi
0x1400064ab  mov     eax, [rsp+720h+var_6C0]
0x1400064af  shr     eax, cl
0x1400064b1  sub     eax, edi
0x1400064b3  shl     eax, cl
0x1400064b5  cdqe
0x1400064b7  add     rax, [rsp+720h+lpMem]
0x1400064bc  mov     qword ptr [rsp+720h+var_6E8+8], rax
0x1400064c1  mov     dword ptr [rsp+720h+var_6D8], ecx
0x1400064c5  movups  xmm0, [rsp+720h+var_6E8+8]
0x1400064ca  movups  xmmword ptr [rsp+720h+var_700+8], xmm0
0x1400064cf  movsd   xmm1, [rsp+720h+var_6D0]
0x1400064d5  movsd   qword ptr [rsp+720h+var_6E8], xmm1
0x1400064db  lea     rdx, [rsp+720h+var_700+8]; struct SString::CIterator *
0x1400064e0  lea     rcx, [rsp+720h+var_6C0]; this
0x1400064e5  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@G@Z; SString::FindBack(SString::CIterator &,ushort)
0x1400064ea  test    eax, eax
0x1400064ec  jz      loc_1400065C3
0x1400064f2  mov     ecx, dword ptr [rsp+720h+var_6F0]
0x1400064f6  mov     eax, edi
0x1400064f8  shl     eax, cl
0x1400064fa  movsxd  rdi, eax
0x1400064fd  add     rdi, qword ptr [rsp+720h+var_700+8]
0x140006502  mov     eax, dword ptr [rsp+720h+var_6B8]
0x140006506  shr     eax, 1
0x140006508  not     eax
0x14000650a  mov     r15d, 1
0x140006510  test    r15b, al
0x140006513  jnz     short loc_14000652D
0x140006515  lea     rcx, [rsp+720h+var_6C0]; this
0x14000651a  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x14000651f  test    eax, eax
0x140006521  jnz     short loc_14000652D
0x140006523  lea     rcx, [rsp+720h+var_6C0]; this
0x140006528  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000652d  test    byte ptr [rsp+720h+var_6B8], 10h
0x140006532  jz      short loc_140006545
0x140006534  mov     r8d, r15d
0x140006537  mov     edx, [rsp+720h+var_6BC]
0x14000653b  lea     rcx, [rsp+720h+var_6C0]
0x140006540  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140006545  sub     rdi, [rsp+720h+lpMem]
0x14000654a  mov     ecx, dword ptr [rsp+720h+var_6F0]
0x14000654e  sar     rdi, cl
0x140006551  mov     eax, dword ptr [rsp+720h+var_6B8]
0x140006555  shr     eax, 1
0x140006557  not     eax
0x140006559  test    r15b, al
0x14000655c  jnz     short loc_140006576
0x14000655e  lea     rcx, [rsp+720h+var_6C0]; this
0x140006563  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006568  test    eax, eax
0x14000656a  jnz     short loc_140006576
0x14000656c  lea     rcx, [rsp+720h+var_6C0]; this
0x140006571  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006576  test    byte ptr [rsp+720h+var_6B8], 10h
0x14000657b  jz      short loc_14000658E
0x14000657d  mov     r8d, r15d
0x140006580  mov     edx, [rsp+720h+var_6BC]
0x140006584  lea     rcx, [rsp+720h+var_6C0]
0x140006589  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x14000658e  mov     rax, [rsp+720h+lpMem]
0x140006593  mov     qword ptr [rsp+720h+var_6E8+8], rax
0x140006598  mov     eax, dword ptr [rsp+720h+var_6B8]
0x14000659c  not     eax
0x14000659e  and     eax, r15d
0x1400065a1  mov     dword ptr [rsp+720h+var_6D8], eax
0x1400065a5  mov     r9, cs:?s_Empty@SString@@0PEAV1@EA; struct SString *
0x1400065ac  mov     r8d, edi; unsigned int
0x1400065af  lea     rdx, [rsp+720h+var_6E8+8]; struct SString::Iterator *
0x1400065b4  lea     rcx, [rsp+720h+var_6C0]; this
0x1400065b9  call    ?Replace@SString@@QEAAXAEBVIterator@1@IAEBV1@@Z; SString::Replace(SString::Iterator const &,uint,SString const &)
0x1400065be  mov     edi, 1
0x1400065c3  mov     eax, dword ptr [rsp+720h+var_6B8]
0x1400065c7  shr     eax, 1
0x1400065c9  not     eax
0x1400065cb  test    dil, al
0x1400065ce  jnz     short loc_1400065E8
0x1400065d0  lea     rcx, [rsp+720h+var_6C0]; this
0x1400065d5  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1400065da  test    eax, eax
0x1400065dc  jnz     short loc_1400065E8
0x1400065de  lea     rcx, [rsp+720h+var_6C0]; this
0x1400065e3  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400065e8  test    byte ptr [rsp+720h+var_6B8], 10h
0x1400065ed  jz      short loc_140006600
0x1400065ef  mov     r8d, edi
0x1400065f2  mov     edx, [rsp+720h+var_6BC]
0x1400065f6  lea     rcx, [rsp+720h+var_6C0]
0x1400065fb  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140006600  mov     rsi, [rsp+720h+lpMem]
0x140006605  mov     eax, dword ptr [rsp+720h+var_6B8]
0x140006609  mov     edi, eax
0x14000660b  not     edi
0x14000660d  mov     ecx, 1
0x140006612  and     edi, ecx
0x140006614  shr     eax, 1
0x140006616  not     eax
0x140006618  test    cl, al
0x14000661a  jnz     short loc_140006639
0x14000661c  lea     rcx, [rsp+720h+var_6C0]; this
0x140006621  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006626  xor     r15d, r15d
0x140006629  test    eax, eax
0x14000662b  jnz     short loc_14000663C
0x14000662d  lea     rcx, [rsp+720h+var_6C0]; this
0x140006632  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006637  jmp     short loc_14000663C
0x140006639  xor     r15d, r15d
0x14000663c  mov     eax, dword ptr [rsp+720h+var_6B8]
0x140006640  test    al, 2
0x140006642  jz      short loc_14000666C
  ... truncated ...
```
