# HsmFltPreSET_INFORMATION

- ea: `0x1400525b0`
- end: `0x1400529e1`
- name: `HsmFltPreSET_INFORMATION`
- size: `1073`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callees

- `0x140001910`
- `0x140001ab4`
- `0x140001d00`
- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x140007ddc`
- `0x14000cd0c`
- `0x1400525b0`
- `0x1400529f0`
- `0x140053128`
- `0x1400536e0`
- `0x140055308`
- `0x140058cbc`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14005267c`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005267c`
- `FLTMGR!FltDeleteContext` at `0x1400529a8`
- `FLTMGR!FltDeleteContext` at `0x1400529a8`
- `FLTMGR!FltGetRequestorProcess` at `0x1400525d3`
- `FLTMGR!FltGetRequestorProcess` at `0x1400526b9`
- `FLTMGR!FltGetRequestorProcess` at `0x1400525d3`
- `FLTMGR!FltGetRequestorProcess` at `0x1400526b9`
- `FLTMGR!FltGetInstanceContext` at `0x140052608`
- `FLTMGR!FltGetInstanceContext` at `0x140052608`
- `FLTMGR!FltReleaseContext` at `0x140052631`
- `FLTMGR!FltReleaseContext` at `0x1400526dd`
- `FLTMGR!FltReleaseContext` at `0x14005273d`
- `FLTMGR!FltReleaseContext` at `0x140052797`
- `FLTMGR!FltReleaseContext` at `0x140052631`
- `FLTMGR!FltReleaseContext` at `0x1400526dd`
- `FLTMGR!FltReleaseContext` at `0x14005273d`
- `FLTMGR!FltReleaseContext` at `0x140052797`

## pseudocode

```c
__int64 __fastcall HsmFltPreSET_INFORMATION(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *Instance,
        union _LARGE_INTEGER **a3)
{
  ULONG Options; // ebx
  PEPROCESS RequestorProcess; // rax
  struct _FLT_INSTANCE *v8; // rcx
  unsigned __int16 *v9; // r15
  struct _FILE_OBJECT *v10; // rdx
  union _LARGE_INTEGER *v11; // rsi
  struct _FLT_INSTANCE *v12; // rdi
  int v13; // edx
  int v14; // r8d
  _QWORD *v15; // r14
  __int64 v16; // rcx
  PEPROCESS v17; // rax
  PFLT_CONTEXT v18; // rcx
  unsigned int v19; // ebx
  int v20; // r9d
  __int64 *EaBuffer; // rax
  __int64 v23; // rbx
  __int64 v24; // r13
  unsigned int v25; // eax
  char StreamSize; // al
  __int64 v27; // r8
  __int64 v28; // r10
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFLT_CONTEXT v30; // [rsp+A0h] [rbp+8h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v32; // [rsp+B8h] [rbp+20h]

  Options = CallbackData->Iopb->Parameters.Create.Options;
  *a3 = 0;
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  if ( (unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
    return 1;
  v8 = (struct _FLT_INSTANCE *)*((_QWORD *)Instance + 3);
  Context = 0;
  FltGetInstanceContext(v8, &Context);
  v9 = (unsigned __int16 *)Context;
  if ( !Context )
    return 1;
  if ( *(_DWORD *)Context != 1665758024 )
  {
    FltReleaseContext(Context);
    v9 = 0;
    Context = 0;
  }
  if ( !v9 )
    return 1;
  v10 = (struct _FILE_OBJECT *)*((_QWORD *)Instance + 4);
  v11 = 0;
  v12 = (struct _FLT_INSTANCE *)*((_QWORD *)Instance + 3);
  v30 = 0;
  FltGetStreamHandleContext(v12, v10, &v30);
  v15 = v30;
  if ( v30 )
  {
    v16 = *((_QWORD *)v30 + 2);
    if ( (*(_DWORD *)(v16 + 28) & 1) != 0 )
    {
      if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v16 + 16) + 16LL) + 32LL) != v12 )
      {
        v18 = v30;
        goto LABEL_11;
      }
      v17 = FltGetRequestorProcess(CallbackData);
      if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(v17) )
      {
        v15 = v30;
LABEL_12:
        if ( v15 )
          v11 = (union _LARGE_INTEGER *)v15[2];
        goto LABEL_14;
      }
