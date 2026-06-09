# SchemeRetrieveUncachedAuxInfo

- ea: `0x180003104`
- end: `0x18000316a`
- name: `SchemeRetrieveUncachedAuxInfo`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`
- `0x1800196e0`
- `0x18001a250`

## callees

- `0x1800017e0`
- `0x180003104`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000311f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000311f`

## pseudocode

```c
void __fastcall SchemeRetrieveUncachedAuxInfo(__int64 a1)
{
  struct _FILETIME *v2; // rcx
  _QWORD *v3; // rax

  if ( a1 )
  {
    if ( *(_DWORD *)a1 > 8u )
    {
      v2 = *(struct _FILETIME **)(a1 + 8);
      if ( v2 )
        GetSystemTimeAsFileTime(v2);
    }
    if ( *(_DWORD *)a1 > 0x18u && *(_QWORD *)(a1 + 24) )
      I_UrlCacheZeroCbSizeStruct();
    if ( *(_DWORD *)a1 > 0x20u && *(_QWORD *)(a1 + 32) )
      I_UrlCacheZeroCbSizeStruct();
    if ( *(_DWORD *)a1 > 0x28u )
    {
      v3 = *(_QWORD **)(a1 + 40);
      if ( v3 )
        *v3 = 0;
    }
  }
}

```

## disassembly

```asm
0x180003104  test    rcx, rcx
0x180003107  jz      short locret_18000315B
0x180003109  push    rbx
0x18000310a  sub     rsp, 20h
0x18000310e  cmp     dword ptr [rcx], 8
0x180003111  mov     rbx, rcx
0x180003114  jbe     short loc_180003125
0x180003116  mov     rcx, [rcx+8]; lpSystemTimeAsFileTime
0x18000311a  test    rcx, rcx
0x18000311d  jz      short loc_180003125
0x18000311f  call    cs:__imp_GetSystemTimeAsFileTime
0x180003125  cmp     dword ptr [rbx], 18h
0x180003128  jbe     short loc_180003133
0x18000312a  mov     rcx, [rbx+18h]
0x18000312e  test    rcx, rcx
0x180003131  jnz     short loc_180003163
0x180003133  cmp     dword ptr [rbx], 20h ; ' '
0x180003136  jbe     short loc_180003141
0x180003138  mov     rcx, [rbx+20h]
0x18000313c  test    rcx, rcx
0x18000313f  jnz     short loc_18000315C
0x180003141  cmp     dword ptr [rbx], 28h ; '('
0x180003144  jbe     short loc_180003156
0x180003146  mov     rax, [rbx+28h]
0x18000314a  test    rax, rax
0x18000314d  jz      short loc_180003156
0x18000314f  mov     qword ptr [rax], 0
0x180003156  add     rsp, 20h
0x18000315a  pop     rbx
0x18000315b  retn
0x18000315c  call    I_UrlCacheZeroCbSizeStruct
0x180003161  jmp     short loc_180003141
0x180003163  call    I_UrlCacheZeroCbSizeStruct
0x180003168  jmp     short loc_180003133
```
