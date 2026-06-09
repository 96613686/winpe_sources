# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180012314`
- end: `0x1800124aa`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `406`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012280`
- `0x1800122a0`
- `0x1800122c0`
- `0x1800122e0`
- `0x180012300`

## callees

- `0x18000e18c`
- `0x18000e2a8`
- `0x180010dd4`
- `0x180012314`
- `0x180012b02`
- `0x180012b40`

## import_xrefs

- `msvcrt!malloc` at `0x180012360`
- `msvcrt!malloc` at `0x180012360`
- `KERNEL32!GetModuleFileNameW` at `0x180012395`
- `KERNEL32!GetModuleFileNameW` at `0x180012395`
- `KERNEL32!GetLastError` at `0x1800123ad`
- `KERNEL32!GetLastError` at `0x1800123ad`

## string_xrefs

- `0x18001243f`: `REGISTRY`
- `0x18001245e`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS(
        ATL::CComModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  DWORD ModuleFileNameW; // eax
  int v7; // ebx
  signed int LastError; // eax
  unsigned __int16 *v9; // rcx
  WCHAR v10; // ax
  WCHAR *v11; // rdx
  void *v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h]
  int v15; // [rsp+3Ch] [rbp-C4h]
  __int64 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v19[528]; // [rsp+270h] [rbp+170h] BYREF

  v17 = 0;
  v14 = 0;
  v15 = 10;
  v13 = malloc(0x50u);
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(*((HMODULE *)ATL::_pModule + 1), Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
  {
    v7 = -2147024785;
  }
  else if ( ModuleFileNameW )
  {
    v9 = v19;
    v10 = Filename[0];
    if ( Filename[0] )
    {
      v11 = Filename;
      do
      {
        *v9++ = v10;
        if ( v10 == 39 )
          *v9++ = 39;
        v10 = *++v11;
      }
      while ( *v11 );
    }
    *v9 = 0;
    v7 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v13, L"Module", v19);
    if ( v7 >= 0 )
    {
      v16 = 0;
      if ( a3 )
        v7 = ATL::CRegObject::RegisterFromResource(
               (ATL::CRegObject *)&v13,
               Filename,
               (const unsigned __int16 *)a2,
               L"REGISTRY",
               1);
      else
        v7 = ATL::CRegObject::RegisterFromResource(
               (ATL::CRegObject *)&v13,
               Filename,
               (const unsigned __int16 *)a2,
               L"REGISTRY",
               0);
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012314  mov     [rsp-8+arg_0], rbx
0x180012319  mov     [rsp-8+arg_10], rsi
0x18001231e  push    rbp
0x18001231f  push    rdi
0x180012320  push    r14
0x180012322  lea     rbp, [rsp-5A0h]
0x18001232a  sub     rsp, 6A0h
0x180012331  mov     rax, cs:__security_cookie
0x180012338  xor     rax, rsp
0x18001233b  mov     [rbp+5B0h+var_20], rax
0x180012342  mov     edi, r8d
0x180012345  mov     esi, edx
0x180012347  xor     r14d, r14d
0x18001234a  mov     [rsp+6B0h+var_660], r14
0x18001234f  mov     [rsp+6B0h+var_678], r14d
0x180012354  mov     [rsp+6B0h+var_674], 0Ah
0x18001235c  lea     ecx, [r14+50h]; Size
0x180012360  call    cs:__imp_malloc
0x180012366  mov     [rsp+6B0h+var_680], rax
0x18001236b  xor     edx, edx; Val
0x18001236d  mov     r8d, 20Ah; Size
0x180012373  lea     rcx, [rsp+6B0h+Filename]; void *
0x180012378  call    memset_0
0x18001237d  mov     ebx, 104h
0x180012382  mov     r8d, ebx; nSize
0x180012385  lea     rdx, [rsp+6B0h+Filename]; lpFilename
0x18001238a  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x180012391  mov     rcx, [rcx+8]; hModule
0x180012395  call    cs:__imp_GetModuleFileNameW
0x18001239b  cmp     eax, ebx
0x18001239d  jnz     short loc_1800123A9
0x18001239f  mov     ebx, 8007006Fh
0x1800123a4  jmp     loc_180012476
0x1800123a9  test    eax, eax
0x1800123ab  jnz     short loc_1800123CB
0x1800123ad  call    cs:__imp_GetLastError
0x1800123b3  mov     ebx, eax
0x1800123b5  test    eax, eax
0x1800123b7  jle     loc_180012476
0x1800123bd  movzx   ebx, ax
0x1800123c0  or      ebx, 80070000h
0x1800123c6  jmp     loc_180012476
0x1800123cb  lea     rcx, [rbp+5B0h+var_440]
0x1800123d2  movzx   eax, [rsp+6B0h+Filename]
0x1800123d7  test    ax, ax
0x1800123da  jz      short loc_180012408
0x1800123dc  lea     rdx, [rsp+6B0h+Filename]
0x1800123e1  mov     r8d, 27h ; '''
0x1800123e7  mov     [rcx], ax
0x1800123ea  add     rcx, 2
0x1800123ee  cmp     ax, r8w
0x1800123f2  jnz     short loc_1800123FC
0x1800123f4  mov     [rcx], r8w
0x1800123f8  add     rcx, 2
0x1800123fc  add     rdx, 2
0x180012400  movzx   eax, word ptr [rdx]
0x180012403  test    ax, ax
0x180012406  jnz     short loc_1800123E7
0x180012408  mov     [rcx], r14w
0x18001240c  lea     r8, [rbp+5B0h+var_440]; unsigned __int16 *
0x180012413  lea     rdx, aModule; "Module"
0x18001241a  lea     rcx, [rsp+6B0h+var_680]; this
0x18001241f  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012424  mov     ebx, eax
0x180012426  test    eax, eax
0x180012428  js      short loc_180012476
0x18001242a  movzx   r8d, si; unsigned __int16 *
0x18001242e  mov     [rsp+6B0h+var_668], r14
0x180012433  test    edi, edi
0x180012435  jz      short loc_180012459
0x180012437  mov     [rsp+6B0h+var_690], 1; int
0x18001243f  lea     r9, aRegistry; "REGISTRY"
0x180012446  lea     rdx, [rsp+6B0h+Filename]; unsigned __int16 *
0x18001244b  lea     rcx, [rsp+6B0h+var_680]; this
0x180012450  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180012455  mov     ebx, eax
0x180012457  jmp     short loc_180012476
0x180012459  mov     [rsp+6B0h+var_690], r14d; int
0x18001245e  lea     r9, aRegistry; "REGISTRY"
0x180012465  lea     rdx, [rsp+6B0h+Filename]; unsigned __int16 *
0x18001246a  lea     rcx, [rsp+6B0h+var_680]; this
0x18001246f  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180012474  mov     ebx, eax
0x180012476  lea     rcx, [rsp+6B0h+var_680]; this
0x18001247b  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180012480  nop
0x180012481  mov     eax, ebx
0x180012483  mov     rcx, [rbp+5B0h+var_20]
0x18001248a  xor     rcx, rsp; StackCookie
0x18001248d  call    __security_check_cookie
0x180012492  lea     r11, [rsp+6B0h+var_10]
0x18001249a  mov     rbx, [r11+20h]
0x18001249e  mov     rsi, [r11+30h]
0x1800124a2  mov     rsp, r11
0x1800124a5  pop     r14
0x1800124a7  pop     rdi
0x1800124a8  pop     rbp
0x1800124a9  retn
```
