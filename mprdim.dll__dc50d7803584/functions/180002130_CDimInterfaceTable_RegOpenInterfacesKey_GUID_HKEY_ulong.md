# CDimInterfaceTable::RegOpenInterfacesKey(_GUID *,HKEY__ * &,ulong &)

- ea: `0x180002130`
- end: `0x180002310`
- name: `?RegOpenInterfacesKey@CDimInterfaceTable@@AEAAKPEAU_GUID@@AEAPEAUHKEY__@@AEAK@Z`
- size: `480`
- prototype: `unsigned int(CDimInterfaceTable *__hidden this, struct _GUID *, HKEY *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800239f8`
- `0x180023e54`
- `0x180026e0c`

## callees

- `0x180002130`
- `0x18000def0`
- `0x180036924`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x18000227c`
- `rtutils!RouterLogEventW` at `0x18000227c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800021ea`
- `ADVAPI32!RegOpenKeyExW` at `0x1800021ea`
- `ADVAPI32!RegCloseKey` at `0x1800022db`
- `ADVAPI32!RegCloseKey` at `0x1800022db`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002238`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002238`

## string_xrefs

- `0x180002191`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18000229b`: `Cannot access the Registry key %s.`

## pseudocode

```c
LSTATUS __fastcall CDimInterfaceTable::RegOpenInterfacesKey(
        CDimInterfaceTable *this,
        struct _GUID *a2,
        HKEY *a3,
        unsigned int *a4)
{
  LPWSTR v8; // rsi
  __int64 v9; // rax
  LSTATUS v10; // ebx
  LSTATUS result; // eax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-858h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-854h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-850h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+70h] [rbp-848h] BYREF
  int v16; // [rsp+80h] [rbp-838h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-834h] BYREF

  *a3 = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  *a4 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v8 = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
  if ( *((_BYTE *)this + 116) && a2 )
  {
    v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v9 )
    {
      v10 = OpenInterfacesKey(a2, a3);
      if ( v10 )
        goto LABEL_10;
LABEL_9:
      result = RegQueryInfoKeyW(*a3, 0, 0, 0, a4, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      ++cbMaxValueNameLen;
      v10 = result;
      if ( !result )
        return result;
      goto LABEL_10;
    }
  }
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces",
          0,
          0x20019u,
          a3);
  if ( !v10 )
    goto LABEL_9;
LABEL_10:
  plpszSubStringArray = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
  if ( dword_180070F40 )
  {
    RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, v10);
    v8 = plpszSubStringArray;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v16, L"Cannot access the Registry key %s.", v8);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v16);
  }
  if ( *a3 )
  {
    RegCloseKey(*a3);
    *a3 = 0;
  }
  *a4 = 0;
  return v10;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  push    rbp
0x180002136  push    rsi
0x180002137  push    rdi
0x180002138  push    r14
0x18000213a  push    r15
0x18000213c  sub     rsp, 890h
0x180002143  mov     rax, cs:__security_cookie
0x18000214a  xor     rax, rsp
0x18000214d  mov     [rsp+8B8h+var_38], rax
0x180002155  xor     ebp, ebp
0x180002157  mov     rdi, r8
0x18000215a  mov     [r8], rbp
0x18000215d  mov     r15, rdx
0x180002160  mov     rbx, rcx
0x180002163  mov     [rsp+8B8h+cbMaxValueNameLen], ebp
0x180002167  mov     r8d, 7FCh; Size
0x18000216d  mov     [rsp+8B8h+cValues], ebp
0x180002171  xor     edx, edx; Val
0x180002173  mov     [rsp+8B8h+cbMaxValueLen], ebp
0x180002177  lea     rcx, [rsp+8B8h+var_834]; void *
0x18000217f  mov     [r9], ebp
0x180002182  mov     r14, r9
0x180002185  mov     [rsp+8B8h+var_838], ebp
0x18000218c  call    memset_0
0x180002191  lea     rsi, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x180002198  cmp     [rbx+74h], bpl
0x18000219c  jz      short loc_1800021D2
0x18000219e  test    r15, r15
0x1800021a1  jz      short loc_1800021D2
0x1800021a3  mov     rax, [r15]
0x1800021a6  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800021ad  jnz     short loc_1800021BA
0x1800021af  mov     rax, [r15+8]
0x1800021b3  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800021ba  test    rax, rax
0x1800021bd  jz      short loc_1800021D2
0x1800021bf  mov     rdx, rdi; HKEY *
0x1800021c2  mov     rcx, r15; struct _GUID *
0x1800021c5  call    OpenInterfacesKey
0x1800021ca  mov     ebx, eax
0x1800021cc  test    eax, eax
0x1800021ce  jz      short loc_1800021F6
0x1800021d0  jmp     short loc_18000224C
0x1800021d2  mov     r9d, 20019h; samDesired
0x1800021d8  mov     [rsp+8B8h+phkResult], rdi; phkResult
0x1800021dd  xor     r8d, r8d; ulOptions
0x1800021e0  mov     rdx, rsi; lpSubKey
0x1800021e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800021ea  call    cs:__imp_RegOpenKeyExW
0x1800021f0  mov     ebx, eax
0x1800021f2  test    eax, eax
0x1800021f4  jnz     short loc_18000224C
0x1800021f6  mov     rcx, [rdi]; hKey
0x1800021f9  lea     rax, [rsp+8B8h+cbMaxValueLen]
0x1800021fe  mov     [rsp+8B8h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x180002203  xor     r9d, r9d; lpReserved
0x180002206  mov     [rsp+8B8h+lpcbSecurityDescriptor], rbp; lpcbSecurityDescriptor
0x18000220b  xor     r8d, r8d; lpcchClass
0x18000220e  mov     [rsp+8B8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180002213  xor     edx, edx; lpClass
0x180002215  lea     rax, [rsp+8B8h+cbMaxValueNameLen]
0x18000221a  mov     [rsp+8B8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000221f  lea     rax, [rsp+8B8h+cValues]
0x180002224  mov     [rsp+8B8h+lpcValues], rax; lpcValues
0x180002229  mov     [rsp+8B8h+lpcbMaxClassLen], rbp; lpcbMaxClassLen
0x18000222e  mov     [rsp+8B8h+lpcbMaxSubKeyLen], rbp; lpcbMaxSubKeyLen
0x180002233  mov     [rsp+8B8h+phkResult], r14; lpcSubKeys
0x180002238  call    cs:__imp_RegQueryInfoKeyW
0x18000223e  inc     [rsp+8B8h+cbMaxValueNameLen]
0x180002242  mov     ebx, eax
0x180002244  test    eax, eax
0x180002246  jz      loc_1800022E9
0x18000224c  cmp     cs:dword_180070F40, ebp
0x180002252  mov     [rsp+8B8h+plpszSubStringArray], rsi
0x180002257  jbe     short loc_180002287
0x180002259  mov     rcx, cs:hLogHandle; hLogHandle
0x180002260  lea     rax, [rsp+8B8h+plpszSubStringArray]
0x180002265  mov     edx, 1; dwEventType
0x18000226a  mov     dword ptr [rsp+8B8h+lpcbMaxSubKeyLen], ebx; dwErrorCode
0x18000226e  mov     r9d, edx; dwSubStringCount
0x180002271  mov     [rsp+8B8h+phkResult], rax; plpszSubStringArray
0x180002276  mov     r8d, 4E84h; dwMessageId
0x18000227c  call    cs:__imp_RouterLogEventW
0x180002282  mov     rsi, [rsp+8B8h+plpszSubStringArray]
0x180002287  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18000228e  jz      short loc_1800022D3
0x180002290  mov     r8, rsi
0x180002293  mov     word ptr [rsp+8B8h+var_838], bp
0x18000229b  lea     rdx, aCannotAccessTh_1; "Cannot access the Registry key %s."
0x1800022a2  lea     rcx, [rsp+8B8h+var_838]
0x1800022aa  call    FormatRRASErrorString
0x1800022af  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800022b6  jz      short loc_1800022D3
0x1800022b8  lea     r8, [rsp+8B8h+var_838]
0x1800022c0  lea     rdx, RasDimTraceAdminError
0x1800022c7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800022ce  call    McTemplateU0z_EventWriteTransfer
0x1800022d3  mov     rcx, [rdi]; hKey
0x1800022d6  test    rcx, rcx
0x1800022d9  jz      short loc_1800022E4
0x1800022db  call    cs:__imp_RegCloseKey
0x1800022e1  mov     [rdi], rbp
0x1800022e4  mov     [r14], ebp
0x1800022e7  mov     eax, ebx
0x1800022e9  mov     rcx, [rsp+8B8h+var_38]
0x1800022f1  xor     rcx, rsp; StackCookie
0x1800022f4  call    __security_check_cookie
0x1800022f9  mov     rbx, [rsp+8B8h+arg_0]
0x180002301  add     rsp, 890h
0x180002308  pop     r15
0x18000230a  pop     r14
0x18000230c  pop     rdi
0x18000230d  pop     rsi
0x18000230e  pop     rbp
0x18000230f  retn
```
