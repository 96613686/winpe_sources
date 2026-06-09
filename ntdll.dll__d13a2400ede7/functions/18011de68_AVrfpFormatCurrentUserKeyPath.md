# AVrfpFormatCurrentUserKeyPath

- ea: `0x18011de68`
- end: `0x18011deba`
- name: `AVrfpFormatCurrentUserKeyPath`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ec51c`

## callees

- `0x180036fa0`
- `0x1800773d0`
- `0x18010a4f8`
- `0x18011de68`

## string_xrefs

- `0x18011de7b`: `\REGISTRY\USER\`

## pseudocode

```c
__int64 __fastcall AVrfpFormatCurrentUserKeyPath(__int64 a1)
{
  __int64 result; // rax

  *(_OWORD *)a1 = 0;
  *(_WORD *)(a1 + 2) = 1252;
  *(_QWORD *)(a1 + 8) = AVrfpCurrentUserKeyPath;
  result = RtlAppendUnicodeToString(a1, L"\\REGISTRY\\USER\\");
  if ( (int)result >= 0 )
  {
    result = AVrfpAppendCurrentUserSid(a1);
    if ( (int)result >= 0 )
      return RtlAppendUnicodeStringToString(a1, &qword_1801718D0);
  }
  return result;
}

```

## disassembly

```asm
0x18011de68  push    rbx
0x18011de6a  sub     rsp, 20h
0x18011de6e  xorps   xmm0, xmm0
0x18011de71  lea     rax, AVrfpCurrentUserKeyPath
0x18011de78  movups  xmmword ptr [rcx], xmm0
0x18011de7b  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x18011de82  mov     word ptr [rcx+2], 4E4h
0x18011de88  mov     [rcx+8], rax
0x18011de8c  mov     rbx, rcx
0x18011de8f  call    RtlAppendUnicodeToString
0x18011de94  test    eax, eax
0x18011de96  js      short loc_18011DEB3
0x18011de98  mov     rcx, rbx
0x18011de9b  call    AVrfpAppendCurrentUserSid
0x18011dea0  test    eax, eax
0x18011dea2  js      short loc_18011DEB3
0x18011dea4  lea     rdx, qword_1801718D0
0x18011deab  mov     rcx, rbx
0x18011deae  call    RtlAppendUnicodeStringToString
0x18011deb3  add     rsp, 20h
0x18011deb7  pop     rbx
0x18011deb8  retn
```
