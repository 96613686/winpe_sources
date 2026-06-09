# CSafeReg::Connect(ushort const *,HKEY__ *)

- ea: `0x18001ac04`
- end: `0x18001ac6c`
- name: `?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(PHKEY phkResult, LPCWSTR lpMachineName, HKEY)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004b7c`
- `0x18000839c`
- `0x180008b70`
- `0x18000d814`
- `0x1800130a8`
- `0x1800131b8`
- `0x180016084`
- `0x180016ffc`

## callees

- `0x180005274`
- `0x18001ac04`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x18001ac36`
- `ADVAPI32!RegConnectRegistryW` at `0x18001ac36`
- `USER32!SetCursor` at `0x18001ac54`
- `USER32!SetCursor` at `0x18001ac54`

## pseudocode

```c
__int64 __fastcall CSafeReg::Connect(PHKEY phkResult, LPCWSTR lpMachineName, HCURSOR a3)
{
  unsigned int v5; // esi
  LSTATUS v6; // eax
  HCURSOR hCursor; // [rsp+40h] [rbp+18h] BYREF

  hCursor = a3;
  v5 = 0;
  CWaitCursor::CWaitCursor((CWaitCursor *)&hCursor);
  v6 = RegConnectRegistryW(lpMachineName, HKEY_LOCAL_MACHINE, phkResult);
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    else
      v5 = v6;
  }
  SetCursor(hCursor);
  return v5;
}

```

## disassembly

```asm
0x18001ac04  mov     rax, rsp
0x18001ac07  mov     [rax+8], rbx
0x18001ac0b  mov     [rax+10h], rsi
0x18001ac0f  mov     [rax+18h], r8
0x18001ac13  push    rdi
0x18001ac14  sub     rsp, 20h
0x18001ac18  mov     rbx, rcx
0x18001ac1b  mov     rdi, rdx
0x18001ac1e  lea     rcx, [rax+18h]; this
0x18001ac22  xor     esi, esi
0x18001ac24  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18001ac29  mov     r8, rbx; phkResult
0x18001ac2c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001ac33  mov     rcx, rdi; lpMachineName
0x18001ac36  call    cs:__imp_RegConnectRegistryW
0x18001ac3c  test    eax, eax
0x18001ac3e  jz      short loc_18001AC4F
0x18001ac40  jg      short loc_18001AC46
0x18001ac42  mov     esi, eax
0x18001ac44  jmp     short loc_18001AC4F
0x18001ac46  movzx   esi, ax
0x18001ac49  or      esi, 80070000h
0x18001ac4f  mov     rcx, [rsp+28h+hCursor]; hCursor
0x18001ac54  call    cs:__imp_SetCursor
0x18001ac5a  mov     rbx, [rsp+28h+arg_0]
0x18001ac5f  mov     eax, esi
0x18001ac61  mov     rsi, [rsp+28h+arg_8]
0x18001ac66  add     rsp, 20h
0x18001ac6a  pop     rdi
0x18001ac6b  retn
```
