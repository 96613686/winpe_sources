# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000e20c`
- end: `0x14000e52c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000e880`

## callees

- `0x140001fa0`
- `0x1400024e0`
- `0x140002b36`
- `0x14000623c`
- `0x14000c318`
- `0x14000c44c`
- `0x14000cc48`
- `0x14000d708`
- `0x14000e20c`
- `0x14000f740`
- `0x140010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000e2ad`
- `KERNEL32!EnterCriticalSection` at `0x14000e394`
- `KERNEL32!EnterCriticalSection` at `0x14000e42a`
- `KERNEL32!EnterCriticalSection` at `0x14000e46b`
- `KERNEL32!EnterCriticalSection` at `0x14000e2ad`
- `KERNEL32!EnterCriticalSection` at `0x14000e394`
- `KERNEL32!EnterCriticalSection` at `0x14000e42a`
- `KERNEL32!EnterCriticalSection` at `0x14000e46b`
- `KERNEL32!LeaveCriticalSection` at `0x14000e2c8`
- `KERNEL32!LeaveCriticalSection` at `0x14000e44f`
- `KERNEL32!LeaveCriticalSection` at `0x14000e48d`
- `KERNEL32!LeaveCriticalSection` at `0x14000e2c8`
- `KERNEL32!LeaveCriticalSection` at `0x14000e44f`
- `KERNEL32!LeaveCriticalSection` at `0x14000e48d`
- `KERNEL32!GetModuleFileNameW` at `0x14000e311`
- `KERNEL32!GetModuleFileNameW` at `0x14000e311`
- `KERNEL32!GetModuleHandleW` at `0x14000e384`
- `KERNEL32!GetModuleHandleW` at `0x14000e384`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e4b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000e4b1`

## string_xrefs

- `0x14000e4cf`: `REGISTRY`

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
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v28[0] = 0;
  v28[1] = 0;
  v27 = &ATL::CRegObject::`vftable';
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
      goto LABEL_34;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_33:
      v11 = Error;
      goto LABEL_34;
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
            goto LABEL_34;
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
          Error = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v27,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    a3 != 0);
        goto LABEL_33;
      }
    }
