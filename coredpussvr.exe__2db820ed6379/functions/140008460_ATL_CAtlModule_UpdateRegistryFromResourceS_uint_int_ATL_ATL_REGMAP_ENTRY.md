# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140008460`
- end: `0x140008785`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `805`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140008ae0`

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
- `0x140008460`
- `0x140009090`
- `0x14000a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000870c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000870c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140008542`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140008542`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400085d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000866d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400086ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400085d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000866d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400086ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400086e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400086e2`

## string_xrefs

- `0x140008737`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
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
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
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
      goto LABEL_32;
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_31:
      v9 = Error;
      goto LABEL_32;
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
            goto LABEL_32;
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
          Error = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v25,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    a3 != 0);
        goto LABEL_31;
      }
    }
LABEL_32:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
    return (unsigned int)v9;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140008460  push    rbp
0x140008462  push    rbx
0x140008463  push    rsi
0x140008464  push    rdi
0x140008465  push    r12
0x140008467  push    r14
0x140008469  push    r15
0x14000846b  lea     rbp, [rsp-9D0h]
0x140008473  sub     rsp, 0AD0h
0x14000847a  mov     rax, cs:__security_cookie
0x140008481  xor     rax, rsp
0x140008484  mov     [rbp+0A00h+var_40], rax
0x14000848b  mov     rbx, r9
0x14000848e  mov     r14d, r8d
0x140008491  mov     r15d, edx
0x140008494  mov     rsi, rcx
0x140008497  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000849e  mov     [rsp+0B00h+var_AD0], rax
0x1400084a3  xor     r12d, r12d
0x1400084a6  mov     [rsp+0B00h+var_AC8], r12
0x1400084ab  mov     [rsp+0B00h+var_AC0], r12
0x1400084b0  mov     [rsp+0B00h+var_AB8], r12d
0x1400084b5  xorps   xmm0, xmm0
0x1400084b8  xor     eax, eax
0x1400084ba  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1400084bf  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1400084c4  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1400084c9  mov     [rsp+0B00h+var_A88], r12b
0x1400084ce  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1400084d3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400084d8  mov     edi, eax
0x1400084da  test    eax, eax
0x1400084dc  js      loc_140008751
0x1400084e2  mov     [rsp+0B00h+var_A88], 1
0x1400084e7  test    rbx, rbx
0x1400084ea  jz      short loc_14000850B
0x1400084ec  jmp     short loc_140008503
0x1400084ee  mov     r8, [rbx+8]; unsigned __int16 *
0x1400084f2  mov     rdx, rax; unsigned __int16 *
0x1400084f5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1400084fa  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1400084ff  lea     rbx, [rbx+10h]
0x140008503  mov     rax, [rbx]
0x140008506  test    rax, rax
0x140008509  jnz     short loc_1400084EE
0x14000850b  mov     rax, [rsi]
0x14000850e  lea     rdx, [rsp+0B00h+var_AD0]
0x140008513  mov     rcx, rsi
0x140008516  mov     rax, [rax+28h]
0x14000851a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000851f  mov     ebx, eax
0x140008521  test    eax, eax
0x140008523  js      loc_1400086FE
0x140008529  mov     rbx, cs:hModule
0x140008530  mov     edi, 104h
0x140008535  mov     r8d, edi; nSize
0x140008538  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x14000853f  mov     rcx, rbx; hModule
0x140008542  call    cs:__imp_GetModuleFileNameW
0x140008549  nop     dword ptr [rax+rax+00h]
0x14000854e  test    eax, eax
0x140008550  jnz     short loc_14000855C
0x140008552  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140008557  jmp     loc_1400086FC
0x14000855c  cmp     eax, edi
0x14000855e  jnz     short loc_14000856A
0x140008560  mov     ebx, 8007007Ah
0x140008565  jmp     loc_1400086FE
0x14000856a  lea     rdx, [rbp+0A00h+Filename]
0x140008571  mov     ecx, r12d
0x140008574  mov     r9d, 27h ; '''
0x14000857a  movzx   r8d, word ptr [rdx]
0x14000857e  test    r8w, r8w
0x140008582  jz      short loc_1400085AE
0x140008584  mov     [rbp+rcx*2+0A00h+Src], r8w
0x14000858a  cmp     r8w, r9w
0x14000858e  jnz     short loc_1400085A0
0x140008590  cmp     ecx, 206h
0x140008596  jnb     short loc_1400085A0
0x140008598  inc     ecx
0x14000859a  mov     [rbp+rcx*2+0A00h+Src], r9w
0x1400085a0  add     rdx, 2
0x1400085a4  inc     ecx
0x1400085a6  cmp     ecx, 207h
0x1400085ac  jb      short loc_14000857A
0x1400085ae  mov     [rbp+rcx*2+0A00h+Src], r12w
0x1400085b4  test    rbx, rbx
0x1400085b7  jz      short loc_1400085E6
0x1400085b9  xor     ecx, ecx; lpModuleName
0x1400085bb  call    cs:__imp_GetModuleHandleW
0x1400085c2  nop     dword ptr [rax+rax+00h]
0x1400085c7  cmp     rbx, rax
0x1400085ca  jz      short loc_1400085E6
0x1400085cc  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400085d1  call    cs:__imp_EnterCriticalSection
0x1400085d8  nop     dword ptr [rax+rax+00h]
0x1400085dd  lea     r8, [rbp+0A00h+Src]
0x1400085e1  jmp     loc_140008680
0x1400085e6  mov     edi, 22h ; '"'
0x1400085eb  mov     [rbp+0A00h+var_460], di
0x1400085f2  lea     rcx, [rbp+0A00h+Src]
0x1400085f6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400085fa  mov     rax, rbx
0x1400085fd  inc     rax
0x140008600  cmp     [rcx+rax*2], r12w
0x140008605  jnz     short loc_1400085FD
0x140008607  inc     eax
0x140008609  movsxd  r8, eax
0x14000860c  add     r8, r8; Size
0x14000860f  jz      short loc_14000862E
0x140008611  cmp     r8, 414h
0x140008618  ja      loc_14000870C
0x14000861e  lea     rdx, [rbp+0A00h+Src]; Src
0x140008622  lea     rcx, [rbp+0A00h+var_45E]; void *
0x140008629  call    memcpy_0
0x14000862e  lea     rax, [rbp+0A00h+var_460]
0x140008635  inc     rbx
0x140008638  cmp     [rax+rbx*2], r12w
0x14000863d  jnz     short loc_140008635
0x14000863f  movsxd  rax, ebx
0x140008642  mov     [rbp+rax*2+0A00h+var_460], di
0x14000864a  lea     rcx, ds:2[rax*2]
0x140008652  cmp     rcx, 418h
0x140008659  jnb     loc_14000877F
0x14000865f  mov     [rbp+rcx+0A00h+var_460], r12w
0x140008668  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000866d  call    cs:__imp_EnterCriticalSection
0x140008674  nop     dword ptr [rax+rax+00h]
0x140008679  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x140008680  lea     rdx, aModule; "Module"
0x140008687  lea     rcx, [rsp+0B00h+var_AC8]; this
0x14000868c  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140008691  mov     ebx, eax
0x140008693  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140008698  call    cs:__imp_LeaveCriticalSection
0x14000869f  nop     dword ptr [rax+rax+00h]
0x1400086a4  neg     ebx
0x1400086a6  sbb     ebx, ebx
0x1400086a8  mov     edi, 8007000Eh
0x1400086ad  not     ebx
0x1400086af  and     ebx, edi
0x1400086b1  test    ebx, ebx
0x1400086b3  js      short loc_1400086FE
0x1400086b5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400086ba  call    cs:__imp_EnterCriticalSection
0x1400086c1  nop     dword ptr [rax+rax+00h]
0x1400086c6  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x1400086ca  lea     rdx, aModuleRaw; "Module_Raw"
0x1400086d1  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400086d6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400086db  mov     ebx, eax
0x1400086dd  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400086e2  call    cs:__imp_LeaveCriticalSection
0x1400086e9  nop     dword ptr [rax+rax+00h]
0x1400086ee  mov     ecx, ebx
0x1400086f0  neg     ecx
0x1400086f2  sbb     eax, eax
0x1400086f4  not     eax
0x1400086f6  and     eax, edi
0x1400086f8  test    ebx, ebx
0x1400086fa  jnz     short loc_140008726
0x1400086fc  mov     ebx, eax
0x1400086fe  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008703  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140008708  mov     eax, ebx
0x14000870a  jmp     short loc_14000875D
0x14000870c  call    cs:__imp__o__errno
0x140008713  nop     dword ptr [rax+rax+00h]
0x140008718  mov     [rax], edi
0x14000871a  call    _invalid_parameter_noinfo
0x14000871f  mov     ebx, 80004005h
0x140008724  jmp     short loc_1400086FE
0x140008726  mov     eax, r12d
0x140008729  test    r14d, r14d
0x14000872c  setnz   al
0x14000872f  movzx   r8d, r15w; unsigned __int16 *
0x140008733  mov     [rsp+0B00h+var_AE0], eax; int
0x140008737  lea     r9, aRegistry; "REGISTRY"
0x14000873e  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x140008745  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000874a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x14000874f  jmp     short loc_1400086FC
0x140008751  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140008756  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x14000875b  mov     eax, edi
0x14000875d  mov     rcx, [rbp+0A00h+var_40]
0x140008764  xor     rcx, rsp; StackCookie
0x140008767  call    __security_check_cookie
0x14000876c  add     rsp, 0AD0h
0x140008773  pop     r15
0x140008775  pop     r14
0x140008777  pop     r12
0x140008779  pop     rdi
0x14000877a  pop     rsi
0x14000877b  pop     rbx
0x14000877c  pop     rbp
0x14000877d  retn
0x14000877f  call    __report_rangecheckfailure
```
