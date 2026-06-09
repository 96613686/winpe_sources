# tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>>(void)

- ea: `0x180006a0c`
- end: `0x180006bbe`
- name: `??$start@V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@0@XZ`
- size: `434`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180015cd0`

## callees

- `0x1800026b0`
- `0x180006a0c`
- `0x180006bc4`
- `0x180010ba8`
- `0x180019820`
- `0x18001a4cc`
- `0x18001a540`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006b30`
- `KERNEL32!GetLastError` at `0x180006b30`
- `KERNEL32!LeaveCriticalSection` at `0x180006b83`
- `KERNEL32!LeaveCriticalSection` at `0x180006b83`
- `KERNEL32!EnterCriticalSection` at `0x180006a82`
- `KERNEL32!EnterCriticalSection` at `0x180006a82`
- `KERNEL32!SetLastError` at `0x180006b48`
- `KERNEL32!SetLastError` at `0x180006b48`
- `ole32!CoTaskMemFree` at `0x180006b6f`
- `ole32!CoTaskMemFree` at `0x180006b6f`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  int v7; // edx
  int v8; // r8d
  bool v9; // zf
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // r12
  DWORD LastError; // ebx
  void *v16; // rcx
  LPVOID v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+48h] [rbp-B8h]
  int v21; // [rsp+49h] [rbp-B7h] BYREF
  char v22; // [rsp+4Dh] [rbp-B3h]
  char v23; // [rsp+4Eh] [rbp-B2h] BYREF
  char v24; // [rsp+849h] [rbp+749h] BYREF
  int *v25; // [rsp+850h] [rbp+750h]
  char *v26; // [rsp+858h] [rbp+758h]
  char *v27; // [rsp+860h] [rbp+760h]

  *a1 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(v18);
  v3 = *v2;
  *v2 = 0;
  v4 = *a1;
  *a1 = v3;
  if ( v4 )
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v4);
  if ( v18[0] )
    tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(v18[0]);
  v5 = *a1;
  v6 = *a1 + 5;
  EnterCriticalSection(v6);
  pv = 0;
  v9 = (v5[1].SpinCount & 0x800) == 0;
  v25 = &v21;
  v27 = &v24;
  v26 = &v23;
  v20 = 0;
  v21 = -2143256512;
  v22 = 0;
  if ( !v9 && (HIDWORD(v5->LockSemaphore) & 0x8000) == 0 )
    v11 = tip2::details::shared_data<0,0,0>::serialize_data(&v5->LockCount, &pv, 1);
  else
    v11 = 0;
  LOBYTE(v8) = v5[1].DebugInfo;
  v12 = TestCreate(v5->LockSemaphore, v7, v8, HIDWORD(v5->LockSemaphore), v11, (__int64)&v5[3].SpinCount);
  v13 = *(_QWORD *)&v5[6].LockCount;
  v14 = v12;
  if ( v13 )
  {
    LastError = GetLastError();
    TestClose(v13);
    SetLastError(LastError);
  }
  v16 = pv;
  *(_QWORD *)&v5[6].LockCount = v14;
  LODWORD(v5[4].SpinCount) = 1;
  if ( v16 )
    CoTaskMemFree(v16);
  if ( v6 )
    LeaveCriticalSection(v6);
  return a1;
}

