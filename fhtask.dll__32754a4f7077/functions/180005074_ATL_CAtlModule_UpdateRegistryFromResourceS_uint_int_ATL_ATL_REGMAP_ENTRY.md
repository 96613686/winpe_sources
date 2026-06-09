# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005074`
- end: `0x180005322`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `686`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005040`
- `0x180005060`

## callees

- `0x180001a18`
- `0x1800023f8`
- `0x1800025d8`
- `0x180003078`
- `0x1800039cc`
- `0x180004428`
- `0x180005074`
- `0x180009a00`
- `0x18000b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800051fc`
- `msvcrt!memcpy_s` at `0x1800051fc`
- `KERNEL32!EnterCriticalSection` at `0x1800051b4`
- `KERNEL32!EnterCriticalSection` at `0x180005249`
- `KERNEL32!EnterCriticalSection` at `0x18000528a`
- `KERNEL32!EnterCriticalSection` at `0x1800051b4`
- `KERNEL32!EnterCriticalSection` at `0x180005249`
- `KERNEL32!EnterCriticalSection` at `0x18000528a`
- `KERNEL32!GetModuleFileNameW` at `0x180005131`
- `KERNEL32!GetModuleFileNameW` at `0x180005131`
- `KERNEL32!LeaveCriticalSection` at `0x18000526e`
- `KERNEL32!LeaveCriticalSection` at `0x1800052ac`
- `KERNEL32!LeaveCriticalSection` at `0x18000526e`
- `KERNEL32!LeaveCriticalSection` at `0x1800052ac`
- `KERNEL32!GetModuleHandleW` at `0x1800051a4`
- `KERNEL32!GetModuleHandleW` at `0x1800051a4`

## string_xrefs

- `0x1800052d0`: `REGISTRY`

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
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
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
                      (const WCHAR *)&v21,
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
0x180005074  push    rbp
0x180005076  push    rbx
0x180005077  push    rsi
0x180005078  push    rdi
0x180005079  push    r14
0x18000507b  push    r15
0x18000507d  lea     rbp, [rsp-9D8h]
0x180005085  sub     rsp, 0AD8h
0x18000508c  mov     rax, cs:__security_cookie
0x180005093  xor     rax, rsp
0x180005096  mov     [rbp+0A00h+var_40], rax
0x18000509d  mov     esi, r8d
0x1800050a0  mov     r14d, edx
0x1800050a3  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800050aa  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800050b1  mov     [rsp+0B00h+var_AD0], rax
0x1800050b6  xor     r15d, r15d
0x1800050b9  mov     [rsp+0B00h+var_AC8], r15
0x1800050be  mov     [rsp+0B00h+var_AC0], r15
0x1800050c3  mov     [rsp+0B00h+var_AB8], r15d
0x1800050c8  xorps   xmm0, xmm0
0x1800050cb  xor     eax, eax
0x1800050cd  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1800050d2  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1800050d7  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1800050dc  mov     [rsp+0B00h+var_A88], r15b
0x1800050e1  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1800050e6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800050eb  mov     ebx, eax
0x1800050ed  test    eax, eax
0x1800050ef  js      loc_1800052F1
0x1800050f5  mov     [rsp+0B00h+var_A88], 1
0x1800050fa  mov     rax, [rdi]
0x1800050fd  lea     rdx, [rsp+0B00h+var_AD0]
0x180005102  mov     rcx, rdi
0x180005105  mov     rax, [rax+28h]
0x180005109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510e  mov     ebx, eax
0x180005110  test    eax, eax
0x180005112  js      loc_1800052F1
0x180005118  mov     rbx, cs:hInstance
0x18000511f  mov     edi, 104h
0x180005124  mov     r8d, edi; nSize
0x180005127  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000512e  mov     rcx, rbx; hModule
0x180005131  call    cs:__imp_GetModuleFileNameW
0x180005137  test    eax, eax
0x180005139  jnz     short loc_180005145
0x18000513b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005140  jmp     loc_1800052E8
0x180005145  cmp     eax, edi
0x180005147  jnz     short loc_180005153
0x180005149  mov     ebx, 8007007Ah
0x18000514e  jmp     loc_1800052F1
0x180005153  lea     rdx, [rbp+0A00h+Filename]
0x18000515a  mov     ecx, r15d
0x18000515d  mov     r9d, 27h ; '''
0x180005163  movzx   r8d, word ptr [rdx]
0x180005167  test    r8w, r8w
0x18000516b  jz      short loc_180005197
0x18000516d  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005173  cmp     r8w, r9w
0x180005177  jnz     short loc_180005189
0x180005179  cmp     ecx, 206h
0x18000517f  jnb     short loc_180005189
0x180005181  inc     ecx
0x180005183  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180005189  add     rdx, 2
0x18000518d  inc     ecx
0x18000518f  cmp     ecx, 207h
0x180005195  jb      short loc_180005163
0x180005197  mov     [rbp+rcx*2+0A00h+Source], r15w
0x18000519d  test    rbx, rbx
0x1800051a0  jz      short loc_1800051C3
0x1800051a2  xor     ecx, ecx; lpModuleName
0x1800051a4  call    cs:__imp_GetModuleHandleW
0x1800051aa  cmp     rbx, rax
0x1800051ad  jz      short loc_1800051C3
0x1800051af  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800051b4  call    cs:__imp_EnterCriticalSection
0x1800051ba  lea     r8, [rbp+0A00h+Source]
0x1800051be  jmp     loc_180005256
0x1800051c3  mov     edi, 22h ; '"'
0x1800051c8  mov     [rbp+0A00h+var_460], di
0x1800051cf  lea     rcx, [rbp+0A00h+Source]
0x1800051d3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800051d7  mov     rax, rbx
0x1800051da  inc     rax
0x1800051dd  cmp     [rcx+rax*2], r15w
0x1800051e2  jnz     short loc_1800051DA
0x1800051e4  inc     eax
0x1800051e6  movsxd  r9, eax
0x1800051e9  add     r9, r9; SourceSize
0x1800051ec  lea     r8, [rbp+0A00h+Source]; Source
0x1800051f0  mov     edx, 414h; DestinationSize
0x1800051f5  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800051fc  call    cs:__imp_memcpy_s
0x180005202  test    eax, eax
0x180005204  jnz     loc_1800052EC
0x18000520a  lea     rax, [rbp+0A00h+var_460]
0x180005211  inc     rbx
0x180005214  cmp     [rax+rbx*2], r15w
0x180005219  jnz     short loc_180005211
0x18000521b  movsxd  rax, ebx
0x18000521e  mov     [rbp+rax*2+0A00h+var_460], di
0x180005226  lea     rcx, ds:2[rax*2]
0x18000522e  cmp     rcx, 418h
0x180005235  jnb     loc_18000531C
0x18000523b  mov     [rbp+rcx+0A00h+var_460], r15w
0x180005244  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005249  call    cs:__imp_EnterCriticalSection
0x18000524f  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005256  lea     rdx, aModule; "Module"
0x18000525d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005262  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005267  mov     ebx, eax
0x180005269  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000526e  call    cs:__imp_LeaveCriticalSection
0x180005274  neg     ebx
0x180005276  sbb     ebx, ebx
0x180005278  mov     edi, 8007000Eh
0x18000527d  not     ebx
0x18000527f  and     ebx, edi
0x180005281  test    ebx, ebx
0x180005283  js      short loc_1800052F1
0x180005285  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000528a  call    cs:__imp_EnterCriticalSection
0x180005290  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005294  lea     rdx, aModuleRaw; "Module_Raw"
0x18000529b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800052a0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800052a5  mov     ebx, eax
0x1800052a7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800052ac  call    cs:__imp_LeaveCriticalSection
0x1800052b2  mov     ecx, ebx
0x1800052b4  neg     ecx
0x1800052b6  sbb     eax, eax
0x1800052b8  not     eax
0x1800052ba  and     eax, edi
0x1800052bc  test    ebx, ebx
0x1800052be  jz      short loc_1800052E8
0x1800052c0  mov     eax, r15d
0x1800052c3  test    esi, esi
0x1800052c5  setnz   al
0x1800052c8  movzx   r8d, r14w; unsigned __int16 *
0x1800052cc  mov     [rsp+0B00h+var_AE0], eax; int
0x1800052d0  lea     r9, aRegistry; "REGISTRY"
0x1800052d7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800052de  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800052e3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800052e8  mov     ebx, eax
0x1800052ea  jmp     short loc_1800052F1
0x1800052ec  mov     ebx, 80004005h
0x1800052f1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800052f6  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800052fb  mov     eax, ebx
0x1800052fd  mov     rcx, [rbp+0A00h+var_40]
0x180005304  xor     rcx, rsp; StackCookie
0x180005307  call    __security_check_cookie
0x18000530c  add     rsp, 0AD8h
0x180005313  pop     r15
0x180005315  pop     r14
0x180005317  pop     rdi
0x180005318  pop     rsi
0x180005319  pop     rbx
0x18000531a  pop     rbp
0x18000531b  retn
0x18000531c  call    __report_rangecheckfailure
```
