# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800093cc`
- end: `0x18000970a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009720`

## callees

- `0x180001898`
- `0x180002028`
- `0x180002178`
- `0x180002a88`
- `0x180002f5c`
- `0x180003878`
- `0x1800093cc`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800095aa`
- `msvcrt!memcpy_s` at `0x1800095aa`
- `KERNEL32!GetModuleHandleW` at `0x180009549`
- `KERNEL32!GetModuleHandleW` at `0x180009549`
- `KERNEL32!LeaveCriticalSection` at `0x180009488`
- `KERNEL32!LeaveCriticalSection` at `0x18000961c`
- `KERNEL32!LeaveCriticalSection` at `0x180009661`
- `KERNEL32!LeaveCriticalSection` at `0x180009488`
- `KERNEL32!LeaveCriticalSection` at `0x18000961c`
- `KERNEL32!LeaveCriticalSection` at `0x180009661`
- `KERNEL32!GetModuleFileNameW` at `0x1800094ce`
- `KERNEL32!GetModuleFileNameW` at `0x1800094ce`
- `KERNEL32!EnterCriticalSection` at `0x18000946d`
- `KERNEL32!EnterCriticalSection` at `0x180009559`
- `KERNEL32!EnterCriticalSection` at `0x1800095f7`
- `KERNEL32!EnterCriticalSection` at `0x18000963c`
- `KERNEL32!EnterCriticalSection` at `0x18000946d`
- `KERNEL32!EnterCriticalSection` at `0x180009559`
- `KERNEL32!EnterCriticalSection` at `0x1800095f7`
- `KERNEL32!EnterCriticalSection` at `0x18000963c`

## string_xrefs

- `0x180009697`: `REGISTRY`

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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
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
      goto LABEL_39;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_39;
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
          goto LABEL_39;
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
LABEL_39:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
      {
        if ( a3 )
        {
          if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 1);
            goto LABEL_11;
          }
        }
        else if ( a2 )
        {
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 0);
          goto LABEL_11;
        }
        v11 = -2147024809;
        goto LABEL_39;
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
LABEL_11:
    v11 = Error;
    goto LABEL_39;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800093cc  mov     [rsp-8+arg_10], rbx
0x1800093d1  push    rbp
0x1800093d2  push    rsi
0x1800093d3  push    rdi
0x1800093d4  push    r12
0x1800093d6  push    r13
0x1800093d8  push    r14
0x1800093da  push    r15
0x1800093dc  lea     rbp, [rsp-9D0h]
0x1800093e4  sub     rsp, 0AD0h
0x1800093eb  mov     rax, cs:__security_cookie
0x1800093f2  xor     rax, rsp
0x1800093f5  mov     [rbp+0A00h+var_40], rax
0x1800093fc  xor     r13d, r13d
0x1800093ff  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009406  xorps   xmm0, xmm0
0x180009409  mov     [rsp+0B00h+var_AD0], rax
0x18000940e  xor     eax, eax
0x180009410  mov     [rsp+0B00h+var_AC8], r13
0x180009415  mov     r15, rcx
0x180009418  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000941d  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180009422  mov     [rsp+0B00h+var_AC0], r13
0x180009427  mov     rbx, r9
0x18000942a  mov     [rsp+0B00h+var_AB8], r13d
0x18000942f  mov     r12d, r8d
0x180009432  mov     [rsp+0B00h+var_A88], r13b
0x180009437  mov     r14, rdx
0x18000943a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000943f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180009444  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009449  mov     edi, eax
0x18000944b  test    eax, eax
0x18000944d  js      loc_1800096CE
0x180009453  mov     [rsp+0B00h+var_A88], 1
0x180009458  test    rbx, rbx
0x18000945b  jz      short loc_18000949A
0x18000945d  jmp     short loc_180009492
0x18000945f  mov     rsi, [rbx+8]
0x180009463  test    rsi, rsi
0x180009466  jz      short loc_18000948E
0x180009468  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000946d  call    cs:__imp_EnterCriticalSection
0x180009473  mov     r8, rsi; unsigned __int16 *
0x180009476  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000947b  mov     rdx, rdi; unsigned __int16 *
0x18000947e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009483  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009488  call    cs:__imp_LeaveCriticalSection
0x18000948e  add     rbx, 10h
0x180009492  mov     rdi, [rbx]
0x180009495  test    rdi, rdi
0x180009498  jnz     short loc_18000945F
0x18000949a  mov     rax, [r15]
0x18000949d  lea     rdx, [rsp+0B00h+var_AD0]
0x1800094a2  mov     rcx, r15
0x1800094a5  mov     rax, [rax+28h]
0x1800094a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ae  mov     ebx, eax
0x1800094b0  test    eax, eax
0x1800094b2  js      loc_1800096C0
0x1800094b8  mov     rbx, cs:hInstance
0x1800094bf  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800094c3  mov     edi, 104h
0x1800094c8  mov     rcx, rbx; hModule
0x1800094cb  mov     r8d, edi; nSize
0x1800094ce  call    cs:__imp_GetModuleFileNameW
0x1800094d4  test    eax, eax
0x1800094d6  jnz     short loc_1800094E4
0x1800094d8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800094dd  mov     ebx, eax
0x1800094df  jmp     loc_1800096C0
0x1800094e4  cmp     eax, edi
0x1800094e6  jnz     short loc_1800094F2
0x1800094e8  mov     ebx, 8007007Ah
0x1800094ed  jmp     loc_1800096C0
0x1800094f2  lea     rdx, [rbp+0A00h+Filename]
0x1800094f6  mov     ecx, r13d
0x1800094f9  mov     r9d, 27h ; '''
0x1800094ff  movzx   r8d, word ptr [rdx]
0x180009503  test    r8w, r8w
0x180009507  jz      short loc_180009539
0x180009509  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180009512  cmp     r8w, r9w
0x180009516  jnz     short loc_18000952B
0x180009518  cmp     ecx, 206h
0x18000951e  jnb     short loc_18000952B
0x180009520  inc     ecx
0x180009522  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000952b  add     rdx, 2
0x18000952f  inc     ecx
0x180009531  cmp     ecx, 207h
0x180009537  jb      short loc_1800094FF
0x180009539  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180009542  test    rbx, rbx
0x180009545  jz      short loc_18000956B
0x180009547  xor     ecx, ecx; lpModuleName
0x180009549  call    cs:__imp_GetModuleHandleW
0x18000954f  cmp     rbx, rax
0x180009552  jz      short loc_18000956B
0x180009554  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009559  call    cs:__imp_EnterCriticalSection
0x18000955f  lea     r8, [rbp+0A00h+Source]
0x180009566  jmp     loc_180009604
0x18000956b  mov     edi, 22h ; '"'
0x180009570  lea     rcx, [rbp+0A00h+Source]
0x180009577  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000957b  mov     [rbp+0A00h+var_460], di
0x180009582  mov     rax, rbx
0x180009585  inc     rax
0x180009588  cmp     [rcx+rax*2], r13w
0x18000958d  jnz     short loc_180009585
0x18000958f  inc     eax
0x180009591  lea     r8, [rbp+0A00h+Source]; Source
0x180009598  movsxd  r9, eax
0x18000959b  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800095a2  add     r9, r9; SourceSize
0x1800095a5  mov     edx, 414h; DestinationSize
0x1800095aa  call    cs:__imp_memcpy_s
0x1800095b0  test    eax, eax
0x1800095b2  jnz     loc_1800096BB
0x1800095b8  lea     rax, [rbp+0A00h+var_460]
0x1800095bf  inc     rbx
0x1800095c2  cmp     [rax+rbx*2], r13w
0x1800095c7  jnz     short loc_1800095BF
0x1800095c9  movsxd  rax, ebx
0x1800095cc  lea     rcx, ds:2[rax*2]
0x1800095d4  mov     [rbp+rax*2+0A00h+var_460], di
0x1800095dc  cmp     rcx, 418h
0x1800095e3  jnb     loc_180009704
0x1800095e9  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800095f2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800095f7  call    cs:__imp_EnterCriticalSection
0x1800095fd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180009604  lea     rdx, aModule; "Module"
0x18000960b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009610  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009615  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000961a  mov     ebx, eax
0x18000961c  call    cs:__imp_LeaveCriticalSection
0x180009622  neg     ebx
0x180009624  mov     edi, 8007000Eh
0x180009629  sbb     ebx, ebx
0x18000962b  not     ebx
0x18000962d  and     ebx, edi
0x18000962f  test    ebx, ebx
0x180009631  js      loc_1800096C0
0x180009637  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000963c  call    cs:__imp_EnterCriticalSection
0x180009642  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180009649  lea     rdx, aModuleRaw; "Module_Raw"
0x180009650  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009655  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000965a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000965f  mov     ebx, eax
0x180009661  call    cs:__imp_LeaveCriticalSection
0x180009667  mov     ecx, ebx
0x180009669  neg     ecx
0x18000966b  sbb     eax, eax
0x18000966d  not     eax
0x18000966f  and     eax, edi
0x180009671  test    ebx, ebx
0x180009673  jz      loc_1800094DD
0x180009679  test    r12d, r12d
0x18000967c  jz      short loc_18000968D
0x18000967e  test    r14, r14
0x180009681  jz      short loc_1800096B4
0x180009683  mov     [rsp+0B00h+var_AE0], 1
0x18000968b  jmp     short loc_180009697
0x18000968d  test    r14, r14
0x180009690  jz      short loc_1800096B4
0x180009692  mov     [rsp+0B00h+var_AE0], r13d; int
0x180009697  lea     r9, aRegistry; "REGISTRY"
0x18000969e  mov     r8, r14; unsigned __int16 *
0x1800096a1  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800096a5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800096aa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800096af  jmp     loc_1800094DD
0x1800096b4  mov     ebx, 80070057h
0x1800096b9  jmp     short loc_1800096C0
0x1800096bb  mov     ebx, 80004005h
0x1800096c0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800096c5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800096ca  mov     eax, ebx
0x1800096cc  jmp     short loc_1800096DA
0x1800096ce  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800096d3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800096d8  mov     eax, edi
0x1800096da  mov     rcx, [rbp+0A00h+var_40]
0x1800096e1  xor     rcx, rsp; StackCookie
0x1800096e4  call    __security_check_cookie
0x1800096e9  mov     rbx, [rsp+0B00h+arg_10]
0x1800096f1  add     rsp, 0AD0h
0x1800096f8  pop     r15
0x1800096fa  pop     r14
0x1800096fc  pop     r13
0x1800096fe  pop     r12
0x180009700  pop     rdi
0x180009701  pop     rsi
0x180009702  pop     rbp
0x180009703  retn
0x180009704  call    __report_rangecheckfailure
```
