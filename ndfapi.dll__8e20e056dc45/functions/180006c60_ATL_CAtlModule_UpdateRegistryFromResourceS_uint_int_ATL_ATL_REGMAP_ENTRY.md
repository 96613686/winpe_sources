# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006c60`
- end: `0x180006f7b`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `795`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800077d0`
- `0x1800078e0`
- `0x1800157c0`

## callees

- `0x180002488`
- `0x180004220`
- `0x1800043c0`
- `0x180004df8`
- `0x1800058fc`
- `0x1800060c8`
- `0x180006c60`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006e36`
- `msvcrt!memcpy_s` at `0x180006e36`
- `KERNEL32!GetModuleHandleW` at `0x180006dde`
- `KERNEL32!GetModuleHandleW` at `0x180006dde`
- `KERNEL32!EnterCriticalSection` at `0x180006d05`
- `KERNEL32!EnterCriticalSection` at `0x180006dee`
- `KERNEL32!EnterCriticalSection` at `0x180006e83`
- `KERNEL32!EnterCriticalSection` at `0x180006ec4`
- `KERNEL32!EnterCriticalSection` at `0x180006d05`
- `KERNEL32!EnterCriticalSection` at `0x180006dee`
- `KERNEL32!EnterCriticalSection` at `0x180006e83`
- `KERNEL32!EnterCriticalSection` at `0x180006ec4`
- `KERNEL32!LeaveCriticalSection` at `0x180006d20`
- `KERNEL32!LeaveCriticalSection` at `0x180006ea8`
- `KERNEL32!LeaveCriticalSection` at `0x180006ee6`
- `KERNEL32!LeaveCriticalSection` at `0x180006d20`
- `KERNEL32!LeaveCriticalSection` at `0x180006ea8`
- `KERNEL32!LeaveCriticalSection` at `0x180006ee6`
- `KERNEL32!GetModuleFileNameW` at `0x180006d69`
- `KERNEL32!GetModuleFileNameW` at `0x180006d69`

## string_xrefs

