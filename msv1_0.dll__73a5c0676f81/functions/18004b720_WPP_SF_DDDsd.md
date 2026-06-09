# WPP_SF_DDDsd

- ea: `0x18004b720`
- end: `0x18004b7a4`
- name: `WPP_SF_DDDsd`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a20`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18004b796`
- `ntdll!EtwTraceMessage` at `0x18004b796`

## string_xrefs

- `0x18004b75b`: `onecore\ds\security\protocols\msv_sspi\credapi.cxx`

## pseudocode

```c
__int64 __fastcall WPP_SF_DDDsd(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
}

```

## disassembly

```asm
0x18004b720  mov     r11, rsp
0x18004b723  mov     [r11+20h], r9d
0x18004b727  sub     rsp, 98h
0x18004b72e  mov     qword ptr [r11-28h], 0
0x18004b736  lea     rax, [r11-18h]
0x18004b73a  mov     r9d, 26h ; '&'
0x18004b740  mov     dword ptr [r11-18h], 495h
0x18004b748  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18004b74f  lea     edx, [r9-22h]
0x18004b753  mov     [r11-30h], rdx
0x18004b757  mov     [r11-38h], rax
0x18004b75b  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\msv_s"...
0x18004b762  mov     qword ptr [r11-40h], 33h ; '3'
0x18004b76a  mov     [r11-48h], rax
0x18004b76e  lea     rax, [r11+30h]
0x18004b772  mov     [r11-50h], rdx
0x18004b776  mov     [r11-58h], rax
0x18004b77a  lea     rax, [r11+28h]
0x18004b77e  mov     [r11-60h], rdx
0x18004b782  mov     [r11-68h], rax
0x18004b786  lea     rax, [r11+20h]
0x18004b78a  mov     [r11-70h], rdx
0x18004b78e  lea     edx, [r9+5]
0x18004b792  mov     [r11-78h], rax
0x18004b796  call    cs:__imp_EtwTraceMessage
0x18004b79c  add     rsp, 98h
0x18004b7a3  retn
```
