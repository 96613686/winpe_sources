# CUserProfile::CloneEnvBlock(void)

- ea: `0x180027a14`
- end: `0x180027ace`
- name: `?CloneEnvBlock@CUserProfile@@IEAAJXZ`
- size: `186`
- prototype: `int __fastcall(CUserProfile *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180027a14`
- `0x18002aef0`
- `0x18002d2d8`
- `0x180030e58`
- `0x180030ebc`
- `0x1800452e8`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180027a42`
- `ntdll!RtlDestroyEnvironment` at `0x180027a42`
- `ntdll!RtlCreateEnvironment` at `0x180027a5e`
- `ntdll!RtlCreateEnvironment` at `0x180027a5e`

## string_xrefs

- `0x180027a6d`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180027aa4`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180027a14  mov     [rsp+arg_8], rbx
0x180027a19  mov     [rsp+arg_10], rsi
0x180027a1e  push    rdi; int
0x180027a1f  sub     rsp, 20h
0x180027a23  lea     rbx, [rcx+108h]
0x180027a2a  mov     rsi, rcx
0x180027a2d  mov     rdi, [rbx]
0x180027a30  test    rdi, rdi
0x180027a33  jz      short loc_180027A52
0x180027a35  lea     rcx, [rsp+28h+arg_0]; this
0x180027a3a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180027a3f  mov     rcx, rdi; Environment
0x180027a42  call    cs:__imp_RtlDestroyEnvironment
0x180027a48  lea     rcx, [rsp+28h+arg_0]; this
0x180027a4d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180027a52  mov     rdx, rbx; Environment
0x180027a55  mov     qword ptr [rbx], 0
0x180027a5c  mov     cl, 1; Inherit
0x180027a5e  call    cs:__imp_RtlCreateEnvironment
0x180027a64  test    eax, eax
0x180027a66  jns     short loc_180027A83
0x180027a68  mov     rcx, [rsp+28h]; this
0x180027a6d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180027a74  mov     r9d, eax; char *
0x180027a77  mov     edx, 8ABh; void *
0x180027a7c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180027a81  jmp     short loc_180027ABE
0x180027a83  mov     r8, [rsi+98h]; unsigned __int16 *
0x180027a8a  lea     rdx, aUserprofile; "USERPROFILE"
0x180027a91  mov     rcx, rbx; void **
0x180027a94  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x180027a99  mov     ebx, eax
0x180027a9b  test    eax, eax
0x180027a9d  jns     short loc_180027ABC
0x180027a9f  mov     rcx, [rsp+28h]; this
0x180027aa4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180027aab  mov     r9d, eax; char *
0x180027aae  mov     edx, 8ACh; void *
0x180027ab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ab8  mov     eax, ebx
0x180027aba  jmp     short loc_180027ABE
0x180027abc  xor     eax, eax
0x180027abe  mov     rbx, [rsp+28h+arg_8]
0x180027ac3  mov     rsi, [rsp+28h+arg_10]
0x180027ac8  add     rsp, 20h
0x180027acc  pop     rdi
0x180027acd  retn
```
