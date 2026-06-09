# WPP_SF_sDsd

- ea: `0x18000b594`
- end: `0x18000b64e`
- name: `WPP_SF_sDsd`
- size: `186`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, __int64, char)`
- caller_count: `69`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180001690`
- `0x180001930`
- `0x180001acc`
- `0x180001de8`
- `0x180001fd0`
- `0x1800022a0`
- `0x180002510`
- `0x1800029e0`
- `0x180003050`
- `0x1800037a0`
- `0x180003f10`
- `0x180004570`
- `0x180005240`
- `0x1800058e0`
- `0x180005cb0`
- `0x180005ec0`
- `0x180006070`
- `0x180006720`
- `0x180006904`
- `0x180006b60`
- `0x180007990`
- `0x180007de4`
- `0x1800081a8`
- `0x180008810`
- `0x180008b80`
- `0x1800091e0`
- `0x1800097f0`
- `0x180009ca0`
- `0x180009fb0`
- `0x18000a120`
- `0x18000a960`
- `0x18000ae00`
- `0x18000b360`
- `0x18000b654`
- `0x18000b6a0`
- `0x18000bb90`
- `0x18000be50`
- `0x18000c1c0`
- `0x18000cc40`
- `0x18000cfb0`
- `0x18000d2b0`
- `0x18000d6cc`
- `0x18000da9c`
- `0x18000dea0`
- `0x18000e320`
- `0x18000e820`
- `0x18000ec00`
- `0x18000eea0`
- `0x18000f2d0`

## callees

- `0x18000b594`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b642`
- `ntdll!EtwTraceMessage` at `0x18000b642`

## pseudocode

```c
__int64 __fastcall WPP_SF_sDsd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, __int64 a6)
{
  __int64 v6; // rax
  __int64 v7; // rdx

  v6 = -1;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_BYTE *)(a6 + v7) );
  }
  if ( a4 )
  {
    do
      ++v6;
    while ( *(_BYTE *)(a4 + v6) );
  }
  return EtwTraceMessage(a1, 43, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids);
}

```

## disassembly

```asm
0x18000b594  push    rbx
0x18000b596  sub     rsp, 70h
0x18000b59a  mov     r8, [rsp+78h+arg_28]
0x18000b5a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b5a6  xor     r11d, r11d
0x18000b5a9  mov     r10d, 5
0x18000b5af  test    r8, r8
0x18000b5b2  jz      short loc_18000B5C5
0x18000b5b4  mov     rdx, rax
0x18000b5b7  inc     rdx
0x18000b5ba  cmp     [r8+rdx], r11b
0x18000b5be  jnz     short loc_18000B5B7
0x18000b5c0  inc     rdx
0x18000b5c3  jmp     short loc_18000B5C8
0x18000b5c5  mov     rdx, r10
0x18000b5c8  test    r8, r8
0x18000b5cb  lea     rbx, aNull; "NULL"
0x18000b5d2  cmovz   r8, rbx
0x18000b5d6  test    r9, r9
0x18000b5d9  jz      short loc_18000B5EB
0x18000b5db  inc     rax
0x18000b5de  cmp     [r9+rax], r11b
0x18000b5e2  jnz     short loc_18000B5DB
0x18000b5e4  lea     r10, [rax+1]
0x18000b5e8  test    r9, r9
0x18000b5eb  mov     [rsp+78h+var_18], r11
0x18000b5f0  lea     rax, [rsp+78h+arg_30]
0x18000b5f8  cmovz   r9, rbx
0x18000b5fc  mov     ebx, 0Ah
0x18000b601  lea     r11d, [rbx-6]
0x18000b605  mov     [rsp+78h+var_20], r11
0x18000b60a  mov     [rsp+78h+var_28], rax
0x18000b60f  lea     rax, [rsp+78h+arg_20]
0x18000b617  mov     [rsp+78h+var_30], rdx
0x18000b61c  lea     edx, [rbx+21h]
0x18000b61f  mov     [rsp+78h+var_38], r8
0x18000b624  lea     r8, WPP_0d7e072671ea36b765e87831c1b7d985_Traceguids
0x18000b62b  mov     [rsp+78h+var_40], r11
0x18000b630  mov     [rsp+78h+var_48], rax
0x18000b635  mov     [rsp+78h+var_50], r10
0x18000b63a  mov     [rsp+78h+var_58], r9
0x18000b63f  mov     r9d, ebx
0x18000b642  call    cs:__imp_EtwTraceMessage
0x18000b648  add     rsp, 70h
0x18000b64c  pop     rbx
0x18000b64d  retn
```