LABEL_10:
      v18 = v30;
LABEL_11:
      FltReleaseContext(v18);
      v15 = 0;
      v30 = 0;
      goto LABEL_12;
    }
    if ( v30 )
    {
      FltDeleteContext(v30);
      goto LABEL_10;
    }
  }
LABEL_14:
  LOBYTE(v14) = v11 != 0;
  LOBYTE(v13) = v11 == 0;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, v13, v14, (_DWORD)v15, (__int64)v11);
  if ( Options == 4 )
  {
    v19 = HsmFltPreSetBasicInformation(v9, v11, v15, CallbackData, Instance, a3);
  }
  else if ( Options == 20 )
  {
LABEL_16:
    v19 = 1;
    if ( v15 )
    {
      Iopb = CallbackData->Iopb;
      if ( !Iopb->Parameters.SetFileInformation.AdvanceOnly )
      {
        EaBuffer = (__int64 *)Iopb->Parameters.Create.EaBuffer;
        v32 = *((_QWORD *)Instance + 4);
        v23 = *EaBuffer;
        v24 = (unsigned int)HsmpAcquireUserRequestRundownProtection(v11, CallbackData);
        HsmDbgBreakOnStatus(v24);
        if ( (int)v24 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            StreamSize = HsmpGetStreamSize(v11);
            WPP_SF_qqLiqiqd(
              *(_QWORD *)(v28 + 24),
              61,
              (unsigned int)WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
              (_DWORD)v9,
              (char)v11,
              v11[3].HighPart,
              StreamSize,
              v32,
              *(_QWORD *)(v27 + 32),
              CallbackData,
              v24);
          }
          CallbackData->IoStatus.Status = v24;
          v19 = 4;
          CallbackData->IoStatus.Information = 0;
        }
        else
        {
          v25 = HsmpRecallInitiateHydration(
                  (_DWORD)v15,
                  (_DWORD)v11,
                  CallbackData->Iopb->TargetFileObject,
                  9,
                  (__int64)CallbackData,
                  v23,
                  -1);
          v19 = v25;
          if ( v25 )
          {
            if ( v25 != 2 )
              HsmpReleaseUserRequestRundownProtection(v11);
          }
          else
          {
            *a3 = v11;
          }
        }
      }
    }
  }
  else
  {
    switch ( Options )
    {
      case 0xAu:
      case 0x41u:
        v19 = HsmFltPreSetRenameInformation(v9, v11, v15, CallbackData, (__int64)Instance, (__int64)a3);
        break;
      case 0xBu:
      case 0x48u:
        v19 = HsmFltPreSetLinkInformation(v9, v11, (__int64)Instance, (__int64)a3);
        break;
      case 0xDu:
      case 0x40u:
        v19 = HsmFltPreSetDispositionInformation(v9, Instance, (__int64)a3);
        break;
      case 0x13u:
        goto LABEL_16;
      default:
        v19 = 1;
        break;
    }
  }
  FltReleaseContext(v9);
  if ( v15 )
    FltReleaseContext(v15);
  if ( v19 != 2 )
  {
    LOBYTE(v20) = v11 == 0;
    HsmpTracePreCallbackExit(v19, (_DWORD)CallbackData, (unsigned int)*a3, v20, v11 != 0);
  }
  return v19;
}

