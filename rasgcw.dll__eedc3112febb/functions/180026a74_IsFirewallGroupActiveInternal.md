# IsFirewallGroupActiveInternal

- ea: `0x180026a74`
- end: `0x180026b27`
- name: `IsFirewallGroupActiveInternal`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026944`

## callees

- `0x180026a74`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026ab7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026ab7`

## pseudocode

```c
__int64 __fastcall IsFirewallGroupActiveInternal(__int64 a1, _DWORD *a2)
{
  HRESULT v4; // ebx
  __int16 v6; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  *a2 = 0;
  v6 = 0;
  v4 = CoCreateInstance(&CLSID_NetFwPolicy2, 0, 1u, &IID_INetFwPolicy2, &v7);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int16 *))(*(_QWORD *)v7 + 168LL))(
           v7,
           0x7FFFFFFF,
           a1,
           &v6);
    if ( v4 == 1 )
      v4 = -2147023728;
  }
  if ( v6 == -1 )
    *a2 = 1;
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026a74  mov     r11, rsp
0x180026a77  mov     [r11+8], rbx
0x180026a7b  mov     [r11+20h], rsi
0x180026a7f  push    rdi
0x180026a80  sub     rsp, 30h
0x180026a84  xor     eax, eax
0x180026a86  mov     qword ptr [r11+18h], 0
0x180026a8e  mov     [rdx], eax
0x180026a90  lea     r9, IID_INetFwPolicy2; riid
0x180026a97  mov     rdi, rdx
0x180026a9a  mov     [rsp+38h+arg_8], ax
0x180026a9f  xor     edx, edx; pUnkOuter
0x180026aa1  lea     rax, [r11+18h]
0x180026aa5  mov     rsi, rcx
0x180026aa8  mov     [r11-18h], rax
0x180026aac  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x180026ab3  lea     r8d, [rdx+1]; dwClsContext
0x180026ab7  call    cs:__imp_CoCreateInstance
0x180026abd  mov     ebx, eax
0x180026abf  test    eax, eax
0x180026ac1  js      short loc_180026AF1
0x180026ac3  mov     rcx, [rsp+38h+arg_10]
0x180026ac8  lea     r9, [rsp+38h+arg_8]
0x180026acd  mov     r8, rsi
0x180026ad0  mov     edx, 7FFFFFFFh
0x180026ad5  mov     rax, [rcx]
0x180026ad8  mov     rax, [rax+0A8h]
0x180026adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ae4  mov     ebx, eax
0x180026ae6  mov     eax, 80070490h
0x180026aeb  cmp     ebx, 1
0x180026aee  cmovz   ebx, eax
0x180026af1  cmp     [rsp+38h+arg_8], 0FFFFh
0x180026af7  jnz     short loc_180026AFF
0x180026af9  mov     dword ptr [rdi], 1
0x180026aff  mov     rcx, [rsp+38h+arg_10]
0x180026b04  test    rcx, rcx
0x180026b07  jz      short loc_180026B15
0x180026b09  mov     rax, [rcx]
0x180026b0c  mov     rax, [rax+10h]
0x180026b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b15  mov     rsi, [rsp+38h+arg_18]
0x180026b1a  mov     eax, ebx
0x180026b1c  mov     rbx, [rsp+38h+arg_0]
0x180026b21  add     rsp, 30h
0x180026b25  pop     rdi
0x180026b26  retn
```
