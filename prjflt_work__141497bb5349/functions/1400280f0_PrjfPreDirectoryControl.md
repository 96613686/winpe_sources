# PrjfPreDirectoryControl

- ea: `0x1400280f0`
- end: `0x14002845e`
- name: `PrjfPreDirectoryControl`
- size: `878`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140002d9c`
- `0x140003480`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000eda4`
- `0x140024b24`
- `0x1400280f0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400282f1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400282f1`
- `FLTMGR!FltLockUserBuffer` at `0x1400282af`
- `FLTMGR!FltLockUserBuffer` at `0x1400282af`
- `FLTMGR!FltReleaseContext` at `0x1400283fb`
- `FLTMGR!FltReleaseContext` at `0x14002840f`
- `FLTMGR!FltReleaseContext` at `0x140028427`
- `FLTMGR!FltReleaseContext` at `0x1400283fb`
- `FLTMGR!FltReleaseContext` at `0x14002840f`
- `FLTMGR!FltReleaseContext` at `0x140028427`

## pseudocode

```c
__int64 __fastcall PrjfPreDirectoryControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  char v3; // si
  unsigned int v6; // edi
  char *UnionContext; // r12
  char ContextFileObject; // al
  _DWORD *p_IrpFlags; // rdx
  PFLT_CONTEXT v10; // r13
  struct _FLT_INSTANCE *v11; // rcx
  int v12; // r8d
  int v13; // r14d
  bool v14; // zf
  int v15; // edi
  LARGE_INTEGER AllocationSize; // rcx
  KPROCESSOR_MODE RequestorMode; // al
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  ULONG_PTR v21; // rax
  int BugCheckOnFailure; // [rsp+20h] [rbp-59h]
  ULONG Priority; // [rsp+28h] [rbp-51h]
  int v25; // [rsp+30h] [rbp-49h]
  int v26; // [rsp+38h] [rbp-41h]
  int v27; // [rsp+40h] [rbp-39h]
  int v28; // [rsp+48h] [rbp-31h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-1h] BYREF
  PFLT_CONTEXT v30[2]; // [rsp+80h] [rbp+7h] BYREF
  _OWORD v31[4]; // [rsp+90h] [rbp+17h] BYREF
  unsigned int v32; // [rsp+E0h] [rbp+67h] BYREF
  PFLT_CONTEXT v33; // [rsp+F8h] [rbp+7Fh] BYREF

  Iopb = CallbackData->Iopb;
  v3 = 1;
  Context = 0;
  v32 = 0;
  v30[0] = 0;
  v6 = 1;
  v33 = 0;
  if ( Iopb->MinorFunction != 1 || (Iopb->OperationFlags & 8) != 0 )
    return v6;
  UnionContext = 0;
  ContextFileObject = PrjfGetContextFileObjectEx(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        *(PFILE_OBJECT *)(a2 + 32),
                        v30,
                        &v33,
                        &Context);
  v10 = v33;
  if ( !ContextFileObject || *(_DWORD *)v33 != 1 )
    goto LABEL_47;
  if ( Context )
  {
    v11 = *(struct _FLT_INSTANCE **)(a2 + 24);
    v31[0] = *((_OWORD *)v30[0] + 6);
    UnionContext = (char *)PrjfGetUnionContext(v11, v31);
    if ( !UnionContext )
      goto LABEL_47;
    p_IrpFlags = &CallbackData->Iopb->IrpFlags;
    v13 = p_IrpFlags[10];
    if ( v13 > 38 )
    {
      if ( v13 == 60 || v13 == 63 || v13 == 78 || v13 == 79 || v13 == 80 )
        goto LABEL_25;
      v14 = v13 == 81;
    }
    else
    {
      if ( v13 == 38 || v13 == 1 || v13 == 2 || v13 == 3 || v13 == 12 || v13 == 33 )
        goto LABEL_25;
      v14 = v13 == 37;
    }
    if ( !v14 )
    {
      LOBYTE(p_IrpFlags) = BYTE10(xmmword_14001A3D0) & 4;
      if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          786,
          (_DWORD)p_IrpFlags,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          18,
          32,
          (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
          173,
          v13);
      }
      goto LABEL_47;
    }
LABEL_25:
    v14 = *((_QWORD *)p_IrpFlags + 8) == 0;
    LODWORD(v33) = p_IrpFlags[6];
    if ( v14 )
    {
      p_IrpFlags = (_DWORD *)*((_QWORD *)p_IrpFlags + 7);
      if ( (CallbackData->Flags & 8) == 0 )
      {
        RequestorMode = CallbackData->RequestorMode;
LABEL_35:
        v18 = PrjfEnumerateDirectoryWithMerge(
                (__int64)CallbackData,
                *(struct _FLT_INSTANCE **)(a2 + 24),
                *(struct _FILE_OBJECT **)(a2 + 32),
                v13,
                (__int64)CallbackData->Iopb->Parameters.QueryEa.EaList,
                CallbackData->Iopb->Parameters.Create.EaLength,
                CallbackData->Iopb->OperationFlags,
                RequestorMode,
                (unsigned int)v33,
                (__int64)p_IrpFlags,
                &v32);
        v15 = v18;
        if ( (int)(v18 + 0x80000000) < 0 || v18 == -2147483643 )
        {
          v21 = v32;
          if ( !v32 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgsKM(0x80000000LL, p_IrpFlags);
            v21 = v32;
          }
          CallbackData->IoStatus.Information = v21;
        }
        LOBYTE(p_IrpFlags) = BYTE10(xmmword_14001A3E0) & 4;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
          v3 = 0;
        if ( (_BYTE)p_IrpFlags || v3 )
        {
          LOBYTE(v19) = v3;
          WPP_RECORDER_AND_TRACE_SF_sDqZd(
            *((_QWORD *)Context + 9),
            (_DWORD)p_IrpFlags,
            v19,
            v20,
            BugCheckOnFailure,
            Priority,
            v25,
            v26,
            v27,
            v28,
            *(_QWORD *)(a2 + 32),
            *((_QWORD *)Context + 9),
            v15);
        }
        goto LABEL_46;
      }
    }
    else
    {
      v15 = FltLockUserBuffer(CallbackData);
      if ( v15 < 0 )
      {
LABEL_46:
        CallbackData->IoStatus.Status = v15;
        v6 = 4;
LABEL_47:
        if ( Context )
          FltReleaseContext(Context);
        goto LABEL_49;
      }
      AllocationSize = CallbackData->Iopb->Parameters.Create.AllocationSize;
      if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
        p_IrpFlags = *(_DWORD **)(AllocationSize.QuadPart + 24);
      else
        p_IrpFlags = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
      if ( !p_IrpFlags )
      {
        v15 = -1073741801;
        goto LABEL_46;
      }
    }
    RequestorMode = 0;
    goto LABEL_35;
  }
LABEL_49:
  if ( v10 )
    FltReleaseContext(v10);
  if ( v30[0] )
    FltReleaseContext(v30[0]);
  if ( UnionContext )
    PrjfReleaseUnionContext(UnionContext, (__int64)p_IrpFlags);
  return v6;
}

```

