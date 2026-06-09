# CscPreProcessOpen

- ea: `0x140070040`
- end: `0x140070546`
- name: `CscPreProcessOpen`
- size: `1286`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x140003a00`
- `0x1400109e0`
- `0x140016a04`
- `0x1400190ec`
- `0x14002f010`
- `0x14002f0f0`
- `0x140070040`
- `0x1400706b0`

## import_xrefs

- `rdbss!RxIterateOnFcbOpens` at `0x14007037b`
- `rdbss!RxIterateOnFcbOpens` at `0x14007037b`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14007038d`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14007038d`
- `rdbss!RxCreateRxContext` at `0x140070337`
- `rdbss!RxCreateRxContext` at `0x140070337`

## pseudocode

```c
__int64 __fastcall CscPreProcessOpen(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rdx
  unsigned int v4; // r13d
  __int64 v5; // r15
  bool v6; // r12
  int v7; // r14d
  int v8; // ebp
  __int64 v9; // rdx
  int v10; // r8d
  unsigned int v11; // edi
  unsigned int v12; // ebp
  __int64 v13; // rdi
  unsigned __int16 v14; // cx
  __int64 v15; // rax
  __int64 v17; // rcx
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v19; // rdi
  int v20; // ebp
  int v21; // [rsp+28h] [rbp-90h]
  _BYTE v22[4]; // [rsp+40h] [rbp-78h] BYREF
  int v23; // [rsp+44h] [rbp-74h]
  int v24; // [rsp+48h] [rbp-70h] BYREF
  int v25; // [rsp+4Ch] [rbp-6Ch] BYREF
  __int128 v26; // [rsp+50h] [rbp-68h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(unsigned __int16 *)(a1 + 746);
  v5 = *(_QWORD *)(*(_QWORD *)(v1 + 120) + 32LL);
  v6 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v7 = 0;
  v8 = 0;
  v23 = 0;
  v26 = 0;
  CscUpdateAndCaptureConnectionStateEx(v1, v3, a1, 1, (__int64)&v26, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v1);
  CscCleanupFcbContextFlags(v1, v9);
  v11 = *(_DWORD *)(a1 + 256);
  v22[0] = 0;
  v24 = 0;
  v25 = 0;
  if ( (v11 & 0x10000000) != 0 )
  {
    if ( (v11 & 0x20000000) != 0 )
    {
      *(_DWORD *)(a1 + 712) = 0;
      *(_QWORD *)(a1 + 696) = 0;
    }
  }
  else
  {
    LOBYTE(v10) = 1;
    v7 = CscProcessCscEa(
           *(_QWORD *)(a1 + 696),
           *(_DWORD *)(a1 + 712),
           v10,
           (int)a1 + 512,
           (__int64)v22,
           (__int64)&v24,
           (__int64)&v25);
    if ( v7 < 0 )
      goto LABEL_26;
    v12 = v11;
    if ( v22[0] )
    {
      if ( v24 == 1 )
      {
        *(_DWORD *)(a1 + 712) = 0;
        *(_QWORD *)(a1 + 696) = 0;
      }
      v12 = v25 | v11;
      if ( v11 != (v25 | v11)
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_32ed2d9bb3b53ee3ef8df58514c2f3dd_Traceguids, v11, v12);
      }
    }
    *(_QWORD *)(a1 + 256) = v12 | 0x10000000LL;
  }
  v13 = *(unsigned int *)(a1 + 256);
  if ( (v13 & 1) != 0 )
    *(_WORD *)(a1 + 746) |= 0x40u;
  if ( (v13 & 2) != 0 )
    *(_WORD *)(a1 + 746) |= 0x20u;
  v14 = *(_WORD *)(a1 + 746);
  if ( (v13 & 0x800) != 0 || (v13 & 0x40000) != 0 )
  {
    *(_WORD *)(a1 + 746) |= 0x1000u;
    v14 = *(_WORD *)(a1 + 746);
    LODWORD(v13) = v13 | 0x400;
    *(_QWORD *)(a1 + 256) = v13;
  }
  if ( (v13 & 0x20000) != 0 )
  {
    *(_WORD *)(a1 + 746) |= 0x100u;
    v14 = *(_WORD *)(a1 + 746);
  }
  if ( (v13 & 0x400) != 0 )
  {
    *(_WORD *)(a1 + 746) |= 0x2000u;
    v14 = *(_WORD *)(a1 + 746);
    if ( (v13 & 0x800) == 0 && (v13 & 0x40000) == 0 && (v13 & 0x80000) == 0 )
    {
      v14 |= 0x40u;
      LODWORD(v13) = v13 | 1;
      *(_WORD *)(a1 + 746) = v14;
      *(_QWORD *)(a1 + 256) = (unsigned int)v13;
    }
  }
  if ( (_WORD)v4 != v14
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v4, v14);
  }
  if ( (v13 & 0x400) != 0 || *(_WORD *)v1 == 0xEC21 )
    goto LABEL_67;
  v17 = *(_QWORD *)(v1 + 144);
  if ( v17 && *(_WORD *)v17 != 0xEAA1 )
    v17 = 0;
  if ( (*(_DWORD *)(a1 + 512) & 0xFFEFFF7F) == 0 && (!v17 || (*(_DWORD *)(v17 + 4) & 0x20) == 0) )
    goto LABEL_67;
  RxContext = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(a1 + 80), 2u);
  v19 = RxContext;
  if ( RxContext )
  {
    v20 = 0;
    RxContext->pFcb = (PMRX_FCB)v1;
    LOWORD(RxContext->RealDevice) = 0;
    LOBYTE(v21) = 0;
    RxContext->CurrentIrp = *(PIRP *)(a1 + 40);
    v7 = RxIterateOnFcbOpens(RxContext, v1, 0, CscCheckQueryInfoOpenPerFobxCallback, 0, v21);
    RxDereferenceAndDeleteRxContext_Real(v19);
  }
  else
  {
    v20 = 1421;
    v7 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)v7,
      v20);
  if ( v7 < 0 )
  {
    v8 = 1612;
  }
  else
  {
LABEL_67:
    if ( v6 && (v26 & 0x10) == 0 )
    {
      v15 = *(_QWORD *)(a1 + 656);
      if ( v15 )
      {
        if ( *(_QWORD *)(v15 + 40) )
        {
          if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 48) + 352LL) + 64LL) )
          {
            if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
            {
              v7 = -1073741536;
            }
            else
            {
              *(_OWORD *)(a1 + 208) = 0;
              *(_OWORD *)(a1 + 224) = 0;
              *(_QWORD *)(a1 + 240) = 0;
              v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v5 + 48) + 352LL) + 64LL))(a1);
            }
          }
          else
          {
            v7 = -1073741822;
          }
        }
      }
    }
    v8 = v23;
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)v7,
      v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140070040  push    rbx
