# ClasspDeviceWriteZeros

- ea: `0x140030604`
- end: `0x140030a17`
- name: `ClasspDeviceWriteZeros`
- size: `1043`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, int, PVOID BufferAddress, ULONG BufferLength)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140019de0`

## callees

- `0x14000de10`
- `0x140030604`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceWriteZeros(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        PVOID BufferAddress,
        ULONG BufferLength)
{
  bool v6; // zf
  char v7; // bp
  __int64 v8; // r13
  int v10; // eax
  int v12; // eax
  char v13; // r11
  __int64 i; // r10
  __int64 v15; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // r8
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // r8
  unsigned int v21; // edi
  __int64 v22; // r11
  char v23; // bl
  __int64 v24; // rcx
  unsigned __int64 v25; // r10
  __int64 v26; // r9
  int v27; // ecx
  int v28; // ecx
  __int64 v29; // rcx
  char v30; // r11
  __int64 j; // r10
  __int64 v32; // rcx
  unsigned __int64 v33; // r9
  __int64 v34; // r8
  int v35; // ecx
  int v36; // ecx
  char v37; // r11
  __int64 k; // r10
  __int64 v39; // rcx
  unsigned __int64 v40; // r9
  __int64 v41; // r8
  int v42; // ecx
  int v43; // ecx
  unsigned int v44; // r8d
  unsigned __int64 v45; // r10
  __int64 v46; // r9
  __int64 v47; // rcx

  v6 = *(_BYTE *)(a2 + 2) == 40;
  v7 = a4;
  v8 = *(_QWORD *)(a1 + 1144);
  v10 = *(_DWORD *)(a1 + 584);
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    *(_DWORD *)(a2 + 40) = v10;
    *(_WORD *)(a2 + 38) = 32;
  }
  else
  {
    *(_DWORD *)(a2 + 20) = v10;
    *(_BYTE *)(a2 + 9) = 32;
  }
  v12 = *(_DWORD *)(a1 + 592);
  if ( v6 )
  {
    v6 = *(_DWORD *)(a2 + 20) == 0;
    *(_DWORD *)(a2 + 24) = v12;
    if ( v6 )
    {
      v13 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v15 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v15 >= 0x80 )
        {
          v16 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v15 < (unsigned int)v16 )
          {
            v17 = (unsigned int)v15;
            v18 = *(_DWORD *)(v15 + a2) - 64;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                if ( v19 == 1 && v17 + 40 <= v16 )
                  break;
              }
              else if ( v17 + 56 <= v16 )
              {
                v13 = 1;
                *(_BYTE *)(v17 + a2 + 10) = 16;
              }
            }
            else if ( v17 + 40 <= v16 )
            {
              *(_BYTE *)(v17 + a2 + 10) = 16;
              break;
            }
            if ( v13 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(a2 + 12) = v12;
    *(_BYTE *)(a2 + 10) = 16;
  }
  if ( *(_BYTE *)(a2 + 2) != 40 )
  {
    v20 = a2 + 72;
    goto LABEL_45;
  }
  v20 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v21 = *(_DWORD *)(a2 + 56);
    if ( v21 )
    {
      v22 = 0;
      v23 = 0;
      do
      {
        v24 = *(unsigned int *)(a2 + 4 * v22 + 120);
        if ( (unsigned int)v24 >= 0x80 )
        {
          v25 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v24 < (unsigned int)v25 )
          {
            v26 = (unsigned int)v24;
            v27 = *(_DWORD *)(v24 + a2) - 64;
            if ( v27 )
            {
              v28 = v27 - 1;
              if ( v28 )
              {
                if ( v28 == 1 && v26 + 40 <= v25 )
                {
                  v29 = v26 + a2 + 32;
                  if ( !*(_DWORD *)(v26 + a2 + 12) )
                    v29 = v20;
                  v20 = v29;
                  break;
                }
              }
              else if ( v26 + 56 <= v25 )
              {
                if ( !*(_BYTE *)(v26 + a2 + 10) )
                  break;
                v23 = 1;
                v20 = v26 + a2 + 24;
              }
            }
            else if ( v26 + 40 <= v25 )
            {
              if ( *(_BYTE *)(v26 + a2 + 10) )
                v20 = v26 + a2 + 24;
              break;
            }
            if ( v23 )
              break;
          }
        }
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (unsigned int)v22 < v21 );
    }
  }
LABEL_45:
  *(_OWORD *)v20 = 0;
  if ( (*(_WORD *)(a1 + 640) & 0x20) != 0 )
  {
    *(_BYTE *)(v20 + 8) = BYTE1(a3);
    *(_BYTE *)(v20 + 7) = BYTE2(a3);
    *(_BYTE *)(v20 + 6) = BYTE3(a3);
    *(_BYTE *)(v20 + 5) = BYTE4(a3);
    *(_BYTE *)(v20 + 4) = BYTE5(a3);
    *(_BYTE *)(v20 + 3) = BYTE6(a3);
    *(_BYTE *)(v20 + 2) = HIBYTE(a3);
    *(_BYTE *)(v20 + 12) = BYTE1(a4);
    *(_BYTE *)(v20 + 11) = BYTE2(a4);
    *(_BYTE *)(v20 + 10) = HIBYTE(a4);
    *(_BYTE *)(v20 + 9) = a3;
    *(_BYTE *)(v20 + 13) = v7;
    *(_BYTE *)v20 = -118;
    if ( *(_BYTE *)(a2 + 2) == 40 )
    {
      if ( !*(_DWORD *)(a2 + 20) )
      {
        v30 = 0;
        for ( j = 0; (unsigned int)j < *(_DWORD *)(a2 + 56); j = (unsigned int)(j + 1) )
        {
          v32 = *(unsigned int *)(a2 + 4 * j + 120);
          if ( (unsigned int)v32 >= 0x80 )
          {
            v33 = *(unsigned int *)(a2 + 16);
            if ( (unsigned int)v32 < (unsigned int)v33 )
            {
              v34 = (unsigned int)v32;
              v35 = *(_DWORD *)(v32 + a2) - 64;
              if ( v35 )
              {
                v36 = v35 - 1;
                if ( v36 )
                {
                  if ( v36 == 1 && v34 + 40 <= v33 )
                    break;
                }
                else if ( v34 + 56 <= v33 )
                {
                  v30 = 1;
                  *(_BYTE *)(v34 + a2 + 10) = 16;
                }
              }
              else if ( v34 + 40 <= v33 )
              {
                *(_BYTE *)(v34 + a2 + 10) = 16;
                break;
              }
              if ( v30 )
                break;
            }
          }
        }
      }
    }
    else
    {
      *(_BYTE *)(a2 + 10) = 16;
    }
  }
  else
  {
    *(_BYTE *)(v20 + 2) = BYTE3(a3);
    *(_BYTE *)(v20 + 3) = BYTE2(a3);
    *(_BYTE *)(v20 + 4) = BYTE1(a3);
    *(_BYTE *)(v20 + 7) = BYTE1(a4);
    *(_BYTE *)(v20 + 5) = a3;
    *(_BYTE *)(v20 + 8) = v7;
    *(_BYTE *)v20 = 42;
    if ( *(_BYTE *)(a2 + 2) == 40 )
    {
      if ( !*(_DWORD *)(a2 + 20) )
      {
        v37 = 0;
        for ( k = 0; (unsigned int)k < *(_DWORD *)(a2 + 56); k = (unsigned int)(k + 1) )
        {
          v39 = *(unsigned int *)(a2 + 4 * k + 120);
          if ( (unsigned int)v39 >= 0x80 )
          {
            v40 = *(unsigned int *)(a2 + 16);
            if ( (unsigned int)v39 < (unsigned int)v40 )
            {
              v41 = (unsigned int)v39;
              v42 = *(_DWORD *)(v39 + a2) - 64;
              if ( v42 )
              {
                v43 = v42 - 1;
                if ( v43 )
                {
                  if ( v43 == 1 && v41 + 40 <= v40 )
                    break;
                }
                else if ( v41 + 56 <= v40 )
                {
                  v37 = 1;
                  *(_BYTE *)(v41 + a2 + 10) = 10;
                }
              }
              else if ( v41 + 40 <= v40 )
              {
                *(_BYTE *)(v41 + a2 + 10) = 10;
                break;
              }
              if ( v37 )
                break;
            }
          }
        }
      }
    }
    else
    {
      *(_BYTE *)(a2 + 10) = 10;
    }
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1152) + 16LL) & 0xF8000000) == 0xA0000000 )
  {
    v44 = 0;
    v45 = 0;
    while ( v44 < *(_DWORD *)(v8 + 628) )
    {
      v46 = *(_QWORD *)(v8 + 632);
      v47 = 16LL * v44;
      v45 += *(_QWORD *)(v47 + v46 + 8) * *(unsigned int *)(v47 + v46);
      if ( a3 * (unsigned __int64)*(unsigned int *)(a1 + 572) < v45 )
      {
        if ( *(_DWORD *)(v47 + v46 + 4) == 2 )
        {
          if ( *(_BYTE *)(a2 + 2) == 40 )
            *(_DWORD *)(a2 + 24) |= 0x1000u;
          else
            *(_DWORD *)(a2 + 12) |= 0x1000u;
        }
        return ClassSendSrbSynchronous(
                 *(PDEVICE_OBJECT *)(a1 + 8),
                 (PSCSI_REQUEST_BLOCK)a2,
                 BufferAddress,
                 BufferLength,
                 1u);
      }
      ++v44;
    }
  }
  return ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(a1 + 8), (PSCSI_REQUEST_BLOCK)a2, BufferAddress, BufferLength, 1u);
}

```

