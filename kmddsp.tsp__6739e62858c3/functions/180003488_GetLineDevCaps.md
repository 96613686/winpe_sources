# GetLineDevCaps

- ea: `0x180003488`
- end: `0x180003717`
- name: `GetLineDevCaps`
- size: `655`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180005a10`
- `0x1800062b0`

## callees

- `0x180001c7e`
- `0x18000298c`
- `0x180003488`
- `0x18000392c`
- `0x180003980`
- `0x180003af0`
- `0x180004184`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003574`
- `KERNEL32!LocalFree` at `0x180003574`
- `KERNEL32!LocalAlloc` at `0x180003589`
- `KERNEL32!LocalAlloc` at `0x180003589`

## pseudocode

```c
_DWORD *__fastcall GetLineDevCaps(int a1, int a2)
{
  unsigned int v2; // esi
  SIZE_T v5; // rdx
  _DWORD *v6; // rbx
  unsigned int v7; // ebp
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  void *lpInBuffer; // [rsp+70h] [rbp+18h] BYREF

  v2 = 396;
  lpInBuffer = 0;
  v5 = 396;
  while ( 1 )
  {
    v8 = LocalAlloc(0x40u, v5);
    v9 = v8;
    if ( !v8 )
    {
      TspLog(1, "GetLineDevCaps: failed to alloc mem of size(%x)", v2);
      return 0;
    }
    *v8 = v2;
    if ( (unsigned int)PrepareSyncRequest(117637392, a1, v2 + 12, &lpInBuffer) )
      return 0;
    v6 = lpInBuffer;
    *((_DWORD *)lpInBuffer + 5) = a1;
    v6[6] = a2;
    v6[7] = v2;
    v6[9] = 236;
    v6[8] = 236;
    memset_0(v6 + 10, 0, 0xE0u);
    if ( (unsigned int)SyncDriverRequest(0x8FFF23C8, v6) )
    {
      FreeRequest(v6);
      return 0;
    }
    TspLog(8, "GetLineDevCaps: ulNeeded(%x), LINEDEVCAPS(%x), LINE_DEV_CAPS(%x)", v6[8], 268, 236);
    v7 = 2 * v6[8] - 204;
    TspLog(8, "GetLineDevCaps: dwNeededSize(%x), dwTotalSize(%x)", v7, v2);
    if ( v7 <= v2 )
      break;
    FreeRequest(v6);
    LocalFree(v9);
    v5 = v7;
    v2 = v7;
  }
  *(_OWORD *)(v9 + 7) = *(_OWORD *)(v6 + 14);
  *(_OWORD *)(v9 + 11) = *(_OWORD *)(v6 + 18);
  *(_OWORD *)(v9 + 15) = *(_OWORD *)(v6 + 22);
  *(_OWORD *)(v9 + 19) = *(_OWORD *)(v6 + 26);
  *(_OWORD *)(v9 + 23) = *(_OWORD *)(v6 + 30);
  *(_OWORD *)(v9 + 27) = *(_OWORD *)(v6 + 34);
  *(_OWORD *)(v9 + 31) = *(_OWORD *)(v6 + 38);
  *(_OWORD *)(v9 + 35) = *(_OWORD *)(v6 + 42);
  *(_OWORD *)(v9 + 39) = *(_OWORD *)(v6 + 46);
  *(_OWORD *)(v9 + 43) = *(_OWORD *)(v6 + 50);
  *(_OWORD *)(v9 + 47) = *(_OWORD *)(v6 + 54);
  v9[51] = v6[58];
  v9[28] |= 0x2000u;
  v9[2] = 268;
  InsertVarDataString(v6 + 7, v6 + 10, v9, v9 + 3);
  InsertVarDataString(v6 + 7, v6 + 12, v9, v9 + 5);
  InsertVarDataString(v6 + 7, v6 + 15, v9, v9 + 8);
  InsertVarData(v6 + 7, v6 + 59, v9, v9 + 52);
  v9[54] = v6[61];
  InsertVarData(v6 + 7, v6 + 62, v9, v9 + 55);
  InsertVarData(v6 + 7, v6 + 64, v9, v9 + 57);
  v9[1] = v9[2];
  FreeRequest(v6);
  return v9;
}

```

