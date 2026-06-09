# Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(void)

- ea: `0x180011134`
- end: `0x180011289`
- name: `?CheckForPendingTasks@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAXXZ`
- size: `341`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800106fc`
- `0x180012790`
- `0x1800129c0`
- `0x180012c00`
- `0x180014dfc`

## callees

- `0x18000a060`
- `0x18000d410`
- `0x18000dcb4`
- `0x18000f058`
- `0x18000fc18`
- `0x1800109b8`
- `0x180010ba4`
- `0x180011134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001114a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001114a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800111f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001120f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800111f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001120f`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::CheckForPendingTasks(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  void *v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rbp
  __int64 i; // rbx
  __int64 v7; // rsi
  Microsoft::IoT::ShellExtension::CCBT *v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rsi
  _QWORD *v11; // rax
  __int64 j; // rax
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+48h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+50h] [rbp+18h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v5 = *((_QWORD *)this + 21);
  v15 = v1;
  for ( i = *((_QWORD *)this + 20);
        i != v5 && !(unsigned __int8)lambda_3d4decfc9588325a017799f8021f1d5c_::operator()(v4, i);
        i += 88 )
  {
    ;
  }
  if ( i != v5 )
  {
    v7 = i + 88;
    if ( i + 88 == v5 )
      goto LABEL_11;
    do
    {
      if ( !(unsigned __int8)lambda_3d4decfc9588325a017799f8021f1d5c_::operator()(v4, v7) )
      {
        Microsoft::IoT::ShellExtension::CCBT::operator=(i, v7);
        i += 88;
      }
      v7 += 88;
    }
    while ( v7 != v5 );
    if ( i != v5 )
    {
LABEL_11:
      v8 = (Microsoft::IoT::ShellExtension::CCBT *)std::_Move_unchecked<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *>(
                                                     v5,
                                                     *((_QWORD *)this + 21),
                                                     i);
      std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
        v8,
        *((Microsoft::IoT::ShellExtension::CCBT **)this + 21));
      *((_QWORD *)this + 21) = v8;
    }
  }
  v9 = *((_QWORD *)this + 20);
  v10 = *((_QWORD *)this + 21);
  while ( v9 != v10 )
  {
    if ( *(_DWORD *)(v9 + 56) == -2147483638 && GetTickCount64() - *(_QWORD *)(v9 + 8) > 0x7530 )
    {
      *(_DWORD *)(v9 + 56) = -2147024638;
      *(_QWORD *)(v9 + 8) = GetTickCount64();
      v13 = *(_QWORD *)(v9 + 40);
      v11 = *(_QWORD **)(v9 + 16);
      if ( v11 )
        v11 = (_QWORD *)*v11;
      v14 = v11;
      Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunchTimedOut<unsigned short *,unsigned short *>(
        (__int64 *)&v14,
        &v13);
    }
    v9 += 88;
  }
  for ( j = *((_QWORD *)this + 20); j != *((_QWORD *)this + 21); j += 88 )
  {
    if ( *(_DWORD *)(j + 56) == -2147483638 )
      goto LABEL_25;
  }
  wil::details::SetEvent(*((wil::details **)this + 8), v3);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x180011134  mov     [rsp+arg_18], rbx
0x180011139  push    rbp
0x18001113a  push    rsi
0x18001113b  push    rdi
0x18001113c  sub     rsp, 20h
0x180011140  lea     rbx, [rcx+60h]
0x180011144  mov     rdi, rcx
0x180011147  mov     rcx, rbx; lpCriticalSection
0x18001114a  call    cs:__imp_EnterCriticalSection
0x180011150  mov     rbp, [rdi+0A8h]
0x180011157  mov     [rsp+38h+arg_10], rbx
0x18001115c  mov     rbx, [rdi+0A0h]
0x180011163  jmp     short loc_180011175
0x180011165  mov     rdx, rbx
0x180011168  call    _lambda_3d4decfc9588325a017799f8021f1d5c___operator__
0x18001116d  test    al, al
0x18001116f  jnz     short loc_18001117A
0x180011171  add     rbx, 58h ; 'X'
0x180011175  cmp     rbx, rbp
0x180011178  jnz     short loc_180011165
0x18001117a  cmp     rbx, rbp
0x18001117d  jz      short loc_1800111DC
0x18001117f  lea     rsi, [rbx+58h]
0x180011183  cmp     rsi, rbp
0x180011186  jz      short loc_1800111B1
0x180011188  mov     rdx, rsi
0x18001118b  call    _lambda_3d4decfc9588325a017799f8021f1d5c___operator__
0x180011190  test    al, al
0x180011192  jnz     short loc_1800111A3
0x180011194  mov     rdx, rsi
0x180011197  mov     rcx, rbx
0x18001119a  call    ??4CCBT@ShellExtension@IoT@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::IoT::ShellExtension::CCBT::operator=(Microsoft::IoT::ShellExtension::CCBT &&)
0x18001119f  add     rbx, 58h ; 'X'
0x1800111a3  add     rsi, 58h ; 'X'
0x1800111a7  cmp     rsi, rbp
0x1800111aa  jnz     short loc_180011188
0x1800111ac  cmp     rbx, rbp
0x1800111af  jz      short loc_1800111DC
0x1800111b1  mov     rdx, [rdi+0A8h]
0x1800111b8  mov     r8, rbx
0x1800111bb  mov     rcx, rbp
0x1800111be  call    ??$_Move_unchecked@PEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@@std@@YAPEAVCCBT@ShellExtension@IoT@Microsoft@@PEAV1234@00@Z; std::_Move_unchecked<Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT *)
0x1800111c3  mov     rdx, [rdi+0A8h]
0x1800111ca  mov     rcx, rax; this
0x1800111cd  mov     rbx, rax
0x1800111d0  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x1800111d5  mov     [rdi+0A8h], rbx
0x1800111dc  mov     rbx, [rdi+0A0h]
0x1800111e3  mov     ebp, 8000000Ah
0x1800111e8  mov     rsi, [rdi+0A8h]
0x1800111ef  jmp     short loc_180011246
0x1800111f1  cmp     [rbx+38h], ebp
0x1800111f4  jnz     short loc_180011242
0x1800111f6  call    cs:__imp_GetTickCount64
0x1800111fc  sub     rax, [rbx+8]
0x180011200  cmp     rax, 7530h
0x180011206  jbe     short loc_180011242
0x180011208  mov     dword ptr [rbx+38h], 80070102h
0x18001120f  call    cs:__imp_GetTickCount64
0x180011215  mov     [rbx+8], rax
0x180011219  mov     rax, [rbx+28h]
0x18001121d  mov     [rsp+38h+arg_0], rax
0x180011222  mov     rax, [rbx+10h]
0x180011226  test    rax, rax
0x180011229  jz      short loc_18001122E
0x18001122b  mov     rax, [rax]
0x18001122e  lea     rdx, [rsp+38h+arg_0]
0x180011233  mov     [rsp+38h+arg_8], rax
0x180011238  lea     rcx, [rsp+38h+arg_8]
0x18001123d  call    ??$BackgroundTaskLaunchTimedOut@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunchTimedOut<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180011242  add     rbx, 58h ; 'X'
0x180011246  cmp     rbx, rsi
0x180011249  jnz     short loc_1800111F1
0x18001124b  mov     rax, [rdi+0A0h]
0x180011252  mov     rcx, [rdi+0A8h]
0x180011259  jmp     short loc_180011264
0x18001125b  cmp     [rax+38h], ebp
0x18001125e  jz      short loc_180011272
0x180011260  add     rax, 58h ; 'X'
0x180011264  cmp     rax, rcx
0x180011267  jnz     short loc_18001125B
0x180011269  mov     rcx, [rdi+40h]; this
0x18001126d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180011272  lea     rcx, [rsp+38h+arg_10]
0x180011277  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001127c  mov     rbx, [rsp+38h+arg_18]
0x180011281  add     rsp, 20h
0x180011285  pop     rdi
0x180011286  pop     rsi
0x180011287  pop     rbp
0x180011288  retn
```
