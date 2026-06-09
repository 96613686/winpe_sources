# ICLocate

- ea: `0x1800033e0`
- end: `0x1800035c3`
- name: `ICLocate`
- size: `483`
- prototype: `HIC __stdcall(DWORD fccType, DWORD fccHandler, LPBITMAPINFOHEADER lpbiIn, LPBITMAPINFOHEADER lpbiOut, WORD wFlags)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a90`
- `0x1800047f0`
- `0x180005cf0`
- `0x1800060a0`
- `0x180008400`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180002640`
- `0x180002e90`
- `0x1800033e0`
- `0x1800035d0`
- `0x180003a60`

## pseudocode

```c
HIC __stdcall ICLocate(
        DWORD fccType,
        DWORD fccHandler,
        LPBITMAPINFOHEADER lpbiIn,
        LPBITMAPINFOHEADER lpbiOut,
        WORD wFlags)
{
  UINT v9; // edi
  HIC v10; // rax
  HIC v11; // rbx
  DWORD biCompression; // edx
  HIC v14; // rax
  DWORD i; // esi
  HIC v16; // rax
  ICINFO icinfo; // [rsp+30h] [rbp-288h] BYREF

  memset_0(&icinfo, 0, sizeof(icinfo));
  if ( !fccType )
    return 0;
  switch ( wFlags )
  {
    case 1u:
      goto LABEL_9;
    case 2u:
    case 3u:
      v9 = 16395;
      goto LABEL_10;
    case 5u:
LABEL_9:
      v9 = 16390;
      goto LABEL_10;
  }
  if ( wFlags != 8 )
    return 0;
  v9 = 16415;
LABEL_10:
  if ( fccHandler )
  {
    v10 = ICOpen(fccType, fccHandler, wFlags);
    v11 = v10;
    if ( v10 && !ICSendMessage(v10, v9, (DWORD_PTR)lpbiIn, (DWORD_PTR)lpbiOut) )
      return v11;
    if ( v11 )
      ICClose(v11);
  }
  if ( fccType == 1667524982 && lpbiIn )
  {
    biCompression = lpbiIn->biCompression;
    if ( biCompression <= 1 )
      biCompression = 1162629709;
    if ( biCompression > 0x100 )
    {
      if ( biCompression == 1296126531 )
        biCompression = 1129730893;
      v14 = ICOpen(0x63646976u, biCompression, wFlags);
      v11 = v14;
      if ( v14 && !ICSendMessage(v14, v9, (DWORD_PTR)lpbiIn, (DWORD_PTR)lpbiOut) )
        return v11;
      if ( v11 )
        ICClose(v11);
    }
  }
  for ( i = 0; ICInfo(fccType, i, &icinfo); ++i )
  {
    v16 = ICOpen(fccType, icinfo.fccHandler, wFlags);
    v11 = v16;
    if ( v16 )
    {
      if ( !ICSendMessage(v16, v9, (DWORD_PTR)lpbiIn, (DWORD_PTR)lpbiOut) )
      {
        if ( v11 )
          return v11;
        return 0;
      }
      ICClose(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800033e0  push    rbx
0x1800033e2  push    rsi
0x1800033e3  push    rdi
0x1800033e4  push    r12
0x1800033e6  push    r13
0x1800033e8  push    r14
0x1800033ea  push    r15
0x1800033ec  sub     rsp, 280h
0x1800033f3  mov     rax, cs:__security_cookie
0x1800033fa  xor     rax, rsp
0x1800033fd  mov     [rsp+2B8h+var_48], rax
0x180003405  mov     r13, r9
0x180003408  mov     r15, r8
0x18000340b  mov     ebx, edx
0x18000340d  mov     r12d, ecx
0x180003410  movzx   edi, [rsp+2B8h+wFlags]
0x180003418  xor     edx, edx; Val
0x18000341a  mov     r8d, 238h; Size
0x180003420  lea     rcx, [rsp+2B8h+icinfo]; void *
0x180003425  call    memset_0
0x18000342a  test    r12d, r12d
0x18000342d  jz      loc_18000359E
0x180003433  mov     r14d, edi
0x180003436  mov     ecx, edi
0x180003438  sub     ecx, 1
0x18000343b  jz      short loc_180003463
0x18000343d  sub     ecx, 1
0x180003440  jz      short loc_18000345C
0x180003442  sub     ecx, 1
0x180003445  jz      short loc_18000345C
0x180003447  sub     ecx, 2
0x18000344a  jz      short loc_180003463
0x18000344c  cmp     ecx, 3
0x18000344f  jnz     loc_18000359E
0x180003455  mov     edi, 401Fh
0x18000345a  jmp     short loc_180003468
0x18000345c  mov     edi, 400Bh
0x180003461  jmp     short loc_180003468
0x180003463  mov     edi, 4006h
0x180003468  mov     [rsp+2B8h+hic], 0
0x180003471  test    ebx, ebx
0x180003473  jz      short loc_1800034B9
0x180003475  mov     r8d, r14d; wMode
0x180003478  mov     edx, ebx; fccHandler
0x18000347a  mov     ecx, r12d; fccType
0x18000347d  call    ICOpen
0x180003482  mov     rbx, rax
0x180003485  mov     [rsp+2B8h+hic], rax
0x18000348a  test    rax, rax
0x18000348d  jz      short loc_1800034AC
0x18000348f  mov     r9, r13; dw2
0x180003492  mov     r8, r15; dw1
0x180003495  mov     edx, edi; msg
0x180003497  mov     rcx, rax; hic
0x18000349a  call    ICSendMessage
0x18000349f  test    rax, rax
0x1800034a2  jnz     short loc_1800034AC
0x1800034a4  mov     rax, rbx
0x1800034a7  jmp     loc_1800035A0
0x1800034ac  test    rbx, rbx
0x1800034af  jz      short loc_1800034B9
0x1800034b1  mov     rcx, rbx; hic
0x1800034b4  call    ICClose
0x1800034b9  mov     ecx, 63646976h; fccType
0x1800034be  cmp     r12d, ecx
0x1800034c1  jnz     short loc_180003527
0x1800034c3  test    r15, r15
0x1800034c6  jz      short loc_180003527
0x1800034c8  mov     edx, [r15+10h]
0x1800034cc  cmp     edx, 1
0x1800034cf  jz      short loc_1800034D5
0x1800034d1  test    edx, edx
0x1800034d3  jnz     short loc_1800034DA
0x1800034d5  mov     edx, 454C524Dh
0x1800034da  cmp     edx, 100h
0x1800034e0  jbe     short loc_180003527
0x1800034e2  mov     eax, 4356534Dh
0x1800034e7  cmp     edx, 4D415243h
0x1800034ed  cmovz   edx, eax; fccHandler
0x1800034f0  mov     r8d, r14d; wMode
0x1800034f3  call    ICOpen
0x1800034f8  mov     rbx, rax
0x1800034fb  mov     [rsp+2B8h+hic], rax
0x180003500  test    rax, rax
0x180003503  jz      short loc_18000351A
0x180003505  mov     r9, r13; dw2
0x180003508  mov     r8, r15; dw1
0x18000350b  mov     edx, edi; msg
0x18000350d  mov     rcx, rax; hic
0x180003510  call    ICSendMessage
0x180003515  test    rax, rax
0x180003518  jz      short loc_1800034A4
0x18000351a  test    rbx, rbx
0x18000351d  jz      short loc_180003527
0x18000351f  mov     rcx, rbx; hic
0x180003522  call    ICClose
0x180003527  xor     esi, esi
0x180003529  lea     r8, [rsp+2B8h+icinfo]; lpicinfo
0x18000352e  mov     edx, esi; fccHandler
0x180003530  mov     ecx, r12d; fccType
0x180003533  call    ICInfo
0x180003538  test    eax, eax
0x18000353a  jz      short loc_18000359E
0x18000353c  mov     r8d, r14d; wMode
0x18000353f  mov     edx, [rsp+2B8h+icinfo.fccHandler]; fccHandler
0x180003543  mov     ecx, r12d; fccType
0x180003546  call    ICOpen
0x18000354b  mov     rbx, rax
0x18000354e  mov     [rsp+2B8h+hic], rax
0x180003553  test    rax, rax
0x180003556  jz      short loc_180003576
0x180003558  mov     r9, r13; dw2
0x18000355b  mov     r8, r15; dw1
0x18000355e  mov     edx, edi; msg
0x180003560  mov     rcx, rbx; hic
0x180003563  call    ICSendMessage
0x180003568  test    rax, rax
0x18000356b  jz      short loc_18000357A
0x18000356d  mov     rcx, rbx; hic
0x180003570  call    ICClose
0x180003575  nop
0x180003576  inc     esi
0x180003578  jmp     short loc_180003529
0x18000357a  jmp     short loc_180003595
0x18000357c  mov     rbx, [rsp+2B8h+hic]
0x180003581  test    rbx, rbx
0x180003584  jz      short loc_180003595
0x180003586  mov     rcx, rbx; hic
0x180003589  call    ICClose
0x18000358e  xor     ebx, ebx
0x180003590  mov     [rsp+2B8h+hic], rbx
0x180003595  test    rbx, rbx
0x180003598  jnz     loc_1800034A4
0x18000359e  xor     eax, eax
0x1800035a0  mov     rcx, [rsp+2B8h+var_48]
0x1800035a8  xor     rcx, rsp; StackCookie
0x1800035ab  call    __security_check_cookie
0x1800035b0  add     rsp, 280h
0x1800035b7  pop     r15
0x1800035b9  pop     r14
0x1800035bb  pop     r13
0x1800035bd  pop     r12
0x1800035bf  pop     rdi
0x1800035c0  pop     rsi
0x1800035c1  pop     rbx
0x1800035c2  retn
```
