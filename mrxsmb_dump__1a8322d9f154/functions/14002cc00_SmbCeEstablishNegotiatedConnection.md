# SmbCeEstablishNegotiatedConnection

- ea: `0x14002cc00`
- end: `0x14002d142`
- name: `SmbCeEstablishNegotiatedConnection`
- size: `1346`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _WORD *, _BYTE *, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140024330`
- `0x1400463a8`

## callees

- `0x14002cc00`
- `0x140034e10`
- `0x140038068`
- `0x140039fa8`
- `0x14003e14c`
- `0x1400422dc`
- `0x1400423fc`
- `0x14004ace4`
- `0x14008f6f0`
- `0x140090350`
- `0x140094bf0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002cf97`
- `ntoskrnl!ExAllocatePool2` at `0x14002cf97`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002cf7b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002cf7b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002cdd5`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002cdd5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002cde8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002cde8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d131`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d131`
- `rdbss!RxDiagnosticTrace` at `0x14002ce66`
- `rdbss!RxDiagnosticTrace` at `0x14002ce66`

## pseudocode

```c
__int64 __fastcall SmbCeEstablishNegotiatedConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        _BYTE *a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v7; // ebx
  _QWORD *v8; // r14
  int v9; // ebp
  unsigned int *v11; // rcx
  _BYTE *v13; // r15
  __int64 v14; // r13
  bool v15; // bl
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // edx
  int v20; // r8d
  _WORD *v21; // rax
  _QWORD *v22; // rbp
  char v23; // r12
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *Pool2; // rax
  void *v29; // rsi
  unsigned __int16 *v30; // r11
  char v31; // bl
  int v32; // eax
  char v33; // [rsp+58h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-90h]
  __int64 v35; // [rsp+70h] [rbp-88h]
  __int64 v36; // [rsp+78h] [rbp-80h]
  __int64 v37; // [rsp+80h] [rbp-78h]
  KIRQL v38; // [rsp+90h] [rbp-68h]
  PVOID P; // [rsp+98h] [rbp-60h]
  __int64 v40; // [rsp+A0h] [rbp-58h]
  UNICODE_STRING v41; // [rsp+A8h] [rbp-50h] BYREF
  char v42; // [rsp+100h] [rbp+8h]

  v7 = *(_DWORD *)(a1 + 828);
  v8 = 0;
  v9 = (int)a4;
  v41 = 0;
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZd(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        (unsigned int)WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
        a1,
        a1 + 80,
        v7);
LABEL_6:
      v11 = (unsigned int *)(a7 + 8);
LABEL_7:
      *v11 = v7;
      v11[1] = 0;
      return v7;
    }
    goto LABEL_68;
  }
  v13 = a5;
  v14 = *(_QWORD *)(a1 + 24);
  P = 0;
  v42 = 0;
  v15 = a5 && (*a5 & 1) != 0;
  v16 = *(unsigned __int16 *)(a2 + 2);
  if ( (_WORD)v16 )
    v17 = a2 + v16;
  else
    v17 = 0;
  v18 = v17 + 32;
  if ( !v17 )
    v18 = 0;
  v40 = v18;
  if ( a4 && *a4 )
  {
    P = (PVOID)SmbCeFindTransport(v14, 0, a4);
    if ( !P )
    {
      v7 = -1073741252;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_ZqD(WPP_GLOBAL_Control->AttachedDevice, v19, v20, v9, a1);
        goto LABEL_6;
      }
LABEL_68:
      v11 = (unsigned int *)(a7 + 8);
      if ( v8 )
      {
        *(_QWORD *)v11 = v8[1];
        ExFreePoolWithTag(v8, 0x6D536243u);
        return v7;
      }
      goto LABEL_7;
    }
    v42 = 1;
  }
  v21 = *(_WORD **)(a1 + 64);
  v22 = 0;
  v41 = *(UNICODE_STRING *)(a1 + 128);
  v23 = v21 && (*v21 > 2u || *v21 >= 2u && (v21[1] || v21[2] >= 2u)) || *(_WORD *)(a1 + 880) != 0;
  v38 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v14 + 1920));
  *(_DWORD *)(v14 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( !v15 )
  {
    v24 = *(_QWORD *)(a1 + 576);
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids, v24, a1);
      }
      RxDiagnosticTrace(*(_QWORD *)(a1 + 16), 1, "Free ConnectionInfo %p", *(const void **)(a1 + 576));
      SmbCeDereferenceConnectionInfo(*(PVOID *)(a1 + 576));
      *(_DWORD *)(a1 + 4) &= ~1u;
      *(_QWORD *)(a1 + 576) = 0;
      v25 = *(_QWORD *)(a1 + 528);
      if ( v25 != a1 + 528 )
      {
        v26 = v25 - 392;
        while ( v26 )
        {
          v27 = *(_QWORD *)(v26 + 392);
          *(_DWORD *)(v26 + 4) &= ~8u;
          v26 = 0;
          if ( v27 != a1 + 528 )
            v26 = v27 - 392;
        }
      }
    }
  }
  if ( !a5 )
  {
    v22 = (_QWORD *)_InterlockedExchange64((volatile __int64 *)(a1 + 600), 0);
    if ( v22 )
      v13 = (_BYTE *)v22[1];
  }
  if ( (*(_DWORD *)(a1 + 752) >= 2u || *(_DWORD *)(a1 + 756) >= 2u || *(_DWORD *)(a1 + 760) >= 2u)
    && (((*(_BYTE *)(a1 + 737) & 0xC) - 4) & 0xF7) == 0 )
  {
    ++*(_DWORD *)(a1 + 720);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
        a1,
        *(_DWORD *)(a1 + 720));
    }
    *(_QWORD *)(a1 + 752) = 0;
    *(_DWORD *)(a1 + 760) = 0;
  }
  *(_DWORD *)(v14 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v14 + 1920), v38);
  Pool2 = (_QWORD *)ExAllocatePool2(64, 48, 1834181187);
  v8 = Pool2;
  if ( Pool2 )
  {
    Pool2[4] = 0;
    *Pool2 = SmbCeCompleteTransportConnectionEstablishment;
    Pool2[2] = a7;
    Pool2[3] = a3 | !v15;
    Pool2[5] = a6;
    v37 = a1 + 860;
    v30 = (unsigned __int16 *)(a1 + 880);
    v36 = a1 + 852;
    v35 = *(_QWORD *)(a1 + 520);
    v34 = a1 + 836;
    v31 = *(_BYTE *)(a1 + 738) & 1;
    v33 = (*(_BYTE *)(a1 + 737) & 3) == 3;
    v32 = *(_DWORD *)(a1 + 720);
    v29 = P;
    v7 = VctEstablishConnection(
           v8 + 4,
           &v41,
           v40,
           (__int64)P,
           v23,
           v31,
           v13,
           v30,
           v32,
           a2,
           (__int64)v8,
           v33,
           v14,
           v34,
           v35,
           v36,
           v37);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids);
    }
    v29 = P;
    v7 = -1073741670;
  }
  if ( v22 )
    SmbCeDeReferenceMoveClientAddrList(v22);
  if ( v42 )
    SmbCepDereferenceTransport(v29);
  if ( v7 != 259 )
    goto LABEL_68;
  return v7;
}

```

