# CSharingConfiguration::GetSharingMode(IShellItemArray *,SHARE_MODE *)

- ea: `0x180054620`
- end: `0x1800547e2`
- name: `?GetSharingMode@CSharingConfiguration@@UEAAJPEAUIShellItemArray@@PEAW4SHARE_MODE@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CSharingConfiguration *__hidden this, struct IShellItemArray *, enum SHARE_MODE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18001d370`
- `0x180054620`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005468c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054704`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005468c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054704`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18005464d`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18005464d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180054662`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180054662`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::GetSharingMode(
        CSharingConfiguration *this,
        struct IShellItemArray *a2,
        enum SHARE_MODE *a3)
{
  int v5; // edi
  int v6; // ebx
  struct IShellItemArrayVtbl *lpVtbl; // rax
  struct IShellItemArrayVtbl *v8; // rax
  struct IShellItem *v10; // [rsp+30h] [rbp-18h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+50h] BYREF

  v5 = 0;
  if ( !SHRegGetBoolValueFromHKCUHKLM(
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
          L"SharingWizardOn",
          1) )
    goto LABEL_15;
  if ( !(unsigned int)SHWindowsPolicy(POLID_NoInplaceSharing) )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_LibraryShareEngine, 0, 1u, &GUID_559b1911_d3af_486e_b8bc_242b24df0114, &ppv) >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *))(*(_QWORD *)ppv + 32LL))(ppv, a2);
      if ( v6 >= 0 && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 96LL))(ppv) )
      {
        v5 = 1;
        *(_DWORD *)a3 = 2;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v5 )
        goto LABEL_13;
    }
  }
  ppv = 0;
  if ( CoCreateInstance(&CLSID_SmbShareEngine, 0, 1u, &GUID_559b1911_d3af_486e_b8bc_242b24df0114, &ppv) < 0 )
    goto LABEL_15;
  v6 = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *))(*(_QWORD *)ppv + 32LL))(ppv, a2);
  if ( v6 >= 0 && !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 96LL))(ppv) )
  {
    v5 = 1;
    *(_DWORD *)a3 = 0;
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v5 )
  {
LABEL_13:
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  else
  {
LABEL_15:
    lpVtbl = a2->lpVtbl;
    LODWORD(ppv) = 0;
    v6 = ((__int64 (__fastcall *)(struct IShellItemArray *, LPVOID *))lpVtbl->GetCount)(a2, &ppv);
    if ( v6 < 0 )
      return (unsigned int)v6;
    if ( (_DWORD)ppv == 1 )
    {
      v8 = a2->lpVtbl;
      v10 = 0;
      v6 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v8->GetItemAt)(a2, 0, &v10);
      if ( v6 < 0 )
        return (unsigned int)v6;
      if ( !(unsigned int)CanShareSMB(v10) )
      {
        v5 = 1;
        *(_DWORD *)a3 = 3;
      }
      ((void (__fastcall *)(struct IShellItem *))v10->lpVtbl->Release)(v10);
    }
  }
  if ( !v5 )
    return (unsigned int)-2147467263;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180054620  push    rbp
0x180054622  push    rbx
0x180054623  push    rsi
0x180054624  push    rdi
0x180054625  push    r12
0x180054627  push    r14
0x180054629  mov     rbp, rsp
0x18005462c  sub     rsp, 48h
0x180054630  mov     rsi, r8
0x180054633  lea     rcx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005463a  mov     r14, rdx
0x18005463d  xor     edi, edi
0x18005463f  lea     rdx, pszValue; "SharingWizardOn"
0x180054646  lea     r12d, [rdi+1]
0x18005464a  mov     r8d, r12d; fDefault
0x18005464d  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x180054653  test    eax, eax
0x180054655  jz      loc_18005475A
0x18005465b  lea     rcx, POLID_NoInplaceSharing
0x180054662  call    cs:__imp_SHWindowsPolicy
0x180054668  test    eax, eax
0x18005466a  jnz     short loc_1800546E0
0x18005466c  lea     rax, [rbp+arg_18]
0x180054670  mov     [rbp+arg_18], rdi
0x180054674  lea     r9, _GUID_559b1911_d3af_486e_b8bc_242b24df0114; riid
0x18005467b  mov     [rsp+48h+ppv], rax; ppv
0x180054680  mov     r8d, r12d; dwClsContext
0x180054683  lea     rcx, CLSID_LibraryShareEngine; rclsid
0x18005468a  xor     edx, edx; pUnkOuter
0x18005468c  call    cs:__imp_CoCreateInstance
0x180054692  test    eax, eax
0x180054694  js      short loc_1800546E0
0x180054696  mov     rcx, [rbp+arg_18]
0x18005469a  mov     rdx, r14
0x18005469d  mov     rax, [rcx]
0x1800546a0  mov     rax, [rax+20h]
0x1800546a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546a9  mov     ebx, eax
0x1800546ab  test    eax, eax
0x1800546ad  js      short loc_1800546CC
0x1800546af  mov     rcx, [rbp+arg_18]
0x1800546b3  mov     rdx, [rcx]
0x1800546b6  mov     rax, [rdx+60h]
0x1800546ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546bf  test    eax, eax
0x1800546c1  jnz     short loc_1800546CC
0x1800546c3  mov     edi, r12d
0x1800546c6  mov     dword ptr [rsi], 2
0x1800546cc  mov     rcx, [rbp+arg_18]
0x1800546d0  mov     rax, [rcx]
0x1800546d3  mov     rax, [rax+10h]
0x1800546d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546dc  test    edi, edi
0x1800546de  jnz     short loc_180054754
0x1800546e0  lea     rax, [rbp+arg_18]
0x1800546e4  mov     [rbp+arg_18], 0
0x1800546ec  lea     r9, _GUID_559b1911_d3af_486e_b8bc_242b24df0114; riid
0x1800546f3  mov     [rsp+48h+ppv], rax; ppv
0x1800546f8  mov     r8d, r12d; dwClsContext
0x1800546fb  lea     rcx, CLSID_SmbShareEngine; rclsid
0x180054702  xor     edx, edx; pUnkOuter
0x180054704  call    cs:__imp_CoCreateInstance
0x18005470a  test    eax, eax
0x18005470c  js      short loc_18005475A
0x18005470e  mov     rcx, [rbp+arg_18]
0x180054712  mov     rdx, r14
0x180054715  mov     rax, [rcx]
0x180054718  mov     rax, [rax+20h]
0x18005471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054721  mov     ebx, eax
0x180054723  test    eax, eax
0x180054725  js      short loc_180054740
0x180054727  mov     rcx, [rbp+arg_18]
0x18005472b  mov     rax, [rcx]
0x18005472e  mov     rax, [rax+60h]
0x180054732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054737  test    eax, eax
0x180054739  jnz     short loc_180054740
0x18005473b  mov     edi, r12d
0x18005473e  mov     [rsi], eax
0x180054740  mov     rcx, [rbp+arg_18]
0x180054744  mov     rax, [rcx]
0x180054747  mov     rax, [rax+10h]
0x18005474b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054750  test    edi, edi
0x180054752  jz      short loc_18005475A
0x180054754  test    ebx, ebx
0x180054756  js      short loc_1800547D3
0x180054758  jmp     short loc_1800547C9
0x18005475a  mov     rax, [r14]
0x18005475d  lea     rdx, [rbp+arg_18]
0x180054761  mov     rcx, r14
0x180054764  mov     dword ptr [rbp+arg_18], 0
0x18005476b  mov     rax, [rax+38h]
0x18005476f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054774  mov     ebx, eax
0x180054776  test    eax, eax
0x180054778  js      short loc_1800547D3
0x18005477a  cmp     dword ptr [rbp+arg_18], r12d
0x18005477e  jnz     short loc_1800547C9
0x180054780  mov     rax, [r14]
0x180054783  lea     r8, [rbp+var_18]
0x180054787  xor     edx, edx
0x180054789  mov     [rbp+var_18], 0
0x180054791  mov     rcx, r14
0x180054794  mov     rax, [rax+40h]
0x180054798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005479d  mov     ebx, eax
0x18005479f  test    eax, eax
0x1800547a1  js      short loc_1800547D3
0x1800547a3  mov     rcx, [rbp+var_18]; struct IShellItem *
0x1800547a7  call    ?CanShareSMB@@YAJPEAUIShellItem@@@Z; CanShareSMB(IShellItem *)
0x1800547ac  test    eax, eax
0x1800547ae  jnz     short loc_1800547B9
0x1800547b0  mov     edi, r12d
0x1800547b3  mov     dword ptr [rsi], 3
0x1800547b9  mov     rcx, [rbp+var_18]
0x1800547bd  mov     rax, [rcx]
0x1800547c0  mov     rax, [rax+10h]
0x1800547c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547c9  test    edi, edi
0x1800547cb  mov     eax, 80004001h
0x1800547d0  cmovz   ebx, eax
0x1800547d3  mov     eax, ebx
0x1800547d5  add     rsp, 48h
0x1800547d9  pop     r14
0x1800547db  pop     r12
0x1800547dd  pop     rdi
0x1800547de  pop     rsi
0x1800547df  pop     rbx
0x1800547e0  pop     rbp
0x1800547e1  retn
```
