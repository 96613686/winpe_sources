# SslDeleteKernelContext

- ea: `0x140023430`
- end: `0x14002348c`
- name: `SslDeleteKernelContext`
- size: `92`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140003e30`
- `0x140005170`
- `0x140023430`
- `0x14002fd60`
- `0x14002fdf0`

## pseudocode

```c
__int64 __fastcall SslDeleteKernelContext(_QWORD *Entry, unsigned __int64 *a2)
{
  __int64 v4; // rdx
  __int64 result; // rax
  unsigned int v6; // edi
  unsigned __int64 v7; // rcx

  GetExternalSchannelAlgorithmsDeferred();
  LOBYTE(v4) = 1;
  result = SslReferenceContext(Entry, v4);
  v6 = result;
  if ( (int)result < 0 )
  {
    *a2 = (unsigned __int64)Entry;
  }
  else
  {
    v7 = Entry[38];
    *a2 = v7;
    SchannelUnMapLsaToKernelContext(v7, (__int64)Entry);
    SslDerefContext(Entry);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140023430  mov     [rsp+arg_0], rbx
0x140023435  mov     [rsp+arg_8], rsi
0x14002343a  push    rdi
0x14002343b  sub     rsp, 20h
0x14002343f  mov     rsi, rdx
0x140023442  mov     rbx, rcx
0x140023445  call    GetExternalSchannelAlgorithmsDeferred
0x14002344a  mov     dl, 1
0x14002344c  mov     rcx, rbx
0x14002344f  call    SslReferenceContext
0x140023454  mov     edi, eax
0x140023456  test    eax, eax
0x140023458  js      short loc_140023487
0x14002345a  mov     rcx, [rbx+130h]; unsigned __int64
0x140023461  mov     rdx, rbx; unsigned __int64
0x140023464  mov     [rsi], rcx
0x140023467  call    ?SchannelUnMapLsaToKernelContext@@YAX_K0@Z; SchannelUnMapLsaToKernelContext(unsigned __int64,unsigned __int64)
0x14002346c  mov     rcx, rbx; Entry
0x14002346f  call    SslDerefContext
0x140023474  mov     eax, edi
0x140023476  mov     rbx, [rsp+28h+arg_0]
0x14002347b  mov     rsi, [rsp+28h+arg_8]
0x140023480  add     rsp, 20h
0x140023484  pop     rdi
0x140023485  retn
0x140023487  mov     [rsi], rbx
0x14002348a  jmp     short loc_140023476
```
