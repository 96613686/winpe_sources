# Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(Microsoft::IoT::ShellExtension::CCBT &,bool)

- ea: `0x180010f74`
- end: `0x180011060`
- name: `?CancelTask@CCBTLauncher@ShellExtension@IoT@Microsoft@@AEAAJAEAVCCBT@234@_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(Microsoft::IoT::ShellExtension::CCBTLauncher *this, struct Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800106fc`
- `0x180010e48`

## callees

- `0x180005fc4`
- `0x18000d410`
- `0x18000f0bc`
- `0x180010f74`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010f89`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010fa9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010fa9`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::CancelTask(
        Microsoft::IoT::ShellExtension::CCBTLauncher *this,
        struct Microsoft::IoT::ShellExtension::CCBT *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 (__fastcall *v10)(__int64, __int64, __int64, _OWORD *, int); // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-38h]
  _OWORD v16[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF
  __int64 v19; // [rsp+68h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+78h] [rbp+20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v20 = v4;
  if ( *((_DWORD *)a2 + 14) )
    goto LABEL_11;
  *((_BYTE *)a2 + 78) = 1;
  *((_DWORD *)a2 + 14) = -2147483638;
  *((_QWORD *)a2 + 1) = GetTickCount64();
  v18 = *((_QWORD *)a2 + 5);
  v5 = (__int64 *)*((_QWORD *)a2 + 2);
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  v19 = v6;
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskProactiveCanceling<unsigned short *,unsigned short *>(
    &v19,
    &v18);
  v7 = *((_QWORD *)this + 24);
  v8 = *((_QWORD *)this + 11);
  v9 = *((unsigned int *)this + 14);
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _OWORD *, int))(*(_QWORD *)v8 + 64LL);
  v16[0] = *(_OWORD *)((char *)a2 + 60);
  if ( !v7 )
  {
    v11 = v10(v8, 0, v9, v16, 5632);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 542;
      goto LABEL_10;
    }
LABEL_11:
    v12 = 0;
    goto LABEL_12;
  }
  v11 = v10(v8, v7, v9, v16, 5632);
  v12 = v11;
  if ( v11 >= 0 )
    goto LABEL_11;
  v13 = 538;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
    (const char *)(unsigned int)v11,
    v15);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
  return v12;
}

```

## disassembly

```asm
0x180010f74  push    rbx
0x180010f76  push    rsi
0x180010f77  push    rdi
0x180010f78  sub     rsp, 40h
0x180010f7c  mov     rdi, rdx
0x180010f7f  mov     rsi, rcx
0x180010f82  lea     rbx, [rcx+60h]
0x180010f86  mov     rcx, rbx; lpCriticalSection
0x180010f89  call    cs:__imp_EnterCriticalSection
0x180010f8f  mov     [rsp+58h+arg_18], rbx
0x180010f94  cmp     dword ptr [rdi+38h], 0
0x180010f98  jnz     loc_18001104A
0x180010f9e  mov     byte ptr [rdi+4Eh], 1
0x180010fa2  mov     dword ptr [rdi+38h], 8000000Ah
0x180010fa9  call    cs:__imp_GetTickCount64
0x180010faf  mov     [rdi+8], rax
0x180010fb3  mov     rax, [rdi+28h]
0x180010fb7  mov     [rsp+58h+arg_0], rax
0x180010fbc  mov     rax, [rdi+10h]
0x180010fc0  test    rax, rax
0x180010fc3  jz      short loc_180010FCA
0x180010fc5  mov     rcx, [rax]
0x180010fc8  jmp     short loc_180010FCC
0x180010fca  xor     ecx, ecx
0x180010fcc  mov     [rsp+58h+arg_8], rcx
0x180010fd1  lea     rdx, [rsp+58h+arg_0]
0x180010fd6  lea     rcx, [rsp+58h+arg_8]
0x180010fdb  call    ??$BackgroundTaskProactiveCanceling@PEAGPEAG@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SAX$$QEAPEAG0@Z; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskProactiveCanceling<ushort *,ushort *>(ushort * &&,ushort * &&)
0x180010fe0  mov     rdx, [rsi+0C0h]
0x180010fe7  mov     rcx, [rsi+58h]
0x180010feb  mov     r8d, [rsi+38h]
0x180010fef  mov     rax, [rcx]
0x180010ff2  movups  xmm0, xmmword ptr [rdi+3Ch]
0x180010ff6  mov     [rsp+58h+var_38], 1600h; int
0x180010ffe  lea     r9, [rsp+58h+var_28]
0x180011003  mov     rax, [rax+40h]
0x180011007  movdqu  [rsp+58h+var_28], xmm0
0x18001100d  test    rdx, rdx
0x180011010  jz      short loc_180011024
0x180011012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011017  mov     ebx, eax
0x180011019  test    eax, eax
0x18001101b  jns     short loc_18001104A
0x18001101d  mov     edx, 21Ah
0x180011022  jmp     short loc_180011034
0x180011024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011029  mov     ebx, eax
0x18001102b  test    eax, eax
0x18001102d  jns     short loc_18001104A
0x18001102f  mov     edx, 21Eh; void *
0x180011034  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18001103b  mov     r9d, eax; char *
0x18001103e  mov     rcx, [rsp+58h]; this
0x180011043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011048  jmp     short loc_18001104C
0x18001104a  xor     ebx, ebx
0x18001104c  lea     rcx, [rsp+58h+arg_18]
0x180011051  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180011056  mov     eax, ebx
0x180011058  add     rsp, 40h
0x18001105c  pop     rdi
0x18001105d  pop     rsi
0x18001105e  pop     rbx
0x18001105f  retn
```
