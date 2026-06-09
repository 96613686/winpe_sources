# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005e3c`
- end: `0x18000617a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006190`

## callees

- `0x180001938`
- `0x180002254`
- `0x18000252c`
- `0x180003114`
- `0x18000433c`
- `0x180004d18`
- `0x180005e3c`
- `0x18000dd10`
- `0x180010010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000601a`
- `msvcrt!memcpy_s` at `0x18000601a`
- `KERNEL32!EnterCriticalSection` at `0x180005edd`
- `KERNEL32!EnterCriticalSection` at `0x180005fc9`
- `KERNEL32!EnterCriticalSection` at `0x180006067`
- `KERNEL32!EnterCriticalSection` at `0x1800060ac`
- `KERNEL32!EnterCriticalSection` at `0x180005edd`
- `KERNEL32!EnterCriticalSection` at `0x180005fc9`
- `KERNEL32!EnterCriticalSection` at `0x180006067`
- `KERNEL32!EnterCriticalSection` at `0x1800060ac`
- `KERNEL32!LeaveCriticalSection` at `0x180005ef8`
- `KERNEL32!LeaveCriticalSection` at `0x18000608c`
- `KERNEL32!LeaveCriticalSection` at `0x1800060d1`
- `KERNEL32!LeaveCriticalSection` at `0x180005ef8`
- `KERNEL32!LeaveCriticalSection` at `0x18000608c`
- `KERNEL32!LeaveCriticalSection` at `0x1800060d1`
- `KERNEL32!GetModuleHandleW` at `0x180005fb9`
- `KERNEL32!GetModuleHandleW` at `0x180005fb9`
- `KERNEL32!GetModuleFileNameW` at `0x180005f3e`
- `KERNEL32!GetModuleFileNameW` at `0x180005f3e`

## string_xrefs

