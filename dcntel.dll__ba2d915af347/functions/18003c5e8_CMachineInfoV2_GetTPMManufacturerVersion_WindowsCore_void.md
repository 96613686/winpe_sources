# CMachineInfoV2::GetTPMManufacturerVersion_WindowsCore(void)

- ea: `0x18003c5e8`
- end: `0x18003c829`
- name: `?GetTPMManufacturerVersion_WindowsCore@CMachineInfoV2@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003c3c0`

## callees

- `0x180009260`
- `0x1800092e0`
- `0x180009f08`
- `0x180009f14`
- `0x180014f2c`
- `0x1800157b8`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18003c5e8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c63b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c63b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c663`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c6a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c72a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c663`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c6a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c80f`

## string_xrefs

- `0x18003c634`: `TpmCoreProvisioning.dll`
- `0x18003c695`: `Tpm20GetCompleteManufacturerVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMachineInfoV2::GetTPMManufacturerVersion_WindowsCore(__int64 a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  int (__fastcall *v5)(unsigned int *, void *); // r14
  unsigned __int64 v6; // rbx
  void *v7; // rsi
  __int64 v8; // r8
  FARPROC v9; // rax
  int (__fastcall *v10)(unsigned int *, void *); // r14
  char *v11; // r14
  size_t v12; // rbx
  signed int LastError; // eax
  int v15; // edx
  unsigned int v16; // r8d
  const int *v17; // [rsp+28h] [rbp-18h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-10h]
  char v19; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+50h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, L"#", 1u);
  Library = LoadLibraryExW(L"TpmCoreProvisioning.dll", 0, 0x800u);
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TpmGet_IsTpmVersion20");
    v19 = 0;
    if ( !ProcAddress )
      goto LABEL_10;
    if ( ((int (__fastcall *)(char *))ProcAddress)(&v19) < 0 )
      goto LABEL_21;
    if ( v19 )
    {
      v20 = 0;
      v4 = GetProcAddress(hModule, "Tpm20GetCompleteManufacturerVersion");
      v5 = (int (__fastcall *)(unsigned int *, void *))v4;
      if ( v4 && ((unsigned int (__fastcall *)(unsigned int *, _QWORD))v4)(&v20, 0) == -2146893784 )
      {
        v6 = -1;
        v7 = operator new[](saturated_mul(v20, 2u));
        memset_0(v7, 0, 2LL * v20);
        if ( v5(&v20, v7) >= 0 )
        {
          do
            ++v6;
          while ( *((_WORD *)v7 + v6) );
          goto LABEL_14;
        }
        goto LABEL_20;
      }
    }
    else
    {
LABEL_10:
      v20 = 0;
      v9 = GetProcAddress(hModule, "TpmGet_ManufacturerVersion");
      v10 = (int (__fastcall *)(unsigned int *, void *))v9;
      if ( v9 && ((int (__fastcall *)(unsigned int *, _QWORD))v9)(&v20, 0) >= 0 )
      {
        v6 = -1;
        v7 = operator new[](saturated_mul(v20, 2u));
        memset_0(v7, 0, 2LL * v20);
        if ( v10(&v20, v7) >= 0 )
        {
          do
            ++v6;
          while ( *((_WORD *)v7 + v6) );
LABEL_14:
          if ( v6 > *(_QWORD *)(a1 + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              (char **)a1,
              v6,
              v8,
              v7);
          }
          else
          {
            if ( *(_QWORD *)(a1 + 24) <= 7u )
              v11 = (char *)a1;
            else
              v11 = *(char **)a1;
            *(_QWORD *)(a1 + 16) = v6;
            v12 = 2 * v6;
            memmove_0(v11, v7, v12);
            *(_WORD *)&v11[v12] = 0;
          }
        }
LABEL_20:
        operator delete(v7);
      }
    }
  }
LABEL_21:
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v17) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v15, v16);
    JUMPOUT(0x18003C828LL);
  }
  return a1;
}

