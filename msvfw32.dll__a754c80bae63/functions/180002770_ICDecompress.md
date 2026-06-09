# ICDecompress

- ea: `0x180002770`
- end: `0x1800027c2`
- name: `ICDecompress`
- size: `82`
- prototype: `DWORD __cdecl(HIC hic, DWORD dwFlags, LPBITMAPINFOHEADER lpbiFormat, LPVOID lpData, LPBITMAPINFOHEADER lpbi, LPVOID lpBits)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`
- `0x1800063c0`
- `0x180009bb0`

## callees

- `0x180003a60`

## pseudocode

```c
DWORD __cdecl ICDecompress(
        HIC hic,
        DWORD dwFlags,
        LPBITMAPINFOHEADER lpbiFormat,
        LPVOID lpData,
        LPBITMAPINFOHEADER lpbi,
        LPVOID lpBits)
{
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  LPBITMAPINFOHEADER v8; // [rsp+28h] [rbp-30h]
  LPVOID v9; // [rsp+30h] [rbp-28h]
  LPBITMAPINFOHEADER v10; // [rsp+38h] [rbp-20h]
  LPVOID v11; // [rsp+40h] [rbp-18h]
  int v12; // [rsp+48h] [rbp-10h]

  v7[0] = dwFlags;
  v7[1] = 0;
  v10 = lpbi;
  v8 = lpbiFormat;
  v9 = lpData;
  v11 = lpBits;
  v12 = 0;
  return ICSendMessage(hic, 0x400Du, (DWORD_PTR)v7, 0x30u);
}

```

## disassembly

```asm
0x180002770  mov     r11, rsp
0x180002773  sub     rsp, 58h
0x180002777  mov     [rsp+58h+var_38], edx
0x18000277b  xor     eax, eax
0x18000277d  mov     [rsp+58h+var_34], eax
0x180002781  mov     edx, 400Dh; msg
0x180002786  mov     rax, [rsp+58h+lpbi]
0x18000278e  mov     [r11-20h], rax
0x180002792  mov     rax, [rsp+58h+lpBits]
0x18000279a  mov     [r11-30h], r8
0x18000279e  lea     r8, [r11-38h]; dw1
0x1800027a2  mov     [r11-28h], r9
0x1800027a6  mov     r9d, 30h ; '0'; dw2
0x1800027ac  mov     [r11-18h], rax
0x1800027b0  mov     [rsp+58h+var_10], 0
0x1800027b8  call    ICSendMessage
0x1800027bd  add     rsp, 58h
0x1800027c1  retn
```
