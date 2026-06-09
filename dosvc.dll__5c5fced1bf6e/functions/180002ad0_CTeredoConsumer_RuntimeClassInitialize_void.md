# CTeredoConsumer::RuntimeClassInitialize(void)

- ea: `0x180002ad0`
- end: `0x180002b2b`
- name: `?RuntimeClassInitialize@CTeredoConsumer@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CTeredoConsumer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003d28`

## callees

- `0x180002ad0`
- `0x180003290`
- `0x180005e7c`

## import_xrefs

- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x180002af6`
- `ext-ms-win-networking-teredo-l1-1-0!TeredoExtAcquireTeredoConsumerHandle` at `0x180002af6`

## string_xrefs

- `0x180002b07`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CTeredoConsumer::RuntimeClassInitialize(CTeredoConsumer *this)
{
  int v3; // eax
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !(unsigned __int8)IsTeredoExtAcquireTeredoConsumerHandlePresent() )
    return 2147500033LL;
  v3 = TeredoExtAcquireTeredoConsumerHandle(2, (char *)this + 16);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF,
    (int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
    (const char *)(unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x180002ad0  push    rbx; int
0x180002ad2  sub     rsp, 20h
0x180002ad6  mov     rbx, rcx
0x180002ad9  call    IsTeredoExtAcquireTeredoConsumerHandlePresent
0x180002ade  test    al, al
0x180002ae0  jnz     short loc_180002AED
0x180002ae2  mov     eax, 80004001h
0x180002ae7  add     rsp, 20h
0x180002aeb  pop     rbx
0x180002aec  retn
0x180002aed  lea     rdx, [rbx+10h]
0x180002af1  mov     ecx, 2
0x180002af6  call    cs:__imp_TeredoExtAcquireTeredoConsumerHandle
0x180002afc  mov     ebx, eax
0x180002afe  test    eax, eax
0x180002b00  jns     short loc_180002B23
0x180002b02  mov     rcx, [rsp+28h]; this
0x180002b07  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180002b0e  mov     r9d, eax; char *
0x180002b11  mov     edx, 0Fh; void *
0x180002b16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b1b  mov     eax, ebx
0x180002b1d  add     rsp, 20h
0x180002b21  pop     rbx
0x180002b22  retn
0x180002b23  xor     eax, eax
0x180002b25  add     rsp, 20h
0x180002b29  pop     rbx
0x180002b2a  retn
```
