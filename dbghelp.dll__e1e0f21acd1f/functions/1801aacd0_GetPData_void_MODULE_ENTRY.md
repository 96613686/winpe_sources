# GetPData(void *,_MODULE_ENTRY *)

- ea: `0x1801aacd0`
- end: `0x1801ab3c4`
- name: `?GetPData@@YAHPEAXPEAU_MODULE_ENTRY@@@Z`
- size: `1780`
- prototype: `int(void *, struct _MODULE_ENTRY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000d35c`
- `0x1800233f8`

## callees

- `0x1800089f0`
- `0x18000a820`
- `0x180010440`
- `0x180015f04`
- `0x1800238d8`
- `0x180190f48`
- `0x1801aacd0`
- `0x1801aba9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aadb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aadb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ab3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ab3a3`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801ab369`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801ab369`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801aaf62`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801aaf62`

## pseudocode

```c
_BOOL8 __fastcall GetPData(void *a1, struct _MODULE_ENTRY *a2)
{
  bool v2; // zf
  unsigned __int64 v5; // r14
  __int64 v6; // r15
  _DWORD *v7; // rbx
  void *v8; // r13
  unsigned __int64 v9; // rcx
  DWORD v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // r9
  _DWORD *v18; // rax
  unsigned int v19; // ecx
  _DWORD *v20; // rax
  _DWORD *v21; // rsi
  DWORD v22; // eax
  DWORD v23; // ecx
  int v24; // edx
  unsigned int v25; // eax
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  int v29; // ecx
  DWORD v30; // eax
  DWORD v31; // ecx
  int v32; // edx
  unsigned int v33; // eax
  __int64 v34; // rax
  int v35; // ecx
  unsigned int v36; // ecx
  __int128 v37; // [rsp+40h] [rbp-10h] BYREF
  DWORD flOldProtect; // [rsp+98h] [rbp+48h] BYREF
  HANDLE FileW; // [rsp+A0h] [rbp+50h]
  SIZE_T dwSize; // [rsp+A8h] [rbp+58h]

  v2 = *((_QWORD *)a2 + 310) == 0;
  v37 = 0;
  flOldProtect = 0;
  if ( !v2 )
    return 1;
  if ( !(unsigned int)LoadSymbols(a1, a2, 0) )
    return 0;
  LODWORD(v5) = 0;
  if ( *((_QWORD *)a2 + 2434) )
  {
    v6 = *((_QWORD *)a2 + 311);
    v7 = (_DWORD *)((char *)a2 + 19436);
    FileW = 0;
    v8 = 0;
    if ( v6 && *v7 == 5 )
      goto LABEL_7;
    if ( (unsigned int)diaGetPData(a2) )
    {
      v6 = *((_QWORD *)a2 + 311);
LABEL_7:
      v9 = *((unsigned int *)a2 + 629);
      goto LABEL_21;
    }
  }
  v7 = (_DWORD *)((char *)a2 + 19436);
  if ( !*((_DWORD *)a2 + 4859) )
    return 0;
  ToggleFailCriticalErrors(0);
  v10 = 3;
  if ( dword_1802AF874 == 2 )
    v10 = 7;
  FileW = CreateFileW(*((LPCWSTR *)a2 + 39), 0x80000000, v10, 0, 3u, 0, 0);
  v8 = FileW;
  ToggleFailCriticalErrors(1);
  if ( v8 == (void *)-1LL )
    return 0;
  v37 = *(_OWORD *)MapItRO(&v37, v8);
  if ( !(_QWORD)v37 )
    goto LABEL_79;
  if ( *(_WORD *)v37 != 23117 )
  {
    if ( *(_WORD *)v37 == 18756 )
    {
      v13 = *(unsigned int *)(v37 + 28);
      v14 = (*(unsigned int *)(v37 + 32) * (unsigned __int128)0x2492492492492493uLL) >> 64;
      v15 = *(unsigned int *)(v37 + 24);
      v16 = *(unsigned int *)(v37 + 32) - v14;
      flOldProtect = 0;
      v17 = (v14 + (v16 >> 1)) >> 4;
      v18 = (_DWORD *)(v37 + v13 + 8 * (5 * v15 + 6));
      v19 = 0;
      while ( v19 < (unsigned int)v17 )
      {
        if ( v18[3] == 5 )
        {
          v6 = v37 + (unsigned int)v18[6];
          LODWORD(v5) = v18[4] / 0xCu;
          goto LABEL_37;
        }
        flOldProtect = ++v19;
        v18 += 7;
      }
    }
    goto LABEL_79;
  }
  v11 = *(int *)(v37 + 60);
  if ( *(_WORD *)(v11 + v37 + 24) == 267 )
  {
    v12 = *(unsigned int *)(v11 + v37 + 144);
    v9 = *(unsigned int *)(v11 + v37 + 148);
  }
  else
  {
    if ( *(_WORD *)(v11 + v37 + 24) != 523 )
      goto LABEL_79;
    v12 = *(unsigned int *)(v11 + v37 + 160);
    v9 = *(unsigned int *)(v11 + v37 + 164);
  }
  v6 = v37 + v12;
LABEL_21:
  if ( (_DWORD)v9 )
  {
    if ( *((_WORD *)a2 + 22) == 448
      || *((_WORD *)a2 + 22) == 450
      || *((_WORD *)a2 + 22) == 452
      || *((_WORD *)a2 + 22) == 498 )
    {
      LODWORD(v5) = (unsigned int)v9 >> 3;
      goto LABEL_37;
    }
    if ( *((unsigned __int16 *)a2 + 22) == 34404 )
    {
      v5 = v9 / 0xC;
      goto LABEL_37;
    }
    if ( *((unsigned __int16 *)a2 + 22) == 43620 )
    {
      LODWORD(v5) = (unsigned int)v9 >> 3;
LABEL_37:
      if ( !(_DWORD)v5 )
        goto LABEL_79;
      dwSize = (unsigned int)(20 * v5);
      v20 = VirtualAlloc(0, dwSize, 0x1000u, 4u);
      *((_QWORD *)a2 + 310) = v20;
      v21 = v20;
      if ( !v20 )
        goto LABEL_79;
      switch ( *((_WORD *)a2 + 22) )
      {
        case 0x1C0:
        case 0x1C2:
          flOldProtect = 0;
          v34 = 0;
          v35 = 0;
          do
          {
            v21[5 * v35] = (*(_DWORD *)(v6 + 8 * v34) & 0xFFFFFFFE) - *((_DWORD *)a2 + 6);
            v36 = *(_DWORD *)(v6 + 8LL * flOldProtect + 4);
            v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                      + (((v36 >> 8) & 0x3FFFFF) << (((v36 & 0x40000000) != 0) + 1));
            v21[5 * flOldProtect + 2] = v21[5 * flOldProtect]
                                      + (*(unsigned __int8 *)(v6 + 8LL * flOldProtect + 4) << (((*(_DWORD *)(v6 + 8LL * flOldProtect + 4)
                                                                                               & 0x40000000) != 0)
                                                                                             + 1));
            v21[5 * flOldProtect + 3] = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 31;
            v21[5 * flOldProtect + 4] = (*(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 30) & 1;
            v34 = flOldProtect + 1;
            flOldProtect = v34;
            v35 = v34;
          }
          while ( (unsigned int)v34 < (unsigned int)v5 );
          goto LABEL_78;
        case 0x1C4:
          flOldProtect = 0;
          v30 = 0;
          v31 = 0;
          do
          {
            v21[5 * v31] = *(_DWORD *)(v6 + 8LL * v30);
            v32 = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) & 3;
            if ( v32 == 3 )
            {
              v21[5 * flOldProtect + 1] = v21[5 * flOldProtect] + 10;
            }
            else if ( v32 )
            {
              v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                        + 2 * ((*(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 2) & 0x7FF);
            }
            else if ( GetXData(a1, a2) )
            {
              v33 = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) - *((_DWORD *)a2 + 632);
              if ( v33 < *((_DWORD *)a2 + 630) )
                v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                          + 2 * (*(_DWORD *)(v33 + *((_QWORD *)a2 + 312)) & 0x3FFFF);
            }
            v21[5 * flOldProtect + 2] = *(_DWORD *)(v6 + 8LL * flOldProtect + 4);
            v21[5 * flOldProtect + 3] = 0;
            v21[5 * flOldProtect + 4] = 0;
            v30 = flOldProtect + 1;
            flOldProtect = v30;
            v31 = v30;
          }
          while ( v30 < (unsigned int)v5 );
          break;
        case 0x1F2:
          flOldProtect = 0;
          v28 = 0;
          v29 = 0;
          do
          {
            v21[5 * v29] = *(_DWORD *)(v6 + 8 * v28) - *((_DWORD *)a2 + 6);
            v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                      + ((*(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 6) & 0xFFFFFC);
            v21[5 * flOldProtect + 2] = v21[5 * flOldProtect] + 4 * *(unsigned __int8 *)(v6 + 8LL * flOldProtect + 4);
            v21[5 * flOldProtect + 3] = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 30;
            v21[5 * flOldProtect + 4] = 0;
            v28 = flOldProtect + 1;
            flOldProtect = v28;
            v29 = v28;
          }
          while ( (unsigned int)v28 < (unsigned int)v5 );
          goto LABEL_78;
        default:
          if ( *((unsigned __int16 *)a2 + 22) == 34404 )
          {
            flOldProtect = 0;
            v26 = 0;
            v27 = 0;
            do
            {
              v21[5 * v27] = *(_DWORD *)(v6 + 12 * v26);
              v21[5 * flOldProtect + 1] = *(_DWORD *)(v6 + 12LL * flOldProtect + 4);
              v21[5 * flOldProtect + 2] = *(_DWORD *)(v6 + 12LL * flOldProtect + 8);
              v21[5 * flOldProtect + 3] = 0;
              v21[5 * flOldProtect + 4] = 0;
              v26 = flOldProtect + 1;
              flOldProtect = v26;
              v27 = v26;
            }
            while ( (unsigned int)v26 < (unsigned int)v5 );
            goto LABEL_78;
          }
          if ( *((unsigned __int16 *)a2 + 22) != 43620 )
          {
LABEL_78:
            VirtualProtect(*((LPVOID *)a2 + 310), dwSize, 2u, &flOldProtect);
            *((_DWORD *)a2 + 626) = v5;
            goto LABEL_79;
          }
          flOldProtect = 0;
          v22 = 0;
          v23 = 0;
          do
          {
            v21[5 * v23] = *(_DWORD *)(v6 + 8LL * v22);
            v24 = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) & 3;
            if ( v24 == 3 )
            {
              v21[5 * flOldProtect + 1] = v21[5 * flOldProtect] + 12;
            }
            else if ( v24 )
            {
              v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                        + 4 * ((*(_DWORD *)(v6 + 8LL * flOldProtect + 4) >> 2) & 0x7FF);
            }
            else if ( GetXData(a1, a2) )
            {
              v25 = *(_DWORD *)(v6 + 8LL * flOldProtect + 4) - *((_DWORD *)a2 + 632);
              if ( v25 < *((_DWORD *)a2 + 630) )
                v21[5 * flOldProtect + 1] = v21[5 * flOldProtect]
                                          + 4 * (*(_DWORD *)(v25 + *((_QWORD *)a2 + 312)) & 0x3FFFF);
            }
            v21[5 * flOldProtect + 2] = *(_DWORD *)(v6 + 8LL * flOldProtect + 4);
            v21[5 * flOldProtect + 3] = 0;
            v21[5 * flOldProtect + 4] = 0;
            v22 = flOldProtect + 1;
            flOldProtect = v22;
            v23 = v22;
          }
          while ( v22 < (unsigned int)v5 );
          break;
      }
      v8 = FileW;
      goto LABEL_78;
    }
  }
LABEL_79:
  if ( *v7 != 5 )
  {
    FreeIt(*((void **)a2 + 311));
    *((_QWORD *)a2 + 311) = 0;
  }
  MappedSpan::unmap((MappedSpan *)&v37);
  if ( v8 )
    CloseHandle(v8);
  return (_DWORD)v5 != 0;
}

```

