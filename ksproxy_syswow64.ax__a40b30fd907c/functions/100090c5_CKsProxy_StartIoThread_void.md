# CKsProxy::StartIoThread(void)

- ea: `0x100090c5`
- end: `0x10009119`
- name: `?StartIoThread@CKsProxy@@QAGJXZ`
- size: `84`
- prototype: `unsigned int __cdecl(CKsProxy *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100115a5`

## callees

- `0x100090c5`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100090f5`
- `KERNEL32!GetLastError` at `0x100090f5`
- `KERNEL32!CreateThread` at `0x100090e9`
- `KERNEL32!CreateThread` at `0x100090e9`

## pseudocode

```c
unsigned int __cdecl CKsProxy::StartIoThread(CKsProxy *this)
{
  DWORD *v1; // ecx
  DWORD *v2; // esi
  unsigned int result; // eax
  DWORD LastError; // eax
  int v5; // ecx

  v2 = v1;
  if ( v1[58] )
    return 0;
  v1[58] = (DWORD)CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CKsProxy::IoThread, v1, 0, v1 + 59);
  LastError = GetLastError();
  v5 = LastError;
  if ( v2[58] )
    return 0;
  result = (unsigned __int16)LastError | 0x80070000;
  if ( v5 <= 0 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x100090c5  mov     edi, edi
0x100090c7  push    esi
0x100090c8  mov     esi, ecx
0x100090ca  push    edi
0x100090cb  xor     edi, edi
0x100090cd  cmp     [esi+0E8h], edi
0x100090d3  jz      short loc_100090D9
0x100090d5  xor     eax, eax
0x100090d7  jmp     short loc_10009116
0x100090d9  lea     eax, [esi+0ECh]
0x100090df  push    eax; lpThreadId
0x100090e0  push    edi; dwCreationFlags
0x100090e1  push    esi; lpParameter
0x100090e2  push    offset ?IoThread@CKsProxy@@SGKPAV1@@Z; lpStartAddress
0x100090e7  push    edi; dwStackSize
0x100090e8  push    edi; lpThreadAttributes
0x100090e9  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x100090ef  mov     [esi+0E8h], eax
0x100090f5  call    ds:__imp__GetLastError@0; GetLastError()
0x100090fb  mov     ecx, eax
0x100090fd  cmp     [esi+0E8h], edi
0x10009103  jnz     short loc_10009114
0x10009105  movzx   eax, cx
0x10009108  or      eax, 80070000h
0x1000910d  test    ecx, ecx
0x1000910f  cmovle  eax, ecx
0x10009112  jmp     short loc_10009116
0x10009114  mov     eax, edi
0x10009116  pop     edi
0x10009117  pop     esi
0x10009118  retn
```
