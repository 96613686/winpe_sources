# ActivateRpcInterface

- ea: `0x1800160c4`
- end: `0x18001634a`
- name: `ActivateRpcInterface`
- size: `646`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015fac`
- `0x18001603c`

## callees

- `0x1800160c4`
- `0x180017b74`
- `0x18001c500`
- `0x18001d09c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016139`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180016290`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180016290`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180016212`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180016212`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180016280`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180016280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001632d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001632d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001612f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001612f`

## pseudocode

```c
__int64 __fastcall ActivateRpcInterface(__int64 a1, _QWORD *a2)
{
  DWORD LastError; // eax
  DWORD v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  DWORD v9; // eax
  _QWORD v10[6]; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v12; // [rsp+B8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_cef5404d8a2231070386988250481c1f_Traceguids);
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cef5404d8a2231070386988250481c1f_Traceguids, LastError);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 6u )
      goto LABEL_15;
    v7 = 13;
LABEL_14:
    WPP_SF_d(v6[2], v7, WPP_cef5404d8a2231070386988250481c1f_Traceguids, v5);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
    return v5;
  }
  v10[0] = 0;
  v10[1] = L"ncalrpc";
  v10[2] = 0;
  v10[3] = SecurityDescriptor;
  v10[4] = 10;
  *(_QWORD *)(a1 + 72) = SecurityDescriptor;
  v12 = 0;
  v9 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *, __int64, int, __int64 (__fastcall *)(), _QWORD, __int64 *))RpcServerInterfaceGroupCreateW)(
         a1,
         1,
         v10,
         1,
         1800,
         NcbRpcIdleCallback,
         0,
         &v12);
  v5 = v9;
  if ( v9 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cef5404d8a2231070386988250481c1f_Traceguids, v9);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 6u )
      goto LABEL_15;
    v7 = 15;
    goto LABEL_14;
  }
  v5 = RpcServerInterfaceGroupActivate(v12);
  if ( v5 )
  {
    RpcServerInterfaceGroupClose(v12);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_cef5404d8a2231070386988250481c1f_Traceguids, v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 6u )
      goto LABEL_15;
    v7 = 17;
    goto LABEL_14;
  }
  *a2 = v12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_cef5404d8a2231070386988250481c1f_Traceguids);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x1800160c4  mov     [rsp-28h+arg_0], rbx
