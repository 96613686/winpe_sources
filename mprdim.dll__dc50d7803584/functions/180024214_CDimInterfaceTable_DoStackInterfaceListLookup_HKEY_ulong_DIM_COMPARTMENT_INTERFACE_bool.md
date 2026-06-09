# CDimInterfaceTable::DoStackInterfaceListLookup(HKEY__ *,ulong,_DIM_COMPARTMENT_INTERFACE *,bool &)

- ea: `0x180024214`
- end: `0x18002444a`
- name: `?DoStackInterfaceListLookup@CDimInterfaceTable@@AEAAKPEAUHKEY__@@KPEAU_DIM_COMPARTMENT_INTERFACE@@AEA_N@Z`
- size: `566`
- prototype: `__int64 __fastcall(CDimInterfaceTable *this, HKEY, unsigned int, struct _DIM_COMPARTMENT_INTERFACE *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x18000def0`
- `0x180024214`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800242ba`
- `ADVAPI32!RegQueryValueExW` at `0x180024358`
- `ADVAPI32!RegQueryValueExW` at `0x1800243ab`
- `ADVAPI32!RegQueryValueExW` at `0x1800242ba`
- `ADVAPI32!RegQueryValueExW` at `0x180024358`
- `ADVAPI32!RegQueryValueExW` at `0x1800243ab`

## string_xrefs

- `0x1800242e1`: `Error %d occured while querying registry value %s.`
- `0x180024349`: `VsidOrVlanTag`
- `0x180024374`: `Invalid Interface entry - VsidOrVlanTag is set to 0. Removing this interface from registry.`
- `0x1800243c2`: `Error %d occured while reading multi tenant interface LUID. Removing this interface from registry.`

## pseudocode

```c
__int64 __fastcall CDimInterfaceTable::DoStackInterfaceListLookup(
        CDimInterfaceTable *this,
        HKEY a2,
        unsigned int a3,
        struct _DIM_COMPARTMENT_INTERFACE *a4,
        bool *a5)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  const wchar_t *v10; // r8
  unsigned int i; // r8d
  __int64 v12; // r9
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE lpData[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE v18[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[2044]; // [rsp+54h] [rbp-ACh] BYREF

  *(_DWORD *)lpData = 0;
  *(_QWORD *)v18 = 0;
  *(_DWORD *)Data = 0;
  *a5 = 0;
  Type = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  cbData = 4;
  v8 = RegQueryValueExW(a2, L"Type", 0, &Type, Data, &cbData);
  v9 = v8;
  if ( v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return v9;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"Error %d occured while querying registry value %s.", v8, L"Type");
  }
  else
  {
    if ( *(_DWORD *)Data != 3 )
    {
      *a5 = 1;
      return v9;
    }
    cbData = 4;
    v9 = RegQueryValueExW(a2, L"VsidOrVlanTag", 0, &Type, lpData, &cbData);
    if ( !*(_DWORD *)lpData )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        return v9;
      v10 = L"Invalid Interface entry - VsidOrVlanTag is set to 0. Removing this interface from registry.";
      goto LABEL_6;
    }
    cbData = 8;
    v9 = RegQueryValueExW(a2, L"MultiTenantIfLuid", 0, &Type, v18, &cbData);
    if ( !v9 )
    {
      for ( i = 0; i < a3; ++i )
      {
        v12 = 536LL * i;
        if ( *(_DWORD *)((char *)a4 + v12) == *(_DWORD *)lpData && *(_QWORD *)((char *)a4 + v12 + 8) == *(_QWORD *)v18 )
        {
          *(_WORD *)((char *)a4 + v12 + 532) = 1;
          *a5 = 1;
          return v9;
        }
      }
      return v9;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      return v9;
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"Error %d occured while reading multi tenant interface LUID. Removing this interface from registry.",
      v9);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    v10 = (const wchar_t *)&v19;
LABEL_6:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, v10);
  }
  return v9;
}

