# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000878c`
- end: `0x140008ad4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `840`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140008af0`

## callees

- `0x140001500`
- `0x1400017f0`
- `0x1400020a6`
- `0x140005c40`
- `0x140005e4c`
- `0x140006140`
- `0x140006900`
- `0x140006ebc`
- `0x140007880`
- `0x14000878c`
- `0x140009090`
- `0x14000a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008a47`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008a47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400088ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400088ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000886b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000886b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400089a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400089f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008900`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400089a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400089f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400089d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008a1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400089d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008a1d`

## string_xrefs

- `0x140008a7f`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  signed int v9; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  unsigned __int16 v16; // r8
  unsigned __int16 *v17; // r8
  __int64 v18; // rbx
  __int64 v19; // rax
  size_t v20; // r8
  unsigned __int64 v21; // rcx
  int v22; // ebx
  int v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Src[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v33[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

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
      while ( *(_QWORD *)a4 )
      {
        ATL::CRegObject::AddReplacement(
          (ATL::CRegObject *)&v25,
          *(const unsigned __int16 **)a4,
          *((const unsigned __int16 **)a4 + 1));
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v9 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v9 < 0 )
      goto LABEL_31;
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_30;
    }
    if ( ModuleFileNameW == 260 )
    {
      v9 = -2147024774;
    }
    else
    {
      v13 = Filename;
      v14 = 0;
      v15 = 39;
      do
      {
        v16 = *v13;
        if ( !*v13 )
          break;
        Src[v14] = v16;
        if ( v16 == 39 && (unsigned int)v14 < 0x206 )
        {
          LODWORD(v14) = v14 + 1;
          Src[(unsigned int)v14] = 39;
        }
        ++v13;
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < 0x207 );
      Src[v14] = 0;
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v32 = 34;
        v18 = -1;
        v19 = -1;
        do
          ++v19;
        while ( Src[v19] );
        v20 = 2LL * ((int)v19 + 1);
        if ( v20 )
        {
          if ( v20 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v13, v20, v15) = 34;
            invalid_parameter_noinfo();
            v9 = -2147467259;
            goto LABEL_31;
          }
          memcpy_0(v33, Src, v20);
        }
        do
          ++v18;
        while ( *(_WORD *)&v33[2 * v18 - 2] );
        *(_WORD *)&v33[2 * (int)v18 - 2] = 34;
        v21 = 2LL * (int)v18 + 2;
        if ( v21 >= 0x418 )
          _report_rangecheckfailure(v21, v13, v20, v15);
        *(_WORD *)&v33[v21 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v17 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v17 = Src;
      }
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v17);
      LeaveCriticalSection(&CriticalSection);
      v9 = v22 == 0 ? 0x8007000E : 0;
      if ( v9 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v23 == 0 ? 0x8007000E : 0;
        if ( v23 )
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 1);
              goto LABEL_30;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 0);
            goto LABEL_30;
          }
          v9 = -2147024809;
          goto LABEL_31;
        }
LABEL_30:
        v9 = Error;
      }
    }
LABEL_31:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
    return (unsigned int)v9;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000878c  push    rbp
