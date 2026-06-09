# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006164`
- end: `0x180006412`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `686`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006130`
- `0x180006150`

## callees

- `0x180001b08`
- `0x1800022a0`
- `0x1800028fc`
- `0x180003130`
- `0x180003414`
- `0x180005488`
- `0x180006164`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800062ec`
- `msvcrt!memcpy_s` at `0x1800062ec`
- `KERNEL32!GetModuleFileNameW` at `0x180006221`
- `KERNEL32!GetModuleFileNameW` at `0x180006221`
- `KERNEL32!GetModuleHandleW` at `0x180006294`
- `KERNEL32!GetModuleHandleW` at `0x180006294`
- `KERNEL32!EnterCriticalSection` at `0x1800062a4`
- `KERNEL32!EnterCriticalSection` at `0x180006339`
- `KERNEL32!EnterCriticalSection` at `0x18000637a`
- `KERNEL32!EnterCriticalSection` at `0x1800062a4`
- `KERNEL32!EnterCriticalSection` at `0x180006339`
- `KERNEL32!EnterCriticalSection` at `0x18000637a`
- `KERNEL32!LeaveCriticalSection` at `0x18000635e`
- `KERNEL32!LeaveCriticalSection` at `0x18000639c`
- `KERNEL32!LeaveCriticalSection` at `0x18000635e`
- `KERNEL32!LeaveCriticalSection` at `0x18000639c`

## string_xrefs

