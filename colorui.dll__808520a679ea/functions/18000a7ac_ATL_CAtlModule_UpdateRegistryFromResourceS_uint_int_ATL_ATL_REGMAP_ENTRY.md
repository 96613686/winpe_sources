# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000a7ac`
- end: `0x18000aac3`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ae10`

## callees

- `0x180001a58`
- `0x180003018`
- `0x180003ff0`
- `0x180004a54`
- `0x180006664`
- `0x180008c0c`
- `0x18000a7ac`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a97e`
- `msvcrt!memcpy_s` at `0x18000a97e`
- `KERNEL32!EnterCriticalSection` at `0x18000a84d`
- `KERNEL32!EnterCriticalSection` at `0x18000a936`
- `KERNEL32!EnterCriticalSection` at `0x18000a9cb`
- `KERNEL32!EnterCriticalSection` at `0x18000aa0c`
- `KERNEL32!EnterCriticalSection` at `0x18000a84d`
- `KERNEL32!EnterCriticalSection` at `0x18000a936`
- `KERNEL32!EnterCriticalSection` at `0x18000a9cb`
- `KERNEL32!EnterCriticalSection` at `0x18000aa0c`
- `KERNEL32!GetModuleFileNameW` at `0x18000a8b1`
- `KERNEL32!GetModuleFileNameW` at `0x18000a8b1`
- `KERNEL32!LeaveCriticalSection` at `0x18000a868`
- `KERNEL32!LeaveCriticalSection` at `0x18000a9f0`
- `KERNEL32!LeaveCriticalSection` at `0x18000aa2e`
- `KERNEL32!LeaveCriticalSection` at `0x18000a868`
- `KERNEL32!LeaveCriticalSection` at `0x18000a9f0`
- `KERNEL32!LeaveCriticalSection` at `0x18000aa2e`
- `KERNEL32!GetModuleHandleW` at `0x18000a926`
- `KERNEL32!GetModuleHandleW` at `0x18000a926`

## string_xrefs

