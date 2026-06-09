# KbdHid_IOCTL

- ea: `0x140003470`
- end: `0x1400039fd`
- name: `KbdHid_IOCTL`
- size: `1421`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003040`
- `0x140003470`
- `0x140003a10`
- `0x140005490`
- `0x140005928`
- `0x140005a0c`
- `0x140005acc`
- `0x140005ba8`
- `0x140005c9c`
- `0x140007240`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400034cf`
- `ntoskrnl!IofCompleteRequest` at `0x14000397d`
- `ntoskrnl!IofCompleteRequest` at `0x1400034cf`
- `ntoskrnl!IofCompleteRequest` at `0x14000397d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003999`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003999`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400034b5`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400034b5`

## pseudocode

```c
__int64 __fastcall KbdHid_IOCTL(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  char v4; // r13
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  unsigned int v11; // r14d
  _WORD *v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx
  int v15; // r9d
  int v16; // eax
  int v17; // r8d
  _OWORD *v18; // rax
  int Completion; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int16 v22; // cx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // edx
  int RemlockSize; // [rsp+20h] [rbp-48h]
  char v28; // [rsp+30h] [rbp-38h]
  char v29; // [rsp+38h] [rbp-30h]

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  v4 = a1;
  *(_QWORD *)(a2 + 56) = 0;
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), (PVOID)a2, File, 1u, 0x20u);
  v10 = v6;
  if ( v6 < 0 )
  {
    *(_DWORD *)(a2 + 48) = v6;
    IofCompleteRequest((PIRP)a2, 0);
    return v10;
  }
  v11 = *(_DWORD *)(v3 + 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqL(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v9, RemlockSize, v4, a2, *(_DWORD *)(v3 + 24));
  if ( v11 == 720900 )
  {
    if ( *(_DWORD *)(v3 + 16) >= 6u )
    {
      v21 = *(_QWORD *)(a2 + 24);
      v22 = *(_WORD *)(v21 + 2);
      if ( v22 || *(_WORD *)(v21 + 4) )
      {
        if ( v22 >= *(_WORD *)(v2 + 298) && v22 <= *(_WORD *)(v2 + 304) )
        {
          v7 = *(unsigned __int16 *)(v21 + 4);
          if ( (unsigned __int16)v7 >= *(_WORD *)(v2 + 300) && (unsigned __int16)v7 <= *(_WORD *)(v2 + 306) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v7) = 4;
              WPP_RECORDER_SF_dd(WPP_GLOBAL_Control->DeviceExtension, v7, v8, 20, RemlockSize, v22, *(_WORD *)(v21 + 4));
            }
            v23 = *(_QWORD *)(a2 + 24);
            *(_DWORD *)(v2 + 356) = *(_DWORD *)v23;
            *(_WORD *)(v2 + 360) = *(_WORD *)(v23 + 4);
            *(_DWORD *)(v2 + 504) = 0x3E8u / *(unsigned __int16 *)(*(_QWORD *)(a2 + 24) + 2LL);
            v24 = -10000 * *(unsigned __int16 *)(*(_QWORD *)(a2 + 24) + 4LL);
            *(_DWORD *)(v2 + 500) = -1;
            *(_DWORD *)(v2 + 496) = v24;
            goto LABEL_73;
          }
        }
        v10 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v13 = 19;
          goto LABEL_72;
        }
      }
    }
    else
    {
      v10 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 18;
        goto LABEL_72;
      }
    }
    goto LABEL_73;
  }
  if ( v11 > 0xB0200 )
  {
    switch ( v11 )
    {
      case 0xB0203u:
        if ( *(_QWORD *)(v2 + 144) )
        {
          v10 = -1073741757;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v13 = 12;
            goto LABEL_72;
          }
        }
        else if ( *(_DWORD *)(v3 + 16) >= 0x10u )
        {
          v10 = 0;
          *(_OWORD *)(v2 + 136) = *(_OWORD *)*(_QWORD *)(v3 + 32);
        }
        else
        {
          v10 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v13 = 13;
            goto LABEL_72;
          }
        }
        break;
      case 0xB0403u:
        v10 = -1073741822;
        break;
      case 0xB0803u:
      case 0xB1003u:
        v10 = -1073741637;
        break;
      default:
        goto LABEL_47;
    }
    goto LABEL_73;
  }
  if ( v11 == 721408 )
  {
    if ( *(_DWORD *)(v3 + 8) >= 7u )
    {
      Completion = KbdHid_WaitForExtendedAttributesQueryCompletion(v2);
      v10 = Completion;
      if ( Completion >= 0 )
      {
        v20 = *(_QWORD *)(a2 + 24);
        *(_DWORD *)v20 = *(_DWORD *)(v2 + 308);
        *(_WORD *)(v20 + 4) = *(_WORD *)(v2 + 312);
        *(_BYTE *)(v20 + 6) = *(_BYTE *)(v2 + 314);
        *(_QWORD *)(a2 + 56) = 7;
        goto LABEL_73;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      v29 = Completion;
      v15 = 22;
      v28 = a2;
    }
    else
    {
      v10 = -1073741789;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_73;
      v29 = 35;
      v15 = 21;
      v28 = a2;
    }
    goto LABEL_30;
  }
  if ( v11 == 720896 )
  {
    if ( *(_DWORD *)(v3 + 8) >= 0x1Cu )
    {
      v16 = KbdHid_WaitForExtendedAttributesQueryCompletion(v2);
      v10 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Lqd(WPP_GLOBAL_Control->DeviceExtension, 3, v17, 15, RemlockSize, 0, a2, v16);
        v10 = 0;
      }
      v18 = *(_OWORD **)(a2 + 24);
      *v18 = *(_OWORD *)(v2 + 280);
      *(_OWORD *)((char *)v18 + 12) = *(_OWORD *)(v2 + 292);
      *(_QWORD *)(a2 + 56) = 28;
      goto LABEL_73;
    }
    v10 = -1073741789;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    v29 = 35;
    v15 = 14;
    v28 = a2;
LABEL_30:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_Lqd(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v15, RemlockSize, 0, v28, v29);
    goto LABEL_73;
  }
  if ( v11 != 720904 )
  {
    if ( v11 != 720928 )
    {
      if ( v11 == 720960 )
      {
        if ( *(_DWORD *)(v3 + 8) >= 4u )
        {
          v10 = 0;
          **(_DWORD **)(a2 + 24) = *(_DWORD *)(v2 + 352);
          *(_QWORD *)(a2 + 56) = 4;
        }
        else
        {
          v10 = -1073741789;
        }
        goto LABEL_73;
      }
      if ( v11 == 721024 )
      {
        if ( *(_DWORD *)(v3 + 8) >= 0xEu )
        {
          v12 = *(_WORD **)(a2 + 24);
          *v12 = 3;
          memmove(v12 + 1, qword_1400093A8, 0xCu);
          v10 = 0;
          *(_QWORD *)(a2 + 56) = 14;
        }
        else
        {
          v10 = -1073741789;
        }
        goto LABEL_73;
      }
LABEL_47:
      v10 = -1073741808;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Dd(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v9, RemlockSize, v11);
      goto LABEL_73;
    }
    if ( *(_DWORD *)(v3 + 8) >= 6u )
    {
      v10 = 0;
      v14 = *(_QWORD *)(a2 + 24);
      *(_DWORD *)v14 = *(_DWORD *)(v2 + 356);
      *(_WORD *)(v14 + 4) = *(_WORD *)(v2 + 360);
      *(_QWORD *)(a2 + 56) = 6;
    }
    else
    {
      v10 = -1073741789;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 17;
LABEL_72:
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(WPP_GLOBAL_Control->DeviceExtension, v7, 3, v13, RemlockSize, v10);
        goto LABEL_73;
      }
    }
    goto LABEL_73;
  }
  if ( *(_DWORD *)(v3 + 16) < 4u )
  {
    v10 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 16;
      goto LABEL_72;
    }
