# AVrfpFormatCurrentUserKeyPath

- ea: `0x18011d378`
- end: `0x18011d3ca`
- name: `AVrfpFormatCurrentUserKeyPath`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800eba3c`

## callees

- `0x18002ad90`
- `0x18005a9f0`
- `0x180109568`
- `0x18011d378`

## string_xrefs

- `0x18011d38b`: `\REGISTRY\USER\`

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
      return RtlAppendUnicodeStringToString(a1, &qword_1801718C0);
  }
  return result;
}

```

## disassembly

```asm
0x18011d378  push    rbx
0x18011d37a  sub     rsp, 20h
0x18011d37e  xorps   xmm0, xmm0
0x18011d381  lea     rax, AVrfpCurrentUserKeyPath
0x18011d388  movups  xmmword ptr [rcx], xmm0
0x18011d38b  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x18011d392  mov     word ptr [rcx+2], 4E4h
0x18011d398  mov     [rcx+8], rax
0x18011d39c  mov     rbx, rcx
0x18011d39f  call    RtlAppendUnicodeToString
0x18011d3a4  test    eax, eax
0x18011d3a6  js      short loc_18011D3C3
0x18011d3a8  mov     rcx, rbx
0x18011d3ab  call    AVrfpAppendCurrentUserSid
0x18011d3b0  test    eax, eax
0x18011d3b2  js      short loc_18011D3C3
0x18011d3b4  lea     rdx, qword_1801718C0
0x18011d3bb  mov     rcx, rbx
0x18011d3be  call    RtlAppendUnicodeStringToString
0x18011d3c3  add     rsp, 20h
0x18011d3c7  pop     rbx
0x18011d3c8  retn
```
