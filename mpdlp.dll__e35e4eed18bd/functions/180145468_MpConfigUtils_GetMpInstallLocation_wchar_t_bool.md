# MpConfigUtils::GetMpInstallLocation(wchar_t * *,bool)

- ea: `0x180145468`
- end: `0x180145629`
- name: `?GetMpInstallLocation@MpConfigUtils@@YAJPEAPEA_W_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(MpConfigUtils *__hidden this, wchar_t **, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180145314`

## callees

- `0x18007f51c`
- `0x180089510`
- `0x180104b10`
- `0x18010cb40`
- `0x18010ce3c`
- `0x180145468`
- `0x1801458c0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1801454e9`
- `MpClient!MpFreeMemory` at `0x180145546`
- `MpClient!MpFreeMemory` at `0x1801455c7`
- `MpClient!MpFreeMemory` at `0x1801455f1`
- `MpClient!MpFreeMemory` at `0x1801454e9`
- `MpClient!MpFreeMemory` at `0x180145546`
- `MpClient!MpFreeMemory` at `0x1801455c7`
- `MpClient!MpFreeMemory` at `0x1801455f1`
- `MpClient!MpConfigClose` at `0x1801454b9`
- `MpClient!MpConfigClose` at `0x180145555`
- `MpClient!MpConfigClose` at `0x180145600`
- `MpClient!MpConfigClose` at `0x1801454b9`
- `MpClient!MpConfigClose` at `0x180145555`
- `MpClient!MpConfigClose` at `0x180145600`
- `MpClient!MpConfigOpen` at `0x1801454a4`
- `MpClient!MpConfigOpen` at `0x1801454a4`

## string_xrefs

- `0x1801454ce`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::GetMpInstallLocation(MpConfigUtils *this, wchar_t **a2)
{
  int v3; // eax
  const struct std::nothrow_t *v4; // rdx
  const wchar_t *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  int ValueString; // ebx
  wchar_t **v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  void *v13; // rcx
  wchar_t **v14; // [rsp+20h] [rbp-30h] BYREF
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  void *v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF

  *(_QWORD *)this = 0;
  v15 = 0;
  v3 = MpConfigOpen(L".", &v15);
  v7 = v15;
  ValueString = v3;
  if ( v3 < 0 )
  {
LABEL_2:
    if ( v7 )
      MpConfigClose(v7, v4, v5, v6);
    return (unsigned int)ValueString;
  }
  v14 = 0;
  ValueString = MpConfigGetValueString(v15, L"InstallLocation", &v14);
  if ( ValueString < 0 )
  {
LABEL_6:
    if ( v14 )
      MpFreeMemory(v14);
    v7 = v15;
    goto LABEL_2;
  }
  v10 = v14;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)v14 + v11) );
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_fa2f10c90b2f3ba8b75fecf2c246e53e_Traceguids);
      v10 = v14;
    }
    if ( v10 )
      MpFreeMemory(v10);
    if ( v15 )
      MpConfigClose(v15, v10, v5, v6);
    return 2147942411LL;
  }
  if ( *((_WORD *)v14 + v11 - 1) == 92 )
  {
    *((_WORD *)v14 + v11 - 1) = 0;
    v10 = v14;
  }
  v16 = 0;
  ValueString = CommonUtil::UtilExpandEnvironmentStrings((CommonUtil *)&v16, v10, v5);
  if ( ValueString < 0 )
  {
LABEL_23:
    if ( v16 )
      operator delete(v16, v4);
    goto LABEL_6;
  }
  v17 = 0;
  ValueString = MpAllocSprintfW(&v17, L"%s", v16);
  if ( ValueString < 0 )
  {
    if ( v17 )
      MpFreeMemory(v17);
    goto LABEL_23;
  }
  v12 = v17;
  v13 = v16;
  v17 = 0;
  *(_QWORD *)this = v12;
  if ( v13 )
    operator delete(v13, v4);
  if ( v14 )
    MpFreeMemory(v14);
  if ( v15 )
    MpConfigClose(v15, v4, v5, v6);
  return 0;
}

