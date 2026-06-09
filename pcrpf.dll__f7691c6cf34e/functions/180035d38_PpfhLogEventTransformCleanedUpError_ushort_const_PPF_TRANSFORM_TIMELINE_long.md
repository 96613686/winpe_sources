# PpfhLogEventTransformCleanedUpError(ushort const *,PPF_TRANSFORM_TIMELINE,long)

- ea: `0x180035d38`
- end: `0x180035e22`
- name: `?PpfhLogEventTransformCleanedUpError@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@J@Z`
- size: `234`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned int, int)`
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
- `0x180035d38`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035dd7`
- `ntdll!EtwEventWrite` at `0x180035dd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventTransformCleanedUpError(const unsigned __int16 *a1, unsigned int a2, int a3)
{
  int v4; // eax
  int v5; // ebx
  unsigned int v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+28h] [rbp-38h] BYREF
  __int128 v10; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  int v13; // [rsp+80h] [rbp+20h] BYREF

  v13 = a3;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v4 = InitializeEventDataDescWithStr(&v9, a1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *(_QWORD *)&v10 = &v8;
    v8 = a2;
    *(_QWORD *)&v11 = &v13;
    *((_QWORD *)&v10 + 1) = 4;
    *((_QWORD *)&v11 + 1) = 4;
    v7 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_CLEANED_UP_ERROR, 3, &v9);
    if ( v7 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x138,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v7,
               v8);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v4,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x180035d38  mov     [rsp-8+arg_8], rbx
0x180035d3d  mov     [rsp-8+arg_18], rdi
0x180035d42  mov     [rsp-8+arg_10], r8d
0x180035d47  push    rbp
0x180035d48  mov     rbp, rsp
0x180035d4b  sub     rsp, 60h
0x180035d4f  mov     rax, cs:__security_cookie
0x180035d56  xor     rax, rsp
0x180035d59  mov     [rbp+var_8], rax
0x180035d5d  xorps   xmm0, xmm0
0x180035d60  mov     edi, edx
0x180035d62  mov     rdx, rcx; unsigned __int16 *
0x180035d65  lea     rcx, [rbp+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180035d69  movups  xmmword ptr [rbp+var_38.Ptr], xmm0
0x180035d6d  movups  [rbp+var_28], xmm0
0x180035d71  movups  [rbp+var_18], xmm0
0x180035d75  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035d7a  mov     ebx, eax
0x180035d7c  test    eax, eax
0x180035d7e  jns     short loc_180035D9C
0x180035d80  mov     rcx, [rbp+8]; this
0x180035d84  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035d8b  mov     r9d, eax; char *
0x180035d8e  mov     edx, 133h; void *
0x180035d93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d98  mov     eax, ebx
0x180035d9a  jmp     short loc_180035E03
0x180035d9c  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035da3  lea     rax, [rbp+var_40]
0x180035da7  mov     qword ptr [rbp+var_28], rax
0x180035dab  lea     r9, [rbp+var_38]
0x180035daf  lea     rax, [rbp+arg_10]
0x180035db3  mov     [rbp+var_40], edi
0x180035db6  mov     r8d, 3
0x180035dbc  mov     qword ptr [rbp+var_18], rax
0x180035dc0  lea     rdx, PCRPF_EVENT_TRANSFORM_CLEANED_UP_ERROR
0x180035dc7  mov     qword ptr [rbp+var_28+8], 4
0x180035dcf  mov     qword ptr [rbp+var_18+8], 4
0x180035dd7  call    cs:__imp_EtwEventWrite
0x180035dde  nop     dword ptr [rax+rax+00h]
0x180035de3  test    eax, eax
0x180035de5  jz      short loc_180035E01
0x180035de7  mov     rcx, [rbp+8]; this
0x180035deb  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035df2  mov     r9d, eax; char *
0x180035df5  mov     edx, 138h; void *
0x180035dfa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035dff  jmp     short loc_180035E03
0x180035e01  xor     eax, eax
0x180035e03  mov     rcx, [rbp+var_8]
0x180035e07  xor     rcx, rsp; StackCookie
0x180035e0a  call    __security_check_cookie
0x180035e0f  lea     r11, [rsp+60h+var_s0]
0x180035e14  mov     rbx, [r11+18h]
0x180035e18  mov     rdi, [r11+28h]
0x180035e1c  mov     rsp, r11
0x180035e1f  pop     rbp
0x180035e20  retn
```
