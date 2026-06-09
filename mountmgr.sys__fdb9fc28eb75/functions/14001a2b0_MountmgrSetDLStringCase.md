# MountmgrSetDLStringCase

- ea: `0x14001a2b0`
- end: `0x14001a3c7`
- name: `MountmgrSetDLStringCase`
- size: `279`
- prototype: `__int64 __fastcall(UNICODE_STRING *, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be4c`
- `0x14000c2d4`
- `0x14000ff00`
- `0x140014fc0`

## callees

- `0x140001ae0`
- `0x140003280`
- `0x14001a2b0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a310`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001a310`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001a36d`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001a36d`

## pseudocode

```c
__int64 __fastcall MountmgrSetDLStringCase(UNICODE_STRING *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  BOOLEAN v5; // al
  __int64 v6; // r8
  WCHAR v7; // di
  PWSTR Buffer; // rcx

  if ( a1->Length == 28 )
  {
    a1->Length = 24;
    v5 = RtlEqualUnicodeString(a1, &String2, 1u);
    a1->Length = 28;
    if ( v5 )
    {
      v7 = RtlUpcaseUnicodeChar(a1->Buffer[12]);
      result = (__int64)memset(a1->Buffer, 0, a1->MaximumLength);
      Buffer = a1->Buffer;
      *(_OWORD *)Buffer = *(_OWORD *)L"\\DosDevices\\";
      *((_QWORD *)Buffer + 2) = *(_QWORD *)L"ces\\";
      Buffer[12] = v7;
      Buffer[13] = 58;
    }
    else
    {
      result = (__int64)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 1) != 0 )
          return WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 350, v6, 0);
      }
    }
  }
  else
  {
    result = (__int64)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        return WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 349, a3, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a2b0  push    rbx
0x14001a2b2  sub     rsp, 40h
0x14001a2b6  cmp     word ptr [rcx], 1Ch
0x14001a2ba  mov     rbx, rcx
0x14001a2bd  jz      short loc_14001A301
0x14001a2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2c6  lea     rax, WPP_GLOBAL_Control
0x14001a2cd  cmp     rcx, rax
0x14001a2d0  jz      loc_14001A3C0
0x14001a2d6  mov     eax, [rcx+2Ch]
0x14001a2d9  test    al, 1
0x14001a2db  jz      loc_14001A3C0
0x14001a2e1  cmp     byte ptr [rcx+29h], 2
0x14001a2e5  jb      loc_14001A3C0
0x14001a2eb  mov     rcx, [rcx+18h]
0x14001a2ef  mov     edx, 15Dh
0x14001a2f4  xor     r9d, r9d
0x14001a2f7  call    WPP_SF_L
0x14001a2fc  jmp     loc_14001A3C0
0x14001a301  mov     r8b, 1; CaseInSensitive
0x14001a304  mov     word ptr [rcx], 18h
0x14001a309  lea     rdx, String2; String2
0x14001a310  call    cs:__imp_RtlEqualUnicodeString
0x14001a317  nop     dword ptr [rax+rax+00h]
0x14001a31c  mov     word ptr [rbx], 1Ch
0x14001a321  test    al, al
0x14001a323  jnz     short loc_14001A356
0x14001a325  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a32c  lea     rax, WPP_GLOBAL_Control
0x14001a333  cmp     rcx, rax
0x14001a336  jz      loc_14001A3C0
0x14001a33c  mov     eax, [rcx+2Ch]
0x14001a33f  test    al, 1
0x14001a341  jz      short loc_14001A3C0
0x14001a343  mov     rcx, [rcx+18h]
0x14001a347  mov     edx, 15Eh
0x14001a34c  xor     r9d, r9d
0x14001a34f  call    WPP_SF_L
0x14001a354  jmp     short loc_14001A3C0
0x14001a356  mov     rcx, [rbx+8]
0x14001a35a  mov     [rsp+48h+arg_0], rdi
0x14001a35f  movaps  [rsp+48h+var_18], xmm6
0x14001a364  movaps  [rsp+48h+var_28], xmm7
0x14001a369  movzx   ecx, word ptr [rcx+18h]; SourceCharacter
0x14001a36d  call    cs:__imp_RtlUpcaseUnicodeChar
0x14001a374  nop     dword ptr [rax+rax+00h]
0x14001a379  movzx   r8d, word ptr [rbx+2]; Size
0x14001a37e  xor     edx, edx; Val
0x14001a380  mov     rcx, [rbx+8]; void *
0x14001a384  movzx   edi, ax
0x14001a387  movups  xmm7, xmmword ptr cs:aDosdevices; "\\DosDevices\\"
0x14001a38e  movsd   xmm6, qword ptr cs:aDosdevices+10h; "ces\\"
0x14001a396  call    memset
0x14001a39b  mov     rcx, [rbx+8]
0x14001a39f  movups  xmmword ptr [rcx], xmm7
0x14001a3a2  movaps  xmm7, [rsp+48h+var_28]
0x14001a3a7  movsd   qword ptr [rcx+10h], xmm6
0x14001a3ac  movaps  xmm6, [rsp+48h+var_18]
0x14001a3b1  mov     [rcx+18h], di
0x14001a3b5  mov     rdi, [rsp+48h+arg_0]
0x14001a3ba  mov     word ptr [rcx+1Ah], 3Ah ; ':'
0x14001a3c0  add     rsp, 40h
0x14001a3c4  pop     rbx
0x14001a3c5  retn
```
