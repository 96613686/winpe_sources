# RpcGetUserName

- ea: `0x180061af0`
- end: `0x180061d92`
- name: `RpcGetUserName`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x18001e6f0`
- `0x180022200`
- `0x18004e850`
- `0x180061af0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061c7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061cc8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061c7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180061cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061cfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061d10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061cfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061d2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061d2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061d44`

## string_xrefs

- `0x180061bc2`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcGetUserName(__int64 a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  const char *v6; // r8
  int v7; // edi
  struct ITSSession *v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rdi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rsi
  unsigned __int64 v18; // rdi
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rbx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  struct ITSSession *v25; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[592]; // [rsp+40h] [rbp-C0h] BYREF

  v25 = 0;
  pv = 0;
  v23 = 0;
  v24 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v26, 0, "RpcGetUserName");
  if ( !a1 )
  {
    v6 = "hSession";
LABEL_3:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v6, "RpcGetUserName");
    v7 = -2147024809;
    goto LABEL_29;
  }
  if ( !a2 )
  {
    v6 = "pszUserName";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = "pszDomain";
    goto LABEL_3;
  }
  SmartPtr<ITSSession>::operator=(&v25, *(_QWORD *)(a1 + 1592));
  v8 = v25;
  v9 = CheckAccessToSession(v25, 1u, 0);
  v7 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s", (unsigned int)v9, "RpcGetUserName");
    goto LABEL_29;
  }
  v10 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)v8 + 96LL))(v8, &v24);
  v7 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(4, "Session->getUserName failed: 0x%x", v10);
    goto LABEL_29;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 40LL))(v24, &pv);
  v7 = v11;
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "UserName->GetUserStr failed: 0x%x in %s", (unsigned int)v11, "RpcGetUserName");
    goto LABEL_29;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v24 + 48LL))(v24, &v23);
  v7 = v12;
  if ( v12 >= 0 )
  {
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)pv + v14) );
    v15 = v14 + 1;
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v14 + 1));
    v17 = v16;
    if ( !v16 )
    {
      v7 = -2147024882;
      goto LABEL_29;
    }
    StringCchCopyW(v16, v15, (const unsigned __int16 *)pv);
    do
      ++v13;
    while ( v23[v13] );
    v18 = v13 + 1;
    v19 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v13 + 1));
    v20 = v19;
    if ( v19 )
    {
      v7 = StringCchCopyW(v19, v18, v23);
      if ( v7 >= 0 )
      {
        *a2 = v17;
        *a3 = v20;
        goto LABEL_29;
      }
    }
    else
    {
      v7 = -2147024882;
    }
    LocalFree(v17);
    if ( v20 )
      LocalFree(v20);
  }
  else
  {
    _DbgPrintMessage(8, "UserName->GetDomain failed: 0x%x in %s", (unsigned int)v12, "RpcGetUserName");
  }
LABEL_29:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v23 )
    CoTaskMemFree(v23);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v26);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180061af0  push    rbp
0x180061af2  push    rbx
0x180061af3  push    rsi
0x180061af4  push    rdi
0x180061af5  push    r12
0x180061af7  push    r14
0x180061af9  push    r15
0x180061afb  lea     rbp, [rsp-1A0h]
0x180061b03  sub     rsp, 2A0h
0x180061b0a  mov     rax, cs:__security_cookie
0x180061b11  xor     rax, rsp
0x180061b14  mov     [rbp+1D0h+var_40], rax
0x180061b1b  xor     r12d, r12d
0x180061b1e  lea     rsi, aRpcgetusername; "RpcGetUserName"
0x180061b25  mov     r15, r8
0x180061b28  mov     [rsp+2D0h+var_298], r12
0x180061b2d  mov     r14, rdx
0x180061b30  mov     [rsp+2D0h+pv], r12
0x180061b35  mov     rbx, rcx
0x180061b38  mov     [rsp+2D0h+var_2A8], r12
0x180061b3d  mov     r8, rsi; char *
0x180061b40  mov     [rsp+2D0h+var_2A0], r12
0x180061b45  xor     edx, edx; int
0x180061b47  lea     rcx, [rsp+2D0h+var_290]; this
0x180061b4c  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180061b51  test    rbx, rbx
0x180061b54  jnz     short loc_180061B7B
0x180061b56  lea     r8, aHsession; "hSession"
0x180061b5d  mov     r9, rsi
0x180061b60  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180061b67  mov     ecx, 8; int
0x180061b6c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061b71  mov     edi, 80070057h
0x180061b76  jmp     loc_180061D24
0x180061b7b  test    r14, r14
0x180061b7e  jnz     short loc_180061B89
0x180061b80  lea     r8, aPszusername; "pszUserName"
0x180061b87  jmp     short loc_180061B5D
0x180061b89  test    r15, r15
0x180061b8c  jnz     short loc_180061B97
0x180061b8e  lea     r8, aPszdomain; "pszDomain"
0x180061b95  jmp     short loc_180061B5D
0x180061b97  mov     rdx, [rbx+638h]
0x180061b9e  lea     rcx, [rsp+2D0h+var_298]
0x180061ba3  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180061ba8  mov     rbx, [rsp+2D0h+var_298]
0x180061bad  xor     r8d, r8d; int
0x180061bb0  mov     rcx, rbx; struct ITSSession *
0x180061bb3  lea     edx, [r8+1]; unsigned int
0x180061bb7  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x180061bbc  mov     edi, eax
0x180061bbe  test    eax, eax
0x180061bc0  jns     short loc_180061BCB
0x180061bc2  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x180061bc9  jmp     short loc_180061C46
0x180061bcb  mov     rax, [rbx]
0x180061bce  lea     rdx, [rsp+2D0h+var_2A0]
0x180061bd3  mov     rcx, rbx
0x180061bd6  mov     rax, [rax+60h]
0x180061bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bdf  mov     edi, eax
0x180061be1  test    eax, eax
0x180061be3  jns     short loc_180061BFE
0x180061be5  mov     r8d, eax
0x180061be8  lea     rdx, aSessionGetuser_0; "Session->getUserName failed: 0x%x"
0x180061bef  mov     ecx, 4; int
0x180061bf4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061bf9  jmp     loc_180061D24
0x180061bfe  mov     rcx, [rsp+2D0h+var_2A0]
0x180061c03  lea     rdx, [rsp+2D0h+pv]
0x180061c08  mov     rax, [rcx]
0x180061c0b  mov     rax, [rax+28h]
0x180061c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c14  mov     edi, eax
0x180061c16  test    eax, eax
0x180061c18  jns     short loc_180061C23
0x180061c1a  lea     rdx, aUsernameGetuse_0; "UserName->GetUserStr failed: 0x%x in %s"
0x180061c21  jmp     short loc_180061C46
0x180061c23  mov     rcx, [rsp+2D0h+var_2A0]
0x180061c28  lea     rdx, [rsp+2D0h+var_2A8]
0x180061c2d  mov     rax, [rcx]
0x180061c30  mov     rax, [rax+30h]
0x180061c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c39  mov     edi, eax
0x180061c3b  test    eax, eax
0x180061c3d  jns     short loc_180061C5B
0x180061c3f  lea     rdx, aUsernameGetdom; "UserName->GetDomain failed: 0x%x in %s"
0x180061c46  mov     r9, rsi
0x180061c49  mov     r8d, eax
0x180061c4c  mov     ecx, 8; int
0x180061c51  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061c56  jmp     loc_180061D24
0x180061c5b  mov     rcx, [rsp+2D0h+pv]
0x180061c60  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180061c64  mov     rax, rbx
0x180061c67  inc     rax
0x180061c6a  cmp     [rcx+rax*2], r12w
0x180061c6f  jnz     short loc_180061C67
0x180061c71  lea     rdi, [rax+1]
0x180061c75  mov     ecx, 40h ; '@'; uFlags
0x180061c7a  lea     rdx, [rdi+rdi]; uBytes
0x180061c7e  call    cs:__imp_LocalAlloc
0x180061c85  nop     dword ptr [rax+rax+00h]
0x180061c8a  mov     rsi, rax
0x180061c8d  test    rax, rax
0x180061c90  jnz     short loc_180061C9C
0x180061c92  mov     edi, 8007000Eh
0x180061c97  jmp     loc_180061D24
0x180061c9c  mov     r8, [rsp+2D0h+pv]; unsigned __int16 *
0x180061ca1  mov     rdx, rdi; unsigned __int64
0x180061ca4  mov     rcx, rsi; unsigned __int16 *
0x180061ca7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061cac  mov     r10, [rsp+2D0h+var_2A8]
0x180061cb1  inc     rbx
0x180061cb4  cmp     [r10+rbx*2], r12w
0x180061cb9  jnz     short loc_180061CB1
0x180061cbb  lea     rdi, [rbx+1]
0x180061cbf  mov     ecx, 40h ; '@'; uFlags
0x180061cc4  lea     rdx, [rdi+rdi]; uBytes
0x180061cc8  call    cs:__imp_LocalAlloc
0x180061ccf  nop     dword ptr [rax+rax+00h]
0x180061cd4  mov     rbx, rax
0x180061cd7  test    rax, rax
0x180061cda  jnz     short loc_180061CE3
0x180061cdc  mov     edi, 8007000Eh
0x180061ce1  jmp     short loc_180061CF9
0x180061ce3  mov     r8, [rsp+2D0h+var_2A8]; unsigned __int16 *
0x180061ce8  mov     rdx, rdi; unsigned __int64
0x180061ceb  mov     rcx, rbx; unsigned __int16 *
0x180061cee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061cf3  mov     edi, eax
0x180061cf5  test    eax, eax
0x180061cf7  jns     short loc_180061D1E
0x180061cf9  mov     rcx, rsi; hMem
0x180061cfc  call    cs:__imp_LocalFree
0x180061d03  nop     dword ptr [rax+rax+00h]
0x180061d08  test    rbx, rbx
0x180061d0b  jz      short loc_180061D24
0x180061d0d  mov     rcx, rbx; hMem
0x180061d10  call    cs:__imp_LocalFree
0x180061d17  nop     dword ptr [rax+rax+00h]
0x180061d1c  jmp     short loc_180061D24
0x180061d1e  mov     [r14], rsi
0x180061d21  mov     [r15], rbx
0x180061d24  mov     rcx, [rsp+2D0h+pv]; pv
0x180061d29  test    rcx, rcx
0x180061d2c  jz      short loc_180061D3A
0x180061d2e  call    cs:__imp_CoTaskMemFree
0x180061d35  nop     dword ptr [rax+rax+00h]
0x180061d3a  mov     rcx, [rsp+2D0h+var_2A8]; pv
0x180061d3f  test    rcx, rcx
0x180061d42  jz      short loc_180061D50
0x180061d44  call    cs:__imp_CoTaskMemFree
0x180061d4b  nop     dword ptr [rax+rax+00h]
0x180061d50  lea     rcx, [rsp+2D0h+var_290]; this
0x180061d55  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180061d5a  lea     rcx, [rsp+2D0h+var_2A0]
0x180061d5f  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180061d64  lea     rcx, [rsp+2D0h+var_298]
0x180061d69  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180061d6e  mov     eax, edi
0x180061d70  mov     rcx, [rbp+1D0h+var_40]
0x180061d77  xor     rcx, rsp; StackCookie
0x180061d7a  call    __security_check_cookie
0x180061d7f  add     rsp, 2A0h
0x180061d86  pop     r15
0x180061d88  pop     r14
0x180061d8a  pop     r12
0x180061d8c  pop     rdi
0x180061d8d  pop     rsi
0x180061d8e  pop     rbx
0x180061d8f  pop     rbp
0x180061d90  retn
```
