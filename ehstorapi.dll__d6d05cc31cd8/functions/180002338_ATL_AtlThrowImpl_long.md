# ATL::AtlThrowImpl(long)

- ea: `0x180002338`
- end: `0x180002352`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`
- `0x180002210`
- `0x180002d68`
- `0x1800038ec`
- `0x18000394c`
- `0x180003a40`
- `0x180003ff4`
- `0x18000408c`
- `0x1800080cc`
- `0x180008bb8`
- `0x18000919c`
- `0x180009724`

## callees

- `0x18000c3fe`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  pExceptionObject = a1;
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180002338  sub     rsp, 28h
0x18000233c  mov     [rsp+28h+pExceptionObject], ecx
0x180002340  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180002347  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000234c  call    _CxxThrowException_0
```
