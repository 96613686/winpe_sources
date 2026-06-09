# ACSendMessage

- ea: `0x14000881c`
- end: `0x140008b71`
- name: `ACSendMessage`
- size: `853`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140008b78`
- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x14000881c`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001dfb4`
- `0x14001fbb4`
- `0x1400242b4`
- `0x14002479c`
- `0x140024bb0`
- `0x140024fc0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140008948`
- `ntoskrnl!ProbeForRead` at `0x140008948`

## pseudocode

```c
__int64 __fastcall ACSendMessage(
        struct _DEVICE_OBJECT *a1,
        __int64 a2,
        int a3,
        const struct CQueueBase *a4,
        volatile void *Address)
{
  _DWORD *DeviceExtension; // r13
  int v9; // eax
  int v10; // edi
  struct CTransaction *v11; // r12
  _OWORD *v12; // rax
  _OWORD *v13; // rcx
  __int64 v14; // rdx
  const struct BOID *v15; // rdx
  int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // edx
  struct QUEUE_FORMAT *v22[36]; // [rsp+70h] [rbp-428h] BYREF
  _QWORD v23[88]; // [rsp+190h] [rbp-308h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 71, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a4);
  }
  memset(v23, 0, sizeof(v23));
  memset(v22, 0, 280);
  DeviceExtension = a1->DeviceExtension;
  v9 = CQueueBase::Validate(a4);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = 0;
    v10 = 0;
    if ( DeviceExtension[246] )
    {
      ACDeepProbeSendParams(a1, (struct CACSendParameters *)Address, (struct ACSendParametersPointerContents *)v22);
      v15 = (const struct BOID *)*((_QWORD *)Address + 45);
    }
    else
    {
      ProbeForRead(Address, 0x2C0u, 1u);
      v12 = Address;
      v13 = v23;
      v14 = 5;
      do
      {
        *v13 = *v12;
        v13[1] = v12[1];
        v13[2] = v12[2];
        v13[3] = v12[3];
        v13[4] = v12[4];
        v13[5] = v12[5];
        v13[6] = v12[6];
        v13[7] = v12[7];
        v13 += 8;
        v12 += 8;
        --v14;
      }
      while ( v14 );
      *v13 = *v12;
      v13[1] = v12[1];
      v13[2] = v12[2];
      v13[3] = v12[3];
      ACDeepProbeSendParams(a1, (struct CACSendParameters *)v23, (struct ACSendParametersPointerContents *)v22);
      v15 = (const struct BOID *)v23[45];
    }
    if ( v15 )
    {
      v11 = CTransaction::Find(a1, v15);
      if ( !v11 )
        v10 = -1072824239;
    }
    if ( v10 >= 0 )
    {
      *(_OWORD *)(a2 + 120) = 0;
      *(_OWORD *)(a2 + 136) = 0;
      *(_DWORD *)(a2 + 144) = *(_DWORD *)(a2 + 144) & 0xFFFFFFF8 | 1;
      if ( DeviceExtension[246] )
        v16 = CQueue::PutNewPacket(
                a4,
                (struct _IRP *)a2,
                v11,
                a3,
                (const struct CACSendParameters *)Address,
                (const struct ACSendParametersPointerContents *)v22);
      else
        v16 = CQueue::PutNewPacket(
                a4,
                (struct _IRP *)a2,
                v11,
                a3,
                (const struct CACSendParameters *)v23,
                (const struct ACSendParametersPointerContents *)v22);
      v10 = v16;
    }
    if ( v22[23] )
    {
      v17 = v23[74];
      if ( DeviceExtension[246] )
        v17 = *((_DWORD *)Address + 148);
      ACFreeDeepCopyQueueFormat(v22[23], v17);
    }
    if ( v22[24] )
    {
      v18 = v23[76];
      if ( DeviceExtension[246] )
        v18 = *((_DWORD *)Address + 152);
      ACFreeDeepCopyQueueFormat(v22[24], v18);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      72,
      WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v9,
      a4);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000881c  push    rsi
