# CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)

- ea: `0x180005630`
- end: `0x1800057e8`
- name: `?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002558c`

## callees

- `0x180005630`
- `0x1800438d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005772`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005772`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800056be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800056be`

## pseudocode

```c
__int64 __fastcall CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(
        __int64 a1,
        const IID *a2,
        __int64 *a3)
{
  DWORD v4; // r8d
  const IID *v7; // rcx
  unsigned int v8; // edx
  HRESULT v9; // ebx
  unsigned int v10; // r8d
  int v11; // r9d
  IUnknown *pItf; // r15
  __int64 v13; // r15
  _QWORD *v14; // rcx
  __int64 v15; // rax
  MULTI_QI pResults; // [rsp+30h] [rbp-29h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v19[2]; // [rsp+68h] [rbp+Fh] BYREF
  int v20; // [rsp+78h] [rbp+1Fh]
  int v21; // [rsp+7Ch] [rbp+23h]
  __int64 v22; // [rsp+80h] [rbp+27h]
  __int64 v23; // [rsp+88h] [rbp+2Fh]
  LPVOID ppv; // [rsp+C0h] [rbp+67h] BYREF

  pResults.pIID = a2;
  *a3 = 0;
  pServerInfo.pAuthInfo = (COAUTHINFO *)v19;
  v19[0] = -1;
  v4 = *(_DWORD *)(a1 + 32);
  v7 = *(const IID **)(a1 + 24);
  v19[1] = 0;
  v20 = 6;
  v21 = 3;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)&pServerInfo.dwReserved1 = 0;
  pServerInfo.pwszName = 0;
  *(_QWORD *)&pServerInfo.dwReserved2 = 0;
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v9 = CoCreateInstanceEx(v7, 0, v4, &pServerInfo, 1u, &pResults);
  if ( v9 >= 0 )
  {
    pItf = pResults.pItf;
    v9 = CscCom_SetClientProxyBlanket(pResults.pItf, v8, v10, v11);
    if ( v9 >= 0 )
      v9 = ((__int64 (__fastcall *)(IUnknown *, const IID *, __int64 *))pItf->lpVtbl->QueryInterface)(pItf, a2, a3);
    ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    if ( v9 >= 0 )
    {
      v13 = *a3;
      v9 = -2147024809;
      if ( !*a3 )
      {
LABEL_16:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        *a3 = 0;
        return (unsigned int)v9;
      }
      v14 = *(_QWORD **)(a1 + 8);
      v15 = *(_QWORD *)&a2->Data1 - *v14;
      if ( *(_QWORD *)&a2->Data1 == *v14 )
        v15 = *(_QWORD *)a2->Data4 - v14[1];
      if ( v15 )
      {
        v9 = -2147467262;
        goto LABEL_16;
      }
      if ( *(_DWORD *)(a1 + 16) )
      {
        v9 = -2147467259;
        goto LABEL_16;
      }
      *(_DWORD *)(a1 + 16) = 0;
      ppv = 0;
      v9 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, const IID *, __int64))(*(_QWORD *)ppv + 24LL))(
               ppv,
               v13,
               a2,
               a1 + 16);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      if ( v9 < 0 )
      {
        *(_DWORD *)(a1 + 16) = 0;
        goto LABEL_16;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005630  mov     [rsp-8+arg_8], rbx
0x180005635  mov     [rsp-8+arg_10], rsi
0x18000563a  push    rbp
0x18000563b  push    rdi
0x18000563c  push    r12
0x18000563e  push    r14
0x180005640  push    r15
0x180005642  lea     rbp, [rsp-37h]
0x180005647  sub     rsp, 90h
0x18000564e  xor     r12d, r12d
0x180005651  mov     [rbp+57h+var_80.pIID], rdx
0x180005655  mov     [r8], r12
0x180005658  lea     rax, [rbp+57h+var_48]
0x18000565c  mov     [rbp+57h+pServerInfo.pAuthInfo], rax
0x180005660  lea     r9, [rbp+57h+pServerInfo]; pServerInfo
0x180005664  lea     rax, [rbp+57h+var_80]
0x180005668  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x180005670  mov     rsi, r8
0x180005673  mov     [rsp+0B0h+pResults], rax; pResults
0x180005678  mov     r8d, [rcx+20h]; dwClsCtx
0x18000567c  mov     r14, rdx
0x18000567f  mov     rdi, rcx
0x180005682  mov     [rsp+0B0h+dwCount], 1; dwCount
0x18000568a  mov     rcx, [rcx+18h]; Clsid
0x18000568e  xor     edx, edx; punkOuter
0x180005690  mov     [rbp+57h+var_40], r12
0x180005694  mov     [rbp+57h+var_38], 6
0x18000569b  mov     [rbp+57h+var_34], 3
0x1800056a2  mov     [rbp+57h+var_30], r12
0x1800056a6  mov     [rbp+57h+var_28], r12
0x1800056aa  mov     qword ptr [rbp+57h+pServerInfo.dwReserved1], r12
0x1800056ae  mov     [rbp+57h+pServerInfo.pwszName], r12
0x1800056b2  mov     qword ptr [rbp+57h+pServerInfo.dwReserved2], r12
0x1800056b6  mov     [rbp+57h+var_80.pItf], r12
0x1800056ba  mov     qword ptr [rbp+57h+var_80.hr], r12
0x1800056be  call    cs:__imp_CoCreateInstanceEx
0x1800056c4  mov     ebx, eax
0x1800056c6  test    eax, eax
0x1800056c8  js      loc_1800057CA
0x1800056ce  mov     r15, [rbp+57h+var_80.pItf]
0x1800056d2  mov     rcx, r15; struct IUnknown *
0x1800056d5  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x1800056da  mov     ebx, eax
0x1800056dc  test    eax, eax
0x1800056de  js      short loc_1800056F6
0x1800056e0  mov     rax, [r15]
0x1800056e3  mov     r8, rsi
0x1800056e6  mov     rdx, r14
0x1800056e9  mov     rcx, r15
0x1800056ec  mov     rax, [rax]
0x1800056ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f4  mov     ebx, eax
0x1800056f6  mov     rax, [r15]
0x1800056f9  mov     rcx, r15
0x1800056fc  mov     rax, [rax+10h]
0x180005700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005705  test    ebx, ebx
0x180005707  js      loc_1800057CA
0x18000570d  mov     r15, [rsi]
0x180005710  mov     ebx, 80070057h
0x180005715  test    r15, r15
0x180005718  jz      loc_1800057B4
0x18000571e  mov     rcx, [rdi+8]
0x180005722  mov     rax, [r14]
0x180005725  sub     rax, [rcx]
0x180005728  jnz     short loc_180005732
0x18000572a  mov     rax, [r14+8]
0x18000572e  sub     rax, [rcx+8]
0x180005732  test    rax, rax
0x180005735  jz      short loc_18000573E
0x180005737  mov     ebx, 80004002h
0x18000573c  jmp     short loc_1800057B8
0x18000573e  cmp     [rdi+10h], r12d
0x180005742  jz      short loc_18000574B
0x180005744  mov     ebx, 80004005h
0x180005749  jmp     short loc_1800057B8
0x18000574b  lea     rax, [rbp+57h+ppv]
0x18000574f  mov     [rdi+10h], r12d
0x180005753  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000575a  mov     qword ptr [rsp+0B0h+dwCount], rax; ppv
0x18000575f  xor     edx, edx; pUnkOuter
0x180005761  mov     [rbp+57h+ppv], r12
0x180005765  mov     r8d, 1; dwClsContext
0x18000576b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005772  call    cs:__imp_CoCreateInstance
0x180005778  mov     ebx, eax
0x18000577a  test    eax, eax
0x18000577c  js      short loc_1800057AA
0x18000577e  mov     rcx, [rbp+57h+ppv]
0x180005782  lea     r9, [rdi+10h]
0x180005786  mov     r8, r14
0x180005789  mov     rdx, r15
0x18000578c  mov     rax, [rcx]
0x18000578f  mov     rax, [rax+18h]
0x180005793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005798  mov     rcx, [rbp+57h+ppv]
0x18000579c  mov     ebx, eax
0x18000579e  mov     rax, [rcx]
0x1800057a1  mov     rax, [rax+10h]
0x1800057a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057aa  test    ebx, ebx
0x1800057ac  jns     short loc_1800057CA
0x1800057ae  mov     [rdi+10h], r12d
0x1800057b2  jmp     short loc_1800057B8
0x1800057b4  test    ebx, ebx
0x1800057b6  jns     short loc_1800057CA
0x1800057b8  mov     rdx, [r15]
0x1800057bb  mov     rcx, r15
0x1800057be  mov     rax, [rdx+10h]
0x1800057c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c7  mov     [rsi], r12
0x1800057ca  lea     r11, [rsp+0B0h+var_20]
0x1800057d2  mov     eax, ebx
0x1800057d4  mov     rbx, [r11+38h]
0x1800057d8  mov     rsi, [r11+40h]
0x1800057dc  mov     rsp, r11
0x1800057df  pop     r15
0x1800057e1  pop     r14
0x1800057e3  pop     r12
0x1800057e5  pop     rdi
0x1800057e6  pop     rbp
0x1800057e7  retn
```
