# SmbCseDissociateMidFromBufferContextLite

- ea: `0x140006bb0`
- end: `0x140006eac`
- name: `SmbCseDissociateMidFromBufferContextLite`
- size: `764`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140006150`
- `0x140006ec0`
- `0x14000b4b0`
- `0x140048498`

## callees

- `0x140004760`
- `0x140006bb0`
- `0x140022400`
- `0x1400383d0`
- `0x140048c0c`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140006e5d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006e5d`
- `rdbss!RxDiagnosticTrace` at `0x140006da6`
- `rdbss!RxDiagnosticTrace` at `0x140006da6`
- `rdbss!RxPostToWorkerThread` at `0x140006e8f`
- `rdbss!RxPostToWorkerThread` at `0x140006e8f`

## pseudocode

```c
char __fastcall SmbCseDissociateMidFromBufferContextLite(unsigned int *pContext, __int64 a2)
{
  char **v2; // rax
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  __int64 i; // r9
  int v8; // ebp
  unsigned int v9; // eax
  _DWORD *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  __int32 v13; // r8d
  struct _RDBSS_DEVICE_OBJECT *v14; // rdi

  LODWORD(v2) = *(_DWORD *)(a2 + 4);
  if ( ((unsigned __int8)v2 & 1) != 0 )
  {
    v5 = *(_QWORD *)(a2 + 40);
    if ( v5 >= *((_QWORD *)pContext + 8) && v5 < *((_QWORD *)pContext + 9) )
    {
      *(_QWORD *)(*((_QWORD *)pContext + 13) + 8 * (v5 % pContext[24])) = 0;
      *((_QWORD *)pContext + 15) = MEMORY[0xFFFFF78000000008];
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids, a2);
      }
      *(_DWORD *)(a2 + 4) &= ~1u;
      if ( v5 == *((_QWORD *)pContext + 8) )
      {
        v6 = pContext[24];
        for ( i = *((_QWORD *)pContext + 13); !*(_QWORD *)(i + 8 * (v5 % v6)); ++v5 )
        {
          if ( v5 >= *((_QWORD *)pContext + 9) )
            break;
        }
        v8 = v5 - pContext[16];
        v9 = pContext[20] - v8;
        *((_QWORD *)pContext + 8) = v5;
        pContext[20] = v9;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qdddi(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            v6,
            pContext,
            pContext[20],
            pContext[21],
            pContext[22],
            v5);
        }
      }
      else
      {
        v8 = 0;
      }
      v10 = pContext + 20;
      pContext[23] -= *(_DWORD *)(a2 + 732);
      if ( !pContext[20] && pContext[23] )
        __int2c();
      if ( _InterlockedExchange((volatile __int32 *)pContext + 22, 0) != v8 )
      {
        SmbCseReconcileCreditsGranted(pContext);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qdddi(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            v11,
            pContext,
            *v10,
            pContext[21],
            pContext[22],
            *((_QWORD *)pContext + 8));
        }
      }
      if ( !pContext[3] )
      {
        RxDiagnosticTrace(
          *((_QWORD *)pContext + 2),
          1,
          "WINDOW: Size %lx Limit %lx (OldPending/Next) (%lx/%lx) Creds %lx",
          *v10,
          pContext[21],
          pContext[16],
          pContext[18],
          pContext[22]);
        if ( byte_14007D25F )
        {
          if ( (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
            McTemplateK0pqqqxxd_EtwWriteTransfer(
              pContext[18],
              pContext[16],
              a2 + 880,
              (_DWORD)pContext,
              *v10,
              pContext[21],
              pContext[36],
              pContext[16],
              pContext[18],
              pContext[22]);
        }
      }
      v12 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 88LL);
      if ( v12 )
      {
        v13 = pContext[21] - *v10;
        if ( pContext[21] < *v10 )
          v13 = 0;
        _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v12 + 424) + 1492LL), v13);
      }
      v2 = (char **)(pContext + 8);
      if ( *v2 != (char *)v2 || (v2 = (char **)(pContext + 12), *v2 != (char *)v2) )
      {
        if ( !*((_BYTE *)pContext + 216) )
        {
          v14 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(*(_QWORD *)(a2 + 56) + 72LL) + 24LL);
          LOBYTE(v2) = ExAcquireRundownProtection((PEX_RUNDOWN_REF)pContext + 28);
          if ( (_BYTE)v2 )
          {
            *((_BYTE *)pContext + 216) = 1;
            LOBYTE(v2) = RxPostToWorkerThread(
                           v14,
                           NormalWorkQueue,
                           (PRX_WORK_QUEUE_ITEM)(pContext + 38),
                           SmbCsepResumeSuspendedMidAssignmentRequestsWorker,
                           pContext);
          }
        }
      }
    }
  }
  return (char)v2;
}

```

