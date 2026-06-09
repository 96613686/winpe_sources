# CTSRpcClientTrackerMgr::ReleaseTracker(unsigned __int64)

- ea: `0x180033220`
- end: `0x180033497`
- name: `?ReleaseTracker@CTSRpcClientTrackerMgr@@UEAAJ_K@Z`
- size: `631`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x1800077a0`
- `0x180033220`
- `0x18004e850`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180033331`
- `ntdll!RtlReleaseResource` at `0x18003334d`
- `ntdll!RtlReleaseResource` at `0x180033331`
- `ntdll!RtlReleaseResource` at `0x18003334d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003329d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003329d`
- `ntdll!RtlLookupElementGenericTable` at `0x1800332c6`
- `ntdll!RtlLookupElementGenericTable` at `0x1800332c6`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800332e4`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800332e4`
- `ntdll!EtwEventWriteTransfer` at `0x180033455`
- `ntdll!EtwEventWriteTransfer` at `0x180033455`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003337d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003337d`

## string_xrefs

- `0x180033315`: `m_ptrRpcClientList.Remove failed: 0x%x in %s`
- `0x1800333c4`: `RpcClientTracker removed successfully this RPC Caller`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTSRpcClientTrackerMgr::ReleaseTracker(CTSRpcClientTrackerMgr *this, volatile signed __int32 *a2)
{
  unsigned int v4; // ebx
  struct _RTL_RESOURCE *v5; // r14
  __int64 *v6; // rax
  __int64 v7; // rdi
  BOOLEAN v8; // bl
  RPC_STATUS v9; // eax
  signed int v10; // ecx
  __int64 v11; // rax
  unsigned int Pid; // [rsp+30h] [rbp-49h] BYREF
  volatile signed __int32 *Buffer; // [rsp+38h] [rbp-41h] BYREF
  __int64 v15; // [rsp+40h] [rbp-39h] BYREF
  __int64 v16; // [rsp+48h] [rbp-31h]
  __int64 v17; // [rsp+50h] [rbp-29h] BYREF
  int *v18; // [rsp+60h] [rbp-19h] BYREF
  int v19; // [rsp+68h] [rbp-11h]
  int v20; // [rsp+6Ch] [rbp-Dh]
  char *v21; // [rsp+70h] [rbp-9h]
  int v22; // [rsp+78h] [rbp-1h]
  int v23; // [rsp+7Ch] [rbp+3h]
  const char *v24; // [rsp+80h] [rbp+7h]
  __int64 v25; // [rsp+88h] [rbp+Fh]
  __int64 *v26; // [rsp+90h] [rbp+17h]
  __int64 v27; // [rsp+98h] [rbp+1Fh]
  volatile signed __int32 **p_Buffer; // [rsp+A0h] [rbp+27h]
  __int64 v29; // [rsp+A8h] [rbp+2Fh]

  if ( a2 )
  {
    _InterlockedDecrement(a2 + 401);
    v5 = (struct _RTL_RESOURCE *)((char *)this + 1592);
    v15 = (__int64)this + 1592;
    LODWORD(v16) = 1;
    if ( *((_DWORD *)this + 422) )
      RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 1592), 1u);
    if ( *((_DWORD *)a2 + 401)
      || (Buffer = a2,
          (v6 = (__int64 *)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 1696), &Buffer)) != 0)
      && (v7 = *v6,
          v8 = RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 1696), v6),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7),
          v8) )
    {
      if ( LODWORD(v5[1].Lock.DebugInfo) )
        RtlReleaseResource(v5);
      v4 = 0;
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        LODWORD(Buffer) = *((_DWORD *)a2 + 401);
        Pid = 0;
        v9 = I_RpcBindingInqLocalClientPID(0, &Pid);
        v10 = v9;
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        v11 = 0;
        if ( v10 >= 0 )
          v11 = Pid;
        v17 = v11;
        p_Buffer = &Buffer;
        v29 = 4;
        v26 = &v17;
        v27 = 8;
        v24 = "RpcClientTracker removed successfully this RPC Caller";
        v25 = 54;
        v15 = 0x14050B000000LL;
        v16 = 0;
        v18 = off_1800DF028;
        v19 = *(unsigned __int16 *)off_1800DF028;
        v20 = 2;
        v21 = byte_1800C81B1;
        v22 = 50;
        v23 = 1;
        Pid = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(RegHandle, &v15, 0, 0, 5, &v18);
      }
    }
    else
    {
      v4 = -2147024809;
      _DbgPrintMessage(
        8,
        "m_ptrRpcClientList.Remove failed: 0x%x in %s",
        -2147024809,
        "CTSRpcClientTrackerMgr::ReleaseTracker");
      if ( LODWORD(v5[1].Lock.DebugInfo) )
        RtlReleaseResource(v5);
    }
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a2 + 16LL))(a2);
  }
  else
  {
    v4 = -2147024809;
    _DbgPrintMessage(8, "NULL == ptrCookie failed: 0x%x in %s", -2147024809, "CTSRpcClientTrackerMgr::ReleaseTracker");
  }
  return v4;
}

```