0x14000881e  push    rdi
0x14000881f  push    r12
0x140008821  push    r13
0x140008823  push    r14
0x140008825  push    r15
0x140008827  sub     rsp, 468h
0x14000882e  mov     rax, cs:__security_cookie
0x140008835  xor     rax, rsp
0x140008838  mov     [rsp+498h+var_48], rax
0x140008840  mov     rsi, r9
0x140008843  mov     [rsp+498h+var_468], r8d
0x140008848  mov     r15, rdx
0x14000884b  mov     rdi, rcx
0x14000884e  mov     [rsp+498h+var_458], rcx
0x140008853  mov     r14, [rsp+498h+Address]
0x14000885b  mov     [rsp+498h+var_440], rdx
0x140008860  mov     [rsp+498h+var_460], r8d
0x140008865  mov     [rsp+498h+var_450], r9
0x14000886a  mov     [rsp+498h+var_438], r14
0x14000886f  lea     r12, WPP_GLOBAL_Control
0x140008876  mov     rcx, cs:WPP_GLOBAL_Control
0x14000887d  cmp     rcx, r12
0x140008880  jz      short loc_14000889E
0x140008882  mov     eax, [rcx+6Ch]
0x140008885  test    al, 4
0x140008887  jz      short loc_14000889E
0x140008889  mov     edx, 47h ; 'G'
0x14000888e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008895  mov     rcx, [rcx+58h]
0x140008899  call    WPP_SF_q
0x14000889e  xor     edx, edx; Val
0x1400088a0  mov     r8d, 2C0h; Size
0x1400088a6  lea     rcx, [rsp+498h+var_308]; void *
0x1400088ae  call    memset
0x1400088b3  mov     [rsp+498h+var_428], 0
0x1400088bc  xor     edx, edx; Val
0x1400088be  mov     r8d, 110h; Size
0x1400088c4  lea     rcx, [rsp+498h+var_420]; void *
0x1400088c9  call    memset
0x1400088ce  mov     r13, [rdi+40h]
0x1400088d2  mov     [rsp+498h+var_430], r13
0x1400088d7  mov     rcx, rsi; struct CQueueBase *
0x1400088da  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x1400088df  mov     edi, eax
0x1400088e1  test    eax, eax
0x1400088e3  jns     short loc_140008924
0x1400088e5  mov     r10, cs:WPP_GLOBAL_Control
0x1400088ec  cmp     r10, r12
0x1400088ef  jz      loc_140008B4C
0x1400088f5  mov     ecx, [r10+6Ch]
0x1400088f9  test    cl, 1
0x1400088fc  jz      loc_140008B4C
0x140008902  mov     edx, 48h ; 'H'
0x140008907  mov     [rsp+498h+var_478], rsi
0x14000890c  mov     r9d, eax
0x14000890f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008916  mov     rcx, [r10+58h]
0x14000891a  call    WPP_SF_Dq
0x14000891f  jmp     loc_140008B4C
0x140008924  xor     r12d, r12d
0x140008927  mov     [rsp+498h+var_448], r12
0x14000892c  xor     edi, edi
0x14000892e  cmp     [r13+3D8h], edi
0x140008935  jnz     loc_1400089EF
0x14000893b  mov     edx, 2C0h; Length
0x140008940  lea     r8d, [r12+1]; Alignment
0x140008945  mov     rcx, r14; Address
0x140008948  call    cs:__imp_ProbeForRead
0x14000894f  nop     dword ptr [rax+rax+00h]
0x140008954  mov     rax, r14
0x140008957  lea     rcx, [rsp+498h+var_308]
0x14000895f  lea     edx, [rdi+5]
0x140008962  lea     r8d, [rdx+7Bh]
0x140008966  movups  xmm0, xmmword ptr [rax]
0x140008969  movups  xmmword ptr [rcx], xmm0
0x14000896c  movups  xmm1, xmmword ptr [rax+10h]
0x140008970  movups  xmmword ptr [rcx+10h], xmm1
0x140008974  movups  xmm0, xmmword ptr [rax+20h]
0x140008978  movups  xmmword ptr [rcx+20h], xmm0
0x14000897c  movups  xmm1, xmmword ptr [rax+30h]
0x140008980  movups  xmmword ptr [rcx+30h], xmm1
0x140008984  movups  xmm0, xmmword ptr [rax+40h]
0x140008988  movups  xmmword ptr [rcx+40h], xmm0
0x14000898c  movups  xmm1, xmmword ptr [rax+50h]
0x140008990  movups  xmmword ptr [rcx+50h], xmm1
0x140008994  movups  xmm0, xmmword ptr [rax+60h]
0x140008998  movups  xmmword ptr [rcx+60h], xmm0
0x14000899c  movups  xmm1, xmmword ptr [rax+70h]
0x1400089a0  movups  xmmword ptr [rcx+70h], xmm1
0x1400089a4  add     rcx, r8
0x1400089a7  add     rax, r8
0x1400089aa  sub     rdx, 1
0x1400089ae  jnz     short loc_140008966
0x1400089b0  movups  xmm0, xmmword ptr [rax]
0x1400089b3  movups  xmmword ptr [rcx], xmm0
0x1400089b6  movups  xmm1, xmmword ptr [rax+10h]
0x1400089ba  movups  xmmword ptr [rcx+10h], xmm1
0x1400089be  movups  xmm0, xmmword ptr [rax+20h]
0x1400089c2  movups  xmmword ptr [rcx+20h], xmm0
0x1400089c6  movups  xmm1, xmmword ptr [rax+30h]
0x1400089ca  movups  xmmword ptr [rcx+30h], xmm1
0x1400089ce  lea     r8, [rsp+498h+var_428]; struct ACSendParametersPointerContents *
0x1400089d3  lea     rdx, [rsp+498h+var_308]; struct CACSendParameters *
0x1400089db  mov     rcx, [rsp+498h+var_458]; struct _DEVICE_OBJECT *
0x1400089e0  call    ?ACDeepProbeSendParams@@YAXPEAU_DEVICE_OBJECT@@PEAVCACSendParameters@@PEAUACSendParametersPointerContents@@@Z; ACDeepProbeSendParams(_DEVICE_OBJECT *,CACSendParameters *,ACSendParametersPointerContents *)
0x1400089e5  mov     rdx, [rsp+498h+var_1A0]
0x1400089ed  jmp     short loc_140008A08
0x1400089ef  lea     r8, [rsp+498h+var_428]; struct ACSendParametersPointerContents *
0x1400089f4  mov     rdx, r14; struct CACSendParameters *
0x1400089f7  mov     rcx, [rsp+498h+var_458]; struct _DEVICE_OBJECT *
0x1400089fc  call    ?ACDeepProbeSendParams@@YAXPEAU_DEVICE_OBJECT@@PEAVCACSendParameters@@PEAUACSendParametersPointerContents@@@Z; ACDeepProbeSendParams(_DEVICE_OBJECT *,CACSendParameters *,ACSendParametersPointerContents *)
0x140008a01  mov     rdx, [r14+168h]; struct BOID *
0x140008a08  test    rdx, rdx
0x140008a0b  jz      short loc_140008A2E
0x140008a0d  mov     rcx, [rsp+498h+var_458]; struct _DEVICE_OBJECT *
0x140008a12  call    ?Find@CTransaction@@SAPEAV1@PEAU_DEVICE_OBJECT@@PEBUBOID@@@Z; CTransaction::Find(_DEVICE_OBJECT *,BOID const *)
0x140008a17  mov     r12, rax
0x140008a1a  mov     [rsp+498h+var_448], rax
0x140008a1f  mov     eax, 0C00E0051h
0x140008a24  test    r12, r12
0x140008a27  cmovz   edi, eax
0x140008a2a  mov     [rsp+498h+var_464], edi
0x140008a2e  mov     ecx, [rsp+498h+var_468]
0x140008a32  jmp     short loc_140008A95
0x140008a34  mov     edi, eax
0x140008a36  mov     [rsp+498h+var_464], eax
0x140008a3a  lea     rax, WPP_GLOBAL_Control
0x140008a41  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a48  cmp     rcx, rax
0x140008a4b  jz      short loc_140008A78
0x140008a4d  mov     eax, [rcx+6Ch]
0x140008a50  test    al, 1
0x140008a52  jz      short loc_140008A78
0x140008a54  mov     edx, 49h ; 'I'
0x140008a59  mov     rsi, [rsp+498h+var_450]
0x140008a5e  mov     [rsp+498h+var_478], rsi
0x140008a63  mov     r9d, edi
0x140008a66  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008a6d  mov     rcx, [rcx+58h]
0x140008a71  call    WPP_SF_Dq
0x140008a76  jmp     short loc_140008A7D
0x140008a78  mov     rsi, [rsp+498h+var_450]
0x140008a7d  mov     r12, [rsp+498h+var_448]
0x140008a82  mov     r15, [rsp+498h+var_440]
0x140008a87  mov     ecx, [rsp+498h+var_460]
0x140008a8b  mov     r14, [rsp+498h+var_438]
0x140008a90  mov     r13, [rsp+498h+var_430]
0x140008a95  test    edi, edi
0x140008a97  js      short loc_140008AF8
0x140008a99  xorps   xmm0, xmm0
0x140008a9c  movups  xmmword ptr [r15+78h], xmm0
0x140008aa1  movups  xmmword ptr [r15+88h], xmm0
0x140008aa9  mov     eax, [r15+90h]
0x140008ab0  and     eax, 0FFFFFFF9h
0x140008ab3  or      eax, 1
0x140008ab6  mov     [r15+90h], eax
0x140008abd  lea     rax, [rsp+498h+var_428]
0x140008ac2  mov     r9d, ecx; int
0x140008ac5  mov     r8, r12; struct CTransaction *
0x140008ac8  mov     rdx, r15; struct _IRP *
0x140008acb  mov     [rsp+498h+var_470], rax; struct ACSendParametersPointerContents *
0x140008ad0  mov     rcx, rsi; this
0x140008ad3  cmp     dword ptr [r13+3D8h], 0
0x140008adb  jnz     short loc_140008AEC
0x140008add  lea     rax, [rsp+498h+var_308]
0x140008ae5  mov     [rsp+498h+var_478], rax
0x140008aea  jmp     short loc_140008AF1
0x140008aec  mov     [rsp+498h+var_478], r14; struct CACSendParameters *
0x140008af1  call    ?PutNewPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCTransaction@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@@Z; CQueue::PutNewPacket(_IRP *,CTransaction *,int,CACSendParameters const *,ACSendParametersPointerContents const *)
0x140008af6  mov     edi, eax
0x140008af8  mov     rcx, [rsp+498h+var_370]; struct QUEUE_FORMAT *
0x140008b00  test    rcx, rcx
0x140008b03  jz      short loc_140008B22
0x140008b05  cmp     dword ptr [r13+3D8h], 0
0x140008b0d  mov     edx, [rsp+498h+var_B8]
0x140008b14  jz      short loc_140008B1D
0x140008b16  mov     edx, [r14+250h]; unsigned int
0x140008b1d  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140008b22  mov     rcx, [rsp+498h+var_368]; struct QUEUE_FORMAT *
0x140008b2a  test    rcx, rcx
0x140008b2d  jz      short loc_140008B4C
0x140008b2f  cmp     dword ptr [r13+3D8h], 0
0x140008b37  mov     edx, [rsp+498h+var_A8]
0x140008b3e  jz      short loc_140008B47
0x140008b40  mov     edx, [r14+260h]; unsigned int
0x140008b47  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x140008b4c  mov     eax, edi
0x140008b4e  mov     rcx, [rsp+498h+var_48]
0x140008b56  xor     rcx, rsp; StackCookie
0x140008b59  call    __security_check_cookie
0x140008b5e  add     rsp, 468h
0x140008b65  pop     r15
0x140008b67  pop     r14
0x140008b69  pop     r13
0x140008b6b  pop     r12
0x140008b6d  pop     rdi
0x140008b6e  pop     rsi
0x140008b6f  retn
```
