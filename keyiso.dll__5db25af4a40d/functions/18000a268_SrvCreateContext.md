# SrvCreateContext

- ea: `0x18000a268`
- end: `0x18000a3c1`
- name: `SrvCreateContext`
- size: `345`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, unsigned int **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005f80`

## callees

- `0x180002d20`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`
- `0x1800062a0`
- `0x18000a268`
- `0x18000a3c8`
- `0x18000a6cc`
- `0x18000d0ac`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a318`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000a318`
- `ntdll!RtlEnterCriticalSection` at `0x18000a36d`
- `ntdll!RtlEnterCriticalSection` at `0x18000a36d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a3ab`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a3ab`

## string_xrefs

- `0x18000a2b7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`
- `0x18000a334`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvCreateContext(RPC_BINDING_HANDLE Binding, unsigned int **a2)
{
  unsigned int *v4; // rax
  int v5; // edx
  unsigned int *v6; // rbx
  unsigned int v7; // edi
  unsigned int inited; // eax
  const char *v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx

  v4 = (unsigned int *)MSCryptAlloc(304);
  v6 = v4;
  if ( !v4 )
  {
    v7 = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        246);
    goto LABEL_15;
  }
  memset_0(v4, 0, 0x130u);
  inited = SrvInitContext(Binding, v6);
  v7 = inited;
  if ( inited )
  {
    v9 = "Status";
    v10 = 1026;
LABEL_9:
    DebugTraceError(inited, v9, "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c", v10);
    MSCryptFree(v6);
    v6 = 0;
    goto LABEL_15;
  }
  inited = I_RpcBindingInqLocalClientPID(Binding, v6 + 4);
  if ( inited )
  {
    v7 = -2146893810;
    v9 = "dwError";
    v10 = 1034;
    goto LABEL_9;
  }
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    *((_QWORD *)v6 + 37) = CreateKeyIsoPerfCounterInstance(v6[4]);
  RtlEnterCriticalSection(&g_ResLock);
  v11 = SrvCryptContextList;
  if ( *(__int64 **)(SrvCryptContextList + 8) != &SrvCryptContextList )
    __fastfail(3u);
  *((_QWORD *)v6 + 3) = SrvCryptContextList;
  *((_QWORD *)v6 + 4) = &SrvCryptContextList;
  *(_QWORD *)(v11 + 8) = v6 + 6;
  SrvCryptContextList = (__int64)(v6 + 6);
  RtlLeaveCriticalSection(&g_ResLock);
LABEL_15:
  *a2 = v6;
  return v7;
}

```

## disassembly

```asm
0x18000a268  push    rbx
0x18000a26a  push    rbp
0x18000a26b  push    rsi
0x18000a26c  push    rdi
0x18000a26d  push    r14
0x18000a26f  sub     rsp, 40h
0x18000a273  mov     rbp, rcx
0x18000a276  mov     edi, 130h
0x18000a27b  mov     ecx, edi
0x18000a27d  mov     r14, rdx
0x18000a280  call    MSCryptAlloc
0x18000a285  mov     rbx, rax
0x18000a288  test    rax, rax
0x18000a28b  jnz     short loc_18000A2E4
0x18000a28d  mov     edi, 8009000Eh
0x18000a292  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a299  lea     rax, WPP_GLOBAL_Control
0x18000a2a0  cmp     rcx, rax
0x18000a2a3  jz      loc_18000A3B1
0x18000a2a9  test    byte ptr [rcx+1Ch], 1
0x18000a2ad  jz      loc_18000A3B1
0x18000a2b3  mov     rcx, [rcx+10h]
0x18000a2b7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a2be  mov     [rsp+68h+var_38], 3F6h
0x18000a2c6  lea     r9, aStatus; "Status"
0x18000a2cd  mov     [rsp+68h+var_40], r8
0x18000a2d2  mov     [rsp+68h+var_48], 8009000Eh
0x18000a2da  call    WPP_SF_sDsd
0x18000a2df  jmp     loc_18000A3B1
0x18000a2e4  mov     r8, rdi; Size
0x18000a2e7  xor     edx, edx; Val
0x18000a2e9  mov     rcx, rbx; void *
0x18000a2ec  call    memset_0
0x18000a2f1  mov     rdx, rbx
0x18000a2f4  mov     rcx, rbp
0x18000a2f7  call    SrvInitContext
0x18000a2fc  mov     edi, eax
0x18000a2fe  test    eax, eax
0x18000a300  jz      short loc_18000A311
0x18000a302  lea     rdx, aStatus; "Status"
0x18000a309  mov     r9d, 402h
0x18000a30f  jmp     short loc_18000A334
0x18000a311  lea     rdx, [rbx+10h]; Pid
0x18000a315  mov     rcx, rbp; Binding
0x18000a318  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000a31e  test    eax, eax
0x18000a320  jz      short loc_18000A34E
0x18000a322  mov     edi, 8009000Eh
0x18000a327  lea     rdx, aDwerror; "dwError"
0x18000a32e  mov     r9d, 40Ah
0x18000a334  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a33b  mov     ecx, eax
0x18000a33d  call    DebugTraceError
0x18000a342  mov     rcx, rbx
0x18000a345  call    MSCryptFree
0x18000a34a  xor     ebx, ebx
0x18000a34c  jmp     short loc_18000A3B1
0x18000a34e  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x18000a353  test    eax, eax
0x18000a355  jz      short loc_18000A366
0x18000a357  mov     ecx, [rbx+10h]
0x18000a35a  call    CreateKeyIsoPerfCounterInstance
0x18000a35f  mov     [rbx+128h], rax
0x18000a366  lea     rcx, g_ResLock; CriticalSection
0x18000a36d  call    cs:__imp_RtlEnterCriticalSection
0x18000a373  mov     rcx, cs:SrvCryptContextList
0x18000a37a  lea     rdx, SrvCryptContextList
0x18000a381  cmp     [rcx+8], rdx
0x18000a385  jz      short loc_18000A38E
0x18000a387  mov     ecx, 3
0x18000a38c  int     29h; Win8: RtlFailFast(ecx)
0x18000a38e  lea     rax, [rbx+18h]
0x18000a392  mov     [rax], rcx
0x18000a395  mov     [rax+8], rdx
0x18000a399  mov     [rcx+8], rax
0x18000a39d  lea     rcx, g_ResLock; CriticalSection
0x18000a3a4  mov     cs:SrvCryptContextList, rax
0x18000a3ab  call    cs:__imp_RtlLeaveCriticalSection
0x18000a3b1  mov     [r14], rbx
0x18000a3b4  mov     eax, edi
0x18000a3b6  add     rsp, 40h
0x18000a3ba  pop     r14
0x18000a3bc  pop     rdi
0x18000a3bd  pop     rsi
0x18000a3be  pop     rbp
0x18000a3bf  pop     rbx
0x18000a3c0  retn
```
