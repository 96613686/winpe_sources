# MRxDAVQueryDirectoryFromCache

- ea: `0x14001fc00`
- end: `0x140020006`
- name: `MRxDAVQueryDirectoryFromCache`
- size: `1030`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140003698`
- `0x14001f6c0`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140006900`
- `0x14001fc00`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fc7d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fcd5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd9a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe2f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff11`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff65`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fc7d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fcd5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd9a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe2f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fe83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff11`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ff65`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryDirectoryFromCache(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // r14
  unsigned int v6; // r12d
  int v9; // ebp
  __int64 v10; // rbx
  HANDLE v11; // rax
  unsigned int v12; // ebx
  __int64 v13; // rbx
  HANDLE v14; // rax
  unsigned int v15; // ebp
  void *v16; // rcx
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rbx
  HANDLE v23; // rax
  __int64 v24; // rbx
  HANDLE CurrentThreadId; // rax
  _QWORD *v27; // [rsp+98h] [rbp+20h]
  int v29; // [rsp+A0h] [rbp+28h]

  v27 = a4;
  v4 = *(_QWORD *)(a1 + 64);
  v6 = *(_DWORD *)(a1 + 472);
  v29 = *(_DWORD *)(a1 + 448);
  v9 = *(unsigned __int16 *)(v4 + 80);
  switch ( v29 )
  {
    case 1:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        CurrentThreadId = PsGetCurrentThreadId();
        WPP_SF_q(v24, 68, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId);
        a4 = v27;
      }
      v15 = v9 + 72;
      if ( v15 <= v6 )
      {
        *(_DWORD *)(a2 + 4) = 1;
        v12 = 0;
        *(_DWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = *(_QWORD *)a3;
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(a3 + 8);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(a3 + 16);
        *(_QWORD *)(a2 + 32) = *(_QWORD *)(a3 + 24);
        *(_DWORD *)(a2 + 56) = *(_DWORD *)(a3 + 32) & 0xFFFFFEFF;
        *(_QWORD *)(a2 + 40) = a4[1];
        *(_QWORD *)(a2 + 48) = *a4;
        *(_DWORD *)(a2 + 60) = *(unsigned __int16 *)(v4 + 80);
        v16 = (void *)(a2 + 64);
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v20 = PsGetCurrentThreadId();
        v21 = 69;
        goto LABEL_38;
      }
      return (unsigned int)-2147483643;
    case 2:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v23 = PsGetCurrentThreadId();
        WPP_SF_q(v22, 70, WPP_609949de13fe38daba556366630c430b_Traceguids, v23);
        a4 = v27;
      }
      v15 = v9 + 72;
      if ( v15 <= v6 )
      {
        *(_DWORD *)(a2 + 4) = 1;
        v16 = (void *)(a2 + 68);
        v12 = 0;
        *(_DWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = *(_QWORD *)a3;
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(a3 + 8);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(a3 + 16);
        *(_QWORD *)(a2 + 32) = *(_QWORD *)(a3 + 24);
        *(_DWORD *)(a2 + 56) = *(_DWORD *)(a3 + 32) & 0xFFFFFEFF;
        *(_QWORD *)(a2 + 40) = a4[1];
        *(_QWORD *)(a2 + 48) = *a4;
        *(_DWORD *)(a2 + 64) = 0;
        *(_DWORD *)(a2 + 60) = *(unsigned __int16 *)(v4 + 80);
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v20 = PsGetCurrentThreadId();
        v21 = 71;
        goto LABEL_38;
      }
      return (unsigned int)-2147483643;
    case 3:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v18 = PsGetCurrentThreadId();
        WPP_SF_q(v17, 72, WPP_609949de13fe38daba556366630c430b_Traceguids, v18);
        a4 = v27;
      }
      v15 = v9 + 96;
      if ( v15 <= v6 )
      {
        *(_DWORD *)(a2 + 4) = 1;
        v16 = (void *)(a2 + 94);
        v12 = 0;
        *(_DWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = *(_QWORD *)a3;
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(a3 + 8);
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(a3 + 16);
        *(_QWORD *)(a2 + 32) = *(_QWORD *)(a3 + 24);
        *(_DWORD *)(a2 + 56) = *(_DWORD *)(a3 + 32) & 0xFFFFFEFF;
        *(_QWORD *)(a2 + 40) = a4[1];
        *(_QWORD *)(a2 + 48) = *a4;
        *(_DWORD *)(a2 + 64) = 0;
        *(_BYTE *)(a2 + 68) = 0;
        *(_WORD *)(a2 + 70) = 0;
        *(_DWORD *)(a2 + 60) = *(unsigned __int16 *)(v4 + 80);
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v19 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v20 = PsGetCurrentThreadId();
        v21 = 73;
LABEL_38:
        WPP_SF_q(v19, v21, WPP_609949de13fe38daba556366630c430b_Traceguids, v20);
        return (unsigned int)-2147483643;
      }
      return (unsigned int)-2147483643;
    case 12:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v14 = PsGetCurrentThreadId();
        WPP_SF_q(v13, 67, WPP_609949de13fe38daba556366630c430b_Traceguids, v14);
      }
      v15 = v9 + 16;
      if ( v15 > v6 )
        return (unsigned int)-2147483643;
      v12 = 0;
      *(_DWORD *)(a2 + 4) = 1;
      *(_DWORD *)a2 = 0;
      v16 = (void *)(a2 + 12);
      *(_DWORD *)(a2 + 8) = *(unsigned __int16 *)(v4 + 80);
LABEL_40:
      memmove(v16, *(const void **)(v4 + 88), *(unsigned __int16 *)(v4 + 80));
      *(_DWORD *)(a1 + 472) -= v15;
      return v12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v11 = PsGetCurrentThreadId();
    WPP_SF_qD(v10, 74, WPP_609949de13fe38daba556366630c430b_Traceguids, v11, v29);
  }
  return (unsigned int)-1073741637;
}

