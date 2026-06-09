# CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)

- ea: `0x18002ab14`
- end: `0x18002abd7`
- name: `?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const unsigned __int16 *, unsigned int *, struct IInternetSecurityManager **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a5f0`
- `0x18002a660`
- `0x18002abe0`
- `0x18002ac38`

## callees

- `0x18002ab14`
- `0x180031010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002ab5b`
- `ole32!CoCreateInstance` at `0x18002ab5b`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::getZone(
        CImpIADOSecurity *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct IInternetSecurityManager **a4)
{
  HRESULT Instance; // esi
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]
  struct IInternetSecurityManager *ppv; // [rsp+60h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  ppv = 0;
  v9 = 4;
  Instance = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IInternetSecurityManager *, const unsigned __int16 *, unsigned int *, _QWORD))ppv->lpVtbl->MapUrlToZone)(
                 ppv,
                 a2,
                 &v9,
                 0);
    if ( Instance < 0 )
      v9 = 4;
  }
  if ( a4 )
  {
    *a4 = ppv;
  }
  else if ( ppv )
  {
    ((void (__fastcall *)(struct IInternetSecurityManager *))ppv->lpVtbl->Release)(ppv);
  }
  if ( a3 )
    *a3 = v9;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002ab14  mov     rax, rsp
0x18002ab17  mov     [rax+10h], rbx
0x18002ab1b  mov     [rax+8], rcx
0x18002ab1f  push    rbp
0x18002ab20  push    rsi
0x18002ab21  push    rdi
0x18002ab22  sub     rsp, 30h
0x18002ab26  mov     rbp, rdx
0x18002ab29  mov     qword ptr [rax+18h], 0
0x18002ab31  xor     edx, edx; pUnkOuter
0x18002ab33  mov     dword ptr [rax+8], 4
0x18002ab3a  mov     rdi, r9
0x18002ab3d  lea     rax, [rax+18h]
0x18002ab41  mov     rbx, r8
0x18002ab44  mov     [rsp+48h+ppv], rax; ppv
0x18002ab49  lea     r9, IID_IInternetSecurityManager; riid
0x18002ab50  lea     r8d, [rdx+1]; dwClsContext
0x18002ab54  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18002ab5b  call    cs:__imp_CoCreateInstance
0x18002ab62  nop     dword ptr [rax+rax+00h]
0x18002ab67  mov     esi, eax
0x18002ab69  test    eax, eax
0x18002ab6b  js      short loc_18002AB97
0x18002ab6d  mov     rcx, [rsp+48h+arg_10]
0x18002ab72  lea     r8, [rsp+48h+arg_0]
0x18002ab77  xor     r9d, r9d
0x18002ab7a  mov     rdx, rbp
0x18002ab7d  mov     rax, [rcx]
0x18002ab80  mov     rax, [rax+28h]
0x18002ab84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab89  mov     esi, eax
0x18002ab8b  test    eax, eax
0x18002ab8d  jns     short loc_18002AB97
0x18002ab8f  mov     [rsp+48h+arg_0], 4
0x18002ab97  test    rdi, rdi
0x18002ab9a  jz      short loc_18002ABA6
0x18002ab9c  mov     rax, [rsp+48h+arg_10]
0x18002aba1  mov     [rdi], rax
0x18002aba4  jmp     short loc_18002ABBC
0x18002aba6  mov     rcx, [rsp+48h+arg_10]
0x18002abab  test    rcx, rcx
0x18002abae  jz      short loc_18002ABBC
0x18002abb0  mov     rax, [rcx]
0x18002abb3  mov     rax, [rax+10h]
0x18002abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abbc  test    rbx, rbx
0x18002abbf  jz      short loc_18002ABC7
0x18002abc1  mov     eax, [rsp+48h+arg_0]
0x18002abc5  mov     [rbx], eax
0x18002abc7  mov     rbx, [rsp+48h+arg_8]
0x18002abcc  mov     eax, esi
0x18002abce  add     rsp, 30h
0x18002abd2  pop     rdi
0x18002abd3  pop     rsi
0x18002abd4  pop     rbp
0x18002abd5  retn
```
