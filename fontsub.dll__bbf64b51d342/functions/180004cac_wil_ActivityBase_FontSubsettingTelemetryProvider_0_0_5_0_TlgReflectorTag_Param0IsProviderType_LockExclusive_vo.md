# wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180004cac`
- end: `0x180004d2d`
- name: `?LockExclusive@?$ActivityBase@VFontSubsettingTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003f30`
- `0x1800052a0`
- `0x180007378`
- `0x1800073d4`

## callees

- `0x180003a64`
- `0x180004cac`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180004cd4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004cd4`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<FontSubsettingTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rbx
  char *v5; // rax
  int v6; // ecx
  int v7; // esi
  char v9; // [rsp+30h] [rbp+8h] BYREF
  char v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v2 )
  {
    v4 = v2 + 33;
    AcquireSRWLockExclusive(v4);
    v5 = &v10;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v4 = 0;
    v5 = &v9;
    v7 = 0;
    v6 = 2;
  }
  *a2 = v4;
  *(_QWORD *)v5 = 0;
  if ( v6 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v7 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x180004cac  mov     [rsp+arg_10], rbx
0x180004cb1  mov     [rsp+arg_18], rsi
0x180004cb6  push    rdi
0x180004cb7  sub     rsp, 20h
0x180004cbb  mov     rbx, [rcx+118h]
0x180004cc2  mov     rdi, rdx
0x180004cc5  test    rbx, rbx
0x180004cc8  jz      short loc_180004CE8
0x180004cca  add     rbx, 108h
0x180004cd1  mov     rcx, rbx; SRWLock
0x180004cd4  call    cs:__imp_AcquireSRWLockExclusive
0x180004cda  lea     rax, [rsp+28h+arg_8]
0x180004cdf  xor     ecx, ecx
0x180004ce1  mov     esi, 1
0x180004ce6  jmp     short loc_180004CF4
0x180004ce8  xor     ebx, ebx
0x180004cea  lea     rax, [rsp+28h+arg_0]
0x180004cef  xor     esi, esi
0x180004cf1  lea     ecx, [rbx+2]
0x180004cf4  mov     [rdi], rbx
0x180004cf7  mov     qword ptr [rax], 0
0x180004cfe  test    ecx, ecx
0x180004d00  jz      short loc_180004D0C
0x180004d02  lea     rcx, [rsp+28h+arg_0]
0x180004d07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004d0c  test    esi, esi
0x180004d0e  jz      short loc_180004D1A
0x180004d10  lea     rcx, [rsp+28h+arg_8]
0x180004d15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004d1a  mov     rbx, [rsp+28h+arg_10]
0x180004d1f  mov     rax, rdi
0x180004d22  mov     rsi, [rsp+28h+arg_18]
0x180004d27  add     rsp, 20h
0x180004d2b  pop     rdi
0x180004d2c  retn
```
