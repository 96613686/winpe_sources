# operator new(uint)

- ea: `0x1004ce5d`
- end: `0x1004ce9a`
- name: `??2@YAPAXI@Z`
- size: `61`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `83`
- callee_count: `4`
- tags: ``

## callers

- `0x1000bea0`
- `0x1000c0d0`
- `0x1000cc30`
- `0x1000e140`
- `0x1000e9f0`
- `0x1000f260`
- `0x1000f4a0`
- `0x1000f8a0`
- `0x1000fa40`
- `0x1000fcf0`
- `0x10012470`
- `0x100124f0`
- `0x10012e10`
- `0x10013f50`
- `0x10014330`
- `0x100146e0`
- `0x100148a0`
- `0x10014d90`
- `0x10016040`
- `0x10016800`
- `0x10016c40`
- `0x10016e10`
- `0x10017160`
- `0x10017b50`
- `0x10018220`
- `0x10019cd0`
- `0x1001a7b0`
- `0x1001a970`
- `0x1001b4a0`
- `0x1001bdc0`
- `0x1001df20`
- `0x1001f370`
- `0x1001f5a0`
- `0x1001f750`
- `0x1001f8e0`
- `0x100204c0`
- `0x100205d0`
- `0x100225b0`
- `0x10023390`
- `0x10024540`
- `0x10024630`
- `0x10024750`
- `0x100249b0`
- `0x10024c90`
- `0x10025180`
- `0x10027860`
- `0x10028340`
- `0x100294e0`
- `0x10029a90`
- `0x1002b570`

## callees

- `0x1004cda7`
- `0x1004ce5d`
- `0x1004d91c`
- `0x1004d928`

## import_xrefs

- `msvcrt!malloc` at `0x1004ce77`
- `msvcrt!malloc` at `0x1004ce77`

## pseudocode

```c
void *__cdecl operator new(size_t Size)
{
  void *result; // eax
  _BYTE pExceptionObject[12]; // [esp+0h] [ebp-Ch] BYREF

  while ( 1 )
  {
    result = _malloc(Size);
    if ( result )
      break;
    if ( !_callnewh(Size) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      _CxxThrowException(pExceptionObject, (_ThrowInfo *)&_TI2_AVbad_alloc_std__);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1004ce5d  mov     edi, edi
0x1004ce5f  push    ebp
0x1004ce60  mov     ebp, esp
0x1004ce62  sub     esp, 0Ch
0x1004ce65  jmp     short loc_1004CE74
0x1004ce67  push    [ebp+Size]; Size
0x1004ce6a  call    __callnewh
0x1004ce6f  pop     ecx
0x1004ce70  test    eax, eax
0x1004ce72  jz      short loc_1004CE84
0x1004ce74  push    [ebp+Size]; Size
0x1004ce77  call    ds:__imp__malloc
0x1004ce7d  pop     ecx
0x1004ce7e  test    eax, eax
0x1004ce80  jz      short loc_1004CE67
0x1004ce82  leave
0x1004ce83  retn
0x1004ce84  lea     ecx, [ebp+pExceptionObject]; this
0x1004ce87  call    ??0bad_alloc@std@@QAE@XZ; std::bad_alloc::bad_alloc(void)
0x1004ce8c  push    offset __TI2?AVbad_alloc@std@@; pThrowInfo
0x1004ce91  lea     eax, [ebp+pExceptionObject]
0x1004ce94  push    eax; pExceptionObject
0x1004ce95  call    __CxxThrowException@8; _CxxThrowException(x,x)
```
