# GetMediaTypePath(_GUID const *,_GUID const *,ushort *,ulong)

- ea: `0x180002450`
- end: `0x1800024f4`
- name: `?GetMediaTypePath@@YAJPEBU_GUID@@0PEAGK@Z`
- size: `164`
- prototype: `int(const struct _GUID *, const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ee0`
- `0x18000277c`

## callees

- `0x180002450`
- `0x18000259c`
- `0x180002660`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000248f`
- `KERNEL32!lstrlenW` at `0x1800024ca`
- `KERNEL32!lstrlenW` at `0x18000248f`
- `KERNEL32!lstrlenW` at `0x1800024ca`
- `ole32!StringFromGUID2` at `0x1800024a7`
- `ole32!StringFromGUID2` at `0x1800024de`
- `ole32!StringFromGUID2` at `0x1800024a7`
- `ole32!StringFromGUID2` at `0x1800024de`

## pseudocode

```c
int __fastcall GetMediaTypePath(const struct _GUID *a1, const struct _GUID *a2, unsigned __int16 *a3)
{
  int v5; // eax
  int result; // eax
  int v7; // eax

  StringCchCopyW(a3, 0xC8u, L"Media Type");
  StringCchCatW(a3, 0xC8u, L"\\");
  v5 = lstrlenW(a3);
  result = StringFromGUID2(&MEDIATYPE_Stream, &a3[v5], 100);
  if ( result >= 0 )
  {
    if ( a2 )
    {
      StringCchCatW(a3, 0xC8u, L"\\");
      v7 = lstrlenW(a3);
      return StringFromGUID2(a2, &a3[v7], 100);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002450  mov     [rsp+arg_0], rbx
0x180002455  mov     [rsp+arg_8], rsi
0x18000245a  push    rdi
0x18000245b  sub     rsp, 20h
0x18000245f  mov     rbx, r8
0x180002462  mov     rdi, rdx
0x180002465  mov     esi, 0C8h
0x18000246a  lea     r8, aMediaType; "Media Type"
0x180002471  mov     edx, esi; unsigned __int64
0x180002473  mov     rcx, rbx; unsigned __int16 *
0x180002476  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000247b  lea     r8, asc_1800230A0; "\\"
0x180002482  mov     edx, esi; unsigned __int64
0x180002484  mov     rcx, rbx; unsigned __int16 *
0x180002487  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000248c  mov     rcx, rbx; lpString
0x18000248f  call    cs:__imp_lstrlenW
0x180002495  movsxd  rcx, eax
0x180002498  lea     r8d, [rsi-64h]; cchMax
0x18000249c  lea     rdx, [rbx+rcx*2]; lpsz
0x1800024a0  lea     rcx, MEDIATYPE_Stream; rguid
0x1800024a7  call    cs:__imp_StringFromGUID2
0x1800024ad  test    eax, eax
0x1800024af  js      short loc_1800024E4
0x1800024b1  test    rdi, rdi
0x1800024b4  jz      short loc_1800024E4
0x1800024b6  lea     r8, asc_1800230A0; "\\"
0x1800024bd  mov     edx, esi; unsigned __int64
0x1800024bf  mov     rcx, rbx; unsigned __int16 *
0x1800024c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800024c7  mov     rcx, rbx; lpString
0x1800024ca  call    cs:__imp_lstrlenW
0x1800024d0  movsxd  rcx, eax
0x1800024d3  lea     r8d, [rsi-64h]; cchMax
0x1800024d7  lea     rdx, [rbx+rcx*2]; lpsz
0x1800024db  mov     rcx, rdi; rguid
0x1800024de  call    cs:__imp_StringFromGUID2
0x1800024e4  mov     rbx, [rsp+28h+arg_0]
0x1800024e9  mov     rsi, [rsp+28h+arg_8]
0x1800024ee  add     rsp, 20h
0x1800024f2  pop     rdi
0x1800024f3  retn
```
