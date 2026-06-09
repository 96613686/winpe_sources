# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000579c`
- end: `0x180005ada`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005af0`

## callees

- `0x1800017c8`
- `0x180002824`
- `0x1800029fc`
- `0x180003484`
- `0x180003edc`
- `0x180004818`
- `0x18000579c`
- `0x180006030`
- `0x180007010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000597a`
- `msvcrt!memcpy_s` at `0x18000597a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005858`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005858`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000583d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005929`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000583d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005929`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000589e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000589e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005919`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005919`

## string_xrefs

- `0x180005a67`: `REGISTRY`

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
0x18000579c  mov     [rsp-8+arg_10], rbx
0x1800057a1  push    rbp
0x1800057a2  push    rsi
0x1800057a3  push    rdi
0x1800057a4  push    r12
0x1800057a6  push    r13
0x1800057a8  push    r14
0x1800057aa  push    r15
0x1800057ac  lea     rbp, [rsp-9D0h]
0x1800057b4  sub     rsp, 0AD0h
0x1800057bb  mov     rax, cs:__security_cookie
0x1800057c2  xor     rax, rsp
0x1800057c5  mov     [rbp+0A00h+var_40], rax
0x1800057cc  xor     r13d, r13d
0x1800057cf  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800057d6  xorps   xmm0, xmm0
0x1800057d9  mov     [rsp+0B00h+var_AD0], rax
0x1800057de  xor     eax, eax
0x1800057e0  mov     [rsp+0B00h+var_AC8], r13
0x1800057e5  mov     r15, rcx
0x1800057e8  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800057ed  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800057f2  mov     [rsp+0B00h+var_AC0], r13
0x1800057f7  mov     rbx, r9
0x1800057fa  mov     [rsp+0B00h+var_AB8], r13d
0x1800057ff  mov     r12d, r8d
0x180005802  mov     [rsp+0B00h+var_A88], r13b
0x180005807  mov     r14, rdx
0x18000580a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000580f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005814  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005819  mov     edi, eax
0x18000581b  test    eax, eax
0x18000581d  js      loc_180005A9E
0x180005823  mov     [rsp+0B00h+var_A88], 1
0x180005828  test    rbx, rbx
0x18000582b  jz      short loc_18000586A
0x18000582d  jmp     short loc_180005862
0x18000582f  mov     rsi, [rbx+8]
0x180005833  test    rsi, rsi
0x180005836  jz      short loc_18000585E
0x180005838  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000583d  call    cs:__imp_EnterCriticalSection
0x180005843  mov     r8, rsi; unsigned __int16 *
0x180005846  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000584b  mov     rdx, rdi; unsigned __int16 *
0x18000584e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005853  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005858  call    cs:__imp_LeaveCriticalSection
0x18000585e  add     rbx, 10h
0x180005862  mov     rdi, [rbx]
0x180005865  test    rdi, rdi
0x180005868  jnz     short loc_18000582F
0x18000586a  mov     rax, [r15]
0x18000586d  lea     rdx, [rsp+0B00h+var_AD0]
0x180005872  mov     rcx, r15
0x180005875  mov     rax, [rax+28h]
0x180005879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587e  mov     ebx, eax
0x180005880  test    eax, eax
0x180005882  js      loc_180005A90
0x180005888  mov     rbx, cs:hModule
0x18000588f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005893  mov     edi, 104h
0x180005898  mov     rcx, rbx; hModule
0x18000589b  mov     r8d, edi; nSize
0x18000589e  call    cs:__imp_GetModuleFileNameW
0x1800058a4  test    eax, eax
0x1800058a6  jnz     short loc_1800058B4
0x1800058a8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800058ad  mov     ebx, eax
0x1800058af  jmp     loc_180005A90
0x1800058b4  cmp     eax, edi
0x1800058b6  jnz     short loc_1800058C2
0x1800058b8  mov     ebx, 8007007Ah
0x1800058bd  jmp     loc_180005A90
0x1800058c2  lea     rdx, [rbp+0A00h+Filename]
0x1800058c6  mov     ecx, r13d
0x1800058c9  mov     r9d, 27h ; '''
0x1800058cf  movzx   r8d, word ptr [rdx]
0x1800058d3  test    r8w, r8w
0x1800058d7  jz      short loc_180005909
0x1800058d9  mov     [rbp+rcx*2+0A00h+Source], r8w
0x1800058e2  cmp     r8w, r9w
0x1800058e6  jnz     short loc_1800058FB
0x1800058e8  cmp     ecx, 206h
0x1800058ee  jnb     short loc_1800058FB
0x1800058f0  inc     ecx
0x1800058f2  mov     [rbp+rcx*2+0A00h+Source], r9w
0x1800058fb  add     rdx, 2
0x1800058ff  inc     ecx
0x180005901  cmp     ecx, 207h
0x180005907  jb      short loc_1800058CF
0x180005909  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180005912  test    rbx, rbx
0x180005915  jz      short loc_18000593B
0x180005917  xor     ecx, ecx; lpModuleName
0x180005919  call    cs:__imp_GetModuleHandleW
0x18000591f  cmp     rbx, rax
0x180005922  jz      short loc_18000593B
0x180005924  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005929  call    cs:__imp_EnterCriticalSection
0x18000592f  lea     r8, [rbp+0A00h+Source]
0x180005936  jmp     loc_1800059D4
0x18000593b  mov     edi, 22h ; '"'
0x180005940  lea     rcx, [rbp+0A00h+Source]
0x180005947  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000594b  mov     [rbp+0A00h+var_460], di
0x180005952  mov     rax, rbx
0x180005955  inc     rax
0x180005958  cmp     [rcx+rax*2], r13w
0x18000595d  jnz     short loc_180005955
0x18000595f  inc     eax
0x180005961  lea     r8, [rbp+0A00h+Source]; Source
0x180005968  movsxd  r9, eax
0x18000596b  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180005972  add     r9, r9; SourceSize
0x180005975  mov     edx, 414h; DestinationSize
0x18000597a  call    cs:__imp_memcpy_s
0x180005980  test    eax, eax
0x180005982  jnz     loc_180005A8B
0x180005988  lea     rax, [rbp+0A00h+var_460]
0x18000598f  inc     rbx
0x180005992  cmp     [rax+rbx*2], r13w
0x180005997  jnz     short loc_18000598F
0x180005999  movsxd  rax, ebx
0x18000599c  lea     rcx, ds:2[rax*2]
0x1800059a4  mov     [rbp+rax*2+0A00h+var_460], di
0x1800059ac  cmp     rcx, 418h
0x1800059b3  jnb     loc_180005AD4
0x1800059b9  mov     [rbp+rcx+0A00h+var_460], r13w
0x1800059c2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800059c7  call    cs:__imp_EnterCriticalSection
0x1800059cd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1800059d4  lea     rdx, aModule; "Module"
0x1800059db  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800059e0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800059e5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800059ea  mov     ebx, eax
0x1800059ec  call    cs:__imp_LeaveCriticalSection
0x1800059f2  neg     ebx
0x1800059f4  mov     edi, 8007000Eh
0x1800059f9  sbb     ebx, ebx
0x1800059fb  not     ebx
0x1800059fd  and     ebx, edi
0x1800059ff  test    ebx, ebx
0x180005a01  js      loc_180005A90
0x180005a07  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005a0c  call    cs:__imp_EnterCriticalSection
0x180005a12  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005a19  lea     rdx, aModuleRaw; "Module_Raw"
0x180005a20  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005a25  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005a2a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005a2f  mov     ebx, eax
0x180005a31  call    cs:__imp_LeaveCriticalSection
0x180005a37  mov     ecx, ebx
0x180005a39  neg     ecx
0x180005a3b  sbb     eax, eax
0x180005a3d  not     eax
0x180005a3f  and     eax, edi
0x180005a41  test    ebx, ebx
0x180005a43  jz      loc_1800058AD
0x180005a49  test    r12d, r12d
0x180005a4c  jz      short loc_180005A5D
0x180005a4e  test    r14, r14
0x180005a51  jz      short loc_180005A84
0x180005a53  mov     [rsp+0B00h+var_AE0], 1
0x180005a5b  jmp     short loc_180005A67
0x180005a5d  test    r14, r14
0x180005a60  jz      short loc_180005A84
0x180005a62  mov     [rsp+0B00h+var_AE0], r13d; int
0x180005a67  lea     r9, aRegistry; "REGISTRY"
0x180005a6e  mov     r8, r14; unsigned __int16 *
0x180005a71  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180005a75  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005a7a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180005a7f  jmp     loc_1800058AD
0x180005a84  mov     ebx, 80070057h
0x180005a89  jmp     short loc_180005A90
0x180005a8b  mov     ebx, 80004005h
0x180005a90  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005a95  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005a9a  mov     eax, ebx
0x180005a9c  jmp     short loc_180005AAA
0x180005a9e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005aa3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005aa8  mov     eax, edi
0x180005aaa  mov     rcx, [rbp+0A00h+var_40]
0x180005ab1  xor     rcx, rsp; StackCookie
0x180005ab4  call    __security_check_cookie
0x180005ab9  mov     rbx, [rsp+0B00h+arg_10]
0x180005ac1  add     rsp, 0AD0h
0x180005ac8  pop     r15
0x180005aca  pop     r14
0x180005acc  pop     r13
0x180005ace  pop     r12
0x180005ad0  pop     rdi
0x180005ad1  pop     rsi
0x180005ad2  pop     rbp
0x180005ad3  retn
0x180005ad4  call    __report_rangecheckfailure
```
