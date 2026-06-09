# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005d2c`
- end: `0x18000604c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x180001f90`
- `0x180002010`
- `0x1800029f6`
- `0x18000310c`
- `0x18000331c`
- `0x180003e74`
- `0x18000465c`
- `0x180005038`
- `0x180005d2c`
- `0x1800123c8`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fd1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005de8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005de8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005e31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005e31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ea4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ea4`

## string_xrefs

- `0x180005ff6`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rcx
  int v24; // ebx
  int v25; // ebx
  void **v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v9 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v27);
    if ( v11 < 0 )
      goto LABEL_34;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_33:
      v11 = Error;
      goto LABEL_34;
    }
    if ( ModuleFileNameW == 260 )
    {
      v11 = -2147024774;
    }
    else
    {
      v15 = Filename;
      v16 = 0;
      v17 = 39;
      do
      {
        v18 = *v15;
        if ( !*v15 )
          break;
        Src[v16] = v18;
        if ( v18 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Src[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Src[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v34 = 34;
        v20 = -1;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v15, v22, v17) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_34;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v23, v15, v22, v17);
        *(_WORD *)&v35[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v19 = &v34;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v19 = Src;
      }
      v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", v19);
      LeaveCriticalSection(&CriticalSection);
      v11 = v24 == 0 ? 0x8007000E : 0;
      if ( v11 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v25 == 0 ? 0x8007000E : 0;
        if ( v25 )
          Error = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v27,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    a3 != 0);
        goto LABEL_33;
      }
    }
LABEL_34:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005d2c  mov     [rsp-8+arg_10], rbx
0x180005d31  push    rbp
0x180005d32  push    rsi
0x180005d33  push    rdi
0x180005d34  push    r12
0x180005d36  push    r13
0x180005d38  push    r14
0x180005d3a  push    r15
0x180005d3c  lea     rbp, [rsp-9D0h]
0x180005d44  sub     rsp, 0AD0h
0x180005d4b  mov     rax, cs:__security_cookie
0x180005d52  xor     rax, rsp
0x180005d55  mov     [rbp+0A00h+var_40], rax
0x180005d5c  mov     rbx, r9
0x180005d5f  mov     r15d, r8d
0x180005d62  mov     r12d, edx
0x180005d65  mov     r14, rcx
0x180005d68  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005d6f  mov     [rsp+0B00h+var_AD0], rax
0x180005d74  xor     r13d, r13d
0x180005d77  mov     [rsp+0B00h+var_AC8], r13
0x180005d7c  mov     [rsp+0B00h+var_AC0], r13
0x180005d81  mov     [rsp+0B00h+var_AB8], r13d
0x180005d86  xorps   xmm0, xmm0
0x180005d89  xor     eax, eax
0x180005d8b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180005d90  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005d95  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180005d9a  mov     [rsp+0B00h+var_A88], r13b
0x180005d9f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180005da4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005da9  mov     edi, eax
0x180005dab  test    eax, eax
0x180005dad  js      loc_180006010
0x180005db3  mov     [rsp+0B00h+var_A88], 1
0x180005db8  test    rbx, rbx
0x180005dbb  jz      short loc_180005DFA
0x180005dbd  jmp     short loc_180005DF2
0x180005dbf  mov     rsi, [rbx+8]
0x180005dc3  test    rsi, rsi
0x180005dc6  jz      short loc_180005DEE
0x180005dc8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005dcd  call    cs:__imp_EnterCriticalSection
0x180005dd3  mov     r8, rsi; unsigned __int16 *
0x180005dd6  mov     rdx, rdi; unsigned __int16 *
0x180005dd9  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005dde  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005de3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005de8  call    cs:__imp_LeaveCriticalSection
0x180005dee  add     rbx, 10h
0x180005df2  mov     rdi, [rbx]
0x180005df5  test    rdi, rdi
0x180005df8  jnz     short loc_180005DBF
0x180005dfa  mov     rax, [r14]
0x180005dfd  lea     rdx, [rsp+0B00h+var_AD0]
0x180005e02  mov     rcx, r14
0x180005e05  mov     rax, [rax+28h]
0x180005e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e0e  mov     ebx, eax
0x180005e10  test    eax, eax
0x180005e12  js      loc_180005FC3
0x180005e18  mov     rbx, cs:hInstance
0x180005e1f  mov     edi, 104h
0x180005e24  mov     r8d, edi; nSize
0x180005e27  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005e2e  mov     rcx, rbx; hModule
0x180005e31  call    cs:__imp_GetModuleFileNameW
0x180005e37  test    eax, eax
0x180005e39  jnz     short loc_180005E45
0x180005e3b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005e40  jmp     loc_180005FC1
0x180005e45  cmp     eax, edi
0x180005e47  jnz     short loc_180005E53
0x180005e49  mov     ebx, 8007007Ah
0x180005e4e  jmp     loc_180005FC3
0x180005e53  lea     rdx, [rbp+0A00h+Filename]
0x180005e5a  mov     ecx, r13d
0x180005e5d  mov     r9d, 27h ; '''
0x180005e63  movzx   r8d, word ptr [rdx]
0x180005e67  test    r8w, r8w
0x180005e6b  jz      short loc_180005E97
0x180005e6d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180005e73  cmp     r8w, r9w
0x180005e77  jnz     short loc_180005E89
0x180005e79  cmp     ecx, 206h
0x180005e7f  jnb     short loc_180005E89
0x180005e81  inc     ecx
0x180005e83  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180005e89  add     rdx, 2
0x180005e8d  inc     ecx
0x180005e8f  cmp     ecx, 207h
0x180005e95  jb      short loc_180005E63
0x180005e97  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180005e9d  test    rbx, rbx
0x180005ea0  jz      short loc_180005EC3
0x180005ea2  xor     ecx, ecx; lpModuleName
0x180005ea4  call    cs:__imp_GetModuleHandleW
0x180005eaa  cmp     rbx, rax
0x180005ead  jz      short loc_180005EC3
0x180005eaf  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005eb4  call    cs:__imp_EnterCriticalSection
0x180005eba  lea     r8, [rbp+0A00h+Src]
0x180005ebe  jmp     loc_180005F57
0x180005ec3  mov     edi, 22h ; '"'
0x180005ec8  mov     [rbp+0A00h+var_460], di
0x180005ecf  lea     rcx, [rbp+0A00h+Src]
0x180005ed3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005ed7  mov     rax, rbx
0x180005eda  inc     rax
0x180005edd  cmp     [rcx+rax*2], r13w
0x180005ee2  jnz     short loc_180005EDA
0x180005ee4  inc     eax
0x180005ee6  movsxd  r8, eax
0x180005ee9  add     r8, r8; Size
0x180005eec  jz      short loc_180005F0B
0x180005eee  cmp     r8, 414h
0x180005ef5  ja      loc_180005FD1
0x180005efb  lea     rdx, [rbp+0A00h+Src]; Src
0x180005eff  lea     rcx, [rbp+0A00h+var_45E]; void *
0x180005f06  call    memcpy_0
0x180005f0b  lea     rax, [rbp+0A00h+var_460]
0x180005f12  inc     rbx
0x180005f15  cmp     [rax+rbx*2], r13w
0x180005f1a  jnz     short loc_180005F12
0x180005f1c  movsxd  rax, ebx
0x180005f1f  mov     [rbp+rax*2+0A00h+var_460], di
0x180005f27  lea     rcx, ds:2[rax*2]
0x180005f2f  cmp     rcx, 418h
0x180005f36  jnb     loc_180006046
0x180005f3c  mov     [rbp+rcx+0A00h+var_460], r13w
0x180005f45  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005f4a  call    cs:__imp_EnterCriticalSection
0x180005f50  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005f57  lea     rdx, aModule; "Module"
0x180005f5e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005f63  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005f68  mov     ebx, eax
0x180005f6a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005f6f  call    cs:__imp_LeaveCriticalSection
0x180005f75  neg     ebx
0x180005f77  sbb     ebx, ebx
0x180005f79  mov     edi, 8007000Eh
0x180005f7e  not     ebx
0x180005f80  and     ebx, edi
0x180005f82  test    ebx, ebx
0x180005f84  js      short loc_180005FC3
0x180005f86  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005f8b  call    cs:__imp_EnterCriticalSection
0x180005f91  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x180005f95  lea     rdx, aModuleRaw; "Module_Raw"
0x180005f9c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005fa1  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005fa6  mov     ebx, eax
0x180005fa8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005fad  call    cs:__imp_LeaveCriticalSection
0x180005fb3  mov     ecx, ebx
0x180005fb5  neg     ecx
0x180005fb7  sbb     eax, eax
0x180005fb9  not     eax
0x180005fbb  and     eax, edi
0x180005fbd  test    ebx, ebx
0x180005fbf  jnz     short loc_180005FE5
0x180005fc1  mov     ebx, eax
0x180005fc3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005fc8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005fcd  mov     eax, ebx
0x180005fcf  jmp     short loc_18000601C
0x180005fd1  call    cs:__imp__o__errno
0x180005fd7  mov     [rax], edi
0x180005fd9  call    _invalid_parameter_noinfo
0x180005fde  mov     ebx, 80004005h
0x180005fe3  jmp     short loc_180005FC3
0x180005fe5  mov     eax, r13d
0x180005fe8  test    r15d, r15d
0x180005feb  setnz   al
0x180005fee  movzx   r8d, r12w; unsigned __int16 *
0x180005ff2  mov     [rsp+0B00h+var_AE0], eax; int
0x180005ff6  lea     r9, aRegistry; "REGISTRY"
0x180005ffd  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006004  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006009  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000600e  jmp     short loc_180005FC1
0x180006010  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006015  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000601a  mov     eax, edi
0x18000601c  mov     rcx, [rbp+0A00h+var_40]
0x180006023  xor     rcx, rsp; StackCookie
0x180006026  call    __security_check_cookie
0x18000602b  mov     rbx, [rsp+0B00h+arg_10]
0x180006033  add     rsp, 0AD0h
0x18000603a  pop     r15
0x18000603c  pop     r14
0x18000603e  pop     r13
0x180006040  pop     r12
0x180006042  pop     rdi
0x180006043  pop     rsi
0x180006044  pop     rbp
0x180006045  retn
0x180006046  call    __report_rangecheckfailure
```
