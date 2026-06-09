# DsRolepSetRegStringValue

- ea: `0x18000b734`
- end: `0x18000b7ea`
- name: `DsRolepSetRegStringValue`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180003ff0`
- `0x180006b70`

## callees

- `0x18000b734`
- `0x18001fe50`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b7b5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000b770`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18000b770`

## string_xrefs

- `0x18000b769`: `System\CurrentControlSet\Services\NTDS\Parameters`
- `0x18000b7bf`: `System\CurrentControlSet\Services\NTDS\Parameters`

## pseudocode

```c
__int64 __fastcall DsRolepSetRegStringValue(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  int v6; // r8d
  __int64 v7; // rax
  ULONGLONG ullOperand; // [rsp+28h] [rbp-30h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF

  phkResult = 0;
  v5 = 87;
  if ( a2 )
  {
    if ( a3 )
    {
      v5 = RegCreateKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\NTDS\\Parameters", &phkResult);
      if ( !v5 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)(a3 + 2 * v7) );
        v5 = DsRolepRegSetValueEx((int)phkResult, a2, v6, 1, a3, 2 * v7 + 2);
        RegCloseKey(phkResult);
      }
    }
  }
  LODWORD(ullOperand) = v5;
  DsRolepLogPrintRoutine(
    4,
    "DsRolepSetRegStringValue on %ws\\%ws to %ws returned %lu\n",
    L"System\\CurrentControlSet\\Services\\NTDS\\Parameters",
    a2,
    a3,
    ullOperand);
  return v5;
}

```

## disassembly

```asm
0x18000b734  mov     [rsp+phkResult], rcx
0x18000b739  push    rbx
0x18000b73a  push    rbp
0x18000b73b  push    rsi
0x18000b73c  push    rdi
0x18000b73d  sub     rsp, 38h
0x18000b741  xor     ebp, ebp
0x18000b743  mov     rdi, r8
0x18000b746  mov     [rsp+58h+phkResult], rbp
0x18000b74b  mov     rsi, rdx
0x18000b74e  mov     ebx, 57h ; 'W'
0x18000b753  test    rdx, rdx
0x18000b756  jz      short loc_18000B7BB
0x18000b758  test    r8, r8
0x18000b75b  jz      short loc_18000B7BB
0x18000b75d  lea     r8, [rsp+58h+phkResult]; phkResult
0x18000b762  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b769  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\NT"...
0x18000b770  call    cs:__imp_RegCreateKeyW
0x18000b776  mov     ebx, eax
0x18000b778  test    eax, eax
0x18000b77a  jnz     short loc_18000B7BB
0x18000b77c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b780  inc     rax
0x18000b783  cmp     [rdi+rax*2], bp
0x18000b787  jnz     short loc_18000B780
0x18000b789  mov     rcx, [rsp+58h+phkResult]; int
0x18000b78e  lea     rax, ds:2[rax*2]
0x18000b796  mov     [rsp+58h+ullOperand], rax; ullOperand
0x18000b79b  mov     r9d, 1; int
0x18000b7a1  mov     rdx, rsi; int
0x18000b7a4  mov     qword ptr [rsp+58h+var_38], rdi; int
0x18000b7a9  call    DsRolepRegSetValueEx
0x18000b7ae  mov     rcx, [rsp+58h+phkResult]; hKey
0x18000b7b3  mov     ebx, eax
0x18000b7b5  call    cs:__imp_RegCloseKey
0x18000b7bb  mov     dword ptr [rsp+58h+ullOperand], ebx
0x18000b7bf  lea     r8, SubKey; "System\\CurrentControlSet\\Services\\NT"...
0x18000b7c6  mov     r9, rsi
0x18000b7c9  mov     qword ptr [rsp+58h+var_38], rdi
0x18000b7ce  lea     rdx, aDsrolepsetregs; "DsRolepSetRegStringValue on %ws\\%ws to"...
0x18000b7d5  mov     ecx, 4
0x18000b7da  call    DsRolepLogPrintRoutine
0x18000b7df  mov     eax, ebx
0x18000b7e1  add     rsp, 38h
0x18000b7e5  pop     rdi
0x18000b7e6  pop     rsi
0x18000b7e7  pop     rbp
0x18000b7e8  pop     rbx
0x18000b7e9  retn
```
