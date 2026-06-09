# ACCreateDistribution

- ea: `0x140004d64`
- end: `0x1400050bf`
- name: `ACCreateDistribution`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x140004d64`
- `0x140007684`
- `0x14000d684`
- `0x14000da8c`
- `0x14000e30c`
- `0x14001aa94`
- `0x14001b384`
- `0x14002186c`
- `0x14002479c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140004da7`
- `ntoskrnl!ProbeForRead` at `0x140004e23`
- `ntoskrnl!ProbeForRead` at `0x140004e3d`
- `ntoskrnl!ProbeForRead` at `0x140004da7`
- `ntoskrnl!ProbeForRead` at `0x140004e23`
- `ntoskrnl!ProbeForRead` at `0x140004e3d`

## pseudocode

```c
__int64 __fastcall ACCreateDistribution(struct _DEVICE_OBJECT *a1, struct _GUID *Address)
{
  char *DeviceExtension; // rsi
  unsigned int v5; // r12d
  unsigned int Data1; // r14d
  void *v7; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  struct CACOpenQueueRequest *v11; // r13
  struct _FILE_OBJECT *v12; // r14
  CDistribution *v13; // rax
  CDistribution *v14; // r15
  CQMInterface *v15; // rcx
  int v16; // ebx
  struct QUEUE_FORMAT *v17; // rsi
  __int64 i; // rdi
  _DWORD *FsContext2; // rax
  struct CACOpenQueueRequest *v20; // [rsp+40h] [rbp-68h] BYREF
  volatile void *v21; // [rsp+48h] [rbp-60h]
  volatile void *v22; // [rsp+50h] [rbp-58h]
  struct _GUID v23; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v24; // [rsp+B0h] [rbp+8h]
  struct QUEUE_FORMAT *v25; // [rsp+C8h] [rbp+20h] BYREF

  v25 = 0;
  v20 = 0;
  DeviceExtension = (char *)a1->DeviceExtension;
  ProbeForRead(Address, 0x38u, 1u);
  v5 = *(_DWORD *)Address[1].Data4;
  Data1 = Address[3].Data1;
  v24 = Data1;
  v22 = *(volatile void **)&Address[2].Data1;
  v21 = *(volatile void **)Address[2].Data4;
  v23 = *Address;
  v7 = *(void **)&Address[1].Data1;
  ACProbeArrayElementsForRead(v7, 0x20u, v5);
  ACDeepCopyQueueFormat((struct QUEUE_FORMAT *)v7, v5, &v25);
  ProbeForRead(v21, Data1, 1u);
  ProbeForRead(v22, 8LL * Data1, 1u);
  v8 = CQMInterface::TakeOpenQueueRequest((CQMInterface *)(DeviceExtension + 72), &v23, &v20);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v11 = v20;
    v12 = (struct _FILE_OBJECT *)*((_QWORD *)v20 + 3);
    v13 = (CDistribution *)operator new(0x1A0u, 0x40u, 0x4441514Du, LowPoolPriority);
    if ( v13 )
      v14 = CDistribution::CDistribution(v13, a1, v12);
    else
      v14 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        194,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        v14,
        v24);
    }
    if ( v14 )
    {
      v17 = v25;
      v16 = CDistribution::SetTopLevelQueueFormats(v14, v5, v25);
      if ( v16 >= 0 )
      {
        v12->FsContext = v14;
        *((_DWORD *)v12->FsContext2 + 5) |= 1u;
        *((_DWORD *)v12->FsContext2 + 5) &= ~4u;
        *((_DWORD *)v12->FsContext2 + 5) &= ~2u;
        for ( i = 0; (unsigned int)i < v24; i = (unsigned int)(i + 1) )
        {
          v16 = CDistribution::AddMember(v14, *((void **)v22 + i), *((_BYTE *)v21 + i));
          if ( v16 < 0 )
            break;
          FsContext2 = v12->FsContext2;
          if ( *((_BYTE *)v21 + i) )
            FsContext2[5] |= 2u;
          else
            FsContext2[5] |= 4u;
        }
      }
      else
      {
        v16 = -1073741670;
        v15 = (CQMInterface *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            196,
            WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
            3221225626LL);
        }
      }
    }
    else
    {
      v15 = (CQMInterface *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 195, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
      }
      v16 = -1073741670;
      v17 = v25;
    }
    if ( v17 )
      ACFreeDeepCopyQueueFormat(v17, v5);
    if ( v11 )
      return (unsigned int)CQMInterface::CompleteOpenQueueRequest(v15, v11, v16);
    return (unsigned int)v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        193,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v8);
    }
    return v9;
  }
}

