# ICCompress

- ea: `0x1800026e0`
- end: `0x18000275e`
- name: `ICCompress`
- size: `126`
- prototype: `DWORD __cdecl(HIC hic, DWORD dwFlags, LPBITMAPINFOHEADER lpbiOutput, LPVOID lpData, LPBITMAPINFOHEADER lpbiInput, LPVOID lpBits, LPDWORD lpckid, LPDWORD lpdwFlags, LONG lFrameNum, DWORD dwFrameSize, DWORD dwQuality, LPBITMAPINFOHEADER lpbiPrev, LPVOID lpPrev)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005cf0`
- `0x1800063c0`

## callees

- `0x180003a60`

## pseudocode

```c
DWORD __cdecl ICCompress(
        HIC hic,
        DWORD dwFlags,
        LPBITMAPINFOHEADER lpbiOutput,
        LPVOID lpData,
        LPBITMAPINFOHEADER lpbiInput,
        LPVOID lpBits,
        LPDWORD lpckid,
        LPDWORD lpdwFlags,
        LONG lFrameNum,
        DWORD dwFrameSize,
        DWORD dwQuality,
        LPBITMAPINFOHEADER lpbiPrev,
        LPVOID lpPrev)
{
  DWORD_PTR dw1[7]; // [rsp+20h] [rbp-60h] BYREF
  LONG v15; // [rsp+58h] [rbp-28h]
  DWORD v16; // [rsp+5Ch] [rbp-24h]
  DWORD v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+64h] [rbp-1Ch]
  LPBITMAPINFOHEADER v19; // [rsp+68h] [rbp-18h]
  LPVOID v20; // [rsp+70h] [rbp-10h]

  dw1[0] = dwFlags;
  v18 = 0;
  dw1[3] = (DWORD_PTR)lpbiInput;
  dw1[4] = (DWORD_PTR)lpBits;
  dw1[5] = (DWORD_PTR)lpckid;
  dw1[6] = (DWORD_PTR)lpdwFlags;
  v15 = lFrameNum;
  v16 = dwFrameSize;
  v17 = dwQuality;
  v19 = lpbiPrev;
  dw1[1] = (DWORD_PTR)lpbiOutput;
  dw1[2] = (DWORD_PTR)lpData;
  v20 = lpPrev;
  return ICSendMessage(hic, 0x4008u, (DWORD_PTR)dw1, 0x58u);
}

```

## disassembly

```asm
0x1800026e0  push    rbp
0x1800026e2  mov     rbp, rsp
0x1800026e5  sub     rsp, 80h
0x1800026ec  xor     eax, eax
0x1800026ee  mov     dword ptr [rbp+dw1], edx
0x1800026f1  mov     dword ptr [rbp+dw1+4], eax
0x1800026f4  mov     edx, 4008h; msg
0x1800026f9  mov     [rbp+var_1C], eax
0x1800026fc  mov     rax, [rbp+lpbiInput]
0x180002700  mov     [rbp+var_48], rax
0x180002704  mov     rax, [rbp+lpBits]
0x180002708  mov     [rbp+var_40], rax
0x18000270c  mov     rax, [rbp+lpckid]
0x180002710  mov     [rbp+var_38], rax
0x180002714  mov     rax, [rbp+lpdwFlags]
0x180002718  mov     [rbp+var_30], rax
0x18000271c  mov     eax, [rbp+lFrameNum]
0x18000271f  mov     [rbp+var_28], eax
0x180002722  mov     eax, [rbp+dwFrameSize]
0x180002725  mov     [rbp+var_24], eax
0x180002728  mov     eax, [rbp+dwQuality]
0x18000272b  mov     [rbp+var_20], eax
0x18000272e  mov     rax, [rbp+lpbiPrev]
0x180002732  mov     [rbp+var_18], rax
0x180002736  mov     rax, [rbp+lpPrev]
0x18000273a  mov     [rbp+var_58], r8
0x18000273e  lea     r8, [rbp+dw1]; dw1
0x180002742  mov     [rbp+var_50], r9
0x180002746  mov     r9d, 58h ; 'X'; dw2
0x18000274c  mov     [rbp+var_10], rax
0x180002750  call    ICSendMessage
0x180002755  add     rsp, 80h
0x18000275c  pop     rbp
0x18000275d  retn
```
