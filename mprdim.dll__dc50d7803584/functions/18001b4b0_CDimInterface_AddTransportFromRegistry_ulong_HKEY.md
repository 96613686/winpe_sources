# CDimInterface::AddTransportFromRegistry(ulong,HKEY__ *)

- ea: `0x18001b4b0`
- end: `0x18001b709`
- name: `?AddTransportFromRegistry@CDimInterface@@QEAAKKPEAUHKEY__@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(GUID *this, int, HKEY)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800091dc`
- `0x1800239f8`
- `0x180023e54`

## callees

- `0x18000df70`
- `0x18001b1ec`
- `0x18001b4b0`
- `0x18001c418`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b679`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b6fc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b679`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b6fc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001b592`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001b592`

## string_xrefs

- `0x18001b618`: `CDimInterface::AddTransportFromRegistry: GetInfoFromRegistryKey returned error %d`

## pseudocode

```c
__int64 __fastcall CDimInterface::AddTransportFromRegistry(GUID *this, int a2, HKEY a3)
{
  int v6; // r12d
  unsigned int v7; // ebx
  DWORD i; // edi
  unsigned int InfoFromRegistryKey; // eax
  __int64 v10; // rax
  __int128 *v11; // r9
  void *v13; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v15; // [rsp+6Ch] [rbp-94h] BYREF
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v17[2]; // [rsp+78h] [rbp-88h] BYREF
  void *v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+88h] [rbp-78h]
  GUID ActivityId; // [rsp+98h] [rbp-68h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-58h] BYREF
  int v22; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v23; // [rsp+BCh] [rbp-44h]
  __int128 v24; // [rsp+CCh] [rbp-34h]
  int v25; // [rsp+DCh] [rbp-24h]
  int v26; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  cSubKeys = 0;
  ActivityId = 0;
  v21 = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v6 = SetActivityId(this + 194);
  v7 = RegQueryInfoKeyW(a3, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( !v7 )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      v13 = 0;
      v16 = 0;
      v15 = 0;
      InfoFromRegistryKey = CDimInterface::GetInfoFromRegistryKey(this, a3, i, &v13, &v16, &v15);
      v7 = InfoFromRegistryKey;
      if ( InfoFromRegistryKey )
      {
        if ( InfoFromRegistryKey == 1246 )
          goto LABEL_19;
        if ( InfoFromRegistryKey != 50 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            LOWORD(v26) = 0;
            LOWORD(v22) = 0;
            FormatRRASErrorString(
              &v26,
              L"CDimInterface::AddTransportFromRegistry: GetInfoFromRegistryKey returned error %d",
              InfoFromRegistryKey);
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              v10 = (*(__int64 (__fastcall **)(GUID *))(*(_QWORD *)&this->Data1 + 280LL))(this);
              v11 = &v21;
              if ( this != (GUID *)-3104LL )
                LODWORD(v11) = (_DWORD)this + 3104;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceError,
                (unsigned int)&v26,
                (_DWORD)v11,
                v10,
                (__int64)&v22);
            }
          }
          operator delete[](v13);
          break;
        }
      }
      else if ( !a2 || a2 == v15 )
      {
        v17[0] = 0;
        v19 = 0;
        v18 = v13;
        v17[1] = v16;
        CDimInterface::AddTransport((CDimInterface *)this, v15, (struct _DIM_INTERFACE_CONTAINER *)v17);
LABEL_19:
        v7 = 0;
      }
      operator delete[](v13);
    }
  }
  if ( v6 )
    ReSetActivityId(&ActivityId);
  return v7;
}

```

## disassembly

