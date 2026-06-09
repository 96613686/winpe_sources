# sqlencrypt::SqlSecurityUtility::LoadKeystoreProviders(ushort const *)

- ea: `0x10047e924`
- end: `0x10047ead7`
- name: `?LoadKeystoreProviders@SqlSecurityUtility@sqlencrypt@@SAHPEBG@Z`
- size: `435`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100530c14`

## callees

- `0x10047be6c`
- `0x10047c674`
- `0x10047da0c`
- `0x10047e7bc`
- `0x10047e84c`
- `0x10047e924`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x10047e970`
- `KERNEL32!LoadLibraryW` at `0x10047e970`
- `KERNEL32!GetProcAddress` at `0x10047e98c`
- `KERNEL32!GetProcAddress` at `0x10047e9bd`
- `KERNEL32!GetProcAddress` at `0x10047e98c`
- `KERNEL32!GetProcAddress` at `0x10047e9bd`

## pseudocode

```c
_BOOL8 __fastcall sqlencrypt::SqlSecurityUtility::LoadKeystoreProviders(LPCWSTR lpLibFileName)
{
  BOOL v1; // ebx
  HMODULE LibraryW; // rax
  HMODULE v4; // rbp
  FARPROC ProcAddress; // rax
  struct CEKeystoreProvider2 **v6; // rsi
  struct CEKeystoreProvider2 *i; // rax
  FARPROC v8; // rax
  _QWORD **v9; // r14
  _QWORD *v10; // r15
  char v11; // bl
  __int64 v12; // rdi
  int ConvertedDescs; // eax
  struct sqlencrypt::ProviderList *v14; // rax
  char v16; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  if ( (bidGblFlags & 2) != 0 && off_1005E6F60[0] )
    bidTraceW(0, 1157120, off_1005E6F60[0], *lpLibFileName);
  LibraryW = LoadLibraryW(lpLibFileName);
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CEKeystoreProvider2");
    v6 = (struct CEKeystoreProvider2 **)ProcAddress;
    if ( ProcAddress )
    {
      for ( i = *(struct CEKeystoreProvider2 **)ProcAddress; ; i = *v6 )
      {
        ++v6;
        if ( !i )
          break;
        sqlencrypt::SqlSecurityUtility::LoadKeystoreProvider(i);
      }
    }
    v8 = GetProcAddress(v4, "CEKeystoreProvider");
    v9 = (_QWORD **)v8;
    if ( v8 )
    {
      v10 = *(_QWORD **)v8;
      v9 = (_QWORD **)((char *)v8 + 8);
      if ( *(_QWORD *)v8 )
      {
        v11 = v17;
        do
        {
          v12 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 72);
          v17 = v12;
          ConvertedDescs = sqlencrypt::SqlSecurityUtility::GetConvertedDescs();
          std::_Tree<std::_Tset_traits<CEKeystoreProvider2 const *,std::less<CEKeystoreProvider2 const *>,std::allocator<CEKeystoreProvider2 const *>,0>>::_Insert_nohint<CEKeystoreProvider2 const * const &,std::_Nil>(
            ConvertedDescs,
            (unsigned int)&v16,
            0,
            (unsigned int)&v17,
            v11);
          *(_QWORD *)v12 = *v10;
          *(_QWORD *)(v12 + 8) = v10[1];
          *(_QWORD *)(v12 + 16) = v10[2];
          *(_QWORD *)(v12 + 24) = v10[3];
          *(_QWORD *)(v12 + 32) = v10[4];
          *(_QWORD *)(v12 + 64) = v10[6];
          sqlencrypt::SqlSecurityUtility::LoadKeystoreProvider((struct CEKeystoreProvider2 *)v12);
          v10 = *v9++;
        }
        while ( v10 );
      }
    }
    v17 = (__int64)v4;
    v14 = sqlencrypt::ProviderList::Instance();
    std::vector<HINSTANCE__ *>::emplace_back<HINSTANCE__ * const &>(v14, &v17);
    v1 = v6 != 0 || v9 != 0;
  }
  if ( (bidGblFlags & 2) != 0 && off_1005E6F68[0] )
    bidTraceW(0, 1246208, off_1005E6F68[0], v1);
  return v1;
}

```

