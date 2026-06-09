# UpdateAdvertisement

- ea: `0x18004ffd8`
- end: `0x180050369`
- name: `UpdateAdvertisement`
- size: `913`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018be4`
- `0x18004d8d0`
- `0x18004fd14`

## callees

- `0x180011790`
- `0x18004deac`
- `0x18004ffa8`
- `0x18004ffd8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800500cf`
- `KERNEL32!HeapFree` at `0x1800500cf`
- `KERNEL32!HeapAlloc` at `0x18005018a`
- `KERNEL32!HeapAlloc` at `0x18005018a`
- `WS2_32!__imp_htonl` at `0x1800502c4`
- `WS2_32!__imp_htonl` at `0x1800502c4`
- `WS2_32!__imp_htons` at `0x180050250`
- `WS2_32!__imp_htons` at `0x180050250`

## string_xrefs

- `0x180050067`: `Entered: UpdateAdvertisement`
- `0x18005011e`: `UpdateAdvertisement: Arithmetic overflow - cant allocate %d bytes for Icmp Msg`
- `0x1800501c7`: `UpdateAdvertisement: Cant allocate %d bytes for Icmp Msg`
- `0x18005030b`: `Leaving: UpdateAdvertisement`

## pseudocode

```c
__int64 __fastcall UpdateAdvertisement(__int64 a1)
{
  __int128 *v2; // r9
  _BYTE *v3; // r8
  unsigned int v4; // r14d
  int v5; // eax
  __int128 *v6; // r9
  __int128 *v7; // r9
  __int64 v9; // rbx
  unsigned int v10; // r15d
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int16 v15; // ax
  __int64 v16; // rcx
  __int128 *v17; // r9
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+4Ch] [rbp-B4h]
  __int128 v22; // [rsp+5Ch] [rbp-A4h]
  int v23; // [rsp+6Ch] [rbp-94h]
  int v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  LODWORD(dwBytes) = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v19 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    v2 = &v19;
    if ( a1 != -688 )
      LODWORD(v2) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: UpdateAdvertisement",
      (_DWORD)v2,
      *(_QWORD *)(a1 + 72),
      (__int64)&v20);
  }
  if ( *(_QWORD *)(a1 + 296) )
  {
    SizeofRtrDiscAdvt(*(unsigned int *)(a1 + 668), &dwBytes);
    v4 = dwBytes;
    if ( *(_DWORD *)(a1 + 320) >= (unsigned int)dwBytes )
      goto LABEL_23;
    HeapFree(IPRouterHeap, 0, v3);
    *(_QWORD *)(a1 + 296) = 0;
    *(_DWORD *)(a1 + 320) = 0;
  }
  v5 = SizeofRtrDiscAdvt(*(unsigned int *)(a1 + 668), &dwBytes);
  v4 = dwBytes;
  if ( v5 >= 0 )
  {
    *(_QWORD *)(a1 + 296) = HeapAlloc(IPRouterHeap, 8u, (unsigned int)dwBytes);
  }
  else
  {
    *(_QWORD *)(a1 + 296) = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v24) = 0;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v24, L"UpdateAdvertisement: Arithmetic overflow - cant allocate %d bytes for Icmp Msg", v4);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = &v19;
        if ( a1 != -688 )
          LODWORD(v6) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v24,
          (_DWORD)v6,
          *(_QWORD *)(a1 + 72),
          (__int64)&v20);
      }
    }
  }
  v3 = *(_BYTE **)(a1 + 296);
  if ( !v3 )
  {
    *(_DWORD *)(a1 + 220) = 0;
    *(_DWORD *)(a1 + 320) = 0;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v24) = 0;
      LOWORD(v20) = 0;
      FormatRRASErrorString(&v24, L"UpdateAdvertisement: Cant allocate %d bytes for Icmp Msg", v4);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v7 = &v19;
        if ( a1 != -688 )
          LODWORD(v7) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v24,
          (_DWORD)v7,
          *(_QWORD *)(a1 + 72),
          (__int64)&v20);
      }
    }
    return 8;
  }
  *(_DWORD *)(a1 + 320) = v4;
