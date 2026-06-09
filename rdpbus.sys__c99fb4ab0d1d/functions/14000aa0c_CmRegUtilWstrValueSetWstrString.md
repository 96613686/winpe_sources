# CmRegUtilWstrValueSetWstrString

- ea: `0x14000aa0c`
- end: `0x14000aa60`
- name: `CmRegUtilWstrValueSetWstrString`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a134`

## callees

- `0x140002350`
- `0x14000a828`
- `0x14000aa0c`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilWstrValueSetWstrString(__int64 a1, __int64 a2, const WCHAR *a3)
{
  NTSTATUS result; // eax
  const WCHAR *v4; // r11
  void *v5; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF

  ValueName = 0;
  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a3);
  if ( result >= 0 )
  {
    result = WdmlibRtlInitUnicodeStringEx(&ValueName, v4);
    if ( result >= 0 )
      return CmRegUtilUcValueSetUcString(v5, &ValueName, &DestinationString.Length);
  }
  return result;
}

```

## disassembly

```asm
0x14000aa0c  sub     rsp, 48h
0x14000aa10  mov     r11, rdx
0x14000aa13  mov     r10, rcx
0x14000aa16  xorps   xmm0, xmm0
0x14000aa19  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14000aa1e  xorps   xmm1, xmm1
0x14000aa21  mov     rdx, r8; SourceString
0x14000aa24  movups  xmmword ptr [rsp+48h+ValueName.Length], xmm0
0x14000aa29  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x14000aa2e  call    WdmlibRtlInitUnicodeStringEx
0x14000aa33  test    eax, eax
0x14000aa35  js      short loc_14000AA5A
0x14000aa37  mov     rdx, r11; SourceString
0x14000aa3a  lea     rcx, [rsp+48h+ValueName]; DestinationString
0x14000aa3f  call    WdmlibRtlInitUnicodeStringEx
0x14000aa44  test    eax, eax
0x14000aa46  js      short loc_14000AA5A
0x14000aa48  lea     r8, [rsp+48h+DestinationString]
0x14000aa4d  mov     rcx, r10; KeyHandle
0x14000aa50  lea     rdx, [rsp+48h+ValueName]; ValueName
0x14000aa55  call    CmRegUtilUcValueSetUcString
0x14000aa5a  add     rsp, 48h
0x14000aa5e  retn
```
