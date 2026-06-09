# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001217c`
- end: `0x180012493`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800127e0`

## callees

- `0x180001bb8`
- `0x18000d860`
- `0x18000dc5c`
- `0x18000e8d4`
- `0x18001033c`
- `0x1800110a8`
- `0x18001217c`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001234e`
- `msvcrt!memcpy_s` at `0x18001234e`
- `KERNEL32!EnterCriticalSection` at `0x18001221d`
- `KERNEL32!EnterCriticalSection` at `0x180012306`
- `KERNEL32!EnterCriticalSection` at `0x18001239b`
- `KERNEL32!EnterCriticalSection` at `0x1800123dc`
- `KERNEL32!EnterCriticalSection` at `0x18001221d`
- `KERNEL32!EnterCriticalSection` at `0x180012306`
- `KERNEL32!EnterCriticalSection` at `0x18001239b`
- `KERNEL32!EnterCriticalSection` at `0x1800123dc`
- `KERNEL32!GetModuleFileNameW` at `0x180012281`
- `KERNEL32!GetModuleFileNameW` at `0x180012281`
- `KERNEL32!LeaveCriticalSection` at `0x180012238`
- `KERNEL32!LeaveCriticalSection` at `0x1800123c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800123fe`
- `KERNEL32!LeaveCriticalSection` at `0x180012238`
- `KERNEL32!LeaveCriticalSection` at `0x1800123c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800123fe`
- `KERNEL32!GetModuleHandleW` at `0x1800122f6`
- `KERNEL32!GetModuleHandleW` at `0x1800122f6`

## string_xrefs

