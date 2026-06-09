# PcaMonitorProcess(void *,PCA_PROCESS_TYPE,ushort const *,ushort const *,ushort const *,uint)

- ea: `0x180001bd0`
- end: `0x180001fc1`
- name: `?PcaMonitorProcess@@YAKPEAXW4PCA_PROCESS_TYPE@@PEBG22I@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001bc0`

## callees

- `0x180001870`
- `0x180001bd0`
- `0x180001fd0`
- `0x180002180`
- `0x180002210`
- `0x180002ca0`
- `0x180002ee8`
- `0x180002f20`
- `0x180007738`
- `0x18000c030`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000c1ae`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c1ae`
- `RPCRT4!NdrClientCall3` at `0x180001d49`
- `RPCRT4!NdrClientCall3` at `0x180001d49`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180001c7f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180001c7f`
- `ntdll!RtlFreeHeap` at `0x180001e81`
- `ntdll!RtlFreeHeap` at `0x180001f9c`
- `ntdll!RtlFreeHeap` at `0x180001fb6`
- `ntdll!RtlFreeHeap` at `0x180001e81`
- `ntdll!RtlFreeHeap` at `0x180001f9c`
- `ntdll!RtlFreeHeap` at `0x180001fb6`

## string_xrefs

- `0x180001d88`: `PcaClient`
- `0x180001e8c`: `Failed to create binding handle [%d]`
- `0x180001f17`: `Failed to process CommandLine [%d]`
- `0x180001f29`: `Failed to process CurrentDirectory [%d]`

## pseudocode

```c
__int64 __fastcall PcaMonitorProcess(
        void *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6)
{
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned __int16 *v12; // rsi
  DWORD ProcessId; // eax
  int v14; // r9d
  unsigned int v15; // eax
  unsigned int started; // edi
  unsigned __int64 v17; // rax
  const wchar_t *v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // eax
  int v21; // r8d
  const char *v23; // r9
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  __int64 v26; // [rsp+20h] [rbp-E8h]
  __int64 v27; // [rsp+28h] [rbp-E0h]
  __int64 v28; // [rsp+48h] [rbp-C0h]
  unsigned int v29; // [rsp+50h] [rbp-B8h]
  PVOID v30; // [rsp+58h] [rbp-B0h] BYREF
  int v31; // [rsp+60h] [rbp-A8h]
  int v32; // [rsp+68h] [rbp-A0h]
  PVOID P; // [rsp+70h] [rbp-98h] BYREF
  PVOID v34; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 *v35; // [rsp+80h] [rbp-88h]
  void *v36; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v37; // [rsp+90h] [rbp-78h]
  void *v38; // [rsp+98h] [rbp-70h]
  unsigned __int16 *v39; // [rsp+A0h] [rbp-68h]
  CLIENT_CALL_RETURN v40[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v41; // [rsp+B8h] [rbp-50h] BYREF

  v31 = a2;
  v38 = a1;
  v32 = a2;
  v39 = a3;
  v41 = a4;
  v35 = a5;
  v37 = PcaTimeStart();
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v9, (unsigned int)AE_PCA_MonitorProcess_Start, v10, v11, (__int64)v40);
  v12 = 0;
  v30 = 0;
  P = 0;
  v34 = 0;
  v29 = 0;
  v36 = 0;
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    started = 87;
    AslLogCallPrintf(1, "PcaMonitorProcess", 675, "Bad flags parameter");
    goto LABEL_23;
  }
  ProcessId = GetProcessId(a1);
  if ( !(unsigned int)PcapCheckEnablePca(a3, a4, ProcessId) )
  {
    started = 0;
LABEL_23:
    v19 = 0x200000004201LL;
    goto LABEL_13;
  }
  v15 = PcaExpandMappedDrive((unsigned __int16 **)&v30, a3);
  started = v15;
  if ( v15 )
  {
    v23 = "Failed to process ApplicationName [%d]";
    v24 = 699;
    goto LABEL_27;
  }
  v15 = PcaExpandMappedDrive((unsigned __int16 **)&P, a4);
  started = v15;
  if ( v15 )
  {
    v23 = "Failed to process CommandLine [%d]";
    v24 = 705;
    goto LABEL_27;
  }
  v15 = PcaExpandMappedDrive((unsigned __int16 **)&v34, v35);
  started = v15;
  if ( v15 )
  {
    v23 = "Failed to process CurrentDirectory [%d]";
    v24 = 711;
    goto LABEL_27;
  }
  v15 = PcapCreateBindingHandle(&v36);
  started = v15;
  if ( v15 )
  {
    v23 = "Failed to create binding handle [%d]";
    v24 = 721;
LABEL_27:
    LODWORD(v26) = v15;
    AslLogCallPrintf(1, "PcaMonitorProcess", v24, v23, v26);
    v12 = (unsigned __int16 *)v30;
    v19 = 0x200000004201LL;
    goto LABEL_13;
  }
  v12 = (unsigned __int16 *)v30;
