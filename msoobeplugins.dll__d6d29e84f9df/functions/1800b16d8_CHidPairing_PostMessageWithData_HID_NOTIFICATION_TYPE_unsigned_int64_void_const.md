# CHidPairing::_PostMessageWithData(HID_NOTIFICATION_TYPE,unsigned __int64,void const *)

- ea: `0x1800b16d8`
- end: `0x1800b1754`
- name: `?_PostMessageWithData@CHidPairing@@AEAAJW4HID_NOTIFICATION_TYPE@@_KPEBX@Z`
- size: `124`
- prototype: `int __high(enum HID_NOTIFICATION_TYPE, unsigned __int64, const void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b2254`
- `0x1800b2770`

## callees

- `0x180005d8d`
- `0x18000ac48`
- `0x1800b16d8`

## import_xrefs

- `USER32!PostMessageW` at `0x1800b1722`
- `USER32!PostMessageW` at `0x1800b1722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b16f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b16f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1736`

## pseudocode

```c
__int64 __fastcall CHidPairing::_PostMessageWithData(__int64 a1, int a2, SIZE_T a3, const void *a4)
{
  WPARAM v5; // r15
  void *v8; // rax
  void *v9; // rdi
  unsigned int Error; // ebx

  v5 = a2;
  v8 = CoTaskMemAlloc(a3);
  v9 = v8;
  if ( v8 )
  {
    Error = 0;
    memcpy_0(v8, a4, a3);
    if ( !PostMessageW(*(HWND *)(a1 + 64), *(_DWORD *)(a1 + 280), v5, (LPARAM)v9) )
    {
      Error = ResultFromKnownLastError();
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x1800b16d8  push    rbx
0x1800b16da  push    rbp
0x1800b16db  push    rsi
0x1800b16dc  push    rdi
0x1800b16dd  push    r14
0x1800b16df  push    r15
0x1800b16e1  sub     rsp, 28h
0x1800b16e5  mov     rbp, rcx
0x1800b16e8  movsxd  r15, edx
0x1800b16eb  mov     rcx, r8; cb
0x1800b16ee  mov     r14, r9
0x1800b16f1  mov     rsi, r8
0x1800b16f4  call    cs:__imp_CoTaskMemAlloc
0x1800b16fa  mov     rdi, rax
0x1800b16fd  test    rax, rax
0x1800b1700  jz      short loc_1800B173E
0x1800b1702  mov     r8, rsi; Size
0x1800b1705  mov     rdx, r14; Src
0x1800b1708  mov     rcx, rax; void *
0x1800b170b  xor     ebx, ebx
0x1800b170d  call    memcpy_0
0x1800b1712  mov     edx, [rbp+118h]; Msg
0x1800b1718  mov     r8, r15; wParam
0x1800b171b  mov     rcx, [rbp+40h]; hWnd
0x1800b171f  mov     r9, rdi; lParam
0x1800b1722  call    cs:__imp_PostMessageW
0x1800b1728  test    eax, eax
0x1800b172a  jnz     short loc_1800B1745
0x1800b172c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b1731  mov     rcx, rdi; pv
0x1800b1734  mov     ebx, eax
0x1800b1736  call    cs:__imp_CoTaskMemFree
0x1800b173c  jmp     short loc_1800B1745
0x1800b173e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b1743  mov     ebx, eax
0x1800b1745  mov     eax, ebx
0x1800b1747  add     rsp, 28h
0x1800b174b  pop     r15
0x1800b174d  pop     r14
0x1800b174f  pop     rdi
0x1800b1750  pop     rsi
0x1800b1751  pop     rbp
0x1800b1752  pop     rbx
0x1800b1753  retn
```