- `0x180006107`: `REGISTRY`

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
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v29 = 0;
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
        v32 = 34;
        v19 = -1;
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
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        v21 = 2LL * (int)v19 + 2;
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
0x180005e3c  mov     [rsp-8+arg_10], rbx
0x180005e41  push    rbp
0x180005e42  push    rsi
0x180005e43  push    rdi
0x180005e44  push    r12
0x180005e46  push    r13
0x180005e48  push    r14
0x180005e4a  push    r15
0x180005e4c  lea     rbp, [rsp-9D0h]
0x180005e54  sub     rsp, 0AD0h
0x180005e5b  mov     rax, cs:__security_cookie
0x180005e62  xor     rax, rsp
0x180005e65  mov     [rbp+0A00h+var_40], rax
0x180005e6c  mov     rbx, r9
0x180005e6f  mov     r12d, r8d
0x180005e72  mov     r14, rdx
0x180005e75  mov     r15, rcx
0x180005e78  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005e7f  mov     [rsp+0B00h+var_AD0], rax
0x180005e84  xor     r13d, r13d
0x180005e87  mov     [rsp+0B00h+var_AC8], r13
0x180005e8c  mov     [rsp+0B00h+var_AC0], r13
0x180005e91  mov     [rsp+0B00h+var_AB8], r13d
0x180005e96  xorps   xmm0, xmm0
0x180005e99  xor     eax, eax
0x180005e9b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180005ea0  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005ea5  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180005eaa  mov     [rsp+0B00h+var_A88], r13b
0x180005eaf  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180005eb4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005eb9  mov     edi, eax
0x180005ebb  test    eax, eax
0x180005ebd  js      loc_18000613E
0x180005ec3  mov     [rsp+0B00h+var_A88], 1
0x180005ec8  test    rbx, rbx
0x180005ecb  jz      short loc_180005F0A
0x180005ecd  jmp     short loc_180005F02
0x180005ecf  mov     rsi, [rbx+8]
0x180005ed3  test    rsi, rsi
0x180005ed6  jz      short loc_180005EFE
0x180005ed8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005edd  call    cs:__imp_EnterCriticalSection
0x180005ee3  mov     r8, rsi; unsigned __int16 *
0x180005ee6  mov     rdx, rdi; unsigned __int16 *
0x180005ee9  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005eee  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005ef3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005ef8  call    cs:__imp_LeaveCriticalSection
0x180005efe  add     rbx, 10h
0x180005f02  mov     rdi, [rbx]
0x180005f05  test    rdi, rdi
0x180005f08  jnz     short loc_180005ECF
0x180005f0a  mov     rax, [r15]
0x180005f0d  lea     rdx, [rsp+0B00h+var_AD0]
0x180005f12  mov     rcx, r15
0x180005f15  mov     rax, [rax+28h]
0x180005f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1e  mov     ebx, eax
0x180005f20  test    eax, eax
0x180005f22  js      loc_180006130
0x180005f28  mov     rbx, cs:hInstance
0x180005f2f  mov     edi, 104h
0x180005f34  mov     r8d, edi; nSize
0x180005f37  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005f3b  mov     rcx, rbx; hModule
0x180005f3e  call    cs:__imp_GetModuleFileNameW
0x180005f44  test    eax, eax
0x180005f46  jnz     short loc_180005F54
0x180005f48  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005f4d  mov     ebx, eax
0x180005f4f  jmp     loc_180006130
0x180005f54  cmp     eax, edi
0x180005f56  jnz     short loc_180005F62
0x180005f58  mov     ebx, 8007007Ah
0x180005f5d  jmp     loc_180006130
0x180005f62  lea     rdx, [rbp+0A00h+Filename]
0x180005f66  mov     ecx, r13d
0x180005f69  mov     r9d, 27h ; '''
0x180005f6f  movzx   r8d, word ptr [rdx]
0x180005f73  test    r8w, r8w
0x180005f77  jz      short loc_180005FA9
0x180005f79  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005f82  cmp     r8w, r9w
0x180005f86  jnz     short loc_180005F9B
0x180005f88  cmp     ecx, 206h
0x180005f8e  jnb     short loc_180005F9B
0x180005f90  inc     ecx
0x180005f92  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180005f9b  add     rdx, 2
0x180005f9f  inc     ecx
0x180005fa1  cmp     ecx, 207h
0x180005fa7  jb      short loc_180005F6F
0x180005fa9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180005fb2  test    rbx, rbx
0x180005fb5  jz      short loc_180005FDB
0x180005fb7  xor     ecx, ecx; lpModuleName
0x180005fb9  call    cs:__imp_GetModuleHandleW
0x180005fbf  cmp     rbx, rax
0x180005fc2  jz      short loc_180005FDB
0x180005fc4  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005fc9  call    cs:__imp_EnterCriticalSection
0x180005fcf  lea     r8, [rbp+0A00h+Source]
0x180005fd6  jmp     loc_180006074
0x180005fdb  mov     edi, 22h ; '"'
0x180005fe0  mov     [rbp+0A00h+var_460], di
0x180005fe7  lea     rcx, [rbp+0A00h+Source]
0x180005fee  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005ff2  mov     rax, rbx
0x180005ff5  inc     rax
0x180005ff8  cmp     [rcx+rax*2], r13w
0x180005ffd  jnz     short loc_180005FF5
0x180005fff  inc     eax
0x180006001  movsxd  r9, eax
0x180006004  add     r9, r9; SourceSize
0x180006007  lea     r8, [rbp+0A00h+Source]; Source
0x18000600e  mov     edx, 414h; DestinationSize
0x180006013  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000601a  call    cs:__imp_memcpy_s
0x180006020  test    eax, eax
0x180006022  jnz     loc_18000612B
0x180006028  lea     rax, [rbp+0A00h+var_460]
0x18000602f  inc     rbx
0x180006032  cmp     [rax+rbx*2], r13w
0x180006037  jnz     short loc_18000602F
0x180006039  movsxd  rax, ebx
0x18000603c  mov     [rbp+rax*2+0A00h+var_460], di
0x180006044  lea     rcx, ds:2[rax*2]
0x18000604c  cmp     rcx, 418h
0x180006053  jnb     loc_180006174
0x180006059  mov     [rbp+rcx+0A00h+var_460], r13w
0x180006062  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006067  call    cs:__imp_EnterCriticalSection
0x18000606d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180006074  lea     rdx, aModule; "Module"
0x18000607b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180006080  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180006085  mov     ebx, eax
0x180006087  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000608c  call    cs:__imp_LeaveCriticalSection
0x180006092  neg     ebx
0x180006094  sbb     ebx, ebx
0x180006096  mov     edi, 8007000Eh
0x18000609b  not     ebx
0x18000609d  and     ebx, edi
0x18000609f  test    ebx, ebx
0x1800060a1  js      loc_180006130
0x1800060a7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800060ac  call    cs:__imp_EnterCriticalSection
0x1800060b2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x1800060b9  lea     rdx, aModuleRaw; "Module_Raw"
0x1800060c0  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800060c5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800060ca  mov     ebx, eax
0x1800060cc  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800060d1  call    cs:__imp_LeaveCriticalSection
0x1800060d7  mov     ecx, ebx
0x1800060d9  neg     ecx
0x1800060db  sbb     eax, eax
0x1800060dd  not     eax
0x1800060df  and     eax, edi
0x1800060e1  test    ebx, ebx
0x1800060e3  jz      loc_180005F4D
0x1800060e9  test    r12d, r12d
0x1800060ec  jz      short loc_1800060FD
0x1800060ee  test    r14, r14
0x1800060f1  jz      short loc_180006124
0x1800060f3  mov     [rsp+0B00h+var_AE0], 1
0x1800060fb  jmp     short loc_180006107
0x1800060fd  test    r14, r14
0x180006100  jz      short loc_180006124
0x180006102  mov     [rsp+0B00h+var_AE0], r13d; int
0x180006107  lea     r9, aRegistry; "REGISTRY"
0x18000610e  mov     r8, r14; unsigned __int16 *
0x180006111  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180006115  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000611a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000611f  jmp     loc_180005F4D
0x180006124  mov     ebx, 80070057h
0x180006129  jmp     short loc_180006130
0x18000612b  mov     ebx, 80004005h
0x180006130  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006135  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000613a  mov     eax, ebx
0x18000613c  jmp     short loc_18000614A
0x18000613e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006143  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006148  mov     eax, edi
0x18000614a  mov     rcx, [rbp+0A00h+var_40]
0x180006151  xor     rcx, rsp; StackCookie
0x180006154  call    __security_check_cookie
0x180006159  mov     rbx, [rsp+0B00h+arg_10]
0x180006161  add     rsp, 0AD0h
0x180006168  pop     r15
0x18000616a  pop     r14
0x18000616c  pop     r13
0x18000616e  pop     r12
0x180006170  pop     rdi
0x180006171  pop     rsi
0x180006172  pop     rbp
0x180006173  retn
0x180006174  call    __report_rangecheckfailure
```