```

## disassembly

```asm
0x180145468  mov     [rsp-8+arg_8], rbx
0x18014546d  mov     [rsp-8+arg_10], rsi
0x180145472  mov     [rsp-8+arg_18], rdi
0x180145477  push    rbp
0x180145478  mov     rbp, rsp
0x18014547b  sub     rsp, 50h
0x18014547f  mov     rax, cs:__security_cookie
0x180145486  xor     rax, rsp
0x180145489  mov     [rbp+var_10], rax
0x18014548d  xor     esi, esi
0x18014548f  lea     rdx, [rbp+var_28]
0x180145493  mov     [rcx], rsi
0x180145496  mov     rdi, rcx
0x180145499  lea     rcx, asc_18025D638; "."
0x1801454a0  mov     [rbp+var_28], rsi
0x1801454a4  call    cs:__imp_MpConfigOpen
0x1801454aa  mov     rcx, [rbp+var_28]
0x1801454ae  mov     ebx, eax
0x1801454b0  test    eax, eax
0x1801454b2  jns     short loc_1801454C6
0x1801454b4  test    rcx, rcx
0x1801454b7  jz      short loc_1801454BF
0x1801454b9  call    cs:__imp_MpConfigClose
0x1801454bf  mov     eax, ebx
0x1801454c1  jmp     loc_180145608
0x1801454c6  lea     r8, [rbp+var_30]
0x1801454ca  mov     [rbp+var_30], rsi
0x1801454ce  lea     rdx, aInstalllocatio; "InstallLocation"
0x1801454d5  call    MpConfigGetValueString
0x1801454da  mov     ebx, eax
0x1801454dc  test    eax, eax
0x1801454de  jns     short loc_1801454F5
0x1801454e0  mov     rcx, [rbp+var_30]
0x1801454e4  test    rcx, rcx
0x1801454e7  jz      short loc_1801454EF
0x1801454e9  call    cs:__imp_MpFreeMemory
0x1801454ef  mov     rcx, [rbp+var_28]
0x1801454f3  jmp     short loc_1801454B4
0x1801454f5  mov     rdx, [rbp+var_30]
0x1801454f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801454fd  inc     rax
0x180145500  cmp     [rdx+rax*2], si
0x180145504  jnz     short loc_1801454FD
0x180145506  cmp     rax, 1
0x18014550a  jnb     short loc_180145565
0x18014550c  mov     rcx, cs:WPP_GLOBAL_Control
0x180145513  lea     rax, WPP_GLOBAL_Control
0x18014551a  cmp     rcx, rax
0x18014551d  jz      short loc_18014553E
0x18014551f  test    byte ptr [rcx+1Ch], 1
0x180145523  jz      short loc_18014553E
0x180145525  mov     rcx, [rcx+10h]
0x180145529  lea     r8, WPP_fa2f10c90b2f3ba8b75fecf2c246e53e_Traceguids
0x180145530  mov     edx, 14h
0x180145535  call    WPP_SF_
0x18014553a  mov     rdx, [rbp+var_30]
0x18014553e  test    rdx, rdx
0x180145541  jz      short loc_18014554C
0x180145543  mov     rcx, rdx
0x180145546  call    cs:__imp_MpFreeMemory
0x18014554c  mov     rcx, [rbp+var_28]
0x180145550  test    rcx, rcx
0x180145553  jz      short loc_18014555B
0x180145555  call    cs:__imp_MpConfigClose
0x18014555b  mov     eax, 8007000Bh
0x180145560  jmp     loc_180145608
0x180145565  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x18014556b  jnz     short loc_180145576
0x18014556d  mov     [rdx+rax*2-2], si
0x180145572  mov     rdx, [rbp+var_30]; wchar_t **
0x180145576  lea     rcx, [rbp+var_20]; this
0x18014557a  mov     [rbp+var_20], rsi
0x18014557e  call    ?UtilExpandEnvironmentStrings@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::UtilExpandEnvironmentStrings(wchar_t * *,wchar_t const *)
0x180145583  mov     ebx, eax
0x180145585  test    eax, eax
0x180145587  jns     short loc_1801455A0
0x180145589  mov     rcx, [rbp+var_20]; void *
0x18014558d  test    rcx, rcx
0x180145590  jz      loc_1801454E0
0x180145596  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014559b  jmp     loc_1801454E0
0x1801455a0  mov     r8, [rbp+var_20]
0x1801455a4  lea     rdx, aS_2; "%s"
0x1801455ab  lea     rcx, [rbp+var_18]
0x1801455af  mov     [rbp+var_18], rsi
0x1801455b3  call    MpAllocSprintfW
0x1801455b8  mov     ebx, eax
0x1801455ba  test    eax, eax
0x1801455bc  jns     short loc_1801455CF
0x1801455be  mov     rcx, [rbp+var_18]
0x1801455c2  test    rcx, rcx
0x1801455c5  jz      short loc_180145589
0x1801455c7  call    cs:__imp_MpFreeMemory
0x1801455cd  jmp     short loc_180145589
0x1801455cf  mov     rax, [rbp+var_18]
0x1801455d3  mov     rcx, [rbp+var_20]; void *
0x1801455d7  mov     [rbp+var_18], rsi
0x1801455db  mov     [rdi], rax
0x1801455de  test    rcx, rcx
0x1801455e1  jz      short loc_1801455E8
0x1801455e3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801455e8  mov     rcx, [rbp+var_30]
0x1801455ec  test    rcx, rcx
0x1801455ef  jz      short loc_1801455F7
0x1801455f1  call    cs:__imp_MpFreeMemory
0x1801455f7  mov     rcx, [rbp+var_28]
0x1801455fb  test    rcx, rcx
0x1801455fe  jz      short loc_180145606
0x180145600  call    cs:__imp_MpConfigClose
0x180145606  xor     eax, eax
0x180145608  mov     rcx, [rbp+var_10]
0x18014560c  xor     rcx, rsp; StackCookie
0x18014560f  call    __security_check_cookie
0x180145614  mov     rbx, [rsp+50h+arg_8]
0x180145619  mov     rsi, [rsp+50h+arg_10]
0x18014561e  mov     rdi, [rsp+50h+arg_18]
0x180145623  add     rsp, 50h
0x180145627  pop     rbp
0x180145628  retn
```
