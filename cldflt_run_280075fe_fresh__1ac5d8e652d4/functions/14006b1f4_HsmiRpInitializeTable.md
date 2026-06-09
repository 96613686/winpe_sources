# HsmiRpInitializeTable

- ea: `0x14006b1f4`
- end: `0x14006b720`
- name: `HsmiRpInitializeTable`
- size: `1324`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006ac24`
- `0x14006b728`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x14001e280`
- `0x14001e580`
- `0x14006a790`
- `0x14006b1f4`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14006b40e`
- `ntoskrnl!RtlComputeCrc32` at `0x14006b40e`

## pseudocode

```c
__int64 __fastcall HsmiRpInitializeTable(
        __int64 a1,
        int a2,
        const void *a3,
        unsigned __int16 a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rdi
  int v10; // eax
  unsigned int v11; // ebp
  unsigned int *v12; // r15
  __int64 v13; // rdx
  unsigned int v14; // ecx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  void *v20; // rcx
  unsigned int v21; // r8d
  unsigned __int16 v22; // cx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  int v31; // [rsp+68h] [rbp+10h] BYREF

  v6 = a5;
  v10 = *a6;
  if ( (unsigned __int16)v10 <= 4u )
    v11 = 0;
  else
    v11 = v10 - 4;
  *(_QWORD *)(a5 + 4) = 1884448070;
  v12 = (unsigned int *)(v6 + 12);
  *(_DWORD *)(v6 + 16) = 655360;
  *(_DWORD *)(v6 + 12) = 96;
  memset((void *)(v6 + 20), 0, 0x50u);
  if ( v11 < 0x18 )
  {
LABEL_62:
    v15 = -1073741789;
    goto LABEL_7;
  }
  if ( *(_WORD *)(v6 + 18) )
  {
    v13 = *v12;
    if ( ((v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= v11 )
    {
      v14 = (v13 + 3) & 0xFFFFFFFC;
      *v12 = v14;
      *(_DWORD *)(v6 + 20) = 65543;
      *(_DWORD *)(v6 + 24) = v14;
      *(_BYTE *)(v14 + v6 + 4) = 1;
      ++*v12;
      v15 = 0;
      goto LABEL_7;
    }
    goto LABEL_62;
  }
  v15 = -1073741811;
LABEL_7:
  HsmDbgBreakOnStatus(v15);
  if ( (v15 & 0x80000000) != 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v15;
    }
    v29 = 10;
    goto LABEL_53;
  }
  if ( v11 >= 0x18 )
  {
    if ( *(_WORD *)(v6 + 18) <= 1u )
    {
      v15 = -1073741811;
      goto LABEL_15;
    }
    if ( v11 >= 0x20 )
    {
      v16 = *v12;
      if ( ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v11 )
      {
        v17 = ((_DWORD)v16 + 3) & 0xFFFFFFFC;
        *v12 = v17;
        if ( *(_WORD *)(v6 + 28) )
          *(_WORD *)(v6 + 16) |= 1u;
        *(_DWORD *)(v6 + 28) = 262154;
        v15 = 0;
        *(_DWORD *)(v6 + 32) = v17;
        *(_DWORD *)(v17 + v6 + 4) = a2;
        *v12 += 4;
        goto LABEL_15;
      }
    }
  }
  v15 = -1073741789;
LABEL_15:
  HsmDbgBreakOnStatus(v15);
  if ( (v15 & 0x80000000) != 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v15;
    }
    v29 = 11;
    goto LABEL_53;
  }
  if ( v11 < 0x18 )
    goto LABEL_60;
  if ( *(_WORD *)(v6 + 18) <= 3u )
  {
    v15 = -1073741811;
    goto LABEL_26;
  }
  if ( v11 < 0x30 || (v18 = *v12, a4 + ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v11) )
  {
LABEL_60:
    v15 = -1073741789;
    goto LABEL_26;
  }
  if ( *(_WORD *)(v6 + 44) )
    *(_WORD *)(v6 + 16) |= 1u;
  v19 = (v18 + 3) & 0xFFFFFFFC;
  *v12 = v19;
  *(_WORD *)(v6 + 44) = 17;
  *(_WORD *)(v6 + 46) = a4;
  *(_DWORD *)(v6 + 48) = v19;
  if ( a3 )
  {
    v20 = (void *)(v6 + v19 + 4LL);
    if ( v20 != a3 )
      memmove(v20, a3, a4);
  }
  v15 = 0;
  *v12 += *(unsigned __int16 *)(v6 + 46);
LABEL_26:
  HsmDbgBreakOnStatus(v15);
  if ( (v15 & 0x80000000) != 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return v15;
    }
    v29 = 12;
    goto LABEL_53;
  }
  if ( (a2 & 0x10) == 0 )
  {
    if ( v11 >= 0x18 )
    {
      if ( *(_WORD *)(v6 + 18) <= 2u )
      {
        v15 = -1073741811;
        goto LABEL_40;
      }
      if ( v11 >= 0x28 )
      {
        v24 = *v12;
        if ( ((v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v11 )
        {
          v25 = ((_DWORD)v24 + 3) & 0xFFFFFFFC;
          *v12 = v25;
          if ( *(_WORD *)(v6 + 36) )
            *(_WORD *)(v6 + 16) |= 1u;
          v15 = 0;
          *(_DWORD *)(v6 + 36) = 524294;
          *(_DWORD *)(v6 + 40) = v25;
          *(_QWORD *)(v25 + v6 + 4) = a1;
          *v12 += 8;
LABEL_40:
          HsmDbgBreakOnStatus(v15);
          if ( (v15 & 0x80000000) != 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              return v15;
            }
            v29 = 13;
            goto LABEL_53;
          }
          if ( v11 >= 0x18 )
          {
            if ( *(_WORD *)(v6 + 18) <= 9u )
            {
              v15 = -1073741811;
              goto LABEL_48;
            }
            if ( v11 >= 0x60 )
            {
              v26 = *v12;
              if ( ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v11 )
              {
                v27 = ((_DWORD)v26 + 3) & 0xFFFFFFFC;
                *v12 = v27;
                if ( *(_WORD *)(v6 + 92) )
                  *(_WORD *)(v6 + 16) |= 1u;
                *(_DWORD *)(v6 + 92) = 262154;
                v15 = 0;
                *(_DWORD *)(v6 + 96) = v27;
                *(_DWORD *)(v27 + v6 + 4) = 0;
                *v12 += 4;
                goto LABEL_48;
              }
            }
          }
          v15 = -1073741789;
LABEL_48:
          HsmDbgBreakOnStatus(v15);
          if ( (v15 & 0x80000000) == 0 )
            goto LABEL_28;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return v15;
          }
          v29 = 14;
LABEL_53:
          WPP_SF_d(v28->AttachedDevice, v29, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, v15);
          return v15;
        }
      }
    }
    v15 = -1073741789;
    goto LABEL_40;
  }
