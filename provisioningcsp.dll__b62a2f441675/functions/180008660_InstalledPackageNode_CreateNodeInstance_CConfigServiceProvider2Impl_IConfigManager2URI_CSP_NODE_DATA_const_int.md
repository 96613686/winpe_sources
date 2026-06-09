# InstalledPackageNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180008660`
- end: `0x180008772`
- name: `?CreateNodeInstance@InstalledPackageNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006974`
- `0x180007c10`
- `0x180008660`
- `0x180038010`

## string_xrefs

- `0x1800086a4`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`
- `0x1800086ff`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InstalledPackageNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  _QWORD v16[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v18; // [rsp+78h] [rbp+30h] BYREF

  *a6 = 0;
  LODWORD(a6) = 0;
  v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int **))(*(_QWORD *)a2 + 136LL))(a2, &a6);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 25;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)v8,
      v15);
    return v8;
  }
  v10 = *((unsigned int *)a3 + 2);
  if ( (_DWORD)v10 != (_DWORD)a6 - 1 )
  {
    v8 = -2147418113;
    v9 = 26;
    goto LABEL_3;
  }
  v18 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 72LL))(
          a2,
          v10,
          0,
          &v18);
  v8 = v11;
  if ( v11 >= 0 )
  {
    v16[0] = v18;
    v8 = Microsoft::WRL::Details::MakeAndInitialize<InstalledPackageNode,ICSPNode,IConfigManager2URI *>(a5, v16);
    v13 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)(unsigned int)v11,
      v15);
    v12 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180008660  push    rbp
0x180008662  push    rbx
0x180008663  push    rsi
0x180008664  push    rdi
0x180008665  mov     rbp, rsp
0x180008668  sub     rsp, 48h
0x18000866c  mov     rsi, r8
0x18000866f  mov     rdi, rdx
0x180008672  mov     rax, [rbp+arg_28]
0x180008676  mov     dword ptr [rax], 0
0x18000867c  mov     dword ptr [rbp+arg_28], 0
0x180008683  mov     rax, [rdx]
0x180008686  lea     rdx, [rbp+arg_28]
0x18000868a  mov     rcx, rdi
0x18000868d  mov     rax, [rax+88h]
0x180008694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008699  mov     ebx, eax
0x18000869b  test    eax, eax
0x18000869d  jns     short loc_1800086BC
0x18000869f  mov     edx, 19h; void *
0x1800086a4  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x1800086ab  mov     r9d, ebx; char *
0x1800086ae  mov     rcx, [rbp+20h]; this
0x1800086b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800086b7  jmp     loc_180008766
0x1800086bc  mov     edx, [rsi+8]
0x1800086bf  mov     eax, dword ptr [rbp+arg_28]
0x1800086c2  dec     eax
0x1800086c4  cmp     edx, eax
0x1800086c6  jz      short loc_1800086D4
0x1800086c8  mov     ebx, 8000FFFFh
0x1800086cd  mov     edx, 1Ah
0x1800086d2  jmp     short loc_1800086A4
0x1800086d4  mov     [rbp+arg_8], 0
0x1800086dc  mov     rax, [rdi]
0x1800086df  lea     r9, [rbp+arg_8]
0x1800086e3  xor     r8d, r8d
0x1800086e6  mov     rcx, rdi
0x1800086e9  mov     rax, [rax+48h]
0x1800086ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f2  mov     ebx, eax
0x1800086f4  test    eax, eax
0x1800086f6  jns     short loc_180008731
0x1800086f8  mov     rcx, [rbp+20h]; this
0x1800086fc  mov     r9d, eax; char *
0x1800086ff  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x180008706  mov     edx, 1Dh; void *
0x18000870b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008710  nop
0x180008711  mov     rcx, [rbp+arg_8]
0x180008715  test    rcx, rcx
0x180008718  jz      short loc_18000872F
0x18000871a  mov     [rbp+arg_8], 0
0x180008722  mov     rax, [rcx]
0x180008725  mov     rax, [rax+10h]
0x180008729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872e  nop
0x18000872f  jmp     short loc_180008766
0x180008731  mov     rax, [rbp+arg_8]
0x180008735  mov     [rbp+var_18], rax
0x180008739  lea     rdx, [rbp+var_18]
0x18000873d  mov     rcx, [rbp+arg_20]
0x180008741  call    ??$MakeAndInitialize@VInstalledPackageNode@@UICSPNode@@PEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJPEAPEAUICSPNode@@$$QEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<InstalledPackageNode,ICSPNode,IConfigManager2URI *>(ICSPNode * *,IConfigManager2URI * &&)
0x180008746  mov     ebx, eax
0x180008748  mov     rcx, [rbp+arg_8]
0x18000874c  test    rcx, rcx
0x18000874f  jz      short loc_180008766
0x180008751  mov     [rbp+arg_8], 0
0x180008759  mov     rdx, [rcx]
0x18000875c  mov     rax, [rdx+10h]
0x180008760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008765  nop
0x180008766  mov     eax, ebx
0x180008768  add     rsp, 48h
0x18000876c  pop     rdi
0x18000876d  pop     rsi
0x18000876e  pop     rbx
0x18000876f  pop     rbp
0x180008770  retn
```
