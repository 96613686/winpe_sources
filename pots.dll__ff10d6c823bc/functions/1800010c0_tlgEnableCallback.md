# _tlgEnableCallback

- ea: `0x1800010c0`
- end: `0x180001136`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010c0`
- `0x180005010`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        __int64 a1,
        int a2,
        unsigned __int8 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // eax
  void (__fastcall *v8)(__int64); // rax

  if ( a7 )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        if ( a3 )
          v7 = a3 + 1;
        else
          v7 = 256;
        *(_DWORD *)a7 = v7;
        *(_QWORD *)(a7 + 16) = a4;
        *(_QWORD *)(a7 + 24) = a5;
      }
    }
    else
    {
      *(_DWORD *)a7 = 0;
    }
    v8 = *(void (__fastcall **)(__int64))(a7 + 40);
    if ( v8 )
      v8(a1);
  }
}

```

## disassembly

```asm
0x1800010c0  sub     rsp, 48h
0x1800010c4  mov     r11, rcx
0x1800010c7  mov     rcx, [rsp+48h+arg_30]
0x1800010cf  test    rcx, rcx
0x1800010d2  jz      short loc_180001131
0x1800010d4  mov     r10, [rsp+48h+arg_20]
0x1800010d9  mov     eax, edx
0x1800010db  test    edx, edx
0x1800010dd  jz      short loc_180001102
0x1800010df  cmp     eax, 1
0x1800010e2  jnz     short loc_180001108
0x1800010e4  test    r8b, r8b
0x1800010e7  jz      short loc_1800010F1
0x1800010e9  movzx   eax, r8b
0x1800010ed  inc     eax
0x1800010ef  jmp     short loc_1800010F6
0x1800010f1  mov     eax, 100h
0x1800010f6  mov     [rcx], eax
0x1800010f8  mov     [rcx+10h], r9
0x1800010fc  mov     [rcx+18h], r10
0x180001100  jmp     short loc_180001108
0x180001102  mov     dword ptr [rcx], 0
0x180001108  mov     rax, [rcx+28h]
0x18000110c  test    rax, rax
0x18000110f  jz      short loc_180001131
0x180001111  mov     rcx, [rcx+30h]
0x180001115  mov     [rsp+48h+var_18], rcx
0x18000111a  mov     rcx, [rsp+48h+arg_28]
0x18000111f  mov     [rsp+48h+var_20], rcx
0x180001124  mov     rcx, r11
0x180001127  mov     [rsp+48h+var_28], r10
0x18000112c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001131  add     rsp, 48h
0x180001135  retn
```
