# GetSinglePrivateComputerProp

- ea: `0x180004d74`
- end: `0x180004dbd`
- name: `GetSinglePrivateComputerProp`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004bb4`
- `0x1800085c0`

## import_xrefs

- `mqrt!MQGetPrivateComputerInformation` at `0x180004db2`
- `mqrt!MQGetPrivateComputerInformation` at `0x180004db2`

## pseudocode

```c
HRESULT __fastcall GetSinglePrivateComputerProp(int a1, MQPROPVARIANT *a2, const WCHAR *a3)
{
  MQPRIVATEPROPS v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF

  v5 = a1;
  v4.aPropID = (QMPROPID *)&v5;
  a2->vt = 1;
  v4.aPropVar = a2;
  v4.aStatus = &v6;
  *(_QWORD *)&v4.cProp = 1;
  v6 = 0;
  return MQGetPrivateComputerInformation(a3, &v4);
}

```

## disassembly

```asm
0x180004d74  mov     r11, rsp
0x180004d77  sub     rsp, 48h
0x180004d7b  mov     [rsp+48h+arg_0], ecx
0x180004d7f  lea     rax, [r11+8]
0x180004d83  mov     ecx, 1
0x180004d88  mov     [r11-20h], rax
0x180004d8c  mov     [rdx], cx
0x180004d8f  lea     rax, [r11+10h]
0x180004d93  mov     [r11-18h], rdx
0x180004d97  mov     rcx, r8; lpwcsComputerName
0x180004d9a  lea     rdx, [r11-28h]; pPrivateProps
0x180004d9e  mov     [r11-10h], rax
0x180004da2  mov     qword ptr [r11-28h], 1
0x180004daa  mov     [rsp+48h+arg_8], 0
0x180004db2  call    cs:__imp_MQGetPrivateComputerInformation
0x180004db8  add     rsp, 48h
0x180004dbc  retn
```