0x1800160c9  push    rbp
0x1800160ca  push    rsi
0x1800160cb  push    rdi
0x1800160cc  push    r14
0x1800160ce  push    r15
0x1800160d0  mov     rbp, rsp
0x1800160d3  sub     rsp, 70h
0x1800160d7  mov     rdi, rdx
0x1800160da  mov     rbx, rcx
0x1800160dd  lea     r14, WPP_GLOBAL_Control
0x1800160e4  lea     r15, WPP_cef5404d8a2231070386988250481c1f_Traceguids
0x1800160eb  mov     esi, 1
0x1800160f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160f7  cmp     rcx, r14
0x1800160fa  jz      short loc_180016117
0x1800160fc  test    [rcx+1Ch], sil
0x180016100  jz      short loc_180016117
0x180016102  cmp     byte ptr [rcx+19h], 6
0x180016106  jb      short loc_180016117
0x180016108  lea     edx, [rsi+0Ah]
0x18001610b  mov     r8, r15
0x18001610e  mov     rcx, [rcx+10h]
0x180016112  call    WPP_SF_
0x180016117  mov     [rbp+SecurityDescriptor], 0
0x18001611f  xor     r9d, r9d; SecurityDescriptorSize
0x180016122  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180016126  mov     edx, esi; StringSDRevision
0x180016128  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18001612f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180016135  test    eax, eax
0x180016137  jnz     short loc_1800161A9
0x180016139  call    cs:__imp_GetLastError
0x18001613f  mov     ebx, eax
0x180016141  mov     rcx, cs:WPP_GLOBAL_Control
0x180016148  cmp     rcx, r14
0x18001614b  jz      short loc_180016199
0x18001614d  test    [rcx+1Ch], sil
0x180016151  jz      short loc_180016174
0x180016153  cmp     byte ptr [rcx+19h], 2
0x180016157  jb      short loc_180016174
0x180016159  mov     edx, 0Ch
0x18001615e  mov     r9d, eax
0x180016161  mov     r8, r15
0x180016164  mov     rcx, [rcx+10h]
0x180016168  call    WPP_SF_d
0x18001616d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016174  cmp     rcx, r14
0x180016177  jz      short loc_180016199
0x180016179  test    [rcx+1Ch], sil
0x18001617d  jz      short loc_180016199
0x18001617f  cmp     byte ptr [rcx+19h], 6
0x180016183  jb      short loc_180016199
0x180016185  mov     edx, 0Dh
0x18001618a  mov     r9d, ebx
0x18001618d  mov     r8, r15
0x180016190  mov     rcx, [rcx+10h]
0x180016194  call    WPP_SF_d
0x180016199  lea     rcx, [rbp+SecurityDescriptor]
0x18001619d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800161a2  mov     eax, ebx
0x1800161a4  jmp     loc_180016336
0x1800161a9  mov     [rbp+var_30], 0
0x1800161b1  lea     rax, Protseq; "ncalrpc"
0x1800161b8  mov     [rbp+var_28], rax
0x1800161bc  mov     [rbp+var_20], 0
0x1800161c4  mov     rax, [rbp+SecurityDescriptor]
0x1800161c8  mov     [rbp+var_18], rax
0x1800161cc  mov     [rbp+var_10], 0Ah
0x1800161d4  mov     [rbx+48h], rax
0x1800161d8  mov     [rbp+arg_18], 0
0x1800161e0  lea     rax, [rbp+arg_18]
0x1800161e4  mov     [rsp+70h+var_38], rax
0x1800161e9  mov     [rsp+70h+var_40], 0
0x1800161f2  lea     rax, NcbRpcIdleCallback
0x1800161f9  mov     [rsp+70h+var_48], rax
0x1800161fe  mov     [rsp+70h+var_50], 708h
0x180016206  mov     r9d, esi
0x180016209  lea     r8, [rbp+var_30]
0x18001620d  mov     edx, esi
0x18001620f  mov     rcx, rbx
0x180016212  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x180016218  mov     ebx, eax
0x18001621a  test    eax, eax
0x18001621c  jz      short loc_18001627C
0x18001621e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016225  cmp     rcx, r14
0x180016228  jz      loc_180016199
0x18001622e  test    [rcx+1Ch], sil
0x180016232  jz      short loc_180016255
0x180016234  cmp     byte ptr [rcx+19h], 2
0x180016238  jb      short loc_180016255
0x18001623a  mov     edx, 0Eh
0x18001623f  mov     r9d, eax
0x180016242  mov     r8, r15
0x180016245  mov     rcx, [rcx+10h]
0x180016249  call    WPP_SF_d
0x18001624e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016255  cmp     rcx, r14
0x180016258  jz      loc_180016199
0x18001625e  test    [rcx+1Ch], sil
0x180016262  jz      loc_180016199
0x180016268  cmp     byte ptr [rcx+19h], 6
0x18001626c  jb      loc_180016199
0x180016272  mov     edx, 0Fh
0x180016277  jmp     loc_18001618A
0x18001627c  mov     rcx, [rbp+arg_18]
0x180016280  call    cs:__imp_RpcServerInterfaceGroupActivate
0x180016286  mov     ebx, eax
0x180016288  test    eax, eax
0x18001628a  jz      short loc_1800162F4
0x18001628c  mov     rcx, [rbp+arg_18]
0x180016290  call    cs:__imp_RpcServerInterfaceGroupClose
0x180016296  mov     rcx, cs:WPP_GLOBAL_Control
0x18001629d  cmp     rcx, r14
0x1800162a0  jz      loc_180016199
0x1800162a6  test    [rcx+1Ch], sil
0x1800162aa  jz      short loc_1800162CD
0x1800162ac  cmp     byte ptr [rcx+19h], 2
0x1800162b0  jb      short loc_1800162CD
0x1800162b2  mov     edx, 10h
0x1800162b7  mov     r9d, ebx
0x1800162ba  mov     r8, r15
0x1800162bd  mov     rcx, [rcx+10h]
0x1800162c1  call    WPP_SF_d
0x1800162c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162cd  cmp     rcx, r14
0x1800162d0  jz      loc_180016199
0x1800162d6  test    [rcx+1Ch], sil
0x1800162da  jz      loc_180016199
0x1800162e0  cmp     byte ptr [rcx+19h], 6
0x1800162e4  jb      loc_180016199
0x1800162ea  mov     edx, 11h
0x1800162ef  jmp     loc_18001618A
0x1800162f4  mov     rax, [rbp+arg_18]
0x1800162f8  mov     [rdi], rax
0x1800162fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180016302  cmp     rcx, r14
0x180016305  jz      short loc_180016324
0x180016307  test    [rcx+1Ch], sil
0x18001630b  jz      short loc_180016324
0x18001630d  cmp     byte ptr [rcx+19h], 6
0x180016311  jb      short loc_180016324
0x180016313  mov     edx, 12h
0x180016318  mov     r8, r15
0x18001631b  mov     rcx, [rcx+10h]
0x18001631f  call    WPP_SF_
0x180016324  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180016328  test    rcx, rcx
0x18001632b  jz      short loc_180016334
0x18001632d  call    cs:__imp_LocalFree
0x180016333  nop
0x180016334  xor     eax, eax
0x180016336  mov     rbx, [rsp+70h+arg_0]
0x18001633e  add     rsp, 70h
0x180016342  pop     r15
0x180016344  pop     r14
0x180016346  pop     rdi
0x180016347  pop     rsi
0x180016348  pop     rbp
0x180016349  retn
```
