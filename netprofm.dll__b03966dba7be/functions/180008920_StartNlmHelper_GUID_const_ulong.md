# StartNlmHelper(_GUID const *,ulong)

- ea: `0x180008920`
- end: `0x1800089f2`
- name: `?StartNlmHelper@@YAKPEBU_GUID@@K@Z`
- size: `210`
- prototype: `unsigned int __fastcall(const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180008920`
- `0x180008b60`
- `0x1800120d0`
- `0x180012f40`
- `0x180043010`

## string_xrefs

- `0x1800089dc`: `onecore\net\netprofiles\service\src\public\dll\netshhelper.cpp`

## pseudocode

```c
__int64 __fastcall StartNlmHelper(const struct _GUID *a1)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v4; // [rsp+20h] [rbp-88h] BYREF
  const wchar_t *v5; // [rsp+28h] [rbp-80h]
  __int128 v6; // [rsp+30h] [rbp-78h]
  int v7; // [rsp+40h] [rbp-68h]
  int v8; // [rsp+48h] [rbp-60h]
  __int64 v9; // [rsp+50h] [rbp-58h]
  int v10; // [rsp+58h] [rbp-50h]
  struct _CMD_GROUP_ENTRY near **v11; // [rsp+60h] [rbp-48h]
  __int64 v12; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  memset_0(&v4, 0, 0x70u);
  v4 = 0;
  v5 = L"nlm";
  v7 = 24;
  v11 = &g_nlmCmdGroups;
  v6 = xmmword_180046560;
  v12 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 4;
  v1 = ((__int64 (__fastcall *)(unsigned int *))g_netshRegisterContext)(&v4);
  v2 = v1;
  if ( v1 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\dll\\netshhelper.cpp",
      (const char *)v1,
      v4);
  return v2;
}

```

## disassembly

```asm
0x180008920  push    rbx
0x180008922  sub     rsp, 0A0h
0x180008929  mov     rax, cs:__security_cookie
0x180008930  xor     rax, rsp
0x180008933  mov     [rsp+0A8h+var_18], rax
0x18000893b  xor     edx, edx; Val
0x18000893d  lea     rcx, [rsp+0A8h+var_88]; void *
0x180008942  lea     r8d, [rdx+70h]; Size
0x180008946  call    memset_0
0x18000894b  movups  xmm0, cs:xmmword_180046560
0x180008952  lea     rax, aNlm; "nlm"
0x180008959  mov     [rsp+0A8h+var_88], 0; unsigned int
0x180008961  mov     [rsp+0A8h+var_80], rax
0x180008966  lea     rcx, [rsp+0A8h+var_88]
0x18000896b  lea     rax, ?g_nlmCmdGroups@@3PAU_CMD_GROUP_ENTRY@@A; _CMD_GROUP_ENTRY near * g_nlmCmdGroups
0x180008972  mov     [rsp+0A8h+var_68], 18h
0x18000897a  mov     [rsp+0A8h+var_48], rax
0x18000897f  mov     rax, cs:?g_netshRegisterContext@@3P6AKPEBU_NS_CONTEXT_ATTRIBUTES@@@ZEA; ulong (*g_netshRegisterContext)(_NS_CONTEXT_ATTRIBUTES const *)
0x180008986  movdqu  [rsp+0A8h+var_78], xmm0
0x18000898c  mov     [rsp+0A8h+var_38], 0
0x180008995  mov     [rsp+0A8h+var_60], 0
0x18000899d  mov     [rsp+0A8h+var_58], 0
0x1800089a6  mov     [rsp+0A8h+var_50], 4
0x1800089ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b3  mov     ebx, eax
0x1800089b5  test    eax, eax
0x1800089b7  jnz     short loc_1800089D4
0x1800089b9  mov     eax, ebx
0x1800089bb  mov     rcx, [rsp+0A8h+var_18]
0x1800089c3  xor     rcx, rsp; StackCookie
0x1800089c6  call    __security_check_cookie
0x1800089cb  add     rsp, 0A0h
0x1800089d2  pop     rbx
0x1800089d3  retn
0x1800089d4  mov     rcx, [rsp+0A8h]; this
0x1800089dc  lea     r8, aOnecoreNetNetp_12; "onecore\\net\\netprofiles\\service\\src"...
0x1800089e3  mov     r9d, ebx; char *
0x1800089e6  mov     edx, 78h ; 'x'; void *
0x1800089eb  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800089f0  jmp     short loc_1800089B9
```
