# THREAD_MANAGER::DoThreadCreation(THREAD_MANAGER::THREAD_PARAM *)

- ea: `0x18002083c`
- end: `0x180020a5b`
- name: `?DoThreadCreation@THREAD_MANAGER@@AEAAHPEAUTHREAD_PARAM@1@@Z`
- size: `543`
- prototype: `__int64 __fastcall(THREAD_MANAGER *__hidden this, struct THREAD_MANAGER::THREAD_PARAM *lpParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020480`
- `0x180021bbc`

## callees

- `0x18002083c`
- `0x180020aec`
- `0x1800215f8`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180020967`
- `KERNEL32!GetCurrentProcess` at `0x180020967`
- `KERNEL32!SetEvent` at `0x180020861`
- `KERNEL32!SetEvent` at `0x180020861`
- `KERNEL32!CreateThread` at `0x180020958`
- `KERNEL32!CreateThread` at `0x180020958`
- `KERNEL32!CreateRemoteThreadEx` at `0x18002099f`
- `KERNEL32!CreateRemoteThreadEx` at `0x18002099f`
- `KERNEL32!CloseHandle` at `0x1800209b1`
- `KERNEL32!CloseHandle` at `0x1800209b1`
- `iisutil!PuDbgPrint` at `0x180020897`
- `iisutil!PuDbgPrint` at `0x1800209e7`
- `iisutil!PuDbgPrint` at `0x180020a42`
- `iisutil!PuDbgPrint` at `0x180020897`
- `iisutil!PuDbgPrint` at `0x1800209e7`
- `iisutil!PuDbgPrint` at `0x180020a42`

## string_xrefs

- `0x180020890`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x1800209e0`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180020a3b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180020877`: `W3TP: Signaled a thread to be unparked\n`
- `0x18002087e`: `THREAD_MANAGER::DoThreadCreation`
- `0x1800209ce`: `THREAD_MANAGER::DoThreadCreation`
- `0x180020a29`: `THREAD_MANAGER::DoThreadCreation`
- `0x1800209c7`: `W3TP: Created a new thread\n`
- `0x180020a1e`: `W3TP: CreateThread, increment count on node %d\n`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::DoThreadCreation(
        THREAD_MANAGER *this,
        struct THREAD_MANAGER::THREAD_PARAM *lpParameter)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  _DWORD *v6; // rbp
  struct _PROC_THREAD_ATTRIBUTE_LIST *lpAttributeList; // r14
  __int64 v8; // r8
  __int64 v9; // rax
  HANDLE RemoteThread; // rax
  unsigned int v11; // ebx
  HANDLE CurrentProcess; // rax
  _PROCESSOR_NUMBER v14; // [rsp+80h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 20) )
  {
    SetEvent(*((HANDLE *)this + 11));
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1311,
        "THREAD_MANAGER::DoThreadCreation",
        "W3TP: Signaled a thread to be unparked\n");
    return 0;
  }
  v5 = *((_QWORD *)this + 17);
  v6 = (_DWORD *)((char *)this + 144);
  if ( v5 )
  {
    v8 = *(unsigned int *)(v5 + 12);
    v9 = *(_QWORD *)(v5 + 16);
    *(_DWORD *)(v5 + 12) = ((int)v8 + 1) % (unsigned int)*(unsigned __int16 *)(v5 + 8);
    lpAttributeList = **(struct _PROC_THREAD_ATTRIBUTE_LIST ***)(v9 + 8 * v8);
  }
  else
  {
    lpAttributeList = 0;
    if ( *v6 )
    {
      v4 = 0;
      THREAD_MANAGER::GetNextIdealNodeAndCpu(this, (unsigned int *)&v14.Group);
      if ( !THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(this, &v14) )
        return v4;
      lpAttributeList = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
      *((_DWORD *)lpParameter + 10) = 0;
    }
  }
  if ( *((_QWORD *)this + 17) || *v6 )
  {
    v11 = *(_DWORD *)(*((_QWORD *)this + 14) + 64LL);
    CurrentProcess = GetCurrentProcess();
    RemoteThread = CreateRemoteThreadEx(
                     CurrentProcess,
                     0,
                     v11,
                     THREAD_MANAGER::ThreadManagerThread,
                     lpParameter,
                     v11 != 0 ? 0x10000 : 0,
                     lpAttributeList,
                     0);
  }
  else
  {
    RemoteThread = CreateThread(
                     0,
                     *(unsigned int *)(*((_QWORD *)this + 14) + 64LL),
                     THREAD_MANAGER::ThreadManagerThread,
                     lpParameter,
                     *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) != 0 ? 0x10000 : 0,
                     0);
  }
  if ( !RemoteThread )
    return 0;
  CloseHandle(RemoteThread);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
      1376,
      "THREAD_MANAGER::DoThreadCreation",
      "W3TP: Created a new thread\n");
  v4 = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 19, 1u);
  if ( *v6 )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 19) + 20LL), 1u);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1384,
        "THREAD_MANAGER::DoThreadCreation",
        "W3TP: CreateThread, increment count on node %d\n",
        0);
  }
  return v4;
}

```

