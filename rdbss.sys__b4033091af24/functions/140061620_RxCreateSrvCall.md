# RxCreateSrvCall

- ea: `0x140061620`
- end: `0x140061aec`
- name: `RxCreateSrvCall`
- size: `1228`
- prototype: `PSRV_CALL __stdcall(PRX_CONTEXT RxContext, PUNICODE_STRING Name, PUNICODE_STRING InnerNamePrefix, PRX_CONNECTION_ID RxConnectionId)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14005f400`

## callees

- `0x14000dfd0`
- `0x14000ffa0`
- `0x140014e40`
- `0x14001b178`
- `0x14001c544`
- `0x140023138`
- `0x140025be6`
- `0x140025d80`
- `0x140026080`
- `0x140061620`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140061684`
- `ntoskrnl!ExAllocatePool2` at `0x1400617cc`
- `ntoskrnl!ExAllocatePool2` at `0x140061684`
- `ntoskrnl!ExAllocatePool2` at `0x1400617cc`
- `ntoskrnl!PsReferenceSiloContext` at `0x140061a5e`
- `ntoskrnl!PsReferenceSiloContext` at `0x140061a5e`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400618fa`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400618fa`

## pseudocode

```c
PSRV_CALL __stdcall RxCreateSrvCall(
        PRX_CONTEXT RxContext,
        PUNICODE_STRING Name,
        PUNICODE_STRING InnerNamePrefix,
        PRX_CONNECTION_ID RxConnectionId)
{
  size_t MaximumLength; // rsi
  unsigned __int16 Length; // r12
  __int16 v8; // r14
  __int64 Pool2; // rax
  __int64 v10; // rbx
  _DWORD *v11; // rdi
  __int64 v12; // r13
  int v13; // eax
  PSZ FileName; // rcx
  PSZ i; // rdi
  __int64 v16; // rax
  _WORD *v17; // rax
  void *v18; // rcx
  __int64 v19; // r8
  volatile signed __int32 *v20; // rcx
  struct _LIST_ENTRY *Flink; // r12
  unsigned __int16 v22; // ax
  PUNICODE_STRING v23; // rbp
  UNICODE_STRING v24; // xmm0
  struct _LIST_ENTRY *v25; // rax
  unsigned __int64 Blink; // rdi
  int v27; // ebp
  __int64 v28; // r15
  unsigned __int64 v29; // rax
  int v30; // r8d
  __int64 v32; // rax
  __int128 v33; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int16 v34; // [rsp+98h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, Name);
  }
  MaximumLength = Name->MaximumLength;
  Length = Name->Length;
  v8 = MaximumLength + 2;
  v34 = Name->Length;
  Pool2 = ExAllocatePool2(64, (unsigned int)(MaximumLength + 834), 1666414674);
  v10 = Pool2;
  if ( !Pool2
    || (*(_WORD *)Pool2 = -5360,
        v11 = (_DWORD *)(Pool2 + 136),
        *(_WORD *)(Pool2 + 2) = MaximumLength + 834,
        *(_QWORD *)(Pool2 + 64) = Pool2 + 144,
        Pool2 == -136) )
  {
    v12 = Pool2;
    if ( !Pool2 )
      return (PSRV_CALL)v12;
  }
  else
  {
    memset((void *)(Pool2 + 136), 0, 0x58u);
    *v11 = 5827342;
    *(_QWORD *)(v10 + 152) = v10 + 832;
    v12 = v10;
    *(_WORD *)(v10 + 144) = v8;
    *(_WORD *)(v10 + 146) = v8;
  }
  v13 = SerialNumber;
  *(_DWORD *)(v10 + 228) = SerialNumber;
  SerialNumber = v13 + 1;
  *(_QWORD *)(v10 + 48) = RxContext->NonPagedFcb;
  v33 = 0;
  RxInitializeBufferingManager((PSRV_CALL)v10);
  *(_QWORD *)(v10 + 24) = v10 + 16;
  *(_QWORD *)(v10 + 16) = v10 + 16;
  *(_QWORD *)(v10 + 248) = v10 + 240;
  *(_QWORD *)(v10 + 240) = v10 + 240;
  if ( (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x2000) != 0 )
  {
    FileName = RxContext->TrackerHistory[8].FileName;
    *(_QWORD *)(v10 + 88) = FileName;
    if ( FileName )
      PsReferenceSiloContext();
  }
  *(_QWORD *)(v10 + 72) = 0;
  if ( !LOBYTE(RxContext->RealDevice) && RxContext->TrackerHistory[3].AcquireRelease )
  {
    for ( i = RxContext->TrackerHistory[2].FileName; ; i += v32 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, i + 8);
      }
      if ( !strcmp_0(i + 8, "Principal") )
        break;
      v32 = *(unsigned int *)i;
      if ( !(_DWORD)v32 )
        goto LABEL_16;
    }
    v16 = *((unsigned __int16 *)i + 3);
    if ( (_WORD)v16 )
    {
      v17 = (_WORD *)ExAllocatePool2(66, v16 + 16, 1666414674);
      *(_QWORD *)(v10 + 72) = v17;
      if ( v17 )
      {
        *v17 = *((_WORD *)i + 3);
        *(_WORD *)(*(_QWORD *)(v10 + 72) + 2LL) = *((_WORD *)i + 3);
        *(_QWORD *)(*(_QWORD *)(v10 + 72) + 8LL) = *(_QWORD *)(v10 + 72) + 16LL;
        memmove(
          *(void **)(*(_QWORD *)(v10 + 72) + 8LL),
          &i[(unsigned __int8)i[5] + 9],
          **(unsigned __int16 **)(v10 + 72));
      }
    }
  }
