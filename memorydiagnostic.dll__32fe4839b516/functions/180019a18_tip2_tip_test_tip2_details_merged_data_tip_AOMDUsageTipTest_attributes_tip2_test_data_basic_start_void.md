# tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x180019a18`
- end: `0x180019c5a`
- name: `?start@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `578`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180015cd0`

## callees

- `0x1800026b0`
- `0x180006d20`
- `0x180007bf0`
- `0x180019660`
- `0x180019a18`
- `0x18001a4cc`
- `0x18001a540`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019bc4`
- `KERNEL32!GetLastError` at `0x180019bc4`
- `KERNEL32!LeaveCriticalSection` at `0x180019c20`
- `KERNEL32!LeaveCriticalSection` at `0x180019c20`
- `KERNEL32!EnterCriticalSection` at `0x180019b17`
- `KERNEL32!EnterCriticalSection` at `0x180019b17`
- `KERNEL32!SetLastError` at `0x180019bdc`
- `KERNEL32!SetLastError` at `0x180019bdc`
- `ole32!CoTaskMemFree` at `0x180019a8a`
- `ole32!CoTaskMemFree` at `0x180019acf`
- `ole32!CoTaskMemFree` at `0x180019afe`
- `ole32!CoTaskMemFree` at `0x180019c0c`
- `ole32!CoTaskMemFree` at `0x180019a8a`
- `ole32!CoTaskMemFree` at `0x180019acf`
- `ole32!CoTaskMemFree` at `0x180019afe`
- `ole32!CoTaskMemFree` at `0x180019c0c`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(
        volatile signed __int32 **a1,
        _OWORD *a2)
{
  volatile signed __int32 *v2; // rbx
  volatile signed __int32 **v5; // rax
  volatile signed __int32 *v6; // rdx
  volatile signed __int32 *v7; // rbx
  void *v8; // rbx
  volatile signed __int32 *v9; // rdi
  int v10; // edx
  int v11; // r8d
  bool v12; // zf
  char v13; // al
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r12
  __int64 v17; // r13
  DWORD LastError; // ebx
  void *v19; // rcx
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v22; // [rsp+40h] [rbp-C0h] BYREF
  char v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+49h] [rbp-B7h] BYREF
  char v25; // [rsp+4Dh] [rbp-B3h]
  char v26; // [rsp+4Eh] [rbp-B2h] BYREF
  char v27; // [rsp+849h] [rbp+749h] BYREF
  int *v28; // [rsp+850h] [rbp+750h]
  char *v29; // [rsp+858h] [rbp+758h]
  char *v30; // [rsp+860h] [rbp+760h]

  v2 = *a1;
  if ( *a1 && (*((_QWORD *)v2 + 31) || (v2[18] & 0x100) != 0) )
  {
    *a1 = 0;
    if ( !_InterlockedDecrement(v2 + 84) )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v2);
      CoTaskMemFree((LPVOID)v2);
    }
  }
  if ( !*a1 )
  {
    v5 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(&pv);
    v6 = *v5;
    *v5 = 0;
    v7 = *a1;
    *a1 = v6;
    if ( v7 && _InterlockedExchangeAdd(v7 + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v7);
      CoTaskMemFree((LPVOID)v7);
    }
    v8 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v8);
      CoTaskMemFree(v8);
    }
  }
  v9 = *a1;
  EnterCriticalSection((LPCRITICAL_SECTION)v9 + 5);
  v12 = (v9[18] & 0x800) == 0;
  v28 = &v24;
  v30 = &v27;
  v29 = &v26;
  v22 = 0;
  v23 = 0;
  v24 = -2143256512;
  v25 = 0;
  if ( v12 || (v13 = 1, (v9[7] & 0x8000) != 0) )
    v13 = 0;
  if ( v13 )
    v14 = tip2::details::shared_data<0,0,1>::serialize_data(v9 + 2, &v22, 1);
  else
    v14 = 0;
  LOBYTE(v11) = *((_BYTE *)v9 + 40);
  v15 = TestCreate(*((_DWORD *)v9 + 6), v10, v11, *((_DWORD *)v9 + 7), v14, (__int64)(v9 + 38));
  v16 = *((_QWORD *)v9 + 31);
  v17 = v15;
  if ( v16 )
  {
    LastError = GetLastError();
    TestClose(v16);
    SetLastError(LastError);
  }
  v19 = v22;
  *((_QWORD *)v9 + 31) = v17;
  *((_DWORD *)v9 + 48) = 1;
  *a2 = *(_OWORD *)(v9 + 38);
  if ( v19 )
    CoTaskMemFree(v19);
  if ( v9 != (volatile signed __int32 *)-200LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)v9 + 5);
  return a2;
}

```

