# wil::slim_event_t<0>::wait(void)

- ea: `0x10038893`
- end: `0x100388e2`
- name: `?wait@?$slim_event_t@$0A@@wil@@QAE_NXZ`
- size: `79`
- prototype: `char __thiscall(volatile __int32 *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10038410`

## callees

- `0x10007605`
- `0x10038893`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100388ba`
- `KERNEL32!GetLastError` at `0x100388ba`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x100388b0`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x100388b0`

## string_xrefs

- `0x100388d8`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
char __thiscall wil::slim_event_t<0>::wait(volatile __int32 *this)
{
  int CompareAddress; // [esp+4h] [ebp-4h] BYREF

  do
  {
    if ( _InterlockedExchange(this, 0) )
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
0x10038893  mov     edi, edi
0x10038895  push    ebp; char *
0x10038896  mov     ebp, esp
0x10038898  push    ecx; unsigned int
0x10038899  push    esi; void *
0x1003889a  mov     esi, ecx
0x1003889c  xor     eax, eax
0x1003889e  xchg    eax, [esi]
0x100388a0  test    eax, eax
0x100388a2  jnz     short loc_100388CB
0x100388a4  push    0FFFFFFFFh; dwMilliseconds
0x100388a6  mov     [ebp+CompareAddress], eax
0x100388a9  lea     eax, [ebp+CompareAddress]
0x100388ac  push    4; AddressSize
0x100388ae  push    eax; CompareAddress
0x100388af  push    esi; Address
0x100388b0  call    ds:__imp__WaitOnAddress@16; WaitOnAddress(x,x,x,x)
0x100388b6  test    eax, eax
0x100388b8  jnz     short loc_1003889C
0x100388ba  call    ds:__imp__GetLastError@0; GetLastError()
0x100388c0  cmp     eax, 5B4h
0x100388c5  jnz     short loc_100388D0
0x100388c7  xor     al, al
0x100388c9  jmp     short loc_100388CD
0x100388cb  mov     al, 1
0x100388cd  pop     esi
0x100388ce  leave
0x100388cf  retn
0x100388d0  mov     ecx, [ebp+4]
0x100388d3  mov     edx, 0DBFh
0x100388d8  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x100388dd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
