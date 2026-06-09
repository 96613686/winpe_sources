# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000ffec`
- end: `0x18001030c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010660`

## callees

- `0x1800024a0`
- `0x180002cb0`
- `0x1800032b2`
- `0x18000b5c8`
- `0x18000ba7c`
- `0x18000c3f8`
- `0x18000de54`
- `0x18000edc8`
- `0x18000ffec`
- `0x1800156c8`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010291`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010291`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800100f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800100f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010164`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010164`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001008d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001020a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001024b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001008d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001020a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001024b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001022f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001026d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001022f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001026d`

## string_xrefs

- `0x1800102b6`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const wchar_t *v9; // rsi
  const wchar_t *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  wchar_t v18; // r8
  wchar_t *v19; // r8
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
  wchar_t Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v8 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const wchar_t **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const wchar_t *)*((_QWORD *)a4 + 1);
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
        v34 = 34;
        v20 = -1;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v15, v22) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_34;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
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
                    (const WCHAR *)&v27,
                    Filename,
                    (const wchar_t *)a2,
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
0x18000ffec  mov     [rsp-8+arg_10], rbx
0x18000fff1  push    rbp
0x18000fff2  push    rsi
0x18000fff3  push    rdi
0x18000fff4  push    r12
0x18000fff6  push    r13
0x18000fff8  push    r14
0x18000fffa  push    r15
0x18000fffc  lea     rbp, [rsp-9D0h]
0x180010004  sub     rsp, 0AD0h
0x18001000b  mov     rax, cs:__security_cookie
0x180010012  xor     rax, rsp
0x180010015  mov     [rbp+0A00h+var_40], rax
0x18001001c  mov     rbx, r9
0x18001001f  mov     r15d, r8d
0x180010022  mov     r12d, edx
0x180010025  mov     r14, rcx
0x180010028  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001002f  mov     [rsp+0B00h+var_AD0], rax
0x180010034  xor     r13d, r13d
0x180010037  mov     [rsp+0B00h+var_AC8], r13
0x18001003c  mov     [rsp+0B00h+var_AC0], r13
0x180010041  mov     [rsp+0B00h+var_AB8], r13d
0x180010046  xorps   xmm0, xmm0
0x180010049  xor     eax, eax
0x18001004b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180010050  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180010055  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18001005a  mov     [rsp+0B00h+var_A88], r13b
0x18001005f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180010064  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180010069  mov     edi, eax
0x18001006b  test    eax, eax
0x18001006d  js      loc_1800102D0
0x180010073  mov     [rsp+0B00h+var_A88], 1
0x180010078  test    rbx, rbx
0x18001007b  jz      short loc_1800100BA
0x18001007d  jmp     short loc_1800100B2
0x18001007f  mov     rsi, [rbx+8]
0x180010083  test    rsi, rsi
0x180010086  jz      short loc_1800100AE
0x180010088  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001008d  call    cs:__imp_EnterCriticalSection
0x180010093  mov     r8, rsi; wchar_t *
0x180010096  mov     rdx, rdi; wchar_t *
0x180010099  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18001009e  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x1800100a3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800100a8  call    cs:__imp_LeaveCriticalSection
0x1800100ae  add     rbx, 10h
0x1800100b2  mov     rdi, [rbx]
0x1800100b5  test    rdi, rdi
0x1800100b8  jnz     short loc_18001007F
0x1800100ba  mov     rax, [r14]
0x1800100bd  lea     rdx, [rsp+0B00h+var_AD0]
0x1800100c2  mov     rcx, r14
0x1800100c5  mov     rax, [rax+28h]
0x1800100c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100ce  mov     ebx, eax
0x1800100d0  test    eax, eax
0x1800100d2  js      loc_180010283
0x1800100d8  mov     rbx, cs:hModule
0x1800100df  mov     edi, 104h
0x1800100e4  mov     r8d, edi; nSize
0x1800100e7  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800100ee  mov     rcx, rbx; hModule
0x1800100f1  call    cs:__imp_GetModuleFileNameW
0x1800100f7  test    eax, eax
0x1800100f9  jnz     short loc_180010105
0x1800100fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010100  jmp     loc_180010281
0x180010105  cmp     eax, edi
0x180010107  jnz     short loc_180010113
0x180010109  mov     ebx, 8007007Ah
0x18001010e  jmp     loc_180010283
0x180010113  lea     rdx, [rbp+0A00h+Filename]
0x18001011a  mov     ecx, r13d
0x18001011d  mov     r9d, 27h ; '''
0x180010123  movzx   r8d, word ptr [rdx]
0x180010127  test    r8w, r8w
0x18001012b  jz      short loc_180010157
0x18001012d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180010133  cmp     r8w, r9w
0x180010137  jnz     short loc_180010149
0x180010139  cmp     ecx, 206h
0x18001013f  jnb     short loc_180010149
0x180010141  inc     ecx
0x180010143  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180010149  add     rdx, 2
0x18001014d  inc     ecx
0x18001014f  cmp     ecx, 207h
0x180010155  jb      short loc_180010123
0x180010157  mov     [rbp+rcx*2+0A00h+Src], r13w
0x18001015d  test    rbx, rbx
0x180010160  jz      short loc_180010183
0x180010162  xor     ecx, ecx; lpModuleName
0x180010164  call    cs:__imp_GetModuleHandleW
0x18001016a  cmp     rbx, rax
0x18001016d  jz      short loc_180010183
0x18001016f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180010174  call    cs:__imp_EnterCriticalSection
0x18001017a  lea     r8, [rbp+0A00h+Src]
0x18001017e  jmp     loc_180010217
0x180010183  mov     edi, 22h ; '"'
0x180010188  mov     [rbp+0A00h+var_460], di
0x18001018f  lea     rcx, [rbp+0A00h+Src]
0x180010193  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010197  mov     rax, rbx
0x18001019a  inc     rax
0x18001019d  cmp     [rcx+rax*2], r13w
0x1800101a2  jnz     short loc_18001019A
0x1800101a4  inc     eax
0x1800101a6  movsxd  r8, eax
0x1800101a9  add     r8, r8; Size
0x1800101ac  jz      short loc_1800101CB
0x1800101ae  cmp     r8, 414h
0x1800101b5  ja      loc_180010291
0x1800101bb  lea     rdx, [rbp+0A00h+Src]; Src
0x1800101bf  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800101c6  call    memcpy_0
0x1800101cb  lea     rax, [rbp+0A00h+var_460]
0x1800101d2  inc     rbx
0x1800101d5  cmp     [rax+rbx*2], r13w
0x1800101da  jnz     short loc_1800101D2
0x1800101dc  movsxd  rax, ebx
0x1800101df  mov     [rbp+rax*2+0A00h+var_460], di
0x1800101e7  lea     rcx, ds:2[rax*2]
0x1800101ef  cmp     rcx, 418h
0x1800101f6  jnb     loc_180010306
0x1800101fc  mov     [rbp+rcx+0A00h+var_460], r13w
0x180010205  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001020a  call    cs:__imp_EnterCriticalSection
0x180010210  lea     r8, [rbp+0A00h+var_460]; wchar_t *
0x180010217  lea     rdx, aModule; "Module"
0x18001021e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180010223  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180010228  mov     ebx, eax
0x18001022a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001022f  call    cs:__imp_LeaveCriticalSection
0x180010235  neg     ebx
0x180010237  sbb     ebx, ebx
0x180010239  mov     edi, 8007000Eh
0x18001023e  not     ebx
0x180010240  and     ebx, edi
0x180010242  test    ebx, ebx
0x180010244  js      short loc_180010283
0x180010246  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001024b  call    cs:__imp_EnterCriticalSection
0x180010251  lea     r8, [rbp+0A00h+Src]; wchar_t *
0x180010255  lea     rdx, aModuleRaw; "Module_Raw"
0x18001025c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180010261  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180010266  mov     ebx, eax
0x180010268  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18001026d  call    cs:__imp_LeaveCriticalSection
0x180010273  mov     ecx, ebx
0x180010275  neg     ecx
0x180010277  sbb     eax, eax
0x180010279  not     eax
0x18001027b  and     eax, edi
0x18001027d  test    ebx, ebx
0x18001027f  jnz     short loc_1800102A5
0x180010281  mov     ebx, eax
0x180010283  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180010288  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001028d  mov     eax, ebx
0x18001028f  jmp     short loc_1800102DC
0x180010291  call    cs:__imp__o__errno
0x180010297  mov     [rax], edi
0x180010299  call    _invalid_parameter_noinfo
0x18001029e  mov     ebx, 80004005h
0x1800102a3  jmp     short loc_180010283
0x1800102a5  mov     eax, r13d
0x1800102a8  test    r15d, r15d
0x1800102ab  setnz   al
0x1800102ae  movzx   r8d, r12w; wchar_t *
0x1800102b2  mov     [rsp+0B00h+var_AE0], eax; int
0x1800102b6  lea     r9, aRegistry; "REGISTRY"
0x1800102bd  lea     rdx, [rbp+0A00h+Filename]; wchar_t *
0x1800102c4  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800102c9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x1800102ce  jmp     short loc_180010281
0x1800102d0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800102d5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800102da  mov     eax, edi
0x1800102dc  mov     rcx, [rbp+0A00h+var_40]
0x1800102e3  xor     rcx, rsp; StackCookie
0x1800102e6  call    __security_check_cookie
0x1800102eb  mov     rbx, [rsp+0B00h+arg_10]
0x1800102f3  add     rsp, 0AD0h
0x1800102fa  pop     r15
0x1800102fc  pop     r14
0x1800102fe  pop     r13
0x180010300  pop     r12
0x180010302  pop     rdi
0x180010303  pop     rsi
0x180010304  pop     rbp
0x180010305  retn
0x180010306  call    __report_rangecheckfailure
```
