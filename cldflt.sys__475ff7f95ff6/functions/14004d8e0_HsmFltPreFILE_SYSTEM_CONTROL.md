# HsmFltPreFILE_SYSTEM_CONTROL

- ea: `0x14004d8e0`
- end: `0x14004dfdb`
- name: `HsmFltPreFILE_SYSTEM_CONTROL`
- size: `1787`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
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
- `0x1400468c8`
- `0x140046968`
- `0x1400469f4`
- `0x140046a70`
- `0x14004d8e0`
- `0x14004dff0`
- `0x140062db8`
- `0x14006de90`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14004d949`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004d949`
- `FLTMGR!FltDeleteContext` at `0x14004dcdb`
- `FLTMGR!FltDeleteContext` at `0x14004dcdb`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d910`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d989`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d910`
- `FLTMGR!FltGetRequestorProcess` at `0x14004d989`
- `FLTMGR!FltReleaseContext` at `0x14004d9aa`
- `FLTMGR!FltReleaseContext` at `0x14004da55`
- `FLTMGR!FltReleaseContext` at `0x14004d9aa`
- `FLTMGR!FltReleaseContext` at `0x14004da55`

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
  int v25; // r12d
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
    HsmDbgBreakOnStatus(v25);
    if ( v25 < 0 )
      goto LABEL_55;
    v3 = 1;
    v27 = BYTE1(*(_DWORD *)(v8[2] + 28)) & 1;
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode(CallbackData);
    if ( (unsigned __int8)HsmOsDisguisePlaceholder(PlaceholderCompatMode, v27) )
    {
      HsmDbgBreakOnStatus(-1073741195);
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
          HsmDbgBreakOnStatus(v25);
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
          HsmDbgBreakOnStatus(v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreQUERY_ALLOCATED_RANGES(CallbackData, v35, v8);
            goto LABEL_19;
          }
          goto LABEL_55;
        }
        goto LABEL_24;
      }
      if ( (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
        goto LABEL_24;
      v25 = HsmpAcquireUserRequestRundownProtection(v18, CallbackData);
      HsmDbgBreakOnStatus(v25);
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
        HsmDbgBreakOnStatus(v25);
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
          HsmDbgBreakOnStatus(v25);
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
      HsmDbgBreakOnStatus(v25);
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
        HsmDbgBreakOnStatus(v25);
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
          HsmDbgBreakOnStatus(v25);
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
          HsmDbgBreakOnStatus(v25);
          if ( v25 >= 0 )
          {
            v3 = 1;
            v21 = HsmFltPreDELETE_REPARSE_POINT((__int64)CallbackData, v37, (__int64)v8);
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
      HsmDbgBreakOnStatus(v25);
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
      HsmDbgBreakOnStatus(v25);
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
    HsmDbgBreakOnStatus(v25);
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
0x14004d8e0  mov     [rsp+arg_18], rbx
0x14004d8e5  push    rbp
0x14004d8e6  push    rsi
0x14004d8e7  push    rdi
0x14004d8e8  push    r12
0x14004d8ea  push    r14
0x14004d8ec  sub     rsp, 40h
0x14004d8f0  xor     r12d, r12d
0x14004d8f3  mov     r14, r8
0x14004d8f6  mov     [r8], r12
0x14004d8f9  mov     rdi, rdx
0x14004d8fc  mov     rbp, rcx
0x14004d8ff  mov     esi, 1
0x14004d904  mov     ebx, r12d
0x14004d907  test    rcx, rcx
0x14004d90a  jz      loc_14004DC8E
0x14004d910  call    cs:__imp_FltGetRequestorProcess
0x14004d917  nop     dword ptr [rax+rax+00h]
0x14004d91c  mov     rcx, rax
0x14004d91f  call    HsmOsIsPassThroughModeEnabled
0x14004d924  test    al, al
0x14004d926  jnz     loc_14004DA6E
0x14004d92c  mov     rdx, [rdi+20h]; FileObject
0x14004d930  lea     r8, [rsp+68h+Context]; Context
0x14004d935  mov     [rsp+68h+arg_10], r15
0x14004d93d  mov     r15, [rdi+18h]
0x14004d941  mov     rcx, r15; Instance
0x14004d944  mov     [rsp+68h+Context], r12
0x14004d949  call    cs:__imp_FltGetStreamHandleContext
0x14004d950  nop     dword ptr [rax+rax+00h]
0x14004d955  mov     rbx, [rsp+68h+Context]
0x14004d95a  test    rbx, rbx
0x14004d95d  jz      short loc_14004D9BE
0x14004d95f  mov     rcx, [rbx+10h]
0x14004d963  mov     eax, [rcx+1Ch]
0x14004d966  test    sil, al
0x14004d969  jz      loc_14004DCCF
0x14004d96f  mov     rax, [rcx+10h]
0x14004d973  mov     rcx, [rax+10h]
0x14004d977  cmp     [rcx+20h], r15
0x14004d97b  jnz     loc_14004DEEC
0x14004d981  test    rbp, rbp
0x14004d984  jz      short loc_14004D9BE
0x14004d986  mov     rcx, rbp; CallbackData
0x14004d989  call    cs:__imp_FltGetRequestorProcess
0x14004d990  nop     dword ptr [rax+rax+00h]
0x14004d995  mov     rcx, rax
0x14004d998  call    HsmOsIsPassThroughModeEnabled
0x14004d99d  test    al, al
0x14004d99f  jz      loc_14004DEF4
0x14004d9a5  mov     rcx, [rsp+68h+Context]; Context
0x14004d9aa  call    cs:__imp_FltReleaseContext
0x14004d9b1  nop     dword ptr [rax+rax+00h]
0x14004d9b6  mov     rbx, r12
0x14004d9b9  mov     [rsp+68h+Context], rbx
0x14004d9be  mov     [rsp+68h+arg_8], r13
0x14004d9c3  test    rbx, rbx
0x14004d9c6  jnz     loc_14004DCAC
0x14004d9cc  mov     rax, [rbp+10h]
0x14004d9d0  cmp     byte ptr [rax+4], 0Dh
0x14004d9d4  jnz     loc_14004DA61
0x14004d9da  mov     ecx, [rax+28h]
0x14004d9dd  cmp     ecx, 903BCh
0x14004d9e3  jz      short loc_14004D9F5
0x14004d9e5  cmp     ecx, 900A4h
0x14004d9eb  jz      short loc_14004D9F5
0x14004d9ed  cmp     ecx, 9040Ch
0x14004d9f3  jnz     short loc_14004DA61
0x14004d9f5  mov     r9, rbx
0x14004d9f8  mov     [rsp+68h+var_48], r12
0x14004d9fd  xor     r8d, r8d
0x14004da00  movzx   edx, sil
0x14004da04  mov     rcx, rbp
0x14004da07  mov     r13, r12
0x14004da0a  call    HsmpTracePreCallbackEnter
0x14004da0f  mov     rax, [rbp+10h]
0x14004da13  mov     ecx, [rax+28h]
0x14004da16  cmp     ecx, 903BCh
0x14004da1c  jnz     loc_14004DAA3
0x14004da22  lea     r8, [rbp+20h]
0x14004da26  mov     rdx, rbx; int
0x14004da29  mov     rcx, rbp; CallbackData
0x14004da2c  call    HsmFltProcessHSMControl
0x14004da31  mov     esi, eax
0x14004da33  test    esi, esi
0x14004da35  jz      loc_14004DF82
0x14004da3b  cmp     esi, 2
0x14004da3e  jz      short loc_14004DA4D
0x14004da40  test    r12b, r12b
0x14004da43  jz      short loc_14004DA4D
0x14004da45  mov     rcx, r13; Context
0x14004da48  call    HsmpReleaseUserRequestRundownProtection
0x14004da4d  test    rbx, rbx
0x14004da50  jz      short loc_14004DA61
0x14004da52  mov     rcx, rbx; Context
0x14004da55  call    cs:__imp_FltReleaseContext
0x14004da5c  nop     dword ptr [rax+rax+00h]
0x14004da61  mov     r13, [rsp+68h+arg_8]
0x14004da66  mov     r15, [rsp+68h+arg_10]
0x14004da6e  mov     r8, [r14]
0x14004da71  test    rbx, rbx
0x14004da74  mov     rdx, rbp
0x14004da77  mov     ecx, esi
0x14004da79  setnz   al
0x14004da7c  test    rbx, rbx
0x14004da7f  mov     byte ptr [rsp+68h+var_48], al
0x14004da83  setz    r9b
0x14004da87  call    HsmpTracePreCallbackExit
0x14004da8c  mov     rbx, [rsp+68h+arg_18]
0x14004da94  mov     eax, esi
0x14004da96  add     rsp, 40h
0x14004da9a  pop     r14
0x14004da9c  pop     r12
0x14004da9e  pop     rdi
0x14004da9f  pop     rsi
0x14004daa0  pop     rbp
0x14004daa1  retn
0x14004daa3  cmp     ecx, 900A8h
0x14004daa9  jz      short loc_14004DB1F
0x14004daab  cmp     ecx, 903FCh
0x14004dab1  ja      loc_14004DB8D
0x14004dab7  jz      loc_14004DF8A
0x14004dabd  cmp     ecx, 900E3h
0x14004dac3  ja      loc_14004DC3F
0x14004dac9  jz      loc_14004DF30
0x14004dacf  sub     ecx, 900A4h
0x14004dad5  jz      loc_14004DC2F
0x14004dadb  sub     ecx, 8
0x14004dade  jz      loc_14004DEFE
0x14004dae4  cmp     ecx, 33h ; '3'
0x14004dae7  jnz     loc_14004DA4D
0x14004daed  mov     rdx, rbp; CallbackData
0x14004daf0  mov     rcx, r13; Context
0x14004daf3  call    HsmpAcquireUserRequestRundownProtection
0x14004daf8  mov     ecx, eax
0x14004dafa  mov     r12d, eax
0x14004dafd  call    HsmDbgBreakOnStatus
0x14004db02  test    r12d, r12d
0x14004db05  js      loc_14004DC96
0x14004db0b  mov     r8, rbx
0x14004db0e  mov     rcx, rbp
0x14004db11  movzx   r12d, sil
0x14004db15  call    HsmFltPreWRITE_RAW_ENCRYPTED
0x14004db1a  jmp     loc_14004DA31
0x14004db1f  mov     rdx, rbp; CallbackData
0x14004db22  mov     rcx, r13; Context
0x14004db25  call    HsmpAcquireUserRequestRundownProtection
0x14004db2a  mov     ecx, eax
0x14004db2c  mov     r12d, eax
0x14004db2f  call    HsmDbgBreakOnStatus
0x14004db34  test    r12d, r12d
0x14004db37  js      loc_14004DC96
0x14004db3d  mov     rax, [rbx+10h]
0x14004db41  mov     rcx, rbp
0x14004db44  movzx   r12d, sil
0x14004db48  mov     edi, [rax+1Ch]
0x14004db4b  shr     edi, 8
0x14004db4e  and     dil, sil
0x14004db51  call    HsmOsGetPlaceholderCompatMode
0x14004db56  movzx   ecx, al
0x14004db59  movzx   edx, dil
0x14004db5d  call    HsmOsDisguisePlaceholder
0x14004db62  test    al, al
0x14004db64  jz      loc_14004DA33
0x14004db6a  mov     ecx, 0C0000275h
0x14004db6f  call    HsmDbgBreakOnStatus
0x14004db74  mov     dword ptr [rbp+18h], 0C0000275h
0x14004db7b  mov     esi, 4
0x14004db80  mov     qword ptr [rbp+20h], 0
0x14004db88  jmp     loc_14004DA33
0x14004db8d  cmp     ecx, 94264h
0x14004db93  jbe     loc_14004DFA3
0x14004db99  cmp     ecx, 980C8h
0x14004db9f  jz      loc_14004DEAA
0x14004dba5  cmp     ecx, 98268h
0x14004dbab  jz      loc_14004DE52
0x14004dbb1  cmp     ecx, 9C040h
0x14004dbb7  jnz     loc_14004DA4D
0x14004dbbd  mov     rax, [rbx+10h]
0x14004dbc1  mov     ecx, [rax+1Ch]
0x14004dbc4  test    cl, 2
0x14004dbc7  jnz     loc_14004DA4D
0x14004dbcd  mov     rdx, rbp; CallbackData
0x14004dbd0  mov     rcx, r13; Context
0x14004dbd3  call    HsmpAcquireUserRequestRundownProtection
0x14004dbd8  mov     ecx, eax
0x14004dbda  mov     r12d, eax
0x14004dbdd  call    HsmDbgBreakOnStatus
0x14004dbe2  test    r12d, r12d
0x14004dbe5  js      loc_14004DC96
0x14004dbeb  mov     rdx, [rbx+10h]
0x14004dbef  movzx   r12d, sil
0x14004dbf3  test    dword ptr [rdx+1Ch], 100h
0x14004dbfa  jnz     loc_14004DA33
0x14004dc00  mov     r8, [rbp+10h]
0x14004dc04  mov     r9d, esi
0x14004dc07  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFFh
0x14004dc10  mov     rcx, rbx
0x14004dc13  mov     [rsp+68h+var_40], 0
0x14004dc1c  mov     [rsp+68h+var_48], rbp
0x14004dc21  mov     r8, [r8+8]
0x14004dc25  call    HsmpRecallInitiateHydration
0x14004dc2a  jmp     loc_14004DA31
0x14004dc2f  mov     r8, rbx
0x14004dc32  mov     rcx, rbp
0x14004dc35  call    HsmFltPreSET_REPARSE_POINT
0x14004dc3a  jmp     loc_14004DA31
0x14004dc3f  sub     ecx, 900EFh
0x14004dc45  jz      loc_14004DF62
0x14004dc4b  sub     ecx, 0Dh
0x14004dc4e  jz      loc_14004DCEC
0x14004dc54  cmp     ecx, 174h
0x14004dc5a  jnz     loc_14004DA4D
0x14004dc60  mov     rdx, rbp; CallbackData
0x14004dc63  mov     rcx, r13; Context
0x14004dc66  call    HsmpAcquireUserRequestRundownProtection
0x14004dc6b  mov     ecx, eax
0x14004dc6d  mov     r12d, eax
0x14004dc70  call    HsmDbgBreakOnStatus
0x14004dc75  test    r12d, r12d
0x14004dc78  js      short loc_14004DC96
0x14004dc7a  mov     r8, rbx
0x14004dc7d  mov     rcx, rbp
0x14004dc80  movzx   r12d, sil
0x14004dc84  call    HsmFltPreSET_PURGE_FAILURE_MODE
0x14004dc89  jmp     loc_14004DA31
0x14004dc8e  mov     rax, r12
0x14004dc91  jmp     loc_14004D91C
0x14004dc96  mov     [rbp+18h], r12d
0x14004dc9a  mov     esi, 4
0x14004dc9f  mov     qword ptr [rbp+20h], 0
0x14004dca7  jmp     loc_14004DA4D
0x14004dcac  mov     rax, [rbx+10h]
0x14004dcb0  mov     r9, rbx
0x14004dcb3  movzx   r8d, sil
0x14004dcb7  mov     [rsp+68h+var_48], rax
0x14004dcbc  xor     edx, edx
0x14004dcbe  mov     rcx, rbp
0x14004dcc1  call    HsmpTracePreCallbackEnter
0x14004dcc6  mov     r13, [rbx+10h]
0x14004dcca  jmp     loc_14004DA0F
0x14004dccf  test    rbx, rbx
0x14004dcd2  jz      loc_14004D9BE
0x14004dcd8  mov     rcx, rbx; Context
0x14004dcdb  call    cs:__imp_FltDeleteContext
0x14004dce2  nop     dword ptr [rax+rax+00h]
0x14004dce7  jmp     loc_14004D9A5
0x14004dcec  mov     rax, [rbx+10h]
0x14004dcf0  mov     ecx, [rax+1Ch]
0x14004dcf3  test    cl, 2
0x14004dcf6  jnz     loc_14004DA4D
0x14004dcfc  mov     rdx, rbp; CallbackData
0x14004dcff  mov     rcx, r13; Context
0x14004dd02  call    HsmpAcquireUserRequestRundownProtection
0x14004dd07  mov     ecx, eax
0x14004dd09  mov     r12d, eax
0x14004dd0c  call    HsmDbgBreakOnStatus
0x14004dd11  test    r12d, r12d
0x14004dd14  js      short loc_14004DC96
0x14004dd16  mov     rax, [rbp+10h]
0x14004dd1a  movzx   r12d, sil
0x14004dd1e  mov     rcx, [rax+30h]
0x14004dd22  test    rcx, rcx
0x14004dd25  jz      loc_14004DA33
0x14004dd2b  cmp     dword ptr [rax+20h], 18h
0x14004dd2f  jb      loc_14004DA33
0x14004dd35  cmp     dword ptr [rcx+10h], 4000h
0x14004dd3c  jnz     loc_14004DA33
0x14004dd42  mov     rax, [rbx+10h]
0x14004dd46  test    dword ptr [rax+1Ch], 100h
0x14004dd4d  jnz     loc_14004DA33
0x14004dd53  mov     dword ptr [rbp+18h], 0C000CF0Ah
0x14004dd5a  mov     esi, 4
0x14004dd5f  mov     qword ptr [rbp+20h], 0
0x14004dd67  jmp     loc_14004DA33
0x14004dd6c  mov     rax, [rbx+10h]
0x14004dd70  mov     ecx, [rax+1Ch]
0x14004dd73  test    cl, 2
0x14004dd76  jnz     loc_14004DA4D
0x14004dd7c  mov     rdx, rbp; CallbackData
0x14004dd7f  mov     rcx, r13; Context
0x14004dd82  call    HsmpAcquireUserRequestRundownProtection
0x14004dd87  mov     ecx, eax
0x14004dd89  mov     r12d, eax
0x14004dd8c  call    HsmDbgBreakOnStatus
0x14004dd91  test    r12d, r12d
0x14004dd94  js      loc_14004DC96
0x14004dd9a  mov     r8, rbx
0x14004dd9d  mov     rcx, rbp
0x14004dda0  movzx   r12d, sil
0x14004dda4  call    HsmFltPreQUERY_ALLOCATED_RANGES
0x14004dda9  jmp     loc_14004DA31
0x14004ddae  mov     rax, [rbx+10h]
0x14004ddb2  mov     ecx, [rax+1Ch]
0x14004ddb5  test    cl, 2
0x14004ddb8  jnz     loc_14004DA4D
0x14004ddbe  mov     rdx, rbp; CallbackData
0x14004ddc1  mov     rcx, r13; Context
0x14004ddc4  call    HsmpAcquireUserRequestRundownProtection
0x14004ddc9  mov     ecx, eax
  ... truncated ...
```
