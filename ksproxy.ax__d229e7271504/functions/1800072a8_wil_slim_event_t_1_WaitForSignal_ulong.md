# wil::slim_event_t<1>::WaitForSignal(ulong)

- ea: `0x1800072a8`
- end: `0x180007310`
- name: `?WaitForSignal@?$slim_event_t@$00@wil@@AEAA_NK@Z`
- size: `104`
- prototype: `bool __fastcall(volatile void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007114`

## callees

- `0x1800072a8`
- `0x180021db4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800072da`
- `KERNEL32!GetLastError` at `0x1800072da`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800072c8`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1800072c8`

## string_xrefs

- `0x1800072f2`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall wil::slim_event_t<1>::WaitForSignal(volatile void *a1)
{
  BOOL v1; // ebx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int CompareAddress; // [rsp+38h] [rbp+10h] BYREF

  CompareAddress = 0;
  v1 = WaitOnAddress(a1, &CompareAddress, 4u, 0xFFFFFFFF);
  if ( !v1 && GetLastError() != 1460 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
  return v1;
}

```

## disassembly

```asm
0x1800072a8  mov     [rsp+CompareAddress], edx
0x1800072ac  push    rbx
0x1800072ad  sub     rsp, 20h
0x1800072b1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800072b5  mov     [rsp+28h+CompareAddress], 0
0x1800072bd  mov     r8d, 4; AddressSize
0x1800072c3  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x1800072c8  call    cs:__imp_WaitOnAddress
0x1800072cf  nop     dword ptr [rax+rax+00h]
0x1800072d4  mov     ebx, eax
0x1800072d6  test    eax, eax
0x1800072d8  jnz     short loc_180007304
0x1800072da  call    cs:__imp_GetLastError
0x1800072e1  nop     dword ptr [rax+rax+00h]
0x1800072e6  cmp     eax, 5B4h
0x1800072eb  jz      short loc_180007304
0x1800072ed  mov     rcx, [rsp+28h]; this
0x1800072f2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800072f9  mov     edx, 0DBFh; void *
0x1800072fe  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007304  test    ebx, ebx
0x180007306  setnz   al
0x180007309  add     rsp, 20h
0x18000730d  pop     rbx
0x18000730e  retn
```
