# PlaiInitializeStore(void)

- ea: `0x18012c5f0`
- end: `0x18012cca3`
- name: `?PlaiInitializeStore@@YAJXZ`
- size: `1715`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f2ce0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800098d0`
- `0x18002b3a0`
- `0x1800db5d0`
- `0x1801147e0`
- `0x18012c5f0`
- `0x18013aee0`

## import_xrefs

- `ntdll!EtwNotificationRegister` at `0x18012c740`
- `ntdll!EtwNotificationRegister` at `0x18012c740`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18012c853`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18012c853`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012c8f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012c8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012cc7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012cc7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18012c9b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18012c9b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012cc6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18012cc6b`
- `RPCRT4!UuidCreate` at `0x18012c7c8`
- `RPCRT4!UuidCreate` at `0x18012c7c8`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012cb77`
- `RPCRT4!RpcServerRegisterIf3` at `0x18012cb77`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18012cac3`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18012cac3`

## string_xrefs

- `0x18012c8e5`: `System\CurrentControlSet\Services\PLA\Configuration`

## pseudocode

```c
__int64 PlaiInitializeStore(void)
{
  int v0; // eax
  unsigned int v1; // edi
  __int64 v2; // rbx
  int *v3; // r9
  int *v4; // rcx
  unsigned int v5; // eax
  int v6; // eax
  __int64 v7; // rbx
  RPC_STATUS v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rbx
  LSTATUS v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rax
  LSTATUS v16; // eax
  int v17; // eax
  int v18; // eax
  RPC_STATUS v19; // eax
  int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  int v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES v27; // [rsp+88h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v30[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v31[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v32[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v33[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v34[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v35[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v36[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v37[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v38[64]; // [rsp+500h] [rbp+400h] BYREF

  hKey = 0;
  Uuid = 0;
  memset(&v27, 0, sizeof(v27));
  PlaiLoadTaskSchedulerUseXMLStore();
  qword_180169CF8 = 0;
  stru_180169BA8.Blink = &stru_180169BA8;
  stru_180169BA8.Flink = &stru_180169BA8;
  stru_180169BB8.Blink = &stru_180169BB8;
  stru_180169BB8.Flink = &stru_180169BB8;
  xmmword_180169D00 = 0;
  xmmword_180169D10 = 0;
  xmmword_180169D20 = 0;
  v0 = PlaiInitializeCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)&xmmword_180169D00 + 8));
  v1 = v0;
  if ( v0 >= 0 )
  {
    LODWORD(xmmword_180169D00) = 1;
    v5 = EtwNotificationRegister(SessionNotificationGuid, 7, PlaiStoreTraceCallback, 0, &qword_180169CF8);
    v6 = PlaiHResultFromWin32(v5);
    v1 = v6;
    if ( v6 >= 0 )
    {
      v8 = UuidCreate(&Uuid);
      v1 = v8;
      if ( v8 >= 0 )
      {
        if ( StringFromGUID2(&Uuid, sz, 40) )
        {
          v11 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Services\\PLA\\Configuration",
                  0,
                  2u,
                  &hKey);
          v12 = PlaiHResultFromWin32(v11);
          v1 = v12;
          if ( v12 >= 0 )
          {
            v14 = -1;
            v15 = -1;
            do
              ++v15;
            while ( sz[v15] );
            v16 = RegSetValueExW(hKey, L"RPCEndPoint", 0, 1u, (const BYTE *)sz, 2 * v15 + 2);
            v17 = PlaiHResultFromWin32(v16);
            v1 = v17;
            if ( v17 >= 0 )
            {
              v18 = PlaiCreateSecurityDescriptor(1u, &v27);
              v1 = v18;
              if ( v18 >= 0 )
              {
                v19 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x14u, sz, v27.lpSecurityDescriptor);
                v20 = PlaiHResultFromWin32(v19);
                v1 = v20;
                if ( v20 >= 0 )
                {
                  v21 = RpcServerRegisterIf3(
                          qword_180142F00,
                          0,
                          0,
                          41,
                          20,
                          0,
                          PlaiRpcIfCallback,
                          v27.lpSecurityDescriptor);
                  v22 = PlaiHResultFromWin32(v21);
                  v1 = v22;
                  if ( v22 >= 0 )
                    goto LABEL_67;
                  v25 = 0;
                  v24 = v22;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_67;
                  }
                  PlaiWhoAmI(v38, 0x4000000000000800uLL);
                  do
                    ++v14;
                  while ( v38[v14] );
                }
                else
                {
                  v25 = 0;
                  v24 = v20;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_67;
                  }
                  PlaiWhoAmI(v37, 0x4000000000000800uLL);
                  do
                    ++v14;
                  while ( v37[v14] );
                }
              }
              else
              {
                v25 = 0;
                v24 = v18;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_67;
                }
                PlaiWhoAmI(v36, 0x4000000000000800uLL);
                do
                  ++v14;
                while ( v36[v14] );
              }
            }
            else
            {
              v25 = 0;
              v24 = v17;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_67;
              }
              PlaiWhoAmI(v35, 0x4000000000000800uLL);
              do
                ++v14;
              while ( v35[v14] );
            }
          }
          else
          {
            v25 = 0;
            v24 = v12;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_67;
            }
            PlaiWhoAmI(v34, 0x4000000000000800uLL);
            v13 = -1;
            do
              ++v13;
            while ( v34[v13] );
          }
        }
        else
        {
          v1 = -2147467259;
          v24 = -2147467259;
          v25 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_67;
          }
          PlaiWhoAmI(v33, 0x4000000000000800uLL);
          v10 = -1;
          do
            ++v10;
          while ( v33[v10] );
        }
      }
      else
      {
        v25 = 0;
        v24 = v8;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_67;
        }
        PlaiWhoAmI(v32, 0x4000000000000800uLL);
        v9 = -1;
        do
          ++v9;
        while ( v32[v9] );
      }
    }
    else
    {
      v25 = 0;
      v24 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_67;
      }
      PlaiWhoAmI(v31, 0x4000000000000800uLL);
      v7 = -1;
      do
        ++v7;
      while ( v31[v7] );
    }
    v3 = &v24;
    v4 = &v25;
