# DwLineGetAddrCaps

- ea: `0x1800024bc`
- end: `0x1800025d2`
- name: `DwLineGetAddrCaps`
- size: `278`
- prototype: `__int64 __fastcall(DWORD dwDeviceID, DWORD dwAddressID, DWORD dwAPIVersion, DWORD dwExtVersion, int, int, LPLINEADDRESSCAPS, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000de88`

## callees

- `0x1800024bc`
- `0x18000d92c`
- `0x1800240a8`
- `0x18002927e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002557`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002566`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetAddressCapsA` at `0x180002523`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetAddressCapsA` at `0x1800025a7`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetAddressCapsA` at `0x180002523`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetAddressCapsA` at `0x1800025a7`

## pseudocode

```c
__int64 __fastcall DwLineGetAddrCaps(
        DWORD dwDeviceID,
        DWORD dwAddressID,
        DWORD dwAPIVersion,
        DWORD dwExtVersion,
        int a5,
        int a6,
        LPLINEADDRESSCAPS lpAddressCaps,
        struct lineaddresscaps_tag **a8)
{
  LONG AddressCaps; // eax
  unsigned int v13; // ebx
  DWORD dwNeededSize; // edi
  struct lineaddresscaps_tag *v15; // rax

  memset_0(&lpAddressCaps->dwNeededSize, 0, 0x31Cu);
  lpAddressCaps->dwTotalSize = 800;
  *a8 = lpAddressCaps;
  if ( a5 )
    AddressCaps = RasLineGetAddressCaps(dwDeviceID, dwAddressID, dwExtVersion, lpAddressCaps);
  else
    AddressCaps = lineGetAddressCapsA(RasLine, dwDeviceID, dwAddressID, dwAPIVersion, dwExtVersion, lpAddressCaps);
  v13 = AddressCaps;
  if ( AddressCaps == -2147483571 )
  {
    dwNeededSize = lpAddressCaps->dwNeededSize;
    if ( !dwNeededSize )
    {
      RasTapiTrace("DwLineGetAddrCaps: NeededSize==0!!");
      return v13;
    }
  }
  else
  {
    if ( lpAddressCaps->dwNeededSize <= 0x320 )
      return v13;
    dwNeededSize = lpAddressCaps->dwNeededSize;
  }
  v15 = (struct lineaddresscaps_tag *)LocalAlloc(0x40u, dwNeededSize);
  *a8 = v15;
  if ( v15 )
  {
    v15->dwTotalSize = dwNeededSize;
    if ( a5 )
      return (unsigned int)RasLineGetAddressCaps(dwDeviceID, dwAddressID, dwExtVersion, v15);
    else
      return (unsigned int)lineGetAddressCapsA(RasLine, dwDeviceID, dwAddressID, dwAPIVersion, dwExtVersion, v15);
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x1800024bc  push    rbx
0x1800024be  push    rbp
0x1800024bf  push    rsi
0x1800024c0  push    rdi
0x1800024c1  push    r12
0x1800024c3  push    r13
0x1800024c5  push    r14
0x1800024c7  sub     rsp, 30h
0x1800024cb  mov     rdi, [rsp+68h+arg_30]
0x1800024d3  mov     r12d, r8d
0x1800024d6  mov     ebp, edx
0x1800024d8  mov     r14d, ecx
0x1800024db  xor     edx, edx; Val
0x1800024dd  mov     r8d, 31Ch; Size
0x1800024e3  mov     esi, r9d
0x1800024e6  lea     rcx, [rdi+4]; void *
0x1800024ea  call    memset_0
0x1800024ef  cmp     [rsp+68h+arg_20], 0
0x1800024f7  mov     r13, [rsp+68h+arg_38]
0x1800024ff  mov     dword ptr [rdi], 320h
0x180002505  mov     [r13+0], rdi
0x180002509  jnz     short loc_18000252B
0x18000250b  mov     ecx, cs:RasLine; hLineApp
0x180002511  mov     r9d, r12d; dwAPIVersion
0x180002514  mov     [rsp+68h+lpAddressCaps], rdi; lpAddressCaps
0x180002519  mov     r8d, ebp; dwAddressID
0x18000251c  mov     edx, r14d; dwDeviceID
0x18000251f  mov     [rsp+68h+dwExtVersion], esi; dwExtVersion
0x180002523  call    cs:__imp_lineGetAddressCapsA
0x180002529  jmp     short loc_18000253B
0x18000252b  mov     r9, rdi
0x18000252e  mov     r8d, esi
0x180002531  mov     edx, ebp
0x180002533  mov     ecx, r14d
0x180002536  call    RasLineGetAddressCaps
0x18000253b  mov     ebx, eax
0x18000253d  cmp     eax, 8000004Dh
0x180002542  jz      short loc_18000256E
0x180002544  cmp     dword ptr [rdi+4], 320h
0x18000254b  jbe     short loc_1800025C1
0x18000254d  mov     edi, [rdi+4]
0x180002550  mov     edx, edi; uBytes
0x180002552  mov     ecx, 40h ; '@'; uFlags
0x180002557  call    cs:__imp_LocalAlloc
0x18000255d  mov     [r13+0], rax
0x180002561  test    rax, rax
0x180002564  jnz     short loc_180002583
0x180002566  call    cs:__imp_GetLastError
0x18000256c  jmp     short loc_1800025BF
0x18000256e  mov     edi, [rdi+4]
0x180002571  test    edi, edi
0x180002573  jnz     short loc_180002550
0x180002575  lea     rcx, aDwlinegetaddrc; "DwLineGetAddrCaps: NeededSize==0!!"
0x18000257c  call    RasTapiTrace
0x180002581  jmp     short loc_1800025C1
0x180002583  cmp     [rsp+68h+arg_20], 0
0x18000258b  mov     [rax], edi
0x18000258d  jnz     short loc_1800025AF
0x18000258f  mov     ecx, cs:RasLine; hLineApp
0x180002595  mov     r9d, r12d; dwAPIVersion
0x180002598  mov     [rsp+68h+lpAddressCaps], rax; lpAddressCaps
0x18000259d  mov     r8d, ebp; dwAddressID
0x1800025a0  mov     edx, r14d; dwDeviceID
0x1800025a3  mov     [rsp+68h+dwExtVersion], esi; dwExtVersion
0x1800025a7  call    cs:__imp_lineGetAddressCapsA
0x1800025ad  jmp     short loc_1800025BF
0x1800025af  mov     r9, rax
0x1800025b2  mov     r8d, esi
0x1800025b5  mov     edx, ebp
0x1800025b7  mov     ecx, r14d
0x1800025ba  call    RasLineGetAddressCaps
0x1800025bf  mov     ebx, eax
0x1800025c1  mov     eax, ebx
0x1800025c3  add     rsp, 30h
0x1800025c7  pop     r14
0x1800025c9  pop     r13
0x1800025cb  pop     r12
0x1800025cd  pop     rdi
0x1800025ce  pop     rsi
0x1800025cf  pop     rbp
0x1800025d0  pop     rbx
0x1800025d1  retn
```
