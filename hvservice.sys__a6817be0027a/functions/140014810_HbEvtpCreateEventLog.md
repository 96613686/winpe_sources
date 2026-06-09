# HbEvtpCreateEventLog

- ea: `0x140014810`
- end: `0x140014be5`
- name: `HbEvtpCreateEventLog`
- size: `981`
- prototype: `__int64 __fastcall(char *DeferredContext, int, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140010914`
- `0x1400115a0`

## callees

- `0x140001230`
- `0x140001600`
- `0x1400020f8`
- `0x140002ae0`
- `0x140010700`
- `0x140010a78`
- `0x140014810`

## import_xrefs

- `ntoskrnl!HvlQueryActiveHypervisorProcessorCount` at `0x140014a12`
- `ntoskrnl!HvlQueryActiveHypervisorProcessorCount` at `0x140014a12`
- `ntoskrnl!ExAllocatePool2` at `0x140014995`
- `ntoskrnl!ExAllocatePool2` at `0x1400149bf`
- `ntoskrnl!ExAllocatePool2` at `0x140014a44`
- `ntoskrnl!ExAllocatePool2` at `0x140014995`
- `ntoskrnl!ExAllocatePool2` at `0x1400149bf`
- `ntoskrnl!ExAllocatePool2` at `0x140014a44`
- `ntoskrnl!KeReleaseMutex` at `0x140014955`
- `ntoskrnl!KeReleaseMutex` at `0x140014955`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014869`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014869`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400149e8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400149e8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400148d0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400148d0`
- `ntoskrnl!InitializeSListHead` at `0x1400149ff`
- `ntoskrnl!InitializeSListHead` at `0x1400149ff`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001492a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140014a9d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001492a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140014a9d`
- `winhvr!WinHvInitializeEventLogBufferGroup` at `0x140014b3f`
- `winhvr!WinHvInitializeEventLogBufferGroup` at `0x140014b3f`

## string_xrefs

- `0x14001488e`: `HbEvtpCreateEventLog`
- `0x140014a75`: `HbEvtpCreateEventLog`
- `0x140014af6`: `HbEvtpCreateEventLog`
- `0x140014b65`: `HbEvtpCreateEventLog`

## pseudocode

