# ReadQoSPoliciesFromRegistry

- ea: `0x180037308`
- end: `0x180037486`
- name: `ReadQoSPoliciesFromRegistry`
- size: `382`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180036a40`
- `0x18003c810`
- `0x18003fde0`

## callees

- `0x180037308`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800373cc`
- `ADVAPI32!RegQueryValueExW` at `0x1800373cc`

## string_xrefs

- `0x180037421`: `ReadQoSPoliciesFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadQoSPoliciesFromRegistry(HKEY hKey, _DWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  int v8; // edx
  __int64 v9; // rcx
  BOOL v10; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[2044]; // [rsp+44h] [rbp-BCh] BYREF

  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( a2 && hKey )
  {
    v4 = 0;
    *a2 = 2;
    v5 = 0;
    while ( (unsigned int)v5 < 2 )
    {
      cbData = 4;
      v6 = L"TxBandwidthKbps";
      if ( (_DWORD)v5 )
        v6 = L"RxBandwidthKbps";
      v7 = RegQueryValueExW(hKey, v6, 0, &Type, Data, &cbData);
      v4 = v7;
      if ( v7 == 2 )
      {
        v8 = 0;
        *(_DWORD *)Data = 0;
        v4 = 0;
      }
      else
      {
        if ( v7 || Type != 4 )
          goto LABEL_13;
        v8 = *(_DWORD *)Data;
      }
      v9 = 3 * v5;
      a2[v9 + 1] = v8;
      v10 = v5 != 0;
      v5 = (unsigned int)(v5 + 1);
      a2[v9 + 2] = v10;
    }
  }
  else
  {
LABEL_13:
    v4 = 87;
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"%s: failed: %d.", L"ReadQoSPoliciesFromRegistry");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v15);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180037308  mov     [rsp-8+arg_10], rbx
0x18003730d  mov     [rsp-8+arg_18], rsi
0x180037312  push    rbp
0x180037313  push    rdi
0x180037314  push    r14
0x180037316  lea     rbp, [rsp-750h]
0x18003731e  sub     rsp, 850h
0x180037325  mov     rax, cs:__security_cookie
0x18003732c  xor     rax, rsp
0x18003732f  mov     [rbp+760h+var_20], rax
0x180037336  mov     rsi, rdx
0x180037339  mov     [rsp+860h+cbData], 0
0x180037341  mov     r14, rcx
0x180037344  mov     dword ptr [rsp+860h+Data], 0
0x18003734c  xor     eax, eax
0x18003734e  mov     [rsp+860h+Type], 0
0x180037356  xor     edx, edx; Val
0x180037358  mov     [rsp+860h+var_820], eax
0x18003735c  lea     rcx, [rsp+860h+var_81C]; void *
0x180037361  mov     r8d, 7FCh; Size
0x180037367  call    memset_0
0x18003736c  test    rsi, rsi
0x18003736f  jz      loc_18003740C
0x180037375  test    r14, r14
0x180037378  jz      loc_18003740C
0x18003737e  xor     ebx, ebx
0x180037380  mov     dword ptr [rsi], 2
0x180037386  xor     edi, edi
0x180037388  cmp     edi, 2
0x18003738b  jnb     loc_18003745D
0x180037391  lea     rax, aRxbandwidthkbp; "RxBandwidthKbps"
0x180037398  mov     [rsp+860h+cbData], 4
0x1800373a0  test    edi, edi
0x1800373a2  lea     rdx, aTxbandwidthkbp; "TxBandwidthKbps"
0x1800373a9  lea     r9, [rsp+860h+Type]; lpType
0x1800373ae  mov     rcx, r14; hKey
0x1800373b1  cmovnz  rdx, rax; lpValueName
0x1800373b5  lea     rax, [rsp+860h+cbData]
0x1800373ba  mov     [rsp+860h+lpcbData], rax; lpcbData
0x1800373bf  xor     r8d, r8d; lpReserved
0x1800373c2  lea     rax, [rsp+860h+Data]
0x1800373c7  mov     [rsp+860h+lpData], rax; lpData
0x1800373cc  call    cs:__imp_RegQueryValueExW
0x1800373d2  mov     ebx, eax
0x1800373d4  cmp     eax, 2
0x1800373d7  jnz     short loc_1800373E3
0x1800373d9  xor     edx, edx
0x1800373db  mov     dword ptr [rsp+860h+Data], edx
0x1800373df  xor     ebx, ebx
0x1800373e1  jmp     short loc_1800373F2
0x1800373e3  test    eax, eax
0x1800373e5  jnz     short loc_18003740C
0x1800373e7  cmp     [rsp+860h+Type], 4
0x1800373ec  jnz     short loc_18003740C
0x1800373ee  mov     edx, dword ptr [rsp+860h+Data]
0x1800373f2  xor     eax, eax
0x1800373f4  lea     rcx, [rdi+rdi*2]
0x1800373f8  test    edi, edi
0x1800373fa  mov     [rsi+rcx*4+4], edx
0x1800373fe  setnz   al
0x180037401  inc     edi
0x180037403  mov     [rsi+rcx*4+8], eax
0x180037407  jmp     loc_180037388
0x18003740c  mov     r9d, 57h ; 'W'
0x180037412  mov     ebx, r9d
0x180037415  cmp     qword ptr cs:xmmword_180071090, 0
0x18003741d  jz      short loc_18003745D
0x18003741f  xor     eax, eax
0x180037421  lea     r8, aReadqospolicie; "ReadQoSPoliciesFromRegistry"
0x180037428  lea     rdx, aSFailedD; "%s: failed: %d."
0x18003742f  mov     word ptr [rsp+860h+var_820], ax
0x180037434  lea     rcx, [rsp+860h+var_820]
0x180037439  call    FormatRRASErrorString
0x18003743e  mov     rdx, qword ptr cs:xmmword_180071090
0x180037445  lea     r8, [rsp+860h+var_820]
0x18003744a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180037451  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180037458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003745d  mov     eax, ebx
0x18003745f  mov     rcx, [rbp+760h+var_20]
0x180037466  xor     rcx, rsp; StackCookie
0x180037469  call    __security_check_cookie
0x18003746e  lea     r11, [rsp+860h+var_10]
0x180037476  mov     rbx, [r11+30h]
0x18003747a  mov     rsi, [r11+38h]
0x18003747e  mov     rsp, r11
0x180037481  pop     r14
0x180037483  pop     rdi
0x180037484  pop     rbp
0x180037485  retn
```