LABEL_23:
  *v3 = 9;
  *(_BYTE *)(*(_QWORD *)(a1 + 296) + 1LL) = 0;
  v9 = *(_QWORD *)(a1 + 296);
  *(_WORD *)(v9 + 6) = htons(*(_WORD *)(a1 + 218));
  v10 = 0;
  *(_BYTE *)(*(_QWORD *)(a1 + 296) + 5LL) = 2;
  *(_WORD *)(*(_QWORD *)(a1 + 296) + 2LL) = 0;
  v11 = *(_QWORD *)(a1 + 296);
  v12 = *(_BYTE *)(a1 + 668);
  *(_QWORD *)(a1 + 312) = v11;
  *(_DWORD *)(a1 + 304) = v4;
  for ( *(_BYTE *)(v11 + 4) = v12;
        v10 < *(_DWORD *)(a1 + 668);
        *(_DWORD *)(v14 + 8 * v13 + 12) = htonl(*(_DWORD *)(a1 + 228)) )
  {
    v13 = v10;
    *(_DWORD *)(*(_QWORD *)(a1 + 296) + 8LL * v10 + 8) = *(_DWORD *)(28LL * v10 + *(_QWORD *)(a1 + 712));
    v14 = *(_QWORD *)(a1 + 296);
    ++v10;
  }
  v15 = Compute16BitXSum(*(_QWORD *)(a1 + 296), v4);
  *(_WORD *)(v16 + 2) = v15;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    v17 = &v19;
    if ( a1 != -688 )
      LODWORD(v17) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: UpdateAdvertisement",
      (_DWORD)v17,
      *(_QWORD *)(a1 + 72),
      (__int64)&v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18004ffd8  mov     [rsp-8+arg_8], rbx
