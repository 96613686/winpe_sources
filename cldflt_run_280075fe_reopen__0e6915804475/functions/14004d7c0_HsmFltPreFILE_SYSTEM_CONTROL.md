# HsmFltPreFILE_SYSTEM_CONTROL

- ea: `0x14004d7c0`
- end: `0x14004debb`
- name: `HsmFltPreFILE_SYSTEM_CONTROL`
- size: `1787`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140001910`
- `0x140001ab4`
- `0x140001d00`
- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x140007d94`
- `0x140007ddc`
- `0x140009364`
- `0x140033ba4`
- `0x1400345b4`
- `0x1400361f4`
- `0x1400467d8`
- `0x140046878`
- `0x140046904`
- `0x140046980`
- `0x14004d7c0`
- `0x14004ded0`
- `0x140062c98`
- `0x14006dd70`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14004d829`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004d829`
- `FLTMGR!FltDeleteContext` at `0x14004dbbb`
- `FLTMGR!FltDeleteContext` at `0x14004dbbb`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d7f0`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d869`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d7f0`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d869`
- `FLTMGR!FltReleaseContext` at `0x14004d88a`
- `FLTMGR!FltReleaseContext` at `0x14004d935`
- `FLTMGR!FltReleaseContext` at `0x14004d88a`
- `FLTMGR!FltReleaseContext` at `0x14004d935`

## pseudocode

