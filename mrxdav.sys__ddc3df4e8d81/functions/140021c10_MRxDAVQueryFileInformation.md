# MRxDAVQueryFileInformation

- ea: `0x140021c10`
- end: `0x1400220ba`
- name: `MRxDAVQueryFileInformation`
- size: `1194`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x140006c00`
- `0x140021c10`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140021c79`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021d14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021d76`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021de6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021e34`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021ebc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021f0b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021f5b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021fab`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022021`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021c79`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021d14`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021d76`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021de6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021e34`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021ebc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021f0b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021f5b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021fab`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140022021`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryFileInformation(__int64 a1)
{
  __int64 v1; // rbp
  int v2; // r13d
  unsigned int v3; // edi
  unsigned int v4; // r14d
  int v5; // r15d
  __int64 v6; // rsi
  int v7; // r12d
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rdx
  char v15; // al

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_DWORD *)(a1 + 448);
  v3 = 0;
  v4 = *(_DWORD *)(a1 + 472);
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 456);
  v7 = *(_DWORD *)(v1 + 232);
  if ( !v7 )
    v7 = 32;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qD(v8, 24, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId, v2);
  }
  switch ( v2 )
  {
    case 4:
      if ( v4 >= 0x28 )
      {
        v5 = 40;
        *(_DWORD *)(v6 + 24) = *(_DWORD *)(v1 + 224);
        *(_DWORD *)(v6 + 28) = *(_DWORD *)(v1 + 228);
        *(_DWORD *)v6 = *(_DWORD *)(v1 + 200);
        *(_DWORD *)(v6 + 4) = *(_DWORD *)(v1 + 204);
        *(_DWORD *)(v6 + 8) = *(_DWORD *)(v1 + 208);
        *(_DWORD *)(v6 + 12) = *(_DWORD *)(v1 + 212);
        *(_DWORD *)(v6 + 16) = *(_DWORD *)(v1 + 216);
        *(_DWORD *)(v6 + 20) = *(_DWORD *)(v1 + 220);
        *(_DWORD *)(v6 + 32) = v7;
        goto LABEL_62;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 25;
        goto LABEL_60;
      }
      goto LABEL_62;
    case 5:
      if ( v4 >= 0x18 )
      {
        *(_DWORD *)v6 = *(_DWORD *)(v1 + 24);
        *(_DWORD *)(v6 + 4) = *(_DWORD *)(v1 + 28);
        v5 = 24;
        *(_DWORD *)(v6 + 8) = *(_DWORD *)(v1 + 32);
        *(_DWORD *)(v6 + 12) = *(_DWORD *)(v1 + 36);
        v15 = *(_BYTE *)(v1 + 156) & 1;
        *(_DWORD *)(v6 + 16) = 1;
        *(_BYTE *)(v6 + 20) = v15;
        *(_BYTE *)(v6 + 21) = v7 & 0x10;
        goto LABEL_62;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 26;
        goto LABEL_60;
      }
      goto LABEL_62;
    case 6:
      if ( v4 >= 8 )
      {
        *(_QWORD *)v6 = 0;
        goto LABEL_50;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_62;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 27;
      goto LABEL_60;
    case 7:
      if ( v4 >= 4 )
      {
        *(_DWORD *)v6 = 0;
        v5 = 4;
        goto LABEL_62;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 28;
        goto LABEL_60;
      }
      goto LABEL_62;
    case 21:
      if ( v4 >= 8 )
      {
        *(_DWORD *)v6 = 0;
        *(_WORD *)(v6 + 4) = 0;
        goto LABEL_50;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        goto LABEL_62;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      v14 = 30;
LABEL_60:
      WPP_SF_q(v12, v14, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v13);
      goto LABEL_62;
    case 22:
      if ( v4 >= 0x2C )
      {
        *(_DWORD *)v6 = 0;
        v5 = 44;
        *(_DWORD *)(v6 + 4) = 14;
        *(_QWORD *)(v6 + 8) = *(_QWORD *)(v1 + 32);
        *(_QWORD *)(v6 + 16) = *(_QWORD *)(v1 + 24);
        *(_QWORD *)(v6 + 24) = *(_QWORD *)L"::$DATA";
        *(_DWORD *)(v6 + 32) = *(_DWORD *)L"ATA";
        *(_WORD *)(v6 + 36) = aData[6];
        goto LABEL_62;
      }
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 31;
        goto LABEL_60;
      }
      goto LABEL_62;
    case 35:
      if ( v4 < 8 )
      {
        v3 = -1073741670;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_62;
        }
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v13 = PsGetCurrentThreadId();
        v14 = 29;
        goto LABEL_60;
      }
      *(_DWORD *)v6 = v7;
      *(_DWORD *)(v6 + 4) = 0;
LABEL_50:
      v5 = 8;
      goto LABEL_62;
    case 48:
      v3 = -1073741637;
      goto LABEL_62;
  }
  if ( v2 != 55 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qD(v10, 33, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v11, v2);
    }
    v3 = -1073741822;
    goto LABEL_62;
  }
  if ( v4 >= 0x74 )
  {
    memset((void *)(v6 + 8), 0, 0x6Cu);
    *(_DWORD *)v6 = 7602177;
    v5 = 116;
    *(_DWORD *)(v6 + 4) = 3014656;
    goto LABEL_62;
  }
  v3 = -1073741670;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    v14 = 32;
    goto LABEL_60;
  }
