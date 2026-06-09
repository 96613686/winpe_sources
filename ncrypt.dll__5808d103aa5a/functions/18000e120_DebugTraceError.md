# DebugTraceError

- ea: `0x18000e120`
- end: `0x18000e15e`
- name: `DebugTraceError`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `128`
- callee_count: `2`
- tags: ``

## callers

- `0x180001550`
- `0x180001c08`
- `0x180001e78`
- `0x180002280`
- `0x180002400`
- `0x18000260c`
- `0x180002790`
- `0x180002c34`
- `0x180002f74`
- `0x180003150`
- `0x180003460`
- `0x18000382c`
- `0x180003ce4`
- `0x180003f1c`
- `0x18000423c`
- `0x180004310`
- `0x180004454`
- `0x180004c00`
- `0x1800050d0`
- `0x1800053ac`
- `0x1800058b0`
- `0x180005a18`
- `0x180005fa0`
- `0x180006090`
- `0x180006730`
- `0x180006a70`
- `0x180006c9c`
- `0x180007420`
- `0x1800077f0`
- `0x180007df4`
- `0x1800081e8`
- `0x180008a90`
- `0x180008c1c`
- `0x180008da0`
- `0x1800090e0`
- `0x18000962c`
- `0x180009830`
- `0x180009aa0`
- `0x180009cf0`
- `0x180009e50`
- `0x180009ecc`
- `0x18000a3d0`
- `0x18000a7e0`
- `0x18000aa90`
- `0x18000adc0`
- `0x18000b4f0`
- `0x18000b6c0`
- `0x18000b8a0`
- `0x18000ba30`
- `0x18000bb60`

## callees

- `0x18000d02c`
- `0x18000e120`

## pseudocode

```c
__int64 __fastcall DebugTraceError(unsigned int a1, int a2, __int64 a3, char a4)
{
  __int64 result; // rax

  result = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_sDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a1, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18000e120  sub     rsp, 48h
0x18000e124  mov     eax, ecx
0x18000e126  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e12d  lea     r10, WPP_GLOBAL_Control
0x18000e134  cmp     rcx, r10
0x18000e137  jz      short loc_18000E159
0x18000e139  test    byte ptr [rcx+1Ch], 1
0x18000e13d  jz      short loc_18000E159
0x18000e13f  mov     rcx, [rcx+10h]
0x18000e143  mov     [rsp+48h+var_18], r9d
0x18000e148  mov     r9, rdx
0x18000e14b  mov     [rsp+48h+var_20], r8
0x18000e150  mov     [rsp+48h+var_28], eax
0x18000e154  call    WPP_SF_sDsd
0x18000e159  add     rsp, 48h
0x18000e15d  retn
```