```c
__int64 __fastcall HbEvtpCreateEventLog(char *DeferredContext, int a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rbp
  __int64 v5; // rbx
  char v9; // r13
  int LogConfiguration; // eax
  __int64 v11; // rdi
  __int64 Pool2; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  int v17; // ecx
  int ActiveHypervisorProcessorCount; // [rsp+50h] [rbp-78h] BYREF
  __int64 v19; // [rsp+58h] [rbp-70h] BYREF
  PRKMUTEX Mutex; // [rsp+60h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-60h] BYREF

  v4 = a2;
  v5 = 0;
  Mutex = (PRKMUTEX)(DeferredContext + 208);
  v19 = 0;
  ActiveHypervisorProcessorCount = 0;
  UserData = 0;
  KeWaitForSingleObject(DeferredContext + 208, Executive, 0, 0, 0);
  if ( DeferredContext[264] != 1 )
  {
    if ( !ExAcquireRundownProtection(&stru_1400092E8 + 18 * v4) )
    {
      ActiveHypervisorProcessorCount = -1073741661;
      goto LABEL_9;
    }
    v9 = 0;
    LogConfiguration = HbEvtpGetLogConfiguration((unsigned int)v4, &v19);
    v11 = v19;
    ActiveHypervisorProcessorCount = LogConfiguration;
    if ( LogConfiguration >= 0 )
    {
      if ( *(_DWORD *)(v19 + 8) )
      {
        ActiveHypervisorProcessorCount = -1073741811;
LABEL_8:
        ExReleaseRundownProtection(&stru_1400092E8 + 18 * v4);
        goto LABEL_9;
      }
      *(_DWORD *)(v19 + 48) = a3;
      Pool2 = ExAllocatePool2(64, (unsigned int)(112 * a4[2]), 1967284808);
      *(_QWORD *)(v11 + 32) = Pool2;
      if ( !Pool2
        || (v14 = ExAllocatePool2(64, (unsigned int)(8 * a4[2]), 1967284808), (*(_QWORD *)(v11 + 40) = v14) == 0) )
      {
        ActiveHypervisorProcessorCount = -1073741670;
        goto LABEL_8;
      }
      if ( a4[2] )
      {
        do
        {
          ExInitializeRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(v11 + 40) + 8 * v5));
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (unsigned int)v5 < a4[2] );
      }
      InitializeSListHead((PSLIST_HEADER)(v11 + 112));
      ActiveHypervisorProcessorCount = HvlQueryActiveHypervisorProcessorCount(&HbEvtpActiveProcessorCount);
      if ( ActiveHypervisorProcessorCount >= 0 )
      {
        if ( (_DWORD)v4 != 1
          || (v15 = ExAllocatePool2(256, 4LL * (unsigned int)HbEvtpActiveProcessorCount, 1967284808),
              (*(_QWORD *)(v11 + 136) = v15) != 0) )
        {
          if ( ActiveHypervisorProcessorCount < 0 )
            goto LABEL_19;
          HbpTraceEvent(
            2,
            "HbEvtpCreateEventLog",
            3220,
            "Initializing event log buffer group: type %d, mode %d, count %d, size %d, threshold %d",
            v4,
            a3,
            a4[2],
            a4[1],
            a4[3]);
          v16 = WinHvInitializeEventLogBufferGroup(
                  (unsigned int)v4,
                  a3,
                  (unsigned int)a4[2],
                  (unsigned int)a4[1],
                  a4[3],
                  a4[4]);
          v17 = a4[2];
          ActiveHypervisorProcessorCount = v16;
          if ( v16 >= 0 )
          {
            *(_DWORD *)(v11 + 8) = v17;
            LODWORD(v5) = 0;
            v9 = 1;
            *(_DWORD *)v11 = *a4;
            *(_DWORD *)(v11 + 4) = a4[1];
            if ( *(_DWORD *)(v11 + 8) )
            {
              do
              {
                ActiveHypervisorProcessorCount = HbEvtpCreateEventLogBuffer(DeferredContext);
                if ( ActiveHypervisorProcessorCount < 0 )
                  break;
                LODWORD(v5) = v5 + 1;
              }
              while ( (unsigned int)v5 < *(_DWORD *)(v11 + 8) );
            }
          }
          else
          {
            HbpTraceEvent(
              0,
              "HbEvtpCreateEventLog",
              3237,
              "WinHvInitializeEventLogBufferGroup failed: type %d, mode %d, count %d, status 0x%x",
              v4,
              a3,
              v17,
              v16);
          }
        }
        else
        {
          ActiveHypervisorProcessorCount = -1073741670;
          HbpTraceEvent(0, "HbEvtpCreateEventLog", 3204, "Out of memory. Can't allocate LastLpSequenceNumber.");
        }
      }
    }
    if ( ActiveHypervisorProcessorCount >= 0 )
      goto LABEL_8;
LABEL_19:
    if ( v9 )
    {
      *(_DWORD *)(v11 + 8) = v5;
      ExReleaseRundownProtection(&stru_1400092E8 + 18 * v4);
      HbEvtpDeleteEventLog(DeferredContext, (unsigned int)v4);
      *(_QWORD *)&UserData.Size = 4;
      UserData.Ptr = (ULONGLONG)&ActiveHypervisorProcessorCount;
      HbEvtpWriteEventLog(&HV_EVENTLOG_CREATION_FAILED, 1u, &UserData);
      goto LABEL_9;
    }
    goto LABEL_8;
  }
  HbpTraceEvent(2, "HbEvtpCreateEventLog", 3122, "Event log creation is disabled");
  ActiveHypervisorProcessorCount = -1073741738;
LABEL_9:
  KeReleaseMutex(Mutex, 0);
  return (unsigned int)ActiveHypervisorProcessorCount;
}

```

## disassembly

