# ICSeqCompressFrame

- ea: `0x1800063c0`
- end: `0x1800064ff`
- name: `ICSeqCompressFrame`
- size: `319`
- prototype: `LPVOID __stdcall(PCOMPVARS pc, UINT uiFlags, LPVOID lpBits, BOOL *pfKey, LONG *plSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800026e0`
- `0x180002770`
- `0x1800063c0`

## pseudocode

```c
LPVOID __stdcall ICSeqCompressFrame(PCOMPVARS pc, UINT uiFlags, LPVOID lpBits, BOOL *pfKey, LONG *plSize)
{
  LONG *v5; // rdi
  LONG dwFrameSize; // ecx
  void *lpPrev; // rax
  LPBITMAPINFO lpbiPrev; // r8
  DWORD v12; // edx
  bool v13; // zf
  DWORD ckid[4]; // [rsp+70h] [rbp-18h] BYREF
  DWORD dwFlags; // [rsp+90h] [rbp+8h] BYREF

  v5 = plSize;
  dwFlags = 0;
  ckid[0] = 0;
  if ( plSize )
    dwFrameSize = *plSize;
  else
    dwFrameSize = 0;
  if ( pc->lKeyCount < pc->lKey )
  {
    lpPrev = pc->lpBitsPrev;
    v12 = 0;
    lpbiPrev = pc->lpbiIn;
  }
  else
  {
    lpPrev = 0;
    dwFlags = 16;
    lpbiPrev = 0;
    v12 = 1;
  }
  if ( (ICCompress(
          pc->hic,
          v12,
          &pc->lpbiOut->bmiHeader,
          pc->lpBitsOut,
          &pc->lpbiIn->bmiHeader,
          lpBits,
          ckid,
          &dwFlags,
          pc->lFrame,
          dwFrameSize,
          pc->lQ,
          &lpbiPrev->bmiHeader,
          lpPrev)
      & 0x80000000) != 0 )
    return 0;
  if ( v5 )
    *v5 = pc->lpbiOut->bmiHeader.biSizeImage;
  if ( pc->lpBitsPrev
    && ICDecompress(pc->hic, 0, &pc->lpbiOut->bmiHeader, pc->lpBitsOut, &pc->lpbiIn->bmiHeader, pc->lpBitsPrev) )
  {
    return 0;
  }
  v13 = (dwFlags & 0x10) == 0;
  *pfKey = dwFlags & 0x10;
  if ( !v13 )
    pc->lKeyCount = 0;
  if ( pc->lKey )
    ++pc->lKeyCount;
  else
    pc->lKeyCount = -1;
  ++pc->lFrame;
  return pc->lpBitsOut;
}

```

## disassembly

```asm
0x1800063c0  mov     rax, rsp
0x1800063c3  mov     [rax+10h], rbx
0x1800063c7  mov     [rax+18h], rsi
0x1800063cb  push    rdi
0x1800063cc  sub     rsp, 80h
0x1800063d3  mov     rdi, [rsp+88h+plSize]
0x1800063db  mov     rsi, r9
0x1800063de  mov     dword ptr [rax+8], 0
0x1800063e5  mov     r9, r8
0x1800063e8  mov     dword ptr [rax-18h], 0
0x1800063ef  mov     rbx, rcx
0x1800063f2  test    rdi, rdi
0x1800063f5  jz      short loc_1800063FB
0x1800063f7  mov     ecx, [rdi]
0x1800063f9  jmp     short loc_1800063FD
0x1800063fb  xor     ecx, ecx
0x1800063fd  mov     eax, [rbx+3Ch]
0x180006400  cmp     [rbx+48h], eax
0x180006403  jl      short loc_18000641C
0x180006405  xor     eax, eax
0x180006407  mov     [rsp+88h+dwFlags], 10h
0x180006412  xor     r8d, r8d
0x180006415  mov     edx, 1
0x18000641a  jmp     short loc_180006426
0x18000641c  mov     rax, [rbx+30h]
0x180006420  xor     edx, edx; dwFlags
0x180006422  mov     r8, [rbx+18h]
0x180006426  mov     [rsp+88h+lpPrev], rax; lpPrev
0x18000642b  mov     eax, [rbx+44h]
0x18000642e  mov     [rsp+88h+lpbiPrev], r8; lpbiPrev
0x180006433  mov     r8, [rbx+20h]; lpbiOutput
0x180006437  mov     [rsp+88h+dwQuality], eax; dwQuality
0x18000643b  mov     eax, [rbx+38h]
0x18000643e  mov     [rsp+88h+dwFrameSize], ecx; dwFrameSize
0x180006442  mov     rcx, [rbx+8]; hic
0x180006446  mov     [rsp+88h+lFrameNum], eax; lFrameNum
0x18000644a  lea     rax, [rsp+88h+dwFlags]
0x180006452  mov     [rsp+88h+lpdwFlags], rax; lpdwFlags
0x180006457  lea     rax, [rsp+88h+ckid]
0x18000645c  mov     [rsp+88h+lpckid], rax; lpckid
0x180006461  mov     rax, [rbx+18h]
0x180006465  mov     [rsp+88h+lpBits], r9; lpBits
0x18000646a  mov     r9, [rbx+28h]; lpData
0x18000646e  mov     [rsp+88h+lpbiInput], rax; lpbiInput
0x180006473  call    ICCompress
0x180006478  test    eax, eax
0x18000647a  js      short loc_1800064E8
0x18000647c  test    rdi, rdi
0x18000647f  jz      short loc_18000648A
0x180006481  mov     rax, [rbx+20h]
0x180006485  mov     ecx, [rax+14h]
0x180006488  mov     [rdi], ecx
0x18000648a  mov     rax, [rbx+30h]
0x18000648e  test    rax, rax
0x180006491  jz      short loc_1800064B8
0x180006493  mov     r9, [rbx+28h]; lpData
0x180006497  xor     edx, edx; dwFlags
0x180006499  mov     r8, [rbx+20h]; lpbiFormat
0x18000649d  mov     rcx, [rbx+8]; hic
0x1800064a1  mov     [rsp+88h+lpBits], rax; lpBits
0x1800064a6  mov     rax, [rbx+18h]
0x1800064aa  mov     [rsp+88h+lpbiInput], rax; lpbi
0x1800064af  call    ICDecompress
0x1800064b4  test    eax, eax
0x1800064b6  jnz     short loc_1800064E8
0x1800064b8  mov     eax, [rsp+88h+dwFlags]
0x1800064bf  and     eax, 10h
0x1800064c2  mov     [rsi], eax
0x1800064c4  jz      short loc_1800064CD
0x1800064c6  mov     dword ptr [rbx+48h], 0
0x1800064cd  cmp     dword ptr [rbx+3Ch], 0
0x1800064d1  jz      short loc_1800064D8
0x1800064d3  inc     dword ptr [rbx+48h]
0x1800064d6  jmp     short loc_1800064DF
0x1800064d8  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800064df  inc     dword ptr [rbx+38h]
0x1800064e2  mov     rax, [rbx+28h]
0x1800064e6  jmp     short loc_1800064EA
0x1800064e8  xor     eax, eax
0x1800064ea  lea     r11, [rsp+88h+var_8]
0x1800064f2  mov     rbx, [r11+18h]
0x1800064f6  mov     rsi, [r11+20h]
0x1800064fa  mov     rsp, r11
0x1800064fd  pop     rdi
0x1800064fe  retn
```
