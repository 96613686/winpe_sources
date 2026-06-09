# CKsProxy::AccessDeniedWaitThread(CKsProxy *)

- ea: `0x180012d00`
- end: `0x180012ea9`
- name: `?AccessDeniedWaitThread@CKsProxy@@SAKPEAV1@@Z`
- size: `425`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b14`
- `0x180012d00`
- `0x180025890`
- `0x18003f33c`
- `0x180045010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180012d20`
- `KERNEL32!WaitForSingleObjectEx` at `0x180012d20`
- `KERNEL32!LeaveCriticalSection` at `0x180012e1b`
- `KERNEL32!LeaveCriticalSection` at `0x180012e3f`
- `KERNEL32!LeaveCriticalSection` at `0x180012e1b`
- `KERNEL32!LeaveCriticalSection` at `0x180012e3f`
- `KERNEL32!EnterCriticalSection` at `0x180012d3e`
- `KERNEL32!EnterCriticalSection` at `0x180012d3e`

## pseudocode

```c
__int64 __fastcall CKsProxy::AccessDeniedWaitThread(char *Parameter)
{
  __int64 v2; // rcx
  unsigned int v3; // r15d
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbp
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // r14
  int (__fastcall **v8)(_QWORD, GUID *, __int64 *); // rax
  int v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  while ( 1 )
  {
    if ( WaitForSingleObjectEx(*((HANDLE *)Parameter + 80), 0xFFFFFFFF, 0) )
    {
      CBaseFilter::NotifyEvent((CBaseFilter *)Parameter, 3, -2147024891, 0);
      return 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
    if ( *((_DWORD *)Parameter + 101) )
      break;
    v2 = *((_QWORD *)Parameter + 79);
    v3 = -2147024891;
    if ( v2 )
      v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
    v4 = *((_QWORD *)Parameter + 36);
    if ( v4 )
    {
      do
      {
        v5 = *(_QWORD *)(v4 + 16);
        v6 = *(_QWORD *)(v4 + 8);
        v4 = v6;
        if ( *(_QWORD *)(v5 + 48) )
        {
          v7 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))(v5 + 24);
          v10 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)(v5 + 24) + 72LL))(v5 + 24, &v10) >= 0 && v10 == 1 )
          {
            v8 = *v7;
            v11 = 0;
            if ( (*v8)(v7, &GUID_7bb38260_d19c_11d2_b38a_00a0c95ec22e, &v11) >= 0 )
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 128LL))(v11, 0, v3);
            wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v11);
          }
        }
      }
      while ( v6 );
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
    (*(void (__fastcall **)(char *))(*((_QWORD *)Parameter + 3) + 32LL))(Parameter + 24);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)Parameter + 11));
  return 0;
}