## disassembly

```asm
0x180019a18  mov     [rsp-8+arg_10], rbx
0x180019a1d  push    rbp
0x180019a1e  push    rsi
0x180019a1f  push    rdi
0x180019a20  push    r12
0x180019a22  push    r13
0x180019a24  push    r14
0x180019a26  push    r15
0x180019a28  lea     rbp, [rsp-780h]
0x180019a30  sub     rsp, 880h
0x180019a37  mov     rax, cs:__security_cookie
0x180019a3e  xor     rax, rsp
0x180019a41  mov     [rbp+7B0h+var_40], rax
0x180019a48  mov     rbx, [rcx]
0x180019a4b  or      esi, 0FFFFFFFFh
0x180019a4e  xor     r12d, r12d
0x180019a51  mov     r15, rdx
0x180019a54  mov     rdi, rcx
0x180019a57  test    rbx, rbx
0x180019a5a  jz      short loc_180019A96
0x180019a5c  cmp     [rbx+0F8h], r12
0x180019a63  jnz     short loc_180019A6E
0x180019a65  test    dword ptr [rbx+48h], 100h
0x180019a6c  jz      short loc_180019A96
0x180019a6e  mov     [rcx], r12
0x180019a71  mov     eax, esi
0x180019a73  lock xadd [rbx+150h], eax
0x180019a7b  add     eax, esi
0x180019a7d  jnz     short loc_180019A96
0x180019a7f  mov     rcx, rbx
0x180019a82  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180019a87  mov     rcx, rbx; pv
0x180019a8a  call    cs:__imp_CoTaskMemFree
0x180019a91  nop     dword ptr [rax+rax+00h]
0x180019a96  cmp     [rdi], r12
0x180019a99  jnz     short loc_180019B0A
0x180019a9b  lea     rcx, [rsp+8B0h+pv]
0x180019aa0  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(void)
0x180019aa5  mov     rdx, [rax]
0x180019aa8  mov     [rax], r12
0x180019aab  mov     rbx, [rdi]
0x180019aae  mov     [rdi], rdx
0x180019ab1  test    rbx, rbx
0x180019ab4  jz      short loc_180019ADB
0x180019ab6  mov     eax, esi
0x180019ab8  lock xadd [rbx+150h], eax
0x180019ac0  add     eax, esi
0x180019ac2  jnz     short loc_180019ADB
0x180019ac4  mov     rcx, rbx
0x180019ac7  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180019acc  mov     rcx, rbx; pv
0x180019acf  call    cs:__imp_CoTaskMemFree
0x180019ad6  nop     dword ptr [rax+rax+00h]
0x180019adb  mov     rbx, [rsp+8B0h+pv]
0x180019ae0  test    rbx, rbx
0x180019ae3  jz      short loc_180019B0A
0x180019ae5  mov     eax, esi
0x180019ae7  lock xadd [rbx+150h], eax
0x180019aef  add     eax, esi
0x180019af1  jnz     short loc_180019B0A
0x180019af3  mov     rcx, rbx
0x180019af6  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180019afb  mov     rcx, rbx; pv
0x180019afe  call    cs:__imp_CoTaskMemFree
0x180019b05  nop     dword ptr [rax+rax+00h]
0x180019b0a  mov     rdi, [rdi]
0x180019b0d  lea     rsi, [rdi+0C8h]
0x180019b14  mov     rcx, rsi; lpCriticalSection
0x180019b17  call    cs:__imp_EnterCriticalSection
0x180019b1e  nop     dword ptr [rax+rax+00h]
0x180019b23  test    dword ptr [rdi+48h], 800h
0x180019b2a  lea     rax, [rsp+8B0h+var_867]
0x180019b2f  mov     [rbp+7B0h+var_60], rax
0x180019b36  lea     rax, [rbp+7B0h+var_67]
0x180019b3d  mov     [rbp+7B0h+var_50], rax
0x180019b44  lea     rax, [rsp+8B0h+var_862]
0x180019b49  mov     [rbp+7B0h+var_58], rax
0x180019b50  mov     [rsp+8B0h+var_870], r12
0x180019b55  mov     [rsp+8B0h+var_868], r12b
0x180019b5a  mov     [rsp+8B0h+var_867], 80408040h
0x180019b62  mov     [rsp+8B0h+var_863], r12b
0x180019b67  jz      short loc_180019B74
0x180019b69  test    dword ptr [rdi+1Ch], 8000h
0x180019b70  mov     al, 1
0x180019b72  jz      short loc_180019B77
0x180019b74  mov     al, r12b
0x180019b77  lea     r14, [rdi+98h]
0x180019b7e  test    al, al
0x180019b80  jz      short loc_180019B98
0x180019b82  mov     r8d, 1
0x180019b88  lea     rdx, [rsp+8B0h+var_870]
0x180019b8d  lea     rcx, [rdi+8]
0x180019b91  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180019b96  jmp     short loc_180019B9B
0x180019b98  mov     rax, r12
0x180019b9b  mov     r9d, [rdi+1Ch]
0x180019b9f  mov     r8b, [rdi+28h]
0x180019ba3  mov     ecx, [rdi+18h]
0x180019ba6  mov     [rsp+8B0h+var_888], r14
0x180019bab  mov     [rsp+8B0h+var_890], rax
0x180019bb0  call    TestCreate
0x180019bb5  mov     r12, [rdi+0F8h]
0x180019bbc  mov     r13, rax
0x180019bbf  test    r12, r12
0x180019bc2  jz      short loc_180019BE8
0x180019bc4  call    cs:__imp_GetLastError
0x180019bcb  nop     dword ptr [rax+rax+00h]
0x180019bd0  mov     rcx, r12
0x180019bd3  mov     ebx, eax
0x180019bd5  call    TestClose
0x180019bda  mov     ecx, ebx; dwErrCode
0x180019bdc  call    cs:__imp_SetLastError
0x180019be3  nop     dword ptr [rax+rax+00h]
0x180019be8  mov     rcx, [rsp+8B0h+var_870]; pv
0x180019bed  mov     [rdi+0F8h], r13
0x180019bf4  mov     dword ptr [rdi+0C0h], 1
0x180019bfe  movups  xmm0, xmmword ptr [r14]
0x180019c02  movdqu  xmmword ptr [r15], xmm0
0x180019c07  test    rcx, rcx
0x180019c0a  jz      short loc_180019C18
0x180019c0c  call    cs:__imp_CoTaskMemFree
0x180019c13  nop     dword ptr [rax+rax+00h]
0x180019c18  test    rsi, rsi
0x180019c1b  jz      short loc_180019C2C
0x180019c1d  mov     rcx, rsi; lpCriticalSection
0x180019c20  call    cs:__imp_LeaveCriticalSection
0x180019c27  nop     dword ptr [rax+rax+00h]
0x180019c2c  mov     rax, r15
0x180019c2f  mov     rcx, [rbp+7B0h+var_40]
0x180019c36  xor     rcx, rsp; StackCookie
0x180019c39  call    __security_check_cookie
0x180019c3e  mov     rbx, [rsp+8B0h+arg_10]
0x180019c46  add     rsp, 880h
0x180019c4d  pop     r15
0x180019c4f  pop     r14
0x180019c51  pop     r13
0x180019c53  pop     r12
0x180019c55  pop     rdi
0x180019c56  pop     rsi
0x180019c57  pop     rbp
0x180019c58  retn
```
