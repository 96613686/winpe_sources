# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800043dc`
- end: `0x1800046f3`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800043c0`
- `0x180007b90`
- `0x1800093a0`
- `0x180009710`

## callees

- `0x180001898`
- `0x180002028`
- `0x180002178`
- `0x180002a88`
- `0x180002f5c`
- `0x180003878`
- `0x1800043dc`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800045ae`
- `msvcrt!memcpy_s` at `0x1800045ae`
- `KERNEL32!GetModuleHandleW` at `0x180004556`
- `KERNEL32!GetModuleHandleW` at `0x180004556`
- `KERNEL32!LeaveCriticalSection` at `0x180004498`
- `KERNEL32!LeaveCriticalSection` at `0x180004620`
- `KERNEL32!LeaveCriticalSection` at `0x18000465e`
- `KERNEL32!LeaveCriticalSection` at `0x180004498`
- `KERNEL32!LeaveCriticalSection` at `0x180004620`
- `KERNEL32!LeaveCriticalSection` at `0x18000465e`
- `KERNEL32!GetModuleFileNameW` at `0x1800044e1`
- `KERNEL32!GetModuleFileNameW` at `0x1800044e1`
- `KERNEL32!EnterCriticalSection` at `0x18000447d`
- `KERNEL32!EnterCriticalSection` at `0x180004566`
- `KERNEL32!EnterCriticalSection` at `0x1800045fb`
- `KERNEL32!EnterCriticalSection` at `0x18000463c`
- `KERNEL32!EnterCriticalSection` at `0x18000447d`
- `KERNEL32!EnterCriticalSection` at `0x180004566`
- `KERNEL32!EnterCriticalSection` at `0x1800045fb`
- `KERNEL32!EnterCriticalSection` at `0x18000463c`

## string_xrefs