```asm
0x140014810  push    rbx
0x140014812  push    rbp
0x140014813  push    rsi
0x140014814  push    r12
0x140014816  push    r14
0x140014818  sub     rsp, 0A0h
0x14001481f  mov     rax, cs:__security_cookie
0x140014826  xor     rax, rsp
0x140014829  mov     [rsp+0C8h+var_50], rax
0x14001482e  lea     rax, [rcx+0D0h]
0x140014835  movsxd  rbp, edx
0x140014838  xor     ebx, ebx
0x14001483a  mov     [rsp+0C8h+Mutex], rax
0x14001483f  mov     rsi, r9
0x140014842  mov     [rsp+0C8h+var_70], rbx
0x140014847  mov     r12d, r8d
0x14001484a  mov     [rsp+0C8h+var_78], ebx
0x14001484e  mov     r14, rcx
0x140014851  mov     [rsp+0C8h+Timeout], rbx; Timeout
0x140014856  xorps   xmm0, xmm0
0x140014859  mov     rcx, rax; Object
0x14001485c  xor     r9d, r9d; Alertable
0x14001485f  xor     r8d, r8d; WaitMode
0x140014862  xor     edx, edx; WaitReason
0x140014864  movups  xmmword ptr [rsp+0C8h+UserData.Ptr], xmm0
0x140014869  call    cs:__imp_KeWaitForSingleObject
0x140014870  nop     dword ptr [rax+rax+00h]
0x140014875  movzx   eax, byte ptr [r14+108h]
0x14001487d  cmp     al, 1
0x14001487f  jnz     short loc_1400148AC
0x140014881  lea     r9, aEventLogCreati; "Event log creation is disabled"
0x140014888  mov     r8d, 0C32h
0x14001488e  lea     rdx, aHbevtpcreateev_0; "HbEvtpCreateEventLog"
0x140014895  mov     ecx, 2
0x14001489a  call    HbpTraceEvent
0x14001489f  mov     [rsp+0C8h+var_78], 0C0000056h
0x1400148a7  jmp     loc_14001494E
0x1400148ac  mov     [rsp+0C8h+var_40], r15
0x1400148b4  lea     rax, stru_1400092E8
0x1400148bb  lea     r15, ds:0[rbp*8]
0x1400148c3  add     r15, rbp
0x1400148c6  shl     r15, 4
0x1400148ca  add     r15, rax
0x1400148cd  mov     rcx, r15; RunRef
0x1400148d0  call    cs:__imp_ExAcquireRundownProtection
0x1400148d7  nop     dword ptr [rax+rax+00h]
0x1400148dc  test    al, al
0x1400148de  jnz     short loc_1400148EA
0x1400148e0  mov     [rsp+0C8h+var_78], 0C00000A3h
0x1400148e8  jmp     short loc_140014946
0x1400148ea  mov     [rsp+0C8h+var_30], rdi
0x1400148f2  lea     rdx, [rsp+0C8h+var_70]
0x1400148f7  mov     [rsp+0C8h+var_38], r13
0x1400148ff  mov     ecx, ebp
0x140014901  xor     r13b, r13b
0x140014904  call    HbEvtpGetLogConfiguration
0x140014909  mov     rdi, [rsp+0C8h+var_70]
0x14001490e  mov     [rsp+0C8h+var_78], eax
0x140014912  test    eax, eax
0x140014914  js      loc_140014A83
0x14001491a  cmp     [rdi+8], ebx
0x14001491d  jz      short loc_140014982
0x14001491f  mov     [rsp+0C8h+var_78], 0C000000Dh
0x140014927  mov     rcx, r15; RunRef
0x14001492a  call    cs:__imp_ExReleaseRundownProtection
0x140014931  nop     dword ptr [rax+rax+00h]
0x140014936  mov     r13, [rsp+0C8h+var_38]
0x14001493e  mov     rdi, [rsp+0C8h+var_30]
0x140014946  mov     r15, [rsp+0C8h+var_40]
0x14001494e  mov     rcx, [rsp+0C8h+Mutex]; Mutex
0x140014953  xor     edx, edx; Wait
0x140014955  call    cs:__imp_KeReleaseMutex
0x14001495c  nop     dword ptr [rax+rax+00h]
0x140014961  mov     eax, [rsp+0C8h+var_78]
0x140014965  mov     rcx, [rsp+0C8h+var_50]
0x14001496a  xor     rcx, rsp; StackCookie
0x14001496d  call    __security_check_cookie
0x140014972  add     rsp, 0A0h
0x140014979  pop     r14
0x14001497b  pop     r12
0x14001497d  pop     rsi
0x14001497e  pop     rbp
0x14001497f  pop     rbx
0x140014980  retn
0x140014982  mov     [rdi+30h], r12d
0x140014986  mov     ecx, 40h ; '@'
0x14001498b  imul    edx, [rsi+8], 70h ; 'p'
0x14001498f  mov     r8d, 75426248h
0x140014995  call    cs:__imp_ExAllocatePool2
0x14001499c  nop     dword ptr [rax+rax+00h]
0x1400149a1  mov     [rdi+20h], rax
0x1400149a5  test    rax, rax
0x1400149a8  jz      loc_140014BD8
0x1400149ae  mov     edx, [rsi+8]
0x1400149b1  mov     ecx, 40h ; '@'
0x1400149b6  shl     edx, 3
0x1400149b9  mov     r8d, 75426248h
0x1400149bf  call    cs:__imp_ExAllocatePool2
0x1400149c6  nop     dword ptr [rax+rax+00h]
0x1400149cb  mov     [rdi+28h], rax
0x1400149cf  test    rax, rax
0x1400149d2  jz      loc_140014BD8
0x1400149d8  cmp     [rsi+8], ebx
0x1400149db  jbe     short loc_1400149FB
0x1400149dd  nop     dword ptr [rax]
0x1400149e0  mov     rax, [rdi+28h]
0x1400149e4  lea     rcx, [rax+rbx*8]; RunRef
0x1400149e8  call    cs:__imp_ExInitializeRundownProtection
0x1400149ef  nop     dword ptr [rax+rax+00h]
0x1400149f4  inc     ebx
0x1400149f6  cmp     ebx, [rsi+8]
0x1400149f9  jb      short loc_1400149E0
0x1400149fb  lea     rcx, [rdi+70h]; SListHead
0x1400149ff  call    cs:__imp_InitializeSListHead
0x140014a06  nop     dword ptr [rax+rax+00h]
0x140014a0b  lea     rcx, HbEvtpActiveProcessorCount
0x140014a12  call    cs:__imp_HvlQueryActiveHypervisorProcessorCount
0x140014a19  nop     dword ptr [rax+rax+00h]
0x140014a1e  mov     [rsp+0C8h+var_78], eax
0x140014a22  test    eax, eax
0x140014a24  js      short loc_140014A83
0x140014a26  cmp     ebp, 1
0x140014a29  jnz     loc_140014AE1
0x140014a2f  mov     edx, cs:HbEvtpActiveProcessorCount
0x140014a35  mov     ecx, 100h
0x140014a3a  shl     rdx, 2
0x140014a3e  mov     r8d, 75426248h
0x140014a44  call    cs:__imp_ExAllocatePool2
0x140014a4b  nop     dword ptr [rax+rax+00h]
0x140014a50  mov     [rdi+88h], rax
0x140014a57  test    rax, rax
0x140014a5a  jnz     loc_140014AE1
0x140014a60  mov     [rsp+0C8h+var_78], 0C000009Ah
0x140014a68  lea     r9, aOutOfMemoryCan_0; "Out of memory. Can't allocate LastLpSeq"...
0x140014a6f  mov     r8d, 0C84h
0x140014a75  lea     rdx, aHbevtpcreateev_0; "HbEvtpCreateEventLog"
0x140014a7c  xor     ecx, ecx
0x140014a7e  call    HbpTraceEvent
0x140014a83  cmp     [rsp+0C8h+var_78], 0
0x140014a88  jge     loc_140014927
0x140014a8e  test    r13b, r13b
0x140014a91  jz      loc_140014927
0x140014a97  mov     rcx, r15; RunRef
0x140014a9a  mov     [rdi+8], ebx
0x140014a9d  call    cs:__imp_ExReleaseRundownProtection
0x140014aa4  nop     dword ptr [rax+rax+00h]
0x140014aa9  mov     edx, ebp
0x140014aab  mov     rcx, r14
0x140014aae  call    HbEvtpDeleteEventLog
0x140014ab3  lea     rax, [rsp+0C8h+var_78]
0x140014ab8  mov     qword ptr [rsp+0C8h+UserData.Size], 4
0x140014ac1  lea     r8, [rsp+0C8h+UserData]; UserData
0x140014ac6  mov     [rsp+0C8h+UserData.Ptr], rax
0x140014acb  mov     edx, 1; UserDataCount
0x140014ad0  lea     rcx, HV_EVENTLOG_CREATION_FAILED; EventDescriptor
0x140014ad7  call    HbEvtpWriteEventLog
0x140014adc  jmp     loc_140014936
0x140014ae1  cmp     [rsp+0C8h+var_78], 0
0x140014ae6  jl      short loc_140014A8E
0x140014ae8  mov     eax, [rsi+0Ch]
0x140014aeb  lea     r9, aInitializingEv; "Initializing event log buffer group: ty"...
0x140014af2  mov     [rsp+0C8h+var_88], eax
0x140014af6  lea     rdx, aHbevtpcreateev_0; "HbEvtpCreateEventLog"
0x140014afd  mov     eax, [rsi+4]
0x140014b00  mov     r8d, 0C94h
0x140014b06  mov     [rsp+0C8h+var_90], eax
0x140014b0a  mov     ecx, 2
0x140014b0f  mov     eax, [rsi+8]
0x140014b12  mov     [rsp+0C8h+var_98], eax
0x140014b16  mov     [rsp+0C8h+var_A0], r12d
0x140014b1b  mov     dword ptr [rsp+0C8h+Timeout], ebp
0x140014b1f  call    HbpTraceEvent
0x140014b24  mov     eax, [rsi+10h]
0x140014b27  mov     edx, r12d
0x140014b2a  mov     r9d, [rsi+4]
0x140014b2e  mov     ecx, ebp
0x140014b30  mov     r8d, [rsi+8]
0x140014b34  mov     [rsp+0C8h+var_A0], eax
0x140014b38  mov     eax, [rsi+0Ch]
0x140014b3b  mov     dword ptr [rsp+0C8h+Timeout], eax
0x140014b3f  call    cs:__imp_WinHvInitializeEventLogBufferGroup
0x140014b46  nop     dword ptr [rax+rax+00h]
0x140014b4b  mov     ecx, [rsi+8]
0x140014b4e  mov     [rsp+0C8h+var_78], eax
0x140014b52  test    eax, eax
0x140014b54  jns     short loc_140014B87
0x140014b56  mov     [rsp+0C8h+var_90], eax
0x140014b5a  lea     r9, aWinhvinitializ; "WinHvInitializeEventLogBufferGroup fail"...
0x140014b61  mov     [rsp+0C8h+var_98], ecx
0x140014b65  lea     rdx, aHbevtpcreateev_0; "HbEvtpCreateEventLog"
0x140014b6c  mov     [rsp+0C8h+var_A0], r12d
0x140014b71  xor     ecx, ecx
0x140014b73  mov     r8d, 0CA5h
0x140014b79  mov     dword ptr [rsp+0C8h+Timeout], ebp
0x140014b7d  call    HbpTraceEvent
0x140014b82  jmp     loc_140014A83
0x140014b87  mov     [rdi+8], ecx
0x140014b8a  xor     ebx, ebx
0x140014b8c  mov     eax, [rsi]
0x140014b8e  mov     r13b, 1
0x140014b91  mov     [rdi], eax
0x140014b93  mov     eax, [rsi+4]
0x140014b96  mov     [rdi+4], eax
0x140014b99  cmp     [rdi+8], ebx
0x140014b9c  jbe     loc_140014A83
0x140014ba2  nop     dword ptr [rax+00h]
0x140014ba6  nop     word ptr [rax+rax+00000000h]
0x140014bb0  mov     r9, rdi
0x140014bb3  mov     r8d, ebx
0x140014bb6  mov     edx, ebp
0x140014bb8  mov     rcx, r14; DeferredContext
0x140014bbb  call    HbEvtpCreateEventLogBuffer
0x140014bc0  mov     [rsp+0C8h+var_78], eax
0x140014bc4  test    eax, eax
0x140014bc6  js      loc_140014A83
0x140014bcc  inc     ebx
0x140014bce  cmp     ebx, [rdi+8]
0x140014bd1  jb      short loc_140014BB0
0x140014bd3  jmp     loc_140014A83
0x140014bd8  mov     [rsp+0C8h+var_78], 0C000009Ah
0x140014be0  jmp     loc_140014927
```
