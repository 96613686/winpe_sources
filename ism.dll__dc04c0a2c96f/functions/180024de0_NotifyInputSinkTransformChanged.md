# NotifyInputSinkTransformChanged

- ea: `0x180024de0`
- end: `0x180024fdb`
- name: `NotifyInputSinkTransformChanged`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000c5bc`
- `0x180024de0`
- `0x180024fe4`
- `0x18002501c`
- `0x18008dcac`
- `0x1800f0354`
- `0x1800f0c5c`
- `0x1800f0cc4`
- `0x1800f9758`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024f0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e4a`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180024e2c`
- `win32u!NtQueryCompositionInputSinkLuid` at `0x180024e2c`

## string_xrefs

- `0x180024f5d`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\inputsinkdatacache\lib\inputsinkdatacache.cpp`

## pseudocode

```c
__int64 __fastcall NotifyInputSinkTransformChanged(__int64 a1, _OWORD *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 i; // rax
  int v13; // eax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180244880 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 32LL) )
  {
    Init_thread_header(&dword_180244880);
    if ( dword_180244880 == -1 )
    {
      SRWLock.Ptr = 0;
      std::unordered_map<unsigned __int64,unsigned __int64>::unordered_map<unsigned __int64,unsigned __int64>(&qword_180244818);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(&qword_180244858);
      qword_180244870 = 0;
      byte_180244878 = 0;
      atexit(InputSinkDataCache::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180244880);
    }
  }
  v4 = 0;
  v16 = 0;
  if ( a1 )
  {
    NtQueryCompositionInputSinkLuid(a1, &v16);
    v4 = v16;
  }
  LODWORD(v16) = v4;
  AcquireSRWLockExclusive(&SRWLock);
  v7 = 2
     * (qword_180244848
      & std::_Uhash_compare<IInputTarget *,std::hash<IInputTarget *>,std::equal_to<IInputTarget *>>::operator()<IInputTarget *>(
          v5,
          &v16,
          v6));
  v8 = v16;
  v9 = *(_QWORD *)(qword_180244830 + 8 * v7 + 8);
  if ( v9 == qword_180244820 )
  {
LABEL_8:
    v9 = 0;
  }
  else
  {
    while ( v16 != *(_QWORD *)(v9 + 16) )
    {
      if ( v9 == *(_QWORD *)(qword_180244830 + 8 * v7) )
        goto LABEL_8;
      v9 = *(_QWORD *)(v9 + 8);
    }
  }
  v10 = qword_180244820;
  if ( v9 )
    v10 = v9;
  if ( v10 != qword_180244820 )
  {
    for ( i = qword_180244858; i != qword_180244860 && (*(_DWORD *)i != 2 || *(_QWORD *)(i + 8) != v16); i += 96 )
      ;
    if ( i == qword_180244860 )
    {
      std::vector<NotificationData>::_Emplace_one_at_back<unsigned __int64 &,tagINPUT_TRANSFORM const &>(
        &qword_180244858,
        &v16,
        a2,
        v16);
    }
    else
    {
      *(_OWORD *)(i + 32) = *a2;
      *(_OWORD *)(i + 48) = a2[1];
      *(_OWORD *)(i + 64) = a2[2];
      *(_OWORD *)(i + 80) = a2[3];
    }
    if ( qword_180244870 && !byte_180244878 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)qword_180244870 + 80LL))(
              qword_180244870,
              1000000,
              0,
              v8);
      if ( v13 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\inputsinkdatacache\\lib\\"
                        "inputsinkdatacache.cpp",
          (const char *)(unsigned int)v13,
          v14);
      byte_180244878 = 1;
    }
  }
  ReleaseSRWLockExclusive(&SRWLock);
  return 1;
}

```

## disassembly

