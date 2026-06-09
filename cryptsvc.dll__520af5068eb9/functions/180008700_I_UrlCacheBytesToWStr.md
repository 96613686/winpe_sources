# I_UrlCacheBytesToWStr

- ea: `0x180008700`
- end: `0x1800088e6`
- name: `I_UrlCacheBytesToWStr`
- size: `486`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007af0`

## callees

- `0x180008700`

## pseudocode

```c
__int64 __fastcall I_UrlCacheBytesToWStr(__int64 a1, unsigned __int8 *a2, _WORD *a3)
{
  int v3; // r9d
  __int16 v4; // ax
  unsigned int v5; // ecx
  __int16 v6; // ax
  unsigned int v7; // ecx
  __int16 v8; // ax
  unsigned int v9; // ecx
  __int16 v10; // ax
  unsigned int v11; // ecx
  __int16 v12; // ax
  unsigned int v13; // ecx
  __int16 v14; // ax
  unsigned int v15; // ecx
  __int16 v16; // ax
  unsigned int v17; // ecx
  __int16 v18; // ax
  unsigned int v19; // ecx
  __int16 v20; // ax
  unsigned int v21; // ecx
  __int16 v22; // ax
  unsigned int v23; // ecx
  __int16 v24; // ax
  unsigned int v25; // ecx
  __int16 v26; // ax
  unsigned int v27; // ecx
  __int16 v28; // ax
  unsigned int v29; // ecx
  __int16 v30; // ax
  unsigned int v31; // ecx
  __int16 v32; // ax
  unsigned int v33; // ecx
  __int16 v34; // ax
  unsigned int v35; // ecx
  __int64 result; // rax

  v3 = 2;
  do
  {
    v4 = 48;
    v5 = *a2 >> 4;
    if ( v5 > 9 )
      v4 = 55;
    *a3 = v5 + v4;
    v6 = 48;
    v7 = *a2 & 0xF;
    if ( v7 > 9 )
      v6 = 55;
    a3[1] = v7 + v6;
    v8 = 48;
    v9 = a2[1] >> 4;
    if ( v9 > 9 )
      v8 = 55;
    a3[2] = v9 + v8;
    v10 = 48;
    v11 = a2[1] & 0xF;
    if ( v11 > 9 )
      v10 = 55;
    a3[3] = v11 + v10;
    v12 = 48;
    v13 = a2[2] >> 4;
    if ( v13 > 9 )
      v12 = 55;
    a3[4] = v13 + v12;
    v14 = 48;
    v15 = a2[2] & 0xF;
    if ( v15 > 9 )
      v14 = 55;
    a3[5] = v15 + v14;
    v16 = 48;
    v17 = a2[3] >> 4;
    if ( v17 > 9 )
      v16 = 55;
    a3[6] = v17 + v16;
    v18 = 48;
    v19 = a2[3] & 0xF;
    if ( v19 > 9 )
      v18 = 55;
    a3[7] = v19 + v18;
    v20 = 48;
    v21 = a2[4] >> 4;
    if ( v21 > 9 )
      v20 = 55;
    a3[8] = v21 + v20;
    v22 = 48;
    v23 = a2[4] & 0xF;
    if ( v23 > 9 )
      v22 = 55;
    a3[9] = v23 + v22;
    v24 = 48;
    v25 = a2[5] >> 4;
    if ( v25 > 9 )
      v24 = 55;
    a3[10] = v25 + v24;
    v26 = 48;
    v27 = a2[5] & 0xF;
    if ( v27 > 9 )
      v26 = 55;
    a3 += 16;
    a2 += 8;
    *(a3 - 5) = v27 + v26;
    v28 = 48;
    v29 = *(a2 - 2) >> 4;
    if ( v29 > 9 )
      v28 = 55;
    *(a3 - 4) = v29 + v28;
    v30 = 48;
    v31 = *(a2 - 2) & 0xF;
    if ( v31 > 9 )
      v30 = 55;
    *(a3 - 3) = v31 + v30;
    v32 = 48;
    v33 = *(a2 - 1) >> 4;
    if ( v33 > 9 )
      v32 = 55;
    *(a3 - 2) = v33 + v32;
    v34 = 48;
    v35 = *(a2 - 1) & 0xF;
    if ( v35 > 9 )
      v34 = 55;
    *(a3 - 1) = v35 + v34;
    --v3;
  }
  while ( v3 );
  result = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180008700  mov     r9d, 2
0x180008706  mov     r10d, 37h ; '7'
0x18000870c  nop     dword ptr [rax+00h]
0x180008710  movzx   ecx, byte ptr [rdx]
0x180008713  mov     eax, 30h ; '0'
0x180008718  shr     ecx, 4
0x18000871b  cmp     ecx, 9
0x18000871e  cmova   ax, r10w
0x180008723  add     ax, cx
0x180008726  mov     [r8], ax
0x18000872a  mov     eax, 30h ; '0'
0x18000872f  movzx   ecx, byte ptr [rdx]
0x180008732  and     ecx, 0Fh
0x180008735  cmp     ecx, 9
0x180008738  cmova   ax, r10w
0x18000873d  add     ax, cx
0x180008740  mov     [r8+2], ax
0x180008745  mov     eax, 30h ; '0'
0x18000874a  movzx   ecx, byte ptr [rdx+1]
0x18000874e  shr     ecx, 4
0x180008751  cmp     ecx, 9
0x180008754  cmova   ax, r10w
0x180008759  add     ax, cx
0x18000875c  mov     [r8+4], ax
0x180008761  mov     eax, 30h ; '0'
0x180008766  movzx   ecx, byte ptr [rdx+1]
0x18000876a  and     ecx, 0Fh
0x18000876d  cmp     ecx, 9
0x180008770  cmova   ax, r10w
0x180008775  add     ax, cx
0x180008778  mov     [r8+6], ax
0x18000877d  mov     eax, 30h ; '0'
0x180008782  movzx   ecx, byte ptr [rdx+2]
0x180008786  shr     ecx, 4
0x180008789  cmp     ecx, 9
0x18000878c  cmova   ax, r10w
0x180008791  add     ax, cx
0x180008794  mov     [r8+8], ax
0x180008799  mov     eax, 30h ; '0'
0x18000879e  movzx   ecx, byte ptr [rdx+2]
0x1800087a2  and     ecx, 0Fh
0x1800087a5  cmp     ecx, 9
0x1800087a8  cmova   ax, r10w
0x1800087ad  add     ax, cx
0x1800087b0  mov     [r8+0Ah], ax
0x1800087b5  mov     eax, 30h ; '0'
0x1800087ba  movzx   ecx, byte ptr [rdx+3]
0x1800087be  shr     ecx, 4
0x1800087c1  cmp     ecx, 9
0x1800087c4  cmova   ax, r10w
0x1800087c9  add     ax, cx
0x1800087cc  mov     [r8+0Ch], ax
0x1800087d1  mov     eax, 30h ; '0'
0x1800087d6  movzx   ecx, byte ptr [rdx+3]
0x1800087da  and     ecx, 0Fh
0x1800087dd  cmp     ecx, 9
0x1800087e0  cmova   ax, r10w
0x1800087e5  add     ax, cx
0x1800087e8  mov     [r8+0Eh], ax
0x1800087ed  mov     eax, 30h ; '0'
0x1800087f2  movzx   ecx, byte ptr [rdx+4]
0x1800087f6  shr     ecx, 4
0x1800087f9  cmp     ecx, 9
0x1800087fc  cmova   ax, r10w
0x180008801  add     ax, cx
0x180008804  mov     [r8+10h], ax
0x180008809  mov     eax, 30h ; '0'
0x18000880e  movzx   ecx, byte ptr [rdx+4]
0x180008812  and     ecx, 0Fh
0x180008815  cmp     ecx, 9
0x180008818  cmova   ax, r10w
0x18000881d  add     ax, cx
0x180008820  mov     [r8+12h], ax
0x180008825  mov     eax, 30h ; '0'
0x18000882a  movzx   ecx, byte ptr [rdx+5]
0x18000882e  shr     ecx, 4
0x180008831  cmp     ecx, 9
0x180008834  cmova   ax, r10w
0x180008839  add     ax, cx
0x18000883c  mov     [r8+14h], ax
0x180008841  mov     eax, 30h ; '0'
0x180008846  movzx   ecx, byte ptr [rdx+5]
0x18000884a  and     ecx, 0Fh
0x18000884d  cmp     ecx, 9
0x180008850  cmova   ax, r10w
0x180008855  lea     r8, [r8+20h]
0x180008859  add     ax, cx
0x18000885c  lea     rdx, [rdx+8]
0x180008860  mov     [r8-0Ah], ax
0x180008865  mov     eax, 30h ; '0'
0x18000886a  movzx   ecx, byte ptr [rdx-2]
0x18000886e  shr     ecx, 4
0x180008871  cmp     ecx, 9
0x180008874  cmova   ax, r10w
0x180008879  add     ax, cx
0x18000887c  mov     [r8-8], ax
0x180008881  mov     eax, 30h ; '0'
0x180008886  movzx   ecx, byte ptr [rdx-2]
0x18000888a  and     ecx, 0Fh
0x18000888d  cmp     ecx, 9
0x180008890  cmova   ax, r10w
0x180008895  add     ax, cx
0x180008898  mov     [r8-6], ax
0x18000889d  mov     eax, 30h ; '0'
0x1800088a2  movzx   ecx, byte ptr [rdx-1]
0x1800088a6  shr     ecx, 4
0x1800088a9  cmp     ecx, 9
0x1800088ac  cmova   ax, r10w
0x1800088b1  add     ax, cx
0x1800088b4  mov     [r8-4], ax
0x1800088b9  mov     eax, 30h ; '0'
0x1800088be  movzx   ecx, byte ptr [rdx-1]
0x1800088c2  and     ecx, 0Fh
0x1800088c5  cmp     ecx, 9
0x1800088c8  cmova   ax, r10w
0x1800088cd  add     ax, cx
0x1800088d0  mov     [r8-2], ax
0x1800088d5  add     r9d, 0FFFFFFFFh
0x1800088d9  jnz     loc_180008710
0x1800088df  xor     eax, eax
0x1800088e1  mov     [r8], ax
0x1800088e5  retn
```
