# HsmFltPreSET_INFORMATION

- ea: `0x1400526d0`
- end: `0x140052b01`
- name: `HsmFltPreSET_INFORMATION`
- size: `1073`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, struct _FLT_INSTANCE *Instance, _QWORD *)`
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
- `0x1400526d0`
- `0x140052b10`
- `0x140053248`
- `0x140053800`
- `0x140055428`
- `0x140058ddc`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14005279c`
- `FLTMGR!FltGetStreamHandleContext` at `0x14005279c`
- `FLTMGR!FltDeleteContext` at `0x140052ac8`
- `FLTMGR!FltDeleteContext` at `0x140052ac8`
- `FLTMGR!FltGetRequestorProcess` at `0x1400526f3`
- `FLTMGR!FltGetRequestorProcess` at `0x1400527d9`
- `FLTMGR!FltGetRequestorProcess` at `0x1400526f3`
- `FLTMGR!FltGetRequestorProcess` at `0x1400527d9`
- `FLTMGR!FltGetInstanceContext` at `0x140052728`
- `FLTMGR!FltGetInstanceContext` at `0x140052728`
- `FLTMGR!FltReleaseContext` at `0x140052751`
- `FLTMGR!FltReleaseContext` at `0x1400527fd`
- `FLTMGR!FltReleaseContext` at `0x14005285d`
- `FLTMGR!FltReleaseContext` at `0x1400528b7`
- `FLTMGR!FltReleaseContext` at `0x140052751`
- `FLTMGR!FltReleaseContext` at `0x1400527fd`
- `FLTMGR!FltReleaseContext` at `0x14005285d`
- `FLTMGR!FltReleaseContext` at `0x1400528b7`

## pseudocode

```c
__int64 __fastcall HsmFltPreSET_INFORMATION(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *Instance,
        _QWORD *a3)
{
  ULONG Options; // ebx
  PEPROCESS RequestorProcess; // rax
  struct _FLT_INSTANCE *v8; // rcx
  PFLT_CONTEXT v9; // r15
  struct _FILE_OBJECT *v10; // rdx
  _DWORD *v11; // rsi
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
  int v24; // r13d
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
  v9 = Context;
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
          v11 = (_DWORD *)v15[2];
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
        v24 = HsmpAcquireUserRequestRundownProtection(v11, CallbackData);
        HsmDbgBreakOnStatus(v24);
        if ( v24 < 0 )
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
              v11[7],
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
        v19 = HsmFltPreSetRenameInformation(v9, v11, (__int64)Instance, (__int64)a3);
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
    HsmpTracePreCallbackExit(v19, (_DWORD)CallbackData, *a3, v20, v11 != 0);
  }
  return v19;
}

```

## disassembly

