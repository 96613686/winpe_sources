# AlpcConnectionServer::Start(ushort const *)

- ea: `0x180070748`
- end: `0x180070903`
- name: `?Start@AlpcConnectionServer@@QEAAXPEBG@Z`
- size: `443`
- prototype: `void __fastcall(AlpcConnectionServer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006eda0`

## callees

- `0x180003220`
- `0x180004100`
- `0x180070748`
- `0x180070964`

## import_xrefs

- `ntdll!NtClose` at `0x180070897`
- `ntdll!NtClose` at `0x1800708ae`
- `ntdll!NtClose` at `0x1800708c5`
- `ntdll!NtClose` at `0x180070897`
- `ntdll!NtClose` at `0x1800708ae`
- `ntdll!NtClose` at `0x1800708c5`
- `ntdll!TpReleaseAlpcCompletion` at `0x180070888`
- `ntdll!TpReleaseAlpcCompletion` at `0x180070888`
- `ntdll!TpWaitForAlpcCompletion` at `0x18007087f`
- `ntdll!TpWaitForAlpcCompletion` at `0x18007087f`
- `ntdll!TpAllocAlpcCompletion` at `0x180070869`
- `ntdll!TpAllocAlpcCompletion` at `0x180070869`
- `ntdll!NtAlpcCreatePort` at `0x180070845`
- `ntdll!NtAlpcCreatePort` at `0x180070845`
- `ntdll!RtlInitUnicodeString` at `0x1800707a8`
- `ntdll!RtlInitUnicodeString` at `0x1800707a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800708dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800708dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180070801`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180070801`

## pseudocode

```c
void __fastcall AlpcConnectionServer::Start(AlpcConnectionServer *this, const unsigned __int16 *a2)
{
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-59h] BYREF
  __int128 v7; // [rsp+38h] [rbp-51h] BYREF
  __int128 v8; // [rsp+48h] [rbp-41h]
  __int128 v9; // [rsp+58h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  int v11; // [rsp+80h] [rbp-9h] BYREF
  __int64 v12; // [rsp+84h] [rbp-5h]
  __int16 v13; // [rsp+8Ch] [rbp+3h]
  __int64 v14; // [rsp+90h] [rbp+7h]
  __int64 v15; // [rsp+98h] [rbp+Fh]
  __int64 v16; // [rsp+A0h] [rbp+17h]
  __int64 v17; // [rsp+A8h] [rbp+1Fh]
  __int64 v18; // [rsp+B0h] [rbp+27h]
  __int64 v19; // [rsp+B8h] [rbp+2Fh]
  int v20; // [rsp+C0h] [rbp+37h]

  DestinationString = 0;
  memset_0(&v11, 0, 0x48u);
  SecurityDescriptor = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\RPC Control\\FconAlpcPort");
  v14 = 56;
  v16 = 0xFFFFFFFFLL;
  v17 = 0xFFFFFFFFLL;
  v19 = 0xFFFFFFFFLL;
  v18 = 0xFFFFFFFFLL;
  v20 = 0;
  v15 = 0;
  v12 = 12;
  v13 = 1;
  v11 = 0x20000;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYD:", 1u, &SecurityDescriptor, 0) )
  {
    LODWORD(v7) = 48;
    *(_QWORD *)&v8 = &DestinationString;
    v9 = (unsigned __int64)SecurityDescriptor;
    *((_QWORD *)&v7 + 1) = 0;
    DWORD2(v8) = 64;
    if ( (int)NtAlpcCreatePort((char *)this + 16, &v7, &v11) >= 0 )
    {
      TpAllocAlpcCompletion(this, *((_QWORD *)this + 2), AlpcConnectionServer::ProcessMessageStatic, this, 0);
      AlpcConnectionServer::WaitBeforeServerShutdown(this);
    }
  }
  if ( *(_QWORD *)this )
  {
    TpWaitForAlpcCompletion();
    TpReleaseAlpcCompletion(*(_QWORD *)this);
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    NtClose(v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    NtClose(v4);
    *((_QWORD *)this + 3) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    NtClose(v5);
    *((_QWORD *)this + 2) = 0;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x180070748  mov     [rsp-8+arg_8], rbx
0x18007074d  mov     [rsp-8+arg_10], rdi
0x180070752  push    rbp
0x180070753  lea     rbp, [rsp-57h]
0x180070758  sub     rsp, 0E0h
0x18007075f  mov     rax, cs:__security_cookie
0x180070766  xor     rax, rsp
0x180070769  mov     [rbp+57h+var_10], rax
0x18007076d  xor     edx, edx; Val
0x18007076f  mov     rbx, rcx
0x180070772  xorps   xmm0, xmm0
0x180070775  lea     rcx, [rbp+57h+var_60]; void *
0x180070779  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007077d  lea     r8d, [rdx+48h]; Size
0x180070781  call    memset_0
0x180070786  xorps   xmm0, xmm0
0x180070789  mov     [rbp+57h+SecurityDescriptor], 0
0x180070791  lea     rdx, aRpcControlFcon; "\\RPC Control\\FconAlpcPort"
0x180070798  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007079c  movups  [rbp+57h+var_A8], xmm0
0x1800707a0  movups  [rbp+57h+var_98], xmm0
0x1800707a4  movups  [rbp+57h+var_88], xmm0
0x1800707a8  call    cs:__imp_RtlInitUnicodeString
0x1800707ae  mov     eax, 0FFFFFFFFh
0x1800707b3  mov     [rbp+57h+var_50], 38h ; '8'
0x1800707bb  xor     r9d, r9d; SecurityDescriptorSize
0x1800707be  mov     [rbp+57h+var_40], rax
0x1800707c2  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800707c6  mov     [rbp+57h+var_38], rax
0x1800707ca  lea     rcx, aOSyd; "O:SYD:"
0x1800707d1  mov     [rbp+57h+var_28], rax
0x1800707d5  mov     [rbp+57h+var_30], rax
0x1800707d9  lea     edx, [r9+1]; StringSDRevision
0x1800707dd  mov     [rbp+57h+var_20], 0
0x1800707e4  mov     [rbp+57h+var_48], 0
0x1800707ec  mov     [rbp+57h+var_5C], 0Ch
0x1800707f4  mov     [rbp+57h+var_54], 1
0x1800707fa  mov     [rbp+57h+var_60], 20000h
0x180070801  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180070807  test    eax, eax
0x180070809  jz      short loc_180070877
0x18007080b  lea     rax, [rbp+57h+DestinationString]
0x18007080f  mov     dword ptr [rbp+57h+var_A8], 30h ; '0'
0x180070816  mov     qword ptr [rbp+57h+var_98], rax
0x18007081a  lea     r8, [rbp+57h+var_60]
0x18007081e  mov     rax, [rbp+57h+SecurityDescriptor]
0x180070822  lea     rdx, [rbp+57h+var_A8]
0x180070826  lea     rcx, [rbx+10h]
0x18007082a  mov     qword ptr [rbp+57h+var_88], rax
0x18007082e  mov     qword ptr [rbp+57h+var_A8+8], 0
0x180070836  mov     dword ptr [rbp+57h+var_98+8], 40h ; '@'
0x18007083d  mov     qword ptr [rbp+57h+var_88+8], 0
0x180070845  call    cs:__imp_NtAlpcCreatePort
0x18007084b  test    eax, eax
0x18007084d  js      short loc_180070877
0x18007084f  mov     rdx, [rbx+10h]
0x180070853  lea     r8, ?ProcessMessageStatic@AlpcConnectionServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@@Z; AlpcConnectionServer::ProcessMessageStatic(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *)
0x18007085a  mov     r9, rbx
0x18007085d  mov     [rsp+0E0h+var_C0], 0
0x180070866  mov     rcx, rbx
0x180070869  call    cs:__imp_TpAllocAlpcCompletion
0x18007086f  mov     rcx, rbx; this
0x180070872  call    ?WaitBeforeServerShutdown@AlpcConnectionServer@@AEAAXXZ; AlpcConnectionServer::WaitBeforeServerShutdown(void)
0x180070877  mov     rcx, [rbx]
0x18007087a  test    rcx, rcx
0x18007087d  jz      short loc_18007088E
0x18007087f  call    cs:__imp_TpWaitForAlpcCompletion
0x180070885  mov     rcx, [rbx]
0x180070888  call    cs:__imp_TpReleaseAlpcCompletion
0x18007088e  mov     rcx, [rbx+8]; Handle
0x180070892  test    rcx, rcx
0x180070895  jz      short loc_1800708A5
0x180070897  call    cs:__imp_NtClose
0x18007089d  mov     qword ptr [rbx+8], 0
0x1800708a5  mov     rcx, [rbx+18h]; Handle
0x1800708a9  test    rcx, rcx
0x1800708ac  jz      short loc_1800708BC
0x1800708ae  call    cs:__imp_NtClose
0x1800708b4  mov     qword ptr [rbx+18h], 0
0x1800708bc  mov     rcx, [rbx+10h]; Handle
0x1800708c0  test    rcx, rcx
0x1800708c3  jz      short loc_1800708D3
0x1800708c5  call    cs:__imp_NtClose
0x1800708cb  mov     qword ptr [rbx+10h], 0
0x1800708d3  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800708d7  test    rcx, rcx
0x1800708da  jz      short loc_1800708E2
0x1800708dc  call    cs:__imp_LocalFree
0x1800708e2  mov     rcx, [rbp+57h+var_10]
0x1800708e6  xor     rcx, rsp; StackCookie
0x1800708e9  call    __security_check_cookie
0x1800708ee  lea     r11, [rsp+0E0h+var_s0]
0x1800708f6  mov     rbx, [r11+18h]
0x1800708fa  mov     rdi, [r11+20h]
0x1800708fe  mov     rsp, r11
0x180070901  pop     rbp
0x180070902  retn
```
