# PpfhLogEventSubscriberSuccess(ushort const *,ulong)

- ea: `0x180035a48`
- end: `0x180035b0f`
- name: `?PpfhLogEventSubscriberSuccess@@YAJPEBGK@Z`
- size: `199`
- prototype: `int __fastcall(const unsigned __int16 *, int)`
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
- `0x180035a48`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035ace`
- `ntdll!EtwEventWrite` at `0x180035ace`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventSubscriberSuccess(const unsigned __int16 *a1, int a2)
{
  int v2; // eax
  int v3; // ebx
  unsigned int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+20h] [rbp-48h] BYREF
  __int128 v7; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v10; // [rsp+78h] [rbp+10h] BYREF

  v10 = a2;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v2 = InitializeEventDataDescWithStr(&v6, a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_QWORD *)&v7 = &v10;
    *((_QWORD *)&v7 + 1) = 4;
    v5 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_SUBSCRIBER_NOTIFIED, 3, &v6);
    if ( v5 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x146,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v5,
               v6.Ptr);
    else
      return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v2,
      v6.Ptr);
    return v3;
  }
}

```

## disassembly

```asm
0x180035a48  mov     [rsp+arg_8], edx
0x180035a4c  push    rbx
0x180035a4d  sub     rsp, 60h
0x180035a51  mov     rax, cs:__security_cookie
0x180035a58  xor     rax, rsp
0x180035a5b  mov     [rsp+68h+var_18], rax
0x180035a60  xorps   xmm0, xmm0
0x180035a63  mov     rdx, rcx; unsigned __int16 *
0x180035a66  lea     rcx, [rsp+68h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x180035a6b  movups  xmmword ptr [rsp+68h+var_48.Ptr], xmm0; unsigned int
0x180035a70  movups  [rsp+68h+var_38], xmm0
0x180035a75  movups  [rsp+68h+var_28], xmm0
0x180035a7a  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035a7f  mov     ebx, eax
0x180035a81  test    eax, eax
0x180035a83  jns     short loc_180035AA2
0x180035a85  mov     rcx, [rsp+68h]; this
0x180035a8a  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035a91  mov     r9d, eax; char *
0x180035a94  mov     edx, 143h; void *
0x180035a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a9e  mov     eax, ebx
0x180035aa0  jmp     short loc_180035AFB
0x180035aa2  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035aa9  lea     rax, [rsp+68h+arg_8]
0x180035aae  lea     r9, [rsp+68h+var_48]
0x180035ab3  mov     qword ptr [rsp+68h+var_38], rax
0x180035ab8  mov     r8d, 3
0x180035abe  mov     qword ptr [rsp+68h+var_38+8], 4
0x180035ac7  lea     rdx, PCRPF_EVENT_SUBSCRIBER_NOTIFIED
0x180035ace  call    cs:__imp_EtwEventWrite
0x180035ad5  nop     dword ptr [rax+rax+00h]
0x180035ada  test    eax, eax
0x180035adc  jz      short loc_180035AF9
0x180035ade  mov     rcx, [rsp+68h]; this
0x180035ae3  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035aea  mov     r9d, eax; char *
0x180035aed  mov     edx, 146h; void *
0x180035af2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035af7  jmp     short loc_180035AFB
0x180035af9  xor     eax, eax
0x180035afb  mov     rcx, [rsp+68h+var_18]
0x180035b00  xor     rcx, rsp; StackCookie
0x180035b03  call    __security_check_cookie
0x180035b08  add     rsp, 60h
0x180035b0c  pop     rbx
0x180035b0d  retn
```
