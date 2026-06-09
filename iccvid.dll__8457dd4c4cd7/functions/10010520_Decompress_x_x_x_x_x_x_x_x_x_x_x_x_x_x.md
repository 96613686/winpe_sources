# Decompress(x,x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x10010520`
- end: `0x100106a7`
- name: `_Decompress@56`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x10004142`
- `0x1000510e`
- `0x100101f2`
- `0x10010520`
- `0x100106ad`

## pseudocode

```c
int __fastcall Decompress(
        ULONG a1,
        int a2,
        int a3,
        char *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14)
{
  int result; // eax
  int v16; // ebx
  int v17; // edx
  unsigned int v18; // ecx
  void *v19; // ebx
  int v20; // ecx
  int v21; // [esp-14h] [ebp-2Ch]
  int v22; // [esp-10h] [ebp-28h]
  int v23; // [esp-Ch] [ebp-24h]
  int v24; // [esp+8h] [ebp-10h]
  int v26; // [esp+10h] [ebp-8h] BYREF
  unsigned int v27; // [esp+14h] [ebp-4h] BYREF

  if ( *(_DWORD *)(a1 + 92)
    || (result = DecompressBegin(a1, a1, a3, a1, a5, a6, a7, a8, a9, v21, v22, v23, a13, a14)) == 0 )
  {
    v16 = *(_DWORD *)(a9 + 4);
    if ( *(_DWORD *)(a1 + 144) != v16 || *(_DWORD *)(a1 + 148) != *(_DWORD *)(a9 + 8) )
    {
      *(_DWORD *)(a1 + 144) = v16;
      v17 = *(_DWORD *)(a9 + 8);
      *(_DWORD *)(a1 + 148) = v17;
      v18 = ((v16 * (unsigned int)*(unsigned __int16 *)(a9 + 14) + 31) >> 3) & 0x1FFFFFFC;
      *(_DWORD *)(a1 + 152) = v18;
      if ( v17 < 0 )
      {
        *(_DWORD *)(a1 + 156) = v18 * (-1 - v17);
      }
      else
      {
        *(_DWORD *)(a1 + 156) = 0;
        *(_DWORD *)(a1 + 152) = -v18;
      }
    }
    v24 = *(_DWORD *)(a1 + 152);
    v19 = (void *)(a10 + *(_DWORD *)(a1 + 156) + a11 * *(__int16 *)(a1 + 110) - v24 * (*(__int16 *)(a1 + 122) + a12 - 1));
    if ( !GetVideoFrameSize(a3, &v27) || !GetVideoFrameSize(a9, &v26) )
      return -100;
    if ( (a2 & 0x10000000) == 0 )
    {
      v20 = *(_DWORD *)(a1 + 92);
      if ( (*(_BYTE *)(a1 + 104) & 1) != 0 )
      {
        if ( !CVDecompress(
                v20,
                a4,
                v27,
                *(_DWORD *)(a1 + 132),
                *(_DWORD *)(a1 + 136),
                *(_DWORD *)(a1 + 132),
                *(_DWORD *)(a1 + 140)) )
          return -100;
        if ( a2 >= 0 )
          ButtHeadCopyBits(
            *(void **)(a1 + 132),
            *(_DWORD *)(a1 + 136),
            *(_DWORD *)(a1 + 140),
            v19,
            a10,
            v26,
            *(_DWORD *)(a1 + 152),
            *(_WORD *)(a1 + 110) * *(_WORD *)(a1 + 120),
            *(unsigned __int16 *)(a1 + 122));
      }
      else if ( !CVDecompress(v20, a4, v27, a10, v26, (int)v19, v24) )
      {
        return -100;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10010520  mov     edi, edi
0x10010522  push    ebp
0x10010523  mov     ebp, esp
0x10010525  sub     esp, 10h
0x10010528  push    esi
0x10010529  mov     esi, ecx
0x1001052b  mov     [ebp+var_C], edx
0x1001052e  push    edi
0x1001052f  mov     edi, [ebp+arg_18]
0x10010532  cmp     dword ptr [esi+5Ch], 0
0x10010536  jnz     short loc_1001055F
0x10010538  push    [ebp+arg_2C]
0x1001053b  push    [ebp+arg_28]
0x1001053e  sub     esp, 0Ch
0x10010541  push    edi
0x10010542  push    [ebp+arg_14]
0x10010545  push    [ebp+arg_10]
0x10010548  push    [ebp+arg_C]
0x1001054b  push    [ebp+arg_8]
0x1001054e  push    ecx
0x1001054f  push    [ebp+arg_0]
0x10010552  call    _DecompressBegin@56; DecompressBegin(x,x,x,x,x,x,x,x,x,x,x,x,x,x)
0x10010557  test    eax, eax
0x10010559  jnz     loc_1001063F
0x1001055f  push    ebx
0x10010560  mov     ebx, [edi+4]
0x10010563  cmp     [esi+90h], ebx
0x10010569  jnz     short loc_10010576
0x1001056b  mov     eax, [esi+94h]
0x10010571  cmp     eax, [edi+8]
0x10010574  jz      short loc_100105C4
0x10010576  mov     [esi+90h], ebx
0x1001057c  mov     edx, [edi+8]
0x1001057f  mov     [esi+94h], edx
0x10010585  movzx   ecx, word ptr [edi+0Eh]
0x10010589  imul    ecx, ebx
0x1001058c  add     ecx, 1Fh
0x1001058f  shr     ecx, 3
0x10010592  and     ecx, 1FFFFFFCh
0x10010598  mov     [esi+98h], ecx
0x1001059e  test    edx, edx
0x100105a0  js      short loc_100105B6
0x100105a2  neg     ecx
0x100105a4  mov     dword ptr [esi+9Ch], 0
0x100105ae  mov     [esi+98h], ecx
0x100105b4  jmp     short loc_100105C4
0x100105b6  or      eax, 0FFFFFFFFh
0x100105b9  sub     eax, edx
0x100105bb  imul    eax, ecx
0x100105be  mov     [esi+9Ch], eax
0x100105c4  mov     eax, [ebp+arg_24]
0x100105c7  movsx   ecx, word ptr [esi+7Ah]
0x100105cb  dec     eax
0x100105cc  mov     edx, [esi+98h]
0x100105d2  add     eax, ecx
0x100105d4  movsx   ebx, word ptr [esi+6Eh]
0x100105d8  imul    ebx, [ebp+arg_20]
0x100105dc  mov     ecx, [ebp+arg_0]
0x100105df  imul    eax, edx
0x100105e2  mov     [ebp+var_10], edx
0x100105e5  lea     edx, [ebp+var_4]
0x100105e8  sub     ebx, eax
0x100105ea  add     ebx, [esi+9Ch]
0x100105f0  add     ebx, [ebp+arg_1C]
0x100105f3  call    GetVideoFrameSize
0x100105f8  test    eax, eax
0x100105fa  jz      short loc_1001063B
0x100105fc  lea     edx, [ebp+var_8]
0x100105ff  mov     ecx, edi
0x10010601  call    GetVideoFrameSize
0x10010606  test    eax, eax
0x10010608  jz      short loc_1001063B
0x1001060a  mov     edi, [ebp+var_C]
0x1001060d  test    edi, 10000000h
0x10010613  jnz     loc_100106A3
0x10010619  test    byte ptr [esi+68h], 1
0x1001061d  mov     ecx, [esi+5Ch]
0x10010620  mov     edx, [ebp+arg_4]
0x10010623  jnz     short loc_10010645
0x10010625  push    [ebp+var_10]
0x10010628  push    ebx
0x10010629  push    [ebp+var_8]
0x1001062c  push    [ebp+arg_1C]
0x1001062f  push    [ebp+var_4]
0x10010632  call    _CVDecompress@28; CVDecompress(x,x,x,x,x,x,x)
0x10010637  test    eax, eax
0x10010639  jnz     short loc_100106A3
0x1001063b  push    0FFFFFF9Ch
0x1001063d  pop     eax
0x1001063e  pop     ebx
0x1001063f  pop     edi
0x10010640  pop     esi
0x10010641  leave
0x10010642  retn    30h ; '0'
0x10010645  push    dword ptr [esi+8Ch]
0x1001064b  mov     eax, [esi+84h]
0x10010651  push    eax
0x10010652  push    dword ptr [esi+88h]
0x10010658  push    eax
0x10010659  push    [ebp+var_4]
0x1001065c  call    _CVDecompress@28; CVDecompress(x,x,x,x,x,x,x)
0x10010661  test    eax, eax
0x10010663  jz      short loc_1001063B
0x10010665  test    edi, edi
0x10010667  js      short loc_100106A3
0x10010669  movzx   eax, word ptr [esi+7Ah]
0x1001066d  movzx   edx, word ptr [esi+78h]
0x10010671  push    eax; int
0x10010672  movzx   eax, word ptr [esi+6Eh]
0x10010676  mov     ecx, [esi+84h]; Src
0x1001067c  imul    edx, eax
0x1001067f  movzx   eax, dx
0x10010682  mov     edx, ecx
0x10010684  push    eax; __int16
0x10010685  push    dword ptr [esi+98h]; int
0x1001068b  push    [ebp+var_8]; int
0x1001068e  push    [ebp+arg_1C]; int
0x10010691  push    ebx; void *
0x10010692  push    dword ptr [esi+8Ch]; int
0x10010698  push    dword ptr [esi+88h]; int
0x1001069e  call    _ButtHeadCopyBits@40; ButtHeadCopyBits(x,x,x,x,x,x,x,x,x,x)
0x100106a3  xor     eax, eax
0x100106a5  jmp     short loc_1001063E
```
