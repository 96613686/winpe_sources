# TapiNoLocationDlg

- ea: `0x180046234`
- end: `0x180046325`
- name: `TapiNoLocationDlg`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd74`
- `0x180011cec`
- `0x180028074`

## callees

- `0x180046234`
- `0x18004d110`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18004627c`
- `rtutils!TracePrintfExA` at `0x1800462b3`
- `rtutils!TracePrintfExA` at `0x1800462e7`
- `rtutils!TracePrintfExA` at `0x18004627c`
- `rtutils!TracePrintfExA` at `0x1800462b3`
- `rtutils!TracePrintfExA` at `0x1800462e7`
- `TAPI32!lineGetTranslateCapsW` at `0x1800462c5`
- `TAPI32!lineGetTranslateCapsW` at `0x1800462c5`
- `TAPI32!LOpenDialAsst` at `0x180046303`
- `TAPI32!LOpenDialAsst` at `0x180046303`

## pseudocode

```c
__int64 __fastcall TapiNoLocationDlg(__int64 a1, HLINEAPP *a2, __int64 a3)
{
  DWORD v3; // ecx
  LONG TranslateCapsW; // eax
  unsigned int v7; // ebx
  struct linetranslatecaps_tag TranslateCaps; // [rsp+20h] [rbp-48h] BYREF

  v3 = g_dwTraceId;
  memset(&TranslateCaps, 0, sizeof(TranslateCaps));
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "TapiNoLocationDlg");
    v3 = g_dwTraceId;
  }
  memset(&TranslateCaps, 0, sizeof(TranslateCaps));
  TranslateCaps.dwTotalSize = 44;
  if ( v3 != -1 )
    TracePrintfExA(v3, 0xCu, "lineGetTranslateCapsW");
  TranslateCapsW = lineGetTranslateCapsW(*a2, 0x10004u, &TranslateCaps);
  v7 = TranslateCapsW;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "lineGetTranslateCapsW=$%X", TranslateCapsW);
  if ( v7 == -2147483634 )
    return (unsigned int)LOpenDialAsst(
                           a3,
                           0,
                           1,
                           1,
                           *(_QWORD *)&TranslateCaps.dwTotalSize,
                           *(_QWORD *)&TranslateCaps.dwUsedSize,
                           *(_QWORD *)&TranslateCaps.dwLocationListSize,
                           *(_QWORD *)&TranslateCaps.dwCurrentLocationID,
                           *(_QWORD *)&TranslateCaps.dwCardListSize,
                           TranslateCaps.dwCurrentPreferredCardID);
  return v7;
}

```

## disassembly

```asm
0x180046234  mov     [rsp+arg_0], rbx
0x180046239  push    rdi
0x18004623a  sub     rsp, 60h
0x18004623e  mov     rax, cs:__security_cookie
0x180046245  xor     rax, rsp
0x180046248  mov     [rsp+68h+var_18], rax
0x18004624d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180046253  xorps   xmm0, xmm0
0x180046256  mov     rdi, r8
0x180046259  mov     rbx, rdx
0x18004625c  movups  xmmword ptr [rsp+68h+TranslateCaps.dwLocationListSize], xmm0
0x180046261  movups  xmmword ptr [rsp+68h+TranslateCaps.dwNumCards], xmm0
0x180046266  movups  xmmword ptr [rsp+68h+TranslateCaps.dwTotalSize], xmm0
0x18004626b  cmp     ecx, 0FFFFFFFFh
0x18004626e  jz      short loc_180046288
0x180046270  lea     r8, aTapinolocation; "TapiNoLocationDlg"
0x180046277  mov     edx, 0Ch; dwFlags
0x18004627c  call    cs:__imp_TracePrintfExA
0x180046282  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180046288  xorps   xmm0, xmm0
0x18004628b  movups  xmmword ptr [rsp+68h+TranslateCaps.dwTotalSize], xmm0
0x180046290  mov     [rsp+68h+TranslateCaps.dwTotalSize], 2Ch ; ','
0x180046298  movups  xmmword ptr [rsp+68h+TranslateCaps.dwLocationListSize], xmm0
0x18004629d  movups  xmmword ptr [rsp+68h+TranslateCaps.dwNumCards], xmm0
0x1800462a2  cmp     ecx, 0FFFFFFFFh
0x1800462a5  jz      short loc_1800462B9
0x1800462a7  lea     r8, aLinegettransla_0; "lineGetTranslateCapsW"
0x1800462ae  mov     edx, 0Ch; dwFlags
0x1800462b3  call    cs:__imp_TracePrintfExA
0x1800462b9  mov     ecx, [rbx]; hLineApp
0x1800462bb  lea     r8, [rsp+68h+TranslateCaps]; lpTranslateCaps
0x1800462c0  mov     edx, 10004h; dwAPIVersion
0x1800462c5  call    cs:__imp_lineGetTranslateCapsW
0x1800462cb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800462d1  mov     ebx, eax
0x1800462d3  cmp     ecx, 0FFFFFFFFh
0x1800462d6  jz      short loc_1800462ED
0x1800462d8  mov     r9d, eax
0x1800462db  lea     r8, aLinegettransla_1; "lineGetTranslateCapsW=$%X"
0x1800462e2  mov     edx, 0Ch; dwFlags
0x1800462e7  call    cs:__imp_TracePrintfExA
0x1800462ed  cmp     ebx, 8000000Eh
0x1800462f3  jnz     short loc_18004630B
0x1800462f5  mov     r8d, 1
0x1800462fb  xor     edx, edx
0x1800462fd  mov     r9d, r8d
0x180046300  mov     rcx, rdi
0x180046303  call    cs:__imp_LOpenDialAsst
0x180046309  mov     ebx, eax
0x18004630b  mov     eax, ebx
0x18004630d  mov     rcx, [rsp+68h+var_18]
0x180046312  xor     rcx, rsp; StackCookie
0x180046315  call    __security_check_cookie
0x18004631a  mov     rbx, [rsp+68h+arg_0]
0x18004631f  add     rsp, 60h
0x180046323  pop     rdi
0x180046324  retn
```
