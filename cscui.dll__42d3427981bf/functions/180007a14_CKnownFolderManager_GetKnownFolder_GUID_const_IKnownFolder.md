# CKnownFolderManager::GetKnownFolder(_GUID const &,IKnownFolder * *)

- ea: `0x180007a14`
- end: `0x180007b3b`
- name: `?GetKnownFolder@CKnownFolderManager@@QEAAJAEBU_GUID@@PEAPEAUIKnownFolder@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CKnownFolderManager *__hidden this, const struct _GUID *, struct IKnownFolder **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800079a8`
- `0x18003618c`

## callees

- `0x180006430`
- `0x180007a14`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007aa7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007aa7`

## pseudocode

```c
__int64 __fastcall CKnownFolderManager::GetKnownFolder(
        CKnownFolderManager *this,
        const struct _GUID *a2,
        struct IKnownFolder **a3)
{
  unsigned int v3; // esi
  HRESULT Instance; // ebx
  HRESULT v8; // eax
  struct IUnknown *ppv; // [rsp+60h] [rbp+30h] BYREF
  __int64 v11; // [rsp+70h] [rbp+40h] BYREF

  *a3 = 0;
  v3 = *(_DWORD *)this;
  v11 = 0;
  ppv = 0;
  if ( v3 )
  {
    Instance = CoCreateInstance(
                 &CLSID_StdGlobalInterfaceTable,
                 0,
                 1u,
                 &GUID_00000146_0000_0000_c000_000000000046,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_9;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, GUID *, __int64 *))ppv->lpVtbl[1].Release)(
           ppv,
           v3,
           &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
           &v11);
  }
  else
  {
    Instance = CoCreateInstance(
                 &CLSID_KnownFolderManager,
                 0,
                 1u,
                 &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    if ( (int)MarshalToGIT(ppv, &IID_IKnownFolderManager, (unsigned int *)this) < 0 )
      *(_DWORD *)this = 0;
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
           ppv,
           &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
           &v11);
  }
  Instance = v8;
  ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
LABEL_9:
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct IKnownFolder **))(*(_QWORD *)v11 + 48LL))(
                 v11,
                 a2,
                 a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007a14  mov     [rsp-28h+arg_8], rbx
0x180007a19  push    rbp
0x180007a1a  push    rsi
0x180007a1b  push    rdi
0x180007a1c  push    r14
0x180007a1e  push    r15
0x180007a20  mov     rbp, rsp
0x180007a23  sub     rsp, 30h
0x180007a27  mov     qword ptr [r8], 0
0x180007a2e  lea     rax, [rbp+arg_0]
0x180007a32  mov     esi, [rcx]
0x180007a34  mov     r15, rdx
0x180007a37  xor     edx, edx; pUnkOuter
0x180007a39  mov     [rbp+arg_10], 0
0x180007a41  mov     [rbp+arg_0], 0
0x180007a49  mov     r14, r8
0x180007a4c  mov     [rsp+30h+ppv], rax; ppv
0x180007a51  mov     rdi, rcx
0x180007a54  lea     r8d, [rdx+1]; dwClsContext
0x180007a58  test    esi, esi
0x180007a5a  jz      short loc_180007A99
0x180007a5c  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007a63  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007a6a  call    cs:__imp_CoCreateInstance
0x180007a70  mov     ebx, eax
0x180007a72  test    eax, eax
0x180007a74  js      loc_180007AFC
0x180007a7a  mov     rcx, [rbp+arg_0]
0x180007a7e  lea     r9, [rbp+arg_10]
0x180007a82  lea     r8, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018
0x180007a89  mov     edx, esi
0x180007a8b  mov     rax, [rcx]
0x180007a8e  mov     rax, [rax+28h]
0x180007a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a97  jmp     short loc_180007AEA
0x180007a99  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180007aa0  lea     rcx, CLSID_KnownFolderManager; rclsid
0x180007aa7  call    cs:__imp_CoCreateInstance
0x180007aad  mov     ebx, eax
0x180007aaf  test    eax, eax
0x180007ab1  js      short loc_180007B28
0x180007ab3  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180007ab7  lea     rdx, IID_IKnownFolderManager; struct _GUID *
0x180007abe  mov     r8, rdi; unsigned int *
0x180007ac1  call    ?MarshalToGIT@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; MarshalToGIT(IUnknown *,_GUID const &,ulong *)
0x180007ac6  test    eax, eax
0x180007ac8  jns     short loc_180007AD0
0x180007aca  mov     dword ptr [rdi], 0
0x180007ad0  mov     rcx, [rbp+arg_0]
0x180007ad4  lea     r8, [rbp+arg_10]
0x180007ad8  lea     rdx, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018
0x180007adf  mov     rax, [rcx]
0x180007ae2  mov     rax, [rax]
0x180007ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aea  mov     rcx, [rbp+arg_0]
0x180007aee  mov     ebx, eax
0x180007af0  mov     rax, [rcx]
0x180007af3  mov     rax, [rax+10h]
0x180007af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afc  test    ebx, ebx
0x180007afe  js      short loc_180007B28
0x180007b00  mov     rcx, [rbp+arg_10]
0x180007b04  mov     r8, r14
0x180007b07  mov     rdx, r15
0x180007b0a  mov     rax, [rcx]
0x180007b0d  mov     rax, [rax+30h]
0x180007b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b16  mov     rcx, [rbp+arg_10]
0x180007b1a  mov     ebx, eax
0x180007b1c  mov     rdx, [rcx]
0x180007b1f  mov     rax, [rdx+10h]
0x180007b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b28  mov     eax, ebx
0x180007b2a  mov     rbx, [rsp+30h+arg_8]
0x180007b2f  add     rsp, 30h
0x180007b33  pop     r15
0x180007b35  pop     r14
0x180007b37  pop     rdi
0x180007b38  pop     rsi
0x180007b39  pop     rbp
0x180007b3a  retn
```
