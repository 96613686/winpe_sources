# LuafvRemoveExtraStreamName

- ea: `0x14001a320`
- end: `0x14001a3c1`
- name: `LuafvRemoveExtraStreamName`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a3c8`

## callees

- `0x14001a320`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a391`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a391`

## pseudocode

```c
char __fastcall LuafvRemoveExtraStreamName(unsigned __int16 *a1, const UNICODE_STRING *a2)
{
  unsigned __int64 v2; // r9
  WCHAR *v5; // r8
  WCHAR *v6; // rdx
  USHORT v7; // ax
  __int16 v8; // cx
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  v5 = (WCHAR *)(v2 + *a1);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v5;
  v6 = v5;
  v7 = 0;
  while ( (unsigned __int64)v5 > v2 )
  {
    v5 = v6 - 1;
    v7 += 2;
    String1.Buffer = v6 - 1;
    String1.Length = v7;
    v8 = *(v6 - 1);
    if ( v8 == 58 )
    {
      String1.MaximumLength = v7;
      LOBYTE(v7) = RtlEqualUnicodeString(&String1, a2, 1u);
      if ( (_BYTE)v7 )
      {
        LOBYTE(v7) = String1.Length;
        *a1 -= String1.Length;
        if ( String1.Buffer > (PWSTR)*((_QWORD *)a1 + 1) && *(String1.Buffer - 1) == 58 )
          *a1 -= 2;
      }
      return v7;
    }
    --v6;
    if ( v8 == 92 )
      return v7;
  }
  return v7;
}

```

## disassembly

```asm
0x14001a320  push    rbx
0x14001a322  sub     rsp, 30h
0x14001a326  mov     r9, [rcx+8]
0x14001a32a  mov     r10, rdx
0x14001a32d  movzx   r8d, word ptr [rcx]
0x14001a331  mov     rbx, rcx
0x14001a334  add     r8, r9
0x14001a337  mov     qword ptr [rsp+38h+String1.Length], 0
0x14001a340  mov     [rsp+38h+String1.Buffer], r8
0x14001a345  mov     rdx, r8
0x14001a348  xor     eax, eax
0x14001a34a  nop     word ptr [rax+rax+00h]
0x14001a350  cmp     r8, r9
0x14001a353  jbe     short loc_14001A37A
0x14001a355  lea     r8, [rdx-2]
0x14001a359  add     ax, 2
0x14001a35d  mov     [rsp+38h+String1.Buffer], r8
0x14001a362  mov     [rsp+38h+String1.Length], ax
0x14001a367  movzx   ecx, word ptr [r8]
0x14001a36b  cmp     cx, 3Ah ; ':'
0x14001a36f  jz      short loc_14001A381
0x14001a371  mov     rdx, r8
0x14001a374  cmp     cx, 5Ch ; '\'
0x14001a378  jnz     short loc_14001A350
0x14001a37a  add     rsp, 30h
0x14001a37e  pop     rbx
0x14001a37f  retn
0x14001a381  mov     r8b, 1; CaseInSensitive
0x14001a384  mov     [rsp+38h+String1.MaximumLength], ax
0x14001a389  mov     rdx, r10; String2
0x14001a38c  lea     rcx, [rsp+38h+String1]; String1
0x14001a391  call    cs:__imp_RtlEqualUnicodeString
0x14001a398  nop     dword ptr [rax+rax+00h]
0x14001a39d  test    al, al
0x14001a39f  jz      short loc_14001A37A
0x14001a3a1  movzx   eax, [rsp+38h+String1.Length]
0x14001a3a6  sub     [rbx], ax
0x14001a3a9  mov     rcx, [rsp+38h+String1.Buffer]
0x14001a3ae  cmp     rcx, [rbx+8]
0x14001a3b2  jbe     short loc_14001A37A
0x14001a3b4  cmp     word ptr [rcx-2], 3Ah ; ':'
0x14001a3b9  jnz     short loc_14001A37A
0x14001a3bb  sub     word ptr [rbx], 2
0x14001a3bf  jmp     short loc_14001A37A
```