```asm
0x1400526d0  push    rbx
0x1400526d2  push    rbp
0x1400526d3  push    r12
0x1400526d5  push    r13
0x1400526d7  push    r14
0x1400526d9  sub     rsp, 70h
0x1400526dd  mov     rax, [rcx+10h]
0x1400526e1  xor     r14d, r14d
0x1400526e4  mov     r12, r8
0x1400526e7  mov     r13, rdx
0x1400526ea  mov     rbp, rcx
0x1400526ed  mov     ebx, [rax+20h]
0x1400526f0  mov     [r8], r14
0x1400526f3  call    cs:__imp_FltGetRequestorProcess
0x1400526fa  nop     dword ptr [rax+rax+00h]
0x1400526ff  mov     rcx, rax
0x140052702  call    HsmOsIsPassThroughModeEnabled
0x140052707  test    al, al
0x140052709  jnz     loc_140052AD9
0x14005270f  mov     rcx, [r13+18h]; Instance
0x140052713  lea     rdx, [rsp+98h+Context]; Context
0x14005271b  mov     [rsp+98h+var_38], r15
0x140052720  mov     [rsp+98h+Context], r14
0x140052728  call    cs:__imp_FltGetInstanceContext
0x14005272f  nop     dword ptr [rax+rax+00h]
0x140052734  mov     r15, [rsp+98h+Context]
0x14005273c  test    r15, r15
0x14005273f  jz      loc_140052968
0x140052745  cmp     dword ptr [r15], 63497348h
0x14005274c  jz      short loc_140052768
0x14005274e  mov     rcx, r15; Context
0x140052751  call    cs:__imp_FltReleaseContext
0x140052758  nop     dword ptr [rax+rax+00h]
0x14005275d  mov     r15d, r14d
0x140052760  mov     [rsp+98h+Context], r14
0x140052768  test    r15, r15
0x14005276b  jz      loc_140052968
0x140052771  mov     rdx, [r13+20h]; FileObject
0x140052775  lea     r8, [rsp+98h+arg_0]; Context
0x14005277d  mov     [rsp+98h+arg_8], rsi
0x140052785  mov     rsi, r14
0x140052788  mov     [rsp+98h+var_30], rdi
0x14005278d  mov     rdi, [r13+18h]
0x140052791  mov     rcx, rdi; Instance
0x140052794  mov     [rsp+98h+arg_0], r14
0x14005279c  call    cs:__imp_FltGetStreamHandleContext
0x1400527a3  nop     dword ptr [rax+rax+00h]
0x1400527a8  mov     r14, [rsp+98h+arg_0]
0x1400527b0  test    r14, r14
0x1400527b3  jz      short loc_14005281D
0x1400527b5  mov     rcx, [r14+10h]
0x1400527b9  mov     eax, [rcx+1Ch]
0x1400527bc  test    al, 1
0x1400527be  jz      loc_140052ABC
0x1400527c4  mov     rax, [rcx+10h]
0x1400527c8  mov     rcx, [rax+10h]
0x1400527cc  cmp     [rcx+20h], rdi
0x1400527d0  jnz     loc_140052AE3
0x1400527d6  mov     rcx, rbp; CallbackData
0x1400527d9  call    cs:__imp_FltGetRequestorProcess
0x1400527e0  nop     dword ptr [rax+rax+00h]
0x1400527e5  mov     rcx, rax
0x1400527e8  call    HsmOsIsPassThroughModeEnabled
0x1400527ed  test    al, al
0x1400527ef  jz      loc_140052AEB
0x1400527f5  mov     rcx, [rsp+98h+arg_0]; Context
0x1400527fd  call    cs:__imp_FltReleaseContext
0x140052804  nop     dword ptr [rax+rax+00h]
0x140052809  xor     r14d, r14d
0x14005280c  mov     [rsp+98h+arg_0], r14
0x140052814  test    r14, r14
0x140052817  jnz     loc_1400528C5
0x14005281d  test    rsi, rsi
0x140052820  mov     [rsp+98h+Instance], rsi
0x140052825  mov     r9, r14
0x140052828  mov     rcx, rbp
0x14005282b  setnz   r8b
0x14005282f  test    rsi, rsi
0x140052832  setz    dl
0x140052835  call    HsmpTracePreCallbackEnter
0x14005283a  cmp     ebx, 4
0x14005283d  jz      loc_1400528CE
0x140052843  cmp     ebx, 14h
0x140052846  jnz     loc_1400528F0
0x14005284c  mov     ebx, 1; jumptable 0000000140052914 case 19
0x140052851  test    r14, r14
0x140052854  jnz     loc_140052AA9
0x14005285a  mov     rcx, r15; Context
0x14005285d  call    cs:__imp_FltReleaseContext
0x140052864  nop     dword ptr [rax+rax+00h]
0x140052869  test    r14, r14
0x14005286c  jnz     short loc_1400528B4
0x14005286e  mov     rdi, [rsp+98h+var_30]
0x140052873  cmp     ebx, 2
0x140052876  jz      short loc_140052897
0x140052878  mov     r8, [r12]
0x14005287c  test    rsi, rsi
0x14005287f  mov     rdx, rbp
0x140052882  mov     ecx, ebx
0x140052884  setnz   al
0x140052887  test    rsi, rsi
0x14005288a  mov     byte ptr [rsp+98h+Instance], al
0x14005288e  setz    r9b
0x140052892  call    HsmpTracePreCallbackExit
0x140052897  mov     rsi, [rsp+98h+arg_8]
0x14005289f  mov     eax, ebx
0x1400528a1  mov     r15, [rsp+98h+var_38]
0x1400528a6  add     rsp, 70h
0x1400528aa  pop     r14
0x1400528ac  pop     r13
0x1400528ae  pop     r12
0x1400528b0  pop     rbp
0x1400528b1  pop     rbx
0x1400528b2  retn
0x1400528b4  mov     rcx, r14; Context
0x1400528b7  call    cs:__imp_FltReleaseContext
0x1400528be  nop     dword ptr [rax+rax+00h]
0x1400528c3  jmp     short loc_14005286E
0x1400528c5  mov     rsi, [r14+10h]
0x1400528c9  jmp     loc_14005281D
0x1400528ce  mov     [rsp+98h+var_70], r12
0x1400528d3  mov     r9, rbp
0x1400528d6  mov     r8, r14
0x1400528d9  mov     [rsp+98h+Instance], r13
0x1400528de  mov     rdx, rsi
0x1400528e1  mov     rcx, r15
0x1400528e4  call    HsmFltPreSetBasicInformation
0x1400528e9  mov     ebx, eax
0x1400528eb  jmp     loc_14005285A
0x1400528f0  add     ebx, 0FFFFFFF6h; switch 63 cases
0x1400528f3  cmp     ebx, 3Eh
0x1400528f6  ja      short def_140052914; jumptable 0000000140052914 default case, cases 12,14-18,20-63,66-71
0x1400528f8  lea     rdx, cs:140000000h
0x1400528ff  movsxd  rax, ebx
0x140052902  movzx   eax, ds:(byte_140021FF2 - 140000000h)[rdx+rax]
0x14005290a  mov     ecx, ds:(jpt_140052914 - 140000000h)[rdx+rax*4]
0x140052911  add     rcx, rdx
0x140052914  jmp     rcx; switch jump
0x14005291a  mov     [rsp+98h+var_70], r12; jumptable 0000000140052914 cases 13,64
0x14005291f  mov     r9, rbp
0x140052922  mov     r8, r14
0x140052925  mov     [rsp+98h+Instance], r13; Instance
0x14005292a  mov     rdx, rsi
0x14005292d  mov     rcx, r15; Context
0x140052930  call    HsmFltPreSetDispositionInformation
0x140052935  mov     ebx, eax
0x140052937  jmp     loc_14005285A
0x14005293c  mov     ebx, 1; jumptable 0000000140052914 default case, cases 12,14-18,20-63,66-71
0x140052941  jmp     loc_14005285A
0x140052946  mov     [rsp+98h+var_70], r12; jumptable 0000000140052914 cases 10,65
0x14005294b  mov     r9, rbp
0x14005294e  mov     r8, r14
0x140052951  mov     [rsp+98h+Instance], r13; __int64
0x140052956  mov     rdx, rsi; PFLT_CONTEXT
0x140052959  mov     rcx, r15; Context
0x14005295c  call    HsmFltPreSetRenameInformation
0x140052961  mov     ebx, eax
0x140052963  jmp     loc_14005285A
0x140052968  mov     r15, [rsp+98h+var_38]
0x14005296d  mov     eax, 1
0x140052972  add     rsp, 70h
0x140052976  pop     r14
0x140052978  pop     r13
0x14005297a  pop     r12
0x14005297c  pop     rbp
0x14005297d  pop     rbx
0x14005297e  retn
0x140052980  mov     [rsp+98h+var_70], r12; jumptable 0000000140052914 cases 11,72
0x140052985  mov     r9, rbp
0x140052988  mov     r8, r14
0x14005298b  mov     [rsp+98h+Instance], r13; __int64
0x140052990  mov     rdx, rsi; PFLT_CONTEXT
0x140052993  mov     rcx, r15; Context
0x140052996  call    HsmFltPreSetLinkInformation
0x14005299b  mov     ebx, eax
0x14005299d  jmp     loc_14005285A
0x1400529a2  mov     rcx, [r13+20h]
0x1400529a6  mov     rdx, rbp; CallbackData
0x1400529a9  mov     rax, [rax+38h]
0x1400529ad  mov     [rsp+98h+arg_18], rcx
0x1400529b5  mov     rcx, rsi; Context
0x1400529b8  mov     rbx, [rax]
0x1400529bb  call    HsmpAcquireUserRequestRundownProtection
0x1400529c0  mov     ecx, eax
0x1400529c2  mov     r13d, eax
0x1400529c5  call    HsmDbgBreakOnStatus
0x1400529ca  test    r13d, r13d
0x1400529cd  js      short loc_140052A1B
0x1400529cf  mov     r8, [rbp+10h]
0x1400529d3  mov     r9d, 9
0x1400529d9  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFFh
0x1400529e2  mov     rdx, rsi
0x1400529e5  mov     [rsp+98h+var_70], rbx
0x1400529ea  mov     rcx, r14
0x1400529ed  mov     [rsp+98h+Instance], rbp
0x1400529f2  mov     r8, [r8+8]
0x1400529f6  call    HsmpRecallInitiateHydration
0x1400529fb  mov     ebx, eax
0x1400529fd  test    eax, eax
0x1400529ff  jz      loc_140052AF8
0x140052a05  cmp     eax, 2
0x140052a08  jz      loc_14005285A
0x140052a0e  mov     rcx, rsi; Context
0x140052a11  call    HsmpReleaseUserRequestRundownProtection
0x140052a16  jmp     loc_14005285A
0x140052a1b  mov     r10, cs:WPP_GLOBAL_Control
0x140052a22  lea     rax, WPP_GLOBAL_Control
0x140052a29  cmp     r10, rax
0x140052a2c  jz      short loc_140052A93
0x140052a2e  mov     ecx, [r10+2Ch]
0x140052a32  test    cl, 1
0x140052a35  jz      short loc_140052A93
0x140052a37  cmp     byte ptr [r10+29h], 2
0x140052a3c  jb      short loc_140052A93
0x140052a3e  mov     r8, [rsi+10h]
0x140052a42  mov     rcx, rsi
0x140052a45  call    HsmpGetStreamSize
0x140052a4a  mov     r8, [r8+20h]
0x140052a4e  mov     edx, 3Dh ; '='
0x140052a53  mov     rcx, [rsp+98h+arg_18]
0x140052a5b  mov     r9, r15
0x140052a5e  mov     [rsp+98h+var_48], r13d
0x140052a63  mov     [rsp+98h+var_50], rbp
0x140052a68  mov     [rsp+98h+var_58], r8
0x140052a6d  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140052a74  mov     [rsp+98h+var_60], rcx
0x140052a79  mov     rcx, [r10+18h]
0x140052a7d  mov     [rsp+98h+var_68], rax
0x140052a82  mov     eax, [rsi+1Ch]
0x140052a85  mov     dword ptr [rsp+98h+var_70], eax
0x140052a89  mov     [rsp+98h+Instance], rsi
0x140052a8e  call    WPP_SF_qqLiqiqd
0x140052a93  mov     [rbp+18h], r13d
0x140052a97  mov     ebx, 4
0x140052a9c  mov     qword ptr [rbp+20h], 0
0x140052aa4  jmp     loc_14005285A
0x140052aa9  mov     rax, [rbp+10h]
0x140052aad  cmp     byte ptr [rax+31h], 0
0x140052ab1  jnz     loc_14005285A
0x140052ab7  jmp     loc_1400529A2
0x140052abc  test    r14, r14
0x140052abf  jz      loc_14005281D
0x140052ac5  mov     rcx, r14; Context
0x140052ac8  call    cs:__imp_FltDeleteContext
0x140052acf  nop     dword ptr [rax+rax+00h]
0x140052ad4  jmp     loc_1400527F5
0x140052ad9  mov     eax, 1
0x140052ade  jmp     loc_1400528A6
0x140052ae3  mov     rcx, r14
0x140052ae6  jmp     loc_1400527FD
0x140052aeb  mov     r14, [rsp+98h+arg_0]
0x140052af3  jmp     loc_140052814
0x140052af8  mov     [r12], rsi
0x140052afc  jmp     loc_14005285A
```
