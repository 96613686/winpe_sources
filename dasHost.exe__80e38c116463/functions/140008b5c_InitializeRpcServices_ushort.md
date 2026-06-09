# InitializeRpcServices(ushort *)

- ea: `0x140008b5c`
- end: `0x140008d73`
- name: `?InitializeRpcServices@@YAJPEAG@Z`
- size: `535`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140010928`

## callees

- `0x140001570`
- `0x140008b5c`
- `0x140008d7c`
- `0x140008eec`
- `0x140008f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140008ca1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140008ca1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008cb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008cb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ce0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008cc0`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140008c33`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140008c33`
- `RPCRT4!I_RpcMapWin32Status` at `0x140008c46`
- `RPCRT4!I_RpcMapWin32Status` at `0x140008c46`
- `RPCRT4!RpcServerRegisterIf3` at `0x140008c7b`
- `RPCRT4!RpcServerRegisterIf3` at `0x140008c7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140008bef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140008bef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008cf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008cf0`

## pseudocode

```c
__int64 __fastcall InitializeRpcServices(unsigned __int16 *a1, int a2, int a3)
{
  unsigned __int16 *v4; // rcx
  int EndpoingString; // edi
  int v6; // edx
  signed int LastError; // ebx
  int v8; // r8d
  RPC_STATUS v9; // eax
  DWORD v10; // eax
  HANDLE EventW; // rax
  HANDLE ProcessHeap; // rax
  char v13; // al
  int v15; // [rsp+28h] [rbp-70h]
  RPC_WSTR Endpoint; // [rsp+40h] [rbp-58h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-50h] BYREF
  WCHAR StringSecurityDescriptor[16]; // [rsp+50h] [rbp-48h] BYREF

  Endpoint = 0;
  SecurityDescriptor = 0;
  wcscpy(StringSecurityDescriptor, L"D:(A;;A;;;SY)");
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 12, &WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    EndpoingString = 0;
    LastError = GetLastError();
    goto LABEL_16;
  }
  LastError = 0;
  EndpoingString = MakeEndpoingString(v4, a1, &Endpoint);
  if ( EndpoingString >= 0 )
  {
    v9 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, Endpoint, 0);
    if ( v9 && v9 != 1740 || (v15 = 0, (v9 = RpcServerRegisterIf3(qword_14001E9B0, 0, 0, 41, 1234)) != 0) )
    {
      v10 = I_RpcMapWin32Status(v9);
LABEL_13:
      LastError = v10;
      goto LABEL_14;
    }
    g_bDasHostCommandAndControlRegistered = 1;
    g_hRpcEvent = 0;
    EventW = CreateEventW(0, 1, 0, a1);
    g_hRpcEvent = EventW;
    if ( !EventW || !SetEvent(EventW) )
    {
      v10 = GetLastError();
      goto LABEL_13;
    }
  }
LABEL_14:
  if ( Endpoint )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Endpoint);
  }
LABEL_16:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( EndpoingString >= 0 )
      v13 = LastError;
    else
      v13 = EndpoingString;
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v6,
      v8,
      13,
      &WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids,
      v15,
      v13);
  }
  if ( EndpoingString < 0 )
    return (unsigned int)EndpoingString;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140008b5c  mov     r11, rsp
