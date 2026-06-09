# CEventClass2::RegisterEventClass(ushort const *,tagPROPVARIANT * const)

- ea: `0x180035930`
- end: `0x180035a97`
- name: `?RegisterEventClass@CEventClass2@@AEAAJPEBGQEAUtagPROPVARIANT@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CEventClass2 *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024c10`

## callees

- `0x180006194`
- `0x18000c910`
- `0x180035930`
- `0x180040908`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035982`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180035978`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180035978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800359ae`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800359ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035a6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035a6d`

## pseudocode

```c
signed int __fastcall CEventClass2::RegisterEventClass(
        CEventClass2 *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *const a3)
{
  signed int result; // eax
  const OLECHAR *bstrVal; // rcx
  HRESULT v6; // ebx
  const unsigned __int16 *v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  __int64 v11; // r8
  _QWORD *v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h]
  _QWORD v14[6]; // [rsp+40h] [rbp-C0h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( SearchPathW(0, a2, 0, 0x105u, Buffer, 0) )
  {
    bstrVal = a3->bstrVal;
    pclsid = 0;
    v6 = CLSIDFromString(bstrVal, &pclsid);
    if ( v6 >= 0 )
    {
      v7 = a3[1].bstrVal;
      v8 = (int)safe_lstrlenW(v7) + 4LL;
      v9 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v8, 2u));
      v10 = v9;
      if ( v9 )
      {
        v6 = StringCchPrintfW(v9, v8, L"%s.1", v7);
        if ( v6 >= 0 )
        {
          v14[0] = 0;
          v14[1] = &pclsid;
          v14[2] = v7;
          v14[5] = L"Both";
          v14[3] = v10;
          v12 = v14;
          v14[4] = v7;
          v13 = 1;
          v6 = Registrar::RegisterServer(&v12, Buffer, v11, v7);
        }
        CoTaskMemFree(v10);
      }
      else
      {
        return -2147024882;
      }
    }
    return v6;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180035930  mov     [rsp-8+arg_0], rbx
0x180035935  push    rbp
0x180035936  push    rsi
0x180035937  push    rdi
0x180035938  lea     rbp, [rsp-1A0h]
0x180035940  sub     rsp, 2A0h
0x180035947  mov     rax, cs:__security_cookie
0x18003594e  xor     rax, rsp
0x180035951  mov     [rbp+1B0h+var_20], rax
0x180035958  mov     rdi, r8
0x18003595b  mov     [rsp+2B0h+lpFilePart], 0; lpFilePart
0x180035964  lea     rax, [rbp+1B0h+Buffer]
0x180035968  xor     r8d, r8d; lpExtension
0x18003596b  mov     r9d, 105h; nBufferLength
0x180035971  mov     [rsp+2B0h+lpBuffer], rax; lpBuffer
0x180035976  xor     ecx, ecx; lpPath
0x180035978  call    cs:__imp_SearchPathW
0x18003597e  test    eax, eax
0x180035980  jnz     short loc_18003599D
0x180035982  call    cs:__imp_GetLastError
0x180035988  test    eax, eax
0x18003598a  jle     loc_180035A75
0x180035990  movzx   eax, ax
0x180035993  or      eax, 80070000h
0x180035998  jmp     loc_180035A75
0x18003599d  mov     rcx, [rdi+8]; lpsz
0x1800359a1  lea     rdx, [rsp+2B0h+pclsid]; pclsid
0x1800359a6  xorps   xmm0, xmm0
0x1800359a9  movups  xmmword ptr [rsp+2B0h+pclsid.Data1], xmm0
0x1800359ae  call    cs:__imp_CLSIDFromString
0x1800359b4  mov     ebx, eax
0x1800359b6  test    eax, eax
0x1800359b8  js      loc_180035A73
0x1800359be  mov     rdi, [rdi+20h]
0x1800359c2  mov     rcx, rdi; unsigned __int16 *
0x1800359c5  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800359ca  movsxd  rbx, eax
0x1800359cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800359d4  add     rbx, 4
0x1800359d8  mov     eax, 2
0x1800359dd  mul     rbx
0x1800359e0  cmovb   rax, rcx
0x1800359e4  mov     rcx, rax; cb
0x1800359e7  call    cs:__imp_CoTaskMemAlloc
0x1800359ed  mov     rsi, rax
0x1800359f0  test    rax, rax
0x1800359f3  jnz     short loc_1800359FC
0x1800359f5  mov     ebx, 8007000Eh
0x1800359fa  jmp     short loc_180035A73
0x1800359fc  mov     r9, rdi
0x1800359ff  lea     r8, aS1; "%s.1"
0x180035a06  mov     rdx, rbx; unsigned __int64
0x180035a09  mov     rcx, rsi; unsigned __int16 *
0x180035a0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035a11  mov     ebx, eax
0x180035a13  test    eax, eax
0x180035a15  js      short loc_180035A6A
0x180035a17  lea     rax, [rsp+2B0h+pclsid]
0x180035a1c  mov     [rsp+2B0h+var_270], 0
0x180035a25  mov     [rsp+2B0h+var_268], rax
0x180035a2a  lea     rdx, [rbp+1B0h+Buffer]
0x180035a2e  lea     rax, aBoth; "Both"
0x180035a35  mov     [rsp+2B0h+var_260], rdi
0x180035a3a  mov     [rsp+2B0h+var_248], rax
0x180035a3f  lea     rcx, [rsp+2B0h+var_280]
0x180035a44  lea     rax, [rsp+2B0h+var_270]
0x180035a49  mov     [rsp+2B0h+var_258], rsi
0x180035a4e  mov     r9, rdi
0x180035a51  mov     [rsp+2B0h+var_280], rax
0x180035a56  mov     [rsp+2B0h+var_250], rdi
0x180035a5b  mov     [rsp+2B0h+var_278], 1
0x180035a63  call    ?RegisterServer@Registrar@@QEAAJPEBGW4ServerKind@1@000@Z; Registrar::RegisterServer(ushort const *,Registrar::ServerKind,ushort const *,ushort const *,ushort const *)
0x180035a68  mov     ebx, eax
0x180035a6a  mov     rcx, rsi; pv
0x180035a6d  call    cs:__imp_CoTaskMemFree
0x180035a73  mov     eax, ebx
0x180035a75  mov     rcx, [rbp+1B0h+var_20]
0x180035a7c  xor     rcx, rsp; StackCookie
0x180035a7f  call    __security_check_cookie
0x180035a84  mov     rbx, [rsp+2B0h+arg_0]
0x180035a8c  add     rsp, 2A0h
0x180035a93  pop     rdi
0x180035a94  pop     rsi
0x180035a95  pop     rbp
0x180035a96  retn
```