## disassembly

```asm
0x1801aacd0  mov     [rsp-38h+arg_0], rcx
0x1801aacd5  push    rbp
0x1801aacd6  push    rbx
0x1801aacd7  push    rsi
0x1801aacd8  push    rdi
0x1801aacd9  push    r13
0x1801aacdb  push    r14
0x1801aacdd  push    r15
0x1801aacdf  mov     rbp, rsp
0x1801aace2  sub     rsp, 50h
0x1801aace6  cmp     qword ptr [rdx+9B0h], 0
0x1801aacee  xorps   xmm0, xmm0
0x1801aacf1  movdqu  [rbp+var_10], xmm0
0x1801aacf6  mov     rdi, rdx
0x1801aacf9  mov     [rbp+flOldProtect], 0
0x1801aad00  jz      short loc_1801AAD0C
0x1801aad02  mov     eax, 1
0x1801aad07  jmp     loc_1801AB3B5
0x1801aad0c  xor     r8d, r8d; unsigned int
0x1801aad0f  call    ?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z; LoadSymbols(void *,_MODULE_ENTRY *,ulong)
0x1801aad14  xor     r10d, r10d
0x1801aad17  test    eax, eax
0x1801aad19  jz      loc_1801AB3B3
0x1801aad1f  lea     esi, [r10+3]
0x1801aad23  mov     r14d, r10d
0x1801aad26  cmp     [rdi+4C10h], r10
0x1801aad2d  jz      short loc_1801AAD71
0x1801aad2f  mov     r15, [rdi+9B8h]
0x1801aad36  lea     rbx, [rdi+4BECh]
0x1801aad3d  mov     [rbp+arg_10], r10
0x1801aad41  mov     r13d, r10d
0x1801aad44  test    r15, r15
0x1801aad47  jz      short loc_1801AAD59
0x1801aad49  cmp     dword ptr [rbx], 5
0x1801aad4c  jnz     short loc_1801AAD59
0x1801aad4e  mov     ecx, [rdi+9D4h]
0x1801aad54  jmp     loc_1801AAE54
0x1801aad59  mov     rcx, rdi; struct _MODULE_ENTRY *
0x1801aad5c  call    ?diaGetPData@@YAHPEAU_MODULE_ENTRY@@@Z; diaGetPData(_MODULE_ENTRY *)
0x1801aad61  xor     r10d, r10d
0x1801aad64  test    eax, eax
0x1801aad66  jz      short loc_1801AAD71
0x1801aad68  mov     r15, [rdi+9B8h]
0x1801aad6f  jmp     short loc_1801AAD4E
0x1801aad71  lea     rbx, [rdi+4BECh]
0x1801aad78  cmp     [rbx], r10d
0x1801aad7b  jz      loc_1801AB3B3
0x1801aad81  xor     ecx, ecx; int
0x1801aad83  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x1801aad88  cmp     cs:dword_1802AF874, 2
0x1801aad8f  mov     r8d, esi
0x1801aad92  mov     rcx, [rdi+138h]; lpFileName
0x1801aad99  mov     eax, 7
0x1801aad9e  cmovz   r8d, eax; dwShareMode
0x1801aada2  mov     [rsp+50h+hTemplateFile], r14; hTemplateFile
0x1801aada7  xor     r9d, r9d; lpSecurityAttributes
0x1801aadaa  mov     [rsp+50h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1801aadaf  mov     edx, 80000000h; dwDesiredAccess
0x1801aadb4  mov     [rsp+50h+dwCreationDisposition], esi; dwCreationDisposition
0x1801aadb8  call    cs:__imp_CreateFileW
0x1801aadbe  mov     ecx, 1; int
0x1801aadc3  mov     [rbp+arg_10], rax
0x1801aadc7  mov     r13, rax
0x1801aadca  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x1801aadcf  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1801aadd3  jz      loc_1801AB3B3
0x1801aadd9  mov     rdx, r13
0x1801aaddc  lea     rcx, [rbp+var_10]
0x1801aade0  call    ?MapItRO@@YA?AVMappedSpan@@PEAX@Z; MapItRO(void *)
0x1801aade5  xor     r10d, r10d
0x1801aade8  movups  xmm0, xmmword ptr [rax]
0x1801aadeb  movq    r8, xmm0
0x1801aadf0  movdqu  [rbp+var_10], xmm0
0x1801aadf5  test    r8, r8
0x1801aadf8  jz      loc_1801AB376
0x1801aadfe  mov     eax, 5A4Dh
0x1801aae03  cmp     [r8], ax
0x1801aae07  jnz     loc_1801AAEBB
0x1801aae0d  movsxd  rcx, dword ptr [r8+3Ch]
0x1801aae11  mov     eax, 10Bh
0x1801aae16  cmp     [rcx+r8+18h], ax
0x1801aae1c  jnz     short loc_1801AAE30
0x1801aae1e  mov     r15d, [rcx+r8+90h]
0x1801aae26  mov     ecx, [rcx+r8+94h]
0x1801aae2e  jmp     short loc_1801AAE51
0x1801aae30  mov     eax, 20Bh
0x1801aae35  cmp     [rcx+r8+18h], ax
0x1801aae3b  jnz     loc_1801AB376
0x1801aae41  mov     r15d, [rcx+r8+0A0h]
0x1801aae49  mov     ecx, [rcx+r8+0A4h]
0x1801aae51  add     r15, r8
0x1801aae54  test    ecx, ecx
0x1801aae56  jz      loc_1801AB376
0x1801aae5c  movzx   edx, word ptr [rdi+2Ch]
0x1801aae60  sub     edx, 1C0h
0x1801aae66  jz      short loc_1801AAEB0
0x1801aae68  sub     edx, 2
0x1801aae6b  jz      short loc_1801AAEB0
0x1801aae6d  sub     edx, 2
0x1801aae70  jz      short loc_1801AAEB0
0x1801aae72  sub     edx, 2Eh ; '.'
0x1801aae75  jz      short loc_1801AAEB0
0x1801aae77  sub     edx, 8472h
0x1801aae7d  jz      short loc_1801AAE97
0x1801aae7f  cmp     edx, 2400h
0x1801aae85  jnz     loc_1801AB376
0x1801aae8b  mov     r14d, ecx
0x1801aae8e  shr     r14d, 3
0x1801aae92  jmp     loc_1801AAF3E
0x1801aae97  mov     rax, 0AAAAAAAAAAAAAAABh
0x1801aaea1  mul     rcx
0x1801aaea4  mov     r14, rdx
0x1801aaea7  shr     r14, 3
0x1801aaeab  jmp     loc_1801AAF3E
0x1801aaeb0  shr     ecx, 3
0x1801aaeb3  mov     r14d, ecx
0x1801aaeb6  jmp     loc_1801AAF3E
0x1801aaebb  mov     eax, 4944h
0x1801aaec0  cmp     [r8], ax
0x1801aaec4  jnz     loc_1801AB376
0x1801aaeca  mov     r9d, [r8+20h]
0x1801aaece  mov     rax, 2492492492492493h
0x1801aaed8  mov     ecx, [r8+1Ch]
0x1801aaedc  mul     r9
0x1801aaedf  mov     eax, [r8+18h]
0x1801aaee3  sub     r9, rdx
0x1801aaee6  mov     [rbp+flOldProtect], r10d
0x1801aaeea  shr     r9, 1
0x1801aaeed  add     r9, rdx
0x1801aaef0  lea     rax, [rax+rax*4]
0x1801aaef4  shr     r9, 4
0x1801aaef8  add     rcx, r8
0x1801aaefb  lea     rax, [rax+6]
0x1801aaeff  lea     rax, [rcx+rax*8]
0x1801aaf03  mov     ecx, r10d
0x1801aaf06  cmp     ecx, r9d
0x1801aaf09  jnb     loc_1801AB376
0x1801aaf0f  cmp     dword ptr [rax+0Ch], 5
0x1801aaf13  jz      short loc_1801AAF20
0x1801aaf15  inc     ecx
0x1801aaf17  mov     [rbp+flOldProtect], ecx
0x1801aaf1a  add     rax, 1Ch
0x1801aaf1e  jmp     short loc_1801AAF06
0x1801aaf20  mov     r15d, [rax+18h]
0x1801aaf24  mov     ecx, [rax+10h]
0x1801aaf27  add     r15, r8
0x1801aaf2a  mov     rax, 0AAAAAAAAAAAAAAABh
0x1801aaf34  mul     rcx
0x1801aaf37  shr     rdx, 3
0x1801aaf3b  mov     r14d, edx
0x1801aaf3e  test    r14d, r14d
0x1801aaf41  jz      loc_1801AB376
0x1801aaf47  lea     eax, [r14+r14*4]
0x1801aaf4b  mov     r9d, 4; flProtect
0x1801aaf51  shl     eax, 2
0x1801aaf54  mov     r8d, 1000h; flAllocationType
0x1801aaf5a  mov     edx, eax; dwSize
0x1801aaf5c  mov     [rbp+dwSize], rax
0x1801aaf60  xor     ecx, ecx; lpAddress
0x1801aaf62  call    cs:__imp_VirtualAlloc
0x1801aaf68  xor     r10d, r10d
0x1801aaf6b  mov     [rdi+9B0h], rax
0x1801aaf72  mov     rsi, rax
0x1801aaf75  test    rax, rax
0x1801aaf78  jz      loc_1801AB376
0x1801aaf7e  movzx   eax, word ptr [rdi+2Ch]
0x1801aaf82  sub     eax, 1C0h
0x1801aaf87  jz      loc_1801AB2A1
0x1801aaf8d  sub     eax, 2
0x1801aaf90  jz      loc_1801AB2A1
0x1801aaf96  sub     eax, 2
0x1801aaf99  jz      loc_1801AB1AE
0x1801aaf9f  sub     eax, 2Eh ; '.'
0x1801aafa2  jz      loc_1801AB125
0x1801aafa8  sub     eax, 8472h
0x1801aafad  jz      loc_1801AB0AD
0x1801aafb3  cmp     eax, 2400h
0x1801aafb8  jnz     loc_1801AB354
0x1801aafbe  mov     [rbp+flOldProtect], r10d
0x1801aafc2  test    r14d, r14d
0x1801aafc5  jz      loc_1801AB354
0x1801aafcb  mov     r13, [rbp+arg_0]
0x1801aafcf  mov     eax, r10d
0x1801aafd2  mov     ecx, r10d
0x1801aafd5  mov     edx, eax
0x1801aafd7  mov     eax, ecx
0x1801aafd9  lea     rcx, [rax+rax*4]
0x1801aafdd  mov     eax, [r15+rdx*8]
0x1801aafe1  mov     [rsi+rcx*4], eax
0x1801aafe4  mov     eax, [rbp+flOldProtect]
0x1801aafe7  mov     ecx, [r15+rax*8+4]
0x1801aafec  mov     edx, ecx
0x1801aafee  and     edx, 3
0x1801aaff1  cmp     edx, 3
0x1801aaff4  jnz     short loc_1801AB006
0x1801aaff6  lea     rcx, [rax+rax*4]
0x1801aaffa  mov     eax, [rsi+rcx*4]
0x1801aaffd  add     eax, 0Ch
0x1801ab000  mov     [rsi+rcx*4+4], eax
0x1801ab004  jmp     short loc_1801AB06D
0x1801ab006  test    edx, edx
0x1801ab008  jz      short loc_1801AB023
0x1801ab00a  lea     rdx, [rax+rax*4]
0x1801ab00e  shr     ecx, 2
0x1801ab011  mov     eax, [rsi+rdx*4]
0x1801ab014  and     ecx, 7FFh
0x1801ab01a  lea     ecx, [rax+rcx*4]
0x1801ab01d  mov     [rsi+rdx*4+4], ecx
0x1801ab021  jmp     short loc_1801AB06D
0x1801ab023  mov     rdx, rdi; struct _MODULE_ENTRY *
0x1801ab026  mov     rcx, r13; void *
0x1801ab029  call    ?GetXData@@YAHPEAXPEAU_MODULE_ENTRY@@@Z; GetXData(void *,_MODULE_ENTRY *)
0x1801ab02e  xor     r10d, r10d
0x1801ab031  test    eax, eax
0x1801ab033  jz      short loc_1801AB06D
0x1801ab035  mov     ecx, [rbp+flOldProtect]
0x1801ab038  mov     eax, [r15+rcx*8+4]
0x1801ab03d  sub     eax, [rdi+9E0h]
0x1801ab043  cmp     eax, [rdi+9D8h]
0x1801ab049  jnb     short loc_1801AB06D
0x1801ab04b  lea     r8, [rcx+rcx*4]
0x1801ab04f  mov     ecx, eax
0x1801ab051  mov     rax, [rdi+9C0h]
0x1801ab058  mov     edx, [rcx+rax]
0x1801ab05b  mov     eax, [rsi+r8*4]
0x1801ab05f  and     edx, 3FFFFh
0x1801ab065  lea     ecx, [rax+rdx*4]
0x1801ab068  mov     [rsi+r8*4+4], ecx
0x1801ab06d  mov     eax, [rbp+flOldProtect]
0x1801ab070  lea     rcx, [rax+rax*4]
0x1801ab074  mov     eax, [r15+rax*8+4]
0x1801ab079  mov     [rsi+rcx*4+8], eax
0x1801ab07d  mov     eax, [rbp+flOldProtect]
0x1801ab080  lea     rcx, [rax+rax*4]
0x1801ab084  mov     [rsi+rcx*4+0Ch], r10d
0x1801ab089  mov     eax, [rbp+flOldProtect]
0x1801ab08c  lea     rcx, [rax+rax*4]
0x1801ab090  mov     [rsi+rcx*4+10h], r10d
0x1801ab095  mov     eax, [rbp+flOldProtect]
0x1801ab098  inc     eax
0x1801ab09a  mov     [rbp+flOldProtect], eax
0x1801ab09d  mov     ecx, eax
0x1801ab09f  cmp     eax, r14d
0x1801ab0a2  jb      loc_1801AAFD5
0x1801ab0a8  jmp     loc_1801AB298
0x1801ab0ad  mov     [rbp+flOldProtect], r10d
0x1801ab0b1  test    r14d, r14d
0x1801ab0b4  jz      loc_1801AB354
0x1801ab0ba  mov     eax, r10d
0x1801ab0bd  mov     ecx, r10d
0x1801ab0c0  lea     rdx, [rax+rax*2]
0x1801ab0c4  mov     eax, ecx
0x1801ab0c6  lea     rcx, [rax+rax*4]
0x1801ab0ca  mov     eax, [r15+rdx*4]
0x1801ab0ce  mov     [rsi+rcx*4], eax
0x1801ab0d1  mov     eax, [rbp+flOldProtect]
0x1801ab0d4  lea     rdx, [rax+rax*4]
0x1801ab0d8  lea     rcx, [rax+rax*2]
0x1801ab0dc  mov     eax, [r15+rcx*4+4]
0x1801ab0e1  mov     [rsi+rdx*4+4], eax
0x1801ab0e5  mov     eax, [rbp+flOldProtect]
0x1801ab0e8  lea     rcx, [rax+rax*2]
0x1801ab0ec  lea     rdx, [rax+rax*4]
0x1801ab0f0  mov     eax, [r15+rcx*4+8]
0x1801ab0f5  mov     [rsi+rdx*4+8], eax
0x1801ab0f9  mov     eax, [rbp+flOldProtect]
0x1801ab0fc  lea     rcx, [rax+rax*4]
0x1801ab100  mov     [rsi+rcx*4+0Ch], r10d
0x1801ab105  mov     eax, [rbp+flOldProtect]
0x1801ab108  lea     rcx, [rax+rax*4]
0x1801ab10c  mov     [rsi+rcx*4+10h], r10d
0x1801ab111  mov     eax, [rbp+flOldProtect]
0x1801ab114  inc     eax
0x1801ab116  mov     [rbp+flOldProtect], eax
0x1801ab119  mov     ecx, eax
0x1801ab11b  cmp     eax, r14d
0x1801ab11e  jb      short loc_1801AB0C0
0x1801ab120  jmp     loc_1801AB354
0x1801ab125  mov     [rbp+flOldProtect], r10d
0x1801ab129  test    r14d, r14d
0x1801ab12c  jz      loc_1801AB354
0x1801ab132  mov     eax, r10d
0x1801ab135  mov     ecx, r10d
0x1801ab138  mov     edx, [r15+rax*8]
0x1801ab13c  sub     edx, [rdi+18h]
0x1801ab13f  mov     eax, ecx
0x1801ab141  lea     rcx, [rax+rax*4]
0x1801ab145  mov     [rsi+rcx*4], edx
0x1801ab148  mov     eax, [rbp+flOldProtect]
0x1801ab14b  mov     ecx, [r15+rax*8+4]
0x1801ab150  lea     rdx, [rax+rax*4]
0x1801ab154  shr     ecx, 6
0x1801ab157  and     ecx, 0FFFFFCh
0x1801ab15d  add     ecx, [rsi+rdx*4]
0x1801ab160  mov     [rsi+rdx*4+4], ecx
0x1801ab164  mov     eax, [rbp+flOldProtect]
0x1801ab167  movzx   ecx, byte ptr [r15+rax*8+4]
0x1801ab16d  lea     rdx, [rax+rax*4]
0x1801ab171  mov     eax, [rsi+rdx*4]
0x1801ab174  lea     ecx, [rax+rcx*4]
  ... truncated ...
```
