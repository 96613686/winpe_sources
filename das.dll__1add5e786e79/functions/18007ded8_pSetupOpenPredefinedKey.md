# pSetupOpenPredefinedKey

- ea: `0x18007ded8`
- end: `0x18007df4f`
- name: `pSetupOpenPredefinedKey`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18007ddd8`

## callees

- `0x18007dd84`
- `0x18007debc`
- `0x18007ded8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18007df03`
- `ntdll!RtlNtStatusToDosError` at `0x18007df03`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18007def7`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18007def7`
- `ntdll!RtlFreeUnicodeString` at `0x18007df32`
- `ntdll!RtlFreeUnicodeString` at `0x18007df32`

## pseudocode

```c
__int64 __fastcall pSetupOpenPredefinedKey(__int64 a1, __int64 a2)
{
  int v3; // eax
  ULONG v4; // eax
  PWSTR Buffer; // rax
  unsigned int v6; // ebx
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-18h] BYREF

  KeyPath = 0;
  if ( a1 == -2147483647 )
  {
    v3 = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( v3 < 0 )
    {
      v4 = RtlNtStatusToDosError(v3);
LABEL_6:
      v6 = v4;
      goto LABEL_7;
    }
    Buffer = KeyPath.Buffer;
LABEL_5:
    v4 = pSetupOpenKeyEx(0, Buffer, 0x2000000, a2);
    goto LABEL_6;
  }
  Buffer = (PWSTR)pSetupGetPredefinedKeyPath(a1);
  if ( Buffer )
    goto LABEL_5;
  v6 = 50;
LABEL_7:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  return v6;
}

```

## disassembly

```asm
0x18007ded8  push    rbx
0x18007deda  sub     rsp, 30h
0x18007dede  xorps   xmm0, xmm0
0x18007dee1  mov     rbx, rdx
0x18007dee4  movups  xmmword ptr [rsp+38h+KeyPath.Length], xmm0
0x18007dee9  cmp     rcx, 0FFFFFFFF80000001h
0x18007def0  jnz     short loc_18007DF40
0x18007def2  lea     rcx, [rsp+38h+KeyPath]; KeyPath
0x18007def7  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18007defd  test    eax, eax
0x18007deff  jns     short loc_18007DF0B
0x18007df01  mov     ecx, eax; Status
0x18007df03  call    cs:__imp_RtlNtStatusToDosError
0x18007df09  jmp     short loc_18007DF23
0x18007df0b  mov     rax, [rsp+38h+KeyPath.Buffer]
0x18007df10  mov     r9, rbx
0x18007df13  mov     r8d, 2000000h
0x18007df19  mov     rdx, rax
0x18007df1c  xor     ecx, ecx
0x18007df1e  call    pSetupOpenKeyEx
0x18007df23  mov     ebx, eax
0x18007df25  cmp     [rsp+38h+KeyPath.Buffer], 0
0x18007df2b  jz      short loc_18007DF38
0x18007df2d  lea     rcx, [rsp+38h+KeyPath]; UnicodeString
0x18007df32  call    cs:__imp_RtlFreeUnicodeString
0x18007df38  mov     eax, ebx
0x18007df3a  add     rsp, 30h
0x18007df3e  pop     rbx
0x18007df3f  retn
0x18007df40  call    pSetupGetPredefinedKeyPath
0x18007df45  test    rax, rax
0x18007df48  jnz     short loc_18007DF10
0x18007df4a  lea     ebx, [rax+32h]
0x18007df4d  jmp     short loc_18007DF25
```
