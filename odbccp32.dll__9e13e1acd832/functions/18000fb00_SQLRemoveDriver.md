# SQLRemoveDriver

- ea: `0x18000fb00`
- end: `0x18000fb5d`
- name: `SQLRemoveDriver`
- size: `93`
- prototype: `BOOL __stdcall(LPCSTR lpszDriver, BOOL fRemoveDSN, LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002940`
- `0x180009bd0`
- `0x18000fb00`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLRemoveDriver(LPCSTR lpszDriver, BOOL fRemoveDSN, LPDWORD lpdwUsageCount)
{
  BOOL v5; // ebx
  LPCWSTR lpszDrivera; // [rsp+48h] [rbp+20h] BYREF

  lpszDrivera = 0;
  v5 = 0;
  if ( (unsigned int)GWConvertToUnicode(lpszDriver, (WCHAR **)&lpszDrivera, 0xFFFFFFFD) )
    v5 = SQLRemoveDriverW(lpszDrivera, fRemoveDSN, lpdwUsageCount);
  OFree((void *)lpszDrivera);
  return v5;
}

```

## disassembly

```asm
0x18000fb00  mov     rax, rsp
0x18000fb03  mov     [rax+8], rbx
0x18000fb07  mov     [rax+10h], rsi
0x18000fb0b  push    rdi
0x18000fb0c  sub     rsp, 20h
0x18000fb10  mov     rdi, r8
0x18000fb13  mov     qword ptr [rax+20h], 0
0x18000fb1b  mov     esi, edx
0x18000fb1d  xor     ebx, ebx
0x18000fb1f  lea     rdx, [rax+20h]
0x18000fb23  lea     r8d, [rbx-3]
0x18000fb27  call    GWConvertToUnicode
0x18000fb2c  test    eax, eax
0x18000fb2e  jz      short loc_18000FB41
0x18000fb30  mov     rcx, [rsp+28h+lpszDriver]; lpszDriver
0x18000fb35  mov     r8, rdi; lpdwUsageCount
0x18000fb38  mov     edx, esi; fRemoveDSN
0x18000fb3a  call    SQLRemoveDriverW
0x18000fb3f  mov     ebx, eax
0x18000fb41  mov     rcx, [rsp+28h+lpszDriver]
0x18000fb46  call    OFree
0x18000fb4b  mov     rsi, [rsp+28h+arg_8]
0x18000fb50  mov     eax, ebx
0x18000fb52  mov     rbx, [rsp+28h+arg_0]
0x18000fb57  add     rsp, 20h
0x18000fb5b  pop     rdi
0x18000fb5c  retn
```
