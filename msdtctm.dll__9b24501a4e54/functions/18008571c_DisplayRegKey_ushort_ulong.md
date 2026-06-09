# DisplayRegKey(ushort *,ulong)

- ea: `0x18008571c`
- end: `0x1800857b9`
- name: `?DisplayRegKey@@YAJPEAGK@Z`
- size: `157`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ebdc`

## callees

- `0x1800206c4`
- `0x1800846c0`
- `0x18008571c`
- `0x1800858a4`
- `0x180085974`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085791`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800857a6`

## string_xrefs

- `0x180085768`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18008572b`: `DisplayRegKey (com\complus\dtc\shared\util\stringutil.cpp@269): DisplayRegKey: NULL != pwszKey`

## pseudocode

```c
__int64 __fastcall DisplayRegKey(unsigned __int16 *a1, int a2)
{
  int StringW; // eax
  int v3; // edi
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rcx
  unsigned __int16 *v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    DtcInternalErrorW(L"DisplayRegKey (com\\complus\\dtc\\shared\\util\\stringutil.cpp@269): DisplayRegKey: NULL != pwszKey");
  v8 = 0;
  StringW = MakeStringW(&v8, L"Key: %s\\%s\nNum of Values = %d\n", L"HKLM\\Cluster", a1, a2);
  v3 = StringW;
  if ( StringW >= 0 )
  {
    v4 = v8;
    v5 = 0;
  }
  else
  {
    v4 = 0;
    TraceFileW(StringW, L"FormatRegValue failed", L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", 0xFBu);
    v5 = v8;
  }
  CoTaskMemFree(v5);
  if ( v3 >= 0 )
    OutputString(v4);
  CoTaskMemFree(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008571c  mov     [rsp+arg_8], rbx
0x180085721  push    rdi
0x180085722  sub     rsp, 30h
0x180085726  test    rcx, rcx
0x180085729  jnz     short loc_180085738
0x18008572b  lea     rcx, aDisplayregkeyC; "DisplayRegKey (com\\complus\\dtc\\share"...
0x180085732  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180085738  mov     [rsp+38h+var_18], edx
0x18008573c  lea     r8, aHklmCluster; "HKLM\\Cluster"
0x180085743  mov     r9, rcx
0x180085746  mov     [rsp+38h+arg_0], 0
0x18008574f  lea     rdx, aKeySSNumOfValu; "Key: %s\\%s\nNum of Values = %d\n"
0x180085756  lea     rcx, [rsp+38h+arg_0]; unsigned __int16 **
0x18008575b  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180085760  mov     edi, eax
0x180085762  test    eax, eax
0x180085764  jns     short loc_18008578A
0x180085766  xor     ebx, ebx
0x180085768  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x18008576f  mov     r9d, 0FBh; unsigned int
0x180085775  lea     rdx, aFormatregvalue; "FormatRegValue failed"
0x18008577c  mov     ecx, eax; int
0x18008577e  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180085783  mov     rcx, [rsp+38h+arg_0]
0x180085788  jmp     short loc_180085791
0x18008578a  mov     rbx, [rsp+38h+arg_0]
0x18008578f  xor     ecx, ecx; pv
0x180085791  call    cs:__imp_CoTaskMemFree
0x180085797  test    edi, edi
0x180085799  js      short loc_1800857A3
0x18008579b  mov     rcx, rbx; unsigned __int16 *
0x18008579e  call    ?OutputString@@YAXPEAG@Z; OutputString(ushort *)
0x1800857a3  mov     rcx, rbx; pv
0x1800857a6  call    cs:__imp_CoTaskMemFree
0x1800857ac  mov     rbx, [rsp+38h+arg_8]
0x1800857b1  mov     eax, edi
0x1800857b3  add     rsp, 30h
0x1800857b7  pop     rdi
0x1800857b8  retn
```