- `0x1800063c0`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v6; // rdi
  signed int v7; // ebx
  HMODULE v8; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v11; // rdx
  __int64 v12; // rcx
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // ebx
  int v19; // ebx
  void **v21; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v22[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v25; // [rsp+78h] [rbp-88h]
  unsigned __int16 Source[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v28; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v6 = ATL::_pAtlModule;
  v21 = &ATL::CRegObject::`vftable';
  v22[0] = 0;
  v22[1] = 0;
  v23 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v25 = 0;
  v7 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v7 >= 0 )
  {
    v25 = 1;
    v7 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v6 + 40LL))(v6, &v21);
    if ( v7 >= 0 )
    {
      v8 = hInstance;
      ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
      if ( !ModuleFileNameW )
      {
        Error = ATL::AtlHresultFromLastError();
LABEL_25:
        v7 = Error;
        goto LABEL_27;
      }
      if ( ModuleFileNameW == 260 )
      {
        v7 = -2147024774;
      }
      else
      {
        v11 = Filename;
        v12 = 0;
        do
        {
          v13 = *v11;
          if ( !*v11 )
            break;
          Source[v12] = v13;
          if ( v13 == 39 && (unsigned int)v12 < 0x206 )
          {
            LODWORD(v12) = v12 + 1;
            Source[(unsigned int)v12] = 39;
          }
          ++v11;
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < 0x207 );
        Source[v12] = 0;
        if ( !v8 || v8 == GetModuleHandleW(0) )
        {
          v28 = 34;
          v15 = -1;
          v16 = -1;
          do
            ++v16;
          while ( Source[v16] );
          if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v16 + 1)) )
          {
            v7 = -2147467259;
            goto LABEL_27;
          }
          do
            ++v15;
          while ( *(_WORD *)&Destination[2 * v15 - 2] );
          *(_WORD *)&Destination[2 * (int)v15 - 2] = 34;
          v17 = 2LL * (int)v15 + 2;
          if ( v17 >= 0x418 )
            _report_rangecheckfailure();
          *(_WORD *)&Destination[v17 - 2] = 0;
          EnterCriticalSection(&CriticalSection);
          v14 = &v28;
        }
        else
        {
          EnterCriticalSection(&CriticalSection);
          v14 = Source;
        }
        v18 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v22, L"Module", v14);
        LeaveCriticalSection(&CriticalSection);
        v7 = v18 == 0 ? 0x8007000E : 0;
        if ( v7 >= 0 )
        {
          EnterCriticalSection(&CriticalSection);
          v19 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v22, L"Module_Raw", Source);
          LeaveCriticalSection(&CriticalSection);
          Error = v19 == 0 ? 0x8007000E : 0;
          if ( v19 )
            Error = ATL::CRegObject::RegisterFromResource(
                      (ATL::CRegObject *)&v21,
                      Filename,
                      (const unsigned __int16 *)a2,
                      L"REGISTRY",
                      a3 != 0);
          goto LABEL_25;
        }
      }
    }
  }
LABEL_27:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006164  push    rbp
0x180006166  push    rbx
0x180006167  push    rsi
0x180006168  push    rdi
0x180006169  push    r14
0x18000616b  push    r15
0x18000616d  lea     rbp, [rsp-9D8h]
0x180006175  sub     rsp, 0AD8h
0x18000617c  mov     rax, cs:__security_cookie
0x180006183  xor     rax, rsp
0x180006186  mov     [rbp+0A00h+var_40], rax
0x18000618d  mov     esi, r8d
0x180006190  mov     r14d, edx
0x180006193  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000619a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800061a1  mov     [rsp+0B00h+var_AD0], rax
0x1800061a6  xor     r15d, r15d
0x1800061a9  mov     [rsp+0B00h+var_AC8], r15
0x1800061ae  mov     [rsp+0B00h+var_AC0], r15
0x1800061b3  mov     [rsp+0B00h+var_AB8], r15d
0x1800061b8  xorps   xmm0, xmm0
0x1800061bb  xor     eax, eax
0x1800061bd  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800061c2  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800061c7  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800061cc  mov     [rsp+0B00h+var_A88], r15b
0x1800061d1  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800061d6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800061db  mov     ebx, eax
0x1800061dd  test    eax, eax
0x1800061df  js      loc_1800063E1
0x1800061e5  mov     [rsp+0B00h+var_A88], 1
0x1800061ea  mov     rax, [rdi]
0x1800061ed  lea     rdx, [rsp+0B00h+var_AD0]
0x1800061f2  mov     rcx, rdi
0x1800061f5  mov     rax, [rax+28h]
0x1800061f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061fe  mov     ebx, eax
0x180006200  test    eax, eax
0x180006202  js      loc_1800063E1
0x180006208  mov     rbx, cs:hInstance
0x18000620f  mov     edi, 104h
0x180006214  mov     r8d, edi; nSize
0x180006217  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000621e  mov     rcx, rbx; hModule
0x180006221  call    cs:__imp_GetModuleFileNameW
0x180006227  test    eax, eax
0x180006229  jnz     short loc_180006235
0x18000622b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006230  jmp     loc_1800063D8
0x180006235  cmp     eax, edi
0x180006237  jnz     short loc_180006243
0x180006239  mov     ebx, 8007007Ah
0x18000623e  jmp     loc_1800063E1
0x180006243  lea     rdx, [rbp+0A00h+Filename]
0x18000624a  mov     ecx, r15d
0x18000624d  mov     r9d, 27h ; '''
0x180006253  movzx   r8d, word ptr [rdx]
0x180006257  test    r8w, r8w
0x18000625b  jz      short loc_180006287
0x18000625d  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180006263  cmp     r8w, r9w
0x180006267  jnz     short loc_180006279
0x180006269  cmp     ecx, 206h
0x18000626f  jnb     short loc_180006279
0x180006271  inc     ecx
0x180006273  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180006279  add     rdx, 2
0x18000627d  inc     ecx
0x18000627f  cmp     ecx, 207h
0x180006285  jb      short loc_180006253
0x180006287  mov     [rbp+rcx*2+0A00h+Source], r15w
0x18000628d  test    rbx, rbx
0x180006290  jz      short loc_1800062B3
0x180006292  xor     ecx, ecx; lpModuleName
0x180006294  call    cs:__imp_GetModuleHandleW
0x18000629a  cmp     rbx, rax
0x18000629d  jz      short loc_1800062B3
0x18000629f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800062a4  call    cs:__imp_EnterCriticalSection
0x1800062aa  lea     r8, [rbp+0A00h+Source]
0x1800062ae  jmp     loc_180006346
0x1800062b3  mov     edi, 22h ; '"'
0x1800062b8  mov     [rbp+0A00h+var_460], di
0x1800062bf  lea     rcx, [rbp+0A00h+Source]
0x1800062c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800062c7  mov     rax, rbx
0x1800062ca  inc     rax
0x1800062cd  cmp     [rcx+rax*2], r15w
0x1800062d2  jnz     short loc_1800062CA
0x1800062d4  inc     eax
0x1800062d6  movsxd  r9, eax
0x1800062d9  add     r9, r9; SourceSize
0x1800062dc  lea     r8, [rbp+0A00h+Source]; Source
0x1800062e0  mov     edx, 414h; DestinationSize
0x1800062e5  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800062ec  call    cs:__imp_memcpy_s
0x1800062f2  test    eax, eax
0x1800062f4  jnz     loc_1800063DC
0x1800062fa  lea     rax, [rbp+0A00h+var_460]
0x180006301  inc     rbx
0x180006304  cmp     [rax+rbx*2], r15w
0x180006309  jnz     short loc_180006301
0x18000630b  movsxd  rax, ebx
0x18000630e  mov     [rbp+rax*2+0A00h+var_460], di
0x180006316  lea     rcx, ds:2[rax*2]
0x18000631e  cmp     rcx, 418h
0x180006325  jnb     loc_18000640C
0x18000632b  mov     [rbp+rcx+0A00h+var_460], r15w
0x180006334  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006339  call    cs:__imp_EnterCriticalSection
0x18000633f  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180006346  lea     rdx, aModule; "Module"
0x18000634d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006352  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006357  mov     ebx, eax
0x180006359  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000635e  call    cs:__imp_LeaveCriticalSection
0x180006364  neg     ebx
0x180006366  sbb     ebx, ebx
0x180006368  mov     edi, 8007000Eh
0x18000636d  not     ebx
0x18000636f  and     ebx, edi
0x180006371  test    ebx, ebx
0x180006373  js      short loc_1800063E1
0x180006375  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000637a  call    cs:__imp_EnterCriticalSection
0x180006380  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180006384  lea     rdx, aModuleRaw; "Module_Raw"
0x18000638b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006390  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006395  mov     ebx, eax
0x180006397  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000639c  call    cs:__imp_LeaveCriticalSection
0x1800063a2  mov     ecx, ebx
0x1800063a4  neg     ecx
0x1800063a6  sbb     eax, eax
0x1800063a8  not     eax
0x1800063aa  and     eax, edi
0x1800063ac  test    ebx, ebx
0x1800063ae  jz      short loc_1800063D8
0x1800063b0  mov     eax, r15d
0x1800063b3  test    esi, esi
0x1800063b5  setnz   al
0x1800063b8  movzx   r8d, r14w; unsigned __int16 *
0x1800063bc  mov     [rsp+0B00h+var_AE0], eax; int
0x1800063c0  lea     r9, aRegistry; "REGISTRY"
0x1800063c7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800063ce  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800063d3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800063d8  mov     ebx, eax
0x1800063da  jmp     short loc_1800063E1
0x1800063dc  mov     ebx, 80004005h
0x1800063e1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800063e6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800063eb  mov     eax, ebx
0x1800063ed  mov     rcx, [rbp+0A00h+var_40]
0x1800063f4  xor     rcx, rsp; StackCookie
0x1800063f7  call    __security_check_cookie
0x1800063fc  add     rsp, 0AD8h
0x180006403  pop     r15
0x180006405  pop     r14
0x180006407  pop     rdi
0x180006408  pop     rsi
0x180006409  pop     rbx
0x18000640a  pop     rbp
0x18000640b  retn
0x18000640c  call    __report_rangecheckfailure
```