## disassembly

```asm
0x14002cc00  mov     [rsp+arg_10], r8
0x14002cc05  mov     [rsp+arg_8], rdx
0x14002cc0a  push    rbx
0x14002cc0b  push    rbp
0x14002cc0c  push    rsi
0x14002cc0d  push    rdi
0x14002cc0e  push    r13
0x14002cc10  push    r14
0x14002cc12  push    r15
0x14002cc14  sub     rsp, 0C0h
0x14002cc1b  mov     ebx, [rcx+33Ch]
0x14002cc21  xor     r14d, r14d
0x14002cc24  xorps   xmm0, xmm0
0x14002cc27  mov     rbp, r9
0x14002cc2a  mov     rsi, rcx
0x14002cc2d  movups  [rsp+0F8h+var_50], xmm0
0x14002cc35  test    ebx, ebx
0x14002cc37  jns     short loc_14002CCB4
0x14002cc39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002cc40  lea     rdi, WPP_GLOBAL_Control
0x14002cc47  cmp     rcx, rdi
0x14002cc4a  jz      loc_14002D10D
0x14002cc50  mov     eax, [rcx+2Ch]
0x14002cc53  test    al, 1
0x14002cc55  jz      loc_14002D10D
0x14002cc5b  cmp     byte ptr [rcx+29h], 1
0x14002cc5f  jb      loc_14002D10D
0x14002cc65  mov     rcx, [rcx+18h]
0x14002cc69  lea     rax, [rsi+50h]
0x14002cc6d  mov     edx, 0Eh
0x14002cc72  mov     [rsp+0F8h+var_D0], ebx
0x14002cc76  mov     r9, rsi
0x14002cc79  mov     [rsp+0F8h+var_D8], rax
0x14002cc7e  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002cc85  call    WPP_SF_qZd
0x14002cc8a  mov     rcx, [rsp+0F8h+arg_30]
0x14002cc92  add     rcx, 8
0x14002cc96  mov     [rcx], ebx
0x14002cc98  mov     dword ptr [rcx+4], 0
0x14002cc9f  mov     eax, ebx
0x14002cca1  add     rsp, 0C0h
0x14002cca8  pop     r15
0x14002ccaa  pop     r14
0x14002ccac  pop     r13
0x14002ccae  pop     rdi
0x14002ccaf  pop     rsi
0x14002ccb0  pop     rbp
0x14002ccb1  pop     rbx
0x14002ccb2  retn
0x14002ccb4  mov     r15, [rsp+0F8h+arg_20]
0x14002ccbc  mov     r13, [rcx+18h]
0x14002ccc0  mov     [rsp+0F8h+P], r14
0x14002ccc8  mov     [rsp+0F8h+arg_0], r14b
0x14002ccd0  test    r15, r15
0x14002ccd3  jz      short loc_14002CCDF
0x14002ccd5  test    byte ptr [r15], 1
0x14002ccd9  jz      short loc_14002CCDF
0x14002ccdb  mov     bl, 1
0x14002ccdd  jmp     short loc_14002CCE1
0x14002ccdf  xor     bl, bl
0x14002cce1  movzx   eax, word ptr [rdx+2]
0x14002cce5  test    ax, ax
0x14002cce8  jnz     short loc_14002CCEE
0x14002ccea  xor     ecx, ecx
0x14002ccec  jmp     short loc_14002CCF2
0x14002ccee  lea     rcx, [rdx+rax]
0x14002ccf2  xor     eax, eax
0x14002ccf4  lea     rdx, [rcx+20h]
0x14002ccf8  test    rcx, rcx
0x14002ccfb  cmovz   rdx, rax
0x14002ccff  mov     [rsp+0F8h+var_58], rdx
0x14002cd07  test    rbp, rbp
0x14002cd0a  jz      short loc_14002CD7B
0x14002cd0c  cmp     [r9], ax
0x14002cd10  jz      short loc_14002CD7B
0x14002cd12  mov     r8, rbp
0x14002cd15  xor     edx, edx
0x14002cd17  mov     rcx, r13
0x14002cd1a  call    SmbCeFindTransport
0x14002cd1f  mov     [rsp+0F8h+P], rax
0x14002cd27  test    rax, rax
0x14002cd2a  jnz     short loc_14002CD73
0x14002cd2c  mov     ebx, 0C000023Ch
0x14002cd31  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002cd38  lea     rdi, WPP_GLOBAL_Control
0x14002cd3f  cmp     rcx, rdi
0x14002cd42  jz      loc_14002D10D
0x14002cd48  mov     eax, [rcx+2Ch]
0x14002cd4b  test    al, 1
0x14002cd4d  jz      loc_14002D10D
0x14002cd53  cmp     byte ptr [rcx+29h], 1
0x14002cd57  jb      loc_14002D10D
0x14002cd5d  mov     rcx, [rcx+18h]
0x14002cd61  mov     r9, rbp
0x14002cd64  mov     [rsp+0F8h+var_D8], rsi
0x14002cd69  call    WPP_SF_ZqD
0x14002cd6e  jmp     loc_14002CC8A
0x14002cd73  mov     [rsp+0F8h+arg_0], 1
0x14002cd7b  movups  xmm0, xmmword ptr [rsi+80h]
0x14002cd82  mov     rax, [rsi+40h]
0x14002cd86  xor     ebp, ebp
0x14002cd88  mov     [rsp+0F8h+arg_18], r12
0x14002cd90  mov     edx, 1
0x14002cd95  movups  [rsp+0F8h+var_50], xmm0
0x14002cd9d  test    rax, rax
0x14002cda0  jz      short loc_14002CDBD
0x14002cda2  cmp     word ptr [rax], 2
0x14002cda6  ja      short loc_14002CDB7
0x14002cda8  jb      short loc_14002CDBD
0x14002cdaa  cmp     [rax+2], bp
0x14002cdae  ja      short loc_14002CDB7
0x14002cdb0  cmp     word ptr [rax+4], 2
0x14002cdb5  jb      short loc_14002CDBD
0x14002cdb7  movzx   r12d, dl
0x14002cdbb  jmp     short loc_14002CDCE
0x14002cdbd  xor     al, al
0x14002cdbf  cmp     [rsi+370h], bp
0x14002cdc6  movzx   r12d, al
0x14002cdca  cmovnz  r12d, edx
0x14002cdce  lea     rcx, [r13+780h]; SpinLock
0x14002cdd5  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002cddc  nop     dword ptr [rax+rax+00h]
0x14002cde1  mov     [rsp+0F8h+var_68], al
0x14002cde8  call    cs:__imp_PsGetCurrentThreadId
0x14002cdef  nop     dword ptr [rax+rax+00h]
0x14002cdf4  mov     [r13+930h], eax
0x14002cdfb  lea     rdi, WPP_GLOBAL_Control
0x14002ce02  test    bl, bl
0x14002ce04  jnz     loc_14002CED0
0x14002ce0a  mov     r9, [rsi+240h]
0x14002ce11  test    r9, r9
0x14002ce14  jz      loc_14002CED0
0x14002ce1a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ce21  cmp     rcx, rdi
0x14002ce24  jz      short loc_14002CE4F
0x14002ce26  test    dword ptr [rcx+2Ch], 100h
0x14002ce2d  jz      short loc_14002CE4F
0x14002ce2f  cmp     byte ptr [rcx+29h], 2
0x14002ce33  jb      short loc_14002CE4F
0x14002ce35  mov     rcx, [rcx+18h]
0x14002ce39  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002ce40  mov     edx, 10h
0x14002ce45  mov     [rsp+0F8h+var_D8], rsi
0x14002ce4a  call    WPP_SF_qq
0x14002ce4f  mov     r9, [rsi+240h]
0x14002ce56  lea     r8, aFreeConnection; "Free ConnectionInfo %p"
0x14002ce5d  mov     rcx, [rsi+10h]
0x14002ce61  mov     edx, 1
0x14002ce66  call    cs:__imp_RxDiagnosticTrace
0x14002ce6d  nop     dword ptr [rax+rax+00h]
0x14002ce72  mov     rcx, [rsi+240h]; P
0x14002ce79  call    SmbCeDereferenceConnectionInfo
0x14002ce7e  and     dword ptr [rsi+4], 0FFFFFFFEh
0x14002ce82  lea     r8, [rsi+210h]
0x14002ce89  mov     [rsi+240h], rbp
0x14002ce90  mov     rdx, [r8]
0x14002ce93  cmp     rdx, r8
0x14002ce96  jz      short loc_14002CED0
0x14002ce98  add     rdx, 0FFFFFFFFFFFFFE78h
0x14002ce9f  jz      short loc_14002CED0
0x14002cea1  nop     dword ptr [rax+00h]
0x14002cea5  nop     word ptr [rax+rax+00000000h]
0x14002ceb0  mov     rcx, [rdx+188h]
0x14002ceb7  and     dword ptr [rdx+4], 0FFFFFFF7h
0x14002cebb  xor     edx, edx
0x14002cebd  cmp     rcx, r8
0x14002cec0  lea     rax, [rcx-188h]
0x14002cec7  cmovnz  rdx, rax
0x14002cecb  test    rdx, rdx
0x14002cece  jnz     short loc_14002CEB0
0x14002ced0  test    r15, r15
0x14002ced3  jnz     short loc_14002CEE5
0x14002ced5  xchg    rbp, [rsi+258h]
0x14002cedc  test    rbp, rbp
0x14002cedf  jz      short loc_14002CEE5
0x14002cee1  mov     r15, [rbp+8]
0x14002cee5  cmp     dword ptr [rsi+2F0h], 2
0x14002ceec  jnb     short loc_14002CF00
0x14002ceee  cmp     dword ptr [rsi+2F4h], 2
0x14002cef5  jnb     short loc_14002CF00
0x14002cef7  cmp     dword ptr [rsi+2F8h], 2
0x14002cefe  jb      short loc_14002CF61
0x14002cf00  movzx   eax, byte ptr [rsi+2E1h]
0x14002cf07  and     al, 0Ch
0x14002cf09  sub     al, 4
0x14002cf0b  test    al, 0F7h
0x14002cf0d  jnz     short loc_14002CF61
0x14002cf0f  inc     dword ptr [rsi+2D0h]
0x14002cf15  mov     r8d, [rsi+2D0h]
0x14002cf1c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002cf23  cmp     rcx, rdi
0x14002cf26  jz      short loc_14002CF52
0x14002cf28  mov     eax, [rcx+2Ch]
0x14002cf2b  test    al, 4
0x14002cf2d  jz      short loc_14002CF52
0x14002cf2f  cmp     byte ptr [rcx+29h], 4
0x14002cf33  jb      short loc_14002CF52
0x14002cf35  mov     rcx, [rcx+18h]
0x14002cf39  mov     edx, 11h
0x14002cf3e  mov     dword ptr [rsp+0F8h+var_D8], r8d
0x14002cf43  mov     r9, rsi
0x14002cf46  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002cf4d  call    WPP_SF_qD
0x14002cf52  xor     eax, eax
0x14002cf54  mov     [rsi+2F0h], rax
0x14002cf5b  mov     [rsi+2F8h], eax
0x14002cf61  movzx   edx, [rsp+0F8h+var_68]; OldIrql
0x14002cf69  lea     rcx, [r13+780h]; SpinLock
0x14002cf70  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002cf7b  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002cf82  nop     dword ptr [rax+rax+00h]
0x14002cf87  mov     edx, 30h ; '0'
0x14002cf8c  mov     ecx, 40h ; '@'
0x14002cf91  mov     r8d, 6D536243h
0x14002cf97  call    cs:__imp_ExAllocatePool2
0x14002cf9e  nop     dword ptr [rax+rax+00h]
0x14002cfa3  mov     r14, rax
0x14002cfa6  test    rax, rax
0x14002cfa9  jnz     short loc_14002CFEB
0x14002cfab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002cfb2  cmp     rcx, rdi
0x14002cfb5  jz      short loc_14002CFD9
0x14002cfb7  mov     eax, [rcx+2Ch]
0x14002cfba  test    al, 1
0x14002cfbc  jz      short loc_14002CFD9
0x14002cfbe  cmp     byte ptr [rcx+29h], 1
0x14002cfc2  jb      short loc_14002CFD9
0x14002cfc4  mov     rcx, [rcx+18h]
0x14002cfc8  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002cfcf  mov     edx, 12h
0x14002cfd4  call    WPP_SF_
0x14002cfd9  mov     rsi, [rsp+0F8h+P]
0x14002cfe1  mov     ebx, 0C000009Ah
0x14002cfe6  jmp     loc_14002D0DA
0x14002cfeb  lea     rax, SmbCeCompleteTransportConnectionEstablishment
0x14002cff2  mov     qword ptr [r14+20h], 0
0x14002cffa  mov     [r14], rax
0x14002cffd  mov     rax, [rsp+0F8h+arg_30]
0x14002d005  mov     [r14+10h], rax
0x14002d009  movzx   eax, bl
0x14002d00c  xor     rax, 1
0x14002d010  or      rax, [rsp+0F8h+arg_10]
0x14002d018  mov     [r14+18h], rax
0x14002d01c  mov     rax, [rsp+0F8h+arg_28]
0x14002d024  mov     [r14+28h], rax
0x14002d028  movzx   eax, byte ptr [rsi+2E1h]
0x14002d02f  lea     rcx, [rsi+35Ch]
0x14002d036  movzx   ebx, byte ptr [rsi+2E2h]
0x14002d03d  lea     rdx, [rsi+354h]
0x14002d044  mov     r8, [rsp+0F8h+var_58]
0x14002d04c  lea     r10, [rsi+344h]
0x14002d053  mov     [rsp+0F8h+var_78], rcx
0x14002d05b  lea     r11, [rsi+370h]
0x14002d062  mov     [rsp+0F8h+var_80], rdx
0x14002d067  lea     rcx, [r14+20h]
0x14002d06b  and     al, 3
0x14002d06d  lea     rdx, [rsp+0F8h+var_50]
0x14002d075  cmp     al, 3
0x14002d077  mov     rax, [rsi+208h]
0x14002d07e  mov     [rsp+0F8h+var_88], rax
0x14002d083  mov     rax, [rsp+0F8h+arg_8]
0x14002d08b  setz    r9b
0x14002d08f  mov     [rsp+0F8h+var_90], r10
0x14002d094  and     bl, 1
0x14002d097  mov     [rsp+0F8h+var_98], r13
0x14002d09c  mov     [rsp+0F8h+var_A0], r9b
0x14002d0a1  mov     [rsp+0F8h+var_A8], r14
0x14002d0a6  mov     [rsp+0F8h+var_B0], rax
0x14002d0ab  mov     eax, [rsi+2D0h]
0x14002d0b1  mov     rsi, [rsp+0F8h+P]
0x14002d0b9  mov     [rsp+0F8h+var_B8], eax
0x14002d0bd  mov     r9, rsi
0x14002d0c0  mov     [rsp+0F8h+var_C0], r11
0x14002d0c5  mov     [rsp+0F8h+var_C8], r15
0x14002d0ca  mov     byte ptr [rsp+0F8h+var_D0], bl
0x14002d0ce  mov     byte ptr [rsp+0F8h+var_D8], r12b
0x14002d0d3  call    VctEstablishConnection
0x14002d0d8  mov     ebx, eax
0x14002d0da  mov     r12, [rsp+0F8h+arg_18]
0x14002d0e2  test    rbp, rbp
0x14002d0e5  jz      short loc_14002D0EF
0x14002d0e7  mov     rcx, rbp; P
0x14002d0ea  call    SmbCeDeReferenceMoveClientAddrList
0x14002d0ef  cmp     [rsp+0F8h+arg_0], 0
0x14002d0f7  jz      short loc_14002D101
0x14002d0f9  mov     rcx, rsi; P
0x14002d0fc  call    SmbCepDereferenceTransport
0x14002d101  cmp     ebx, 103h
0x14002d107  jz      loc_14002CC9F
0x14002d10d  mov     rcx, [rsp+0F8h+arg_30]
0x14002d115  add     rcx, 8
0x14002d119  test    r14, r14
0x14002d11c  jz      loc_14002CC96
0x14002d122  mov     rax, [r14+8]
0x14002d126  mov     edx, 6D536243h; Tag
0x14002d12b  mov     [rcx], rax
0x14002d12e  mov     rcx, r14; P
0x14002d131  call    cs:__imp_ExFreePoolWithTag
0x14002d138  nop     dword ptr [rax+rax+00h]
0x14002d13d  jmp     loc_14002CC9F
  ... truncated ...
```