## disassembly

```asm
0x18002083c  mov     [rsp+arg_8], rbx
0x180020841  push    rbp
0x180020842  push    rsi
0x180020843  push    rdi
0x180020844  push    r14
0x180020846  push    r15
0x180020848  sub     rsp, 40h
0x18002084c  xor     esi, esi
0x18002084e  mov     r15, rdx
0x180020851  mov     rdi, rcx
0x180020854  mov     [rsp+68h+arg_0], esi
0x180020858  cmp     [rcx+50h], esi
0x18002085b  jz      short loc_1800208A4
0x18002085d  mov     rcx, [rcx+58h]; hEvent
0x180020861  call    cs:__imp_SetEvent
0x180020867  test    byte ptr cs:g_dwDebugFlags, 3
0x18002086e  jz      short loc_18002089D
0x180020870  mov     rcx, cs:g_pDebug
0x180020877  lea     rax, aW3tpSignaledAT; "W3TP: Signaled a thread to be unparked"...
0x18002087e  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x180020885  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18002088a  mov     r8d, 51Fh
0x180020890  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180020897  call    cs:__imp_PuDbgPrint
0x18002089d  xor     ebx, ebx
0x18002089f  jmp     loc_180020A48
0x1800208a4  mov     r9, [rcx+88h]
0x1800208ab  lea     rbp, [rcx+90h]
0x1800208b2  test    r9, r9
0x1800208b5  jnz     short loc_1800208FC
0x1800208b7  xor     r14d, r14d
0x1800208ba  cmp     [rbp+0], esi
0x1800208bd  jz      short loc_18002091C
0x1800208bf  lea     r8, [rsp+68h+arg_0]
0x1800208c4  xor     ebx, ebx
0x1800208c6  lea     rdx, [rsp+68h+arg_10]; unsigned int *
0x1800208ce  call    ?GetNextIdealNodeAndCpu@THREAD_MANAGER@@AEAA?AU_PROCESSOR_NUMBER@@AEAK@Z; THREAD_MANAGER::GetNextIdealNodeAndCpu(ulong &)
0x1800208d3  lea     rdx, [rsp+68h+arg_10]; struct _PROCESSOR_NUMBER *
0x1800208db  mov     rcx, rdi; this
0x1800208de  call    ?SetReusableThreadAttributeListWithIdealCpu@THREAD_MANAGER@@AEAAHPEAU_PROCESSOR_NUMBER@@@Z; THREAD_MANAGER::SetReusableThreadAttributeListWithIdealCpu(_PROCESSOR_NUMBER *)
0x1800208e3  test    eax, eax
0x1800208e5  jz      loc_180020A48
0x1800208eb  mov     r14, [rdi+0A8h]
0x1800208f2  mov     esi, [rsp+68h+arg_0]
0x1800208f6  mov     [r15+28h], esi
0x1800208fa  jmp     short loc_18002091C
0x1800208fc  mov     r8d, [r9+0Ch]
0x180020900  xor     edx, edx
0x180020902  movzx   ecx, word ptr [r9+8]
0x180020907  lea     eax, [r8+1]
0x18002090b  div     ecx
0x18002090d  mov     rax, [r9+10h]
0x180020911  mov     [r9+0Ch], edx
0x180020915  mov     rcx, [rax+r8*8]
0x180020919  mov     r14, [rcx]
0x18002091c  cmp     qword ptr [rdi+88h], 0
0x180020924  jnz     short loc_180020960
0x180020926  cmp     dword ptr [rbp+0], 0
0x18002092a  jnz     short loc_180020960
0x18002092c  mov     rax, [rdi+70h]
0x180020930  lea     r8, ?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z; lpStartAddress
0x180020937  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x180020940  mov     r9, r15; lpParameter
0x180020943  mov     edx, [rax+40h]; dwStackSize
0x180020946  mov     eax, edx
0x180020948  neg     eax
0x18002094a  sbb     ecx, ecx
0x18002094c  and     ecx, 10000h
0x180020952  mov     [rsp+68h+dwCreationFlags], ecx; dwCreationFlags
0x180020956  xor     ecx, ecx; lpThreadAttributes
0x180020958  call    cs:__imp_CreateThread
0x18002095e  jmp     short loc_1800209A5
0x180020960  mov     rax, [rdi+70h]
0x180020964  mov     ebx, [rax+40h]
0x180020967  call    cs:__imp_GetCurrentProcess
0x18002096d  mov     [rsp+68h+var_30], 0; lpThreadId
0x180020976  lea     r9, ?ThreadManagerThread@THREAD_MANAGER@@CAKPEAX@Z; lpStartAddress
0x18002097d  mov     ecx, ebx
0x18002097f  mov     [rsp+68h+lpAttributeList], r14; lpAttributeList
0x180020984  neg     ecx
0x180020986  mov     r8d, ebx; dwStackSize
0x180020989  mov     rcx, rax; hProcess
0x18002098c  sbb     edx, edx
0x18002098e  and     edx, 10000h
0x180020994  mov     dword ptr [rsp+68h+lpThreadId], edx; dwCreationFlags
0x180020998  xor     edx, edx; lpThreadAttributes
0x18002099a  mov     qword ptr [rsp+68h+dwCreationFlags], r15; lpParameter
0x18002099f  call    cs:__imp_CreateRemoteThreadEx
0x1800209a5  test    rax, rax
0x1800209a8  jz      loc_18002089D
0x1800209ae  mov     rcx, rax; hObject
0x1800209b1  call    cs:__imp_CloseHandle
0x1800209b7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800209be  jz      short loc_1800209ED
0x1800209c0  mov     rcx, cs:g_pDebug
0x1800209c7  lea     rax, aW3tpCreatedANe; "W3TP: Created a new thread\n"
0x1800209ce  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x1800209d5  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1800209da  mov     r8d, 560h
0x1800209e0  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800209e7  call    cs:__imp_PuDbgPrint
0x1800209ed  mov     ebx, 1
0x1800209f2  lock add [rdi+4Ch], ebx
0x1800209f6  cmp     dword ptr [rbp+0], 0
0x1800209fa  jz      short loc_180020A48
0x1800209fc  mov     eax, esi
0x1800209fe  lea     rcx, [rax+rax*2]
0x180020a02  mov     rax, [rdi+98h]
0x180020a09  lock add [rax+rcx*8+14h], ebx
0x180020a0e  test    byte ptr cs:g_dwDebugFlags, 3
0x180020a15  jz      short loc_180020A48
0x180020a17  mov     rcx, cs:g_pDebug
0x180020a1e  lea     rax, aW3tpCreatethre; "W3TP: CreateThread, increment count on "...
0x180020a25  mov     dword ptr [rsp+68h+lpThreadId], esi
0x180020a29  lea     r9, aThreadManagerD_0; "THREAD_MANAGER::DoThreadCreation"
0x180020a30  mov     r8d, 568h
0x180020a36  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x180020a3b  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180020a42  call    cs:__imp_PuDbgPrint
0x180020a48  mov     eax, ebx
0x180020a4a  mov     rbx, [rsp+68h+arg_8]
0x180020a4f  add     rsp, 40h
0x180020a53  pop     r15
0x180020a55  pop     r14
0x180020a57  pop     rdi
0x180020a58  pop     rsi
0x180020a59  pop     rbp
0x180020a5a  retn
```
