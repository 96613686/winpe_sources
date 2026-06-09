# VidSchiCreateDeviceInternal

- ea: `0x140113fb0`
- end: `0x140114386`
- name: `VidSchiCreateDeviceInternal`
- size: `982`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400e16f0`
- `0x1400e177c`

## callees

- `0x140004268`
- `0x140009ed0`
- `0x14002c5d0`
- `0x14002c610`
- `0x140036d88`
- `0x1400438e4`
- `0x1400450fc`
- `0x1400ace00`
- `0x1400e1500`
- `0x140113fb0`
- `0x14011438c`
- `0x140114460`
- `0x14011dabc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140114257`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140114257`
- `ntoskrnl!ExInitializeResourceLite` at `0x140114071`
- `ntoskrnl!ExInitializeResourceLite` at `0x140114071`
- `ntoskrnl!ExAllocatePool2` at `0x14011402d`
- `ntoskrnl!ExAllocatePool2` at `0x14011402d`
- `watchdog!WdLogSingleEntry0` at `0x140113fe6`
- `watchdog!WdLogSingleEntry0` at `0x140114044`
- `watchdog!WdLogSingleEntry0` at `0x140113fe6`
- `watchdog!WdLogSingleEntry0` at `0x140114044`
- `watchdog!WdLogSingleEntry1` at `0x1401142e9`
- `watchdog!WdLogSingleEntry1` at `0x140114365`
- `watchdog!WdLogSingleEntry1` at `0x1401142e9`
- `watchdog!WdLogSingleEntry1` at `0x140114365`

## string_xrefs

