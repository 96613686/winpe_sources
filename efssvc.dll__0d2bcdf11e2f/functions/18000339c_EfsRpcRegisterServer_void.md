# EfsRpcRegisterServer(void *)

- ea: `0x18000339c`
- end: `0x18000368b`
- name: `?EfsRpcRegisterServer@@YAJPEAX@Z`
- size: `751`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002fb0`

## callees

- `0x18000339c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003477`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003462`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800034aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003462`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800034aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003656`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000366a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003656`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000366a`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180003633`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x180003633`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000361c`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000361c`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800035d6`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800035d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800033d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800033d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033be`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180003403`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180003403`

## pseudocode

```c
__int64 __fastcall EfsRpcRegisterServer(void *a1)
{
  HANDLE ProcessHeap; // rax
  void *v3; // rax
  signed int v4; // ebx
  signed int v5; // eax
  PSECURITY_DESCRIPTOR v6; // r14
  PSECURITY_DESCRIPTOR v7; // rsi
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR v9; // rcx
  RPC_STATUS v10; // eax
  bool v11; // cc
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+68h] [rbp-98h]
  const wchar_t *v19; // [rsp+70h] [rbp-90h]
  const wchar_t *v20; // [rsp+78h] [rbp-88h]
  PSECURITY_DESCRIPTOR v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v24; // [rsp+98h] [rbp-68h]
  __int128 v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+B8h] [rbp-48h]
  __int64 v29; // [rsp+C0h] [rbp-40h]
  __int64 v30; // [rsp+C8h] [rbp-38h]
  const wchar_t *v31; // [rsp+D0h] [rbp-30h]
  PSECURITY_DESCRIPTOR v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+E0h] [rbp-20h]
  __int64 *v34; // [rsp+E8h] [rbp-18h]
  __int128 v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+104h] [rbp+4h]
  __int64 v38; // [rsp+110h] [rbp+10h]
  __int64 v39; // [rsp+118h] [rbp+18h]
  const wchar_t *v40; // [rsp+120h] [rbp+20h]
  PSECURITY_DESCRIPTOR v41; // [rsp+128h] [rbp+28h]
  DWORD cbSid; // [rsp+178h] [rbp+78h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+180h] [rbp+80h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+188h] [rbp+88h] BYREF

  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x44u);
  g_AdminSid = v3;
  if ( v3 )
  {
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v3, &cbSid) )
    {
      SecurityDescriptor = 0;
      hMem = 0;
      v6 = 0;
      v7 = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGW;;;AC)(A;;GRGW;;;S-1-15-3-1024-3203351429"
              "-2120443784-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)S:(ML;;NRNW;;;LW)",
             1u,
             &SecurityDescriptor,
             0)
        && ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3203351429-212"
              "0443784-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)",
             1u,
             &hMem,
             0) )
      {
        v6 = SecurityDescriptor;
        v9 = 0;
        v7 = hMem;
        v4 = 0;
        SecurityDescriptor = 0;
        hMem = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v9 = SecurityDescriptor;
      }
      if ( v9 )
        LocalFree(v9);
      if ( hMem )
        LocalFree(hMem);
      if ( v4 >= 0 )
      {
        v23 = 0;
        v27 = 1234;
        v37 = 1234;
        v24 = qword_180010F70;
        v25 = 0;
        v31 = L"EFS RPC Interface";
        v17 = 10;
        v34 = qword_1800117A0;
        v22 = 10;
        v40 = L"EFSK RPC Interface";
        v26 = 9;
        v14 = L"ncalrpc";
        v28 = 0x400000;
        v19 = L"ncacn_np";
        v20 = L"\\pipe\\efsrpc";
        v29 = 0;
        v30 = 0;
        v32 = v7;
        v33 = 0;
        v35 = 0;
        v36 = 41;
        v38 = 0;
        v39 = 0;
        v41 = v7;
        v13 = 0;
        v15 = 0;
        v16 = v7;
        v18 = 0;
        v21 = v6;
        v10 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
        v11 = v10 <= 0;
        if ( v10
          || (v10 = ((__int64 (__fastcall *)(int *, __int64, int *, __int64, int, void (__fastcall *)(void *, void *), void *, __int64 *))RpcServerInterfaceGroupCreateW)(
                      &v23,
                      2,
                      &v13,
                      2,
                      -1,
                      EfsRpcIdleCallback,
                      a1,
                      &qword_180018868),
              v11 = v10 <= 0,
              v10)
          || (v10 = RpcServerInterfaceGroupActivate(qword_180018868), v11 = v10 <= 0, v10) )
        {
          if ( v11 )
            v4 = v10;
          else
            v4 = (unsigned __int16)v10 | 0x80070000;
        }
      }
      if ( v6 )
        LocalFree(v6);
      if ( v7 )
        LocalFree(v7);
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000339c  push    rbp
0x18000339e  push    rbx
0x18000339f  push    rsi
0x1800033a0  push    rdi
0x1800033a1  push    r12
0x1800033a3  push    r14
0x1800033a5  push    r15
0x1800033a7  lea     rbp, [rsp-30h]
0x1800033ac  sub     rsp, 130h
0x1800033b3  mov     ebx, 44h ; 'D'
0x1800033b8  mov     r15, rcx
0x1800033bb  mov     [rbp+60h+cbSid], ebx
0x1800033be  call    cs:__imp_GetProcessHeap
0x1800033c5  nop     dword ptr [rax+rax+00h]
0x1800033ca  mov     r8d, ebx; dwBytes
0x1800033cd  xor     edx, edx; dwFlags
0x1800033cf  mov     rcx, rax; hHeap
0x1800033d2  call    cs:__imp_HeapAlloc
0x1800033d9  nop     dword ptr [rax+rax+00h]
0x1800033de  xor     r12d, r12d
0x1800033e1  mov     cs:g_AdminSid, rax
0x1800033e8  test    rax, rax
0x1800033eb  jnz     short loc_1800033F7
0x1800033ed  mov     ebx, 8007000Eh
0x1800033f2  jmp     loc_180003676
0x1800033f7  xor     edx, edx; DomainSid
0x1800033f9  lea     r9, [rbp+60h+cbSid]; cbSid
0x1800033fd  mov     r8, rax; pSid
0x180003400  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180003403  call    cs:__imp_CreateWellKnownSid
0x18000340a  nop     dword ptr [rax+rax+00h]
0x18000340f  test    eax, eax
0x180003411  jnz     short loc_180003437
0x180003413  call    cs:__imp_GetLastError
0x18000341a  nop     dword ptr [rax+rax+00h]
0x18000341f  mov     ebx, eax
0x180003421  test    eax, eax
0x180003423  jle     loc_180003676
0x180003429  movzx   ebx, ax
0x18000342c  or      ebx, 80070000h
0x180003432  jmp     loc_180003676
0x180003437  xor     r9d, r9d; SecurityDescriptorSize
0x18000343a  mov     [rbp+60h+SecurityDescriptor], r12
0x180003441  lea     r8, [rbp+60h+SecurityDescriptor]; SecurityDescriptor
0x180003448  mov     [rbp+60h+hMem], r12
0x18000344f  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180003456  mov     r14, r12
0x180003459  mov     rsi, r12
0x18000345c  lea     ebx, [r9+1]
0x180003460  mov     edx, ebx; StringSDRevision
0x180003462  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003469  nop     dword ptr [rax+rax+00h]
0x18000346e  mov     edi, 80070000h
0x180003473  test    eax, eax
0x180003475  jnz     short loc_180003497
0x180003477  call    cs:__imp_GetLastError
0x18000347e  nop     dword ptr [rax+rax+00h]
0x180003483  mov     ebx, eax
0x180003485  test    eax, eax
0x180003487  jle     short loc_18000348E
0x180003489  movzx   ebx, ax
0x18000348c  or      ebx, edi
0x18000348e  mov     rcx, [rbp+60h+SecurityDescriptor]
0x180003495  jmp     short loc_1800034DC
0x180003497  xor     r9d, r9d; SecurityDescriptorSize
0x18000349a  lea     r8, [rbp+60h+hMem]; SecurityDescriptor
0x1800034a1  mov     edx, ebx; StringSDRevision
0x1800034a3  lea     rcx, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800034aa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800034b1  nop     dword ptr [rax+rax+00h]
0x1800034b6  test    eax, eax
0x1800034b8  jz      short loc_180003477
0x1800034ba  mov     r14, [rbp+60h+SecurityDescriptor]
0x1800034c1  mov     rcx, r12; hMem
0x1800034c4  mov     rsi, [rbp+60h+hMem]
0x1800034cb  mov     ebx, r12d
0x1800034ce  mov     [rbp+60h+SecurityDescriptor], rcx
0x1800034d5  mov     [rbp+60h+hMem], r12
0x1800034dc  test    rcx, rcx
0x1800034df  jz      short loc_1800034ED
0x1800034e1  call    cs:__imp_LocalFree
0x1800034e8  nop     dword ptr [rax+rax+00h]
0x1800034ed  mov     rcx, [rbp+60h+hMem]; hMem
0x1800034f4  test    rcx, rcx
0x1800034f7  jz      short loc_180003505
0x1800034f9  call    cs:__imp_LocalFree
0x180003500  nop     dword ptr [rax+rax+00h]
0x180003505  test    ebx, ebx
0x180003507  js      loc_18000364E
0x18000350d  mov     ecx, 4D2h
0x180003512  mov     [rbp+60h+var_D0], r12d
0x180003516  mov     edx, 9; AuthnSvc
0x18000351b  mov     [rbp+60h+var_AC], ecx
0x18000351e  mov     [rbp+60h+var_5C], rcx
0x180003522  lea     rax, qword_180010F70
0x180003529  mov     [rbp+60h+var_C8], rax
0x18000352d  xorps   xmm0, xmm0
0x180003530  lea     rax, aEfsRpcInterfac; "EFS RPC Interface"
0x180003537  movdqa  [rbp+60h+var_C0], xmm0
0x18000353c  mov     [rbp+60h+var_90], rax
0x180003540  lea     ecx, [rdx+1]
0x180003543  lea     rax, qword_1800117A0
0x18000354a  mov     [rsp+160h+var_100], ecx
0x18000354e  mov     [rbp+60h+var_78], rax
0x180003552  xor     r9d, r9d; Arg
0x180003555  lea     rax, aEfskRpcInterfa; "EFSK RPC Interface"
0x18000355c  mov     [rbp+60h+var_D8], ecx
0x18000355f  mov     [rbp+60h+var_40], rax
0x180003563  xor     r8d, r8d; GetKeyFn
0x180003566  lea     rax, aNcalrpc; "ncalrpc"
0x18000356d  mov     [rbp+60h+var_B0], edx
0x180003570  mov     [rsp+160h+var_118], rax
0x180003575  xor     ecx, ecx; ServerPrincName
0x180003577  lea     rax, aNcacnNp; "ncacn_np"
0x18000357e  mov     [rbp+60h+var_A8], 400000h
0x180003585  mov     [rsp+160h+var_F0], rax
0x18000358a  lea     rax, aPipeEfsrpc; "\\pipe\\efsrpc"
0x180003591  mov     [rsp+160h+var_E8], rax
0x180003596  mov     [rbp+60h+var_A0], r12
0x18000359a  mov     [rbp+60h+var_98], r12
0x18000359e  mov     [rbp+60h+var_88], rsi
0x1800035a2  mov     [rbp+60h+var_80], r12d
0x1800035a6  movdqa  [rbp+60h+var_70], xmm0
0x1800035ab  mov     [rbp+60h+var_60], 29h ; ')'
0x1800035b2  mov     [rbp+60h+var_50], r12
0x1800035b6  mov     [rbp+60h+var_48], r12
0x1800035ba  mov     [rbp+60h+var_38], rsi
0x1800035be  mov     [rsp+160h+var_120], r12d
0x1800035c3  mov     [rsp+160h+var_110], r12
0x1800035c8  mov     [rsp+160h+var_108], rsi
0x1800035cd  mov     [rsp+160h+var_F8], r12d
0x1800035d2  mov     [rbp+60h+var_E0], r14
0x1800035d6  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800035dd  nop     dword ptr [rax+rax+00h]
0x1800035e2  test    eax, eax
0x1800035e4  jnz     short loc_180003643
0x1800035e6  lea     rax, qword_180018868
0x1800035ed  mov     edx, 2
0x1800035f2  mov     [rsp+160h+var_128], rax
0x1800035f7  lea     r8, [rsp+160h+var_120]
0x1800035fc  lea     rax, ?EfsRpcIdleCallback@@YAXPEAX0K@Z; EfsRpcIdleCallback(void *,void *,ulong)
0x180003603  mov     [rsp+160h+var_130], r15
0x180003608  mov     [rsp+160h+var_138], rax
0x18000360d  lea     rcx, [rbp+60h+var_D0]
0x180003611  mov     r9d, edx
0x180003614  mov     [rsp+160h+var_140], 0FFFFFFFFh
0x18000361c  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x180003623  nop     dword ptr [rax+rax+00h]
0x180003628  test    eax, eax
0x18000362a  jnz     short loc_180003643
0x18000362c  mov     rcx, cs:qword_180018868
0x180003633  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000363a  nop     dword ptr [rax+rax+00h]
0x18000363f  test    eax, eax
0x180003641  jz      short loc_18000364E
0x180003643  jg      short loc_180003649
0x180003645  mov     ebx, eax
0x180003647  jmp     short loc_18000364E
0x180003649  movzx   ebx, ax
0x18000364c  or      ebx, edi
0x18000364e  test    r14, r14
0x180003651  jz      short loc_180003662
0x180003653  mov     rcx, r14; hMem
0x180003656  call    cs:__imp_LocalFree
0x18000365d  nop     dword ptr [rax+rax+00h]
0x180003662  test    rsi, rsi
0x180003665  jz      short loc_180003676
0x180003667  mov     rcx, rsi; hMem
0x18000366a  call    cs:__imp_LocalFree
0x180003671  nop     dword ptr [rax+rax+00h]
0x180003676  mov     eax, ebx
0x180003678  add     rsp, 130h
0x18000367f  pop     r15
0x180003681  pop     r14
0x180003683  pop     r12
0x180003685  pop     rdi
0x180003686  pop     rsi
0x180003687  pop     rbx
0x180003688  pop     rbp
0x180003689  retn
```
