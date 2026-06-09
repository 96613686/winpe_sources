# CmRegUtilCreateWstrKey

- ea: `0x140022300`
- end: `0x140022357`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140021af0`
- `0x140021fd8`

## callees

- `0x140005d08`
- `0x140022254`
- `0x140022300`

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
0x140022300  sub     rsp, 58h
0x140022304  mov     r10, rcx
0x140022307  xorps   xmm0, xmm0
0x14002230a  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14002230f  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140022314  call    WdmlibRtlInitUnicodeStringEx
0x140022319  test    eax, eax
0x14002231b  js      short loc_140022351
0x14002231d  mov     rax, [rsp+58h+arg_30]
0x140022325  lea     rdx, [rsp+58h+DestinationString]
0x14002232a  mov     [rsp+58h+var_28], rax
0x14002232f  mov     rcx, r10
0x140022332  mov     rax, [rsp+58h+arg_28]
0x14002233a  mov     [rsp+58h+var_30], rax
0x14002233f  mov     rax, [rsp+58h+arg_20]
0x140022347  mov     [rsp+58h+var_38], rax
0x14002234c  call    CmRegUtilCreateUcKey
0x140022351  add     rsp, 58h
0x140022355  retn
```