0x18004ffdd  mov     [rsp-8+arg_10], rsi
0x18004ffe2  push    rbp
0x18004ffe3  push    rdi
0x18004ffe4  push    r12
0x18004ffe6  push    r14
0x18004ffe8  push    r15
0x18004ffea  lea     rbp, [rsp-780h]
0x18004fff2  sub     rsp, 880h
0x18004fff9  mov     rax, cs:__security_cookie
0x180050000  xor     rax, rsp
0x180050003  mov     [rbp+7A0h+var_30], rax
0x18005000a  mov     rsi, rcx
0x18005000d  xor     r12d, r12d
0x180050010  lea     rcx, [rsp+8A0h+var_82C]; void *
0x180050015  mov     dword ptr [rsp+8A0h+dwBytes], r12d
0x18005001a  xor     edx, edx; Val
0x18005001c  mov     [rsp+8A0h+var_830], r12d
0x180050021  mov     r8d, 7FCh; Size
0x180050027  call    memset_0
0x18005002c  xorps   xmm0, xmm0
0x18005002f  mov     [rsp+8A0h+var_858], r12d
0x180050034  xor     eax, eax
0x180050036  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18005003d  movups  [rsp+8A0h+var_854], xmm0
0x180050042  mov     [rsp+8A0h+var_834], eax
0x180050046  movups  [rsp+8A0h+var_844], xmm0
0x18005004b  movups  [rsp+8A0h+var_868], xmm0
0x180050050  jz      short loc_180050098
0x180050052  lea     rax, [rsi+2B0h]
0x180050059  mov     word ptr [rsp+8A0h+var_858], r12w
0x18005005f  test    rax, rax
0x180050062  lea     r9, [rsp+8A0h+var_868]
0x180050067  lea     r8, aEnteredUpdatea; "Entered: UpdateAdvertisement"
0x18005006e  cmovnz  r9, rax
0x180050072  lea     rdx, RasRtrmgrParamTraceInfo
0x180050079  lea     rax, [rsp+8A0h+var_858]
0x18005007e  mov     [rsp+8A0h+var_878], rax
0x180050083  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005008a  mov     rax, [rsi+48h]
0x18005008e  mov     [rsp+8A0h+var_880], rax
0x180050093  call    McTemplateU0zjzz_EventWriteTransfer
0x180050098  mov     r8, [rsi+128h]
0x18005009f  test    r8, r8
0x1800500a2  jz      short loc_1800500E3
0x1800500a4  mov     ecx, [rsi+29Ch]
0x1800500aa  lea     rdx, [rsp+8A0h+dwBytes]
0x1800500af  call    SizeofRtrDiscAdvt
0x1800500b4  mov     r14d, dword ptr [rsp+8A0h+dwBytes]
0x1800500b9  cmp     [rsi+140h], r14d
0x1800500c0  jnb     loc_180050233
0x1800500c6  mov     rcx, cs:IPRouterHeap; hHeap
0x1800500cd  xor     edx, edx; dwFlags
0x1800500cf  call    cs:__imp_HeapFree
0x1800500d5  mov     [rsi+128h], r12
0x1800500dc  mov     [rsi+140h], r12d
0x1800500e3  mov     ecx, [rsi+29Ch]
0x1800500e9  lea     rdx, [rsp+8A0h+dwBytes]
0x1800500ee  call    SizeofRtrDiscAdvt
0x1800500f3  mov     r14d, dword ptr [rsp+8A0h+dwBytes]
0x1800500f8  mov     ebx, 8
0x1800500fd  test    eax, eax
0x1800500ff  jns     short loc_18005017E
0x180050101  mov     [rsi+128h], r12
0x180050108  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18005010f  jge     loc_180050197
0x180050115  mov     r8d, r14d
0x180050118  mov     word ptr [rsp+8A0h+var_830], r12w
0x18005011e  lea     rdx, aUpdateadvertis_0; "UpdateAdvertisement: Arithmetic overflo"...
0x180050125  mov     word ptr [rsp+8A0h+var_858], r12w
0x18005012b  lea     rcx, [rsp+8A0h+var_830]
0x180050130  call    FormatRRASErrorString
0x180050135  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18005013c  jge     short loc_180050197
0x18005013e  lea     rax, [rsi+2B0h]
0x180050145  test    rax, rax
0x180050148  lea     r9, [rsp+8A0h+var_868]
0x18005014d  lea     r8, [rsp+8A0h+var_830]
0x180050152  cmovnz  r9, rax
0x180050156  lea     rdx, RasRtrmgrParamTraceInfo
0x18005015d  lea     rax, [rsp+8A0h+var_858]
0x180050162  mov     [rsp+8A0h+var_878], rax
0x180050167  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005016e  mov     rax, [rsi+48h]
0x180050172  mov     [rsp+8A0h+var_880], rax
0x180050177  call    McTemplateU0zjzz_EventWriteTransfer
0x18005017c  jmp     short loc_180050197
0x18005017e  mov     rcx, cs:IPRouterHeap; hHeap
0x180050185  mov     r8, r14; dwBytes
0x180050188  mov     edx, ebx; dwFlags
0x18005018a  call    cs:__imp_HeapAlloc
0x180050190  mov     [rsi+128h], rax
0x180050197  mov     r8, [rsi+128h]
0x18005019e  test    r8, r8
0x1800501a1  jnz     loc_18005022C
0x1800501a7  mov     [rsi+0DCh], r12d
0x1800501ae  mov     [rsi+140h], r12d
0x1800501b5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800501bc  jge     short loc_180050225
0x1800501be  mov     r8d, r14d
0x1800501c1  mov     word ptr [rsp+8A0h+var_830], r12w
0x1800501c7  lea     rdx, aUpdateadvertis; "UpdateAdvertisement: Cant allocate %d b"...
0x1800501ce  mov     word ptr [rsp+8A0h+var_858], r12w
0x1800501d4  lea     rcx, [rsp+8A0h+var_830]
0x1800501d9  call    FormatRRASErrorString
0x1800501de  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800501e5  jge     short loc_180050225
0x1800501e7  lea     r8, [rsi+2B0h]
0x1800501ee  test    r8, r8
0x1800501f1  lea     r9, [rsp+8A0h+var_868]
0x1800501f6  lea     rdx, RasRtrmgrParamTraceInfo
0x1800501fd  cmovnz  r9, r8
0x180050201  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050208  lea     r8, [rsp+8A0h+var_858]
0x18005020d  mov     [rsp+8A0h+var_878], r8
0x180050212  mov     r8, [rsi+48h]
0x180050216  mov     [rsp+8A0h+var_880], r8
0x18005021b  lea     r8, [rsp+8A0h+var_830]
0x180050220  call    McTemplateU0zjzz_EventWriteTransfer
0x180050225  mov     eax, ebx
0x180050227  jmp     loc_18005033E
0x18005022c  mov     [rsi+140h], r14d
0x180050233  mov     byte ptr [r8], 9
0x180050237  mov     rax, [rsi+128h]
0x18005023e  mov     [rax+1], r12b
0x180050242  movzx   ecx, word ptr [rsi+0DAh]; hostshort
0x180050249  mov     rbx, [rsi+128h]
0x180050250  call    cs:__imp_htons
0x180050256  mov     [rbx+6], ax
0x18005025a  mov     r15d, r12d
0x18005025d  mov     rax, [rsi+128h]
0x180050264  mov     byte ptr [rax+5], 2
0x180050268  mov     rcx, [rsi+128h]
0x18005026f  mov     [rcx+2], r12w
0x180050274  mov     rcx, [rsi+128h]
0x18005027b  mov     al, [rsi+29Ch]
0x180050281  mov     [rsi+138h], rcx
0x180050288  mov     [rsi+130h], r14d
0x18005028f  mov     [rcx+4], al
0x180050292  cmp     [rsi+29Ch], r12d
0x180050299  jbe     short loc_1800502DA
0x18005029b  mov     rax, [rsi+2C8h]
0x1800502a2  mov     rdx, [rsi+128h]
0x1800502a9  mov     edi, r15d
0x1800502ac  imul    rcx, rdi, 1Ch
0x1800502b0  mov     ecx, [rcx+rax]
0x1800502b3  mov     [rdx+rdi*8+8], ecx
0x1800502b7  mov     ecx, [rsi+0E4h]; hostlong
0x1800502bd  mov     rbx, [rsi+128h]
0x1800502c4  call    cs:__imp_htonl
0x1800502ca  inc     r15d
0x1800502cd  mov     [rbx+rdi*8+0Ch], eax
0x1800502d1  cmp     r15d, [rsi+29Ch]
0x1800502d8  jb      short loc_18005029B
0x1800502da  mov     rcx, [rsi+128h]
0x1800502e1  mov     edx, r14d
0x1800502e4  call    Compute16BitXSum
0x1800502e9  mov     [rcx+2], ax
0x1800502ed  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800502f4  jz      short loc_18005033C
0x1800502f6  lea     rax, [rsi+2B0h]
0x1800502fd  mov     word ptr [rsp+8A0h+var_858], r12w
0x180050303  test    rax, rax
0x180050306  lea     r9, [rsp+8A0h+var_868]
0x18005030b  lea     r8, aLeavingUpdatea; "Leaving: UpdateAdvertisement"
0x180050312  cmovnz  r9, rax
0x180050316  lea     rdx, RasRtrmgrParamTraceInfo
0x18005031d  lea     rax, [rsp+8A0h+var_858]
0x180050322  mov     [rsp+8A0h+var_878], rax
0x180050327  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005032e  mov     rax, [rsi+48h]
0x180050332  mov     [rsp+8A0h+var_880], rax
0x180050337  call    McTemplateU0zjzz_EventWriteTransfer
0x18005033c  xor     eax, eax
0x18005033e  mov     rcx, [rbp+7A0h+var_30]
0x180050345  xor     rcx, rsp; StackCookie
0x180050348  call    __security_check_cookie
0x18005034d  lea     r11, [rsp+8A0h+var_20]
0x180050355  mov     rbx, [r11+38h]
0x180050359  mov     rsi, [r11+40h]
0x18005035d  mov     rsp, r11
0x180050360  pop     r15
0x180050362  pop     r14
0x180050364  pop     r12
0x180050366  pop     rdi
0x180050367  pop     rbp
0x180050368  retn
```
