# CmRegUtilCreateWstrKey

- ea: `0x140044a58`
- end: `0x140044aaf`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140044248`
- `0x140044730`

## callees

- `0x14003707c`
- `0x1400449ac`
- `0x140044a58`

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
0x140044a58  sub     rsp, 58h
0x140044a5c  mov     r10, rcx
0x140044a5f  xorps   xmm0, xmm0
0x140044a62  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140044a67  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140044a6c  call    WdmlibRtlInitUnicodeStringEx
0x140044a71  test    eax, eax
0x140044a73  js      short loc_140044AA9
0x140044a75  mov     rax, [rsp+58h+arg_30]
0x140044a7d  lea     rdx, [rsp+58h+DestinationString]
0x140044a82  mov     [rsp+58h+var_28], rax
0x140044a87  mov     rcx, r10
0x140044a8a  mov     rax, [rsp+58h+arg_28]
0x140044a92  mov     [rsp+58h+var_30], rax
0x140044a97  mov     rax, [rsp+58h+arg_20]
0x140044a9f  mov     [rsp+58h+var_38], rax
0x140044aa4  call    CmRegUtilCreateUcKey
0x140044aa9  add     rsp, 58h
0x140044aad  retn
```