```

## disassembly

```asm
0x1400525b0  push    rbx
0x1400525b2  push    rbp
0x1400525b3  push    r12
0x1400525b5  push    r13
0x1400525b7  push    r14
0x1400525b9  sub     rsp, 70h
0x1400525bd  mov     rax, [rcx+10h]
0x1400525c1  xor     r14d, r14d
0x1400525c4  mov     r12, r8
0x1400525c7  mov     r13, rdx
0x1400525ca  mov     rbp, rcx
0x1400525cd  mov     ebx, [rax+20h]
0x1400525d0  mov     [r8], r14
0x1400525d3  call    cs:__imp_FltGetRequestorProcess
0x1400525da  nop     dword ptr [rax+rax+00h]
0x1400525df  mov     rcx, rax
0x1400525e2  call    HsmOsIsPassThroughModeEnabled
0x1400525e7  test    al, al
0x1400525e9  jnz     loc_1400529B9
0x1400525ef  mov     rcx, [r13+18h]; Instance
0x1400525f3  lea     rdx, [rsp+98h+Context]; Context
0x1400525fb  mov     [rsp+98h+var_38], r15
0x140052600  mov     [rsp+98h+Context], r14
0x140052608  call    cs:__imp_FltGetInstanceContext
0x14005260f  nop     dword ptr [rax+rax+00h]
0x140052614  mov     r15, [rsp+98h+Context]
0x14005261c  test    r15, r15
0x14005261f  jz      loc_140052848
0x140052625  cmp     dword ptr [r15], 63497348h
0x14005262c  jz      short loc_140052648
0x14005262e  mov     rcx, r15; Context
0x140052631  call    cs:__imp_FltReleaseContext
0x140052638  nop     dword ptr [rax+rax+00h]
0x14005263d  mov     r15d, r14d
0x140052640  mov     [rsp+98h+Context], r14
0x140052648  test    r15, r15
0x14005264b  jz      loc_140052848
0x140052651  mov     rdx, [r13+20h]; FileObject
0x140052655  lea     r8, [rsp+98h+arg_0]; Context
0x14005265d  mov     [rsp+98h+arg_8], rsi
0x140052665  mov     rsi, r14
0x140052668  mov     [rsp+98h+var_30], rdi
0x14005266d  mov     rdi, [r13+18h]
0x140052671  mov     rcx, rdi; Instance
0x140052674  mov     [rsp+98h+arg_0], r14
0x14005267c  call    cs:__imp_FltGetStreamHandleContext
0x140052683  nop     dword ptr [rax+rax+00h]
0x140052688  mov     r14, [rsp+98h+arg_0]
0x140052690  test    r14, r14
0x140052693  jz      short loc_1400526FD
0x140052695  mov     rcx, [r14+10h]
0x140052699  mov     eax, [rcx+1Ch]
0x14005269c  test    al, 1
0x14005269e  jz      loc_14005299C
0x1400526a4  mov     rax, [rcx+10h]
0x1400526a8  mov     rcx, [rax+10h]
0x1400526ac  cmp     [rcx+20h], rdi
0x1400526b0  jnz     loc_1400529C3
0x1400526b6  mov     rcx, rbp; CallbackData
0x1400526b9  call    cs:__imp_FltGetRequestorProcess
0x1400526c0  nop     dword ptr [rax+rax+00h]
0x1400526c5  mov     rcx, rax
0x1400526c8  call    HsmOsIsPassThroughModeEnabled
0x1400526cd  test    al, al
0x1400526cf  jz      loc_1400529CB
0x1400526d5  mov     rcx, [rsp+98h+arg_0]; Context
0x1400526dd  call    cs:__imp_FltReleaseContext
0x1400526e4  nop     dword ptr [rax+rax+00h]
0x1400526e9  xor     r14d, r14d
0x1400526ec  mov     [rsp+98h+arg_0], r14
0x1400526f4  test    r14, r14
0x1400526f7  jnz     loc_1400527A5
0x1400526fd  test    rsi, rsi
0x140052700  mov     [rsp+98h+Instance], rsi
0x140052705  mov     r9, r14
0x140052708  mov     rcx, rbp
0x14005270b  setnz   r8b
0x14005270f  test    rsi, rsi
0x140052712  setz    dl
0x140052715  call    HsmpTracePreCallbackEnter
0x14005271a  cmp     ebx, 4
0x14005271d  jz      loc_1400527AE
0x140052723  cmp     ebx, 14h
0x140052726  jnz     loc_1400527D0
0x14005272c  mov     ebx, 1; jumptable 00000001400527F4 case 19
0x140052731  test    r14, r14
0x140052734  jnz     loc_140052989
0x14005273a  mov     rcx, r15; Context
0x14005273d  call    cs:__imp_FltReleaseContext
0x140052744  nop     dword ptr [rax+rax+00h]
0x140052749  test    r14, r14
0x14005274c  jnz     short loc_140052794
0x14005274e  mov     rdi, [rsp+98h+var_30]
0x140052753  cmp     ebx, 2
0x140052756  jz      short loc_140052777
0x140052758  mov     r8, [r12]
0x14005275c  test    rsi, rsi
0x14005275f  mov     rdx, rbp
0x140052762  mov     ecx, ebx
0x140052764  setnz   al
0x140052767  test    rsi, rsi
0x14005276a  mov     byte ptr [rsp+98h+Instance], al
0x14005276e  setz    r9b
0x140052772  call    HsmpTracePreCallbackExit
0x140052777  mov     rsi, [rsp+98h+arg_8]
0x14005277f  mov     eax, ebx
0x140052781  mov     r15, [rsp+98h+var_38]
0x140052786  add     rsp, 70h
0x14005278a  pop     r14
0x14005278c  pop     r13
0x14005278e  pop     r12
0x140052790  pop     rbp
0x140052791  pop     rbx
0x140052792  retn
0x140052794  mov     rcx, r14; Context
0x140052797  call    cs:__imp_FltReleaseContext
0x14005279e  nop     dword ptr [rax+rax+00h]
0x1400527a3  jmp     short loc_14005274E
0x1400527a5  mov     rsi, [r14+10h]
0x1400527a9  jmp     loc_1400526FD
0x1400527ae  mov     [rsp+98h+var_70], r12
0x1400527b3  mov     r9, rbp
0x1400527b6  mov     r8, r14
0x1400527b9  mov     [rsp+98h+Instance], r13
0x1400527be  mov     rdx, rsi
0x1400527c1  mov     rcx, r15
0x1400527c4  call    HsmFltPreSetBasicInformation
0x1400527c9  mov     ebx, eax
0x1400527cb  jmp     loc_14005273A
0x1400527d0  add     ebx, 0FFFFFFF6h; switch 63 cases
0x1400527d3  cmp     ebx, 3Eh
0x1400527d6  ja      short def_1400527F4; jumptable 00000001400527F4 default case, cases 12,14-18,20-63,66-71
0x1400527d8  lea     rdx, cs:140000000h
0x1400527df  movsxd  rax, ebx
0x1400527e2  movzx   eax, ds:(byte_140021FF2 - 140000000h)[rdx+rax]
0x1400527ea  mov     ecx, ds:(jpt_1400527F4 - 140000000h)[rdx+rax*4]
0x1400527f1  add     rcx, rdx
0x1400527f4  jmp     rcx; switch jump
0x1400527fa  mov     [rsp+98h+var_70], r12; jumptable 00000001400527F4 cases 13,64
0x1400527ff  mov     r9, rbp
0x140052802  mov     r8, r14
0x140052805  mov     [rsp+98h+Instance], r13; Instance
0x14005280a  mov     rdx, rsi
0x14005280d  mov     rcx, r15; Context
0x140052810  call    HsmFltPreSetDispositionInformation
0x140052815  mov     ebx, eax
0x140052817  jmp     loc_14005273A
0x14005281c  mov     ebx, 1; jumptable 00000001400527F4 default case, cases 12,14-18,20-63,66-71
0x140052821  jmp     loc_14005273A
0x140052826  mov     [rsp+98h+var_70], r12; jumptable 00000001400527F4 cases 10,65
0x14005282b  mov     r9, rbp
0x14005282e  mov     r8, r14
0x140052831  mov     [rsp+98h+Instance], r13; __int64
0x140052836  mov     rdx, rsi; PFLT_CONTEXT
0x140052839  mov     rcx, r15; Context
0x14005283c  call    HsmFltPreSetRenameInformation
0x140052841  mov     ebx, eax
0x140052843  jmp     loc_14005273A
0x140052848  mov     r15, [rsp+98h+var_38]
0x14005284d  mov     eax, 1
0x140052852  add     rsp, 70h
0x140052856  pop     r14
0x140052858  pop     r13
0x14005285a  pop     r12
0x14005285c  pop     rbp
0x14005285d  pop     rbx
0x14005285e  retn
0x140052860  mov     [rsp+98h+var_70], r12; jumptable 00000001400527F4 cases 11,72
0x140052865  mov     r9, rbp
0x140052868  mov     r8, r14
0x14005286b  mov     [rsp+98h+Instance], r13; __int64
0x140052870  mov     rdx, rsi; PFLT_CONTEXT
0x140052873  mov     rcx, r15; Context
0x140052876  call    HsmFltPreSetLinkInformation
0x14005287b  mov     ebx, eax
0x14005287d  jmp     loc_14005273A
0x140052882  mov     rcx, [r13+20h]
0x140052886  mov     rdx, rbp; CallbackData
0x140052889  mov     rax, [rax+38h]
0x14005288d  mov     [rsp+98h+arg_18], rcx
0x140052895  mov     rcx, rsi; Context
0x140052898  mov     rbx, [rax]
0x14005289b  call    HsmpAcquireUserRequestRundownProtection
0x1400528a0  mov     ecx, eax
0x1400528a2  mov     r13d, eax
0x1400528a5  call    HsmDbgBreakOnStatus
0x1400528aa  test    r13d, r13d
0x1400528ad  js      short loc_1400528FB
0x1400528af  mov     r8, [rbp+10h]
0x1400528b3  mov     r9d, 9
0x1400528b9  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFFh
0x1400528c2  mov     rdx, rsi
0x1400528c5  mov     [rsp+98h+var_70], rbx
0x1400528ca  mov     rcx, r14
0x1400528cd  mov     [rsp+98h+Instance], rbp
0x1400528d2  mov     r8, [r8+8]
0x1400528d6  call    HsmpRecallInitiateHydration
0x1400528db  mov     ebx, eax
0x1400528dd  test    eax, eax
0x1400528df  jz      loc_1400529D8
0x1400528e5  cmp     eax, 2
0x1400528e8  jz      loc_14005273A
0x1400528ee  mov     rcx, rsi; Context
0x1400528f1  call    HsmpReleaseUserRequestRundownProtection
0x1400528f6  jmp     loc_14005273A
0x1400528fb  mov     r10, cs:WPP_GLOBAL_Control
0x140052902  lea     rax, WPP_GLOBAL_Control
0x140052909  cmp     r10, rax
0x14005290c  jz      short loc_140052973
0x14005290e  mov     ecx, [r10+2Ch]
0x140052912  test    cl, 1
0x140052915  jz      short loc_140052973
0x140052917  cmp     byte ptr [r10+29h], 2
0x14005291c  jb      short loc_140052973
0x14005291e  mov     r8, [rsi+10h]
0x140052922  mov     rcx, rsi
0x140052925  call    HsmpGetStreamSize
0x14005292a  mov     r8, [r8+20h]
0x14005292e  mov     edx, 3Dh ; '='
0x140052933  mov     rcx, [rsp+98h+arg_18]
0x14005293b  mov     r9, r15
0x14005293e  mov     [rsp+98h+var_48], r13d
0x140052943  mov     [rsp+98h+var_50], rbp
0x140052948  mov     [rsp+98h+var_58], r8
0x14005294d  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140052954  mov     [rsp+98h+var_60], rcx
0x140052959  mov     rcx, [r10+18h]
0x14005295d  mov     [rsp+98h+var_68], rax
0x140052962  mov     eax, [rsi+1Ch]
0x140052965  mov     dword ptr [rsp+98h+var_70], eax
0x140052969  mov     [rsp+98h+Instance], rsi
0x14005296e  call    WPP_SF_qqLiqiqd
0x140052973  mov     [rbp+18h], r13d
0x140052977  mov     ebx, 4
0x14005297c  mov     qword ptr [rbp+20h], 0
0x140052984  jmp     loc_14005273A
0x140052989  mov     rax, [rbp+10h]
0x14005298d  cmp     byte ptr [rax+31h], 0
0x140052991  jnz     loc_14005273A
0x140052997  jmp     loc_140052882
0x14005299c  test    r14, r14
0x14005299f  jz      loc_1400526FD
0x1400529a5  mov     rcx, r14; Context
0x1400529a8  call    cs:__imp_FltDeleteContext
0x1400529af  nop     dword ptr [rax+rax+00h]
0x1400529b4  jmp     loc_1400526D5
0x1400529b9  mov     eax, 1
0x1400529be  jmp     loc_140052786
0x1400529c3  mov     rcx, r14
0x1400529c6  jmp     loc_1400526DD
0x1400529cb  mov     r14, [rsp+98h+arg_0]
0x1400529d3  jmp     loc_1400526F4
0x1400529d8  mov     [r12], rsi
0x1400529dc  jmp     loc_14005273A
```
