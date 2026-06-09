# LuafvRemoveExtraStreamName

- ea: `0x14001a2d0`
- end: `0x14001a371`
- name: `LuafvRemoveExtraStreamName`
- size: `161`
- prototype: `char __fastcall(unsigned __int16 *, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a378`

## callees

- `0x14001a2d0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a341`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a341`

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
0x14001a2d0  push    rbx
0x14001a2d2  sub     rsp, 30h
0x14001a2d6  mov     r9, [rcx+8]
0x14001a2da  mov     r10, rdx
0x14001a2dd  movzx   r8d, word ptr [rcx]
0x14001a2e1  mov     rbx, rcx
0x14001a2e4  add     r8, r9
0x14001a2e7  mov     qword ptr [rsp+38h+String1.Length], 0
0x14001a2f0  mov     [rsp+38h+String1.Buffer], r8
0x14001a2f5  mov     rdx, r8
0x14001a2f8  xor     eax, eax
0x14001a2fa  nop     word ptr [rax+rax+00h]
0x14001a300  cmp     r8, r9
0x14001a303  jbe     short loc_14001A32A
0x14001a305  lea     r8, [rdx-2]
0x14001a309  add     ax, 2
0x14001a30d  mov     [rsp+38h+String1.Buffer], r8
0x14001a312  mov     [rsp+38h+String1.Length], ax
0x14001a317  movzx   ecx, word ptr [r8]
0x14001a31b  cmp     cx, 3Ah ; ':'
0x14001a31f  jz      short loc_14001A331
0x14001a321  mov     rdx, r8
0x14001a324  cmp     cx, 5Ch ; '\'
0x14001a328  jnz     short loc_14001A300
0x14001a32a  add     rsp, 30h
0x14001a32e  pop     rbx
0x14001a32f  retn
0x14001a331  mov     r8b, 1; CaseInSensitive
0x14001a334  mov     [rsp+38h+String1.MaximumLength], ax
0x14001a339  mov     rdx, r10; String2
0x14001a33c  lea     rcx, [rsp+38h+String1]; String1
0x14001a341  call    cs:__imp_RtlEqualUnicodeString
0x14001a348  nop     dword ptr [rax+rax+00h]
0x14001a34d  test    al, al
0x14001a34f  jz      short loc_14001A32A
0x14001a351  movzx   eax, [rsp+38h+String1.Length]
0x14001a356  sub     [rbx], ax
0x14001a359  mov     rcx, [rsp+38h+String1.Buffer]
0x14001a35e  cmp     rcx, [rbx+8]
0x14001a362  jbe     short loc_14001A32A
0x14001a364  cmp     word ptr [rcx-2], 3Ah ; ':'
0x14001a369  jnz     short loc_14001A32A
0x14001a36b  sub     word ptr [rbx], 2
0x14001a36f  jmp     short loc_14001A32A
```
