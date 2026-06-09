# RtpCreateDSObject(ulong,wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,_GUID *)

- ea: `0x18000d7e8`
- end: `0x18000d8ae`
- name: `?RtpCreateDSObject@@YAJKPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@PEAU_GUID@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t *, void *, unsigned int, unsigned int *const, struct tagPROPVARIANT *const, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e590`

## callees

- `0x18000d7c0`
- `0x18000d7e8`
- `0x180013c74`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d879`
- `RPCRT4!NdrClientCall3` at `0x18000d879`
- `KERNEL32!TlsGetValue` at `0x18000d81d`
- `KERNEL32!TlsGetValue` at `0x18000d81d`

## pseudocode

```c
__int64 __fastcall RtpCreateDSObject(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        int a4,
        unsigned int *const a5,
        struct tagPROPVARIANT *const a6,
        struct _GUID *a7)
{
  LPVOID Value; // rax
  int Pointer; // eax
  unsigned int v12; // ebx
  int v14; // [rsp+20h] [rbp-48h]
  DWORD v15; // [rsp+30h] [rbp-38h]
  int v16; // [rsp+40h] [rbp-28h]
  DWORD v17; // [rsp+70h] [rbp+8h] BYREF

  v17 = 0;
  GetSecurityDescriptorSize(a3, &v17);
  Value = TlsGetValue(g_hBindIndex);
  v16 = a4;
  v15 = v17;
  v14 = 56;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x21u,
                            0,
                            Value,
                            v14,
                            a2,
                            v15,
                            a3,
                            v16,
                            a5,
                            a6,
                            a7).Pointer;
  v12 = Pointer;
  if ( Pointer < 0 )
    LogMsgHR(Pointer, (wchar_t *)L"rt/qmrt", 0x14u);
  return v12;
}

```

## disassembly

```asm
0x18000d7e8  mov     rax, rsp
0x18000d7eb  mov     [rax+10h], rbx
0x18000d7ef  mov     [rax+18h], rsi
0x18000d7f3  mov     [rax+8], ecx
0x18000d7f6  push    rdi
0x18000d7f7  sub     rsp, 60h
0x18000d7fb  mov     rsi, rdx
0x18000d7fe  mov     dword ptr [rax+8], 0
0x18000d805  lea     rdx, [rax+8]
0x18000d809  mov     rcx, r8
0x18000d80c  mov     ebx, r9d
0x18000d80f  mov     rdi, r8
0x18000d812  call    GetSecurityDescriptorSize
0x18000d817  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x18000d81d  call    cs:__imp_TlsGetValue
0x18000d823  mov     rcx, [rsp+68h+arg_30]
0x18000d82b  xor     r8d, r8d; pReturnValue
0x18000d82e  mov     [rsp+68h+var_10], rcx
0x18000d833  mov     r9, rax
0x18000d836  mov     rcx, [rsp+68h+arg_28]
0x18000d83e  mov     [rsp+68h+var_18], rcx
0x18000d843  mov     rcx, [rsp+68h+arg_20]
0x18000d84b  lea     edx, [r8+21h]; nProcNum
0x18000d84f  mov     [rsp+68h+var_20], rcx
0x18000d854  mov     ecx, [rsp+68h+arg_0]
0x18000d858  mov     [rsp+68h+var_28], ebx
0x18000d85c  mov     [rsp+68h+var_30], rdi
0x18000d861  mov     [rsp+68h+var_38], ecx
0x18000d865  lea     rcx, pProxyInfo; pProxyInfo
0x18000d86c  mov     [rsp+68h+var_40], rsi
0x18000d871  mov     [rsp+68h+var_48], 38h ; '8'
0x18000d879  call    cs:__imp_NdrClientCall3
0x18000d87f  mov     rbx, rax
0x18000d882  test    eax, eax
0x18000d884  jns     short loc_18000D89A
0x18000d886  mov     r8d, 14h; unsigned __int16
0x18000d88c  lea     rdx, aRtQmrt; "rt/qmrt"
0x18000d893  mov     ecx, ebx; int
0x18000d895  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000d89a  lea     r11, [rsp+68h+var_8]
0x18000d89f  mov     eax, ebx
0x18000d8a1  mov     rbx, [r11+18h]
0x18000d8a5  mov     rsi, [r11+20h]
0x18000d8a9  mov     rsp, r11
0x18000d8ac  pop     rdi
0x18000d8ad  retn
```