0x140008b5f  mov     [r11+10h], rbx
0x140008b63  mov     [r11+18h], rbp
0x140008b67  push    rdi
0x140008b68  push    r12
0x140008b6a  push    r13
0x140008b6c  sub     rsp, 80h
0x140008b73  mov     rax, cs:__security_cookie
0x140008b7a  xor     rax, rsp
0x140008b7d  mov     [rsp+98h+var_28], rax
0x140008b82  movups  xmm0, xmmword ptr cs:aDAGaSy; "D:(A;;GA;;;SY)"
0x140008b89  mov     rbp, rcx
0x140008b8c  mov     qword ptr [r11-58h], 0
0x140008b94  movups  xmm1, xmmword ptr cs:aDAGaSy+0Eh; "A;;;SY)"
0x140008b9b  mov     qword ptr [r11-50h], 0
0x140008ba3  movups  xmmword ptr [rsp+98h+StringSecurityDescriptor], xmm0
0x140008ba8  movups  xmmword ptr [rsp+98h+StringSecurityDescriptor+0Eh], xmm1
0x140008bad  lea     r12, WPP_RECORDER_INITIALIZED
0x140008bb4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008bbb  lea     r13, WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids
0x140008bc2  jz      short loc_140008BDE
0x140008bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bcb  mov     r9d, 0Ch; int
0x140008bd1  mov     [r11-78h], r13
0x140008bd5  mov     rcx, [rcx+28h]; int
0x140008bd9  call    WPP_RECORDER_SF_s
0x140008bde  xor     r9d, r9d; SecurityDescriptorSize
0x140008be1  lea     r8, [rsp+98h+SecurityDescriptor]; SecurityDescriptor
0x140008be6  lea     rcx, [rsp+98h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140008beb  lea     edx, [r9+1]; StringSDRevision
0x140008bef  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140008bf5  test    eax, eax
0x140008bf7  jnz     short loc_140008C08
0x140008bf9  xor     edi, edi
0x140008bfb  call    cs:__imp_GetLastError
0x140008c01  mov     ebx, eax
0x140008c03  jmp     loc_140008CE6
0x140008c08  lea     r8, [rsp+98h+Endpoint]; unsigned __int16 **
0x140008c0d  mov     rdx, rbp; unsigned __int16 *
0x140008c10  xor     ebx, ebx
0x140008c12  call    ?MakeEndpoingString@@YAJPEAG0PEAPEAG@Z; MakeEndpoingString(ushort *,ushort *,ushort * *)
0x140008c17  mov     edi, eax
0x140008c19  test    eax, eax
0x140008c1b  js      loc_140008CC8
0x140008c21  mov     r8, [rsp+98h+Endpoint]; Endpoint
0x140008c26  lea     edx, [rbx+0Ah]; MaxCalls
0x140008c29  xor     r9d, r9d; SecurityDescriptor
0x140008c2c  lea     rcx, ProtSeq; "ncalrpc"
0x140008c33  call    cs:__imp_RpcServerUseProtseqEpW
0x140008c39  test    eax, eax
0x140008c3b  jz      short loc_140008C4E
0x140008c3d  cmp     eax, 6CCh
0x140008c42  jz      short loc_140008C4E
0x140008c44  mov     ecx, eax; Status
0x140008c46  call    cs:__imp_I_RpcMapWin32Status
0x140008c4c  jmp     short loc_140008CC6
0x140008c4e  mov     rax, [rsp+98h+SecurityDescriptor]
0x140008c53  lea     rcx, qword_14001E9B0
0x140008c5a  mov     [rsp+98h+var_60], rax
0x140008c5f  mov     r9d, 29h ; ')'
0x140008c65  mov     qword ptr [rsp+98h+var_68], rbx
0x140008c6a  xor     r8d, r8d
0x140008c6d  mov     [rsp+98h+var_70], ebx; int
0x140008c71  xor     edx, edx
0x140008c73  mov     dword ptr [rsp+98h+MessageGuid], 4D2h
0x140008c7b  call    cs:__imp_RpcServerRegisterIf3
0x140008c81  test    eax, eax
0x140008c83  jnz     short loc_140008C44
0x140008c85  mov     r9, rbp; lpName
0x140008c88  mov     cs:?g_bDasHostCommandAndControlRegistered@@3HA, 1; int g_bDasHostCommandAndControlRegistered
0x140008c92  xor     r8d, r8d; bInitialState
0x140008c95  mov     cs:?g_hRpcEvent@@3PEAXEA, rbx; void * g_hRpcEvent
0x140008c9c  lea     edx, [rax+1]; bManualReset
0x140008c9f  xor     ecx, ecx; lpEventAttributes
0x140008ca1  call    cs:__imp_CreateEventW
0x140008ca7  mov     cs:?g_hRpcEvent@@3PEAXEA, rax; void * g_hRpcEvent
0x140008cae  test    rax, rax
0x140008cb1  jz      short loc_140008CC0
0x140008cb3  mov     rcx, rax; hEvent
0x140008cb6  call    cs:__imp_SetEvent
0x140008cbc  test    eax, eax
0x140008cbe  jnz     short loc_140008CC8
0x140008cc0  call    cs:__imp_GetLastError
0x140008cc6  mov     ebx, eax
0x140008cc8  cmp     [rsp+98h+Endpoint], 0
0x140008cce  jz      short loc_140008CE6
0x140008cd0  call    cs:__imp_GetProcessHeap
0x140008cd6  mov     r8, [rsp+98h+Endpoint]; lpMem
0x140008cdb  xor     edx, edx; dwFlags
0x140008cdd  mov     rcx, rax; hHeap
0x140008ce0  call    cs:__imp_HeapFree
0x140008ce6  mov     rcx, [rsp+98h+SecurityDescriptor]; hMem
0x140008ceb  test    rcx, rcx
0x140008cee  jz      short loc_140008CF6
0x140008cf0  call    cs:__imp_LocalFree
0x140008cf6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008cfd  jz      short loc_140008D36
0x140008cff  test    edi, edi
0x140008d01  jns     short loc_140008D07
0x140008d03  mov     eax, edi
0x140008d05  jmp     short loc_140008D17
0x140008d07  test    ebx, ebx
0x140008d09  jg      short loc_140008D0F
0x140008d0b  mov     eax, ebx
0x140008d0d  jmp     short loc_140008D17
0x140008d0f  movzx   eax, bx
0x140008d12  or      eax, 80070000h
0x140008d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d1e  mov     r9d, 0Dh; int
0x140008d24  mov     dword ptr [rsp+98h+var_68], eax; char
0x140008d28  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x140008d2d  mov     rcx, [rcx+28h]; int
0x140008d31  call    WPP_RECORDER_SF_sd
0x140008d36  test    edi, edi
0x140008d38  jns     short loc_140008D3E
0x140008d3a  mov     eax, edi
0x140008d3c  jmp     short loc_140008D4D
0x140008d3e  test    ebx, ebx
0x140008d40  jle     short loc_140008D4B
0x140008d42  movzx   ebx, bx
0x140008d45  or      ebx, 80070000h
0x140008d4b  mov     eax, ebx
0x140008d4d  mov     rcx, [rsp+98h+var_28]
0x140008d52  xor     rcx, rsp; StackCookie
0x140008d55  call    __security_check_cookie
0x140008d5a  lea     r11, [rsp+98h+var_18]
0x140008d62  mov     rbx, [r11+28h]
0x140008d66  mov     rbp, [r11+30h]
0x140008d6a  mov     rsp, r11
0x140008d6d  pop     r13
0x140008d6f  pop     r12
0x140008d71  pop     rdi
0x140008d72  retn
```
