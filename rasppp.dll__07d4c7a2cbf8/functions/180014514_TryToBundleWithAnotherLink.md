# TryToBundleWithAnotherLink

- ea: `0x180014514`
- end: `0x18001483e`
- name: `TryToBundleWithAnotherLink`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e86c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000fd10`
- `0x180010850`
- `0x180014514`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014724`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014794`
- `rasman!RasPortBundle` at `0x1800145cc`
- `rasman!RasPortBundle` at `0x1800145cc`

## string_xrefs

- `0x1800145e9`: `Bundling this link with hPort = %d`

## pseudocode

```c
__int64 __fastcall TryToBundleWithAnotherLink(__int64 a1)
{
  __int64 *j; // rdi
  DWORD LastError; // r15d
  __int64 i; // rsi
  __int64 v5; // rax
  void *v6; // r14
  __int64 v7; // rcx
  __int64 k; // rsi
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // eax
  LPVOID v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v16 = 0;
  j = 0;
  LastError = 0;
  memset_0(v17, 0, sizeof(v17));
  *(_QWORD *)(a1 + 72) = -1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v5 = -1;
    if ( (unsigned int)i >= (unsigned int)qword_18004C970 )
      break;
    for ( j = (__int64 *)*((_QWORD *)PcbTable + i); j; j = (__int64 *)*j )
    {
      if ( j[2] != *(_QWORD *)(a1 + 16) && (j[7] & 1) != 0 && (unsigned int)CanPortsBeBundled(j, a1, 1) )
      {
        if ( *(_DWORD *)(j[1] + 16) >= *(_DWORD *)(j[1] + 24) )
        {
          LastError = 931;
          break;
        }
        LastError = RasPortBundle(j[2], *(_QWORD *)(a1 + 16));
        if ( !LastError )
        {
          if ( byte_18004CF33 < 0 )
          {
            LOWORD(v16) = 0;
            FormatRRASErrorString(&v16, L"Bundling this link with hPort = %d", j[2]);
            if ( byte_18004CF33 < 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v16);
          }
          *(_QWORD *)(a1 + 72) = j[2];
          break;
        }
      }
    }
    v5 = *(_QWORD *)(a1 + 72);
    if ( v5 != -1 )
      break;
  }
  v6 = 0;
  if ( !LastError && v5 != -1 )
  {
    if ( j )
      *((_DWORD *)j + 14) |= 2u;
    *(_DWORD *)(a1 + 56) |= 2u;
    v6 = *(void **)(a1 + 8);
    if ( j )
    {
      *(_QWORD *)(a1 + 8) = j[1];
      j[9] = *(_QWORD *)(a1 + 16);
    }
    ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
    ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 20LL);
    v7 = *(_QWORD *)(a1 + 8);
    for ( k = 0; (unsigned int)k < *(_DWORD *)(v7 + 48); k = (unsigned int)(k + 1) )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8 * k) )
      {
        if ( (byte_18004CF34 & 1) != 0 )
        {
          v9 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"Found slot %d for port %d in BCB back pointer array", (unsigned int)k, v9);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8 * k) = a1;
        break;
      }
    }
    v10 = *(_QWORD *)(a1 + 8);
    v11 = *(_DWORD *)(v10 + 48);
    if ( (_DWORD)k == v11 )
    {
      v12 = HeapReAlloc(hHeap, 8u, *(LPVOID *)(v10 + 8), 8LL * (unsigned int)(2 * v11));
      if ( v12 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = v12;
        if ( (byte_18004CF34 & 1) != 0 )
        {
          v14 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            &v16,
            L"Found slot %d for port %d in BCB back pointer array after ReAlloc",
            (unsigned int)k,
            v14);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8 * k) = a1;
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL) *= 2;
      }
      else
      {
        *(_QWORD *)(a1 + 8) = v6;
        --*(_DWORD *)(j[1] + 16);
        --*(_DWORD *)(j[1] + 20);
        *(_DWORD *)(a1 + 56) &= ~2u;
        if ( byte_18004CF33 < 0 )
        {
          v13 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"Couldn't ReAlloc BCB back pointer array for port %d", v13);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v16);
        }
        v6 = 0;
        LastError = GetLastError();
      }
    }
  }
  DeallocateAndRemoveBcbFromTable(v6);
  return LastError;
}

