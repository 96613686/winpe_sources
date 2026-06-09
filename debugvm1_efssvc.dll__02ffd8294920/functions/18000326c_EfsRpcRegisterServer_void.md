# EfsRpcRegisterServer(void *)

- ea: `0x18000326c`
- end: `0x180003506`
- name: `?EfsRpcRegisterServer@@YAJPEAX@Z`
- size: `666`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ee0`

## callees

- `0x18000326c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003329`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000331a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003356`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000331a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003356`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034ec`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800034c1`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800034c1`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800034b0`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1800034b0`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180003470`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180003470`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000329c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000329c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000328e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000328e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800032c7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800032c7`

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
        v24 = qword_18000FF70;
        v25 = 0;
        v31 = L"EFS RPC Interface";
        v17 = 10;
        v34 = qword_1800107A0;
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
          || (v10 = ((__int64 (__fastcall *)(int *, __int64, int *, __int64, int, __int64 (__fastcall *)(), void *, __int64 *))RpcServerInterfaceGroupCreateW)(
                      &v23,
                      2,
                      &v13,
                      2,
                      -1,
                      guard_check_icall_nop,
                      a1,
                      &qword_180017868),
              v11 = v10 <= 0,
              v10)
          || (v10 = RpcServerInterfaceGroupActivate(qword_180017868), v11 = v10 <= 0, v10) )
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
0x18000326c  push    rbp
0x18000326e  push    rbx
0x18000326f  push    rsi
0x180003270  push    rdi
0x180003271  push    r12
0x180003273  push    r14
0x180003275  push    r15
0x180003277  lea     rbp, [rsp-30h]
0x18000327c  sub     rsp, 130h
0x180003283  mov     ebx, 44h ; 'D'
0x180003288  mov     r15, rcx
0x18000328b  mov     [rbp+60h+cbSid], ebx
0x18000328e  call    cs:__imp_GetProcessHeap
0x180003294  mov     r8d, ebx; dwBytes
0x180003297  xor     edx, edx; dwFlags
0x180003299  mov     rcx, rax; hHeap
0x18000329c  call    cs:__imp_HeapAlloc
0x1800032a2  xor     r12d, r12d
0x1800032a5  mov     cs:g_AdminSid, rax
0x1800032ac  test    rax, rax
0x1800032af  jnz     short loc_1800032BB
0x1800032b1  mov     ebx, 8007000Eh
0x1800032b6  jmp     loc_1800034F2
0x1800032bb  xor     edx, edx; DomainSid
0x1800032bd  lea     r9, [rbp+60h+cbSid]; cbSid
0x1800032c1  mov     r8, rax; pSid
0x1800032c4  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800032c7  call    cs:__imp_CreateWellKnownSid
0x1800032cd  test    eax, eax
0x1800032cf  jnz     short loc_1800032EF
0x1800032d1  call    cs:__imp_GetLastError
0x1800032d7  mov     ebx, eax
0x1800032d9  test    eax, eax
0x1800032db  jle     loc_1800034F2
0x1800032e1  movzx   ebx, ax
0x1800032e4  or      ebx, 80070000h
0x1800032ea  jmp     loc_1800034F2
0x1800032ef  xor     r9d, r9d; SecurityDescriptorSize
0x1800032f2  mov     [rbp+60h+SecurityDescriptor], r12
0x1800032f9  lea     r8, [rbp+60h+SecurityDescriptor]; SecurityDescriptor
0x180003300  mov     [rbp+60h+hMem], r12
0x180003307  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000330e  mov     r14, r12
0x180003311  mov     rsi, r12
0x180003314  lea     ebx, [r9+1]
0x180003318  mov     edx, ebx; StringSDRevision
0x18000331a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003320  mov     edi, 80070000h
0x180003325  test    eax, eax
0x180003327  jnz     short loc_180003343
0x180003329  call    cs:__imp_GetLastError
0x18000332f  mov     ebx, eax
0x180003331  test    eax, eax
0x180003333  jle     short loc_18000333A
0x180003335  movzx   ebx, ax
0x180003338  or      ebx, edi
0x18000333a  mov     rcx, [rbp+60h+SecurityDescriptor]
0x180003341  jmp     short loc_180003382
0x180003343  xor     r9d, r9d; SecurityDescriptorSize
0x180003346  lea     r8, [rbp+60h+hMem]; SecurityDescriptor
0x18000334d  mov     edx, ebx; StringSDRevision
0x18000334f  lea     rcx, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180003356  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000335c  test    eax, eax
0x18000335e  jz      short loc_180003329
0x180003360  mov     r14, [rbp+60h+SecurityDescriptor]
0x180003367  mov     rcx, r12; hMem
0x18000336a  mov     rsi, [rbp+60h+hMem]
0x180003371  mov     ebx, r12d
0x180003374  mov     [rbp+60h+SecurityDescriptor], rcx
0x18000337b  mov     [rbp+60h+hMem], r12
0x180003382  test    rcx, rcx
0x180003385  jz      short loc_18000338D
0x180003387  call    cs:__imp_LocalFree
0x18000338d  mov     rcx, [rbp+60h+hMem]; hMem
0x180003394  test    rcx, rcx
0x180003397  jz      short loc_18000339F
0x180003399  call    cs:__imp_LocalFree
0x18000339f  test    ebx, ebx
0x1800033a1  js      loc_1800034D6
0x1800033a7  mov     ecx, 4D2h
0x1800033ac  mov     [rbp+60h+var_D0], r12d
0x1800033b0  mov     edx, 9; AuthnSvc
0x1800033b5  mov     [rbp+60h+var_AC], ecx
0x1800033b8  mov     [rbp+60h+var_5C], rcx
0x1800033bc  lea     rax, qword_18000FF70
0x1800033c3  mov     [rbp+60h+var_C8], rax
0x1800033c7  xorps   xmm0, xmm0
0x1800033ca  lea     rax, aEfsRpcInterfac; "EFS RPC Interface"
0x1800033d1  movdqa  [rbp+60h+var_C0], xmm0
0x1800033d6  mov     [rbp+60h+var_90], rax
0x1800033da  lea     ecx, [rdx+1]
0x1800033dd  lea     rax, qword_1800107A0
0x1800033e4  mov     [rsp+160h+var_100], ecx
0x1800033e8  mov     [rbp+60h+var_78], rax
0x1800033ec  xor     r9d, r9d; Arg
0x1800033ef  lea     rax, aEfskRpcInterfa; "EFSK RPC Interface"
0x1800033f6  mov     [rbp+60h+var_D8], ecx
0x1800033f9  mov     [rbp+60h+var_40], rax
0x1800033fd  xor     r8d, r8d; GetKeyFn
0x180003400  lea     rax, aNcalrpc; "ncalrpc"
0x180003407  mov     [rbp+60h+var_B0], edx
0x18000340a  mov     [rsp+160h+var_118], rax
0x18000340f  xor     ecx, ecx; ServerPrincName
0x180003411  lea     rax, aNcacnNp; "ncacn_np"
0x180003418  mov     [rbp+60h+var_A8], 400000h
0x18000341f  mov     [rsp+160h+var_F0], rax
0x180003424  lea     rax, aPipeEfsrpc; "\\pipe\\efsrpc"
0x18000342b  mov     [rsp+160h+var_E8], rax
0x180003430  mov     [rbp+60h+var_A0], r12
0x180003434  mov     [rbp+60h+var_98], r12
0x180003438  mov     [rbp+60h+var_88], rsi
0x18000343c  mov     [rbp+60h+var_80], r12d
0x180003440  movdqa  [rbp+60h+var_70], xmm0
0x180003445  mov     [rbp+60h+var_60], 29h ; ')'
0x18000344c  mov     [rbp+60h+var_50], r12
0x180003450  mov     [rbp+60h+var_48], r12
0x180003454  mov     [rbp+60h+var_38], rsi
0x180003458  mov     [rsp+160h+var_120], r12d
0x18000345d  mov     [rsp+160h+var_110], r12
0x180003462  mov     [rsp+160h+var_108], rsi
0x180003467  mov     [rsp+160h+var_F8], r12d
0x18000346c  mov     [rbp+60h+var_E0], r14
0x180003470  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180003476  test    eax, eax
0x180003478  jnz     short loc_1800034CB
0x18000347a  lea     rax, qword_180017868
0x180003481  mov     edx, 2
0x180003486  mov     [rsp+160h+var_128], rax
0x18000348b  lea     r8, [rsp+160h+var_120]
0x180003490  lea     rax, _guard_check_icall_nop
0x180003497  mov     [rsp+160h+var_130], r15
0x18000349c  mov     [rsp+160h+var_138], rax
0x1800034a1  lea     rcx, [rbp+60h+var_D0]
0x1800034a5  mov     r9d, edx
0x1800034a8  mov     [rsp+160h+var_140], 0FFFFFFFFh
0x1800034b0  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x1800034b6  test    eax, eax
0x1800034b8  jnz     short loc_1800034CB
0x1800034ba  mov     rcx, cs:qword_180017868
0x1800034c1  call    cs:__imp_RpcServerInterfaceGroupActivate
0x1800034c7  test    eax, eax
0x1800034c9  jz      short loc_1800034D6
0x1800034cb  jg      short loc_1800034D1
0x1800034cd  mov     ebx, eax
0x1800034cf  jmp     short loc_1800034D6
0x1800034d1  movzx   ebx, ax
0x1800034d4  or      ebx, edi
0x1800034d6  test    r14, r14
0x1800034d9  jz      short loc_1800034E4
0x1800034db  mov     rcx, r14; hMem
0x1800034de  call    cs:__imp_LocalFree
0x1800034e4  test    rsi, rsi
0x1800034e7  jz      short loc_1800034F2
0x1800034e9  mov     rcx, rsi; hMem
0x1800034ec  call    cs:__imp_LocalFree
0x1800034f2  mov     eax, ebx
0x1800034f4  add     rsp, 130h
0x1800034fb  pop     r15
0x1800034fd  pop     r14
0x1800034ff  pop     r12
0x180003501  pop     rdi
0x180003502  pop     rsi
0x180003503  pop     rbx
0x180003504  pop     rbp
0x180003505  retn
```
