# LuafvCompareDirectoryEntryName

- ea: `0x1400226b4`
- end: `0x14002272d`
- name: `LuafvCompareDirectoryEntryName`
- size: `121`
- prototype: `LONG __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140024050`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002271b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002271b`

## pseudocode

```c
LONG __fastcall LuafvCompareDirectoryEntryName(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // r10
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING v6; // [rsp+30h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a1 + 96);
  v6 = 0;
  v5 = 0;
  v6.Length = *(_WORD *)(a3 + *(_QWORD *)(v3 + 24));
  v6.MaximumLength = v6.Length;
  v6.Buffer = (PWSTR)(a2 + *(_QWORD *)(v3 + 24));
  v5.Length = *(_WORD *)(a3 + *(_QWORD *)(v3 + 56));
  v5.MaximumLength = v5.Length;
  v5.Buffer = (PWSTR)(a2 + *(_QWORD *)(v3 + 56));
  return RtlCompareUnicodeString(&v6, &v5, 1u);
}

```

## disassembly

```asm
0x1400226b4  mov     r11, rsp
0x1400226b7  sub     rsp, 48h
0x1400226bb  mov     r10, [rcx+60h]
0x1400226bf  xorps   xmm0, xmm0
0x1400226c2  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x1400226c7  mov     r9d, r8d
0x1400226ca  mov     r8b, 1; CaseInSensitive
0x1400226cd  mov     edx, edx
0x1400226cf  xorps   xmm1, xmm1
0x1400226d2  movups  [rsp+48h+var_28], xmm1
0x1400226d7  mov     rax, [r10+18h]
0x1400226db  movzx   ecx, word ptr [r9+rax]
0x1400226e0  mov     [rsp+48h+var_18.Length], cx
0x1400226e5  mov     [rsp+48h+var_18.MaximumLength], cx
0x1400226ea  mov     rcx, [r10+18h]
0x1400226ee  add     rcx, rdx
0x1400226f1  mov     [r11-10h], rcx
0x1400226f5  mov     rax, [r10+38h]
0x1400226f9  movzx   ecx, word ptr [r9+rax]
0x1400226fe  mov     word ptr [rsp+48h+var_28], cx
0x140022703  mov     word ptr [rsp+48h+var_28+2], cx
0x140022708  mov     rcx, [r10+38h]
0x14002270c  add     rcx, rdx
0x14002270f  lea     rdx, [r11-28h]; String2
0x140022713  mov     [r11-20h], rcx
0x140022717  lea     rcx, [r11-18h]; String1
0x14002271b  call    cs:__imp_RtlCompareUnicodeString
0x140022722  nop     dword ptr [rax+rax+00h]
0x140022727  add     rsp, 48h
0x14002272b  retn
```