LABEL_10:
  v40[0].Simple = 0;
  LODWORD(v28) = a6;
  LODWORD(v27) = v31;
  v40[0] = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, v36, a1, v27, v12, P, v34, v28);
  v17 = PcaTimeStart() - v37;
  v18 = (const wchar_t *)&dword_18000ED9C;
  if ( v12 )
    v18 = v12;
  PcaTracePrintf("PcaClient", 0, 0, "MonitorProcess,%S,Time,%llu", v18, v17);
  v19 = 0x200000004201LL;
LABEL_13:
  v20 = v29;
  if ( started )
  {
    while ( v20 <= 1 )
    {
      v25 = started - 1708;
      if ( (unsigned int)v25 > 0x2D || !_bittest64(&v19, v25) )
        break;
      started = PcacpStartPCAService();
      v20 = ++v29;
      v19 = 0x200000004201LL;
      if ( !started )
        goto LABEL_10;
    }
  }
  if ( v12 && v12 != a3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( P && P != a4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  v21 = (int)v34;
  if ( v34 && v34 != v35 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v34);
  if ( (Microsoft_Windows_Program_Compatibility_AssistantEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)L"h", v21, v14, (__int64)&v41);
  return started;
}

```

## disassembly

```asm
0x180001bd0  push    rbx
0x180001bd2  push    rsi
0x180001bd3  push    rdi
0x180001bd4  push    r12
0x180001bd6  push    r13
0x180001bd8  push    r14
0x180001bda  push    r15
0x180001bdc  sub     rsp, 0D0h
0x180001be3  mov     rax, cs:__security_cookie
0x180001bea  xor     rax, rsp
0x180001bed  mov     [rsp+108h+var_40], rax
0x180001bf5  mov     r14, r9
0x180001bf8  mov     r15, r8
0x180001bfb  mov     [rsp+108h+var_A8], edx
0x180001bff  mov     r12, rcx
0x180001c02  mov     [rsp+108h+var_70], rcx
0x180001c0a  mov     [rsp+108h+var_A0], edx
0x180001c0e  mov     [rsp+108h+var_68], r8
0x180001c16  mov     [rsp+108h+var_50], r9
0x180001c1e  mov     rax, [rsp+108h+arg_20]
0x180001c26  mov     [rsp+108h+var_88], rax
0x180001c2e  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x180001c33  mov     [rsp+108h+var_78], rax
0x180001c3b  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, 1
0x180001c42  jnz     loc_180001EC2
0x180001c48  xor     ebx, ebx
0x180001c4a  mov     esi, ebx
0x180001c4c  mov     [rsp+108h+var_B0], rbx
0x180001c51  mov     [rsp+108h+P], rbx
0x180001c56  mov     [rsp+108h+var_90], rbx
0x180001c5b  mov     [rsp+108h+var_B8], ebx
0x180001c5f  mov     [rsp+108h+var_80], rbx
0x180001c67  mov     r13d, [rsp+108h+arg_28]
0x180001c6f  test    r13d, 0FFFFFFFCh
0x180001c76  jnz     loc_180001EE0
0x180001c7c  mov     rcx, r12; Process
0x180001c7f  call    cs:__imp_GetProcessId
0x180001c85  mov     r8d, eax; unsigned int
0x180001c88  mov     rdx, r14; unsigned __int16 *
0x180001c8b  mov     rcx, r15; unsigned __int16 *
0x180001c8e  call    ?PcapCheckEnablePca@@YAHPEBG0K@Z; PcapCheckEnablePca(ushort const *,ushort const *,ulong)
0x180001c93  test    eax, eax
0x180001c95  jz      loc_180001E5C
0x180001c9b  mov     rdx, r15; unsigned __int16 *
0x180001c9e  lea     rcx, [rsp+108h+var_B0]; unsigned __int16 **
0x180001ca3  call    ?PcaExpandMappedDrive@@YAKPEAPEAGPEBG@Z; PcaExpandMappedDrive(ushort * *,ushort const *)
0x180001ca8  mov     edi, eax
0x180001caa  test    eax, eax
0x180001cac  jnz     loc_180001F08
0x180001cb2  mov     rdx, r14; unsigned __int16 *
0x180001cb5  lea     rcx, [rsp+108h+P]; unsigned __int16 **
0x180001cba  call    ?PcaExpandMappedDrive@@YAKPEAPEAGPEBG@Z; PcaExpandMappedDrive(ushort * *,ushort const *)
0x180001cbf  mov     edi, eax
0x180001cc1  test    eax, eax
0x180001cc3  jnz     loc_180001F17
0x180001cc9  mov     rdx, [rsp+108h+var_88]; unsigned __int16 *
0x180001cd1  lea     rcx, [rsp+108h+var_90]; unsigned __int16 **
0x180001cd6  call    ?PcaExpandMappedDrive@@YAKPEAPEAGPEBG@Z; PcaExpandMappedDrive(ushort * *,ushort const *)
0x180001cdb  mov     edi, eax
0x180001cdd  test    eax, eax
0x180001cdf  jnz     loc_180001F29
0x180001ce5  lea     rcx, [rsp+108h+var_80]; void **
0x180001ced  call    ?PcapCreateBindingHandle@@YAKPEAPEAX@Z; PcapCreateBindingHandle(void * *)
0x180001cf2  mov     edi, eax
0x180001cf4  test    eax, eax
0x180001cf6  jnz     loc_180001E8C
0x180001cfc  mov     rsi, [rsp+108h+var_B0]
0x180001d01  nop
0x180001d02  mov     qword ptr [rsp+108h+var_60], rbx
0x180001d0a  mov     dword ptr [rsp+108h+var_C0], r13d
0x180001d0f  mov     rax, [rsp+108h+var_90]
0x180001d14  mov     [rsp+108h+var_C8], rax
0x180001d19  mov     rax, [rsp+108h+P]
0x180001d1e  mov     [rsp+108h+var_D0], rax
0x180001d23  mov     [rsp+108h+var_D8], rsi
0x180001d28  mov     eax, [rsp+108h+var_A8]
0x180001d2c  mov     dword ptr [rsp+108h+var_E0], eax
0x180001d30  mov     [rsp+108h+var_E8], r12
0x180001d35  mov     r9, [rsp+108h+var_80]
0x180001d3d  xor     r8d, r8d; pReturnValue
0x180001d40  xor     edx, edx; nProcNum
0x180001d42  lea     rcx, pProxyInfo; pProxyInfo
0x180001d49  call    cs:__imp_NdrClientCall3
0x180001d4f  mov     qword ptr [rsp+108h+var_60], rax
0x180001d57  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x180001d5c  sub     rax, [rsp+108h+var_78]
0x180001d64  lea     rcx, dword_18000ED9C
0x180001d6b  test    rsi, rsi
0x180001d6e  cmovnz  rcx, rsi
0x180001d72  mov     [rsp+108h+var_E0], rax
0x180001d77  mov     [rsp+108h+var_E8], rcx
0x180001d7c  lea     r9, aMonitorprocess; "MonitorProcess,%S,Time,%llu"
0x180001d83  xor     r8d, r8d; unsigned int
0x180001d86  xor     edx, edx; unsigned int
0x180001d88  lea     rcx, aPcaclient; "PcaClient"
0x180001d8f  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180001d94  mov     rcx, 200000004201h
0x180001d9e  jmp     short loc_180001DDB
0x180001da0  mov     edi, eax
0x180001da2  xor     ebx, ebx
0x180001da4  mov     rcx, 200000004201h
0x180001dae  mov     r13d, [rsp+108h+arg_28]
0x180001db6  mov     rsi, [rsp+108h+var_B0]
0x180001dbb  mov     r12, [rsp+108h+var_70]
0x180001dc3  mov     eax, [rsp+108h+var_A0]
0x180001dc7  mov     [rsp+108h+var_A8], eax
0x180001dcb  mov     r15, [rsp+108h+var_68]
0x180001dd3  mov     r14, [rsp+108h+var_50]
0x180001ddb  mov     eax, [rsp+108h+var_B8]
0x180001ddf  nop
0x180001de0  test    edi, edi
0x180001de2  jnz     loc_180001F3B
0x180001de8  test    rsi, rsi
0x180001deb  jnz     loc_180001F81
0x180001df1  mov     r8, [rsp+108h+P]; P
0x180001df6  test    r8, r8
0x180001df9  jnz     short loc_180001E6D
0x180001dfb  mov     r8, [rsp+108h+var_90]; P
0x180001e00  test    r8, r8
0x180001e03  jz      short loc_180001E13
0x180001e05  cmp     r8, [rsp+108h+var_88]
0x180001e0d  jnz     loc_180001FA7
0x180001e13  test    cs:Microsoft_Windows_Program_Compatibility_AssistantEnableBits, 1
0x180001e1a  jnz     short loc_180001E41
0x180001e1c  mov     eax, edi
0x180001e1e  mov     rcx, [rsp+108h+var_40]
0x180001e26  xor     rcx, rsp; StackCookie
0x180001e29  call    __security_check_cookie
0x180001e2e  add     rsp, 0D0h
0x180001e35  pop     r15
0x180001e37  pop     r14
0x180001e39  pop     r13
0x180001e3b  pop     r12
0x180001e3d  pop     rdi
0x180001e3e  pop     rsi
0x180001e3f  pop     rbx
0x180001e40  retn
0x180001e41  lea     rax, [rsp+108h+var_50]
0x180001e49  mov     [rsp+108h+var_E8], rax
0x180001e4e  lea     rdx, AE_PCA_MonitorProcess_Stop; "h"
0x180001e55  call    McGenEventWrite_EtwEventWriteTransfer
0x180001e5a  jmp     short loc_180001E1C
0x180001e5c  mov     edi, ebx
0x180001e5e  mov     rcx, 200000004201h
0x180001e68  jmp     loc_180001DDB
0x180001e6d  cmp     r8, r14
0x180001e70  jz      short loc_180001DFB
0x180001e72  mov     rcx, gs:60h
0x180001e7b  xor     edx, edx; Flags
0x180001e7d  mov     rcx, [rcx+30h]; HeapHandle
0x180001e81  call    cs:__imp_RtlFreeHeap
0x180001e87  jmp     loc_180001DFB
0x180001e8c  lea     r9, aFailedToCreate_0; "Failed to create binding handle [%d]"
0x180001e93  mov     r8d, 2D1h
0x180001e99  mov     dword ptr [rsp+108h+var_E8], eax
0x180001e9d  lea     rdx, aPcamonitorproc_1; "PcaMonitorProcess"
0x180001ea4  mov     ecx, 1
0x180001ea9  call    AslLogCallPrintf
0x180001eae  mov     rsi, [rsp+108h+var_B0]
0x180001eb3  mov     rcx, 200000004201h
0x180001ebd  jmp     loc_180001DDB
0x180001ec2  lea     rax, [rsp+108h+var_60]
0x180001eca  mov     [rsp+108h+var_E8], rax
0x180001ecf  lea     rdx, AE_PCA_MonitorProcess_Start
0x180001ed6  call    McGenEventWrite_EtwEventWriteTransfer
0x180001edb  jmp     loc_180001C48
0x180001ee0  mov     edi, 57h ; 'W'
0x180001ee5  lea     r9, aBadFlagsParame; "Bad flags parameter"
0x180001eec  mov     r8d, 2A3h
0x180001ef2  lea     rdx, aPcamonitorproc_1; "PcaMonitorProcess"
0x180001ef9  mov     ecx, 1
0x180001efe  call    AslLogCallPrintf
0x180001f03  jmp     loc_180001E5E
0x180001f08  lea     r9, aFailedToProces; "Failed to process ApplicationName [%d]"
0x180001f0f  mov     r8d, 2BBh
0x180001f15  jmp     short loc_180001E99
0x180001f17  lea     r9, aFailedToProces_0; "Failed to process CommandLine [%d]"
0x180001f1e  mov     r8d, 2C1h
0x180001f24  jmp     loc_180001E99
0x180001f29  lea     r9, aFailedToProces_1; "Failed to process CurrentDirectory [%d]"
0x180001f30  mov     r8d, 2C7h
0x180001f36  jmp     loc_180001E99
0x180001f3b  cmp     eax, 1
0x180001f3e  ja      loc_180001DE8
0x180001f44  lea     eax, [rdi-6ACh]
0x180001f4a  cmp     eax, 2Dh ; '-'
0x180001f4d  ja      loc_180001DE8
0x180001f53  bt      rcx, rax
0x180001f57  jnb     loc_180001DE8
0x180001f5d  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x180001f62  mov     edi, eax
0x180001f64  mov     eax, [rsp+108h+var_B8]
0x180001f68  inc     eax
0x180001f6a  mov     [rsp+108h+var_B8], eax
0x180001f6e  test    edi, edi
0x180001f70  mov     rcx, 200000004201h
0x180001f7a  jnz     short loc_180001F3B
0x180001f7c  jmp     loc_180001D01
0x180001f81  cmp     rsi, r15
0x180001f84  jz      loc_180001DF1
0x180001f8a  mov     rcx, gs:60h
0x180001f93  mov     r8, rsi; P
0x180001f96  xor     edx, edx; Flags
0x180001f98  mov     rcx, [rcx+30h]; HeapHandle
0x180001f9c  call    cs:__imp_RtlFreeHeap
0x180001fa2  jmp     loc_180001DF1
0x180001fa7  mov     rcx, gs:60h
0x180001fb0  xor     edx, edx; Flags
0x180001fb2  mov     rcx, [rcx+30h]; HeapHandle
0x180001fb6  call    cs:__imp_RtlFreeHeap
0x180001fbc  jmp     loc_180001E13
0x18000c1a0  push    rbp
0x18000c1a2  sub     rsp, 50h
0x18000c1a6  mov     rbp, rdx
0x18000c1a9  mov     rcx, [rcx]
0x18000c1ac  mov     ecx, [rcx]; ExceptionCode
0x18000c1ae  call    cs:__imp_I_RpcExceptionFilter
0x18000c1b4  nop
0x18000c1b5  add     rsp, 50h
0x18000c1b9  pop     rbp
0x18000c1ba  retn
```
