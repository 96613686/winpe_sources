# PoWdiPass1_DevicesSuspend

- ea: `0x180003e00`
- end: `0x180003e9e`
- name: `PoWdiPass1_DevicesSuspend`
- size: `158`
- prototype: `__int64 __fastcall(PEVENT_RECORD pEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800022dc`
- `0x180003e00`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiPass1_DevicesSuspend(PEVENT_RECORD pEvent, __int64 a2, __int64 a3)
{
  TDHSTATUS result; // eax
  __int64 v6; // r8
  TDHSTATUS v7[6]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  v7[0] = 0;
  LODWORD(v8) = 0;
  v9 = 0;
  result = PoWdiGetProperty(pEvent, (ULONGLONG)L"TargetState", a3, (BYTE *)&v9, 4u, (ULONG *)&v8);
  if ( !result && (_DWORD)v8 == 4 )
  {
    result = PoWdiGetProperty(pEvent, (ULONGLONG)L"EffectiveState", v6, (BYTE *)v7, 4u, (ULONG *)&v8);
    if ( !result && (_DWORD)v8 == 4 )
    {
      *(_DWORD *)(a2 + 12) = v9;
      result = v7[0];
      *(_DWORD *)(a2 + 16) = v7[0];
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003e00  mov     rax, rsp
0x180003e03  mov     [rax+8], rbx
0x180003e07  push    rdi
0x180003e08  sub     rsp, 40h
0x180003e0c  mov     dword ptr [rax-18h], 0
0x180003e13  mov     rbx, rdx
0x180003e16  mov     dword ptr [rax+18h], 0
0x180003e1d  lea     r9, [rsp+48h+arg_18]
0x180003e22  mov     dword ptr [rax+20h], 0
0x180003e29  lea     rax, [rax+18h]
0x180003e2d  mov     [rsp+48h+var_20], rax; __int64
0x180003e32  lea     rdx, aTargetstate; "TargetState"
0x180003e39  mov     [rsp+48h+var_28], 4; int
0x180003e41  mov     rdi, rcx
0x180003e44  call    PoWdiGetProperty
0x180003e49  test    eax, eax
0x180003e4b  jnz     short loc_180003E93
0x180003e4d  cmp     dword ptr [rsp+48h+arg_10], 4
0x180003e52  jnz     short loc_180003E93
0x180003e54  lea     rax, [rsp+48h+arg_10]
0x180003e59  mov     rcx, rdi; pEvent
0x180003e5c  mov     [rsp+48h+var_20], rax; __int64
0x180003e61  lea     r9, [rsp+48h+var_18]
0x180003e66  lea     rdx, aEffectivestate; "EffectiveState"
0x180003e6d  mov     [rsp+48h+var_28], 4; int
0x180003e75  call    PoWdiGetProperty
0x180003e7a  test    eax, eax
0x180003e7c  jnz     short loc_180003E93
0x180003e7e  cmp     dword ptr [rsp+48h+arg_10], 4
0x180003e83  jnz     short loc_180003E93
0x180003e85  mov     eax, [rsp+48h+arg_18]
0x180003e89  mov     [rbx+0Ch], eax
0x180003e8c  mov     eax, [rsp+48h+var_18]
0x180003e90  mov     [rbx+10h], eax
0x180003e93  mov     rbx, [rsp+48h+arg_0]
0x180003e98  add     rsp, 40h
0x180003e9c  pop     rdi
0x180003e9d  retn
```
