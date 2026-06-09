# ATL::AtlThrowImpl(long)

- ea: `0x18000b48c`
- end: `0x18000b4a6`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180003390`
- `0x180007720`
- `0x180007800`
- `0x180009660`
- `0x180009af0`
- `0x18000a360`
- `0x18000b250`
- `0x18000b348`
- `0x18000b65c`
- `0x18000b6f0`
- `0x18000b7ec`
- `0x18000ba44`
- `0x18000ba7c`
- `0x18000bac8`
- `0x18000bc04`
- `0x18000be54`
- `0x18000bff8`
- `0x18000dbec`
- `0x18000dd28`
- `0x18000ec74`
- `0x18000f9dc`

## callees

- `0x18000d258`

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
0x18000b48c  sub     rsp, 28h
0x18000b490  mov     [rsp+28h+pExceptionObject], ecx
0x18000b494  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000b49b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000b4a0  call    _CxxThrowException_0
```
