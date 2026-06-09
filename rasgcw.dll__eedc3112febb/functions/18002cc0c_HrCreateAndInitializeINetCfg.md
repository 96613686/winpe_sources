# HrCreateAndInitializeINetCfg

- ea: `0x18002cc0c`
- end: `0x18002cd6c`
- name: `HrCreateAndInitializeINetCfg`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002990c`

## callees

- `0x18002cc0c`
- `0x18002cf2c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cc87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cc87`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cc36`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002cc36`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002cd56`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002cd56`

## pseudocode

```c
__int64 __fastcall HrCreateAndInitializeINetCfg(_DWORD *a1, LPVOID *a2, int a3, __int64 a4, __int64 a5)
{
  HRESULT v8; // eax
  HRESULT v9; // ebx
  int v10; // eax
  LPVOID v11; // rcx
  void (*v12)(void); // rax
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  *a1 = 1;
  v8 = CoInitializeEx(0, 6u);
  if ( v8 >= 0 )
  {
    *a1 = 1;
LABEL_6:
    ppv = 0;
    v9 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &ppv);
    if ( v9 < 0 )
    {
LABEL_18:
      if ( *a1 )
      {
        *a1 = 0;
        CoUninitialize();
      }
      return (unsigned int)v9;
    }
    v15 = 0;
    if ( !a3 )
      goto LABEL_12;
    v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_INetCfgLock, &v15);
    if ( v9 < 0 )
      goto LABEL_17;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, 0, a5, 0);
    v9 = v10;
    if ( v10 == 1 )
    {
      v9 = -2147180508;
      goto LABEL_17;
    }
    if ( v10 >= 0 )
    {
LABEL_12:
      v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
      if ( v9 < 0 )
      {
        if ( !v15 )
          goto LABEL_17;
        v12 = *(void (**)(void))(*(_QWORD *)v15 + 32LL);
      }
      else
      {
        v11 = ppv;
        *a2 = ppv;
        v12 = *(void (**)(void))(*(_QWORD *)v11 + 8LL);
      }
      v12();
    }
LABEL_17:
    ReleaseObj(v15);
    ReleaseObj(ppv);
    if ( v9 >= 0 )
      return (unsigned int)v9;
    goto LABEL_18;
  }
  v9 = 0;
  *a1 = 0;
  if ( v8 != -2147417850 )
    v9 = v8;
  if ( v9 >= 0 )
    goto LABEL_6;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002cc0c  mov     [rsp+arg_10], rbx
0x18002cc11  push    rsi
0x18002cc12  push    rdi
0x18002cc13  push    r14
0x18002cc15  sub     rsp, 30h
0x18002cc19  mov     qword ptr [rdx], 0
0x18002cc20  mov     r14, rdx
0x18002cc23  mov     dword ptr [rcx], 1
0x18002cc29  mov     rdi, rcx
0x18002cc2c  xor     ecx, ecx; pvReserved
0x18002cc2e  mov     edx, 6; dwCoInit
0x18002cc33  mov     esi, r8d
0x18002cc36  call    cs:__imp_CoInitializeEx
0x18002cc3c  test    eax, eax
0x18002cc3e  js      short loc_18002CC48
0x18002cc40  mov     dword ptr [rdi], 1
0x18002cc46  jmp     short loc_18002CC60
0x18002cc48  xor     ebx, ebx
0x18002cc4a  mov     dword ptr [rdi], 0
0x18002cc50  cmp     eax, 80010106h
0x18002cc55  cmovnz  ebx, eax
0x18002cc58  test    ebx, ebx
0x18002cc5a  js      loc_18002CD5C
0x18002cc60  xor     edx, edx; pUnkOuter
0x18002cc62  mov     [rsp+48h+arg_0], 0
0x18002cc6b  lea     rax, [rsp+48h+arg_0]
0x18002cc70  lea     r9, IID_INetCfg; riid
0x18002cc77  mov     [rsp+48h+ppv], rax; ppv
0x18002cc7c  lea     rcx, CLSID_CNetCfg; rclsid
0x18002cc83  lea     r8d, [rdx+1]; dwClsContext
0x18002cc87  call    cs:__imp_CoCreateInstance
0x18002cc8d  mov     ebx, eax
0x18002cc8f  test    eax, eax
0x18002cc91  js      loc_18002CD4B
0x18002cc97  mov     [rsp+48h+arg_8], 0
0x18002cca0  test    esi, esi
0x18002cca2  jz      short loc_18002CCF3
0x18002cca4  mov     rcx, [rsp+48h+arg_0]
0x18002cca9  lea     r8, [rsp+48h+arg_8]
0x18002ccae  lea     rdx, IID_INetCfgLock
0x18002ccb5  mov     rax, [rcx]
0x18002ccb8  mov     rax, [rax]
0x18002ccbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccc0  mov     ebx, eax
0x18002ccc2  test    eax, eax
0x18002ccc4  js      short loc_18002CD33
0x18002ccc6  mov     rcx, [rsp+48h+arg_8]
0x18002cccb  xor     r9d, r9d
0x18002ccce  mov     r8, [rsp+48h+arg_20]
0x18002ccd3  xor     edx, edx
0x18002ccd5  mov     rax, [rcx]
0x18002ccd8  mov     rax, [rax+18h]
0x18002ccdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cce1  mov     ebx, eax
0x18002cce3  cmp     eax, 1
0x18002cce6  jnz     short loc_18002CCEF
0x18002cce8  mov     ebx, 8004A024h
0x18002cced  jmp     short loc_18002CD33
0x18002ccef  test    eax, eax
0x18002ccf1  js      short loc_18002CD33
0x18002ccf3  mov     rcx, [rsp+48h+arg_0]
0x18002ccf8  xor     edx, edx
0x18002ccfa  mov     rax, [rcx]
0x18002ccfd  mov     rax, [rax+18h]
0x18002cd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd06  mov     ebx, eax
0x18002cd08  test    eax, eax
0x18002cd0a  js      short loc_18002CD1D
0x18002cd0c  mov     rcx, [rsp+48h+arg_0]
0x18002cd11  mov     [r14], rcx
0x18002cd14  mov     rax, [rcx]
0x18002cd17  mov     rax, [rax+8]
0x18002cd1b  jmp     short loc_18002CD2E
0x18002cd1d  mov     rcx, [rsp+48h+arg_8]
0x18002cd22  test    rcx, rcx
0x18002cd25  jz      short loc_18002CD33
0x18002cd27  mov     rax, [rcx]
0x18002cd2a  mov     rax, [rax+20h]
0x18002cd2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd33  mov     rcx, [rsp+48h+arg_8]
0x18002cd38  call    ReleaseObj
0x18002cd3d  mov     rcx, [rsp+48h+arg_0]
0x18002cd42  call    ReleaseObj
0x18002cd47  test    ebx, ebx
0x18002cd49  jns     short loc_18002CD5C
0x18002cd4b  cmp     dword ptr [rdi], 0
0x18002cd4e  jz      short loc_18002CD5C
0x18002cd50  mov     dword ptr [rdi], 0
0x18002cd56  call    cs:__imp_CoUninitialize
0x18002cd5c  mov     eax, ebx
0x18002cd5e  mov     rbx, [rsp+48h+arg_10]
0x18002cd63  add     rsp, 30h
0x18002cd67  pop     r14
0x18002cd69  pop     rdi
0x18002cd6a  pop     rsi
0x18002cd6b  retn
```
