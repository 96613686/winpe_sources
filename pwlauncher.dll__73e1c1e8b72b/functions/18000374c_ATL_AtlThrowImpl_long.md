# ATL::AtlThrowImpl(long)

- ea: `0x18000374c`
- end: `0x18000376e`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011d0`
- `0x180001210`
- `0x180001250`
- `0x180002818`
- `0x180002b3c`
- `0x180003118`
- `0x18000314c`
- `0x180003284`
- `0x180003cc4`
- `0x1800042a8`
- `0x18000448c`
- `0x180009e04`
- `0x18000a38c`
- `0x18000a710`
- `0x18000a85c`
- `0x18000ad08`
- `0x18000b14c`

## callees

- `0x180002148`
- `0x18000253c`

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
0x18000374c  sub     rsp, 28h
0x180003750  mov     edx, ecx; int
0x180003752  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180003757  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000375c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180003763  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180003768  call    _CxxThrowException_0
```
