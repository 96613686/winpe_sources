# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000aacc`
- end: `0x18000ae0a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ae20`

## callees

- `0x180001a58`
- `0x180003018`
- `0x180003ff0`
- `0x180004a54`
- `0x180006664`
- `0x180008c0c`
- `0x18000aacc`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000acaa`
- `msvcrt!memcpy_s` at `0x18000acaa`
- `KERNEL32!EnterCriticalSection` at `0x18000ab6d`
- `KERNEL32!EnterCriticalSection` at `0x18000ac59`
- `KERNEL32!EnterCriticalSection` at `0x18000acf7`
- `KERNEL32!EnterCriticalSection` at `0x18000ad3c`
- `KERNEL32!EnterCriticalSection` at `0x18000ab6d`
- `KERNEL32!EnterCriticalSection` at `0x18000ac59`
- `KERNEL32!EnterCriticalSection` at `0x18000acf7`
- `KERNEL32!EnterCriticalSection` at `0x18000ad3c`
- `KERNEL32!GetModuleFileNameW` at `0x18000abce`
- `KERNEL32!GetModuleFileNameW` at `0x18000abce`
- `KERNEL32!LeaveCriticalSection` at `0x18000ab88`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad1c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad61`
- `KERNEL32!LeaveCriticalSection` at `0x18000ab88`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad1c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad61`
- `KERNEL32!GetModuleHandleW` at `0x18000ac49`
- `KERNEL32!GetModuleHandleW` at `0x18000ac49`

## string_xrefs

- `0x18000ad97`: `REGISTRY`

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
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
0x18000aacc  mov     [rsp-8+arg_10], rbx
0x18000aad1  push    rbp
0x18000aad2  push    rsi
0x18000aad3  push    rdi
0x18000aad4  push    r12
0x18000aad6  push    r13
0x18000aad8  push    r14
0x18000aada  push    r15
0x18000aadc  lea     rbp, [rsp-9D0h]
0x18000aae4  sub     rsp, 0AD0h
0x18000aaeb  mov     rax, cs:__security_cookie
0x18000aaf2  xor     rax, rsp
0x18000aaf5  mov     [rbp+0A00h+var_40], rax
0x18000aafc  xor     r13d, r13d
0x18000aaff  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000ab06  xorps   xmm0, xmm0
0x18000ab09  mov     [rsp+0B00h+var_AD0], rax
0x18000ab0e  xor     eax, eax
0x18000ab10  mov     [rsp+0B00h+var_AC8], r13
0x18000ab15  mov     r15, rcx
0x18000ab18  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000ab1d  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000ab22  mov     [rsp+0B00h+var_AC0], r13
0x18000ab27  mov     rbx, r9
0x18000ab2a  mov     [rsp+0B00h+var_AB8], r13d
0x18000ab2f  mov     r12d, r8d
0x18000ab32  mov     [rsp+0B00h+var_A88], r13b
0x18000ab37  mov     r14, rdx
0x18000ab3a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000ab3f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000ab44  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ab49  mov     edi, eax
0x18000ab4b  test    eax, eax
0x18000ab4d  js      loc_18000ADCE
0x18000ab53  mov     [rsp+0B00h+var_A88], 1
0x18000ab58  test    rbx, rbx
0x18000ab5b  jz      short loc_18000AB9A
0x18000ab5d  jmp     short loc_18000AB92
0x18000ab5f  mov     rsi, [rbx+8]
0x18000ab63  test    rsi, rsi
0x18000ab66  jz      short loc_18000AB8E
0x18000ab68  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ab6d  call    cs:__imp_EnterCriticalSection
0x18000ab73  mov     r8, rsi; unsigned __int16 *
0x18000ab76  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000ab7b  mov     rdx, rdi; unsigned __int16 *
0x18000ab7e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000ab83  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ab88  call    cs:__imp_LeaveCriticalSection
0x18000ab8e  add     rbx, 10h
0x18000ab92  mov     rdi, [rbx]
0x18000ab95  test    rdi, rdi
0x18000ab98  jnz     short loc_18000AB5F
0x18000ab9a  mov     rax, [r15]
0x18000ab9d  lea     rdx, [rsp+0B00h+var_AD0]
0x18000aba2  mov     rcx, r15
0x18000aba5  mov     rax, [rax+28h]
0x18000aba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abae  mov     ebx, eax
0x18000abb0  test    eax, eax
0x18000abb2  js      loc_18000ADC0
0x18000abb8  mov     rbx, cs:hInstance
0x18000abbf  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000abc3  mov     edi, 104h
0x18000abc8  mov     rcx, rbx; hModule
0x18000abcb  mov     r8d, edi; nSize
0x18000abce  call    cs:__imp_GetModuleFileNameW
0x18000abd4  test    eax, eax
0x18000abd6  jnz     short loc_18000ABE4
0x18000abd8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000abdd  mov     ebx, eax
0x18000abdf  jmp     loc_18000ADC0
0x18000abe4  cmp     eax, edi
0x18000abe6  jnz     short loc_18000ABF2
0x18000abe8  mov     ebx, 8007007Ah
0x18000abed  jmp     loc_18000ADC0
0x18000abf2  lea     rdx, [rbp+0A00h+Filename]
0x18000abf6  mov     ecx, r13d
0x18000abf9  mov     r9d, 27h ; '''
0x18000abff  movzx   r8d, word ptr [rdx]
0x18000ac03  test    r8w, r8w
0x18000ac07  jz      short loc_18000AC39
0x18000ac09  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000ac12  cmp     r8w, r9w
0x18000ac16  jnz     short loc_18000AC2B
0x18000ac18  cmp     ecx, 206h
0x18000ac1e  jnb     short loc_18000AC2B
0x18000ac20  inc     ecx
0x18000ac22  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000ac2b  add     rdx, 2
0x18000ac2f  inc     ecx
0x18000ac31  cmp     ecx, 207h
0x18000ac37  jb      short loc_18000ABFF
0x18000ac39  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000ac42  test    rbx, rbx
0x18000ac45  jz      short loc_18000AC6B
0x18000ac47  xor     ecx, ecx; lpModuleName
0x18000ac49  call    cs:__imp_GetModuleHandleW
0x18000ac4f  cmp     rbx, rax
0x18000ac52  jz      short loc_18000AC6B
0x18000ac54  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ac59  call    cs:__imp_EnterCriticalSection
0x18000ac5f  lea     r8, [rbp+0A00h+Source]
0x18000ac66  jmp     loc_18000AD04
0x18000ac6b  mov     edi, 22h ; '"'
0x18000ac70  lea     rcx, [rbp+0A00h+Source]
0x18000ac77  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ac7b  mov     [rbp+0A00h+var_460], di
0x18000ac82  mov     rax, rbx
0x18000ac85  inc     rax
0x18000ac88  cmp     [rcx+rax*2], r13w
0x18000ac8d  jnz     short loc_18000AC85
0x18000ac8f  inc     eax
0x18000ac91  lea     r8, [rbp+0A00h+Source]; Source
0x18000ac98  movsxd  r9, eax
0x18000ac9b  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000aca2  add     r9, r9; SourceSize
0x18000aca5  mov     edx, 414h; DestinationSize
0x18000acaa  call    cs:__imp_memcpy_s
0x18000acb0  test    eax, eax
0x18000acb2  jnz     loc_18000ADBB
0x18000acb8  lea     rax, [rbp+0A00h+var_460]
0x18000acbf  inc     rbx
0x18000acc2  cmp     [rax+rbx*2], r13w
0x18000acc7  jnz     short loc_18000ACBF
0x18000acc9  movsxd  rax, ebx
0x18000accc  lea     rcx, ds:2[rax*2]
0x18000acd4  mov     [rbp+rax*2+0A00h+var_460], di
0x18000acdc  cmp     rcx, 418h
0x18000ace3  jnb     loc_18000AE04
0x18000ace9  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000acf2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000acf7  call    cs:__imp_EnterCriticalSection
0x18000acfd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000ad04  lea     rdx, aModule; "Module"
0x18000ad0b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000ad10  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000ad15  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ad1a  mov     ebx, eax
0x18000ad1c  call    cs:__imp_LeaveCriticalSection
0x18000ad22  neg     ebx
0x18000ad24  mov     edi, 8007000Eh
0x18000ad29  sbb     ebx, ebx
0x18000ad2b  not     ebx
0x18000ad2d  and     ebx, edi
0x18000ad2f  test    ebx, ebx
0x18000ad31  js      loc_18000ADC0
0x18000ad37  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ad3c  call    cs:__imp_EnterCriticalSection
0x18000ad42  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000ad49  lea     rdx, aModuleRaw; "Module_Raw"
0x18000ad50  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000ad55  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000ad5a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000ad5f  mov     ebx, eax
0x18000ad61  call    cs:__imp_LeaveCriticalSection
0x18000ad67  mov     ecx, ebx
0x18000ad69  neg     ecx
0x18000ad6b  sbb     eax, eax
0x18000ad6d  not     eax
0x18000ad6f  and     eax, edi
0x18000ad71  test    ebx, ebx
0x18000ad73  jz      loc_18000ABDD
0x18000ad79  test    r12d, r12d
0x18000ad7c  jz      short loc_18000AD8D
0x18000ad7e  test    r14, r14
0x18000ad81  jz      short loc_18000ADB4
0x18000ad83  mov     [rsp+0B00h+var_AE0], 1
0x18000ad8b  jmp     short loc_18000AD97
0x18000ad8d  test    r14, r14
0x18000ad90  jz      short loc_18000ADB4
0x18000ad92  mov     [rsp+0B00h+var_AE0], r13d; int
0x18000ad97  lea     r9, aRegistry; "REGISTRY"
0x18000ad9e  mov     r8, r14; unsigned __int16 *
0x18000ada1  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000ada5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000adaa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000adaf  jmp     loc_18000ABDD
0x18000adb4  mov     ebx, 80070057h
0x18000adb9  jmp     short loc_18000ADC0
0x18000adbb  mov     ebx, 80004005h
0x18000adc0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000adc5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000adca  mov     eax, ebx
0x18000adcc  jmp     short loc_18000ADDA
0x18000adce  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000add3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000add8  mov     eax, edi
0x18000adda  mov     rcx, [rbp+0A00h+var_40]
0x18000ade1  xor     rcx, rsp; StackCookie
0x18000ade4  call    __security_check_cookie
0x18000ade9  mov     rbx, [rsp+0B00h+arg_10]
0x18000adf1  add     rsp, 0AD0h
0x18000adf8  pop     r15
0x18000adfa  pop     r14
0x18000adfc  pop     r13
0x18000adfe  pop     r12
0x18000ae00  pop     rdi
0x18000ae01  pop     rsi
0x18000ae02  pop     rbp
0x18000ae03  retn
0x18000ae04  call    __report_rangecheckfailure
```
