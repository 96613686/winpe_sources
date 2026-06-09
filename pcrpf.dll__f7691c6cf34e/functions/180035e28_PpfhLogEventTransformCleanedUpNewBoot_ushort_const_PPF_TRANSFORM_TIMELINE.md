# PpfhLogEventTransformCleanedUpNewBoot(ushort const *,PPF_TRANSFORM_TIMELINE)

- ea: `0x180035e28`
- end: `0x180035ef6`
- name: `?PpfhLogEventTransformCleanedUpNewBoot@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@@Z`
- size: `206`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800107e8`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000dfe0`
- `0x18003535c`
- `0x180035e28`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035eb0`
- `ntdll!EtwEventWrite` at `0x180035eb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventTransformCleanedUpNewBoot(const unsigned __int16 *a1, unsigned int a2)
{
  int v3; // eax
  int v4; // ebx
  unsigned int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+28h] [rbp-30h] BYREF
  __int128 v9; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v9 = 0;
  v3 = InitializeEventDataDescWithStr(&v8, a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)&v9 = &v7;
    v7 = a2;
    *((_QWORD *)&v9 + 1) = 4;
    v6 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_CLEANED_UP_NEW_BOOT, 2, &v8);
    if ( v6 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x127,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v6,
               v7);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
}

```

## disassembly

```asm
0x180035e28  mov     [rsp+arg_8], rbx
0x180035e2d  push    rdi
0x180035e2e  sub     rsp, 50h
0x180035e32  mov     rax, cs:__security_cookie
0x180035e39  xor     rax, rsp
0x180035e3c  mov     [rsp+58h+var_10], rax
0x180035e41  xorps   xmm0, xmm0
0x180035e44  mov     edi, edx
0x180035e46  mov     rdx, rcx; unsigned __int16 *
0x180035e49  lea     rcx, [rsp+58h+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x180035e4e  movups  xmmword ptr [rsp+58h+var_30.Ptr], xmm0
0x180035e53  movups  [rsp+58h+var_20], xmm0
0x180035e58  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035e5d  mov     ebx, eax
0x180035e5f  test    eax, eax
0x180035e61  jns     short loc_180035E80
0x180035e63  mov     rcx, [rsp+58h]; this
0x180035e68  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035e6f  mov     r9d, eax; char *
0x180035e72  mov     edx, 123h; void *
0x180035e77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e7c  mov     eax, ebx
0x180035e7e  jmp     short loc_180035EDD
0x180035e80  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035e87  lea     rax, [rsp+58h+var_38]
0x180035e8c  lea     r9, [rsp+58h+var_30]
0x180035e91  mov     qword ptr [rsp+58h+var_20], rax
0x180035e96  mov     r8d, 2
0x180035e9c  mov     [rsp+58h+var_38], edi; unsigned int
0x180035ea0  lea     rdx, PCRPF_EVENT_TRANSFORM_CLEANED_UP_NEW_BOOT
0x180035ea7  mov     qword ptr [rsp+58h+var_20+8], 4
0x180035eb0  call    cs:__imp_EtwEventWrite
0x180035eb7  nop     dword ptr [rax+rax+00h]
0x180035ebc  test    eax, eax
0x180035ebe  jz      short loc_180035EDB
0x180035ec0  mov     rcx, [rsp+58h]; this
0x180035ec5  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035ecc  mov     r9d, eax; char *
0x180035ecf  mov     edx, 127h; void *
0x180035ed4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035ed9  jmp     short loc_180035EDD
0x180035edb  xor     eax, eax
0x180035edd  mov     rcx, [rsp+58h+var_10]
0x180035ee2  xor     rcx, rsp; StackCookie
0x180035ee5  call    __security_check_cookie
0x180035eea  mov     rbx, [rsp+58h+arg_8]
0x180035eef  add     rsp, 50h
0x180035ef3  pop     rdi
0x180035ef4  retn
```