```asm
0x180024de0  mov     [rsp+arg_8], rbx
0x180024de5  push    rdi
0x180024de6  sub     rsp, 20h
0x180024dea  mov     r8d, cs:_tls_index
0x180024df1  mov     rdi, rcx
0x180024df4  mov     rax, gs:58h
0x180024dfd  mov     rbx, rdx
0x180024e00  mov     ecx, 20h ; ' '
0x180024e05  mov     rax, [rax+r8*8]
0x180024e09  mov     eax, [rcx+rax]
0x180024e0c  cmp     cs:dword_180244880, eax
0x180024e12  jg      loc_180024F72
0x180024e18  xor     eax, eax
0x180024e1a  mov     [rsp+28h+arg_0], rax
0x180024e1f  test    rdi, rdi
0x180024e22  jz      short loc_180024E37
0x180024e24  lea     rdx, [rsp+28h+arg_0]
0x180024e29  mov     rcx, rdi
0x180024e2c  call    cs:__imp_NtQueryCompositionInputSinkLuid
0x180024e32  mov     rax, [rsp+28h+arg_0]
0x180024e37  mov     ecx, dword ptr [rsp+28h+arg_0+4]
0x180024e3b  mov     dword ptr [rsp+28h+arg_0+4], ecx
0x180024e3f  lea     rcx, SRWLock; SRWLock
0x180024e46  mov     dword ptr [rsp+28h+arg_0], eax
0x180024e4a  call    cs:__imp_AcquireSRWLockExclusive
0x180024e50  lea     rdx, [rsp+28h+arg_0]
0x180024e55  call    ??$?RPEAUIInputTarget@@@?$_Uhash_compare@PEAUIInputTarget@@U?$hash@PEAUIInputTarget@@@std@@U?$equal_to@PEAUIInputTarget@@@3@@std@@QEBA_KAEBQEAUIInputTarget@@@Z; std::_Uhash_compare<IInputTarget *,std::hash<IInputTarget *>,std::equal_to<IInputTarget *>>::operator()<IInputTarget *>(IInputTarget * const &)
0x180024e5a  and     rax, cs:qword_180244848
0x180024e61  mov     rdx, cs:qword_180244830
0x180024e68  add     rax, rax
0x180024e6b  mov     r8, cs:qword_180244820
0x180024e72  mov     r9, [rsp+28h+arg_0]
0x180024e77  mov     rcx, [rdx+rax*8+8]
0x180024e7c  cmp     rcx, r8
0x180024e7f  jz      short loc_180024E96
0x180024e81  mov     rdx, [rdx+rax*8]
0x180024e85  cmp     r9, [rcx+10h]
0x180024e89  jz      short loc_180024E98
0x180024e8b  cmp     rcx, rdx
0x180024e8e  jz      short loc_180024E96
0x180024e90  mov     rcx, [rcx+8]
0x180024e94  jmp     short loc_180024E85
0x180024e96  xor     ecx, ecx
0x180024e98  test    rcx, rcx
0x180024e9b  mov     rax, r8
0x180024e9e  cmovnz  rax, rcx
0x180024ea2  cmp     rax, r8
0x180024ea5  jz      short loc_180024F04
0x180024ea7  mov     rax, cs:qword_180244858
0x180024eae  mov     rcx, cs:qword_180244860
0x180024eb5  jmp     short loc_180024EC6
0x180024eb7  cmp     dword ptr [rax], 2
0x180024eba  jnz     short loc_180024EC2
0x180024ebc  cmp     [rax+8], r9
0x180024ec0  jz      short loc_180024ECB
0x180024ec2  add     rax, 60h ; '`'
0x180024ec6  cmp     rax, rcx
0x180024ec9  jnz     short loc_180024EB7
0x180024ecb  cmp     rax, rcx
0x180024ece  jz      short loc_180024F21
0x180024ed0  movups  xmm0, xmmword ptr [rbx]
0x180024ed3  movups  xmmword ptr [rax+20h], xmm0
0x180024ed7  movups  xmm1, xmmword ptr [rbx+10h]
0x180024edb  movups  xmmword ptr [rax+30h], xmm1
0x180024edf  movups  xmm0, xmmword ptr [rbx+20h]
0x180024ee3  movups  xmmword ptr [rax+40h], xmm0
0x180024ee7  movups  xmm1, xmmword ptr [rbx+30h]
0x180024eeb  movups  xmmword ptr [rax+50h], xmm1
0x180024eef  mov     rcx, cs:qword_180244870
0x180024ef6  test    rcx, rcx
0x180024ef9  jz      short loc_180024F04
0x180024efb  cmp     cs:byte_180244878, 0
0x180024f02  jz      short loc_180024F37
0x180024f04  lea     rcx, SRWLock; SRWLock
0x180024f0b  call    cs:__imp_ReleaseSRWLockExclusive
0x180024f11  mov     rbx, [rsp+28h+arg_8]
0x180024f16  mov     eax, 1
0x180024f1b  add     rsp, 20h
0x180024f1f  pop     rdi
0x180024f20  retn
0x180024f21  mov     r8, rbx
0x180024f24  lea     rdx, [rsp+28h+arg_0]
0x180024f29  lea     rcx, qword_180244858
0x180024f30  call    ??$_Emplace_one_at_back@AEA_KAEBUtagINPUT_TRANSFORM@@@?$vector@VNotificationData@@V?$allocator@VNotificationData@@@std@@@std@@AEAAAEAVNotificationData@@AEA_KAEBUtagINPUT_TRANSFORM@@@Z; std::vector<NotificationData>::_Emplace_one_at_back<unsigned __int64 &,tagINPUT_TRANSFORM const &>(unsigned __int64 &,tagINPUT_TRANSFORM const &)
0x180024f35  jmp     short loc_180024EEF
0x180024f37  mov     rax, [rcx]
0x180024f3a  xor     r8d, r8d
0x180024f3d  mov     edx, 0F4240h
0x180024f42  mov     rax, [rax+50h]
0x180024f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f4b  test    eax, eax
0x180024f4d  js      short loc_180024F58
0x180024f4f  mov     cs:byte_180244878, 1
0x180024f56  jmp     short loc_180024F04
0x180024f58  mov     rcx, [rsp+28h]; this
0x180024f5d  lea     r8, aOnecoreuapWind_190; "onecoreuap\\windows\\moderncore\\inputv"...
0x180024f64  mov     r9d, eax; char *
0x180024f67  mov     edx, 8Ch; void *
0x180024f6c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180024f72  lea     rcx, dword_180244880
0x180024f79  call    _Init_thread_header
0x180024f7e  cmp     cs:dword_180244880, 0FFFFFFFFh
0x180024f85  jnz     loc_180024E18
0x180024f8b  xor     eax, eax
0x180024f8d  lea     rcx, qword_180244818
0x180024f94  mov     cs:SRWLock.Ptr, rax
0x180024f9b  call    ??0?$unordered_map@_K_KU?$hash@_K@std@@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_K_K@std@@@2@@std@@QEAA@XZ; std::unordered_map<unsigned __int64,unsigned __int64>::unordered_map<unsigned __int64,unsigned __int64>(void)
0x180024fa0  lea     rcx, qword_180244858
0x180024fa7  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x180024fac  lea     rcx, _InputSinkDataCache__GetInstance____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x180024fb3  mov     cs:qword_180244870, 0
0x180024fbe  mov     cs:byte_180244878, 0
0x180024fc5  call    atexit
0x180024fca  lea     rcx, dword_180244880
0x180024fd1  call    _Init_thread_footer
0x180024fd6  jmp     loc_180024E18
```
