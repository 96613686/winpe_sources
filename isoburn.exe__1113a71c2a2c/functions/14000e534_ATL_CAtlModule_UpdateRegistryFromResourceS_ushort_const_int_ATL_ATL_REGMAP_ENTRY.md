# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000e534`
- end: `0x14000e877`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000e890`

## callees

- `0x140001fa0`
- `0x1400024e0`
- `0x140002b36`
- `0x14000623c`
- `0x14000c318`
- `0x14000c44c`
- `0x14000cc48`
- `0x14000d708`
- `0x14000e534`
- `0x14000f740`
- `0x140010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000e5d5`
- `KERNEL32!EnterCriticalSection` at `0x14000e6bf`
- `KERNEL32!EnterCriticalSection` at `0x14000e75e`
- `KERNEL32!EnterCriticalSection` at `0x14000e79f`
- `KERNEL32!EnterCriticalSection` at `0x14000e5d5`
- `KERNEL32!EnterCriticalSection` at `0x14000e6bf`
- `KERNEL32!EnterCriticalSection` at `0x14000e75e`
- `KERNEL32!EnterCriticalSection` at `0x14000e79f`
- `KERNEL32!LeaveCriticalSection` at `0x14000e5f0`
- `KERNEL32!LeaveCriticalSection` at `0x14000e783`
- `KERNEL32!LeaveCriticalSection` at `0x14000e7c4`
- `KERNEL32!LeaveCriticalSection` at `0x14000e5f0`
- `KERNEL32!LeaveCriticalSection` at `0x14000e783`
- `KERNEL32!LeaveCriticalSection` at `0x14000e7c4`
- `KERNEL32!GetModuleFileNameW` at `0x14000e636`
- `KERNEL32!GetModuleFileNameW` at `0x14000e636`
- `KERNEL32!GetModuleHandleW` at `0x14000e6af`
- `KERNEL32!GetModuleHandleW` at `0x14000e6af`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e7e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e7e8`

## string_xrefs

- `0x14000e81a`: `REGISTRY`

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
  __int64 v17; // r9
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rcx
  int v24; // ebx
  int v25; // ebx
  void **v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Src[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  v31 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
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
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v27);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_32;
    }
    if ( ModuleFileNameW == 260 )
    {
      v11 = -2147024774;
    }
    else
    {
      v15 = Filename;
      v16 = 0;
      v17 = 39;
      do
      {
        v18 = *v15;
        if ( !*v15 )
          break;
        Src[v16] = v18;
        if ( v18 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Src[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Src[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v20 = -1;
        v34 = 34;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v15, v22, v17) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_33;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        v23 = 2LL * (int)v20 + 2;
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v23, v15, v22, v17);
        *(_WORD *)&v35[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v19 = &v34;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v19 = Src;
      }
      v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", v19);
      LeaveCriticalSection(&CriticalSection);
      v11 = v24 == 0 ? 0x8007000E : 0;
      if ( v11 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v25 == 0 ? 0x8007000E : 0;
        if ( v25 )
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 0);
            goto LABEL_32;
          }
          v11 = -2147024809;
          goto LABEL_33;
        }
LABEL_32:
        v11 = Error;
      }
    }
