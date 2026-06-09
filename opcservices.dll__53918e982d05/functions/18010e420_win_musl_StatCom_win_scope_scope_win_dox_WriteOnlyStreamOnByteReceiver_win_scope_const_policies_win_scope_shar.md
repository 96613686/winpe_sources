# win_musl::StatCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,2,win_musl::InnerCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,win_scope::report_policy_throw>>::Stat(tagSTATSTG *,ulong)

- ea: `0x18010e420`
- end: `0x18010e46e`
- name: `?Stat@?$StatCom@V?$scope@PEAVWriteOnlyStreamOnByteReceiver@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@$01V?$InnerCom@V?$scope@PEAVWriteOnlyStreamOnByteReceiver@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@Ureport_policy_throw@2@@win_musl@@@win_musl@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18010dd54`
- `0x18010e420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010e456`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010e456`

## pseudocode

```c
__int64 __fastcall win_musl::StatCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,2,win_musl::InnerCom<win_scope::scope<win_dox::WriteOnlyStreamOnByteReceiver *,win_scope::const_policies<win_scope::shared_policies>>,IStream,win_scope::report_policy_throw>>::Stat(
        int a1,
        LPVOID *a2,
        int a3)
{
  __int64 result; // rax
  char v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = 1;
  result = win_musl::ModuleEntryCall_win_musl::StatCom_win_scope::scope_win_dox::WriteOnlyStreamOnByteReceiver___win_scope::const_policies_win_scope::shared_policies____IStream_2_win_musl::InnerCom_win_scope::scope_win_dox::WriteOnlyStreamOnByteReceiver___win_scope::const_policies_win_scope::shared_policies____IStream_win_scope::report_policy_throw____tagSTATSTG___unsigned_long_bool___(
             a1,
             (_DWORD)a2,
             (_DWORD)a2,
             a3,
             (__int64)&v5);
  if ( (int)result >= 0 && !v5 )
  {
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    return 2147483658LL;
  }
  return result;
}

```

## disassembly

```asm
0x18010e420  push    rbx
0x18010e422  sub     rsp, 30h
0x18010e426  lea     rax, [rsp+38h+arg_18]
0x18010e42b  mov     [rsp+38h+arg_18], 1
0x18010e430  mov     r9d, r8d
0x18010e433  mov     [rsp+38h+var_18], rax
0x18010e438  mov     r8, rdx
0x18010e43b  mov     rbx, rdx
0x18010e43e  call    win_musl__ModuleEntryCall_win_musl__StatCom_win_scope__scope_win_dox__WriteOnlyStreamOnByteReceiver___win_scope__const_policies_win_scope__shared_policies____IStream_2_win_musl__InnerCom_win_scope__scope_win_dox__WriteOnlyStreamOnByteReceiver___win_scope__const_policies_win_scope__shared_policies____IStream_win_scope__report_policy_throw____tagSTATSTG___unsigned_long_bool___
0x18010e443  test    eax, eax
0x18010e445  js      short loc_18010E468
0x18010e447  cmp     [rsp+38h+arg_18], 0
0x18010e44c  jnz     short loc_18010E468
0x18010e44e  mov     rcx, [rbx]; pv
0x18010e451  test    rcx, rcx
0x18010e454  jz      short loc_18010E463
0x18010e456  call    cs:__imp_CoTaskMemFree
0x18010e45c  mov     qword ptr [rbx], 0
0x18010e463  mov     eax, 8000000Ah
0x18010e468  add     rsp, 30h
0x18010e46c  pop     rbx
0x18010e46d  retn
```
