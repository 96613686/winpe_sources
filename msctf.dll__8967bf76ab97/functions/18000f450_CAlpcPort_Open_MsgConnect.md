# CAlpcPort::Open(MsgConnect *)

- ea: `0x18000f450`
- end: `0x18000f85c`
- name: `?Open@CAlpcPort@@QEAA_NPEAUMsgConnect@@@Z`
- size: `1036`
- prototype: `bool __fastcall(CAlpcPort *this, struct MsgConnect *, __int64)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f170`
- `0x18000fcf0`
- `0x18002dae0`
- `0x18002f140`
- `0x180034300`

## callees

- `0x18000e160`
- `0x18000e7b0`
- `0x18000f450`
- `0x18000f864`
- `0x18000fac0`
- `0x18005ba10`
- `0x18008ced0`
- `0x18009eaea`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000f54e`
- `ntdll!RtlInitUnicodeString` at `0x18000f54e`
- `ntdll!AlpcGetMessageAttribute` at `0x18000f716`
- `ntdll!AlpcGetMessageAttribute` at `0x18000f729`
- `ntdll!AlpcGetMessageAttribute` at `0x18000f716`
- `ntdll!AlpcGetMessageAttribute` at `0x18000f729`
- `ntdll!NtAlpcConnectPortEx` at `0x18000f6b2`
- `ntdll!NtAlpcConnectPortEx` at `0x18000f6b2`
- `ntdll!NtAlpcQueryInformation` at `0x18000f764`
- `ntdll!NtAlpcQueryInformation` at `0x18000f764`
- `ntdll!NtQueryInformationProcess` at `0x18000f4ed`
- `ntdll!NtQueryInformationProcess` at `0x18000f790`
- `ntdll!NtQueryInformationProcess` at `0x18000f4ed`
- `ntdll!NtQueryInformationProcess` at `0x18000f790`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f772`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f660`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000f660`

## pseudocode

