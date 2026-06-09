# ATL::AtlThrowImpl(long)

- ea: `0x18000f208`
- end: `0x18000f22a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc5c`
- `0x18000e0bc`
- `0x18000e698`
- `0x18000e6cc`
- `0x18000e910`
- `0x18000eb5c`
- `0x18000f024`
- `0x18001098c`
- `0x1800110a8`
- `0x180011384`

## callees

- `0x180001e0e`
- `0x18000d58c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a1);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x18000f208  sub     rsp, 28h
0x18000f20c  mov     edx, ecx; int
0x18000f20e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x18000f213  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000f218  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000f21f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000f224  call    _CxxThrowException_0
```
