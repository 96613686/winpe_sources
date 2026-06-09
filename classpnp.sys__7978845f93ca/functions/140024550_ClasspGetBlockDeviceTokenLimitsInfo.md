# ClasspGetBlockDeviceTokenLimitsInfo

- ea: `0x140024550`
- end: `0x140024c4f`
- name: `ClasspGetBlockDeviceTokenLimitsInfo`
- size: `1791`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400561c0`

## callees

- `0x14000de10`
- `0x14000f3e0`
- `0x14001fc38`
- `0x14002001c`
- `0x140024550`
- `0x140027e2c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400245e7`
- `ntoskrnl!ExAllocatePool2` at `0x140024640`
- `ntoskrnl!ExAllocatePool2` at `0x1400245e7`
- `ntoskrnl!ExAllocatePool2` at `0x140024640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024bcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024be7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024bcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024be7`

## pseudocode

```c
__int64 __fastcall ClasspGetBlockDeviceTokenLimitsInfo(__int64 a1)
{
  __int64 v1; // r15
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 Pool2; // rdi
  NTSTATUS v6; // esi
  _BYTE *v7; // rbp
  __int64 v8; // rax
  char v9; // al
  int v10; // ecx
  int v11; // ecx
  char v12; // r10
  unsigned int i; // r9d
  __int64 v14; // rcx
  unsigned __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // ecx
  _BYTE *v19; // r8
  unsigned int v20; // ebx
  unsigned int v21; // r10d
  char v22; // r11
  __int64 v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  _BYTE *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rcx
  _BYTE *v32; // rcx
  _BYTE *v33; // rcx
  _BYTE *v34; // rcx
  _DWORD *v35; // rax
  __int64 v36; // rbx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  unsigned __int16 v40; // [rsp+C0h] [rbp+8h]
  __int16 v41; // [rsp+C0h] [rbp+8h]
  __int16 v42; // [rsp+C8h] [rbp+10h]

  v1 = *(_QWORD *)(a1 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 211, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
  }
  v3 = *(_QWORD *)(v1 + 528);
  if ( !v3 || (v4 = 184, *(_BYTE *)(v3 + 30) != 1) )
    v4 = 88;
  Pool2 = ExAllocatePool2(64, v4, 1918067539);
  if ( Pool2 )
  {
    v7 = (_BYTE *)ExAllocatePool2(64, 255, 1884709715);
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 213, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
      }
      v6 = -1073741670;
      goto LABEL_102;
    }
    v8 = *(_QWORD *)(v1 + 528);
    if ( v8 && *(_BYTE *)(v8 + 30) == 1 )
    {
      if ( (int)InitializeStorageRequestBlock(Pool2) >= 0 )
      {
        v9 = *(_BYTE *)(Pool2 + 2);
        *(_DWORD *)(Pool2 + 20) = 0;
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 214, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
      }
    }
    v9 = 0;
    *(_BYTE *)(Pool2 + 2) = 0;
    *(_WORD *)Pool2 = 88;
