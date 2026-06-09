# CContextMenuOverExplorerCommands::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180014920`
- end: `0x180014b94`
- name: `?QueryContextMenu@CContextMenuOverExplorerCommands@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `628`
- prototype: `int(CContextMenuOverExplorerCommands *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014920`
- `0x180014b9c`
- `0x180014f58`
- `0x180014fcc`
- `0x180015cf8`
- `0x18001d574`
- `0x180023280`
- `0x1800232a0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b0a`
- `SHCORE!IUnknown_SetSite` at `0x1800149a6`
- `SHCORE!IUnknown_SetSite` at `0x1800149a6`
- `USER32!InsertMenuW` at `0x180014b64`
- `USER32!InsertMenuW` at `0x180014b89`
- `USER32!InsertMenuW` at `0x180014b64`
- `USER32!InsertMenuW` at `0x180014b89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContextMenuOverExplorerCommands::QueryContextMenu(
        CContextMenuOverExplorerCommands *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  CContextMenuOverExplorerCommands *v9; // rdi
  unsigned int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rcx
  unsigned int v15; // esi
  char inserted; // al
  int v17; // ecx
  char v18; // al
  int v19; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  int (__fastcall *v21)(__int64, _QWORD, LPVOID *); // [rsp+58h] [rbp-8h]
  int v22; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+58h]

  v23 = a4;
  v9 = (CContextMenuOverExplorerCommands *)((char *)this - 32);
  *((_DWORD *)this + 21) = a4;
  v10 = 0;
  v19 = 0;
  v22 = 0;
  (*(void (__fastcall **)(char *, int *, int *))(*((_QWORD *)this - 4) + 64LL))((char *)this - 32, &v19, &v22);
  if ( (v19 & a6) != 0 )
    return v10;
  if ( (int)CContextMenuOverExplorerCommands::_EnsureParentCommand(v9) < 0 )
    return v10;
  LOBYTE(v11) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialIExplorerCommand>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CentennialIExplorerCommand>::GetImpl'::`2'::impl,
    v11);
  IUnknown_SetSite(*((IUnknown **)this + 2), *((IUnknown **)this - 2));
  if ( (int)CContextMenuOverExplorerCommands::_EnsureShellItemArray(v9) < 0 )
    return v10;
  a6 = 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, unsigned int *))(**((_QWORD **)this + 2) + 56LL))(
         *((_QWORD *)this + 2),
         *((_QWORD *)this + 7),
         1,
         &a6) < 0
    || (a6 & 2) != 0 )
  {
    return v10;
  }
  pv = 0;
  v12 = *((_QWORD *)this + 2);
  v21 = *(int (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v12 + 24LL);
  pv = 0;
  if ( v21(v12, *((_QWORD *)this + 7), &pv) >= 0 )
  {
    *((_DWORD *)this + 20) = 0;
    v13 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( (v22 & 4) != 0 )
    {
      v15 = v23;
      inserted = CContextMenuOverExplorerCommands::InsertMenuItemForParentCommand(v9, a2, a3, v23, a6, v22, pv);
    }
    else
    {
      if ( (*(int (__fastcall **)(_QWORD *, char *))(**((_QWORD **)v9 + 6) + 80LL))(
             *((_QWORD **)v9 + 6),
             (char *)this + 24) < 0 )
        goto LABEL_11;
      v15 = v23;
      inserted = CContextMenuOverExplorerCommands::InsertMenuItemForSubCommands(
                   v9,
                   a2,
                   a3,
                   v23,
                   a5,
                   a6,
                   (const unsigned __int16 *)pv);
    }
    if ( inserted )
    {
      v17 = 0;
      v18 = v22;
      if ( (v22 & 1) != 0 )
      {
        InsertMenuW(a2, a3, 0xC00u, 0, 0);
        v17 = 1;
        v18 = v22;
      }
      if ( (v18 & 2) != 0 )
        InsertMenuW(a2, v17 + a3 + 1, 0xC00u, 0, 0);
      v10 = (unsigned __int16)(*((_WORD *)this + 40) + 1);
      *((_DWORD *)this + 22) = v15 + *((_DWORD *)this + 20) - 1;
    }
  }
LABEL_11:
  if ( pv )
    CoTaskMemFree(pv);
  return v10;
}

