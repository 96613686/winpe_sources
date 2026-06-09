# CEdpNotificationTaskHandler::ShowToast(EdpToastType)

- ea: `0x180005e44`
- end: `0x1800060bf`
- name: `?ShowToast@CEdpNotificationTaskHandler@@AEAAJW4EdpToastType@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180006570`

## callees

- `0x180005e44`
- `0x180007b10`
- `0x180008310`
- `0x18000ac1c`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006063`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006063`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005fde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005fde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ee3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ee3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ef2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ef2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000604c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000604c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006034`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180006034`
- `ntdll!RtlNtStatusToDosError` at `0x180005ec0`
- `ntdll!RtlNtStatusToDosError` at `0x180005f2b`
- `ntdll!RtlNtStatusToDosError` at `0x180005ec0`
- `ntdll!RtlNtStatusToDosError` at `0x180005f2b`
- `ntdll!NtQueryWnfStateData` at `0x180005ea5`
- `ntdll!NtQueryWnfStateData` at `0x180005f1f`
- `ntdll!NtQueryWnfStateData` at `0x180005ea5`
- `ntdll!NtQueryWnfStateData` at `0x180005f1f`

## pseudocode

```c
__int64 __fastcall CEdpNotificationTaskHandler::ShowToast(__int64 a1, int a2)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  unsigned int EdpToast; // edi
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  NTSTATUS v8; // eax
  signed int v9; // eax
  HANDLE v10; // rax
  __int64 v11; // rcx
  SIZE_T dwBytes; // [rsp+30h] [rbp-19h] BYREF
  void **v14; // [rsp+38h] [rbp-11h] BYREF
  __int64 v15; // [rsp+40h] [rbp-9h]
  _QWORD v16[3]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v17; // [rsp+60h] [rbp+17h] BYREF
  GUID ProviderId; // [rsp+68h] [rbp+1Fh] BYREF

  dwBytes = 0;
  switch ( a2 )
  {
    case 1:
      v17 = WNF_EDP_AAD_REAUTH_REQUIRED;
      v2 = NtQueryWnfStateData(&v17, 0, 0, (char *)&dwBytes + 4, 0, &dwBytes);
      if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741789 )
      {
        EdpToast = 0;
        v5 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v7 = HeapAlloc(ProcessHeap, 8u, v5);
        if ( v7 )
        {
          v8 = NtQueryWnfStateData(&v17, 0, 0, (char *)&dwBytes + 4, v7, &dwBytes);
          if ( v8 >= 0 )
          {
            if ( HIDWORD(dwBytes) )
              EdpToast = CreateEdpToast(1, v7, (unsigned int)dwBytes);
            else
              EdpToast = 1;
          }
          else
          {
            v9 = RtlNtStatusToDosError(v8);
            EdpToast = v9;
            if ( v9 > 0 )
              EdpToast = (unsigned __int16)v9 | 0x80070000;
          }
          v10 = GetProcessHeap();
          HeapFree(v10, 0, v7);
        }
      }
      else
      {
        v3 = RtlNtStatusToDosError(v2);
        EdpToast = v3;
        if ( v3 > 0 )
          return (unsigned __int16)v3 | 0x80070000;
      }
      break;
    case 2:
      v17 = WNF_EDP_MISSING_CREDENTIALS;
      return (unsigned int)CreateEdpToast(2, 0, 0);
    case 3:
      v15 = 0;
      v14 = &BitLockerToast::`vftable';
      v16[0] = &g_hBitLockerSilentProvider;
      v16[1] = &g_bitLockerSilentProviderInitLock;
      v16[2] = &g_bitLockerSilentProviderRefCount;
      AcquireSRWLockExclusive(&g_bitLockerSilentProviderInitLock);
      if ( !g_bitLockerSilentProviderRefCount )
      {
        ProviderId = *(GUID *)(*((_QWORD *)g_hBitLockerSilentProvider + 1) - 16LL);
        if ( *((_QWORD *)g_hBitLockerSilentProvider + 4) )
          __fastfail(5u);
        *((_QWORD *)g_hBitLockerSilentProvider + 5) = 0;
        *((_QWORD *)g_hBitLockerSilentProvider + 6) = 0;
        if ( !EventRegister(
                &ProviderId,
                tlgEnableCallback,
                g_hBitLockerSilentProvider,
                (PREGHANDLE)g_hBitLockerSilentProvider + 4) )
          EventSetInformation(
            *((_QWORD *)g_hBitLockerSilentProvider + 4),
            2,
            *((_QWORD *)g_hBitLockerSilentProvider + 1),
            **((unsigned __int16 **)g_hBitLockerSilentProvider + 1));
      }
      ++g_bitLockerSilentProviderRefCount;
      ReleaseSRWLockExclusive(&g_bitLockerSilentProviderInitLock);
      EdpToast = EdpToast::LaunchToast((EdpToast *)&v14);
      TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v16);
      v11 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      break;
    default:
      return (unsigned int)-2147024809;
  }
  return EdpToast;
}