LABEL_66:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v3, 4, qword_180147320, 1, v4, 4, "PlaiInitializeStore", 20);
    goto LABEL_67;
  }
  v24 = 0;
  v25 = v0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v30, 0x4000000000000800uLL);
    v2 = -1;
    do
      ++v2;
    while ( v30[v2] );
    v3 = &v25;
    v4 = &v24;
    goto LABEL_66;
  }
LABEL_67:
  if ( v27.lpSecurityDescriptor )
  {
    LocalFree(v27.lpSecurityDescriptor);
    v27.lpSecurityDescriptor = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18012c5f0  push    rbp
0x18012c5f2  push    rbx
0x18012c5f3  push    rsi
0x18012c5f4  push    rdi
0x18012c5f5  push    r14
0x18012c5f7  lea     rbp, [rsp-490h]
0x18012c5ff  sub     rsp, 590h
0x18012c606  mov     rax, cs:__security_cookie
0x18012c60d  xor     rax, rsp
0x18012c610  mov     [rbp+4B0h+var_30], rax
0x18012c617  xorps   xmm0, xmm0
0x18012c61a  xor     r14d, r14d
0x18012c61d  mov     [rbp+4B0h+hKey], r14
0x18012c621  movups  xmmword ptr [rbp+4B0h+Uuid.Data1], xmm0
0x18012c625  mov     qword ptr [rbp+4B0h+var_528.nLength], r14
0x18012c629  movdqu  xmmword ptr [rbp+4B0h+var_528.lpSecurityDescriptor], xmm0
0x18012c62e  call    ?PlaiLoadTaskSchedulerUseXMLStore@@YAJXZ; PlaiLoadTaskSchedulerUseXMLStore(void)
0x18012c633  xorps   xmm0, xmm0
0x18012c636  mov     cs:qword_180169CF8, r14
0x18012c63d  lea     rax, stru_180169BA8
0x18012c644  mov     cs:stru_180169BA8.Blink, rax
0x18012c64b  lea     rcx, xmmword_180169D00+8; struct _RTL_CRITICAL_SECTION *
0x18012c652  mov     cs:stru_180169BA8.Flink, rax
0x18012c659  lea     rax, stru_180169BB8
0x18012c660  mov     cs:stru_180169BB8.Blink, rax
0x18012c667  mov     cs:stru_180169BB8.Flink, rax
0x18012c66e  movups  cs:xmmword_180169D00, xmm0
0x18012c675  movups  cs:xmmword_180169D10, xmm0
0x18012c67c  movups  cs:xmmword_180169D20, xmm0
0x18012c683  call    ?PlaiInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; PlaiInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x18012c688  mov     edi, eax
0x18012c68a  test    eax, eax
0x18012c68c  jns     loc_18012C715
0x18012c692  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c699  mov     [rsp+5B0h+var_540], r14d
0x18012c69e  mov     [rsp+5B0h+var_538], eax
0x18012c6a2  jz      loc_18012CC62
0x18012c6a8  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c6b2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c6b9  jz      loc_18012CC62
0x18012c6bf  mov     rax, cs:qword_180169748
0x18012c6c6  and     rax, rdx
0x18012c6c9  cmp     cs:qword_180169748, rax
0x18012c6d0  jnz     loc_18012CC62
0x18012c6d6  lea     rcx, [rbp+4B0h+var_4B0]; unsigned __int16 *
0x18012c6da  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012c6df  lea     rax, [rbp+4B0h+var_4B0]
0x18012c6e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c6e7  inc     rbx
0x18012c6ea  cmp     [rax+rbx*2], r14w
0x18012c6ef  jnz     short loc_18012C6E7
0x18012c6f1  lea     ecx, [rbx+rbx]
0x18012c6f4  mov     esi, 1
0x18012c6f9  add     rcx, 2
0x18012c6fd  lea     rax, [rbp+4B0h+var_4B0]
0x18012c701  mov     [rsp+5B0h+var_550], rcx
0x18012c706  lea     r9, [rsp+5B0h+var_538]
0x18012c70b  lea     rcx, [rsp+5B0h+var_540]
0x18012c710  jmp     loc_18012CC0C
0x18012c715  mov     esi, 1
0x18012c71a  lea     rax, qword_180169CF8
0x18012c721  xor     r9d, r9d
0x18012c724  mov     dword ptr cs:xmmword_180169D00, esi
0x18012c72a  lea     r8, ?PlaiStoreTraceCallback@@YAKPEAU_ETW_NOTIFICATION_HEADER@@PEAX@Z; PlaiStoreTraceCallback(_ETW_NOTIFICATION_HEADER *,void *)
0x18012c731  mov     [rsp+5B0h+phkResult], rax
0x18012c736  lea     rcx, SessionNotificationGuid
0x18012c73d  lea     edx, [rsi+6]
0x18012c740  call    cs:__imp_EtwNotificationRegister
0x18012c746  mov     ecx, eax; unsigned int
0x18012c748  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18012c74d  mov     edi, eax
0x18012c74f  test    eax, eax
0x18012c751  jns     short loc_18012C7C4
0x18012c753  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c75a  mov     [rsp+5B0h+var_538], r14d
0x18012c75f  mov     [rsp+5B0h+var_540], eax
0x18012c763  jz      loc_18012CC62
0x18012c769  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c773  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c77a  jz      loc_18012CC62
0x18012c780  mov     rax, cs:qword_180169748
0x18012c787  and     rax, rdx
0x18012c78a  cmp     cs:qword_180169748, rax
0x18012c791  jnz     loc_18012CC62
0x18012c797  lea     rcx, [rbp+4B0h+var_430]; unsigned __int16 *
0x18012c79e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012c7a3  lea     rax, [rbp+4B0h+var_430]
0x18012c7aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c7ae  inc     rbx
0x18012c7b1  cmp     [rax+rbx*2], r14w
0x18012c7b6  jnz     short loc_18012C7AE
0x18012c7b8  lea     rax, [rbp+4B0h+var_430]
0x18012c7bf  jmp     loc_18012CBF6
0x18012c7c4  lea     rcx, [rbp+4B0h+Uuid]; Uuid
0x18012c7c8  call    cs:__imp_UuidCreate
0x18012c7ce  mov     edi, eax
0x18012c7d0  test    eax, eax
0x18012c7d2  jns     short loc_18012C845
0x18012c7d4  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c7db  mov     [rsp+5B0h+var_538], r14d
0x18012c7e0  mov     [rsp+5B0h+var_540], eax
0x18012c7e4  jz      loc_18012CC62
0x18012c7ea  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c7f4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c7fb  jz      loc_18012CC62
0x18012c801  mov     rax, cs:qword_180169748
0x18012c808  and     rax, rdx
0x18012c80b  cmp     cs:qword_180169748, rax
0x18012c812  jnz     loc_18012CC62
0x18012c818  lea     rcx, [rbp+4B0h+var_3B0]; unsigned __int16 *
0x18012c81f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012c824  lea     rax, [rbp+4B0h+var_3B0]
0x18012c82b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c82f  inc     rbx
0x18012c832  cmp     [rax+rbx*2], r14w
0x18012c837  jnz     short loc_18012C82F
0x18012c839  lea     rax, [rbp+4B0h+var_3B0]
0x18012c840  jmp     loc_18012CBF6
0x18012c845  mov     r8d, 28h ; '('; cchMax
0x18012c84b  lea     rdx, [rbp+4B0h+sz]; lpsz
0x18012c84f  lea     rcx, [rbp+4B0h+Uuid]; rguid
0x18012c853  call    cs:__imp_StringFromGUID2
0x18012c859  test    eax, eax
0x18012c85b  jnz     short loc_18012C8D3
0x18012c85d  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c864  mov     edi, 80004005h
0x18012c869  mov     [rsp+5B0h+var_540], edi
0x18012c86d  mov     [rsp+5B0h+var_538], r14d
0x18012c872  jz      loc_18012CC62
0x18012c878  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c882  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c889  jz      loc_18012CC62
0x18012c88f  mov     rax, cs:qword_180169748
0x18012c896  and     rax, rdx
0x18012c899  cmp     cs:qword_180169748, rax
0x18012c8a0  jnz     loc_18012CC62
0x18012c8a6  lea     rcx, [rbp+4B0h+var_330]; unsigned __int16 *
0x18012c8ad  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012c8b2  lea     rax, [rbp+4B0h+var_330]
0x18012c8b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c8bd  inc     rbx
0x18012c8c0  cmp     [rax+rbx*2], r14w
0x18012c8c5  jnz     short loc_18012C8BD
0x18012c8c7  lea     rax, [rbp+4B0h+var_330]
0x18012c8ce  jmp     loc_18012CBF6
0x18012c8d3  lea     rax, [rbp+4B0h+hKey]
0x18012c8d7  mov     r9d, 2; samDesired
0x18012c8dd  xor     r8d, r8d; ulOptions
0x18012c8e0  mov     [rsp+5B0h+phkResult], rax; phkResult
0x18012c8e5  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\PL"...
0x18012c8ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012c8f3  call    cs:__imp_RegOpenKeyExW
0x18012c8f9  mov     ecx, eax; unsigned int
0x18012c8fb  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18012c900  mov     edi, eax
0x18012c902  test    eax, eax
0x18012c904  jns     short loc_18012C977
0x18012c906  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c90d  mov     [rsp+5B0h+var_538], r14d
0x18012c912  mov     [rsp+5B0h+var_540], eax
0x18012c916  jz      loc_18012CC62
0x18012c91c  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c926  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c92d  jz      loc_18012CC62
0x18012c933  mov     rax, cs:qword_180169748
0x18012c93a  and     rax, rdx
0x18012c93d  cmp     cs:qword_180169748, rax
0x18012c944  jnz     loc_18012CC62
0x18012c94a  lea     rcx, [rbp+4B0h+var_2B0]; unsigned __int16 *
0x18012c951  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012c956  lea     rax, [rbp+4B0h+var_2B0]
0x18012c95d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c961  inc     rbx
0x18012c964  cmp     [rax+rbx*2], r14w
0x18012c969  jnz     short loc_18012C961
0x18012c96b  lea     rax, [rbp+4B0h+var_2B0]
0x18012c972  jmp     loc_18012CBF6
0x18012c977  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012c97b  lea     rcx, [rbp+4B0h+sz]
0x18012c97f  mov     rax, rbx
0x18012c982  inc     rax
0x18012c985  cmp     [rcx+rax*2], r14w
0x18012c98a  jnz     short loc_18012C982
0x18012c98c  mov     rcx, [rbp+4B0h+hKey]; hKey
0x18012c990  lea     eax, ds:2[rax*2]
0x18012c997  mov     [rsp+5B0h+cbData], eax; cbData
0x18012c99b  lea     rdx, ValueName; "RPCEndPoint"
0x18012c9a2  lea     rax, [rbp+4B0h+sz]
0x18012c9a6  mov     r9d, esi; dwType
0x18012c9a9  xor     r8d, r8d; Reserved
0x18012c9ac  mov     [rsp+5B0h+phkResult], rax; lpData
0x18012c9b1  call    cs:__imp_RegSetValueExW
0x18012c9b7  mov     ecx, eax; unsigned int
0x18012c9b9  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18012c9be  mov     edi, eax
0x18012c9c0  test    eax, eax
0x18012c9c2  jns     short loc_18012CA31
0x18012c9c4  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012c9cb  mov     [rsp+5B0h+var_538], r14d
0x18012c9d0  mov     [rsp+5B0h+var_540], eax
0x18012c9d4  jz      loc_18012CC62
0x18012c9da  mov     rdx, 4000000000000800h; unsigned __int64
0x18012c9e4  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012c9eb  jz      loc_18012CC62
0x18012c9f1  mov     rax, cs:qword_180169748
0x18012c9f8  and     rax, rdx
0x18012c9fb  cmp     cs:qword_180169748, rax
0x18012ca02  jnz     loc_18012CC62
0x18012ca08  lea     rcx, [rbp+4B0h+var_230]; unsigned __int16 *
0x18012ca0f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012ca14  lea     rax, [rbp+4B0h+var_230]
0x18012ca1b  inc     rbx
0x18012ca1e  cmp     [rax+rbx*2], r14w
0x18012ca23  jnz     short loc_18012CA1B
0x18012ca25  lea     rax, [rbp+4B0h+var_230]
0x18012ca2c  jmp     loc_18012CBF6
0x18012ca31  lea     rdx, [rbp+4B0h+var_528]; struct _SECURITY_ATTRIBUTES *
0x18012ca35  mov     ecx, esi; unsigned int
0x18012ca37  call    ?PlaiCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z; PlaiCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)
0x18012ca3c  mov     edi, eax
0x18012ca3e  test    eax, eax
0x18012ca40  jns     short loc_18012CAAF
0x18012ca42  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012ca49  mov     [rsp+5B0h+var_538], r14d
0x18012ca4e  mov     [rsp+5B0h+var_540], eax
0x18012ca52  jz      loc_18012CC62
0x18012ca58  mov     rdx, 4000000000000800h; unsigned __int64
0x18012ca62  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012ca69  jz      loc_18012CC62
0x18012ca6f  mov     rax, cs:qword_180169748
0x18012ca76  and     rax, rdx
0x18012ca79  cmp     cs:qword_180169748, rax
0x18012ca80  jnz     loc_18012CC62
0x18012ca86  lea     rcx, [rbp+4B0h+var_1B0]; unsigned __int16 *
0x18012ca8d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012ca92  lea     rax, [rbp+4B0h+var_1B0]
0x18012ca99  inc     rbx
0x18012ca9c  cmp     [rax+rbx*2], r14w
0x18012caa1  jnz     short loc_18012CA99
0x18012caa3  lea     rax, [rbp+4B0h+var_1B0]
0x18012caaa  jmp     loc_18012CBF6
0x18012caaf  mov     r9, [rbp+4B0h+var_528.lpSecurityDescriptor]; SecurityDescriptor
0x18012cab3  lea     r8, [rbp+4B0h+sz]; Endpoint
0x18012cab7  mov     edx, 14h; MaxCalls
0x18012cabc  lea     rcx, Protseq; "ncalrpc"
0x18012cac3  call    cs:__imp_RpcServerUseProtseqEpW
0x18012cac9  mov     ecx, eax; unsigned int
0x18012cacb  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18012cad0  mov     edi, eax
0x18012cad2  test    eax, eax
0x18012cad4  jns     short loc_18012CB43
0x18012cad6  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012cadd  mov     [rsp+5B0h+var_538], r14d
0x18012cae2  mov     [rsp+5B0h+var_540], eax
0x18012cae6  jz      loc_18012CC62
0x18012caec  mov     rdx, 4000000000000800h; unsigned __int64
0x18012caf6  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012cafd  jz      loc_18012CC62
0x18012cb03  mov     rax, cs:qword_180169748
0x18012cb0a  and     rax, rdx
0x18012cb0d  cmp     cs:qword_180169748, rax
0x18012cb14  jnz     loc_18012CC62
0x18012cb1a  lea     rcx, [rbp+4B0h+var_130]; unsigned __int16 *
0x18012cb21  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012cb26  lea     rax, [rbp+4B0h+var_130]
0x18012cb2d  inc     rbx
0x18012cb30  cmp     [rax+rbx*2], r14w
0x18012cb35  jnz     short loc_18012CB2D
0x18012cb37  lea     rax, [rbp+4B0h+var_130]
0x18012cb3e  jmp     loc_18012CBF6
0x18012cb43  mov     rax, [rbp+4B0h+var_528.lpSecurityDescriptor]
0x18012cb47  lea     rcx, qword_180142F00
0x18012cb4e  mov     [rsp+5B0h+var_578], rax
0x18012cb53  mov     r9d, 29h ; ')'
0x18012cb59  lea     rax, ?PlaiRpcIfCallback@@YAJPEAX0@Z; PlaiRpcIfCallback(void *,void *)
0x18012cb60  xor     r8d, r8d
0x18012cb63  mov     [rsp+5B0h+var_580], rax
0x18012cb68  xor     edx, edx
0x18012cb6a  mov     [rsp+5B0h+cbData], r14d
0x18012cb6f  mov     dword ptr [rsp+5B0h+phkResult], 14h
0x18012cb77  call    cs:__imp_RpcServerRegisterIf3
0x18012cb7d  mov     ecx, eax; unsigned int
0x18012cb7f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18012cb84  mov     edi, eax
0x18012cb86  test    eax, eax
0x18012cb88  jns     loc_18012CC62
0x18012cb8e  cmp     dword ptr cs:xmmword_180169738, r14d
0x18012cb95  mov     [rsp+5B0h+var_538], r14d
0x18012cb9a  mov     [rsp+5B0h+var_540], eax
0x18012cb9e  jz      loc_18012CC62
0x18012cba4  mov     rdx, 4000000000000800h; unsigned __int64
0x18012cbae  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012cbb5  jz      loc_18012CC62
0x18012cbbb  mov     rax, cs:qword_180169748
0x18012cbc2  and     rax, rdx
0x18012cbc5  cmp     cs:qword_180169748, rax
0x18012cbcc  jnz     loc_18012CC62
0x18012cbd2  lea     rcx, [rbp+4B0h+var_B0]; unsigned __int16 *
0x18012cbd9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012cbde  lea     rax, [rbp+4B0h+var_B0]
  ... truncated ...
```
