# CFaxCommon::UpdateRegistry(int)

- ea: `0x180004680`
- end: `0x180004800`
- name: `?UpdateRegistry@CFaxCommon@@SAJH@Z`
- size: `384`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002058`
- `0x18000212c`
- `0x180003794`
- `0x180004680`
- `0x180015cbe`
- `0x180015cf0`

## import_xrefs

- `msvcrt!malloc` at `0x1800046bd`
- `msvcrt!malloc` at `0x1800046bd`
- `KERNEL32!GetLastError` at `0x180004715`
- `KERNEL32!GetLastError` at `0x180004715`
- `KERNEL32!GetModuleFileNameW` at `0x1800046f2`
- `KERNEL32!GetModuleFileNameW` at `0x1800046f2`

## string_xrefs

- `0x1800047a2`: `REGISTRY`
- `0x1800047c0`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFaxCommon::UpdateRegistry(int a1)
{
  DWORD ModuleFileNameW; // eax
  int v3; // ebx
  signed int LastError; // eax
  unsigned __int16 *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rdx
  const unsigned __int16 *v8; // r8
  void *v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h]
  int v12; // [rsp+3Ch] [rbp-C4h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  __int64 v14; // [rsp+50h] [rbp-B0h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v16[528]; // [rsp+270h] [rbp+170h] BYREF

  v14 = 0;
  v11 = 0;
  v12 = 10;
  v10 = malloc(0x50u);
  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(*((HMODULE *)ATL::_pModule + 1), Filename, 0x104u);
  if ( ModuleFileNameW == 260 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v10);
    return (unsigned int)-2147024785;
  }
  else
  {
    if ( ModuleFileNameW )
    {
      v5 = v16;
      v6 = Filename[0];
      if ( Filename[0] )
      {
        v7 = Filename;
        do
        {
          *v5++ = v6;
          if ( v6 == 39 )
            *v5++ = 39;
          v6 = *++v7;
        }
        while ( *v7 );
      }
      *v5 = 0;
      v3 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v10, L"Module", v16);
      if ( v3 >= 0 )
      {
        v13 = 0;
        if ( a1 )
          v3 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v10, Filename, v8, L"REGISTRY", 1);
        else
          v3 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v10, Filename, v8, L"REGISTRY", 0);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v10);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004680  push    rbp
0x180004682  push    rbx
0x180004683  push    rsi
0x180004684  push    rdi
0x180004685  lea     rbp, [rsp-5A8h]
0x18000468d  sub     rsp, 6A8h
0x180004694  mov     rax, cs:__security_cookie
0x18000469b  xor     rax, rsp
0x18000469e  mov     [rbp+5C0h+var_30], rax
0x1800046a5  mov     edi, ecx
0x1800046a7  xor     esi, esi
0x1800046a9  mov     [rsp+6C0h+var_670], rsi
0x1800046ae  mov     [rsp+6C0h+var_688], esi
0x1800046b2  mov     [rsp+6C0h+var_684], 0Ah
0x1800046ba  lea     ecx, [rsi+50h]; Size
0x1800046bd  call    cs:__imp_malloc
0x1800046c3  mov     [rsp+6C0h+var_690], rax
0x1800046c8  xor     edx, edx; Val
0x1800046ca  mov     r8d, 20Ah; Size
0x1800046d0  lea     rcx, [rsp+6C0h+Filename]; void *
0x1800046d5  call    memset_0
0x1800046da  mov     ebx, 104h
0x1800046df  mov     r8d, ebx; nSize
0x1800046e2  lea     rdx, [rsp+6C0h+Filename]; lpFilename
0x1800046e7  mov     rcx, cs:?_pModule@ATL@@3PEAVCComModule@1@EA; ATL::CComModule * ATL::_pModule
0x1800046ee  mov     rcx, [rcx+8]; hModule
0x1800046f2  call    cs:__imp_GetModuleFileNameW
0x1800046f8  cmp     eax, ebx
0x1800046fa  jnz     short loc_180004711
0x1800046fc  lea     rcx, [rsp+6C0h+var_690]; this
0x180004701  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004706  nop
0x180004707  mov     ebx, 8007006Fh
0x18000470c  jmp     loc_1800047E3
0x180004711  test    eax, eax
0x180004713  jnz     short loc_180004733
0x180004715  call    cs:__imp_GetLastError
0x18000471b  mov     ebx, eax
0x18000471d  test    eax, eax
0x18000471f  jle     loc_1800047D8
0x180004725  movzx   ebx, ax
0x180004728  or      ebx, 80070000h
0x18000472e  jmp     loc_1800047D8
0x180004733  lea     rcx, [rbp+5C0h+var_450]
0x18000473a  movzx   eax, [rsp+6C0h+Filename]
0x18000473f  test    ax, ax
0x180004742  jz      short loc_180004770
0x180004744  lea     rdx, [rsp+6C0h+Filename]
0x180004749  mov     r8d, 27h ; '''
0x18000474f  mov     [rcx], ax
0x180004752  add     rcx, 2
0x180004756  cmp     ax, r8w
0x18000475a  jnz     short loc_180004764
0x18000475c  mov     [rcx], r8w
0x180004760  add     rcx, 2
0x180004764  add     rdx, 2
0x180004768  movzx   eax, word ptr [rdx]
0x18000476b  test    ax, ax
0x18000476e  jnz     short loc_18000474F
0x180004770  mov     [rcx], si
0x180004773  lea     r8, [rbp+5C0h+var_450]; unsigned __int16 *
0x18000477a  lea     rdx, String2; "Module"
0x180004781  lea     rcx, [rsp+6C0h+var_690]; this
0x180004786  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000478b  mov     ebx, eax
0x18000478d  test    eax, eax
0x18000478f  js      short loc_1800047D8
0x180004791  mov     [rsp+6C0h+var_678], rsi
0x180004796  test    edi, edi
0x180004798  jz      short loc_1800047BC
0x18000479a  mov     [rsp+6C0h+var_6A0], 1; int
0x1800047a2  lea     r9, aRegistry; "REGISTRY"
0x1800047a9  lea     rdx, [rsp+6C0h+Filename]; unsigned __int16 *
0x1800047ae  lea     rcx, [rsp+6C0h+var_690]; this
0x1800047b3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800047b8  mov     ebx, eax
0x1800047ba  jmp     short loc_1800047D8
0x1800047bc  mov     [rsp+6C0h+var_6A0], esi; int
0x1800047c0  lea     r9, aRegistry; "REGISTRY"
0x1800047c7  lea     rdx, [rsp+6C0h+Filename]; unsigned __int16 *
0x1800047cc  lea     rcx, [rsp+6C0h+var_690]; this
0x1800047d1  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800047d6  mov     ebx, eax
0x1800047d8  lea     rcx, [rsp+6C0h+var_690]; this
0x1800047dd  call    ??1CRegObject@ATL@@QEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800047e2  nop
0x1800047e3  mov     eax, ebx
0x1800047e5  mov     rcx, [rbp+5C0h+var_30]
0x1800047ec  xor     rcx, rsp; StackCookie
0x1800047ef  call    __security_check_cookie
0x1800047f4  add     rsp, 6A8h
0x1800047fb  pop     rdi
0x1800047fc  pop     rsi
0x1800047fd  pop     rbx
0x1800047fe  pop     rbp
0x1800047ff  retn
```
