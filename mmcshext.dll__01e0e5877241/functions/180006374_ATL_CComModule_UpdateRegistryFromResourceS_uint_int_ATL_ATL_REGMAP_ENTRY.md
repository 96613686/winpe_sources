# ATL::CComModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006374`
- end: `0x18000650a`
- name: `?UpdateRegistryFromResourceS@CComModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `406`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006340`
- `0x180006360`

## callees

- `0x180002d4c`
- `0x180002e9c`
- `0x180004ed4`
- `0x180006374`
- `0x18000a582`
- `0x18000a5b0`

## import_xrefs

- `msvcrt!malloc` at `0x1800063c0`
- `msvcrt!malloc` at `0x1800063c0`
- `KERNEL32!GetModuleFileNameW` at `0x1800063f5`
- `KERNEL32!GetModuleFileNameW` at `0x1800063f5`
- `KERNEL32!GetLastError` at `0x18000640d`
- `KERNEL32!GetLastError` at `0x18000640d`

## string_xrefs

- `0x18000649f`: `REGISTRY`
- `0x1800064be`: `REGISTRY`

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
0x180006374  mov     [rsp-8+arg_0], rbx
0x180006379  mov     [rsp-8+arg_10], rsi
0x18000637e  push    rbp
0x18000637f  push    rdi
0x180006380  push    r14
0x180006382  lea     rbp, [rsp-5A0h]
0x18000638a  sub     rsp, 6A0h
0x180006391  mov     rax, cs:__security_cookie
0x180006398  xor     rax, rsp
0x18000639b  mov     [rbp+5B0h+var_20], rax
0x1800063a2  mov     edi, r8d
0x1800063a5  mov     esi, edx
0x1800063a7  xor     r14d, r14d
0x1800063aa  mov     [rsp+6B0h+var_660], r14
0x1800063af  mov     [rsp+6B0h+var_678], r14d
0x1800063b4  mov     [rsp+6B0h+var_674], 0Ah
0x1800063bc  lea     ecx, [r14+50h]; Size
0x1800063c0  call    cs:__imp_malloc
0x1800063c6  mov     [rsp+6B0h+var_680], rax
0x1800063cb  xor     edx, edx; Val
0x1800063cd  mov     r8d, 20Ah; Size
0x1800063d3  lea     rcx, [rsp+6B0h+Filename]; void *
0x1800063d8  call    memset_0
0x1800063dd  mov     ebx, 104h
0x1800063e2  mov     r8d, ebx; nSize
0x1800063e5  lea     rdx, [rsp+6B0h+Filename]; lpFilename
0x1800063ea  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x1800063f1  mov     rcx, [rcx+8]; hModule
0x1800063f5  call    cs:__imp_GetModuleFileNameW
0x1800063fb  cmp     eax, ebx
0x1800063fd  jnz     short loc_180006409
0x1800063ff  mov     ebx, 8007006Fh
0x180006404  jmp     loc_1800064D6
0x180006409  test    eax, eax
0x18000640b  jnz     short loc_18000642B
0x18000640d  call    cs:__imp_GetLastError
0x180006413  mov     ebx, eax
0x180006415  test    eax, eax
0x180006417  jle     loc_1800064D6
0x18000641d  movzx   ebx, ax
0x180006420  or      ebx, 80070000h
0x180006426  jmp     loc_1800064D6
0x18000642b  lea     rcx, [rbp+5B0h+var_440]
0x180006432  movzx   eax, [rsp+6B0h+Filename]
0x180006437  test    ax, ax
0x18000643a  jz      short loc_180006468
0x18000643c  lea     rdx, [rsp+6B0h+Filename]
0x180006441  mov     r8d, 27h ; '''
0x180006447  mov     [rcx], ax
0x18000644a  add     rcx, 2
0x18000644e  cmp     ax, r8w
0x180006452  jnz     short loc_18000645C
0x180006454  mov     [rcx], r8w
0x180006458  add     rcx, 2
0x18000645c  add     rdx, 2
0x180006460  movzx   eax, word ptr [rdx]
0x180006463  test    ax, ax
0x180006466  jnz     short loc_180006447
0x180006468  mov     [rcx], r14w
0x18000646c  lea     r8, [rbp+5B0h+var_440]; unsigned __int16 *
0x180006473  lea     rdx, String2; "Module"
0x18000647a  lea     rcx, [rsp+6B0h+var_680]; this
0x18000647f  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006484  mov     ebx, eax
0x180006486  test    eax, eax
0x180006488  js      short loc_1800064D6
0x18000648a  movzx   r8d, si; unsigned __int16 *
0x18000648e  mov     [rsp+6B0h+var_668], r14
0x180006493  test    edi, edi
0x180006495  jz      short loc_1800064B9
0x180006497  mov     [rsp+6B0h+var_690], 1; int
0x18000649f  lea     r9, aRegistry; "REGISTRY"
0x1800064a6  lea     rdx, [rsp+6B0h+Filename]; unsigned __int16 *
0x1800064ab  lea     rcx, [rsp+6B0h+var_680]; this
0x1800064b0  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800064b5  mov     ebx, eax
0x1800064b7  jmp     short loc_1800064D6
0x1800064b9  mov     [rsp+6B0h+var_690], r14d; int
0x1800064be  lea     r9, aRegistry; "REGISTRY"
0x1800064c5  lea     rdx, [rsp+6B0h+Filename]; unsigned __int16 *
0x1800064ca  lea     rcx, [rsp+6B0h+var_680]; this
0x1800064cf  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800064d4  mov     ebx, eax
0x1800064d6  lea     rcx, [rsp+6B0h+var_680]; this
0x1800064db  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800064e0  nop
0x1800064e1  mov     eax, ebx
0x1800064e3  mov     rcx, [rbp+5B0h+var_20]
0x1800064ea  xor     rcx, rsp; StackCookie
0x1800064ed  call    __security_check_cookie
0x1800064f2  lea     r11, [rsp+6B0h+var_10]
0x1800064fa  mov     rbx, [r11+20h]
0x1800064fe  mov     rsi, [r11+30h]
0x180006502  mov     rsp, r11
0x180006505  pop     r14
0x180006507  pop     rdi
0x180006508  pop     rbp
0x180006509  retn
```