LABEL_16:
  v18 = *(void **)(v12 + 152);
  *(_WORD *)(v12 + 146) = MaximumLength;
  *(_WORD *)(v12 + 144) = Length;
  memmove(v18, Name->Buffer, MaximumLength);
  v20 = (volatile signed __int32 *)(v12 + 4);
  Flink = RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink;
  if ( LOBYTE(Flink[8].Flink) )
    v22 = -2;
  else
    v22 = Name->MaximumLength;
  *(_QWORD *)(v12 + 192) = v12;
  *(_QWORD *)(v12 + 184) = v20;
  *(_WORD *)(v12 + 140) = v22;
  _InterlockedIncrement(v20);
  v23 = InnerNamePrefix;
  if ( InnerNamePrefix )
    v24 = *InnerNamePrefix;
  else
    v24 = 0;
  *(UNICODE_STRING *)(v12 + 208) = v24;
  v25 = Flink[1].Flink;
  Blink = (unsigned __int64)Flink->Blink;
  if ( ((unsigned __int8)v25 & 1) == 0 )
    goto LABEL_21;
  if ( Blink )
  {
    Blink ^= (unsigned __int64)&Flink->Blink;
LABEL_21:
    LOBYTE(v19) = 0;
    v27 = (unsigned __int8)v25 & 1;
    if ( Blink )
    {
      v28 = v12 + 144;
      while ( 1 )
      {
        if ( (int)RxpCompareFn_PrefixName2PrefixName(v12 + 144, Blink, v19) < 0 )
        {
          v29 = *(_QWORD *)Blink;
          if ( v27 )
          {
            if ( !v29 )
            {
LABEL_47:
              v23 = InnerNamePrefix;
              LOBYTE(v19) = 0;
              goto LABEL_30;
            }
            v29 ^= Blink;
          }
          if ( !v29 )
            goto LABEL_47;
        }
        else
        {
          v29 = *(_QWORD *)(Blink + 8);
          if ( v27 )
          {
            if ( !v29 )
            {
LABEL_45:
              v23 = InnerNamePrefix;
              LOBYTE(v19) = 1;
              goto LABEL_30;
            }
            v29 ^= Blink;
          }
          if ( !v29 )
            goto LABEL_45;
        }
        Blink = v29;
      }
    }
    v23 = InnerNamePrefix;
    goto LABEL_29;
  }
  LOBYTE(v19) = 0;
