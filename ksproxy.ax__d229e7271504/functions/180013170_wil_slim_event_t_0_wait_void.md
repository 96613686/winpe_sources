# wil::slim_event_t<0>::wait(void)

- ea: `0x180013170`
- end: `0x1800131e3`
- name: `?wait@?$slim_event_t@$0A@@wil@@QEAA_NXZ`
- size: `115`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800119f0`

## callees

- `0x180013170`
- `0x1800131ec`
- `0x180021db4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800131ac`
- `KERNEL32!GetLastError` at `0x1800131ac`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001319c`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001319c`

## string_xrefs

- `0x1800131c8`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
char __fastcall wil::slim_event_t<0>::wait(__int64 a1)
{
  volatile void *v2; // rcx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int CompareAddress; // [rsp+38h] [rbp+10h] BYREF

  do
  {
    if ( (unsigned __int8)wil::slim_event_t<0>::TryAcquireEvent(a1) )
      return 1;
    CompareAddress = 0;
  }
  while ( WaitOnAddress(v2, &CompareAddress, 4u, 0xFFFFFFFF) );
  if ( GetLastError() != 1460 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  return 0;
}

```

## disassembly

```asm
0x180013170  push    rbx
0x180013172  sub     rsp, 20h
0x180013176  mov     rbx, rcx
0x180013179  mov     rcx, rbx
0x18001317c  call    ?TryAcquireEvent@?$slim_event_t@$0A@@wil@@AEAA_NXZ; wil::slim_event_t<0>::TryAcquireEvent(void)
0x180013181  test    al, al
0x180013183  jnz     short loc_1800131DA
0x180013185  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180013189  mov     [rsp+28h+CompareAddress], 0
0x180013191  mov     r8d, 4; AddressSize
0x180013197  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x18001319c  call    cs:__imp_WaitOnAddress
0x1800131a3  nop     dword ptr [rax+rax+00h]
0x1800131a8  test    eax, eax
0x1800131aa  jnz     short loc_180013179
0x1800131ac  call    cs:__imp_GetLastError
0x1800131b3  nop     dword ptr [rax+rax+00h]
0x1800131b8  cmp     eax, 5B4h
0x1800131bd  jnz     short loc_1800131C3
0x1800131bf  xor     al, al
0x1800131c1  jmp     short loc_1800131DC
0x1800131c3  mov     rcx, [rsp+28h]; this
0x1800131c8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800131cf  mov     edx, 0DBFh; void *
0x1800131d4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800131da  mov     al, 1
0x1800131dc  add     rsp, 20h
0x1800131e0  pop     rbx
0x1800131e1  retn
```