- `0x180012427`: `REGISTRY`

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

  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v29 = 0;
  v8 = ATL::CComCriticalSection::Init(&CriticalSection);
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
        v32 = 34;
        v19 = -1;
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
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        v21 = 2LL * (int)v19 + 2;
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
                  (const WCHAR *)&v25,
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
0x18001217c  mov     [rsp-8+arg_10], rbx
0x180012181  push    rbp
0x180012182  push    rsi
0x180012183  push    rdi
0x180012184  push    r12
0x180012186  push    r13
0x180012188  push    r14
0x18001218a  push    r15
0x18001218c  lea     rbp, [rsp-9D0h]
0x180012194  sub     rsp, 0AD0h
0x18001219b  mov     rax, cs:__security_cookie
0x1800121a2  xor     rax, rsp
0x1800121a5  mov     [rbp+0A00h+var_40], rax
0x1800121ac  mov     rbx, r9
0x1800121af  mov     r15d, r8d
0x1800121b2  mov     r12d, edx
0x1800121b5  mov     r14, rcx
0x1800121b8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800121bf  mov     [rsp+0B00h+var_AD0], rax
0x1800121c4  xor     r13d, r13d
0x1800121c7  mov     [rsp+0B00h+var_AC8], r13
0x1800121cc  mov     [rsp+0B00h+var_AC0], r13
0x1800121d1  mov     [rsp+0B00h+var_AB8], r13d
0x1800121d6  xorps   xmm0, xmm0
0x1800121d9  xor     eax, eax
0x1800121db  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800121e0  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800121e5  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800121ea  mov     [rsp+0B00h+var_A88], r13b
0x1800121ef  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800121f4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800121f9  mov     edi, eax
0x1800121fb  test    eax, eax
0x1800121fd  js      loc_180012457
0x180012203  mov     [rsp+0B00h+var_A88], 1
0x180012208  test    rbx, rbx
0x18001220b  jz      short loc_18001224A
0x18001220d  jmp     short loc_180012242
0x18001220f  mov     rsi, [rbx+8]
0x180012213  test    rsi, rsi
0x180012216  jz      short loc_18001223E
0x180012218  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001221d  call    cs:__imp_EnterCriticalSection
0x180012223  mov     r8, rsi; unsigned __int16 *
0x180012226  mov     rdx, rdi; unsigned __int16 *
0x180012229  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18001222e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180012233  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180012238  call    cs:__imp_LeaveCriticalSection
0x18001223e  add     rbx, 10h
0x180012242  mov     rdi, [rbx]
0x180012245  test    rdi, rdi
0x180012248  jnz     short loc_18001220F
0x18001224a  mov     rax, [r14]
0x18001224d  lea     rdx, [rsp+0B00h+var_AD0]
0x180012252  mov     rcx, r14
0x180012255  mov     rax, [rax+28h]
0x180012259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225e  mov     ebx, eax
0x180012260  test    eax, eax
0x180012262  js      loc_180012449
0x180012268  mov     rbx, cs:hModule
0x18001226f  mov     edi, 104h
0x180012274  mov     r8d, edi; nSize
0x180012277  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18001227e  mov     rcx, rbx; hModule
0x180012281  call    cs:__imp_GetModuleFileNameW
0x180012287  test    eax, eax
0x180012289  jnz     short loc_180012297
0x18001228b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012290  mov     ebx, eax
0x180012292  jmp     loc_180012449
0x180012297  cmp     eax, edi
0x180012299  jnz     short loc_1800122A5
0x18001229b  mov     ebx, 8007007Ah
0x1800122a0  jmp     loc_180012449
0x1800122a5  lea     rdx, [rbp+0A00h+Filename]
0x1800122ac  mov     ecx, r13d
0x1800122af  mov     r9d, 27h ; '''
0x1800122b5  movzx   r8d, word ptr [rdx]
0x1800122b9  test    r8w, r8w
0x1800122bd  jz      short loc_1800122E9
0x1800122bf  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800122c5  cmp     r8w, r9w
0x1800122c9  jnz     short loc_1800122DB
0x1800122cb  cmp     ecx, 206h
0x1800122d1  jnb     short loc_1800122DB
0x1800122d3  inc     ecx
0x1800122d5  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800122db  add     rdx, 2
0x1800122df  inc     ecx
0x1800122e1  cmp     ecx, 207h
0x1800122e7  jb      short loc_1800122B5
0x1800122e9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x1800122ef  test    rbx, rbx
0x1800122f2  jz      short loc_180012315
0x1800122f4  xor     ecx, ecx; lpModuleName
0x1800122f6  call    cs:__imp_GetModuleHandleW
0x1800122fc  cmp     rbx, rax
0x1800122ff  jz      short loc_180012315
0x180012301  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180012306  call    cs:__imp_EnterCriticalSection
0x18001230c  lea     r8, [rbp+0A00h+Source]
0x180012310  jmp     loc_1800123A8
0x180012315  mov     edi, 22h ; '"'
0x18001231a  mov     [rbp+0A00h+var_460], di
0x180012321  lea     rcx, [rbp+0A00h+Source]
0x180012325  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012329  mov     rax, rbx
0x18001232c  inc     rax
0x18001232f  cmp     [rcx+rax*2], r13w
0x180012334  jnz     short loc_18001232C
0x180012336  inc     eax
0x180012338  movsxd  r9, eax
0x18001233b  add     r9, r9; SourceSize
0x18001233e  lea     r8, [rbp+0A00h+Source]; Source
0x180012342  mov     edx, 414h; DestinationSize
0x180012347  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18001234e  call    cs:__imp_memcpy_s
0x180012354  test    eax, eax
0x180012356  jnz     loc_180012444
0x18001235c  lea     rax, [rbp+0A00h+var_460]
0x180012363  inc     rbx
0x180012366  cmp     [rax+rbx*2], r13w
0x18001236b  jnz     short loc_180012363
0x18001236d  movsxd  rax, ebx
0x180012370  mov     [rbp+rax*2+0A00h+var_460], di
0x180012378  lea     rcx, ds:2[rax*2]
0x180012380  cmp     rcx, 418h
0x180012387  jnb     loc_18001248D
0x18001238d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180012396  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001239b  call    cs:__imp_EnterCriticalSection
0x1800123a1  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800123a8  lea     rdx, aModule; "Module"
0x1800123af  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800123b4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800123b9  mov     ebx, eax
0x1800123bb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800123c0  call    cs:__imp_LeaveCriticalSection
0x1800123c6  neg     ebx
0x1800123c8  sbb     ebx, ebx
0x1800123ca  mov     edi, 8007000Eh
0x1800123cf  not     ebx
0x1800123d1  and     ebx, edi
0x1800123d3  test    ebx, ebx
0x1800123d5  js      short loc_180012449
0x1800123d7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800123dc  call    cs:__imp_EnterCriticalSection
0x1800123e2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x1800123e6  lea     rdx, aModuleRaw; "Module_Raw"
0x1800123ed  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800123f2  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800123f7  mov     ebx, eax
0x1800123f9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800123fe  call    cs:__imp_LeaveCriticalSection
0x180012404  mov     ecx, ebx
0x180012406  neg     ecx
0x180012408  sbb     eax, eax
0x18001240a  not     eax
0x18001240c  and     eax, edi
0x18001240e  test    ebx, ebx
0x180012410  jz      loc_180012290
0x180012416  mov     eax, r13d
0x180012419  test    r15d, r15d
0x18001241c  setnz   al
0x18001241f  movzx   r8d, r12w; unsigned __int16 *
0x180012423  mov     [rsp+0B00h+var_AE0], eax; int
0x180012427  lea     r9, aRegistry; "REGISTRY"
0x18001242e  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180012435  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18001243a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001243f  jmp     loc_180012290
0x180012444  mov     ebx, 80004005h
0x180012449  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18001244e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180012453  mov     eax, ebx
0x180012455  jmp     short loc_180012463
0x180012457  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18001245c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180012461  mov     eax, edi
0x180012463  mov     rcx, [rbp+0A00h+var_40]
0x18001246a  xor     rcx, rsp; StackCookie
0x18001246d  call    __security_check_cookie
0x180012472  mov     rbx, [rsp+0B00h+arg_10]
0x18001247a  add     rsp, 0AD0h
0x180012481  pop     r15
0x180012483  pop     r14
0x180012485  pop     r13
0x180012487  pop     r12
0x180012489  pop     rdi
0x18001248a  pop     rsi
0x18001248b  pop     rbp
0x18001248c  retn
0x18001248d  call    __report_rangecheckfailure
```
