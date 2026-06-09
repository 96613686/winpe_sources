# VidSchiCreateDeviceInternal

- ea: `0x140111370`
- end: `0x140111746`
- name: `VidSchiCreateDeviceInternal`
- size: `982`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400d9290`
- `0x1400d931c`

## callees

- `0x1400045ec`
- `0x14000a240`
- `0x14002f510`
- `0x14002f550`
- `0x140037d28`
- `0x140043774`
- `0x140044ef8`
- `0x1400aba50`
- `0x1400d90a0`
- `0x140111370`
- `0x14011174c`
- `0x140111820`
- `0x14011a2cc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140111617`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140111617`
- `ntoskrnl!ExInitializeResourceLite` at `0x140111431`
- `ntoskrnl!ExInitializeResourceLite` at `0x140111431`
- `ntoskrnl!ExAllocatePool2` at `0x1401113ed`
- `ntoskrnl!ExAllocatePool2` at `0x1401113ed`
- `watchdog!WdLogSingleEntry0` at `0x1401113a6`
- `watchdog!WdLogSingleEntry0` at `0x140111404`
- `watchdog!WdLogSingleEntry0` at `0x1401113a6`
- `watchdog!WdLogSingleEntry0` at `0x140111404`
- `watchdog!WdLogSingleEntry1` at `0x1401116a9`
- `watchdog!WdLogSingleEntry1` at `0x140111725`
- `watchdog!WdLogSingleEntry1` at `0x1401116a9`
- `watchdog!WdLogSingleEntry1` at `0x140111725`

## string_xrefs

- `0x1401116c4`: `Failed to create VidSchDevice, VidSchControlVSyncDevice returned 0x%I64x`

## pseudocode