0x140070042  push    rbp
0x140070043  push    rsi
0x140070044  push    rdi
0x140070045  push    r12
0x140070047  push    r13
0x140070049  push    r14
0x14007004b  push    r15
0x14007004d  sub     rsp, 78h
0x140070051  mov     rax, cs:__security_cookie
0x140070058  xor     rax, rsp
0x14007005b  mov     [rsp+0B8h+var_58], rax
0x140070060  mov     rsi, [rcx+38h]
0x140070064  mov     rbx, rcx
0x140070067  mov     rdx, [rcx+48h]
0x14007006b  xorps   xmm0, xmm0
0x14007006e  movzx   r13d, word ptr [rcx+2EAh]
0x140070076  mov     r8, rcx
0x140070079  mov     r9b, 1
0x14007007c  mov     rax, [rsi+78h]
0x140070080  mov     r15, [rax+20h]
0x140070084  mov     rax, cs:CscDeviceObject
0x14007008b  cmp     [rcx+50h], rax
0x14007008f  lea     rax, [rsp+0B8h+var_68]
0x140070094  mov     rcx, rsi
0x140070097  setnz   r12b
0x14007009b  xor     r14d, r14d
0x14007009e  mov     ebp, r14d
0x1400700a1  mov     [rsp+0B8h+var_74], r14d
0x1400700a6  mov     byte ptr [rsp+0B8h+var_90], bpl
0x1400700ab  mov     [rsp+0B8h+var_98], rax
0x1400700b0  movups  [rsp+0B8h+var_68], xmm0
0x1400700b5  call    CscUpdateAndCaptureConnectionStateEx
0x1400700ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400700c1  lea     rax, WPP_GLOBAL_Control
0x1400700c8  cmp     rcx, rax
0x1400700cb  jnz     loc_14007029E
0x1400700d1  mov     rcx, rsi
0x1400700d4  call    CscCleanupFcbContextFlags
0x1400700d9  mov     edi, [rbx+100h]
0x1400700df  mov     [rsp+0B8h+var_78], bpl
0x1400700e4  mov     [rsp+0B8h+var_70], r14d
0x1400700e9  mov     [rsp+0B8h+var_6C], r14d
0x1400700ee  bt      edi, 1Ch
0x1400700f2  jb      loc_1400702C6
0x1400700f8  mov     edx, [rbx+2C8h]
0x1400700fe  lea     rax, [rsp+0B8h+var_6C]
0x140070103  mov     rcx, [rbx+2B8h]
0x14007010a  lea     r9, [rbx+200h]
0x140070111  mov     [rsp+0B8h+var_88], rax
0x140070116  mov     r8b, 1
0x140070119  lea     rax, [rsp+0B8h+var_70]
0x14007011e  mov     [rsp+0B8h+var_90], rax
0x140070123  lea     rax, [rsp+0B8h+var_78]
0x140070128  mov     [rsp+0B8h+var_98], rax
0x14007012d  call    CscProcessCscEa
0x140070132  mov     r14d, eax
0x140070135  test    eax, eax
0x140070137  js      loc_140070265
0x14007013d  cmp     [rsp+0B8h+var_78], 0
0x140070142  mov     ebp, edi
0x140070144  jnz     loc_140070405
0x14007014a  mov     eax, ebp
0x14007014c  bts     rax, 1Ch
0x140070151  mov     [rbx+100h], rax
0x140070158  mov     edi, [rbx+100h]
0x14007015e  test    dil, 1
0x140070162  jz      short loc_14007016C
0x140070164  or      word ptr [rbx+2EAh], 40h
0x14007016c  test    dil, 2
0x140070170  jz      short loc_14007017A
0x140070172  or      word ptr [rbx+2EAh], 20h
0x14007017a  movzx   ecx, word ptr [rbx+2EAh]
0x140070181  bt      edi, 0Bh
0x140070185  jnb     loc_1400703CA
0x14007018b  mov     eax, 1000h
0x140070190  or      [rbx+2EAh], ax
0x140070197  movzx   ecx, word ptr [rbx+2EAh]
0x14007019e  bts     edi, 0Ah
0x1400701a2  mov     [rbx+100h], rdi
0x1400701a9  bt      edi, 11h
0x1400701ad  jb      loc_1400704F2
0x1400701b3  bt      edi, 0Ah
0x1400701b7  jnb     short loc_1400701D6
0x1400701b9  mov     eax, 2000h
0x1400701be  or      [rbx+2EAh], ax
0x1400701c5  movzx   ecx, word ptr [rbx+2EAh]
0x1400701cc  bt      edi, 0Bh
0x1400701d0  jnb     loc_1400704B7
0x1400701d6  cmp     r13w, cx
0x1400701da  jnz     loc_140070470
0x1400701e0  bt      edi, 0Ah
0x1400701e4  jnb     loc_1400702E3
0x1400701ea  test    r12b, r12b
0x1400701ed  jz      short loc_140070261
0x1400701ef  test    byte ptr [rsp+0B8h+var_68], 10h
0x1400701f4  jnz     short loc_140070261
0x1400701f6  mov     rax, [rbx+290h]
0x1400701fd  test    rax, rax
0x140070200  jz      short loc_140070261
0x140070202  cmp     qword ptr [rax+28h], 0
0x140070207  jz      short loc_140070261
0x140070209  mov     rax, [r15+30h]
0x14007020d  mov     rcx, [rax+160h]
0x140070214  cmp     qword ptr [rcx+40h], 0
0x140070219  jz      loc_14007053B
0x14007021f  mov     eax, [rbx+80h]
0x140070225  test    al, 2
0x140070227  jnz     loc_1400704E7
0x14007022d  xor     eax, eax
0x14007022f  xorps   xmm0, xmm0
0x140070232  movups  xmmword ptr [rbx+0D0h], xmm0
0x140070239  mov     rcx, rbx
0x14007023c  movups  xmmword ptr [rbx+0E0h], xmm0
0x140070243  mov     [rbx+0F0h], rax
0x14007024a  mov     rax, [r15+30h]
0x14007024e  mov     rdx, [rax+160h]
0x140070255  mov     rax, [rdx+40h]
0x140070259  call    _guard_dispatch_icall
0x14007025e  mov     r14d, eax
0x140070261  mov     ebp, [rsp+0B8h+var_74]
0x140070265  mov     rcx, cs:WPP_GLOBAL_Control
0x14007026c  lea     rax, WPP_GLOBAL_Control
0x140070273  cmp     rcx, rax
0x140070276  jnz     loc_1400703D9
0x14007027c  mov     eax, r14d
0x14007027f  mov     rcx, [rsp+0B8h+var_58]
0x140070284  xor     rcx, rsp; StackCookie
0x140070287  call    __security_check_cookie
0x14007028c  add     rsp, 78h
0x140070290  pop     r15
0x140070292  pop     r14
0x140070294  pop     r13
0x140070296  pop     r12
0x140070298  pop     rdi
0x140070299  pop     rsi
0x14007029a  pop     rbp
0x14007029b  pop     rbx
0x14007029c  retn
0x14007029e  mov     eax, [rcx+2Ch]
0x1400702a1  test    al, 20h
0x1400702a3  jz      loc_1400700D1
0x1400702a9  mov     rcx, [rcx+18h]
0x1400702ad  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400702b4  mov     edx, 18h
0x1400702b9  mov     r9, rsi
0x1400702bc  call    WPP_SF_q
0x1400702c1  jmp     loc_1400700D1
0x1400702c6  bt      edi, 1Dh
0x1400702ca  jnb     loc_140070158
0x1400702d0  mov     [rbx+2C8h], r14d
0x1400702d7  mov     [rbx+2B8h], r14
0x1400702de  jmp     loc_140070158
0x1400702e3  mov     eax, 0EC21h
0x1400702e8  cmp     [rsi], ax
0x1400702eb  jz      loc_1400701EA
0x1400702f1  mov     rcx, [rsi+90h]
0x1400702f8  test    rcx, rcx
0x1400702fb  jz      short loc_14007030B
0x1400702fd  xor     eax, eax
0x1400702ff  mov     edx, 0EAA1h
0x140070304  cmp     dx, [rcx]
0x140070307  cmovnz  rcx, rax
0x14007030b  test    dword ptr [rbx+200h], 0FFEFFF7Fh
0x140070315  jnz     short loc_14007032B
0x140070317  test    rcx, rcx
0x14007031a  jz      loc_1400701EA
0x140070320  mov     eax, [rcx+4]
0x140070323  test    al, 20h
0x140070325  jz      loc_1400701EA
0x14007032b  mov     rdx, [rbx+50h]; RxDeviceObject
0x14007032f  mov     r8d, 2; InitialContextFlags
0x140070335  xor     ecx, ecx; Irp
0x140070337  call    cs:__imp_RxCreateRxContext
0x14007033e  nop     dword ptr [rax+rax+00h]
0x140070343  mov     rdi, rax
0x140070346  test    rax, rax
0x140070349  jz      loc_14007050A
0x14007034f  xor     ebp, ebp
0x140070351  mov     [rax+38h], rsi
0x140070355  mov     [rax+20h], bp
0x140070359  lea     r9, CscCheckQueryInfoOpenPerFobxCallback
0x140070360  mov     rax, [rbx+28h]
0x140070364  xor     r8d, r8d
0x140070367  mov     byte ptr [rsp+0B8h+var_90], bpl
0x14007036c  mov     rdx, rsi
0x14007036f  mov     rcx, rdi
0x140070372  mov     [rdi+28h], rax
0x140070376  mov     [rsp+0B8h+var_98], rbp
0x14007037b  call    cs:__imp_RxIterateOnFcbOpens
0x140070382  nop     dword ptr [rax+rax+00h]
0x140070387  mov     rcx, rdi; RxContext
0x14007038a  mov     r14d, eax
0x14007038d  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140070394  nop     dword ptr [rax+rax+00h]
0x140070399  mov     rcx, cs:WPP_GLOBAL_Control
0x1400703a0  lea     rax, WPP_GLOBAL_Control
0x1400703a7  cmp     rcx, rax
0x1400703aa  jz      short loc_1400703B7
0x1400703ac  mov     eax, [rcx+2Ch]
0x1400703af  test    al, 20h
0x1400703b1  jnz     loc_14007051A
0x1400703b7  test    r14d, r14d
0x1400703ba  jns     loc_1400701EA
0x1400703c0  mov     ebp, 64Ch
0x1400703c5  jmp     loc_140070265
0x1400703ca  bt      edi, 12h
0x1400703ce  jnb     loc_1400701A9
0x1400703d4  jmp     loc_14007018B
0x1400703d9  mov     eax, [rcx+2Ch]
0x1400703dc  test    al, 20h
0x1400703de  jz      loc_14007027C
0x1400703e4  mov     rcx, [rcx+18h]
0x1400703e8  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x1400703ef  mov     edx, 1Ah
0x1400703f4  mov     dword ptr [rsp+0B8h+var_98], ebp
0x1400703f8  mov     r9d, r14d
0x1400703fb  call    WPP_SF_Dd
0x140070400  jmp     loc_14007027C
0x140070405  cmp     [rsp+0B8h+var_70], 1
0x14007040a  jnz     short loc_140070421
0x14007040c  mov     dword ptr [rbx+2C8h], 0
0x140070416  mov     qword ptr [rbx+2B8h], 0
0x140070421  or      ebp, [rsp+0B8h+var_6C]
0x140070425  cmp     edi, ebp
0x140070427  jz      loc_14007014A
0x14007042d  mov     rcx, cs:WPP_GLOBAL_Control
0x140070434  lea     rax, WPP_GLOBAL_Control
0x14007043b  cmp     rcx, rax
0x14007043e  jz      loc_14007014A
0x140070444  mov     eax, [rcx+2Ch]
0x140070447  test    al, 20h
0x140070449  jz      loc_14007014A
0x14007044f  mov     rcx, [rcx+18h]
0x140070453  lea     r8, WPP_32ed2d9bb3b53ee3ef8df58514c2f3dd_Traceguids
0x14007045a  mov     edx, 0Ch
0x14007045f  mov     dword ptr [rsp+0B8h+var_98], ebp
0x140070463  mov     r9d, edi
0x140070466  call    WPP_SF_Dd
0x14007046b  jmp     loc_14007014A
0x140070470  mov     r10, cs:WPP_GLOBAL_Control
0x140070477  lea     rax, WPP_GLOBAL_Control
0x14007047e  cmp     r10, rax
0x140070481  jz      loc_1400701E0
0x140070487  mov     eax, [r10+2Ch]
0x14007048b  test    al, 20h
0x14007048d  jz      loc_1400701E0
0x140070493  movzx   eax, cx
0x140070496  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14007049d  mov     rcx, [r10+18h]
0x1400704a1  mov     r9d, r13d
0x1400704a4  mov     edx, 19h
0x1400704a9  mov     dword ptr [rsp+0B8h+var_98], eax
0x1400704ad  call    WPP_SF_Dd
0x1400704b2  jmp     loc_1400701E0
0x1400704b7  bt      edi, 12h
0x1400704bb  jb      loc_1400701D6
0x1400704c1  bt      edi, 13h
0x1400704c5  jb      loc_1400701D6
0x1400704cb  or      cx, 40h
0x1400704cf  or      edi, 1
0x1400704d2  mov     [rbx+2EAh], cx
0x1400704d9  mov     eax, edi
0x1400704db  mov     [rbx+100h], rax
0x1400704e2  jmp     loc_1400701D6
0x1400704e7  mov     r14d, 0C0000120h
0x1400704ed  jmp     loc_140070261
0x1400704f2  mov     eax, 100h
0x1400704f7  or      [rbx+2EAh], ax
0x1400704fe  movzx   ecx, word ptr [rbx+2EAh]
0x140070505  jmp     loc_1400701B3
0x14007050a  mov     ebp, 58Dh
0x14007050f  mov     r14d, 0C000009Ah
0x140070515  jmp     loc_140070399
0x14007051a  mov     rcx, [rcx+18h]
0x14007051e  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140070525  mov     edx, 17h
0x14007052a  mov     dword ptr [rsp+0B8h+var_98], ebp
0x14007052e  mov     r9d, r14d
0x140070531  call    WPP_SF_Dd
0x140070536  jmp     loc_1400703B7
0x14007053b  mov     r14d, 0C0000002h
0x140070541  jmp     loc_140070261
```
