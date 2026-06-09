# NetTrace::CPersistentTrace::CommitProviders(ATL::CRegKey &)

- ea: `0x180028f00`
- end: `0x1800290a1`
- name: `?CommitProviders@CPersistentTrace@NetTrace@@AEAAJAEAVCRegKey@ATL@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(NetTrace::CPersistentTrace *this, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cdc`

## callees

- `0x1800084e4`
- `0x18001f0a4`
- `0x180028f00`
- `0x1800290a8`
- `0x180029b74`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18002907a`
- `KERNEL32!RaiseException` at `0x18002907a`
- `ADVAPI32!RegSetValueExW` at `0x180029052`
- `ADVAPI32!RegSetValueExW` at `0x180029052`
- `OLEAUT32!__imp_SysFreeString` at `0x180028fb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180028fb2`

## pseudocode

```c
__int64 __fastcall NetTrace::CPersistentTrace::CommitProviders(NetTrace::CPersistentTrace *this, HKEY *a2)
{
  HKEY *v2; // r12
  NetTrace::CPersistentTrace *v3; // rsi
  LSTATUS v4; // ebx
  unsigned int v5; // r15d
  int i; // edi
  bool v7; // cc
  LPCWSTR *v8; // rax
  unsigned __int16 *v9; // r9
  __int64 v10; // r14
  unsigned int lpData; // [rsp+20h] [rbp-98h]
  DWORD cbData; // [rsp+28h] [rbp-90h]
  struct _SECURITY_ATTRIBUTES *v14; // [rsp+30h] [rbp-88h]
  unsigned int *v15; // [rsp+38h] [rbp-80h]
  unsigned int v16; // [rsp+40h] [rbp-78h]
  BSTR bstrString; // [rsp+48h] [rbp-70h] BYREF
  __int64 v18; // [rsp+50h] [rbp-68h]
  const ATL::CAtlException *v19; // [rsp+58h] [rbp-60h] BYREF
  HKEY hKey[11]; // [rsp+60h] [rbp-58h] BYREF
  __int64 Data; // [rsp+D0h] [rbp+18h] BYREF
  LSTATUS v24; // [rsp+D8h] [rbp+20h]

  v2 = a2;
  v3 = this;
  v4 = *(_DWORD *)this;
  if ( !*(_DWORD *)this )
  {
    v5 = *((_DWORD *)this + 26);
    v16 = v5;
    for ( i = 0; ; ++i )
    {
      LODWORD(Data) = i;
      if ( i >= v5 )
        break;
      v7 = v4 <= 0;
      if ( v4 )
        goto LABEL_15;
      if ( i < 0 || i >= *((_DWORD *)v3 + 26) )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        __debugbreak();
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v10 = *((_QWORD *)v3 + 12) + 48LL * i;
        v18 = v10;
        memset(hKey, 0, 24);
        v8 = (LPCWSTR *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)v10);
        v4 = ((__int64 (__fastcall *)(ATL::CRegKey *, HKEY, LPCWSTR, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *))ATL::CRegKey::Create)(
               (ATL::CRegKey *)hKey,
               *v2,
               *v8,
               v9,
               lpData,
               cbData,
               v14,
               v15);
        SysFreeString(bstrString);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v19) )
        {
          v24 = *(unsigned __int16 *)v19;
          v3 = this;
          v2 = a2;
          v4 = v24;
          v5 = v16;
          i = Data;
          v10 = v18;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180028FBB);
        }
      }
      if ( !v4 )
      {
        v4 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"Enabled", 1u);
        if ( !v4 )
        {
          v4 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"EnableLevel", *(unsigned __int8 *)(v10 + 16));
          if ( !v4 )
          {
            Data = *(_QWORD *)(v10 + 24);
            v4 = RegSetValueExW(hKey[0], L"MatchAnyKeyword", 0, 0xBu, (const BYTE *)&Data, 8u);
          }
        }
      }
      ATL::CRegKey::Close(hKey);
    }
    v7 = v4 <= 0;
