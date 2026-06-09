# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009c78`
- end: `0x180009faa`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `818`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009c60`
- `0x180012d20`
- `0x180012e40`

## callees

- `0x180001e08`
- `0x1800058b8`
- `0x180005da0`
- `0x1800060e0`
- `0x1800068ac`
- `0x1800079f0`
- `0x180008f00`
- `0x180009c78`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009e43`
- `msvcrt!memcpy_s` at `0x180009e43`
- `KERNEL32!GetModuleHandleW` at `0x180009dd6`
- `KERNEL32!GetModuleHandleW` at `0x180009dd6`
- `KERNEL32!EnterCriticalSection` at `0x180009dec`
- `KERNEL32!EnterCriticalSection` at `0x180009e96`
- `KERNEL32!EnterCriticalSection` at `0x180009ee7`
- `KERNEL32!EnterCriticalSection` at `0x180009dec`
- `KERNEL32!EnterCriticalSection` at `0x180009e96`
- `KERNEL32!EnterCriticalSection` at `0x180009ee7`
- `KERNEL32!LeaveCriticalSection` at `0x180009ec1`
- `KERNEL32!LeaveCriticalSection` at `0x180009f12`
- `KERNEL32!LeaveCriticalSection` at `0x180009ec1`
- `KERNEL32!LeaveCriticalSection` at `0x180009f12`
- `KERNEL32!GetModuleFileNameW` at `0x180009d55`
- `KERNEL32!GetModuleFileNameW` at `0x180009d55`

## string_xrefs

