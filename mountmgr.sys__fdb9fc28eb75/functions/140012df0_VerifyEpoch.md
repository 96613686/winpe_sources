# VerifyEpoch

- ea: `0x140012df0`
- end: `0x140012e59`
- name: `VerifyEpoch`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a810`
- `0x14000b5e8`
- `0x14000e340`
- `0x14000ecbc`
- `0x14000f680`
- `0x140010d00`
- `0x140010ef0`
- `0x140011500`
- `0x1400119a0`
- `0x140012e60`
- `0x1400135a0`
- `0x140013e70`

## callees

- `0x140001ae0`
- `0x140012df0`

## pseudocode

```c
__int64 __fastcall VerifyEpoch(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx

  if ( *(_QWORD *)(a1 + 336) == a2 )
    return 0;
  v3 = *(_QWORD **)(a1 + 16);
  v4 = (_QWORD *)(a1 + 16);
  if ( v3 != v4 )
  {
    while ( a3 != v3[22] )
    {
      v3 = (_QWORD *)*v3;
      if ( v3 == v4 )
        goto LABEL_6;
    }
    return 0;
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_L((__int64)WPP_GLOBAL_Control->AttachedDevice, 0x13u, a3, -1073741810);
  return 3221225486LL;
}

```

## disassembly

```asm
0x140012df0  sub     rsp, 28h
0x140012df4  cmp     [rcx+150h], rdx
0x140012dfb  jz      short loc_140012E13
0x140012dfd  mov     rax, [rcx+10h]
0x140012e01  add     rcx, 10h
0x140012e05  cmp     rax, rcx
0x140012e08  jz      short loc_140012E23
0x140012e0a  cmp     r8, [rax+0B0h]
0x140012e11  jnz     short loc_140012E1B
0x140012e13  xor     eax, eax
0x140012e15  add     rsp, 28h
0x140012e19  retn
0x140012e1b  mov     rax, [rax]
0x140012e1e  cmp     rax, rcx
0x140012e21  jnz     short loc_140012E0A
0x140012e23  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e2a  lea     rdx, WPP_GLOBAL_Control
0x140012e31  cmp     rcx, rdx
0x140012e34  jz      short loc_140012E52
0x140012e36  mov     edx, [rcx+2Ch]
0x140012e39  test    dl, 1
0x140012e3c  jz      short loc_140012E52
0x140012e3e  mov     rcx, [rcx+18h]
0x140012e42  mov     edx, 13h
0x140012e47  mov     r9d, 0C000000Eh
0x140012e4d  call    WPP_SF_L
0x140012e52  mov     eax, 0C000000Eh
0x140012e57  jmp     short loc_140012E15
```