LABEL_62:
  *(_DWORD *)(a1 + 472) -= v5;
  return v3;
}

```

## disassembly

```asm
0x140021c10  mov     [rsp+arg_0], rcx
0x140021c15  push    rbx
0x140021c16  push    rbp
0x140021c17  push    rsi
0x140021c18  push    rdi
0x140021c19  push    r12
0x140021c1b  push    r13
0x140021c1d  push    r14
0x140021c1f  push    r15
0x140021c21  sub     rsp, 38h
0x140021c25  mov     rbp, [rcx+38h]
0x140021c29  xor     r8d, r8d
0x140021c2c  mov     r13d, [rcx+1C0h]
0x140021c33  mov     edi, r8d
0x140021c36  mov     r14d, [rcx+1D8h]
0x140021c3d  mov     r15d, r8d
0x140021c40  mov     rsi, [rcx+1C8h]
0x140021c47  mov     r12d, [rbp+0E8h]
0x140021c4e  lea     eax, [r8+20h]
0x140021c52  test    r12d, r12d
0x140021c55  cmovz   r12d, eax
0x140021c59  mov     rbx, cs:WPP_GLOBAL_Control
0x140021c60  lea     rdx, WPP_GLOBAL_Control
0x140021c67  cmp     rbx, rdx
0x140021c6a  jz      short loc_140021CAB
0x140021c6c  test    dword ptr [rbx+2Ch], 4000h
0x140021c73  jz      short loc_140021CAB
0x140021c75  mov     rbx, [rbx+18h]
0x140021c79  call    cs:__imp_PsGetCurrentThreadId
0x140021c80  nop     dword ptr [rax+rax+00h]
0x140021c85  mov     edx, 18h
0x140021c8a  mov     [rsp+78h+var_58], r13d
0x140021c8f  mov     r9, rax
0x140021c92  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021c99  mov     rcx, rbx
0x140021c9c  call    WPP_SF_qD
0x140021ca1  lea     rdx, WPP_GLOBAL_Control
0x140021ca8  xor     r8d, r8d
0x140021cab  mov     ecx, r13d
0x140021cae  sub     ecx, 4
0x140021cb1  jz      loc_140021FF9
0x140021cb7  sub     ecx, 1
0x140021cba  jz      loc_140021F7F
0x140021cc0  sub     ecx, 1
0x140021cc3  jz      loc_140021F2F
0x140021cc9  sub     ecx, 1
0x140021ccc  jz      loc_140021EDF
0x140021cd2  sub     ecx, 0Eh
0x140021cd5  jz      loc_140021E90
0x140021cdb  sub     ecx, 1
0x140021cde  jz      loc_140021E08
0x140021ce4  sub     ecx, 0Dh
0x140021ce7  jz      loc_140021DBA
0x140021ced  sub     ecx, 0Dh
0x140021cf0  jz      loc_140021DB0
0x140021cf6  cmp     ecx, 7
0x140021cf9  jz      short loc_140021D46
0x140021cfb  mov     rbx, cs:WPP_GLOBAL_Control
0x140021d02  cmp     rbx, rdx
0x140021d05  jz      short loc_140021D3C
0x140021d07  test    dword ptr [rbx+2Ch], 2000h
0x140021d0e  jz      short loc_140021D3C
0x140021d10  mov     rbx, [rbx+18h]
0x140021d14  call    cs:__imp_PsGetCurrentThreadId
0x140021d1b  nop     dword ptr [rax+rax+00h]
0x140021d20  mov     edx, 21h ; '!'
0x140021d25  mov     [rsp+78h+var_58], r13d
0x140021d2a  mov     r9, rax
0x140021d2d  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021d34  mov     rcx, rbx
0x140021d37  call    WPP_SF_qD
0x140021d3c  mov     edi, 0C0000002h
0x140021d41  jmp     loc_140022097
0x140021d46  mov     ebx, 74h ; 't'
0x140021d4b  cmp     r14d, ebx
0x140021d4e  jnb     short loc_140021D8C
0x140021d50  mov     edi, 0C000009Ah
0x140021d55  mov     rbx, cs:WPP_GLOBAL_Control
0x140021d5c  cmp     rbx, rdx
0x140021d5f  jz      loc_140022097
0x140021d65  test    dword ptr [rbx+2Ch], 2000h
0x140021d6c  jz      loc_140022097
0x140021d72  mov     rbx, [rbx+18h]
0x140021d76  call    cs:__imp_PsGetCurrentThreadId
0x140021d7d  nop     dword ptr [rax+rax+00h]
0x140021d82  mov     edx, 20h ; ' '
0x140021d87  jmp     loc_140022032
0x140021d8c  xor     edx, edx; Val
0x140021d8e  lea     rcx, [rsi+8]; void *
0x140021d92  lea     r8d, [rdx+6Ch]; Size
0x140021d96  call    memset
0x140021d9b  mov     dword ptr [rsi], 740001h
0x140021da1  mov     r15d, ebx
0x140021da4  mov     dword ptr [rsi+4], 2E0000h
0x140021dab  jmp     loc_140022097
0x140021db0  mov     edi, 0C00000BBh
0x140021db5  jmp     loc_140022097
0x140021dba  cmp     r14d, 8
0x140021dbe  jnb     short loc_140021DFC
0x140021dc0  mov     edi, 0C000009Ah
0x140021dc5  mov     rbx, cs:WPP_GLOBAL_Control
0x140021dcc  cmp     rbx, rdx
0x140021dcf  jz      loc_140022097
0x140021dd5  test    dword ptr [rbx+2Ch], 2000h
0x140021ddc  jz      loc_140022097
0x140021de2  mov     rbx, [rbx+18h]
0x140021de6  call    cs:__imp_PsGetCurrentThreadId
0x140021ded  nop     dword ptr [rax+rax+00h]
0x140021df2  mov     edx, 1Dh
0x140021df7  jmp     loc_140022032
0x140021dfc  mov     [rsi], r12d
0x140021dff  mov     [rsi+4], r8d
0x140021e03  jmp     loc_140021F74
0x140021e08  cmp     r14d, 2Ch ; ','
0x140021e0c  jnb     short loc_140021E4A
0x140021e0e  mov     edi, 0C000009Ah
0x140021e13  mov     rbx, cs:WPP_GLOBAL_Control
0x140021e1a  cmp     rbx, rdx
0x140021e1d  jz      loc_140022097
0x140021e23  test    dword ptr [rbx+2Ch], 2000h
0x140021e2a  jz      loc_140022097
0x140021e30  mov     rbx, [rbx+18h]
0x140021e34  call    cs:__imp_PsGetCurrentThreadId
0x140021e3b  nop     dword ptr [rax+rax+00h]
0x140021e40  mov     edx, 1Fh
0x140021e45  jmp     loc_140022032
0x140021e4a  mov     [rsi], r8d
0x140021e4d  mov     r15d, 2Ch ; ','
0x140021e53  mov     dword ptr [rsi+4], 0Eh
0x140021e5a  mov     rax, [rbp+20h]
0x140021e5e  mov     [rsi+8], rax
0x140021e62  mov     rax, [rbp+18h]
0x140021e66  mov     [rsi+10h], rax
0x140021e6a  movsd   xmm0, qword ptr cs:aData; "::$DATA"
0x140021e72  movsd   qword ptr [rsi+18h], xmm0
0x140021e77  mov     eax, dword ptr cs:aData+8; "ATA"
0x140021e7d  mov     [rsi+20h], eax
0x140021e80  movzx   eax, word ptr cs:aData+0Ch; "A"
0x140021e87  mov     [rsi+24h], ax
0x140021e8b  jmp     loc_140022097
0x140021e90  cmp     r14d, 8
0x140021e94  jnb     short loc_140021ED2
0x140021e96  mov     edi, 0C000009Ah
0x140021e9b  mov     rbx, cs:WPP_GLOBAL_Control
0x140021ea2  cmp     rbx, rdx
0x140021ea5  jz      loc_140022097
0x140021eab  test    dword ptr [rbx+2Ch], 2000h
0x140021eb2  jz      loc_140022097
0x140021eb8  mov     rbx, [rbx+18h]
0x140021ebc  call    cs:__imp_PsGetCurrentThreadId
0x140021ec3  nop     dword ptr [rax+rax+00h]
0x140021ec8  mov     edx, 1Eh
0x140021ecd  jmp     loc_140022032
0x140021ed2  mov     [rsi], r8d
0x140021ed5  mov     [rsi+4], r8w
0x140021eda  jmp     loc_140021F74
0x140021edf  cmp     r14d, 4
0x140021ee3  jnb     short loc_140021F21
0x140021ee5  mov     edi, 0C000009Ah
0x140021eea  mov     rbx, cs:WPP_GLOBAL_Control
0x140021ef1  cmp     rbx, rdx
0x140021ef4  jz      loc_140022097
0x140021efa  test    dword ptr [rbx+2Ch], 2000h
0x140021f01  jz      loc_140022097
0x140021f07  mov     rbx, [rbx+18h]
0x140021f0b  call    cs:__imp_PsGetCurrentThreadId
0x140021f12  nop     dword ptr [rax+rax+00h]
0x140021f17  mov     edx, 1Ch
0x140021f1c  jmp     loc_140022032
0x140021f21  mov     [rsi], r8d
0x140021f24  mov     r15d, 4
0x140021f2a  jmp     loc_140022097
0x140021f2f  cmp     r14d, 8
0x140021f33  jnb     short loc_140021F71
0x140021f35  mov     edi, 0C000009Ah
0x140021f3a  mov     rbx, cs:WPP_GLOBAL_Control
0x140021f41  cmp     rbx, rdx
0x140021f44  jz      loc_140022097
0x140021f4a  test    dword ptr [rbx+2Ch], 2000h
0x140021f51  jz      loc_140022097
0x140021f57  mov     rbx, [rbx+18h]
0x140021f5b  call    cs:__imp_PsGetCurrentThreadId
0x140021f62  nop     dword ptr [rax+rax+00h]
0x140021f67  mov     edx, 1Bh
0x140021f6c  jmp     loc_140022032
0x140021f71  mov     [rsi], rdi
0x140021f74  mov     r15d, 8
0x140021f7a  jmp     loc_140022097
0x140021f7f  cmp     r14d, 18h
0x140021f83  jnb     short loc_140021FBE
0x140021f85  mov     edi, 0C000009Ah
0x140021f8a  mov     rbx, cs:WPP_GLOBAL_Control
0x140021f91  cmp     rbx, rdx
0x140021f94  jz      loc_140022097
0x140021f9a  test    dword ptr [rbx+2Ch], 2000h
0x140021fa1  jz      loc_140022097
0x140021fa7  mov     rbx, [rbx+18h]
0x140021fab  call    cs:__imp_PsGetCurrentThreadId
0x140021fb2  nop     dword ptr [rax+rax+00h]
0x140021fb7  mov     edx, 1Ah
0x140021fbc  jmp     short loc_140022032
0x140021fbe  mov     eax, [rbp+18h]
0x140021fc1  mov     ecx, 1
0x140021fc6  mov     [rsi], eax
0x140021fc8  mov     eax, [rbp+1Ch]
0x140021fcb  mov     [rsi+4], eax
0x140021fce  mov     eax, [rbp+20h]
0x140021fd1  lea     r15d, [rcx+17h]
0x140021fd5  mov     [rsi+8], eax
0x140021fd8  mov     eax, [rbp+24h]
0x140021fdb  mov     [rsi+0Ch], eax
0x140021fde  mov     al, [rbp+9Ch]
0x140021fe4  and     al, cl
0x140021fe6  mov     [rsi+10h], ecx
0x140021fe9  and     r12b, 10h
0x140021fed  mov     [rsi+14h], al
0x140021ff0  mov     [rsi+15h], r12b
0x140021ff4  jmp     loc_140022097
0x140021ff9  cmp     r14d, 28h ; '('
0x140021ffd  jnb     short loc_140022046
0x140021fff  mov     edi, 0C000009Ah
0x140022004  mov     rbx, cs:WPP_GLOBAL_Control
0x14002200b  cmp     rbx, rdx
0x14002200e  jz      loc_140022097
0x140022014  test    dword ptr [rbx+2Ch], 2000h
0x14002201b  jz      short loc_140022097
0x14002201d  mov     rbx, [rbx+18h]
0x140022021  call    cs:__imp_PsGetCurrentThreadId
0x140022028  nop     dword ptr [rax+rax+00h]
0x14002202d  mov     edx, 19h
0x140022032  mov     r9, rax
0x140022035  lea     r8, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x14002203c  mov     rcx, rbx
0x14002203f  call    WPP_SF_q
0x140022044  jmp     short loc_140022097
0x140022046  mov     eax, [rbp+0E0h]
0x14002204c  mov     r15d, 28h ; '('
0x140022052  mov     [rsi+18h], eax
0x140022055  mov     eax, [rbp+0E4h]
0x14002205b  mov     [rsi+1Ch], eax
0x14002205e  mov     eax, [rbp+0C8h]
0x140022064  mov     [rsi], eax
0x140022066  mov     ecx, [rbp+0CCh]
0x14002206c  mov     [rsi+4], ecx
0x14002206f  mov     ecx, [rbp+0D0h]
0x140022075  mov     [rsi+8], ecx
0x140022078  mov     ecx, [rbp+0D4h]
0x14002207e  mov     [rsi+0Ch], ecx
0x140022081  mov     ecx, [rbp+0D8h]
0x140022087  mov     [rsi+10h], ecx
0x14002208a  mov     ecx, [rbp+0DCh]
0x140022090  mov     [rsi+14h], ecx
0x140022093  mov     [rsi+20h], r12d
0x140022097  mov     rax, [rsp+78h+arg_0]
0x14002209f  sub     [rax+1D8h], r15d
0x1400220a6  mov     eax, edi
0x1400220a8  add     rsp, 38h
0x1400220ac  pop     r15
0x1400220ae  pop     r14
0x1400220b0  pop     r13
0x1400220b2  pop     r12
0x1400220b4  pop     rdi
0x1400220b5  pop     rsi
0x1400220b6  pop     rbp
0x1400220b7  pop     rbx
0x1400220b8  retn
```
