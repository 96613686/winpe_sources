# CMachineSettings::OnChangedRouterEnabled(RSTableMetaEntry *,int,void *,void * *)

- ea: `0x180035c30`
- end: `0x180035cce`
- name: `?OnChangedRouterEnabled@CMachineSettings@@QEAAJPEAURSTableMetaEntry@@HPEAXPEAPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(CMachineSettings *__hidden this, struct RSTableMetaEntry *, int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180035c30`
- `0x1800371b8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035c90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035c90`
- `CLBCatQ!ActivatorUpdateForIsRouterChanges` at `0x180035ca3`
- `CLBCatQ!ActivatorUpdateForIsRouterChanges` at `0x180035ca3`

## pseudocode

```c
__int64 __fastcall CMachineSettings::OnChangedRouterEnabled(
        CMachineSettings *this,
        struct RSTableMetaEntry *a2,
        int a3,
        _WORD *a4)
{
  HRESULT IsRouterChanges; // edi
  BOOL v5; // ebx
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  IsRouterChanges = 0;
  v5 = 0;
  if ( a4 )
    v5 = ((*a4 - 89) & 0xFFDF) == 0;
  if ( !a3 )
  {
    if ( v5 )
      utAddComputerToCluster(v5);
    ppv = 0;
    IsRouterChanges = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
    if ( IsRouterChanges >= 0 )
    {
      IsRouterChanges = ActivatorUpdateForIsRouterChanges((struct ISimpleTableDispenser *)ppv, v5);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)IsRouterChanges;
}

```

## disassembly

```asm
0x180035c30  mov     [rsp+arg_0], rbx
0x180035c35  mov     [rsp+arg_8], rsi
0x180035c3a  push    rdi
0x180035c3b  sub     rsp, 30h
0x180035c3f  xor     edi, edi
0x180035c41  xor     ebx, ebx
0x180035c43  lea     esi, [rdi+1]
0x180035c46  test    r9, r9
0x180035c49  jz      short loc_180035C5E
0x180035c4b  movzx   eax, word ptr [r9]
0x180035c4f  mov     ecx, 0FFDFh
0x180035c54  sub     ax, 59h ; 'Y'
0x180035c58  test    cx, ax
0x180035c5b  cmovz   ebx, esi
0x180035c5e  test    r8d, r8d
0x180035c61  jnz     short loc_180035CBC
0x180035c63  test    ebx, ebx
0x180035c65  jz      short loc_180035C6E
0x180035c67  mov     ecx, ebx; int
0x180035c69  call    ?utAddComputerToCluster@@YAJH@Z; utAddComputerToCluster(int)
0x180035c6e  lea     rax, [rsp+38h+arg_18]
0x180035c73  mov     [rsp+38h+arg_18], rdi
0x180035c78  lea     r9, IID_ISimpleTableDispenser; riid
0x180035c7f  mov     [rsp+38h+ppv], rax; ppv
0x180035c84  mov     r8d, esi; dwClsContext
0x180035c87  lea     rcx, CLSID_STDispenser; rclsid
0x180035c8e  xor     edx, edx; pUnkOuter
0x180035c90  call    cs:__imp_CoCreateInstance
0x180035c96  mov     edi, eax
0x180035c98  test    eax, eax
0x180035c9a  js      short loc_180035CBC
0x180035c9c  mov     rcx, [rsp+38h+arg_18]
0x180035ca1  mov     edx, ebx
0x180035ca3  call    cs:__imp_?ActivatorUpdateForIsRouterChanges@@YAJPEAUISimpleTableDispenser@@H@Z; ActivatorUpdateForIsRouterChanges(ISimpleTableDispenser *,int)
0x180035ca9  mov     rcx, [rsp+38h+arg_18]
0x180035cae  mov     edi, eax
0x180035cb0  mov     rax, [rcx]
0x180035cb3  mov     rax, [rax+10h]
0x180035cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cbc  mov     rbx, [rsp+38h+arg_0]
0x180035cc1  mov     eax, edi
0x180035cc3  mov     rsi, [rsp+38h+arg_8]
0x180035cc8  add     rsp, 30h
0x180035ccc  pop     rdi
0x180035ccd  retn
```
