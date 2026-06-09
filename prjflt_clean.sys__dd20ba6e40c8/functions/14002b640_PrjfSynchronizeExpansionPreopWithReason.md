# PrjfSynchronizeExpansionPreopWithReason

- ea: `0x14002b640`
- end: `0x14002b882`
- name: `PrjfSynchronizeExpansionPreopWithReason`
- size: `578`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, int, int, int, __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140005920`
- `0x140005960`
- `0x14002ec30`
- `0x140040510`
- `0x1400412d0`

## callees

- `0x140002b50`
- `0x14000b1a0`
- `0x14000d128`
- `0x140021c5c`
- `0x140029088`
- `0x140029214`
- `0x14002b640`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x14002b7ee`
- `FLTMGR!FltReleaseContext` at `0x14002b802`
- `FLTMGR!FltReleaseContext` at `0x14002b816`
- `FLTMGR!FltReleaseContext` at `0x14002b7ee`
- `FLTMGR!FltReleaseContext` at `0x14002b802`
- `FLTMGR!FltReleaseContext` at `0x14002b816`

## pseudocode

```c
__int64 __fastcall PrjfSynchronizeExpansionPreopWithReason(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  unsigned int v12; // edi
  char ContextFileObject; // al
  PFLT_CONTEXT v14; // rbp
  _DWORD *v15; // r14
  int v16; // edx
  int SetStreamHandleContext; // ebx
  int v18; // r8d
  int v19; // esi
  PFLT_CONTEXT v21; // [rsp+60h] [rbp-58h] BYREF
  PFLT_CONTEXT Context[10]; // [rsp+68h] [rbp-50h] BYREF
  PFLT_CONTEXT v23; // [rsp+C8h] [rbp+10h] BYREF

  v23 = 0;
  v21 = 0;
  Context[0] = 0;
  *a8 = 0;
  v12 = 1;
  ContextFileObject = PrjfGetContextFileObject(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        *(PFILE_OBJECT *)(a2 + 32),
                        (__int64 *)&v23,
                        &v21);
  v14 = v23;
  v15 = v21;
  if ( !ContextFileObject || *((_DWORD *)v23 + 16) >= a3 )
    goto LABEL_19;
  SetStreamHandleContext = PrjfGetSetStreamHandleContext(
                             *(PFLT_INSTANCE *)(a2 + 24),
                             *(PFILE_OBJECT *)(a2 + 32),
                             v23,
                             v21,
                             0,
                             Context);
  if ( SetStreamHandleContext < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 4;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        522,
        v16,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        36,
        (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        83,
        SetStreamHandleContext);
    }
    goto LABEL_16;
  }
  if ( *v15 )
  {
    if ( (unsigned int)(*v15 - 1) < 2 )
      goto LABEL_17;
    SetStreamHandleContext = -1073741811;
    MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"Invalid stream context type");
    goto LABEL_16;
  }
  if ( !a4 )
    goto LABEL_17;
  v19 = a4 - 1;
  if ( v19 )
  {
    if ( v19 != 1 )
    {
      SetStreamHandleContext = -1073741811;
      MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"Invalid sync type");
LABEL_16:
      CallbackData->IoStatus.Status = SetStreamHandleContext;
      v12 = 4;
      CallbackData->IoStatus.Information = 0;
      goto LABEL_17;
    }
    SetStreamHandleContext = PrjfExpandAndWait(
                               CallbackData,
                               *(struct _FLT_INSTANCE **)(a2 + 24),
                               *(_QWORD *)(a2 + 32),
                               (__int64)v14,
                               a3,
                               1,
                               a7,
                               0);
LABEL_15:
    if ( SetStreamHandleContext >= 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  if ( (CallbackData->Flags & 2) != 0 )
  {
    v12 = 3;
  }
  else
  {
    SetStreamHandleContext = PrjfExpandAndPend(CallbackData, a3, 1, a7);
    if ( SetStreamHandleContext != 259 )
      goto LABEL_15;
    v12 = 2;
  }
LABEL_17:
  if ( Context[0] )
    FltReleaseContext(Context[0]);
LABEL_19:
  if ( v15 )
    FltReleaseContext(v15);
  if ( v14 )
    FltReleaseContext(v14);
  return v12;
}

```

