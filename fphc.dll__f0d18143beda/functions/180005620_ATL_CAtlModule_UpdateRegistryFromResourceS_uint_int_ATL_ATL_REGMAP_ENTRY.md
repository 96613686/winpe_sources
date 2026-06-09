# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005620`
- end: `0x18000594a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `810`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005ae0`
- `0x180005bf0`
- `0x180008b60`

## callees

- `0x180002408`
- `0x180002c28`
- `0x180002d88`
- `0x1800037b8`
- `0x1800042bc`
- `0x180004a88`
- `0x180005620`
- `0x180011340`
- `0x180012010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005801`
- `msvcrt!memcpy_s` at `0x180005801`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005725`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005725`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000584e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000588f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000584e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000588f`

## string_xrefs

- `0x1800058cc`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v6; // r14
  int v7; // edi
  const unsigned __int16 *v8; // rsi
  const unsigned __int16 *v9; // rdi
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v21; // ebx
  int v22; // ebx
  const unsigned __int16 *v23; // r8
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v6 = ATL::_pAtlModule;
  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v29 = 0;
  v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v7 >= 0 )
  {
    v29 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v9 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v8 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v8 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v9, v8);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v10 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v25);
    if ( v10 < 0 )
      goto LABEL_36;
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v10 = -2147024774;
        goto LABEL_36;
      }
      v14 = Filename;
      v15 = 0;
      do
      {
        v16 = *v14;
        if ( !*v14 )
          break;
        Source[v15] = v16;
        if ( v16 == 39 && (unsigned int)v15 < 0x206 )
        {
          LODWORD(v15) = v15 + 1;
          Source[(unsigned int)v15] = 39;
        }
        ++v14;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < 0x207 );
      Source[v15] = 0;
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v32 = 34;
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( Source[v19] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v19 + 1)) )
        {
          v10 = -2147467259;
          goto LABEL_36;
        }
        do
          ++v18;
        while ( *(_WORD *)&Destination[2 * v18 - 2] );
        *(_WORD *)&Destination[2 * (int)v18 - 2] = 34;
        v20 = 2LL * (int)v18 + 2;
        if ( v20 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v20 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v17 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v17 = Source;
      }
      v21 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v17);
      LeaveCriticalSection(&CriticalSection);
      v10 = v21 == 0 ? 0x8007000E : 0;
      if ( v10 < 0 )
      {
LABEL_36:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v10;
      }
      EnterCriticalSection(&CriticalSection);
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v22 == 0 ? 0x8007000E : 0;
      if ( v22 )
      {
        if ( a3 )
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, v23, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, v23, L"REGISTRY", 0);
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v10 = Error;
    goto LABEL_36;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005620  mov     [rsp-8+arg_0], rbx
0x180005625  mov     [rsp-8+arg_8], rsi
0x18000562a  push    rbp
0x18000562b  push    rdi
0x18000562c  push    r12
0x18000562e  push    r14
0x180005630  push    r15
0x180005632  lea     rbp, [rsp-9D0h]
0x18000563a  sub     rsp, 0AD0h
0x180005641  mov     rax, cs:__security_cookie
0x180005648  xor     rax, rsp
0x18000564b  mov     [rbp+9F0h+var_30], rax
0x180005652  mov     rbx, r9
0x180005655  mov     r15d, r8d
0x180005658  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000565f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005666  mov     [rsp+0AF0h+var_AC0], rax
0x18000566b  xor     r12d, r12d
0x18000566e  mov     [rsp+0AF0h+var_AB8], r12
0x180005673  mov     [rsp+0AF0h+var_AB0], r12
0x180005678  mov     [rsp+0AF0h+var_AA8], r12d
0x18000567d  xorps   xmm0, xmm0
0x180005680  xor     eax, eax
0x180005682  movups  xmmword ptr [rsp+0AF0h+CriticalSection.DebugInfo], xmm0
0x180005687  movups  xmmword ptr [rsp+0AF0h+CriticalSection.OwningThread], xmm0
0x18000568c  mov     [rsp+0AF0h+CriticalSection.SpinCount], rax
0x180005691  mov     [rsp+0AF0h+var_A78], r12b
0x180005696  lea     rcx, [rsp+0AF0h+CriticalSection]; this
0x18000569b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800056a0  mov     edi, eax
0x1800056a2  test    eax, eax
0x1800056a4  js      loc_18000590D
0x1800056aa  mov     [rsp+0AF0h+var_A78], 1
0x1800056af  test    rbx, rbx
0x1800056b2  jz      short loc_1800056F1
0x1800056b4  jmp     short loc_1800056E9
0x1800056b6  mov     rsi, [rbx+8]
0x1800056ba  test    rsi, rsi
0x1800056bd  jz      short loc_1800056E5
0x1800056bf  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x1800056c4  call    cs:__imp_EnterCriticalSection
0x1800056ca  mov     r8, rsi; unsigned __int16 *
0x1800056cd  mov     rdx, rdi; unsigned __int16 *
0x1800056d0  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x1800056d5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800056da  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x1800056df  call    cs:__imp_LeaveCriticalSection
0x1800056e5  add     rbx, 10h
0x1800056e9  mov     rdi, [rbx]
0x1800056ec  test    rdi, rdi
0x1800056ef  jnz     short loc_1800056B6
0x1800056f1  mov     rax, [r14]
0x1800056f4  lea     rdx, [rsp+0AF0h+var_AC0]
0x1800056f9  mov     rcx, r14
0x1800056fc  mov     rax, [rax+28h]
0x180005700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005705  mov     ebx, eax
0x180005707  test    eax, eax
0x180005709  js      loc_1800058FF
0x18000570f  mov     rbx, cs:hInstance
0x180005716  mov     edi, 104h
0x18000571b  mov     r8d, edi; nSize
0x18000571e  lea     rdx, [rbp+9F0h+Filename]; lpFilename
0x180005722  mov     rcx, rbx; hModule
0x180005725  call    cs:__imp_GetModuleFileNameW
0x18000572b  test    eax, eax
0x18000572d  jnz     short loc_18000573B
0x18000572f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005734  mov     ebx, eax
0x180005736  jmp     loc_1800058FF
0x18000573b  cmp     eax, edi
0x18000573d  jnz     short loc_180005749
0x18000573f  mov     ebx, 8007007Ah
0x180005744  jmp     loc_1800058FF
0x180005749  lea     rdx, [rbp+9F0h+Filename]
0x18000574d  mov     ecx, r12d
0x180005750  mov     r9d, 27h ; '''
0x180005756  movzx   r8d, word ptr [rdx]
0x18000575a  test    r8w, r8w
0x18000575e  jz      short loc_180005790
0x180005760  mov     [rbp+rcx*2+9F0h+Source], r8w
0x180005769  cmp     r8w, r9w
0x18000576d  jnz     short loc_180005782
0x18000576f  cmp     ecx, 206h
0x180005775  jnb     short loc_180005782
0x180005777  inc     ecx
0x180005779  mov     [rbp+rcx*2+9F0h+Source], r9w
0x180005782  add     rdx, 2
0x180005786  inc     ecx
0x180005788  cmp     ecx, 207h
0x18000578e  jb      short loc_180005756
0x180005790  mov     [rbp+rcx*2+9F0h+Source], r12w
0x180005799  test    rbx, rbx
0x18000579c  jz      short loc_1800057C2
0x18000579e  xor     ecx, ecx; lpModuleName
0x1800057a0  call    cs:__imp_GetModuleHandleW
0x1800057a6  cmp     rbx, rax
0x1800057a9  jz      short loc_1800057C2
0x1800057ab  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x1800057b0  call    cs:__imp_EnterCriticalSection
0x1800057b6  lea     r8, [rbp+9F0h+Source]
0x1800057bd  jmp     loc_18000585B
0x1800057c2  mov     edi, 22h ; '"'
0x1800057c7  mov     [rbp+9F0h+var_450], di
0x1800057ce  lea     rcx, [rbp+9F0h+Source]
0x1800057d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800057d9  mov     rax, rbx
0x1800057dc  inc     rax
0x1800057df  cmp     [rcx+rax*2], r12w
0x1800057e4  jnz     short loc_1800057DC
0x1800057e6  inc     eax
0x1800057e8  movsxd  r9, eax
0x1800057eb  add     r9, r9; SourceSize
0x1800057ee  lea     r8, [rbp+9F0h+Source]; Source
0x1800057f5  mov     edx, 414h; DestinationSize
0x1800057fa  lea     rcx, [rbp+9F0h+Destination]; Destination
0x180005801  call    cs:__imp_memcpy_s
0x180005807  test    eax, eax
0x180005809  jnz     loc_1800058FA
0x18000580f  lea     rax, [rbp+9F0h+var_450]
0x180005816  inc     rbx
0x180005819  cmp     [rax+rbx*2], r12w
0x18000581e  jnz     short loc_180005816
0x180005820  movsxd  rax, ebx
0x180005823  mov     [rbp+rax*2+9F0h+var_450], di
0x18000582b  lea     rcx, ds:2[rax*2]
0x180005833  cmp     rcx, 418h
0x18000583a  jnb     loc_180005944
0x180005840  mov     [rbp+rcx+9F0h+var_450], r12w
0x180005849  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x18000584e  call    cs:__imp_EnterCriticalSection
0x180005854  lea     r8, [rbp+9F0h+var_450]; unsigned __int16 *
0x18000585b  lea     rdx, aModule; "Module"
0x180005862  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180005867  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000586c  mov     ebx, eax
0x18000586e  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180005873  call    cs:__imp_LeaveCriticalSection
0x180005879  neg     ebx
0x18000587b  sbb     ebx, ebx
0x18000587d  mov     edi, 8007000Eh
0x180005882  not     ebx
0x180005884  and     ebx, edi
0x180005886  test    ebx, ebx
0x180005888  js      short loc_1800058FF
0x18000588a  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x18000588f  call    cs:__imp_EnterCriticalSection
0x180005895  lea     r8, [rbp+9F0h+Source]; unsigned __int16 *
0x18000589c  lea     rdx, aModuleRaw; "Module_Raw"
0x1800058a3  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x1800058a8  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800058ad  mov     ebx, eax
0x1800058af  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x1800058b4  call    cs:__imp_LeaveCriticalSection
0x1800058ba  mov     ecx, ebx
0x1800058bc  neg     ecx
0x1800058be  sbb     eax, eax
0x1800058c0  not     eax
0x1800058c2  and     eax, edi
0x1800058c4  test    ebx, ebx
0x1800058c6  jz      loc_180005734
0x1800058cc  lea     r9, aRegistry; "REGISTRY"
0x1800058d3  lea     rdx, [rbp+9F0h+Filename]; unsigned __int16 *
0x1800058d7  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1800058dc  test    r15d, r15d
0x1800058df  jz      short loc_1800058EB
0x1800058e1  mov     [rsp+0AF0h+var_AD0], 1
0x1800058e9  jmp     short loc_1800058F0
0x1800058eb  mov     [rsp+0AF0h+var_AD0], r12d; int
0x1800058f0  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800058f5  jmp     loc_180005734
0x1800058fa  mov     ebx, 80004005h
0x1800058ff  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180005904  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005909  mov     eax, ebx
0x18000590b  jmp     short loc_180005919
0x18000590d  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180005912  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005917  mov     eax, edi
0x180005919  mov     rcx, [rbp+9F0h+var_30]
0x180005920  xor     rcx, rsp; StackCookie
0x180005923  call    __security_check_cookie
0x180005928  lea     r11, [rsp+0AF0h+var_20]
0x180005930  mov     rbx, [r11+30h]
0x180005934  mov     rsi, [r11+38h]
0x180005938  mov     rsp, r11
0x18000593b  pop     r15
0x18000593d  pop     r14
0x18000593f  pop     r12
0x180005941  pop     rdi
0x180005942  pop     rbp
0x180005943  retn
0x180005944  call    __report_rangecheckfailure
```