```

## disassembly

```asm
0x180005e44  push    rbp
0x180005e46  push    rbx
0x180005e47  push    rdi
0x180005e48  push    r12
0x180005e4a  lea     rbp, [rsp-3Fh]
0x180005e4f  sub     rsp, 88h
0x180005e56  mov     rax, cs:__security_cookie
0x180005e5d  xor     rax, rsp
0x180005e60  mov     [rbp+57h+var_28], rax
0x180005e64  mov     dword ptr [rbp+57h+dwBytes+4], 0
0x180005e6b  mov     dword ptr [rbp+57h+dwBytes], 0
0x180005e72  cmp     edx, 1
0x180005e75  jnz     loc_180005F7A
0x180005e7b  mov     rax, cs:WNF_EDP_AAD_REAUTH_REQUIRED
0x180005e82  mov     [rbp+57h+var_40], rax
0x180005e86  lea     rax, [rbp+57h+dwBytes]
0x180005e8a  mov     [rsp+0A0h+var_78], rax
0x180005e8f  mov     [rsp+0A0h+var_80], 0
0x180005e98  lea     r9, [rbp+57h+dwBytes+4]
0x180005e9c  xor     r8d, r8d
0x180005e9f  xor     edx, edx
0x180005ea1  lea     rcx, [rbp+57h+var_40]
0x180005ea5  call    cs:__imp_NtQueryWnfStateData
0x180005eab  mov     edx, 80000000h
0x180005eb0  lea     ecx, [rax+rdx]
0x180005eb3  test    edx, ecx
0x180005eb5  jnz     short loc_180005EDE
0x180005eb7  cmp     eax, 0C0000023h
0x180005ebc  jz      short loc_180005EDE
0x180005ebe  mov     ecx, eax; Status
0x180005ec0  call    cs:__imp_RtlNtStatusToDosError
0x180005ec6  mov     edi, eax
0x180005ec8  test    eax, eax
0x180005eca  jle     loc_1800060A4
0x180005ed0  movzx   edi, ax
0x180005ed3  or      edi, 80070000h
0x180005ed9  jmp     loc_1800060A4
0x180005ede  xor     edi, edi
0x180005ee0  mov     ebx, dword ptr [rbp+57h+dwBytes]
0x180005ee3  call    cs:__imp_GetProcessHeap
0x180005ee9  mov     r8d, ebx; dwBytes
0x180005eec  lea     edx, [rdi+8]; dwFlags
0x180005eef  mov     rcx, rax; hHeap
0x180005ef2  call    cs:__imp_HeapAlloc
0x180005ef8  mov     rbx, rax
0x180005efb  test    rax, rax
0x180005efe  jz      loc_1800060A4
0x180005f04  lea     rax, [rbp+57h+dwBytes]
0x180005f08  mov     [rsp+0A0h+var_78], rax
0x180005f0d  mov     [rsp+0A0h+var_80], rbx
0x180005f12  lea     r9, [rbp+57h+dwBytes+4]
0x180005f16  xor     r8d, r8d
0x180005f19  xor     edx, edx
0x180005f1b  lea     rcx, [rbp+57h+var_40]
0x180005f1f  call    cs:__imp_NtQueryWnfStateData
0x180005f25  test    eax, eax
0x180005f27  jns     short loc_180005F42
0x180005f29  mov     ecx, eax; Status
0x180005f2b  call    cs:__imp_RtlNtStatusToDosError
0x180005f31  mov     edi, eax
0x180005f33  test    eax, eax
0x180005f35  jle     short loc_180005F61
0x180005f37  movzx   edi, ax
0x180005f3a  or      edi, 80070000h
0x180005f40  jmp     short loc_180005F61
0x180005f42  cmp     dword ptr [rbp+57h+dwBytes+4], edi
0x180005f45  jnz     short loc_180005F4E
0x180005f47  mov     edi, 1
0x180005f4c  jmp     short loc_180005F61
0x180005f4e  mov     r8d, dword ptr [rbp+57h+dwBytes]
0x180005f52  mov     rdx, rbx
0x180005f55  mov     ecx, 1
0x180005f5a  call    ?CreateEdpToast@@YAJW4EdpToastType@@QEAEK@Z; CreateEdpToast(EdpToastType,uchar * const,ulong)
0x180005f5f  mov     edi, eax
0x180005f61  call    cs:__imp_GetProcessHeap
0x180005f67  mov     rcx, rax; hHeap
0x180005f6a  mov     r8, rbx; lpMem
0x180005f6d  xor     edx, edx; dwFlags
0x180005f6f  call    cs:__imp_HeapFree
0x180005f75  jmp     loc_1800060A4
0x180005f7a  cmp     edx, 2
0x180005f7d  jnz     short loc_180005F9E
0x180005f7f  mov     rax, cs:WNF_EDP_MISSING_CREDENTIALS
0x180005f86  mov     [rbp+57h+var_40], rax
0x180005f8a  xor     r8d, r8d
0x180005f8d  xor     edx, edx
0x180005f8f  lea     ecx, [rdx+2]
0x180005f92  call    ?CreateEdpToast@@YAJW4EdpToastType@@QEAEK@Z; CreateEdpToast(EdpToastType,uchar * const,ulong)
0x180005f97  mov     edi, eax
0x180005f99  jmp     loc_1800060A4
0x180005f9e  cmp     edx, 3
0x180005fa1  jnz     loc_18000609F
0x180005fa7  mov     [rbp+57h+var_60], 0
0x180005faf  lea     rax, ??_7BitLockerToast@@6B@; const BitLockerToast::`vftable'
0x180005fb6  mov     [rbp+57h+var_68], rax
0x180005fba  lea     rax, g_hBitLockerSilentProvider
0x180005fc1  mov     [rbp+57h+var_58], rax
0x180005fc5  lea     r12, ?g_bitLockerSilentProviderInitLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_bitLockerSilentProviderInitLock
0x180005fcc  mov     [rbp+57h+var_50], r12
0x180005fd0  lea     rax, ?g_bitLockerSilentProviderRefCount@@3JC; long volatile g_bitLockerSilentProviderRefCount
0x180005fd7  mov     [rbp+57h+var_48], rax
0x180005fdb  mov     rcx, r12; SRWLock
0x180005fde  call    cs:__imp_AcquireSRWLockExclusive
0x180005fe4  mov     eax, cs:?g_bitLockerSilentProviderRefCount@@3JC; long volatile g_bitLockerSilentProviderRefCount
0x180005fea  test    eax, eax
0x180005fec  jnz     short loc_180006052
0x180005fee  mov     rbx, cs:g_hBitLockerSilentProvider
0x180005ff5  mov     rax, [rbx+8]
0x180005ff9  movups  xmm0, xmmword ptr [rax-10h]
0x180005ffd  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x180006002  lea     rdi, [rbx+20h]
0x180006006  cmp     qword ptr [rdi], 0
0x18000600a  jz      short loc_180006013
0x18000600c  mov     ecx, 5
0x180006011  int     29h; Win8: RtlFailFast(ecx)
0x180006013  mov     qword ptr [rbx+28h], 0
0x18000601b  mov     qword ptr [rbx+30h], 0
0x180006023  mov     r9, rdi; RegHandle
0x180006026  mov     r8, rbx; CallbackContext
0x180006029  lea     rdx, _tlgEnableCallback; EnableCallback
0x180006030  lea     rcx, [rbp+57h+ProviderId]; ProviderId
0x180006034  call    cs:__imp_EventRegister
0x18000603a  test    eax, eax
0x18000603c  jnz     short loc_180006052
0x18000603e  mov     r8, [rbx+8]
0x180006042  movzx   r9d, word ptr [r8]
0x180006046  lea     edx, [rax+2]
0x180006049  mov     rcx, [rdi]
0x18000604c  call    cs:__imp_EventSetInformation
0x180006052  mov     eax, cs:?g_bitLockerSilentProviderRefCount@@3JC; long volatile g_bitLockerSilentProviderRefCount
0x180006058  inc     eax
0x18000605a  mov     cs:?g_bitLockerSilentProviderRefCount@@3JC, eax; long volatile g_bitLockerSilentProviderRefCount
0x180006060  mov     rcx, r12; SRWLock
0x180006063  call    cs:__imp_ReleaseSRWLockExclusive
0x180006069  nop
0x18000606a  lea     rcx, [rbp+57h+var_68]; this
0x18000606e  call    ?LaunchToast@EdpToast@@QEAAJXZ; EdpToast::LaunchToast(void)
0x180006073  mov     edi, eax
0x180006075  lea     rcx, [rbp+57h+var_58]; this
0x180006079  call    ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
0x18000607e  nop
0x18000607f  mov     rcx, [rbp+57h+var_60]
0x180006083  test    rcx, rcx
0x180006086  jz      short loc_18000609D
0x180006088  mov     [rbp+57h+var_60], 0
0x180006090  mov     rax, [rcx]
0x180006093  mov     rax, [rax+10h]
0x180006097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609c  nop
0x18000609d  jmp     short loc_1800060A4
0x18000609f  mov     edi, 80070057h
0x1800060a4  mov     eax, edi
0x1800060a6  mov     rcx, [rbp+57h+var_28]
0x1800060aa  xor     rcx, rsp; StackCookie
0x1800060ad  call    __security_check_cookie
0x1800060b2  add     rsp, 88h
0x1800060b9  pop     r12
0x1800060bb  pop     rdi
0x1800060bc  pop     rbx
0x1800060bd  pop     rbp
0x1800060be  retn
```