## disassembly

```asm
0x180003488  mov     [rsp+arg_0], rbx
0x18000348d  mov     [rsp+arg_8], rbp
0x180003492  push    rsi
0x180003493  push    rdi
0x180003494  push    r12
0x180003496  push    r14
0x180003498  push    r15
0x18000349a  sub     rsp, 30h
0x18000349e  mov     esi, 18Ch
0x1800034a3  mov     [rsp+58h+lpInBuffer], 0
0x1800034ac  mov     r12d, edx
0x1800034af  mov     r15d, ecx
0x1800034b2  mov     edx, esi
0x1800034b4  jmp     loc_180003584
0x1800034b9  lea     r8d, [rsi+0Ch]
0x1800034bd  mov     [rdi], esi
0x1800034bf  lea     r9, [rsp+58h+lpInBuffer]
0x1800034c4  mov     edx, r15d
0x1800034c7  mov     ecx, 7030110h
0x1800034cc  call    PrepareSyncRequest
0x1800034d1  test    eax, eax
0x1800034d3  jnz     loc_1800035B5
0x1800034d9  mov     rbx, [rsp+58h+lpInBuffer]
0x1800034de  xor     edx, edx; Val
0x1800034e0  mov     r8d, 0E0h; Size
0x1800034e6  mov     [rbx+14h], r15d
0x1800034ea  lea     r14, [rbx+1Ch]
0x1800034ee  mov     [rbx+18h], r12d
0x1800034f2  lea     rcx, [rbx+28h]; void *
0x1800034f6  mov     [r14], esi
0x1800034f9  mov     dword ptr [rbx+24h], 0ECh
0x180003500  mov     dword ptr [rbx+20h], 0ECh
0x180003507  call    memset_0
0x18000350c  mov     rdx, rbx; lpInBuffer
0x18000350f  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180003514  call    SyncDriverRequest
0x180003519  test    eax, eax
0x18000351b  jnz     loc_18000370A
0x180003521  mov     r8d, [r14+4]
0x180003525  lea     rdx, aGetlinedevcaps; "GetLineDevCaps: ulNeeded(%x), LINEDEVCA"...
0x18000352c  mov     r9d, 10Ch
0x180003532  mov     [rsp+58h+var_38], 0ECh
0x18000353b  lea     ecx, [rax+8]
0x18000353e  call    TspLog
0x180003543  mov     eax, [r14+4]
0x180003547  lea     rdx, aGetlinedevcaps_1; "GetLineDevCaps: dwNeededSize(%x), dwTot"...
0x18000354e  mov     r9d, esi
0x180003551  mov     ecx, 8
0x180003556  lea     ebp, ds:0FFFFFFFFFFFFFF34h[rax*2]
0x18000355d  mov     r8d, ebp
0x180003560  call    TspLog
0x180003565  cmp     ebp, esi
0x180003567  jbe     short loc_1800035CF
0x180003569  mov     rcx, rbx; void *
0x18000356c  call    FreeRequest
0x180003571  mov     rcx, rdi; hMem
0x180003574  call    cs:__imp_LocalFree
0x18000357b  nop     dword ptr [rax+rax+00h]
0x180003580  mov     edx, ebp; uBytes
0x180003582  mov     esi, ebp
0x180003584  mov     ecx, 40h ; '@'; uFlags
0x180003589  call    cs:__imp_LocalAlloc
0x180003590  nop     dword ptr [rax+rax+00h]
0x180003595  mov     rdi, rax
0x180003598  test    rax, rax
0x18000359b  jnz     loc_1800034B9
0x1800035a1  mov     r8d, esi
0x1800035a4  lea     rdx, aGetlinedevcaps_0; "GetLineDevCaps: failed to alloc mem of "...
0x1800035ab  mov     ecx, 1
0x1800035b0  call    TspLog
0x1800035b5  xor     eax, eax
0x1800035b7  mov     rbx, [rsp+58h+arg_0]
0x1800035bc  mov     rbp, [rsp+58h+arg_8]
0x1800035c1  add     rsp, 30h
0x1800035c5  pop     r15
0x1800035c7  pop     r14
0x1800035c9  pop     r12
0x1800035cb  pop     rdi
0x1800035cc  pop     rsi
0x1800035cd  retn
0x1800035cf  movups  xmm0, xmmword ptr [r14+1Ch]
0x1800035d4  lea     r9, [rdi+0Ch]
0x1800035d8  mov     r8, rdi
0x1800035db  lea     rdx, [r14+0Ch]
0x1800035df  mov     rcx, r14
0x1800035e2  movups  xmmword ptr [rdi+1Ch], xmm0
0x1800035e6  movups  xmm1, xmmword ptr [r14+2Ch]
0x1800035eb  movups  xmmword ptr [rdi+2Ch], xmm1
0x1800035ef  movups  xmm0, xmmword ptr [r14+3Ch]
0x1800035f4  movups  xmmword ptr [rdi+3Ch], xmm0
0x1800035f8  movups  xmm1, xmmword ptr [r14+4Ch]
0x1800035fd  movups  xmmword ptr [rdi+4Ch], xmm1
0x180003601  movups  xmm0, xmmword ptr [r14+5Ch]
0x180003606  movups  xmmword ptr [rdi+5Ch], xmm0
0x18000360a  movups  xmm1, xmmword ptr [r14+6Ch]
0x18000360f  movups  xmmword ptr [rdi+6Ch], xmm1
0x180003613  movups  xmm0, xmmword ptr [r14+7Ch]
0x180003618  movups  xmmword ptr [rdi+7Ch], xmm0
0x18000361c  movups  xmm1, xmmword ptr [r14+8Ch]
0x180003624  movups  xmmword ptr [rdi+8Ch], xmm1
0x18000362b  movups  xmm0, xmmword ptr [r14+9Ch]
0x180003633  movups  xmmword ptr [rdi+9Ch], xmm0
0x18000363a  movups  xmm1, xmmword ptr [r14+0ACh]
0x180003642  movups  xmmword ptr [rdi+0ACh], xmm1
0x180003649  movups  xmm0, xmmword ptr [r14+0BCh]
0x180003651  movups  xmmword ptr [rdi+0BCh], xmm0
0x180003658  mov     eax, [r14+0CCh]
0x18000365f  mov     [rdi+0CCh], eax
0x180003665  bts     dword ptr [rdi+70h], 0Dh
0x18000366a  mov     dword ptr [rdi+8], 10Ch
0x180003671  call    InsertVarDataString
0x180003676  lea     r9, [rdi+14h]
0x18000367a  mov     r8, rdi
0x18000367d  lea     rdx, [r14+14h]
0x180003681  mov     rcx, r14
0x180003684  call    InsertVarDataString
0x180003689  lea     r9, [rdi+20h]
0x18000368d  mov     r8, rdi
0x180003690  lea     rdx, [r14+20h]
0x180003694  mov     rcx, r14
0x180003697  call    InsertVarDataString
0x18000369c  lea     r9, [rdi+0D0h]
0x1800036a3  mov     r8, rdi
0x1800036a6  lea     rdx, [r14+0D0h]
0x1800036ad  mov     rcx, r14
0x1800036b0  call    InsertVarData
0x1800036b5  mov     eax, [r14+0D8h]
0x1800036bc  lea     r9, [rdi+0DCh]
0x1800036c3  lea     rdx, [r14+0DCh]
0x1800036ca  mov     [rdi+0D8h], eax
0x1800036d0  mov     r8, rdi
0x1800036d3  mov     rcx, r14
0x1800036d6  call    InsertVarData
0x1800036db  lea     r9, [rdi+0E4h]
0x1800036e2  mov     r8, rdi
0x1800036e5  lea     rdx, [r14+0E4h]
0x1800036ec  mov     rcx, r14
0x1800036ef  call    InsertVarData
0x1800036f4  mov     eax, [rdi+8]
0x1800036f7  mov     rcx, rbx; void *
0x1800036fa  mov     [rdi+4], eax
0x1800036fd  call    FreeRequest
0x180003702  mov     rax, rdi
0x180003705  jmp     loc_1800035B7
0x18000370a  mov     rcx, rbx; void *
0x18000370d  call    FreeRequest
0x180003712  jmp     loc_1800035B5
```
