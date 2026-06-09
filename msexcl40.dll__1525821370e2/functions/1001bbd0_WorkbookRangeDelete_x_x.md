# WorkbookRangeDelete(x,x)

- ea: `0x1001bbd0`
- end: `0x1001bc0c`
- name: `_WorkbookRangeDelete@8`
- size: `60`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x10029730`
- `0x10029b60`
- `0x1002e5d0`

## callees

- `0x1001bbd0`
- `0x1001c2b0`
- `0x10021260`
- `0x10025ab7`
- `0x100358c5`

## pseudocode

```c
int __fastcall WorkbookRangeDelete(int a1, DispatchDriver *a2)
{
  if ( a1 && *(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      DispatchDriver::~DispatchDriver(a2);
      operator delete(a2);
    }
    return TranslateEXErrorToJETError(0);
  }
  else
  {
    if ( a2 )
      MemFree(a2);
    return 0;
  }
}

```

## disassembly

```asm
0x1001bbd0  mov     edi, edi
0x1001bbd2  push    esi
0x1001bbd3  mov     esi, edx
0x1001bbd5  test    ecx, ecx
0x1001bbd7  jz      short loc_1001BBFD
0x1001bbd9  cmp     dword ptr [ecx+0Ch], 0
0x1001bbdd  jz      short loc_1001BBFD
0x1001bbdf  test    esi, esi
0x1001bbe1  jz      short loc_1001BBF5
0x1001bbe3  mov     ecx, esi; this
0x1001bbe5  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x1001bbea  push    8; unsigned int
0x1001bbec  push    esi; void *
0x1001bbed  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001bbf2  add     esp, 8
0x1001bbf5  xor     ecx, ecx
0x1001bbf7  pop     esi
0x1001bbf8  jmp     _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001bbfd  test    esi, esi
0x1001bbff  jz      short loc_1001BC08
0x1001bc01  mov     ecx, esi
0x1001bc03  call    _MemFree@4; MemFree(x)
0x1001bc08  xor     eax, eax
0x1001bc0a  pop     esi
0x1001bc0b  retn
```
