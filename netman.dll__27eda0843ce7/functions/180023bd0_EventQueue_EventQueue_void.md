# EventQueue::EventQueue(void *)

- ea: `0x180023bd0`
- end: `0x180023f0a`
- name: `??0EventQueue@@QEAA@PEAX@Z`
- size: `826`
- prototype: `EventQueue *__fastcall(EventQueue *this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001f9c4`

## callees

- `0x180018ac4`
- `0x180019200`
- `0x180019c68`
- `0x180023bd0`
- `0x180023f1c`
- `0x18003060c`
- `0x180034de4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180023d6d`
- `KERNEL32!InitializeCriticalSection` at `0x180023d6d`
- `KERNEL32!GetLastError` at `0x180023e1b`
- `KERNEL32!GetLastError` at `0x180023e1b`
- `KERNEL32!CreateEventW` at `0x180023cc2`
- `KERNEL32!CreateEventW` at `0x180023d94`
- `KERNEL32!CreateEventW` at `0x180023cc2`
- `KERNEL32!CreateEventW` at `0x180023d94`
- `KERNEL32!CloseHandle` at `0x180023dfc`
- `KERNEL32!CloseHandle` at `0x180023dfc`
- `KERNEL32!GetCurrentProcess` at `0x180023c68`
- `KERNEL32!GetCurrentProcess` at `0x180023c71`
- `KERNEL32!GetCurrentProcess` at `0x180023c68`
- `KERNEL32!GetCurrentProcess` at `0x180023c71`
- `KERNEL32!DuplicateHandle` at `0x180023c96`
- `KERNEL32!DuplicateHandle` at `0x180023c96`
- `ntdll!RtlRegisterWait` at `0x180023d1f`
- `ntdll!RtlRegisterWait` at `0x180023dde`
- `ntdll!RtlRegisterWait` at `0x180023d1f`
- `ntdll!RtlRegisterWait` at `0x180023dde`
- `ntdll!RtlNtStatusToDosError` at `0x180023e94`
- `ntdll!RtlNtStatusToDosError` at `0x180023e94`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
EventQueue *__fastcall EventQueue::EventQueue(EventQueue *this, void *a2)
{
  _QWORD *v4; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v6; // rax
  BOOL v7; // eax
  HANDLE EventW; // rbx
  _DWORD *v9; // rax
  int v10; // eax
  EventQueue *result; // rax
  HANDLE v12; // rbx
  _QWORD *v13; // rax
  NTSTATUS v14; // eax
  signed int LastError; // ebx
  signed int v16; // eax
  EventQueue *v17; // rbx
  _BYTE *v18; // rdx
  Event *v19; // rcx
  _BYTE *v20; // rdx
  EventQueue *v21; // rbx
  Event *v22; // rcx
  _BYTE v23[32]; // [rsp+0h] [rbp-A8h] BYREF
  int v24; // [rsp+40h] [rbp-68h]
  signed int v25; // [rsp+44h] [rbp-64h] BYREF
  int Win32Error; // [rsp+48h] [rbp-60h] BYREF
  signed int v27; // [rsp+4Ch] [rbp-5Ch] BYREF
  int v28; // [rsp+50h] [rbp-58h] BYREF
  int v29; // [rsp+54h] [rbp-54h] BYREF
  NTSTATUS v30; // [rsp+58h] [rbp-50h] BYREF
  int pExceptionObject; // [rsp+5Ch] [rbp-4Ch] BYREF
  int v32; // [rsp+60h] [rbp-48h] BYREF
  HANDLE v33; // [rsp+68h] [rbp-40h] BYREF
  EventQueue *v34; // [rsp+70h] [rbp-38h]

  v34 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v4 = MemAlloc(0x20u);
  *v4 = v4;
  v4[1] = v4;
  *(_QWORD *)this = v4;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_7b395475d90435087767593a55cc59de_Traceguids);
  v24 = 0;
  CurrentProcess = GetCurrentProcess();
  v6 = GetCurrentProcess();
  v7 = DuplicateHandle(v6, a2, CurrentProcess, (LPHANDLE)this + 8, 0, 0, 2u);
  try
  {
    if ( !v7 )
    {
      LastError = GetLastError();
      v24 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_7b395475d90435087767593a55cc59de_Traceguids);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v25 = LastError;
      throw (long *)&v25;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl'::`2'::impl) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v33 = EventW;
      if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        Win32Error = HrFromLastWin32Error();
        throw (long *)&Win32Error;
      }
      v9 = MemAlloc(0x10u);
      if ( !v9 )
      {
        *((_QWORD *)this + 7) = 0;
        v28 = -2147024882;
        throw (long *)&v28;
      }
      *(_QWORD *)v9 = EventW;
      v9[2] = 0;
      *((_QWORD *)this + 7) = v9;
      v33 = 0;
      v10 = RtlRegisterWait((PHANDLE)this + 9, EventW, DispatchEvents, 0, 0xFFFFFFFF, 0);
      v24 = v10;
      if ( v10 < 0 )
      {
        v16 = RtlNtStatusToDosError(v10);
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v27 = v16;
        throw (long *)&v27;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
    }
    else
    {
      v12 = CreateEventW(0, 0, 0, 0);
      if ( !v12 )
      {
        v29 = HrFromLastWin32Error();
        throw (long *)&v29;
      }
      v13 = MemAlloc(0x10u);
      if ( !v13 )
      {
        *((_QWORD *)this + 7) = 0;
        CloseHandle(v12);
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      v13[1] = 0;
      *v13 = v12;
      *((_QWORD *)this + 7) = v13;
      v14 = RtlRegisterWait((PHANDLE)this + 9, v12, DispatchEvents, 0, 0xFFFFFFFF, 0);
      v24 = v14;
      if ( v14 < 0 )
      {
        v30 = v14;
        throw (long *)&v30;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_7b395475d90435087767593a55cc59de_Traceguids);
    InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    result = this;
  }
  catch ( long )
  {
    v18 = v23;
    v17 = v34;
    if ( *((_QWORD *)v34 + 9) && v24 >= 0 )
      RtlDeregisterWaitEx(*((HANDLE *)v34 + 9), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v19 = (Event *)*((_QWORD *)v17 + 7);
    if ( v19 )
      Event::`scalar deleting destructor'(v19, (unsigned int)v18);
    if ( *((_QWORD *)v17 + 8) )
      CloseHandle(*((HANDLE *)v17 + 8));
    throw;
  }
  catch ( ... )
  {
    v20 = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_7b395475d90435087767593a55cc59de_Traceguids);
    v21 = v34;
    if ( *((_QWORD *)v34 + 9) && v24 >= 0 )
      RtlDeregisterWaitEx(*((HANDLE *)v34 + 9), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v22 = (Event *)*((_QWORD *)v21 + 7);
    if ( v22 )
      Event::`scalar deleting destructor'(v22, (unsigned int)v20);
    if ( *((_QWORD *)v21 + 8) )
      CloseHandle(*((HANDLE *)v21 + 8));
    v32 = -2147418113;
    throw (long *)&v32;
  }
  return result;
}

```

## disassembly

```asm
0x180023bd0  mov     [rsp+arg_10], rbx
0x180023bd5  mov     [rsp+arg_18], rsi
0x180023bda  push    rdi
0x180023bdb  push    r12
0x180023bdd  push    r13
0x180023bdf  push    r14
0x180023be1  push    r15
0x180023be3  sub     rsp, 80h
0x180023bea  mov     r12, rdx
0x180023bed  mov     rdi, rcx
0x180023bf0  mov     [rsp+0A8h+var_38], rcx
0x180023bf5  xor     r13d, r13d
0x180023bf8  mov     [rcx], r13
0x180023bfb  mov     [rcx+8], r13
0x180023bff  lea     ecx, [r13+20h]; unsigned __int64
0x180023c03  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180023c08  mov     [rax], rax
0x180023c0b  mov     [rax+8], rax
0x180023c0f  mov     [rdi], rax
0x180023c12  xorps   xmm0, xmm0
0x180023c15  xor     eax, eax
0x180023c17  movups  xmmword ptr [rdi+10h], xmm0
0x180023c1b  movups  xmmword ptr [rdi+20h], xmm0
0x180023c1f  mov     [rdi+30h], rax
0x180023c23  mov     [rdi+38h], r13
0x180023c27  mov     [rdi+40h], r13
0x180023c2b  lea     r14, [rdi+48h]
0x180023c2f  mov     [r14], r13
0x180023c32  mov     [rdi+50h], r13d
0x180023c36  lea     rax, WPP_GLOBAL_Control
0x180023c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c44  cmp     rcx, rax
0x180023c47  jz      short loc_180023C63
0x180023c49  test    byte ptr [rcx+1Ch], 8
0x180023c4d  jz      short loc_180023C63
0x180023c4f  lea     edx, [r13+0Ah]
0x180023c53  lea     r8, WPP_7b395475d90435087767593a55cc59de_Traceguids
0x180023c5a  mov     rcx, [rcx+10h]
0x180023c5e  call    WPP_SF_
0x180023c63  mov     [rsp+0A8h+var_68], r13d
0x180023c68  call    cs:__imp_GetCurrentProcess
0x180023c6e  mov     rbx, rax
0x180023c71  call    cs:__imp_GetCurrentProcess
0x180023c77  mov     [rsp+0A8h+dwOptions], 2; dwOptions
0x180023c7f  mov     [rsp+0A8h+bInheritHandle], r13d; bInheritHandle
0x180023c84  mov     [rsp+0A8h+dwDesiredAccess], r13d; dwDesiredAccess
0x180023c89  lea     r9, [rdi+40h]; lpTargetHandle
0x180023c8d  mov     r8, rbx; hTargetProcessHandle
0x180023c90  mov     rdx, r12; hSourceHandle
0x180023c93  mov     rcx, rax; hSourceProcessHandle
0x180023c96  call    cs:__imp_DuplicateHandle
0x180023c9c  test    eax, eax
0x180023c9e  jz      loc_180023E1B
0x180023ca4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety> `wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl(void)'::`2'::impl
0x180023cab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(void)
0x180023cb0  xor     r9d, r9d; lpName
0x180023cb3  xor     r8d, r8d; bInitialState
0x180023cb6  xor     edx, edx; bManualReset
0x180023cb8  xor     ecx, ecx; lpEventAttributes
0x180023cba  test    al, al
0x180023cbc  jz      loc_180023D94
0x180023cc2  call    cs:__imp_CreateEventW
0x180023cc8  mov     rbx, rax
0x180023ccb  mov     [rsp+0A8h+var_40], rax
0x180023cd0  inc     rax
0x180023cd3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023cd9  jz      loc_180023E78
0x180023cdf  mov     ecx, 10h; unsigned __int64
0x180023ce4  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180023ce9  test    rax, rax
0x180023cec  jz      loc_180023EBB
0x180023cf2  mov     [rax], rbx
0x180023cf5  mov     [rax+8], r13d
0x180023cf9  mov     [rdi+38h], rax
0x180023cfd  mov     [rsp+0A8h+var_40], r13
0x180023d02  mov     [rsp+0A8h+bInheritHandle], r13d; ulFlags
0x180023d07  mov     [rsp+0A8h+dwDesiredAccess], 0FFFFFFFFh; ulMilliseconds
0x180023d0f  xor     r9d, r9d; pvContext
0x180023d12  lea     r8, ?DispatchEvents@@YAXPEAXE@Z; Callback
0x180023d19  mov     rdx, rbx; hObject
0x180023d1c  mov     rcx, r14; phNewWaitObject
0x180023d1f  call    cs:__imp_RtlRegisterWait
0x180023d25  mov     [rsp+0A8h+var_68], eax
0x180023d29  test    eax, eax
0x180023d2b  js      loc_180023E92
0x180023d31  lea     rcx, [rsp+0A8h+var_40]
0x180023d36  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d42  lea     rax, WPP_GLOBAL_Control
0x180023d49  cmp     rcx, rax
0x180023d4c  jz      short loc_180023D69
0x180023d4e  test    byte ptr [rcx+1Ch], 8
0x180023d52  jz      short loc_180023D69
0x180023d54  mov     edx, 0Ch
0x180023d59  lea     r8, WPP_7b395475d90435087767593a55cc59de_Traceguids
0x180023d60  mov     rcx, [rcx+10h]
0x180023d64  call    WPP_SF_
0x180023d69  lea     rcx, [rdi+10h]; lpCriticalSection
0x180023d6d  call    cs:__imp_InitializeCriticalSection
0x180023d73  nop
0x180023d74  mov     rax, rdi
0x180023d77  lea     r11, [rsp+0A8h+var_28]
0x180023d7f  mov     rbx, [r11+40h]
0x180023d83  mov     rsi, [r11+48h]
0x180023d87  mov     rsp, r11
0x180023d8a  pop     r15
0x180023d8c  pop     r14
0x180023d8e  pop     r13
0x180023d90  pop     r12
0x180023d92  pop     rdi
0x180023d93  retn
0x180023d94  call    cs:__imp_CreateEventW
0x180023d9a  nop
0x180023d9b  mov     rbx, rax
0x180023d9e  test    rax, rax
0x180023da1  jz      loc_180023ED9
0x180023da7  mov     ecx, 10h; unsigned __int64
0x180023dac  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180023db1  test    rax, rax
0x180023db4  jz      short loc_180023DF5
0x180023db6  mov     [rax+8], r13
0x180023dba  mov     [rax], rbx
0x180023dbd  mov     [rdi+38h], rax
0x180023dc1  mov     [rsp+0A8h+bInheritHandle], r13d; ulFlags
0x180023dc6  mov     [rsp+0A8h+dwDesiredAccess], 0FFFFFFFFh; ulMilliseconds
0x180023dce  xor     r9d, r9d; pvContext
0x180023dd1  lea     r8, ?DispatchEvents@@YAXPEAXE@Z; Callback
0x180023dd8  mov     rdx, rbx; hObject
0x180023ddb  mov     rcx, r14; phNewWaitObject
0x180023dde  call    cs:__imp_RtlRegisterWait
0x180023de4  mov     [rsp+0A8h+var_68], eax
0x180023de8  test    eax, eax
0x180023dea  js      loc_180023EF3
0x180023df0  jmp     loc_180023D3B
0x180023df5  mov     [rdi+38h], r13
0x180023df9  mov     rcx, rbx; hObject
0x180023dfc  call    cs:__imp_CloseHandle
0x180023e02  mov     [rsp+0A8h+pExceptionObject], 8007000Eh
0x180023e0a  lea     rdx, _TI1J; pThrowInfo
0x180023e11  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180023e16  call    _CxxThrowException_0
0x180023e1b  call    cs:__imp_GetLastError
0x180023e21  mov     ebx, eax
0x180023e23  mov     [rsp+0A8h+var_68], eax
0x180023e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e2e  lea     rax, WPP_GLOBAL_Control
0x180023e35  cmp     rcx, rax
0x180023e38  jz      short loc_180023E55
0x180023e3a  test    byte ptr [rcx+1Ch], 8
0x180023e3e  jz      short loc_180023E55
0x180023e40  mov     edx, 0Bh
0x180023e45  lea     r8, WPP_7b395475d90435087767593a55cc59de_Traceguids
0x180023e4c  mov     rcx, [rcx+10h]
0x180023e50  call    WPP_SF_
0x180023e55  test    ebx, ebx
0x180023e57  jle     short loc_180023E62
0x180023e59  movzx   ebx, bx
0x180023e5c  or      ebx, 80070000h
0x180023e62  mov     [rsp+0A8h+var_64], ebx
0x180023e66  lea     rdx, _TI1J; pThrowInfo
0x180023e6d  lea     rcx, [rsp+0A8h+var_64]; pExceptionObject
0x180023e72  call    _CxxThrowException_0
0x180023e78  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180023e7d  mov     [rsp+0A8h+var_60], eax
0x180023e81  lea     rdx, _TI1J; pThrowInfo
0x180023e88  lea     rcx, [rsp+0A8h+var_60]; pExceptionObject
0x180023e8d  call    _CxxThrowException_0
0x180023e92  mov     ecx, eax; Status
0x180023e94  call    cs:__imp_RtlNtStatusToDosError
0x180023e9a  test    eax, eax
0x180023e9c  jle     short loc_180023EA6
0x180023e9e  movzx   eax, ax
0x180023ea1  or      eax, 80070000h
0x180023ea6  mov     [rsp+0A8h+var_5C], eax
0x180023eaa  lea     rdx, _TI1J; pThrowInfo
0x180023eb1  lea     rcx, [rsp+0A8h+var_5C]; pExceptionObject
0x180023eb6  call    _CxxThrowException_0
0x180023ebb  mov     [rdi+38h], r13
0x180023ebf  mov     [rsp+0A8h+var_58], 8007000Eh
0x180023ec7  lea     rdx, _TI1J; pThrowInfo
0x180023ece  lea     rcx, [rsp+0A8h+var_58]; pExceptionObject
0x180023ed3  call    _CxxThrowException_0
0x180023ed9  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180023ede  mov     [rsp+0A8h+var_54], eax
0x180023ee2  lea     rdx, _TI1J; pThrowInfo
0x180023ee9  lea     rcx, [rsp+0A8h+var_54]; pExceptionObject
0x180023eee  call    _CxxThrowException_0
0x180023ef3  mov     [rsp+0A8h+var_50], eax
0x180023ef7  lea     rdx, _TI1J; pThrowInfo
0x180023efe  lea     rcx, [rsp+0A8h+var_50]; pExceptionObject
0x180023f03  call    _CxxThrowException_0
```