```

## disassembly

```asm
0x180006a0c  mov     [rsp-8+arg_8], rbx
0x180006a11  mov     [rsp-8+arg_10], rsi
0x180006a16  push    rbp
0x180006a17  push    rdi
0x180006a18  push    r12
0x180006a1a  push    r14
0x180006a1c  push    r15
0x180006a1e  lea     rbp, [rsp-780h]
0x180006a26  sub     rsp, 880h
0x180006a2d  mov     rax, cs:__security_cookie
0x180006a34  xor     rax, rsp
0x180006a37  mov     [rbp+7A0h+var_30], rax
0x180006a3e  and     qword ptr [rcx], 0
0x180006a42  mov     rsi, rcx
0x180006a45  lea     rcx, [rsp+8A0h+var_870]
0x180006a4a  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(void)
0x180006a4f  mov     rdx, [rax]
0x180006a52  and     qword ptr [rax], 0
0x180006a56  mov     rcx, [rsi]; pv
0x180006a59  mov     [rsi], rdx
0x180006a5c  test    rcx, rcx
0x180006a5f  jz      short loc_180006A66
0x180006a61  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180006a66  mov     rcx, [rsp+8A0h+var_870]; pv
0x180006a6b  test    rcx, rcx
0x180006a6e  jz      short loc_180006A75
0x180006a70  call    ?Release@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::Release(void)
0x180006a75  mov     rdi, [rsi]
0x180006a78  lea     r14, [rdi+0C8h]
0x180006a7f  mov     rcx, r14; lpCriticalSection
0x180006a82  call    cs:__imp_EnterCriticalSection
0x180006a89  nop     dword ptr [rax+rax+00h]
0x180006a8e  and     [rsp+8A0h+pv], 0
0x180006a94  lea     rax, [rsp+8A0h+var_857]
0x180006a99  test    dword ptr [rdi+48h], 800h
0x180006aa0  mov     [rbp+7A0h+var_50], rax
0x180006aa7  lea     rax, [rbp+7A0h+var_57]
0x180006aae  mov     [rbp+7A0h+var_40], rax
0x180006ab5  lea     rax, [rsp+8A0h+var_852]
0x180006aba  mov     [rbp+7A0h+var_48], rax
0x180006ac1  mov     [rsp+8A0h+var_858], 0
0x180006ac6  mov     [rsp+8A0h+var_857], 80408040h
0x180006ace  mov     [rsp+8A0h+var_853], 0
0x180006ad3  jz      short loc_180006AE2
0x180006ad5  test    dword ptr [rdi+1Ch], 8000h
0x180006adc  jnz     short loc_180006AE2
0x180006ade  mov     al, 1
0x180006ae0  jmp     short loc_180006AE4
0x180006ae2  xor     al, al
0x180006ae4  lea     r15, [rdi+98h]
0x180006aeb  test    al, al
0x180006aed  jz      short loc_180006B05
0x180006aef  mov     r8d, 1
0x180006af5  lea     rdx, [rsp+8A0h+pv]
0x180006afa  lea     rcx, [rdi+8]
0x180006afe  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180006b03  jmp     short loc_180006B07
0x180006b05  xor     eax, eax
0x180006b07  mov     r9d, [rdi+1Ch]
0x180006b0b  mov     r8b, [rdi+28h]
0x180006b0f  mov     ecx, [rdi+18h]
0x180006b12  mov     [rsp+8A0h+var_878], r15
0x180006b17  mov     [rsp+8A0h+var_880], rax
0x180006b1c  call    TestCreate
0x180006b21  mov     r15, [rdi+0F8h]
0x180006b28  mov     r12, rax
0x180006b2b  test    r15, r15
0x180006b2e  jz      short loc_180006B54
0x180006b30  call    cs:__imp_GetLastError
0x180006b37  nop     dword ptr [rax+rax+00h]
0x180006b3c  mov     rcx, r15
0x180006b3f  mov     ebx, eax
0x180006b41  call    TestClose
0x180006b46  mov     ecx, ebx; dwErrCode
0x180006b48  call    cs:__imp_SetLastError
0x180006b4f  nop     dword ptr [rax+rax+00h]
0x180006b54  mov     rcx, [rsp+8A0h+pv]; pv
0x180006b59  mov     [rdi+0F8h], r12
0x180006b60  mov     dword ptr [rdi+0C0h], 1
0x180006b6a  test    rcx, rcx
0x180006b6d  jz      short loc_180006B7B
0x180006b6f  call    cs:__imp_CoTaskMemFree
0x180006b76  nop     dword ptr [rax+rax+00h]
0x180006b7b  test    r14, r14
0x180006b7e  jz      short loc_180006B8F
0x180006b80  mov     rcx, r14; lpCriticalSection
0x180006b83  call    cs:__imp_LeaveCriticalSection
0x180006b8a  nop     dword ptr [rax+rax+00h]
0x180006b8f  mov     rax, rsi
0x180006b92  mov     rcx, [rbp+7A0h+var_30]
0x180006b99  xor     rcx, rsp; StackCookie
0x180006b9c  call    __security_check_cookie
0x180006ba1  lea     r11, [rsp+8A0h+var_20]
0x180006ba9  mov     rbx, [r11+38h]
0x180006bad  mov     rsi, [r11+40h]
0x180006bb1  mov     rsp, r11
0x180006bb4  pop     r15
0x180006bb6  pop     r14
0x180006bb8  pop     r12
0x180006bba  pop     rdi
0x180006bbb  pop     rbp
0x180006bbc  retn
```