## disassembly

```asm
0x140030604  mov     rax, rsp
0x140030607  mov     [rax+8], rbx
0x14003060b  mov     [rax+10h], rbp
0x14003060f  mov     [rax+20h], r9d
0x140030613  mov     [rax+18h], r8
0x140030617  push    rsi
0x140030618  push    rdi
0x140030619  push    r13
0x14003061b  push    r14
0x14003061d  push    r15
0x14003061f  sub     rsp, 30h
0x140030623  cmp     byte ptr [rdx+2], 28h ; '('
0x140030627  mov     ebp, r9d
0x14003062a  mov     r13, [rcx+478h]
0x140030631  mov     r15, r8
0x140030634  mov     eax, [rcx+248h]
0x14003063a  mov     r14, rcx
0x14003063d  mov     esi, 20h ; ' '
0x140030642  jnz     short loc_14003064D
0x140030644  mov     [rdx+28h], eax
0x140030647  mov     [rdx+26h], si
0x14003064b  jmp     short loc_140030654
0x14003064d  mov     [rdx+14h], eax
0x140030650  mov     [rdx+9], sil
0x140030654  mov     eax, [rcx+250h]
0x14003065a  jnz     loc_1400306E0
0x140030660  cmp     dword ptr [rdx+14h], 0
0x140030664  mov     [rdx+18h], eax
0x140030667  jnz     short loc_1400306E7
0x140030669  xor     r11b, r11b
0x14003066c  xor     r10d, r10d
0x14003066f  cmp     [rdx+38h], r10d
0x140030673  jbe     short loc_1400306E7
0x140030675  mov     ecx, [rdx+r10*4+78h]
0x14003067a  cmp     ecx, 80h
0x140030680  jb      short loc_1400306CD
0x140030682  mov     r9d, [rdx+10h]
0x140030686  cmp     ecx, r9d
0x140030689  jnb     short loc_1400306CD
0x14003068b  mov     r8d, ecx
0x14003068e  mov     ecx, [rcx+rdx]
0x140030691  sub     ecx, 40h ; '@'
0x140030694  jz      short loc_1400306BF
0x140030696  sub     ecx, 1
0x140030699  jz      short loc_1400306AB
0x14003069b  cmp     ecx, 1
0x14003069e  jnz     short loc_1400306C8
0x1400306a0  lea     rcx, [r8+28h]
0x1400306a4  cmp     rcx, r9
0x1400306a7  jbe     short loc_1400306E7
0x1400306a9  jmp     short loc_1400306C8
0x1400306ab  lea     rcx, [r8+38h]
0x1400306af  cmp     rcx, r9
0x1400306b2  ja      short loc_1400306C8
0x1400306b4  mov     r11b, 1
0x1400306b7  mov     byte ptr [r8+rdx+0Ah], 10h
0x1400306bd  jmp     short loc_1400306C8
0x1400306bf  lea     rcx, [r8+28h]
0x1400306c3  cmp     rcx, r9
0x1400306c6  jbe     short loc_1400306D8
0x1400306c8  test    r11b, r11b
0x1400306cb  jnz     short loc_1400306E7
0x1400306cd  inc     r10d
0x1400306d0  cmp     r10d, [rdx+38h]
0x1400306d4  jb      short loc_140030675
0x1400306d6  jmp     short loc_1400306E7
0x1400306d8  mov     byte ptr [r8+rdx+0Ah], 10h
0x1400306de  jmp     short loc_1400306E7
0x1400306e0  mov     [rdx+0Ch], eax
0x1400306e3  mov     byte ptr [rdx+0Ah], 10h
0x1400306e7  cmp     byte ptr [rdx+2], 28h ; '('
0x1400306eb  jnz     loc_14003079C
0x1400306f1  xor     r8d, r8d
0x1400306f4  cmp     [rdx+14h], r8d
0x1400306f8  jnz     loc_1400307A0
0x1400306fe  mov     edi, [rdx+38h]
0x140030701  test    edi, edi
0x140030703  jz      loc_1400307A0
0x140030709  xor     r11d, r11d
0x14003070c  xor     bl, bl
0x14003070e  mov     ecx, [rdx+r11*4+78h]
0x140030713  cmp     ecx, 80h
0x140030719  jb      short loc_140030781
0x14003071b  mov     r10d, [rdx+10h]
0x14003071f  cmp     ecx, r10d
0x140030722  jnb     short loc_140030781
0x140030724  mov     r9d, ecx
0x140030727  mov     ecx, [rcx+rdx]
0x14003072a  sub     ecx, 40h ; '@'
0x14003072d  jz      short loc_140030774
0x14003072f  sub     ecx, 1
0x140030732  jz      short loc_140030758
0x140030734  cmp     ecx, 1
0x140030737  jnz     short loc_14003077D
0x140030739  lea     rcx, [r9+28h]
0x14003073d  cmp     rcx, r10
0x140030740  ja      short loc_14003077D
0x140030742  lea     rcx, [rdx+20h]
0x140030746  add     rcx, r9
0x140030749  cmp     dword ptr [r9+rdx+0Ch], 0
0x14003074f  cmovz   rcx, r8
0x140030753  mov     r8, rcx
0x140030756  jmp     short loc_1400307A0
0x140030758  lea     rcx, [r9+38h]
0x14003075c  cmp     rcx, r10
0x14003075f  ja      short loc_14003077D
0x140030761  cmp     byte ptr [r9+rdx+0Ah], 0
0x140030767  jbe     short loc_1400307A0
0x140030769  lea     r8, [rdx+18h]
0x14003076d  mov     bl, 1
0x14003076f  add     r8, r9
0x140030772  jmp     short loc_14003077D
0x140030774  lea     rcx, [r9+28h]
0x140030778  cmp     rcx, r10
0x14003077b  jbe     short loc_14003078B
0x14003077d  test    bl, bl
0x14003077f  jnz     short loc_1400307A0
0x140030781  inc     r11d
0x140030784  cmp     r11d, edi
0x140030787  jb      short loc_14003070E
0x140030789  jmp     short loc_1400307A0
0x14003078b  cmp     byte ptr [r9+rdx+0Ah], 0
0x140030791  jbe     short loc_1400307A0
0x140030793  lea     r8, [rdx+18h]
0x140030797  add     r8, r9
0x14003079a  jmp     short loc_1400307A0
0x14003079c  lea     r8, [rdx+48h]
0x1400307a0  xorps   xmm0, xmm0
0x1400307a3  movups  xmmword ptr [r8], xmm0
0x1400307a7  movzx   eax, word ptr [r14+280h]
0x1400307af  test    sil, al
0x1400307b2  jz      loc_1400308BA
0x1400307b8  mov     al, [rsp+58h+arg_11]
0x1400307bc  mov     [r8+8], al
0x1400307c0  mov     al, [rsp+58h+arg_12]
0x1400307c4  mov     [r8+7], al
0x1400307c8  mov     al, [rsp+58h+arg_13]
0x1400307cc  mov     [r8+6], al
0x1400307d0  mov     al, [rsp+58h+arg_14]
0x1400307d4  mov     [r8+5], al
0x1400307d8  mov     al, [rsp+58h+arg_15]
0x1400307dc  mov     [r8+4], al
0x1400307e0  mov     al, [rsp+58h+arg_16]
0x1400307e4  mov     [r8+3], al
0x1400307e8  mov     al, [rsp+58h+arg_17]
0x1400307ec  mov     [r8+2], al
0x1400307f0  mov     al, [rsp+58h+arg_19]
0x1400307f4  mov     [r8+0Ch], al
0x1400307f8  mov     al, [rsp+58h+arg_1A]
0x1400307fc  mov     [r8+0Bh], al
0x140030800  mov     al, [rsp+58h+arg_1B]
0x140030804  mov     [r8+0Ah], al
0x140030808  mov     [r8+9], r15b
0x14003080c  mov     [r8+0Dh], bpl
0x140030810  mov     byte ptr [r8], 8Ah
0x140030814  cmp     byte ptr [rdx+2], 28h ; '('
0x140030818  jnz     loc_1400308B1
0x14003081e  cmp     dword ptr [rdx+14h], 0
0x140030822  jnz     loc_14003096D
0x140030828  xor     r11b, r11b
0x14003082b  xor     r10d, r10d
0x14003082e  cmp     [rdx+38h], r10d
0x140030832  jbe     loc_14003096D
0x140030838  mov     ecx, [rdx+r10*4+78h]
0x14003083d  cmp     ecx, 80h
0x140030843  jb      short loc_140030898
0x140030845  mov     r9d, [rdx+10h]
0x140030849  cmp     ecx, r9d
0x14003084c  jnb     short loc_140030898
0x14003084e  mov     r8d, ecx
0x140030851  mov     ecx, [rcx+rdx]
0x140030854  sub     ecx, 40h ; '@'
0x140030857  jz      short loc_140030886
0x140030859  sub     ecx, 1
0x14003085c  jz      short loc_140030872
0x14003085e  cmp     ecx, 1
0x140030861  jnz     short loc_14003088F
0x140030863  lea     rcx, [r8+28h]
0x140030867  cmp     rcx, r9
0x14003086a  jbe     loc_14003096D
0x140030870  jmp     short loc_14003088F
0x140030872  lea     rcx, [r8+38h]
0x140030876  cmp     rcx, r9
0x140030879  ja      short loc_14003088F
0x14003087b  mov     r11b, 1
0x14003087e  mov     byte ptr [r8+rdx+0Ah], 10h
0x140030884  jmp     short loc_14003088F
0x140030886  lea     rcx, [r8+28h]
0x14003088a  cmp     rcx, r9
0x14003088d  jbe     short loc_1400308A6
0x14003088f  test    r11b, r11b
0x140030892  jnz     loc_14003096D
0x140030898  inc     r10d
0x14003089b  cmp     r10d, [rdx+38h]
0x14003089f  jb      short loc_140030838
0x1400308a1  jmp     loc_14003096D
0x1400308a6  mov     byte ptr [r8+rdx+0Ah], 10h
0x1400308ac  jmp     loc_14003096D
0x1400308b1  mov     byte ptr [rdx+0Ah], 10h
0x1400308b5  jmp     loc_14003096D
0x1400308ba  mov     al, [rsp+58h+arg_13]
0x1400308be  mov     [r8+2], al
0x1400308c2  mov     al, [rsp+58h+arg_12]
0x1400308c6  mov     [r8+3], al
0x1400308ca  mov     al, [rsp+58h+arg_11]
0x1400308ce  mov     [r8+4], al
0x1400308d2  mov     al, [rsp+58h+arg_19]
0x1400308d6  mov     [r8+7], al
0x1400308da  mov     [r8+5], r15b
0x1400308de  mov     [r8+8], bpl
0x1400308e2  mov     byte ptr [r8], 2Ah ; '*'
0x1400308e6  cmp     byte ptr [rdx+2], 28h ; '('
0x1400308ea  jnz     short loc_140030969
0x1400308ec  cmp     dword ptr [rdx+14h], 0
0x1400308f0  jnz     short loc_14003096D
0x1400308f2  xor     r11b, r11b
0x1400308f5  xor     r10d, r10d
0x1400308f8  cmp     [rdx+38h], r10d
0x1400308fc  jbe     short loc_14003096D
0x1400308fe  mov     ecx, [rdx+r10*4+78h]
0x140030903  cmp     ecx, 80h
0x140030909  jb      short loc_140030956
0x14003090b  mov     r9d, [rdx+10h]
0x14003090f  cmp     ecx, r9d
0x140030912  jnb     short loc_140030956
0x140030914  mov     r8d, ecx
0x140030917  mov     ecx, [rcx+rdx]
0x14003091a  sub     ecx, 40h ; '@'
0x14003091d  jz      short loc_140030948
0x14003091f  sub     ecx, 1
0x140030922  jz      short loc_140030934
0x140030924  cmp     ecx, 1
0x140030927  jnz     short loc_140030951
0x140030929  lea     rcx, [r8+28h]
0x14003092d  cmp     rcx, r9
0x140030930  jbe     short loc_14003096D
0x140030932  jmp     short loc_140030951
0x140030934  lea     rcx, [r8+38h]
0x140030938  cmp     rcx, r9
0x14003093b  ja      short loc_140030951
0x14003093d  mov     r11b, 1
0x140030940  mov     byte ptr [r8+rdx+0Ah], 0Ah
0x140030946  jmp     short loc_140030951
0x140030948  lea     rcx, [r8+28h]
0x14003094c  cmp     rcx, r9
0x14003094f  jbe     short loc_140030961
0x140030951  test    r11b, r11b
0x140030954  jnz     short loc_14003096D
0x140030956  inc     r10d
0x140030959  cmp     r10d, [rdx+38h]
0x14003095d  jb      short loc_1400308FE
0x14003095f  jmp     short loc_14003096D
0x140030961  mov     byte ptr [r8+rdx+0Ah], 0Ah
0x140030967  jmp     short loc_14003096D
0x140030969  mov     byte ptr [rdx+0Ah], 0Ah
0x14003096d  mov     rax, [r14+480h]
0x140030974  mov     ecx, [rax+10h]
0x140030977  and     ecx, 0F8000000h
0x14003097d  cmp     ecx, 0A0000000h
0x140030983  jnz     short loc_1400309E1
0x140030985  mov     r11d, [r13+274h]
0x14003098c  xor     r8d, r8d
0x14003098f  xor     r10d, r10d
0x140030992  cmp     r8d, r11d
0x140030995  jnb     short loc_1400309E1
0x140030997  mov     r9, [r13+278h]
0x14003099e  mov     ecx, r8d
0x1400309a1  shl     rcx, 4
0x1400309a5  mov     eax, [rcx+r9]
0x1400309a9  imul    rax, [rcx+r9+8]
0x1400309af  add     r10, rax
0x1400309b2  mov     eax, [r14+23Ch]
0x1400309b9  imul    rax, r15
0x1400309bd  cmp     rax, r10
0x1400309c0  jb      short loc_1400309C7
0x1400309c2  inc     r8d
0x1400309c5  jmp     short loc_140030992
0x1400309c7  cmp     dword ptr [rcx+r9+4], 2
0x1400309cd  jnz     short loc_1400309E1
0x1400309cf  cmp     byte ptr [rdx+2], 28h ; '('
0x1400309d3  jnz     short loc_1400309DC
0x1400309d5  bts     dword ptr [rdx+18h], 0Ch
0x1400309da  jmp     short loc_1400309E1
0x1400309dc  bts     dword ptr [rdx+0Ch], 0Ch
0x1400309e1  mov     r9d, [rsp+58h+BufferLength]; BufferLength
0x1400309e9  mov     r8, [rsp+58h+BufferAddress]; BufferAddress
0x1400309f1  mov     rcx, [r14+8]; DeviceObject
0x1400309f5  mov     [rsp+58h+WriteToDevice], 1; WriteToDevice
0x1400309fa  call    ClassSendSrbSynchronous
0x1400309ff  mov     rbx, [rsp+58h+arg_0]
0x140030a04  mov     rbp, [rsp+58h+arg_8]
0x140030a09  add     rsp, 30h
0x140030a0d  pop     r15
0x140030a0f  pop     r14
0x140030a11  pop     r13
0x140030a13  pop     rdi
0x140030a14  pop     rsi
0x140030a15  retn
```
