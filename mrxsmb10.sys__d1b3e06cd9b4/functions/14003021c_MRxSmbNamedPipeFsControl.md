# MRxSmbNamedPipeFsControl

- ea: `0x14003021c`
- end: `0x140030ba7`
- name: `MRxSmbNamedPipeFsControl`
- size: `2443`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002f640`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000f1d0`
- `0x14000f634`
- `0x14000f6c4`
- `0x140016560`
- `0x1400166c0`
- `0x14003021c`
- `0x14004b5f0`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140030b3a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140030b3a`
- `ntoskrnl!ProbeForWrite` at `0x14003069d`
- `ntoskrnl!ProbeForWrite` at `0x14003069d`
- `ntoskrnl!ProbeForRead` at `0x14003067a`
- `ntoskrnl!ProbeForRead` at `0x14003067a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140030369`
- `ntoskrnl!IoGetRequestorProcess` at `0x140030369`
- `ntoskrnl!KeStackAttachProcess` at `0x140030380`
- `ntoskrnl!KeStackAttachProcess` at `0x140030380`
- `ntoskrnl!ExAllocatePool2` at `0x14003047b`
- `ntoskrnl!ExAllocatePool2` at `0x140030872`
- `ntoskrnl!ExAllocatePool2` at `0x14003047b`
- `ntoskrnl!ExAllocatePool2` at `0x140030872`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030ac5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030ac5`

## pseudocode

