# SoftwareCryptPiece

- ea: `0x140002784`
- end: `0x1400028e2`
- name: `SoftwareCryptPiece`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001430`

## callees

- `0x140002784`
- `0x14000292c`
- `0x1400029cc`

## import_xrefs

- `cng!BCryptDecrypt` at `0x140002842`
- `cng!BCryptDecrypt` at `0x140002842`
- `cng!BCryptEncrypt` at `0x140002850`
- `cng!BCryptEncrypt` at `0x140002850`

## pseudocode

```c
int __fastcall SoftwareCryptPiece(__int64 *a1)
{
  __int64 v2; // rax
  unsigned int v3; // ecx
  ULONG v4; // edi
  ULONG dwFlags; // esi
  void *v6; // rcx
  UCHAR *v7; // rdx
  __int64 v8; // rax
  UCHAR *pbIV; // [rsp+20h] [rbp-58h]
  ULONG cbIV; // [rsp+28h] [rbp-50h]
  UCHAR *pbOutput; // [rsp+30h] [rbp-48h]
  ULONG cbOutput; // [rsp+38h] [rbp-40h]
  ULONG pcbResult; // [rsp+80h] [rbp+8h] BYREF

  pcbResult = 0;
  v2 = *a1;
  v3 = *((_DWORD *)a1 + 8);
  v4 = *(_DWORD *)(v2 + 32);
  if ( v3 < 2 * v4 )
    dwFlags = *((_DWORD *)a1 + 21);
  else
    dwFlags = 0;
  if ( v3 < 2 * v4 )
    v4 = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_DDD(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_390e2dc370203258022970013e7d63eb_Traceguids,
      *((unsigned int *)a1 + 39),
      v4,
      v3);
  v6 = *(void **)(a1[1] + 16);
  v7 = (UCHAR *)a1[3];
  cbOutput = *((_DWORD *)a1 + 16);
  pbOutput = (UCHAR *)a1[7];
  cbIV = *((_DWORD *)a1 + 12);
  pbIV = (UCHAR *)a1[5];
  if ( *((_BYTE *)a1 + 16) )
    LODWORD(v8) = BCryptDecrypt(v6, v7, v4, 0, pbIV, cbIV, pbOutput, cbOutput, &pcbResult, dwFlags);
  else
    LODWORD(v8) = BCryptEncrypt(v6, v7, v4, 0, pbIV, cbIV, pbOutput, cbOutput, &pcbResult, dwFlags);
  *((_DWORD *)a1 + 22) = v8;
  if ( (int)v8 >= 0 )
  {
    *((_DWORD *)a1 + 8) -= v4;
    *((_DWORD *)a1 + 16) -= v4;
    a1[3] += v4;
    a1[7] += v4;
    LODWORD(v8) = pcbResult;
    *((_DWORD *)a1 + 20) += pcbResult;
    if ( dwFlags )
    {
      v8 = a1[1];
      *(_OWORD *)(v8 + 40) = 0;
    }
    if ( !*((_DWORD *)a1 + 8) )
      *((_DWORD *)a1 + 38) = 3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v8) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (v8 & 4) != 0 )
        LODWORD(v8) = WPP_SF_D(
                        (__int64)WPP_GLOBAL_Control->AttachedDevice,
                        0xBu,
                        (__int64)WPP_390e2dc370203258022970013e7d63eb_Traceguids,
                        *((_DWORD *)a1 + 39));
    }
  }
  else
  {
    *((_DWORD *)a1 + 38) = 3;
  }
  return v8;
}

