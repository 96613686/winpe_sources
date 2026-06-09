# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006054`
- end: `0x180006397`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800063b0`

## callees

- `0x180001f90`
- `0x180002010`
- `0x1800029f6`
- `0x18000310c`
- `0x18000331c`
- `0x180003e74`
- `0x18000465c`
- `0x180005038`
- `0x180006054`
- `0x1800123c8`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006308`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006308`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006110`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006110`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000627e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800062bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000627e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800062bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006156`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006156`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061cf`

## string_xrefs

- `0x18000633a`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Src[520]; // [rsp+290h] [rbp+190h] BYREF
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
      goto LABEL_33;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
            *(_DWORD *)_o__errno(Src, v15, v22, v17) = 34;
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
              Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 0);
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
0x180006054  mov     [rsp-8+arg_10], rbx
0x180006059  push    rbp
0x18000605a  push    rsi
0x18000605b  push    rdi
0x18000605c  push    r12
0x18000605e  push    r13
0x180006060  push    r14
0x180006062  push    r15
0x180006064  lea     rbp, [rsp-9D0h]
0x18000606c  sub     rsp, 0AD0h
0x180006073  mov     rax, cs:__security_cookie
0x18000607a  xor     rax, rsp
0x18000607d  mov     [rbp+0A00h+var_40], rax
0x180006084  mov     rbx, r9
0x180006087  mov     r12d, r8d
0x18000608a  mov     r14, rdx
0x18000608d  mov     r15, rcx
0x180006090  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180006097  mov     [rsp+0B00h+var_AD0], rax
0x18000609c  xor     r13d, r13d
0x18000609f  mov     [rsp+0B00h+var_AC8], r13
0x1800060a4  mov     [rsp+0B00h+var_AC0], r13
0x1800060a9  mov     [rsp+0B00h+var_AB8], r13d
0x1800060ae  xorps   xmm0, xmm0
0x1800060b1  xor     eax, eax
0x1800060b3  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800060b8  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800060bd  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800060c2  mov     [rsp+0B00h+var_A88], r13b
0x1800060c7  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800060cc  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800060d1  mov     edi, eax
0x1800060d3  test    eax, eax
0x1800060d5  js      loc_18000635B
0x1800060db  mov     [rsp+0B00h+var_A88], 1
0x1800060e0  test    rbx, rbx
0x1800060e3  jz      short loc_180006122
0x1800060e5  jmp     short loc_18000611A
0x1800060e7  mov     rsi, [rbx+8]
0x1800060eb  test    rsi, rsi
0x1800060ee  jz      short loc_180006116
0x1800060f0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800060f5  call    cs:__imp_EnterCriticalSection
0x1800060fb  mov     r8, rsi; unsigned __int16 *
0x1800060fe  mov     rdx, rdi; unsigned __int16 *
0x180006101  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006106  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000610b  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006110  call    cs:__imp_LeaveCriticalSection
0x180006116  add     rbx, 10h
0x18000611a  mov     rdi, [rbx]
0x18000611d  test    rdi, rdi
0x180006120  jnz     short loc_1800060E7
0x180006122  mov     rax, [r15]
0x180006125  lea     rdx, [rsp+0B00h+var_AD0]
0x18000612a  mov     rcx, r15
0x18000612d  mov     rax, [rax+28h]
0x180006131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006136  mov     ebx, eax
0x180006138  test    eax, eax
0x18000613a  js      loc_1800062FA
0x180006140  mov     rbx, cs:hInstance
0x180006147  mov     edi, 104h
0x18000614c  mov     r8d, edi; nSize
0x18000614f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180006153  mov     rcx, rbx; hModule
0x180006156  call    cs:__imp_GetModuleFileNameW
0x18000615c  test    eax, eax
0x18000615e  jnz     short loc_18000616A
0x180006160  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006165  jmp     loc_1800062F8
0x18000616a  cmp     eax, edi
0x18000616c  jnz     short loc_180006178
0x18000616e  mov     ebx, 8007007Ah
0x180006173  jmp     loc_1800062FA
0x180006178  lea     rdx, [rbp+0A00h+Filename]
0x18000617c  mov     ecx, r13d
0x18000617f  mov     r9d, 27h ; '''
0x180006185  movzx   r8d, word ptr [rdx]
0x180006189  test    r8w, r8w
0x18000618d  jz      short loc_1800061BF
0x18000618f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180006198  cmp     r8w, r9w
0x18000619c  jnz     short loc_1800061B1
0x18000619e  cmp     ecx, 206h
0x1800061a4  jnb     short loc_1800061B1
0x1800061a6  inc     ecx
0x1800061a8  mov     [rbp+rcx*2+0A00h+Src], r9w
0x1800061b1  add     rdx, 2
0x1800061b5  inc     ecx
0x1800061b7  cmp     ecx, 207h
0x1800061bd  jb      short loc_180006185
0x1800061bf  mov     [rbp+rcx*2+0A00h+Src], r13w
0x1800061c8  test    rbx, rbx
0x1800061cb  jz      short loc_1800061F1
0x1800061cd  xor     ecx, ecx; lpModuleName
0x1800061cf  call    cs:__imp_GetModuleHandleW
0x1800061d5  cmp     rbx, rax
0x1800061d8  jz      short loc_1800061F1
0x1800061da  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800061df  call    cs:__imp_EnterCriticalSection
0x1800061e5  lea     r8, [rbp+0A00h+Src]
0x1800061ec  jmp     loc_18000628B
0x1800061f1  mov     edi, 22h ; '"'
0x1800061f6  mov     [rbp+0A00h+var_460], di
0x1800061fd  lea     rcx, [rbp+0A00h+Src]
0x180006204  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006208  mov     rax, rbx
0x18000620b  inc     rax
0x18000620e  cmp     [rcx+rax*2], r13w
0x180006213  jnz     short loc_18000620B
0x180006215  inc     eax
0x180006217  movsxd  r8, eax
0x18000621a  add     r8, r8; Size
0x18000621d  jz      short loc_18000623F
0x18000621f  cmp     r8, 414h
0x180006226  ja      loc_180006308
0x18000622c  lea     rdx, [rbp+0A00h+Src]; Src
0x180006233  lea     rcx, [rbp+0A00h+var_45E]; void *
0x18000623a  call    memcpy_0
0x18000623f  lea     rax, [rbp+0A00h+var_460]
0x180006246  inc     rbx
0x180006249  cmp     [rax+rbx*2], r13w
0x18000624e  jnz     short loc_180006246
0x180006250  movsxd  rax, ebx
0x180006253  mov     [rbp+rax*2+0A00h+var_460], di
0x18000625b  lea     rcx, ds:2[rax*2]
0x180006263  cmp     rcx, 418h
0x18000626a  jnb     loc_180006391
0x180006270  mov     [rbp+rcx+0A00h+var_460], r13w
0x180006279  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000627e  call    cs:__imp_EnterCriticalSection
0x180006284  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000628b  lea     rdx, aModule; "Module"
0x180006292  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006297  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000629c  mov     ebx, eax
0x18000629e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800062a3  call    cs:__imp_LeaveCriticalSection
0x1800062a9  neg     ebx
0x1800062ab  sbb     ebx, ebx
0x1800062ad  mov     edi, 8007000Eh
0x1800062b2  not     ebx
0x1800062b4  and     ebx, edi
0x1800062b6  test    ebx, ebx
0x1800062b8  js      short loc_1800062FA
0x1800062ba  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800062bf  call    cs:__imp_EnterCriticalSection
0x1800062c5  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x1800062cc  lea     rdx, aModuleRaw; "Module_Raw"
0x1800062d3  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800062d8  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800062dd  mov     ebx, eax
0x1800062df  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800062e4  call    cs:__imp_LeaveCriticalSection
0x1800062ea  mov     ecx, ebx
0x1800062ec  neg     ecx
0x1800062ee  sbb     eax, eax
0x1800062f0  not     eax
0x1800062f2  and     eax, edi
0x1800062f4  test    ebx, ebx
0x1800062f6  jnz     short loc_18000631C
0x1800062f8  mov     ebx, eax
0x1800062fa  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800062ff  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006304  mov     eax, ebx
0x180006306  jmp     short loc_180006367
0x180006308  call    cs:__imp__o__errno
0x18000630e  mov     [rax], edi
0x180006310  call    _invalid_parameter_noinfo
0x180006315  mov     ebx, 80004005h
0x18000631a  jmp     short loc_1800062FA
0x18000631c  test    r12d, r12d
0x18000631f  jz      short loc_180006330
0x180006321  test    r14, r14
0x180006324  jz      short loc_180006354
0x180006326  mov     [rsp+0B00h+var_AE0], 1
0x18000632e  jmp     short loc_18000633A
0x180006330  test    r14, r14
0x180006333  jz      short loc_180006354
0x180006335  mov     [rsp+0B00h+var_AE0], r13d; int
0x18000633a  lea     r9, aRegistry; "REGISTRY"
0x180006341  mov     r8, r14; unsigned __int16 *
0x180006344  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006348  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000634d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006352  jmp     short loc_1800062F8
0x180006354  mov     ebx, 80070057h
0x180006359  jmp     short loc_1800062FA
0x18000635b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006360  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006365  mov     eax, edi
0x180006367  mov     rcx, [rbp+0A00h+var_40]
0x18000636e  xor     rcx, rsp; StackCookie
0x180006371  call    __security_check_cookie
0x180006376  mov     rbx, [rsp+0B00h+arg_10]
0x18000637e  add     rsp, 0AD0h
0x180006385  pop     r15
0x180006387  pop     r14
0x180006389  pop     r13
0x18000638b  pop     r12
0x18000638d  pop     rdi
0x18000638e  pop     rsi
0x18000638f  pop     rbp
0x180006390  retn
0x180006391  call    __report_rangecheckfailure
```
