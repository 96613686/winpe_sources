# FindNodeOrParent

- ea: `0x14001cef0`
- end: `0x14001cfc2`
- name: `FindNodeOrParent`
- size: `210`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c420`
- `0x14001cd64`
- `0x14001ce94`

## callees

- `0x14001cef0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cf2f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001cf2f`

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
0x14001cef0  mov     [rsp+arg_18], rsi
0x14001cef5  push    r15
0x14001cef7  sub     rsp, 20h
0x14001cefb  cmp     dword ptr [rcx+10h], 0
0x14001ceff  mov     rsi, r8
0x14001cf02  mov     r15, rdx
0x14001cf05  jz      loc_14001CF94
0x14001cf0b  mov     [rsp+28h+arg_0], rbx
0x14001cf10  mov     rbx, [rcx]
0x14001cf13  mov     [rsp+28h+arg_8], rdi
0x14001cf18  mov     edi, [rcx+14h]
0x14001cf1b  mov     [rsp+28h+arg_10], r14
0x14001cf20  test    edi, edi
0x14001cf22  jnz     short loc_14001CF68
0x14001cf24  mov     r8b, 1; CaseInSensitive
0x14001cf27  lea     rdx, [rbx+20h]; String2
0x14001cf2b  lea     rcx, [r15+8]; String1
0x14001cf2f  call    cs:__imp_RtlCompareUnicodeString
0x14001cf36  nop     dword ptr [rax+rax+00h]
0x14001cf3b  cdqe
0x14001cf3d  test    rax, rax
0x14001cf40  js      short loc_14001CFAA
0x14001cf42  jg      short loc_14001CF86
0x14001cf44  mov     eax, 1
0x14001cf49  mov     rdi, [rsp+28h+arg_8]
0x14001cf4e  mov     r14, [rsp+28h+arg_10]
0x14001cf53  mov     [rsi], rbx
0x14001cf56  mov     rbx, [rsp+28h+arg_0]
0x14001cf5b  mov     rsi, [rsp+28h+arg_18]
0x14001cf60  add     rsp, 20h
0x14001cf64  pop     r15
0x14001cf66  retn
0x14001cf68  mov     rax, [r15+8]
0x14001cf6c  sub     rax, [rbx+20h]
0x14001cf70  jnz     short loc_14001CF3D
0x14001cf72  mov     rax, [r15]
0x14001cf75  mov     rcx, [rbx+18h]
0x14001cf79  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001cf7d  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14001cf81  sub     rax, rcx
0x14001cf84  jmp     short loc_14001CF3D
0x14001cf86  mov     rax, [rbx+10h]
0x14001cf8a  test    rax, rax
0x14001cf8d  jz      short loc_14001CFA3
0x14001cf8f  mov     rbx, rax
0x14001cf92  jmp     short loc_14001CF20
0x14001cf94  mov     rsi, [rsp+28h+arg_18]
0x14001cf99  xor     eax, eax
0x14001cf9b  add     rsp, 20h
0x14001cf9f  pop     r15
0x14001cfa1  retn
0x14001cfa3  mov     eax, 3
0x14001cfa8  jmp     short loc_14001CF49
0x14001cfaa  mov     rax, [rbx+8]
0x14001cfae  test    rax, rax
0x14001cfb1  jz      short loc_14001CFBB
0x14001cfb3  mov     rbx, rax
0x14001cfb6  jmp     loc_14001CF20
0x14001cfbb  mov     eax, 2
0x14001cfc0  jmp     short loc_14001CF49
```
