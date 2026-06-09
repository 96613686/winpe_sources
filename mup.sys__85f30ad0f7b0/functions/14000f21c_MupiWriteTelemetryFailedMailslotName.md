# MupiWriteTelemetryFailedMailslotName

- ea: `0x14000f21c`
- end: `0x14000f27d`
- name: `MupiWriteTelemetryFailedMailslotName`
- size: `97`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001a128`

## callees

- `0x140002668`
- `0x140005044`
- `0x14000f21c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f248`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f248`

## pseudocode

```c
void __fastcall MupiWriteTelemetryFailedMailslotName(PCUNICODE_STRING String2)
{
  unsigned __int16 i; // bx

  for ( i = 0; i < 6u; ++i )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&qword_140007080[2 * i], String2, 1u) )
    {
      MupWriteTelemetryKnownRemoteMailslotFailed(String2);
      return;
    }
  }
  if ( i == 6 )
    MupWriteTelemetryOtherRemoteMailslotFailed(String2);
}

```

## disassembly

```asm
0x14000f21c  mov     [rsp+arg_0], rbx
0x14000f221  push    rdi
0x14000f222  sub     rsp, 20h
0x14000f226  mov     rdi, rcx
0x14000f229  xor     ebx, ebx
0x14000f22b  cmp     bx, 6
0x14000f22f  jnb     short loc_14000F267
0x14000f231  lea     rax, qword_140007080
0x14000f238  movzx   ecx, bx
0x14000f23b  shl     rcx, 4
0x14000f23f  mov     r8b, 1; CaseInSensitive
0x14000f242  add     rcx, rax; String1
0x14000f245  mov     rdx, rdi; String2
0x14000f248  call    cs:__imp_RtlCompareUnicodeString
0x14000f24f  nop     dword ptr [rax+rax+00h]
0x14000f254  test    eax, eax
0x14000f256  jz      short loc_14000F25D
0x14000f258  inc     bx
0x14000f25b  jmp     short loc_14000F22B
0x14000f25d  mov     rcx, rdi
0x14000f260  call    MupWriteTelemetryKnownRemoteMailslotFailed
0x14000f265  jmp     short loc_14000F271
0x14000f267  jnz     short loc_14000F271
0x14000f269  mov     rcx, rdi
0x14000f26c  call    MupWriteTelemetryOtherRemoteMailslotFailed
0x14000f271  mov     rbx, [rsp+28h+arg_0]
0x14000f276  add     rsp, 20h
0x14000f27a  pop     rdi
0x14000f27b  retn
```
