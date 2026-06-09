# PpfhLogEventSubscriberError(ushort const *,ulong,long)

- ea: `0x180035960`
- end: `0x180035a40`
- name: `?PpfhLogEventSubscriberError@@YAJPEBGKJ@Z`
- size: `224`
- prototype: `int __fastcall(const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d1e8`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000dfe0`
- `0x18003535c`
- `0x180035960`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800359f9`
- `ntdll!EtwEventWrite` at `0x1800359f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventSubscriberError(const unsigned __int16 *a1, int a2, int a3)
{
  int v3; // eax
  int v4; // ebx
  unsigned int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+20h] [rbp-40h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  __int128 v9; // [rsp+40h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  int v11; // [rsp+78h] [rbp+18h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF

  v12 = a3;
  v11 = a2;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v3 = InitializeEventDataDescWithStr(&v7, a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)&v8 = &v11;
    *((_QWORD *)&v8 + 1) = 4;
    *(_QWORD *)&v9 = &v12;
    *((_QWORD *)&v9 + 1) = 4;
    v6 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_SUBSCRIBER_ERROR, 3, &v7);
    if ( v6 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x156,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v6,
               v7.Ptr);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v3,
      v7.Ptr);
    return v4;
  }
}

```

## disassembly

```asm
0x180035960  mov     [rsp-8+arg_18], rbx
0x180035965  mov     [rsp-8+arg_10], r8d
0x18003596a  mov     [rsp-8+arg_8], edx
0x18003596e  push    rbp
0x18003596f  mov     rbp, rsp
0x180035972  sub     rsp, 60h
0x180035976  mov     rax, cs:__security_cookie
0x18003597d  xor     rax, rsp
0x180035980  mov     [rbp+var_10], rax
0x180035984  xorps   xmm0, xmm0
0x180035987  mov     rdx, rcx; unsigned __int16 *
0x18003598a  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x18003598e  movups  xmmword ptr [rbp+var_40.Ptr], xmm0
0x180035992  movups  [rbp+var_30], xmm0
0x180035996  movups  [rbp+var_20], xmm0
0x18003599a  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18003599f  mov     ebx, eax
0x1800359a1  test    eax, eax
0x1800359a3  jns     short loc_1800359C1
0x1800359a5  mov     rcx, [rbp+8]; this
0x1800359a9  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800359b0  mov     r9d, eax; char *
0x1800359b3  mov     edx, 152h; void *
0x1800359b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800359bd  mov     eax, ebx
0x1800359bf  jmp     short loc_180035A25
0x1800359c1  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800359c8  lea     rax, [rbp+arg_8]
0x1800359cc  mov     qword ptr [rbp+var_30], rax
0x1800359d0  lea     r9, [rbp+var_40]
0x1800359d4  lea     rax, [rbp+arg_10]
0x1800359d8  mov     qword ptr [rbp+var_30+8], 4
0x1800359e0  mov     r8d, 3
0x1800359e6  mov     qword ptr [rbp+var_20], rax
0x1800359ea  lea     rdx, PCRPF_EVENT_SUBSCRIBER_ERROR
0x1800359f1  mov     qword ptr [rbp+var_20+8], 4
0x1800359f9  call    cs:__imp_EtwEventWrite
0x180035a00  nop     dword ptr [rax+rax+00h]
0x180035a05  test    eax, eax
0x180035a07  jz      short loc_180035A23
0x180035a09  mov     rcx, [rbp+8]; this
0x180035a0d  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035a14  mov     r9d, eax; char *
0x180035a17  mov     edx, 156h; void *
0x180035a1c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035a21  jmp     short loc_180035A25
0x180035a23  xor     eax, eax
0x180035a25  mov     rcx, [rbp+var_10]
0x180035a29  xor     rcx, rsp; StackCookie
0x180035a2c  call    __security_check_cookie
0x180035a31  mov     rbx, [rsp+60h+arg_18]
0x180035a39  add     rsp, 60h
0x180035a3d  pop     rbp
0x180035a3e  retn
```
