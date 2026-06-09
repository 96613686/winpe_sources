# CEventClass2::UnregisterEventClass(ushort const *,ushort const *)

- ea: `0x180035aa0`
- end: `0x180035b8f`
- name: `?UnregisterEventClass@CEventClass2@@SAXPEBG0@Z`
- size: `239`
- prototype: `static void(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011a30`

## callees

- `0x180006194`
- `0x18000c910`
- `0x180035aa0`
- `0x180040b78`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035b01`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180035ace`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180035ace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b6a`

## pseudocode

```c
void __fastcall CEventClass2::UnregisterEventClass(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rsi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  _QWORD *v6; // [rsp+20h] [rbp-60h] BYREF
  int v7; // [rsp+28h] [rbp-58h]
  _QWORD v8[6]; // [rsp+30h] [rbp-50h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-20h] BYREF

  pclsid = 0;
  if ( CLSIDFromString(a1, &pclsid) >= 0 )
  {
    v3 = (int)safe_lstrlenW(a2) + 4LL;
    v4 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v3, 2u));
    v5 = v4;
    if ( v4 )
    {
      if ( (int)StringCchPrintfW(v4, v3, L"%s.1", a2) >= 0 )
      {
        v8[0] = 0;
        v8[1] = &pclsid;
        v8[2] = a2;
        v8[5] = L"Both";
        v6 = v8;
        v8[3] = v5;
        v8[4] = a2;
        v7 = 1;
        Registrar::UnregisterServer(&v6);
      }
      CoTaskMemFree(v5);
    }
  }
}

```

## disassembly

```asm
0x180035aa0  mov     [rsp-18h+arg_10], rbx
0x180035aa5  push    rbp
0x180035aa6  push    rsi
0x180035aa7  push    rdi
0x180035aa8  mov     rbp, rsp
0x180035aab  sub     rsp, 80h
0x180035ab2  mov     rax, cs:__security_cookie
0x180035ab9  xor     rax, rsp
0x180035abc  mov     [rbp+var_10], rax
0x180035ac0  mov     rdi, rdx
0x180035ac3  xorps   xmm0, xmm0
0x180035ac6  lea     rdx, [rbp+pclsid]; pclsid
0x180035aca  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180035ace  call    cs:__imp_CLSIDFromString
0x180035ad4  test    eax, eax
0x180035ad6  js      loc_180035B70
0x180035adc  mov     rcx, rdi; unsigned __int16 *
0x180035adf  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180035ae4  movsxd  rsi, eax
0x180035ae7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180035aee  add     rsi, 4
0x180035af2  mov     eax, 2
0x180035af7  mul     rsi
0x180035afa  cmovb   rax, rcx
0x180035afe  mov     rcx, rax; cb
0x180035b01  call    cs:__imp_CoTaskMemAlloc
0x180035b07  mov     rbx, rax
0x180035b0a  test    rax, rax
0x180035b0d  jz      short loc_180035B70
0x180035b0f  mov     r9, rdi
0x180035b12  lea     r8, aS1; "%s.1"
0x180035b19  mov     rdx, rsi; unsigned __int64
0x180035b1c  mov     rcx, rax; unsigned __int16 *
0x180035b1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035b24  test    eax, eax
0x180035b26  js      short loc_180035B67
0x180035b28  lea     rax, [rbp+pclsid]
0x180035b2c  mov     [rbp+var_50], 0
0x180035b34  mov     [rbp+var_48], rax
0x180035b38  lea     rcx, [rbp+var_60]
0x180035b3c  lea     rax, aBoth; "Both"
0x180035b43  mov     [rbp+var_40], rdi
0x180035b47  mov     [rbp+var_28], rax
0x180035b4b  lea     rax, [rbp+var_50]
0x180035b4f  mov     [rbp+var_60], rax
0x180035b53  mov     [rbp+var_38], rbx
0x180035b57  mov     [rbp+var_30], rdi
0x180035b5b  mov     [rbp+var_58], 1
0x180035b62  call    ?UnregisterServer@Registrar@@QEAAJPEBGW4ServerKind@1@@Z; Registrar::UnregisterServer(ushort const *,Registrar::ServerKind)
0x180035b67  mov     rcx, rbx; pv
0x180035b6a  call    cs:__imp_CoTaskMemFree
0x180035b70  mov     rcx, [rbp+var_10]
0x180035b74  xor     rcx, rsp; StackCookie
0x180035b77  call    __security_check_cookie
0x180035b7c  mov     rbx, [rsp+80h+arg_10]
0x180035b84  add     rsp, 80h
0x180035b8b  pop     rdi
0x180035b8c  pop     rsi
0x180035b8d  pop     rbp
0x180035b8e  retn
```