```

## disassembly

```asm
0x14001fc00  mov     [rsp+arg_18], r9
0x14001fc05  push    rbx
0x14001fc06  push    rbp
0x14001fc07  push    rsi
0x14001fc08  push    rdi
0x14001fc09  push    r12
0x14001fc0b  push    r13
0x14001fc0d  push    r14
0x14001fc0f  push    r15
0x14001fc11  sub     rsp, 38h
0x14001fc15  mov     r14, [rcx+40h]
0x14001fc19  mov     rsi, rdx
0x14001fc1c  mov     r12d, [rcx+1D8h]
0x14001fc23  mov     r13, rcx
0x14001fc26  mov     ecx, [rcx+1C0h]
0x14001fc2c  mov     r15, r8
0x14001fc2f  mov     edx, ecx
0x14001fc31  mov     [rsp+78h+arg_20], ecx
0x14001fc38  movzx   ebp, word ptr [r14+50h]
0x14001fc3d  sub     edx, 1
0x14001fc40  jz      loc_14001FEF1
0x14001fc46  sub     edx, 1
0x14001fc49  jz      loc_14001FE0F
0x14001fc4f  sub     edx, 1
0x14001fc52  jz      loc_14001FD26
0x14001fc58  cmp     edx, 9
0x14001fc5b  jz      short loc_14001FCB5
0x14001fc5d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fc64  lea     rdi, WPP_GLOBAL_Control
0x14001fc6b  cmp     rbx, rdi
0x14001fc6e  jz      short loc_14001FCAB
0x14001fc70  test    dword ptr [rbx+2Ch], 2000h
0x14001fc77  jz      short loc_14001FCAB
0x14001fc79  mov     rbx, [rbx+18h]
0x14001fc7d  call    cs:__imp_PsGetCurrentThreadId
0x14001fc84  nop     dword ptr [rax+rax+00h]
0x14001fc89  mov     edx, 4Ah ; 'J'
0x14001fc8e  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fc95  mov     r9, rax
0x14001fc98  mov     rcx, rbx
0x14001fc9b  mov     eax, [rsp+78h+arg_20]
0x14001fca2  mov     [rsp+78h+var_58], eax
0x14001fca6  call    WPP_SF_qD
0x14001fcab  mov     ebx, 0C00000BBh
0x14001fcb0  jmp     loc_14001FFF2
0x14001fcb5  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fcbc  lea     rdi, WPP_GLOBAL_Control
0x14001fcc3  cmp     rbx, rdi
0x14001fcc6  jz      short loc_14001FCF8
0x14001fcc8  test    dword ptr [rbx+2Ch], 4000h
0x14001fccf  jz      short loc_14001FCF8
0x14001fcd1  mov     rbx, [rbx+18h]
0x14001fcd5  call    cs:__imp_PsGetCurrentThreadId
0x14001fcdc  nop     dword ptr [rax+rax+00h]
0x14001fce1  mov     edx, 43h ; 'C'
0x14001fce6  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fced  mov     r9, rax
0x14001fcf0  mov     rcx, rbx
0x14001fcf3  call    WPP_SF_q
0x14001fcf8  add     ebp, 10h
0x14001fcfb  cmp     ebp, r12d
0x14001fcfe  jbe     short loc_14001FD0A
0x14001fd00  mov     ebx, 80000005h
0x14001fd05  jmp     loc_14001FFF2
0x14001fd0a  xor     ebx, ebx
0x14001fd0c  mov     dword ptr [rsi+4], 1
0x14001fd13  mov     [rsi], ebx
0x14001fd15  lea     rcx, [rsi+0Ch]
0x14001fd19  movzx   eax, word ptr [r14+50h]
0x14001fd1e  mov     [rsi+8], eax
0x14001fd21  jmp     loc_14001FFDD
0x14001fd26  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fd2d  lea     rdi, WPP_GLOBAL_Control
0x14001fd34  cmp     rbx, rdi
0x14001fd37  jz      short loc_14001FD71
0x14001fd39  test    dword ptr [rbx+2Ch], 4000h
0x14001fd40  jz      short loc_14001FD71
0x14001fd42  mov     rbx, [rbx+18h]
0x14001fd46  call    cs:__imp_PsGetCurrentThreadId
0x14001fd4d  nop     dword ptr [rax+rax+00h]
0x14001fd52  mov     edx, 48h ; 'H'
0x14001fd57  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fd5e  mov     r9, rax
0x14001fd61  mov     rcx, rbx
0x14001fd64  call    WPP_SF_q
0x14001fd69  mov     r9, [rsp+78h+arg_18]
0x14001fd71  add     ebp, 60h ; '`'
0x14001fd74  cmp     ebp, r12d
0x14001fd77  jbe     short loc_14001FDB0
0x14001fd79  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fd80  cmp     rbx, rdi
0x14001fd83  jz      loc_14001FD00
0x14001fd89  test    dword ptr [rbx+2Ch], 2000h
0x14001fd90  jz      loc_14001FD00
0x14001fd96  mov     rbx, [rbx+18h]
0x14001fd9a  call    cs:__imp_PsGetCurrentThreadId
0x14001fda1  nop     dword ptr [rax+rax+00h]
0x14001fda6  mov     edx, 49h ; 'I'
0x14001fdab  jmp     loc_14001FF76
0x14001fdb0  mov     dword ptr [rsi+4], 1
0x14001fdb7  lea     rcx, [rsi+5Eh]
0x14001fdbb  xor     ebx, ebx
0x14001fdbd  mov     [rsi], ebx
0x14001fdbf  mov     rax, [r15]
0x14001fdc2  mov     [rsi+8], rax
0x14001fdc6  mov     rax, [r15+8]
0x14001fdca  mov     [rsi+10h], rax
0x14001fdce  mov     rax, [r15+10h]
0x14001fdd2  mov     [rsi+18h], rax
0x14001fdd6  mov     rax, [r15+18h]
0x14001fdda  mov     [rsi+20h], rax
0x14001fdde  mov     eax, [r15+20h]
0x14001fde2  btr     eax, 8
0x14001fde6  mov     [rsi+38h], eax
0x14001fde9  mov     rax, [r9+8]
0x14001fded  mov     [rsi+28h], rax
0x14001fdf1  mov     rax, [r9]
0x14001fdf4  mov     [rsi+30h], rax
0x14001fdf8  mov     [rsi+40h], ebx
0x14001fdfb  mov     [rsi+44h], bl
0x14001fdfe  mov     [rsi+46h], bx
0x14001fe02  movzx   eax, word ptr [r14+50h]
0x14001fe07  mov     [rsi+3Ch], eax
0x14001fe0a  jmp     loc_14001FFDD
0x14001fe0f  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fe16  lea     rdi, WPP_GLOBAL_Control
0x14001fe1d  cmp     rbx, rdi
0x14001fe20  jz      short loc_14001FE5A
0x14001fe22  test    dword ptr [rbx+2Ch], 4000h
0x14001fe29  jz      short loc_14001FE5A
0x14001fe2b  mov     rbx, [rbx+18h]
0x14001fe2f  call    cs:__imp_PsGetCurrentThreadId
0x14001fe36  nop     dword ptr [rax+rax+00h]
0x14001fe3b  mov     edx, 46h ; 'F'
0x14001fe40  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fe47  mov     r9, rax
0x14001fe4a  mov     rcx, rbx
0x14001fe4d  call    WPP_SF_q
0x14001fe52  mov     r9, [rsp+78h+arg_18]
0x14001fe5a  add     ebp, 48h ; 'H'
0x14001fe5d  cmp     ebp, r12d
0x14001fe60  jbe     short loc_14001FE99
0x14001fe62  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fe69  cmp     rbx, rdi
0x14001fe6c  jz      loc_14001FD00
0x14001fe72  test    dword ptr [rbx+2Ch], 2000h
0x14001fe79  jz      loc_14001FD00
0x14001fe7f  mov     rbx, [rbx+18h]
0x14001fe83  call    cs:__imp_PsGetCurrentThreadId
0x14001fe8a  nop     dword ptr [rax+rax+00h]
0x14001fe8f  mov     edx, 47h ; 'G'
0x14001fe94  jmp     loc_14001FF76
0x14001fe99  mov     dword ptr [rsi+4], 1
0x14001fea0  lea     rcx, [rsi+44h]
0x14001fea4  xor     ebx, ebx
0x14001fea6  mov     [rsi], ebx
0x14001fea8  mov     rax, [r15]
0x14001feab  mov     [rsi+8], rax
0x14001feaf  mov     rax, [r15+8]
0x14001feb3  mov     [rsi+10h], rax
0x14001feb7  mov     rax, [r15+10h]
0x14001febb  mov     [rsi+18h], rax
0x14001febf  mov     rax, [r15+18h]
0x14001fec3  mov     [rsi+20h], rax
0x14001fec7  mov     eax, [r15+20h]
0x14001fecb  btr     eax, 8
0x14001fecf  mov     [rsi+38h], eax
0x14001fed2  mov     rax, [r9+8]
0x14001fed6  mov     [rsi+28h], rax
0x14001feda  mov     rax, [r9]
0x14001fedd  mov     [rsi+30h], rax
0x14001fee1  mov     [rsi+40h], ebx
0x14001fee4  movzx   eax, word ptr [r14+50h]
0x14001fee9  mov     [rsi+3Ch], eax
0x14001feec  jmp     loc_14001FFDD
0x14001fef1  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fef8  lea     rdi, WPP_GLOBAL_Control
0x14001feff  cmp     rbx, rdi
0x14001ff02  jz      short loc_14001FF3C
0x14001ff04  test    dword ptr [rbx+2Ch], 4000h
0x14001ff0b  jz      short loc_14001FF3C
0x14001ff0d  mov     rbx, [rbx+18h]
0x14001ff11  call    cs:__imp_PsGetCurrentThreadId
0x14001ff18  nop     dword ptr [rax+rax+00h]
0x14001ff1d  mov     edx, 44h ; 'D'
0x14001ff22  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001ff29  mov     r9, rax
0x14001ff2c  mov     rcx, rbx
0x14001ff2f  call    WPP_SF_q
0x14001ff34  mov     r9, [rsp+78h+arg_18]
0x14001ff3c  add     ebp, 48h ; 'H'
0x14001ff3f  cmp     ebp, r12d
0x14001ff42  jbe     short loc_14001FF8D
0x14001ff44  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ff4b  cmp     rbx, rdi
0x14001ff4e  jz      loc_14001FD00
0x14001ff54  test    dword ptr [rbx+2Ch], 2000h
0x14001ff5b  jz      loc_14001FD00
0x14001ff61  mov     rbx, [rbx+18h]
0x14001ff65  call    cs:__imp_PsGetCurrentThreadId
0x14001ff6c  nop     dword ptr [rax+rax+00h]
0x14001ff71  mov     edx, 45h ; 'E'
0x14001ff76  mov     r9, rax
0x14001ff79  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001ff80  mov     rcx, rbx
0x14001ff83  call    WPP_SF_q
0x14001ff88  jmp     loc_14001FD00
0x14001ff8d  mov     dword ptr [rsi+4], 1
0x14001ff94  xor     ebx, ebx
0x14001ff96  mov     [rsi], ebx
0x14001ff98  mov     rax, [r15]
0x14001ff9b  mov     [rsi+8], rax
0x14001ff9f  mov     rax, [r15+8]
0x14001ffa3  mov     [rsi+10h], rax
0x14001ffa7  mov     rax, [r15+10h]
0x14001ffab  mov     [rsi+18h], rax
0x14001ffaf  mov     rax, [r15+18h]
0x14001ffb3  mov     [rsi+20h], rax
0x14001ffb7  mov     eax, [r15+20h]
0x14001ffbb  btr     eax, 8
0x14001ffbf  mov     [rsi+38h], eax
0x14001ffc2  mov     rax, [r9+8]
0x14001ffc6  mov     [rsi+28h], rax
0x14001ffca  mov     rcx, [r9]
0x14001ffcd  mov     [rsi+30h], rcx
0x14001ffd1  movzx   ecx, word ptr [r14+50h]
0x14001ffd6  mov     [rsi+3Ch], ecx
0x14001ffd9  lea     rcx, [rsi+40h]; void *
0x14001ffdd  movzx   r8d, word ptr [r14+50h]; Size
0x14001ffe2  mov     rdx, [r14+58h]; Src
0x14001ffe6  call    memmove
0x14001ffeb  sub     [r13+1D8h], ebp
0x14001fff2  mov     eax, ebx
0x14001fff4  add     rsp, 38h
0x14001fff8  pop     r15
0x14001fffa  pop     r14
0x14001fffc  pop     r13
0x14001fffe  pop     r12
0x140020000  pop     rdi
0x140020001  pop     rsi
0x140020002  pop     rbp
0x140020003  pop     rbx
0x140020004  retn
```
