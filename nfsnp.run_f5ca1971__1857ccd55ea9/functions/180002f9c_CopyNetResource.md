# CopyNetResource

- ea: `0x180002f9c`
- end: `0x18000319e`
- name: `CopyNetResource`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008570`

## callees

- `0x180002508`
- `0x180002f9c`
- `0x180009338`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000315b`
- `msvcrt!wcscpy_s` at `0x18000315b`
- `KERNEL32!SetLastError` at `0x180003055`
- `KERNEL32!SetLastError` at `0x18000310f`
- `KERNEL32!SetLastError` at `0x180003055`
- `KERNEL32!SetLastError` at `0x18000310f`
- `KERNEL32!GlobalFree` at `0x18000311e`
- `KERNEL32!GlobalFree` at `0x18000311e`
- `KERNEL32!GlobalAlloc` at `0x18000301b`
- `KERNEL32!GlobalAlloc` at `0x1800030d4`
- `KERNEL32!GlobalAlloc` at `0x18000301b`
- `KERNEL32!GlobalAlloc` at `0x1800030d4`

## pseudocode

```c
_QWORD *__fastcall CopyNetResource(__int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  SIZE_T v7; // rdx
  rsize_t v8; // rsi
  wchar_t *v9; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return 0;
    if ( (*((_BYTE *)v2 + 28) & 2) == 0 )
    {
LABEL_25:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 )
        WPP_SF_(v2[2], 37, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      return 0;
    }
    WPP_SF_(v2[2], 32, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
LABEL_24:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v3 = GlobalAlloc(0x40u, 0x30u);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    SetLastError(8u);
    goto LABEL_24;
  }
  *(_DWORD *)v3 = *(_DWORD *)a1;
  *((_DWORD *)v3 + 1) = *(_DWORD *)(a1 + 4);
  *((_DWORD *)v3 + 2) = *(_DWORD *)(a1 + 8);
  *((_DWORD *)v3 + 3) = *(_DWORD *)(a1 + 12);
  v3[2] = 0;
  v3[4] = 0;
  v3[5] = 0;
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v7 = 2LL * (unsigned int)(v6 + 1);
    v8 = (unsigned int)(v6 + 1);
    v9 = (wchar_t *)GlobalAlloc(0x40u, v7);
    v4[3] = v9;
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      SetLastError(8u);
      GlobalFree(v4);
      goto LABEL_24;
    }
    wcscpy_s(v9, v8, *(const wchar_t **)(a1 + 24));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180002f9c  push    rbx
0x180002f9e  push    rbp
0x180002f9f  push    rsi
0x180002fa0  push    rdi
0x180002fa1  push    r14
0x180002fa3  push    r15
0x180002fa5  sub     rsp, 28h
0x180002fa9  mov     rdi, rcx
0x180002fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fb3  lea     rbp, WPP_GLOBAL_Control
0x180002fba  lea     r14, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180002fc1  cmp     rcx, rbp
0x180002fc4  jz      short loc_180002FE4
0x180002fc6  test    byte ptr [rcx+1Ch], 1
0x180002fca  jz      short loc_180002FE4
0x180002fcc  mov     rcx, [rcx+10h]
0x180002fd0  mov     edx, 1Fh
0x180002fd5  mov     r8, r14
0x180002fd8  call    WPP_SF_
0x180002fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe4  xor     r15d, r15d
0x180002fe7  test    rdi, rdi
0x180002fea  jnz     short loc_180003013
0x180002fec  cmp     rcx, rbp
0x180002fef  jz      loc_18000314D
0x180002ff5  test    byte ptr [rcx+1Ch], 2
0x180002ff9  jz      loc_180003131
0x180002fff  mov     rcx, [rcx+10h]
0x180003003  lea     edx, [rdi+20h]
0x180003006  mov     r8, r14
0x180003009  call    WPP_SF_
0x18000300e  jmp     loc_18000312A
0x180003013  mov     edx, 30h ; '0'; dwBytes
0x180003018  lea     ecx, [rdx+10h]; uFlags
0x18000301b  call    cs:__imp_GlobalAlloc
0x180003022  nop     dword ptr [rax+rax+00h]
0x180003027  mov     rbx, rax
0x18000302a  test    rax, rax
0x18000302d  jnz     short loc_180003066
0x18000302f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003036  cmp     rcx, rbp
0x180003039  jz      short loc_180003050
0x18000303b  test    byte ptr [rcx+1Ch], 2
0x18000303f  jz      short loc_180003050
0x180003041  mov     rcx, [rcx+10h]
0x180003045  lea     edx, [rax+21h]
0x180003048  mov     r8, r14
0x18000304b  call    WPP_SF_
0x180003050  mov     ecx, 8; dwErrCode
0x180003055  call    cs:__imp_SetLastError
0x18000305c  nop     dword ptr [rax+rax+00h]
0x180003061  jmp     loc_18000312A
0x180003066  mov     eax, [rdi]
0x180003068  mov     [rbx], eax
0x18000306a  mov     eax, [rdi+4]
0x18000306d  mov     [rbx+4], eax
0x180003070  mov     eax, [rdi+8]
0x180003073  mov     [rbx+8], eax
0x180003076  mov     eax, [rdi+0Ch]
0x180003079  mov     [rbx+0Ch], eax
0x18000307c  mov     [rbx+10h], r15
0x180003080  mov     [rbx+20h], r15
0x180003084  mov     [rbx+28h], r15
0x180003088  mov     rax, [rdi+18h]
0x18000308c  test    rax, rax
0x18000308f  jz      loc_180003167
0x180003095  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003099  inc     rsi
0x18000309c  cmp     [rax+rsi*2], r15w
0x1800030a1  jnz     short loc_180003099
0x1800030a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030aa  cmp     rcx, rbp
0x1800030ad  jz      short loc_1800030C6
0x1800030af  test    byte ptr [rcx+1Ch], 8
0x1800030b3  jz      short loc_1800030C6
0x1800030b5  mov     rcx, [rcx+10h]
0x1800030b9  mov     edx, 22h ; '"'
0x1800030be  mov     r8, r14
0x1800030c1  call    WPP_SF_
0x1800030c6  lea     eax, [rsi+1]
0x1800030c9  mov     ecx, 40h ; '@'; uFlags
0x1800030ce  lea     rdx, [rax+rax]; dwBytes
0x1800030d2  mov     esi, eax
0x1800030d4  call    cs:__imp_GlobalAlloc
0x1800030db  nop     dword ptr [rax+rax+00h]
0x1800030e0  mov     [rbx+18h], rax
0x1800030e4  test    rax, rax
0x1800030e7  jnz     short loc_180003151
0x1800030e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f0  cmp     rcx, rbp
0x1800030f3  jz      short loc_18000310A
0x1800030f5  test    byte ptr [rcx+1Ch], 2
0x1800030f9  jz      short loc_18000310A
0x1800030fb  mov     rcx, [rcx+10h]
0x1800030ff  lea     edx, [rax+23h]
0x180003102  mov     r8, r14
0x180003105  call    WPP_SF_
0x18000310a  mov     ecx, 8; dwErrCode
0x18000310f  call    cs:__imp_SetLastError
0x180003116  nop     dword ptr [rax+rax+00h]
0x18000311b  mov     rcx, rbx; hMem
0x18000311e  call    cs:__imp_GlobalFree
0x180003125  nop     dword ptr [rax+rax+00h]
0x18000312a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003131  cmp     rcx, rbp
0x180003134  jz      short loc_18000314D
0x180003136  test    byte ptr [rcx+1Ch], 2
0x18000313a  jz      short loc_18000314D
0x18000313c  mov     rcx, [rcx+10h]
0x180003140  mov     edx, 25h ; '%'
0x180003145  mov     r8, r14
0x180003148  call    WPP_SF_
0x18000314d  xor     eax, eax
0x18000314f  jmp     short loc_180003190
0x180003151  mov     r8, [rdi+18h]; Source
0x180003155  mov     rdx, rsi; SizeInWords
0x180003158  mov     rcx, rax; Destination
0x18000315b  call    cs:__imp_wcscpy_s
0x180003162  nop     dword ptr [rax+rax+00h]
0x180003167  mov     rcx, cs:WPP_GLOBAL_Control
0x18000316e  cmp     rcx, rbp
0x180003171  jz      short loc_18000318D
0x180003173  test    byte ptr [rcx+1Ch], 1
0x180003177  jz      short loc_18000318D
0x180003179  mov     rcx, [rcx+10h]
0x18000317d  mov     edx, 24h ; '$'
0x180003182  mov     r9, rbx
0x180003185  mov     r8, r14
0x180003188  call    WPP_SF_q
0x18000318d  mov     rax, rbx
0x180003190  add     rsp, 28h
0x180003194  pop     r15
0x180003196  pop     r14
0x180003198  pop     rdi
0x180003199  pop     rsi
0x18000319a  pop     rbp
0x18000319b  pop     rbx
0x18000319c  retn
```
