# RtpCreateObject(ulong,wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const)

- ea: `0x18000d8b4`
- end: `0x18000d9c2`
- name: `?RtpCreateObject@@YAJKPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, void *, unsigned int, unsigned int *const, struct tagPROPVARIANT *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e590`

## callees

- `0x18000a364`
- `0x18000d74c`
- `0x18000d7c0`
- `0x18000d8b4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d92e`
- `RPCRT4!NdrClientCall3` at `0x18000d92e`
- `KERNEL32!TlsGetValue` at `0x18000d8e3`
- `KERNEL32!TlsGetValue` at `0x18000d8e3`

## pseudocode

```c
__int64 __fastcall RtpCreateObject(
        int a1,
        const wchar_t *a2,
        void *a3,
        int a4,
        unsigned int *const a5,
        struct tagPROPVARIANT *const a6)
{
  LPVOID Value; // rax
  int Pointer; // eax
  unsigned int v12; // ebx
  DWORD v14[14]; // [rsp+60h] [rbp-38h] BYREF

  v14[0] = 0;
  GetSecurityDescriptorSize(a3, v14);
  Value = TlsGetValue(g_hBindIndex);
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            6u,
                            0,
                            Value,
                            a1,
                            a2,
                            v14[0],
                            a3,
                            a4,
                            a5,
                            a6).Pointer;
  v12 = Pointer;
  if ( Pointer < 0 )
  {
    if ( Pointer == -1072824315 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 62));
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 508) & 1) != 0 )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 62), Pointer);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18000d8b4  push    rbx
0x18000d8b6  push    rbp
0x18000d8b7  push    rsi
0x18000d8b8  push    rdi
0x18000d8b9  sub     rsp, 78h
0x18000d8bd  mov     rbp, rdx
0x18000d8c0  mov     [rsp+98h+var_38], 0
0x18000d8c8  mov     esi, ecx
0x18000d8ca  lea     rdx, [rsp+98h+var_38]
0x18000d8cf  mov     rcx, r8
0x18000d8d2  mov     ebx, r9d
0x18000d8d5  mov     rdi, r8
0x18000d8d8  call    GetSecurityDescriptorSize
0x18000d8dd  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000d8e3  call    cs:__imp_TlsGetValue
0x18000d8e9  mov     r10, [rsp+98h+arg_28]
0x18000d8f1  xor     r8d, r8d; pReturnValue
0x18000d8f4  mov     r9, [rsp+98h+arg_20]
0x18000d8fc  mov     ecx, [rsp+98h+var_38]
0x18000d900  mov     [rsp+98h+var_48], r10
0x18000d905  mov     [rsp+98h+var_50], r9
0x18000d90a  lea     edx, [r8+6]; nProcNum
0x18000d90e  mov     [rsp+98h+var_58], ebx
0x18000d912  mov     r9, rax
0x18000d915  mov     [rsp+98h+var_60], rdi
0x18000d91a  mov     [rsp+98h+var_68], ecx
0x18000d91e  lea     rcx, pProxyInfo; pProxyInfo
0x18000d925  mov     [rsp+98h+var_70], rbp
0x18000d92a  mov     dword ptr [rsp+98h+var_78], esi
0x18000d92e  call    cs:__imp_NdrClientCall3
0x18000d934  mov     rbx, rax
0x18000d937  test    eax, eax
0x18000d939  jns     short loc_18000D9B7
0x18000d93b  cmp     ebx, 0C00E0005h
0x18000d941  jnz     short loc_18000D97C
0x18000d943  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d94a  lea     rdx, WPP_GLOBAL_Control
0x18000d951  cmp     rcx, rdx
0x18000d954  jz      short loc_18000D9B7
0x18000d956  test    byte ptr [rcx+1FCh], 2
0x18000d95d  jz      short loc_18000D9B7
0x18000d95f  mov     rcx, [rcx+1F0h]; LoggerHandle
0x18000d966  lea     r8, WPP_ff36fd3f1d4f35b0a2f9f26ac6bf0214_Traceguids
0x18000d96d  mov     edx, 0Ah
0x18000d972  mov     r9, rbp
0x18000d975  call    WPP_SF_S
0x18000d97a  jmp     short loc_18000D9B7
0x18000d97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d983  lea     rdx, WPP_GLOBAL_Control
0x18000d98a  cmp     rcx, rdx
0x18000d98d  jz      short loc_18000D9B7
0x18000d98f  test    byte ptr [rcx+1FCh], 1
0x18000d996  jz      short loc_18000D9B7
0x18000d998  mov     rcx, [rcx+1F0h]; LoggerHandle
0x18000d99f  lea     r8, WPP_ff36fd3f1d4f35b0a2f9f26ac6bf0214_Traceguids
0x18000d9a6  mov     edx, 0Bh
0x18000d9ab  mov     dword ptr [rsp+98h+var_78], ebx; char
0x18000d9af  mov     r9, rbp
0x18000d9b2  call    WPP_SF_Sd
0x18000d9b7  mov     eax, ebx
0x18000d9b9  add     rsp, 78h
0x18000d9bd  pop     rdi
0x18000d9be  pop     rsi
0x18000d9bf  pop     rbp
0x18000d9c0  pop     rbx
0x18000d9c1  retn
```
