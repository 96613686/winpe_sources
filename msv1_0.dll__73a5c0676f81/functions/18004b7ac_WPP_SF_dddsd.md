# WPP_SF_dddsd

- ea: `0x18004b7ac`
- end: `0x18004b830`
- name: `WPP_SF_dddsd`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d14`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18004b822`
- `ntdll!EtwTraceMessage` at `0x18004b822`

## string_xrefs

- `0x18004b7e7`: `onecore\ds\security\protocols\msv_sspi\credapi.cxx`

## pseudocode

```c
__int64 __fastcall WPP_SF_dddsd(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
}

```

## disassembly

```asm
0x18004b7ac  mov     r11, rsp
0x18004b7af  mov     [r11+20h], r9d
0x18004b7b3  sub     rsp, 98h
0x18004b7ba  mov     qword ptr [r11-28h], 0
0x18004b7c2  lea     rax, [r11-18h]
0x18004b7c6  mov     r9d, 1Bh
0x18004b7cc  mov     dword ptr [r11-18h], 374h
0x18004b7d4  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18004b7db  lea     edx, [r9-17h]
0x18004b7df  mov     [r11-30h], rdx
0x18004b7e3  mov     [r11-38h], rax
0x18004b7e7  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\msv_s"...
0x18004b7ee  mov     qword ptr [r11-40h], 33h ; '3'
0x18004b7f6  mov     [r11-48h], rax
0x18004b7fa  lea     rax, [r11+30h]
0x18004b7fe  mov     [r11-50h], rdx
0x18004b802  mov     [r11-58h], rax
0x18004b806  lea     rax, [r11+28h]
0x18004b80a  mov     [r11-60h], rdx
0x18004b80e  mov     [r11-68h], rax
0x18004b812  lea     rax, [r11+20h]
0x18004b816  mov     [r11-70h], rdx
0x18004b81a  lea     edx, [r9+10h]
0x18004b81e  mov     [r11-78h], rax
0x18004b822  call    cs:__imp_EtwTraceMessage
0x18004b828  add     rsp, 98h
0x18004b82f  retn
```
