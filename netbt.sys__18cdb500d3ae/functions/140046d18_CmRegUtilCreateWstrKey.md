# CmRegUtilCreateWstrKey

- ea: `0x140046d18`
- end: `0x140046d6f`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140046508`
- `0x1400469f0`

## callees

- `0x140030d6c`
- `0x140046c6c`
- `0x140046d18`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  void *v10; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
    return CmRegUtilCreateUcKey(v10, &DestinationString, v8, v9, a5, a6, a7);
  return result;
}

```

## disassembly

```asm
0x140046d18  sub     rsp, 58h
0x140046d1c  mov     r10, rcx
0x140046d1f  xorps   xmm0, xmm0
0x140046d22  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140046d27  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140046d2c  call    WdmlibRtlInitUnicodeStringEx
0x140046d31  test    eax, eax
0x140046d33  js      short loc_140046D69
0x140046d35  mov     rax, [rsp+58h+arg_30]
0x140046d3d  lea     rdx, [rsp+58h+DestinationString]
0x140046d42  mov     [rsp+58h+var_28], rax
0x140046d47  mov     rcx, r10
0x140046d4a  mov     rax, [rsp+58h+arg_28]
0x140046d52  mov     [rsp+58h+var_30], rax
0x140046d57  mov     rax, [rsp+58h+arg_20]
0x140046d5f  mov     [rsp+58h+var_38], rax
0x140046d64  call    CmRegUtilCreateUcKey
0x140046d69  add     rsp, 58h
0x140046d6d  retn
```