## disassembly

```asm
0x140006bb0  mov     [rsp+arg_18], rbx
0x140006bb5  push    rsi
0x140006bb6  sub     rsp, 50h
0x140006bba  mov     eax, [rdx+4]
0x140006bbd  mov     rsi, rdx
0x140006bc0  mov     rbx, rcx
0x140006bc3  test    al, 1
0x140006bc5  jz      loc_140006EA0
0x140006bcb  mov     [rsp+58h+arg_8], rdi
0x140006bd0  mov     rdi, [rdx+28h]
0x140006bd4  cmp     rdi, [rcx+40h]
0x140006bd8  jb      loc_140006E9B
0x140006bde  cmp     rdi, [rcx+48h]
0x140006be2  jnb     loc_140006E9B
0x140006be8  mov     ecx, [rcx+60h]
0x140006beb  xor     edx, edx
0x140006bed  mov     rax, rdi
0x140006bf0  mov     [rsp+58h+arg_0], rbp
0x140006bf5  div     rcx
0x140006bf8  mov     rax, [rbx+68h]
0x140006bfc  mov     [rsp+58h+arg_10], r14
0x140006c01  mov     qword ptr [rax+rdx*8], 0
0x140006c09  mov     rax, ds:0FFFFF78000000008h
0x140006c13  mov     [rbx+78h], rax
0x140006c17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006c1e  lea     r14, WPP_GLOBAL_Control
0x140006c25  cmp     rcx, r14
0x140006c28  jz      short loc_140006C4F
0x140006c2a  mov     eax, [rcx+2Ch]
0x140006c2d  test    al, al
0x140006c2f  jns     short loc_140006C4F
0x140006c31  cmp     byte ptr [rcx+29h], 4
0x140006c35  jb      short loc_140006C4F
0x140006c37  mov     rcx, [rcx+18h]
0x140006c3b  lea     r8, WPP_292ccbb15a33399a00ff0fb71a7a37d6_Traceguids
0x140006c42  mov     edx, 11h
0x140006c47  mov     r9, rsi
0x140006c4a  call    WPP_SF_q
0x140006c4f  and     dword ptr [rsi+4], 0FFFFFFFEh
0x140006c53  cmp     rdi, [rbx+40h]
0x140006c57  jnz     loc_140006CE6
0x140006c5d  mov     r8d, [rbx+60h]
0x140006c61  xor     edx, edx
0x140006c63  mov     r9, [rbx+68h]
0x140006c67  mov     rax, rdi
0x140006c6a  div     r8
0x140006c6d  cmp     qword ptr [r9+rdx*8], 0
0x140006c72  jnz     short loc_140006C8F
0x140006c74  mov     rcx, [rbx+48h]
0x140006c78  cmp     rdi, rcx
0x140006c7b  jnb     short loc_140006C8F
0x140006c7d  inc     rdi
0x140006c80  xor     edx, edx
0x140006c82  mov     rax, rdi
0x140006c85  div     r8
0x140006c88  cmp     qword ptr [r9+rdx*8], 0
0x140006c8d  jz      short loc_140006C78
0x140006c8f  mov     eax, [rbx+50h]
0x140006c92  mov     ebp, edi
0x140006c94  sub     ebp, [rbx+40h]
0x140006c97  sub     eax, ebp
0x140006c99  mov     [rbx+40h], rdi
0x140006c9d  mov     [rbx+50h], eax
0x140006ca0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006ca7  cmp     rcx, r14
0x140006caa  jz      short loc_140006CE8
0x140006cac  mov     eax, [rcx+2Ch]
0x140006caf  test    al, al
0x140006cb1  jns     short loc_140006CE8
0x140006cb3  cmp     byte ptr [rcx+29h], 4
0x140006cb7  jb      short loc_140006CE8
0x140006cb9  mov     eax, [rbx+58h]
0x140006cbc  mov     edx, 12h
0x140006cc1  mov     rcx, [rcx+18h]
0x140006cc5  mov     r9, rbx
0x140006cc8  mov     [rsp+58h+var_20], rdi
0x140006ccd  mov     [rsp+58h+var_28], eax
0x140006cd1  mov     eax, [rbx+54h]
0x140006cd4  mov     [rsp+58h+var_30], eax
0x140006cd8  mov     eax, [rbx+50h]
0x140006cdb  mov     dword ptr [rsp+58h+pContext], eax
0x140006cdf  call    WPP_SF_qdddi
0x140006ce4  jmp     short loc_140006CE8
0x140006ce6  xor     ebp, ebp
0x140006ce8  mov     eax, 50h ; 'P'
0x140006ced  mov     rcx, rbx
0x140006cf0  lea     rdi, [rax+rbx]
0x140006cf4  mov     eax, [rsi+2DCh]
0x140006cfa  sub     [rbx+5Ch], eax
0x140006cfd  cmp     dword ptr [rdi], 0
0x140006d00  mov     eax, [rbx+5Ch]
0x140006d03  jnz     short loc_140006D0B
0x140006d05  test    eax, eax
0x140006d07  jz      short loc_140006D0B
0x140006d09  int     2Ch; Windows NT - assertion failure
0x140006d0b  xor     edx, edx
0x140006d0d  xchg    edx, [rbx+58h]
0x140006d10  sub     edx, ebp
0x140006d12  mov     rbp, [rsp+58h+arg_0]
0x140006d17  jz      short loc_140006D68
0x140006d19  mov     rcx, rbx
0x140006d1c  call    SmbCseReconcileCreditsGranted
0x140006d21  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140006d28  cmp     rcx, r14
0x140006d2b  jz      short loc_140006D68
0x140006d2d  mov     eax, [rcx+2Ch]
0x140006d30  test    al, al
0x140006d32  jns     short loc_140006D68
0x140006d34  cmp     byte ptr [rcx+29h], 4
0x140006d38  jb      short loc_140006D68
0x140006d3a  mov     rax, [rbx+40h]
0x140006d3e  mov     edx, 13h
0x140006d43  mov     rcx, [rcx+18h]
0x140006d47  mov     r9, rbx
0x140006d4a  mov     [rsp+58h+var_20], rax
0x140006d4f  mov     eax, [rbx+58h]
0x140006d52  mov     [rsp+58h+var_28], eax
0x140006d56  mov     eax, [rbx+54h]
0x140006d59  mov     [rsp+58h+var_30], eax
0x140006d5d  mov     eax, [rdi]
0x140006d5f  mov     dword ptr [rsp+58h+pContext], eax
0x140006d63  call    WPP_SF_qdddi
0x140006d68  cmp     dword ptr [rbx+0Ch], 0
0x140006d6c  mov     r14, [rsp+58h+arg_10]
0x140006d71  jnz     loc_140006E01
0x140006d77  mov     eax, [rbx+58h]
0x140006d7a  lea     r8, aWindowSizeLxLi; "WINDOW: Size %lx Limit %lx (OldPending/"...
0x140006d81  mov     r9d, [rdi]
0x140006d84  mov     edx, 1
0x140006d89  mov     rcx, [rbx+10h]
0x140006d8d  mov     dword ptr [rsp+58h+var_20], eax
0x140006d91  mov     eax, [rbx+48h]
0x140006d94  mov     [rsp+58h+var_28], eax
0x140006d98  mov     eax, [rbx+40h]
0x140006d9b  mov     [rsp+58h+var_30], eax
0x140006d9f  mov     eax, [rbx+54h]
0x140006da2  mov     dword ptr [rsp+58h+pContext], eax
0x140006da6  call    cs:__imp_RxDiagnosticTrace
0x140006dad  nop     dword ptr [rax+rax+00h]
0x140006db2  cmp     cs:byte_14007D25F, 0
0x140006db9  jz      short loc_140006E01
0x140006dbb  test    cs:Microsoft_Windows_SMBClientEnableBits, 8
0x140006dc2  jz      short loc_140006E01
0x140006dc4  mov     eax, [rbx+58h]
0x140006dc7  lea     r8, [rsi+370h]
0x140006dce  mov     ecx, [rbx+48h]
0x140006dd1  mov     r9, rbx
0x140006dd4  mov     edx, [rbx+40h]
0x140006dd7  mov     [rsp+58h+var_10], eax
0x140006ddb  mov     eax, [rbx+90h]
0x140006de1  mov     [rsp+58h+var_18], rcx
0x140006de6  mov     [rsp+58h+var_20], rdx
0x140006deb  mov     [rsp+58h+var_28], eax
0x140006def  mov     eax, [rbx+54h]
0x140006df2  mov     [rsp+58h+var_30], eax
0x140006df6  mov     eax, [rdi]
0x140006df8  mov     dword ptr [rsp+58h+pContext], eax
0x140006dfc  call    McTemplateK0pqqqxxd_EtwWriteTransfer
0x140006e01  mov     rax, [rsi+38h]
0x140006e05  mov     r9, [rax+58h]
0x140006e09  test    r9, r9
0x140006e0c  jz      short loc_140006E2F
0x140006e0e  mov     ecx, [rbx+54h]
0x140006e11  xor     eax, eax
0x140006e13  mov     edx, [rdi]
0x140006e15  mov     r8d, ecx
0x140006e18  sub     r8d, edx
0x140006e1b  cmp     ecx, edx
0x140006e1d  cmovb   r8d, eax
0x140006e21  mov     rax, [r9+1A8h]
0x140006e28  xchg    r8d, [rax+5D4h]
0x140006e2f  lea     rax, [rbx+20h]
0x140006e33  cmp     [rax], rax
0x140006e36  jnz     short loc_140006E41
0x140006e38  lea     rax, [rbx+30h]
0x140006e3c  cmp     [rax], rax
0x140006e3f  jz      short loc_140006E9B
0x140006e41  cmp     byte ptr [rbx+0D8h], 0
0x140006e48  jnz     short loc_140006E9B
0x140006e4a  mov     rax, [rsi+38h]
0x140006e4e  mov     rcx, [rax+48h]
0x140006e52  mov     rdi, [rcx+18h]
0x140006e56  lea     rcx, [rbx+0E0h]; RunRef
0x140006e5d  call    cs:__imp_ExAcquireRundownProtection
0x140006e64  nop     dword ptr [rax+rax+00h]
0x140006e69  test    al, al
0x140006e6b  jz      short loc_140006E9B
0x140006e6d  lea     r8, [rbx+98h]; pWorkQueueItem
0x140006e74  mov     byte ptr [rbx+0D8h], 1
0x140006e7b  lea     r9, SmbCsepResumeSuspendedMidAssignmentRequestsWorker; Routine
0x140006e82  mov     [rsp+58h+pContext], rbx; pContext
0x140006e87  mov     edx, 3; WorkQueueType
0x140006e8c  mov     rcx, rdi; pMRxDeviceObject
0x140006e8f  call    cs:__imp_RxPostToWorkerThread
0x140006e96  nop     dword ptr [rax+rax+00h]
0x140006e9b  mov     rdi, [rsp+58h+arg_8]
0x140006ea0  mov     rbx, [rsp+58h+arg_18]
0x140006ea5  add     rsp, 50h
0x140006ea9  pop     rsi
0x140006eaa  retn
```
