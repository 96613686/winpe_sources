# CmRegUtilCreateWstrKey

- ea: `0x14000e658`
- end: `0x14000e6af`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000de48`
- `0x14000e330`

## callees

- `0x140006430`
- `0x14000e5ac`
- `0x14000e658`

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
0x14000e658  sub     rsp, 58h
0x14000e65c  mov     r10, rcx
0x14000e65f  xorps   xmm0, xmm0
0x14000e662  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000e667  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14000e66c  call    WdmlibRtlInitUnicodeStringEx
0x14000e671  test    eax, eax
0x14000e673  js      short loc_14000E6A9
0x14000e675  mov     rax, [rsp+58h+arg_30]
0x14000e67d  lea     rdx, [rsp+58h+DestinationString]
0x14000e682  mov     [rsp+58h+var_28], rax
0x14000e687  mov     rcx, r10
0x14000e68a  mov     rax, [rsp+58h+arg_28]
0x14000e692  mov     [rsp+58h+var_30], rax
0x14000e697  mov     rax, [rsp+58h+arg_20]
0x14000e69f  mov     [rsp+58h+var_38], rax
0x14000e6a4  call    CmRegUtilCreateUcKey
0x14000e6a9  add     rsp, 58h
0x14000e6ad  retn
```