```

## disassembly

```asm
0x180012d00  mov     [rsp+arg_10], rbx
0x180012d05  push    rbp
0x180012d06  push    rsi
0x180012d07  push    rdi
0x180012d08  push    r14
0x180012d0a  push    r15
0x180012d0c  sub     rsp, 20h
0x180012d10  mov     rbx, rcx
0x180012d13  mov     rcx, [rbx+280h]; hHandle
0x180012d1a  xor     r8d, r8d; bAlertable
0x180012d1d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012d20  call    cs:__imp_WaitForSingleObjectEx
0x180012d27  nop     dword ptr [rax+rax+00h]
0x180012d2c  test    eax, eax
0x180012d2e  jnz     loc_180012E7F
0x180012d34  lea     rsi, [rbx+198h]
0x180012d3b  mov     rcx, rsi; lpCriticalSection
0x180012d3e  call    cs:__imp_EnterCriticalSection
0x180012d45  nop     dword ptr [rax+rax+00h]
0x180012d4a  cmp     dword ptr [rbx+194h], 0
0x180012d51  jnz     loc_180012E3C
0x180012d57  mov     rcx, [rbx+278h]
0x180012d5e  mov     r15d, 80070005h
0x180012d64  test    rcx, rcx
0x180012d67  jz      short loc_180012D78
0x180012d69  mov     rax, [rcx]
0x180012d6c  mov     rax, [rax+30h]
0x180012d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d75  mov     r15d, eax
0x180012d78  mov     rdi, [rbx+120h]
0x180012d7f  test    rdi, rdi
0x180012d82  jz      loc_180012E18
0x180012d88  mov     rcx, [rdi+10h]
0x180012d8c  mov     rbp, [rdi+8]
0x180012d90  mov     rdi, rbp
0x180012d93  cmp     qword ptr [rcx+30h], 0
0x180012d98  jz      short loc_180012E0F
0x180012d9a  lea     r14, [rcx+18h]
0x180012d9e  mov     [rsp+48h+arg_0], 0
0x180012da6  mov     rax, [r14]
0x180012da9  lea     rdx, [rsp+48h+arg_0]
0x180012dae  mov     rcx, r14
0x180012db1  mov     rax, [rax+48h]
0x180012db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dba  test    eax, eax
0x180012dbc  js      short loc_180012E0F
0x180012dbe  cmp     [rsp+48h+arg_0], 1
0x180012dc3  jnz     short loc_180012E0F
0x180012dc5  mov     rax, [r14]
0x180012dc8  lea     r8, [rsp+48h+arg_8]
0x180012dcd  lea     rdx, _GUID_7bb38260_d19c_11d2_b38a_00a0c95ec22e
0x180012dd4  mov     [rsp+48h+arg_8], 0
0x180012ddd  mov     rcx, r14
0x180012de0  mov     rax, [rax]
0x180012de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012de8  test    eax, eax
0x180012dea  js      short loc_180012E05
0x180012dec  mov     rcx, [rsp+48h+arg_8]
0x180012df1  mov     r8d, r15d
0x180012df4  xor     edx, edx
0x180012df6  mov     rax, [rcx]
0x180012df9  mov     rax, [rax+80h]
0x180012e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e05  lea     rcx, [rsp+48h+arg_8]
0x180012e0a  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180012e0f  test    rbp, rbp
0x180012e12  jnz     loc_180012D88
0x180012e18  mov     rcx, rsi; lpCriticalSection
0x180012e1b  call    cs:__imp_LeaveCriticalSection
0x180012e22  nop     dword ptr [rax+rax+00h]
0x180012e27  lea     rcx, [rbx+18h]
0x180012e2b  mov     rax, [rcx]
0x180012e2e  mov     rax, [rax+20h]
0x180012e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e37  jmp     loc_180012D13
0x180012e3c  mov     rcx, rsi; lpCriticalSection
0x180012e3f  call    cs:__imp_LeaveCriticalSection
0x180012e46  nop     dword ptr [rax+rax+00h]
0x180012e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e52  lea     rax, WPP_GLOBAL_Control
0x180012e59  cmp     rcx, rax
0x180012e5c  jz      short loc_180012E95
0x180012e5e  cmp     byte ptr [rcx+19h], 2
0x180012e62  jb      short loc_180012E95
0x180012e64  mov     r9, [rbx+58h]
0x180012e68  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180012e6f  mov     rcx, [rcx+10h]
0x180012e73  mov     edx, 0Dh
0x180012e78  call    WPP_SF_S
0x180012e7d  jmp     short loc_180012E95
0x180012e7f  xor     r9d, r9d; __int64
0x180012e82  mov     r8, 0FFFFFFFF80070005h; __int64
0x180012e89  mov     rcx, rbx; this
0x180012e8c  lea     edx, [r9+3]; int
0x180012e90  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x180012e95  mov     rbx, [rsp+48h+arg_10]
0x180012e9a  xor     eax, eax
0x180012e9c  add     rsp, 20h
0x180012ea0  pop     r15
0x180012ea2  pop     r14
0x180012ea4  pop     rdi
0x180012ea5  pop     rsi
0x180012ea6  pop     rbp
0x180012ea7  retn
```
