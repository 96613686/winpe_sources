# CSyncItemLog::CreateInstance(CSyncItemLog * *)

- ea: `0x1800041f0`
- end: `0x180004461`
- name: `?CreateInstance@CSyncItemLog@@SAJPEAPEAV1@@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct CSyncItemLog **)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003dd4`
- `0x180003e70`
- `0x180006e60`
- `0x180017d50`
- `0x18001ae68`
- `0x18001b324`
- `0x18001b5c0`
- `0x18001ef88`
- `0x180023a20`
- `0x180024ae0`
- `0x18002558c`
- `0x18003c54c`
- `0x180040114`
- `0x180040440`
- `0x18004328c`

## callees

- `0x1800041f0`
- `0x18000c1e8`
- `0x18003faa4`
- `0x1800438d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800042b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800042b7`

## pseudocode

```c
__int64 __fastcall CSyncItemLog::CreateInstance(struct CSyncItemLog **a1)
{
  _DWORD *v2; // rax
  const struct _GUID *v3; // rdx
  _DWORD *v4; // rbx
  DWORD v5; // r8d
  const IID *v6; // rcx
  unsigned int v7; // edx
  HRESULT v8; // edi
  unsigned int v9; // r8d
  int v10; // r9d
  IUnknown *pItf; // r14
  __int64 v12; // rcx
  __int64 v13; // r14
  _QWORD *v14; // rcx
  __int64 v15; // rax
  MULTI_QI pResults; // [rsp+30h] [rbp-39h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v19[2]; // [rsp+68h] [rbp-1h] BYREF
  int v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+7Ch] [rbp+13h]
  __int64 v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]
  __int64 v24; // [rsp+D0h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+6Fh] BYREF

  *a1 = 0;
  v2 = operator new(0x38u);
  v4 = v2;
  if ( !v2 )
    return 2147942414LL;
  v2[2] = 1;
  *(_QWORD *)v2 = &CSyncItemLog::`vftable';
  CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)(v2 + 4), v3);
  v5 = v4[12];
  v6 = (const IID *)*((_QWORD *)v4 + 5);
  pServerInfo.pAuthInfo = (COAUTHINFO *)v19;
  v24 = 0;
  v19[0] = -1;
  v19[1] = 0;
  v20 = 6;
  v21 = 3;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pwszName = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 0;
  pResults.pIID = &GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff;
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v8 = CoCreateInstanceEx(v6, 0, v5, &pServerInfo, 1u, &pResults);
  if ( v8 >= 0 )
  {
    pItf = pResults.pItf;
    v8 = CscCom_SetClientProxyBlanket(pResults.pItf, v7, v9, v10);
    if ( v8 >= 0 )
      v8 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pItf->lpVtbl->QueryInterface)(
             pItf,
             &GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff,
             &v24);
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    if ( v8 >= 0 )
    {
      v12 = v24;
      v8 = -2147024809;
      v13 = v24;
      if ( v24 )
      {
        v14 = (_QWORD *)*((_QWORD *)v4 + 3);
        v15 = *(_QWORD *)&GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff.Data1 - *v14;
        if ( *(_QWORD *)&GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff.Data1 == *v14 )
          v15 = *(_QWORD *)GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff.Data4 - v14[1];
        if ( v15 )
        {
          v8 = -2147467262;
LABEL_19:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          v24 = 0;
          goto LABEL_21;
        }
        if ( v4[8] )
        {
          v8 = -2147467259;
          goto LABEL_19;
        }
        v4[8] = 0;
        ppv = 0;
        v8 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, _DWORD *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 v13,
                 &GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff,
                 v4 + 8);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( v8 < 0 )
        {
          v4[8] = 0;
          goto LABEL_19;
        }
        v12 = v24;
      }
      if ( v8 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        *a1 = (struct CSyncItemLog *)v4;
        _InterlockedIncrement(v4 + 2);
        goto LABEL_21;
      }
      goto LABEL_19;
    }
  }
