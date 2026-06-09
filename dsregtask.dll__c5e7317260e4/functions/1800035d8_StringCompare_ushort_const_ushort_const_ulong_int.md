# StringCompare(ushort const *,ushort const *,ulong,int *)

- ea: `0x1800035d8`
- end: `0x180003678`
- name: `?StringCompare@@YAJPEBG0KPEAH@Z`
- size: `160`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180003000`
- `0x1800030ec`
- `0x180003454`
- `0x1800035d8`

## string_xrefs

- `0x180003603`: `StringCompare`
- `0x18000361d`: `StringCompare`
- `0x180003643`: `StringCompare`
- `0x18000364a`: `StringCompare`

## pseudocode

```c
__int64 __fastcall StringCompare(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  if ( a4 )
  {
    v6 = CompareStringInternal(a1, (int)a2, a3, (int)a4, v8, (enum COMPARE_STR_RESULT *)&v9);
    v5 = v6;
    if ( v6 >= 0 )
      *a4 = v9 == 2;
    else
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"StringCompare",
        L"StringCompare",
        (unsigned int)v6);
  }
  else
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"StringCompare", L"equal");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"StringCompare", L"equal");
  }
  return v5;
}

```

## disassembly

```asm
0x1800035d8  mov     [rsp+arg_0], rbx
0x1800035dd  mov     [rsp+arg_10], r8d
0x1800035e2  push    rdi
0x1800035e3  sub     rsp, 30h
0x1800035e7  mov     [rsp+38h+arg_10], 0
0x1800035ef  mov     rdi, r9
0x1800035f2  test    r9, r9
0x1800035f5  jnz     short loc_18000362B
0x1800035f7  lea     r8, aEqual; "equal"
0x1800035fe  mov     ebx, 80070057h
0x180003603  lea     rdx, aStringcompare; "StringCompare"
0x18000360a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180003611  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180003616  lea     rdx, aEqual; "equal"
0x18000361d  lea     rcx, aStringcompare; "StringCompare"
0x180003624  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180003629  jmp     short loc_18000366B
0x18000362b  lea     rax, [rsp+38h+arg_10]
0x180003630  mov     [rsp+38h+var_10], rax; enum COMPARE_STR_RESULT *
0x180003635  call    ?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z; CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)
0x18000363a  mov     ebx, eax
0x18000363c  test    eax, eax
0x18000363e  jns     short loc_18000365F
0x180003640  mov     r9d, eax
0x180003643  lea     r8, aStringcompare; "StringCompare"
0x18000364a  lea     rdx, aStringcompare; "StringCompare"
0x180003651  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x."
0x180003658  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000365d  jmp     short loc_18000366B
0x18000365f  xor     eax, eax
0x180003661  cmp     [rsp+38h+arg_10], 2
0x180003666  setz    al
0x180003669  mov     [rdi], eax
0x18000366b  mov     eax, ebx
0x18000366d  mov     rbx, [rsp+38h+arg_0]
0x180003672  add     rsp, 30h
0x180003676  pop     rdi
0x180003677  retn
```
