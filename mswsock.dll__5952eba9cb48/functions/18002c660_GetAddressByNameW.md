# GetAddressByNameW

- ea: `0x18002c660`
- end: `0x18002c734`
- name: `GetAddressByNameW`
- size: `212`
- prototype: `INT __stdcall(DWORD dwNameSpace, LPGUID lpServiceType, LPWSTR lpServiceName, LPINT lpiProtocols, DWORD dwResolution, LPSERVICE_ASYNC_INFO lpServiceAsyncInfo, LPVOID lpCsaddrBuffer, LPDWORD lpdwBufferLength, LPWSTR lpAliasBuffer, LPDWORD lpdwAliasBufferLength)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c410`

## callees

- `0x18002b060`
- `0x18002b924`
- `0x18002c660`
- `0x18002ff9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c68c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c68c`

## pseudocode

```c
INT __stdcall GetAddressByNameW(
        DWORD dwNameSpace,
        LPGUID lpServiceType,
        LPWSTR lpServiceName,
        LPINT lpiProtocols,
        DWORD dwResolution,
        LPSERVICE_ASYNC_INFO lpServiceAsyncInfo,
        LPVOID lpCsaddrBuffer,
        LPDWORD lpdwBufferLength,
        LPWSTR lpAliasBuffer,
        LPDWORD lpdwAliasBufferLength)
{
  DWORD v14; // ecx
  DWORD v16; // eax
  INT v17; // ebx
  DWORD dwBufferLength[14]; // [rsp+50h] [rbp-38h] BYREF

  dwBufferLength[0] = 0;
  if ( lpServiceAsyncInfo )
  {
    v14 = 50;
LABEL_3:
    SetLastError(v14);
    return -1;
  }
  if ( !NspInitialized )
  {
    v16 = InitializeNsp();
    if ( v16 )
    {
      v14 = v16;
      goto LABEL_3;
    }
  }
  v17 = DoNameResolution(
          dwNameSpace,
          (__int64)lpServiceType,
          (__int64)lpServiceName,
          (__int64)lpiProtocols,
          dwResolution,
          (__int64)lpCsaddrBuffer,
          lpdwBufferLength,
          lpAliasBuffer,
          lpdwAliasBufferLength);
  if ( !v17 && !EnumProtocolsW(lpiProtocols, 0, dwBufferLength) )
  {
    v14 = 10043;
    goto LABEL_3;
  }
  return v17;
}

```

## disassembly

```asm
0x18002c660  push    rbx
0x18002c662  push    rbp
0x18002c663  push    rsi
0x18002c664  push    rdi
0x18002c665  sub     rsp, 68h
0x18002c669  cmp     [rsp+88h+lpServiceAsyncInfo], 0
0x18002c672  mov     rdi, r9
0x18002c675  mov     rbx, r8
0x18002c678  mov     [rsp+88h+dwBufferLength], 0
0x18002c680  mov     rsi, rdx
0x18002c683  mov     ebp, ecx
0x18002c685  jz      short loc_18002C6A0
0x18002c687  mov     ecx, 32h ; '2'; dwErrCode
0x18002c68c  call    cs:__imp_SetLastError
0x18002c693  nop     dword ptr [rax+rax+00h]
0x18002c698  or      eax, 0FFFFFFFFh
0x18002c69b  jmp     loc_18002C72A
0x18002c6a0  cmp     cs:NspInitialized, 0
0x18002c6a7  jnz     short loc_18002C6B6
0x18002c6a9  call    InitializeNsp
0x18002c6ae  test    eax, eax
0x18002c6b0  jz      short loc_18002C6B6
0x18002c6b2  mov     ecx, eax
0x18002c6b4  jmp     short loc_18002C68C
0x18002c6b6  mov     rax, [rsp+88h+lpdwAliasBufferLength]
0x18002c6be  mov     r9, rdi
0x18002c6c1  mov     [rsp+88h+var_48], rax
0x18002c6c6  mov     r8, rbx
0x18002c6c9  mov     rax, [rsp+88h+lpAliasBuffer]
0x18002c6d1  mov     rdx, rsi
0x18002c6d4  mov     [rsp+88h+var_50], rax
0x18002c6d9  mov     ecx, ebp
0x18002c6db  mov     rax, [rsp+88h+lpdwBufferLength]
0x18002c6e3  mov     [rsp+88h+var_58], rax
0x18002c6e8  mov     rax, [rsp+88h+lpCsaddrBuffer]
0x18002c6f0  mov     [rsp+88h+var_60], rax
0x18002c6f5  mov     eax, [rsp+88h+dwResolution]
0x18002c6fc  mov     [rsp+88h+var_68], eax
0x18002c700  call    DoNameResolution
0x18002c705  mov     ebx, eax
0x18002c707  test    eax, eax
0x18002c709  jnz     short loc_18002C728
0x18002c70b  lea     r8, [rsp+88h+dwBufferLength]; lpdwBufferLength
0x18002c710  xor     edx, edx; lpProtocolBuffer
0x18002c712  mov     rcx, rdi; lpiProtocols
0x18002c715  call    EnumProtocolsW
0x18002c71a  test    eax, eax
0x18002c71c  jnz     short loc_18002C728
0x18002c71e  mov     ecx, 273Bh
0x18002c723  jmp     loc_18002C68C
0x18002c728  mov     eax, ebx
0x18002c72a  add     rsp, 68h
0x18002c72e  pop     rdi
0x18002c72f  pop     rsi
0x18002c730  pop     rbp
0x18002c731  pop     rbx
0x18002c732  retn
```
