# Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &)

- ea: `0x1800433e4`
- end: `0x1800434ae`
- name: `?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z`
- size: `202`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180042020`

## callees

- `0x180043168`
- `0x1800433e4`
- `0x180047010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18004341c`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18004341c`

## pseudocode

```c
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
0x1800433e4  mov     [rsp-18h+arg_0], rbx
0x1800433e9  mov     [rsp-18h+arg_8], rsi
0x1800433ee  push    rbp
0x1800433ef  push    rdi
0x1800433f0  push    r14
0x1800433f2  mov     rbp, rsp
0x1800433f5  sub     rsp, 40h
0x1800433f9  mov     r14, rdx
0x1800433fc  mov     [rbp+arg_10], 0
0x180043404  lea     rax, [rbp+arg_10]
0x180043408  mov     [rbp+var_20], rax
0x18004340c  mov     [rbp+var_18], 0
0x180043414  mov     [rbp+var_10], 1
0x180043418  lea     rdx, [rbp+var_18]
0x18004341c  call    cs:__imp_OpenProvisioningPackageForRead
0x180043422  mov     esi, eax
0x180043424  cmp     [rbp+var_10], 0
0x180043428  jz      short loc_180043451
0x18004342a  mov     rbx, [rbp+var_18]
0x18004342e  mov     rdi, [rbp+var_20]
0x180043432  mov     rcx, [rdi]
0x180043435  cmp     rbx, rcx
0x180043438  jz      short loc_180043451
0x18004343a  test    rcx, rcx
0x18004343d  jz      short loc_18004344E
0x18004343f  mov     rax, [rcx]
0x180043442  mov     rax, [rax+80h]
0x180043449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004344e  mov     [rdi], rbx
0x180043451  test    esi, esi
0x180043453  jns     short loc_180043472
0x180043455  mov     rcx, [rbp+arg_10]
0x180043459  test    rcx, rcx
0x18004345c  jz      short loc_18004346E
0x18004345e  mov     rax, [rcx]
0x180043461  mov     rax, [rax+80h]
0x180043468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004346d  nop
0x18004346e  xor     al, al
0x180043470  jmp     short loc_18004349B
0x180043472  mov     rdx, r14
0x180043475  lea     rcx, [rbp+arg_10]
0x180043479  call    ?TryCreateProvisioningFileManager@ProvisioningFileManager@@SA_N$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@AEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@3@@Z; ProvisioningFileManager::TryCreateProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x18004347e  mov     bl, al
0x180043480  mov     rcx, [rbp+arg_10]
0x180043484  test    rcx, rcx
0x180043487  jz      short loc_180043499
0x180043489  mov     rdx, [rcx]
0x18004348c  mov     rax, [rdx+80h]
0x180043493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043498  nop
0x180043499  mov     al, bl
0x18004349b  mov     rbx, [rsp+40h+arg_0]
0x1800434a0  mov     rsi, [rsp+40h+arg_8]
0x1800434a5  add     rsp, 40h
0x1800434a9  pop     r14
0x1800434ab  pop     rdi
0x1800434ac  pop     rbp
0x1800434ad  retn
```
