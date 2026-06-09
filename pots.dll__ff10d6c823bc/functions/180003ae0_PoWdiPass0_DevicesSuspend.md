# PoWdiPass0_DevicesSuspend

- ea: `0x180003ae0`
- end: `0x180003b49`
- name: `PoWdiPass0_DevicesSuspend`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800022dc`
- `0x180003ae0`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiPass0_DevicesSuspend(struct _EVENT_RECORD *a1, __int64 a2, __int64 a3)
{
  TDHSTATUS result; // eax
  int v5; // eax
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF
  int v7; // [rsp+58h] [rbp+20h] BYREF

  v7 = 0;
  LODWORD(v6) = 0;
  result = PoWdiGetProperty(a1, (ULONGLONG)L"EffectiveState", a3, (BYTE *)&v7, 4u, (ULONG *)&v6);
  if ( !result && (_DWORD)v6 == 4 )
  {
    v5 = *(_DWORD *)(a2 + 4);
    if ( v7 == 5 )
      result = v5 | 1;
    else
      result = v5 & 0xFFFFFFFE;
    *(_DWORD *)(a2 + 136) |= 1u;
    *(_DWORD *)(a2 + 4) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180003ae0  push    rbx
0x180003ae2  sub     rsp, 30h
0x180003ae6  lea     rax, [rsp+38h+arg_10]
0x180003aeb  mov     [rsp+38h+arg_18], 0
0x180003af3  mov     rbx, rdx
0x180003af6  mov     [rsp+38h+var_10], rax; __int64
0x180003afb  lea     r9, [rsp+38h+arg_18]
0x180003b00  mov     [rsp+38h+var_18], 4; int
0x180003b08  lea     rdx, aEffectivestate; "EffectiveState"
0x180003b0f  mov     dword ptr [rsp+38h+arg_10], 0
0x180003b17  call    PoWdiGetProperty
0x180003b1c  test    eax, eax
0x180003b1e  jnz     short loc_180003B43
0x180003b20  cmp     dword ptr [rsp+38h+arg_10], 4
0x180003b25  jnz     short loc_180003B43
0x180003b27  cmp     [rsp+38h+arg_18], 5
0x180003b2c  mov     eax, [rbx+4]
0x180003b2f  jnz     short loc_180003B36
0x180003b31  or      eax, 1
0x180003b34  jmp     short loc_180003B39
0x180003b36  and     eax, 0FFFFFFFEh
0x180003b39  or      dword ptr [rbx+88h], 1
0x180003b40  mov     [rbx+4], eax
0x180003b43  add     rsp, 30h
0x180003b47  pop     rbx
0x180003b48  retn
```