```

## disassembly

```asm
0x180024214  mov     [rsp-8+arg_0], rbx
0x180024219  push    rbp
0x18002421a  push    rsi
0x18002421b  push    rdi
0x18002421c  push    r14
0x18002421e  push    r15
0x180024220  lea     rbp, [rsp-760h]
0x180024228  sub     rsp, 860h
0x18002422f  mov     rax, cs:__security_cookie
0x180024236  xor     rax, rsp
0x180024239  mov     [rbp+780h+var_30], rax
0x180024240  mov     rsi, [rbp+780h+arg_20]
0x180024247  lea     rcx, [rsp+880h+var_82C]; void *
0x18002424c  mov     r15d, r8d
0x18002424f  mov     dword ptr [rsp+880h+var_848], 0
0x180024257  mov     r14, rdx
0x18002425a  mov     qword ptr [rsp+880h+var_840], 0
0x180024263  xor     eax, eax
0x180024265  mov     dword ptr [rsp+880h+Data], 0
0x18002426d  xor     edx, edx; Val
0x18002426f  mov     byte ptr [rsi], 0
0x180024272  mov     r8d, 7FCh; Size
0x180024278  mov     [rsp+880h+Type], 0
0x180024280  mov     rdi, r9
0x180024283  mov     [rsp+880h+var_830], eax
0x180024287  call    memset_0
0x18002428c  lea     rax, [rsp+880h+cbData]
0x180024291  mov     [rsp+880h+cbData], 4
0x180024299  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18002429e  lea     r9, [rsp+880h+Type]; lpType
0x1800242a3  lea     rax, [rsp+880h+Data]
0x1800242a8  xor     r8d, r8d; lpReserved
0x1800242ab  lea     rdx, aType; "Type"
0x1800242b2  mov     [rsp+880h+lpData], rax; lpData
0x1800242b7  mov     rcx, r14; hKey
0x1800242ba  call    cs:__imp_RegQueryValueExW
0x1800242c0  mov     ebx, eax
0x1800242c2  test    eax, eax
0x1800242c4  jz      short loc_18002431F
0x1800242c6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800242cd  jz      loc_180024422
0x1800242d3  xor     ecx, ecx
0x1800242d5  lea     r9, aType; "Type"
0x1800242dc  mov     word ptr [rsp+880h+var_830], cx
0x1800242e1  lea     rdx, aErrorDOccuredW_7; "Error %d occured while querying registr"...
0x1800242e8  lea     rcx, [rsp+880h+var_830]
0x1800242ed  mov     r8d, eax
0x1800242f0  call    FormatRRASErrorString
0x1800242f5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800242fc  jz      loc_180024422
0x180024302  lea     r8, [rsp+880h+var_830]
0x180024307  lea     rdx, RasDimTraceError
0x18002430e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024315  call    McTemplateU0z_EventWriteTransfer
0x18002431a  jmp     loc_180024422
0x18002431f  cmp     dword ptr [rsp+880h+Data], 3
0x180024324  jnz     loc_18002441F
0x18002432a  lea     rax, [rsp+880h+cbData]
0x18002432f  mov     [rsp+880h+cbData], 4
0x180024337  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18002433c  lea     r9, [rsp+880h+Type]; lpType
0x180024341  lea     rax, [rsp+880h+var_848]
0x180024346  xor     r8d, r8d; lpReserved
0x180024349  lea     rdx, aVsidorvlantag; "VsidOrVlanTag"
0x180024350  mov     [rsp+880h+lpData], rax; lpData
0x180024355  mov     rcx, r14; hKey
0x180024358  call    cs:__imp_RegQueryValueExW
0x18002435e  cmp     dword ptr [rsp+880h+var_848], 0
0x180024363  mov     ebx, eax
0x180024365  jnz     short loc_18002437D
0x180024367  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002436e  jz      loc_180024422
0x180024374  lea     r8, aInvalidInterfa; "Invalid Interface entry - VsidOrVlanTag"...
0x18002437b  jmp     short loc_180024307
0x18002437d  lea     rax, [rsp+880h+cbData]
0x180024382  mov     [rsp+880h+cbData], 8
0x18002438a  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18002438f  lea     r9, [rsp+880h+Type]; lpType
0x180024394  lea     rax, [rsp+880h+var_840]
0x180024399  xor     r8d, r8d; lpReserved
0x18002439c  lea     rdx, aMultitenantifl; "MultiTenantIfLuid"
0x1800243a3  mov     [rsp+880h+lpData], rax; lpData
0x1800243a8  mov     rcx, r14; hKey
0x1800243ab  call    cs:__imp_RegQueryValueExW
0x1800243b1  mov     ebx, eax
0x1800243b3  test    eax, eax
0x1800243b5  jz      short loc_1800243E0
0x1800243b7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800243be  jz      short loc_180024422
0x1800243c0  xor     eax, eax
0x1800243c2  lea     rdx, aErrorDOccuredW_2; "Error %d occured while reading multi te"...
0x1800243c9  mov     r8d, ebx
0x1800243cc  mov     word ptr [rsp+880h+var_830], ax
0x1800243d1  lea     rcx, [rsp+880h+var_830]
0x1800243d6  call    FormatRRASErrorString
0x1800243db  jmp     loc_1800242F5
0x1800243e0  mov     r10d, dword ptr [rsp+880h+var_848]
0x1800243e5  xor     r8d, r8d
0x1800243e8  mov     rax, qword ptr [rsp+880h+var_840]
0x1800243ed  lea     edx, [r8+1]
0x1800243f1  cmp     r8d, r15d
0x1800243f4  jnb     short loc_180024422
0x1800243f6  mov     ecx, r8d
0x1800243f9  imul    r9, rcx, 218h
0x180024400  cmp     [r9+rdi], r10d
0x180024404  jnz     short loc_18002440D
0x180024406  cmp     [r9+rdi+8], rax
0x18002440b  jz      short loc_180024412
0x18002440d  add     r8d, edx
0x180024410  jmp     short loc_1800243F1
0x180024412  mov     [r9+rdi+214h], dx
0x18002441b  mov     [rsi], dl
0x18002441d  jmp     short loc_180024422
0x18002441f  mov     byte ptr [rsi], 1
0x180024422  mov     eax, ebx
0x180024424  mov     rcx, [rbp+780h+var_30]
0x18002442b  xor     rcx, rsp; StackCookie
0x18002442e  call    __security_check_cookie
0x180024433  mov     rbx, [rsp+880h+arg_0]
0x18002443b  add     rsp, 860h
0x180024442  pop     r15
0x180024444  pop     r14
0x180024446  pop     rdi
0x180024447  pop     rsi
0x180024448  pop     rbp
0x180024449  retn
```