- `0x180006f0f`: `REGISTRY`

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
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
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
0x180006c60  mov     [rsp-8+arg_0], rbx
0x180006c65  push    rbp
0x180006c66  push    rsi
0x180006c67  push    rdi
0x180006c68  push    r12
0x180006c6a  push    r13
0x180006c6c  push    r14
0x180006c6e  push    r15
0x180006c70  lea     rbp, [rsp-9D0h]
0x180006c78  sub     rsp, 0AD0h
0x180006c7f  mov     rax, cs:__security_cookie
0x180006c86  xor     rax, rsp
0x180006c89  mov     [rbp+0A00h+var_40], rax
0x180006c90  mov     rbx, r9
0x180006c93  mov     r15d, r8d
0x180006c96  mov     r12d, edx
0x180006c99  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006ca0  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180006ca7  mov     [rsp+0B00h+var_AD0], rax
0x180006cac  xor     r13d, r13d
0x180006caf  mov     [rsp+0B00h+var_AC8], r13
0x180006cb4  mov     [rsp+0B00h+var_AC0], r13
0x180006cb9  mov     [rsp+0B00h+var_AB8], r13d
0x180006cbe  xorps   xmm0, xmm0
0x180006cc1  xor     eax, eax
0x180006cc3  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180006cc8  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180006ccd  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180006cd2  mov     [rsp+0B00h+var_A88], r13b
0x180006cd7  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180006cdc  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006ce1  mov     edi, eax
0x180006ce3  test    eax, eax
0x180006ce5  js      loc_180006F3F
0x180006ceb  mov     [rsp+0B00h+var_A88], 1
0x180006cf0  test    rbx, rbx
0x180006cf3  jz      short loc_180006D32
0x180006cf5  jmp     short loc_180006D2A
0x180006cf7  mov     rsi, [rbx+8]
0x180006cfb  test    rsi, rsi
0x180006cfe  jz      short loc_180006D26
0x180006d00  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006d05  call    cs:__imp_EnterCriticalSection
0x180006d0b  mov     r8, rsi; unsigned __int16 *
0x180006d0e  mov     rdx, rdi; unsigned __int16 *
0x180006d11  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006d16  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006d1b  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006d20  call    cs:__imp_LeaveCriticalSection
0x180006d26  add     rbx, 10h
0x180006d2a  mov     rdi, [rbx]
0x180006d2d  test    rdi, rdi
0x180006d30  jnz     short loc_180006CF7
0x180006d32  mov     rax, [r14]
0x180006d35  lea     rdx, [rsp+0B00h+var_AD0]
0x180006d3a  mov     rcx, r14
0x180006d3d  mov     rax, [rax+28h]
0x180006d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d46  mov     ebx, eax
0x180006d48  test    eax, eax
0x180006d4a  js      loc_180006F31
0x180006d50  mov     rbx, cs:hModule
0x180006d57  mov     edi, 104h
0x180006d5c  mov     r8d, edi; nSize
0x180006d5f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180006d66  mov     rcx, rbx; hModule
0x180006d69  call    cs:__imp_GetModuleFileNameW
0x180006d6f  test    eax, eax
0x180006d71  jnz     short loc_180006D7F
0x180006d73  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006d78  mov     ebx, eax
0x180006d7a  jmp     loc_180006F31
0x180006d7f  cmp     eax, edi
0x180006d81  jnz     short loc_180006D8D
0x180006d83  mov     ebx, 8007007Ah
0x180006d88  jmp     loc_180006F31
0x180006d8d  lea     rdx, [rbp+0A00h+Filename]
0x180006d94  mov     ecx, r13d
0x180006d97  mov     r9d, 27h ; '''
0x180006d9d  movzx   r8d, word ptr [rdx]
0x180006da1  test    r8w, r8w
0x180006da5  jz      short loc_180006DD1
0x180006da7  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180006dad  cmp     r8w, r9w
0x180006db1  jnz     short loc_180006DC3
0x180006db3  cmp     ecx, 206h
0x180006db9  jnb     short loc_180006DC3
0x180006dbb  inc     ecx
0x180006dbd  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180006dc3  add     rdx, 2
0x180006dc7  inc     ecx
0x180006dc9  cmp     ecx, 207h
0x180006dcf  jb      short loc_180006D9D
0x180006dd1  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180006dd7  test    rbx, rbx
0x180006dda  jz      short loc_180006DFD
0x180006ddc  xor     ecx, ecx; lpModuleName
0x180006dde  call    cs:__imp_GetModuleHandleW
0x180006de4  cmp     rbx, rax
0x180006de7  jz      short loc_180006DFD
0x180006de9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006dee  call    cs:__imp_EnterCriticalSection
0x180006df4  lea     r8, [rbp+0A00h+Source]
0x180006df8  jmp     loc_180006E90
0x180006dfd  mov     edi, 22h ; '"'
0x180006e02  mov     [rbp+0A00h+var_460], di
0x180006e09  lea     rcx, [rbp+0A00h+Source]
0x180006e0d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006e11  mov     rax, rbx
0x180006e14  inc     rax
0x180006e17  cmp     [rcx+rax*2], r13w
0x180006e1c  jnz     short loc_180006E14
0x180006e1e  inc     eax
0x180006e20  movsxd  r9, eax
0x180006e23  add     r9, r9; SourceSize
0x180006e26  lea     r8, [rbp+0A00h+Source]; Source
0x180006e2a  mov     edx, 414h; DestinationSize
0x180006e2f  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180006e36  call    cs:__imp_memcpy_s
0x180006e3c  test    eax, eax
0x180006e3e  jnz     loc_180006F2C
0x180006e44  lea     rax, [rbp+0A00h+var_460]
0x180006e4b  inc     rbx
0x180006e4e  cmp     [rax+rbx*2], r13w
0x180006e53  jnz     short loc_180006E4B
0x180006e55  movsxd  rax, ebx
0x180006e58  mov     [rbp+rax*2+0A00h+var_460], di
0x180006e60  lea     rcx, ds:2[rax*2]
0x180006e68  cmp     rcx, 418h
0x180006e6f  jnb     loc_180006F75
0x180006e75  mov     [rbp+rcx+0A00h+var_460], r13w
0x180006e7e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006e83  call    cs:__imp_EnterCriticalSection
0x180006e89  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180006e90  lea     rdx, aModule; "Module"
0x180006e97  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006e9c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006ea1  mov     ebx, eax
0x180006ea3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006ea8  call    cs:__imp_LeaveCriticalSection
0x180006eae  neg     ebx
0x180006eb0  sbb     ebx, ebx
0x180006eb2  mov     edi, 8007000Eh
0x180006eb7  not     ebx
0x180006eb9  and     ebx, edi
0x180006ebb  test    ebx, ebx
0x180006ebd  js      short loc_180006F31
0x180006ebf  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006ec4  call    cs:__imp_EnterCriticalSection
0x180006eca  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180006ece  lea     rdx, aModuleRaw; "Module_Raw"
0x180006ed5  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006eda  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006edf  mov     ebx, eax
0x180006ee1  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006ee6  call    cs:__imp_LeaveCriticalSection
0x180006eec  mov     ecx, ebx
0x180006eee  neg     ecx
0x180006ef0  sbb     eax, eax
0x180006ef2  not     eax
0x180006ef4  and     eax, edi
0x180006ef6  test    ebx, ebx
0x180006ef8  jz      loc_180006D78
0x180006efe  mov     eax, r13d
0x180006f01  test    r15d, r15d
0x180006f04  setnz   al
0x180006f07  movzx   r8d, r12w; unsigned __int16 *
0x180006f0b  mov     [rsp+0B00h+var_AE0], eax; int
0x180006f0f  lea     r9, aRegistry; "REGISTRY"
0x180006f16  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006f1d  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006f22  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006f27  jmp     loc_180006D78
0x180006f2c  mov     ebx, 80004005h
0x180006f31  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006f36  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006f3b  mov     eax, ebx
0x180006f3d  jmp     short loc_180006F4B
0x180006f3f  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006f44  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006f49  mov     eax, edi
0x180006f4b  mov     rcx, [rbp+0A00h+var_40]
0x180006f52  xor     rcx, rsp; StackCookie
0x180006f55  call    __security_check_cookie
0x180006f5a  mov     rbx, [rsp+0B00h+arg_0]
0x180006f62  add     rsp, 0AD0h
0x180006f69  pop     r15
0x180006f6b  pop     r14
0x180006f6d  pop     r13
0x180006f6f  pop     r12
0x180006f71  pop     rdi
0x180006f72  pop     rsi
0x180006f73  pop     rbp
0x180006f74  retn
0x180006f75  call    __report_rangecheckfailure
```
