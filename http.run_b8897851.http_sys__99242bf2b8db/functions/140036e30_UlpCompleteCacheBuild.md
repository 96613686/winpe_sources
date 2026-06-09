# UlpCompleteCacheBuild

- ea: `0x140036e30`
- end: `0x140037075`
- name: `UlpCompleteCacheBuild`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x140032fd0`
- `0x140036e30`
- `0x140037080`
- `0x14005e050`
- `0x14013dc78`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140036e97`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036e97`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036f9e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036f9e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140036f2d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140036f2d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140036ebe`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140036ebe`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140036efb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140036efb`
- `ntoskrnl!KeSetEvent` at `0x140036fbc`
- `ntoskrnl!KeSetEvent` at `0x140036fbc`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140036f56`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140036f56`

## pseudocode

```c
PSLIST_ENTRY __fastcall UlpCompleteCacheBuild(__int64 a1, int a2, __int64 a3)
{
  struct _SLIST_ENTRY *v6; // rdi
  __int64 CurrentServerSilo; // rsi
  char v8; // bl
  __int64 v9; // rax
  __int64 v10; // rbp
  PSLIST_ENTRY result; // rax
  ULONG v12; // ebp
  __int64 v13; // rbx

  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qdP(1033, 182, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, a1, a2, a3);
  *(_QWORD *)(a1 + 120) = a3;
  v6 = (struct _SLIST_ENTRY *)(a1 + 64);
  *(_DWORD *)(a1 + 112) = a2;
  if ( *(_QWORD *)(a1 + 64) || *(_QWORD *)(a1 + 80) || *(_QWORD *)(a1 + 96) )
    UlBugCheckEx(1u, a1 + 64, (ULONG_PTR)"minio\\http\\sys\\sendresponse.c", 0x2CD6u);
  CurrentServerSilo = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 136LL) + 64LL);
  if ( KeGetCurrentIrql() )
  {
    v12 = 0;
    if ( (unsigned int)dword_1401A3F48 > 1 )
    {
      v12 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F60 )
        v12 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( CurrentServerSilo == -1 )
      CurrentServerSilo = PsGetCurrentServerSilo();
    *(_QWORD *)(a1 + 96) = CurrentServerSilo;
    UxPodReferenceSilo(CurrentServerSilo, 1230466133, 13);
    *(_BYTE *)(a1 + 88) = 1;
    v13 = *(_QWORD *)(qword_1401A3F50 + 8LL * v12);
    v6[1].Next = (struct _SLIST_ENTRY *)UlpCompleteCacheBuildWorker;
    result = ExpInterlockedPushEntrySList((PSLIST_HEADER)(v13 + 16), v6);
    if ( !result )
    {
      KeSetEvent((PRKEVENT)(v13 + 32), 0, 0);
      result = (PSLIST_ENTRY)UlpActivateThreadPoolQueue((PVOID)v13);
    }
  }
  else
  {
    v8 = 0;
    if ( CurrentServerSilo == -1 )
    {
      v10 = 0;
    }
    else
    {
      v9 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v10 = v9;
      v8 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v9, CurrentServerSilo);
    }
    result = (PSLIST_ENTRY)UlpCompleteCacheBuildWorker(v6);
    if ( v8 )
    {
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v10);
      result = (PSLIST_ENTRY)PsDetachSiloFromCurrentThread(v10);
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    return (PSLIST_ENTRY)WPP_SF_(1033, 183, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140036e30  push    rbx
0x140036e32  push    rbp
0x140036e33  push    rsi
0x140036e34  push    rdi
0x140036e35  sub     rsp, 48h
0x140036e39  mov     rdi, r8
0x140036e3c  mov     esi, edx
0x140036e3e  mov     rbx, rcx
0x140036e41  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140036e48  jnz     loc_140036FDF
0x140036e4e  mov     [rbx+78h], rdi
0x140036e52  lea     rdi, [rbx+40h]
0x140036e56  mov     [rbx+70h], esi
0x140036e59  cmp     qword ptr [rdi], 0
0x140036e5d  jnz     short loc_140036E6D
0x140036e5f  cmp     qword ptr [rdi+10h], 0
0x140036e64  jnz     short loc_140036E6D
0x140036e66  cmp     qword ptr [rdi+20h], 0
0x140036e6b  jz      short loc_140036E88
0x140036e6d  mov     r9d, 2CD6h; BugCheckParameter4
0x140036e73  lea     r8, aMinioHttpSysSe; "minio\\http\\sys\\sendresponse.c"
0x140036e7a  mov     rdx, rdi; BugCheckParameter2
0x140036e7d  mov     ecx, 1; BugCheckParameter1
0x140036e82  call    UlBugCheckEx
0x140036e88  mov     rax, [rbx+18h]
0x140036e8c  mov     rcx, [rax+88h]
0x140036e93  mov     rsi, [rcx+40h]
0x140036e97  call    cs:__imp_KeGetCurrentIrql
0x140036e9e  nop     dword ptr [rax+rax+00h]
0x140036ea3  test    al, al
0x140036ea5  jnz     short loc_140036F1E
0x140036ea7  xor     bl, bl
0x140036ea9  xorps   xmm0, xmm0
0x140036eac  movups  [rsp+68h+var_38], xmm0
0x140036eb1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140036eb5  jz      loc_140036FD5
0x140036ebb  mov     rcx, rsi
0x140036ebe  call    cs:__imp_PsAttachSiloToCurrentThread
0x140036ec5  nop     dword ptr [rax+rax+00h]
0x140036eca  mov     rbp, rax
0x140036ecd  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140036ed4  mov     ebx, 1
0x140036ed9  jnz     loc_140037006
0x140036edf  mov     rcx, rdi
0x140036ee2  call    UlpCompleteCacheBuildWorker
0x140036ee7  test    bl, bl
0x140036ee9  jz      short loc_140036F07
0x140036eeb  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140036ef2  jnz     loc_140037029
0x140036ef8  mov     rcx, rbp
0x140036efb  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140036f02  nop     dword ptr [rax+rax+00h]
0x140036f07  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140036f0e  jnz     loc_14003705A
0x140036f14  add     rsp, 48h
0x140036f18  pop     rdi
0x140036f19  pop     rsi
0x140036f1a  pop     rbp
0x140036f1b  pop     rbx
0x140036f1c  retn
0x140036f1e  xor     ebp, ebp
0x140036f20  lea     ebx, [rbp+1]
0x140036f23  cmp     cs:dword_1401A3F48, ebx
0x140036f29  jbe     short loc_140036F50
0x140036f2b  xor     ecx, ecx; ProcNumber
0x140036f2d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140036f34  nop     dword ptr [rax+rax+00h]
0x140036f39  xor     edx, edx
0x140036f3b  div     cs:UxNumberOfProcessors
0x140036f41  cmp     cs:byte_1401A3F60, 0
0x140036f48  mov     ebp, edx
0x140036f4a  jnz     loc_140037047
0x140036f50  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140036f54  jnz     short loc_140036F65
0x140036f56  call    cs:__imp_PsGetCurrentServerSilo
0x140036f5d  nop     dword ptr [rax+rax+00h]
0x140036f62  mov     rsi, rax
0x140036f65  mov     edx, 49576C55h
0x140036f6a  mov     [rdi+20h], rsi
0x140036f6e  mov     r8d, 0Dh
0x140036f74  mov     rcx, rsi
0x140036f77  call    UxPodReferenceSilo
0x140036f7c  mov     [rdi+18h], bl
0x140036f7f  mov     rdx, rdi; ListEntry
0x140036f82  mov     rax, cs:qword_1401A3F50
0x140036f89  mov     ecx, ebp
0x140036f8b  mov     rbx, [rax+rcx*8]
0x140036f8f  lea     rax, UlpCompleteCacheBuildWorker
0x140036f96  mov     [rdi+10h], rax
0x140036f9a  lea     rcx, [rbx+10h]; ListHead
0x140036f9e  call    cs:__imp_ExpInterlockedPushEntrySList
0x140036fa5  nop     dword ptr [rax+rax+00h]
0x140036faa  test    rax, rax
0x140036fad  jnz     loc_140036F07
0x140036fb3  lea     rcx, [rbx+20h]; Event
0x140036fb7  xor     r8d, r8d; Wait
0x140036fba  xor     edx, edx; Increment
0x140036fbc  call    cs:__imp_KeSetEvent
0x140036fc3  nop     dword ptr [rax+rax+00h]
0x140036fc8  mov     rcx, rbx; Context
0x140036fcb  call    UlpActivateThreadPoolQueue
0x140036fd0  jmp     loc_140036F07
0x140036fd5  mov     rbp, qword ptr [rsp+68h+var_38+8]
0x140036fda  jmp     loc_140036EDF
0x140036fdf  mov     edx, 0B6h
0x140036fe4  mov     [rsp+68h+var_40], rdi
0x140036fe9  mov     ecx, 409h
0x140036fee  mov     dword ptr [rsp+68h+var_48], esi
0x140036ff2  mov     r9, rbx
0x140036ff5  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x140036ffc  call    WPP_SF_qdP
0x140037001  jmp     loc_140036E4E
0x140037006  mov     edx, 19h
0x14003700b  mov     [rsp+68h+var_48], rsi
0x140037010  mov     ecx, 51Ch
0x140037015  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x14003701c  mov     r9, rax
0x14003701f  call    WPP_SF_qq
0x140037024  jmp     loc_140036EDF
0x140037029  mov     edx, 1Ah
0x14003702e  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140037035  mov     ecx, 51Ch
0x14003703a  mov     r9, rbp
0x14003703d  call    WPP_SF_q
0x140037042  jmp     loc_140036EF8
0x140037047  lea     rcx, UlThreadPoolArena
0x14003704e  call    UlpAssignThreadPoolWork
0x140037053  mov     ebp, eax
0x140037055  jmp     loc_140036F50
0x14003705a  mov     edx, 0B7h
0x14003705f  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x140037066  mov     ecx, 409h
0x14003706b  call    WPP_SF_
0x140037070  jmp     loc_140036F14
```
