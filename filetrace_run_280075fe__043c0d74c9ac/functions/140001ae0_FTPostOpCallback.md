# FTPostOpCallback

- ea: `0x140001ae0`
- end: `0x1400020ff`
- name: `FTPostOpCallback`
- size: `1567`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001ae0`
- `0x14000292c`
- `0x140002d68`
- `0x1400031f0`
- `0x140003510`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140001e8e`
- `ntoskrnl!IoWMIWriteEvent` at `0x140001e8e`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140001c82`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140001c82`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001f5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000207c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002092`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400020cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003ebc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001f5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000207c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002092`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400020cd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003ebc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002011`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000202b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002045`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002064`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400020b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002011`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000202b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002045`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002064`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400020b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ea3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001ec6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001ec6`
- `FLTMGR!FltGetRequestorProcessId` at `0x140001c58`
- `FLTMGR!FltGetRequestorProcessId` at `0x140001c58`
- `FLTMGR!FltReleaseContext` at `0x140001ff7`
- `FLTMGR!FltReleaseContext` at `0x140001ff7`
- `FLTMGR!FltGetRequestorProcess` at `0x140001c6e`
- `FLTMGR!FltGetRequestorProcess` at `0x140001c6e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140001f25`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140001f25`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001f01`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001f01`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140001ea5`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140001ea5`

## pseudocode