## disassembly

```asm
0x180033220  mov     [rsp-8+arg_10], rbx
0x180033225  mov     [rsp-8+arg_18], rsi
0x18003322a  push    rbp
0x18003322b  push    rdi
0x18003322c  push    r14
0x18003322e  lea     rbp, [rsp-47h]
0x180033233  sub     rsp, 0C0h
0x18003323a  mov     rax, cs:__security_cookie
0x180033241  xor     rax, rsp
0x180033244  mov     [rbp+57h+var_20], rax
0x180033248  mov     rsi, rdx
0x18003324b  mov     rbx, rcx
0x18003324e  test    rdx, rdx
0x180033251  jnz     short loc_180033278
0x180033253  mov     ebx, 80070057h
0x180033258  lea     r9, aCtsrpcclienttr_0; "CTSRpcClientTrackerMgr::ReleaseTracker"
0x18003325f  mov     r8d, ebx
0x180033262  lea     rdx, aNullPtrcookieF; "NULL == ptrCookie failed: 0x%x in %s"
0x180033269  mov     ecx, 8; int
0x18003326e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033273  jmp     loc_180033470
0x180033278  lock dec dword ptr [rdx+644h]
0x18003327f  lea     r14, [rcx+638h]
0x180033286  mov     [rbp+57h+var_90], r14
0x18003328a  mov     dword ptr [rbp+57h+var_88], 1
0x180033291  cmp     dword ptr [r14+60h], 0
0x180033296  jz      short loc_1800332AA
0x180033298  mov     dl, 1; Wait
0x18003329a  mov     rcx, r14; Resource
0x18003329d  call    cs:__imp_RtlAcquireResourceExclusive
0x1800332a4  nop     dword ptr [rax+rax+00h]
0x1800332a9  nop
0x1800332aa  cmp     dword ptr [rsi+644h], 0
0x1800332b1  jnz     loc_180033343
0x1800332b7  mov     [rbp+57h+Buffer], rsi
0x1800332bb  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800332bf  lea     rcx, [rbx+6A0h]; Table
0x1800332c6  call    cs:__imp_RtlLookupElementGenericTable
0x1800332cd  nop     dword ptr [rax+rax+00h]
0x1800332d2  test    rax, rax
0x1800332d5  jz      short loc_180033306
0x1800332d7  mov     rdi, [rax]
0x1800332da  mov     rdx, rax; Buffer
0x1800332dd  lea     rcx, [rbx+6A0h]; Table
0x1800332e4  call    cs:__imp_RtlDeleteElementGenericTable
0x1800332eb  nop     dword ptr [rax+rax+00h]
0x1800332f0  movzx   ebx, al
0x1800332f3  mov     rdx, [rdi]
0x1800332f6  mov     rcx, rdi
0x1800332f9  mov     rax, [rdx+10h]
0x1800332fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033302  test    bl, bl
0x180033304  jnz     short loc_180033343
0x180033306  mov     ebx, 80070057h
0x18003330b  lea     r9, aCtsrpcclienttr_0; "CTSRpcClientTrackerMgr::ReleaseTracker"
0x180033312  mov     r8d, ebx
0x180033315  lea     rdx, aMPtrrpcclientl_0; "m_ptrRpcClientList.Remove failed: 0x%x "...
0x18003331c  mov     ecx, 8; int
0x180033321  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033326  nop
0x180033327  cmp     dword ptr [r14+60h], 0
0x18003332c  jz      short loc_18003333E
0x18003332e  mov     rcx, r14; Resource
0x180033331  call    cs:__imp_RtlReleaseResource
0x180033338  nop     dword ptr [rax+rax+00h]
0x18003333d  nop
0x18003333e  jmp     loc_180033461
0x180033343  cmp     dword ptr [r14+60h], 0
0x180033348  jz      short loc_18003335A
0x18003334a  mov     rcx, r14; Resource
0x18003334d  call    cs:__imp_RtlReleaseResource
0x180033354  nop     dword ptr [rax+rax+00h]
0x180033359  nop
0x18003335a  mov     eax, cs:dword_1800DF020
0x180033360  xor     ebx, ebx
0x180033362  cmp     eax, 5
0x180033365  jbe     loc_180033461
0x18003336b  mov     eax, [rsi+644h]
0x180033371  mov     dword ptr [rbp+57h+Buffer], eax
0x180033374  mov     [rbp+57h+Pid], ebx
0x180033377  lea     rdx, [rbp+57h+Pid]; Pid
0x18003337b  xor     ecx, ecx; Binding
0x18003337d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180033384  nop     dword ptr [rax+rax+00h]
0x180033389  mov     ecx, eax
0x18003338b  test    eax, eax
0x18003338d  jle     short loc_180033398
0x18003338f  movzx   ecx, ax
0x180033392  or      ecx, 80070000h
0x180033398  mov     eax, ebx
0x18003339a  test    ecx, ecx
0x18003339c  cmovns  eax, [rbp+57h+Pid]
0x1800333a0  mov     [rbp+57h+var_80], rax
0x1800333a4  lea     rax, [rbp+57h+Buffer]
0x1800333a8  mov     [rbp+57h+var_30], rax
0x1800333ac  mov     [rbp+57h+var_28], 4
0x1800333b4  lea     rax, [rbp+57h+var_80]
0x1800333b8  mov     [rbp+57h+var_40], rax
0x1800333bc  mov     [rbp+57h+var_38], 8
0x1800333c4  lea     rax, aRpcclienttrack; "RpcClientTracker removed successfully t"...
0x1800333cb  mov     [rbp+57h+var_50], rax
0x1800333cf  mov     [rbp+57h+var_48], 36h ; '6'
0x1800333d7  mov     dword ptr [rbp+57h+var_90], 0B000000h
0x1800333de  movzx   eax, cs:word_1800C81A7
0x1800333e5  mov     dword ptr [rbp+57h+var_90+4], eax
0x1800333e8  mov     [rbp+57h+var_88], rbx
0x1800333ec  mov     rax, cs:off_1800DF028
0x1800333f3  mov     [rbp+57h+var_70], rax
0x1800333f7  movzx   eax, word ptr [rax]
0x1800333fa  mov     [rbp+57h+var_68], eax
0x1800333fd  mov     [rbp+57h+var_64], 2
0x180033404  lea     rax, byte_1800C81B1
0x18003340b  mov     [rbp+57h+var_60], rax
0x18003340f  mov     [rbp+57h+var_58], 32h ; '2'
0x180033416  mov     [rbp+57h+var_54], 1
0x18003341d  lea     rax, _TraceLoggingMetadataEnd
0x180033424  lea     rcx, _TraceLoggingMetadata
0x18003342b  sub     eax, ecx
0x18003342d  mov     [rbp+57h+Pid], eax
0x180033430  mov     eax, [rbp+57h+Pid]
0x180033433  lea     rax, [rbp+57h+var_70]
0x180033437  mov     [rsp+0D0h+var_A8], rax
0x18003343c  mov     [rsp+0D0h+var_B0], 5
0x180033444  xor     r9d, r9d
0x180033447  xor     r8d, r8d
0x18003344a  lea     rdx, [rbp+57h+var_90]
0x18003344e  mov     rcx, cs:RegHandle
0x180033455  call    cs:__imp_EtwEventWriteTransfer
0x18003345c  nop     dword ptr [rax+rax+00h]
0x180033461  mov     rdx, [rsi]
0x180033464  mov     rcx, rsi
0x180033467  mov     rax, [rdx+10h]
0x18003346b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033470  mov     eax, ebx
0x180033472  mov     rcx, [rbp+57h+var_20]
0x180033476  xor     rcx, rsp; StackCookie
0x180033479  call    __security_check_cookie
0x18003347e  lea     r11, [rsp+0D0h+var_10]
0x180033486  mov     rbx, [r11+30h]
0x18003348a  mov     rsi, [r11+38h]
0x18003348e  mov     rsp, r11
0x180033491  pop     r14
0x180033493  pop     rdi
0x180033494  pop     rbp
0x180033495  retn
```
