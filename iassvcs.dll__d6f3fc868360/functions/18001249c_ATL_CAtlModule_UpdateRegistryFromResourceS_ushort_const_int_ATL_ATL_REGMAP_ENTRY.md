# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001249c`
- end: `0x1800127da`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800127f0`

## callees

- `0x180001bb8`
- `0x18000d860`
- `0x18000dc5c`
- `0x18000e8d4`
- `0x18001033c`
- `0x1800110a8`
- `0x18001249c`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001267a`
- `msvcrt!memcpy_s` at `0x18001267a`
- `KERNEL32!EnterCriticalSection` at `0x18001253d`
- `KERNEL32!EnterCriticalSection` at `0x180012629`
- `KERNEL32!EnterCriticalSection` at `0x1800126c7`
- `KERNEL32!EnterCriticalSection` at `0x18001270c`
- `KERNEL32!EnterCriticalSection` at `0x18001253d`
- `KERNEL32!EnterCriticalSection` at `0x180012629`
- `KERNEL32!EnterCriticalSection` at `0x1800126c7`
- `KERNEL32!EnterCriticalSection` at `0x18001270c`
- `KERNEL32!GetModuleFileNameW` at `0x18001259e`
- `KERNEL32!GetModuleFileNameW` at `0x18001259e`
- `KERNEL32!LeaveCriticalSection` at `0x180012558`
- `KERNEL32!LeaveCriticalSection` at `0x1800126ec`
- `KERNEL32!LeaveCriticalSection` at `0x180012731`
- `KERNEL32!LeaveCriticalSection` at `0x180012558`
- `KERNEL32!LeaveCriticalSection` at `0x1800126ec`
- `KERNEL32!LeaveCriticalSection` at `0x180012731`
- `KERNEL32!GetModuleHandleW` at `0x180012619`
- `KERNEL32!GetModuleHandleW` at `0x180012619`

## string_xrefs