```asm
0x18001b4b0  mov     [rsp-8+arg_8], rbx
0x18001b4b5  push    rbp
0x18001b4b6  push    rsi
0x18001b4b7  push    rdi
0x18001b4b8  push    r12
0x18001b4ba  push    r13
0x18001b4bc  push    r14
0x18001b4be  push    r15
0x18001b4c0  lea     rbp, [rsp-7F0h]
0x18001b4c8  sub     rsp, 8F0h
0x18001b4cf  mov     rax, cs:__security_cookie
0x18001b4d6  xor     rax, rsp
0x18001b4d9  mov     [rbp+820h+var_40], rax
0x18001b4e0  mov     r13, r8
0x18001b4e3  mov     r14d, edx
0x18001b4e6  mov     rsi, rcx
0x18001b4e9  mov     [rsp+920h+cSubKeys], 0
0x18001b4f1  xorps   xmm0, xmm0
0x18001b4f4  movups  xmmword ptr [rbp+820h+ActivityId.Data1], xmm0
0x18001b4f8  xorps   xmm1, xmm1
0x18001b4fb  movups  [rbp+820h+var_878], xmm1
0x18001b4ff  xor     eax, eax
0x18001b501  mov     [rbp+820h+var_840], eax
0x18001b504  xor     edx, edx; Val
0x18001b506  mov     r8d, 7FCh; Size
0x18001b50c  lea     rcx, [rbp+820h+var_83C]; void *
0x18001b510  call    memset_0
0x18001b515  xor     eax, eax
0x18001b517  mov     [rbp+820h+var_868], eax
0x18001b51a  xorps   xmm0, xmm0
0x18001b51d  movups  [rbp+820h+var_864], xmm0
0x18001b521  movups  [rbp+820h+var_854], xmm0
0x18001b525  mov     [rbp+820h+var_844], eax
0x18001b528  lea     r15, [rsi+0C20h]
0x18001b52f  lea     rdx, [rbp+820h+ActivityId]
0x18001b533  mov     rcx, r15; ActivityId
0x18001b536  call    SetActivityId
0x18001b53b  mov     r12d, eax
0x18001b53e  mov     [rsp+920h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001b547  mov     [rsp+920h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18001b550  mov     [rsp+920h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18001b559  mov     [rsp+920h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18001b562  mov     [rsp+920h+lpcValues], 0; lpcValues
0x18001b56b  mov     [rsp+920h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18001b574  mov     [rsp+920h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18001b57d  lea     rax, [rsp+920h+cSubKeys]
0x18001b582  mov     [rsp+920h+lpcSubKeys], rax; lpcSubKeys
0x18001b587  xor     r9d, r9d; lpReserved
0x18001b58a  xor     r8d, r8d; lpcchClass
0x18001b58d  xor     edx, edx; lpClass
0x18001b58f  mov     rcx, r13; hKey
0x18001b592  call    cs:__imp_RegQueryInfoKeyW
0x18001b598  mov     ebx, eax
0x18001b59a  test    eax, eax
0x18001b59c  jnz     loc_18001B67F
0x18001b5a2  xor     edi, edi
0x18001b5a4  cmp     edi, [rsp+920h+cSubKeys]
0x18001b5a8  jnb     loc_18001B67F
0x18001b5ae  xor     eax, eax
0x18001b5b0  mov     [rsp+920h+var_8C0], rax
0x18001b5b5  mov     [rsp+920h+var_8B0], eax
0x18001b5b9  mov     [rsp+920h+var_8B4], eax
0x18001b5bd  lea     rax, [rsp+920h+var_8B4]
0x18001b5c2  mov     [rsp+920h+lpcbMaxSubKeyLen], rax
0x18001b5c7  lea     rax, [rsp+920h+var_8B0]
0x18001b5cc  mov     [rsp+920h+lpcSubKeys], rax
0x18001b5d1  lea     r9, [rsp+920h+var_8C0]
0x18001b5d6  mov     r8d, edi
0x18001b5d9  mov     rdx, r13
0x18001b5dc  mov     rcx, rsi
0x18001b5df  call    ?GetInfoFromRegistryKey@CDimInterface@@AEAAKPEAUHKEY__@@KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAK2@Z; CDimInterface::GetInfoFromRegistryKey(HKEY__ *,ulong,std::unique_ptr<uchar [0]> &,ulong &,ulong &)
0x18001b5e4  mov     ebx, eax
0x18001b5e6  test    eax, eax
0x18001b5e8  jz      loc_18001B6B9
0x18001b5ee  cmp     eax, 4DEh
0x18001b5f3  jz      loc_18001B6F5
0x18001b5f9  cmp     eax, 32h ; '2'
0x18001b5fc  jz      loc_18001B6F7
0x18001b602  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001b609  jz      short loc_18001B674
0x18001b60b  xor     eax, eax
0x18001b60d  mov     word ptr [rbp+820h+var_840], ax
0x18001b611  mov     word ptr [rbp+820h+var_868], ax
0x18001b615  mov     r8d, ebx
0x18001b618  lea     rdx, aCdiminterfaceA_0; "CDimInterface::AddTransportFromRegistry"...
0x18001b61f  lea     rcx, [rbp+820h+var_840]
0x18001b623  call    FormatRRASErrorString
0x18001b628  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001b62f  jz      short loc_18001B674
0x18001b631  mov     rax, [rsi]
0x18001b634  mov     rcx, rsi
0x18001b637  mov     rax, [rax+118h]
0x18001b63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b643  lea     r9, [rbp+820h+var_878]
0x18001b647  test    r15, r15
0x18001b64a  cmovnz  r9, r15
0x18001b64e  lea     rcx, [rbp+820h+var_868]
0x18001b652  mov     [rsp+920h+lpcbMaxSubKeyLen], rcx
0x18001b657  mov     [rsp+920h+lpcSubKeys], rax
0x18001b65c  lea     r8, [rbp+820h+var_840]
0x18001b660  lea     rdx, RasDimParamTraceError
0x18001b667  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b66e  call    McTemplateU0zjzz_EventWriteTransfer
0x18001b673  nop
0x18001b674  mov     rcx, [rsp+920h+var_8C0]
0x18001b679  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b67f  test    r12d, r12d
0x18001b682  jz      short loc_18001B68D
0x18001b684  lea     rcx, [rbp+820h+ActivityId]; ActivityId
0x18001b688  call    ReSetActivityId
0x18001b68d  mov     eax, ebx
0x18001b68f  mov     rcx, [rbp+820h+var_40]
0x18001b696  xor     rcx, rsp; StackCookie
0x18001b699  call    __security_check_cookie
0x18001b69e  mov     rbx, [rsp+920h+arg_8]
0x18001b6a6  add     rsp, 8F0h
0x18001b6ad  pop     r15
0x18001b6af  pop     r14
0x18001b6b1  pop     r13
0x18001b6b3  pop     r12
0x18001b6b5  pop     rdi
0x18001b6b6  pop     rsi
0x18001b6b7  pop     rbp
0x18001b6b8  retn
0x18001b6b9  mov     edx, [rsp+920h+var_8B4]; unsigned int
0x18001b6bd  test    r14d, r14d
0x18001b6c0  jz      short loc_18001B6C7
0x18001b6c2  cmp     r14d, edx
0x18001b6c5  jnz     short loc_18001B6F7
0x18001b6c7  mov     [rsp+920h+var_8A8], 0
0x18001b6cf  xorps   xmm0, xmm0
0x18001b6d2  movdqu  [rbp+820h+var_898], xmm0
0x18001b6d7  mov     rax, [rsp+920h+var_8C0]
0x18001b6dc  mov     [rbp+820h+var_8A0], rax
0x18001b6e0  mov     eax, [rsp+920h+var_8B0]
0x18001b6e4  mov     [rsp+920h+var_8A4], eax
0x18001b6e8  lea     r8, [rsp+920h+var_8A8]; struct _DIM_INTERFACE_CONTAINER *
0x18001b6ed  mov     rcx, rsi; this
0x18001b6f0  call    ?AddTransport@CDimInterface@@QEAAKKPEAU_DIM_INTERFACE_CONTAINER@@@Z; CDimInterface::AddTransport(ulong,_DIM_INTERFACE_CONTAINER *)
0x18001b6f5  xor     ebx, ebx
0x18001b6f7  mov     rcx, [rsp+920h+var_8C0]
0x18001b6fc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b702  inc     edi
0x18001b704  jmp     loc_18001B5A4
```
