# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180008c1c`
- end: `0x180008f5a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008f70`

## callees

- `0x180002218`
- `0x180005368`
- `0x1800056c8`
- `0x18000626c`
- `0x180006f6c`
- `0x180007a88`
- `0x180008c1c`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008dfa`
- `msvcrt!memcpy_s` at `0x180008dfa`
- `KERNEL32!GetModuleHandleW` at `0x180008d99`
- `KERNEL32!GetModuleHandleW` at `0x180008d99`
- `KERNEL32!LeaveCriticalSection` at `0x180008cd8`
- `KERNEL32!LeaveCriticalSection` at `0x180008e6c`
- `KERNEL32!LeaveCriticalSection` at `0x180008eb1`
- `KERNEL32!LeaveCriticalSection` at `0x180008cd8`
- `KERNEL32!LeaveCriticalSection` at `0x180008e6c`
- `KERNEL32!LeaveCriticalSection` at `0x180008eb1`
- `KERNEL32!EnterCriticalSection` at `0x180008cbd`
- `KERNEL32!EnterCriticalSection` at `0x180008da9`
- `KERNEL32!EnterCriticalSection` at `0x180008e47`
- `KERNEL32!EnterCriticalSection` at `0x180008e8c`
- `KERNEL32!EnterCriticalSection` at `0x180008cbd`
- `KERNEL32!EnterCriticalSection` at `0x180008da9`
- `KERNEL32!EnterCriticalSection` at `0x180008e47`
- `KERNEL32!EnterCriticalSection` at `0x180008e8c`
- `KERNEL32!GetModuleFileNameW` at `0x180008d1e`
- `KERNEL32!GetModuleFileNameW` at `0x180008d1e`

## string_xrefs

- `0x180008ee7`: `REGISTRY`

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
0x180008c1c  mov     [rsp-8+arg_10], rbx
0x180008c21  push    rbp
0x180008c22  push    rsi
0x180008c23  push    rdi
0x180008c24  push    r12
0x180008c26  push    r13
0x180008c28  push    r14
0x180008c2a  push    r15
0x180008c2c  lea     rbp, [rsp-9D0h]
0x180008c34  sub     rsp, 0AD0h
0x180008c3b  mov     rax, cs:__security_cookie
0x180008c42  xor     rax, rsp
0x180008c45  mov     [rbp+0A00h+var_40], rax
0x180008c4c  xor     r13d, r13d
0x180008c4f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008c56  xorps   xmm0, xmm0
0x180008c59  mov     [rsp+0B00h+var_AD0], rax
0x180008c5e  xor     eax, eax
0x180008c60  mov     [rsp+0B00h+var_AC8], r13
0x180008c65  mov     r15, rcx
0x180008c68  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180008c6d  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180008c72  mov     [rsp+0B00h+var_AC0], r13
0x180008c77  mov     rbx, r9
0x180008c7a  mov     [rsp+0B00h+var_AB8], r13d
0x180008c7f  mov     r12d, r8d
0x180008c82  mov     [rsp+0B00h+var_A88], r13b
0x180008c87  mov     r14, rdx
0x180008c8a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180008c8f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180008c94  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008c99  mov     edi, eax
0x180008c9b  test    eax, eax
0x180008c9d  js      loc_180008F1E
0x180008ca3  mov     [rsp+0B00h+var_A88], 1
0x180008ca8  test    rbx, rbx
0x180008cab  jz      short loc_180008CEA
0x180008cad  jmp     short loc_180008CE2
0x180008caf  mov     rsi, [rbx+8]
0x180008cb3  test    rsi, rsi
0x180008cb6  jz      short loc_180008CDE
0x180008cb8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008cbd  call    cs:__imp_EnterCriticalSection
0x180008cc3  mov     r8, rsi; unsigned __int16 *
0x180008cc6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180008ccb  mov     rdx, rdi; unsigned __int16 *
0x180008cce  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008cd3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008cd8  call    cs:__imp_LeaveCriticalSection
0x180008cde  add     rbx, 10h
0x180008ce2  mov     rdi, [rbx]
0x180008ce5  test    rdi, rdi
0x180008ce8  jnz     short loc_180008CAF
0x180008cea  mov     rax, [r15]
0x180008ced  lea     rdx, [rsp+0B00h+var_AD0]
0x180008cf2  mov     rcx, r15
0x180008cf5  mov     rax, [rax+28h]
0x180008cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfe  mov     ebx, eax
0x180008d00  test    eax, eax
0x180008d02  js      loc_180008F10
0x180008d08  mov     rbx, cs:hInstance
0x180008d0f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180008d13  mov     edi, 104h
0x180008d18  mov     rcx, rbx; hModule
0x180008d1b  mov     r8d, edi; nSize
0x180008d1e  call    cs:__imp_GetModuleFileNameW
0x180008d24  test    eax, eax
0x180008d26  jnz     short loc_180008D34
0x180008d28  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008d2d  mov     ebx, eax
0x180008d2f  jmp     loc_180008F10
0x180008d34  cmp     eax, edi
0x180008d36  jnz     short loc_180008D42
0x180008d38  mov     ebx, 8007007Ah
0x180008d3d  jmp     loc_180008F10
0x180008d42  lea     rdx, [rbp+0A00h+Filename]
0x180008d46  mov     ecx, r13d
0x180008d49  mov     r9d, 27h ; '''
0x180008d4f  movzx   r8d, word ptr [rdx]
0x180008d53  test    r8w, r8w
0x180008d57  jz      short loc_180008D89
0x180008d59  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180008d62  cmp     r8w, r9w
0x180008d66  jnz     short loc_180008D7B
0x180008d68  cmp     ecx, 206h
0x180008d6e  jnb     short loc_180008D7B
0x180008d70  inc     ecx
0x180008d72  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180008d7b  add     rdx, 2
0x180008d7f  inc     ecx
0x180008d81  cmp     ecx, 207h
0x180008d87  jb      short loc_180008D4F
0x180008d89  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180008d92  test    rbx, rbx
0x180008d95  jz      short loc_180008DBB
0x180008d97  xor     ecx, ecx; lpModuleName
0x180008d99  call    cs:__imp_GetModuleHandleW
0x180008d9f  cmp     rbx, rax
0x180008da2  jz      short loc_180008DBB
0x180008da4  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008da9  call    cs:__imp_EnterCriticalSection
0x180008daf  lea     r8, [rbp+0A00h+Source]
0x180008db6  jmp     loc_180008E54
0x180008dbb  mov     edi, 22h ; '"'
0x180008dc0  lea     rcx, [rbp+0A00h+Source]
0x180008dc7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008dcb  mov     [rbp+0A00h+var_460], di
0x180008dd2  mov     rax, rbx
0x180008dd5  inc     rax
0x180008dd8  cmp     [rcx+rax*2], r13w
0x180008ddd  jnz     short loc_180008DD5
0x180008ddf  inc     eax
0x180008de1  lea     r8, [rbp+0A00h+Source]; Source
0x180008de8  movsxd  r9, eax
0x180008deb  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180008df2  add     r9, r9; SourceSize
0x180008df5  mov     edx, 414h; DestinationSize
0x180008dfa  call    cs:__imp_memcpy_s
0x180008e00  test    eax, eax
0x180008e02  jnz     loc_180008F0B
0x180008e08  lea     rax, [rbp+0A00h+var_460]
0x180008e0f  inc     rbx
0x180008e12  cmp     [rax+rbx*2], r13w
0x180008e17  jnz     short loc_180008E0F
0x180008e19  movsxd  rax, ebx
0x180008e1c  lea     rcx, ds:2[rax*2]
0x180008e24  mov     [rbp+rax*2+0A00h+var_460], di
0x180008e2c  cmp     rcx, 418h
0x180008e33  jnb     loc_180008F54
0x180008e39  mov     [rbp+rcx+0A00h+var_460], r13w
0x180008e42  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008e47  call    cs:__imp_EnterCriticalSection
0x180008e4d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180008e54  lea     rdx, aModule; "Module"
0x180008e5b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180008e60  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008e65  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008e6a  mov     ebx, eax
0x180008e6c  call    cs:__imp_LeaveCriticalSection
0x180008e72  neg     ebx
0x180008e74  mov     edi, 8007000Eh
0x180008e79  sbb     ebx, ebx
0x180008e7b  not     ebx
0x180008e7d  and     ebx, edi
0x180008e7f  test    ebx, ebx
0x180008e81  js      loc_180008F10
0x180008e87  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008e8c  call    cs:__imp_EnterCriticalSection
0x180008e92  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180008e99  lea     rdx, aModuleRaw; "Module_Raw"
0x180008ea0  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180008ea5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180008eaa  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180008eaf  mov     ebx, eax
0x180008eb1  call    cs:__imp_LeaveCriticalSection
0x180008eb7  mov     ecx, ebx
0x180008eb9  neg     ecx
0x180008ebb  sbb     eax, eax
0x180008ebd  not     eax
0x180008ebf  and     eax, edi
0x180008ec1  test    ebx, ebx
0x180008ec3  jz      loc_180008D2D
0x180008ec9  test    r12d, r12d
0x180008ecc  jz      short loc_180008EDD
0x180008ece  test    r14, r14
0x180008ed1  jz      short loc_180008F04
0x180008ed3  mov     [rsp+0B00h+var_AE0], 1
0x180008edb  jmp     short loc_180008EE7
0x180008edd  test    r14, r14
0x180008ee0  jz      short loc_180008F04
0x180008ee2  mov     [rsp+0B00h+var_AE0], r13d; int
0x180008ee7  lea     r9, aRegistry; "REGISTRY"
0x180008eee  mov     r8, r14; unsigned __int16 *
0x180008ef1  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180008ef5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008efa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008eff  jmp     loc_180008D2D
0x180008f04  mov     ebx, 80070057h
0x180008f09  jmp     short loc_180008F10
0x180008f0b  mov     ebx, 80004005h
0x180008f10  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008f15  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008f1a  mov     eax, ebx
0x180008f1c  jmp     short loc_180008F2A
0x180008f1e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180008f23  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008f28  mov     eax, edi
0x180008f2a  mov     rcx, [rbp+0A00h+var_40]
0x180008f31  xor     rcx, rsp; StackCookie
0x180008f34  call    __security_check_cookie
0x180008f39  mov     rbx, [rsp+0B00h+arg_10]
0x180008f41  add     rsp, 0AD0h
0x180008f48  pop     r15
0x180008f4a  pop     r14
0x180008f4c  pop     r13
0x180008f4e  pop     r12
0x180008f50  pop     rdi
0x180008f51  pop     rsi
0x180008f52  pop     rbp
0x180008f53  retn
0x180008f54  call    __report_rangecheckfailure
```
