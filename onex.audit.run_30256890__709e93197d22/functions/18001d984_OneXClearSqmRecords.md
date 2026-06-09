# OneXClearSqmRecords

- ea: `0x18001d984`
- end: `0x18001dab2`
- name: `OneXClearSqmRecords`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d8c0`

## callees

- `0x180005440`
- `0x18001d984`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001da79`
- `MobileNetworking!ReleaseWriteLock` at `0x18001da79`
- `MobileNetworking!AcquireWriteLock` at `0x18001d9df`
- `MobileNetworking!AcquireWriteLock` at `0x18001d9df`
- `MobileNetworking!FreeMemory` at `0x18001da4f`
- `MobileNetworking!FreeMemory` at `0x18001da4f`

## pseudocode

```c
__int64 OneXClearSqmRecords()
{
  __int64 v0; // rdx
  _QWORD *v1; // rcx
  __int64 result; // rax
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 94, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  AcquireWriteLock(g_OneXInfo, qword_18003DE28, "OneXClearSqmRecords", 939);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 95, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  while ( (__int64 *)qword_18003DE18 != &qword_18003DE18 )
  {
    v3 = qword_18003DE18;
    v0 = *(_QWORD *)qword_18003DE18;
    if ( *(_QWORD *)(*(_QWORD *)qword_18003DE18 + 8LL) != qword_18003DE18
      || (v1 = *(_QWORD **)(qword_18003DE18 + 8), *v1 != qword_18003DE18) )
    {
      __fastfail(3u);
    }
    *v1 = v0;
    *(_QWORD *)(v0 + 8) = v1;
    FreeMemory(&v3, "OneXClearSqmRecords", 948);
  }
  result = ReleaseWriteLock(g_OneXInfo, qword_18003DE28, "OneXClearSqmRecords", 951);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 96, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x18001d984  push    rsi
0x18001d986  sub     rsp, 20h
0x18001d98a  mov     [rsp+28h+arg_0], 0
0x18001d993  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d99a  lea     rsi, WPP_GLOBAL_Control
0x18001d9a1  cmp     rcx, rsi
0x18001d9a4  jz      short loc_18001D9C4
0x18001d9a6  test    dword ptr [rcx+44h], 800h
0x18001d9ad  jz      short loc_18001D9C4
0x18001d9af  mov     rcx, [rcx+38h]
0x18001d9b3  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001d9ba  mov     edx, 5Eh ; '^'
0x18001d9bf  call    WPP_SF_
0x18001d9c4  mov     r9d, 3ABh
0x18001d9ca  lea     r8, aOnexclearsqmre; "OneXClearSqmRecords"
0x18001d9d1  lea     rdx, qword_18003DE28
0x18001d9d8  lea     rcx, g_OneXInfo
0x18001d9df  call    cs:__imp_AcquireWriteLock
0x18001d9e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9ec  cmp     rcx, rsi
0x18001d9ef  jz      short loc_18001DA0C
0x18001d9f1  test    byte ptr [rcx+44h], 4
0x18001d9f5  jz      short loc_18001DA0C
0x18001d9f7  mov     rcx, [rcx+38h]
0x18001d9fb  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001da02  mov     edx, 5Fh ; '_'
0x18001da07  call    WPP_SF_
0x18001da0c  mov     rax, cs:qword_18003DE18
0x18001da13  lea     rcx, qword_18003DE18
0x18001da1a  cmp     rax, rcx
0x18001da1d  jz      short loc_18001DA5E
0x18001da1f  mov     [rsp+28h+arg_0], rax
0x18001da24  mov     rdx, [rax]
0x18001da27  cmp     [rdx+8], rax
0x18001da2b  jnz     short loc_18001DA57
0x18001da2d  mov     rcx, [rax+8]
0x18001da31  cmp     [rcx], rax
0x18001da34  jnz     short loc_18001DA57
0x18001da36  mov     [rcx], rdx
0x18001da39  mov     r8d, 3B4h
0x18001da3f  mov     [rdx+8], rcx
0x18001da43  lea     rdx, aOnexclearsqmre; "OneXClearSqmRecords"
0x18001da4a  lea     rcx, [rsp+28h+arg_0]
0x18001da4f  call    cs:__imp_FreeMemory
0x18001da55  jmp     short loc_18001DA0C
0x18001da57  mov     ecx, 3
0x18001da5c  int     29h; Win8: RtlFailFast(ecx)
0x18001da5e  mov     r9d, 3B7h
0x18001da64  lea     r8, aOnexclearsqmre; "OneXClearSqmRecords"
0x18001da6b  lea     rdx, qword_18003DE28
0x18001da72  lea     rcx, g_OneXInfo
0x18001da79  call    cs:__imp_ReleaseWriteLock
0x18001da7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da86  cmp     rcx, rsi
0x18001da89  jz      short loc_18001DAAC
0x18001da8b  test    dword ptr [rcx+44h], 800h
0x18001da92  jz      short loc_18001DAAC
0x18001da94  mov     rcx, [rcx+38h]
0x18001da98  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18001da9f  mov     edx, 60h ; '`'
0x18001daa4  xor     r9d, r9d
0x18001daa7  call    WPP_SF_D
0x18001daac  add     rsp, 20h
0x18001dab0  pop     rsi
0x18001dab1  retn
```
