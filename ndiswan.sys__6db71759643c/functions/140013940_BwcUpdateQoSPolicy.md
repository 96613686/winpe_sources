# BwcUpdateQoSPolicy

- ea: `0x140013940`
- end: `0x1400139fb`
- name: `BwcUpdateQoSPolicy`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140011940`

## callees

- `0x140011ed4`
- `0x140013570`
- `0x140013940`

## pseudocode

```c
__int64 __fastcall BwcUpdateQoSPolicy(__int64 a1, unsigned int a2)
{
  int updated; // r8d
  int v4; // eax
  __int64 v6; // rdx
  _QWORD v8[7]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF

  updated = 0;
  v8[2] = (unsigned __int64)a2 << 10;
  v4 = *(_DWORD *)(a1 + 4);
  v8[1] = 0;
  v9 = 0;
  v8[3] = 0;
  v8[4] = 0;
  v8[0] = 0;
  if ( a2 )
  {
    if ( !v4 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      if ( v6 )
      {
        updated = BwcUpdateFlow(v8, v6);
        if ( updated < 0 )
          return (unsigned int)updated;
      }
      else
      {
        updated = BwcCreateFlow(v8, &v9);
        if ( updated < 0 )
          return (unsigned int)updated;
        _InterlockedExchange64((volatile __int64 *)(a1 + 16), v9);
      }
      *(_DWORD *)(a1 + 4) = a2;
      _InterlockedIncrement((volatile signed __int32 *)a1);
      return (unsigned int)updated;
    }
    if ( a2 != v4 )
    {
      updated = BwcUpdateFlow(v8, *(_QWORD *)(a1 + 16));
      if ( updated >= 0 )
        *(_DWORD *)(a1 + 4) = a2;
    }
  }
  else if ( v4 )
  {
    *(_DWORD *)(a1 + 4) = 0;
    _InterlockedDecrement((volatile signed __int32 *)a1);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140013940  mov     r11, rsp
0x140013943  mov     [r11+8], rbx
0x140013947  push    rdi
0x140013948  sub     rsp, 50h
0x14001394c  xor     r8d, r8d
0x14001394f  mov     eax, edx
0x140013951  shl     rax, 0Ah
0x140013955  mov     rbx, rcx
0x140013958  mov     [r11-28h], rax
0x14001395c  mov     eax, [rcx+4]
0x14001395f  mov     edi, edx
0x140013961  mov     qword ptr [r11-30h], 0
0x140013969  mov     qword ptr [r11+18h], 0
0x140013971  mov     [r11-20h], r8
0x140013975  mov     [r11-18h], r8
0x140013979  mov     [r11-38h], r8
0x14001397d  test    edx, edx
0x14001397f  jnz     short loc_14001398E
0x140013981  test    eax, eax
0x140013983  jz      short loc_1400139EC
0x140013985  mov     [rcx+4], r8d
0x140013989  lock dec dword ptr [rcx]
0x14001398c  jmp     short loc_1400139EC
0x14001398e  test    eax, eax
0x140013990  jnz     short loc_1400139D0
0x140013992  mov     rdx, [rcx+10h]
0x140013996  lea     rcx, [rsp+58h+var_38]
0x14001399b  test    rdx, rdx
0x14001399e  jnz     short loc_1400139BC
0x1400139a0  lea     rdx, [rsp+58h+arg_10]
0x1400139a5  call    BwcCreateFlow
0x1400139aa  mov     r8d, eax
0x1400139ad  test    eax, eax
0x1400139af  js      short loc_1400139EC
0x1400139b1  mov     rcx, [rsp+58h+arg_10]
0x1400139b6  xchg    rcx, [rbx+10h]
0x1400139ba  jmp     short loc_1400139C8
0x1400139bc  call    BwcUpdateFlow
0x1400139c1  mov     r8d, eax
0x1400139c4  test    eax, eax
0x1400139c6  js      short loc_1400139EC
0x1400139c8  mov     [rbx+4], edi
0x1400139cb  lock inc dword ptr [rbx]
0x1400139ce  jmp     short loc_1400139EC
0x1400139d0  cmp     edi, eax
0x1400139d2  jz      short loc_1400139EC
0x1400139d4  mov     rdx, [rcx+10h]
0x1400139d8  lea     rcx, [rsp+58h+var_38]
0x1400139dd  call    BwcUpdateFlow
0x1400139e2  mov     r8d, eax
0x1400139e5  test    eax, eax
0x1400139e7  js      short loc_1400139EC
0x1400139e9  mov     [rbx+4], edi
0x1400139ec  mov     rbx, [rsp+58h+arg_0]
0x1400139f1  mov     eax, r8d
0x1400139f4  add     rsp, 50h
0x1400139f8  pop     rdi
0x1400139f9  retn
```
