# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000547c`
- end: `0x180005793`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005450`
- `0x180005ae0`

## callees

- `0x1800017c8`
- `0x180002824`
- `0x1800029fc`
- `0x180003484`
- `0x180003edc`
- `0x180004818`
- `0x18000547c`
- `0x180006030`
- `0x180007010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000564e`
- `msvcrt!memcpy_s` at `0x18000564e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005538`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005538`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000551d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005606`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000569b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000551d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005606`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000569b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800056dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f6`

## string_xrefs

- `0x180005720`: `REGISTRY`

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
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  int v22; // ebx
  int v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 Source[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v26[0] = 0;
  v26[1] = 0;
  v25 = &ATL::CRegObject::`vftable';
  v27 = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v29 = 1;
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
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_33;
      }
      v15 = Filename;
      v16 = 0;
      do
      {
        v17 = *v15;
        if ( !*v15 )
          break;
        Source[v16] = v17;
        if ( v17 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Source[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Source[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v19 = -1;
        v32 = 34;
        v20 = -1;
        do
          ++v20;
        while ( Source[v20] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v20 + 1)) )
        {
          v11 = -2147467259;
          goto LABEL_33;
        }
        do
          ++v19;
        while ( *(_WORD *)&Destination[2 * v19 - 2] );
        v21 = 2LL * (int)v19 + 2;
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        if ( v21 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v21 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v18 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = Source;
      }
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = v22 == 0 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_33:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v25,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  a3 != 0);
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v11 = Error;
    goto LABEL_33;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000547c  mov     [rsp-8+arg_10], rbx
0x180005481  push    rbp
0x180005482  push    rsi
0x180005483  push    rdi
0x180005484  push    r12
0x180005486  push    r13
0x180005488  push    r14
0x18000548a  push    r15
0x18000548c  lea     rbp, [rsp-9D0h]
0x180005494  sub     rsp, 0AD0h
0x18000549b  mov     rax, cs:__security_cookie
0x1800054a2  xor     rax, rsp
0x1800054a5  mov     [rbp+0A00h+var_40], rax
0x1800054ac  xor     r13d, r13d
0x1800054af  mov     r12d, edx
0x1800054b2  xorps   xmm0, xmm0
0x1800054b5  mov     [rsp+0B00h+var_AC8], r13
0x1800054ba  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800054c1  mov     [rsp+0B00h+var_AC0], r13
0x1800054c6  mov     [rsp+0B00h+var_AD0], rax
0x1800054cb  mov     r14, rcx
0x1800054ce  xor     eax, eax
0x1800054d0  mov     [rsp+0B00h+var_AB8], r13d
0x1800054d5  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800054da  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800054df  mov     rbx, r9
0x1800054e2  mov     [rsp+0B00h+var_A88], r13b
0x1800054e7  mov     r15d, r8d
0x1800054ea  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800054ef  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800054f4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800054f9  mov     edi, eax
0x1800054fb  test    eax, eax
0x1800054fd  js      loc_180005757
0x180005503  mov     [rsp+0B00h+var_A88], 1
0x180005508  test    rbx, rbx
0x18000550b  jz      short loc_18000554A
0x18000550d  jmp     short loc_180005542
0x18000550f  mov     rsi, [rbx+8]
0x180005513  test    rsi, rsi
0x180005516  jz      short loc_18000553E
0x180005518  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000551d  call    cs:__imp_EnterCriticalSection
0x180005523  mov     r8, rsi; unsigned __int16 *
0x180005526  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000552b  mov     rdx, rdi; unsigned __int16 *
0x18000552e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005533  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005538  call    cs:__imp_LeaveCriticalSection
0x18000553e  add     rbx, 10h
0x180005542  mov     rdi, [rbx]
0x180005545  test    rdi, rdi
0x180005548  jnz     short loc_18000550F
0x18000554a  mov     rax, [r14]
0x18000554d  lea     rdx, [rsp+0B00h+var_AD0]
0x180005552  mov     rcx, r14
0x180005555  mov     rax, [rax+28h]
0x180005559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000555e  mov     ebx, eax
0x180005560  test    eax, eax
0x180005562  js      loc_180005749
0x180005568  mov     rbx, cs:hModule
0x18000556f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005576  mov     edi, 104h
0x18000557b  mov     rcx, rbx; hModule
0x18000557e  mov     r8d, edi; nSize
0x180005581  call    cs:__imp_GetModuleFileNameW
0x180005587  test    eax, eax
0x180005589  jnz     short loc_180005597
0x18000558b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005590  mov     ebx, eax
0x180005592  jmp     loc_180005749
0x180005597  cmp     eax, edi
0x180005599  jnz     short loc_1800055A5
0x18000559b  mov     ebx, 8007007Ah
0x1800055a0  jmp     loc_180005749
0x1800055a5  lea     rdx, [rbp+0A00h+Filename]
0x1800055ac  mov     ecx, r13d
0x1800055af  mov     r9d, 27h ; '''
0x1800055b5  movzx   r8d, word ptr [rdx]
0x1800055b9  test    r8w, r8w
0x1800055bd  jz      short loc_1800055E9
0x1800055bf  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800055c5  cmp     r8w, r9w
0x1800055c9  jnz     short loc_1800055DB
0x1800055cb  cmp     ecx, 206h
0x1800055d1  jnb     short loc_1800055DB
0x1800055d3  inc     ecx
0x1800055d5  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800055db  add     rdx, 2
0x1800055df  inc     ecx
0x1800055e1  cmp     ecx, 207h
0x1800055e7  jb      short loc_1800055B5
0x1800055e9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x1800055ef  test    rbx, rbx
0x1800055f2  jz      short loc_180005615
0x1800055f4  xor     ecx, ecx; lpModuleName
0x1800055f6  call    cs:__imp_GetModuleHandleW
0x1800055fc  cmp     rbx, rax
0x1800055ff  jz      short loc_180005615
0x180005601  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005606  call    cs:__imp_EnterCriticalSection
0x18000560c  lea     r8, [rbp+0A00h+Source]
0x180005610  jmp     loc_1800056A8
0x180005615  mov     edi, 22h ; '"'
0x18000561a  lea     rcx, [rbp+0A00h+Source]
0x18000561e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005622  mov     [rbp+0A00h+var_460], di
0x180005629  mov     rax, rbx
0x18000562c  inc     rax
0x18000562f  cmp     [rcx+rax*2], r13w
0x180005634  jnz     short loc_18000562C
0x180005636  inc     eax
0x180005638  lea     r8, [rbp+0A00h+Source]; Source
0x18000563c  movsxd  r9, eax
0x18000563f  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180005646  add     r9, r9; SourceSize
0x180005649  mov     edx, 414h; DestinationSize
0x18000564e  call    cs:__imp_memcpy_s
0x180005654  test    eax, eax
0x180005656  jnz     loc_180005744
0x18000565c  lea     rax, [rbp+0A00h+var_460]
0x180005663  inc     rbx
0x180005666  cmp     [rax+rbx*2], r13w
0x18000566b  jnz     short loc_180005663
0x18000566d  movsxd  rax, ebx
0x180005670  lea     rcx, ds:2[rax*2]
0x180005678  mov     [rbp+rax*2+0A00h+var_460], di
0x180005680  cmp     rcx, 418h
0x180005687  jnb     loc_18000578D
0x18000568d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180005696  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000569b  call    cs:__imp_EnterCriticalSection
0x1800056a1  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800056a8  lea     rdx, aModule; "Module"
0x1800056af  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800056b4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800056b9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800056be  mov     ebx, eax
0x1800056c0  call    cs:__imp_LeaveCriticalSection
0x1800056c6  neg     ebx
0x1800056c8  mov     edi, 8007000Eh
0x1800056cd  sbb     ebx, ebx
0x1800056cf  not     ebx
0x1800056d1  and     ebx, edi
0x1800056d3  test    ebx, ebx
0x1800056d5  js      short loc_180005749
0x1800056d7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800056dc  call    cs:__imp_EnterCriticalSection
0x1800056e2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x1800056e6  lea     rdx, aModuleRaw; "Module_Raw"
0x1800056ed  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800056f2  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800056f7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800056fc  mov     ebx, eax
0x1800056fe  call    cs:__imp_LeaveCriticalSection
0x180005704  mov     ecx, ebx
0x180005706  neg     ecx
0x180005708  sbb     eax, eax
0x18000570a  not     eax
0x18000570c  and     eax, edi
0x18000570e  test    ebx, ebx
0x180005710  jz      loc_180005590
0x180005716  mov     eax, r13d
0x180005719  movzx   r8d, r12w; unsigned __int16 *
0x18000571d  test    r15d, r15d
0x180005720  lea     r9, aRegistry; "REGISTRY"
0x180005727  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000572e  setnz   al
0x180005731  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005736  mov     [rsp+0B00h+var_AE0], eax; int
0x18000573a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000573f  jmp     loc_180005590
0x180005744  mov     ebx, 80004005h
0x180005749  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000574e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005753  mov     eax, ebx
0x180005755  jmp     short loc_180005763
0x180005757  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000575c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005761  mov     eax, edi
0x180005763  mov     rcx, [rbp+0A00h+var_40]
0x18000576a  xor     rcx, rsp; StackCookie
0x18000576d  call    __security_check_cookie
0x180005772  mov     rbx, [rsp+0B00h+arg_10]
0x18000577a  add     rsp, 0AD0h
0x180005781  pop     r15
0x180005783  pop     r14
0x180005785  pop     r13
0x180005787  pop     r12
0x180005789  pop     rdi
0x18000578a  pop     rsi
0x18000578b  pop     rbp
0x18000578c  retn
0x18000578d  call    __report_rangecheckfailure
```
