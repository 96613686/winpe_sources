# CProfileMgr::HrCoCreateProfileManager(INetworkListManagerPrivate * *)

- ea: `0x180020b6c`
- end: `0x180020c2a`
- name: `?HrCoCreateProfileManager@CProfileMgr@@AEAAJPEAPEAUINetworkListManagerPrivate@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(CProfileMgr *__hidden this, struct INetworkListManagerPrivate **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f550`
- `0x180020cf8`

## callees

- `0x180014274`
- `0x18001ecf8`
- `0x18001ee80`
- `0x180020b6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020bc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020bc1`

## pseudocode

```c
__int64 __fastcall CProfileMgr::HrCoCreateProfileManager(struct IUnknown *this, struct IUnknown **a2)
{
  HRESULT Instance; // edi
  struct IUnknown *v5; // rcx
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( !a2 )
    return 2147500035LL;
  if ( *a2 )
    return 0;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v5 = ppv;
    if ( ppv )
    {
      if ( *a2 )
      {
        ReleaseObj(ppv);
      }
      else
      {
        *a2 = ppv;
        NcCoSetProxyBlanket(v5);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180020b6c  mov     [rsp+arg_8], rbx
0x180020b71  mov     [rsp+arg_0], rcx
0x180020b76  push    rdi
0x180020b77  sub     rsp, 30h
0x180020b7b  mov     rbx, rdx
0x180020b7e  test    rdx, rdx
0x180020b81  jnz     short loc_180020B8D
0x180020b83  mov     eax, 80004003h
0x180020b88  jmp     loc_180020C1F
0x180020b8d  cmp     qword ptr [rdx], 0
0x180020b91  jz      short loc_180020B9A
0x180020b93  xor     eax, eax
0x180020b95  jmp     loc_180020C1F
0x180020b9a  xor     edx, edx; pUnkOuter
0x180020b9c  mov     [rsp+38h+arg_0], 0
0x180020ba5  lea     rax, [rsp+38h+arg_0]
0x180020baa  lea     r9, IID_INetworkListManagerPrivate; riid
0x180020bb1  mov     [rsp+38h+ppv], rax; ppv
0x180020bb6  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180020bbd  lea     r8d, [rdx+4]; dwClsContext
0x180020bc1  call    cs:__imp_CoCreateInstance
0x180020bc7  mov     edi, eax
0x180020bc9  test    eax, eax
0x180020bcb  js      short loc_180020BEC
0x180020bcd  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180020bd2  test    rcx, rcx
0x180020bd5  jz      short loc_180020BEC
0x180020bd7  cmp     qword ptr [rbx], 0
0x180020bdb  jnz     short loc_180020BE7
0x180020bdd  mov     [rbx], rcx
0x180020be0  call    ?NcCoSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcCoSetProxyBlanket(IUnknown *)
0x180020be5  jmp     short loc_180020BEC
0x180020be7  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180020bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bf3  lea     rax, WPP_GLOBAL_Control
0x180020bfa  cmp     rcx, rax
0x180020bfd  jz      short loc_180020C1D
0x180020bff  test    byte ptr [rcx+1Ch], 8
0x180020c03  jz      short loc_180020C1D
0x180020c05  mov     rcx, [rcx+10h]
0x180020c09  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x180020c10  mov     edx, 34h ; '4'
0x180020c15  mov     r9d, edi
0x180020c18  call    WPP_SF_d
0x180020c1d  mov     eax, edi
0x180020c1f  mov     rbx, [rsp+38h+arg_8]
0x180020c24  add     rsp, 30h
0x180020c28  pop     rdi
0x180020c29  retn
```
