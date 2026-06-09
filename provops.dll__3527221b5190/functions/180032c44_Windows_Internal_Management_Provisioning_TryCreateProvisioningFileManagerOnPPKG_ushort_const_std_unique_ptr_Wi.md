# Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &)

- ea: `0x180032c44`
- end: `0x180032d0e`
- name: `?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002edd0`

## callees

- `0x1800329c8`
- `0x180032c44`
- `0x180037010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180032c7c`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180032c7c`

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
0x180032c44  mov     [rsp-18h+arg_0], rbx
0x180032c49  mov     [rsp-18h+arg_8], rsi
0x180032c4e  push    rbp
0x180032c4f  push    rdi
0x180032c50  push    r14
0x180032c52  mov     rbp, rsp
0x180032c55  sub     rsp, 40h
0x180032c59  mov     r14, rdx
0x180032c5c  mov     [rbp+arg_10], 0
0x180032c64  lea     rax, [rbp+arg_10]
0x180032c68  mov     [rbp+var_20], rax
0x180032c6c  mov     [rbp+var_18], 0
0x180032c74  mov     [rbp+var_10], 1
0x180032c78  lea     rdx, [rbp+var_18]
0x180032c7c  call    cs:__imp_OpenProvisioningPackageForRead
0x180032c82  mov     esi, eax
0x180032c84  cmp     [rbp+var_10], 0
0x180032c88  jz      short loc_180032CB1
0x180032c8a  mov     rbx, [rbp+var_18]
0x180032c8e  mov     rdi, [rbp+var_20]
0x180032c92  mov     rcx, [rdi]
0x180032c95  cmp     rbx, rcx
0x180032c98  jz      short loc_180032CB1
0x180032c9a  test    rcx, rcx
0x180032c9d  jz      short loc_180032CAE
0x180032c9f  mov     rax, [rcx]
0x180032ca2  mov     rax, [rax+80h]
0x180032ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cae  mov     [rdi], rbx
0x180032cb1  test    esi, esi
0x180032cb3  jns     short loc_180032CD2
0x180032cb5  mov     rcx, [rbp+arg_10]
0x180032cb9  test    rcx, rcx
0x180032cbc  jz      short loc_180032CCE
0x180032cbe  mov     rax, [rcx]
0x180032cc1  mov     rax, [rax+80h]
0x180032cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ccd  nop
0x180032cce  xor     al, al
0x180032cd0  jmp     short loc_180032CFB
0x180032cd2  mov     rdx, r14
0x180032cd5  lea     rcx, [rbp+arg_10]
0x180032cd9  call    ?TryCreateProvisioningFileManager@ProvisioningFileManager@@SA_N$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@AEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@3@@Z; ProvisioningFileManager::TryCreateProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x180032cde  mov     bl, al
0x180032ce0  mov     rcx, [rbp+arg_10]
0x180032ce4  test    rcx, rcx
0x180032ce7  jz      short loc_180032CF9
0x180032ce9  mov     rdx, [rcx]
0x180032cec  mov     rax, [rdx+80h]
0x180032cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cf8  nop
0x180032cf9  mov     al, bl
0x180032cfb  mov     rbx, [rsp+40h+arg_0]
0x180032d00  mov     rsi, [rsp+40h+arg_8]
0x180032d05  add     rsp, 40h
0x180032d09  pop     r14
0x180032d0b  pop     rdi
0x180032d0c  pop     rbp
0x180032d0d  retn
```