```c
bool __fastcall CAlpcPort::Open(CAlpcPort *this, struct MsgConnect *a2, __int64 a3)
{
  int v5; // ecx
  __int64 v6; // rax
  WCHAR *v7; // rcx
  __int64 v8; // r8
  char v9; // si
  struct _ALPC_MESSAGE_ATTRIBUTES *MessageAttributes; // rax
  __int64 MessageAttribute; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  HANDLE CurrentProcess; // rax
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  int v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+80h] [rbp-80h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v22[4]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+B8h] [rbp-48h]
  _OWORD ProcessInformation[3]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v25[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v26; // [rsp+140h] [rbp+40h]
  _QWORD v27[2]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v28[2]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v29[26]; // [rsp+180h] [rbp+80h]
  _BYTE v30[470]; // [rsp+19Ah] [rbp+9Ah] BYREF
  WCHAR StringSecurityDescriptor[29]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v32[470]; // [rsp+3AAh] [rbp+2AAh] BYREF
  WCHAR SourceString[264]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v34[264]; // [rsp+790h] [rbp+690h] BYREF

  if ( (Microsoft_Windows_TSF_msctfEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, ConnectServer_Start, a3, 1, v27);
  memset_0(SourceString, 0, 0x208u);
  v34[0] = 0;
  GetThreadDesktopName(v34);
  ReturnLength = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  if ( NtQueryInformationProcess(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         ProcessBasicInformation,
         ProcessInformation,
         0x30u,
         &ReturnLength) )
  {
    v5 = -1;
  }
  else
  {
    v5 = *(_DWORD *)(*((_QWORD *)&ProcessInformation[0] + 1) + 704LL);
  }
  StringCchPrintfW(SourceString, 0x104u, L"%s%s%d", L"\\BaseNamedObjects\\msctf.server", v34, v5);
  SourceString[259] = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v22[0] = 48;
  v22[3] = 0;
  v22[2] = &DestinationString;
  v22[1] = 0;
  v26 = 0;
  v6 = *(_QWORD *)this;
  v23 = 0;
  memset(v25, 0, sizeof(v25));
  (*(void (__fastcall **)(CAlpcPort *, _OWORD *))(v6 + 8))(this, v25);
  v20 = 64;
  wcscpy(StringSecurityDescriptor, L"S:(ML;;NRNWNX;;;S-6-8208)");
  memset_0(v32, 0, 0x1CEu);
  v28[0] = *(_OWORD *)L"S:(ML;;NRNWNX;;;S-1-16-8192)";
  v28[1] = *(_OWORD *)L"RNWNX;;;S-1-16-8192)";
  *(_OWORD *)v29 = *(_OWORD *)L"S-1-16-8192)";
  *(_OWORD *)&v29[10] = *(_OWORD *)L"6-8192)";
  memset_0(v30, 0, 0x1CEu);
  SecurityDescriptor = 0;
  if ( IsUserOOBE() )
    v7 = (WCHAR *)v28;
  else
    v7 = StringSecurityDescriptor;
  ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0);
  v19 = -10000000;
  if ( (unsigned int)NtAlpcConnectPortEx(
                       (char *)this + 8,
                       v22,
                       0,
                       v25,
                       0x20000,
                       SecurityDescriptor,
                       a2,
                       &v20,
                       0,
                       0,
                       &v19) )
    goto LABEL_8;
  v9 = 0;
  MessageAttributes = CreateMessageAttributes(0x70000000u);
  *((_QWORD *)this + 2) = MessageAttributes;
  if ( MessageAttributes )
  {
    MessageAttribute = AlpcGetMessageAttribute(MessageAttributes, 0x20000000);
    v12 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 3) = MessageAttribute;
    *((_QWORD *)this + 4) = AlpcGetMessageAttribute(v12, 0x40000000);
    v9 = 1;
  }
  v13 = *((_QWORD *)this + 1);
  ReturnLength = 0;
  v18 = 8;
  v27[0] = 0;
  if ( (int)NtAlpcQueryInformation(v13, 12, v27, 8, &v18) < 0
    || (CurrentProcess = GetCurrentProcess(),
        NtQueryInformationProcess(CurrentProcess, ProcessSessionInformation, &ReturnLength, 4u, 0) < 0)
    || LODWORD(v27[0]) != ReturnLength
    || !v9 )
  {
LABEL_8:
    CAlpcPort::Close(this);
    if ( (Microsoft_Windows_TSF_msctfEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, FailedConnectServer, v8, 1, v27);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (Microsoft_Windows_TSF_msctfEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_TSF_msctf_Context, ConnectServer_End, v8, 1, v27);
  return *((_QWORD *)this + 1) != 0;
}

```

## disassembly

