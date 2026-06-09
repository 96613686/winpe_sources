# Auditor::Shutdown(void)

- ea: `0x180017398`
- end: `0x180017472`
- name: `?Shutdown@Auditor@@UEAAJXZ`
- size: `218`
- prototype: `HRESULT __fastcall(Auditor *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015250`
- `0x180015968`

## callees

- `0x180017398`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800173c8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800173c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173fb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173fb`

## pseudocode

```c
HRESULT __fastcall Auditor::Shutdown(Auditor *this)
{
  HRESULT result; // eax
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  GUID clsid; // [rsp+38h] [rbp-20h] BYREF

  clsid = 0;
  result = CLSIDFromProgID(L"IAS.AuditChannel", &clsid);
  if ( result >= 0 )
  {
    ppv = 0;
    v3 = CoCreateInstance(&clsid, 0, 1u, &GUID_6bc0969b_0ce6_11d1_baae_00c04fc2e20d, &ppv);
    if ( v3 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)ppv + 40LL))(
        ppv,
        ((unsigned __int64)this + 72) & -(__int64)(this != 0));
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 0;
    }
    else
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017398  mov     [rsp+arg_8], rbx
0x18001739d  push    rdi
0x18001739e  sub     rsp, 50h
0x1800173a2  mov     rax, cs:__security_cookie
0x1800173a9  xor     rax, rsp
0x1800173ac  mov     [rsp+58h+var_10], rax
0x1800173b1  mov     rdi, rcx
0x1800173b4  xorps   xmm0, xmm0
0x1800173b7  movups  xmmword ptr [rsp+58h+clsid.Data1], xmm0
0x1800173bc  lea     rdx, [rsp+58h+clsid]; lpclsid
0x1800173c1  lea     rcx, szProgID; "IAS.AuditChannel"
0x1800173c8  call    cs:__imp_CLSIDFromProgID
0x1800173ce  test    eax, eax
0x1800173d0  js      loc_18001745A
0x1800173d6  mov     [rsp+58h+var_28], 0
0x1800173df  lea     rax, [rsp+58h+var_28]
0x1800173e4  mov     [rsp+58h+ppv], rax; ppv
0x1800173e9  lea     r9, _GUID_6bc0969b_0ce6_11d1_baae_00c04fc2e20d; riid
0x1800173f0  xor     edx, edx; pUnkOuter
0x1800173f2  lea     r8d, [rdx+1]; dwClsContext
0x1800173f6  lea     rcx, [rsp+58h+clsid]; rclsid
0x1800173fb  call    cs:__imp_CoCreateInstance
0x180017401  mov     ebx, eax
0x180017403  test    eax, eax
0x180017405  jns     short loc_180017422
0x180017407  mov     rcx, [rsp+58h+var_28]
0x18001740c  test    rcx, rcx
0x18001740f  jz      short loc_18001741E
0x180017411  mov     rdx, [rcx]
0x180017414  mov     rax, [rdx+10h]
0x180017418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001741d  nop
0x18001741e  mov     eax, ebx
0x180017420  jmp     short loc_18001745A
0x180017422  mov     rcx, [rsp+58h+var_28]
0x180017427  mov     r8, [rcx]
0x18001742a  lea     rax, [rdi+48h]
0x18001742e  neg     rdi
0x180017431  sbb     rdx, rdx
0x180017434  and     rdx, rax
0x180017437  mov     rax, [r8+28h]
0x18001743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017440  nop
0x180017441  mov     rcx, [rsp+58h+var_28]
0x180017446  test    rcx, rcx
0x180017449  jz      short loc_180017458
0x18001744b  mov     rax, [rcx]
0x18001744e  mov     rax, [rax+10h]
0x180017452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017457  nop
0x180017458  xor     eax, eax
0x18001745a  mov     rcx, [rsp+58h+var_10]
0x18001745f  xor     rcx, rsp; StackCookie
0x180017462  call    __security_check_cookie
0x180017467  mov     rbx, [rsp+58h+arg_8]
0x18001746c  add     rsp, 50h
0x180017470  pop     rdi
0x180017471  retn
```