## disassembly

```asm
0x10047e924  mov     [rsp+arg_0], rbx
0x10047e929  mov     [rsp+arg_10], rbp
0x10047e92e  mov     [rsp+arg_18], rsi
0x10047e933  push    rdi
0x10047e934  push    r14
0x10047e936  push    r15
0x10047e938  sub     rsp, 40h
0x10047e93c  xor     ebx, ebx
0x10047e93e  mov     rdi, rcx
0x10047e941  test    byte ptr cs:_bidGblFlags, 2
0x10047e948  jz      short loc_10047E96D
0x10047e94a  mov     rax, cs:off_1005E6F60; "<sqlencrypt::SqlSecurityUtility::LoadKe"...
0x10047e951  test    rax, rax
0x10047e954  jz      short loc_10047E96D
0x10047e956  movzx   r9d, word ptr [rcx]
0x10047e95a  mov     edx, 11A800h
0x10047e95f  mov     r8, cs:off_1005E6F60; "<sqlencrypt::SqlSecurityUtility::LoadKe"...
0x10047e966  xor     ecx, ecx
0x10047e968  call    _bidTraceW
0x10047e96d  mov     rcx, rdi; lpLibFileName
0x10047e970  call    cs:__imp_LoadLibraryW
0x10047e976  mov     rbp, rax
0x10047e979  test    rax, rax
0x10047e97c  jz      loc_10047EA91
0x10047e982  lea     rdx, aCekeystoreprov; "CEKeystoreProvider2"
0x10047e989  mov     rcx, rax; hModule
0x10047e98c  call    cs:__imp_GetProcAddress
0x10047e992  mov     rsi, rax
0x10047e995  test    rax, rax
0x10047e998  jz      short loc_10047E9B3
0x10047e99a  mov     rax, [rax]
0x10047e99d  jmp     short loc_10047E9AA
0x10047e99f  mov     rcx, rax; struct CEKeystoreProvider2 *
0x10047e9a2  call    ?LoadKeystoreProvider@SqlSecurityUtility@sqlencrypt@@CAHPEAUCEKeystoreProvider2@@@Z; sqlencrypt::SqlSecurityUtility::LoadKeystoreProvider(CEKeystoreProvider2 *)
0x10047e9a7  mov     rax, [rsi]
0x10047e9aa  add     rsi, 8
0x10047e9ae  test    rax, rax
0x10047e9b1  jnz     short loc_10047E99F
0x10047e9b3  lea     rdx, aCekeystoreprov_0; "CEKeystoreProvider"
0x10047e9ba  mov     rcx, rbp; hModule
0x10047e9bd  call    cs:__imp_GetProcAddress
0x10047e9c3  mov     r14, rax
0x10047e9c6  test    rax, rax
0x10047e9c9  jz      loc_10047EA68
0x10047e9cf  mov     r15, [rax]
0x10047e9d2  add     r14, 8
0x10047e9d6  test    r15, r15
0x10047e9d9  jz      loc_10047EA68
0x10047e9df  mov     bl, byte ptr [rsp+58h+arg_8]
0x10047e9e3  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10047e9ea  mov     edx, 48h ; 'H'
0x10047e9ef  mov     rax, [rcx]
0x10047e9f2  mov     rax, [rax+58h]
0x10047e9f6  call    cs:__guard_dispatch_icall_fptr
0x10047e9fc  mov     rdi, rax
0x10047e9ff  mov     [rsp+58h+arg_8], rax
0x10047ea04  call    ?GetConvertedDescs@SqlSecurityUtility@sqlencrypt@@CAAEAV?$set@PEBUCEKeystoreProvider2@@U?$less@PEBUCEKeystoreProvider2@@@std@@V?$allocator@PEBUCEKeystoreProvider2@@@3@@std@@XZ; sqlencrypt::SqlSecurityUtility::GetConvertedDescs(void)
0x10047ea09  lea     r9, [rsp+58h+arg_8]
0x10047ea0e  mov     [rsp+58h+var_38], bl
0x10047ea12  xor     r8d, r8d
0x10047ea15  lea     rdx, [rsp+58h+var_28]
0x10047ea1a  mov     rcx, rax
0x10047ea1d  call    ??$_Insert_nohint@AEBQEBUCEKeystoreProvider2@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEBUCEKeystoreProvider2@@U?$less@PEBUCEKeystoreProvider2@@@std@@V?$allocator@PEBUCEKeystoreProvider2@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBUCEKeystoreProvider2@@@std@@@std@@@std@@_N@1@_NAEBQEBUCEKeystoreProvider2@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<CEKeystoreProvider2 const *,std::less<CEKeystoreProvider2 const *>,std::allocator<CEKeystoreProvider2 const *>,0>>::_Insert_nohint<CEKeystoreProvider2 const * const &,std::_Nil>(bool,CEKeystoreProvider2 const * const &,std::_Nil)
0x10047ea22  mov     rax, [r15]
0x10047ea25  mov     rcx, rdi; struct CEKeystoreProvider2 *
0x10047ea28  mov     [rdi], rax
0x10047ea2b  mov     rax, [r15+8]
0x10047ea2f  mov     [rdi+8], rax
0x10047ea33  mov     rax, [r15+10h]
0x10047ea37  mov     [rdi+10h], rax
0x10047ea3b  mov     rax, [r15+18h]
0x10047ea3f  mov     [rdi+18h], rax
0x10047ea43  mov     rax, [r15+20h]
0x10047ea47  mov     [rdi+20h], rax
0x10047ea4b  mov     rax, [r15+30h]
0x10047ea4f  mov     [rdi+40h], rax
0x10047ea53  call    ?LoadKeystoreProvider@SqlSecurityUtility@sqlencrypt@@CAHPEAUCEKeystoreProvider2@@@Z; sqlencrypt::SqlSecurityUtility::LoadKeystoreProvider(CEKeystoreProvider2 *)
0x10047ea58  mov     r15, [r14]
0x10047ea5b  add     r14, 8
0x10047ea5f  test    r15, r15
0x10047ea62  jnz     loc_10047E9E3
0x10047ea68  mov     [rsp+58h+arg_8], rbp
0x10047ea6d  call    ?Instance@ProviderList@sqlencrypt@@SAPEAV12@XZ; sqlencrypt::ProviderList::Instance(void)
0x10047ea72  lea     rdx, [rsp+58h+arg_8]
0x10047ea77  mov     rcx, rax
0x10047ea7a  call    ??$emplace_back@AEBQEAUHINSTANCE__@@@?$vector@PEAUHINSTANCE__@@V?$allocator@PEAUHINSTANCE__@@@std@@@std@@QEAA?A_TAEBQEAUHINSTANCE__@@@Z
0x10047ea7f  xor     ebx, ebx
0x10047ea81  test    r14, r14
0x10047ea84  setnz   bl
0x10047ea87  xor     eax, eax
0x10047ea89  test    rsi, rsi
0x10047ea8c  setnz   al
0x10047ea8f  or      ebx, eax
0x10047ea91  test    byte ptr cs:_bidGblFlags, 2
0x10047ea98  jz      short loc_10047EABC
0x10047ea9a  mov     rcx, cs:off_1005E6F68; "<sqlencrypt::SqlSecurityUtility::LoadKe"...
0x10047eaa1  test    rcx, rcx
0x10047eaa4  jz      short loc_10047EABC
0x10047eaa6  mov     r8, cs:off_1005E6F68; "<sqlencrypt::SqlSecurityUtility::LoadKe"...
0x10047eaad  mov     r9d, ebx
0x10047eab0  mov     edx, 130400h
0x10047eab5  xor     ecx, ecx
0x10047eab7  call    _bidTraceW
0x10047eabc  mov     rbp, [rsp+58h+arg_10]
0x10047eac1  mov     eax, ebx
0x10047eac3  mov     rbx, [rsp+58h+arg_0]
0x10047eac8  mov     rsi, [rsp+58h+arg_18]
0x10047eacd  add     rsp, 40h
0x10047ead1  pop     r15
0x10047ead3  pop     r14
0x10047ead5  pop     rdi
0x10047ead6  retn
```
