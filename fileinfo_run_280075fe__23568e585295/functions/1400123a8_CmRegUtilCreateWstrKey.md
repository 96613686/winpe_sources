# CmRegUtilCreateWstrKey

- ea: `0x1400123a8`
- end: `0x1400123ff`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140011b98`
- `0x140012080`

## callees

- `0x1400037b8`
- `0x1400122fc`
- `0x1400123a8`

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
0x1400123a8  sub     rsp, 58h
0x1400123ac  mov     r10, rcx
0x1400123af  xorps   xmm0, xmm0
0x1400123b2  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400123b7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1400123bc  call    WdmlibRtlInitUnicodeStringEx
0x1400123c1  test    eax, eax
0x1400123c3  js      short loc_1400123F9
0x1400123c5  mov     rax, [rsp+58h+arg_30]
0x1400123cd  lea     rdx, [rsp+58h+DestinationString]
0x1400123d2  mov     [rsp+58h+var_28], rax
0x1400123d7  mov     rcx, r10
0x1400123da  mov     rax, [rsp+58h+arg_28]
0x1400123e2  mov     [rsp+58h+var_30], rax
0x1400123e7  mov     rax, [rsp+58h+arg_20]
0x1400123ef  mov     [rsp+58h+var_38], rax
0x1400123f4  call    CmRegUtilCreateUcKey
0x1400123f9  add     rsp, 58h
0x1400123fd  retn
```