- `0x180009f30`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v7; // edi
  signed int v8; // ebx
  HMODULE v9; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // r8
  unsigned __int16 *v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // ebx
  int v20; // ebx
  const unsigned __int16 *v21; // r8
  void **v23; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v27; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v30; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v23 = &ATL::CRegObject::`vftable';
  v24[0] = 0;
  v24[1] = 0;
  v25 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v27 = 0;
  v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v7 >= 0 )
  {
    v27 = 1;
    if ( a4 )
    {
      while ( *(_QWORD *)a4 )
      {
        ATL::CRegObject::AddReplacement(
          (ATL::CRegObject *)&v23,
          *(const unsigned __int16 **)a4,
          *((const unsigned __int16 **)a4 + 1));
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v8 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v23);
    if ( v8 < 0 )
      goto LABEL_34;
    v9 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v8 = -2147024774;
        goto LABEL_34;
      }
      v12 = Filename;
      v13 = 0;
      do
      {
        v14 = *v12;
        if ( !*v12 )
          break;
        Source[v13] = v14;
        if ( v14 == 39 && (unsigned int)v13 < 0x206 )
        {
          LODWORD(v13) = v13 + 1;
          Source[(unsigned int)v13] = 39;
        }
        ++v12;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < 0x207 );
      Source[v13] = 0;
      if ( !v9 || v9 == GetModuleHandleW(0) )
      {
        v30 = 34;
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( Source[v17] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v17 + 1)) )
        {
          v8 = -2147467259;
          goto LABEL_34;
        }
        do
          ++v16;
        while ( *(_WORD *)&Destination[2 * v16 - 2] );
        *(_WORD *)&Destination[2 * (int)v16 - 2] = 34;
        v18 = 2LL * (int)v16 + 2;
        if ( v18 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v18 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v15 = &v30;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v15 = Source;
      }
      v19 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v24, L"Module", v15);
      LeaveCriticalSection(&CriticalSection);
      v8 = v19 == 0 ? 0x8007000E : 0;
      if ( v8 < 0 )
      {
LABEL_34:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
        return (unsigned int)v8;
      }
      EnterCriticalSection(&CriticalSection);
      v20 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v24, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v20 == 0 ? 0x8007000E : 0;
      if ( v20 )
      {
        if ( a3 )
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v23, Filename, v21, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v23, Filename, v21, L"REGISTRY", 0);
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v8 = Error;
    goto LABEL_34;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009c78  mov     [rsp-8+arg_8], rbx
0x180009c7d  push    rbp
0x180009c7e  push    rsi
0x180009c7f  push    rdi
0x180009c80  push    r14
0x180009c82  push    r15
0x180009c84  lea     rbp, [rsp-9D0h]
0x180009c8c  sub     rsp, 0AD0h
0x180009c93  mov     rax, cs:__security_cookie
0x180009c9a  xor     rax, rsp
0x180009c9d  mov     [rbp+9F0h+var_30], rax
0x180009ca4  mov     rbx, r9
0x180009ca7  mov     r14d, r8d
0x180009caa  mov     rsi, rcx
0x180009cad  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009cb4  mov     [rsp+0AF0h+var_AC0], rax
0x180009cb9  xor     r15d, r15d
0x180009cbc  mov     [rsp+0AF0h+var_AB8], r15
0x180009cc1  mov     [rsp+0AF0h+var_AB0], r15
0x180009cc6  mov     [rsp+0AF0h+var_AA8], r15d
0x180009ccb  xorps   xmm0, xmm0
0x180009cce  xor     eax, eax
0x180009cd0  movups  xmmword ptr [rsp+0AF0h+CriticalSection.DebugInfo], xmm0
0x180009cd5  movups  xmmword ptr [rsp+0AF0h+CriticalSection.OwningThread], xmm0
0x180009cda  mov     [rsp+0AF0h+CriticalSection.SpinCount], rax
0x180009cdf  mov     [rsp+0AF0h+var_A78], r15b
0x180009ce4  lea     rcx, [rsp+0AF0h+CriticalSection]; this
0x180009ce9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009cee  mov     edi, eax
0x180009cf0  test    eax, eax
0x180009cf2  js      loc_180009F71
0x180009cf8  mov     [rsp+0AF0h+var_A78], 1
0x180009cfd  test    rbx, rbx
0x180009d00  jz      short loc_180009D21
0x180009d02  jmp     short loc_180009D19
0x180009d04  mov     r8, [rbx+8]; unsigned __int16 *
0x180009d08  mov     rdx, rax; unsigned __int16 *
0x180009d0b  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180009d10  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180009d15  lea     rbx, [rbx+10h]
0x180009d19  mov     rax, [rbx]
0x180009d1c  test    rax, rax
0x180009d1f  jnz     short loc_180009D04
0x180009d21  mov     rax, [rsi]
0x180009d24  lea     rdx, [rsp+0AF0h+var_AC0]
0x180009d29  mov     rcx, rsi
0x180009d2c  mov     rax, [rax+28h]
0x180009d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d35  mov     ebx, eax
0x180009d37  test    eax, eax
0x180009d39  js      loc_180009F63
0x180009d3f  mov     rbx, cs:hInstance
0x180009d46  mov     edi, 104h
0x180009d4b  mov     r8d, edi; nSize
0x180009d4e  lea     rdx, [rbp+9F0h+Filename]; lpFilename
0x180009d52  mov     rcx, rbx; hModule
0x180009d55  call    cs:__imp_GetModuleFileNameW
0x180009d5c  nop     dword ptr [rax+rax+00h]
0x180009d61  test    eax, eax
0x180009d63  jnz     short loc_180009D71
0x180009d65  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009d6a  mov     ebx, eax
0x180009d6c  jmp     loc_180009F63
0x180009d71  cmp     eax, edi
0x180009d73  jnz     short loc_180009D7F
0x180009d75  mov     ebx, 8007007Ah
0x180009d7a  jmp     loc_180009F63
0x180009d7f  lea     rdx, [rbp+9F0h+Filename]
0x180009d83  mov     ecx, r15d
0x180009d86  mov     r9d, 27h ; '''
0x180009d8c  movzx   r8d, word ptr [rdx]
0x180009d90  test    r8w, r8w
0x180009d94  jz      short loc_180009DC6
0x180009d96  mov     [rbp+rcx*2+9F0h+Source], r8w
0x180009d9f  cmp     r8w, r9w
0x180009da3  jnz     short loc_180009DB8
0x180009da5  cmp     ecx, 206h
0x180009dab  jnb     short loc_180009DB8
0x180009dad  inc     ecx
0x180009daf  mov     [rbp+rcx*2+9F0h+Source], r9w
0x180009db8  add     rdx, 2
0x180009dbc  inc     ecx
0x180009dbe  cmp     ecx, 207h
0x180009dc4  jb      short loc_180009D8C
0x180009dc6  mov     [rbp+rcx*2+9F0h+Source], r15w
0x180009dcf  test    rbx, rbx
0x180009dd2  jz      short loc_180009E04
0x180009dd4  xor     ecx, ecx; lpModuleName
0x180009dd6  call    cs:__imp_GetModuleHandleW
0x180009ddd  nop     dword ptr [rax+rax+00h]
0x180009de2  cmp     rbx, rax
0x180009de5  jz      short loc_180009E04
0x180009de7  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180009dec  call    cs:__imp_EnterCriticalSection
0x180009df3  nop     dword ptr [rax+rax+00h]
0x180009df8  lea     r8, [rbp+9F0h+Source]
0x180009dff  jmp     loc_180009EA9
0x180009e04  mov     edi, 22h ; '"'
0x180009e09  mov     [rbp+9F0h+var_450], di
0x180009e10  lea     rcx, [rbp+9F0h+Source]
0x180009e17  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009e1b  mov     rax, rbx
0x180009e1e  inc     rax
0x180009e21  cmp     [rcx+rax*2], r15w
0x180009e26  jnz     short loc_180009E1E
0x180009e28  inc     eax
0x180009e2a  movsxd  r9, eax
0x180009e2d  add     r9, r9; SourceSize
0x180009e30  lea     r8, [rbp+9F0h+Source]; Source
0x180009e37  mov     edx, 414h; DestinationSize
0x180009e3c  lea     rcx, [rbp+9F0h+Destination]; Destination
0x180009e43  call    cs:__imp_memcpy_s
0x180009e4a  nop     dword ptr [rax+rax+00h]
0x180009e4f  test    eax, eax
0x180009e51  jnz     loc_180009F5E
0x180009e57  lea     rax, [rbp+9F0h+var_450]
0x180009e5e  inc     rbx
0x180009e61  cmp     [rax+rbx*2], r15w
0x180009e66  jnz     short loc_180009E5E
0x180009e68  movsxd  rax, ebx
0x180009e6b  mov     [rbp+rax*2+9F0h+var_450], di
0x180009e73  lea     rcx, ds:2[rax*2]
0x180009e7b  cmp     rcx, 418h
0x180009e82  jnb     loc_180009FA4
0x180009e88  mov     [rbp+rcx+9F0h+var_450], r15w
0x180009e91  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180009e96  call    cs:__imp_EnterCriticalSection
0x180009e9d  nop     dword ptr [rax+rax+00h]
0x180009ea2  lea     r8, [rbp+9F0h+var_450]; unsigned __int16 *
0x180009ea9  lea     rdx, aModule; "Module"
0x180009eb0  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180009eb5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009eba  mov     ebx, eax
0x180009ebc  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180009ec1  call    cs:__imp_LeaveCriticalSection
0x180009ec8  nop     dword ptr [rax+rax+00h]
0x180009ecd  neg     ebx
0x180009ecf  sbb     ebx, ebx
0x180009ed1  mov     edi, 8007000Eh
0x180009ed6  not     ebx
0x180009ed8  and     ebx, edi
0x180009eda  test    ebx, ebx
0x180009edc  js      loc_180009F63
0x180009ee2  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180009ee7  call    cs:__imp_EnterCriticalSection
0x180009eee  nop     dword ptr [rax+rax+00h]
0x180009ef3  lea     r8, [rbp+9F0h+Source]; unsigned __int16 *
0x180009efa  lea     rdx, aModuleRaw; "Module_Raw"
0x180009f01  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180009f06  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009f0b  mov     ebx, eax
0x180009f0d  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180009f12  call    cs:__imp_LeaveCriticalSection
0x180009f19  nop     dword ptr [rax+rax+00h]
0x180009f1e  mov     ecx, ebx
0x180009f20  neg     ecx
0x180009f22  sbb     eax, eax
0x180009f24  not     eax
0x180009f26  and     eax, edi
0x180009f28  test    ebx, ebx
0x180009f2a  jz      loc_180009D6A
0x180009f30  lea     r9, aRegistry; "REGISTRY"
0x180009f37  lea     rdx, [rbp+9F0h+Filename]; unsigned __int16 *
0x180009f3b  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180009f40  test    r14d, r14d
0x180009f43  jz      short loc_180009F4F
0x180009f45  mov     [rsp+0AF0h+var_AD0], 1
0x180009f4d  jmp     short loc_180009F54
0x180009f4f  mov     [rsp+0AF0h+var_AD0], r15d; int
0x180009f54  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009f59  jmp     loc_180009D6A
0x180009f5e  mov     ebx, 80004005h
0x180009f63  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180009f68  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009f6d  mov     eax, ebx
0x180009f6f  jmp     short loc_180009F7D
0x180009f71  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180009f76  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009f7b  mov     eax, edi
0x180009f7d  mov     rcx, [rbp+9F0h+var_30]
0x180009f84  xor     rcx, rsp; StackCookie
0x180009f87  call    __security_check_cookie
0x180009f8c  mov     rbx, [rsp+0AF0h+arg_8]
0x180009f94  add     rsp, 0AD0h
0x180009f9b  pop     r15
0x180009f9d  pop     r14
0x180009f9f  pop     rdi
0x180009fa0  pop     rsi
0x180009fa1  pop     rbp
0x180009fa2  retn
0x180009fa4  call    __report_rangecheckfailure
```
