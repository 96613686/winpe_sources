# CImpIADOSecurity::getPolicy(ulong,ulong *)

- ea: `0x18002a920`
- end: `0x18002aa21`
- name: `?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z`
- size: `257`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a5f0`
- `0x18002a660`
- `0x18002abe0`
- `0x18002ac38`

## callees

- `0x18002a920`
- `0x180031010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002a965`
- `ole32!CoCreateInstance` at `0x18002a965`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::getPolicy(CImpIADOSecurity *this, unsigned int a2, unsigned int *a3)
{
  HRESULT v5; // edi
  unsigned int v7; // [rsp+60h] [rbp+20h] BYREF
  int v8; // [rsp+64h] [rbp+24h]
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF

  v8 = HIDWORD(this);
  ppv = 0;
  v7 = 3;
  v5 = CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned int *, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
           ppv,
           a2,
           5126,
           &v7,
           4,
           0);
    if ( v5 < 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned int *, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
             ppv,
             a2,
             4609,
             &v7,
             4,
             0);
      if ( v5 >= 0 )
      {
        if ( a2 )
        {
          if ( a2 == 1 && v7 == 3 )
            v7 = 1;
        }
        else
        {
          v7 = 0;
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( a3 )
    *a3 = v7;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a920  mov     [rsp-18h+arg_8], rbx
0x18002a925  mov     [rsp-18h+arg_0], rcx
0x18002a92a  push    rbp
0x18002a92b  push    rsi
0x18002a92c  push    rdi
0x18002a92d  mov     rbp, rsp
0x18002a930  sub     rsp, 40h
0x18002a934  mov     ebx, edx
0x18002a936  mov     [rbp+arg_10], 0
0x18002a93e  xor     edx, edx; pUnkOuter
0x18002a940  mov     dword ptr [rbp+arg_0], 3
0x18002a947  mov     rsi, r8
0x18002a94a  lea     rax, [rbp+arg_10]
0x18002a94e  lea     r9, IID_IInternetZoneManager; riid
0x18002a955  mov     [rsp+40h+ppv], rax; ppv
0x18002a95a  lea     rcx, CLSID_InternetZoneManager; rclsid
0x18002a961  lea     r8d, [rdx+1]; dwClsContext
0x18002a965  call    cs:__imp_CoCreateInstance
0x18002a96c  nop     dword ptr [rax+rax+00h]
0x18002a971  mov     edi, eax
0x18002a973  test    eax, eax
0x18002a975  js      short loc_18002A9F2
0x18002a977  mov     rcx, [rbp+arg_10]
0x18002a97b  lea     r9, [rbp+arg_0]
0x18002a97f  mov     [rsp+40h+var_18], 0
0x18002a987  mov     r8d, 1406h
0x18002a98d  mov     edx, ebx
0x18002a98f  mov     dword ptr [rsp+40h+ppv], 4
0x18002a997  mov     rax, [rcx]
0x18002a99a  mov     rax, [rax+38h]
0x18002a99e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9a3  mov     edi, eax
0x18002a9a5  test    eax, eax
0x18002a9a7  jns     short loc_18002A9F2
0x18002a9a9  mov     rcx, [rbp+arg_10]
0x18002a9ad  lea     r9, [rbp+arg_0]
0x18002a9b1  mov     [rsp+40h+var_18], 0
0x18002a9b9  mov     r8d, 1201h
0x18002a9bf  mov     edx, ebx
0x18002a9c1  mov     dword ptr [rsp+40h+ppv], 4
0x18002a9c9  mov     rax, [rcx]
0x18002a9cc  mov     rax, [rax+38h]
0x18002a9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9d5  mov     edi, eax
0x18002a9d7  test    eax, eax
0x18002a9d9  js      short loc_18002A9F2
0x18002a9db  test    ebx, ebx
0x18002a9dd  jnz     short loc_18002A9E4
0x18002a9df  mov     dword ptr [rbp+arg_0], ebx
0x18002a9e2  jmp     short loc_18002A9F2
0x18002a9e4  cmp     ebx, 1
0x18002a9e7  jnz     short loc_18002A9F2
0x18002a9e9  cmp     dword ptr [rbp+arg_0], 3
0x18002a9ed  jnz     short loc_18002A9F2
0x18002a9ef  mov     dword ptr [rbp+arg_0], ebx
0x18002a9f2  mov     rcx, [rbp+arg_10]
0x18002a9f6  test    rcx, rcx
0x18002a9f9  jz      short loc_18002AA07
0x18002a9fb  mov     rax, [rcx]
0x18002a9fe  mov     rax, [rax+10h]
0x18002aa02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa07  test    rsi, rsi
0x18002aa0a  jz      short loc_18002AA11
0x18002aa0c  mov     eax, dword ptr [rbp+arg_0]
0x18002aa0f  mov     [rsi], eax
0x18002aa11  mov     rbx, [rsp+40h+arg_8]
0x18002aa16  mov     eax, edi
0x18002aa18  add     rsp, 40h
0x18002aa1c  pop     rdi
0x18002aa1d  pop     rsi
0x18002aa1e  pop     rbp
0x18002aa1f  retn
```
