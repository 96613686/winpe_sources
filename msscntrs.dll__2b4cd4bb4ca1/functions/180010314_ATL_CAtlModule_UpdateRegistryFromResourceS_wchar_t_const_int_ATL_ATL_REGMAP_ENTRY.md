# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180010314`
- end: `0x180010657`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010670`

## callees

- `0x1800024a0`
- `0x180002cb0`
- `0x1800032b2`
- `0x18000b5c8`
- `0x18000ba7c`
- `0x18000c3f8`
- `0x18000de54`
- `0x18000edc8`
- `0x180010314`
- `0x1800156c8`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800105c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800105c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010416`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010416`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001048f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001048f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001049f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001053e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001057f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800103b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001049f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001053e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001057f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010563`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010563`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105a4`

## string_xrefs

- `0x1800105fa`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const wchar_t *v9; // rsi
  const wchar_t *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  wchar_t v18; // r8
  wchar_t *v19; // r8
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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Src[520]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v8 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const wchar_t **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const wchar_t *)*((_QWORD *)a4 + 1);
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
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_32;
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
            *(_DWORD *)_o__errno(Src, v15, v22) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_33;
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
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v27, Filename, a2, L"REGISTRY", 0);
            goto LABEL_32;
          }
          v11 = -2147024809;
          goto LABEL_33;
        }
LABEL_32:
        v11 = Error;
      }
    }