```

## disassembly

```asm
0x18003c5e8  mov     [rsp-38h+arg_0], rcx
0x18003c5ed  push    rbp
0x18003c5ee  push    rbx
0x18003c5ef  push    rsi
0x18003c5f0  push    rdi
0x18003c5f1  push    r12
0x18003c5f3  push    r14
0x18003c5f5  push    r15
0x18003c5f7  mov     rbp, rsp
0x18003c5fa  sub     rsp, 40h
0x18003c5fe  mov     rdi, rcx
0x18003c601  xor     r15d, r15d
0x18003c604  mov     [rbp+var_20], r15d
0x18003c608  xorps   xmm0, xmm0
0x18003c60b  movups  xmmword ptr [rcx], xmm0
0x18003c60e  mov     [rcx+10h], r15
0x18003c612  mov     [rcx+18h], r15
0x18003c616  lea     ebx, [r15+1]
0x18003c61a  mov     r8d, ebx
0x18003c61d  lea     rdx, asc_1801B4764; "#"
0x18003c624  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003c629  mov     [rbp+var_20], ebx
0x18003c62c  xor     edx, edx; hFile
0x18003c62e  mov     r8d, 800h; dwFlags
0x18003c634  lea     rcx, aTpmcoreprovisi_1; "TpmCoreProvisioning.dll"
0x18003c63b  call    cs:__imp_LoadLibraryExW
0x18003c641  lea     r12, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003c648  mov     [rbp+var_18], r12
0x18003c64c  mov     [rbp+hModule], rax
0x18003c650  test    rax, rax
0x18003c653  jz      loc_18003C7E6
0x18003c659  lea     rdx, aTpmgetIstpmver; "TpmGet_IsTpmVersion20"
0x18003c660  mov     rcx, rax; hModule
0x18003c663  call    cs:__imp_GetProcAddress
0x18003c669  mov     [rbp+arg_8], r15b
0x18003c66d  test    rax, rax
0x18003c670  jz      loc_18003C71B
0x18003c676  lea     rcx, [rbp+arg_8]
0x18003c67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c67f  test    eax, eax
0x18003c681  js      loc_18003C7E6
0x18003c687  cmp     [rbp+arg_8], r15b
0x18003c68b  jz      loc_18003C71B
0x18003c691  mov     [rbp+arg_10], r15d
0x18003c695  lea     rdx, aTpm20getcomple; "Tpm20GetCompleteManufacturerVersion"
0x18003c69c  mov     rcx, [rbp+hModule]; hModule
0x18003c6a0  call    cs:__imp_GetProcAddress
0x18003c6a6  mov     r14, rax
0x18003c6a9  test    rax, rax
0x18003c6ac  jz      loc_18003C7E6
0x18003c6b2  xor     edx, edx
0x18003c6b4  lea     rcx, [rbp+arg_10]
0x18003c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6bd  cmp     eax, 80090028h
0x18003c6c2  jnz     loc_18003C7E6
0x18003c6c8  mov     ecx, [rbp+arg_10]
0x18003c6cb  lea     eax, [rbx+1]
0x18003c6ce  mul     rcx
0x18003c6d1  lea     rbx, [r15-1]
0x18003c6d5  cmovb   rax, rbx
0x18003c6d9  mov     rcx, rax; unsigned __int64
0x18003c6dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c6e1  mov     rsi, rax
0x18003c6e4  mov     r8d, [rbp+arg_10]
0x18003c6e8  add     r8, r8; Size
0x18003c6eb  xor     edx, edx; Val
0x18003c6ed  mov     rcx, rax; void *
0x18003c6f0  call    memset_0
0x18003c6f5  mov     rdx, rsi
0x18003c6f8  lea     rcx, [rbp+arg_10]
0x18003c6fc  mov     rax, r14
0x18003c6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c704  test    eax, eax
0x18003c706  js      loc_18003C7DD
0x18003c70c  inc     rbx
0x18003c70f  cmp     [rsi+rbx*2], r15w
0x18003c714  jnz     short loc_18003C70C
0x18003c716  jmp     loc_18003C79E
0x18003c71b  mov     [rbp+arg_10], r15d
0x18003c71f  lea     rdx, aTpmgetManufact; "TpmGet_ManufacturerVersion"
0x18003c726  mov     rcx, [rbp+hModule]; hModule
0x18003c72a  call    cs:__imp_GetProcAddress
0x18003c730  mov     r14, rax
0x18003c733  test    rax, rax
0x18003c736  jz      loc_18003C7E6
0x18003c73c  xor     edx, edx
0x18003c73e  lea     rcx, [rbp+arg_10]
0x18003c742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c747  test    eax, eax
0x18003c749  js      loc_18003C7E6
0x18003c74f  mov     ecx, [rbp+arg_10]
0x18003c752  mov     eax, 2
0x18003c757  mul     rcx
0x18003c75a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18003c761  cmovb   rax, rbx
0x18003c765  mov     rcx, rax; unsigned __int64
0x18003c768  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c76d  mov     rsi, rax
0x18003c770  mov     r8d, [rbp+arg_10]
0x18003c774  add     r8, r8; Size
0x18003c777  xor     edx, edx; Val
0x18003c779  mov     rcx, rax; void *
0x18003c77c  call    memset_0
0x18003c781  mov     rdx, rsi
0x18003c784  lea     rcx, [rbp+arg_10]
0x18003c788  mov     rax, r14
0x18003c78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c790  test    eax, eax
0x18003c792  js      short loc_18003C7DD
0x18003c794  inc     rbx
0x18003c797  cmp     [rsi+rbx*2], r15w
0x18003c79c  jnz     short loc_18003C794
0x18003c79e  cmp     rbx, [rdi+18h]
0x18003c7a2  ja      short loc_18003C7CF
0x18003c7a4  cmp     qword ptr [rdi+18h], 7
0x18003c7a9  jbe     short loc_18003C7B0
0x18003c7ab  mov     r14, [rdi]
0x18003c7ae  jmp     short loc_18003C7B3
0x18003c7b0  mov     r14, rdi
0x18003c7b3  mov     [rdi+10h], rbx
0x18003c7b7  add     rbx, rbx
0x18003c7ba  mov     r8, rbx; Size
0x18003c7bd  mov     rdx, rsi; Src
0x18003c7c0  mov     rcx, r14; void *
0x18003c7c3  call    memmove_0
0x18003c7c8  mov     [rbx+r14], r15w
0x18003c7cd  jmp     short loc_18003C7DD
0x18003c7cf  mov     r9, rsi
0x18003c7d2  mov     rdx, rbx
0x18003c7d5  mov     rcx, rdi
0x18003c7d8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003c7dd  mov     rcx, rsi; Block
0x18003c7e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c7e5  nop
0x18003c7e6  mov     [rbp+var_18], r12
0x18003c7ea  cmp     [rbp+hModule], r15
0x18003c7ee  jz      short loc_18003C7FD
0x18003c7f0  lea     rcx, [rbp+var_18]
0x18003c7f4  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003c7f9  test    al, al
0x18003c7fb  jz      short loc_18003C80F
0x18003c7fd  mov     rax, rdi
0x18003c800  add     rsp, 40h
0x18003c804  pop     r15
0x18003c806  pop     r14
0x18003c808  pop     r12
0x18003c80a  pop     rdi
0x18003c80b  pop     rsi
0x18003c80c  pop     rbx
0x18003c80d  pop     rbp
0x18003c80e  retn
0x18003c80f  call    cs:__imp_GetLastError
0x18003c815  test    eax, eax
0x18003c817  jle     short loc_18003C821
0x18003c819  movzx   eax, ax
0x18003c81c  or      eax, 80070000h
0x18003c821  mov     ecx, eax; this
0x18003c823  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