```c
__int64 __fastcall VidSchiCreateDeviceInternal(struct _VIDSCH_GLOBAL *a1, __int128 *a2, __int64 a3, __int64 *a4)
{
  __int64 result; // rax
  struct DXGPROCESS *Current; // r15
  __int64 Pool2; // rax
  __int64 v11; // rbx
  __int128 v12; // xmm0
  __int64 v13; // xmm1_8
  __int64 v14; // rdi
  unsigned __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rsi
  __int64 v18; // r8
  int v19; // ecx
  unsigned int v20; // edx
  void *KmdProcessHandle; // rax
  ADAPTER_RENDER *v22; // rcx
  bool v23; // zf
  unsigned int v24; // edi
  unsigned int CurrentProcessId; // r9d
  int v26; // eax
  int v27; // ecx
  int v28; // r8d
  unsigned int i; // edi
  int v30; // eax
  _DXGKARG_CREATEDEVICE v31; // [rsp+70h] [rbp-68h] BYREF

  *a4 = 0;
  if ( (*(_DWORD *)a2 & 1) != 0 )
  {
    Current = *(struct DXGPROCESS **)(g_pVidSchSystemProcess + 8);
  }
  else
  {
    if ( !a3 )
    {
      WdLogSingleEntry0(3);
      result = 3221225485LL;
      WdLogGlobalForLineNumber = 3688;
      return result;
    }
    Current = DXGPROCESS::GetCurrent();
  }
  Pool2 = ExAllocatePool2(64, 1984, 862021974);
  v11 = Pool2;
  if ( !Pool2 )
  {
    WdLogSingleEntry0(3);
    result = 3221225495LL;
    WdLogGlobalForLineNumber = 3707;
    return result;
  }
  *(_DWORD *)Pool2 = 862021974;
  *(_QWORD *)(Pool2 + 8) = a3;
  ExInitializeResourceLite((PERESOURCE)(Pool2 + 1232));
  v12 = *a2;
  *(_QWORD *)(v11 + 40) = a1;
  v13 = *((_QWORD *)a2 + 2);
  *(_OWORD *)(v11 + 56) = v12;
  *(_DWORD *)(v11 + 512) = -1;
  *(_QWORD *)(v11 + 72) = v13;
  VidSchiReadDeviceConfiguration(v11);
  *(_QWORD *)(v11 + 88) = v11 + 80;
  *(_QWORD *)(v11 + 80) = v11 + 80;
  *(_QWORD *)(v11 + 104) = v11 + 96;
  *(_QWORD *)(v11 + 96) = v11 + 96;
  *(_QWORD *)(v11 + 1880) = v11 + 1872;
  *(_QWORD *)(v11 + 1872) = v11 + 1872;
  *(_QWORD *)(v11 + 136) = v11 + 128;
  *(_QWORD *)(v11 + 128) = v11 + 128;
  *(_QWORD *)(v11 + 152) = v11 + 144;
  *(_QWORD *)(v11 + 144) = v11 + 144;
  *(_QWORD *)(v11 + 168) = v11 + 160;
  *(_QWORD *)(v11 + 160) = v11 + 160;
  *(_QWORD *)(v11 + 184) = v11 + 176;
  *(_QWORD *)(v11 + 176) = v11 + 176;
  *(_QWORD *)(v11 + 1976) = 0;
  VidSchSetQueuedPresentLimit(v11, 0);
  memset64((void *)(v11 + 384), 1u, 0x10u);
  VidSchiIncrementDeviceReference(v11);
  VidSchiInterlockedInsertTailList((char *)a1 + 2096, (char *)a1 + 440, v11 + 112, 0);
  if ( (*(_DWORD *)a2 & 1) != 0 )
  {
    v14 = g_pVidSchSystemProcess;
  }
  else
  {
    v14 = *((_QWORD *)Current + 8);
    if ( v14 )
      v14 = *(_QWORD *)(v14 + 24);
  }
  v15 = *((unsigned int *)a1 + 1);
  *(_QWORD *)(v11 + 48) = v14;
  v16 = *(_DWORD *)(*(_QWORD *)(v14 + 2624) + 4 * (v15 >> 5));
  if ( _bittest(&v16, v15 & 0x1F) )
  {
    LODWORD(v17) = -1073741790;
  }
  else
  {
    LODWORD(v17) = VidSchiOpenProcessAdapterInfo((struct _VIDSCH_PROCESS *)v14, a1);
    if ( (int)v17 >= 0 )
    {
      v19 = *(_DWORD *)a2;
      *(_BYTE *)(v11 + 248) = 1;
      if ( (v19 & 1) != 0 )
      {
        v20 = *((_DWORD *)a1 + 1);
        HIDWORD(v31.hKmdProcess) = 0;
        *(_OWORD *)((char *)&v31.pInfo + 4) = 0;
        v31.hDevice = 0;
        v31.Flags.Value = 1;
        KmdProcessHandle = DXGPROCESS::GetKmdProcessHandle(Current, v20);
        v22 = (ADAPTER_RENDER *)*((_QWORD *)a1 + 1);
        v31.hKmdProcess = KmdProcessHandle;
        LODWORD(v17) = ADAPTER_RENDER::DdiCreateDevice(v22, &v31);
        if ( (int)v17 < 0 )
          goto LABEL_15;
        v23 = bTracingEnabled == 0;
        *(_QWORD *)(v11 + 24) = v31.hDevice;
        if ( !v23 )
        {
          v24 = *(_DWORD *)(v11 + 56);
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          if ( (byte_140086201 & 8) != 0 )
            McTemplateK0ppqpttqpqp_EtwWriteTransfer(
              (v24 >> 2) & 1,
              (unsigned int)EventCreateDevice,
              v18,
              CurrentProcessId,
              *((_QWORD *)a1 + 2));
        }
      }
      else
      {
        *(_QWORD *)(v11 + 24) = *(_QWORD *)(a3 + 616);
      }
      if ( (*(_DWORD *)(v11 + 56) & 2) != 0 )
      {
        if ( *((_BYTE *)a1 + 2580) )
        {
          for ( i = 0; i < *((_DWORD *)a1 + 12); ++i )
          {
            if ( *(_DWORD *)(*((_QWORD *)a1 + i + 441) + 4LL) )
            {
              LOBYTE(v18) = 1;
              v30 = VidSchControlVSyncDevice(v11, 2, v18, i);
              v17 = v30;
              if ( v30 < 0 )
              {
                WdLogSingleEntry1(1, v30);
                WdLogGlobalForLineNumber = 3895;
                goto LABEL_28;
              }
            }
          }
        }
        else
        {
          LOBYTE(v18) = 1;
          v26 = VidSchControlVSyncDevice(v11, 2, v18, 4294967293LL);
          v17 = v26;
          if ( v26 < 0 )
          {
            WdLogSingleEntry1(1, v26);
            WdLogGlobalForLineNumber = 3882;
LABEL_28:
            DxgkLogInternalTriageEvent(
              v27,
              0x40000,
              v28,
              (unsigned int)L"Failed to create VidSchDevice, VidSchControlVSyncDevice returned 0x%I64x",
              v17,
              0,
              0,
              0);
            goto LABEL_15;
          }
        }
      }
      *a4 = v11;
      return (unsigned int)v17;
    }
  }
LABEL_15:
  VidSchTerminateDevice((char *)v11);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140111370  push    rbx
0x140111372  push    rbp
0x140111373  push    rsi
0x140111374  push    rdi
0x140111375  push    r12
0x140111377  push    r13
0x140111379  push    r14
0x14011137b  push    r15
0x14011137d  sub     rsp, 98h
0x140111384  mov     qword ptr [r9], 0
0x14011138b  mov     r13, r9
0x14011138e  mov     eax, [rdx]
0x140111390  mov     r14, r8
0x140111393  mov     r12, rdx
0x140111396  mov     rbp, rcx
0x140111399  test    al, 1
0x14011139b  jnz     short loc_1401113D0
0x14011139d  test    r8, r8
0x1401113a0  jnz     short loc_1401113C6
0x1401113a2  lea     ecx, [r8+3]
0x1401113a6  call    cs:__imp_WdLogSingleEntry0
0x1401113ad  nop     dword ptr [rax+rax+00h]
0x1401113b2  mov     eax, 0C000000Dh
0x1401113b7  mov     cs:WdLogGlobalForLineNumber, 0E68h
0x1401113c1  jmp     loc_14011155B
0x1401113c6  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401113cb  mov     r15, rax
0x1401113ce  jmp     short loc_1401113DB
0x1401113d0  mov     rax, cs:g_pVidSchSystemProcess
0x1401113d7  mov     r15, [rax+8]
0x1401113db  mov     edi, 33616956h
0x1401113e0  mov     edx, 7C0h
0x1401113e5  mov     r8d, edi
0x1401113e8  mov     ecx, 40h ; '@'
0x1401113ed  call    cs:__imp_ExAllocatePool2
0x1401113f4  nop     dword ptr [rax+rax+00h]
0x1401113f9  mov     rbx, rax
0x1401113fc  test    rax, rax
0x1401113ff  jnz     short loc_140111424
0x140111401  lea     ecx, [rax+3]
0x140111404  call    cs:__imp_WdLogSingleEntry0
0x14011140b  nop     dword ptr [rax+rax+00h]
0x140111410  mov     eax, 0C0000017h
0x140111415  mov     cs:WdLogGlobalForLineNumber, 0E7Bh
0x14011141f  jmp     loc_14011155B
0x140111424  lea     rcx, [rax+4D0h]; Resource
0x14011142b  mov     [rax], edi
0x14011142d  mov     [rax+8], r14
0x140111431  call    cs:__imp_ExInitializeResourceLite
0x140111438  nop     dword ptr [rax+rax+00h]
0x14011143d  movups  xmm0, xmmword ptr [r12]
0x140111442  mov     rcx, rbx
0x140111445  mov     [rbx+28h], rbp
0x140111449  movsd   xmm1, qword ptr [r12+10h]
0x140111450  movups  xmmword ptr [rbx+38h], xmm0
0x140111454  mov     dword ptr [rbx+200h], 0FFFFFFFFh
0x14011145e  movsd   qword ptr [rbx+48h], xmm1
0x140111463  call    VidSchiReadDeviceConfiguration
0x140111468  lea     rax, [rbx+50h]
0x14011146c  xor     edx, edx
0x14011146e  mov     [rax+8], rax
0x140111472  mov     rcx, rbx
0x140111475  mov     [rax], rax
0x140111478  lea     rax, [rbx+60h]
0x14011147c  mov     [rax+8], rax
0x140111480  mov     [rax], rax
0x140111483  lea     rax, [rbx+750h]
0x14011148a  mov     [rax+8], rax
0x14011148e  mov     [rax], rax
0x140111491  lea     rax, [rbx+80h]
0x140111498  mov     [rax+8], rax
0x14011149c  mov     [rax], rax
0x14011149f  lea     rax, [rbx+90h]
0x1401114a6  mov     [rax+8], rax
0x1401114aa  mov     [rax], rax
0x1401114ad  lea     rax, [rbx+0A0h]
0x1401114b4  mov     [rax+8], rax
0x1401114b8  mov     [rax], rax
0x1401114bb  lea     rax, [rbx+0B0h]
0x1401114c2  mov     [rax+8], rax
0x1401114c6  mov     [rax], rax
0x1401114c9  mov     qword ptr [rbx+7B8h], 0
0x1401114d4  call    VidSchSetQueuedPresentLimit
0x1401114d9  mov     eax, 1
0x1401114de  lea     rdi, [rbx+180h]
0x1401114e5  lea     ecx, [rax+0Fh]
0x1401114e8  rep stosq
0x1401114eb  mov     rcx, rbx
0x1401114ee  call    VidSchiIncrementDeviceReference
0x1401114f3  lea     r8, [rbx+70h]
0x1401114f7  xor     r9d, r9d
0x1401114fa  lea     rdx, [rbp+1B8h]
0x140111501  lea     rcx, [rbp+830h]
0x140111508  call    VidSchiInterlockedInsertTailList
0x14011150d  mov     eax, [r12]
0x140111511  test    al, 1
0x140111513  jnz     short loc_140111526
0x140111515  mov     rdi, [r15+40h]
0x140111519  test    rdi, rdi
0x14011151c  jz      short loc_140111524
0x14011151e  mov     rdi, [rdi+18h]
0x140111522  jmp     short loc_14011152D
0x140111524  jmp     short loc_14011152D
0x140111526  mov     rdi, cs:g_pVidSchSystemProcess
0x14011152d  mov     ecx, [rbp+4]
0x140111530  mov     edx, ecx
0x140111532  mov     [rbx+30h], rdi
0x140111536  mov     rax, [rdi+0A40h]
0x14011153d  and     ecx, 1Fh
0x140111540  shr     rdx, 5
0x140111544  mov     eax, [rax+rdx*4]
0x140111547  bt      eax, ecx
0x14011154a  jnb     short loc_140111570
0x14011154c  mov     esi, 0C0000022h
0x140111551  mov     rcx, rbx; P
0x140111554  call    VidSchTerminateDevice
0x140111559  mov     eax, esi
0x14011155b  add     rsp, 98h
0x140111562  pop     r15
0x140111564  pop     r14
0x140111566  pop     r13
0x140111568  pop     r12
0x14011156a  pop     rdi
0x14011156b  pop     rsi
0x14011156c  pop     rbp
0x14011156d  pop     rbx
0x14011156e  retn
0x140111570  mov     rdx, rbp; struct _VIDSCH_GLOBAL *
0x140111573  mov     rcx, rdi; struct _VIDSCH_PROCESS *
0x140111576  call    VidSchiOpenProcessAdapterInfo
0x14011157b  mov     esi, eax
0x14011157d  test    eax, eax
0x14011157f  js      short loc_140111551
0x140111581  mov     ecx, [r12]
0x140111585  xor     r12d, r12d
0x140111588  mov     byte ptr [rbx+0F8h], 1
0x14011158f  test    cl, 1
0x140111592  jnz     short loc_1401115A4
0x140111594  mov     rcx, [r14+268h]
0x14011159b  mov     [rbx+18h], rcx
0x14011159f  jmp     loc_140111668
0x1401115a4  mov     edx, [rbp+4]; unsigned int
0x1401115a7  xorps   xmm0, xmm0
0x1401115aa  mov     rcx, r15; this
0x1401115ad  mov     dword ptr [rsp+0D8h+var_68.hKmdProcess+4], r12d
0x1401115b5  movdqu  xmmword ptr [rsp+0D8h+var_68.8+4], xmm0
0x1401115bb  mov     [rsp+0D8h+var_68.hDevice], r12
0x1401115c0  mov     dword ptr [rsp+0D8h+var_68.8], 1
0x1401115c8  call    ?GetKmdProcessHandle@DXGPROCESS@@QEBAPEAXI@Z; DXGPROCESS::GetKmdProcessHandle(uint)
0x1401115cd  mov     rcx, [rbp+8]; this
0x1401115d1  lea     rdx, [rsp+0D8h+var_68]; struct _DXGKARG_CREATEDEVICE *
0x1401115d6  mov     [rsp+0D8h+var_68.hKmdProcess], rax
0x1401115de  call    ?DdiCreateDevice@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_CREATEDEVICE@@@Z; ADAPTER_RENDER::DdiCreateDevice(_DXGKARG_CREATEDEVICE *)
0x1401115e3  mov     esi, eax
0x1401115e5  test    eax, eax
0x1401115e7  js      loc_140111551
0x1401115ed  cmp     cs:bTracingEnabled, r12b
0x1401115f4  mov     rax, [rsp+0D8h+var_68.hDevice]
0x1401115f9  mov     [rbx+18h], rax
0x1401115fd  jz      short loc_140111668
0x1401115ff  test    r14, r14
0x140111602  jz      short loc_14011160E
0x140111604  mov     r15, [r14+28h]
0x140111608  mov     r14, [r14+70h]
0x14011160c  jmp     short loc_140111614
0x14011160e  mov     r15, r12
0x140111611  mov     r14, r12
0x140111614  mov     edi, [rbx+38h]
0x140111617  call    cs:__imp_PsGetCurrentProcessId
0x14011161e  nop     dword ptr [rax+rax+00h]
0x140111623  test    cs:byte_140086201, 8
0x14011162a  mov     r9, rax
0x14011162d  jz      short loc_140111668
0x14011162f  mov     rax, [rbp+10h]
0x140111633  lea     rdx, EventCreateDevice
0x14011163a  mov     [rsp+0D8h+var_78], r14
0x14011163f  mov     ecx, edi
0x140111641  mov     [rsp+0D8h+var_88], r15
0x140111646  shr     ecx, 2
0x140111649  shr     edi, 1
0x14011164b  and     ecx, 1
0x14011164e  mov     [rsp+0D8h+var_98], ecx
0x140111652  and     edi, 1
0x140111655  mov     dword ptr [rsp+0D8h+var_A0], edi
0x140111659  mov     [rsp+0D8h+var_A8], rbx
0x14011165e  mov     [rsp+0D8h+var_B8], rax
0x140111663  call    McTemplateK0ppqpttqpqp_EtwWriteTransfer
0x140111668  mov     eax, [rbx+38h]
0x14011166b  mov     r14d, 2
0x140111671  test    r14b, al
0x140111674  jz      loc_14011173D
0x14011167a  cmp     [rbp+0A14h], r12b
0x140111681  jnz     short loc_1401116E9
0x140111683  mov     r9d, 0FFFFFFFDh
0x140111689  mov     r8b, 1
0x14011168c  mov     edx, r14d
0x14011168f  mov     rcx, rbx
0x140111692  call    VidSchControlVSyncDevice
0x140111697  movsxd  rsi, eax
0x14011169a  test    eax, eax
0x14011169c  jns     loc_14011173D
0x1401116a2  mov     rdx, rsi
0x1401116a5  lea     ecx, [r14-1]
0x1401116a9  call    cs:__imp_WdLogSingleEntry1
0x1401116b0  nop     dword ptr [rax+rax+00h]
0x1401116b5  mov     cs:WdLogGlobalForLineNumber, 0F2Ah
0x1401116bf  mov     [rsp+0D8h+var_A0], r12
0x1401116c4  lea     r9, aFailedToCreate_15; "Failed to create VidSchDevice, VidSchCo"...
0x1401116cb  mov     [rsp+0D8h+var_A8], r12
0x1401116d0  mov     edx, 40000h
0x1401116d5  mov     [rsp+0D8h+var_B0], r12
0x1401116da  mov     [rsp+0D8h+var_B8], rsi
0x1401116df  call    DxgkLogInternalTriageEvent
0x1401116e4  jmp     loc_140111551
0x1401116e9  mov     edi, r12d
0x1401116ec  cmp     edi, [rbp+30h]
0x1401116ef  jnb     short loc_14011173D
0x1401116f1  mov     eax, edi
0x1401116f3  mov     rcx, [rbp+rax*8+0DC8h]
0x1401116fb  cmp     [rcx+4], r12d
0x1401116ff  jz      short loc_140111719
0x140111701  mov     r9d, edi
0x140111704  mov     r8b, 1
0x140111707  mov     edx, r14d
0x14011170a  mov     rcx, rbx
0x14011170d  call    VidSchControlVSyncDevice
0x140111712  movsxd  rsi, eax
0x140111715  test    eax, eax
0x140111717  js      short loc_14011171D
0x140111719  inc     edi
0x14011171b  jmp     short loc_1401116EC
0x14011171d  mov     rdx, rsi
0x140111720  mov     ecx, 1
0x140111725  call    cs:__imp_WdLogSingleEntry1
0x14011172c  nop     dword ptr [rax+rax+00h]
0x140111731  mov     cs:WdLogGlobalForLineNumber, 0F37h
0x14011173b  jmp     short loc_1401116BF
0x14011173d  mov     [r13+0], rbx
0x140111741  jmp     loc_140111559
```
