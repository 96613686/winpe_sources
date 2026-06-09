# Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x1800254dc`
- end: `0x18002550e`
- name: `?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z`
- size: `50`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800241c0`

## callees

- `0x18000fdf0`

## pseudocode

```c
__int64 __fastcall Logger::WriteRegistryFailureEvent(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const wchar_t *v4; // rax

  v4 = L"<NULL>";
  if ( a4 )
    v4 = a4;
  return Logger::WriteRegistryFailureEventEx(a1, L"RegGetValueW", L"%s@%s", a3, v4);
}

```

## disassembly

```asm
0x1800254dc  sub     rsp, 38h
0x1800254e0  test    r9, r9
0x1800254e3  lea     rax, aNull_1; "<NULL>"
0x1800254ea  lea     rdx, aReggetvaluew; "RegGetValueW"
0x1800254f1  cmovnz  rax, r9
0x1800254f5  mov     r9, r8
0x1800254f8  lea     r8, aSS; "%s@%s"
0x1800254ff  mov     [rsp+38h+var_18], rax
0x180025504  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180025509  add     rsp, 38h
0x18002550d  retn
```
