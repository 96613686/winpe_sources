# __getptd_noexit

- ea: `0x1002f0b3`
- end: `0x1002f122`
- name: `__getptd_noexit`
- size: `111`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1002d6a8`
- `0x1002d6dc`
- `0x1002d7a5`
- `0x1002f09b`
- `0x1003437f`
- `0x1003a31c`

## callees

- `0x1002df32`
- `0x1002f0b3`
- `0x1002f122`
- `0x100302d8`
- `0x100302f7`
- `0x100336b6`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002f0b5`
- `KERNEL32!GetLastError` at `0x1002f0b5`
- `KERNEL32!SetLastError` at `0x1002f117`
- `KERNEL32!SetLastError` at `0x1002f117`
- `KERNEL32!GetCurrentThreadId` at `0x1002f0ff`
- `KERNEL32!GetCurrentThreadId` at `0x1002f0ff`

## pseudocode

```c
DWORD *_getptd_noexit()
{
  DWORD LastError; // edi
  DWORD *Value; // esi
  DWORD *v2; // eax
  DWORD CurrentThreadId; // eax

  LastError = GetLastError();
  Value = (DWORD *)__crtFlsGetValue(__flsindex);
  if ( !Value )
  {
    v2 = (DWORD *)_calloc_crt(1, 956);
    Value = v2;
    if ( v2 )
    {
      if ( __crtFlsSetValue(__flsindex, v2) )
      {
        _initptd(Value, 0);
        CurrentThreadId = GetCurrentThreadId();
        Value[1] = -1;
        *Value = CurrentThreadId;
      }
      else
      {
        free(Value);
        Value = 0;
      }
    }
  }
  SetLastError(LastError);
  return Value;
}

```

## disassembly

```asm
0x1002f0b3  push    esi
0x1002f0b4  push    edi
0x1002f0b5  call    ds:__imp__GetLastError@0
0x1002f0bb  push    ___flsindex; dwTlsIndex
0x1002f0c1  mov     edi, eax
0x1002f0c3  call    ___crtFlsGetValue
0x1002f0c8  mov     esi, eax
0x1002f0ca  pop     ecx
0x1002f0cb  test    esi, esi
0x1002f0cd  jnz     short loc_1002F116
0x1002f0cf  push    3BCh
0x1002f0d4  push    1
0x1002f0d6  call    __calloc_crt
0x1002f0db  mov     esi, eax
0x1002f0dd  pop     ecx
0x1002f0de  pop     ecx
0x1002f0df  test    esi, esi
0x1002f0e1  jz      short loc_1002F116
0x1002f0e3  push    esi; lpTlsValue
0x1002f0e4  push    ___flsindex; dwTlsIndex
0x1002f0ea  call    ___crtFlsSetValue
0x1002f0ef  pop     ecx
0x1002f0f0  pop     ecx
0x1002f0f1  test    eax, eax
0x1002f0f3  jz      short loc_1002F10D
0x1002f0f5  push    0
0x1002f0f7  push    esi
0x1002f0f8  call    __initptd
0x1002f0fd  pop     ecx
0x1002f0fe  pop     ecx
0x1002f0ff  call    ds:__imp__GetCurrentThreadId@0
0x1002f105  or      dword ptr [esi+4], 0FFFFFFFFh
0x1002f109  mov     [esi], eax
0x1002f10b  jmp     short loc_1002F116
0x1002f10d  push    esi; Block
0x1002f10e  call    _free
0x1002f113  pop     ecx
0x1002f114  xor     esi, esi
0x1002f116  push    edi; dwErrCode
0x1002f117  call    ds:__imp__SetLastError@4
0x1002f11d  pop     edi
0x1002f11e  mov     eax, esi
0x1002f120  pop     esi
0x1002f121  retn
```
