# GetLineObjWithWriteLock

- ea: `0x18000381c`
- end: `0x18000388a`
- name: `GetLineObjWithWriteLock`
- size: `110`
- prototype: `__int64 __fastcall(const void *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003ba8`
- `0x180004520`

## callees

- `0x180001fe4`
- `0x180002508`
- `0x18000381c`
- `0x180007df8`

## string_xrefs

- `0x18000385e`: `GetLineObjWithWriteLock: obj(%p) has bad key(%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithWriteLock(const void *a1, _QWORD *a2)
{
  _DWORD *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  if ( (unsigned int)GetObjWithWriteLock(a1, &v5) )
    return 2147483691LL;
  if ( *v5 != 1263290702 )
  {
    TspLog(2, "GetLineObjWithWriteLock: obj(%p) has bad key(%x)", a1, *v5);
    ReleaseObjWriteLock(a1);
    return 2147483691LL;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000381c  mov     [rsp+arg_0], rbx
0x180003821  push    rdi
0x180003822  sub     rsp, 20h
0x180003826  mov     rdi, rdx
0x180003829  mov     [rsp+28h+arg_10], 0
0x180003832  lea     rdx, [rsp+28h+arg_10]
0x180003837  mov     rbx, rcx
0x18000383a  call    GetObjWithWriteLock
0x18000383f  test    eax, eax
0x180003841  jz      short loc_18000384A
0x180003843  mov     eax, 8000002Bh
0x180003848  jmp     short loc_18000387E
0x18000384a  mov     rax, [rsp+28h+arg_10]
0x18000384f  mov     r9d, [rax]
0x180003852  cmp     r9d, 4B4C494Eh
0x180003859  jz      short loc_180003879
0x18000385b  mov     r8, rbx
0x18000385e  lea     rdx, aGetlineobjwith_0; "GetLineObjWithWriteLock: obj(%p) has ba"...
0x180003865  mov     ecx, 2
0x18000386a  call    TspLog
0x18000386f  mov     rcx, rbx
0x180003872  call    ReleaseObjWriteLock
0x180003877  jmp     short loc_180003843
0x180003879  mov     [rdi], rax
0x18000387c  xor     eax, eax
0x18000387e  mov     rbx, [rsp+28h+arg_0]
0x180003883  add     rsp, 20h
0x180003887  pop     rdi
0x180003888  retn
```
