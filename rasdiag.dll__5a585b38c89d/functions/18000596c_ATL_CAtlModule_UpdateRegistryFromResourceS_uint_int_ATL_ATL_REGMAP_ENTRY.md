# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000596c`
- end: `0x180005c98`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `812`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, __int64, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005e50`
- `0x180005f70`
- `0x180008180`

## callees

- `0x180002398`
- `0x180002c04`
- `0x180002d90`
- `0x180003070`
- `0x18000383c`
- `0x18000447c`
- `0x180004cf0`
- `0x18000596c`
- `0x18000df10`
- `0x18000f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005b38`
- `msvcrt!memcpy_s` at `0x180005b38`
- `KERNEL32!GetModuleHandleW` at `0x180005acb`
- `KERNEL32!GetModuleHandleW` at `0x180005acb`
- `KERNEL32!LeaveCriticalSection` at `0x180005bb6`
- `KERNEL32!LeaveCriticalSection` at `0x180005c07`
- `KERNEL32!LeaveCriticalSection` at `0x180005bb6`
- `KERNEL32!LeaveCriticalSection` at `0x180005c07`
- `KERNEL32!EnterCriticalSection` at `0x180005ae1`
- `KERNEL32!EnterCriticalSection` at `0x180005b8b`
- `KERNEL32!EnterCriticalSection` at `0x180005bdc`
- `KERNEL32!EnterCriticalSection` at `0x180005ae1`
- `KERNEL32!EnterCriticalSection` at `0x180005b8b`
- `KERNEL32!EnterCriticalSection` at `0x180005bdc`
- `KERNEL32!GetModuleFileNameW` at `0x180005a4a`
- `KERNEL32!GetModuleFileNameW` at `0x180005a4a`

## string_xrefs

- `0x180005c25`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v6; // rsi
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

  v6 = ATL::_pAtlModule;
  v23 = &ATL::CRegObject::`vftable';
  v24[0] = 0;
  v24[1] = 0;
  v25 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v27 = 0;
  v7 = ATL::CComCriticalSection::Init(&CriticalSection);
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
    v8 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v23);
    if ( v8 < 0 )
      goto LABEL_34;
    v9 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
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
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v23, Filename, v21, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v23, Filename, v21, L"REGISTRY", 0);
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
0x18000596c  push    rbp
0x18000596e  push    rbx
0x18000596f  push    rsi
0x180005970  push    rdi
0x180005971  push    r14
0x180005973  push    r15
0x180005975  lea     rbp, [rsp-9D8h]
0x18000597d  sub     rsp, 0AD8h
0x180005984  mov     rax, cs:__security_cookie
0x18000598b  xor     rax, rsp
0x18000598e  mov     [rbp+0A00h+var_40], rax
0x180005995  mov     rbx, r9
0x180005998  mov     r14d, r8d
0x18000599b  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800059a2  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800059a9  mov     [rsp+0B00h+var_AD0], rax
0x1800059ae  xor     r15d, r15d
0x1800059b1  mov     [rsp+0B00h+var_AC8], r15
0x1800059b6  mov     [rsp+0B00h+var_AC0], r15
0x1800059bb  mov     [rsp+0B00h+var_AB8], r15d
0x1800059c0  xorps   xmm0, xmm0
0x1800059c3  xor     eax, eax
0x1800059c5  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800059ca  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800059cf  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800059d4  mov     [rsp+0B00h+var_A88], r15b
0x1800059d9  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800059de  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800059e3  mov     edi, eax
0x1800059e5  test    eax, eax
0x1800059e7  js      loc_180005C66
0x1800059ed  mov     [rsp+0B00h+var_A88], 1
0x1800059f2  test    rbx, rbx
0x1800059f5  jz      short loc_180005A16
0x1800059f7  jmp     short loc_180005A0E
0x1800059f9  mov     r8, [rbx+8]; unsigned __int16 *
0x1800059fd  mov     rdx, rax; unsigned __int16 *
0x180005a00  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005a05  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180005a0a  lea     rbx, [rbx+10h]
0x180005a0e  mov     rax, [rbx]
0x180005a11  test    rax, rax
0x180005a14  jnz     short loc_1800059F9
0x180005a16  mov     rax, [rsi]
0x180005a19  lea     rdx, [rsp+0B00h+var_AD0]
0x180005a1e  mov     rcx, rsi
0x180005a21  mov     rax, [rax+28h]
0x180005a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a2a  mov     ebx, eax
0x180005a2c  test    eax, eax
0x180005a2e  js      loc_180005C58
0x180005a34  mov     rbx, cs:hModule
0x180005a3b  mov     edi, 104h
0x180005a40  mov     r8d, edi; nSize
0x180005a43  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005a47  mov     rcx, rbx; hModule
0x180005a4a  call    cs:__imp_GetModuleFileNameW
0x180005a51  nop     dword ptr [rax+rax+00h]
0x180005a56  test    eax, eax
0x180005a58  jnz     short loc_180005A66
0x180005a5a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005a5f  mov     ebx, eax
0x180005a61  jmp     loc_180005C58
0x180005a66  cmp     eax, edi
0x180005a68  jnz     short loc_180005A74
0x180005a6a  mov     ebx, 8007007Ah
0x180005a6f  jmp     loc_180005C58
0x180005a74  lea     rdx, [rbp+0A00h+Filename]
0x180005a78  mov     ecx, r15d
0x180005a7b  mov     r9d, 27h ; '''
0x180005a81  movzx   r8d, word ptr [rdx]
0x180005a85  test    r8w, r8w
0x180005a89  jz      short loc_180005ABB
0x180005a8b  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005a94  cmp     r8w, r9w
0x180005a98  jnz     short loc_180005AAD
0x180005a9a  cmp     ecx, 206h
0x180005aa0  jnb     short loc_180005AAD
0x180005aa2  inc     ecx
0x180005aa4  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180005aad  add     rdx, 2
0x180005ab1  inc     ecx
0x180005ab3  cmp     ecx, 207h
0x180005ab9  jb      short loc_180005A81
0x180005abb  mov     [rbp+rcx*2+0A00h+Source], r15w
0x180005ac4  test    rbx, rbx
0x180005ac7  jz      short loc_180005AF9
0x180005ac9  xor     ecx, ecx; lpModuleName
0x180005acb  call    cs:__imp_GetModuleHandleW
0x180005ad2  nop     dword ptr [rax+rax+00h]
0x180005ad7  cmp     rbx, rax
0x180005ada  jz      short loc_180005AF9
0x180005adc  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005ae1  call    cs:__imp_EnterCriticalSection
0x180005ae8  nop     dword ptr [rax+rax+00h]
0x180005aed  lea     r8, [rbp+0A00h+Source]
0x180005af4  jmp     loc_180005B9E
0x180005af9  mov     edi, 22h ; '"'
0x180005afe  mov     [rbp+0A00h+var_460], di
0x180005b05  lea     rcx, [rbp+0A00h+Source]
0x180005b0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005b10  mov     rax, rbx
0x180005b13  inc     rax
0x180005b16  cmp     [rcx+rax*2], r15w
0x180005b1b  jnz     short loc_180005B13
0x180005b1d  inc     eax
0x180005b1f  movsxd  r9, eax
0x180005b22  add     r9, r9; SourceSize
0x180005b25  lea     r8, [rbp+0A00h+Source]; Source
0x180005b2c  mov     edx, 414h; DestinationSize
0x180005b31  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180005b38  call    cs:__imp_memcpy_s
0x180005b3f  nop     dword ptr [rax+rax+00h]
0x180005b44  test    eax, eax
0x180005b46  jnz     loc_180005C53
0x180005b4c  lea     rax, [rbp+0A00h+var_460]
0x180005b53  inc     rbx
0x180005b56  cmp     [rax+rbx*2], r15w
0x180005b5b  jnz     short loc_180005B53
0x180005b5d  movsxd  rax, ebx
0x180005b60  mov     [rbp+rax*2+0A00h+var_460], di
0x180005b68  lea     rcx, ds:2[rax*2]
0x180005b70  cmp     rcx, 418h
0x180005b77  jnb     loc_180005C92
0x180005b7d  mov     [rbp+rcx+0A00h+var_460], r15w
0x180005b86  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005b8b  call    cs:__imp_EnterCriticalSection
0x180005b92  nop     dword ptr [rax+rax+00h]
0x180005b97  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005b9e  lea     rdx, aModule; "Module"
0x180005ba5  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005baa  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005baf  mov     ebx, eax
0x180005bb1  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005bb6  call    cs:__imp_LeaveCriticalSection
0x180005bbd  nop     dword ptr [rax+rax+00h]
0x180005bc2  neg     ebx
0x180005bc4  sbb     ebx, ebx
0x180005bc6  mov     edi, 8007000Eh
0x180005bcb  not     ebx
0x180005bcd  and     ebx, edi
0x180005bcf  test    ebx, ebx
0x180005bd1  js      loc_180005C58
0x180005bd7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005bdc  call    cs:__imp_EnterCriticalSection
0x180005be3  nop     dword ptr [rax+rax+00h]
0x180005be8  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005bef  lea     rdx, aModuleRaw; "Module_Raw"
0x180005bf6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005bfb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005c00  mov     ebx, eax
0x180005c02  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005c07  call    cs:__imp_LeaveCriticalSection
0x180005c0e  nop     dword ptr [rax+rax+00h]
0x180005c13  mov     ecx, ebx
0x180005c15  neg     ecx
0x180005c17  sbb     eax, eax
0x180005c19  not     eax
0x180005c1b  and     eax, edi
0x180005c1d  test    ebx, ebx
0x180005c1f  jz      loc_180005A5F
0x180005c25  lea     r9, aRegistry; "REGISTRY"
0x180005c2c  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180005c30  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005c35  test    r14d, r14d
0x180005c38  jz      short loc_180005C44
0x180005c3a  mov     [rsp+0B00h+var_AE0], 1
0x180005c42  jmp     short loc_180005C49
0x180005c44  mov     [rsp+0B00h+var_AE0], r15d; int
0x180005c49  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180005c4e  jmp     loc_180005A5F
0x180005c53  mov     ebx, 80004005h
0x180005c58  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005c5d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005c62  mov     eax, ebx
0x180005c64  jmp     short loc_180005C72
0x180005c66  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005c6b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005c70  mov     eax, edi
0x180005c72  mov     rcx, [rbp+0A00h+var_40]
0x180005c79  xor     rcx, rsp; StackCookie
0x180005c7c  call    __security_check_cookie
0x180005c81  add     rsp, 0AD8h
0x180005c88  pop     r15
0x180005c8a  pop     r14
0x180005c8c  pop     rdi
0x180005c8d  pop     rsi
0x180005c8e  pop     rbx
0x180005c8f  pop     rbp
0x180005c90  retn
0x180005c92  call    __report_rangecheckfailure
```