- `0x180004680`: `REGISTRY`

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
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
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
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x1800043dc  mov     [rsp-8+arg_10], rbx
0x1800043e1  push    rbp
0x1800043e2  push    rsi
0x1800043e3  push    rdi
0x1800043e4  push    r12
0x1800043e6  push    r13
0x1800043e8  push    r14
0x1800043ea  push    r15
0x1800043ec  lea     rbp, [rsp-9D0h]
0x1800043f4  sub     rsp, 0AD0h
0x1800043fb  mov     rax, cs:__security_cookie
0x180004402  xor     rax, rsp
0x180004405  mov     [rbp+0A00h+var_40], rax
0x18000440c  xor     r13d, r13d
0x18000440f  mov     r12d, edx
0x180004412  xorps   xmm0, xmm0
0x180004415  mov     [rsp+0B00h+var_AC8], r13
0x18000441a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004421  mov     [rsp+0B00h+var_AC0], r13
0x180004426  mov     [rsp+0B00h+var_AD0], rax
0x18000442b  mov     r14, rcx
0x18000442e  xor     eax, eax
0x180004430  mov     [rsp+0B00h+var_AB8], r13d
0x180004435  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000443a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000443f  mov     rbx, r9
0x180004442  mov     [rsp+0B00h+var_A88], r13b
0x180004447  mov     r15d, r8d
0x18000444a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000444f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180004454  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004459  mov     edi, eax
0x18000445b  test    eax, eax
0x18000445d  js      loc_1800046B7
0x180004463  mov     [rsp+0B00h+var_A88], 1
0x180004468  test    rbx, rbx
0x18000446b  jz      short loc_1800044AA
0x18000446d  jmp     short loc_1800044A2
0x18000446f  mov     rsi, [rbx+8]
0x180004473  test    rsi, rsi
0x180004476  jz      short loc_18000449E
0x180004478  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000447d  call    cs:__imp_EnterCriticalSection
0x180004483  mov     r8, rsi; unsigned __int16 *
0x180004486  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000448b  mov     rdx, rdi; unsigned __int16 *
0x18000448e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004493  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004498  call    cs:__imp_LeaveCriticalSection
0x18000449e  add     rbx, 10h
0x1800044a2  mov     rdi, [rbx]
0x1800044a5  test    rdi, rdi
0x1800044a8  jnz     short loc_18000446F
0x1800044aa  mov     rax, [r14]
0x1800044ad  lea     rdx, [rsp+0B00h+var_AD0]
0x1800044b2  mov     rcx, r14
0x1800044b5  mov     rax, [rax+28h]
0x1800044b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044be  mov     ebx, eax
0x1800044c0  test    eax, eax
0x1800044c2  js      loc_1800046A9
0x1800044c8  mov     rbx, cs:hInstance
0x1800044cf  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800044d6  mov     edi, 104h
0x1800044db  mov     rcx, rbx; hModule
0x1800044de  mov     r8d, edi; nSize
0x1800044e1  call    cs:__imp_GetModuleFileNameW
0x1800044e7  test    eax, eax
0x1800044e9  jnz     short loc_1800044F7
0x1800044eb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800044f0  mov     ebx, eax
0x1800044f2  jmp     loc_1800046A9
0x1800044f7  cmp     eax, edi
0x1800044f9  jnz     short loc_180004505
0x1800044fb  mov     ebx, 8007007Ah
0x180004500  jmp     loc_1800046A9
0x180004505  lea     rdx, [rbp+0A00h+Filename]
0x18000450c  mov     ecx, r13d
0x18000450f  mov     r9d, 27h ; '''
0x180004515  movzx   r8d, word ptr [rdx]
0x180004519  test    r8w, r8w
0x18000451d  jz      short loc_180004549
0x18000451f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180004525  cmp     r8w, r9w
0x180004529  jnz     short loc_18000453B
0x18000452b  cmp     ecx, 206h
0x180004531  jnb     short loc_18000453B
0x180004533  inc     ecx
0x180004535  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000453b  add     rdx, 2
0x18000453f  inc     ecx
0x180004541  cmp     ecx, 207h
0x180004547  jb      short loc_180004515
0x180004549  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000454f  test    rbx, rbx
0x180004552  jz      short loc_180004575
0x180004554  xor     ecx, ecx; lpModuleName
0x180004556  call    cs:__imp_GetModuleHandleW
0x18000455c  cmp     rbx, rax
0x18000455f  jz      short loc_180004575
0x180004561  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004566  call    cs:__imp_EnterCriticalSection
0x18000456c  lea     r8, [rbp+0A00h+Source]
0x180004570  jmp     loc_180004608
0x180004575  mov     edi, 22h ; '"'
0x18000457a  lea     rcx, [rbp+0A00h+Source]
0x18000457e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004582  mov     [rbp+0A00h+var_460], di
0x180004589  mov     rax, rbx
0x18000458c  inc     rax
0x18000458f  cmp     [rcx+rax*2], r13w
0x180004594  jnz     short loc_18000458C
0x180004596  inc     eax
0x180004598  lea     r8, [rbp+0A00h+Source]; Source
0x18000459c  movsxd  r9, eax
0x18000459f  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800045a6  add     r9, r9; SourceSize
0x1800045a9  mov     edx, 414h; DestinationSize
0x1800045ae  call    cs:__imp_memcpy_s
0x1800045b4  test    eax, eax
0x1800045b6  jnz     loc_1800046A4
0x1800045bc  lea     rax, [rbp+0A00h+var_460]
0x1800045c3  inc     rbx
0x1800045c6  cmp     [rax+rbx*2], r13w
0x1800045cb  jnz     short loc_1800045C3
0x1800045cd  movsxd  rax, ebx
0x1800045d0  lea     rcx, ds:2[rax*2]
0x1800045d8  mov     [rbp+rax*2+0A00h+var_460], di
0x1800045e0  cmp     rcx, 418h
0x1800045e7  jnb     loc_1800046ED
0x1800045ed  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800045f6  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800045fb  call    cs:__imp_EnterCriticalSection
0x180004601  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180004608  lea     rdx, aModule; "Module"
0x18000460f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004614  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004619  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000461e  mov     ebx, eax
0x180004620  call    cs:__imp_LeaveCriticalSection
0x180004626  neg     ebx
0x180004628  mov     edi, 8007000Eh
0x18000462d  sbb     ebx, ebx
0x18000462f  not     ebx
0x180004631  and     ebx, edi
0x180004633  test    ebx, ebx
0x180004635  js      short loc_1800046A9
0x180004637  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000463c  call    cs:__imp_EnterCriticalSection
0x180004642  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180004646  lea     rdx, aModuleRaw; "Module_Raw"
0x18000464d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004652  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004657  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000465c  mov     ebx, eax
0x18000465e  call    cs:__imp_LeaveCriticalSection
0x180004664  mov     ecx, ebx
0x180004666  neg     ecx
0x180004668  sbb     eax, eax
0x18000466a  not     eax
0x18000466c  and     eax, edi
0x18000466e  test    ebx, ebx
0x180004670  jz      loc_1800044F0
0x180004676  mov     eax, r13d
0x180004679  movzx   r8d, r12w; unsigned __int16 *
0x18000467d  test    r15d, r15d
0x180004680  lea     r9, aRegistry; "REGISTRY"
0x180004687  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000468e  setnz   al
0x180004691  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004696  mov     [rsp+0B00h+var_AE0], eax; int
0x18000469a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000469f  jmp     loc_1800044F0
0x1800046a4  mov     ebx, 80004005h
0x1800046a9  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800046ae  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800046b3  mov     eax, ebx
0x1800046b5  jmp     short loc_1800046C3
0x1800046b7  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800046bc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800046c1  mov     eax, edi
0x1800046c3  mov     rcx, [rbp+0A00h+var_40]
0x1800046ca  xor     rcx, rsp; StackCookie
0x1800046cd  call    __security_check_cookie
0x1800046d2  mov     rbx, [rsp+0B00h+arg_10]
0x1800046da  add     rsp, 0AD0h
0x1800046e1  pop     r15
0x1800046e3  pop     r14
0x1800046e5  pop     r13
0x1800046e7  pop     r12
0x1800046e9  pop     rdi
0x1800046ea  pop     rsi
0x1800046eb  pop     rbp
0x1800046ec  retn
0x1800046ed  call    __report_rangecheckfailure
```
