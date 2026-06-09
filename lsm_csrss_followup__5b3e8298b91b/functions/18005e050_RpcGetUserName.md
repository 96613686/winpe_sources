# RpcGetUserName

- ea: `0x18005e050`
- end: `0x18005e2ca`
- name: `RpcGetUserName`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180014c00`
- `0x180014f40`
- `0x18001aa50`
- `0x18001d320`
- `0x18001fd70`
- `0x18004b460`
- `0x18005e050`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e1de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e21f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e1de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e21f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e24d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e25b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e24d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e25b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e283`

## string_xrefs

- `0x18005e122`: `CheckAccessToSession(WINSTATION_QUERY) failed: 0x%x in %s`

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
0x18005e050  push    rbp
0x18005e052  push    rbx
0x18005e053  push    rsi
0x18005e054  push    rdi
0x18005e055  push    r12
0x18005e057  push    r14
0x18005e059  push    r15
0x18005e05b  lea     rbp, [rsp-1A0h]
0x18005e063  sub     rsp, 2A0h
0x18005e06a  mov     rax, cs:__security_cookie
0x18005e071  xor     rax, rsp
0x18005e074  mov     [rbp+1D0h+var_40], rax
0x18005e07b  xor     r12d, r12d
0x18005e07e  lea     rsi, aRpcgetusername; "RpcGetUserName"
0x18005e085  mov     r15, r8
0x18005e088  mov     [rsp+2D0h+var_298], r12
0x18005e08d  mov     r14, rdx
0x18005e090  mov     [rsp+2D0h+pv], r12
0x18005e095  mov     rbx, rcx
0x18005e098  mov     [rsp+2D0h+var_2A8], r12
0x18005e09d  mov     r8, rsi; char *
0x18005e0a0  mov     [rsp+2D0h+var_2A0], r12
0x18005e0a5  xor     edx, edx; int
0x18005e0a7  lea     rcx, [rsp+2D0h+var_290]; this
0x18005e0ac  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005e0b1  test    rbx, rbx
0x18005e0b4  jnz     short loc_18005E0DB
0x18005e0b6  lea     r8, aHsession; "hSession"
0x18005e0bd  mov     r9, rsi
0x18005e0c0  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005e0c7  mov     ecx, 8; int
0x18005e0cc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e0d1  mov     edi, 80070057h
0x18005e0d6  jmp     loc_18005E269
0x18005e0db  test    r14, r14
0x18005e0de  jnz     short loc_18005E0E9
0x18005e0e0  lea     r8, aPszusername; "pszUserName"
0x18005e0e7  jmp     short loc_18005E0BD
0x18005e0e9  test    r15, r15
0x18005e0ec  jnz     short loc_18005E0F7
0x18005e0ee  lea     r8, aPszdomain; "pszDomain"
0x18005e0f5  jmp     short loc_18005E0BD
0x18005e0f7  mov     rdx, [rbx+638h]
0x18005e0fe  lea     rcx, [rsp+2D0h+var_298]
0x18005e103  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x18005e108  mov     rbx, [rsp+2D0h+var_298]
0x18005e10d  xor     r8d, r8d; int
0x18005e110  mov     rcx, rbx; struct ITSSession *
0x18005e113  lea     edx, [r8+1]; unsigned int
0x18005e117  call    ?CheckAccessToSession@@YAJPEAUITSSession@@KH@Z; CheckAccessToSession(ITSSession *,ulong,int)
0x18005e11c  mov     edi, eax
0x18005e11e  test    eax, eax
0x18005e120  jns     short loc_18005E12B
0x18005e122  lea     rdx, aCheckaccesstos_5; "CheckAccessToSession(WINSTATION_QUERY) "...
0x18005e129  jmp     short loc_18005E1A6
0x18005e12b  mov     rax, [rbx]
0x18005e12e  lea     rdx, [rsp+2D0h+var_2A0]
0x18005e133  mov     rcx, rbx
0x18005e136  mov     rax, [rax+60h]
0x18005e13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e13f  mov     edi, eax
0x18005e141  test    eax, eax
0x18005e143  jns     short loc_18005E15E
0x18005e145  mov     r8d, eax
0x18005e148  lea     rdx, aSessionGetuser_0; "Session->getUserName failed: 0x%x"
0x18005e14f  mov     ecx, 4; int
0x18005e154  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e159  jmp     loc_18005E269
0x18005e15e  mov     rcx, [rsp+2D0h+var_2A0]
0x18005e163  lea     rdx, [rsp+2D0h+pv]
0x18005e168  mov     rax, [rcx]
0x18005e16b  mov     rax, [rax+28h]
0x18005e16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e174  mov     edi, eax
0x18005e176  test    eax, eax
0x18005e178  jns     short loc_18005E183
0x18005e17a  lea     rdx, aUsernameGetuse_0; "UserName->GetUserStr failed: 0x%x in %s"
0x18005e181  jmp     short loc_18005E1A6
0x18005e183  mov     rcx, [rsp+2D0h+var_2A0]
0x18005e188  lea     rdx, [rsp+2D0h+var_2A8]
0x18005e18d  mov     rax, [rcx]
0x18005e190  mov     rax, [rax+30h]
0x18005e194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e199  mov     edi, eax
0x18005e19b  test    eax, eax
0x18005e19d  jns     short loc_18005E1BB
0x18005e19f  lea     rdx, aUsernameGetdom; "UserName->GetDomain failed: 0x%x in %s"
0x18005e1a6  mov     r9, rsi
0x18005e1a9  mov     r8d, eax
0x18005e1ac  mov     ecx, 8; int
0x18005e1b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e1b6  jmp     loc_18005E269
0x18005e1bb  mov     rcx, [rsp+2D0h+pv]
0x18005e1c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005e1c4  mov     rax, rbx
0x18005e1c7  inc     rax
0x18005e1ca  cmp     [rcx+rax*2], r12w
0x18005e1cf  jnz     short loc_18005E1C7
0x18005e1d1  lea     rdi, [rax+1]
0x18005e1d5  mov     ecx, 40h ; '@'; uFlags
0x18005e1da  lea     rdx, [rdi+rdi]; uBytes
0x18005e1de  call    cs:__imp_LocalAlloc
0x18005e1e4  mov     rsi, rax
0x18005e1e7  test    rax, rax
0x18005e1ea  jnz     short loc_18005E1F3
0x18005e1ec  mov     edi, 8007000Eh
0x18005e1f1  jmp     short loc_18005E269
0x18005e1f3  mov     r8, [rsp+2D0h+pv]; unsigned __int16 *
0x18005e1f8  mov     rdx, rdi; unsigned __int64
0x18005e1fb  mov     rcx, rsi; unsigned __int16 *
0x18005e1fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e203  mov     r10, [rsp+2D0h+var_2A8]
0x18005e208  inc     rbx
0x18005e20b  cmp     [r10+rbx*2], r12w
0x18005e210  jnz     short loc_18005E208
0x18005e212  lea     rdi, [rbx+1]
0x18005e216  mov     ecx, 40h ; '@'; uFlags
0x18005e21b  lea     rdx, [rdi+rdi]; uBytes
0x18005e21f  call    cs:__imp_LocalAlloc
0x18005e225  mov     rbx, rax
0x18005e228  test    rax, rax
0x18005e22b  jnz     short loc_18005E234
0x18005e22d  mov     edi, 8007000Eh
0x18005e232  jmp     short loc_18005E24A
0x18005e234  mov     r8, [rsp+2D0h+var_2A8]; unsigned __int16 *
0x18005e239  mov     rdx, rdi; unsigned __int64
0x18005e23c  mov     rcx, rbx; unsigned __int16 *
0x18005e23f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005e244  mov     edi, eax
0x18005e246  test    eax, eax
0x18005e248  jns     short loc_18005E263
0x18005e24a  mov     rcx, rsi; hMem
0x18005e24d  call    cs:__imp_LocalFree
0x18005e253  test    rbx, rbx
0x18005e256  jz      short loc_18005E269
0x18005e258  mov     rcx, rbx; hMem
0x18005e25b  call    cs:__imp_LocalFree
0x18005e261  jmp     short loc_18005E269
0x18005e263  mov     [r14], rsi
0x18005e266  mov     [r15], rbx
0x18005e269  mov     rcx, [rsp+2D0h+pv]; pv
0x18005e26e  test    rcx, rcx
0x18005e271  jz      short loc_18005E279
0x18005e273  call    cs:__imp_CoTaskMemFree
0x18005e279  mov     rcx, [rsp+2D0h+var_2A8]; pv
0x18005e27e  test    rcx, rcx
0x18005e281  jz      short loc_18005E289
0x18005e283  call    cs:__imp_CoTaskMemFree
0x18005e289  lea     rcx, [rsp+2D0h+var_290]; this
0x18005e28e  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005e293  lea     rcx, [rsp+2D0h+var_2A0]
0x18005e298  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005e29d  lea     rcx, [rsp+2D0h+var_298]
0x18005e2a2  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005e2a7  mov     eax, edi
0x18005e2a9  mov     rcx, [rbp+1D0h+var_40]
0x18005e2b0  xor     rcx, rsp; StackCookie
0x18005e2b3  call    __security_check_cookie
0x18005e2b8  add     rsp, 2A0h
0x18005e2bf  pop     r15
0x18005e2c1  pop     r14
0x18005e2c3  pop     r12
0x18005e2c5  pop     rdi
0x18005e2c6  pop     rsi
0x18005e2c7  pop     rbx
0x18005e2c8  pop     rbp
0x18005e2c9  retn
```
