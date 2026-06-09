# Auditor::Initialize(void)

- ea: `0x1800172b8`
- end: `0x180017391`
- name: `?Initialize@Auditor@@UEAAJXZ`
- size: `217`
- prototype: `HRESULT __fastcall(Auditor *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015100`
- `0x1800157b8`

## callees

- `0x1800172b8`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800172e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800172e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001731b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001731b`

## pseudocode

```c
HRESULT __fastcall Auditor::Initialize(Auditor *this)
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
      v3 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)ppv + 32LL))(
             ppv,
             ((unsigned __int64)this + 72) & -(__int64)(this != 0));
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800172b8  mov     [rsp+arg_8], rbx
0x1800172bd  push    rdi
0x1800172be  sub     rsp, 50h
0x1800172c2  mov     rax, cs:__security_cookie
0x1800172c9  xor     rax, rsp
0x1800172cc  mov     [rsp+58h+var_10], rax
0x1800172d1  mov     rdi, rcx
0x1800172d4  xorps   xmm0, xmm0
0x1800172d7  movups  xmmword ptr [rsp+58h+clsid.Data1], xmm0
0x1800172dc  lea     rdx, [rsp+58h+clsid]; lpclsid
0x1800172e1  lea     rcx, szProgID; "IAS.AuditChannel"
0x1800172e8  call    cs:__imp_CLSIDFromProgID
0x1800172ee  test    eax, eax
0x1800172f0  js      loc_180017379
0x1800172f6  mov     [rsp+58h+var_28], 0
0x1800172ff  lea     rax, [rsp+58h+var_28]
0x180017304  mov     [rsp+58h+ppv], rax; ppv
0x180017309  lea     r9, _GUID_6bc0969b_0ce6_11d1_baae_00c04fc2e20d; riid
0x180017310  xor     edx, edx; pUnkOuter
0x180017312  lea     r8d, [rdx+1]; dwClsContext
0x180017316  lea     rcx, [rsp+58h+clsid]; rclsid
0x18001731b  call    cs:__imp_CoCreateInstance
0x180017321  mov     ebx, eax
0x180017323  test    eax, eax
0x180017325  jns     short loc_180017340
0x180017327  mov     rcx, [rsp+58h+var_28]
0x18001732c  test    rcx, rcx
0x18001732f  jz      short loc_18001733E
0x180017331  mov     rdx, [rcx]
0x180017334  mov     rax, [rdx+10h]
0x180017338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001733d  nop
0x18001733e  jmp     short loc_180017377
0x180017340  mov     rcx, [rsp+58h+var_28]
0x180017345  mov     r8, [rcx]
0x180017348  lea     rax, [rdi+48h]
0x18001734c  neg     rdi
0x18001734f  sbb     rdx, rdx
0x180017352  and     rdx, rax
0x180017355  mov     rax, [r8+20h]
0x180017359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001735e  mov     ebx, eax
0x180017360  mov     rcx, [rsp+58h+var_28]
0x180017365  test    rcx, rcx
0x180017368  jz      short loc_180017377
0x18001736a  mov     rdx, [rcx]
0x18001736d  mov     rax, [rdx+10h]
0x180017371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017376  nop
0x180017377  mov     eax, ebx
0x180017379  mov     rcx, [rsp+58h+var_10]
0x18001737e  xor     rcx, rsp; StackCookie
0x180017381  call    __security_check_cookie
0x180017386  mov     rbx, [rsp+58h+arg_8]
0x18001738b  add     rsp, 50h
0x18001738f  pop     rdi
0x180017390  retn
```
