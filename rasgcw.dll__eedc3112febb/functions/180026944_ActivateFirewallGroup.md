# ActivateFirewallGroup

- ea: `0x180026944`
- end: `0x180026a1e`
- name: `ActivateFirewallGroup`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026a24`

## callees

- `0x180026944`
- `0x180026a74`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026965`
- `OLEAUT32!__imp_SysAllocString` at `0x180026965`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800269f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800269b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800269b1`

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
0x180026944  mov     rax, rsp
0x180026947  mov     [rax+8], rbx
0x18002694b  mov     [rax+10h], rsi
0x18002694f  push    rdi
0x180026950  sub     rsp, 30h
0x180026954  mov     esi, edx
0x180026956  mov     qword ptr [rax+20h], 0
0x18002695e  mov     dword ptr [rax+18h], 0
0x180026965  call    cs:__imp_SysAllocString
0x18002696b  mov     rdi, rax
0x18002696e  test    rax, rax
0x180026971  jnz     short loc_18002697A
0x180026973  mov     ebx, 8007000Eh
0x180026978  jmp     short loc_1800269F6
0x18002697a  lea     rdx, [rsp+38h+arg_10]
0x18002697f  mov     rcx, rdi
0x180026982  call    IsFirewallGroupActiveInternal
0x180026987  mov     ebx, eax
0x180026989  test    eax, eax
0x18002698b  js      short loc_1800269ED
0x18002698d  cmp     [rsp+38h+arg_10], esi
0x180026991  jz      short loc_1800269ED
0x180026993  xor     edx, edx; pUnkOuter
0x180026995  lea     rax, [rsp+38h+arg_18]
0x18002699a  lea     r9, IID_INetFwPolicy2; riid
0x1800269a1  mov     [rsp+38h+ppv], rax; ppv
0x1800269a6  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x1800269ad  lea     r8d, [rdx+1]; dwClsContext
0x1800269b1  call    cs:__imp_CoCreateInstance
0x1800269b7  mov     ebx, eax
0x1800269b9  test    eax, eax
0x1800269bb  js      short loc_1800269ED
0x1800269bd  mov     rcx, [rsp+38h+arg_18]
0x1800269c2  test    rcx, rcx
0x1800269c5  jnz     short loc_1800269CE
0x1800269c7  mov     ebx, 8000FFFFh
0x1800269cc  jmp     short loc_1800269ED
0x1800269ce  mov     rax, [rcx]
0x1800269d1  neg     esi
0x1800269d3  mov     r8, rdi
0x1800269d6  mov     edx, 7FFFFFFFh
0x1800269db  sbb     r9w, r9w
0x1800269df  mov     rax, [rax+0A0h]
0x1800269e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269eb  mov     ebx, eax
0x1800269ed  mov     rcx, rdi; bstrString
0x1800269f0  call    cs:__imp_SysFreeString
0x1800269f6  mov     rcx, [rsp+38h+arg_18]
0x1800269fb  test    rcx, rcx
0x1800269fe  jz      short loc_180026A0C
0x180026a00  mov     rax, [rcx]
0x180026a03  mov     rax, [rax+10h]
0x180026a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a0c  mov     rsi, [rsp+38h+arg_8]
0x180026a11  mov     eax, ebx
0x180026a13  mov     rbx, [rsp+38h+arg_0]
0x180026a18  add     rsp, 30h
0x180026a1c  pop     rdi
0x180026a1d  retn
```