0x14000878e  push    rbx
0x14000878f  push    rsi
0x140008790  push    rdi
0x140008791  push    r12
0x140008793  push    r14
0x140008795  push    r15
0x140008797  lea     rbp, [rsp-9D0h]
0x14000879f  sub     rsp, 0AD0h
0x1400087a6  mov     rax, cs:__security_cookie
0x1400087ad  xor     rax, rsp
0x1400087b0  mov     [rbp+0A00h+var_40], rax
0x1400087b7  mov     rbx, r9
0x1400087ba  mov     r15d, r8d
0x1400087bd  mov     rdi, rdx
0x1400087c0  mov     r14, rcx
0x1400087c3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1400087ca  mov     [rsp+0B00h+var_AD0], rax
0x1400087cf  xor     r12d, r12d
0x1400087d2  mov     [rsp+0B00h+var_AC8], r12
0x1400087d7  mov     [rsp+0B00h+var_AC0], r12
0x1400087dc  mov     [rsp+0B00h+var_AB8], r12d
0x1400087e1  xorps   xmm0, xmm0
0x1400087e4  xor     eax, eax
0x1400087e6  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1400087eb  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1400087f0  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1400087f5  mov     [rsp+0B00h+var_A88], r12b
0x1400087fa  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1400087ff  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140008804  mov     esi, eax
0x140008806  test    eax, eax
0x140008808  js      loc_140008AA0
0x14000880e  mov     [rsp+0B00h+var_A88], 1
0x140008813  test    rbx, rbx
0x140008816  jz      short loc_140008837
0x140008818  jmp     short loc_14000882F
0x14000881a  mov     r8, [rbx+8]; unsigned __int16 *
0x14000881e  mov     rdx, rax; unsigned __int16 *
0x140008821  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008826  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x14000882b  lea     rbx, [rbx+10h]
0x14000882f  mov     rax, [rbx]
0x140008832  test    rax, rax
0x140008835  jnz     short loc_14000881A
0x140008837  mov     rax, [r14]
0x14000883a  lea     rdx, [rsp+0B00h+var_AD0]
0x14000883f  mov     rcx, r14
0x140008842  mov     rax, [rax+28h]
0x140008846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000884b  mov     ebx, eax
0x14000884d  test    eax, eax
0x14000884f  js      loc_140008A39
0x140008855  mov     rbx, cs:hModule
0x14000885c  mov     esi, 104h
0x140008861  mov     r8d, esi; nSize
0x140008864  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x140008868  mov     rcx, rbx; hModule
0x14000886b  call    cs:__imp_GetModuleFileNameW
0x140008872  nop     dword ptr [rax+rax+00h]
0x140008877  test    eax, eax
0x140008879  jnz     short loc_140008885
0x14000887b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140008880  jmp     loc_140008A37
0x140008885  cmp     eax, esi
0x140008887  jnz     short loc_140008893
0x140008889  mov     ebx, 8007007Ah
0x14000888e  jmp     loc_140008A39
0x140008893  lea     rdx, [rbp+0A00h+Filename]
0x140008897  mov     ecx, r12d
0x14000889a  mov     r9d, 27h ; '''
0x1400088a0  movzx   r8d, word ptr [rdx]
0x1400088a4  test    r8w, r8w
0x1400088a8  jz      short loc_1400088DA
0x1400088aa  mov     [rbp+rcx*2+0A00h+Src], r8w
0x1400088b3  cmp     r8w, r9w
0x1400088b7  jnz     short loc_1400088CC
0x1400088b9  cmp     ecx, 206h
0x1400088bf  jnb     short loc_1400088CC
0x1400088c1  inc     ecx
0x1400088c3  mov     [rbp+rcx*2+0A00h+Src], r9w
0x1400088cc  add     rdx, 2
0x1400088d0  inc     ecx
0x1400088d2  cmp     ecx, 207h
0x1400088d8  jb      short loc_1400088A0
0x1400088da  mov     [rbp+rcx*2+0A00h+Src], r12w
0x1400088e3  test    rbx, rbx
0x1400088e6  jz      short loc_140008918
0x1400088e8  xor     ecx, ecx; lpModuleName
0x1400088ea  call    cs:__imp_GetModuleHandleW
0x1400088f1  nop     dword ptr [rax+rax+00h]
0x1400088f6  cmp     rbx, rax
0x1400088f9  jz      short loc_140008918
0x1400088fb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140008900  call    cs:__imp_EnterCriticalSection
0x140008907  nop     dword ptr [rax+rax+00h]
0x14000890c  lea     r8, [rbp+0A00h+Src]
0x140008913  jmp     loc_1400089B8
0x140008918  mov     esi, 22h ; '"'
0x14000891d  mov     [rbp+0A00h+var_460], si
0x140008924  lea     rcx, [rbp+0A00h+Src]
0x14000892b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000892f  mov     rax, rbx
0x140008932  inc     rax
0x140008935  cmp     [rcx+rax*2], r12w
0x14000893a  jnz     short loc_140008932
0x14000893c  inc     eax
0x14000893e  movsxd  r8, eax
0x140008941  add     r8, r8; Size
0x140008944  jz      short loc_140008966
0x140008946  cmp     r8, 414h
0x14000894d  ja      loc_140008A47
0x140008953  lea     rdx, [rbp+0A00h+Src]; Src
0x14000895a  lea     rcx, [rbp+0A00h+var_45E]; void *
0x140008961  call    memcpy_0
0x140008966  lea     rax, [rbp+0A00h+var_460]
0x14000896d  inc     rbx
0x140008970  cmp     [rax+rbx*2], r12w
0x140008975  jnz     short loc_14000896D
0x140008977  movsxd  rax, ebx
0x14000897a  mov     [rbp+rax*2+0A00h+var_460], si
0x140008982  lea     rcx, ds:2[rax*2]
0x14000898a  cmp     rcx, 418h
0x140008991  jnb     loc_140008ACE
0x140008997  mov     [rbp+rcx+0A00h+var_460], r12w
0x1400089a0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400089a5  call    cs:__imp_EnterCriticalSection
0x1400089ac  nop     dword ptr [rax+rax+00h]
0x1400089b1  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x1400089b8  lea     rdx, aModule; "Module"
0x1400089bf  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400089c4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400089c9  mov     ebx, eax
0x1400089cb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400089d0  call    cs:__imp_LeaveCriticalSection
0x1400089d7  nop     dword ptr [rax+rax+00h]
0x1400089dc  neg     ebx
0x1400089de  sbb     ebx, ebx
0x1400089e0  mov     esi, 8007000Eh
0x1400089e5  not     ebx
0x1400089e7  and     ebx, esi
0x1400089e9  test    ebx, ebx
0x1400089eb  js      short loc_140008A39
0x1400089ed  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400089f2  call    cs:__imp_EnterCriticalSection
0x1400089f9  nop     dword ptr [rax+rax+00h]
0x1400089fe  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x140008a05  lea     rdx, aModuleRaw; "Module_Raw"
0x140008a0c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140008a11  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140008a16  mov     ebx, eax
0x140008a18  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140008a1d  call    cs:__imp_LeaveCriticalSection
0x140008a24  nop     dword ptr [rax+rax+00h]
0x140008a29  mov     ecx, ebx
0x140008a2b  neg     ecx
0x140008a2d  sbb     eax, eax
0x140008a2f  not     eax
0x140008a31  and     eax, esi
0x140008a33  test    ebx, ebx
0x140008a35  jnz     short loc_140008A61
0x140008a37  mov     ebx, eax
0x140008a39  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008a3e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140008a43  mov     eax, ebx
0x140008a45  jmp     short loc_140008AAC
0x140008a47  call    cs:__imp__o__errno
0x140008a4e  nop     dword ptr [rax+rax+00h]
0x140008a53  mov     [rax], esi
0x140008a55  call    _invalid_parameter_noinfo
0x140008a5a  mov     ebx, 80004005h
0x140008a5f  jmp     short loc_140008A39
0x140008a61  test    r15d, r15d
0x140008a64  jz      short loc_140008A75
0x140008a66  test    rdi, rdi
0x140008a69  jz      short loc_140008A99
0x140008a6b  mov     [rsp+0B00h+var_AE0], 1
0x140008a73  jmp     short loc_140008A7F
0x140008a75  test    rdi, rdi
0x140008a78  jz      short loc_140008A99
0x140008a7a  mov     [rsp+0B00h+var_AE0], r12d; int
0x140008a7f  lea     r9, aRegistry; "REGISTRY"
0x140008a86  mov     r8, rdi; unsigned __int16 *
0x140008a89  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x140008a8d  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008a92  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x140008a97  jmp     short loc_140008A37
0x140008a99  mov     ebx, 80070057h
0x140008a9e  jmp     short loc_140008A39
0x140008aa0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008aa5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140008aaa  mov     eax, esi
0x140008aac  mov     rcx, [rbp+0A00h+var_40]
0x140008ab3  xor     rcx, rsp; StackCookie
0x140008ab6  call    __security_check_cookie
0x140008abb  add     rsp, 0AD0h
0x140008ac2  pop     r15
0x140008ac4  pop     r14
0x140008ac6  pop     r12
0x140008ac8  pop     rdi
0x140008ac9  pop     rsi
0x140008aca  pop     rbx
0x140008acb  pop     rbp
0x140008acc  retn
0x140008ace  call    __report_rangecheckfailure
```