LABEL_34:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e20c  mov     [rsp-8+arg_10], rbx
0x14000e211  push    rbp
0x14000e212  push    rsi
0x14000e213  push    rdi
0x14000e214  push    r12
0x14000e216  push    r13
0x14000e218  push    r14
0x14000e21a  push    r15
0x14000e21c  lea     rbp, [rsp-9D0h]
0x14000e224  sub     rsp, 0AD0h
0x14000e22b  mov     rax, cs:__security_cookie
0x14000e232  xor     rax, rsp
0x14000e235  mov     [rbp+0A00h+var_40], rax
0x14000e23c  xor     r13d, r13d
0x14000e23f  mov     r12d, edx
0x14000e242  xorps   xmm0, xmm0
0x14000e245  mov     [rsp+0B00h+var_AC8], r13
0x14000e24a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000e251  mov     [rsp+0B00h+var_AC0], r13
0x14000e256  mov     [rsp+0B00h+var_AD0], rax
0x14000e25b  mov     r14, rcx
0x14000e25e  xor     eax, eax
0x14000e260  mov     [rsp+0B00h+var_AB8], r13d
0x14000e265  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x14000e26a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x14000e26f  mov     rbx, r9
0x14000e272  mov     [rsp+0B00h+var_A88], r13b
0x14000e277  mov     r15d, r8d
0x14000e27a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x14000e27f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x14000e284  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14000e289  mov     edi, eax
0x14000e28b  test    eax, eax
0x14000e28d  js      loc_14000E4F0
0x14000e293  mov     [rsp+0B00h+var_A88], 1
0x14000e298  test    rbx, rbx
0x14000e29b  jz      short loc_14000E2DA
0x14000e29d  jmp     short loc_14000E2D2
0x14000e29f  mov     rsi, [rbx+8]
0x14000e2a3  test    rsi, rsi
0x14000e2a6  jz      short loc_14000E2CE
0x14000e2a8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e2ad  call    cs:__imp_EnterCriticalSection
0x14000e2b3  mov     r8, rsi; unsigned __int16 *
0x14000e2b6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e2bb  mov     rdx, rdi; unsigned __int16 *
0x14000e2be  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e2c3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e2c8  call    cs:__imp_LeaveCriticalSection
0x14000e2ce  add     rbx, 10h
0x14000e2d2  mov     rdi, [rbx]
0x14000e2d5  test    rdi, rdi
0x14000e2d8  jnz     short loc_14000E29F
0x14000e2da  mov     rax, [r14]
0x14000e2dd  lea     rdx, [rsp+0B00h+var_AD0]
0x14000e2e2  mov     rcx, r14
0x14000e2e5  mov     rax, [rax+28h]
0x14000e2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e2ee  mov     ebx, eax
0x14000e2f0  test    eax, eax
0x14000e2f2  js      loc_14000E4A3
0x14000e2f8  mov     rbx, cs:hModule
0x14000e2ff  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x14000e306  mov     edi, 104h
0x14000e30b  mov     rcx, rbx; hModule
0x14000e30e  mov     r8d, edi; nSize
0x14000e311  call    cs:__imp_GetModuleFileNameW
0x14000e317  test    eax, eax
0x14000e319  jnz     short loc_14000E325
0x14000e31b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000e320  jmp     loc_14000E4A1
0x14000e325  cmp     eax, edi
0x14000e327  jnz     short loc_14000E333
0x14000e329  mov     ebx, 8007007Ah
0x14000e32e  jmp     loc_14000E4A3
0x14000e333  lea     rdx, [rbp+0A00h+Filename]
0x14000e33a  mov     ecx, r13d
0x14000e33d  mov     r9d, 27h ; '''
0x14000e343  movzx   r8d, word ptr [rdx]
0x14000e347  test    r8w, r8w
0x14000e34b  jz      short loc_14000E377
0x14000e34d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x14000e353  cmp     r8w, r9w
0x14000e357  jnz     short loc_14000E369
0x14000e359  cmp     ecx, 206h
0x14000e35f  jnb     short loc_14000E369
0x14000e361  inc     ecx
0x14000e363  mov     [rbp+rcx*2+0A00h+Src], r9w
0x14000e369  add     rdx, 2
0x14000e36d  inc     ecx
0x14000e36f  cmp     ecx, 207h
0x14000e375  jb      short loc_14000E343
0x14000e377  mov     [rbp+rcx*2+0A00h+Src], r13w
0x14000e37d  test    rbx, rbx
0x14000e380  jz      short loc_14000E3A3
0x14000e382  xor     ecx, ecx; lpModuleName
0x14000e384  call    cs:__imp_GetModuleHandleW
0x14000e38a  cmp     rbx, rax
0x14000e38d  jz      short loc_14000E3A3
0x14000e38f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e394  call    cs:__imp_EnterCriticalSection
0x14000e39a  lea     r8, [rbp+0A00h+Src]
0x14000e39e  jmp     loc_14000E437
0x14000e3a3  mov     edi, 22h ; '"'
0x14000e3a8  lea     rcx, [rbp+0A00h+Src]
0x14000e3ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000e3b0  mov     [rbp+0A00h+var_460], di
0x14000e3b7  mov     rax, rbx
0x14000e3ba  inc     rax
0x14000e3bd  cmp     [rcx+rax*2], r13w
0x14000e3c2  jnz     short loc_14000E3BA
0x14000e3c4  inc     eax
0x14000e3c6  movsxd  r8, eax
0x14000e3c9  add     r8, r8; Size
0x14000e3cc  jz      short loc_14000E3EB
0x14000e3ce  cmp     r8, 414h
0x14000e3d5  ja      loc_14000E4B1
0x14000e3db  lea     rdx, [rbp+0A00h+Src]; Src
0x14000e3df  lea     rcx, [rbp+0A00h+var_45E]; void *
0x14000e3e6  call    memcpy_0
0x14000e3eb  lea     rax, [rbp+0A00h+var_460]
0x14000e3f2  inc     rbx
0x14000e3f5  cmp     [rax+rbx*2], r13w
0x14000e3fa  jnz     short loc_14000E3F2
0x14000e3fc  movsxd  rax, ebx
0x14000e3ff  lea     rcx, ds:2[rax*2]
0x14000e407  mov     [rbp+rax*2+0A00h+var_460], di
0x14000e40f  cmp     rcx, 418h
0x14000e416  jnb     loc_14000E526
0x14000e41c  mov     [rbp+rcx+0A00h+var_460], r13w
0x14000e425  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e42a  call    cs:__imp_EnterCriticalSection
0x14000e430  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x14000e437  lea     rdx, aModule; "Module"
0x14000e43e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e443  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e448  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e44d  mov     ebx, eax
0x14000e44f  call    cs:__imp_LeaveCriticalSection
0x14000e455  neg     ebx
0x14000e457  mov     edi, 8007000Eh
0x14000e45c  sbb     ebx, ebx
0x14000e45e  not     ebx
0x14000e460  and     ebx, edi
0x14000e462  test    ebx, ebx
0x14000e464  js      short loc_14000E4A3
0x14000e466  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e46b  call    cs:__imp_EnterCriticalSection
0x14000e471  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x14000e475  lea     rdx, aModuleRaw; "Module_Raw"
0x14000e47c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000e481  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000e486  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000e48b  mov     ebx, eax
0x14000e48d  call    cs:__imp_LeaveCriticalSection
0x14000e493  mov     ecx, ebx
0x14000e495  neg     ecx
0x14000e497  sbb     eax, eax
0x14000e499  not     eax
0x14000e49b  and     eax, edi
0x14000e49d  test    ebx, ebx
0x14000e49f  jnz     short loc_14000E4C5
0x14000e4a1  mov     ebx, eax
0x14000e4a3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e4a8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000e4ad  mov     eax, ebx
0x14000e4af  jmp     short loc_14000E4FC
0x14000e4b1  call    cs:__imp__o__errno
0x14000e4b7  mov     [rax], edi
0x14000e4b9  call    _invalid_parameter_noinfo
0x14000e4be  mov     ebx, 80004005h
0x14000e4c3  jmp     short loc_14000E4A3
0x14000e4c5  mov     eax, r13d
0x14000e4c8  movzx   r8d, r12w; unsigned __int16 *
0x14000e4cc  test    r15d, r15d
0x14000e4cf  lea     r9, aRegistry; "REGISTRY"
0x14000e4d6  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x14000e4dd  setnz   al
0x14000e4e0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e4e5  mov     [rsp+0B00h+var_AE0], eax; int
0x14000e4e9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x14000e4ee  jmp     short loc_14000E4A1
0x14000e4f0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000e4f5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000e4fa  mov     eax, edi
0x14000e4fc  mov     rcx, [rbp+0A00h+var_40]
0x14000e503  xor     rcx, rsp; StackCookie
0x14000e506  call    __security_check_cookie
0x14000e50b  mov     rbx, [rsp+0B00h+arg_10]
0x14000e513  add     rsp, 0AD0h
0x14000e51a  pop     r15
0x14000e51c  pop     r14
0x14000e51e  pop     r13
0x14000e520  pop     r12
0x14000e522  pop     rdi
0x14000e523  pop     rsi
0x14000e524  pop     rbp
0x14000e525  retn
0x14000e526  call    __report_rangecheckfailure
```