## disassembly

```asm
0x1400280f0  mov     [rsp-8+arg_8], rbx
0x1400280f5  push    rbp
0x1400280f6  push    rsi
0x1400280f7  push    rdi
0x1400280f8  push    r12
0x1400280fa  push    r13
0x1400280fc  push    r14
0x1400280fe  push    r15
0x140028100  lea     rbp, [rsp-27h]
0x140028105  sub     rsp, 0A0h
0x14002810c  mov     rax, [rcx+10h]
0x140028110  xor     r14d, r14d
0x140028113  mov     esi, 1
0x140028118  mov     [rbp+57h+Context], r14
0x14002811c  mov     [rbp+57h+arg_0], r14d
0x140028120  mov     r15, rdx
0x140028123  mov     rbx, rcx
0x140028126  mov     [rbp+57h+var_50], r14
0x14002812a  mov     edi, esi
0x14002812c  mov     [rbp+57h+arg_18], r14
0x140028130  cmp     [rax+5], sil
0x140028134  jnz     loc_140028440
0x14002813a  test    byte ptr [rax+6], 8
0x14002813e  jnz     loc_140028440
0x140028144  mov     rdx, [rdx+20h]; FileObject
0x140028148  lea     rax, [rbp+57h+Context]
0x14002814c  mov     rcx, [r15+18h]; Instance
0x140028150  lea     r9, [rbp+57h+arg_18]
0x140028154  lea     r8, [rbp+57h+var_50]
0x140028158  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax; Context
0x14002815d  mov     r12d, r14d
0x140028160  call    PrjfGetContextFileObjectEx
0x140028165  mov     r13, [rbp+57h+arg_18]
0x140028169  test    al, al
0x14002816b  jz      loc_1400283F2
0x140028171  cmp     [r13+0], esi
0x140028175  jnz     loc_1400283F2
0x14002817b  cmp     [rbp+57h+Context], r14
0x14002817f  jz      loc_140028407
0x140028185  mov     rax, [rbp+57h+var_50]
0x140028189  lea     rdx, [rbp+57h+var_40]
0x14002818d  mov     rcx, [r15+18h]
0x140028191  movups  xmm0, xmmword ptr [rax+60h]
0x140028195  movdqu  [rbp+57h+var_40], xmm0
0x14002819a  call    PrjfGetUnionContext
0x14002819f  mov     r12, rax
0x1400281a2  test    rax, rax
0x1400281a5  jz      loc_1400283F2
0x1400281ab  mov     rdx, [rbx+10h]
0x1400281af  mov     r14d, [rdx+28h]
0x1400281b3  cmp     r14d, 26h ; '&'
0x1400281b7  jg      short loc_1400281F1
0x1400281b9  jz      loc_140028298
0x1400281bf  mov     ecx, r14d
0x1400281c2  sub     ecx, esi
0x1400281c4  jz      loc_140028298
0x1400281ca  sub     ecx, esi
0x1400281cc  jz      loc_140028298
0x1400281d2  sub     ecx, esi
0x1400281d4  jz      loc_140028298
0x1400281da  sub     ecx, 9
0x1400281dd  jz      loc_140028298
0x1400281e3  sub     ecx, 15h
0x1400281e6  jz      loc_140028298
0x1400281ec  cmp     ecx, 4
0x1400281ef  jmp     short loc_14002821D
0x1400281f1  mov     ecx, r14d
0x1400281f4  sub     ecx, 3Ch ; '<'
0x1400281f7  jz      loc_140028298
0x1400281fd  sub     ecx, 3
0x140028200  jz      loc_140028298
0x140028206  sub     ecx, 0Fh
0x140028209  jz      loc_140028298
0x14002820f  sub     ecx, esi
0x140028211  jz      loc_140028298
0x140028217  sub     ecx, esi
0x140028219  jz      short loc_140028298
0x14002821b  cmp     ecx, esi
0x14002821d  jz      short loc_140028298
0x14002821f  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x140028225  lea     rax, WPP_RECORDER_INITIALIZED
0x14002822c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028233  setnz   r8b
0x140028237  and     dl, 4
0x14002823a  jnz     short loc_140028245
0x14002823c  test    r8b, r8b
0x14002823f  jz      loc_1400283F2
0x140028245  mov     r9, cs:WPP_GLOBAL_Control
0x14002824c  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140028253  mov     dword ptr [rsp+0D0h+var_80], r14d
0x140028258  mov     ecx, 312h
0x14002825d  mov     dword ptr [rsp+0D0h+var_88], 0FADh
0x140028265  mov     [rsp+0D0h+var_90], rax
0x14002826a  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140028271  mov     r9, [r9+40h]
0x140028275  mov     [rsp+0D0h+var_98], rax
0x14002827a  mov     [rsp+0D0h+var_A0], 20h ; ' '
0x140028281  mov     [rsp+0D0h+Priority], 12h
0x140028289  mov     byte ptr [rsp+0D0h+BugCheckOnFailure], 3
0x14002828e  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140028293  jmp     loc_1400283F2
0x140028298  cmp     qword ptr [rdx+40h], 0
0x14002829d  mov     eax, [rdx+18h]
0x1400282a0  mov     dword ptr [rbp+57h+arg_18], eax
0x1400282a3  mov     [rbp+57h+var_60], 4
0x1400282aa  jz      short loc_14002830F
0x1400282ac  mov     rcx, rbx; CallbackData
0x1400282af  call    cs:__imp_FltLockUserBuffer
0x1400282b6  nop     dword ptr [rax+rax+00h]
0x1400282bb  mov     edi, eax
0x1400282bd  test    eax, eax
0x1400282bf  js      loc_1400283EC
0x1400282c5  mov     rax, [rbx+10h]
0x1400282c9  mov     rcx, [rax+40h]; MemoryDescriptorList
0x1400282cd  test    byte ptr [rcx+0Ah], 5
0x1400282d1  jz      short loc_1400282D9
0x1400282d3  mov     rdx, [rcx+18h]
0x1400282d7  jmp     short loc_140028300
0x1400282d9  mov     [rsp+0D0h+Priority], 40000010h; Priority
0x1400282e1  xor     r9d, r9d; RequestedAddress
0x1400282e4  mov     r8d, esi; CacheType
0x1400282e7  mov     [rsp+0D0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400282ef  xor     edx, edx; AccessMode
0x1400282f1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400282f8  nop     dword ptr [rax+rax+00h]
0x1400282fd  mov     rdx, rax
0x140028300  test    rdx, rdx
0x140028303  jnz     short loc_140028319
0x140028305  mov     edi, 0C0000017h
0x14002830a  jmp     loc_1400283EC
0x14002830f  mov     eax, [rbx]
0x140028311  mov     rdx, [rdx+38h]
0x140028315  test    al, 8
0x140028317  jz      short loc_14002831D
0x140028319  xor     al, al
0x14002831b  jmp     short loc_140028320
0x14002831d  mov     al, [rbx+50h]
0x140028320  mov     rcx, [rbx+10h]
0x140028324  lea     r8, [rbp+57h+arg_0]
0x140028328  mov     [rsp+0D0h+var_80], r8
0x14002832d  mov     r9d, r14d
0x140028330  mov     r8, [r15+20h]
0x140028334  mov     [rsp+0D0h+var_88], rdx
0x140028339  mov     edx, dword ptr [rbp+57h+arg_18]
0x14002833c  mov     dword ptr [rsp+0D0h+var_90], edx
0x140028340  mov     rdx, [r15+18h]
0x140028344  mov     byte ptr [rsp+0D0h+var_98], al
0x140028348  mov     al, [rcx+6]
0x14002834b  mov     byte ptr [rsp+0D0h+var_A0], al
0x14002834f  mov     eax, [rcx+30h]
0x140028352  mov     [rsp+0D0h+Priority], eax
0x140028356  mov     rax, [rcx+20h]
0x14002835a  mov     rcx, rbx
0x14002835d  mov     qword ptr [rsp+0D0h+BugCheckOnFailure], rax
0x140028362  call    PrjfEnumerateDirectoryWithMerge
0x140028367  mov     ecx, 80000000h
0x14002836c  mov     edi, eax
0x14002836e  add     eax, ecx
0x140028370  test    ecx, eax
0x140028372  jnz     short loc_14002837C
0x140028374  cmp     edi, 80000005h
0x14002837a  jnz     short loc_140028394
0x14002837c  mov     eax, [rbp+57h+arg_0]
0x14002837f  xor     r14d, r14d
0x140028382  test    eax, eax
0x140028384  jnz     short loc_14002838E
0x140028386  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002838b  mov     eax, [rbp+57h+arg_0]
0x14002838e  mov     [rbx+20h], rax
0x140028392  jmp     short loc_140028397
0x140028394  xor     r14d, r14d
0x140028397  mov     dl, byte ptr cs:xmmword_14001A3E0+0Ah
0x14002839d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400283a4  and     dl, 4
0x1400283a7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400283ae  jz      short loc_1400283BE
0x1400283b0  mov     rax, cs:WPP_GLOBAL_Control
0x1400283b7  cmp     [rax+48h], r14w
0x1400283bc  jnz     short loc_1400283C1
0x1400283be  mov     sil, r14b
0x1400283c1  test    dl, dl
0x1400283c3  jnz     short loc_1400283CA
0x1400283c5  test    sil, sil
0x1400283c8  jz      short loc_1400283EC
0x1400283ca  mov     rax, [rbp+57h+Context]
0x1400283ce  mov     r8b, sil
0x1400283d1  mov     [rsp+0D0h+var_70], edi
0x1400283d5  mov     rcx, [rax+48h]
0x1400283d9  mov     rax, [r15+20h]
0x1400283dd  mov     [rsp+0D0h+var_78], rcx
0x1400283e2  mov     [rsp+0D0h+var_80], rax
0x1400283e7  call    WPP_RECORDER_AND_TRACE_SF_sDqZd
0x1400283ec  mov     [rbx+18h], edi
0x1400283ef  mov     edi, [rbp+57h+var_60]
0x1400283f2  mov     rcx, [rbp+57h+Context]; Context
0x1400283f6  test    rcx, rcx
0x1400283f9  jz      short loc_140028407
0x1400283fb  call    cs:__imp_FltReleaseContext
0x140028402  nop     dword ptr [rax+rax+00h]
0x140028407  test    r13, r13
0x14002840a  jz      short loc_14002841B
0x14002840c  mov     rcx, r13; Context
0x14002840f  call    cs:__imp_FltReleaseContext
0x140028416  nop     dword ptr [rax+rax+00h]
0x14002841b  mov     rax, [rbp+57h+var_50]
0x14002841f  test    rax, rax
0x140028422  jz      short loc_140028433
0x140028424  mov     rcx, rax; Context
0x140028427  call    cs:__imp_FltReleaseContext
0x14002842e  nop     dword ptr [rax+rax+00h]
0x140028433  test    r12, r12
0x140028436  jz      short loc_140028440
0x140028438  mov     rcx, r12; P
0x14002843b  call    PrjfReleaseUnionContext
0x140028440  mov     rbx, [rsp+0D0h+arg_8]
0x140028448  mov     eax, edi
0x14002844a  add     rsp, 0A0h
0x140028451  pop     r15
0x140028453  pop     r14
0x140028455  pop     r13
0x140028457  pop     r12
0x140028459  pop     rdi
0x14002845a  pop     rsi
0x14002845b  pop     rbp
0x14002845c  retn
```
