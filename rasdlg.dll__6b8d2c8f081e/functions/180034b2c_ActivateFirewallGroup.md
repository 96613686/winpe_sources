# ActivateFirewallGroup

- ea: `0x180034b2c`
- end: `0x180034c06`
- name: `ActivateFirewallGroup`
- size: `218`
- prototype: `__int64 __fastcall(const OLECHAR *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034c0c`

## callees

- `0x180034b2c`
- `0x180034c5c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034b99`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034b99`
- `OLEAUT32!__imp_SysAllocString` at `0x180034b4d`
- `OLEAUT32!__imp_SysAllocString` at `0x180034b4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180034bd8`
- `OLEAUT32!__imp_SysFreeString` at `0x180034bd8`

## pseudocode

```c
__int64 __fastcall ActivateFirewallGroup(const OLECHAR *a1, int a2)
{
  BSTR v3; // rax
  OLECHAR *v4; // rdi
  HRESULT active; // ebx
  __int64 v6; // r9
  int v8; // [rsp+50h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  ppv = 0;
  v8 = 0;
  v3 = SysAllocString(a1);
  v4 = v3;
  if ( v3 )
  {
    active = IsFirewallGroupActiveInternal(v3, &v8);
    if ( active >= 0 && v8 != a2 )
    {
      active = CoCreateInstance(&CLSID_NetFwPolicy2, 0, 1u, &IID_INetFwPolicy2, &ppv);
      if ( active >= 0 )
      {
        if ( ppv )
        {
          LOWORD(v6) = -(a2 != 0);
          active = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *, __int64))(*(_QWORD *)ppv + 160LL))(
                     ppv,
                     0x7FFFFFFF,
                     v4,
                     v6);
        }
        else
        {
          active = -2147418113;
        }
      }
    }
    SysFreeString(v4);
  }
  else
  {
    active = -2147024882;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180034b2c  mov     rax, rsp
0x180034b2f  mov     [rax+8], rbx
0x180034b33  mov     [rax+10h], rsi
0x180034b37  push    rdi
0x180034b38  sub     rsp, 30h
0x180034b3c  mov     esi, edx
0x180034b3e  mov     qword ptr [rax+20h], 0
0x180034b46  mov     dword ptr [rax+18h], 0
0x180034b4d  call    cs:__imp_SysAllocString
0x180034b53  mov     rdi, rax
0x180034b56  test    rax, rax
0x180034b59  jnz     short loc_180034B62
0x180034b5b  mov     ebx, 8007000Eh
0x180034b60  jmp     short loc_180034BDE
0x180034b62  lea     rdx, [rsp+38h+arg_10]
0x180034b67  mov     rcx, rdi
0x180034b6a  call    IsFirewallGroupActiveInternal
0x180034b6f  mov     ebx, eax
0x180034b71  test    eax, eax
0x180034b73  js      short loc_180034BD5
0x180034b75  cmp     [rsp+38h+arg_10], esi
0x180034b79  jz      short loc_180034BD5
0x180034b7b  xor     edx, edx; pUnkOuter
0x180034b7d  lea     rax, [rsp+38h+arg_18]
0x180034b82  lea     r9, IID_INetFwPolicy2; riid
0x180034b89  mov     [rsp+38h+ppv], rax; ppv
0x180034b8e  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x180034b95  lea     r8d, [rdx+1]; dwClsContext
0x180034b99  call    cs:__imp_CoCreateInstance
0x180034b9f  mov     ebx, eax
0x180034ba1  test    eax, eax
0x180034ba3  js      short loc_180034BD5
0x180034ba5  mov     rcx, [rsp+38h+arg_18]
0x180034baa  test    rcx, rcx
0x180034bad  jnz     short loc_180034BB6
0x180034baf  mov     ebx, 8000FFFFh
0x180034bb4  jmp     short loc_180034BD5
0x180034bb6  mov     rax, [rcx]
0x180034bb9  neg     esi
0x180034bbb  mov     r8, rdi
0x180034bbe  mov     edx, 7FFFFFFFh
0x180034bc3  sbb     r9w, r9w
0x180034bc7  mov     rax, [rax+0A0h]
0x180034bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bd3  mov     ebx, eax
0x180034bd5  mov     rcx, rdi; bstrString
0x180034bd8  call    cs:__imp_SysFreeString
0x180034bde  mov     rcx, [rsp+38h+arg_18]
0x180034be3  test    rcx, rcx
0x180034be6  jz      short loc_180034BF4
0x180034be8  mov     rax, [rcx]
0x180034beb  mov     rax, [rax+10h]
0x180034bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bf4  mov     rsi, [rsp+38h+arg_8]
0x180034bf9  mov     eax, ebx
0x180034bfb  mov     rbx, [rsp+38h+arg_0]
0x180034c00  add     rsp, 30h
0x180034c04  pop     rdi
0x180034c05  retn
```