- `0x140114304`: `Failed to create VidSchDevice, VidSchControlVSyncDevice returned 0x%I64x`

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
          if ( (byte_140087201 & 8) != 0 )
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
0x140113fb0  push    rbx
0x140113fb2  push    rbp
0x140113fb3  push    rsi
0x140113fb4  push    rdi
0x140113fb5  push    r12
0x140113fb7  push    r13
0x140113fb9  push    r14
0x140113fbb  push    r15
0x140113fbd  sub     rsp, 98h
0x140113fc4  mov     qword ptr [r9], 0
0x140113fcb  mov     r13, r9
0x140113fce  mov     eax, [rdx]
0x140113fd0  mov     r14, r8
0x140113fd3  mov     r12, rdx
0x140113fd6  mov     rbp, rcx
0x140113fd9  test    al, 1
0x140113fdb  jnz     short loc_140114010
0x140113fdd  test    r8, r8
0x140113fe0  jnz     short loc_140114006
0x140113fe2  lea     ecx, [r8+3]
0x140113fe6  call    cs:__imp_WdLogSingleEntry0
0x140113fed  nop     dword ptr [rax+rax+00h]
0x140113ff2  mov     eax, 0C000000Dh
0x140113ff7  mov     cs:WdLogGlobalForLineNumber, 0E68h
0x140114001  jmp     loc_14011419B
0x140114006  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14011400b  mov     r15, rax
0x14011400e  jmp     short loc_14011401B
0x140114010  mov     rax, cs:g_pVidSchSystemProcess
0x140114017  mov     r15, [rax+8]
0x14011401b  mov     edi, 33616956h
0x140114020  mov     edx, 7C0h
0x140114025  mov     r8d, edi
0x140114028  mov     ecx, 40h ; '@'
0x14011402d  call    cs:__imp_ExAllocatePool2
0x140114034  nop     dword ptr [rax+rax+00h]
0x140114039  mov     rbx, rax
0x14011403c  test    rax, rax
0x14011403f  jnz     short loc_140114064
0x140114041  lea     ecx, [rax+3]
0x140114044  call    cs:__imp_WdLogSingleEntry0
0x14011404b  nop     dword ptr [rax+rax+00h]
0x140114050  mov     eax, 0C0000017h
0x140114055  mov     cs:WdLogGlobalForLineNumber, 0E7Bh
0x14011405f  jmp     loc_14011419B
0x140114064  lea     rcx, [rax+4D0h]; Resource
0x14011406b  mov     [rax], edi
0x14011406d  mov     [rax+8], r14
0x140114071  call    cs:__imp_ExInitializeResourceLite
0x140114078  nop     dword ptr [rax+rax+00h]
0x14011407d  movups  xmm0, xmmword ptr [r12]
0x140114082  mov     rcx, rbx
0x140114085  mov     [rbx+28h], rbp
0x140114089  movsd   xmm1, qword ptr [r12+10h]
0x140114090  movups  xmmword ptr [rbx+38h], xmm0
0x140114094  mov     dword ptr [rbx+200h], 0FFFFFFFFh
0x14011409e  movsd   qword ptr [rbx+48h], xmm1
0x1401140a3  call    VidSchiReadDeviceConfiguration
0x1401140a8  lea     rax, [rbx+50h]
0x1401140ac  xor     edx, edx
0x1401140ae  mov     [rax+8], rax
0x1401140b2  mov     rcx, rbx
0x1401140b5  mov     [rax], rax
0x1401140b8  lea     rax, [rbx+60h]
0x1401140bc  mov     [rax+8], rax
0x1401140c0  mov     [rax], rax
0x1401140c3  lea     rax, [rbx+750h]
0x1401140ca  mov     [rax+8], rax
0x1401140ce  mov     [rax], rax
0x1401140d1  lea     rax, [rbx+80h]
0x1401140d8  mov     [rax+8], rax
0x1401140dc  mov     [rax], rax
0x1401140df  lea     rax, [rbx+90h]
0x1401140e6  mov     [rax+8], rax
0x1401140ea  mov     [rax], rax
0x1401140ed  lea     rax, [rbx+0A0h]
0x1401140f4  mov     [rax+8], rax
0x1401140f8  mov     [rax], rax
0x1401140fb  lea     rax, [rbx+0B0h]
0x140114102  mov     [rax+8], rax
0x140114106  mov     [rax], rax
0x140114109  mov     qword ptr [rbx+7B8h], 0
0x140114114  call    VidSchSetQueuedPresentLimit
0x140114119  mov     eax, 1
0x14011411e  lea     rdi, [rbx+180h]
0x140114125  lea     ecx, [rax+0Fh]
0x140114128  rep stosq
0x14011412b  mov     rcx, rbx
0x14011412e  call    VidSchiIncrementDeviceReference
0x140114133  lea     r8, [rbx+70h]
0x140114137  xor     r9d, r9d
0x14011413a  lea     rdx, [rbp+1B8h]
0x140114141  lea     rcx, [rbp+830h]
0x140114148  call    VidSchiInterlockedInsertTailList
0x14011414d  mov     eax, [r12]
0x140114151  test    al, 1
0x140114153  jnz     short loc_140114166
0x140114155  mov     rdi, [r15+40h]
0x140114159  test    rdi, rdi
0x14011415c  jz      short loc_140114164
0x14011415e  mov     rdi, [rdi+18h]
0x140114162  jmp     short loc_14011416D
0x140114164  jmp     short loc_14011416D
0x140114166  mov     rdi, cs:g_pVidSchSystemProcess
0x14011416d  mov     ecx, [rbp+4]
0x140114170  mov     edx, ecx
0x140114172  mov     [rbx+30h], rdi
0x140114176  mov     rax, [rdi+0A40h]
0x14011417d  and     ecx, 1Fh
0x140114180  shr     rdx, 5
0x140114184  mov     eax, [rax+rdx*4]
0x140114187  bt      eax, ecx
0x14011418a  jnb     short loc_1401141B0
0x14011418c  mov     esi, 0C0000022h
0x140114191  mov     rcx, rbx; P
0x140114194  call    VidSchTerminateDevice
0x140114199  mov     eax, esi
0x14011419b  add     rsp, 98h
0x1401141a2  pop     r15
0x1401141a4  pop     r14
0x1401141a6  pop     r13
0x1401141a8  pop     r12
0x1401141aa  pop     rdi
0x1401141ab  pop     rsi
0x1401141ac  pop     rbp
0x1401141ad  pop     rbx
0x1401141ae  retn
0x1401141b0  mov     rdx, rbp; struct _VIDSCH_GLOBAL *
0x1401141b3  mov     rcx, rdi; struct _VIDSCH_PROCESS *
0x1401141b6  call    VidSchiOpenProcessAdapterInfo
0x1401141bb  mov     esi, eax
0x1401141bd  test    eax, eax
0x1401141bf  js      short loc_140114191
0x1401141c1  mov     ecx, [r12]
0x1401141c5  xor     r12d, r12d
0x1401141c8  mov     byte ptr [rbx+0F8h], 1
0x1401141cf  test    cl, 1
0x1401141d2  jnz     short loc_1401141E4
0x1401141d4  mov     rcx, [r14+268h]
0x1401141db  mov     [rbx+18h], rcx
0x1401141df  jmp     loc_1401142A8
0x1401141e4  mov     edx, [rbp+4]; unsigned int
0x1401141e7  xorps   xmm0, xmm0
0x1401141ea  mov     rcx, r15; this
0x1401141ed  mov     dword ptr [rsp+0D8h+var_68.hKmdProcess+4], r12d
0x1401141f5  movdqu  xmmword ptr [rsp+0D8h+var_68.8+4], xmm0
0x1401141fb  mov     [rsp+0D8h+var_68.hDevice], r12
0x140114200  mov     dword ptr [rsp+0D8h+var_68.8], 1
0x140114208  call    ?GetKmdProcessHandle@DXGPROCESS@@QEBAPEAXI@Z; DXGPROCESS::GetKmdProcessHandle(uint)
0x14011420d  mov     rcx, [rbp+8]; this
0x140114211  lea     rdx, [rsp+0D8h+var_68]; struct _DXGKARG_CREATEDEVICE *
0x140114216  mov     [rsp+0D8h+var_68.hKmdProcess], rax
0x14011421e  call    ?DdiCreateDevice@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_CREATEDEVICE@@@Z; ADAPTER_RENDER::DdiCreateDevice(_DXGKARG_CREATEDEVICE *)
0x140114223  mov     esi, eax
0x140114225  test    eax, eax
0x140114227  js      loc_140114191
0x14011422d  cmp     cs:bTracingEnabled, r12b
0x140114234  mov     rax, [rsp+0D8h+var_68.hDevice]
0x140114239  mov     [rbx+18h], rax
0x14011423d  jz      short loc_1401142A8
0x14011423f  test    r14, r14
0x140114242  jz      short loc_14011424E
0x140114244  mov     r15, [r14+28h]
0x140114248  mov     r14, [r14+70h]
0x14011424c  jmp     short loc_140114254
0x14011424e  mov     r15, r12
0x140114251  mov     r14, r12
0x140114254  mov     edi, [rbx+38h]
0x140114257  call    cs:__imp_PsGetCurrentProcessId
0x14011425e  nop     dword ptr [rax+rax+00h]
0x140114263  test    cs:byte_140087201, 8
0x14011426a  mov     r9, rax
0x14011426d  jz      short loc_1401142A8
0x14011426f  mov     rax, [rbp+10h]
0x140114273  lea     rdx, EventCreateDevice
0x14011427a  mov     [rsp+0D8h+var_78], r14
0x14011427f  mov     ecx, edi
0x140114281  mov     [rsp+0D8h+var_88], r15
0x140114286  shr     ecx, 2
0x140114289  shr     edi, 1
0x14011428b  and     ecx, 1
0x14011428e  mov     [rsp+0D8h+var_98], ecx
0x140114292  and     edi, 1
0x140114295  mov     dword ptr [rsp+0D8h+var_A0], edi
0x140114299  mov     [rsp+0D8h+var_A8], rbx
0x14011429e  mov     [rsp+0D8h+var_B8], rax
0x1401142a3  call    McTemplateK0ppqpttqpqp_EtwWriteTransfer
0x1401142a8  mov     eax, [rbx+38h]
0x1401142ab  mov     r14d, 2
0x1401142b1  test    r14b, al
0x1401142b4  jz      loc_14011437D
0x1401142ba  cmp     [rbp+0A14h], r12b
0x1401142c1  jnz     short loc_140114329
0x1401142c3  mov     r9d, 0FFFFFFFDh
0x1401142c9  mov     r8b, 1
0x1401142cc  mov     edx, r14d
0x1401142cf  mov     rcx, rbx
0x1401142d2  call    VidSchControlVSyncDevice
0x1401142d7  movsxd  rsi, eax
0x1401142da  test    eax, eax
0x1401142dc  jns     loc_14011437D
0x1401142e2  mov     rdx, rsi
0x1401142e5  lea     ecx, [r14-1]
0x1401142e9  call    cs:__imp_WdLogSingleEntry1
0x1401142f0  nop     dword ptr [rax+rax+00h]
0x1401142f5  mov     cs:WdLogGlobalForLineNumber, 0F2Ah
0x1401142ff  mov     [rsp+0D8h+var_A0], r12
0x140114304  lea     r9, aFailedToCreate_15; "Failed to create VidSchDevice, VidSchCo"...
0x14011430b  mov     [rsp+0D8h+var_A8], r12
0x140114310  mov     edx, 40000h
0x140114315  mov     [rsp+0D8h+var_B0], r12
0x14011431a  mov     [rsp+0D8h+var_B8], rsi
0x14011431f  call    DxgkLogInternalTriageEvent
0x140114324  jmp     loc_140114191
0x140114329  mov     edi, r12d
0x14011432c  cmp     edi, [rbp+30h]
0x14011432f  jnb     short loc_14011437D
0x140114331  mov     eax, edi
0x140114333  mov     rcx, [rbp+rax*8+0DC8h]
0x14011433b  cmp     [rcx+4], r12d
0x14011433f  jz      short loc_140114359
0x140114341  mov     r9d, edi
0x140114344  mov     r8b, 1
0x140114347  mov     edx, r14d
0x14011434a  mov     rcx, rbx
0x14011434d  call    VidSchControlVSyncDevice
0x140114352  movsxd  rsi, eax
0x140114355  test    eax, eax
0x140114357  js      short loc_14011435D
0x140114359  inc     edi
0x14011435b  jmp     short loc_14011432C
0x14011435d  mov     rdx, rsi
0x140114360  mov     ecx, 1
0x140114365  call    cs:__imp_WdLogSingleEntry1
0x14011436c  nop     dword ptr [rax+rax+00h]
0x140114371  mov     cs:WdLogGlobalForLineNumber, 0F37h
0x14011437b  jmp     short loc_1401142FF
0x14011437d  mov     [r13+0], rbx
0x140114381  jmp     loc_140114199
```
