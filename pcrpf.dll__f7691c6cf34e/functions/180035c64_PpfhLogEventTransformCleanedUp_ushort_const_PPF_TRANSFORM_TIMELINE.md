# PpfhLogEventTransformCleanedUp(ushort const *,PPF_TRANSFORM_TIMELINE)

- ea: `0x180035c64`
- end: `0x180035d32`
- name: `?PpfhLogEventTransformCleanedUp@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@@Z`
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
- `0x180035c64`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035cec`
- `ntdll!EtwEventWrite` at `0x180035cec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventTransformCleanedUp(const unsigned __int16 *a1, unsigned int a2)
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
    v6 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_CLEANED_UP, 2, &v8);
    if ( v6 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x118,
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
      (void *)0x114,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
}

```

## disassembly

```asm
0x180035c64  mov     [rsp+arg_8], rbx
0x180035c69  push    rdi
0x180035c6a  sub     rsp, 50h
0x180035c6e  mov     rax, cs:__security_cookie
0x180035c75  xor     rax, rsp
0x180035c78  mov     [rsp+58h+var_10], rax
0x180035c7d  xorps   xmm0, xmm0
0x180035c80  mov     edi, edx
0x180035c82  mov     rdx, rcx; unsigned __int16 *
0x180035c85  lea     rcx, [rsp+58h+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x180035c8a  movups  xmmword ptr [rsp+58h+var_30.Ptr], xmm0
0x180035c8f  movups  [rsp+58h+var_20], xmm0
0x180035c94  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035c99  mov     ebx, eax
0x180035c9b  test    eax, eax
0x180035c9d  jns     short loc_180035CBC
0x180035c9f  mov     rcx, [rsp+58h]; this
0x180035ca4  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035cab  mov     r9d, eax; char *
0x180035cae  mov     edx, 114h; void *
0x180035cb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035cb8  mov     eax, ebx
0x180035cba  jmp     short loc_180035D19
0x180035cbc  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035cc3  lea     rax, [rsp+58h+var_38]
0x180035cc8  lea     r9, [rsp+58h+var_30]
0x180035ccd  mov     qword ptr [rsp+58h+var_20], rax
0x180035cd2  mov     r8d, 2
0x180035cd8  mov     [rsp+58h+var_38], edi; unsigned int
0x180035cdc  lea     rdx, PCRPF_EVENT_TRANSFORM_CLEANED_UP
0x180035ce3  mov     qword ptr [rsp+58h+var_20+8], 4
0x180035cec  call    cs:__imp_EtwEventWrite
0x180035cf3  nop     dword ptr [rax+rax+00h]
0x180035cf8  test    eax, eax
0x180035cfa  jz      short loc_180035D17
0x180035cfc  mov     rcx, [rsp+58h]; this
0x180035d01  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035d08  mov     r9d, eax; char *
0x180035d0b  mov     edx, 118h; void *
0x180035d10  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035d15  jmp     short loc_180035D19
0x180035d17  xor     eax, eax
0x180035d19  mov     rcx, [rsp+58h+var_10]
0x180035d1e  xor     rcx, rsp; StackCookie
0x180035d21  call    __security_check_cookie
0x180035d26  mov     rbx, [rsp+58h+arg_8]
0x180035d2b  add     rsp, 50h
0x180035d2f  pop     rdi
0x180035d30  retn
```