```

## disassembly

```asm
0x140002784  mov     rax, rsp
0x140002787  push    rbx
0x140002788  push    rsi
0x140002789  push    rdi
0x14000278a  push    r14
0x14000278c  sub     rsp, 58h
0x140002790  mov     dword ptr [rax+8], 0
0x140002797  mov     rbx, rcx
0x14000279a  mov     rax, [rcx]
0x14000279d  mov     ecx, [rcx+20h]
0x1400027a0  mov     edi, [rax+20h]
0x1400027a3  lea     eax, [rdi+rdi]
0x1400027a6  cmp     ecx, eax
0x1400027a8  jb      short loc_1400027AE
0x1400027aa  xor     esi, esi
0x1400027ac  jmp     short loc_1400027B1
0x1400027ae  mov     esi, [rbx+54h]
0x1400027b1  mov     r10, cs:WPP_GLOBAL_Control
0x1400027b8  lea     r14, WPP_GLOBAL_Control
0x1400027bf  cmp     ecx, eax
0x1400027c1  cmovb   edi, ecx
0x1400027c4  cmp     r10, r14
0x1400027c7  jz      short loc_1400027F5
0x1400027c9  mov     eax, [r10+2Ch]
0x1400027cd  test    al, 4
0x1400027cf  jz      short loc_1400027F5
0x1400027d1  mov     r9d, [rbx+9Ch]
0x1400027d8  lea     r8, WPP_390e2dc370203258022970013e7d63eb_Traceguids
0x1400027df  mov     [rsp+78h+cbIV], ecx
0x1400027e3  mov     edx, 0Ah
0x1400027e8  mov     rcx, [r10+18h]
0x1400027ec  mov     dword ptr [rsp+78h+pbIV], edi
0x1400027f0  call    WPP_SF_DDD
0x1400027f5  mov     rax, [rbx+8]
0x1400027f9  mov     r8d, [rbx+40h]
0x1400027fd  mov     r9, [rbx+38h]
0x140002801  mov     r10d, [rbx+30h]
0x140002805  mov     rcx, [rax+10h]; hKey
0x140002809  lea     rax, [rsp+78h+arg_0]
0x140002811  mov     r11, [rbx+28h]
0x140002815  mov     rdx, [rbx+18h]; pbInput
0x140002819  mov     [rsp+78h+dwFlags], esi; dwFlags
0x14000281d  mov     [rsp+78h+pcbResult], rax; pcbResult
0x140002822  mov     [rsp+78h+cbOutput], r8d; cbOutput
0x140002827  mov     r8d, edi; cbInput
0x14000282a  mov     [rsp+78h+pbOutput], r9; pbOutput
0x14000282f  xor     r9d, r9d; pPaddingInfo
0x140002832  mov     [rsp+78h+cbIV], r10d; cbIV
0x140002837  mov     [rsp+78h+pbIV], r11; pbIV
0x14000283c  cmp     [rbx+10h], r9b
0x140002840  jz      short loc_140002850
0x140002842  call    cs:__imp_BCryptDecrypt
0x140002849  nop     dword ptr [rax+rax+00h]
0x14000284e  jmp     short loc_14000285C
0x140002850  call    cs:__imp_BCryptEncrypt
0x140002857  nop     dword ptr [rax+rax+00h]
0x14000285c  mov     [rbx+58h], eax
0x14000285f  test    eax, eax
0x140002861  jns     short loc_14000286F
0x140002863  mov     dword ptr [rbx+98h], 3
0x14000286d  jmp     short loc_1400028D7
0x14000286f  sub     [rbx+20h], edi
0x140002872  sub     [rbx+40h], edi
0x140002875  mov     eax, edi
0x140002877  add     [rbx+18h], rax
0x14000287b  add     [rbx+38h], rax
0x14000287f  mov     eax, [rsp+78h+arg_0]
0x140002886  add     [rbx+50h], eax
0x140002889  test    esi, esi
0x14000288b  jz      short loc_140002898
0x14000288d  mov     rax, [rbx+8]
0x140002891  xorps   xmm0, xmm0
0x140002894  movups  xmmword ptr [rax+28h], xmm0
0x140002898  cmp     dword ptr [rbx+20h], 0
0x14000289c  jnz     short loc_1400028A8
0x14000289e  mov     dword ptr [rbx+98h], 3
0x1400028a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028af  cmp     rcx, r14
0x1400028b2  jz      short loc_1400028D7
0x1400028b4  mov     eax, [rcx+2Ch]
0x1400028b7  test    al, 4
0x1400028b9  jz      short loc_1400028D7
0x1400028bb  mov     r9d, [rbx+9Ch]
0x1400028c2  lea     r8, WPP_390e2dc370203258022970013e7d63eb_Traceguids
0x1400028c9  mov     rcx, [rcx+18h]
0x1400028cd  mov     edx, 0Bh
0x1400028d2  call    WPP_SF_D
0x1400028d7  add     rsp, 58h
0x1400028db  pop     r14
0x1400028dd  pop     rdi
0x1400028de  pop     rsi
0x1400028df  pop     rbx
0x1400028e0  retn
```