```c
__int64 __fastcall MRxSmbNamedPipeFsControl(__int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rbx
  int v6; // esi
  __int64 v7; // r14
  __int64 v8; // r14
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v10; // r8
  __int64 *v11; // r14
  __int64 v12; // rdx
  void *Pool2; // rcx
  __int64 v14; // rcx
  char v15; // cl
  volatile void *v16; // r9
  SIZE_T v17; // rdx
  volatile void *v18; // r14
  unsigned int v19; // ecx
  __int64 v20; // rax
  unsigned int v21; // ecx
  bool v22; // cf
  int v23; // eax
  bool v24; // sf
  __int64 v25; // rax
  _DWORD *v26; // r15
  __int64 v27; // r14
  _OWORD *v28; // rdx
  unsigned int v29; // r8d
  PVOID v30; // rcx
  unsigned int v31; // ebx
  int v32; // eax
  _DWORD *v33; // rcx
  unsigned int v35; // [rsp+68h] [rbp-100h]
  char v36; // [rsp+81h] [rbp-E7h]
  int v37; // [rsp+84h] [rbp-E4h] BYREF
  unsigned int v38; // [rsp+88h] [rbp-E0h]
  int v39; // [rsp+8Ch] [rbp-DCh] BYREF
  unsigned __int16 v40; // [rsp+90h] [rbp-D8h]
  int v41; // [rsp+94h] [rbp-D4h]
  int v42; // [rsp+98h] [rbp-D0h]
  unsigned int v43; // [rsp+9Ch] [rbp-CCh]
  PVOID P[2]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-B8h]
  unsigned __int64 v46; // [rsp+B8h] [rbp-B0h]
  __int64 v47; // [rsp+C0h] [rbp-A8h]
  int *v48; // [rsp+C8h] [rbp-A0h]
  int v49; // [rsp+D4h] [rbp-94h]
  unsigned int v50; // [rsp+D8h] [rbp-90h]
  volatile void *v51; // [rsp+E8h] [rbp-80h]
  volatile void *v52; // [rsp+F0h] [rbp-78h]
  __int64 v53; // [rsp+F8h] [rbp-70h]
  __int64 v54; // [rsp+100h] [rbp-68h]
  _KAPC_STATE ApcState; // [rsp+108h] [rbp-60h] BYREF

  v53 = a1;
  v2 = *(_QWORD *)(a1 + 64);
  v54 = v2;
  v3 = *(_QWORD *)(a1 + 56);
  v43 = *(_DWORD *)(a1 + 540);
  LODWORD(v46) = v43;
  *(_OWORD *)P = 0;
  v39 = 0;
  v40 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
  if ( ((*(_WORD *)v3 + 5088) & 0xFFFD) != 0 )
    return 3221225488LL;
  v4 = *(_QWORD *)(v3 + 120);
  if ( !v4 || *(_BYTE *)(v4 + 77) != 1 )
    return 3221225488LL;
  v36 = 0;
  v48 = 0;
  v47 = 0;
  v45 = 0;
  v42 = 0;
  v41 = 0;
  v38 = 0;
  LODWORD(v5) = 0;
  v6 = -1073741802;
  if ( v2 && (v7 = *(_QWORD *)(v2 + 32)) != 0 )
    v8 = *(_QWORD *)(v7 + 48);
  else
    v8 = 0;
  RequestorProcess = IoGetRequestorProcess(*(PIRP *)(a1 + 40));
  KeStackAttachProcess(RequestorProcess, &ApcState);
  *(_OWORD *)P = *(_OWORD *)&s_NamedPipeTransactionName;
  if ( v43 <= 0x11001C )
  {
    if ( v43 != 1114140 && v43 != 1114112 )
    {
      if ( v43 == 1114116 || v43 == 1114120 )
      {
        v6 = -1073741811;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
        }
        goto LABEL_60;
      }
      if ( v43 != 1114128 )
      {
        if ( v43 == 1114136 )
        {
          v37 = 83;
          v11 = *(__int64 **)(a1 + 552);
          if ( v11 && (v10 = *(unsigned int *)(a1 + 568), (unsigned int)v10 >= 0x10) )
          {
            v12 = *((unsigned int *)v11 + 2);
            if ( (unsigned int)v12 <= 0xFFFF
              && (unsigned int)v12 + (unsigned __int16)s_NamedPipeTransactionName <= 0xFFFF
              && v12 - 2 <= (unsigned __int64)(v10 - 16) )
            {
LABEL_26:
              if ( v6 == -1073741802 )
              {
                LOWORD(P[0]) = s_NamedPipeTransactionName + *((_WORD *)v11 + 4);
                WORD1(P[0]) = P[0];
                Pool2 = (void *)ExAllocatePool2(258, LOWORD(P[0]), 1061124178);
                P[1] = Pool2;
                if ( Pool2 )
                {
                  v36 = 1;
                  memmove(Pool2, Src, (unsigned __int16)s_NamedPipeTransactionName);
                  memmove(
                    (char *)P[1] + (unsigned __int16)s_NamedPipeTransactionName,
                    (char *)v11 + 14,
                    *((unsigned int *)v11 + 2));
                }
                else
                {
                  v6 = -1073741670;
                }
                if ( *((_BYTE *)v11 + 12) )
                {
                  v46 = 0x8000000000000000uLL;
                  v14 = *v11;
                  if ( *v11 != 0x8000000000000000uLL )
                  {
                    v5 = v14 / -10000;
                    if ( (unsigned __int64)(v14 / -10000) >> 32 )
                      LODWORD(v5) = -2;
                  }
                }
                v15 = 1;
                goto LABEL_61;
              }
LABEL_60:
              v15 = 0;
              goto LABEL_61;
            }
          }
          else
          {
            v11 = 0;
          }
          v6 = -1073741811;
          goto LABEL_26;
        }
LABEL_44:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
        }
        v6 = -1073741811;
        goto LABEL_60;
      }
    }
LABEL_57:
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
    goto LABEL_60;
  }
  switch ( v43 )
  {
    case 0x110020u:
    case 0x110024u:
    case 0x110054u:
      goto LABEL_57;
    case 0x11400Cu:
      LOWORD(v37) = 35;
      HIWORD(v37) = *(_WORD *)(v8 + 8);
      v48 = &v39;
      v42 = 6;
      v20 = *(_QWORD *)(a1 + 560);
      v45 = v20 + 16;
      v21 = *(_DWORD *)(a1 + 572);
      v38 = v21 - 16;
      if ( !v20 )
        goto LABEL_60;
      v22 = v21 < 0x10;
      v15 = 0;
      if ( v22 )
        v6 = -1073741789;
      break;
    case 0x11C017u:
      LOWORD(v37) = 38;
      HIWORD(v37) = *(_WORD *)(v8 + 8);
      v16 = *(volatile void **)(a1 + 552);
      v47 = (__int64)v16;
      v51 = v16;
      v17 = *(unsigned int *)(a1 + 568);
      v41 = v17;
      v49 = v17;
      v18 = *(volatile void **)(a1 + 560);
      v45 = (__int64)v18;
      v52 = v18;
      v19 = *(_DWORD *)(a1 + 572);
      v38 = v19;
      v50 = v19;
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL) )
        goto LABEL_60;
      if ( v16 )
      {
        ProbeForRead(v16, v17, 1u);
        v19 = v38;
      }
      if ( v18 )
        ProbeForWrite(v18, v19, 1u);
      v15 = 0;
      break;
    default:
      goto LABEL_44;
  }
LABEL_61:
  if ( v6 == -1073741802 )
  {
    if ( v15 && v2 )
    {
      SmbCeReconnect(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(v2 + 32) + 40LL) + 40LL));
      v6 = v23;
    }
    else
    {
      v6 = 0;
    }
    v24 = v6 < 0;
    if ( v6 )
      goto LABEL_93;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Zl(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        (unsigned int)WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids,
        (unsigned int)P,
        (char)P[0]);
    v25 = ExAllocatePool2(66, 152, 1665559891);
    v26 = (_DWORD *)v25;
    if ( v25 )
    {
      v27 = v25 + 48;
      v28 = (_OWORD *)(v25 + 24);
      v29 = v43;
      if ( v43 == 1130508 )
      {
        *(_QWORD *)(v25 + 8) = 0;
        *(_DWORD *)v25 = 1;
      }
      else
      {
        *(_QWORD *)(v25 + 8) = a1;
        *(_DWORD *)v25 = 2;
        *(_QWORD *)(v25 + 56) = 1;
        *(_QWORD *)(v25 + 64) = v25;
        *(_QWORD *)(v25 + 72) = MRxSmbNamedPipeFsControlCompletion;
        *(_QWORD *)(v25 + 104) = 0;
        *(_QWORD *)(v25 + 112) = 0;
        *(_QWORD *)(v25 + 128) = 0;
        *(_QWORD *)(v25 + 136) = 0;
        *(_QWORD *)(v25 + 144) = 0;
      }
      *v28 = RxDefaultTransactionOptions;
      *(_QWORD *)(v25 + 40) = qword_14001F6B0;
      *(_DWORD *)v28 = 0x40000000;
      *(_QWORD *)(v25 + 32) = P;
      *(_DWORD *)(v25 + 40) = v5;
      v30 = 0;
      if ( P[1] != Src )
        v30 = P[1];
      *(_QWORD *)(v25 + 16) = v30;
      v31 = v38;
      v35 = v38;
      if ( v29 == 1130508 )
      {
        v6 = SmbCeTransact(
               a1,
               (_DWORD)v28,
               (unsigned int)&v37,
               4,
               0,
               0,
               0,
               0,
               (__int64)v48,
               v42,
               v47,
               v41,
               v45,
               v38,
               v27);
        if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147483643 )
        {
          if ( *(_DWORD *)(v27 + 64) >= 6u )
          {
            if ( (v40 & 4) == 0 || (_WORD)v39 )
            {
              v33 = *(_DWORD **)(a1 + 560);
              *v33 = v40;
              v33[1] = (unsigned __int16)v39;
              v33[2] = -1;
              v33[3] = HIWORD(v39);
              if ( HIWORD(v39) > v31 )
                v6 = -2147483643;
            }
            else
            {
              v6 = -1073741648;
            }
          }
          *(_QWORD *)(a1 + 184) = (unsigned int)(*(_DWORD *)(v27 + 60) + 16);
        }
      }
      else
      {
        *(_WORD *)(v25 + 26) |= 0x100u;
        v32 = SmbCeTransact(
                a1,
                (_DWORD)v28,
                (unsigned int)&v37,
                4,
                0,
                0,
                0,
                0,
                (__int64)v48,
                v42,
                v47,
                v41,
                v45,
                v35,
                v27);
        v6 = 259;
        if ( v32 != 259 )
          v26[29] = v32;
      }
      MRxSmbNamedPipeFsControlCompletion(v26);
    }
    else
    {
      if ( v36 )
      {
        ExFreePoolWithTag(P[1], 0);
        P[1] = 0;
      }
      v6 = -1073741670;
    }
  }
  v24 = v6 < 0;
LABEL_93:
  if ( v24 )
  {
    if ( v6 == -1073741816 )
      v6 = -1073741629;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_lL(WPP_GLOBAL_Control->AttachedDevice, 20, v10, v43, v6);
  }
  KeUnstackDetachProcess(&ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003021c  mov     r11, rsp
0x14003021f  mov     [r11+10h], rbx
0x140030223  mov     [r11+18h], rsi
0x140030227  push    rdi
0x140030228  push    r12
0x14003022a  push    r13
0x14003022c  push    r14
0x14003022e  push    r15
0x140030230  sub     rsp, 140h
0x140030237  mov     rax, cs:__security_cookie
0x14003023e  xor     rax, rsp
0x140030241  mov     [rsp+168h+var_30], rax
0x140030249  mov     r13, rcx
0x14003024c  mov     [rsp+168h+var_70], rcx
0x140030254  mov     r12, [rcx+40h]
0x140030258  mov     [rsp+168h+var_68], r12
0x140030260  mov     rbx, [rcx+38h]
0x140030264  mov     eax, [rcx+21Ch]
0x14003026a  mov     [rsp+168h+var_CC], eax
0x140030271  mov     dword ptr [rsp+168h+var_B0], eax
0x140030278  xorps   xmm0, xmm0
0x14003027b  movups  xmmword ptr [rsp+168h+P], xmm0
0x140030283  xor     eax, eax
0x140030285  mov     [rsp+168h+var_DC], eax
0x14003028c  mov     [rsp+168h+var_D8], ax
0x140030294  movups  xmmword ptr [r11-60h], xmm0
0x140030299  movups  xmmword ptr [r11-50h], xmm0
0x14003029e  movups  xmmword ptr [r11-40h], xmm0
0x1400302a3  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400302aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400302b1  mov     r15d, 400h
0x1400302b7  cmp     rcx, rax
0x1400302ba  jz      short loc_1400302D7
0x1400302bc  test    [rcx+2Ch], r15d
0x1400302c0  jz      short loc_1400302D7
0x1400302c2  mov     edx, 0Fh
0x1400302c7  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x1400302ce  mov     rcx, [rcx+18h]
0x1400302d2  call    WPP_SF_
0x1400302d7  mov     eax, 13E0h
0x1400302dc  add     ax, [rbx]
0x1400302df  mov     ecx, 0FFFDh
0x1400302e4  test    cx, ax
0x1400302e7  jnz     loc_140030B74
0x1400302ed  mov     rax, [rbx+78h]
0x1400302f1  xor     edi, edi
0x1400302f3  test    rax, rax
0x1400302f6  jz      loc_140030B74
0x1400302fc  cmp     byte ptr [rax+4Dh], 1
0x140030300  jnz     loc_140030B74
0x140030306  mov     al, dil
0x140030309  mov     [rsp+168h+var_E8], al
0x140030310  mov     [rsp+168h+var_E7], al
0x140030317  mov     eax, edi
0x140030319  mov     [rsp+168h+var_A0], rax
0x140030321  mov     [rsp+168h+var_A8], rdi
0x140030329  mov     [rsp+168h+var_B8], rdi
0x140030331  mov     [rsp+168h+var_D0], eax
0x140030338  mov     [rsp+168h+var_D4], edi
0x14003033f  mov     [rsp+168h+var_E0], edi
0x140030346  mov     ebx, edi
0x140030348  mov     esi, 0C0000016h
0x14003034d  test    r12, r12
0x140030350  jz      short loc_140030362
0x140030352  mov     r14, [r12+20h]
0x140030357  test    r14, r14
0x14003035a  jz      short loc_140030362
0x14003035c  mov     r14, [r14+30h]
0x140030360  jmp     short loc_140030365
0x140030362  mov     r14, rdi
0x140030365  mov     rcx, [r13+28h]; Irp
0x140030369  call    cs:__imp_IoGetRequestorProcess
0x140030370  nop     dword ptr [rax+rax+00h]
0x140030375  mov     rcx, rax; PROCESS
0x140030378  lea     rdx, [rsp+168h+ApcState]; ApcState
0x140030380  call    cs:__imp_KeStackAttachProcess
0x140030387  nop     dword ptr [rax+rax+00h]
0x14003038c  movups  xmm0, xmmword ptr cs:s_NamedPipeTransactionName
0x140030393  movdqu  xmmword ptr [rsp+168h+P], xmm0
0x14003039c  mov     ecx, 11001Ch
0x1400303a1  mov     eax, [rsp+168h+var_CC]
0x1400303a8  cmp     eax, ecx
0x1400303aa  ja      loc_140030585
0x1400303b0  jz      loc_1400307C1
0x1400303b6  sub     eax, 110000h
0x1400303bb  jz      loc_1400307C1
0x1400303c1  sub     eax, 4
0x1400303c4  jz      loc_140030546
0x1400303ca  sub     eax, 4
0x1400303cd  jz      loc_140030546
0x1400303d3  sub     eax, 8
0x1400303d6  jz      loc_1400307C1
0x1400303dc  cmp     eax, 8
0x1400303df  jnz     loc_1400305B4
0x1400303e5  mov     [rsp+168h+var_E4], 53h ; 'S'
0x1400303f0  mov     r14, [r13+228h]
0x1400303f7  test    r14, r14
0x1400303fa  jz      short loc_140030435
0x1400303fc  mov     r8d, [r13+238h]
0x140030403  cmp     r8d, 10h
0x140030407  jb      short loc_140030435
0x140030409  mov     edx, [r14+8]
0x14003040d  mov     r9d, 0FFFFh
0x140030413  cmp     edx, r9d
0x140030416  ja      short loc_140030438
0x140030418  movzx   ecx, cs:s_NamedPipeTransactionName
0x14003041f  add     ecx, edx
0x140030421  cmp     ecx, r9d
0x140030424  ja      short loc_140030438
0x140030426  lea     rcx, [rdx-2]
0x14003042a  lea     rax, [r8-10h]
0x14003042e  cmp     rcx, rax
0x140030431  jbe     short loc_14003043D
0x140030433  jmp     short loc_140030438
0x140030435  mov     r14, rdi
0x140030438  mov     esi, 0C000000Dh
0x14003043d  cmp     esi, 0C0000016h
0x140030443  jnz     loc_140030579
0x140030449  mov     [rsp+168h+var_E8], 1
0x140030451  movzx   ecx, word ptr [r14+8]
0x140030456  add     cx, cs:s_NamedPipeTransactionName
0x14003045d  movzx   edx, cx
0x140030460  mov     word ptr [rsp+168h+P], dx
0x140030468  mov     word ptr [rsp+168h+P+2], dx
0x140030470  mov     ecx, 102h
0x140030475  mov     r8d, 3F3F7852h
0x14003047b  call    cs:__imp_ExAllocatePool2
0x140030482  nop     dword ptr [rax+rax+00h]
0x140030487  mov     rcx, rax; void *
0x14003048a  mov     [rsp+168h+P+8], rax
0x140030492  test    rax, rax
0x140030495  jz      short loc_1400304D1
0x140030497  mov     [rsp+168h+var_E7], 1
0x14003049f  movzx   r8d, cs:s_NamedPipeTransactionName; Size
0x1400304a7  mov     rdx, cs:Src; Src
0x1400304ae  call    memmove
0x1400304b3  mov     r8d, [r14+8]; Size
0x1400304b7  lea     rdx, [r14+0Eh]; Src
0x1400304bb  movzx   ecx, cs:s_NamedPipeTransactionName
0x1400304c2  add     rcx, [rsp+168h+P+8]; void *
0x1400304ca  call    memmove
0x1400304cf  jmp     short loc_1400304D6
0x1400304d1  mov     esi, 0C000009Ah
0x1400304d6  cmp     [r14+0Ch], dil
0x1400304da  jz      short loc_140030533
0x1400304dc  mov     dword ptr [rsp+168h+var_B0], edi
0x1400304e3  mov     dword ptr [rsp+168h+var_B0+4], 80000000h
0x1400304ee  mov     rcx, [r14]
0x1400304f1  lea     r14, WPP_GLOBAL_Control
0x1400304f8  cmp     rcx, [rsp+168h+var_B0]
0x140030500  jz      short loc_14003053A
0x140030502  mov     rax, 0CB923A29C779A6B5h
0x14003050c  imul    rcx
0x14003050f  mov     rbx, rdx
0x140030512  sar     rbx, 0Bh
0x140030516  mov     rax, rbx
0x140030519  shr     rax, 3Fh
0x14003051d  add     rbx, rax
0x140030520  mov     rax, rbx
0x140030523  shr     rax, 20h
0x140030527  mov     ecx, 0FFFFFFFEh
0x14003052c  test    eax, eax
0x14003052e  cmovnz  ebx, ecx
0x140030531  jmp     short loc_14003053A
0x140030533  lea     r14, WPP_GLOBAL_Control
0x14003053a  mov     cl, [rsp+168h+var_E8]
0x140030541  jmp     loc_1400307F6
0x140030546  mov     esi, 0C000000Dh
0x14003054b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030552  lea     r14, WPP_GLOBAL_Control
0x140030559  cmp     rcx, r14
0x14003055c  jz      short loc_140030579
0x14003055e  test    [rcx+2Ch], r15d
0x140030562  jz      short loc_140030579
0x140030564  mov     edx, 11h
0x140030569  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x140030570  mov     rcx, [rcx+18h]
0x140030574  call    WPP_SF_
0x140030579  lea     r14, WPP_GLOBAL_Control
0x140030580  jmp     loc_1400307F4
0x140030585  sub     eax, 110020h
0x14003058a  jz      loc_1400307C1
0x140030590  sub     eax, 4
0x140030593  jz      loc_1400307C1
0x140030599  sub     eax, 30h ; '0'
0x14003059c  jz      loc_1400307C1
0x1400305a2  sub     eax, 3FB8h
0x1400305a7  jz      loc_14003074A
0x1400305ad  cmp     eax, 800Bh
0x1400305b2  jz      short loc_1400305EC
0x1400305b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400305bb  lea     r14, WPP_GLOBAL_Control
0x1400305c2  cmp     rcx, r14
0x1400305c5  jz      short loc_1400305E2
0x1400305c7  test    [rcx+2Ch], r15d
0x1400305cb  jz      short loc_1400305E2
0x1400305cd  mov     edx, 12h
0x1400305d2  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x1400305d9  mov     rcx, [rcx+18h]
0x1400305dd  call    WPP_SF_
0x1400305e2  mov     esi, 0C000000Dh
0x1400305e7  jmp     loc_1400307F4
0x1400305ec  mov     eax, 26h ; '&'
0x1400305f1  mov     word ptr [rsp+168h+var_E4], ax
0x1400305f9  movzx   eax, word ptr [r14+8]
0x1400305fe  mov     word ptr [rsp+168h+var_E4+2], ax
0x140030606  mov     r9, [r13+228h]
0x14003060d  mov     [rsp+168h+var_A8], r9
0x140030615  mov     [rsp+168h+var_80], r9
0x14003061d  mov     edx, [r13+238h]; Length
0x140030624  mov     [rsp+168h+var_D4], edx
0x14003062b  mov     [rsp+168h+var_94], edx
0x140030632  mov     r14, [r13+230h]
0x140030639  mov     [rsp+168h+var_B8], r14
0x140030641  mov     [rsp+168h+var_78], r14
0x140030649  mov     ecx, [r13+23Ch]
0x140030650  mov     [rsp+168h+var_E0], ecx
0x140030657  mov     [rsp+168h+var_90], ecx
0x14003065e  mov     rax, [r13+28h]
0x140030662  cmp     [rax+40h], dil
0x140030666  jz      loc_140030579
0x14003066c  test    r9, r9
0x14003066f  jz      short loc_14003068D
0x140030671  mov     r8d, 1; Alignment
0x140030677  mov     rcx, r9; Address
0x14003067a  call    cs:__imp_ProbeForRead
0x140030681  nop     dword ptr [rax+rax+00h]
0x140030686  mov     ecx, [rsp+168h+var_E0]
0x14003068d  test    r14, r14
0x140030690  jz      short loc_1400306A9
0x140030692  mov     edx, ecx; Length
0x140030694  mov     r8d, 1; Alignment
0x14003069a  mov     rcx, r14; Address
0x14003069d  call    cs:__imp_ProbeForWrite
0x1400306a4  nop     dword ptr [rax+rax+00h]
0x1400306a9  lea     r14, WPP_GLOBAL_Control
0x1400306b0  mov     cl, [rsp+168h+var_E8]
0x1400306b7  jmp     loc_1400307F6
0x1400306bc  mov     esi, 0C000000Dh
0x1400306c1  lea     r14, WPP_GLOBAL_Control
0x1400306c8  xor     edi, edi
0x1400306ca  mov     r15d, 400h
0x1400306d0  mov     cl, dil
0x1400306d3  mov     [rsp+168h+var_E7], cl
0x1400306da  mov     [rsp+168h+var_A0], rdi
0x1400306e2  mov     rax, [rsp+168h+var_80]
0x1400306ea  mov     [rsp+168h+var_A8], rax
0x1400306f2  mov     rdx, [rsp+168h+var_78]
0x1400306fa  mov     [rsp+168h+var_B8], rdx
0x140030702  mov     [rsp+168h+var_D0], edi
0x140030709  mov     eax, [rsp+168h+var_94]
0x140030710  mov     [rsp+168h+var_D4], eax
0x140030717  mov     edx, [rsp+168h+var_90]
0x14003071e  mov     [rsp+168h+var_E0], edx
0x140030725  mov     ebx, edi
0x140030727  mov     r13, [rsp+168h+var_70]
0x14003072f  mov     r12, [rsp+168h+var_68]
0x140030737  mov     eax, dword ptr [rsp+168h+var_B0]
0x14003073e  mov     [rsp+168h+var_CC], eax
0x140030745  jmp     loc_1400307F6
0x14003074a  mov     eax, 23h ; '#'
0x14003074f  mov     word ptr [rsp+168h+var_E4], ax
0x140030757  movzx   eax, word ptr [r14+8]
0x14003075c  mov     word ptr [rsp+168h+var_E4+2], ax
0x140030764  lea     rax, [rsp+168h+var_DC]
0x14003076c  mov     [rsp+168h+var_A0], rax
0x140030774  mov     [rsp+168h+var_D0], 6
0x14003077f  mov     rax, [r13+230h]
0x140030786  lea     rcx, [rax+10h]
0x14003078a  mov     [rsp+168h+var_B8], rcx
0x140030792  mov     ecx, [r13+23Ch]
0x140030799  lea     edx, [rcx-10h]
0x14003079c  mov     [rsp+168h+var_E0], edx
0x1400307a3  test    rax, rax
0x1400307a6  jz      loc_140030579
0x1400307ac  lea     r14, WPP_GLOBAL_Control
0x1400307b3  cmp     ecx, 10h
0x1400307b6  mov     cl, bl
0x1400307b8  jnb     short loc_1400307F6
0x1400307ba  mov     esi, 0C0000023h
0x1400307bf  jmp     short loc_1400307F6
0x1400307c1  mov     esi, 0C000000Dh
0x1400307c6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400307cd  lea     r14, WPP_GLOBAL_Control
0x1400307d4  cmp     rcx, r14
0x1400307d7  jz      short loc_1400307F4
0x1400307d9  test    [rcx+2Ch], r15d
0x1400307dd  jz      short loc_1400307F4
0x1400307df  mov     edx, 10h
0x1400307e4  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x1400307eb  mov     rcx, [rcx+18h]
0x1400307ef  call    WPP_SF_
0x1400307f4  mov     cl, bl
0x1400307f6  cmp     esi, 0C0000016h
0x1400307fc  jnz     loc_140030AE4
0x140030802  test    cl, cl
0x140030804  jz      short loc_140030821
0x140030806  test    r12, r12
0x140030809  jz      short loc_140030821
0x14003080b  mov     rax, [r12+20h]
  ... truncated ...
```
