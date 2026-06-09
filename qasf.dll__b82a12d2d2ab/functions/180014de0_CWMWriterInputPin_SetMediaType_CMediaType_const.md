# CWMWriterInputPin::SetMediaType(CMediaType const *)

- ea: `0x180014de0`
- end: `0x180014e13`
- name: `?SetMediaType@CWMWriterInputPin@@UEAAJPEBVCMediaType@@@Z`
- size: `51`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000724c`
- `0x180014de0`
- `0x180014f78`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::SetMediaType(CWMWriterInputPin *this, const struct _AMMediaType *a2)
{
  __int64 result; // rax

  result = CMediaType::Set((struct _AMMediaType *)((char *)this + 104), a2);
  if ( (int)result >= 0 )
    return CWMWriterInputPin::SetWMSDKType(this, (const struct CMediaType *)a2);
  return result;
}

```

## disassembly

```asm
0x180014de0  mov     [rsp+arg_0], rbx
0x180014de5  push    rdi
0x180014de6  sub     rsp, 20h
0x180014dea  mov     rdi, rcx
0x180014ded  mov     rbx, rdx
0x180014df0  add     rcx, 68h ; 'h'; this
0x180014df4  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180014df9  test    eax, eax
0x180014dfb  js      short loc_180014E08
0x180014dfd  mov     rdx, rbx; struct CMediaType *
0x180014e00  mov     rcx, rdi; this
0x180014e03  call    ?SetWMSDKType@CWMWriterInputPin@@QEAAJPEBVCMediaType@@@Z; CWMWriterInputPin::SetWMSDKType(CMediaType const *)
0x180014e08  mov     rbx, [rsp+28h+arg_0]
0x180014e0d  add     rsp, 20h
0x180014e11  pop     rdi
0x180014e12  retn
```