- `0x18000aa50`: `REGISTRY`

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
0x18000a7ac  mov     [rsp-8+arg_10], rbx
0x18000a7b1  push    rbp
0x18000a7b2  push    rsi
0x18000a7b3  push    rdi
0x18000a7b4  push    r12
0x18000a7b6  push    r13
0x18000a7b8  push    r14
0x18000a7ba  push    r15
0x18000a7bc  lea     rbp, [rsp-9D0h]
0x18000a7c4  sub     rsp, 0AD0h
0x18000a7cb  mov     rax, cs:__security_cookie
0x18000a7d2  xor     rax, rsp
0x18000a7d5  mov     [rbp+0A00h+var_40], rax
0x18000a7dc  xor     r13d, r13d
0x18000a7df  mov     r12d, edx
0x18000a7e2  xorps   xmm0, xmm0
0x18000a7e5  mov     [rsp+0B00h+var_AC8], r13
0x18000a7ea  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000a7f1  mov     [rsp+0B00h+var_AC0], r13
0x18000a7f6  mov     [rsp+0B00h+var_AD0], rax
0x18000a7fb  mov     r14, rcx
0x18000a7fe  xor     eax, eax
0x18000a800  mov     [rsp+0B00h+var_AB8], r13d
0x18000a805  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000a80a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000a80f  mov     rbx, r9
0x18000a812  mov     [rsp+0B00h+var_A88], r13b
0x18000a817  mov     r15d, r8d
0x18000a81a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000a81f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000a824  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000a829  mov     edi, eax
0x18000a82b  test    eax, eax
0x18000a82d  js      loc_18000AA87
0x18000a833  mov     [rsp+0B00h+var_A88], 1
0x18000a838  test    rbx, rbx
0x18000a83b  jz      short loc_18000A87A
0x18000a83d  jmp     short loc_18000A872
0x18000a83f  mov     rsi, [rbx+8]
0x18000a843  test    rsi, rsi
0x18000a846  jz      short loc_18000A86E
0x18000a848  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a84d  call    cs:__imp_EnterCriticalSection
0x18000a853  mov     r8, rsi; unsigned __int16 *
0x18000a856  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000a85b  mov     rdx, rdi; unsigned __int16 *
0x18000a85e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a863  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a868  call    cs:__imp_LeaveCriticalSection
0x18000a86e  add     rbx, 10h
0x18000a872  mov     rdi, [rbx]
0x18000a875  test    rdi, rdi
0x18000a878  jnz     short loc_18000A83F
0x18000a87a  mov     rax, [r14]
0x18000a87d  lea     rdx, [rsp+0B00h+var_AD0]
0x18000a882  mov     rcx, r14
0x18000a885  mov     rax, [rax+28h]
0x18000a889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a88e  mov     ebx, eax
0x18000a890  test    eax, eax
0x18000a892  js      loc_18000AA79
0x18000a898  mov     rbx, cs:hInstance
0x18000a89f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000a8a6  mov     edi, 104h
0x18000a8ab  mov     rcx, rbx; hModule
0x18000a8ae  mov     r8d, edi; nSize
0x18000a8b1  call    cs:__imp_GetModuleFileNameW
0x18000a8b7  test    eax, eax
0x18000a8b9  jnz     short loc_18000A8C7
0x18000a8bb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a8c0  mov     ebx, eax
0x18000a8c2  jmp     loc_18000AA79
0x18000a8c7  cmp     eax, edi
0x18000a8c9  jnz     short loc_18000A8D5
0x18000a8cb  mov     ebx, 8007007Ah
0x18000a8d0  jmp     loc_18000AA79
0x18000a8d5  lea     rdx, [rbp+0A00h+Filename]
0x18000a8dc  mov     ecx, r13d
0x18000a8df  mov     r9d, 27h ; '''
0x18000a8e5  movzx   r8d, word ptr [rdx]
0x18000a8e9  test    r8w, r8w
0x18000a8ed  jz      short loc_18000A919
0x18000a8ef  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000a8f5  cmp     r8w, r9w
0x18000a8f9  jnz     short loc_18000A90B
0x18000a8fb  cmp     ecx, 206h
0x18000a901  jnb     short loc_18000A90B
0x18000a903  inc     ecx
0x18000a905  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000a90b  add     rdx, 2
0x18000a90f  inc     ecx
0x18000a911  cmp     ecx, 207h
0x18000a917  jb      short loc_18000A8E5
0x18000a919  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000a91f  test    rbx, rbx
0x18000a922  jz      short loc_18000A945
0x18000a924  xor     ecx, ecx; lpModuleName
0x18000a926  call    cs:__imp_GetModuleHandleW
0x18000a92c  cmp     rbx, rax
0x18000a92f  jz      short loc_18000A945
0x18000a931  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a936  call    cs:__imp_EnterCriticalSection
0x18000a93c  lea     r8, [rbp+0A00h+Source]
0x18000a940  jmp     loc_18000A9D8
0x18000a945  mov     edi, 22h ; '"'
0x18000a94a  lea     rcx, [rbp+0A00h+Source]
0x18000a94e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a952  mov     [rbp+0A00h+var_460], di
0x18000a959  mov     rax, rbx
0x18000a95c  inc     rax
0x18000a95f  cmp     [rcx+rax*2], r13w
0x18000a964  jnz     short loc_18000A95C
0x18000a966  inc     eax
0x18000a968  lea     r8, [rbp+0A00h+Source]; Source
0x18000a96c  movsxd  r9, eax
0x18000a96f  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000a976  add     r9, r9; SourceSize
0x18000a979  mov     edx, 414h; DestinationSize
0x18000a97e  call    cs:__imp_memcpy_s
0x18000a984  test    eax, eax
0x18000a986  jnz     loc_18000AA74
0x18000a98c  lea     rax, [rbp+0A00h+var_460]
0x18000a993  inc     rbx
0x18000a996  cmp     [rax+rbx*2], r13w
0x18000a99b  jnz     short loc_18000A993
0x18000a99d  movsxd  rax, ebx
0x18000a9a0  lea     rcx, ds:2[rax*2]
0x18000a9a8  mov     [rbp+rax*2+0A00h+var_460], di
0x18000a9b0  cmp     rcx, 418h
0x18000a9b7  jnb     loc_18000AABD
0x18000a9bd  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000a9c6  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a9cb  call    cs:__imp_EnterCriticalSection
0x18000a9d1  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000a9d8  lea     rdx, aModule; "Module"
0x18000a9df  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000a9e4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a9e9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a9ee  mov     ebx, eax
0x18000a9f0  call    cs:__imp_LeaveCriticalSection
0x18000a9f6  neg     ebx
0x18000a9f8  mov     edi, 8007000Eh
0x18000a9fd  sbb     ebx, ebx
0x18000a9ff  not     ebx
0x18000aa01  and     ebx, edi
0x18000aa03  test    ebx, ebx
0x18000aa05  js      short loc_18000AA79
0x18000aa07  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000aa0c  call    cs:__imp_EnterCriticalSection
0x18000aa12  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000aa16  lea     rdx, aModuleRaw; "Module_Raw"
0x18000aa1d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000aa22  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000aa27  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000aa2c  mov     ebx, eax
0x18000aa2e  call    cs:__imp_LeaveCriticalSection
0x18000aa34  mov     ecx, ebx
0x18000aa36  neg     ecx
0x18000aa38  sbb     eax, eax
0x18000aa3a  not     eax
0x18000aa3c  and     eax, edi
0x18000aa3e  test    ebx, ebx
0x18000aa40  jz      loc_18000A8C0
0x18000aa46  mov     eax, r13d
0x18000aa49  movzx   r8d, r12w; unsigned __int16 *
0x18000aa4d  test    r15d, r15d
0x18000aa50  lea     r9, aRegistry; "REGISTRY"
0x18000aa57  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000aa5e  setnz   al
0x18000aa61  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000aa66  mov     [rsp+0B00h+var_AE0], eax; int
0x18000aa6a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000aa6f  jmp     loc_18000A8C0
0x18000aa74  mov     ebx, 80004005h
0x18000aa79  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000aa7e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000aa83  mov     eax, ebx
0x18000aa85  jmp     short loc_18000AA93
0x18000aa87  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000aa8c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000aa91  mov     eax, edi
0x18000aa93  mov     rcx, [rbp+0A00h+var_40]
0x18000aa9a  xor     rcx, rsp; StackCookie
0x18000aa9d  call    __security_check_cookie
0x18000aaa2  mov     rbx, [rsp+0B00h+arg_10]
0x18000aaaa  add     rsp, 0AD0h
0x18000aab1  pop     r15
0x18000aab3  pop     r14
0x18000aab5  pop     r13
0x18000aab7  pop     r12
0x18000aab9  pop     rdi
0x18000aaba  pop     rsi
0x18000aabb  pop     rbp
0x18000aabc  retn
0x18000aabd  call    __report_rangecheckfailure
```
