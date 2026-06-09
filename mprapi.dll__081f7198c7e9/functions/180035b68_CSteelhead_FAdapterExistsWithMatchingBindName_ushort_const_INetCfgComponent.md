# CSteelhead::FAdapterExistsWithMatchingBindName(ushort const *,INetCfgComponent * *)

- ea: `0x180035b68`
- end: `0x180035c68`
- name: `?FAdapterExistsWithMatchingBindName@CSteelhead@@IEAAHPEBGPEAPEAUINetCfgComponent@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct INetCfg **this, const unsigned __int16 *, struct INetCfgComponent **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036a0c`

## callees

- `0x180035948`
- `0x180035a78`
- `0x180035b68`
- `0x180036564`
- `0x180036b84`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180035bf0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180035bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c19`

## pseudocode

```c
__int64 __fastcall CSteelhead::FAdapterExistsWithMatchingBindName(
        struct INetCfg **this,
        const unsigned __int16 *a2,
        struct INetCfgComponent **a3)
{
  unsigned int v5; // edi
  int ShouldRouteOverAdapter; // esi
  struct INetCfgComponent *v7; // rbx
  _BYTE v9[48]; // [rsp+20h] [rbp-48h] BYREF
  LPCWSTR lpString2; // [rsp+70h] [rbp+8h] BYREF
  struct INetCfgComponent *v11; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = 0;
  ShouldRouteOverAdapter = 0;
  CIterNetCfgComponent::CIterNetCfgComponent((CIterNetCfgComponent *)v9, this[1], (const struct _GUID *)a3);
  v11 = 0;
  do
  {
    if ( ShouldRouteOverAdapter < 0
      || (unsigned int)CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(v9, &v11) )
    {
      break;
    }
    lpString2 = 0;
    v7 = v11;
    ShouldRouteOverAdapter = HrShouldRouteOverAdapter(v11, (unsigned __int16 **)&lpString2);
    if ( !ShouldRouteOverAdapter )
    {
      if ( !lstrcmpW(a2, lpString2) )
      {
        v5 = ShouldRouteOverAdapter + 1;
        *a3 = v7;
        if ( v7 )
          ((void (__fastcall *)(struct INetCfgComponent *))v7->lpVtbl->AddRef)(v7);
      }
      CoTaskMemFree((LPVOID)lpString2);
    }
    if ( v7 )
      ((void (__fastcall *)(struct INetCfgComponent *))v7->lpVtbl->Release)(v7);
    v11 = 0;
  }
  while ( !v5 );
  CIterNetCfgComponent::~CIterNetCfgComponent((CIterNetCfgComponent *)v9);
  return v5;
}

```

## disassembly

```asm
0x180035b68  mov     [rsp+arg_8], rbx
0x180035b6d  mov     [rsp+arg_18], rbp
0x180035b72  push    rsi
0x180035b73  push    rdi
0x180035b74  push    r14
0x180035b76  sub     rsp, 50h
0x180035b7a  mov     r14, r8
0x180035b7d  mov     rbp, rdx
0x180035b80  mov     qword ptr [r8], 0
0x180035b87  xor     edi, edi
0x180035b89  xor     esi, esi
0x180035b8b  mov     rdx, [rcx+8]; struct INetCfg *
0x180035b8f  lea     rcx, [rsp+68h+var_48]; this
0x180035b94  call    ??0CIterNetCfgComponent@@QEAA@PEAUINetCfg@@PEBU_GUID@@@Z; CIterNetCfgComponent::CIterNetCfgComponent(INetCfg *,_GUID const *)
0x180035b99  nop
0x180035b9a  mov     [rsp+68h+arg_10], rsi
0x180035ba2  test    esi, esi
0x180035ba4  js      loc_180035C47
0x180035baa  lea     rdx, [rsp+68h+arg_10]
0x180035bb2  lea     rcx, [rsp+68h+var_48]
0x180035bb7  call    ?HrNext@?$CIEnumIter@UIEnumNetCfgComponent@@PEAUINetCfgComponent@@@@QEAAJPEAPEAUINetCfgComponent@@@Z; CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(INetCfgComponent * *)
0x180035bbc  test    eax, eax
0x180035bbe  jnz     loc_180035C47
0x180035bc4  mov     [rsp+68h+lpString2], 0
0x180035bcd  lea     rdx, [rsp+68h+lpString2]; unsigned __int16 **
0x180035bd2  mov     rbx, [rsp+68h+arg_10]
0x180035bda  mov     rcx, rbx; struct INetCfgComponent *
0x180035bdd  call    ?HrShouldRouteOverAdapter@@YAJPEAUINetCfgComponent@@PEAPEAG@Z; HrShouldRouteOverAdapter(INetCfgComponent *,ushort * *)
0x180035be2  mov     esi, eax
0x180035be4  test    eax, eax
0x180035be6  jnz     short loc_180035C1F
0x180035be8  mov     rdx, [rsp+68h+lpString2]; lpString2
0x180035bed  mov     rcx, rbp; lpString1
0x180035bf0  call    cs:__imp_lstrcmpW
0x180035bf6  test    eax, eax
0x180035bf8  jnz     short loc_180035C14
0x180035bfa  lea     edi, [rsi+1]
0x180035bfd  mov     [r14], rbx
0x180035c00  test    rbx, rbx
0x180035c03  jz      short loc_180035C14
0x180035c05  mov     rax, [rbx]
0x180035c08  mov     rcx, rbx
0x180035c0b  mov     rax, [rax+8]
0x180035c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c14  mov     rcx, [rsp+68h+lpString2]; pv
0x180035c19  call    cs:__imp_CoTaskMemFree
0x180035c1f  test    rbx, rbx
0x180035c22  jz      short loc_180035C33
0x180035c24  mov     rax, [rbx]
0x180035c27  mov     rcx, rbx
0x180035c2a  mov     rax, [rax+10h]
0x180035c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c33  mov     [rsp+68h+arg_10], 0
0x180035c3f  test    edi, edi
0x180035c41  jz      loc_180035BA2
0x180035c47  lea     rcx, [rsp+68h+var_48]; this
0x180035c4c  call    ??1CIterNetCfgComponent@@QEAA@XZ; CIterNetCfgComponent::~CIterNetCfgComponent(void)
0x180035c51  mov     eax, edi
0x180035c53  lea     r11, [rsp+68h+var_18]
0x180035c58  mov     rbx, [r11+28h]
0x180035c5c  mov     rbp, [r11+38h]
0x180035c60  mov     rsp, r11
0x180035c63  pop     r14
0x180035c65  pop     rdi
0x180035c66  pop     rsi
0x180035c67  retn
```
