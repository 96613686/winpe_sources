# wil::slim_event_t<1>::wait(void)

- ea: `0x1003883c`
- end: `0x1003888c`
- name: `?wait@?$slim_event_t@$00@wil@@QAE_NXZ`
- size: `80`
- prototype: `char __thiscall(_DWORD *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100380fb`

## callees

- `0x10007605`
- `0x1003883c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10038864`
- `KERNEL32!GetLastError` at `0x10038864`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1003885a`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x1003885a`

## string_xrefs

- `0x10038882`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
char __thiscall wil::slim_event_t<1>::wait(_DWORD *this)
{
  int CompareAddress; // [esp+4h] [ebp-4h] BYREF

  do
  {
    if ( *this )
      return 1;
    CompareAddress = 0;
  }
  while ( WaitOnAddress(this, &CompareAddress, 4u, 0xFFFFFFFF) );
  if ( GetLastError() != 1460 )
    wil::details::in1diag3::FailFast_Unexpected((wil::details::in1diag3 *)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h");
  return 0;
}

```

## disassembly

```asm
0x1003883c  mov     edi, edi
0x1003883e  push    ebp; char *
0x1003883f  mov     ebp, esp
0x10038841  push    ecx; unsigned int
0x10038842  push    esi; void *
0x10038843  mov     esi, ecx
0x10038845  cmp     dword ptr [esi], 0
0x10038848  jnz     short loc_10038875
0x1003884a  push    0FFFFFFFFh; dwMilliseconds
0x1003884c  push    4; AddressSize
0x1003884e  lea     eax, [ebp+CompareAddress]
0x10038851  mov     [ebp+CompareAddress], 0
0x10038858  push    eax; CompareAddress
0x10038859  push    esi; Address
0x1003885a  call    ds:__imp__WaitOnAddress@16; WaitOnAddress(x,x,x,x)
0x10038860  test    eax, eax
0x10038862  jnz     short loc_10038845
0x10038864  call    ds:__imp__GetLastError@0; GetLastError()
0x1003886a  cmp     eax, 5B4h
0x1003886f  jnz     short loc_1003887A
0x10038871  xor     al, al
0x10038873  jmp     short loc_10038877
0x10038875  mov     al, 1
0x10038877  pop     esi
0x10038878  leave
0x10038879  retn
0x1003887a  mov     ecx, [ebp+4]
0x1003887d  mov     edx, 0DBFh
0x10038882  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10038887  call    ?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
