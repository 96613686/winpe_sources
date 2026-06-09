# _WalkFreeCacheFileEntryCallback

- ea: `0x180009a60`
- end: `0x180009ac3`
- name: `_WalkFreeCacheFileEntryCallback`
- size: `99`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009a60`

## import_xrefs

- `CRYPT32!I_CryptGetLruEntryData` at `0x180009a6c`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180009a6c`

## pseudocode

```c
__int64 __fastcall WalkFreeCacheFileEntryCallback(_DWORD *a1, __int64 a2)
{
  __int64 LruEntryData; // rax
  __int64 v4; // rcx

  LruEntryData = I_CryptGetLruEntryData(a2);
  if ( !a1 || !LruEntryData )
    return 1;
  if ( !*(_DWORD *)(LruEntryData + 56) || a1[4] )
  {
    v4 = *(_QWORD *)a1;
    if ( *(_DWORD **)(*(_QWORD *)a1 + 8LL) != a1 )
      __fastfail(3u);
    *(_QWORD *)LruEntryData = v4;
    *(_QWORD *)(LruEntryData + 8) = a1;
    *(_QWORD *)(v4 + 8) = LruEntryData;
    *(_QWORD *)a1 = LruEntryData;
    return 1;
  }
  *(_DWORD *)(LruEntryData + 56) = 0;
  return 1;
}

```

## disassembly

```asm
0x180009a60  push    rbx
0x180009a62  sub     rsp, 20h
0x180009a66  mov     rbx, rcx
0x180009a69  mov     rcx, rdx
0x180009a6c  call    cs:__imp_I_CryptGetLruEntryData
0x180009a72  test    rbx, rbx
0x180009a75  jz      short loc_180009A99
0x180009a77  test    rax, rax
0x180009a7a  jz      short loc_180009A99
0x180009a7c  cmp     dword ptr [rax+38h], 0
0x180009a80  jnz     short loc_180009AA4
0x180009a82  mov     rcx, [rbx]
0x180009a85  cmp     [rcx+8], rbx
0x180009a89  jnz     short loc_180009ABC
0x180009a8b  mov     [rax], rcx
0x180009a8e  mov     [rax+8], rbx
0x180009a92  mov     [rcx+8], rax
0x180009a96  mov     [rbx], rax
0x180009a99  mov     eax, 1
0x180009a9e  add     rsp, 20h
0x180009aa2  pop     rbx
0x180009aa3  retn
0x180009aa4  cmp     dword ptr [rbx+10h], 0
0x180009aa8  jnz     short loc_180009A82
0x180009aaa  mov     dword ptr [rax+38h], 0
0x180009ab1  mov     eax, 1
0x180009ab6  add     rsp, 20h
0x180009aba  pop     rbx
0x180009abb  retn
0x180009abc  mov     ecx, 3
0x180009ac1  int     29h; Win8: RtlFailFast(ecx)
```