```c
__int64 __fastcall HsmFltPreFILE_SYSTEM_CONTROL(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  char v3; // r12
  unsigned int v7; // esi
  __int64 *v8; // rbx
  PEPROCESS RequestorProcess; // rax
  int v10; // r9d
  struct _FILE_OBJECT *v11; // rdx
  struct _FLT_INSTANCE *v12; // r15
  __int64 v13; // rcx
  PEPROCESS v14; // rax
  PFLT_CONTEXT v15; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  DWORD LowPart; // ecx
  void *v18; // r13
  __int64 v19; // rdx
  DWORD v20; // ecx
  unsigned int v21; // eax
  DWORD v23; // ecx
  DWORD v24; // ecx
  NTSTATUS v25; // r12d
  __int64 v26; // rdx
  unsigned __int8 v27; // di
  unsigned __int8 PlaceholderCompatMode; // al
  __int64 v29; // rdx
  DWORD v30; // ecx
  DWORD v31; // ecx
  __int64 v32; // rdx
  PFLT_IO_PARAMETER_BLOCK v33; // rax
  _DWORD *Parameters; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  DWORD v39; // ecx
  DWORD v40; // ecx
  PFLT_CONTEXT Context; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  *a3 = 0;
  v7 = 1;
  v8 = 0;
  if ( CallbackData )
    RequestorProcess = FltGetRequestorProcess(CallbackData);
  else
    RequestorProcess = 0;
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
    goto LABEL_26;
  v11 = *(struct _FILE_OBJECT **)(a2 + 32);
  v12 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  FltGetStreamHandleContext(v12, v11, &Context);
  v8 = (__int64 *)Context;
  if ( Context )
  {
    v13 = *((_QWORD *)Context + 2);
    if ( (*(_DWORD *)(v13 + 28) & 1) != 0 )
    {
      if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v13 + 16) + 16LL) + 32LL) != v12 )
      {
        v15 = Context;
        goto LABEL_10;
      }
      if ( !CallbackData )
        goto LABEL_11;
      v14 = FltGetRequestorProcess(CallbackData);
      if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(v14) )
      {
LABEL_9:
        v15 = Context;
LABEL_10:
        FltReleaseContext(v15);
        v8 = 0;
        Context = 0;
        goto LABEL_11;
      }
      v8 = (__int64 *)Context;
    }
    else if ( Context )
    {
      FltDeleteContext(Context);
      goto LABEL_9;
    }
  }
LABEL_11:
  if ( v8 )
  {
    HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, 1, (_DWORD)v8, v8[2]);
    v18 = (void *)v8[2];
  }
  else
  {
    Iopb = CallbackData->Iopb;
    if ( Iopb->MajorFunction != 13 )
      goto LABEL_26;
    LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart != 590780 && LowPart != 589988 && LowPart != 590860 )
      goto LABEL_26;
    v18 = 0;
    HsmpTracePreCallbackEnter((_DWORD)CallbackData, 1, 0, 0, 0);
  }
  v20 = CallbackData->Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( v20 == 590780 )
  {
    v21 = HsmFltProcessHSMControl(CallbackData, (int)v8);
LABEL_19:
    v7 = v21;
    goto LABEL_20;
  }
  if ( v20 == 589992 )
  {
    v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
    HsmDbgBreakOnStatus((unsigned int)v25);
    if ( v25 < 0 )
      goto LABEL_55;
    v3 = 1;
    v27 = BYTE1(*(_DWORD *)(v8[2] + 28)) & 1;
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode((__int64)CallbackData);
    if ( (unsigned __int8)HsmOsDisguisePlaceholder(PlaceholderCompatMode, v27) )
    {
      HsmDbgBreakOnStatus(3221226101LL);
      CallbackData->IoStatus.Status = -1073741195;
      v7 = 4;
      CallbackData->IoStatus.Information = 0;
    }
    goto LABEL_20;
  }
  if ( v20 > 0x903FC )
  {
    if ( v20 <= 0x94264 )
    {
      if ( v20 != 606820 )
      {
        v39 = v20 - 590860;
        if ( !v39 )
        {
          v21 = HsmFltPreSET_REPARSE_POINT_EX(CallbackData, v19, v8);
          goto LABEL_19;
        }
        v40 = v39 - 60;
        if ( !v40 )
        {
          if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
            goto LABEL_24;
          v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreMANAGE_BYPASS_IO(CallbackData, a2, v8);
            goto LABEL_19;
          }
          goto LABEL_55;
        }
        if ( v40 == 15495 && (*(_DWORD *)(v8[2] + 28) & 2) == 0 )
        {
          v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreQUERY_ALLOCATED_RANGES((__int64)CallbackData, v35, (__int64)v8);
            goto LABEL_19;
          }
          goto LABEL_55;
        }
        goto LABEL_24;
      }
      if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
        goto LABEL_24;
      v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
      HsmDbgBreakOnStatus((unsigned int)v25);
      if ( v25 < 0 )
        goto LABEL_55;
      v3 = 1;
      if ( (*(_DWORD *)(v8[2] + 28) & 0x100) == 0 )
      {
        CallbackData->IoStatus.Status = -1073700189;
        v7 = 4;
        CallbackData->IoStatus.Information = 0;
        goto LABEL_20;
      }
    }
    else
    {
      if ( v20 == 622792 )
      {
        if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
          goto LABEL_24;
        v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
        HsmDbgBreakOnStatus((unsigned int)v25);
        if ( v25 >= 0 )
        {
          v3 = 1;
          v21 = HsmFltPreSET_ZERO_DATA(CallbackData, v36, v8);
          goto LABEL_19;
        }
        goto LABEL_55;
      }
      if ( v20 != 623208 )
      {
        if ( v20 == 639040 && (*(_DWORD *)(v8[2] + 28) & 2) == 0 )
        {
          v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)v25);
          if ( v25 < 0 )
            goto LABEL_55;
          v29 = v8[2];
          v3 = 1;
          if ( (*(_DWORD *)(v29 + 28) & 0x100) == 0 )
          {
            v21 = HsmpRecallInitiateHydration(
                    (_DWORD)v8,
                    v29,
                    CallbackData->Iopb->TargetFileObject,
                    1,
                    (__int64)CallbackData,
                    0,
                    -1);
            goto LABEL_19;
          }
          goto LABEL_20;
        }
        goto LABEL_24;
      }
      if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
        goto LABEL_24;
      v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
      HsmDbgBreakOnStatus((unsigned int)v25);
      if ( v25 < 0 )
        goto LABEL_55;
      v3 = 1;
      if ( (*(_DWORD *)(v8[2] + 28) & 0x100) == 0 )
      {
        CallbackData->IoStatus.Status = -1073700188;
        v7 = 4;
        CallbackData->IoStatus.Information = 0;
        goto LABEL_20;
      }
    }
    v7 = 0;
    goto LABEL_20;
  }
  if ( v20 != 590844 )
  {
    if ( v20 <= 0x900E3 )
    {
      if ( v20 == 590051 )
      {
        v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
        HsmDbgBreakOnStatus((unsigned int)v25);
        if ( v25 >= 0 )
        {
          v3 = 1;
          v21 = HsmFltPreREAD_RAW_ENCRYPTED(CallbackData, v38, v8);
          goto LABEL_19;
        }
      }
      else
      {
        v23 = v20 - 589988;
        if ( !v23 )
        {
          v21 = HsmFltPreSET_REPARSE_POINT(CallbackData, v19, v8);
          goto LABEL_19;
        }
        v24 = v23 - 8;
        if ( v24 )
        {
          if ( v24 != 51 )
            goto LABEL_24;
          v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreWRITE_RAW_ENCRYPTED(CallbackData, v26, v8);
            goto LABEL_19;
          }
        }
        else
        {
          v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
          HsmDbgBreakOnStatus((unsigned int)v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreDELETE_REPARSE_POINT(CallbackData, v37, v8);
            goto LABEL_19;
          }
        }
      }
LABEL_55:
      CallbackData->IoStatus.Status = v25;
      v7 = 4;
      CallbackData->IoStatus.Information = 0;
      goto LABEL_24;
    }
    v30 = v20 - 590063;
    if ( !v30 )
    {
      v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
      HsmDbgBreakOnStatus((unsigned int)v25);
      if ( v25 >= 0 )
      {
        v7 = 0;
LABEL_92:
        *a3 = v18;
        goto LABEL_24;
      }
      goto LABEL_55;
    }
    v31 = v30 - 13;
    if ( v31 )
    {
      if ( v31 != 372 )
        goto LABEL_24;
      v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
      HsmDbgBreakOnStatus((unsigned int)v25);
      if ( v25 >= 0 )
      {
        v3 = 1;
        v21 = HsmFltPreSET_PURGE_FAILURE_MODE(CallbackData, v32, v8);
        goto LABEL_19;
      }
      goto LABEL_55;
    }
    if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
      goto LABEL_24;
    v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
    HsmDbgBreakOnStatus((unsigned int)v25);
    if ( v25 < 0 )
      goto LABEL_55;
    v33 = CallbackData->Iopb;
    v3 = 1;
    Parameters = v33->Parameters.CreatePipe.Parameters;
    if ( Parameters
      && v33->Parameters.Create.Options >= 0x18
      && Parameters[4] == 0x4000
      && (*(_DWORD *)(v8[2] + 28) & 0x100) == 0 )
    {
      CallbackData->IoStatus.Status = -1073688822;
      v7 = 4;
      CallbackData->IoStatus.Information = 0;
    }
LABEL_20:
    if ( v7 )
    {
      if ( v7 != 2 && v3 )
        HsmpReleaseUserRequestRundownProtection(v18);
      goto LABEL_24;
    }
    goto LABEL_92;
  }
  CallbackData->IoStatus.Status = 0;
  v7 = 4;
  CallbackData->IoStatus.Information = 0;
LABEL_24:
  if ( v8 )
    FltReleaseContext(v8);
LABEL_26:
  LOBYTE(v10) = v8 == 0;
  HsmpTracePreCallbackExit(v7, (_DWORD)CallbackData, *a3, v10, v8 != 0);
  return v7;
}

```