LABEL_29:
    v10 = *(_DWORD *)(v1 + 584);
    if ( v9 == 40 )
    {
      *(_DWORD *)(Pool2 + 40) = v10;
      *(_DWORD *)(Pool2 + 32) = 255;
      *(_WORD *)(Pool2 + 38) = 32;
    }
    else
    {
      *(_DWORD *)(Pool2 + 20) = v10;
      *(_WORD *)(Pool2 + 8) = 8447;
    }
    v11 = *(_DWORD *)(v1 + 592);
    if ( v9 == 40 )
    {
      *(_DWORD *)(Pool2 + 24) = v11;
      if ( !*(_DWORD *)(Pool2 + 20) )
      {
        v12 = 0;
        for ( i = 0; i < *(_DWORD *)(Pool2 + 56); ++i )
        {
          v14 = *(unsigned int *)(Pool2 + 4LL * i + 120);
          if ( (unsigned int)v14 >= 0x80 )
          {
            v15 = *(unsigned int *)(Pool2 + 16);
            if ( (unsigned int)v14 < (unsigned int)v15 )
            {
              v16 = (unsigned int)v14;
              v17 = *(_DWORD *)(v14 + Pool2) - 64;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  if ( v18 == 1 && v16 + 40 <= v15 )
                    break;
                }
                else if ( v16 + 56 <= v15 )
                {
                  v12 = 1;
                  *(_BYTE *)(v16 + Pool2 + 10) = 6;
                }
              }
              else if ( v16 + 40 <= v15 )
              {
                *(_BYTE *)(v16 + Pool2 + 10) = 6;
                break;
              }
              if ( v12 )
                break;
            }
          }
        }
      }
    }
    else
    {
      *(_DWORD *)(Pool2 + 12) = v11;
      *(_BYTE *)(Pool2 + 10) = 6;
    }
    if ( *(_BYTE *)(Pool2 + 2) != 40 )
    {
      v19 = (_BYTE *)(Pool2 + 72);
      goto LABEL_73;
    }
    v19 = 0;
    if ( !*(_DWORD *)(Pool2 + 20) )
    {
      v20 = *(_DWORD *)(Pool2 + 56);
      if ( v20 )
      {
        v21 = 0;
        v22 = 0;
        do
        {
          v23 = *(unsigned int *)(Pool2 + 4LL * v21 + 120);
          if ( (unsigned int)v23 >= 0x80 )
          {
            v24 = *(unsigned int *)(Pool2 + 16);
            if ( (unsigned int)v23 < (unsigned int)v24 )
            {
              v25 = (unsigned int)v23;
              v26 = *(_DWORD *)(v23 + Pool2) - 64;
              if ( v26 )
              {
                v27 = v26 - 1;
                if ( v27 )
                {
                  if ( v27 == 1 && v25 + 40 <= v24 )
                  {
                    v28 = (_BYTE *)(v25 + Pool2 + 32);
                    if ( !*(_DWORD *)(v25 + Pool2 + 12) )
                      v28 = v19;
                    v19 = v28;
                    break;
                  }
                }
                else if ( v25 + 56 <= v24 )
                {
                  if ( !*(_BYTE *)(v25 + Pool2 + 10) )
                    break;
                  v22 = 1;
                  v19 = (_BYTE *)(v25 + Pool2 + 24);
                }
              }
              else if ( v25 + 40 <= v24 )
              {
                if ( *(_BYTE *)(v25 + Pool2 + 10) )
                  v19 = (_BYTE *)(v25 + Pool2 + 24);
                break;
              }
              if ( v22 )
                break;
            }
          }
          ++v21;
        }
        while ( v21 < v20 );
      }
    }
LABEL_73:
    v19[1] |= 1u;
    *v19 = 18;
    v19[2] = -113;
    v19[4] = -1;
    v6 = ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(v1 + 8), (PSCSI_REQUEST_BLOCK)Pool2, v7, 0xFFu, 0);
    v29 = 60;
    if ( *(_BYTE *)(Pool2 + 2) != 40 )
      v29 = 16;
    if ( v6 == -1073741764 )
    {
      if ( *(_DWORD *)(v29 + Pool2) < 0xFFu )
      {
        v6 = 0;
        goto LABEL_84;
      }
    }
    else if ( v6 >= 0 )
    {
LABEL_84:
      LOBYTE(v40) = v7[3];
      HIBYTE(v40) = v7[2];
      if ( v40 >= 0x24u )
      {
        HIBYTE(v41) = v7[4];
        LOBYTE(v41) = v7[5];
        if ( !v41 )
        {
          LOBYTE(v42) = v7[7];
          HIBYTE(v42) = v7[6];
          if ( v42 == 32 )
          {
            *(_DWORD *)(*(_QWORD *)(v1 + 1152) + 16LL) |= 8u;
            v30 = *(_QWORD *)(v1 + 1152);
            *(_BYTE *)(v30 + 133) = v7[14];
            *(_BYTE *)(v30 + 132) = v7[15];
            v31 = *(_BYTE **)(v1 + 1152);
            v31[139] = v7[16];
            v31[138] = v7[17];
            v31[137] = v7[18];
            v31[136] = v7[19];
            v32 = *(_BYTE **)(v1 + 1152);
            v32[143] = v7[20];
            v32[142] = v7[21];
            v32[141] = v7[22];
            v32[140] = v7[23];
            v33 = *(_BYTE **)(v1 + 1152);
            v33[151] = v7[24];
            v33[150] = v7[25];
            v33[149] = v7[26];
            v33[148] = v7[27];
            v33[147] = v7[28];
            v33[146] = v7[29];
            v33[145] = v7[30];
            v33[144] = v7[31];
            v34 = *(_BYTE **)(v1 + 1152);
            v34[159] = v7[32];
            v34[158] = v7[33];
            v34[157] = v7[34];
            v34[156] = v7[35];
            v34[155] = v7[36];
            v34[154] = v7[37];
            v34[153] = v7[38];
            v34[152] = v7[39];
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v35 = *(_DWORD **)(v1 + 520);
              v36 = *(_QWORD *)(v1 + 1152);
              WPP_SF_qsssDDDIIDDD(
                WPP_GLOBAL_Control->AttachedDevice,
                *(unsigned __int16 *)(v36 + 62),
                (_DWORD)v35 + v35[3],
                a1,
                (__int64)v35 + (unsigned int)v35[3],
                (__int64)v35 + (unsigned int)v35[4],
                (__int64)v35 + (unsigned int)v35[5],
                *(_WORD *)(v36 + 132),
                *(_DWORD *)(v36 + 136),
                *(_DWORD *)(v36 + 140),
                *(_QWORD *)(v36 + 144),
                *(_QWORD *)(v36 + 152),
                *(_WORD *)(v36 + 62),
                *(_DWORD *)(v36 + 68),
                *(_DWORD *)(v36 + 64));
            }
            goto LABEL_101;
          }
        }
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
LABEL_100:
          v6 = -1073740701;
          *(_DWORD *)(*(_QWORD *)(v1 + 1152) + 16LL) &= ~8u;
LABEL_101:
          ExFreePoolWithTag(v7, 0);
LABEL_102:
          ExFreePoolWithTag((PVOID)Pool2, 0);
          goto LABEL_103;
        }
        v38 = 217;
