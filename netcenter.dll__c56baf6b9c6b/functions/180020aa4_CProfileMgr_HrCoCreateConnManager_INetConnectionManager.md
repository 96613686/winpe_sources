# CProfileMgr::HrCoCreateConnManager(INetConnectionManager * *)

- ea: `0x180020aa4`
- end: `0x180020b64`
- name: `?HrCoCreateConnManager@CProfileMgr@@AEAAJPEAPEAUINetConnectionManager@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(CProfileMgr *__hidden this, struct INetConnectionManager **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f630`
- `0x180020cf8`
- `0x1800213ec`

## callees

- `0x180014274`
- `0x18001ecf8`
- `0x18001ee80`
- `0x180020aa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020afb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020afb`

## pseudocode

```c
__int64 __fastcall CProfileMgr::HrCoCreateConnManager(struct IUnknown *this, struct IUnknown **a2)
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
  Instance = CoCreateInstance(
               &CLSID_ConnectionManager,
               0,
               0x404u,
               &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e,
               (LPVOID *)&ppv);
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
      51,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180020aa4  mov     [rsp+arg_8], rbx
0x180020aa9  mov     [rsp+arg_0], rcx
0x180020aae  push    rdi
0x180020aaf  sub     rsp, 30h
0x180020ab3  mov     rbx, rdx
0x180020ab6  test    rdx, rdx
0x180020ab9  jnz     short loc_180020AC5
0x180020abb  mov     eax, 80004003h
0x180020ac0  jmp     loc_180020B59
0x180020ac5  cmp     qword ptr [rdx], 0
0x180020ac9  jz      short loc_180020AD2
0x180020acb  xor     eax, eax
0x180020acd  jmp     loc_180020B59
0x180020ad2  lea     rax, [rsp+38h+arg_0]
0x180020ad7  mov     [rsp+38h+arg_0], 0
0x180020ae0  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x180020ae7  mov     [rsp+38h+ppv], rax; ppv
0x180020aec  xor     edx, edx; pUnkOuter
0x180020aee  lea     rcx, CLSID_ConnectionManager; rclsid
0x180020af5  mov     r8d, 404h; dwClsContext
0x180020afb  call    cs:__imp_CoCreateInstance
0x180020b01  mov     edi, eax
0x180020b03  test    eax, eax
0x180020b05  js      short loc_180020B26
0x180020b07  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180020b0c  test    rcx, rcx
0x180020b0f  jz      short loc_180020B26
0x180020b11  cmp     qword ptr [rbx], 0
0x180020b15  jnz     short loc_180020B21
0x180020b17  mov     [rbx], rcx
0x180020b1a  call    ?NcCoSetProxyBlanket@@YAXPEAUIUnknown@@@Z; NcCoSetProxyBlanket(IUnknown *)
0x180020b1f  jmp     short loc_180020B26
0x180020b21  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180020b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b2d  lea     rax, WPP_GLOBAL_Control
0x180020b34  cmp     rcx, rax
0x180020b37  jz      short loc_180020B57
0x180020b39  test    byte ptr [rcx+1Ch], 8
0x180020b3d  jz      short loc_180020B57
0x180020b3f  mov     rcx, [rcx+10h]
0x180020b43  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x180020b4a  mov     edx, 33h ; '3'
0x180020b4f  mov     r9d, edi
0x180020b52  call    WPP_SF_d
0x180020b57  mov     eax, edi
0x180020b59  mov     rbx, [rsp+38h+arg_8]
0x180020b5e  add     rsp, 30h
0x180020b62  pop     rdi
0x180020b63  retn
```