```

## disassembly

```asm
0x180014920  mov     [rsp-38h+arg_8], rbx
0x180014925  mov     [rsp-38h+arg_18], r9d
0x18001492a  push    rbp
0x18001492b  push    rsi
0x18001492c  push    rdi
0x18001492d  push    r12
0x18001492f  push    r13
0x180014931  push    r14
0x180014933  push    r15
0x180014935  mov     rbp, rsp
0x180014938  sub     rsp, 60h
0x18001493c  mov     r12d, r8d
0x18001493f  mov     r13, rdx
0x180014942  mov     rbx, rcx
0x180014945  lea     rdi, [rcx-20h]
0x180014949  mov     [rdi+74h], r9d
0x18001494d  xor     esi, esi
0x18001494f  mov     r15d, esi
0x180014952  mov     [rbp+var_20], esi
0x180014955  mov     [rbp+arg_0], esi
0x180014958  mov     rax, [rdi]
0x18001495b  lea     r8, [rbp+arg_0]
0x18001495f  lea     rdx, [rbp+var_20]
0x180014963  mov     rcx, rdi
0x180014966  mov     rax, [rax+40h]
0x18001496a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001496f  mov     eax, [rbp+var_20]
0x180014972  test    [rbp+arg_28], eax
0x180014975  jnz     loc_180014A76
0x18001497b  mov     rcx, rdi; this
0x18001497e  call    ?_EnsureParentCommand@CContextMenuOverExplorerCommands@@AEAAJXZ; CContextMenuOverExplorerCommands::_EnsureParentCommand(void)
0x180014983  test    eax, eax
0x180014985  js      loc_180014A76
0x18001498b  lea     r14d, [rsi+1]
0x18001498f  mov     dl, r14b
0x180014992  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialIExplorerCommand@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialIExplorerCommand@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialIExplorerCommand> `wil::Feature<__WilFeatureTraits_Feature_CentennialIExplorerCommand>::GetImpl(void)'::`2'::impl
0x180014999  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialIExplorerCommand@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialIExplorerCommand>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001499e  mov     rdx, [rbx-10h]; punkSite
0x1800149a2  mov     rcx, [rbx+10h]; punk
0x1800149a6  call    cs:__imp_IUnknown_SetSite
0x1800149ac  mov     rcx, rdi; this
0x1800149af  call    ?_EnsureShellItemArray@CContextMenuOverExplorerCommands@@AEAAJXZ; CContextMenuOverExplorerCommands::_EnsureShellItemArray(void)
0x1800149b4  test    eax, eax
0x1800149b6  js      loc_180014A76
0x1800149bc  mov     [rbp+arg_28], esi
0x1800149bf  mov     rcx, [rbx+10h]
0x1800149c3  mov     rax, [rcx]
0x1800149c6  lea     r9, [rbp+arg_28]
0x1800149ca  mov     r8d, r14d
0x1800149cd  mov     rdx, [rbx+38h]
0x1800149d1  mov     rax, [rax+38h]
0x1800149d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149da  test    eax, eax
0x1800149dc  js      loc_180014A76
0x1800149e2  test    byte ptr [rbp+arg_28], 2
0x1800149e6  jnz     loc_180014A76
0x1800149ec  mov     [rbp+pv], rsi
0x1800149f0  mov     r14, [rbx+10h]
0x1800149f4  mov     rax, [r14]
0x1800149f7  mov     rax, [rax+18h]
0x1800149fb  mov     [rbp+var_8], rax
0x1800149ff  mov     rsi, [rbp+pv]
0x180014a03  test    rsi, rsi
0x180014a06  jnz     loc_180014AFE
0x180014a0c  mov     [rbp+pv], 0
0x180014a14  lea     r8, [rbp+pv]
0x180014a18  mov     rdx, [rbx+38h]
0x180014a1c  mov     rcx, r14
0x180014a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a24  xor     r14d, r14d
0x180014a27  test    eax, eax
0x180014a29  js      short loc_180014A6D
0x180014a2b  mov     [rbx+50h], r14d
0x180014a2f  lea     rsi, [rbx+18h]
0x180014a33  mov     rcx, [rsi]
0x180014a36  mov     [rsi], r14
0x180014a39  test    rcx, rcx
0x180014a3c  jz      short loc_180014A4A
0x180014a3e  mov     rax, [rcx]
0x180014a41  mov     rax, [rax+10h]
0x180014a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a4a  mov     ecx, [rbp+arg_0]
0x180014a4d  test    cl, 4
0x180014a50  jnz     short loc_180014A9A
0x180014a52  mov     rcx, [rdi+30h]
0x180014a56  mov     rax, [rcx]
0x180014a59  mov     rdx, rsi
0x180014a5c  mov     rax, [rax+50h]
0x180014a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a65  test    eax, eax
0x180014a67  jns     loc_180014B23
0x180014a6d  mov     rcx, [rbp+pv]; pv
0x180014a71  test    rcx, rcx
0x180014a74  jnz     short loc_180014A91
0x180014a76  mov     eax, r15d
0x180014a79  mov     rbx, [rsp+60h+arg_8]
0x180014a81  add     rsp, 60h
0x180014a85  pop     r15
0x180014a87  pop     r14
0x180014a89  pop     r13
0x180014a8b  pop     r12
0x180014a8d  pop     rdi
0x180014a8e  pop     rsi
0x180014a8f  pop     rbp
0x180014a90  retn
0x180014a91  call    cs:__imp_CoTaskMemFree
0x180014a97  nop
0x180014a98  jmp     short loc_180014A76
0x180014a9a  mov     rax, [rbp+pv]
0x180014a9e  mov     edx, [rbp+arg_28]
0x180014aa1  mov     [rsp+60h+var_30], rax
0x180014aa6  mov     [rsp+60h+var_38], ecx
0x180014aaa  mov     dword ptr [rsp+60h+lpNewItem], edx
0x180014aae  mov     esi, [rbp+arg_18]
0x180014ab1  mov     r9d, esi
0x180014ab4  mov     r8d, r12d
0x180014ab7  mov     rdx, r13
0x180014aba  mov     rcx, rdi
0x180014abd  call    ?InsertMenuItemForParentCommand@CContextMenuOverExplorerCommands@@AEAA_NPEAUHMENU__@@IIKW4DATA_DRIVEN_POPUP_MENU_FLAGS@@PEBG@Z; CContextMenuOverExplorerCommands::InsertMenuItemForParentCommand(HMENU__ *,uint,uint,ulong,DATA_DRIVEN_POPUP_MENU_FLAGS,ushort const *)
0x180014ac2  test    al, al
0x180014ac4  jz      short loc_180014A6D
0x180014ac6  mov     ecx, r14d
0x180014ac9  mov     eax, [rbp+arg_0]
0x180014acc  mov     edi, 1
0x180014ad1  mov     r15d, 0C00h
0x180014ad7  test    dil, al
0x180014ada  jnz     short loc_180014B53
0x180014adc  test    al, 2
0x180014ade  jnz     loc_180014B74
0x180014ae4  movzx   eax, word ptr [rbx+50h]
0x180014ae8  add     ax, di
0x180014aeb  movzx   r15d, ax
0x180014aef  mov     ecx, [rbx+50h]
0x180014af2  dec     ecx
0x180014af4  add     ecx, esi
0x180014af6  mov     [rbx+58h], ecx
0x180014af9  jmp     loc_180014A6D
0x180014afe  lea     rcx, [rbp+var_10]; this
0x180014b02  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180014b07  mov     rcx, rsi; pv
0x180014b0a  call    cs:__imp_CoTaskMemFree
0x180014b10  lea     rcx, [rbp+var_10]; this
0x180014b14  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014b19  nop
0x180014b1a  mov     rax, [rbp+var_8]
0x180014b1e  jmp     loc_180014A0C
0x180014b23  mov     rax, [rbp+pv]
0x180014b27  mov     ecx, [rbp+arg_28]
0x180014b2a  mov     [rsp+60h+var_30], rax; unsigned __int16 *
0x180014b2f  mov     [rsp+60h+var_38], ecx; unsigned int
0x180014b33  mov     eax, [rbp+arg_20]
0x180014b36  mov     dword ptr [rsp+60h+lpNewItem], eax; unsigned int
0x180014b3a  mov     esi, [rbp+arg_18]
0x180014b3d  mov     r9d, esi; unsigned int
0x180014b40  mov     r8d, r12d; unsigned int
0x180014b43  mov     rdx, r13; HMENU
0x180014b46  mov     rcx, rdi; this
0x180014b49  call    ?InsertMenuItemForSubCommands@CContextMenuOverExplorerCommands@@AEAA_NPEAUHMENU__@@IIIKPEBG@Z; CContextMenuOverExplorerCommands::InsertMenuItemForSubCommands(HMENU__ *,uint,uint,uint,ulong,ushort const *)
0x180014b4e  jmp     loc_180014AC2
0x180014b53  mov     [rsp+60h+lpNewItem], r14; lpNewItem
0x180014b58  xor     r9d, r9d; uIDNewItem
0x180014b5b  mov     r8d, r15d; uFlags
0x180014b5e  mov     edx, r12d; uPosition
0x180014b61  mov     rcx, r13; hMenu
0x180014b64  call    cs:__imp_InsertMenuW
0x180014b6a  mov     ecx, edi
0x180014b6c  mov     eax, [rbp+arg_0]
0x180014b6f  jmp     loc_180014ADC
0x180014b74  lea     edx, [r12+1]
0x180014b79  add     edx, ecx; uPosition
0x180014b7b  mov     [rsp+60h+lpNewItem], r14; lpNewItem
0x180014b80  xor     r9d, r9d; uIDNewItem
0x180014b83  mov     r8d, r15d; uFlags
0x180014b86  mov     rcx, r13; hMenu
0x180014b89  call    cs:__imp_InsertMenuW
0x180014b8f  jmp     loc_180014AE4
```