LABEL_73:
    *(_DWORD *)(a2 + 48) = v10;
    IofCompleteRequest((PIRP)a2, 0);
    goto LABEL_74;
  }
  v10 = KbdHid_SetLedIndicators(v2, *(_QWORD *)(a2 + 24), (IRP *)a2);
LABEL_74:
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 152), (PVOID)a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v25) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v25,
      3,
      24,
      (__int64)WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x140003470  mov     [rsp+arg_10], rbx
0x140003475  push    rbp
0x140003476  push    rsi
0x140003477  push    rdi
0x140003478  push    r13
0x14000347a  push    r15
0x14000347c  sub     rsp, 40h
0x140003480  mov     rsi, [rcx+40h]
0x140003484  lea     r8, File; File
0x14000348b  mov     rbp, [rdx+0B8h]
0x140003492  mov     r13, rcx
0x140003495  mov     r9d, 1; Line
0x14000349b  mov     qword ptr [rdx+38h], 0
0x1400034a3  mov     rdi, rdx
0x1400034a6  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x1400034ae  lea     rcx, [rsi+98h]; RemoveLock
0x1400034b5  call    cs:__imp_IoAcquireRemoveLockEx
0x1400034bc  nop     dword ptr [rax+rax+00h]
0x1400034c1  mov     ebx, eax
0x1400034c3  test    eax, eax
0x1400034c5  jns     short loc_1400034E0
0x1400034c7  xor     edx, edx; PriorityBoost
0x1400034c9  mov     [rdi+30h], eax
0x1400034cc  mov     rcx, rdi; Irp
0x1400034cf  call    cs:__imp_IofCompleteRequest
0x1400034d6  nop     dword ptr [rax+rax+00h]
0x1400034db  jmp     loc_1400039E6
0x1400034e0  mov     [rsp+68h+arg_0], r12
0x1400034e5  mov     [rsp+68h+arg_8], r14
0x1400034ea  mov     r14d, [rbp+18h]
0x1400034ee  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400034f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400034fc  jz      short loc_14000351D
0x1400034fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140003505  mov     dword ptr [rsp+68h+var_30], r14d
0x14000350a  mov     [rsp+68h+var_38], rdi
0x14000350f  mov     [rsp+68h+var_40], r13
0x140003514  mov     rcx, [rcx+40h]
0x140003518  call    WPP_RECORDER_SF_qqL
0x14000351d  mov     r13d, 3
0x140003523  cmp     r14d, 0B0004h
0x14000352a  jz      loc_140003863
0x140003530  cmp     r14d, 0B0200h
0x140003537  ja      loc_1400037A0
0x14000353d  jz      loc_140003707
0x140003543  mov     eax, r14d
0x140003546  sub     eax, 0B0000h
0x14000354b  jz      loc_140003657
0x140003551  sub     eax, 8
0x140003554  jz      loc_14000361E
0x14000355a  sub     eax, 18h
0x14000355d  jz      short loc_1400035D5
0x14000355f  sub     eax, 20h ; ' '
0x140003562  jz      short loc_1400035AA
0x140003564  cmp     eax, 40h ; '@'
0x140003567  jnz     loc_1400037C4
0x14000356d  cmp     dword ptr [rbp+8], 0Eh
0x140003571  jnb     short loc_14000357D
0x140003573  mov     ebx, 0C0000023h
0x140003578  jmp     loc_140003975
0x14000357d  mov     rcx, [rdi+18h]
0x140003581  lea     rdx, qword_1400093A8; Src
0x140003588  mov     r8d, 0Ch; Size
0x14000358e  mov     [rcx], r13w
0x140003592  add     rcx, 2; void *
0x140003596  call    memmove
0x14000359b  xor     ebx, ebx
0x14000359d  mov     qword ptr [rdi+38h], 0Eh
0x1400035a5  jmp     loc_140003975
0x1400035aa  cmp     dword ptr [rbp+8], 4
0x1400035ae  jnb     short loc_1400035BA
0x1400035b0  mov     ebx, 0C0000023h
0x1400035b5  jmp     loc_140003975
0x1400035ba  mov     eax, [rsi+160h]
0x1400035c0  xor     ebx, ebx
0x1400035c2  mov     rcx, [rdi+18h]
0x1400035c6  mov     [rcx], eax
0x1400035c8  mov     qword ptr [rdi+38h], 4
0x1400035d0  jmp     loc_140003975
0x1400035d5  cmp     dword ptr [rbp+8], 6
0x1400035d9  jnb     short loc_1400035F8
0x1400035db  mov     ebx, 0C0000023h
0x1400035e0  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400035e7  jz      loc_140003975
0x1400035ed  mov     r9d, 11h
0x1400035f3  jmp     loc_14000395C
0x1400035f8  mov     eax, [rsi+164h]
0x1400035fe  xor     ebx, ebx
0x140003600  mov     rcx, [rdi+18h]
0x140003604  mov     [rcx], eax
0x140003606  movzx   eax, word ptr [rsi+168h]
0x14000360d  mov     [rcx+4], ax
0x140003611  mov     qword ptr [rdi+38h], 6
0x140003619  jmp     loc_140003975
0x14000361e  cmp     dword ptr [rbp+10h], 4
0x140003622  jnb     short loc_140003641
0x140003624  mov     ebx, 0C000000Dh
0x140003629  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140003630  jz      loc_140003975
0x140003636  mov     r9d, 10h
0x14000363c  jmp     loc_14000395C
0x140003641  mov     rdx, [rdi+18h]
0x140003645  mov     r8, rdi
0x140003648  mov     rcx, rsi
0x14000364b  call    KbdHid_SetLedIndicators
0x140003650  mov     ebx, eax
0x140003652  jmp     loc_140003989
0x140003657  cmp     dword ptr [rbp+8], 1Ch
0x14000365b  jnb     short loc_14000369D
0x14000365d  mov     ebx, 0C0000023h
0x140003662  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140003669  jz      loc_140003975
0x14000366f  mov     dword ptr [rsp+68h+var_30], ebx
0x140003673  mov     r9d, 0Eh
0x140003679  mov     [rsp+68h+var_38], rdi
0x14000367e  mov     dword ptr [rsp+68h+var_40], 0B0000h
0x140003686  mov     rcx, cs:WPP_GLOBAL_Control
0x14000368d  mov     dl, 2
0x14000368f  mov     rcx, [rcx+40h]
0x140003693  call    WPP_RECORDER_SF_Lqd
0x140003698  jmp     loc_140003975
0x14000369d  mov     rcx, rsi
0x1400036a0  call    KbdHid_WaitForExtendedAttributesQueryCompletion
0x1400036a5  mov     ebx, eax
0x1400036a7  test    eax, eax
0x1400036a9  jns     short loc_1400036E1
0x1400036ab  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400036b2  jz      short loc_1400036DF
0x1400036b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400036bb  mov     r9d, 0Fh
0x1400036c1  mov     dword ptr [rsp+68h+var_30], eax
0x1400036c5  movzx   edx, r13b
0x1400036c9  mov     [rsp+68h+var_38], rdi
0x1400036ce  mov     dword ptr [rsp+68h+var_40], 0B0000h
0x1400036d6  mov     rcx, [rcx+40h]
0x1400036da  call    WPP_RECORDER_SF_Lqd
0x1400036df  xor     ebx, ebx
0x1400036e1  movups  xmm0, xmmword ptr [rsi+118h]
0x1400036e8  mov     rax, [rdi+18h]
0x1400036ec  movups  xmmword ptr [rax], xmm0
0x1400036ef  movups  xmm1, xmmword ptr [rsi+124h]
0x1400036f6  movups  xmmword ptr [rax+0Ch], xmm1
0x1400036fa  mov     qword ptr [rdi+38h], 1Ch
0x140003702  jmp     loc_140003975
0x140003707  cmp     dword ptr [rbp+8], 7
0x14000370b  jnb     short loc_14000373B
0x14000370d  mov     ebx, 0C0000023h
0x140003712  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140003719  jz      loc_140003975
0x14000371f  mov     dword ptr [rsp+68h+var_30], ebx
0x140003723  mov     r9d, 15h
0x140003729  mov     [rsp+68h+var_38], rdi
0x14000372e  mov     dword ptr [rsp+68h+var_40], 0B0200h
0x140003736  jmp     loc_140003686
0x14000373b  mov     rcx, rsi
0x14000373e  call    KbdHid_WaitForExtendedAttributesQueryCompletion
0x140003743  mov     ebx, eax
0x140003745  test    eax, eax
0x140003747  js      short loc_140003777
0x140003749  mov     eax, [rsi+134h]
0x14000374f  mov     rcx, [rdi+18h]
0x140003753  mov     [rcx], eax
0x140003755  movzx   eax, word ptr [rsi+138h]
0x14000375c  mov     [rcx+4], ax
0x140003760  movzx   eax, byte ptr [rsi+13Ah]
0x140003767  mov     [rcx+6], al
0x14000376a  mov     qword ptr [rdi+38h], 7
0x140003772  jmp     loc_140003975
0x140003777  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000377e  jz      loc_140003975
0x140003784  mov     dword ptr [rsp+68h+var_30], eax
0x140003788  mov     r9d, 16h
0x14000378e  mov     [rsp+68h+var_38], rdi
0x140003793  mov     dword ptr [rsp+68h+var_40], 0B0200h
0x14000379b  jmp     loc_140003686
0x1400037a0  cmp     r14d, 0B0203h
0x1400037a7  jz      short loc_140003804
0x1400037a9  cmp     r14d, 0B0403h
0x1400037b0  jz      short loc_1400037FA
0x1400037b2  cmp     r14d, 0B0803h
0x1400037b9  jz      short loc_1400037F0
0x1400037bb  cmp     r14d, 0B1003h
0x1400037c2  jz      short loc_1400037F0
0x1400037c4  mov     ebx, 0C0000010h
0x1400037c9  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400037d0  jz      loc_140003975
0x1400037d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037dd  mov     dword ptr [rsp+68h+var_40], r14d
0x1400037e2  mov     rcx, [rcx+40h]
0x1400037e6  call    WPP_RECORDER_SF_Dd
0x1400037eb  jmp     loc_140003975
0x1400037f0  mov     ebx, 0C00000BBh
0x1400037f5  jmp     loc_140003975
0x1400037fa  mov     ebx, 0C0000002h
0x1400037ff  jmp     loc_140003975
0x140003804  cmp     qword ptr [rsi+90h], 0
0x14000380c  jz      short loc_14000382B
0x14000380e  mov     ebx, 0C0000043h
0x140003813  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000381a  jz      loc_140003975
0x140003820  mov     r9d, 0Ch
0x140003826  jmp     loc_14000395C
0x14000382b  cmp     dword ptr [rbp+10h], 10h
0x14000382f  jnb     short loc_14000384E
0x140003831  mov     ebx, 0C000000Dh
0x140003836  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000383d  jz      loc_140003975
0x140003843  mov     r9d, 0Dh
0x140003849  jmp     loc_14000395C
0x14000384e  mov     rax, [rbp+20h]
0x140003852  xor     ebx, ebx
0x140003854  movups  xmm0, xmmword ptr [rax]
0x140003857  movups  xmmword ptr [rsi+88h], xmm0
0x14000385e  jmp     loc_140003975
0x140003863  cmp     dword ptr [rbp+10h], 6
0x140003867  jnb     short loc_140003886
0x140003869  mov     ebx, 0C000000Dh
0x14000386e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140003875  jz      loc_140003975
0x14000387b  mov     r9d, 12h
0x140003881  jmp     loc_14000395C
0x140003886  mov     rax, [rdi+18h]
0x14000388a  movzx   ecx, word ptr [rax+2]
0x14000388e  test    cx, cx
0x140003891  jnz     short loc_14000389D
0x140003893  cmp     [rax+4], cx
0x140003897  jz      loc_140003975
0x14000389d  cmp     cx, [rsi+12Ah]
0x1400038a4  jb      loc_140003948
0x1400038aa  cmp     cx, [rsi+130h]
0x1400038b1  ja      loc_140003948
0x1400038b7  movzx   edx, word ptr [rax+4]
0x1400038bb  cmp     dx, [rsi+12Ch]
0x1400038c2  jb      loc_140003948
0x1400038c8  cmp     dx, [rsi+132h]
0x1400038cf  ja      short loc_140003948
0x1400038d1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400038d8  jz      short loc_1400038FA
0x1400038da  mov     dword ptr [rsp+68h+var_38], edx
0x1400038de  mov     r9d, 14h
0x1400038e4  mov     dword ptr [rsp+68h+var_40], ecx
0x1400038e8  mov     dl, 4
0x1400038ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038f1  mov     rcx, [rcx+40h]
0x1400038f5  call    WPP_RECORDER_SF_dd
0x1400038fa  mov     rcx, [rdi+18h]
0x1400038fe  xor     edx, edx
0x140003900  mov     eax, [rcx]
0x140003902  mov     [rsi+164h], eax
0x140003908  movzx   eax, word ptr [rcx+4]
0x14000390c  mov     [rsi+168h], ax
0x140003913  mov     rax, [rdi+18h]
0x140003917  movzx   ecx, word ptr [rax+2]
0x14000391b  mov     eax, 3E8h
0x140003920  div     ecx
0x140003922  mov     [rsi+1F8h], eax
0x140003928  mov     rax, [rdi+18h]
0x14000392c  movzx   ecx, word ptr [rax+4]
0x140003930  imul    eax, ecx, 0FFFFD8F0h
0x140003936  mov     dword ptr [rsi+1F4h], 0FFFFFFFFh
0x140003940  mov     [rsi+1F0h], eax
0x140003946  jmp     short loc_140003975
0x140003948  mov     ebx, 0C000000Dh
0x14000394d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140003954  jz      short loc_140003975
0x140003956  mov     r9d, 13h
0x14000395c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003963  mov     r8d, r13d
0x140003966  mov     dl, 2
0x140003968  mov     dword ptr [rsp+68h+var_40], ebx
0x14000396c  mov     rcx, [rcx+40h]
0x140003970  call    WPP_RECORDER_SF_d
0x140003975  xor     edx, edx; PriorityBoost
0x140003977  mov     [rdi+30h], ebx
0x14000397a  mov     rcx, rdi; Irp
0x14000397d  call    cs:__imp_IofCompleteRequest
0x140003984  nop     dword ptr [rax+rax+00h]
0x140003989  mov     r8d, 20h ; ' '; RemlockSize
0x14000398f  lea     rcx, [rsi+98h]; RemoveLock
0x140003996  mov     rdx, rdi; Tag
0x140003999  call    cs:__imp_IoReleaseRemoveLockEx
0x1400039a0  nop     dword ptr [rax+rax+00h]
0x1400039a5  mov     r14, [rsp+68h+arg_8]
0x1400039aa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400039b1  mov     r12, [rsp+68h+arg_0]
0x1400039b6  jz      short loc_1400039E6
0x1400039b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400039bf  cmp     word ptr [rcx+48h], 0
0x1400039c4  jz      short loc_1400039E6
0x1400039c6  mov     rcx, [rcx+40h]
0x1400039ca  lea     rax, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x1400039d1  mov     r9d, 18h
0x1400039d7  mov     qword ptr [rsp+68h+RemlockSize], rax
0x1400039dc  mov     r8d, r13d
0x1400039df  mov     dl, 5
0x1400039e1  call    WPP_RECORDER_SF_
0x1400039e6  mov     eax, ebx
0x1400039e8  mov     rbx, [rsp+68h+arg_10]
0x1400039f0  add     rsp, 40h
0x1400039f4  pop     r15
  ... truncated ...
```
