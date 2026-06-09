# GetZoneActionPolicy(ushort const *,ulong,ulong *)

- ea: `0x1800ca09c`
- end: `0x1800ca20c`
- name: `?GetZoneActionPolicy@@YAJPEBGKPEAK@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800413b4`

## callees

- `0x1800c8f34`
- `0x1800ca09c`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800ca0f0`
- `ole32!CoCreateInstance` at `0x1800ca154`
- `ole32!CoCreateInstance` at `0x1800ca0f0`
- `ole32!CoCreateInstance` at `0x1800ca154`

## pseudocode

```c
__int64 __fastcall GetZoneActionPolicy(const unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  HRESULT v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  LPVOID v10; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v12; // [rsp+80h] [rbp+30h] BYREF
  LPVOID v13; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v12 = 3;
  v10 = 0;
  v11 = 0;
  v5 = CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, &v13);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_10;
    LODWORD(ppv) = 4411;
    v7 = 4516873;
    goto LABEL_4;
  }
  v5 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, &v10);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v10 + 40LL))(
           v10,
           a1,
           &v11,
           0);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned int *, int, _DWORD))(*(_QWORD *)v13 + 56LL))(
             v13,
             v11,
             6656,
             &v12,
             4,
             0);
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    LODWORD(ppv) = 4417;
    v7 = 4523017;
LABEL_4:
    bidTraceW(off_18012A218[0], v7, L"<GetZoneActionPolicy|ADO|ERR> 0x%08x{HRESULT} line %d\n", (unsigned int)v5, ppv);
  }
LABEL_10:
  if ( v13 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v10 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  *a3 = v12;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ca09c  mov     [rsp-18h+arg_0], rbx
0x1800ca0a1  mov     [rsp-18h+arg_8], edx
0x1800ca0a5  push    rbp
0x1800ca0a6  push    rsi
0x1800ca0a7  push    rdi
0x1800ca0a8  mov     rbp, rsp
0x1800ca0ab  sub     rsp, 50h
0x1800ca0af  xor     edx, edx; pUnkOuter
0x1800ca0b1  mov     [rbp+arg_18], 0
0x1800ca0b9  mov     rdi, r8
0x1800ca0bc  mov     [rbp+arg_10], 3
0x1800ca0c3  mov     rsi, rcx
0x1800ca0c6  mov     [rbp+var_10], 0
0x1800ca0ce  lea     rax, [rbp+arg_18]
0x1800ca0d2  mov     [rbp+arg_8], 0
0x1800ca0d9  lea     r8d, [rdx+1]; dwClsContext
0x1800ca0dd  mov     [rsp+50h+ppv], rax; ppv
0x1800ca0e2  lea     r9, IID_IInternetZoneManager; riid
0x1800ca0e9  lea     rcx, CLSID_InternetZoneManager; rclsid
0x1800ca0f0  call    cs:__imp_CoCreateInstance
0x1800ca0f7  nop     dword ptr [rax+rax+00h]
0x1800ca0fc  mov     ebx, eax
0x1800ca0fe  test    eax, eax
0x1800ca100  jns     short loc_1800CA137
0x1800ca102  test    byte ptr cs:_bidGblFlags, 2
0x1800ca109  jz      loc_1800CA1CD
0x1800ca10f  mov     dword ptr [rsp+50h+ppv], 113Bh
0x1800ca117  mov     edx, 44EC09h
0x1800ca11c  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800ca123  lea     r8, aGetzoneactionp; "<GetZoneActionPolicy|ADO|ERR> 0x%08x{HR"...
0x1800ca12a  mov     r9d, eax
0x1800ca12d  call    _bidTraceW
0x1800ca132  jmp     loc_1800CA1CD
0x1800ca137  xor     edx, edx; pUnkOuter
0x1800ca139  lea     rax, [rbp+var_10]
0x1800ca13d  lea     r9, IID_IInternetSecurityManager; riid
0x1800ca144  mov     [rsp+50h+ppv], rax; ppv
0x1800ca149  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800ca150  lea     r8d, [rdx+1]; dwClsContext
0x1800ca154  call    cs:__imp_CoCreateInstance
0x1800ca15b  nop     dword ptr [rax+rax+00h]
0x1800ca160  mov     ebx, eax
0x1800ca162  test    eax, eax
0x1800ca164  jns     short loc_1800CA17E
0x1800ca166  test    byte ptr cs:_bidGblFlags, 2
0x1800ca16d  jz      short loc_1800CA1CD
0x1800ca16f  mov     dword ptr [rsp+50h+ppv], 1141h
0x1800ca177  mov     edx, 450409h
0x1800ca17c  jmp     short loc_1800CA11C
0x1800ca17e  mov     rcx, [rbp+var_10]
0x1800ca182  lea     r8, [rbp+arg_8]
0x1800ca186  xor     r9d, r9d
0x1800ca189  mov     rdx, rsi
0x1800ca18c  mov     rax, [rcx]
0x1800ca18f  mov     rax, [rax+28h]
0x1800ca193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca198  mov     ebx, eax
0x1800ca19a  test    eax, eax
0x1800ca19c  js      short loc_1800CA1CD
0x1800ca19e  mov     rcx, [rbp+arg_18]
0x1800ca1a2  lea     r9, [rbp+arg_10]
0x1800ca1a6  mov     edx, [rbp+arg_8]
0x1800ca1a9  mov     r8d, 1A00h
0x1800ca1af  mov     [rsp+50h+var_28], 0
0x1800ca1b7  mov     dword ptr [rsp+50h+ppv], 4
0x1800ca1bf  mov     rax, [rcx]
0x1800ca1c2  mov     rax, [rax+38h]
0x1800ca1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca1cb  mov     ebx, eax
0x1800ca1cd  mov     rcx, [rbp+arg_18]
0x1800ca1d1  test    rcx, rcx
0x1800ca1d4  jz      short loc_1800CA1E2
0x1800ca1d6  mov     rax, [rcx]
0x1800ca1d9  mov     rax, [rax+10h]
0x1800ca1dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca1e2  mov     rcx, [rbp+var_10]
0x1800ca1e6  test    rcx, rcx
0x1800ca1e9  jz      short loc_1800CA1F7
0x1800ca1eb  mov     rax, [rcx]
0x1800ca1ee  mov     rax, [rax+10h]
0x1800ca1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca1f7  mov     eax, [rbp+arg_10]
0x1800ca1fa  mov     [rdi], eax
0x1800ca1fc  mov     eax, ebx
0x1800ca1fe  mov     rbx, [rsp+50h+arg_0]
0x1800ca203  add     rsp, 50h
0x1800ca207  pop     rdi
0x1800ca208  pop     rsi
0x1800ca209  pop     rbp
0x1800ca20a  retn
```
