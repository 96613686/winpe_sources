# CUserProfile::CloneEnvBlock(void)

- ea: `0x180029908`
- end: `0x1800299cf`
- name: `?CloneEnvBlock@CUserProfile@@IEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x180029908`
- `0x180030ad0`
- `0x180032894`
- `0x180032900`
- `0x1800364c8`
- `0x1800472a4`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180029936`
- `ntdll!RtlDestroyEnvironment` at `0x180029936`
- `ntdll!RtlCreateEnvironment` at `0x180029958`
- `ntdll!RtlCreateEnvironment` at `0x180029958`

## string_xrefs

- `0x18002996d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800299a4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
int __fastcall CUserProfile::CloneEnvBlock(CUserProfile *this)
{
  PWSTR *v1; // rbx
  WCHAR *v3; // rdi
  NTSTATUS Environment; // eax
  int v5; // r9d
  int v7; // eax
  int v8; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v11; // [rsp+30h] [rbp+8h] BYREF

  v1 = (PWSTR *)((char *)this + 264);
  v3 = (WCHAR *)*((_QWORD *)this + 33);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
    RtlDestroyEnvironment(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
  }
  *v1 = 0;
  Environment = RtlCreateEnvironment(1u, v1);
  if ( Environment < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x8AB,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
             (const char *)(unsigned int)Environment,
             v9);
  v7 = SetEnvvar((void **)v1, L"USERPROFILE", *((const unsigned __int16 **)this + 19), v5);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8AC,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v7,
    v9);
  return v8;
}

```

## disassembly

```asm
0x180029908  mov     [rsp+arg_8], rbx
0x18002990d  mov     [rsp+arg_10], rsi
0x180029912  push    rdi; int
0x180029913  sub     rsp, 20h
0x180029917  lea     rbx, [rcx+108h]
0x18002991e  mov     rsi, rcx
0x180029921  mov     rdi, [rbx]
0x180029924  test    rdi, rdi
0x180029927  jz      short loc_18002994C
0x180029929  lea     rcx, [rsp+28h+arg_0]; this
0x18002992e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180029933  mov     rcx, rdi; Environment
0x180029936  call    cs:__imp_RtlDestroyEnvironment
0x18002993d  nop     dword ptr [rax+rax+00h]
0x180029942  lea     rcx, [rsp+28h+arg_0]; this
0x180029947  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002994c  mov     rdx, rbx; Environment
0x18002994f  mov     qword ptr [rbx], 0
0x180029956  mov     cl, 1; Inherit
0x180029958  call    cs:__imp_RtlCreateEnvironment
0x18002995f  nop     dword ptr [rax+rax+00h]
0x180029964  test    eax, eax
0x180029966  jns     short loc_180029983
0x180029968  mov     rcx, [rsp+28h]; this
0x18002996d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180029974  mov     r9d, eax; char *
0x180029977  mov     edx, 8ABh; void *
0x18002997c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180029981  jmp     short loc_1800299BE
0x180029983  mov     r8, [rsi+98h]; unsigned __int16 *
0x18002998a  lea     rdx, aUserprofile; "USERPROFILE"
0x180029991  mov     rcx, rbx; void **
0x180029994  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x180029999  mov     ebx, eax
0x18002999b  test    eax, eax
0x18002999d  jns     short loc_1800299BC
0x18002999f  mov     rcx, [rsp+28h]; this
0x1800299a4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800299ab  mov     r9d, eax; char *
0x1800299ae  mov     edx, 8ACh; void *
0x1800299b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299b8  mov     eax, ebx
0x1800299ba  jmp     short loc_1800299BE
0x1800299bc  xor     eax, eax
0x1800299be  mov     rbx, [rsp+28h+arg_8]
0x1800299c3  mov     rsi, [rsp+28h+arg_10]
0x1800299c8  add     rsp, 20h
0x1800299cc  pop     rdi
0x1800299cd  retn
```
