# PpfhLogEventGenericActivityError(ushort const *,long)

- ea: `0x180035678`
- end: `0x18003573a`
- name: `?PpfhLogEventGenericActivityError@@YAJPEBGJ@Z`
- size: `194`
- prototype: `int __fastcall(const unsigned __int16 *, int)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001b030`
- `0x18001b080`
- `0x18001b0d0`
- `0x18001b110`
- `0x18001b520`
- `0x18001b560`
- `0x18001b900`
- `0x18004f450`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000dfe0`
- `0x18003535c`
- `0x180035678`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800356f9`
- `ntdll!EtwEventWrite` at `0x1800356f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall PpfhLogEventGenericActivityError(const unsigned __int16 *a1, int a2)
{
  int v2; // eax
  int v3; // ebx
  unsigned int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+20h] [rbp-38h] BYREF
  __int128 v7; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = a2;
  v6 = 0;
  v7 = 0;
  v2 = InitializeEventDataDescWithStr(&v6, a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_QWORD *)&v7 = &v9;
    *((_QWORD *)&v7 + 1) = 4;
    v5 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_GENERIC_ACTIVITY_ERROR, 2, &v6);
    if ( v5 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1BB,
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
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v2,
      v6.Ptr);
    return v3;
  }
}

```

## disassembly

```asm
0x180035678  mov     [rsp+arg_8], edx
0x18003567c  push    rbx
0x18003567d  sub     rsp, 50h
0x180035681  mov     rax, cs:__security_cookie
0x180035688  xor     rax, rsp
0x18003568b  mov     [rsp+58h+var_18], rax
0x180035690  xorps   xmm0, xmm0
0x180035693  mov     rdx, rcx; unsigned __int16 *
0x180035696  lea     rcx, [rsp+58h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18003569b  movups  xmmword ptr [rsp+58h+var_38.Ptr], xmm0; unsigned int
0x1800356a0  movups  [rsp+58h+var_28], xmm0
0x1800356a5  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800356aa  mov     ebx, eax
0x1800356ac  test    eax, eax
0x1800356ae  jns     short loc_1800356CD
0x1800356b0  mov     rcx, [rsp+58h]; this
0x1800356b5  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800356bc  mov     r9d, eax; char *
0x1800356bf  mov     edx, 1B8h; void *
0x1800356c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800356c9  mov     eax, ebx
0x1800356cb  jmp     short loc_180035726
0x1800356cd  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800356d4  lea     rax, [rsp+58h+arg_8]
0x1800356d9  lea     r9, [rsp+58h+var_38]
0x1800356de  mov     qword ptr [rsp+58h+var_28], rax
0x1800356e3  mov     r8d, 2
0x1800356e9  mov     qword ptr [rsp+58h+var_28+8], 4
0x1800356f2  lea     rdx, PCRPF_EVENT_GENERIC_ACTIVITY_ERROR
0x1800356f9  call    cs:__imp_EtwEventWrite
0x180035700  nop     dword ptr [rax+rax+00h]
0x180035705  test    eax, eax
0x180035707  jz      short loc_180035724
0x180035709  mov     rcx, [rsp+58h]; this
0x18003570e  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035715  mov     r9d, eax; char *
0x180035718  mov     edx, 1BBh; void *
0x18003571d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035722  jmp     short loc_180035726
0x180035724  xor     eax, eax
0x180035726  mov     rcx, [rsp+58h+var_18]
0x18003572b  xor     rcx, rsp; StackCookie
0x18003572e  call    __security_check_cookie
0x180035733  add     rsp, 50h
0x180035737  pop     rbx
0x180035738  retn
```