LABEL_21:
  if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(_DWORD *, __int64))v4)(v4, 1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800041f0  push    rbp
0x1800041f2  push    rbx
0x1800041f3  push    rsi
0x1800041f4  push    r12
0x1800041f6  lea     rbp, [rsp-3Fh]
0x1800041fb  sub     rsp, 0A8h
0x180004202  mov     rsi, rcx
0x180004205  xor     r12d, r12d
0x180004208  mov     [rcx], r12
0x18000420b  mov     ecx, 38h ; '8'; Size
0x180004210  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004215  mov     rbx, rax
0x180004218  test    rax, rax
0x18000421b  jz      loc_18000444F
0x180004221  mov     dword ptr [rax+8], 1
0x180004228  lea     rcx, [rbx+10h]; this
0x18000422c  lea     rax, ??_7CSyncItemLog@@6B@; const CSyncItemLog::`vftable'
0x180004233  mov     [rsp+0C0h+arg_10], rdi
0x18000423b  mov     [rbx], rax
0x18000423e  mov     [rsp+0C0h+var_20], r13
0x180004246  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x18000424b  mov     r8d, [rbx+30h]; dwClsCtx
0x18000424f  lea     rax, [rbp+57h+var_58]
0x180004253  mov     rcx, [rbx+28h]; Clsid
0x180004257  lea     r13, _GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff
0x18000425e  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180004262  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180004266  lea     rax, [rbp+57h+var_90]
0x18000426a  mov     [rbp+57h+arg_0], r12
0x18000426e  mov     [rsp+0C0h+pResults], rax; pResults
0x180004273  xor     edx, edx; punkOuter
0x180004275  mov     [rsp+0C0h+dwCount], 1; dwCount
0x18000427d  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180004285  mov     [rbp+57h+var_50], r12
0x180004289  mov     [rbp+57h+var_48], 6
0x180004290  mov     [rbp+57h+var_44], 3
0x180004297  mov     [rbp+57h+var_40], r12
0x18000429b  mov     [rbp+57h+var_38], r12
0x18000429f  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], r12
0x1800042a3  mov     [rbp+57h+pServerInfo.pwszName], r12
0x1800042a7  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], r12
0x1800042ab  mov     [rbp+57h+var_90.pIID], r13
0x1800042af  mov     [rbp+57h+var_90.pItf], r12
0x1800042b3  mov     qword ptr [rbp+57h+var_90.hr], r12
0x1800042b7  call    cs:__imp_CoCreateInstanceEx
0x1800042bd  mov     edi, eax
0x1800042bf  test    eax, eax
0x1800042c1  js      loc_18000440E
0x1800042c7  mov     [rsp+0C0h+var_28], r14
0x1800042cf  mov     r14, [rbp+57h+var_90.pItf]
0x1800042d3  mov     rcx, r14; struct IUnknown *
0x1800042d6  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x1800042db  mov     edi, eax
0x1800042dd  test    eax, eax
0x1800042df  js      short loc_1800042F8
0x1800042e1  mov     rax, [r14]
0x1800042e4  lea     r8, [rbp+57h+arg_0]
0x1800042e8  mov     rdx, r13
0x1800042eb  mov     rcx, r14
0x1800042ee  mov     rax, [rax]
0x1800042f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f6  mov     edi, eax
0x1800042f8  mov     rax, [r14]
0x1800042fb  mov     rcx, r14
0x1800042fe  mov     rax, [rax+10h]
0x180004302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004307  test    edi, edi
0x180004309  js      loc_180004406
0x18000430f  mov     rcx, [rbp+57h+arg_0]
0x180004313  mov     edi, 80070057h
0x180004318  mov     [rsp+0C0h+var_30], r15
0x180004320  mov     r14, rcx
0x180004323  test    rcx, rcx
0x180004326  jz      loc_1800043CD
0x18000432c  mov     rcx, [rbx+18h]
0x180004330  mov     rax, qword ptr cs:_GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff.Data1
0x180004337  sub     rax, [rcx]
0x18000433a  jnz     short loc_180004347
0x18000433c  mov     rax, qword ptr cs:_GUID_3638f50e_a9b3_41cd_ab4e_eccf042571ff.Data4
0x180004343  sub     rax, [rcx+8]
0x180004347  test    rax, rax
0x18000434a  jz      short loc_180004353
0x18000434c  mov     edi, 80004002h
0x180004351  jmp     short loc_1800043D1
0x180004353  cmp     [rbx+20h], r12d
0x180004357  jz      short loc_180004360
0x180004359  mov     edi, 80004005h
0x18000435e  jmp     short loc_1800043D1
0x180004360  lea     rax, [rbp+57h+ppv]
0x180004364  mov     [rbx+20h], r12d
0x180004368  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000436f  mov     qword ptr [rsp+0C0h+dwCount], rax; ppv
0x180004374  xor     edx, edx; pUnkOuter
0x180004376  mov     [rbp+57h+ppv], r12
0x18000437a  mov     r8d, 1; dwClsContext
0x180004380  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004387  call    cs:__imp_CoCreateInstance
0x18000438d  mov     edi, eax
0x18000438f  test    eax, eax
0x180004391  js      short loc_1800043BF
0x180004393  mov     rcx, [rbp+57h+ppv]
0x180004397  lea     r9, [rbx+20h]
0x18000439b  mov     r8, r13
0x18000439e  mov     rdx, r14
0x1800043a1  mov     rax, [rcx]
0x1800043a4  mov     rax, [rax+18h]
0x1800043a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ad  mov     rcx, [rbp+57h+ppv]
0x1800043b1  mov     edi, eax
0x1800043b3  mov     rax, [rcx]
0x1800043b6  mov     rax, [rax+10h]
0x1800043ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043bf  test    edi, edi
0x1800043c1  jns     short loc_1800043C9
0x1800043c3  mov     [rbx+20h], r12d
0x1800043c7  jmp     short loc_1800043D1
0x1800043c9  mov     rcx, [rbp+57h+arg_0]
0x1800043cd  test    edi, edi
0x1800043cf  jns     short loc_1800043EB
0x1800043d1  mov     rax, [r14]
0x1800043d4  mov     rcx, r14
0x1800043d7  mov     rax, [rax+10h]
0x1800043db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e0  mov     rcx, r12
0x1800043e3  mov     [rbp+57h+arg_0], rcx
0x1800043e7  test    edi, edi
0x1800043e9  js      short loc_1800043FE
0x1800043eb  mov     rax, [rcx]
0x1800043ee  mov     rax, [rax+10h]
0x1800043f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f7  mov     [rsi], rbx
0x1800043fa  lock inc dword ptr [rbx+8]
0x1800043fe  mov     r15, [rsp+0C0h+var_30]
0x180004406  mov     r14, [rsp+0C0h+var_28]
0x18000440e  mov     ecx, 0FFFFFFFFh
0x180004413  lock xadd [rbx+8], ecx
0x180004418  mov     r13, [rsp+0C0h+var_20]
0x180004420  cmp     ecx, 1
0x180004423  jnz     short loc_180004438
0x180004425  mov     rcx, [rbx]
0x180004428  mov     edx, 1
0x18000442d  mov     rax, [rcx]
0x180004430  mov     rcx, rbx
0x180004433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004438  mov     eax, edi
0x18000443a  mov     rdi, [rsp+0C0h+arg_10]
0x180004442  add     rsp, 0A8h
0x180004449  pop     r12
0x18000444b  pop     rsi
0x18000444c  pop     rbx
0x18000444d  pop     rbp
0x18000444e  retn
0x18000444f  mov     eax, 8007000Eh
0x180004454  add     rsp, 0A8h
0x18000445b  pop     r12
0x18000445d  pop     rsi
0x18000445e  pop     rbx
0x18000445f  pop     rbp
0x180004460  retn
```