## disassembly

```asm
0x14004d7c0  mov     [rsp+arg_18], rbx
0x14004d7c5  push    rbp
0x14004d7c6  push    rsi
0x14004d7c7  push    rdi
0x14004d7c8  push    r12
0x14004d7ca  push    r14
0x14004d7cc  sub     rsp, 40h
0x14004d7d0  xor     r12d, r12d
0x14004d7d3  mov     r14, r8
0x14004d7d6  mov     [r8], r12
0x14004d7d9  mov     rdi, rdx
0x14004d7dc  mov     rbp, rcx
0x14004d7df  mov     esi, 1
0x14004d7e4  mov     ebx, r12d
0x14004d7e7  test    rcx, rcx
0x14004d7ea  jz      loc_14004DB6E
0x14004d7f0  call    cs:__imp_FltGetRequestorProcess
0x14004d7f7  nop     dword ptr [rax+rax+00h]
0x14004d7fc  mov     rcx, rax
0x14004d7ff  call    HsmOsIsPassThroughModeEnabled
0x14004d804  test    al, al
0x14004d806  jnz     loc_14004D94E
0x14004d80c  mov     rdx, [rdi+20h]; FileObject
0x14004d810  lea     r8, [rsp+68h+Context]; Context
0x14004d815  mov     [rsp+68h+arg_10], r15
0x14004d81d  mov     r15, [rdi+18h]
0x14004d821  mov     rcx, r15; Instance
0x14004d824  mov     [rsp+68h+Context], r12
0x14004d829  call    cs:__imp_FltGetStreamHandleContext
0x14004d830  nop     dword ptr [rax+rax+00h]
0x14004d835  mov     rbx, [rsp+68h+Context]
0x14004d83a  test    rbx, rbx
0x14004d83d  jz      short loc_14004D89E
0x14004d83f  mov     rcx, [rbx+10h]
0x14004d843  mov     eax, [rcx+1Ch]
0x14004d846  test    sil, al
0x14004d849  jz      loc_14004DBAF
0x14004d84f  mov     rax, [rcx+10h]
0x14004d853  mov     rcx, [rax+10h]
0x14004d857  cmp     [rcx+20h], r15
0x14004d85b  jnz     loc_14004DDCC
0x14004d861  test    rbp, rbp
0x14004d864  jz      short loc_14004D89E
0x14004d866  mov     rcx, rbp; CallbackData
0x14004d869  call    cs:__imp_FltGetRequestorProcess
0x14004d870  nop     dword ptr [rax+rax+00h]
0x14004d875  mov     rcx, rax
0x14004d878  call    HsmOsIsPassThroughModeEnabled
0x14004d87d  test    al, al
0x14004d87f  jz      loc_14004DDD4
0x14004d885  mov     rcx, [rsp+68h+Context]; Context
0x14004d88a  call    cs:__imp_FltReleaseContext
0x14004d891  nop     dword ptr [rax+rax+00h]
0x14004d896  mov     rbx, r12
0x14004d899  mov     [rsp+68h+Context], rbx
0x14004d89e  mov     [rsp+68h+arg_8], r13
0x14004d8a3  test    rbx, rbx
0x14004d8a6  jnz     loc_14004DB8C
0x14004d8ac  mov     rax, [rbp+10h]
0x14004d8b0  cmp     byte ptr [rax+4], 0Dh
0x14004d8b4  jnz     loc_14004D941
0x14004d8ba  mov     ecx, [rax+28h]
0x14004d8bd  cmp     ecx, 903BCh
0x14004d8c3  jz      short loc_14004D8D5
0x14004d8c5  cmp     ecx, 900A4h
0x14004d8cb  jz      short loc_14004D8D5
0x14004d8cd  cmp     ecx, 9040Ch
0x14004d8d3  jnz     short loc_14004D941
0x14004d8d5  mov     r9, rbx
0x14004d8d8  mov     [rsp+68h+var_48], r12
0x14004d8dd  xor     r8d, r8d
0x14004d8e0  movzx   edx, sil
0x14004d8e4  mov     rcx, rbp
0x14004d8e7  mov     r13, r12
0x14004d8ea  call    HsmpTracePreCallbackEnter
0x14004d8ef  mov     rax, [rbp+10h]
0x14004d8f3  mov     ecx, [rax+28h]
0x14004d8f6  cmp     ecx, 903BCh
0x14004d8fc  jnz     loc_14004D983
0x14004d902  lea     r8, [rbp+20h]
0x14004d906  mov     rdx, rbx; int
0x14004d909  mov     rcx, rbp; CallbackData
0x14004d90c  call    HsmFltProcessHSMControl
0x14004d911  mov     esi, eax
0x14004d913  test    esi, esi
0x14004d915  jz      loc_14004DE62
0x14004d91b  cmp     esi, 2
0x14004d91e  jz      short loc_14004D92D
0x14004d920  test    r12b, r12b
0x14004d923  jz      short loc_14004D92D
0x14004d925  mov     rcx, r13; Context
0x14004d928  call    HsmpReleaseUserRequestRundownProtection
0x14004d92d  test    rbx, rbx
0x14004d930  jz      short loc_14004D941
0x14004d932  mov     rcx, rbx; Context
0x14004d935  call    cs:__imp_FltReleaseContext
0x14004d93c  nop     dword ptr [rax+rax+00h]
0x14004d941  mov     r13, [rsp+68h+arg_8]
0x14004d946  mov     r15, [rsp+68h+arg_10]
0x14004d94e  mov     r8, [r14]
0x14004d951  test    rbx, rbx
0x14004d954  mov     rdx, rbp
0x14004d957  mov     ecx, esi
0x14004d959  setnz   al
0x14004d95c  test    rbx, rbx
0x14004d95f  mov     byte ptr [rsp+68h+var_48], al
0x14004d963  setz    r9b
0x14004d967  call    HsmpTracePreCallbackExit
0x14004d96c  mov     rbx, [rsp+68h+arg_18]
0x14004d974  mov     eax, esi
0x14004d976  add     rsp, 40h
0x14004d97a  pop     r14
0x14004d97c  pop     r12
0x14004d97e  pop     rdi
0x14004d97f  pop     rsi
0x14004d980  pop     rbp
0x14004d981  retn
0x14004d983  cmp     ecx, 900A8h
0x14004d989  jz      short loc_14004D9FF
0x14004d98b  cmp     ecx, 903FCh
0x14004d991  ja      loc_14004DA6D
0x14004d997  jz      loc_14004DE6A
0x14004d99d  cmp     ecx, 900E3h
0x14004d9a3  ja      loc_14004DB1F
0x14004d9a9  jz      loc_14004DE10
0x14004d9af  sub     ecx, 900A4h
0x14004d9b5  jz      loc_14004DB0F
0x14004d9bb  sub     ecx, 8
0x14004d9be  jz      loc_14004DDDE
0x14004d9c4  cmp     ecx, 33h ; '3'
0x14004d9c7  jnz     loc_14004D92D
0x14004d9cd  mov     rdx, rbp; CallbackData
0x14004d9d0  mov     rcx, r13; Context
0x14004d9d3  call    HsmpAcquireUserRequestRundownProtection
0x14004d9d8  mov     ecx, eax
0x14004d9da  mov     r12d, eax
0x14004d9dd  call    HsmDbgBreakOnStatus
0x14004d9e2  test    r12d, r12d
0x14004d9e5  js      loc_14004DB76
0x14004d9eb  mov     r8, rbx
0x14004d9ee  mov     rcx, rbp
0x14004d9f1  movzx   r12d, sil
0x14004d9f5  call    HsmFltPreWRITE_RAW_ENCRYPTED
0x14004d9fa  jmp     loc_14004D911
0x14004d9ff  mov     rdx, rbp; CallbackData
0x14004da02  mov     rcx, r13; Context
0x14004da05  call    HsmpAcquireUserRequestRundownProtection
0x14004da0a  mov     ecx, eax
0x14004da0c  mov     r12d, eax
0x14004da0f  call    HsmDbgBreakOnStatus
0x14004da14  test    r12d, r12d
0x14004da17  js      loc_14004DB76
0x14004da1d  mov     rax, [rbx+10h]
0x14004da21  mov     rcx, rbp
0x14004da24  movzx   r12d, sil
0x14004da28  mov     edi, [rax+1Ch]
0x14004da2b  shr     edi, 8
0x14004da2e  and     dil, sil
0x14004da31  call    HsmOsGetPlaceholderCompatMode
0x14004da36  movzx   ecx, al
0x14004da39  movzx   edx, dil
0x14004da3d  call    HsmOsDisguisePlaceholder
0x14004da42  test    al, al
0x14004da44  jz      loc_14004D913
0x14004da4a  mov     ecx, 0C0000275h
0x14004da4f  call    HsmDbgBreakOnStatus
0x14004da54  mov     dword ptr [rbp+18h], 0C0000275h
0x14004da5b  mov     esi, 4
0x14004da60  mov     qword ptr [rbp+20h], 0
0x14004da68  jmp     loc_14004D913
0x14004da6d  cmp     ecx, 94264h
0x14004da73  jbe     loc_14004DE83
0x14004da79  cmp     ecx, 980C8h
0x14004da7f  jz      loc_14004DD8A
0x14004da85  cmp     ecx, 98268h
0x14004da8b  jz      loc_14004DD32
0x14004da91  cmp     ecx, 9C040h
0x14004da97  jnz     loc_14004D92D
0x14004da9d  mov     rax, [rbx+10h]
0x14004daa1  mov     ecx, [rax+1Ch]
0x14004daa4  test    cl, 2
0x14004daa7  jnz     loc_14004D92D
0x14004daad  mov     rdx, rbp; CallbackData
0x14004dab0  mov     rcx, r13; Context
0x14004dab3  call    HsmpAcquireUserRequestRundownProtection
0x14004dab8  mov     ecx, eax
0x14004daba  mov     r12d, eax
0x14004dabd  call    HsmDbgBreakOnStatus
0x14004dac2  test    r12d, r12d
0x14004dac5  js      loc_14004DB76
0x14004dacb  mov     rdx, [rbx+10h]
0x14004dacf  movzx   r12d, sil
0x14004dad3  test    dword ptr [rdx+1Ch], 100h
0x14004dada  jnz     loc_14004D913
0x14004dae0  mov     r8, [rbp+10h]
0x14004dae4  mov     r9d, esi
0x14004dae7  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x14004daf0  mov     rcx, rbx
0x14004daf3  mov     [rsp+68h+var_40], 0
0x14004dafc  mov     [rsp+68h+var_48], rbp
0x14004db01  mov     r8, [r8+8]
0x14004db05  call    HsmpRecallInitiateHydration
0x14004db0a  jmp     loc_14004D911
0x14004db0f  mov     r8, rbx
0x14004db12  mov     rcx, rbp
0x14004db15  call    HsmFltPreSET_REPARSE_POINT
0x14004db1a  jmp     loc_14004D911
0x14004db1f  sub     ecx, 900EFh
0x14004db25  jz      loc_14004DE42
0x14004db2b  sub     ecx, 0Dh
0x14004db2e  jz      loc_14004DBCC
0x14004db34  cmp     ecx, 174h
0x14004db3a  jnz     loc_14004D92D
0x14004db40  mov     rdx, rbp; CallbackData
0x14004db43  mov     rcx, r13; Context
0x14004db46  call    HsmpAcquireUserRequestRundownProtection
0x14004db4b  mov     ecx, eax
0x14004db4d  mov     r12d, eax
0x14004db50  call    HsmDbgBreakOnStatus
0x14004db55  test    r12d, r12d
0x14004db58  js      short loc_14004DB76
0x14004db5a  mov     r8, rbx
0x14004db5d  mov     rcx, rbp
0x14004db60  movzx   r12d, sil
0x14004db64  call    HsmFltPreSET_PURGE_FAILURE_MODE
0x14004db69  jmp     loc_14004D911
0x14004db6e  mov     rax, r12
0x14004db71  jmp     loc_14004D7FC
0x14004db76  mov     [rbp+18h], r12d
0x14004db7a  mov     esi, 4
0x14004db7f  mov     qword ptr [rbp+20h], 0
0x14004db87  jmp     loc_14004D92D
0x14004db8c  mov     rax, [rbx+10h]
0x14004db90  mov     r9, rbx
0x14004db93  movzx   r8d, sil
0x14004db97  mov     [rsp+68h+var_48], rax
0x14004db9c  xor     edx, edx
0x14004db9e  mov     rcx, rbp
0x14004dba1  call    HsmpTracePreCallbackEnter
0x14004dba6  mov     r13, [rbx+10h]
0x14004dbaa  jmp     loc_14004D8EF
0x14004dbaf  test    rbx, rbx
0x14004dbb2  jz      loc_14004D89E
0x14004dbb8  mov     rcx, rbx; Context
0x14004dbbb  call    cs:__imp_FltDeleteContext
0x14004dbc2  nop     dword ptr [rax+rax+00h]
0x14004dbc7  jmp     loc_14004D885
0x14004dbcc  mov     rax, [rbx+10h]
0x14004dbd0  mov     ecx, [rax+1Ch]
0x14004dbd3  test    cl, 2
0x14004dbd6  jnz     loc_14004D92D
0x14004dbdc  mov     rdx, rbp; CallbackData
0x14004dbdf  mov     rcx, r13; Context
0x14004dbe2  call    HsmpAcquireUserRequestRundownProtection
0x14004dbe7  mov     ecx, eax
0x14004dbe9  mov     r12d, eax
0x14004dbec  call    HsmDbgBreakOnStatus
0x14004dbf1  test    r12d, r12d
0x14004dbf4  js      short loc_14004DB76
0x14004dbf6  mov     rax, [rbp+10h]
0x14004dbfa  movzx   r12d, sil
0x14004dbfe  mov     rcx, [rax+30h]
0x14004dc02  test    rcx, rcx
0x14004dc05  jz      loc_14004D913
0x14004dc0b  cmp     dword ptr [rax+20h], 18h
0x14004dc0f  jb      loc_14004D913
0x14004dc15  cmp     dword ptr [rcx+10h], 4000h
0x14004dc1c  jnz     loc_14004D913
0x14004dc22  mov     rax, [rbx+10h]
0x14004dc26  test    dword ptr [rax+1Ch], 100h
0x14004dc2d  jnz     loc_14004D913
0x14004dc33  mov     dword ptr [rbp+18h], 0C000CF0Ah
0x14004dc3a  mov     esi, 4
0x14004dc3f  mov     qword ptr [rbp+20h], 0
0x14004dc47  jmp     loc_14004D913
0x14004dc4c  mov     rax, [rbx+10h]
0x14004dc50  mov     ecx, [rax+1Ch]
0x14004dc53  test    cl, 2
0x14004dc56  jnz     loc_14004D92D
0x14004dc5c  mov     rdx, rbp; CallbackData
0x14004dc5f  mov     rcx, r13; Context
0x14004dc62  call    HsmpAcquireUserRequestRundownProtection
0x14004dc67  mov     ecx, eax
0x14004dc69  mov     r12d, eax
0x14004dc6c  call    HsmDbgBreakOnStatus
0x14004dc71  test    r12d, r12d
0x14004dc74  js      loc_14004DB76
0x14004dc7a  mov     r8, rbx
0x14004dc7d  mov     rcx, rbp
0x14004dc80  movzx   r12d, sil
0x14004dc84  call    HsmFltPreQUERY_ALLOCATED_RANGES
0x14004dc89  jmp     loc_14004D911
0x14004dc8e  mov     rax, [rbx+10h]
0x14004dc92  mov     ecx, [rax+1Ch]
0x14004dc95  test    cl, 2
0x14004dc98  jnz     loc_14004D92D
0x14004dc9e  mov     rdx, rbp; CallbackData
0x14004dca1  mov     rcx, r13; Context
0x14004dca4  call    HsmpAcquireUserRequestRundownProtection
0x14004dca9  mov     ecx, eax
  ... truncated ...
```