LABEL_33:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e534  mov     [rsp-8+arg_10], rbx
0x14000e539  push    rbp
0x14000e53a  push    rsi
0x14000e53b  push    rdi
0x14000e53c  push    r12
0x14000e53e  push    r13
0x14000e540  push    r14
0x14000e542  push    r15
0x14000e544  lea     rbp, [rsp-9D0h]
0x14000e54c  sub     rsp, 0AD0h
0x14000e553  mov     rax, cs:__security_cookie
0x14000e55a  xor     rax, rsp
0x14000e55d  mov     [rbp+0A00h+var_40], rax
0x14000e564  xor     r13d, r13d
0x14000e567  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000e56e  xorps   xmm0, xmm0
0x14000e571  mov     [rsp+0B00h+var_AD0], rax
0x14000e576  xor     eax, eax
0x14000e578  mov     [rsp+0B00h+var_AC8], r13
0x14000e57d  mov     r15, rcx
0x14000e580  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x14000e585  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x14000e58a  mov     [rsp+0B00h+var_AC0], r13
0x14000e58f  mov     rbx, r9
0x14000e592  mov     [rsp+0B00h+var_AB8], r13d
0x14000e597  mov     r12d, r8d
0x14000e59a  mov     [rsp+0B00h+var_A88], r13b
0x14000e59f  mov     r14, rdx
0x14000e5a2  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x14000e5a7  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x14000e5ac  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000e5b1  mov     edi, eax
0x14000e5b3  test    eax, eax
0x14000e5b5  js      loc_14000E83B
0x14000e5bb  mov     [rsp+0B00h+var_A88], 1
0x14000e5c0  test    rbx, rbx
0x14000e5c3  jz      short loc_14000E602
0x14000e5c5  jmp     short loc_14000E5FA
0x14000e5c7  mov     rsi, [rbx+8]
0x14000e5cb  test    rsi, rsi
0x14000e5ce  jz      short loc_14000E5F6
0x14000e5d0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e5d5  call    cs:__imp_EnterCriticalSection
0x14000e5db  mov     r8, rsi; unsigned __int16 *
0x14000e5de  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e5e3  mov     rdx, rdi; unsigned __int16 *
0x14000e5e6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e5eb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e5f0  call    cs:__imp_LeaveCriticalSection
0x14000e5f6  add     rbx, 10h
0x14000e5fa  mov     rdi, [rbx]
0x14000e5fd  test    rdi, rdi
0x14000e600  jnz     short loc_14000E5C7
0x14000e602  mov     rax, [r15]
0x14000e605  lea     rdx, [rsp+0B00h+var_AD0]
0x14000e60a  mov     rcx, r15
0x14000e60d  mov     rax, [rax+28h]
0x14000e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e616  mov     ebx, eax
0x14000e618  test    eax, eax
0x14000e61a  js      loc_14000E7DA
0x14000e620  mov     rbx, cs:hModule
0x14000e627  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x14000e62b  mov     edi, 104h
0x14000e630  mov     rcx, rbx; hModule
0x14000e633  mov     r8d, edi; nSize
0x14000e636  call    cs:__imp_GetModuleFileNameW
0x14000e63c  test    eax, eax
0x14000e63e  jnz     short loc_14000E64A
0x14000e640  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000e645  jmp     loc_14000E7D8
0x14000e64a  cmp     eax, edi
0x14000e64c  jnz     short loc_14000E658
0x14000e64e  mov     ebx, 8007007Ah
0x14000e653  jmp     loc_14000E7DA
0x14000e658  lea     rdx, [rbp+0A00h+Filename]
0x14000e65c  mov     ecx, r13d
0x14000e65f  mov     r9d, 27h ; '''
0x14000e665  movzx   r8d, word ptr [rdx]
0x14000e669  test    r8w, r8w
0x14000e66d  jz      short loc_14000E69F
0x14000e66f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x14000e678  cmp     r8w, r9w
0x14000e67c  jnz     short loc_14000E691
0x14000e67e  cmp     ecx, 206h
0x14000e684  jnb     short loc_14000E691
0x14000e686  inc     ecx
0x14000e688  mov     [rbp+rcx*2+0A00h+Src], r9w
0x14000e691  add     rdx, 2
0x14000e695  inc     ecx
0x14000e697  cmp     ecx, 207h
0x14000e69d  jb      short loc_14000E665
0x14000e69f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x14000e6a8  test    rbx, rbx
0x14000e6ab  jz      short loc_14000E6D1
0x14000e6ad  xor     ecx, ecx; lpModuleName
0x14000e6af  call    cs:__imp_GetModuleHandleW
0x14000e6b5  cmp     rbx, rax
0x14000e6b8  jz      short loc_14000E6D1
0x14000e6ba  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e6bf  call    cs:__imp_EnterCriticalSection
0x14000e6c5  lea     r8, [rbp+0A00h+Src]
0x14000e6cc  jmp     loc_14000E76B
0x14000e6d1  mov     edi, 22h ; '"'
0x14000e6d6  lea     rcx, [rbp+0A00h+Src]
0x14000e6dd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000e6e1  mov     [rbp+0A00h+var_460], di
0x14000e6e8  mov     rax, rbx
0x14000e6eb  inc     rax
0x14000e6ee  cmp     [rcx+rax*2], r13w
0x14000e6f3  jnz     short loc_14000E6EB
0x14000e6f5  inc     eax
0x14000e6f7  movsxd  r8, eax
0x14000e6fa  add     r8, r8; Size
0x14000e6fd  jz      short loc_14000E71F
0x14000e6ff  cmp     r8, 414h
0x14000e706  ja      loc_14000E7E8
0x14000e70c  lea     rdx, [rbp+0A00h+Src]; Src
0x14000e713  lea     rcx, [rbp+0A00h+var_45E]; void *
0x14000e71a  call    memcpy_0
0x14000e71f  lea     rax, [rbp+0A00h+var_460]
0x14000e726  inc     rbx
0x14000e729  cmp     [rax+rbx*2], r13w
0x14000e72e  jnz     short loc_14000E726
0x14000e730  movsxd  rax, ebx
0x14000e733  lea     rcx, ds:2[rax*2]
0x14000e73b  mov     [rbp+rax*2+0A00h+var_460], di
0x14000e743  cmp     rcx, 418h
0x14000e74a  jnb     loc_14000E871
0x14000e750  mov     [rbp+rcx+0A00h+var_460], r13w
0x14000e759  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e75e  call    cs:__imp_EnterCriticalSection
0x14000e764  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x14000e76b  lea     rdx, aModule; "Module"
0x14000e772  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e777  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e77c  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e781  mov     ebx, eax
0x14000e783  call    cs:__imp_LeaveCriticalSection
0x14000e789  neg     ebx
0x14000e78b  mov     edi, 8007000Eh
0x14000e790  sbb     ebx, ebx
0x14000e792  not     ebx
0x14000e794  and     ebx, edi
0x14000e796  test    ebx, ebx
0x14000e798  js      short loc_14000E7DA
0x14000e79a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e79f  call    cs:__imp_EnterCriticalSection
0x14000e7a5  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x14000e7ac  lea     rdx, aModuleRaw; "Module_Raw"
0x14000e7b3  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e7b8  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e7bd  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e7c2  mov     ebx, eax
0x14000e7c4  call    cs:__imp_LeaveCriticalSection
0x14000e7ca  mov     ecx, ebx
0x14000e7cc  neg     ecx
0x14000e7ce  sbb     eax, eax
0x14000e7d0  not     eax
0x14000e7d2  and     eax, edi
0x14000e7d4  test    ebx, ebx
0x14000e7d6  jnz     short loc_14000E7FC
0x14000e7d8  mov     ebx, eax
0x14000e7da  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e7df  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000e7e4  mov     eax, ebx
0x14000e7e6  jmp     short loc_14000E847
0x14000e7e8  call    cs:__imp__o__errno
0x14000e7ee  mov     [rax], edi
0x14000e7f0  call    _invalid_parameter_noinfo
0x14000e7f5  mov     ebx, 80004005h
0x14000e7fa  jmp     short loc_14000E7DA
0x14000e7fc  test    r12d, r12d
0x14000e7ff  jz      short loc_14000E810
0x14000e801  test    r14, r14
0x14000e804  jz      short loc_14000E834
0x14000e806  mov     [rsp+0B00h+var_AE0], 1
0x14000e80e  jmp     short loc_14000E81A
0x14000e810  test    r14, r14
0x14000e813  jz      short loc_14000E834
0x14000e815  mov     [rsp+0B00h+var_AE0], r13d; int
0x14000e81a  lea     r9, aRegistry; "REGISTRY"
0x14000e821  mov     r8, r14; unsigned __int16 *
0x14000e824  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x14000e828  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e82d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x14000e832  jmp     short loc_14000E7D8
0x14000e834  mov     ebx, 80070057h
0x14000e839  jmp     short loc_14000E7DA
0x14000e83b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e840  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000e845  mov     eax, edi
0x14000e847  mov     rcx, [rbp+0A00h+var_40]
0x14000e84e  xor     rcx, rsp; StackCookie
0x14000e851  call    __security_check_cookie
0x14000e856  mov     rbx, [rsp+0B00h+arg_10]
0x14000e85e  add     rsp, 0AD0h
0x14000e865  pop     r15
0x14000e867  pop     r14
0x14000e869  pop     r13
0x14000e86b  pop     r12
0x14000e86d  pop     rdi
0x14000e86e  pop     rsi
0x14000e86f  pop     rbp
0x14000e870  retn
0x14000e871  call    __report_rangecheckfailure
```
