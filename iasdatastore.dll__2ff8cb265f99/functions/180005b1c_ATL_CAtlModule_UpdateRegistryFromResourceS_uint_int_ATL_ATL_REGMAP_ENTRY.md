# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005b1c`
- end: `0x180005e33`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006180`
- `0x1800064c0`

## callees

- `0x180001938`
- `0x180002254`
- `0x18000252c`
- `0x180003114`
- `0x18000433c`
- `0x180004d18`
- `0x180005b1c`
- `0x18000dd10`
- `0x180010010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005cee`
- `msvcrt!memcpy_s` at `0x180005cee`
- `KERNEL32!EnterCriticalSection` at `0x180005bbd`
- `KERNEL32!EnterCriticalSection` at `0x180005ca6`
- `KERNEL32!EnterCriticalSection` at `0x180005d3b`
- `KERNEL32!EnterCriticalSection` at `0x180005d7c`
- `KERNEL32!EnterCriticalSection` at `0x180005bbd`
- `KERNEL32!EnterCriticalSection` at `0x180005ca6`
- `KERNEL32!EnterCriticalSection` at `0x180005d3b`
- `KERNEL32!EnterCriticalSection` at `0x180005d7c`
- `KERNEL32!LeaveCriticalSection` at `0x180005bd8`
- `KERNEL32!LeaveCriticalSection` at `0x180005d60`
- `KERNEL32!LeaveCriticalSection` at `0x180005d9e`
- `KERNEL32!LeaveCriticalSection` at `0x180005bd8`
- `KERNEL32!LeaveCriticalSection` at `0x180005d60`
- `KERNEL32!LeaveCriticalSection` at `0x180005d9e`
- `KERNEL32!GetModuleHandleW` at `0x180005c96`
- `KERNEL32!GetModuleHandleW` at `0x180005c96`
- `KERNEL32!GetModuleFileNameW` at `0x180005c21`
- `KERNEL32!GetModuleFileNameW` at `0x180005c21`

## string_xrefs

- `0x180005dc7`: `REGISTRY`

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
0x180005b1c  mov     [rsp-8+arg_10], rbx
0x180005b21  push    rbp
0x180005b22  push    rsi
0x180005b23  push    rdi
0x180005b24  push    r12
0x180005b26  push    r13
0x180005b28  push    r14
0x180005b2a  push    r15
0x180005b2c  lea     rbp, [rsp-9D0h]
0x180005b34  sub     rsp, 0AD0h
0x180005b3b  mov     rax, cs:__security_cookie
0x180005b42  xor     rax, rsp
0x180005b45  mov     [rbp+0A00h+var_40], rax
0x180005b4c  mov     rbx, r9
0x180005b4f  mov     r15d, r8d
0x180005b52  mov     r12d, edx
0x180005b55  mov     r14, rcx
0x180005b58  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005b5f  mov     [rsp+0B00h+var_AD0], rax
0x180005b64  xor     r13d, r13d
0x180005b67  mov     [rsp+0B00h+var_AC8], r13
0x180005b6c  mov     [rsp+0B00h+var_AC0], r13
0x180005b71  mov     [rsp+0B00h+var_AB8], r13d
0x180005b76  xorps   xmm0, xmm0
0x180005b79  xor     eax, eax
0x180005b7b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180005b80  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005b85  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180005b8a  mov     [rsp+0B00h+var_A88], r13b
0x180005b8f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180005b94  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005b99  mov     edi, eax
0x180005b9b  test    eax, eax
0x180005b9d  js      loc_180005DF7
0x180005ba3  mov     [rsp+0B00h+var_A88], 1
0x180005ba8  test    rbx, rbx
0x180005bab  jz      short loc_180005BEA
0x180005bad  jmp     short loc_180005BE2
0x180005baf  mov     rsi, [rbx+8]
0x180005bb3  test    rsi, rsi
0x180005bb6  jz      short loc_180005BDE
0x180005bb8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005bbd  call    cs:__imp_EnterCriticalSection
0x180005bc3  mov     r8, rsi; unsigned __int16 *
0x180005bc6  mov     rdx, rdi; unsigned __int16 *
0x180005bc9  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005bce  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005bd3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005bd8  call    cs:__imp_LeaveCriticalSection
0x180005bde  add     rbx, 10h
0x180005be2  mov     rdi, [rbx]
0x180005be5  test    rdi, rdi
0x180005be8  jnz     short loc_180005BAF
0x180005bea  mov     rax, [r14]
0x180005bed  lea     rdx, [rsp+0B00h+var_AD0]
0x180005bf2  mov     rcx, r14
0x180005bf5  mov     rax, [rax+28h]
0x180005bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfe  mov     ebx, eax
0x180005c00  test    eax, eax
0x180005c02  js      loc_180005DE9
0x180005c08  mov     rbx, cs:hInstance
0x180005c0f  mov     edi, 104h
0x180005c14  mov     r8d, edi; nSize
0x180005c17  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005c1e  mov     rcx, rbx; hModule
0x180005c21  call    cs:__imp_GetModuleFileNameW
0x180005c27  test    eax, eax
0x180005c29  jnz     short loc_180005C37
0x180005c2b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005c30  mov     ebx, eax
0x180005c32  jmp     loc_180005DE9
0x180005c37  cmp     eax, edi
0x180005c39  jnz     short loc_180005C45
0x180005c3b  mov     ebx, 8007007Ah
0x180005c40  jmp     loc_180005DE9
0x180005c45  lea     rdx, [rbp+0A00h+Filename]
0x180005c4c  mov     ecx, r13d
0x180005c4f  mov     r9d, 27h ; '''
0x180005c55  movzx   r8d, word ptr [rdx]
0x180005c59  test    r8w, r8w
0x180005c5d  jz      short loc_180005C89
0x180005c5f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005c65  cmp     r8w, r9w
0x180005c69  jnz     short loc_180005C7B
0x180005c6b  cmp     ecx, 206h
0x180005c71  jnb     short loc_180005C7B
0x180005c73  inc     ecx
0x180005c75  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180005c7b  add     rdx, 2
0x180005c7f  inc     ecx
0x180005c81  cmp     ecx, 207h
0x180005c87  jb      short loc_180005C55
0x180005c89  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180005c8f  test    rbx, rbx
0x180005c92  jz      short loc_180005CB5
0x180005c94  xor     ecx, ecx; lpModuleName
0x180005c96  call    cs:__imp_GetModuleHandleW
0x180005c9c  cmp     rbx, rax
0x180005c9f  jz      short loc_180005CB5
0x180005ca1  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005ca6  call    cs:__imp_EnterCriticalSection
0x180005cac  lea     r8, [rbp+0A00h+Source]
0x180005cb0  jmp     loc_180005D48
0x180005cb5  mov     edi, 22h ; '"'
0x180005cba  mov     [rbp+0A00h+var_460], di
0x180005cc1  lea     rcx, [rbp+0A00h+Source]
0x180005cc5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005cc9  mov     rax, rbx
0x180005ccc  inc     rax
0x180005ccf  cmp     [rcx+rax*2], r13w
0x180005cd4  jnz     short loc_180005CCC
0x180005cd6  inc     eax
0x180005cd8  movsxd  r9, eax
0x180005cdb  add     r9, r9; SourceSize
0x180005cde  lea     r8, [rbp+0A00h+Source]; Source
0x180005ce2  mov     edx, 414h; DestinationSize
0x180005ce7  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180005cee  call    cs:__imp_memcpy_s
0x180005cf4  test    eax, eax
0x180005cf6  jnz     loc_180005DE4
0x180005cfc  lea     rax, [rbp+0A00h+var_460]
0x180005d03  inc     rbx
0x180005d06  cmp     [rax+rbx*2], r13w
0x180005d0b  jnz     short loc_180005D03
0x180005d0d  movsxd  rax, ebx
0x180005d10  mov     [rbp+rax*2+0A00h+var_460], di
0x180005d18  lea     rcx, ds:2[rax*2]
0x180005d20  cmp     rcx, 418h
0x180005d27  jnb     loc_180005E2D
0x180005d2d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180005d36  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005d3b  call    cs:__imp_EnterCriticalSection
0x180005d41  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005d48  lea     rdx, aModule; "Module"
0x180005d4f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005d54  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005d59  mov     ebx, eax
0x180005d5b  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005d60  call    cs:__imp_LeaveCriticalSection
0x180005d66  neg     ebx
0x180005d68  sbb     ebx, ebx
0x180005d6a  mov     edi, 8007000Eh
0x180005d6f  not     ebx
0x180005d71  and     ebx, edi
0x180005d73  test    ebx, ebx
0x180005d75  js      short loc_180005DE9
0x180005d77  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005d7c  call    cs:__imp_EnterCriticalSection
0x180005d82  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005d86  lea     rdx, aModuleRaw; "Module_Raw"
0x180005d8d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005d92  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005d97  mov     ebx, eax
0x180005d99  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005d9e  call    cs:__imp_LeaveCriticalSection
0x180005da4  mov     ecx, ebx
0x180005da6  neg     ecx
0x180005da8  sbb     eax, eax
0x180005daa  not     eax
0x180005dac  and     eax, edi
0x180005dae  test    ebx, ebx
0x180005db0  jz      loc_180005C30
0x180005db6  mov     eax, r13d
0x180005db9  test    r15d, r15d
0x180005dbc  setnz   al
0x180005dbf  movzx   r8d, r12w; unsigned __int16 *
0x180005dc3  mov     [rsp+0B00h+var_AE0], eax; int
0x180005dc7  lea     r9, aRegistry; "REGISTRY"
0x180005dce  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180005dd5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005dda  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180005ddf  jmp     loc_180005C30
0x180005de4  mov     ebx, 80004005h
0x180005de9  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005dee  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005df3  mov     eax, ebx
0x180005df5  jmp     short loc_180005E03
0x180005df7  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005dfc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005e01  mov     eax, edi
0x180005e03  mov     rcx, [rbp+0A00h+var_40]
0x180005e0a  xor     rcx, rsp; StackCookie
0x180005e0d  call    __security_check_cookie
0x180005e12  mov     rbx, [rsp+0B00h+arg_10]
0x180005e1a  add     rsp, 0AD0h
0x180005e21  pop     r15
0x180005e23  pop     r14
0x180005e25  pop     r13
0x180005e27  pop     r12
0x180005e29  pop     rdi
0x180005e2a  pop     rsi
0x180005e2b  pop     rbp
0x180005e2c  retn
0x180005e2d  call    __report_rangecheckfailure
```