LABEL_29:
  v28 = v12 + 144;
LABEL_30:
  RtlRbInsertNodeEx(&Flink->Blink, Blink, v19, v12 + 160);
  ++HIDWORD(Flink->Flink);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_04af8fc7118b317781e27056f3398603_Traceguids,
      v12 + 136,
      v12,
      v28);
  }
  *((_QWORD *)&v33 + 1) = *(_QWORD *)(v12 + 152) + v34;
  WORD1(v33) = MaximumLength - v34;
  LOWORD(v33) = MaximumLength - v34;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qiiZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      *(_QWORD *)&v23->Length,
      v30,
      v12,
      *(_QWORD *)&v23->Length,
      (char)v23->Buffer,
      v28,
      (__int64)&v33);
  }
  return (PSRV_CALL)v12;
}

```

## disassembly

```asm
0x140061620  mov     [rsp+arg_10], r8
0x140061625  push    rbx
0x140061626  push    rbp
0x140061627  push    rsi
0x140061628  push    r12
0x14006162a  push    r14
0x14006162c  push    r15
0x14006162e  sub     rsp, 58h
0x140061632  mov     r15, rdx
0x140061635  mov     rbp, rcx
0x140061638  mov     rcx, cs:WPP_GLOBAL_Control
0x14006163f  lea     rax, WPP_GLOBAL_Control
0x140061646  cmp     rcx, rax
0x140061649  jnz     loc_14006197D
0x14006164f  movzx   esi, word ptr [r15+2]
0x140061654  mov     ecx, 40h ; '@'
0x140061659  movzx   r12d, word ptr [r15]
0x14006165d  mov     r8d, 63537852h
0x140061663  mov     [rsp+88h+arg_0], rdi
0x14006166b  mov     [rsp+88h+var_38], r13
0x140061670  lea     r14d, [rsi+2]
0x140061674  mov     [rsp+88h+arg_8], r12w
0x14006167d  lea     edx, [r14+340h]
0x140061684  call    cs:__imp_ExAllocatePool2
0x14006168b  nop     dword ptr [rax+rax+00h]
0x140061690  mov     rbx, rax
0x140061693  test    rax, rax
0x140061696  jz      loc_140061A38
0x14006169c  mov     word ptr [rax], 0EB10h
0x1400616a1  lea     rdi, [rbx+88h]
0x1400616a8  mov     eax, 340h
0x1400616ad  add     eax, r14d
0x1400616b0  mov     [rbx+2], ax
0x1400616b4  lea     rax, [rbx+90h]
0x1400616bb  mov     [rbx+40h], rax
0x1400616bf  test    rdi, rdi
0x1400616c2  jz      loc_140061A38
0x1400616c8  xor     edx, edx; Val
0x1400616ca  mov     r8d, 58h ; 'X'; Size
0x1400616d0  mov     rcx, rdi; void *
0x1400616d3  call    memset
0x1400616d8  lea     rax, [rbx+340h]
0x1400616df  mov     dword ptr [rdi], 58EB0Eh
0x1400616e5  mov     [rdi+10h], rax
0x1400616e9  mov     r13, rbx
0x1400616ec  mov     [rdi+8], r14w
0x1400616f1  mov     [rdi+0Ah], r14w
0x1400616f6  mov     eax, cs:SerialNumber
0x1400616fc  xorps   xmm0, xmm0
0x1400616ff  mov     [rbx+0E4h], eax
0x140061705  mov     rcx, rbx; SrvCall
0x140061708  inc     eax
0x14006170a  mov     cs:SerialNumber, eax
0x140061710  mov     rax, [rbp+50h]
0x140061714  mov     [rbx+30h], rax
0x140061718  movups  [rsp+88h+var_48], xmm0
0x14006171d  call    RxInitializeBufferingManager
0x140061722  lea     rax, [rbx+10h]
0x140061726  mov     [rax+8], rax
0x14006172a  mov     [rax], rax
0x14006172d  lea     rax, [rbx+0F0h]
0x140061734  mov     [rax+8], rax
0x140061738  mov     [rax], rax
0x14006173b  mov     rax, [rbp+50h]
0x14006173f  test    dword ptr [rax+150h], 2000h
0x140061749  jz      short loc_14006175F
0x14006174b  mov     rcx, [rbp+348h]
0x140061752  mov     [rbx+58h], rcx
0x140061756  test    rcx, rcx
0x140061759  jnz     loc_140061A5E
0x14006175f  mov     qword ptr [rbx+48h], 0
0x140061767  cmp     byte ptr [rbp+20h], 0
0x14006176b  jnz     loc_14006181C
0x140061771  cmp     dword ptr [rbp+2C8h], 0
0x140061778  jbe     loc_14006181C
0x14006177e  mov     rdi, [rbp+2B8h]
0x140061785  lea     r14, WPP_GLOBAL_Control
0x14006178c  mov     rcx, cs:WPP_GLOBAL_Control
0x140061793  cmp     rcx, r14
0x140061796  jnz     loc_1400619C1
0x14006179c  lea     rcx, [rdi+8]; Str1
0x1400617a0  lea     rdx, aPrincipal; "Principal"
0x1400617a7  call    strcmp_0
0x1400617ac  test    eax, eax
0x1400617ae  jnz     loc_140061A1E
0x1400617b4  movzx   eax, word ptr [rdi+6]
0x1400617b8  test    ax, ax
0x1400617bb  jz      short loc_14006181C
0x1400617bd  lea     rdx, [rax+10h]
0x1400617c1  mov     ecx, 42h ; 'B'
0x1400617c6  mov     r8d, 63537852h
0x1400617cc  call    cs:__imp_ExAllocatePool2
0x1400617d3  nop     dword ptr [rax+rax+00h]
0x1400617d8  mov     [rbx+48h], rax
0x1400617dc  test    rax, rax
0x1400617df  jz      short loc_14006181C
0x1400617e1  movzx   ecx, word ptr [rdi+6]
0x1400617e5  mov     [rax], cx
0x1400617e8  mov     rcx, [rbx+48h]
0x1400617ec  movzx   eax, word ptr [rdi+6]
0x1400617f0  mov     [rcx+2], ax
0x1400617f4  mov     rcx, [rbx+48h]
0x1400617f8  lea     rax, [rcx+10h]
0x1400617fc  mov     [rcx+8], rax
0x140061800  mov     rcx, [rbx+48h]
0x140061804  movzx   edx, byte ptr [rdi+5]
0x140061808  add     rdx, 9
0x14006180c  add     rdx, rdi; Src
0x14006180f  movzx   r8d, word ptr [rcx]; Size
0x140061813  mov     rcx, [rcx+8]; void *
0x140061817  call    memmove
0x14006181c  lea     rbx, [r13+88h]
0x140061823  mov     r8, rsi; Size
0x140061826  mov     rcx, [rbx+10h]; void *
0x14006182a  mov     [rbx+0Ah], si
0x14006182e  mov     [rbx+8], r12w
0x140061833  mov     rdx, [r15+8]; Src
0x140061837  call    memmove
0x14006183c  mov     rax, [rbp+50h]
0x140061840  lea     rcx, [r13+4]
0x140061844  mov     r12, [rax+1F8h]
0x14006184b  cmp     byte ptr [r12+80h], 0
0x140061854  jz      loc_1400618DA
0x14006185a  mov     eax, 0FFFEh
0x14006185f  mov     [rbx+38h], r13
0x140061863  mov     [rbx+30h], rcx
0x140061867  mov     [rbx+4], ax
0x14006186b  lock inc dword ptr [rcx]
0x14006186e  mov     rbp, [rsp+88h+arg_10]
0x140061876  test    rbp, rbp
0x140061879  jz      loc_140061A30
0x14006187f  movups  xmm0, xmmword ptr [rbp+0]
0x140061883  lea     r14, [r12+8]
0x140061888  movups  xmmword ptr [rbx+48h], xmm0
0x14006188c  mov     rax, [r14+8]
0x140061890  mov     rdi, [r14]
0x140061893  test    al, 1
0x140061895  jnz     loc_140061A49
0x14006189b  movzx   ebp, al
0x14006189e  xor     r8b, r8b
0x1400618a1  and     ebp, 1
0x1400618a4  test    rdi, rdi
0x1400618a7  jz      short loc_1400618E4
0x1400618a9  lea     r15, [rbx+8]
0x1400618ad  mov     rdx, rdi
0x1400618b0  mov     rcx, r15
0x1400618b3  call    RxpCompareFn_PrefixName2PrefixName
0x1400618b8  test    eax, eax
0x1400618ba  js      loc_1400619AF
0x1400618c0  mov     rax, [rdi+8]
0x1400618c4  test    ebp, ebp
0x1400618c6  jnz     loc_1400619F4
0x1400618cc  test    rax, rax
0x1400618cf  jz      loc_1400619F9
0x1400618d5  mov     rdi, rax
0x1400618d8  jmp     short loc_1400618AD
0x1400618da  movzx   eax, word ptr [r15+2]
0x1400618df  jmp     loc_14006185F
0x1400618e4  mov     rbp, [rsp+88h+arg_10]
0x1400618ec  lea     r15, [rbx+8]
0x1400618f0  lea     r9, [rbx+18h]
0x1400618f4  mov     rdx, rdi
0x1400618f7  mov     rcx, r14
0x1400618fa  call    cs:__imp_RtlRbInsertNodeEx
0x140061901  nop     dword ptr [rax+rax+00h]
0x140061906  inc     dword ptr [r12+4]
0x14006190b  mov     rcx, cs:WPP_GLOBAL_Control
0x140061912  lea     rdi, WPP_GLOBAL_Control
0x140061919  cmp     rcx, rdi
0x14006191c  jz      short loc_140061929
0x14006191e  mov     eax, [rcx+2Ch]
0x140061921  test    al, al
0x140061923  js      loc_140061A7F
0x140061929  movzx   eax, [rsp+88h+arg_8]
0x140061931  sub     si, ax
0x140061934  add     rax, [rbx+10h]
0x140061938  mov     qword ptr [rsp+88h+var_48+8], rax
0x14006193d  mov     word ptr [rsp+88h+var_48+2], si
0x140061942  mov     word ptr [rsp+88h+var_48], si
0x140061947  mov     rcx, cs:WPP_GLOBAL_Control
0x14006194e  cmp     rcx, rdi
0x140061951  jz      short loc_14006195E
0x140061953  mov     eax, [rcx+2Ch]
0x140061956  test    al, al
0x140061958  js      loc_140061AB0
0x14006195e  mov     rdi, [rsp+88h+arg_0]
0x140061966  mov     rax, r13
0x140061969  mov     r13, [rsp+88h+var_38]
0x14006196e  add     rsp, 58h
0x140061972  pop     r15
0x140061974  pop     r14
0x140061976  pop     r12
0x140061978  pop     rsi
0x140061979  pop     rbp
0x14006197a  pop     rbx
0x14006197b  retn
0x14006197d  mov     eax, [rcx+2Ch]
0x140061980  test    al, al
0x140061982  jns     loc_14006164F
0x140061988  cmp     byte ptr [rcx+29h], 4
0x14006198c  jb      loc_14006164F
0x140061992  mov     rcx, [rcx+18h]
0x140061996  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14006199d  mov     edx, 25h ; '%'
0x1400619a2  mov     r9, r15
0x1400619a5  call    WPP_SF_Z
0x1400619aa  jmp     loc_14006164F
0x1400619af  mov     rax, [rdi]
0x1400619b2  test    ebp, ebp
0x1400619b4  jnz     short loc_140061A09
0x1400619b6  test    rax, rax
0x1400619b9  jnz     loc_1400618D5
0x1400619bf  jmp     short loc_140061A0E
0x1400619c1  mov     eax, [rcx+2Ch]
0x1400619c4  test    al, al
0x1400619c6  jns     loc_14006179C
0x1400619cc  cmp     byte ptr [rcx+29h], 4
0x1400619d0  jb      loc_14006179C
0x1400619d6  mov     rcx, [rcx+18h]
0x1400619da  lea     r9, [rdi+8]
0x1400619de  mov     edx, 24h ; '$'
0x1400619e3  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x1400619ea  call    WPP_SF_s
0x1400619ef  jmp     loc_14006179C
0x1400619f4  test    rax, rax
0x1400619f7  jnz     short loc_140061A6F
0x1400619f9  mov     rbp, [rsp+88h+arg_10]
0x140061a01  mov     r8b, 1
0x140061a04  jmp     loc_1400618F0
0x140061a09  test    rax, rax
0x140061a0c  jnz     short loc_140061A77
0x140061a0e  mov     rbp, [rsp+88h+arg_10]
0x140061a16  xor     r8b, r8b
0x140061a19  jmp     loc_1400618F0
0x140061a1e  mov     eax, [rdi]
0x140061a20  test    eax, eax
0x140061a22  jz      loc_14006181C
0x140061a28  add     rdi, rax
0x140061a2b  jmp     loc_14006178C
0x140061a30  xorps   xmm0, xmm0
0x140061a33  jmp     loc_140061883
0x140061a38  mov     r13, rbx
0x140061a3b  test    rbx, rbx
0x140061a3e  jnz     loc_1400616F6
0x140061a44  jmp     loc_14006195E
0x140061a49  test    rdi, rdi
0x140061a4c  jz      short loc_140061A56
0x140061a4e  xor     rdi, r14
0x140061a51  jmp     loc_14006189B
0x140061a56  xor     r8b, r8b
0x140061a59  jmp     loc_1400618EC
0x140061a5e  call    cs:__imp_PsReferenceSiloContext
0x140061a65  nop     dword ptr [rax+rax+00h]
0x140061a6a  jmp     loc_14006175F
0x140061a6f  xor     rax, rdi
0x140061a72  jmp     loc_1400618CC
0x140061a77  xor     rax, rdi
0x140061a7a  jmp     loc_1400619B6
0x140061a7f  cmp     byte ptr [rcx+29h], 4
0x140061a83  jb      loc_140061929
0x140061a89  mov     rcx, [rcx+18h]
0x140061a8d  lea     r8, WPP_04af8fc7118b317781e27056f3398603_Traceguids
0x140061a94  mov     edx, 0Bh
0x140061a99  mov     [rsp+88h+var_60], r15
0x140061a9e  mov     r9, rbx
0x140061aa1  mov     [rsp+88h+var_68], r13
0x140061aa6  call    WPP_SF_qqZ
0x140061aab  jmp     loc_140061929
0x140061ab0  cmp     byte ptr [rcx+29h], 2
0x140061ab4  jb      loc_14006195E
0x140061aba  mov     rdx, [rbp+8]
0x140061abe  lea     rax, [rsp+88h+var_48]
0x140061ac3  mov     rcx, [rcx+18h]
0x140061ac7  mov     r9, r13
0x140061aca  mov     [rsp+88h+var_50], rax
0x140061acf  mov     [rsp+88h+var_58], r15
0x140061ad4  mov     [rsp+88h+var_60], rdx
0x140061ad9  mov     rdx, [rbp+0]
0x140061add  mov     [rsp+88h+var_68], rdx
0x140061ae2  call    WPP_SF_qiiZZ
0x140061ae7  jmp     loc_14006195E
```