LABEL_33:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010314  mov     [rsp-8+arg_10], rbx
0x180010319  push    rbp
0x18001031a  push    rsi
0x18001031b  push    rdi
0x18001031c  push    r12
0x18001031e  push    r13
0x180010320  push    r14
0x180010322  push    r15
0x180010324  lea     rbp, [rsp-9D0h]
0x18001032c  sub     rsp, 0AD0h
0x180010333  mov     rax, cs:__security_cookie
0x18001033a  xor     rax, rsp
0x18001033d  mov     [rbp+0A00h+var_40], rax
0x180010344  mov     rbx, r9
0x180010347  mov     r12d, r8d
0x18001034a  mov     r14, rdx
0x18001034d  mov     r15, rcx
0x180010350  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180010357  mov     [rsp+0B00h+var_AD0], rax
0x18001035c  xor     r13d, r13d
0x18001035f  mov     [rsp+0B00h+var_AC8], r13
0x180010364  mov     [rsp+0B00h+var_AC0], r13
0x180010369  mov     [rsp+0B00h+var_AB8], r13d
0x18001036e  xorps   xmm0, xmm0
0x180010371  xor     eax, eax
0x180010373  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180010378  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18001037d  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180010382  mov     [rsp+0B00h+var_A88], r13b
0x180010387  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18001038c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180010391  mov     edi, eax
0x180010393  test    eax, eax
0x180010395  js      loc_18001061B
0x18001039b  mov     [rsp+0B00h+var_A88], 1
0x1800103a0  test    rbx, rbx
0x1800103a3  jz      short loc_1800103E2
0x1800103a5  jmp     short loc_1800103DA
0x1800103a7  mov     rsi, [rbx+8]
0x1800103ab  test    rsi, rsi
0x1800103ae  jz      short loc_1800103D6
0x1800103b0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800103b5  call    cs:__imp_EnterCriticalSection
0x1800103bb  mov     r8, rsi; wchar_t *
0x1800103be  mov     rdx, rdi; wchar_t *
0x1800103c1  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800103c6  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x1800103cb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800103d0  call    cs:__imp_LeaveCriticalSection
0x1800103d6  add     rbx, 10h
0x1800103da  mov     rdi, [rbx]
0x1800103dd  test    rdi, rdi
0x1800103e0  jnz     short loc_1800103A7
0x1800103e2  mov     rax, [r15]
0x1800103e5  lea     rdx, [rsp+0B00h+var_AD0]
0x1800103ea  mov     rcx, r15
0x1800103ed  mov     rax, [rax+28h]
0x1800103f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f6  mov     ebx, eax
0x1800103f8  test    eax, eax
0x1800103fa  js      loc_1800105BA
0x180010400  mov     rbx, cs:hModule
0x180010407  mov     edi, 104h
0x18001040c  mov     r8d, edi; nSize
0x18001040f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180010413  mov     rcx, rbx; hModule
0x180010416  call    cs:__imp_GetModuleFileNameW
0x18001041c  test    eax, eax
0x18001041e  jnz     short loc_18001042A
0x180010420  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010425  jmp     loc_1800105B8
0x18001042a  cmp     eax, edi
0x18001042c  jnz     short loc_180010438
0x18001042e  mov     ebx, 8007007Ah
0x180010433  jmp     loc_1800105BA
0x180010438  lea     rdx, [rbp+0A00h+Filename]
0x18001043c  mov     ecx, r13d
0x18001043f  mov     r9d, 27h ; '''
0x180010445  movzx   r8d, word ptr [rdx]
0x180010449  test    r8w, r8w
0x18001044d  jz      short loc_18001047F
0x18001044f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180010458  cmp     r8w, r9w
0x18001045c  jnz     short loc_180010471
0x18001045e  cmp     ecx, 206h
0x180010464  jnb     short loc_180010471
0x180010466  inc     ecx
0x180010468  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180010471  add     rdx, 2
0x180010475  inc     ecx
0x180010477  cmp     ecx, 207h
0x18001047d  jb      short loc_180010445
0x18001047f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180010488  test    rbx, rbx
0x18001048b  jz      short loc_1800104B1
0x18001048d  xor     ecx, ecx; lpModuleName
0x18001048f  call    cs:__imp_GetModuleHandleW
0x180010495  cmp     rbx, rax
0x180010498  jz      short loc_1800104B1
0x18001049a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001049f  call    cs:__imp_EnterCriticalSection
0x1800104a5  lea     r8, [rbp+0A00h+Src]
0x1800104ac  jmp     loc_18001054B
0x1800104b1  mov     edi, 22h ; '"'
0x1800104b6  mov     [rbp+0A00h+var_460], di
0x1800104bd  lea     rcx, [rbp+0A00h+Src]
0x1800104c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800104c8  mov     rax, rbx
0x1800104cb  inc     rax
0x1800104ce  cmp     [rcx+rax*2], r13w
0x1800104d3  jnz     short loc_1800104CB
0x1800104d5  inc     eax
0x1800104d7  movsxd  r8, eax
0x1800104da  add     r8, r8; Size
0x1800104dd  jz      short loc_1800104FF
0x1800104df  cmp     r8, 414h
0x1800104e6  ja      loc_1800105C8
0x1800104ec  lea     rdx, [rbp+0A00h+Src]; Src
0x1800104f3  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800104fa  call    memcpy_0
0x1800104ff  lea     rax, [rbp+0A00h+var_460]
0x180010506  inc     rbx
0x180010509  cmp     [rax+rbx*2], r13w
0x18001050e  jnz     short loc_180010506
0x180010510  movsxd  rax, ebx
0x180010513  mov     [rbp+rax*2+0A00h+var_460], di
0x18001051b  lea     rcx, ds:2[rax*2]
0x180010523  cmp     rcx, 418h
0x18001052a  jnb     loc_180010651
0x180010530  mov     [rbp+rcx+0A00h+var_460], r13w
0x180010539  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001053e  call    cs:__imp_EnterCriticalSection
0x180010544  lea     r8, [rbp+0A00h+var_460]; wchar_t *
0x18001054b  lea     rdx, aModule; "Module"
0x180010552  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180010557  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18001055c  mov     ebx, eax
0x18001055e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180010563  call    cs:__imp_LeaveCriticalSection
0x180010569  neg     ebx
0x18001056b  sbb     ebx, ebx
0x18001056d  mov     edi, 8007000Eh
0x180010572  not     ebx
0x180010574  and     ebx, edi
0x180010576  test    ebx, ebx
0x180010578  js      short loc_1800105BA
0x18001057a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001057f  call    cs:__imp_EnterCriticalSection
0x180010585  lea     r8, [rbp+0A00h+Src]; wchar_t *
0x18001058c  lea     rdx, aModuleRaw; "Module_Raw"
0x180010593  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180010598  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18001059d  mov     ebx, eax
0x18001059f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800105a4  call    cs:__imp_LeaveCriticalSection
0x1800105aa  mov     ecx, ebx
0x1800105ac  neg     ecx
0x1800105ae  sbb     eax, eax
0x1800105b0  not     eax
0x1800105b2  and     eax, edi
0x1800105b4  test    ebx, ebx
0x1800105b6  jnz     short loc_1800105DC
0x1800105b8  mov     ebx, eax
0x1800105ba  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800105bf  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800105c4  mov     eax, ebx
0x1800105c6  jmp     short loc_180010627
0x1800105c8  call    cs:__imp__o__errno
0x1800105ce  mov     [rax], edi
0x1800105d0  call    _invalid_parameter_noinfo
0x1800105d5  mov     ebx, 80004005h
0x1800105da  jmp     short loc_1800105BA
0x1800105dc  test    r12d, r12d
0x1800105df  jz      short loc_1800105F0
0x1800105e1  test    r14, r14
0x1800105e4  jz      short loc_180010614
0x1800105e6  mov     [rsp+0B00h+var_AE0], 1
0x1800105ee  jmp     short loc_1800105FA
0x1800105f0  test    r14, r14
0x1800105f3  jz      short loc_180010614
0x1800105f5  mov     [rsp+0B00h+var_AE0], r13d; int
0x1800105fa  lea     r9, aRegistry; "REGISTRY"
0x180010601  mov     r8, r14; wchar_t *
0x180010604  lea     rdx, [rbp+0A00h+Filename]; wchar_t *
0x180010608  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18001060d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180010612  jmp     short loc_1800105B8
0x180010614  mov     ebx, 80070057h
0x180010619  jmp     short loc_1800105BA
0x18001061b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180010620  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180010625  mov     eax, edi
0x180010627  mov     rcx, [rbp+0A00h+var_40]
0x18001062e  xor     rcx, rsp; StackCookie
0x180010631  call    __security_check_cookie
0x180010636  mov     rbx, [rsp+0B00h+arg_10]
0x18001063e  add     rsp, 0AD0h
0x180010645  pop     r15
0x180010647  pop     r14
0x180010649  pop     r13
0x18001064b  pop     r12
0x18001064d  pop     rdi
0x18001064e  pop     rsi
0x18001064f  pop     rbp
0x180010650  retn
0x180010651  call    __report_rangecheckfailure
```