```c
__int64 __fastcall FTPostOpCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  __int64 v8; // rax
  int v9; // esi
  __int64 v10; // r8
  char *v11; // r10
  int v12; // edx
  int v13; // r10d
  PVOID v14; // r12
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r14
  _QWORD *Context; // rax
  void *v17; // r15
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  _BYTE *v21; // rax
  int v23; // [rsp+30h] [rbp-2E8h] BYREF
  PVOID P; // [rsp+38h] [rbp-2E0h] BYREF
  int v25; // [rsp+40h] [rbp-2D8h] BYREF
  int i; // [rsp+44h] [rbp-2D4h]
  int v27[2]; // [rsp+50h] [rbp-2C8h] BYREF
  __int64 v28; // [rsp+58h] [rbp-2C0h]
  __int16 v29; // [rsp+60h] [rbp-2B8h]
  bool v30; // [rsp+62h] [rbp-2B6h]
  int v31; // [rsp+63h] [rbp-2B5h]
  char v32; // [rsp+67h] [rbp-2B1h]
  __int64 v33; // [rsp+68h] [rbp-2B0h]
  __int128 v34; // [rsp+70h] [rbp-2A8h]
  __int64 v35; // [rsp+80h] [rbp-298h]
  LONGLONG TimeQuadPart; // [rsp+88h] [rbp-290h]
  char v37; // [rsp+90h] [rbp-288h]
  int v38; // [rsp+91h] [rbp-287h]
  __int16 v39; // [rsp+95h] [rbp-283h]
  char v40; // [rsp+97h] [rbp-281h]
  __int64 v41; // [rsp+98h] [rbp-280h]
  int v42; // [rsp+A0h] [rbp-278h]
  int v43; // [rsp+A4h] [rbp-274h]
  __int64 v44; // [rsp+A8h] [rbp-270h]
  __int64 v45; // [rsp+B0h] [rbp-268h]
  __int64 v46; // [rsp+B8h] [rbp-260h]
  __int64 v47; // [rsp+C0h] [rbp-258h]
  __int64 v48; // [rsp+C8h] [rbp-250h]
  __int64 v49; // [rsp+D0h] [rbp-248h]
  __int64 v50; // [rsp+D8h] [rbp-240h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-238h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-230h]
  __int64 v53; // [rsp+F0h] [rbp-228h]
  __int64 v54; // [rsp+100h] [rbp-218h]
  int WnodeEventItem; // [rsp+110h] [rbp-208h] BYREF
  __int128 v56; // [rsp+114h] [rbp-204h]
  _BYTE v57[44]; // [rsp+124h] [rbp-1F4h] BYREF
  _BYTE v58[384]; // [rsp+150h] [rbp-1C8h] BYREF

  v54 = a3;
  P = 0;
  v25 = 0;
  v23 = 0;
  WnodeEventItem = 0;
  v56 = 0;
  memset(v57, 0, sizeof(v57));
  *(_QWORD *)v27 = 0;
  v28 = 0;
  v29 = 2;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  TimeQuadPart = 0;
  v37 = 2;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = -1;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  if ( (a4 & 1) == 0 )
  {
    P = v58;
    v27[0] = CallbackData->IoStatus.Status;
    Iopb = CallbackData->Iopb;
    LOWORD(v27[1]) = *(_WORD *)&Iopb->MajorFunction;
    *((_QWORD *)&v34 + 1) = *(_QWORD *)(a2 + 32);
    HIBYTE(v29) = (Iopb->IrpFlags & 2) != 0;
    v30 = (CallbackData->Flags & 2) != 0;
    LODWORD(v35) = FltGetRequestorProcessId(CallbackData);
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    if ( RequestorProcess )
      TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    else
      TimeQuadPart = 0;
    v8 = *(_QWORD *)(a3 + 80);
    if ( v8 )
      v28 = v8 + 8;
    else
      v28 = a3;
    LOBYTE(v29) = *(_BYTE *)(a3 + 72);
    *(_QWORD *)&v34 = *(_QWORD *)(a3 + 192);
    v33 = *(_QWORD *)(a3 + 64);
    LOWORD(WnodeEventItem) = 64;
    *(_DWORD *)&v57[24] = 1179648;
    LOWORD(v56) = CallbackData->Iopb->MajorFunction;
    *(_OWORD *)&v57[4] = FT_MessageGuid;
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      if ( v9 >= *(_DWORD *)(a3 + 200) )
        goto LABEL_37;
      v10 = *(int *)(a3 + 8LL * v9 + 208);
      v11 = (char *)LogSessions + 40 * v10;
      *(_QWORD *)((char *)&v56 + 4) = *(_QWORD *)v11;
      if ( *((_DWORD *)v11 + 3) == *(_DWORD *)(a3 + 8LL * v9 + 204) )
        break;
LABEL_36:
      ++v9;
    }
    v12 = 1 << v10;
    if ( ((1 << v10) & *(_DWORD *)(a3 + 96)) != 0 )
      v41 = *(_QWORD *)(a3 + 88);
    if ( (v12 & *(_DWORD *)(a3 + 108)) != 0 )
      v42 = *(_DWORD *)(a3 + 104);
    if ( (v12 & *(_DWORD *)(a3 + 120)) != 0 )
      v47 = *(_QWORD *)(a3 + 112);
    if ( (v12 & *(_DWORD *)(a3 + 152)) != 0 )
    {
      v44 = *(_QWORD *)(a3 + 128);
      LODWORD(v45) = *(_DWORD *)(a3 + 136);
      v46 = *(_QWORD *)(a3 + 144);
    }
    if ( (v12 & *(_DWORD *)(a3 + 172)) != 0 )
    {
      v49 = *(_QWORD *)(a3 + 160);
      LODWORD(v48) = *(_DWORD *)(a3 + 168);
    }
    if ( (v12 & *(_DWORD *)(a3 + 188)) != 0 )
    {
      v53 = *(_QWORD *)(a3 + 176);
      LODWORD(v52) = *(_DWORD *)(a3 + 184);
    }
    LODWORD(v50) = 0;
    v51 = 0;
    SetCallResult(CallbackData, *((unsigned int *)v11 + 7), &v50, &v51);
    if ( !(unsigned __int8)FormatFileTraceEvent(v13, (int)v27, (int)&v23, (int)&v25, (size_t)&P) )
      goto LABEL_37;
    v14 = P;
    *(_QWORD *)&v57[28] = P;
    *(_DWORD *)&v57[36] = v25;
    if ( IoWMIWriteEvent(&WnodeEventItem) == -1073741816 )
    {
      GenericWorkItem = FltAllocateGenericWorkItem();
      if ( GenericWorkItem )
      {
        Context = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x72744C46u);
        v17 = Context;
        if ( Context )
        {
          *Context = *(_QWORD *)((char *)&v56 + 4);
          if ( FltQueueGenericWorkItem(
                 GenericWorkItem,
                 WmiRegistrationContext.SecurityDescriptor,
                 DisableSession,
                 DelayedWorkQueue,
                 Context) >= 0 )
            goto LABEL_30;
          ExFreePoolWithTag(v17, 0x72744C46u);
        }
        FltFreeGenericWorkItem(GenericWorkItem);
      }
    }
LABEL_30:
    if ( v23 == 1 )
    {
      ExFreeToNPagedLookasideList(&Lookaside, v14);
    }
    else
    {
      if ( v23 != 2 )
      {
LABEL_35:
        P = v58;
        v42 = -1;
        v41 = 0;
        v44 = 0;
        v46 = 0;
        v49 = 0;
        LODWORD(v48) = 0;
        v51 = 0;
        LODWORD(v50) = 0;
        v53 = 0;
        LODWORD(v52) = 0;
        v37 = 2;
        v47 = 0;
        goto LABEL_36;
      }
      ExFreePoolWithTag(v14, 0x72744C46u);
    }
    v23 = 0;
    goto LABEL_35;
  }
LABEL_37:
  FltReleaseContext(*(PFLT_CONTEXT *)(a3 + 192));
  v18 = *(void **)(a3 + 160);
  if ( v18 )
    ExFreePoolWithTag(v18, 0x72744C46u);
  v19 = *(void **)(a3 + 144);
  if ( v19 )
    ExFreePoolWithTag(v19, 0x72744C46u);
  v20 = *(void **)(a3 + 176);
  if ( v20 )
    ExFreePoolWithTag(v20, 0x72744C46u);
  v21 = *(_BYTE **)(a3 + 80);
  if ( v21 )
  {
    if ( *v21 == 1 )
      ExFreePoolWithTag(*(PVOID *)(a3 + 80), 0x72744C46u);
    else
      ExFreeToNPagedLookasideList(&Lookaside, *(PVOID *)(a3 + 80));
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WmiRegistrationContext.Reserved, (PVOID)a3);
  if ( v23 == 1 )
  {
    ExFreeToNPagedLookasideList(&Lookaside, P);
  }
  else if ( v23 == 2 )
  {
    ExFreePoolWithTag(P, 0x72744C46u);
  }
  return 0;
}

```

