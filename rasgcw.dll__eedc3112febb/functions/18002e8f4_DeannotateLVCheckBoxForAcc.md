# DeannotateLVCheckBoxForAcc

- ea: `0x18002e8f4`
- end: `0x18002e9af`
- name: `DeannotateLVCheckBoxForAcc`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800222c0`
- `0x180023400`
- `0x1800250c0`

## callees

- `0x18002e8f4`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e933`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e933`

## pseudocode

```c
HRESULT __fastcall DeannotateLVCheckBoxForAcc(__int64 a1)
{
  HRESULT result; // eax
  LPVOID ppv; // [rsp+40h] [rbp-38h] BYREF
  _OWORD v4[2]; // [rsp+48h] [rbp-30h] BYREF

  ppv = 0;
  result = CoCreateInstance(&CLSID_AccPropServices, 0, 1u, &IID_IAccPropServices, &ppv);
  if ( !result )
  {
    if ( ppv )
    {
      v4[0] = PROPID_ACC_STATE;
      v4[1] = PROPID_ACC_ROLE;
      (*(void (__fastcall **)(LPVOID, __int64, __int64, _QWORD, _OWORD *, int))(*(_QWORD *)ppv + 72LL))(
        ppv,
        a1,
        4294967292LL,
        0,
        v4,
        2);
      return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e8f4  push    rbx
0x18002e8f6  sub     rsp, 70h
0x18002e8fa  mov     rax, cs:__security_cookie
0x18002e901  xor     rax, rsp
0x18002e904  mov     [rsp+78h+var_10], rax
0x18002e909  xor     edx, edx; pUnkOuter
0x18002e90b  mov     [rsp+78h+var_38], 0
0x18002e914  mov     rbx, rcx
0x18002e917  lea     rax, [rsp+78h+var_38]
0x18002e91c  lea     r9, IID_IAccPropServices; riid
0x18002e923  mov     [rsp+78h+ppv], rax; ppv
0x18002e928  lea     rcx, CLSID_AccPropServices; rclsid
0x18002e92f  lea     r8d, [rdx+1]; dwClsContext
0x18002e933  call    cs:__imp_CoCreateInstance
0x18002e939  test    eax, eax
0x18002e93b  jnz     short loc_18002E99C
0x18002e93d  mov     rcx, [rsp+78h+var_38]
0x18002e942  test    rcx, rcx
0x18002e945  jz      short loc_18002E99C
0x18002e947  movups  xmm0, xmmword ptr cs:PROPID_ACC_STATE.Data1
0x18002e94e  lea     rdx, [rsp+78h+var_30]
0x18002e953  mov     [rsp+78h+var_50], 2
0x18002e95b  movups  xmm1, xmmword ptr cs:PROPID_ACC_ROLE.Data1
0x18002e962  mov     [rsp+78h+ppv], rdx
0x18002e967  xor     r9d, r9d
0x18002e96a  movdqu  [rsp+78h+var_30], xmm0
0x18002e970  mov     r8d, 0FFFFFFFCh
0x18002e976  mov     rdx, rbx
0x18002e979  movdqu  [rsp+78h+var_20], xmm1
0x18002e97f  mov     rax, [rcx]
0x18002e982  mov     rax, [rax+48h]
0x18002e986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e98b  mov     rcx, [rsp+78h+var_38]
0x18002e990  mov     rax, [rcx]
0x18002e993  mov     rax, [rax+10h]
0x18002e997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e99c  mov     rcx, [rsp+78h+var_10]
0x18002e9a1  xor     rcx, rsp; StackCookie
0x18002e9a4  call    __security_check_cookie
0x18002e9a9  add     rsp, 70h
0x18002e9ad  pop     rbx
0x18002e9ae  retn
```
