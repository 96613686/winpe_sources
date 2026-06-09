# GetLineObjWithReadLock

- ea: `0x1800037a8`
- end: `0x180003816`
- name: `GetLineObjWithReadLock`
- size: `110`
- prototype: `__int64 __fastcall(const void *, _QWORD *)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x18000338c`
- `0x180003ba8`
- `0x180004670`
- `0x180004880`
- `0x1800049a0`
- `0x180004ec0`
- `0x1800051d0`
- `0x180005320`
- `0x180005db0`
- `0x180006140`
- `0x1800062b0`
- `0x1800063b0`
- `0x1800066e0`
- `0x180006e30`
- `0x1800072e0`
- `0x1800075b0`

## callees

- `0x180001f48`
- `0x180002494`
- `0x1800037a8`
- `0x180007df8`

## string_xrefs

- `0x1800037ea`: `GetLineObjWithReadLock: obj(%p) has bad key(%x)`

## pseudocode

```c
__int64 __fastcall GetLineObjWithReadLock(const void *a1, _QWORD *a2)
{
  _DWORD *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  if ( (unsigned int)GetObjWithReadLock(a1, &v5) )
    return 2147483691LL;
  if ( *v5 != 1263290702 )
  {
    TspLog(2, "GetLineObjWithReadLock: obj(%p) has bad key(%x)", a1, *v5);
    ReleaseObjReadLock(a1);
    return 2147483691LL;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800037a8  mov     [rsp+arg_0], rbx
0x1800037ad  push    rdi
0x1800037ae  sub     rsp, 20h
0x1800037b2  mov     rdi, rdx
0x1800037b5  mov     [rsp+28h+arg_10], 0
0x1800037be  lea     rdx, [rsp+28h+arg_10]
0x1800037c3  mov     rbx, rcx
0x1800037c6  call    GetObjWithReadLock
0x1800037cb  test    eax, eax
0x1800037cd  jz      short loc_1800037D6
0x1800037cf  mov     eax, 8000002Bh
0x1800037d4  jmp     short loc_18000380A
0x1800037d6  mov     rax, [rsp+28h+arg_10]
0x1800037db  mov     r9d, [rax]
0x1800037de  cmp     r9d, 4B4C494Eh
0x1800037e5  jz      short loc_180003805
0x1800037e7  mov     r8, rbx
0x1800037ea  lea     rdx, aGetlineobjwith; "GetLineObjWithReadLock: obj(%p) has bad"...
0x1800037f1  mov     ecx, 2
0x1800037f6  call    TspLog
0x1800037fb  mov     rcx, rbx
0x1800037fe  call    ReleaseObjReadLock
0x180003803  jmp     short loc_1800037CF
0x180003805  mov     [rdi], rax
0x180003808  xor     eax, eax
0x18000380a  mov     rbx, [rsp+28h+arg_0]
0x18000380f  add     rsp, 20h
0x180003813  pop     rdi
0x180003814  retn
```
