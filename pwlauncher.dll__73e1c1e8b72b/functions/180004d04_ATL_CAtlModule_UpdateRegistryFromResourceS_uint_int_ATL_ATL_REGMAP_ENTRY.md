# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180004d04`
- end: `0x18000501f`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `795`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800052b0`
- `0x1800053e0`
- `0x18000c430`

## callees

- `0x180001e58`
- `0x1800026bc`
- `0x180002818`
- `0x180003248`
- `0x180003adc`
- `0x1800042a8`
- `0x180004d04`
- `0x18000fe10`
- `0x180011010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004eda`
- `msvcrt!memcpy_s` at `0x180004eda`
- `KERNEL32!EnterCriticalSection` at `0x180004da9`
- `KERNEL32!EnterCriticalSection` at `0x180004e92`
- `KERNEL32!EnterCriticalSection` at `0x180004f27`
- `KERNEL32!EnterCriticalSection` at `0x180004f68`
- `KERNEL32!EnterCriticalSection` at `0x180004da9`
- `KERNEL32!EnterCriticalSection` at `0x180004e92`
- `KERNEL32!EnterCriticalSection` at `0x180004f27`
- `KERNEL32!EnterCriticalSection` at `0x180004f68`
- `KERNEL32!GetModuleFileNameW` at `0x180004e0d`
- `KERNEL32!GetModuleFileNameW` at `0x180004e0d`
- `KERNEL32!LeaveCriticalSection` at `0x180004dc4`
- `KERNEL32!LeaveCriticalSection` at `0x180004f4c`
- `KERNEL32!LeaveCriticalSection` at `0x180004f8a`
- `KERNEL32!LeaveCriticalSection` at `0x180004dc4`
- `KERNEL32!LeaveCriticalSection` at `0x180004f4c`
- `KERNEL32!LeaveCriticalSection` at `0x180004f8a`
- `KERNEL32!GetModuleHandleW` at `0x180004e82`
- `KERNEL32!GetModuleHandleW` at `0x180004e82`

## string_xrefs

- `0x180004fb3`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v7; // r14
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

  v7 = ATL::_pAtlModule;
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
    v11 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v7 + 40LL))(v7, &v25);
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
0x180004d04  mov     [rsp-8+arg_0], rbx
0x180004d09  push    rbp
0x180004d0a  push    rsi
0x180004d0b  push    rdi
0x180004d0c  push    r12
0x180004d0e  push    r13
0x180004d10  push    r14
0x180004d12  push    r15
0x180004d14  lea     rbp, [rsp-9D0h]
0x180004d1c  sub     rsp, 0AD0h
0x180004d23  mov     rax, cs:__security_cookie
0x180004d2a  xor     rax, rsp
0x180004d2d  mov     [rbp+0A00h+var_40], rax
0x180004d34  mov     rbx, r9
0x180004d37  mov     r15d, r8d
0x180004d3a  mov     r12d, edx
0x180004d3d  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004d44  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004d4b  mov     [rsp+0B00h+var_AD0], rax
0x180004d50  xor     r13d, r13d
0x180004d53  mov     [rsp+0B00h+var_AC8], r13
0x180004d58  mov     [rsp+0B00h+var_AC0], r13
0x180004d5d  mov     [rsp+0B00h+var_AB8], r13d
0x180004d62  xorps   xmm0, xmm0
0x180004d65  xor     eax, eax
0x180004d67  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180004d6c  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180004d71  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180004d76  mov     [rsp+0B00h+var_A88], r13b
0x180004d7b  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180004d80  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004d85  mov     edi, eax
0x180004d87  test    eax, eax
0x180004d89  js      loc_180004FE3
0x180004d8f  mov     [rsp+0B00h+var_A88], 1
0x180004d94  test    rbx, rbx
0x180004d97  jz      short loc_180004DD6
0x180004d99  jmp     short loc_180004DCE
0x180004d9b  mov     rsi, [rbx+8]
0x180004d9f  test    rsi, rsi
0x180004da2  jz      short loc_180004DCA
0x180004da4  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004da9  call    cs:__imp_EnterCriticalSection
0x180004daf  mov     r8, rsi; unsigned __int16 *
0x180004db2  mov     rdx, rdi; unsigned __int16 *
0x180004db5  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004dba  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004dbf  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004dc4  call    cs:__imp_LeaveCriticalSection
0x180004dca  add     rbx, 10h
0x180004dce  mov     rdi, [rbx]
0x180004dd1  test    rdi, rdi
0x180004dd4  jnz     short loc_180004D9B
0x180004dd6  mov     rax, [r14]
0x180004dd9  lea     rdx, [rsp+0B00h+var_AD0]
0x180004dde  mov     rcx, r14
0x180004de1  mov     rax, [rax+28h]
0x180004de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dea  mov     ebx, eax
0x180004dec  test    eax, eax
0x180004dee  js      loc_180004FD5
0x180004df4  mov     rbx, cs:hInstance
0x180004dfb  mov     edi, 104h
0x180004e00  mov     r8d, edi; nSize
0x180004e03  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180004e0a  mov     rcx, rbx; hModule
0x180004e0d  call    cs:__imp_GetModuleFileNameW
0x180004e13  test    eax, eax
0x180004e15  jnz     short loc_180004E23
0x180004e17  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004e1c  mov     ebx, eax
0x180004e1e  jmp     loc_180004FD5
0x180004e23  cmp     eax, edi
0x180004e25  jnz     short loc_180004E31
0x180004e27  mov     ebx, 8007007Ah
0x180004e2c  jmp     loc_180004FD5
0x180004e31  lea     rdx, [rbp+0A00h+Filename]
0x180004e38  mov     ecx, r13d
0x180004e3b  mov     r9d, 27h ; '''
0x180004e41  movzx   r8d, word ptr [rdx]
0x180004e45  test    r8w, r8w
0x180004e49  jz      short loc_180004E75
0x180004e4b  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180004e51  cmp     r8w, r9w
0x180004e55  jnz     short loc_180004E67
0x180004e57  cmp     ecx, 206h
0x180004e5d  jnb     short loc_180004E67
0x180004e5f  inc     ecx
0x180004e61  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180004e67  add     rdx, 2
0x180004e6b  inc     ecx
0x180004e6d  cmp     ecx, 207h
0x180004e73  jb      short loc_180004E41
0x180004e75  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180004e7b  test    rbx, rbx
0x180004e7e  jz      short loc_180004EA1
0x180004e80  xor     ecx, ecx; lpModuleName
0x180004e82  call    cs:__imp_GetModuleHandleW
0x180004e88  cmp     rbx, rax
0x180004e8b  jz      short loc_180004EA1
0x180004e8d  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004e92  call    cs:__imp_EnterCriticalSection
0x180004e98  lea     r8, [rbp+0A00h+Source]
0x180004e9c  jmp     loc_180004F34
0x180004ea1  mov     edi, 22h ; '"'
0x180004ea6  mov     [rbp+0A00h+var_460], di
0x180004ead  lea     rcx, [rbp+0A00h+Source]
0x180004eb1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004eb5  mov     rax, rbx
0x180004eb8  inc     rax
0x180004ebb  cmp     [rcx+rax*2], r13w
0x180004ec0  jnz     short loc_180004EB8
0x180004ec2  inc     eax
0x180004ec4  movsxd  r9, eax
0x180004ec7  add     r9, r9; SourceSize
0x180004eca  lea     r8, [rbp+0A00h+Source]; Source
0x180004ece  mov     edx, 414h; DestinationSize
0x180004ed3  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180004eda  call    cs:__imp_memcpy_s
0x180004ee0  test    eax, eax
0x180004ee2  jnz     loc_180004FD0
0x180004ee8  lea     rax, [rbp+0A00h+var_460]
0x180004eef  inc     rbx
0x180004ef2  cmp     [rax+rbx*2], r13w
0x180004ef7  jnz     short loc_180004EEF
0x180004ef9  movsxd  rax, ebx
0x180004efc  mov     [rbp+rax*2+0A00h+var_460], di
0x180004f04  lea     rcx, ds:2[rax*2]
0x180004f0c  cmp     rcx, 418h
0x180004f13  jnb     loc_180005019
0x180004f19  mov     [rbp+rcx+0A00h+var_460], r13w
0x180004f22  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004f27  call    cs:__imp_EnterCriticalSection
0x180004f2d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180004f34  lea     rdx, aModule; "Module"
0x180004f3b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004f40  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004f45  mov     ebx, eax
0x180004f47  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004f4c  call    cs:__imp_LeaveCriticalSection
0x180004f52  neg     ebx
0x180004f54  sbb     ebx, ebx
0x180004f56  mov     edi, 8007000Eh
0x180004f5b  not     ebx
0x180004f5d  and     ebx, edi
0x180004f5f  test    ebx, ebx
0x180004f61  js      short loc_180004FD5
0x180004f63  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004f68  call    cs:__imp_EnterCriticalSection
0x180004f6e  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180004f72  lea     rdx, aModuleRaw; "Module_Raw"
0x180004f79  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004f7e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004f83  mov     ebx, eax
0x180004f85  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004f8a  call    cs:__imp_LeaveCriticalSection
0x180004f90  mov     ecx, ebx
0x180004f92  neg     ecx
0x180004f94  sbb     eax, eax
0x180004f96  not     eax
0x180004f98  and     eax, edi
0x180004f9a  test    ebx, ebx
0x180004f9c  jz      loc_180004E1C
0x180004fa2  mov     eax, r13d
0x180004fa5  test    r15d, r15d
0x180004fa8  setnz   al
0x180004fab  movzx   r8d, r12w; unsigned __int16 *
0x180004faf  mov     [rsp+0B00h+var_AE0], eax; int
0x180004fb3  lea     r9, aRegistry; "REGISTRY"
0x180004fba  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180004fc1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004fc6  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180004fcb  jmp     loc_180004E1C
0x180004fd0  mov     ebx, 80004005h
0x180004fd5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004fda  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004fdf  mov     eax, ebx
0x180004fe1  jmp     short loc_180004FEF
0x180004fe3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004fe8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004fed  mov     eax, edi
0x180004fef  mov     rcx, [rbp+0A00h+var_40]
0x180004ff6  xor     rcx, rsp; StackCookie
0x180004ff9  call    __security_check_cookie
0x180004ffe  mov     rbx, [rsp+0B00h+arg_0]
0x180005006  add     rsp, 0AD0h
0x18000500d  pop     r15
0x18000500f  pop     r14
0x180005011  pop     r13
0x180005013  pop     r12
0x180005015  pop     rdi
0x180005016  pop     rsi
0x180005017  pop     rbp
0x180005018  retn
0x180005019  call    __report_rangecheckfailure
```
