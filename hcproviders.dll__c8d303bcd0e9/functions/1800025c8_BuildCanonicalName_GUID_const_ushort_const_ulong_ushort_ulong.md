# BuildCanonicalName(_GUID const &,ushort const *,ulong,ushort *,ulong)

- ea: `0x1800025c8`
- end: `0x18000263d`
- name: `?BuildCanonicalName@@YAJAEBU_GUID@@PEBGKPEAGK@Z`
- size: `117`
- prototype: `int(const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009a10`

## callees

- `0x1800025c8`
- `0x180002d90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800025e8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800025e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002625`

## pseudocode

```c
__int64 __fastcall BuildCanonicalName(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  HRESULT v8; // ebx
  int v10; // [rsp+28h] [rbp-40h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-38h] BYREF

  lpsz = 0;
  v8 = StringFromCLSID(a1, &lpsz);
  if ( v8 >= 0 )
  {
    v10 = a3;
    v8 = StringCchPrintfW(a4, a5, L"%s%s%u", lpsz, a2, v10);
    CoTaskMemFree(lpsz);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800025c8  push    rbx
0x1800025ca  push    rbp
0x1800025cb  push    rsi
0x1800025cc  push    rdi
0x1800025cd  sub     rsp, 48h
0x1800025d1  mov     rbp, rdx
0x1800025d4  mov     [rsp+68h+lpsz], 0
0x1800025dd  lea     rdx, [rsp+68h+lpsz]; lplpsz
0x1800025e2  mov     rdi, r9
0x1800025e5  mov     esi, r8d
0x1800025e8  call    cs:__imp_StringFromCLSID
0x1800025ef  nop     dword ptr [rax+rax+00h]
0x1800025f4  mov     ebx, eax
0x1800025f6  test    eax, eax
0x1800025f8  js      short loc_180002631
0x1800025fa  mov     edx, [rsp+68h+arg_20]; unsigned __int64
0x180002601  lea     r8, aSSU; "%s%s%u"
0x180002608  mov     r9, [rsp+68h+lpsz]
0x18000260d  mov     rcx, rdi; unsigned __int16 *
0x180002610  mov     [rsp+68h+var_40], esi
0x180002614  mov     [rsp+68h+var_48], rbp
0x180002619  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000261e  mov     rcx, [rsp+68h+lpsz]; pv
0x180002623  mov     ebx, eax
0x180002625  call    cs:__imp_CoTaskMemFree
0x18000262c  nop     dword ptr [rax+rax+00h]
0x180002631  mov     eax, ebx
0x180002633  add     rsp, 48h
0x180002637  pop     rdi
0x180002638  pop     rsi
0x180002639  pop     rbp
0x18000263a  pop     rbx
0x18000263b  retn
```
