# LdrResGetRCConfig

- ea: `0x1800adfe0`
- end: `0x1800ae511`
- name: `LdrResGetRCConfig`
- size: `1329`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180075be0`
- `0x18007911c`
- `0x1800ab460`
- `0x1800ab4f0`
- `0x1800adc70`

## callees

- `0x18006f0d0`
- `0x180072d10`
- `0x180073550`
- `0x1800ab4f0`
- `0x1800adfe0`
- `0x1800ae518`
- `0x1800ae600`
- `0x1800af64c`
- `0x180162810`

## string_xrefs

- `0x1800ae074`: `LdrResGetRCConfig Exit`
- `0x1800ae061`: `LdrResGetRCConfig Enter`

## pseudocode

```c
__int64 __fastcall LdrResGetRCConfig(__int64 a1, __int64 a2, __int64 *a3, __int64 a4, char a5)
{
  unsigned int v5; // r10d
  __int64 *v6; // r13
  __int64 v7; // rdi
  _DWORD *SharedData; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r15
  __int64 v13; // rax
  int v14; // edi
  _DWORD *v15; // rax
  __int64 result; // rax
  __int64 v17; // rcx
  int v18; // r13d
  int v19; // r8d
  int v20; // eax
  __int64 v21; // rcx
  char v22; // al
  int v23; // r9d
  __int64 *v24; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-A8h]
  __int64 v26; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v30[2]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp-68h]
  __int64 v32; // [rsp+A8h] [rbp-60h]
  _QWORD v33[3]; // [rsp+B0h] [rbp-58h] BYREF

  v5 = a4;
  v25 = a4;
  v6 = a3;
  v31 = a3;
  v7 = a2;
  v27 = a2;
  v32 = a1;
  v33[0] = L"MUI";
  v33[1] = 1;
  v33[2] = 0;
  v28 = 0;
  v26 = a2;
  v24 = 0;
  v29[0] = 3145774;
  v29[1] = L"LdrResGetRCConfig Enter";
  v30[0] = 3014700;
  v30[1] = L"LdrResGetRCConfig Exit";
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
  {
    v10 = (unsigned __int64)NtCurrentPeb()->SharedData + 555;
    v11 = 2147353477;
  }
  else
  {
    v11 = 2147353477;
    v10 = 2147353477;
  }
  if ( (*(_BYTE *)v10 & 1) != 0 )
  {
    v12 = 2147353476;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v10, a2, a3, a4) )
      v17 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v17 = 2147353476;
    LdrpTraceLoadMUIDll(v29, *(unsigned __int8 *)v17);
    v5 = v25;
  }
  else
  {
    v12 = 2147353476;
  }
  if ( a1 )
  {
    if ( a5 )
    {
      v13 = LdrpGetFromMUIMemCache(a1, 0, 0, 8);
      v24 = (__int64 *)v13;
      if ( v13 == -1 )
      {
        v14 = -1073741686;
        goto LABEL_10;
      }
      if ( v13 )
      {
        v14 = 0;
        if ( v6 )
          *v6 = v13;
        goto LABEL_10;
      }
      v5 = v25;
    }
    v18 = v5 & 0x2000;
    if ( !v7 && (v5 & 0x2000) == 0 )
    {
      result = LdrpResGetMappingSize(a1, &v26, v5, 0);
      if ( (int)result < 0 )
        return result;
      LODWORD(v7) = v26;
      v27 = v26;
    }
    v19 = 4144;
    if ( v18 )
      v19 = 8240;
    v20 = LdrpResSearchResourceMappedFile(a1, v7, v19, (unsigned int)v33, 3, (__int64)&v24, (__int64)&v28, 0, 0);
    v14 = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -1073741701 )
      {
        v14 = -1073741686;
LABEL_77:
        a3 = 0;
        v24 = 0;
LABEL_78:
        if ( a5 )
        {
          v23 = -1;
          if ( a3 )
            v23 = (int)a3;
          LdrpSetAlternateResourceModuleHandle(a1, 0, 0, v23, 0, 2, v14, 0);
        }
        goto LABEL_10;
      }
      a3 = v24;
    }
    else
    {
      a3 = v24;
      if ( v18 )
        goto LABEL_82;
      a2 = *((unsigned int *)v24 + 1);
      v10 = v27 + (a1 & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (unsigned __int64)v24 + a2 > v10 )
      {
        v14 = -1073741701;
        goto LABEL_76;
      }
      v14 = -1073020925;
      v10 = *((unsigned int *)v24 + 17);
      a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 18));
      if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
      {
        v10 = *((unsigned int *)v24 + 19);
        a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 20));
        if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
        {
          v10 = *((unsigned int *)v24 + 21);
          a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 22));
          if ( (unsigned int)a4 >= (unsigned int)v10 && (unsigned int)a4 <= (unsigned int)a2 )
          {
            v10 = *((unsigned int *)v24 + 23);
            a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 24));
            if ( (unsigned int)a4 >= (unsigned int)v10 && (unsigned int)a4 <= (unsigned int)a2 )
            {
              v10 = *((unsigned int *)v24 + 25);
              a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 26));
              if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
              {
                v10 = *((unsigned int *)v24 + 27);
                a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 28));
                if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
                {
                  v10 = *((unsigned int *)v24 + 29);
                  a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 30));
                  if ( (unsigned int)a4 <= (unsigned int)a2 && (unsigned int)a4 >= (unsigned int)v10 )
                  {
                    v10 = *((unsigned int *)v24 + 31);
                    a4 = (unsigned int)(v10 + *((_DWORD *)v24 + 32));
                    if ( (unsigned int)a4 <= (unsigned int)a2
                      && (unsigned int)a4 >= (unsigned int)v10
                      && *(_DWORD *)v24 == -20054323
                      && a2 == v28
                      && *((_DWORD *)v24 + 2) == 0x10000 )
                    {
                      v21 = *((unsigned int *)v24 + 3);
                      if ( !(_DWORD)v21 || (unsigned __int8)CheckOneBitValidFlag(v21, 7, v24) )
                      {
                        if ( (unsigned __int8)CheckOneBitValidFlag((_DWORD)a3[2] & 0xFFFFFFCF, 3, a3) )
                        {
                          if ( (unsigned __int8)CheckOneBitValidFlag((unsigned int)a4 & 0xFFFFFFFC, 48, a3) )
                          {
                            if ( (a4 & 1) == 0
                              || (unsigned __int8)CheckOneBitValidFlag(*((unsigned int *)a3 + 6), 3, a3)
                              && ((v10 = *((unsigned int *)a3 + 5), !(_DWORD)v10)
                               || (v22 = CheckOneBitValidFlag(v10, 256, a3)) != 0) )
                            {
LABEL_82:
                              if ( v31 )
                                *v31 = a3;
                              v14 = 0;
                              goto LABEL_78;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_76:
    if ( v14 >= 0 )
      goto LABEL_78;
    goto LABEL_77;
  }
  v14 = -1073741811;
LABEL_10:
  v15 = NtCurrentPeb()->SharedData;
  if ( v15 && *v15 )
    v11 = (__int64)NtCurrentPeb()->SharedData + 555;
  if ( (*(_BYTE *)v11 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v10, a2, a3, a4) )
      v12 = (__int64)NtCurrentPeb()->SharedData + 554;
    LdrpTraceLoadMUIDll(v30, *(unsigned __int8 *)v12);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800adfe0  mov     r11, rsp
0x1800adfe3  push    rbx
0x1800adfe4  push    rsi
0x1800adfe5  push    rdi
0x1800adfe6  push    r12
0x1800adfe8  push    r13
0x1800adfea  push    r14
0x1800adfec  push    r15
0x1800adfee  sub     rsp, 0D0h
0x1800adff5  mov     rax, cs:__security_cookie
0x1800adffc  xor     rax, rsp
0x1800adfff  mov     [rsp+108h+var_40], rax
0x1800ae007  mov     r10d, r9d
0x1800ae00a  mov     [rsp+108h+var_A8], r9d
0x1800ae00f  mov     r13, r8
0x1800ae012  mov     [rsp+108h+var_68], r8
0x1800ae01a  mov     rdi, rdx
0x1800ae01d  mov     [rsp+108h+var_98], rdx
0x1800ae022  mov     r14, rcx
0x1800ae025  mov     [rsp+108h+var_60], rcx
0x1800ae02d  lea     rax, aMui; "MUI"
0x1800ae034  mov     [r11-58h], rax
0x1800ae038  mov     qword ptr [r11-50h], 1
0x1800ae040  xor     r12d, r12d
0x1800ae043  mov     [r11-48h], r12
0x1800ae047  mov     [rsp+108h+var_90], r12
0x1800ae04c  mov     [rsp+108h+var_A0], rdx
0x1800ae051  mov     [rsp+108h+var_B0], r12
0x1800ae056  mov     qword ptr [r11-88h], 30002Eh
0x1800ae061  lea     rax, aLdrresgetrccon_0; "LdrResGetRCConfig Enter"
0x1800ae068  mov     [r11-80h], rax
0x1800ae06c  mov     qword ptr [r11-78h], 2E002Ch
0x1800ae074  lea     rax, aLdrresgetrccon_1; "LdrResGetRCConfig Exit"
0x1800ae07b  mov     [r11-70h], rax
0x1800ae07f  mov     rax, gs:60h
0x1800ae088  mov     rcx, [rax+90h]
0x1800ae08f  test    rcx, rcx
0x1800ae092  jz      loc_1800AE16D
0x1800ae098  cmp     [rcx], r12d
0x1800ae09b  jz      loc_1800AE16D
0x1800ae0a1  mov     rax, gs:60h
0x1800ae0aa  mov     rcx, [rax+90h]
0x1800ae0b1  add     rcx, 22Bh
0x1800ae0b8  mov     ebx, 7FFE0385h
0x1800ae0bd  test    byte ptr [rcx], 1
0x1800ae0c0  jnz     loc_1800AE179
0x1800ae0c6  mov     r15d, 7FFE0384h
0x1800ae0cc  test    r14, r14
0x1800ae0cf  jz      loc_1800AE3C8
0x1800ae0d5  movzx   esi, [rsp+108h+arg_20]
0x1800ae0dd  test    sil, sil
0x1800ae0e0  jz      loc_1800AE1C2
0x1800ae0e6  xor     edx, edx
0x1800ae0e8  mov     r9d, 8
0x1800ae0ee  xor     r8d, r8d
0x1800ae0f1  mov     rcx, r14
0x1800ae0f4  call    LdrpGetFromMUIMemCache
0x1800ae0f9  mov     [rsp+108h+var_B0], rax
0x1800ae0fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ae102  jnz     loc_1800AE3AA
0x1800ae108  mov     edi, 0C000008Ah
0x1800ae10d  mov     rax, gs:60h
0x1800ae116  mov     rax, [rax+90h]
0x1800ae11d  test    rax, rax
0x1800ae120  jz      short loc_1800AE13E
0x1800ae122  cmp     dword ptr [rax], 0
0x1800ae125  jz      short loc_1800AE13E
0x1800ae127  mov     rax, gs:60h
0x1800ae130  mov     rbx, [rax+90h]
0x1800ae137  add     rbx, 22Bh
0x1800ae13e  test    byte ptr [rbx], 1
0x1800ae141  jnz     loc_1800AE3D2
0x1800ae147  mov     eax, edi
0x1800ae149  mov     rcx, [rsp+108h+var_40]
0x1800ae151  xor     rcx, rsp; StackCookie
0x1800ae154  call    __security_check_cookie
0x1800ae159  add     rsp, 0D0h
0x1800ae160  pop     r15
0x1800ae162  pop     r14
0x1800ae164  pop     r13
0x1800ae166  pop     r12
0x1800ae168  pop     rdi
0x1800ae169  pop     rsi
0x1800ae16a  pop     rbx
0x1800ae16b  retn
0x1800ae16d  mov     ebx, 7FFE0385h
0x1800ae172  mov     ecx, ebx
0x1800ae174  jmp     loc_1800AE0BD
0x1800ae179  call    RtlGetCurrentServiceSessionId
0x1800ae17e  mov     r15d, 7FFE0384h
0x1800ae184  test    eax, eax
0x1800ae186  jz      loc_1800AE408
0x1800ae18c  mov     rax, gs:60h
0x1800ae195  mov     rcx, [rax+90h]
0x1800ae19c  add     rcx, 22Ah
0x1800ae1a3  movzx   edx, byte ptr [rcx]
0x1800ae1a6  lea     rcx, [rsp+108h+var_88]
0x1800ae1ae  call    LdrpTraceLoadMUIDll
0x1800ae1b3  mov     r10d, [rsp+108h+var_A8]
0x1800ae1b8  jmp     loc_1800AE0CC
0x1800ae1bd  mov     r10d, [rsp+108h+var_A8]
0x1800ae1c2  mov     r13d, r10d
0x1800ae1c5  and     r13d, 2000h
0x1800ae1cc  test    rdi, rdi
0x1800ae1cf  jnz     short loc_1800AE1FB
0x1800ae1d1  test    r13d, r13d
0x1800ae1d4  jnz     short loc_1800AE1FB
0x1800ae1d6  xor     r9d, r9d
0x1800ae1d9  mov     r8d, r10d
0x1800ae1dc  lea     rdx, [rsp+108h+var_A0]
0x1800ae1e1  mov     rcx, r14
0x1800ae1e4  call    LdrpResGetMappingSize
0x1800ae1e9  test    eax, eax
0x1800ae1eb  js      loc_1800AE149
0x1800ae1f1  mov     rdi, [rsp+108h+var_A0]
0x1800ae1f6  mov     [rsp+108h+var_98], rdi
0x1800ae1fb  mov     eax, 2030h
0x1800ae200  mov     r8d, 1030h
0x1800ae206  test    r13d, r13d
0x1800ae209  cmovnz  r8d, eax
0x1800ae20d  mov     [rsp+108h+var_C8], r12
0x1800ae212  mov     [rsp+108h+var_D0], r12
0x1800ae217  lea     rax, [rsp+108h+var_90]
0x1800ae21c  mov     [rsp+108h+var_D8], rax
0x1800ae221  lea     rax, [rsp+108h+var_B0]
0x1800ae226  mov     [rsp+108h+var_E0], rax
0x1800ae22b  mov     [rsp+108h+var_E8], 3
0x1800ae233  lea     r9, [rsp+108h+var_58]
0x1800ae23b  mov     rdx, rdi
0x1800ae23e  mov     rcx, r14
0x1800ae241  call    LdrpResSearchResourceMappedFile
0x1800ae246  mov     edi, eax
0x1800ae248  test    eax, eax
0x1800ae24a  js      loc_1800AE4F7
0x1800ae250  mov     r8, [rsp+108h+var_B0]
0x1800ae255  test    r13d, r13d
0x1800ae258  jnz     loc_1800AE46B
0x1800ae25e  mov     edx, [r8+4]
0x1800ae262  mov     rcx, r14
0x1800ae265  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800ae269  add     rcx, [rsp+108h+var_98]
0x1800ae26e  lea     rax, [rdx+r8]
0x1800ae272  cmp     rax, rcx
0x1800ae275  ja      loc_1800AE410
0x1800ae27b  mov     edi, 0C00B0003h
0x1800ae280  mov     [rsp+108h+var_B8], edi
0x1800ae284  mov     ecx, [r8+44h]
0x1800ae288  mov     r9d, [r8+48h]
0x1800ae28c  add     r9d, ecx
0x1800ae28f  cmp     r9d, edx
0x1800ae292  ja      short loc_1800AE2D3
0x1800ae294  cmp     r9d, ecx
0x1800ae297  jb      short loc_1800AE2D3
0x1800ae299  mov     ecx, [r8+4Ch]
0x1800ae29d  mov     r9d, [r8+50h]
0x1800ae2a1  add     r9d, ecx
0x1800ae2a4  cmp     r9d, edx
0x1800ae2a7  ja      short loc_1800AE2D3
0x1800ae2a9  cmp     r9d, ecx
0x1800ae2ac  jb      short loc_1800AE2D3
0x1800ae2ae  mov     ecx, [r8+54h]
0x1800ae2b2  mov     r9d, [r8+58h]
0x1800ae2b6  add     r9d, ecx
0x1800ae2b9  cmp     r9d, ecx
0x1800ae2bc  jb      short loc_1800AE2D3
0x1800ae2be  cmp     r9d, edx
0x1800ae2c1  ja      short loc_1800AE2D3
0x1800ae2c3  mov     ecx, [r8+5Ch]
0x1800ae2c7  mov     r9d, [r8+60h]
0x1800ae2cb  add     r9d, ecx
0x1800ae2ce  cmp     r9d, ecx
0x1800ae2d1  jnb     short loc_1800AE2D8
0x1800ae2d3  jmp     loc_1800AE499
0x1800ae2d8  cmp     r9d, edx
0x1800ae2db  ja      short loc_1800AE2D3
0x1800ae2dd  mov     ecx, [r8+64h]
0x1800ae2e1  mov     r9d, [r8+68h]
0x1800ae2e5  add     r9d, ecx
0x1800ae2e8  cmp     r9d, edx
0x1800ae2eb  ja      short loc_1800AE2D3
0x1800ae2ed  cmp     r9d, ecx
0x1800ae2f0  jb      short loc_1800AE2D3
0x1800ae2f2  mov     ecx, [r8+6Ch]
0x1800ae2f6  mov     r9d, [r8+70h]
0x1800ae2fa  add     r9d, ecx
0x1800ae2fd  cmp     r9d, edx
0x1800ae300  ja      short loc_1800AE2D3
0x1800ae302  cmp     r9d, ecx
0x1800ae305  jb      short loc_1800AE2D3
0x1800ae307  mov     ecx, [r8+74h]
0x1800ae30b  mov     r9d, [r8+78h]
0x1800ae30f  add     r9d, ecx
0x1800ae312  cmp     r9d, edx
0x1800ae315  ja      short loc_1800AE2D3
0x1800ae317  cmp     r9d, ecx
0x1800ae31a  jb      short loc_1800AE2D3
0x1800ae31c  mov     ecx, [r8+7Ch]
0x1800ae320  mov     r9d, [r8+80h]
0x1800ae327  add     r9d, ecx
0x1800ae32a  cmp     r9d, edx
0x1800ae32d  ja      short loc_1800AE2D3
0x1800ae32f  cmp     r9d, ecx
0x1800ae332  jb      short loc_1800AE2D3
0x1800ae334  cmp     dword ptr [r8], 0FECDFECDh
0x1800ae33b  jnz     loc_1800AE43B
0x1800ae341  cmp     rdx, [rsp+108h+var_90]
0x1800ae346  jnz     loc_1800AE43B
0x1800ae34c  cmp     dword ptr [r8+8], 10000h
0x1800ae354  jnz     loc_1800AE43F
0x1800ae35a  mov     ecx, [r8+0Ch]
0x1800ae35e  test    ecx, ecx
0x1800ae360  jnz     loc_1800AE441
0x1800ae366  mov     r9d, [r8+10h]
0x1800ae36a  mov     ecx, r9d
0x1800ae36d  and     ecx, 0FFFFFFCFh
0x1800ae370  mov     edx, 3
0x1800ae375  call    CheckOneBitValidFlag
0x1800ae37a  test    al, al
0x1800ae37c  jz      loc_1800AE43D
0x1800ae382  mov     ecx, r9d
0x1800ae385  and     ecx, 0FFFFFFFCh
0x1800ae388  mov     edx, 30h ; '0'
0x1800ae38d  call    CheckOneBitValidFlag
0x1800ae392  test    al, al
0x1800ae394  jz      loc_1800AE43D
0x1800ae39a  test    r9b, 1
0x1800ae39e  jnz     short loc_1800AE41B
0x1800ae3a0  mov     [rsp+108h+var_B8], r12d
0x1800ae3a5  jmp     loc_1800AE46B
0x1800ae3aa  test    rax, rax
0x1800ae3ad  jz      loc_1800AE1BD
0x1800ae3b3  mov     edi, r12d
0x1800ae3b6  test    r13, r13
0x1800ae3b9  jz      loc_1800AE10D
0x1800ae3bf  mov     [r13+0], rax
0x1800ae3c3  jmp     loc_1800AE10D
0x1800ae3c8  mov     edi, 0C000000Dh
0x1800ae3cd  jmp     loc_1800AE10D
0x1800ae3d2  call    RtlGetCurrentServiceSessionId
0x1800ae3d7  test    eax, eax
0x1800ae3d9  jz      short loc_1800AE3F2
0x1800ae3db  mov     rax, gs:60h
0x1800ae3e4  mov     r15, [rax+90h]
0x1800ae3eb  add     r15, 22Ah
0x1800ae3f2  movzx   edx, byte ptr [r15]
0x1800ae3f6  lea     rcx, [rsp+108h+var_78]
0x1800ae3fe  call    LdrpTraceLoadMUIDll
0x1800ae403  jmp     loc_1800AE147
0x1800ae408  mov     rcx, r15
0x1800ae40b  jmp     loc_1800AE1A3
0x1800ae410  mov     edi, 0C000007Bh
0x1800ae415  mov     [rsp+108h+var_B8], edi
0x1800ae419  jmp     short loc_1800AE499
0x1800ae41b  mov     edx, 3
0x1800ae420  mov     ecx, [r8+18h]
0x1800ae424  call    CheckOneBitValidFlag
0x1800ae429  test    al, al
0x1800ae42b  jz      short loc_1800AE455
0x1800ae42d  mov     ecx, [r8+14h]
0x1800ae431  test    ecx, ecx
0x1800ae433  jz      loc_1800AE3A0
0x1800ae439  jmp     short loc_1800AE457
0x1800ae43b  jmp     short loc_1800AE499
0x1800ae43d  jmp     short loc_1800AE499
0x1800ae43f  jmp     short loc_1800AE499
0x1800ae441  mov     edx, 7
0x1800ae446  call    CheckOneBitValidFlag
0x1800ae44b  test    al, al
0x1800ae44d  jnz     loc_1800AE366
0x1800ae453  jmp     short loc_1800AE499
0x1800ae455  jmp     short loc_1800AE499
0x1800ae457  mov     edx, 100h
0x1800ae45c  call    CheckOneBitValidFlag
0x1800ae461  test    al, al
0x1800ae463  jnz     loc_1800AE3A0
0x1800ae469  jmp     short loc_1800AE499
0x1800ae46b  jmp     short loc_1800AE4E5
0x1800ae46d  mov     edi, eax
0x1800ae46f  mov     [rsp+108h+var_B8], eax
0x1800ae473  xor     r8d, r8d
0x1800ae476  mov     [rsp+108h+var_B0], r8
0x1800ae47b  xor     r12d, r12d
0x1800ae47e  mov     ebx, 7FFE0385h
0x1800ae483  mov     r15d, 7FFE0384h
0x1800ae489  movzx   esi, [rsp+108h+arg_20]
0x1800ae491  mov     r14, [rsp+108h+var_60]
0x1800ae499  test    edi, edi
0x1800ae49b  jns     short loc_1800AE4A5
0x1800ae49d  mov     r8, r12
0x1800ae4a0  mov     [rsp+108h+var_B0], r12
0x1800ae4a5  test    sil, sil
0x1800ae4a8  jz      loc_1800AE10D
0x1800ae4ae  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800ae4b5  test    r8, r8
0x1800ae4b8  cmovnz  r9, r8
0x1800ae4bc  mov     [rsp+108h+var_D0], r12
0x1800ae4c1  mov     dword ptr [rsp+108h+var_D8], edi
0x1800ae4c5  mov     dword ptr [rsp+108h+var_E0], 2
0x1800ae4cd  mov     word ptr [rsp+108h+var_E8], r12w
0x1800ae4d3  xor     r8d, r8d
  ... truncated ...
```
