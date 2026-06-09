# RegConnectMachine

- ea: `0x140002c20`
- end: `0x140002cdc`
- name: `RegConnectMachine`
- size: `188`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x1400073d4`
- `0x140008cbc`

## callees

- `0x140002c20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002c76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002c76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002c3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002cbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002c3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002cbe`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x140002c90`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x140002c90`

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
0x140002c20  push    rbx
0x140002c22  push    rsi
0x140002c23  push    rdi
0x140002c24  push    r14
0x140002c26  sub     rsp, 28h
0x140002c2a  mov     [rsp+48h+phkResult], 0
0x140002c33  mov     rbx, rcx
0x140002c36  test    rcx, rcx
0x140002c39  jnz     short loc_140002C51
0x140002c3b  lea     ecx, [rbx+57h]; dwErrCode
0x140002c3e  call    cs:__imp_SetLastError
0x140002c45  nop     dword ptr [rax+rax+00h]
0x140002c4a  xor     eax, eax
0x140002c4c  jmp     loc_140002CD1
0x140002c51  xor     esi, esi
0x140002c53  cmp     dword ptr [rcx+10h], 1
0x140002c57  jnz     short loc_140002CBC
0x140002c59  lea     r14, [rcx+8]
0x140002c5d  mov     rdx, [r14]
0x140002c60  lea     rdi, [rcx+14h]
0x140002c64  test    rdx, rdx
0x140002c67  jz      short loc_140002C85
0x140002c69  cmp     dword ptr [rdi], 1
0x140002c6c  jnz     short loc_140002C87
0x140002c6e  test    r14, r14
0x140002c71  jz      short loc_140002C87
0x140002c73  mov     rcx, rdx; hKey
0x140002c76  call    cs:__imp_RegCloseKey
0x140002c7d  nop     dword ptr [rax+rax+00h]
0x140002c82  mov     [r14], rsi
0x140002c85  xor     edx, edx; hKey
0x140002c87  mov     rcx, [rbx+48h]; lpMachineName
0x140002c8b  lea     r8, [rsp+48h+phkResult]; phkResult
0x140002c90  call    cs:__imp_RegConnectRegistryW
0x140002c97  nop     dword ptr [rax+rax+00h]
0x140002c9c  mov     esi, eax
0x140002c9e  test    eax, eax
0x140002ca0  jnz     short loc_140002CBC
0x140002ca2  mov     rax, [rsp+48h+phkResult]
0x140002ca7  test    rax, rax
0x140002caa  jz      short loc_140002CB7
0x140002cac  mov     [r14], rax
0x140002caf  mov     dword ptr [rdi], 1
0x140002cb5  jmp     short loc_140002CBC
0x140002cb7  mov     esi, 42Bh
0x140002cbc  mov     ecx, esi; dwErrCode
0x140002cbe  call    cs:__imp_SetLastError
0x140002cc5  nop     dword ptr [rax+rax+00h]
0x140002cca  xor     eax, eax
0x140002ccc  test    esi, esi
0x140002cce  setz    al
0x140002cd1  add     rsp, 28h
0x140002cd5  pop     r14
0x140002cd7  pop     rdi
0x140002cd8  pop     rsi
0x140002cd9  pop     rbx
0x140002cda  retn
```
