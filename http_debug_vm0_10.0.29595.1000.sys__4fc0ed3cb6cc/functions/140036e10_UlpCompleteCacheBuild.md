# UlpCompleteCacheBuild

- ea: `0x140036e10`
- end: `0x140037055`
- name: `UlpCompleteCacheBuild`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x140032fb0`
- `0x140036e10`
- `0x140037060`
- `0x14005e030`
- `0x14013dd68`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140036e77`
- `ntoskrnl!KeGetCurrentIrql` at `0x140036e77`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036f7e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036f7e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140036f0d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140036f0d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140036e9e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140036e9e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140036edb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140036edb`
- `ntoskrnl!KeSetEvent` at `0x140036f9c`
- `ntoskrnl!KeSetEvent` at `0x140036f9c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140036f36`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140036f36`

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
    WPP_SF_qdP(1033, 182, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1, a2, a3);
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
    return (PSLIST_ENTRY)WPP_SF_(1033, 183, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140036e10  push    rbx
0x140036e12  push    rbp
0x140036e13  push    rsi
0x140036e14  push    rdi
0x140036e15  sub     rsp, 48h
0x140036e19  mov     rdi, r8
0x140036e1c  mov     esi, edx
0x140036e1e  mov     rbx, rcx
0x140036e21  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140036e28  jnz     loc_140036FBF
0x140036e2e  mov     [rbx+78h], rdi
0x140036e32  lea     rdi, [rbx+40h]
0x140036e36  mov     [rbx+70h], esi
0x140036e39  cmp     qword ptr [rdi], 0
0x140036e3d  jnz     short loc_140036E4D
0x140036e3f  cmp     qword ptr [rdi+10h], 0
0x140036e44  jnz     short loc_140036E4D
0x140036e46  cmp     qword ptr [rdi+20h], 0
0x140036e4b  jz      short loc_140036E68
0x140036e4d  mov     r9d, 2CD6h; BugCheckParameter4
0x140036e53  lea     r8, aMinioHttpSysSe; "minio\\http\\sys\\sendresponse.c"
0x140036e5a  mov     rdx, rdi; BugCheckParameter2
0x140036e5d  mov     ecx, 1; BugCheckParameter1
0x140036e62  call    UlBugCheckEx
0x140036e68  mov     rax, [rbx+18h]
0x140036e6c  mov     rcx, [rax+88h]
0x140036e73  mov     rsi, [rcx+40h]
0x140036e77  call    cs:__imp_KeGetCurrentIrql
0x140036e7e  nop     dword ptr [rax+rax+00h]
0x140036e83  test    al, al
0x140036e85  jnz     short loc_140036EFE
0x140036e87  xor     bl, bl
0x140036e89  xorps   xmm0, xmm0
0x140036e8c  movups  [rsp+68h+var_38], xmm0
0x140036e91  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140036e95  jz      loc_140036FB5
0x140036e9b  mov     rcx, rsi
0x140036e9e  call    cs:__imp_PsAttachSiloToCurrentThread
0x140036ea5  nop     dword ptr [rax+rax+00h]
0x140036eaa  mov     rbp, rax
0x140036ead  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140036eb4  mov     ebx, 1
0x140036eb9  jnz     loc_140036FE6
0x140036ebf  mov     rcx, rdi
0x140036ec2  call    UlpCompleteCacheBuildWorker
0x140036ec7  test    bl, bl
0x140036ec9  jz      short loc_140036EE7
0x140036ecb  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140036ed2  jnz     loc_140037009
0x140036ed8  mov     rcx, rbp
0x140036edb  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140036ee2  nop     dword ptr [rax+rax+00h]
0x140036ee7  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140036eee  jnz     loc_14003703A
0x140036ef4  add     rsp, 48h
0x140036ef8  pop     rdi
0x140036ef9  pop     rsi
0x140036efa  pop     rbp
0x140036efb  pop     rbx
0x140036efc  retn
0x140036efe  xor     ebp, ebp
0x140036f00  lea     ebx, [rbp+1]
0x140036f03  cmp     cs:dword_1401A3F48, ebx
0x140036f09  jbe     short loc_140036F30
0x140036f0b  xor     ecx, ecx; ProcNumber
0x140036f0d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140036f14  nop     dword ptr [rax+rax+00h]
0x140036f19  xor     edx, edx
0x140036f1b  div     cs:UxNumberOfProcessors
0x140036f21  cmp     cs:byte_1401A3F60, 0
0x140036f28  mov     ebp, edx
0x140036f2a  jnz     loc_140037027
0x140036f30  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140036f34  jnz     short loc_140036F45
0x140036f36  call    cs:__imp_PsGetCurrentServerSilo
0x140036f3d  nop     dword ptr [rax+rax+00h]
0x140036f42  mov     rsi, rax
0x140036f45  mov     edx, 49576C55h
0x140036f4a  mov     [rdi+20h], rsi
0x140036f4e  mov     r8d, 0Dh
0x140036f54  mov     rcx, rsi
0x140036f57  call    UxPodReferenceSilo
0x140036f5c  mov     [rdi+18h], bl
0x140036f5f  mov     rdx, rdi; ListEntry
0x140036f62  mov     rax, cs:qword_1401A3F50
0x140036f69  mov     ecx, ebp
0x140036f6b  mov     rbx, [rax+rcx*8]
0x140036f6f  lea     rax, UlpCompleteCacheBuildWorker
0x140036f76  mov     [rdi+10h], rax
0x140036f7a  lea     rcx, [rbx+10h]; ListHead
0x140036f7e  call    cs:__imp_ExpInterlockedPushEntrySList
0x140036f85  nop     dword ptr [rax+rax+00h]
0x140036f8a  test    rax, rax
0x140036f8d  jnz     loc_140036EE7
0x140036f93  lea     rcx, [rbx+20h]; Event
0x140036f97  xor     r8d, r8d; Wait
0x140036f9a  xor     edx, edx; Increment
0x140036f9c  call    cs:__imp_KeSetEvent
0x140036fa3  nop     dword ptr [rax+rax+00h]
0x140036fa8  mov     rcx, rbx; Context
0x140036fab  call    UlpActivateThreadPoolQueue
0x140036fb0  jmp     loc_140036EE7
0x140036fb5  mov     rbp, qword ptr [rsp+68h+var_38+8]
0x140036fba  jmp     loc_140036EBF
0x140036fbf  mov     edx, 0B6h
0x140036fc4  mov     [rsp+68h+var_40], rdi
0x140036fc9  mov     ecx, 409h
0x140036fce  mov     dword ptr [rsp+68h+var_48], esi
0x140036fd2  mov     r9, rbx
0x140036fd5  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140036fdc  call    WPP_SF_qdP
0x140036fe1  jmp     loc_140036E2E
0x140036fe6  mov     edx, 19h
0x140036feb  mov     [rsp+68h+var_48], rsi
0x140036ff0  mov     ecx, 51Ch
0x140036ff5  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140036ffc  mov     r9, rax
0x140036fff  call    WPP_SF_qq
0x140037004  jmp     loc_140036EBF
0x140037009  mov     edx, 1Ah
0x14003700e  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140037015  mov     ecx, 51Ch
0x14003701a  mov     r9, rbp
0x14003701d  call    WPP_SF_q
0x140037022  jmp     loc_140036ED8
0x140037027  lea     rcx, UlThreadPoolArena
0x14003702e  call    UlpAssignThreadPoolWork
0x140037033  mov     ebp, eax
0x140037035  jmp     loc_140036F30
0x14003703a  mov     edx, 0B7h
0x14003703f  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140037046  mov     ecx, 409h
0x14003704b  call    WPP_SF_
0x140037050  jmp     loc_140036EF4
```
