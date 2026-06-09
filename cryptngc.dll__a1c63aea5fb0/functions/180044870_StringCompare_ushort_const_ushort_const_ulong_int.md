# StringCompare(ushort const *,ushort const *,ulong,int *)

- ea: `0x180044870`
- end: `0x180044913`
- name: `?StringCompare@@YAJPEBG0KPEAH@Z`
- size: `163`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025788`
- `0x180045e7c`
- `0x1800461d8`

## callees

- `0x18001b65c`
- `0x180027278`
- `0x180027448`
- `0x180044870`

## string_xrefs

- `0x18004489b`: `StringCompare`
- `0x1800448b5`: `StringCompare`
- `0x1800448de`: `StringCompare`
- `0x1800448e5`: `StringCompare`

## pseudocode

```c
__int64 __fastcall StringCompare(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, int *a4)
{
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  if ( a4 )
  {
    v6 = CompareStringInternal(a1, (__int64)a2, a2, (__int64)a4, v8, (enum COMPARE_STR_RESULT *)&v9);
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
0x180044870  mov     [rsp+arg_0], rbx
0x180044875  mov     [rsp+arg_10], r8d
0x18004487a  push    rdi
0x18004487b  sub     rsp, 30h
0x18004487f  mov     [rsp+38h+arg_10], 0
0x180044887  mov     rdi, r9
0x18004488a  test    r9, r9
0x18004488d  jnz     short loc_1800448C3
0x18004488f  lea     r8, aEqual; "equal"
0x180044896  mov     ebx, 80070057h
0x18004489b  lea     rdx, aStringcompare; "StringCompare"
0x1800448a2  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800448a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800448ae  lea     rdx, aEqual; "equal"
0x1800448b5  lea     rcx, aStringcompare; "StringCompare"
0x1800448bc  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800448c1  jmp     short loc_180044906
0x1800448c3  lea     rax, [rsp+38h+arg_10]
0x1800448c8  mov     r8, rdx; unsigned __int16 *
0x1800448cb  mov     [rsp+38h+var_10], rax; enum COMPARE_STR_RESULT *
0x1800448d0  call    ?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z; CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)
0x1800448d5  mov     ebx, eax
0x1800448d7  test    eax, eax
0x1800448d9  jns     short loc_1800448FA
0x1800448db  mov     r9d, eax
0x1800448de  lea     r8, aStringcompare; "StringCompare"
0x1800448e5  lea     rdx, aStringcompare; "StringCompare"
0x1800448ec  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800448f3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800448f8  jmp     short loc_180044906
0x1800448fa  xor     eax, eax
0x1800448fc  cmp     [rsp+38h+arg_10], 2
0x180044901  setz    al
0x180044904  mov     [rdi], eax
0x180044906  mov     eax, ebx
0x180044908  mov     rbx, [rsp+38h+arg_0]
0x18004490d  add     rsp, 30h
0x180044911  pop     rdi
0x180044912  retn
```
