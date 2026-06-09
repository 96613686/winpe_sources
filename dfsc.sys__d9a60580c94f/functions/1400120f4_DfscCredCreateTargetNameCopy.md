# DfscCredCreateTargetNameCopy

- ea: `0x1400120f4`
- end: `0x140012151`
- name: `DfscCredCreateTargetNameCopy`
- size: `93`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002545c`

## callees

- `0x1400120f4`
- `0x140022620`

## pseudocode

```c
__int64 __fastcall DfscCredCreateTargetNameCopy(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned __int16 *v3; // rdi
  __int64 v5; // r8
  unsigned int NameFromUnicodeString; // edx

  v3 = (unsigned __int16 *)(a1 + 8);
  v5 = *(unsigned __int16 *)(a1 + 8);
  if ( (unsigned int)*a3 >= (unsigned __int64)(v5 + 2) )
  {
    NameFromUnicodeString = DfscCreateNameFromUnicodeString(a2, v3, 2017683012);
    if ( !NameFromUnicodeString )
      *a3 = *v3 + 2;
  }
  else
  {
    NameFromUnicodeString = -2147483643;
    *a3 = v5 + 2;
  }
  return NameFromUnicodeString;
}

```

## disassembly

```asm
0x1400120f4  mov     [rsp+arg_0], rbx
0x1400120f9  push    rdi
0x1400120fa  sub     rsp, 20h
0x1400120fe  lea     rdi, [rcx+8]
0x140012102  mov     rbx, r8
0x140012105  movzx   r8d, word ptr [rdi]
0x140012109  mov     r9, rdx
0x14001210c  mov     eax, [rbx]
0x14001210e  lea     rcx, [r8+2]
0x140012112  cmp     rax, rcx
0x140012115  jnb     short loc_140012124
0x140012117  lea     eax, [r8+2]
0x14001211b  mov     edx, 80000005h
0x140012120  mov     [rbx], eax
0x140012122  jmp     short loc_140012143
0x140012124  mov     r8d, 78436644h
0x14001212a  mov     rdx, rdi
0x14001212d  mov     rcx, r9
0x140012130  call    DfscCreateNameFromUnicodeString
0x140012135  mov     edx, eax
0x140012137  test    eax, eax
0x140012139  jnz     short loc_140012143
0x14001213b  movzx   ecx, word ptr [rdi]
0x14001213e  add     ecx, 2
0x140012141  mov     [rbx], ecx
0x140012143  mov     rbx, [rsp+28h+arg_0]
0x140012148  mov     eax, edx
0x14001214a  add     rsp, 20h
0x14001214e  pop     rdi
0x14001214f  retn
```