```

## disassembly

```asm
0x140004d64  mov     rax, rsp
0x140004d67  mov     [rax+10h], rdx
0x140004d6b  push    rbx
0x140004d6c  push    rsi
0x140004d6d  push    rdi
0x140004d6e  push    r12
0x140004d70  push    r13
0x140004d72  push    r14
0x140004d74  push    r15
0x140004d76  sub     rsp, 70h
0x140004d7a  mov     rbx, rdx
0x140004d7d  mov     rdi, rcx
0x140004d80  mov     dword ptr [rax-74h], 0
0x140004d87  mov     qword ptr [rax+20h], 0
0x140004d8f  mov     qword ptr [rax-68h], 0
0x140004d97  mov     rsi, [rcx+40h]
0x140004d9b  mov     edx, 38h ; '8'; Length
0x140004da0  lea     r8d, [rdx-37h]; Alignment
0x140004da4  mov     rcx, rbx; Address
0x140004da7  call    cs:__imp_ProbeForRead
0x140004dae  nop     dword ptr [rax+rax+00h]
0x140004db3  mov     r12d, [rbx+18h]
0x140004db7  mov     [rsp+0A8h+arg_10], r12d
0x140004dbf  mov     [rsp+0A8h+var_74], r12d
0x140004dc4  mov     r14d, [rbx+30h]
0x140004dc8  mov     [rsp+0A8h+arg_0], r14d
0x140004dd0  mov     r13, [rbx+20h]
0x140004dd4  mov     [rsp+0A8h+var_58], r13
0x140004dd9  mov     r15, [rbx+28h]
0x140004ddd  mov     [rsp+0A8h+var_60], r15
0x140004de2  movups  xmm0, xmmword ptr [rbx]
0x140004de5  movdqu  xmmword ptr [rsp+0A8h+var_50.Data1], xmm0
0x140004deb  mov     rbx, [rbx+10h]
0x140004def  mov     r8d, r12d; unsigned int
0x140004df2  mov     edx, 20h ; ' '; unsigned int
0x140004df7  mov     rcx, rbx; void *
0x140004dfa  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x140004dff  lea     r8, [rsp+0A8h+arg_18]; struct QUEUE_FORMAT **
0x140004e07  mov     edx, r12d; unsigned int
0x140004e0a  mov     rcx, rbx; struct QUEUE_FORMAT *
0x140004e0d  call    ?ACDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@KPEAPEAU1@@Z; ACDeepCopyQueueFormat(QUEUE_FORMAT *,ulong,QUEUE_FORMAT * *)
0x140004e12  mov     ebx, r14d
0x140004e15  mov     r14d, 1
0x140004e1b  mov     r8d, r14d; Alignment
0x140004e1e  mov     edx, ebx; Length
0x140004e20  mov     rcx, r15; Address
0x140004e23  call    cs:__imp_ProbeForRead
0x140004e2a  nop     dword ptr [rax+rax+00h]
0x140004e2f  lea     rdx, ds:0[rbx*8]; Length
0x140004e37  mov     r8d, r14d; Alignment
0x140004e3a  mov     rcx, r13; Address
0x140004e3d  call    cs:__imp_ProbeForRead
0x140004e44  nop     dword ptr [rax+rax+00h]
0x140004e49  lea     rcx, [rsi+48h]; this
0x140004e4d  lea     r8, [rsp+0A8h+var_68]; struct CACOpenQueueRequest **
0x140004e52  lea     rdx, [rsp+0A8h+var_50]; struct _GUID *
0x140004e57  call    ?TakeOpenQueueRequest@CQMInterface@@QEAAJAEBU_GUID@@PEAPEAVCACOpenQueueRequest@@@Z; CQMInterface::TakeOpenQueueRequest(_GUID const &,CACOpenQueueRequest * *)
0x140004e5c  mov     ebx, eax
0x140004e5e  mov     [rsp+0A8h+var_78], eax
0x140004e62  test    eax, eax
0x140004e64  jns     short loc_140004EA0
0x140004e66  lea     rdi, WPP_GLOBAL_Control
0x140004e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e74  cmp     rcx, rdi
0x140004e77  jz      short loc_140004E99
0x140004e79  mov     edx, [rcx+6Ch]
0x140004e7c  test    r14b, dl
0x140004e7f  jz      short loc_140004E99
0x140004e81  mov     edx, 0C1h
0x140004e86  mov     r9d, eax
0x140004e89  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004e90  mov     rcx, [rcx+58h]
0x140004e94  call    WPP_SF_d
0x140004e99  mov     eax, ebx
0x140004e9b  jmp     loc_1400050AE
0x140004ea0  mov     r13, [rsp+0A8h+var_68]
0x140004ea5  mov     r14, [r13+18h]
0x140004ea9  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x140004eac  lea     edx, [r9+40h]; unsigned __int64
0x140004eb0  mov     ecx, 1A0h; unsigned __int64
0x140004eb5  mov     r8d, 4441514Dh; unsigned int
0x140004ebb  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140004ec0  test    rax, rax
0x140004ec3  jz      short loc_140004ED8
0x140004ec5  mov     r8, r14; struct _FILE_OBJECT *
0x140004ec8  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x140004ecb  mov     rcx, rax; this
0x140004ece  call    ??0CDistribution@@QEAA@PEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@@Z; CDistribution::CDistribution(_DEVICE_OBJECT *,_FILE_OBJECT *)
0x140004ed3  mov     r15, rax
0x140004ed6  jmp     short loc_140004EDB
0x140004ed8  xor     r15d, r15d
0x140004edb  lea     rdi, WPP_GLOBAL_Control
0x140004ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ee9  cmp     rcx, rdi
0x140004eec  jz      short loc_140004F18
0x140004eee  mov     eax, [rcx+6Ch]
0x140004ef1  test    al, 4
0x140004ef3  jz      short loc_140004F18
0x140004ef5  mov     edx, 0C2h
0x140004efa  mov     eax, [rsp+0A8h+arg_0]
0x140004f01  mov     [rsp+0A8h+var_88], eax
0x140004f05  mov     r9, r15
0x140004f08  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004f0f  mov     rcx, [rcx+58h]
0x140004f13  call    WPP_SF_qD
0x140004f18  test    r15, r15
0x140004f1b  jnz     short loc_140004F5B
0x140004f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f24  cmp     rcx, rdi
0x140004f27  jz      short loc_140004F45
0x140004f29  mov     eax, [rcx+6Ch]
0x140004f2c  test    al, 1
0x140004f2e  jz      short loc_140004F45
0x140004f30  mov     edx, 0C3h
0x140004f35  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004f3c  mov     rcx, [rcx+58h]
0x140004f40  call    WPP_SF_
0x140004f45  mov     ebx, 0C000009Ah
0x140004f4a  mov     [rsp+0A8h+var_78], ebx
0x140004f4e  mov     rsi, [rsp+0A8h+arg_18]
0x140004f56  jmp     loc_14000508A
0x140004f5b  mov     rsi, [rsp+0A8h+arg_18]
0x140004f63  mov     r8, rsi; struct QUEUE_FORMAT *
0x140004f66  mov     edx, r12d; unsigned int
0x140004f69  mov     rcx, r15; this
0x140004f6c  call    ?SetTopLevelQueueFormats@CDistribution@@QEAAJKQEBUQUEUE_FORMAT@@@Z; CDistribution::SetTopLevelQueueFormats(ulong,QUEUE_FORMAT const * const)
0x140004f71  mov     ebx, eax
0x140004f73  mov     [rsp+0A8h+var_78], eax
0x140004f77  test    eax, eax
0x140004f79  jns     short loc_140004FB7
0x140004f7b  mov     ebx, 0C000009Ah
0x140004f80  mov     [rsp+0A8h+var_78], ebx
0x140004f84  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f8b  cmp     rcx, rdi
0x140004f8e  jz      short loc_140004FB2
0x140004f90  mov     eax, [rcx+6Ch]
0x140004f93  test    al, 1
0x140004f95  jz      short loc_140004FB2
0x140004f97  mov     edx, 0C4h
0x140004f9c  mov     r9d, 0C000009Ah
0x140004fa2  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004fa9  mov     rcx, [rcx+58h]
0x140004fad  call    WPP_SF_d
0x140004fb2  jmp     loc_14000508A
0x140004fb7  mov     [r14+18h], r15
0x140004fbb  mov     rax, [r14+20h]
0x140004fbf  or      dword ptr [rax+14h], 1
0x140004fc3  mov     rax, [r14+20h]
0x140004fc7  and     dword ptr [rax+14h], 0FFFFFFFBh
0x140004fcb  mov     rax, [r14+20h]
0x140004fcf  and     dword ptr [rax+14h], 0FFFFFFFDh
0x140004fd3  xor     edi, edi
0x140004fd5  mov     [rsp+0A8h+var_70], edi
0x140004fd9  cmp     edi, [rsp+0A8h+arg_0]
0x140004fe0  jnb     short loc_14000502D
0x140004fe2  mov     r8, [rsp+0A8h+var_60]
0x140004fe7  mov     r8b, [rdi+r8]; bool
0x140004feb  mov     rax, [rsp+0A8h+var_58]
0x140004ff0  mov     rdx, [rax+rdi*8]; void *
0x140004ff4  mov     rcx, r15; this
0x140004ff7  call    ?AddMember@CDistribution@@QEAAJPEAX_N@Z; CDistribution::AddMember(void *,bool)
0x140004ffc  mov     ebx, eax
0x140004ffe  mov     [rsp+0A8h+var_78], eax
0x140005002  test    eax, eax
0x140005004  jns     short loc_140005010
0x140005006  mov     r12d, [rsp+0A8h+arg_10]
0x14000500e  jmp     short loc_14000508A
0x140005010  mov     rax, [rsp+0A8h+var_60]
0x140005015  cmp     byte ptr [rdi+rax], 0
0x140005019  mov     rax, [r14+20h]
0x14000501d  jz      short loc_140005025
0x14000501f  or      dword ptr [rax+14h], 2
0x140005023  jmp     short loc_140005029
0x140005025  or      dword ptr [rax+14h], 4
0x140005029  inc     edi
0x14000502b  jmp     short loc_140004FD5
0x14000502d  mov     r12d, [rsp+0A8h+arg_10]
0x140005035  jmp     short loc_14000508A
0x140005037  mov     ebx, eax
0x140005039  mov     [rsp+0A8h+var_78], eax
0x14000503d  lea     rax, WPP_GLOBAL_Control
0x140005044  mov     rcx, cs:WPP_GLOBAL_Control
0x14000504b  cmp     rcx, rax
0x14000504e  jz      short loc_140005078
0x140005050  mov     eax, [rcx+6Ch]
0x140005053  test    al, 1
0x140005055  jz      short loc_140005078
0x140005057  mov     edx, 0C5h
0x14000505c  mov     [rsp+0A8h+var_88], ebx
0x140005060  mov     r9, [rsp+0A8h+arg_8]
0x140005068  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000506f  mov     rcx, [rcx+58h]
0x140005073  call    WPP_SF_qD
0x140005078  mov     r12d, [rsp+0A8h+var_74]
0x14000507d  mov     rsi, [rsp+0A8h+arg_18]
0x140005085  mov     r13, [rsp+0A8h+var_68]
0x14000508a  test    rsi, rsi
0x14000508d  jz      short loc_14000509A
0x14000508f  mov     edx, r12d; unsigned int
0x140005092  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140005095  call    ?ACFreeDeepCopyQueueFormat@@YAXPEAUQUEUE_FORMAT@@K@Z; ACFreeDeepCopyQueueFormat(QUEUE_FORMAT *,ulong)
0x14000509a  test    r13, r13
0x14000509d  jz      short loc_1400050AC
0x14000509f  mov     r8d, ebx; int
0x1400050a2  mov     rdx, r13; struct CACOpenQueueRequest *
0x1400050a5  call    ?CompleteOpenQueueRequest@CQMInterface@@QEAAJPEAVCACOpenQueueRequest@@J@Z; CQMInterface::CompleteOpenQueueRequest(CACOpenQueueRequest *,long)
0x1400050aa  mov     ebx, eax
0x1400050ac  mov     eax, ebx
0x1400050ae  add     rsp, 70h
0x1400050b2  pop     r15
0x1400050b4  pop     r14
0x1400050b6  pop     r13
0x1400050b8  pop     r12
0x1400050ba  pop     rdi
0x1400050bb  pop     rsi
0x1400050bc  pop     rbx
0x1400050bd  retn
```
