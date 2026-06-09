# PsmpNetInitializeCallback

- ea: `0x180017890`
- end: `0x1800178f3`
- name: `PsmpNetInitializeCallback`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017890`
- `0x180017f60`

## import_xrefs

- `NduProv!__imp_NduOpenHandle` at `0x1800178a7`
- `NduProv!__imp_NduOpenHandle` at `0x1800178a7`

## pseudocode

```c
__int64 __fastcall PsmpNetInitializeCallback(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // eax
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v4 = NduOpenHandle(&v6);
  if ( v4 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids, v4);
    return 0;
  }
  else
  {
    *a3 = v6;
    return 1;
  }
}

```

## disassembly

```asm
0x180017890  push    rbx
0x180017892  sub     rsp, 20h
0x180017896  lea     rcx, [rsp+28h+arg_18]
0x18001789b  mov     [rsp+28h+arg_18], 0
0x1800178a4  mov     rbx, r8
0x1800178a7  call    cs:__imp_NduOpenHandle
0x1800178ad  test    eax, eax
0x1800178af  jnz     short loc_1800178C0
0x1800178b1  mov     rax, [rsp+28h+arg_18]
0x1800178b6  mov     [rbx], rax
0x1800178b9  mov     eax, 1
0x1800178be  jmp     short loc_1800178ED
0x1800178c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c7  test    byte ptr [rcx+1Ch], 1
0x1800178cb  jz      short loc_1800178EB
0x1800178cd  cmp     byte ptr [rcx+19h], 2
0x1800178d1  jb      short loc_1800178EB
0x1800178d3  mov     rcx, [rcx+10h]
0x1800178d7  lea     r8, WPP_87e93bff43cf31b66581a1de2c4b3e60_Traceguids
0x1800178de  mov     edx, 14h
0x1800178e3  mov     r9d, eax
0x1800178e6  call    WPP_SF_d
0x1800178eb  xor     eax, eax
0x1800178ed  add     rsp, 20h
0x1800178f1  pop     rbx
0x1800178f2  retn
```