LABEL_99:
        WPP_SF_q(v37->AttachedDevice, v38, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
        goto LABEL_100;
      }
LABEL_95:
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_100;
      }
      v38 = 218;
      goto LABEL_99;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 215, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, v6);
    }
    goto LABEL_95;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 212, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1);
  }
  v6 = -1073741670;
LABEL_103:
  *(_DWORD *)(*(_QWORD *)(v1 + 1152) + 128LL) = v6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 219, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, a1, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140024550  mov     [rsp+arg_10], rbx
0x140024555  push    rbp
0x140024556  push    rsi
0x140024557  push    rdi
0x140024558  push    r12
0x14002455a  push    r13
0x14002455c  push    r14
0x14002455e  push    r15
0x140024560  sub     rsp, 80h
0x140024567  mov     r15, [rcx+40h]
0x14002456b  xor     esi, esi
0x14002456d  mov     r13d, esi
0x140024570  mov     [rsp+0B8h+arg_0], si
0x140024578  mov     [rsp+0B8h+arg_8], si
0x140024580  mov     r14, rcx
0x140024583  mov     rcx, cs:WPP_GLOBAL_Control
0x14002458a  lea     rbx, WPP_GLOBAL_Control
0x140024591  lea     r12, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140024598  cmp     rcx, rbx
0x14002459b  jz      short loc_1400245BE
0x14002459d  mov     eax, [rcx+2Ch]
0x1400245a0  test    al, 2
0x1400245a2  jz      short loc_1400245BE
0x1400245a4  cmp     byte ptr [rcx+29h], 5
0x1400245a8  jb      short loc_1400245BE
0x1400245aa  mov     rcx, [rcx+18h]
0x1400245ae  mov     edx, 0D3h
0x1400245b3  mov     r9, r14
0x1400245b6  mov     r8, r12
0x1400245b9  call    WPP_SF_q
0x1400245be  mov     rax, [r15+210h]
0x1400245c5  test    rax, rax
0x1400245c8  jz      short loc_1400245D5
0x1400245ca  cmp     byte ptr [rax+1Eh], 1
0x1400245ce  mov     edx, 0B8h
0x1400245d3  jz      short loc_1400245DA
0x1400245d5  mov     edx, 58h ; 'X'
0x1400245da  mov     ebp, 40h ; '@'
0x1400245df  mov     r8d, 72536353h
0x1400245e5  mov     ecx, ebp
0x1400245e7  call    cs:__imp_ExAllocatePool2
0x1400245ee  nop     dword ptr [rax+rax+00h]
0x1400245f3  mov     rdi, rax
0x1400245f6  test    rax, rax
0x1400245f9  jnz     short loc_140024632
0x1400245fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140024602  cmp     rcx, rbx
0x140024605  jz      short loc_140024628
0x140024607  mov     eax, [rcx+2Ch]
0x14002460a  test    al, 2
0x14002460c  jz      short loc_140024628
0x14002460e  cmp     byte ptr [rcx+29h], 2
0x140024612  jb      short loc_140024628
0x140024614  mov     rcx, [rcx+18h]
0x140024618  mov     edx, 0D4h
0x14002461d  mov     r9, r14
0x140024620  mov     r8, r12
0x140024623  call    WPP_SF_q
0x140024628  mov     esi, 0C000009Ah
0x14002462d  jmp     loc_140024BF3
0x140024632  mov     edx, 0FFh
0x140024637  mov     r8d, 70566353h
0x14002463d  mov     rcx, rbp
0x140024640  call    cs:__imp_ExAllocatePool2
0x140024647  nop     dword ptr [rax+rax+00h]
0x14002464c  mov     rbp, rax
0x14002464f  test    rax, rax
0x140024652  jnz     short loc_14002468B
0x140024654  mov     rcx, cs:WPP_GLOBAL_Control
0x14002465b  cmp     rcx, rbx
0x14002465e  jz      short loc_140024681
0x140024660  mov     eax, [rcx+2Ch]
0x140024663  test    al, 2
0x140024665  jz      short loc_140024681
0x140024667  cmp     byte ptr [rcx+29h], 2
0x14002466b  jb      short loc_140024681
0x14002466d  mov     rcx, [rcx+18h]
0x140024671  mov     edx, 0D5h
0x140024676  mov     r9, r14
0x140024679  mov     r8, r12
0x14002467c  call    WPP_SF_q
0x140024681  mov     esi, 0C000009Ah
0x140024686  jmp     loc_140024BE2
0x14002468b  mov     rax, [r15+210h]
0x140024692  test    rax, rax
0x140024695  jz      short loc_1400246F5
0x140024697  cmp     byte ptr [rax+1Eh], 1
0x14002469b  jnz     short loc_1400246F5
0x14002469d  mov     r9d, 1
0x1400246a3  movzx   edx, si
0x1400246a6  mov     r8d, 0B8h
0x1400246ac  mov     dword ptr [rsp+0B8h+WriteToDevice], 40h ; '@'
0x1400246b4  mov     rcx, rdi
0x1400246b7  call    InitializeStorageRequestBlock
0x1400246bc  test    eax, eax
0x1400246be  js      short loc_1400246C8
0x1400246c0  mov     al, [rdi+2]
0x1400246c3  mov     [rdi+14h], esi
0x1400246c6  jmp     short loc_140024701
0x1400246c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400246cf  cmp     rcx, rbx
0x1400246d2  jz      short loc_1400246F5
0x1400246d4  mov     eax, [rcx+2Ch]
0x1400246d7  test    al, 2
0x1400246d9  jz      short loc_1400246F5
0x1400246db  cmp     byte ptr [rcx+29h], 3
0x1400246df  jb      short loc_1400246F5
0x1400246e1  mov     rcx, [rcx+18h]
0x1400246e5  mov     edx, 0D6h
0x1400246ea  mov     r9, r14
0x1400246ed  mov     r8, r12
0x1400246f0  call    WPP_SF_q
0x1400246f5  mov     al, sil
0x1400246f8  mov     [rdi+2], sil
0x1400246fc  mov     word ptr [rdi], 58h ; 'X'
0x140024701  mov     ecx, [r15+248h]
0x140024708  mov     r12d, 20h ; ' '
0x14002470e  cmp     al, 28h ; '('
0x140024710  jnz     short loc_140024723
0x140024712  mov     [rdi+28h], ecx
0x140024715  mov     dword ptr [rdi+20h], 0FFh
0x14002471c  mov     [rdi+26h], r12w
0x140024721  jmp     short loc_14002472C
0x140024723  mov     [rdi+14h], ecx
0x140024726  mov     word ptr [rdi+8], 20FFh
0x14002472c  mov     ecx, [r15+250h]
0x140024733  jnz     short loc_1400247B2
0x140024735  mov     [rdi+18h], ecx
0x140024738  cmp     [rdi+14h], esi
0x14002473b  jnz     short loc_1400247B9
0x14002473d  mov     r10b, sil
0x140024740  mov     r9d, esi
0x140024743  cmp     [rdi+38h], esi
0x140024746  jbe     short loc_1400247B9
0x140024748  mov     eax, r9d
0x14002474b  mov     ecx, [rdi+rax*4+78h]
0x14002474f  cmp     ecx, 80h
0x140024755  jb      short loc_1400247A0
0x140024757  mov     r8d, [rdi+10h]
0x14002475b  cmp     ecx, r8d
0x14002475e  jnb     short loc_1400247A0
0x140024760  mov     edx, ecx
0x140024762  mov     ecx, [rcx+rdi]
0x140024765  sub     ecx, 40h ; '@'
0x140024768  jz      short loc_140024792
0x14002476a  sub     ecx, 1
0x14002476d  jz      short loc_14002477F
0x14002476f  cmp     ecx, 1
0x140024772  jnz     short loc_14002479B
0x140024774  lea     rcx, [rdx+28h]
0x140024778  cmp     rcx, r8
0x14002477b  jbe     short loc_1400247B9
0x14002477d  jmp     short loc_14002479B
0x14002477f  lea     rcx, [rdx+38h]
0x140024783  cmp     rcx, r8
0x140024786  ja      short loc_14002479B
0x140024788  mov     r10b, 1
0x14002478b  mov     byte ptr [rdx+rdi+0Ah], 6
0x140024790  jmp     short loc_14002479B
0x140024792  lea     rcx, [rdx+28h]
0x140024796  cmp     rcx, r8
0x140024799  jbe     short loc_1400247AB
0x14002479b  test    r10b, r10b
0x14002479e  jnz     short loc_1400247B9
0x1400247a0  inc     r9d
0x1400247a3  cmp     r9d, [rdi+38h]
0x1400247a7  jb      short loc_140024748
0x1400247a9  jmp     short loc_1400247B9
0x1400247ab  mov     byte ptr [rdx+rdi+0Ah], 6
0x1400247b0  jmp     short loc_1400247B9
0x1400247b2  mov     [rdi+0Ch], ecx
0x1400247b5  mov     byte ptr [rdi+0Ah], 6
0x1400247b9  cmp     byte ptr [rdi+2], 28h ; '('
0x1400247bd  jnz     loc_14002486D
0x1400247c3  mov     r8, rsi
0x1400247c6  cmp     [rdi+14h], esi
0x1400247c9  jnz     loc_140024871
0x1400247cf  mov     ebx, [rdi+38h]
0x1400247d2  test    ebx, ebx
0x1400247d4  jz      loc_140024871
0x1400247da  mov     r10d, esi
0x1400247dd  mov     r11b, sil
0x1400247e0  mov     eax, r10d
0x1400247e3  mov     ecx, [rdi+rax*4+78h]
0x1400247e7  cmp     ecx, 80h
0x1400247ed  jb      short loc_140024853
0x1400247ef  mov     r9d, [rdi+10h]
0x1400247f3  cmp     ecx, r9d
0x1400247f6  jnb     short loc_140024853
0x1400247f8  mov     edx, ecx
0x1400247fa  mov     ecx, [rcx+rdi]
0x1400247fd  sub     ecx, 40h ; '@'
0x140024800  jz      short loc_140024845
0x140024802  sub     ecx, 1
0x140024805  jz      short loc_140024829
0x140024807  cmp     ecx, 1
0x14002480a  jnz     short loc_14002484E
0x14002480c  lea     rcx, [rdx+28h]
0x140024810  cmp     rcx, r9
0x140024813  ja      short loc_14002484E
0x140024815  lea     rcx, [rdi+20h]
0x140024819  add     rcx, rdx
0x14002481c  cmp     [rdx+rdi+0Ch], esi
0x140024820  cmovz   rcx, r8
0x140024824  mov     r8, rcx
0x140024827  jmp     short loc_140024871
0x140024829  lea     rcx, [rdx+38h]
0x14002482d  cmp     rcx, r9
0x140024830  ja      short loc_14002484E
0x140024832  cmp     [rdx+rdi+0Ah], sil
0x140024837  jbe     short loc_140024871
0x140024839  lea     r8, [rdi+18h]
0x14002483d  mov     r11b, 1
0x140024840  add     r8, rdx
0x140024843  jmp     short loc_14002484E
0x140024845  lea     rcx, [rdx+28h]
0x140024849  cmp     rcx, r9
0x14002484c  jbe     short loc_14002485D
0x14002484e  test    r11b, r11b
0x140024851  jnz     short loc_140024871
0x140024853  inc     r10d
0x140024856  cmp     r10d, ebx
0x140024859  jb      short loc_1400247E0
0x14002485b  jmp     short loc_140024871
0x14002485d  cmp     [rdx+rdi+0Ah], sil
0x140024862  jbe     short loc_140024871
0x140024864  lea     r8, [rdi+18h]
0x140024868  add     r8, rdx
0x14002486b  jmp     short loc_140024871
0x14002486d  lea     r8, [rdi+48h]
0x140024871  or      byte ptr [r8+1], 1
0x140024876  mov     r9d, 0FFh; BufferLength
0x14002487c  mov     byte ptr [r8], 12h
0x140024880  mov     rdx, rdi; Srb
0x140024883  mov     byte ptr [r8+2], 8Fh
0x140024888  mov     byte ptr [r8+4], 0FFh
0x14002488d  mov     r8, rbp; BufferAddress
0x140024890  mov     rcx, [r15+8]; DeviceObject
0x140024894  mov     [rsp+0B8h+WriteToDevice], sil; WriteToDevice
0x140024899  call    ClassSendSrbSynchronous
0x14002489e  cmp     byte ptr [rdi+2], 28h ; '('
0x1400248a2  mov     esi, eax
0x1400248a4  mov     eax, 3Ch ; '<'
0x1400248a9  lea     ecx, [rax-2Ch]
0x1400248ac  cmovnz  eax, ecx
0x1400248af  xor     ebx, ebx
0x1400248b1  cmp     esi, 0C000003Ch
0x1400248b7  jnz     short loc_1400248C6
0x1400248b9  cmp     dword ptr [rax+rdi], 0FFh
0x1400248c0  jnb     short loc_1400248E9
0x1400248c2  mov     esi, ebx
0x1400248c4  jmp     short loc_1400248CA
0x1400248c6  test    esi, esi
0x1400248c8  js      short loc_1400248E9
0x1400248ca  mov     al, [rbp+2]
0x1400248cd  mov     byte ptr [rsp+0B8h+arg_0+1], al
0x1400248d4  mov     al, [rbp+3]
0x1400248d7  mov     byte ptr [rsp+0B8h+arg_0], al
0x1400248de  movzx   r13d, [rsp+0B8h+arg_0]
0x1400248e7  jmp     short loc_140024931
0x1400248e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248f0  lea     rax, WPP_GLOBAL_Control
0x1400248f7  cmp     rcx, rax
0x1400248fa  jz      loc_140024B82
0x140024900  mov     eax, [rcx+2Ch]
0x140024903  test    al, 2
0x140024905  jz      short loc_140024929
0x140024907  cmp     byte ptr [rcx+29h], 2
0x14002490b  jb      short loc_140024929
0x14002490d  mov     rcx, [rcx+18h]
0x140024911  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140024918  mov     edx, 0D7h
0x14002491d  mov     dword ptr [rsp+0B8h+WriteToDevice], esi
0x140024921  mov     r9, r14
0x140024924  call    WPP_SF_qD
0x140024929  test    esi, esi
0x14002492b  js      loc_140024B82
0x140024931  cmp     r13w, 24h ; '$'
0x140024936  jb      loc_140024B82
0x14002493c  mov     al, [rbp+4]
0x14002493f  mov     byte ptr [rsp+0B8h+arg_0+1], al
0x140024946  mov     al, [rbp+5]
0x140024949  mov     byte ptr [rsp+0B8h+arg_0], al
0x140024950  mov     al, [rbp+6]
0x140024953  mov     byte ptr [rsp+0B8h+arg_8+1], al
0x14002495a  mov     al, [rbp+7]
0x14002495d  mov     byte ptr [rsp+0B8h+arg_8], al
0x140024964  cmp     [rsp+0B8h+arg_0], bx
0x14002496c  jnz     loc_140024B5B
0x140024972  cmp     [rsp+0B8h+arg_8], r12w
0x14002497b  jnz     loc_140024B5B
0x140024981  mov     rax, [r15+480h]
0x140024988  or      dword ptr [rax+10h], 8
0x14002498c  mov     rcx, [r15+480h]
0x140024993  mov     al, [rbp+0Eh]
0x140024996  mov     [rcx+85h], al
0x14002499c  mov     al, [rbp+0Fh]
0x14002499f  mov     [rcx+84h], al
0x1400249a5  mov     rcx, [r15+480h]
0x1400249ac  mov     al, [rbp+10h]
  ... truncated ...
```
