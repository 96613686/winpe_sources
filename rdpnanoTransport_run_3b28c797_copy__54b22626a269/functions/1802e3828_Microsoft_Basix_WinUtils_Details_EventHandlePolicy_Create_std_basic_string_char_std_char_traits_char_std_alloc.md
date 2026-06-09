# Microsoft::Basix::WinUtils::Details::EventHandlePolicy::Create(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,_SECURITY_ATTRIBUTES *,bool,bool,ulong)

- ea: `0x1802e3828`
- end: `0x1802e393d`
- name: `?Create@EventHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAPEAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAU_SECURITY_ATTRIBUTES@@_N2K@Z`
- size: `277`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwDesiredAccess)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d301c`

## callees

- `0x180024700`
- `0x180027b84`
- `0x1802e3828`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802e38cc`
- `KERNEL32!GetLastError` at `0x1802e38cc`
- `KERNEL32!CreateEventExA` at `0x1802e386f`
- `KERNEL32!CreateEventExA` at `0x1802e386f`

## string_xrefs

- `0x1802e38af`: `CreateEventExA failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HANDLE __fastcall Microsoft::Basix::WinUtils::Details::EventHandlePolicy::Create(
        const CHAR *a1,
        struct _SECURITY_ATTRIBUTES *a2,
        unsigned __int8 a3,
        char a4,
        DWORD dwDesiredAccess)
{
  DWORD v5; // eax
  DWORD v6; // r8d
  HANDLE result; // rax
  Microsoft::Basix *v8; // rcx
  const struct std::error_category *v9; // rbx
  signed int LastError; // eax
  unsigned int v11; // edx
  __int128 v12; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-108h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v16[32]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[152]; // [rsp+B0h] [rbp-98h] BYREF

  v5 = a3;
  v6 = a3 | 2;
  if ( !a4 )
    v6 = v5;
  if ( *((_QWORD *)a1 + 2) )
  {
    if ( *((_QWORD *)a1 + 3) > 0xFu )
      a1 = *(const CHAR **)a1;
  }
  else
  {
    a1 = 0;
  }
  result = CreateEventExA(a2, a1, v6, dwDesiredAccess);
  if ( (((unsigned __int64)result + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    std::string::string(v14, (const char *)&Str1);
    std::string::string(v15, "C:\\__w\\1\\s\\src\\libbasix\\winutils\\winhandle.cpp");
    std::string::string(v16, "CreateEventExA failed");
    v9 = Microsoft::Basix::WindowsCategory(v8);
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    v12 = *(_OWORD *)std::error_code::error_code((std::error_code *)v13, v11, v9);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v12,
      (unsigned int)v16,
      (unsigned int)v15,
      34,
      (__int64)v14);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1802e3828  push    rbx
0x1802e382a  mov     eax, 140h
0x1802e382f  call    _alloca_probe
0x1802e3834  sub     rsp, rax
0x1802e3837  mov     r10, rdx
0x1802e383a  movzx   eax, r8b
0x1802e383e  mov     r8d, eax
0x1802e3841  or      r8d, 2
0x1802e3845  test    r9b, r9b
0x1802e3848  cmovz   r8d, eax; dwFlags
0x1802e384c  cmp     qword ptr [rcx+10h], 0
0x1802e3851  jnz     short loc_1802E3857
0x1802e3853  xor     ecx, ecx
0x1802e3855  jmp     short loc_1802E3861
0x1802e3857  cmp     qword ptr [rcx+18h], 0Fh
0x1802e385c  jbe     short loc_1802E3861
0x1802e385e  mov     rcx, [rcx]
0x1802e3861  mov     r9d, [rsp+148h+dwDesiredAccess]; dwDesiredAccess
0x1802e3869  mov     rdx, rcx; lpName
0x1802e386c  mov     rcx, r10; lpEventAttributes
0x1802e386f  call    cs:__imp_CreateEventExA
0x1802e3875  lea     rcx, [rax+1]
0x1802e3879  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1802e3880  jz      short loc_1802E388B
0x1802e3882  add     rsp, 140h
0x1802e3889  pop     rbx
0x1802e388a  retn
0x1802e388b  lea     rdx, Str1
0x1802e3892  lea     rcx, [rsp+148h+var_F8]
0x1802e3897  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e389c  nop
0x1802e389d  lea     rdx, aCW1SSrcLibbasi_78; "C:\\__w\\1\\s\\src\\libbasix\\winutils"...
0x1802e38a4  lea     rcx, [rsp+148h+var_D8]
0x1802e38a9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e38ae  nop
0x1802e38af  lea     rdx, aCreateeventexa; "CreateEventExA failed"
0x1802e38b6  lea     rcx, [rsp+148h+var_B8]
0x1802e38be  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1802e38c3  nop
0x1802e38c4  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1802e38c9  mov     rbx, rax
0x1802e38cc  call    cs:__imp_GetLastError
0x1802e38d2  movzx   edx, ax
0x1802e38d5  or      edx, 80070000h
0x1802e38db  test    eax, eax
0x1802e38dd  cmovle  edx, eax; int
0x1802e38e0  mov     r8, rbx; struct std::error_category *
0x1802e38e3  lea     rcx, [rsp+148h+var_108]; this
0x1802e38e8  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1802e38ed  movups  xmm0, xmmword ptr [rax]
0x1802e38f0  movdqu  [rsp+148h+var_118], xmm0
0x1802e38f6  lea     rax, [rsp+148h+var_F8]
0x1802e38fb  mov     [rsp+148h+var_120], rax
0x1802e3900  mov     [rsp+148h+var_128], 22h ; '"'
0x1802e3909  lea     r9, [rsp+148h+var_D8]
0x1802e390e  lea     r8, [rsp+148h+var_B8]
0x1802e3916  lea     rdx, [rsp+148h+var_118]
0x1802e391b  lea     rcx, [rsp+148h+pExceptionObject]
0x1802e3923  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1802e3928  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1802e392f  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1802e3937  call    _CxxThrowException
```