LABEL_15:
    if ( !v7 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028f00  mov     [rsp+arg_8], rdx
0x180028f05  mov     [rsp+arg_0], rcx
0x180028f0a  push    rbx
0x180028f0b  push    rsi
0x180028f0c  push    rdi
0x180028f0d  push    r12
0x180028f0f  push    r14
0x180028f11  push    r15
0x180028f13  sub     rsp, 88h
0x180028f1a  mov     r12, rdx
0x180028f1d  mov     rsi, rcx
0x180028f20  mov     ebx, [rcx]
0x180028f22  test    ebx, ebx
0x180028f24  jnz     loc_18002908E
0x180028f2a  mov     r15d, [rcx+68h]
0x180028f2e  mov     [rsp+0B8h+var_78], r15d
0x180028f33  xor     edi, edi
0x180028f35  mov     dword ptr [rsp+0B8h+Data], edi
0x180028f3c  cmp     edi, r15d
0x180028f3f  jnb     loc_180029081
0x180028f45  test    ebx, ebx
0x180028f47  jnz     loc_180029083
0x180028f4d  test    edi, edi
0x180028f4f  js      loc_18002906B
0x180028f55  cmp     edi, [rsi+68h]
0x180028f58  jge     loc_18002906B
0x180028f5e  movsxd  rax, edi
0x180028f61  lea     r14, [rax+rax*2]
0x180028f65  shl     r14, 4
0x180028f69  add     r14, [rsi+60h]
0x180028f6d  mov     [rsp+0B8h+var_68], r14
0x180028f72  mov     [rsp+0B8h+hKey], 0
0x180028f7b  mov     [rsp+0B8h+var_50], 0
0x180028f84  mov     [rsp+0B8h+var_48], 0
0x180028f8d  mov     rdx, r14; struct _GUID *
0x180028f90  lea     rcx, [rsp+0B8h+bstrString]; this
0x180028f95  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180028f9a  mov     r8, [rax]; lpSubKey
0x180028f9d  mov     rdx, [r12]; hKey
0x180028fa1  lea     rcx, [rsp+0B8h+hKey]; this
0x180028fa6  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180028fab  mov     ebx, eax
0x180028fad  mov     rcx, [rsp+0B8h+bstrString]; bstrString
0x180028fb2  call    cs:__imp_SysFreeString
0x180028fb8  nop
0x180028fb9  jmp     short loc_180028FE3
0x180028fbb  mov     rsi, [rsp+0B8h+arg_0]
0x180028fc3  mov     r12, [rsp+0B8h+arg_8]
0x180028fcb  mov     ebx, [rsp+0B8h+arg_18]
0x180028fd2  mov     r15d, [rsp+0B8h+var_78]
0x180028fd7  mov     edi, dword ptr [rsp+0B8h+Data]
0x180028fde  mov     r14, [rsp+0B8h+var_68]
0x180028fe3  test    ebx, ebx
0x180028fe5  jnz     short loc_18002905A
0x180028fe7  lea     r8d, [rbx+1]; unsigned int
0x180028feb  lea     rdx, aEnabled; "Enabled"
0x180028ff2  lea     rcx, [rsp+0B8h+hKey]; this
0x180028ff7  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028ffc  mov     ebx, eax
0x180028ffe  test    eax, eax
0x180029000  jnz     short loc_18002905A
0x180029002  movzx   r8d, byte ptr [r14+10h]; unsigned int
0x180029007  lea     rdx, aEnablelevel; "EnableLevel"
0x18002900e  lea     rcx, [rsp+0B8h+hKey]; this
0x180029013  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180029018  mov     ebx, eax
0x18002901a  test    eax, eax
0x18002901c  jnz     short loc_18002905A
0x18002901e  mov     rax, [r14+18h]
0x180029022  mov     [rsp+0B8h+Data], rax
0x18002902a  mov     [rsp+0B8h+cbData], 8; cbData
0x180029032  lea     rax, [rsp+0B8h+Data]
0x18002903a  mov     [rsp+0B8h+lpData], rax; lpData
0x18002903f  lea     r9d, [rbx+0Bh]; dwType
0x180029043  xor     r8d, r8d; Reserved
0x180029046  lea     rdx, ValueName; "MatchAnyKeyword"
0x18002904d  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180029052  call    cs:__imp_RegSetValueExW
0x180029058  mov     ebx, eax
0x18002905a  lea     rcx, [rsp+0B8h+hKey]; this
0x18002905f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029064  inc     edi
0x180029066  jmp     loc_180028F35
0x18002906b  xor     r9d, r9d; lpArguments
0x18002906e  xor     r8d, r8d; nNumberOfArguments
0x180029071  lea     edx, [r9+1]; dwExceptionFlags
0x180029075  mov     ecx, 0C000008Ch; dwExceptionCode
0x18002907a  call    cs:__imp_RaiseException
0x180029080  int     3; Trap to Debugger
0x180029081  test    ebx, ebx
0x180029083  jle     short loc_18002908E
0x180029085  movzx   ebx, bx
0x180029088  or      ebx, 80070000h
0x18002908e  mov     eax, ebx
0x180029090  add     rsp, 88h
0x180029097  pop     r15
0x180029099  pop     r14
0x18002909b  pop     r12
0x18002909d  pop     rdi
0x18002909e  pop     rsi
0x18002909f  pop     rbx
0x1800290a0  retn
```