```asm
0x18000f450  mov     [rsp-8+arg_10], rbx
0x18000f455  mov     [rsp-8+arg_18], rsi
0x18000f45a  push    rbp
0x18000f45b  push    rdi
0x18000f45c  push    r14
0x18000f45e  lea     rbp, [rsp-8B0h]
0x18000f466  sub     rsp, 9B0h
0x18000f46d  mov     rax, cs:__security_cookie
0x18000f474  xor     rax, rsp
0x18000f477  mov     [rbp+8C0h+var_20], rax
0x18000f47e  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 2
0x18000f485  mov     rsi, rdx
0x18000f488  mov     rdi, rcx
0x18000f48b  jnz     loc_18000F804
0x18000f491  xor     edx, edx; Val
0x18000f493  lea     rcx, [rbp+8C0h+SourceString]; void *
0x18000f49a  mov     r8d, 208h; Size
0x18000f4a0  call    memset_0
0x18000f4a5  xor     r14d, r14d
0x18000f4a8  lea     rcx, [rbp+8C0h+var_230]; unsigned __int16 *
0x18000f4af  mov     [rbp+8C0h+var_230], r14w
0x18000f4b7  call    ?GetThreadDesktopName@@YAHPEAGK@Z; GetThreadDesktopName(ushort *,ulong)
0x18000f4bc  xorps   xmm0, xmm0
0x18000f4bf  mov     [rsp+9C0h+var_960], r14d
0x18000f4c4  lea     rax, [rsp+9C0h+var_960]
0x18000f4c9  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18000f4cf  lea     r8, [rbp+8C0h+ProcessInformation]; ProcessInformation
0x18000f4d3  mov     [rsp+9C0h+ReturnLength], rax; ReturnLength
0x18000f4d8  xor     edx, edx; ProcessInformationClass
0x18000f4da  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000f4e1  movups  [rbp+8C0h+ProcessInformation], xmm0
0x18000f4e5  movups  [rbp+8C0h+var_8E8], xmm0
0x18000f4e9  movups  [rbp+8C0h+var_8D8], xmm0
0x18000f4ed  call    cs:__imp_NtQueryInformationProcess
0x18000f4f3  test    eax, eax
0x18000f4f5  jnz     loc_18000F82B
0x18000f4fb  mov     rax, qword ptr [rbp+8C0h+ProcessInformation+8]
0x18000f4ff  mov     ecx, [rax+2C0h]
0x18000f505  mov     dword ptr [rsp+9C0h+var_998], ecx
0x18000f509  lea     rax, [rbp+8C0h+var_230]
0x18000f510  lea     rcx, [rbp+8C0h+SourceString]; unsigned __int16 *
0x18000f517  mov     [rsp+9C0h+ReturnLength], rax
0x18000f51c  lea     r9, aBasenamedobjec; "\\BaseNamedObjects\\msctf.server"
0x18000f523  mov     edx, 104h; unsigned __int64
0x18000f528  lea     r8, aSSD; "%s%s%d"
0x18000f52f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f534  xorps   xmm0, xmm0
0x18000f537  mov     [rbp+8C0h+var_23A], r14w
0x18000f53f  lea     rdx, [rbp+8C0h+SourceString]; SourceString
0x18000f546  lea     rcx, [rbp+8C0h+DestinationString]; DestinationString
0x18000f54a  movups  xmmword ptr [rbp+8C0h+DestinationString.Length], xmm0
0x18000f54e  call    cs:__imp_RtlInitUnicodeString
0x18000f554  xorps   xmm1, xmm1
0x18000f557  mov     [rbp+8C0h+var_928], 30h ; '0'
0x18000f55f  lea     rax, [rbp+8C0h+DestinationString]
0x18000f563  mov     [rbp+8C0h+var_910], r14
0x18000f567  mov     [rbp+8C0h+var_918], rax
0x18000f56b  lea     rdx, [rbp+8C0h+var_8C0]
0x18000f56f  xor     eax, eax
0x18000f571  mov     [rbp+8C0h+var_920], r14
0x18000f575  mov     [rbp+8C0h+var_880], rax
0x18000f579  xorps   xmm0, xmm0
0x18000f57c  mov     rax, [rdi]
0x18000f57f  mov     rcx, rdi
0x18000f582  movdqu  [rbp+8C0h+var_908], xmm0
0x18000f587  movups  [rbp+8C0h+var_8C0], xmm1
0x18000f58b  mov     rax, [rax+8]
0x18000f58f  movups  [rbp+8C0h+var_8B0], xmm1
0x18000f593  movups  [rbp+8C0h+var_8A0], xmm1
0x18000f597  movups  [rbp+8C0h+var_890], xmm1
0x18000f59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a0  movups  xmm0, xmmword ptr cs:aSMlNrnwnxS1168_0; "S:(ML;;NRNWNX;;;S-1-16-8208)"
0x18000f5a7  xor     edx, edx; Val
0x18000f5a9  mov     r8d, 1CEh; Size
0x18000f5af  movups  xmm1, xmmword ptr cs:aSMlNrnwnxS1168_0+10h; "RNWNX;;;S-1-16-8208)"
0x18000f5b6  lea     rcx, [rbp+8C0h+var_616]; void *
0x18000f5bd  mov     [rbp+8C0h+var_940], 40h ; '@'
0x18000f5c5  movaps  xmmword ptr [rbp+8C0h+StringSecurityDescriptor], xmm0
0x18000f5cc  movups  xmm0, xmmword ptr cs:aSMlNrnwnxS1168_0+20h; "S-1-16-8208)"
0x18000f5d3  movaps  [rbp+8C0h+var_640], xmm1
0x18000f5da  movups  xmm1, xmmword ptr cs:aSMlNrnwnxS1168_0+2Ah; "6-8208)"
0x18000f5e1  movaps  [rbp+8C0h+var_630], xmm0
0x18000f5e8  movups  [rbp+8C0h+var_630+0Ah], xmm1
0x18000f5ef  call    memset_0
0x18000f5f4  movups  xmm0, xmmword ptr cs:aSMlNrnwnxS1168; "S:(ML;;NRNWNX;;;S-1-16-8192)"
0x18000f5fb  xor     edx, edx; Val
0x18000f5fd  mov     r8d, 1CEh; Size
0x18000f603  movups  xmm1, xmmword ptr cs:aSMlNrnwnxS1168+10h; "RNWNX;;;S-1-16-8192)"
0x18000f60a  lea     rcx, [rbp+8C0h+var_826]; void *
0x18000f611  movaps  [rbp+8C0h+var_860], xmm0
0x18000f615  movups  xmm0, xmmword ptr cs:aSMlNrnwnxS1168+20h; "S-1-16-8192)"
0x18000f61c  movaps  [rbp+8C0h+var_850], xmm1
0x18000f620  movups  xmm1, xmmword ptr cs:aSMlNrnwnxS1168+2Ah; "6-8192)"
0x18000f627  movaps  xmmword ptr [rbp+8C0h+var_840], xmm0
0x18000f62e  movups  xmmword ptr [rbp+8C0h+var_840+0Ah], xmm1
0x18000f635  call    memset_0
0x18000f63a  mov     [rsp+9C0h+SecurityDescriptor], r14
0x18000f63f  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18000f644  xor     r9d, r9d; SecurityDescriptorSize
0x18000f647  lea     r8, [rsp+9C0h+SecurityDescriptor]; SecurityDescriptor
0x18000f64c  mov     edx, 1; StringSDRevision
0x18000f651  test    al, al
0x18000f653  jnz     loc_18000F7FB
0x18000f659  lea     rcx, [rbp+8C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000f660  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000f666  lea     rax, [rsp+9C0h+var_948]
0x18000f66b  mov     [rsp+9C0h+var_948], 0FFFFFFFFFF676980h
0x18000f674  mov     [rsp+9C0h+var_970], rax
0x18000f679  lea     r9, [rbp+8C0h+var_8C0]
0x18000f67d  mov     [rsp+9C0h+var_978], r14
0x18000f682  lea     rax, [rbp+8C0h+var_940]
0x18000f686  mov     [rsp+9C0h+var_980], r14
0x18000f68b  lea     rdx, [rbp+8C0h+var_928]
0x18000f68f  mov     [rsp+9C0h+var_988], rax
0x18000f694  lea     rcx, [rdi+8]
0x18000f698  mov     rax, [rsp+9C0h+SecurityDescriptor]
0x18000f69d  xor     r8d, r8d
0x18000f6a0  mov     [rsp+9C0h+var_990], rsi
0x18000f6a5  mov     [rsp+9C0h+var_998], rax
0x18000f6aa  mov     dword ptr [rsp+9C0h+ReturnLength], 20000h
0x18000f6b2  call    cs:__imp_NtAlpcConnectPortEx
0x18000f6b8  test    eax, eax
0x18000f6ba  jz      short loc_18000F6F8
0x18000f6bc  mov     rcx, rdi; this
0x18000f6bf  call    ?Close@CAlpcPort@@QEAAXXZ; CAlpcPort::Close(void)
0x18000f6c4  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 4
0x18000f6cb  jz      loc_18000F7B4
0x18000f6d1  lea     rax, [rbp+8C0h+var_870]
0x18000f6d5  mov     r9d, 1
0x18000f6db  lea     rdx, FailedConnectServer
0x18000f6e2  mov     [rsp+9C0h+ReturnLength], rax
0x18000f6e7  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18000f6ee  call    McGenEventWrite_EventWriteTransfer
0x18000f6f3  jmp     loc_18000F7B4
0x18000f6f8  mov     ecx, 70000000h; unsigned int
0x18000f6fd  xor     sil, sil
0x18000f700  call    ?CreateMessageAttributes@@YAPEAU_ALPC_MESSAGE_ATTRIBUTES@@K@Z; CreateMessageAttributes(ulong)
0x18000f705  mov     [rdi+10h], rax
0x18000f709  test    rax, rax
0x18000f70c  jz      short loc_18000F736
0x18000f70e  mov     edx, 20000000h
0x18000f713  mov     rcx, rax
0x18000f716  call    cs:__imp_AlpcGetMessageAttribute
0x18000f71c  mov     rcx, [rdi+10h]
0x18000f720  mov     edx, 40000000h
0x18000f725  mov     [rdi+18h], rax
0x18000f729  call    cs:__imp_AlpcGetMessageAttribute
0x18000f72f  mov     [rdi+20h], rax
0x18000f733  mov     sil, 1
0x18000f736  mov     rcx, [rdi+8]
0x18000f73a  lea     rax, [rsp+9C0h+var_950]
0x18000f73f  mov     r9d, 8
0x18000f745  mov     [rsp+9C0h+ReturnLength], rax
0x18000f74a  lea     r8, [rbp+8C0h+var_870]
0x18000f74e  mov     [rsp+9C0h+var_960], r14d
0x18000f753  mov     edx, 0Ch
0x18000f758  mov     [rsp+9C0h+var_950], 8
0x18000f760  mov     [rbp+8C0h+var_870], r14
0x18000f764  call    cs:__imp_NtAlpcQueryInformation
0x18000f76a  test    eax, eax
0x18000f76c  js      loc_18000F6BC
0x18000f772  call    cs:__imp_GetCurrentProcess
0x18000f778  mov     r9d, 4; ProcessInformationLength
0x18000f77e  mov     [rsp+9C0h+ReturnLength], r14; ReturnLength
0x18000f783  mov     rcx, rax; ProcessHandle
0x18000f786  lea     r8, [rsp+9C0h+var_960]; ProcessInformation
0x18000f78b  mov     edx, 18h; ProcessInformationClass
0x18000f790  call    cs:__imp_NtQueryInformationProcess
0x18000f796  test    eax, eax
0x18000f798  js      loc_18000F6BC
0x18000f79e  mov     eax, [rsp+9C0h+var_960]
0x18000f7a2  cmp     dword ptr [rbp+8C0h+var_870], eax
0x18000f7a5  jnz     loc_18000F6BC
0x18000f7ab  test    sil, sil
0x18000f7ae  jz      loc_18000F6BC
0x18000f7b4  mov     rcx, [rsp+9C0h+SecurityDescriptor]; hMem
0x18000f7b9  test    rcx, rcx
0x18000f7bc  jz      short loc_18000F7C4
0x18000f7be  call    cs:__imp_LocalFree
0x18000f7c4  test    cs:Microsoft_Windows_TSF_msctfEnableBits, 2
0x18000f7cb  jnz     short loc_18000F835
0x18000f7cd  cmp     [rdi+8], r14
0x18000f7d1  setnz   al
0x18000f7d4  mov     rcx, [rbp+8C0h+var_20]
0x18000f7db  xor     rcx, rsp; StackCookie
0x18000f7de  call    __security_check_cookie
0x18000f7e3  lea     r11, [rsp+9C0h+var_10]
0x18000f7eb  mov     rbx, [r11+30h]
0x18000f7ef  mov     rsi, [r11+38h]
0x18000f7f3  mov     rsp, r11
0x18000f7f6  pop     r14
0x18000f7f8  pop     rdi
0x18000f7f9  pop     rbp
0x18000f7fa  retn
0x18000f7fb  lea     rcx, [rbp+8C0h+var_860]
0x18000f7ff  jmp     loc_18000F660
0x18000f804  lea     rax, [rbp+8C0h+var_870]
0x18000f808  mov     r9d, 1
0x18000f80e  lea     rdx, ConnectServer_Start
0x18000f815  mov     [rsp+9C0h+ReturnLength], rax
0x18000f81a  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18000f821  call    McGenEventWrite_EventWriteTransfer
0x18000f826  jmp     loc_18000F491
0x18000f82b  mov     ecx, 0FFFFFFFFh
0x18000f830  jmp     loc_18000F505
0x18000f835  lea     rax, [rbp+8C0h+var_870]
0x18000f839  mov     r9d, 1
0x18000f83f  lea     rdx, ConnectServer_End
0x18000f846  mov     [rsp+9C0h+ReturnLength], rax
0x18000f84b  lea     rcx, Microsoft_Windows_TSF_msctf_Context
0x18000f852  call    McGenEventWrite_EventWriteTransfer
0x18000f857  jmp     loc_18000F7CD
```
