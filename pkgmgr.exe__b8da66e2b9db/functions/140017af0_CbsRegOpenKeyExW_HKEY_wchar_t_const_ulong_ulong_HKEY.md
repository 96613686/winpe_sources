# CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)

- ea: `0x140017af0`
- end: `0x140017b7a`
- name: `?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z`
- size: `138`
- prototype: `LSTATUS __fastcall(HKEY, const wchar_t *, __int64, REGSAM, PHKEY)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140017b80`
- `0x140017eb4`
- `0x140018394`

## callees

- `0x140017af0`
- `0x1400243e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017b64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017b64`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140017b57`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140017b57`

## pseudocode

```c
LSTATUS __fastcall CbsRegOpenKeyExW(HKEY a1, const wchar_t *a2, __int64 a3, REGSAM a4, PHKEY a5)
{
  HKEY *phkResult; // rbx
  HANDLE hTransaction; // [rsp+50h] [rbp+8h] BYREF

  hTransaction = a1;
  phkResult = a5;
  if ( !a5 )
    return -2147467261;
  hTransaction = 0;
  CbsGetCurrentTransaction(&hTransaction);
  if ( hTransaction )
    return RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, a2, 0, a4, phkResult, hTransaction, 0);
  else
    return RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, a4, phkResult);
}

```

## disassembly

```asm
0x140017af0  mov     [rsp+arg_8], rbx
0x140017af5  mov     [rsp+arg_10], rsi
0x140017afa  mov     [rsp+arg_0], rcx
0x140017aff  push    rdi
0x140017b00  sub     rsp, 40h
0x140017b04  mov     rbx, [rsp+48h+arg_20]
0x140017b09  mov     edi, r9d
0x140017b0c  mov     rsi, rdx
0x140017b0f  test    rbx, rbx
0x140017b12  jnz     short loc_140017B1B
0x140017b14  mov     eax, 80004003h
0x140017b19  jmp     short loc_140017B6A
0x140017b1b  lea     rcx, [rsp+48h+arg_0]; void **
0x140017b20  mov     [rsp+48h+arg_0], 0
0x140017b29  call    ?CbsGetCurrentTransaction@@YAJPEAPEAX@Z; CbsGetCurrentTransaction(void * *)
0x140017b2e  mov     rax, [rsp+48h+arg_0]
0x140017b33  xor     r8d, r8d; ulOptions
0x140017b36  mov     r9d, edi; samDesired
0x140017b39  mov     rdx, rsi; lpSubKey
0x140017b3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017b43  test    rax, rax
0x140017b46  jz      short loc_140017B5F
0x140017b48  mov     [rsp+48h+pExtendedParemeter], r8; pExtendedParemeter
0x140017b4d  mov     [rsp+48h+hTransaction], rax; hTransaction
0x140017b52  mov     [rsp+48h+phkResult], rbx; phkResult
0x140017b57  call    cs:__imp_RegOpenKeyTransactedW
0x140017b5d  jmp     short loc_140017B6A
0x140017b5f  mov     [rsp+48h+phkResult], rbx; phkResult
0x140017b64  call    cs:__imp_RegOpenKeyExW
0x140017b6a  mov     rbx, [rsp+48h+arg_8]
0x140017b6f  mov     rsi, [rsp+48h+arg_10]
0x140017b74  add     rsp, 40h
0x140017b78  pop     rdi
0x140017b79  retn
```