## disassembly

```asm
0x140001ae0  mov     r11, rsp
0x140001ae3  push    rbx
0x140001ae4  push    rsi
0x140001ae5  push    rdi
0x140001ae6  push    r12
0x140001ae8  push    r13
0x140001aea  push    r14
0x140001aec  push    r15
0x140001aee  sub     rsp, 2E0h
0x140001af5  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x140001afc  xor     rax, rsp
0x140001aff  mov     [rsp+318h+var_48], rax
0x140001b07  mov     rbx, r8
0x140001b0a  mov     r13, rcx
0x140001b0d  mov     [rsp+318h+var_218], rbx
0x140001b15  xor     r15d, r15d
0x140001b18  mov     [rsp+318h+P], r15
0x140001b1d  mov     [rsp+318h+var_2D8], r15d
0x140001b22  mov     [rsp+318h+var_2E8], r15d
0x140001b27  mov     [r11-208h], r15d
0x140001b2e  xorps   xmm0, xmm0
0x140001b31  xor     eax, eax
0x140001b33  movups  [rsp+318h+var_204], xmm0
0x140001b3b  movups  [rsp+318h+var_1F4], xmm0
0x140001b43  movups  [rsp+318h+var_1E4], xmm0
0x140001b4b  movups  [rsp+318h+var_1E4+0Ch], xmm0
0x140001b53  mov     qword ptr [rsp+318h+var_2C8], r15
0x140001b58  mov     [rsp+318h+var_2C0], r15
0x140001b5d  mov     [rsp+318h+var_2B8], 2
0x140001b64  mov     [rsp+318h+var_2B6], r15b
0x140001b69  mov     [rsp+318h+var_2B5], eax
0x140001b6d  mov     [rsp+318h+var_2B1], al
0x140001b71  mov     [rsp+318h+var_2B0], r15
0x140001b76  movdqa  [rsp+318h+var_2A8], xmm0
0x140001b7c  mov     [r11-298h], r15
0x140001b83  mov     [r11-290h], r15
0x140001b8a  mov     [rsp+318h+var_288], 2
0x140001b92  mov     [rsp+318h+var_287], eax
0x140001b99  mov     [rsp+318h+var_283], ax
0x140001ba1  mov     [rsp+318h+var_281], al
0x140001ba8  mov     [r11-280h], r15
0x140001baf  mov     [rsp+318h+var_278], 0FFFFFFFFh
0x140001bba  mov     [rsp+318h+var_274], eax
0x140001bc1  mov     [r11-270h], r15
0x140001bc8  mov     [r11-268h], r15
0x140001bcf  mov     [r11-260h], r15
0x140001bd6  mov     [r11-258h], r15
0x140001bdd  mov     [r11-250h], r15
0x140001be4  mov     [r11-248h], r15
0x140001beb  mov     [r11-240h], r15
0x140001bf2  mov     [r11-238h], r15
0x140001bf9  mov     [r11-230h], r15
0x140001c00  mov     [r11-228h], r15
0x140001c07  test    r9b, 1
0x140001c0b  jnz     loc_140001FEB
0x140001c11  lea     rax, [r11-1C8h]
0x140001c18  mov     [rsp+318h+P], rax
0x140001c1d  mov     eax, [rcx+18h]
0x140001c20  mov     [rsp+318h+var_2C8], eax
0x140001c24  mov     rcx, [rcx+10h]
0x140001c28  mov     al, [rcx+4]
0x140001c2b  mov     byte ptr [rsp+318h+var_2C8+4], al
0x140001c2f  mov     al, [rcx+5]
0x140001c32  mov     byte ptr [rsp+318h+var_2C8+5], al
0x140001c36  mov     rax, [rdx+20h]
0x140001c3a  mov     qword ptr [rsp+318h+var_2A8+8], rax
0x140001c3f  mov     eax, [rcx]
0x140001c41  shr     eax, 1
0x140001c43  and     al, 1
0x140001c45  mov     byte ptr [rsp+318h+var_2B8+1], al
0x140001c49  mov     eax, [r13+0]
0x140001c4d  shr     eax, 1
0x140001c4f  and     al, 1
0x140001c51  mov     [rsp+318h+var_2B6], al
0x140001c55  mov     rcx, r13; CallbackData
0x140001c58  call    cs:__imp_FltGetRequestorProcessId
0x140001c5f  nop     dword ptr [rax+rax+00h]
0x140001c64  mov     dword ptr [rsp+318h+var_298], eax
0x140001c6b  mov     rcx, r13; CallbackData
0x140001c6e  call    cs:__imp_FltGetRequestorProcess
0x140001c75  nop     dword ptr [rax+rax+00h]
0x140001c7a  test    rax, rax
0x140001c7d  jz      short loc_140001C98
0x140001c7f  mov     rcx, rax; Process
0x140001c82  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140001c89  nop     dword ptr [rax+rax+00h]
0x140001c8e  mov     [rsp+318h+var_290], rax
0x140001c96  jmp     short loc_140001CA0
0x140001c98  mov     [rsp+318h+var_290], r15
0x140001ca0  mov     rax, [rbx+50h]
0x140001ca4  test    rax, rax
0x140001ca7  jz      short loc_140001CB4
0x140001ca9  add     rax, 8
0x140001cad  mov     [rsp+318h+var_2C0], rax
0x140001cb2  jmp     short loc_140001CB9
0x140001cb4  mov     [rsp+318h+var_2C0], rbx
0x140001cb9  mov     al, [rbx+48h]
0x140001cbc  mov     byte ptr [rsp+318h+var_2B8], al
0x140001cc0  mov     rax, [rbx+0C0h]
0x140001cc7  mov     qword ptr [rsp+318h+var_2A8], rax
0x140001ccc  mov     rax, [rbx+40h]
0x140001cd0  mov     [rsp+318h+var_2B0], rax
0x140001cd5  mov     eax, 40h ; '@'
0x140001cda  mov     word ptr [rsp+318h+WnodeEventItem], ax
0x140001ce2  mov     dword ptr [rsp+318h+var_1E4+8], 120000h
0x140001ced  mov     rax, [r13+10h]
0x140001cf1  mov     cl, [rax+4]
0x140001cf4  mov     byte ptr [rsp+318h+var_204], cl
0x140001cfb  mov     byte ptr [rsp+318h+var_204+1], r15b
0x140001d03  movups  xmm0, cs:FT_MessageGuid
0x140001d0a  movdqu  [rsp+318h+var_1F4+4], xmm0
0x140001d13  mov     esi, r15d
0x140001d16  mov     [rsp+318h+var_2D4], r15d
0x140001d1b  mov     edi, 72744C46h
0x140001d20  cmp     esi, [rbx+0C8h]
0x140001d26  jge     loc_140001FF0
0x140001d2c  movsxd  rdx, esi
0x140001d2f  movsxd  r8, dword ptr [rbx+rdx*8+0D0h]
0x140001d37  lea     rcx, [r8+r8*4]
0x140001d3b  mov     rax, cs:LogSessions
0x140001d42  lea     r10, [rax+rcx*8]
0x140001d46  mov     rax, [r10]
0x140001d49  mov     qword ptr [rsp+318h+var_204+4], rax
0x140001d51  mov     eax, [rbx+rdx*8+0CCh]
0x140001d58  cmp     [r10+0Ch], eax
0x140001d5c  jz      short loc_140001D63
0x140001d5e  jmp     loc_140001FE0
0x140001d63  mov     ecx, r8d
0x140001d66  mov     edx, 1
0x140001d6b  shl     edx, cl
0x140001d6d  test    [rbx+60h], edx
0x140001d70  jz      short loc_140001D7E
0x140001d72  mov     rax, [rbx+58h]
0x140001d76  mov     [rsp+318h+var_280], rax
0x140001d7e  test    [rbx+6Ch], edx
0x140001d81  jz      short loc_140001D8D
0x140001d83  mov     eax, [rbx+68h]
0x140001d86  mov     [rsp+318h+var_278], eax
0x140001d8d  test    [rbx+78h], edx
0x140001d90  jz      short loc_140001D9E
0x140001d92  mov     rax, [rbx+70h]
0x140001d96  mov     [rsp+318h+var_258], rax
0x140001d9e  test    [rbx+98h], edx
0x140001da4  jz      short loc_140001DD1
0x140001da6  mov     rax, [rbx+80h]
0x140001dad  mov     [rsp+318h+var_270], rax
0x140001db5  mov     eax, [rbx+88h]
0x140001dbb  mov     dword ptr [rsp+318h+var_268], eax
0x140001dc2  mov     rax, [rbx+90h]
0x140001dc9  mov     [rsp+318h+var_260], rax
0x140001dd1  test    [rbx+0ACh], edx
0x140001dd7  jz      short loc_140001DF5
0x140001dd9  mov     rax, [rbx+0A0h]
0x140001de0  mov     [rsp+318h+var_248], rax
0x140001de8  mov     eax, [rbx+0A8h]
0x140001dee  mov     dword ptr [rsp+318h+var_250], eax
0x140001df5  test    [rbx+0BCh], edx
0x140001dfb  jz      short loc_140001E19
0x140001dfd  mov     rax, [rbx+0B0h]
0x140001e04  mov     [rsp+318h+var_228], rax
0x140001e0c  mov     eax, [rbx+0B8h]
0x140001e12  mov     dword ptr [rsp+318h+var_230], eax
0x140001e19  mov     dword ptr [rsp+318h+var_240], r15d
0x140001e21  mov     [rsp+318h+var_238], r15
0x140001e29  lea     r9, [rsp+318h+var_238]
0x140001e31  lea     r8, [rsp+318h+var_240]
0x140001e39  mov     edx, [r10+1Ch]
0x140001e3d  mov     rcx, r13
0x140001e40  call    SetCallResult
0x140001e45  lea     r8, [rsp+318h+P]
0x140001e4a  mov     [rsp+318h+Context], r8; Size
0x140001e4f  lea     r9, [rsp+318h+var_2D8]; int
0x140001e54  lea     r8, [rsp+318h+var_2E8]; int
0x140001e59  lea     rdx, [rsp+318h+var_2C8]; int
0x140001e5e  mov     rcx, r10; int
0x140001e61  call    FormatFileTraceEvent
0x140001e66  test    al, al
0x140001e68  jz      loc_140001FF0
0x140001e6e  mov     r12, [rsp+318h+P]
0x140001e73  mov     qword ptr [rsp+318h+var_1E4+0Ch], r12
0x140001e7b  mov     eax, [rsp+318h+var_2D8]
0x140001e7f  mov     [rsp+318h+var_1D0], eax
0x140001e86  lea     rcx, [rsp+318h+WnodeEventItem]; WnodeEventItem
0x140001e8e  call    cs:__imp_IoWMIWriteEvent
0x140001e95  nop     dword ptr [rax+rax+00h]
0x140001e9a  cmp     eax, 0C0000008h
0x140001e9f  jnz     loc_140001F34
0x140001ea5  call    cs:__imp_FltAllocateGenericWorkItem
0x140001eac  nop     dword ptr [rax+rax+00h]
0x140001eb1  mov     r14, rax
0x140001eb4  test    rax, rax
0x140001eb7  jz      short loc_140001F34
0x140001eb9  mov     r8d, edi; Tag
0x140001ebc  mov     edx, 8; NumberOfBytes
0x140001ec1  mov     ecx, 200h; PoolType
0x140001ec6  call    cs:__imp_ExAllocatePoolWithTag
0x140001ecd  nop     dword ptr [rax+rax+00h]
0x140001ed2  mov     r15, rax
0x140001ed5  test    rax, rax
0x140001ed8  jz      short loc_140001F22
0x140001eda  mov     rcx, qword ptr [rsp+318h+var_204+4]
0x140001ee2  mov     [rax], rcx
0x140001ee5  mov     [rsp+318h+Context], rax; Context
0x140001eea  mov     r9d, 1; QueueType
0x140001ef0  lea     r8, DisableSession; WorkerRoutine
0x140001ef7  mov     rdx, cs:WmiRegistrationContext.SecurityDescriptor; FltObject
0x140001efe  mov     rcx, r14; FltWorkItem
0x140001f01  call    cs:__imp_FltQueueGenericWorkItem
0x140001f08  nop     dword ptr [rax+rax+00h]
0x140001f0d  test    eax, eax
0x140001f0f  jns     short loc_140001F31
0x140001f11  mov     edx, edi; Tag
0x140001f13  mov     rcx, r15; P
0x140001f16  call    cs:__imp_ExFreePoolWithTag
0x140001f1d  nop     dword ptr [rax+rax+00h]
0x140001f22  mov     rcx, r14; FltWorkItem
0x140001f25  call    cs:__imp_FltFreeGenericWorkItem
0x140001f2c  nop     dword ptr [rax+rax+00h]
0x140001f31  xor     r15d, r15d
0x140001f34  mov     edx, [rsp+318h+var_2E8]
0x140001f38  sub     edx, 1
0x140001f3b  jz      short loc_140001F55
0x140001f3d  cmp     edx, 1
0x140001f40  jnz     short loc_140001F70
0x140001f42  mov     edx, edi; Tag
0x140001f44  mov     rcx, r12; P
0x140001f47  call    cs:__imp_ExFreePoolWithTag
0x140001f4e  nop     dword ptr [rax+rax+00h]
0x140001f53  jmp     short loc_140001F6B
0x140001f55  mov     rdx, r12; Entry
0x140001f58  lea     rcx, Lookaside; Lookaside
0x140001f5f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140001f66  nop     dword ptr [rax+rax+00h]
0x140001f6b  mov     [rsp+318h+var_2E8], r15d
0x140001f70  lea     rax, [rsp+318h+var_1C8]
0x140001f78  mov     [rsp+318h+P], rax
0x140001f7d  mov     [rsp+318h+var_278], 0FFFFFFFFh
0x140001f88  mov     [rsp+318h+var_280], r15
0x140001f90  mov     [rsp+318h+var_270], r15
0x140001f98  mov     [rsp+318h+var_260], r15
0x140001fa0  mov     [rsp+318h+var_248], r15
0x140001fa8  mov     dword ptr [rsp+318h+var_250], r15d
0x140001fb0  mov     [rsp+318h+var_238], r15
0x140001fb8  mov     dword ptr [rsp+318h+var_240], r15d
0x140001fc0  mov     [rsp+318h+var_228], r15
0x140001fc8  mov     dword ptr [rsp+318h+var_230], r15d
0x140001fd0  mov     [rsp+318h+var_288], 2
0x140001fd8  mov     [rsp+318h+var_258], r15
0x140001fe0  inc     esi
0x140001fe2  mov     [rsp+318h+var_2D4], esi
0x140001fe6  jmp     loc_140001D20
0x140001feb  mov     edi, 72744C46h
0x140001ff0  mov     rcx, [rbx+0C0h]; Context
0x140001ff7  call    cs:__imp_FltReleaseContext
0x140001ffe  nop     dword ptr [rax+rax+00h]
0x140002003  mov     rcx, [rbx+0A0h]; P
0x14000200a  test    rcx, rcx
0x14000200d  jz      short loc_14000201D
0x14000200f  mov     edx, edi; Tag
0x140002011  call    cs:__imp_ExFreePoolWithTag
0x140002018  nop     dword ptr [rax+rax+00h]
0x14000201d  mov     rcx, [rbx+90h]; P
0x140002024  test    rcx, rcx
0x140002027  jz      short loc_140002037
0x140002029  mov     edx, edi; Tag
0x14000202b  call    cs:__imp_ExFreePoolWithTag
0x140002032  nop     dword ptr [rax+rax+00h]
0x140002037  mov     rcx, [rbx+0B0h]; P
0x14000203e  test    rcx, rcx
0x140002041  jz      short loc_140002051
0x140002043  mov     edx, edi; Tag
0x140002045  call    cs:__imp_ExFreePoolWithTag
0x14000204c  nop     dword ptr [rax+rax+00h]
0x140002051  mov     rax, [rbx+50h]
0x140002055  test    rax, rax
0x140002058  jz      short loc_140002088
0x14000205a  cmp     byte ptr [rax], 1
0x14000205d  jnz     short loc_140002072
0x14000205f  mov     edx, edi; Tag
0x140002061  mov     rcx, rax; P
0x140002064  call    cs:__imp_ExFreePoolWithTag
0x14000206b  nop     dword ptr [rax+rax+00h]
0x140002070  jmp     short loc_140002088
0x140002072  mov     rdx, rax; Entry
0x140002075  lea     rcx, Lookaside; Lookaside
0x14000207c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002083  nop     dword ptr [rax+rax+00h]
0x140002088  mov     rdx, rbx; Entry
0x14000208b  lea     rcx, WmiRegistrationContext.Reserved; Lookaside
0x140002092  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002099  nop     dword ptr [rax+rax+00h]
0x14000209e  mov     edx, [rsp+318h+var_2E8]
0x1400020a2  sub     edx, 1
0x1400020a5  jz      short loc_1400020C1
0x1400020a7  cmp     edx, 1
0x1400020aa  jnz     short loc_1400020D9
0x1400020ac  mov     edx, edi; Tag
0x1400020ae  mov     rcx, [rsp+318h+P]; P
0x1400020b3  call    cs:__imp_ExFreePoolWithTag
0x1400020ba  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
