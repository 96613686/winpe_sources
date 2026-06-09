# CShareEngine::_InitShareableItem(CShareEngine::SHARINGENGINE_SHAREABLE_ITEM * *,IShellItem *)

- ea: `0x18005afb0`
- end: `0x18005b07a`
- name: `?_InitShareableItem@CShareEngine@@AEAAJPEAPEAUSHARINGENGINE_SHAREABLE_ITEM@1@PEAUIShellItem@@@Z`
- size: `202`
- prototype: `int(CShareEngine *__hidden this, struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM **, struct IShellItem *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180057790`
- `0x180057a00`

## callees

- `0x18005a184`
- `0x18005afb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005afcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005afcf`
- `SHCORE!IUnknown_Set` at `0x18005b000`
- `SHCORE!IUnknown_Set` at `0x18005b000`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18005b022`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18005b04a`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18005b022`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18005b04a`

## pseudocode

```c
__int64 __fastcall CShareEngine::_InitShareableItem(
        CShareEngine *this,
        struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM **a2,
        IUnknown *a3)
{
  LPVOID v5; // rax
  struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM *v6; // rbx
  HRESULT Instance; // edi
  CShareEngine *v8; // rcx
  struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = this;
  v5 = CoTaskMemAlloc(0x20u);
  v10 = (struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM *)v5;
  v6 = (struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM *)v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    *((_OWORD *)v5 + 1) = 0;
    *(_DWORD *)v5 = 0;
    IUnknown_Set((IUnknown **)v5 + 1, a3);
    Instance = SHCoCreateInstance(
                 0,
                 &CLSID_ShellItemArrayAsCollection,
                 0,
                 &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                 (void **)v6 + 2);
    if ( Instance < 0
      || (Instance = SHCoCreateInstance(
                       0,
                       &CLSID_ShellItemArrayAsCollection,
                       0,
                       &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                       (void **)v6 + 3),
          Instance < 0) )
    {
      CShareEngine::_FreeShareableItem(v8, &v10);
      v6 = v10;
    }
  }
  else
  {
    Instance = -2147024882;
  }
  *a2 = v6;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005afb0  mov     [rsp+arg_8], rbx
0x18005afb5  mov     [rsp+arg_10], rsi
0x18005afba  mov     [rsp+arg_0], rcx
0x18005afbf  push    rdi
0x18005afc0  sub     rsp, 30h
0x18005afc4  mov     ecx, 20h ; ' '; cb
0x18005afc9  mov     rdi, r8
0x18005afcc  mov     rsi, rdx
0x18005afcf  call    cs:__imp_CoTaskMemAlloc
0x18005afd5  mov     [rsp+38h+arg_0], rax
0x18005afda  mov     rbx, rax
0x18005afdd  test    rax, rax
0x18005afe0  jnz     short loc_18005AFE9
0x18005afe2  mov     edi, 8007000Eh
0x18005afe7  jmp     short loc_18005B065
0x18005afe9  xorps   xmm0, xmm0
0x18005afec  lea     rcx, [rax+8]; ppunk
0x18005aff0  movups  xmmword ptr [rax], xmm0
0x18005aff3  mov     rdx, rdi; punk
0x18005aff6  movups  xmmword ptr [rax+10h], xmm0
0x18005affa  mov     dword ptr [rax], 0
0x18005b000  call    cs:__imp_IUnknown_Set
0x18005b006  lea     rax, [rbx+10h]
0x18005b00a  xor     r8d, r8d; pUnkOuter
0x18005b00d  lea     r9, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; riid
0x18005b014  mov     [rsp+38h+ppv], rax; ppv
0x18005b019  lea     rdx, CLSID_ShellItemArrayAsCollection; pclsid
0x18005b020  xor     ecx, ecx; pszCLSID
0x18005b022  call    cs:__imp_SHCoCreateInstance
0x18005b028  mov     edi, eax
0x18005b02a  test    eax, eax
0x18005b02c  js      short loc_18005B056
0x18005b02e  lea     rax, [rbx+18h]
0x18005b032  xor     r8d, r8d; pUnkOuter
0x18005b035  lea     r9, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; riid
0x18005b03c  mov     [rsp+38h+ppv], rax; ppv
0x18005b041  lea     rdx, CLSID_ShellItemArrayAsCollection; pclsid
0x18005b048  xor     ecx, ecx; pszCLSID
0x18005b04a  call    cs:__imp_SHCoCreateInstance
0x18005b050  mov     edi, eax
0x18005b052  test    eax, eax
0x18005b054  jns     short loc_18005B065
0x18005b056  lea     rdx, [rsp+38h+arg_0]; struct CShareEngine::SHARINGENGINE_SHAREABLE_ITEM **
0x18005b05b  call    ?_FreeShareableItem@CShareEngine@@AEAAJPEAPEAUSHARINGENGINE_SHAREABLE_ITEM@1@@Z; CShareEngine::_FreeShareableItem(CShareEngine::SHARINGENGINE_SHAREABLE_ITEM * *)
0x18005b060  mov     rbx, [rsp+38h+arg_0]
0x18005b065  mov     [rsi], rbx
0x18005b068  mov     eax, edi
0x18005b06a  mov     rbx, [rsp+38h+arg_8]
0x18005b06f  mov     rsi, [rsp+38h+arg_10]
0x18005b074  add     rsp, 30h
0x18005b078  pop     rdi
0x18005b079  retn
```