```

## disassembly

```asm
0x180014514  mov     [rsp-8+arg_8], rbx
0x180014519  mov     [rsp-8+arg_10], rsi
0x18001451e  push    rbp
0x18001451f  push    rdi
0x180014520  push    r12
0x180014522  push    r14
0x180014524  push    r15
0x180014526  lea     rbp, [rsp-730h]
0x18001452e  sub     rsp, 830h
0x180014535  mov     rax, cs:__security_cookie
0x18001453c  xor     rax, rsp
0x18001453f  mov     [rbp+750h+var_30], rax
0x180014546  mov     rbx, rcx
0x180014549  xor     eax, eax
0x18001454b  lea     rcx, [rsp+850h+var_82C]; void *
0x180014550  mov     [rsp+850h+var_830], eax
0x180014554  xor     edx, edx; Val
0x180014556  mov     r8d, 7FCh; Size
0x18001455c  xor     edi, edi
0x18001455e  xor     r15d, r15d
0x180014561  call    memset_0
0x180014566  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001456a  mov     [rbx+48h], r12
0x18001456e  xor     esi, esi
0x180014570  cmp     esi, dword ptr cs:qword_18004C970
0x180014576  mov     rax, r12
0x180014579  jnb     loc_180014644
0x18001457f  mov     rax, qword ptr cs:PcbTable
0x180014586  mov     rdi, [rax+rsi*8]
0x18001458a  test    rdi, rdi
0x18001458d  jz      loc_180014634
0x180014593  mov     rax, [rbx+10h]
0x180014597  cmp     [rdi+10h], rax
0x18001459b  jz      short loc_1800145D9
0x18001459d  test    byte ptr [rdi+38h], 1
0x1800145a1  jz      short loc_1800145D9
0x1800145a3  mov     r8d, 1
0x1800145a9  mov     rdx, rbx
0x1800145ac  mov     rcx, rdi
0x1800145af  call    CanPortsBeBundled
0x1800145b4  test    eax, eax
0x1800145b6  jz      short loc_1800145D9
0x1800145b8  mov     rcx, [rdi+8]
0x1800145bc  mov     eax, [rcx+18h]
0x1800145bf  cmp     [rcx+10h], eax
0x1800145c2  jnb     short loc_18001462E
0x1800145c4  mov     rdx, [rbx+10h]
0x1800145c8  mov     rcx, [rdi+10h]
0x1800145cc  call    cs:__imp_RasPortBundle
0x1800145d2  mov     r15d, eax
0x1800145d5  test    eax, eax
0x1800145d7  jz      short loc_1800145DE
0x1800145d9  mov     rdi, [rdi]
0x1800145dc  jmp     short loc_18001458A
0x1800145de  cmp     cs:byte_18004CF33, 0
0x1800145e5  jge     short loc_180014624
0x1800145e7  xor     eax, eax
0x1800145e9  lea     rdx, aBundlingThisLi; "Bundling this link with hPort = %d"
0x1800145f0  mov     word ptr [rsp+850h+var_830], ax
0x1800145f5  lea     rcx, [rsp+850h+var_830]
0x1800145fa  mov     r8, [rdi+10h]
0x1800145fe  call    FormatRRASErrorString
0x180014603  cmp     cs:byte_18004CF33, 0
0x18001460a  jge     short loc_180014624
0x18001460c  lea     r8, [rsp+850h+var_830]
0x180014611  lea     rdx, RasPppTraceError
0x180014618  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001461f  call    McTemplateU0z_EventWriteTransfer
0x180014624  mov     rax, [rdi+10h]
0x180014628  mov     [rbx+48h], rax
0x18001462c  jmp     short loc_180014634
0x18001462e  mov     r15d, 3A3h
0x180014634  mov     rax, [rbx+48h]
0x180014638  cmp     rax, r12
0x18001463b  jnz     short loc_180014644
0x18001463d  inc     esi
0x18001463f  jmp     loc_180014570
0x180014644  xor     r14d, r14d
0x180014647  test    r15d, r15d
0x18001464a  jnz     loc_180014808
0x180014650  cmp     rax, r12
0x180014653  jz      loc_180014808
0x180014659  test    rdi, rdi
0x18001465c  jz      short loc_180014662
0x18001465e  or      dword ptr [rdi+38h], 2
0x180014662  or      dword ptr [rbx+38h], 2
0x180014666  mov     r14, [rbx+8]
0x18001466a  test    rdi, rdi
0x18001466d  jz      short loc_18001467F
0x18001466f  mov     rax, [rdi+8]
0x180014673  mov     [rbx+8], rax
0x180014677  mov     rax, [rbx+10h]
0x18001467b  mov     [rdi+48h], rax
0x18001467f  mov     rax, [rbx+8]
0x180014683  inc     dword ptr [rax+10h]
0x180014686  mov     rax, [rbx+8]
0x18001468a  inc     dword ptr [rax+14h]
0x18001468d  mov     rcx, [rbx+8]
0x180014691  xor     esi, esi
0x180014693  cmp     esi, [rcx+30h]
0x180014696  jnb     short loc_1800146FC
0x180014698  mov     rax, [rcx+8]
0x18001469c  cmp     qword ptr [rax+rsi*8], 0
0x1800146a1  jz      short loc_1800146A7
0x1800146a3  inc     esi
0x1800146a5  jmp     short loc_180014693
0x1800146a7  test    cs:byte_18004CF34, 1
0x1800146ae  jz      short loc_1800146F0
0x1800146b0  mov     r9, [rbx+10h]
0x1800146b4  lea     rdx, aFoundSlotDForP; "Found slot %d for port %d in BCB back p"...
0x1800146bb  xor     eax, eax
0x1800146bd  lea     rcx, [rsp+850h+var_830]
0x1800146c2  mov     r8d, esi
0x1800146c5  mov     word ptr [rsp+850h+var_830], ax
0x1800146ca  call    FormatRRASErrorString
0x1800146cf  test    cs:byte_18004CF34, 1
0x1800146d6  jz      short loc_1800146F0
0x1800146d8  lea     r8, [rsp+850h+var_830]
0x1800146dd  lea     rdx, RasPppTraceInfo
0x1800146e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800146eb  call    McTemplateU0z_EventWriteTransfer
0x1800146f0  mov     rax, [rbx+8]
0x1800146f4  mov     rcx, [rax+8]
0x1800146f8  mov     [rcx+rsi*8], rbx
0x1800146fc  mov     r8, [rbx+8]
0x180014700  mov     eax, [r8+30h]
0x180014704  cmp     esi, eax
0x180014706  jnz     loc_180014808
0x18001470c  mov     r8, [r8+8]; lpMem
0x180014710  lea     r9d, [rax+rax]
0x180014714  mov     rcx, cs:hHeap; hHeap
0x18001471b  mov     edx, 8; dwFlags
0x180014720  shl     r9, 3; dwBytes
0x180014724  call    cs:__imp_HeapReAlloc
0x18001472a  mov     rcx, rax
0x18001472d  test    rax, rax
0x180014730  jnz     short loc_18001479F
0x180014732  mov     [rbx+8], r14
0x180014736  or      ecx, 0FFFFFFFFh
0x180014739  mov     rax, [rdi+8]
0x18001473d  add     [rax+10h], ecx
0x180014740  mov     rax, [rdi+8]
0x180014744  add     [rax+14h], ecx
0x180014747  and     dword ptr [rbx+38h], 0FFFFFFFDh
0x18001474b  cmp     cs:byte_18004CF33, 0
0x180014752  jge     short loc_180014791
0x180014754  mov     r8, [rbx+10h]
0x180014758  lea     rdx, aCouldnTRealloc; "Couldn't ReAlloc BCB back pointer array"...
0x18001475f  xor     eax, eax
0x180014761  lea     rcx, [rsp+850h+var_830]
0x180014766  mov     word ptr [rsp+850h+var_830], ax
0x18001476b  call    FormatRRASErrorString
0x180014770  cmp     cs:byte_18004CF33, 0
0x180014777  jge     short loc_180014791
0x180014779  lea     r8, [rsp+850h+var_830]
0x18001477e  lea     rdx, RasPppTraceError
0x180014785  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001478c  call    McTemplateU0z_EventWriteTransfer
0x180014791  xor     r14d, r14d
0x180014794  call    cs:__imp_GetLastError
0x18001479a  mov     r15d, eax
0x18001479d  jmp     short loc_180014808
0x18001479f  mov     rax, [rbx+8]
0x1800147a3  mov     [rax+8], rcx
0x1800147a7  test    cs:byte_18004CF34, 1
0x1800147ae  jz      short loc_1800147F0
0x1800147b0  mov     r9, [rbx+10h]
0x1800147b4  lea     rdx, aFoundSlotDForP_0; "Found slot %d for port %d in BCB back p"...
0x1800147bb  xor     eax, eax
0x1800147bd  lea     rcx, [rsp+850h+var_830]
0x1800147c2  mov     r8d, esi
0x1800147c5  mov     word ptr [rsp+850h+var_830], ax
0x1800147ca  call    FormatRRASErrorString
0x1800147cf  test    cs:byte_18004CF34, 1
0x1800147d6  jz      short loc_1800147F0
0x1800147d8  lea     r8, [rsp+850h+var_830]
0x1800147dd  lea     rdx, RasPppTraceInfo
0x1800147e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800147eb  call    McTemplateU0z_EventWriteTransfer
0x1800147f0  mov     rax, [rbx+8]
0x1800147f4  mov     rdx, [rax+8]
0x1800147f8  mov     [rdx+rsi*8], rbx
0x1800147fc  mov     rdx, [rbx+8]
0x180014800  mov     eax, [rdx+30h]
0x180014803  add     eax, eax
0x180014805  mov     [rdx+30h], eax
0x180014808  mov     rcx, r14; lpMem
0x18001480b  call    DeallocateAndRemoveBcbFromTable
0x180014810  mov     eax, r15d
0x180014813  mov     rcx, [rbp+750h+var_30]
0x18001481a  xor     rcx, rsp; StackCookie
0x18001481d  call    __security_check_cookie
0x180014822  lea     r11, [rsp+850h+var_20]
0x18001482a  mov     rbx, [r11+38h]
0x18001482e  mov     rsi, [r11+40h]
0x180014832  mov     rsp, r11
0x180014835  pop     r15
0x180014837  pop     r14
0x180014839  pop     r12
0x18001483b  pop     rdi
0x18001483c  pop     rbp
0x18001483d  retn
```
