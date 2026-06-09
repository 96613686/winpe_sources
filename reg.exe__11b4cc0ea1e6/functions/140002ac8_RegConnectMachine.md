# RegConnectMachine

- ea: `0x140002ac8`
- end: `0x140002b68`
- name: `RegConnectMachine`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140005bac`
- `0x140006394`
- `0x140006f9c`
- `0x140008788`

## callees

- `0x140002ac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002b15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002ae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002ae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b51`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x140002b29`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x140002b29`

## pseudocode

```c
_BOOL8 __fastcall RegConnectMachine(__int64 a1)
{
  LSTATUS v3; // esi
  HKEY *v4; // r14
  HKEY v5; // rdx
  _DWORD *v6; // rdi
  HKEY phkResult; // [rsp+50h] [rbp+8h] BYREF

  phkResult = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v3 = 0;
  if ( *(_DWORD *)(a1 + 16) == 1 )
  {
    v4 = (HKEY *)(a1 + 8);
    v5 = *(HKEY *)(a1 + 8);
    v6 = (_DWORD *)(a1 + 20);
    if ( v5 )
    {
      if ( *v6 != 1 || a1 == -8 )
      {
LABEL_9:
        v3 = RegConnectRegistryW(*(LPCWSTR *)(a1 + 72), v5, &phkResult);
        if ( !v3 )
        {
          if ( phkResult )
          {
            *v4 = phkResult;
            *v6 = 1;
          }
          else
          {
            v3 = 1067;
          }
        }
        goto LABEL_13;
      }
      RegCloseKey(*(HKEY *)(a1 + 8));
      *v4 = 0;
    }
    v5 = 0;
    goto LABEL_9;
  }
LABEL_13:
  SetLastError(v3);
  return v3 == 0;
}

```

## disassembly

```asm
0x140002ac8  push    rbx
0x140002aca  push    rsi
0x140002acb  push    rdi
0x140002acc  push    r14
0x140002ace  sub     rsp, 28h
0x140002ad2  mov     [rsp+48h+phkResult], 0
0x140002adb  mov     rbx, rcx
0x140002ade  test    rcx, rcx
0x140002ae1  jnz     short loc_140002AF0
0x140002ae3  lea     ecx, [rbx+57h]; dwErrCode
0x140002ae6  call    cs:__imp_SetLastError
0x140002aec  xor     eax, eax
0x140002aee  jmp     short loc_140002B5E
0x140002af0  xor     esi, esi
0x140002af2  cmp     dword ptr [rcx+10h], 1
0x140002af6  jnz     short loc_140002B4F
0x140002af8  lea     r14, [rcx+8]
0x140002afc  mov     rdx, [r14]
0x140002aff  lea     rdi, [rcx+14h]
0x140002b03  test    rdx, rdx
0x140002b06  jz      short loc_140002B1E
0x140002b08  cmp     dword ptr [rdi], 1
0x140002b0b  jnz     short loc_140002B20
0x140002b0d  test    r14, r14
0x140002b10  jz      short loc_140002B20
0x140002b12  mov     rcx, rdx; hKey
0x140002b15  call    cs:__imp_RegCloseKey
0x140002b1b  mov     [r14], rsi
0x140002b1e  xor     edx, edx; hKey
0x140002b20  mov     rcx, [rbx+48h]; lpMachineName
0x140002b24  lea     r8, [rsp+48h+phkResult]; phkResult
0x140002b29  call    cs:__imp_RegConnectRegistryW
0x140002b2f  mov     esi, eax
0x140002b31  test    eax, eax
0x140002b33  jnz     short loc_140002B4F
0x140002b35  mov     rax, [rsp+48h+phkResult]
0x140002b3a  test    rax, rax
0x140002b3d  jz      short loc_140002B4A
0x140002b3f  mov     [r14], rax
0x140002b42  mov     dword ptr [rdi], 1
0x140002b48  jmp     short loc_140002B4F
0x140002b4a  mov     esi, 42Bh
0x140002b4f  mov     ecx, esi; dwErrCode
0x140002b51  call    cs:__imp_SetLastError
0x140002b57  xor     eax, eax
0x140002b59  test    esi, esi
0x140002b5b  setz    al
0x140002b5e  add     rsp, 28h
0x140002b62  pop     r14
0x140002b64  pop     rdi
0x140002b65  pop     rsi
0x140002b66  pop     rbx
0x140002b67  retn
```
