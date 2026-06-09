# FindNodeOrParent

- ea: `0x14001cea0`
- end: `0x14001cf72`
- name: `FindNodeOrParent`
- size: `210`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c3d0`
- `0x14001cd14`
- `0x14001ce44`

## callees

- `0x14001cea0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cedf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cedf`

## pseudocode

```c
__int64 __fastcall FindNodeOrParent(__int64 *a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbx
  int v6; // edi
  signed __int64 v7; // rax
  __int64 result; // rax

  if ( !*((_DWORD *)a1 + 4) )
    return 0;
  v5 = *a1;
  v6 = *((_DWORD *)a1 + 5);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v6 )
      {
        v7 = *(_QWORD *)(a2 + 8) - *(_QWORD *)(v5 + 32);
        if ( !v7 )
          v7 = (*(_QWORD *)a2 & 0xFFFFFFFFFFFFFFF8uLL) - (*(_QWORD *)(v5 + 24) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      else
      {
        v7 = RtlCompareUnicodeString((PCUNICODE_STRING)(a2 + 8), (PCUNICODE_STRING)(v5 + 32), 1u);
      }
      if ( v7 < 0 )
        break;
      if ( v7 <= 0 )
      {
        result = 1;
        goto LABEL_8;
      }
      if ( !*(_QWORD *)(v5 + 16) )
      {
        result = 3;
        goto LABEL_8;
      }
      v5 = *(_QWORD *)(v5 + 16);
    }
    if ( !*(_QWORD *)(v5 + 8) )
      break;
    v5 = *(_QWORD *)(v5 + 8);
  }
  result = 2;
LABEL_8:
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x14001cea0  mov     [rsp+arg_18], rsi
0x14001cea5  push    r15
0x14001cea7  sub     rsp, 20h
0x14001ceab  cmp     dword ptr [rcx+10h], 0
0x14001ceaf  mov     rsi, r8
0x14001ceb2  mov     r15, rdx
0x14001ceb5  jz      loc_14001CF44
0x14001cebb  mov     [rsp+28h+arg_0], rbx
0x14001cec0  mov     rbx, [rcx]
0x14001cec3  mov     [rsp+28h+arg_8], rdi
0x14001cec8  mov     edi, [rcx+14h]
0x14001cecb  mov     [rsp+28h+arg_10], r14
0x14001ced0  test    edi, edi
0x14001ced2  jnz     short loc_14001CF18
0x14001ced4  mov     r8b, 1; CaseInSensitive
0x14001ced7  lea     rdx, [rbx+20h]; String2
0x14001cedb  lea     rcx, [r15+8]; String1
0x14001cedf  call    cs:__imp_RtlCompareUnicodeString
0x14001cee6  nop     dword ptr [rax+rax+00h]
0x14001ceeb  cdqe
0x14001ceed  test    rax, rax
0x14001cef0  js      short loc_14001CF5A
0x14001cef2  jg      short loc_14001CF36
0x14001cef4  mov     eax, 1
0x14001cef9  mov     rdi, [rsp+28h+arg_8]
0x14001cefe  mov     r14, [rsp+28h+arg_10]
0x14001cf03  mov     [rsi], rbx
0x14001cf06  mov     rbx, [rsp+28h+arg_0]
0x14001cf0b  mov     rsi, [rsp+28h+arg_18]
0x14001cf10  add     rsp, 20h
0x14001cf14  pop     r15
0x14001cf16  retn
0x14001cf18  mov     rax, [r15+8]
0x14001cf1c  sub     rax, [rbx+20h]
0x14001cf20  jnz     short loc_14001CEED
0x14001cf22  mov     rax, [r15]
0x14001cf25  mov     rcx, [rbx+18h]
0x14001cf29  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001cf2d  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001cf31  sub     rax, rcx
0x14001cf34  jmp     short loc_14001CEED
0x14001cf36  mov     rax, [rbx+10h]
0x14001cf3a  test    rax, rax
0x14001cf3d  jz      short loc_14001CF53
0x14001cf3f  mov     rbx, rax
0x14001cf42  jmp     short loc_14001CED0
0x14001cf44  mov     rsi, [rsp+28h+arg_18]
0x14001cf49  xor     eax, eax
0x14001cf4b  add     rsp, 20h
0x14001cf4f  pop     r15
0x14001cf51  retn
0x14001cf53  mov     eax, 3
0x14001cf58  jmp     short loc_14001CEF9
0x14001cf5a  mov     rax, [rbx+8]
0x14001cf5e  test    rax, rax
0x14001cf61  jz      short loc_14001CF6B
0x14001cf63  mov     rbx, rax
0x14001cf66  jmp     loc_14001CED0
0x14001cf6b  mov     eax, 2
0x14001cf70  jmp     short loc_14001CEF9
```