LABEL_28:
  v21 = *v12;
  *(_WORD *)(v6 + 16) |= 2u;
  *(_DWORD *)(v6 + 8) = RtlComputeCrc32(0, (PUCHAR)(v6 + 12), v21 - 8);
  *(_DWORD *)v6 = *(_DWORD *)v6 & 0xFFFFFFF0 | 1;
  v22 = *(_WORD *)v12 + 4;
  *(_WORD *)(v6 + 2) = v22;
  v31 = v22;
  if ( (_Config & 2) != 0 )
  {
    HsmiRpCompressBuffer((UCHAR *)v6, &v31);
    v22 = v31;
  }
  *a6 = v22;
  return v15;
}

```

## disassembly

```asm
0x14006b1f4  mov     [rsp+arg_10], rbx
0x14006b1f9  mov     [rsp+arg_0], rcx
0x14006b1fe  push    rbp
0x14006b1ff  push    rsi
0x14006b200  push    rdi
0x14006b201  push    r12
0x14006b203  push    r13
0x14006b205  push    r14
0x14006b207  push    r15
0x14006b209  sub     rsp, 20h
0x14006b20d  mov     rax, [rsp+58h+arg_28]
0x14006b215  xor     r14d, r14d
0x14006b218  mov     rdi, [rsp+58h+arg_20]
0x14006b220  mov     rsi, r8
0x14006b223  mov     r12d, r9d
0x14006b226  mov     r13d, edx
0x14006b229  movzx   eax, word ptr [rax]
0x14006b22c  lea     ecx, [r14+4]
0x14006b230  cmp     ax, cx
0x14006b233  jbe     loc_14006B479
0x14006b239  mov     ebp, eax
0x14006b23b  sub     ebp, ecx
0x14006b23d  xor     edx, edx; Val
0x14006b23f  mov     qword ptr [rdi+4], 70526546h
0x14006b247  lea     r15, [rdi+0Ch]
0x14006b24b  mov     dword ptr [rdi+10h], 0A0000h
0x14006b252  lea     rcx, [rdi+14h]; void *
0x14006b256  mov     dword ptr [r15], 60h ; '`'
0x14006b25d  lea     r8d, [rdx+50h]; Size
0x14006b261  call    memset
0x14006b266  mov     r8d, 1
0x14006b26c  cmp     ebp, 18h
0x14006b26f  jb      loc_14006B61D
0x14006b275  mov     eax, r14d
0x14006b278  mov     r14d, 0C0000023h
0x14006b27e  cmp     ax, [rdi+12h]
0x14006b282  jnb     loc_14006B62B
0x14006b288  mov     edx, [r15]
0x14006b28b  mov     eax, ebp
0x14006b28d  lea     rcx, [rdx+3]
0x14006b291  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b295  add     rcx, r8
0x14006b298  cmp     rcx, rax
0x14006b29b  ja      loc_14006B623
0x14006b2a1  lea     eax, [rdx+3]
0x14006b2a4  and     eax, 0FFFFFFFCh
0x14006b2a7  mov     ecx, eax
0x14006b2a9  mov     [r15], ecx
0x14006b2ac  mov     dword ptr [rdi+14h], 10007h
0x14006b2b3  mov     [rdi+18h], ecx
0x14006b2b6  mov     [rax+rdi+4], r8b
0x14006b2bb  add     [r15], r8d
0x14006b2be  xor     ebx, ebx
0x14006b2c0  mov     ecx, ebx
0x14006b2c2  call    HsmDbgBreakOnStatus
0x14006b2c7  xor     r8d, r8d
0x14006b2ca  test    ebx, ebx
0x14006b2cc  js      loc_14006B5BB
0x14006b2d2  cmp     ebp, 18h
0x14006b2d5  jb      loc_14006B605
0x14006b2db  lea     r9d, [r8+1]
0x14006b2df  cmp     r9w, [rdi+12h]
0x14006b2e4  jnb     loc_14006B635
0x14006b2ea  cmp     ebp, 20h ; ' '
0x14006b2ed  jb      loc_14006B605
0x14006b2f3  mov     edx, [r15]
0x14006b2f6  lea     r10d, [r8+4]
0x14006b2fa  mov     eax, ebp
0x14006b2fc  lea     rcx, [rdx+3]
0x14006b300  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b304  add     rcx, r10
0x14006b307  cmp     rcx, rax
0x14006b30a  ja      loc_14006B605
0x14006b310  lea     eax, [rdx+3]
0x14006b313  and     eax, 0FFFFFFFCh
0x14006b316  mov     [r15], eax
0x14006b319  cmp     [rdi+1Ch], r8w
0x14006b31e  jz      short loc_14006B325
0x14006b320  or      [rdi+10h], r9w
0x14006b325  mov     dword ptr [rdi+1Ch], 4000Ah
0x14006b32c  mov     ebx, r8d
0x14006b32f  mov     [rdi+20h], eax
0x14006b332  mov     [rax+rdi+4], r13d
0x14006b337  add     [r15], r10d
0x14006b33a  mov     ecx, ebx
0x14006b33c  call    HsmDbgBreakOnStatus
0x14006b341  xor     r9d, r9d
0x14006b344  test    ebx, ebx
0x14006b346  js      loc_14006B63F
0x14006b34c  cmp     ebp, 18h
0x14006b34f  jb      loc_14006B60D
0x14006b355  lea     eax, [r9+3]
0x14006b359  cmp     ax, [rdi+12h]
0x14006b35d  jnb     loc_14006B67E
0x14006b363  cmp     ebp, 30h ; '0'
0x14006b366  jb      loc_14006B60D
0x14006b36c  mov     edx, [r15]
0x14006b36f  movzx   r8d, r12w; Size
0x14006b373  lea     rcx, [rax+rdx]
0x14006b377  mov     eax, ebp
0x14006b379  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b37d  add     rcx, r8
0x14006b380  cmp     rcx, rax
0x14006b383  ja      loc_14006B60D
0x14006b389  cmp     [rdi+2Ch], r9w
0x14006b38e  jnz     loc_14006B688
0x14006b394  lea     eax, [rdx+3]
0x14006b397  and     eax, 0FFFFFFFCh
0x14006b39a  mov     [r15], eax
0x14006b39d  mov     word ptr [rdi+2Ch], 11h
0x14006b3a3  mov     [rdi+2Eh], r8w
0x14006b3a8  mov     [rdi+30h], eax
0x14006b3ab  test    rsi, rsi
0x14006b3ae  jz      short loc_14006B3C9
0x14006b3b0  mov     ecx, eax
0x14006b3b2  add     rcx, 4
0x14006b3b6  add     rcx, rdi; void *
0x14006b3b9  cmp     rcx, rsi
0x14006b3bc  jz      short loc_14006B3C9
0x14006b3be  mov     rdx, rsi; Src
0x14006b3c1  call    memmove
0x14006b3c6  xor     r9d, r9d
0x14006b3c9  movzx   eax, word ptr [rdi+2Eh]
0x14006b3cd  mov     ebx, r9d
0x14006b3d0  add     [r15], eax
0x14006b3d3  mov     ecx, ebx
0x14006b3d5  call    HsmDbgBreakOnStatus
0x14006b3da  xor     r12d, r12d
0x14006b3dd  test    ebx, ebx
0x14006b3df  js      loc_14006B696
0x14006b3e5  lea     esi, [r12+2]
0x14006b3ea  lea     r8d, [r12+8]
0x14006b3ef  test    r13b, 10h
0x14006b3f3  jz      loc_14006B481
0x14006b3f9  lea     r13d, [r12+1]
0x14006b3fe  mov     r8d, [r15]
0x14006b401  mov     rdx, r15; Buffer
0x14006b404  or      [rdi+10h], si
0x14006b408  sub     r8d, 8; Length
0x14006b40c  xor     ecx, ecx; InitialCrc
0x14006b40e  call    cs:__imp_RtlComputeCrc32
0x14006b415  nop     dword ptr [rax+rax+00h]
0x14006b41a  mov     [rdi+8], eax
0x14006b41d  mov     eax, [rdi]
0x14006b41f  and     eax, 0FFFFFFF1h
0x14006b422  or      eax, r13d
0x14006b425  mov     [rdi], eax
0x14006b427  movzx   eax, word ptr [r15]
0x14006b42b  add     ax, 4
0x14006b42f  movzx   ecx, ax
0x14006b432  mov     [rdi+2], cx
0x14006b436  mov     edx, dword ptr cs:__Config
0x14006b43c  mov     [rsp+58h+arg_8], ecx
0x14006b440  test    sil, dl
0x14006b443  jz      short loc_14006B456
0x14006b445  lea     rdx, [rsp+58h+arg_8]
0x14006b44a  mov     rcx, rdi
0x14006b44d  call    HsmiRpCompressBuffer
0x14006b452  mov     ecx, [rsp+58h+arg_8]
0x14006b456  mov     rax, [rsp+58h+arg_28]
0x14006b45e  mov     [rax], cx
0x14006b461  mov     eax, ebx
0x14006b463  mov     rbx, [rsp+58h+arg_10]
0x14006b468  add     rsp, 20h
0x14006b46c  pop     r15
0x14006b46e  pop     r14
0x14006b470  pop     r13
0x14006b472  pop     r12
0x14006b474  pop     rdi
0x14006b475  pop     rsi
0x14006b476  pop     rbp
0x14006b477  retn
0x14006b479  mov     ebp, r14d
0x14006b47c  jmp     loc_14006B23D
0x14006b481  cmp     ebp, 18h
0x14006b484  jb      loc_14006B5F7
0x14006b48a  cmp     si, [rdi+12h]
0x14006b48e  jnb     loc_14006B6D5
0x14006b494  cmp     ebp, 28h ; '('
0x14006b497  jb      loc_14006B5F7
0x14006b49d  mov     edx, [r15]
0x14006b4a0  mov     eax, ebp
0x14006b4a2  lea     rcx, [rdx+3]
0x14006b4a6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b4aa  add     rcx, r8
0x14006b4ad  cmp     rcx, rax
0x14006b4b0  ja      loc_14006B5F7
0x14006b4b6  lea     eax, [rdx+3]
0x14006b4b9  mov     r13d, 1
0x14006b4bf  and     eax, 0FFFFFFFCh
0x14006b4c2  mov     [r15], eax
0x14006b4c5  cmp     [rdi+24h], r12w
0x14006b4ca  jz      short loc_14006B4D1
0x14006b4cc  or      [rdi+10h], r13w
0x14006b4d1  mov     rcx, [rsp+58h+arg_0]
0x14006b4d6  mov     ebx, r12d
0x14006b4d9  mov     dword ptr [rdi+24h], 80006h
0x14006b4e0  mov     [rdi+28h], eax
0x14006b4e3  mov     [rax+rdi+4], rcx
0x14006b4e8  add     [r15], r8d
0x14006b4eb  mov     ecx, ebx
0x14006b4ed  call    HsmDbgBreakOnStatus
0x14006b4f2  test    ebx, ebx
0x14006b4f4  js      loc_14006B6DF
0x14006b4fa  cmp     ebp, 18h
0x14006b4fd  jb      loc_14006B615
0x14006b503  mov     eax, 9
0x14006b508  cmp     ax, [rdi+12h]
0x14006b50c  jnb     loc_14006B716
0x14006b512  cmp     ebp, 60h ; '`'
0x14006b515  jb      loc_14006B615
0x14006b51b  mov     edx, [r15]
0x14006b51e  lea     r8d, [rax-5]
0x14006b522  mov     eax, ebp
0x14006b524  lea     rcx, [rdx+3]
0x14006b528  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14006b52c  add     rcx, r8
0x14006b52f  cmp     rcx, rax
0x14006b532  ja      loc_14006B615
0x14006b538  lea     eax, [rdx+3]
0x14006b53b  and     eax, 0FFFFFFFCh
0x14006b53e  mov     [r15], eax
0x14006b541  cmp     [rdi+5Ch], r12w
0x14006b546  jz      short loc_14006B54D
0x14006b548  or      [rdi+10h], r13w
0x14006b54d  mov     dword ptr [rdi+5Ch], 4000Ah
0x14006b554  mov     ebx, r12d
0x14006b557  mov     [rdi+60h], eax
0x14006b55a  mov     [rax+rdi+4], r12d
0x14006b55f  add     [r15], r8d
0x14006b562  mov     ecx, ebx
0x14006b564  call    HsmDbgBreakOnStatus
0x14006b569  test    ebx, ebx
0x14006b56b  jns     loc_14006B3FE
0x14006b571  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b578  lea     rax, WPP_GLOBAL_Control
0x14006b57f  cmp     rcx, rax
0x14006b582  jz      loc_14006B461
0x14006b588  mov     eax, [rcx+2Ch]
0x14006b58b  test    r13b, al
0x14006b58e  jz      loc_14006B461
0x14006b594  cmp     [rcx+29h], sil
0x14006b598  jb      loc_14006B461
0x14006b59e  mov     edx, 0Eh
0x14006b5a3  mov     rcx, [rcx+18h]
0x14006b5a7  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14006b5ae  mov     r9d, ebx
0x14006b5b1  call    WPP_SF_d
0x14006b5b6  jmp     loc_14006B461
0x14006b5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b5c2  lea     rax, WPP_GLOBAL_Control
0x14006b5c9  cmp     rcx, rax
0x14006b5cc  jz      loc_14006B461
0x14006b5d2  mov     eax, [rcx+2Ch]
0x14006b5d5  mov     r13d, 1
0x14006b5db  test    r13b, al
0x14006b5de  jz      loc_14006B461
0x14006b5e4  lea     esi, [r13+1]
0x14006b5e8  cmp     [rcx+29h], sil
0x14006b5ec  jb      loc_14006B461
0x14006b5f2  lea     edx, [rsi+8]
0x14006b5f5  jmp     short loc_14006B5A3
0x14006b5f7  mov     ebx, r14d
0x14006b5fa  mov     r13d, 1
0x14006b600  jmp     loc_14006B4EB
0x14006b605  mov     ebx, r14d
0x14006b608  jmp     loc_14006B33A
0x14006b60d  mov     ebx, r14d
0x14006b610  jmp     loc_14006B3D3
0x14006b615  mov     ebx, r14d
0x14006b618  jmp     loc_14006B562
0x14006b61d  mov     r14d, 0C0000023h
0x14006b623  mov     ebx, r14d
0x14006b626  jmp     loc_14006B2C0
0x14006b62b  mov     ebx, 0C000000Dh
0x14006b630  jmp     loc_14006B2C0
0x14006b635  mov     ebx, 0C000000Dh
0x14006b63a  jmp     loc_14006B33A
0x14006b63f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b646  lea     rax, WPP_GLOBAL_Control
0x14006b64d  cmp     rcx, rax
0x14006b650  jz      loc_14006B461
0x14006b656  mov     eax, [rcx+2Ch]
0x14006b659  mov     r13d, 1
0x14006b65f  test    r13b, al
0x14006b662  jz      loc_14006B461
0x14006b668  lea     esi, [r13+1]
0x14006b66c  cmp     [rcx+29h], sil
0x14006b670  jb      loc_14006B461
0x14006b676  lea     edx, [rsi+9]
0x14006b679  jmp     loc_14006B5A3
0x14006b67e  mov     ebx, 0C000000Dh
0x14006b683  jmp     loc_14006B3D3
0x14006b688  mov     eax, 1
0x14006b68d  or      [rdi+10h], ax
0x14006b691  jmp     loc_14006B394
0x14006b696  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b69d  lea     rax, WPP_GLOBAL_Control
0x14006b6a4  cmp     rcx, rax
0x14006b6a7  jz      loc_14006B461
  ... truncated ...
```