## disassembly

```asm
0x14002b640  mov     r11, rsp
0x14002b643  push    rbx
0x14002b644  push    rbp
0x14002b645  push    rsi
0x14002b646  push    rdi
0x14002b647  push    r12
0x14002b649  push    r13
0x14002b64b  push    r14
0x14002b64d  push    r15
0x14002b64f  sub     rsp, 78h
0x14002b653  mov     rax, [rsp+0B8h+arg_38]
0x14002b65b  mov     r13, rdx
0x14002b65e  mov     esi, r9d
0x14002b661  mov     qword ptr [r11+10h], 0
0x14002b669  mov     r12d, r8d
0x14002b66c  mov     qword ptr [r11-58h], 0
0x14002b674  mov     r15, rcx
0x14002b677  mov     qword ptr [r11-50h], 0
0x14002b67f  mov     qword ptr [rax], 0
0x14002b686  lea     r9, [r11-58h]
0x14002b68a  mov     rdx, [rdx+20h]; FileObject
0x14002b68e  lea     r8, [r11+10h]
0x14002b692  mov     rcx, [r13+18h]; Instance
0x14002b696  mov     edi, 1
0x14002b69b  call    PrjfGetContextFileObject
0x14002b6a0  mov     rbp, [rsp+0B8h+arg_8]
0x14002b6a8  mov     r14, [rsp+0B8h+var_58]
0x14002b6ad  test    al, al
0x14002b6af  jz      loc_14002B7FA
0x14002b6b5  cmp     [rbp+40h], r12d
0x14002b6b9  jge     loc_14002B7FA
0x14002b6bf  mov     rdx, [r13+20h]; FileObject
0x14002b6c3  lea     rax, [rsp+0B8h+Context]
0x14002b6c8  mov     rcx, [r13+18h]; Instance
0x14002b6cc  mov     r9, r14
0x14002b6cf  mov     [rsp+0B8h+var_90], rax; __int64
0x14002b6d4  mov     r8, rbp; Context
0x14002b6d7  mov     [rsp+0B8h+var_98], 0; char
0x14002b6dc  call    PrjfGetSetStreamHandleContext
0x14002b6e1  mov     ebx, eax
0x14002b6e3  test    eax, eax
0x14002b6e5  jns     short loc_14002B75C
0x14002b6e7  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002b6ed  lea     rax, WPP_RECORDER_INITIALIZED
0x14002b6f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002b6fb  setnz   r8b
0x14002b6ff  and     dl, 4
0x14002b702  jnz     short loc_14002B70D
0x14002b704  test    r8b, r8b
0x14002b707  jz      loc_14002B7D3
0x14002b70d  mov     r9, cs:WPP_GLOBAL_Control
0x14002b714  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002b71b  mov     [rsp+0B8h+var_68], ebx
0x14002b71f  mov     ecx, 20Ah
0x14002b724  mov     [rsp+0B8h+var_70], 953h
0x14002b72c  mov     [rsp+0B8h+var_78], rax
0x14002b731  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002b738  mov     r9, [r9+40h]
0x14002b73c  mov     qword ptr [rsp+0B8h+var_80], rax
0x14002b741  mov     word ptr [rsp+0B8h+var_88], 24h ; '$'
0x14002b748  mov     dword ptr [rsp+0B8h+var_90], 0Ah
0x14002b750  mov     [rsp+0B8h+var_98], 2
0x14002b755  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002b75a  jmp     short loc_14002B7D3
0x14002b75c  mov     ecx, [r14]
0x14002b75f  test    ecx, ecx
0x14002b761  jz      short loc_14002B77E
0x14002b763  sub     ecx, edi
0x14002b765  jz      short loc_14002B7E4
0x14002b767  cmp     ecx, edi
0x14002b769  jz      short loc_14002B7E4
0x14002b76b  mov     ebx, 0C000000Dh
0x14002b770  lea     rcx, aInvalidStreamC; "Invalid stream context type"
0x14002b777  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002b77c  jmp     short loc_14002B7D3
0x14002b77e  test    esi, esi
0x14002b780  jz      short loc_14002B7E4
0x14002b782  sub     esi, edi
0x14002b784  jz      loc_14002B836
0x14002b78a  cmp     esi, edi
0x14002b78c  jz      short loc_14002B7A1
0x14002b78e  mov     ebx, 0C000000Dh
0x14002b793  lea     rcx, aInvalidSyncTyp; "Invalid sync type"
0x14002b79a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002b79f  jmp     short loc_14002B7D3
0x14002b7a1  mov     eax, [rsp+0B8h+arg_30]
0x14002b7a8  mov     r9, rbp
0x14002b7ab  mov     r8, [r13+20h]
0x14002b7af  mov     rcx, r15; CallbackData
0x14002b7b2  mov     rdx, [r13+18h]
0x14002b7b6  mov     [rsp+0B8h+var_80], 0; char
0x14002b7bb  mov     [rsp+0B8h+var_88], eax; int
0x14002b7bf  mov     dword ptr [rsp+0B8h+var_90], edi; int
0x14002b7c3  mov     dword ptr [rsp+0B8h+var_98], r12d; int
0x14002b7c8  call    PrjfExpandAndWait
0x14002b7cd  mov     ebx, eax
0x14002b7cf  test    ebx, ebx
0x14002b7d1  jns     short loc_14002B7E4
0x14002b7d3  mov     [r15+18h], ebx
0x14002b7d7  mov     edi, 4
0x14002b7dc  mov     qword ptr [r15+20h], 0
0x14002b7e4  mov     rcx, [rsp+0B8h+Context]; Context
0x14002b7e9  test    rcx, rcx
0x14002b7ec  jz      short loc_14002B7FA
0x14002b7ee  call    cs:__imp_FltReleaseContext
0x14002b7f5  nop     dword ptr [rax+rax+00h]
0x14002b7fa  test    r14, r14
0x14002b7fd  jz      short loc_14002B80E
0x14002b7ff  mov     rcx, r14; Context
0x14002b802  call    cs:__imp_FltReleaseContext
0x14002b809  nop     dword ptr [rax+rax+00h]
0x14002b80e  test    rbp, rbp
0x14002b811  jz      short loc_14002B822
0x14002b813  mov     rcx, rbp; Context
0x14002b816  call    cs:__imp_FltReleaseContext
0x14002b81d  nop     dword ptr [rax+rax+00h]
0x14002b822  mov     eax, edi
0x14002b824  add     rsp, 78h
0x14002b828  pop     r15
0x14002b82a  pop     r14
0x14002b82c  pop     r13
0x14002b82e  pop     r12
0x14002b830  pop     rdi
0x14002b831  pop     rsi
0x14002b832  pop     rbp
0x14002b833  pop     rbx
0x14002b834  retn
0x14002b836  mov     eax, [r15]
0x14002b839  test    al, 2
0x14002b83b  jz      short loc_14002B844
0x14002b83d  mov     edi, 3
0x14002b842  jmp     short loc_14002B7E4
0x14002b844  mov     eax, [rsp+0B8h+arg_30]
0x14002b84b  mov     r9, rbp
0x14002b84e  mov     r8, [r13+20h]
0x14002b852  mov     rcx, r15; CallbackData
0x14002b855  mov     rdx, [r13+18h]
0x14002b859  mov     [rsp+0B8h+var_88], eax; int
0x14002b85d  mov     dword ptr [rsp+0B8h+var_90], edi; int
0x14002b861  mov     dword ptr [rsp+0B8h+var_98], r12d; int
0x14002b866  call    PrjfExpandAndPend
0x14002b86b  mov     ebx, eax
0x14002b86d  cmp     eax, 103h
0x14002b872  jnz     loc_14002B7CF
0x14002b878  mov     edi, 2
0x14002b87d  jmp     loc_14002B7E4
```
