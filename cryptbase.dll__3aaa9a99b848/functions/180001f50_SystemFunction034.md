# SystemFunction034

- ea: `0x180001f50`
- end: `0x18000234a`
- name: `SystemFunction034`
- size: `1018`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002550`

## callees

- `0x180001f50`
- `0x180003b50`

## import_xrefs

- `ntdll!NtClose` at `0x1800022e5`
- `ntdll!NtClose` at `0x1800022e5`
- `ntdll!NtOpenFile` at `0x18000221b`
- `ntdll!NtOpenFile` at `0x18000221b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180002198`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800021ad`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180002198`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800021ad`
- `ntdll!RtlAllocateHeap` at `0x18000212f`
- `ntdll!RtlAllocateHeap` at `0x18000212f`
- `ntdll!RtlInitUnicodeString` at `0x1800020bd`
- `ntdll!RtlInitUnicodeString` at `0x1800020ea`
- `ntdll!RtlInitUnicodeString` at `0x180002101`
- `ntdll!RtlInitUnicodeString` at `0x1800020bd`
- `ntdll!RtlInitUnicodeString` at `0x1800020ea`
- `ntdll!RtlInitUnicodeString` at `0x180002101`
- `ntdll!NtFsControlFile` at `0x1800022a2`
- `ntdll!NtFsControlFile` at `0x1800022a2`
- `ntdll!RtlFreeHeap` at `0x18000223d`
- `ntdll!RtlFreeHeap` at `0x18000223d`
- `ntdll!RtlCopyUnicodeString` at `0x180002182`
- `ntdll!RtlCopyUnicodeString` at `0x180002182`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800022cb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800022cb`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ff0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002033`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002054`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002158`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800021cc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002315`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ff0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002033`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002054`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002158`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800021cc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002315`
- `RPCRT4!I_RpcBindingIsServerLocal` at `0x180002088`
- `RPCRT4!I_RpcBindingIsServerLocal` at `0x180002088`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180001fe2`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180001fe2`
- `RPCRT4!RpcStringFreeW` at `0x180002046`
- `RPCRT4!RpcStringFreeW` at `0x18000214a`
- `RPCRT4!RpcStringFreeW` at `0x1800021be`
- `RPCRT4!RpcStringFreeW` at `0x180002307`
- `RPCRT4!RpcStringFreeW` at `0x180002046`
- `RPCRT4!RpcStringFreeW` at `0x18000214a`
- `RPCRT4!RpcStringFreeW` at `0x1800021be`
- `RPCRT4!RpcStringFreeW` at `0x180002307`
- `RPCRT4!RpcStringBindingParseW` at `0x180002025`
- `RPCRT4!RpcStringBindingParseW` at `0x180002025`

## pseudocode

```c
int __fastcall SystemFunction034(void *a1, void **a2, _OWORD *a3)
{
  RPC_STATUS v6; // eax
  int result; // eax
  RPC_STATUS v8; // eax
  int v9; // ebx
  RPC_STATUS v10; // eax
  RPC_WSTR i; // rdx
  USHORT v12; // bx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // eax
  void *v15; // rcx
  RPC_STATUS v16; // eax
  RPC_WSTR NetworkAddr; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR StringBinding; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING Source; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD InputBuffer[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v27; // [rsp+108h] [rbp+8h]
  _OWORD OutputBuffer[6]; // [rsp+110h] [rbp+10h] BYREF

  *a2 = 0;
  StringBinding = 0;
  NetworkAddr = 0;
  v27 = 0;
  memset(&ObjectAttributes, 0, 44);
  v18 = 0;
  DestinationString = 0;
  SourceString = 0;
  Source = 0;
  Destination = 0;
  IoStatusBlock = 0;
  memset(InputBuffer, 0, sizeof(InputBuffer));
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  v6 = RpcBindingToStringBindingW(a1, &StringBinding);
  result = I_RpcMapWin32Status(v6);
  if ( result >= 0 )
  {
    v8 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
    v9 = I_RpcMapWin32Status(v8);
    v10 = RpcStringFreeW(&StringBinding);
    I_RpcMapWin32Status(v10);
    if ( v9 < 0 )
      return v9;
    if ( NetworkAddr && *NetworkAddr && ((unsigned int)I_RpcBindingIsServerLocal(a1, &v18) || !v18) )
    {
      for ( i = NetworkAddr; *i == 92; ++i )
        ;
      RtlInitUnicodeString(&DestinationString, i);
      if ( DestinationString.Length != 2 || *DestinationString.Buffer != 46 )
      {
        RtlInitUnicodeString(&SourceString, L"\\Device\\LanmanRedirector\\");
        RtlInitUnicodeString(&Source, L"\\IPC$");
        v12 = DestinationString.Length + SourceString.Length + Source.Length;
        Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        if ( !Destination.Buffer )
        {
          v13 = RpcStringFreeW(&NetworkAddr);
          I_RpcMapWin32Status(v13);
          return -1073741670;
        }
        Destination.Length = 0;
        Destination.MaximumLength = v12;
        RtlCopyUnicodeString(&Destination, &SourceString);
        RtlAppendUnicodeStringToString(&Destination, &DestinationString);
        RtlAppendUnicodeStringToString(&Destination, &Source);
        v14 = RpcStringFreeW(&NetworkAddr);
        I_RpcMapWin32Status(v14);
        ObjectAttributes.ObjectName = &Destination;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v9 = NtOpenFile(a2, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x90u);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
        Destination.Buffer = 0;
        if ( v9 < 0 )
          goto LABEL_18;
        v15 = *a2;
        *(_QWORD *)((char *)InputBuffer + 4) = 0x200000006LL;
        v9 = NtFsControlFile(v15, 0, 0, 0, &IoStatusBlock, 0x1401A3u, InputBuffer, 0x24u, OutputBuffer, 0x60u);
        if ( v9 < 0 )
        {
LABEL_17:
          NtClose(*a2);
LABEL_18:
          *a2 = 0;
          return v9;
        }
        *a3 = *(_OWORD *)((char *)&OutputBuffer[4] + 4);
        if ( RtlCompareMemory(a3, &ErrorSessionKey, 0x10u) == 16 )
        {
          v9 = -1073741310;
          goto LABEL_17;
        }
        return v9;
      }
    }
    *a3 = LocalSessionKey;
    v16 = RpcStringFreeW(&NetworkAddr);
    I_RpcMapWin32Status(v16);
    return 1073741830;
  }
  return result;
}

```

## disassembly

```asm
0x180001f50  push    rbp
0x180001f52  push    rsi
0x180001f53  push    rdi
0x180001f54  push    r14
0x180001f56  push    r15
0x180001f58  lea     rbp, [rsp-80h]
0x180001f5d  sub     rsp, 180h
0x180001f64  mov     rax, cs:__security_cookie
0x180001f6b  xor     rax, rsp
0x180001f6e  mov     [rbp+0A0h+var_30], rax
0x180001f72  xorps   xmm0, xmm0
0x180001f75  xorps   xmm1, xmm1
0x180001f78  xor     r15d, r15d
0x180001f7b  mov     rsi, rdx
0x180001f7e  mov     [rdx], r15
0x180001f81  xor     eax, eax
0x180001f83  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x180001f87  lea     rdx, [rsp+1A0h+StringBinding]; StringBinding
0x180001f8c  mov     [rsp+1A0h+StringBinding], r15
0x180001f91  mov     rdi, r8
0x180001f94  mov     [rsp+1A0h+NetworkAddr], r15
0x180001f99  mov     r14, rcx
0x180001f9c  mov     [rbp+0A0h+var_98], eax
0x180001f9f  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x180001fa3  mov     [rsp+1A0h+var_148], r15d
0x180001fa8  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x180001fac  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x180001fb1  movups  xmmword ptr [rbp+0A0h+SourceString.Length], xmm1
0x180001fb5  movups  xmmword ptr [rbp+0A0h+Source.Length], xmm0
0x180001fb9  movups  xmmword ptr [rsp+1A0h+Destination.Length], xmm1
0x180001fbe  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x180001fc2  movups  [rbp+0A0h+var_B8], xmm1
0x180001fc6  movups  [rbp+0A0h+var_A8], xmm1
0x180001fca  movups  [rbp+0A0h+var_90], xmm0
0x180001fce  movups  [rbp+0A0h+var_80], xmm0
0x180001fd2  movups  [rbp+0A0h+var_70], xmm0
0x180001fd6  movups  [rbp+0A0h+var_60], xmm0
0x180001fda  movups  [rbp+0A0h+var_50], xmm0
0x180001fde  movups  [rbp+0A0h+var_40], xmm0
0x180001fe2  call    cs:__imp_RpcBindingToStringBindingW
0x180001fe9  nop     dword ptr [rax+rax+00h]
0x180001fee  mov     ecx, eax; Status
0x180001ff0  call    cs:__imp_I_RpcMapWin32Status
0x180001ff7  nop     dword ptr [rax+rax+00h]
0x180001ffc  test    eax, eax
0x180001ffe  js      loc_18000232E
0x180002004  mov     rcx, [rsp+1A0h+StringBinding]; StringBinding
0x180002009  lea     r9, [rsp+1A0h+NetworkAddr]; NetworkAddr
0x18000200e  mov     [rsp+1A0h+NetworkOptions], r15; NetworkOptions
0x180002013  xor     r8d, r8d; Protseq
0x180002016  xor     edx, edx; ObjUuid
0x180002018  mov     [rsp+1A0h+Endpoint], r15; Endpoint
0x18000201d  mov     [rsp+1A0h+arg_18], rbx
0x180002025  call    cs:__imp_RpcStringBindingParseW
0x18000202c  nop     dword ptr [rax+rax+00h]
0x180002031  mov     ecx, eax; Status
0x180002033  call    cs:__imp_I_RpcMapWin32Status
0x18000203a  nop     dword ptr [rax+rax+00h]
0x18000203f  lea     rcx, [rsp+1A0h+StringBinding]; String
0x180002044  mov     ebx, eax
0x180002046  call    cs:__imp_RpcStringFreeW
0x18000204d  nop     dword ptr [rax+rax+00h]
0x180002052  mov     ecx, eax; Status
0x180002054  call    cs:__imp_I_RpcMapWin32Status
0x18000205b  nop     dword ptr [rax+rax+00h]
0x180002060  test    ebx, ebx
0x180002062  js      loc_1800022F4
0x180002068  mov     rax, [rsp+1A0h+NetworkAddr]
0x18000206d  test    rax, rax
0x180002070  jz      loc_1800022F8
0x180002076  cmp     [rax], r15w
0x18000207a  jz      loc_1800022F8
0x180002080  lea     rdx, [rsp+1A0h+var_148]
0x180002085  mov     rcx, r14
0x180002088  call    cs:__imp_I_RpcBindingIsServerLocal
0x18000208f  nop     dword ptr [rax+rax+00h]
0x180002094  test    eax, eax
0x180002096  jnz     short loc_1800020A3
0x180002098  cmp     [rsp+1A0h+var_148], r15d
0x18000209d  jnz     loc_1800022F8
0x1800020a3  mov     rdx, [rsp+1A0h+NetworkAddr]
0x1800020a8  cmp     word ptr [rdx], 5Ch ; '\'
0x1800020ac  jnz     short loc_1800020B8
0x1800020ae  add     rdx, 2; SourceString
0x1800020b2  cmp     word ptr [rdx], 5Ch ; '\'
0x1800020b6  jz      short loc_1800020AE
0x1800020b8  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x1800020bd  call    cs:__imp_RtlInitUnicodeString
0x1800020c4  nop     dword ptr [rax+rax+00h]
0x1800020c9  cmp     [rsp+1A0h+DestinationString.Length], 2
0x1800020cf  jnz     short loc_1800020DF
0x1800020d1  mov     rax, [rbp+0A0h+DestinationString.Buffer]
0x1800020d5  cmp     word ptr [rax], 2Eh ; '.'
0x1800020d9  jz      loc_1800022F8
0x1800020df  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\"
0x1800020e6  lea     rcx, [rbp+0A0h+SourceString]; DestinationString
0x1800020ea  call    cs:__imp_RtlInitUnicodeString
0x1800020f1  nop     dword ptr [rax+rax+00h]
0x1800020f6  lea     rdx, aIpc; "\\IPC$"
0x1800020fd  lea     rcx, [rbp+0A0h+Source]; DestinationString
0x180002101  call    cs:__imp_RtlInitUnicodeString
0x180002108  nop     dword ptr [rax+rax+00h]
0x18000210d  movzx   eax, [rbp+0A0h+Source.Length]
0x180002111  xor     edx, edx; Flags
0x180002113  add     ax, [rbp+0A0h+SourceString.Length]
0x180002117  mov     rcx, gs:60h
0x180002120  add     ax, [rsp+1A0h+DestinationString.Length]
0x180002125  movzx   ebx, ax
0x180002128  mov     r8d, ebx; Size
0x18000212b  mov     rcx, [rcx+30h]; HeapHandle
0x18000212f  call    cs:__imp_RtlAllocateHeap
0x180002136  nop     dword ptr [rax+rax+00h]
0x18000213b  mov     [rsp+1A0h+Destination.Buffer], rax
0x180002140  test    rax, rax
0x180002143  jnz     short loc_18000216E
0x180002145  lea     rcx, [rsp+1A0h+NetworkAddr]; String
0x18000214a  call    cs:__imp_RpcStringFreeW
0x180002151  nop     dword ptr [rax+rax+00h]
0x180002156  mov     ecx, eax; Status
0x180002158  call    cs:__imp_I_RpcMapWin32Status
0x18000215f  nop     dword ptr [rax+rax+00h]
0x180002164  mov     eax, 0C000009Ah
0x180002169  jmp     loc_180002326
0x18000216e  lea     rdx, [rbp+0A0h+SourceString]; SourceString
0x180002172  mov     [rsp+1A0h+Destination.Length], r15w
0x180002178  lea     rcx, [rsp+1A0h+Destination]; DestinationString
0x18000217d  mov     [rsp+1A0h+Destination.MaximumLength], bx
0x180002182  call    cs:__imp_RtlCopyUnicodeString
0x180002189  nop     dword ptr [rax+rax+00h]
0x18000218e  lea     rdx, [rsp+1A0h+DestinationString]; Source
0x180002193  lea     rcx, [rsp+1A0h+Destination]; Destination
0x180002198  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000219f  nop     dword ptr [rax+rax+00h]
0x1800021a4  lea     rdx, [rbp+0A0h+Source]; Source
0x1800021a8  lea     rcx, [rsp+1A0h+Destination]; Destination
0x1800021ad  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800021b4  nop     dword ptr [rax+rax+00h]
0x1800021b9  lea     rcx, [rsp+1A0h+NetworkAddr]; String
0x1800021be  call    cs:__imp_RpcStringFreeW
0x1800021c5  nop     dword ptr [rax+rax+00h]
0x1800021ca  mov     ecx, eax; Status
0x1800021cc  call    cs:__imp_I_RpcMapWin32Status
0x1800021d3  nop     dword ptr [rax+rax+00h]
0x1800021d8  lea     rax, [rsp+1A0h+Destination]
0x1800021dd  mov     dword ptr [rsp+1A0h+NetworkOptions], 90h; OpenOptions
0x1800021e5  xorps   xmm0, xmm0
0x1800021e8  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1800021ec  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800021f0  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1800021f7  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800021fb  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r15
0x1800021ff  mov     edx, 100001h; DesiredAccess
0x180002204  mov     [rbp+0A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000220b  mov     rcx, rsi; FileHandle
0x18000220e  mov     dword ptr [rsp+1A0h+Endpoint], 1; ShareAccess
0x180002216  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000221b  call    cs:__imp_NtOpenFile
0x180002222  nop     dword ptr [rax+rax+00h]
0x180002227  mov     rcx, gs:60h
0x180002230  xor     edx, edx; Flags
0x180002232  mov     r8, [rsp+1A0h+Destination.Buffer]; P
0x180002237  mov     ebx, eax
0x180002239  mov     rcx, [rcx+30h]; HeapHandle
0x18000223d  call    cs:__imp_RtlFreeHeap
0x180002244  nop     dword ptr [rax+rax+00h]
0x180002249  mov     [rsp+1A0h+Destination.Buffer], r15
0x18000224e  test    ebx, ebx
0x180002250  js      loc_1800022F1
0x180002256  mov     rcx, [rsi]; FileHandle
0x180002259  lea     rax, [rbp+0A0h+var_90]
0x18000225d  mov     [rsp+1A0h+OutputBufferLength], 60h ; '`'; OutputBufferLength
0x180002265  xor     r9d, r9d; ApcContext
0x180002268  mov     [rsp+1A0h+OutputBuffer], rax; OutputBuffer
0x18000226d  xor     r8d, r8d; ApcRoutine
0x180002270  mov     [rsp+1A0h+InputBufferLength], 24h ; '$'; InputBufferLength
0x180002278  lea     rax, [rbp+0A0h+var_B8]
0x18000227c  mov     [rsp+1A0h+InputBuffer], rax; InputBuffer
0x180002281  xor     edx, edx; Event
0x180002283  lea     rax, [rbp+0A0h+IoStatusBlock]
0x180002287  mov     dword ptr [rsp+1A0h+NetworkOptions], 1401A3h; FsControlCode
0x18000228f  mov     [rsp+1A0h+Endpoint], rax; IoStatusBlock
0x180002294  mov     dword ptr [rbp+0A0h+var_B8+4], 6
0x18000229b  mov     dword ptr [rbp+0A0h+var_B8+8], 2
0x1800022a2  call    cs:__imp_NtFsControlFile
0x1800022a9  nop     dword ptr [rax+rax+00h]
0x1800022ae  mov     ebx, eax
0x1800022b0  test    eax, eax
0x1800022b2  js      short loc_1800022E2
0x1800022b4  movups  xmm0, [rbp+0A0h+var_50+4]
0x1800022b8  mov     r8d, 10h; Length
0x1800022be  lea     rdx, ErrorSessionKey; Source2
0x1800022c5  mov     rcx, rdi; Source1
0x1800022c8  movups  xmmword ptr [rdi], xmm0
0x1800022cb  call    cs:__imp_RtlCompareMemory
0x1800022d2  nop     dword ptr [rax+rax+00h]
0x1800022d7  cmp     rax, 10h
0x1800022db  jnz     short loc_1800022F4
0x1800022dd  mov     ebx, 0C0000202h
0x1800022e2  mov     rcx, [rsi]; Handle
0x1800022e5  call    cs:__imp_NtClose
0x1800022ec  nop     dword ptr [rax+rax+00h]
0x1800022f1  mov     [rsi], r15
0x1800022f4  mov     eax, ebx
0x1800022f6  jmp     short loc_180002326
0x1800022f8  movups  xmm0, cs:LocalSessionKey
0x1800022ff  lea     rcx, [rsp+1A0h+NetworkAddr]; String
0x180002304  movups  xmmword ptr [rdi], xmm0
0x180002307  call    cs:__imp_RpcStringFreeW
0x18000230e  nop     dword ptr [rax+rax+00h]
0x180002313  mov     ecx, eax; Status
0x180002315  call    cs:__imp_I_RpcMapWin32Status
0x18000231c  nop     dword ptr [rax+rax+00h]
0x180002321  mov     eax, 40000006h
0x180002326  mov     rbx, [rsp+1A0h+arg_18]
0x18000232e  mov     rcx, [rbp+0A0h+var_30]
0x180002332  xor     rcx, rsp; StackCookie
0x180002335  call    __security_check_cookie
0x18000233a  add     rsp, 180h
0x180002341  pop     r15
0x180002343  pop     r14
0x180002345  pop     rdi
0x180002346  pop     rsi
0x180002347  pop     rbp
0x180002348  retn
```
