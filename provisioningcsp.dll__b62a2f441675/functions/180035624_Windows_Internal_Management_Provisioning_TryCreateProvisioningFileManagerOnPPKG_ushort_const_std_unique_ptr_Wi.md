# Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &)

- ea: `0x180035624`
- end: `0x1800356f5`
- name: `?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180034150`

## callees

- `0x1800353a8`
- `0x180035624`
- `0x180038010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18003565c`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18003565c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  __int64 v4; // rbx
  char v6; // bl
  __int64 v7; // [rsp+28h] [rbp-18h] BYREF
  char v8; // [rsp+30h] [rbp-10h]
  __int64 v9; // [rsp+70h] [rbp+30h] BYREF

  v9 = 0;
  v7 = 0;
  v8 = 1;
  v3 = OpenProvisioningPackageForRead(a1, &v7);
  if ( v8 )
  {
    v4 = v7;
    if ( v7 != v9 )
    {
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
      v9 = v4;
    }
  }
  if ( v3 >= 0 )
  {
    v6 = ProvisioningFileManager::TryCreateProvisioningFileManager(&v9, a2);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
    return v6;
  }
  else
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 128LL))(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x180035624  mov     [rsp-18h+arg_0], rbx
0x180035629  mov     [rsp-18h+arg_8], rsi
0x18003562e  push    rbp
0x18003562f  push    rdi
0x180035630  push    r14
0x180035632  mov     rbp, rsp
0x180035635  sub     rsp, 40h
0x180035639  mov     r14, rdx
0x18003563c  mov     [rbp+arg_10], 0
0x180035644  lea     rax, [rbp+arg_10]
0x180035648  mov     [rbp+var_20], rax
0x18003564c  mov     [rbp+var_18], 0
0x180035654  mov     [rbp+var_10], 1
0x180035658  lea     rdx, [rbp+var_18]
0x18003565c  call    cs:__imp_OpenProvisioningPackageForRead
0x180035663  nop     dword ptr [rax+rax+00h]
0x180035668  mov     esi, eax
0x18003566a  cmp     [rbp+var_10], 0
0x18003566e  jz      short loc_180035697
0x180035670  mov     rbx, [rbp+var_18]
0x180035674  mov     rdi, [rbp+var_20]
0x180035678  mov     rcx, [rdi]
0x18003567b  cmp     rbx, rcx
0x18003567e  jz      short loc_180035697
0x180035680  test    rcx, rcx
0x180035683  jz      short loc_180035694
0x180035685  mov     rax, [rcx]
0x180035688  mov     rax, [rax+80h]
0x18003568f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035694  mov     [rdi], rbx
0x180035697  test    esi, esi
0x180035699  jns     short loc_1800356B8
0x18003569b  mov     rcx, [rbp+arg_10]
0x18003569f  test    rcx, rcx
0x1800356a2  jz      short loc_1800356B4
0x1800356a4  mov     rax, [rcx]
0x1800356a7  mov     rax, [rax+80h]
0x1800356ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356b3  nop
0x1800356b4  xor     al, al
0x1800356b6  jmp     short loc_1800356E1
0x1800356b8  mov     rdx, r14
0x1800356bb  lea     rcx, [rbp+arg_10]
0x1800356bf  call    ?TryCreateProvisioningFileManager@ProvisioningFileManager@@SA_N$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@AEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@3@@Z; ProvisioningFileManager::TryCreateProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x1800356c4  mov     bl, al
0x1800356c6  mov     rcx, [rbp+arg_10]
0x1800356ca  test    rcx, rcx
0x1800356cd  jz      short loc_1800356DF
0x1800356cf  mov     rdx, [rcx]
0x1800356d2  mov     rax, [rdx+80h]
0x1800356d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356de  nop
0x1800356df  mov     al, bl
0x1800356e1  mov     rbx, [rsp+40h+arg_0]
0x1800356e6  mov     rsi, [rsp+40h+arg_8]
0x1800356eb  add     rsp, 40h
0x1800356ef  pop     r14
0x1800356f1  pop     rdi
0x1800356f2  pop     rbp
0x1800356f3  retn
```
