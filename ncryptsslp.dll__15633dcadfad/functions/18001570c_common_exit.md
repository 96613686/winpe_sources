# common_exit

- ea: `0x18001570c`
- end: `0x1800157f0`
- name: `common_exit`
- size: `228`
- prototype: `__int64 __fastcall(UINT uExitCode)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001589c`

## callees

- `0x180015604`
- `0x18001570c`
- `0x1800157f8`
- `0x18001582c`
- `0x18001792c`
- `0x18001796c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015733`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015733`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall common_exit(UINT uExitCode, int a2, int a3)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  _BYTE v7[4]; // [rsp+20h] [rbp-30h] BYREF
  int v8; // [rsp+24h] [rbp-2Ch] BYREF
  int v9; // [rsp+28h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-20h]
  _QWORD v11[3]; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+68h] [rbp+18h] BYREF
  int v13; // [rsp+70h] [rbp+20h] BYREF
  char v14; // [rsp+78h] [rbp+28h] BYREF

  v13 = a3;
  v12 = a2;
  v10 = -2;
  if ( !a3 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
    {
      if ( *(_WORD *)ModuleHandleW == 23117 )
      {
        v5 = *((int *)ModuleHandleW + 15);
        if ( *(_DWORD *)((char *)ModuleHandleW + v5) == 17744
          && *(_WORD *)((char *)ModuleHandleW + v5 + 24) == 523
          && *(_DWORD *)((char *)ModuleHandleW + v5 + 132) > 0xEu
          && *(_DWORD *)((char *)ModuleHandleW + v5 + 248) )
        {
          try_cor_exit_process(uExitCode);
        }
      }
    }
  }
  v14 = 0;
  v11[0] = &v12;
  v11[1] = &v13;
  v11[2] = &v14;
  v8 = 2;
  v9 = 2;
  result = _crt_seh_guarded_call_void_::operator()__lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___(
             v7,
             &v9,
             v11,
             &v8);
  if ( !v13 )
  {
    result = _acrt_get_process_end_policy();
    if ( (_DWORD)result != 1 )
      result = _acrt_app_verifier_enabled();
    if ( !v13 )
      exit_or_terminate_process(uExitCode);
  }
  return result;
}

```

## disassembly

```asm
0x18001570c  mov     [rsp-8+arg_10], r8d
0x180015711  mov     [rsp-8+arg_8], edx
0x180015715  push    rbp
0x180015716  mov     rbp, rsp
0x180015719  sub     rsp, 50h
0x18001571d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180015725  mov     [rsp+50h+arg_0], rbx
0x18001572a  mov     ebx, ecx
0x18001572c  test    r8d, r8d
0x18001572f  jnz     short loc_18001577C
0x180015731  xor     ecx, ecx; lpModuleName
0x180015733  call    cs:__imp_GetModuleHandleW
0x180015739  test    rax, rax
0x18001573c  jz      short loc_18001577C
0x18001573e  mov     ecx, 5A4Dh
0x180015743  cmp     [rax], cx
0x180015746  jnz     short loc_18001577C
0x180015748  movsxd  rcx, dword ptr [rax+3Ch]
0x18001574c  cmp     dword ptr [rcx+rax], 4550h
0x180015753  jnz     short loc_18001577C
0x180015755  mov     edx, 20Bh
0x18001575a  cmp     [rcx+rax+18h], dx
0x18001575f  jnz     short loc_18001577C
0x180015761  cmp     dword ptr [rcx+rax+84h], 0Eh
0x180015769  jbe     short loc_18001577C
0x18001576b  cmp     dword ptr [rcx+rax+0F8h], 0
0x180015773  jz      short loc_18001577C
0x180015775  mov     ecx, ebx
0x180015777  call    try_cor_exit_process
0x18001577c  mov     [rbp+arg_18], 0
0x180015780  lea     rax, [rbp+arg_8]
0x180015784  mov     [rbp+var_18], rax
0x180015788  lea     rax, [rbp+arg_10]
0x18001578c  mov     [rbp+var_10], rax
0x180015790  lea     rax, [rbp+arg_18]
0x180015794  mov     [rbp+var_8], rax
0x180015798  mov     eax, 2
0x18001579d  mov     [rbp+var_2C], eax
0x1800157a0  mov     [rbp+var_28], eax
0x1800157a3  lea     r9, [rbp+var_2C]
0x1800157a7  lea     r8, [rbp+var_18]
0x1800157ab  lea     rdx, [rbp+var_28]
0x1800157af  lea     rcx, [rbp+var_30]
0x1800157b3  call    __crt_seh_guarded_call_void___operator____lambda_d80eeec6fff315bfe5c115232f3240e3___lambda_6e4b09c48022b2350581041d5f6b0c4c_____lambda_2358e3775559c9db80273638284d5e45___
0x1800157b8  nop
0x1800157b9  cmp     [rbp+arg_10], 0
0x1800157bd  jnz     short loc_1800157DD
0x1800157bf  call    __acrt_get_process_end_policy
0x1800157c4  cmp     eax, 1
0x1800157c7  jnz     short loc_1800157CD
0x1800157c9  xor     dl, dl
0x1800157cb  jmp     short loc_1800157D7
0x1800157cd  call    __acrt_app_verifier_enabled
0x1800157d2  test    al, al
0x1800157d4  setz    dl
0x1800157d7  cmp     [rbp+arg_10], 0
0x1800157db  jz      short loc_1800157E8
0x1800157dd  mov     rbx, [rsp+50h+arg_0]
0x1800157e2  add     rsp, 50h
0x1800157e6  pop     rbp
0x1800157e7  retn
0x1800157e8  mov     ecx, ebx; uExitCode
0x1800157ea  call    exit_or_terminate_process
```