- `0x180012767`: `REGISTRY`

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
      goto LABEL_39;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
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
        v32 = 34;
        v19 = -1;
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
            Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, a2, L"REGISTRY", 1);
            goto LABEL_11;
          }
        }
        else if ( a2 )
        {
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, a2, L"REGISTRY", 0);
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
0x18001249c  mov     [rsp-8+arg_10], rbx
0x1800124a1  push    rbp
0x1800124a2  push    rsi
0x1800124a3  push    rdi
0x1800124a4  push    r12
0x1800124a6  push    r13
0x1800124a8  push    r14
0x1800124aa  push    r15
0x1800124ac  lea     rbp, [rsp-9D0h]
0x1800124b4  sub     rsp, 0AD0h
0x1800124bb  mov     rax, cs:__security_cookie
0x1800124c2  xor     rax, rsp
0x1800124c5  mov     [rbp+0A00h+var_40], rax
0x1800124cc  mov     rbx, r9
0x1800124cf  mov     r12d, r8d
0x1800124d2  mov     r14, rdx
0x1800124d5  mov     r15, rcx
0x1800124d8  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800124df  mov     [rsp+0B00h+var_AD0], rax
0x1800124e4  xor     r13d, r13d
0x1800124e7  mov     [rsp+0B00h+var_AC8], r13
0x1800124ec  mov     [rsp+0B00h+var_AC0], r13
0x1800124f1  mov     [rsp+0B00h+var_AB8], r13d
0x1800124f6  xorps   xmm0, xmm0
0x1800124f9  xor     eax, eax
0x1800124fb  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180012500  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180012505  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18001250a  mov     [rsp+0B00h+var_A88], r13b
0x18001250f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180012514  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180012519  mov     edi, eax
0x18001251b  test    eax, eax
0x18001251d  js      loc_18001279E
0x180012523  mov     [rsp+0B00h+var_A88], 1
0x180012528  test    rbx, rbx
0x18001252b  jz      short loc_18001256A
0x18001252d  jmp     short loc_180012562
0x18001252f  mov     rsi, [rbx+8]
0x180012533  test    rsi, rsi
0x180012536  jz      short loc_18001255E
0x180012538  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001253d  call    cs:__imp_EnterCriticalSection
0x180012543  mov     r8, rsi; unsigned __int16 *
0x180012546  mov     rdx, rdi; unsigned __int16 *
0x180012549  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18001254e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180012553  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180012558  call    cs:__imp_LeaveCriticalSection
0x18001255e  add     rbx, 10h
0x180012562  mov     rdi, [rbx]
0x180012565  test    rdi, rdi
0x180012568  jnz     short loc_18001252F
0x18001256a  mov     rax, [r15]
0x18001256d  lea     rdx, [rsp+0B00h+var_AD0]
0x180012572  mov     rcx, r15
0x180012575  mov     rax, [rax+28h]
0x180012579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001257e  mov     ebx, eax
0x180012580  test    eax, eax
0x180012582  js      loc_180012790
0x180012588  mov     rbx, cs:hModule
0x18001258f  mov     edi, 104h
0x180012594  mov     r8d, edi; nSize
0x180012597  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18001259b  mov     rcx, rbx; hModule
0x18001259e  call    cs:__imp_GetModuleFileNameW
0x1800125a4  test    eax, eax
0x1800125a6  jnz     short loc_1800125B4
0x1800125a8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800125ad  mov     ebx, eax
0x1800125af  jmp     loc_180012790
0x1800125b4  cmp     eax, edi
0x1800125b6  jnz     short loc_1800125C2
0x1800125b8  mov     ebx, 8007007Ah
0x1800125bd  jmp     loc_180012790
0x1800125c2  lea     rdx, [rbp+0A00h+Filename]
0x1800125c6  mov     ecx, r13d
0x1800125c9  mov     r9d, 27h ; '''
0x1800125cf  movzx   r8d, word ptr [rdx]
0x1800125d3  test    r8w, r8w
0x1800125d7  jz      short loc_180012609
0x1800125d9  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800125e2  cmp     r8w, r9w
0x1800125e6  jnz     short loc_1800125FB
0x1800125e8  cmp     ecx, 206h
0x1800125ee  jnb     short loc_1800125FB
0x1800125f0  inc     ecx
0x1800125f2  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800125fb  add     rdx, 2
0x1800125ff  inc     ecx
0x180012601  cmp     ecx, 207h
0x180012607  jb      short loc_1800125CF
0x180012609  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180012612  test    rbx, rbx
0x180012615  jz      short loc_18001263B
0x180012617  xor     ecx, ecx; lpModuleName
0x180012619  call    cs:__imp_GetModuleHandleW
0x18001261f  cmp     rbx, rax
0x180012622  jz      short loc_18001263B
0x180012624  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180012629  call    cs:__imp_EnterCriticalSection
0x18001262f  lea     r8, [rbp+0A00h+Source]
0x180012636  jmp     loc_1800126D4
0x18001263b  mov     edi, 22h ; '"'
0x180012640  mov     [rbp+0A00h+var_460], di
0x180012647  lea     rcx, [rbp+0A00h+Source]
0x18001264e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012652  mov     rax, rbx
0x180012655  inc     rax
0x180012658  cmp     [rcx+rax*2], r13w
0x18001265d  jnz     short loc_180012655
0x18001265f  inc     eax
0x180012661  movsxd  r9, eax
0x180012664  add     r9, r9; SourceSize
0x180012667  lea     r8, [rbp+0A00h+Source]; Source
0x18001266e  mov     edx, 414h; DestinationSize
0x180012673  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18001267a  call    cs:__imp_memcpy_s
0x180012680  test    eax, eax
0x180012682  jnz     loc_18001278B
0x180012688  lea     rax, [rbp+0A00h+var_460]
0x18001268f  inc     rbx
0x180012692  cmp     [rax+rbx*2], r13w
0x180012697  jnz     short loc_18001268F
0x180012699  movsxd  rax, ebx
0x18001269c  mov     [rbp+rax*2+0A00h+var_460], di
0x1800126a4  lea     rcx, ds:2[rax*2]
0x1800126ac  cmp     rcx, 418h
0x1800126b3  jnb     loc_1800127D4
0x1800126b9  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800126c2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800126c7  call    cs:__imp_EnterCriticalSection
0x1800126cd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800126d4  lea     rdx, aModule; "Module"
0x1800126db  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800126e0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800126e5  mov     ebx, eax
0x1800126e7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800126ec  call    cs:__imp_LeaveCriticalSection
0x1800126f2  neg     ebx
0x1800126f4  sbb     ebx, ebx
0x1800126f6  mov     edi, 8007000Eh
0x1800126fb  not     ebx
0x1800126fd  and     ebx, edi
0x1800126ff  test    ebx, ebx
0x180012701  js      loc_180012790
0x180012707  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001270c  call    cs:__imp_EnterCriticalSection
0x180012712  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180012719  lea     rdx, aModuleRaw; "Module_Raw"
0x180012720  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180012725  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18001272a  mov     ebx, eax
0x18001272c  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180012731  call    cs:__imp_LeaveCriticalSection
0x180012737  mov     ecx, ebx
0x180012739  neg     ecx
0x18001273b  sbb     eax, eax
0x18001273d  not     eax
0x18001273f  and     eax, edi
0x180012741  test    ebx, ebx
0x180012743  jz      loc_1800125AD
0x180012749  test    r12d, r12d
0x18001274c  jz      short loc_18001275D
0x18001274e  test    r14, r14
0x180012751  jz      short loc_180012784
0x180012753  mov     [rsp+0B00h+var_AE0], 1
0x18001275b  jmp     short loc_180012767
0x18001275d  test    r14, r14
0x180012760  jz      short loc_180012784
0x180012762  mov     [rsp+0B00h+var_AE0], r13d; int
0x180012767  lea     r9, aRegistry; "REGISTRY"
0x18001276e  mov     r8, r14; unsigned __int16 *
0x180012771  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180012775  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18001277a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001277f  jmp     loc_1800125AD
0x180012784  mov     ebx, 80070057h
0x180012789  jmp     short loc_180012790
0x18001278b  mov     ebx, 80004005h
0x180012790  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180012795  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001279a  mov     eax, ebx
0x18001279c  jmp     short loc_1800127AA
0x18001279e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800127a3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800127a8  mov     eax, edi
0x1800127aa  mov     rcx, [rbp+0A00h+var_40]
0x1800127b1  xor     rcx, rsp; StackCookie
0x1800127b4  call    __security_check_cookie
0x1800127b9  mov     rbx, [rsp+0B00h+arg_10]
0x1800127c1  add     rsp, 0AD0h
0x1800127c8  pop     r15
0x1800127ca  pop     r14
0x1800127cc  pop     r13
0x1800127ce  pop     r12
0x1800127d0  pop     rdi
0x1800127d1  pop     rsi
0x1800127d2  pop     rbp
0x1800127d3  retn
0x1800127d4  call    __report_rangecheckfailure
```
