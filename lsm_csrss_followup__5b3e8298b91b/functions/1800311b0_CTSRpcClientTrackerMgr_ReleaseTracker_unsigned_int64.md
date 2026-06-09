# CTSRpcClientTrackerMgr::ReleaseTracker(unsigned __int64)

- ea: `0x1800311b0`
- end: `0x1800313f8`
- name: `?ReleaseTracker@CTSRpcClientTrackerMgr@@UEAAJ_K@Z`
- size: `584`
- prototype: `__int64 __fastcall(CTSRpcClientTrackerMgr *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x1800074c0`
- `0x1800311b0`
- `0x18004b460`
- `0x180097010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800312ab`
- `ntdll!RtlReleaseResource` at `0x1800312c1`
- `ntdll!RtlReleaseResource` at `0x1800312ab`
- `ntdll!RtlReleaseResource` at `0x1800312c1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003122d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003122d`
- `ntdll!RtlLookupElementGenericTable` at `0x18003124c`
- `ntdll!RtlLookupElementGenericTable` at `0x18003124c`
- `ntdll!RtlDeleteElementGenericTable` at `0x180031264`
- `ntdll!RtlDeleteElementGenericTable` at `0x180031264`
- `ntdll!EtwEventWriteTransfer` at `0x1800313bd`
- `ntdll!EtwEventWriteTransfer` at `0x1800313bd`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800312eb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800312eb`

## string_xrefs

- `0x18003128f`: `m_ptrRpcClientList.Remove failed: 0x%x in %s`
- `0x18003132c`: `RpcClientTracker removed successfully this RPC Caller`

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
      if ( (unsigned int)dword_1800DA020 > 5 )
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
        v18 = off_1800DA028;
        v19 = *(unsigned __int16 *)off_1800DA028;
        v20 = 2;
        v21 = byte_1800C3029;
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
0x1800311b0  mov     [rsp-8+arg_10], rbx
0x1800311b5  mov     [rsp-8+arg_18], rsi
0x1800311ba  push    rbp
0x1800311bb  push    rdi
0x1800311bc  push    r14
0x1800311be  lea     rbp, [rsp-47h]
0x1800311c3  sub     rsp, 0C0h
0x1800311ca  mov     rax, cs:__security_cookie
0x1800311d1  xor     rax, rsp
0x1800311d4  mov     [rbp+57h+var_20], rax
0x1800311d8  mov     rsi, rdx
0x1800311db  mov     rbx, rcx
0x1800311de  test    rdx, rdx
0x1800311e1  jnz     short loc_180031208
0x1800311e3  mov     ebx, 80070057h
0x1800311e8  lea     r9, aCtsrpcclienttr_0; "CTSRpcClientTrackerMgr::ReleaseTracker"
0x1800311ef  mov     r8d, ebx
0x1800311f2  lea     rdx, aNullPtrcookieF; "NULL == ptrCookie failed: 0x%x in %s"
0x1800311f9  mov     ecx, 8; int
0x1800311fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180031203  jmp     loc_1800313D2
0x180031208  lock dec dword ptr [rdx+644h]
0x18003120f  lea     r14, [rcx+638h]
0x180031216  mov     [rbp+57h+var_90], r14
0x18003121a  mov     dword ptr [rbp+57h+var_88], 1
0x180031221  cmp     dword ptr [r14+60h], 0
0x180031226  jz      short loc_180031234
0x180031228  mov     dl, 1; Wait
0x18003122a  mov     rcx, r14; Resource
0x18003122d  call    cs:__imp_RtlAcquireResourceExclusive
0x180031233  nop
0x180031234  cmp     dword ptr [rsi+644h], 0
0x18003123b  jnz     short loc_1800312B7
0x18003123d  mov     [rbp+57h+Buffer], rsi
0x180031241  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180031245  lea     rcx, [rbx+6A0h]; Table
0x18003124c  call    cs:__imp_RtlLookupElementGenericTable
0x180031252  test    rax, rax
0x180031255  jz      short loc_180031280
0x180031257  mov     rdi, [rax]
0x18003125a  mov     rdx, rax; Buffer
0x18003125d  lea     rcx, [rbx+6A0h]; Table
0x180031264  call    cs:__imp_RtlDeleteElementGenericTable
0x18003126a  movzx   ebx, al
0x18003126d  mov     rdx, [rdi]
0x180031270  mov     rcx, rdi
0x180031273  mov     rax, [rdx+10h]
0x180031277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003127c  test    bl, bl
0x18003127e  jnz     short loc_1800312B7
0x180031280  mov     ebx, 80070057h
0x180031285  lea     r9, aCtsrpcclienttr_0; "CTSRpcClientTrackerMgr::ReleaseTracker"
0x18003128c  mov     r8d, ebx
0x18003128f  lea     rdx, aMPtrrpcclientl_0; "m_ptrRpcClientList.Remove failed: 0x%x "...
0x180031296  mov     ecx, 8; int
0x18003129b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800312a0  nop
0x1800312a1  cmp     dword ptr [r14+60h], 0
0x1800312a6  jz      short loc_1800312B2
0x1800312a8  mov     rcx, r14; Resource
0x1800312ab  call    cs:__imp_RtlReleaseResource
0x1800312b1  nop
0x1800312b2  jmp     loc_1800313C3
0x1800312b7  cmp     dword ptr [r14+60h], 0
0x1800312bc  jz      short loc_1800312C8
0x1800312be  mov     rcx, r14; Resource
0x1800312c1  call    cs:__imp_RtlReleaseResource
0x1800312c7  nop
0x1800312c8  mov     eax, cs:dword_1800DA020
0x1800312ce  xor     ebx, ebx
0x1800312d0  cmp     eax, 5
0x1800312d3  jbe     loc_1800313C3
0x1800312d9  mov     eax, [rsi+644h]
0x1800312df  mov     dword ptr [rbp+57h+Buffer], eax
0x1800312e2  mov     [rbp+57h+Pid], ebx
0x1800312e5  lea     rdx, [rbp+57h+Pid]; Pid
0x1800312e9  xor     ecx, ecx; Binding
0x1800312eb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800312f1  mov     ecx, eax
0x1800312f3  test    eax, eax
0x1800312f5  jle     short loc_180031300
0x1800312f7  movzx   ecx, ax
0x1800312fa  or      ecx, 80070000h
0x180031300  mov     eax, ebx
0x180031302  test    ecx, ecx
0x180031304  cmovns  eax, [rbp+57h+Pid]
0x180031308  mov     [rbp+57h+var_80], rax
0x18003130c  lea     rax, [rbp+57h+Buffer]
0x180031310  mov     [rbp+57h+var_30], rax
0x180031314  mov     [rbp+57h+var_28], 4
0x18003131c  lea     rax, [rbp+57h+var_80]
0x180031320  mov     [rbp+57h+var_40], rax
0x180031324  mov     [rbp+57h+var_38], 8
0x18003132c  lea     rax, aRpcclienttrack; "RpcClientTracker removed successfully t"...
0x180031333  mov     [rbp+57h+var_50], rax
0x180031337  mov     [rbp+57h+var_48], 36h ; '6'
0x18003133f  mov     dword ptr [rbp+57h+var_90], 0B000000h
0x180031346  movzx   eax, cs:word_1800C301F
0x18003134d  mov     dword ptr [rbp+57h+var_90+4], eax
0x180031350  mov     [rbp+57h+var_88], rbx
0x180031354  mov     rax, cs:off_1800DA028
0x18003135b  mov     [rbp+57h+var_70], rax
0x18003135f  movzx   eax, word ptr [rax]
0x180031362  mov     [rbp+57h+var_68], eax
0x180031365  mov     [rbp+57h+var_64], 2
0x18003136c  lea     rax, byte_1800C3029
0x180031373  mov     [rbp+57h+var_60], rax
0x180031377  mov     [rbp+57h+var_58], 32h ; '2'
0x18003137e  mov     [rbp+57h+var_54], 1
0x180031385  lea     rax, _TraceLoggingMetadataEnd
0x18003138c  lea     rcx, _TraceLoggingMetadata
0x180031393  sub     eax, ecx
0x180031395  mov     [rbp+57h+Pid], eax
0x180031398  mov     eax, [rbp+57h+Pid]
0x18003139b  lea     rax, [rbp+57h+var_70]
0x18003139f  mov     [rsp+0D0h+var_A8], rax
0x1800313a4  mov     [rsp+0D0h+var_B0], 5
0x1800313ac  xor     r9d, r9d
0x1800313af  xor     r8d, r8d
0x1800313b2  lea     rdx, [rbp+57h+var_90]
0x1800313b6  mov     rcx, cs:RegHandle
0x1800313bd  call    cs:__imp_EtwEventWriteTransfer
0x1800313c3  mov     rdx, [rsi]
0x1800313c6  mov     rcx, rsi
0x1800313c9  mov     rax, [rdx+10h]
0x1800313cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313d2  mov     eax, ebx
0x1800313d4  mov     rcx, [rbp+57h+var_20]
0x1800313d8  xor     rcx, rsp; StackCookie
0x1800313db  call    __security_check_cookie
0x1800313e0  lea     r11, [rsp+0D0h+var_10]
0x1800313e8  mov     rbx, [r11+30h]
0x1800313ec  mov     rsi, [r11+38h]
0x1800313f0  mov     rsp, r11
0x1800313f3  pop     r14
0x1800313f5  pop     rdi
0x1800313f6  pop     rbp
0x1800313f7  retn
```
