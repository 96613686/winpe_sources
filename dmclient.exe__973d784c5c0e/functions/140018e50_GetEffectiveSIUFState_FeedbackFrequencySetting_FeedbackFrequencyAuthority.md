# GetEffectiveSIUFState(FeedbackFrequencySetting *,FeedbackFrequencyAuthority *)

- ea: `0x140018e50`
- end: `0x140018fe2`
- name: `?GetEffectiveSIUFState@@YAJPEAW4FeedbackFrequencySetting@@PEAW4FeedbackFrequencyAuthority@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(enum FeedbackFrequencySetting *, enum FeedbackFrequencyAuthority *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x140018e50`
- `0x140018fe8`
- `0x140019128`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140018edf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140018edf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetEffectiveSIUFState(enum FeedbackFrequencySetting *a1, enum FeedbackFrequencyAuthority *a2)
{
  __int64 result; // rax
  int NotificationStateFromPolicy; // eax
  HRESULT v6; // ebx
  unsigned int v7; // eax
  int v8; // edi
  BOOL v9; // r15d
  LPVOID v10; // rcx
  __int16 v11; // ax
  LPVOID v12; // rcx
  int v13; // ebx
  int v14; // eax
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+40h] BYREF
  __int16 v17; // [rsp+90h] [rbp+50h] BYREF
  int v18; // [rsp+98h] [rbp+58h] BYREF

  v18 = 0;
  if ( !a1 )
    return 2147500035LL;
  v16 = 0;
  NotificationStateFromPolicy = GetNotificationStateFromPolicy(&v16);
  v6 = NotificationStateFromPolicy;
  if ( NotificationStateFromPolicy >= 0 )
  {
    v7 = v16;
  }
  else
  {
    if ( NotificationStateFromPolicy != -2147024894 && NotificationStateFromPolicy != -2147467263 )
      return (unsigned int)v6;
    v7 = 0;
  }
  v8 = 1;
  v9 = v7 == 1;
  v17 = 0;
  LOWORD(v16) = 0;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
  if ( v6 < 0 )
  {
    v10 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return (unsigned int)v6;
  }
  if ( (*(int (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, &v17) < 0 )
    v17 = 0;
  if ( (*(int (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 112LL))(ppv, &v16) >= 0 )
  {
    v11 = v16;
  }
  else
  {
    v11 = -1;
    LOWORD(v16) = -1;
  }
  if ( v17 != -1 && v11 )
    v8 = 0;
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v9 )
    v13 = 2;
  else
    v13 = v8 != 0;
  if ( v13 )
  {
    if ( v13 == 1 )
      v14 = 0;
    else
      v14 = 4;
  }
  else
  {
    result = GetLocalSiufState((enum FeedbackFrequencySetting *)&v18);
    if ( (int)result < 0 )
      return result;
    v14 = v18;
  }
  *(_DWORD *)a1 = v14;
  if ( a2 )
    *(_DWORD *)a2 = v13;
  return 0;
}

```

## disassembly

```asm
0x140018e50  push    rbp
0x140018e52  push    rbx
0x140018e53  push    rsi
0x140018e54  push    rdi
0x140018e55  push    r12
0x140018e57  push    r14
0x140018e59  push    r15
0x140018e5b  mov     rbp, rsp
0x140018e5e  sub     rsp, 40h
0x140018e62  mov     rsi, rdx
0x140018e65  mov     r14, rcx
0x140018e68  xor     r12d, r12d
0x140018e6b  mov     [rbp+arg_18], r12d
0x140018e6f  test    rcx, rcx
0x140018e72  jnz     short loc_140018E7E
0x140018e74  mov     eax, 80004003h
0x140018e79  jmp     loc_140018FD2
0x140018e7e  mov     [rbp+arg_0], r12d
0x140018e82  lea     rcx, [rbp+arg_0]; unsigned int *
0x140018e86  call    ?GetNotificationStateFromPolicy@@YAJPEAK@Z; GetNotificationStateFromPolicy(ulong *)
0x140018e8b  mov     ebx, eax
0x140018e8d  test    eax, eax
0x140018e8f  jns     short loc_140018EA4
0x140018e91  cmp     eax, 80070002h
0x140018e96  jz      short loc_140018E9F
0x140018e98  cmp     eax, 80004001h
0x140018e9d  jnz     short loc_140018F0B
0x140018e9f  mov     eax, r12d
0x140018ea2  jmp     short loc_140018EA7
0x140018ea4  mov     eax, [rbp+arg_0]
0x140018ea7  mov     r15d, r12d
0x140018eaa  mov     edi, 1
0x140018eaf  cmp     eax, edi
0x140018eb1  setz    r15b
0x140018eb5  mov     [rbp+arg_10], r12w
0x140018eba  mov     word ptr [rbp+arg_0], r12w
0x140018ebf  mov     [rbp+var_10], r12
0x140018ec3  lea     rax, [rbp+var_10]
0x140018ec7  mov     [rsp+40h+ppv], rax; ppv
0x140018ecc  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x140018ed3  mov     r8d, edi; dwClsContext
0x140018ed6  xor     edx, edx; pUnkOuter
0x140018ed8  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x140018edf  call    cs:__imp_CoCreateInstance
0x140018ee6  nop     dword ptr [rax+rax+00h]
0x140018eeb  mov     ebx, eax
0x140018eed  test    eax, eax
0x140018eef  jns     short loc_140018F12
0x140018ef1  mov     rcx, [rbp+var_10]
0x140018ef5  test    rcx, rcx
0x140018ef8  jz      short loc_140018F0B
0x140018efa  mov     [rbp+var_10], r12
0x140018efe  mov     rax, [rcx]
0x140018f01  mov     rax, [rax+10h]
0x140018f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f0a  nop
0x140018f0b  mov     eax, ebx
0x140018f0d  jmp     loc_140018FD2
0x140018f12  mov     rcx, [rbp+var_10]
0x140018f16  mov     rax, [rcx]
0x140018f19  lea     rdx, [rbp+arg_10]
0x140018f1d  mov     rax, [rax+18h]
0x140018f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f26  test    eax, eax
0x140018f28  jns     short loc_140018F2F
0x140018f2a  mov     [rbp+arg_10], r12w
0x140018f2f  mov     rcx, [rbp+var_10]
0x140018f33  mov     rax, [rcx]
0x140018f36  lea     rdx, [rbp+arg_0]
0x140018f3a  mov     rax, [rax+70h]
0x140018f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f43  or      ecx, 0FFFFFFFFh
0x140018f46  test    eax, eax
0x140018f48  jns     short loc_140018F53
0x140018f4a  movzx   eax, cx
0x140018f4d  mov     word ptr [rbp+arg_0], cx
0x140018f51  jmp     short loc_140018F57
0x140018f53  movzx   eax, word ptr [rbp+arg_0]
0x140018f57  cmp     [rbp+arg_10], cx
0x140018f5b  jz      short loc_140018F65
0x140018f5d  test    ax, ax
0x140018f60  jz      short loc_140018F65
0x140018f62  mov     edi, r12d
0x140018f65  mov     rcx, [rbp+var_10]
0x140018f69  test    rcx, rcx
0x140018f6c  jz      short loc_140018F7F
0x140018f6e  mov     [rbp+var_10], r12
0x140018f72  mov     rax, [rcx]
0x140018f75  mov     rax, [rax+10h]
0x140018f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f7e  nop
0x140018f7f  test    r15d, r15d
0x140018f82  jz      short loc_140018F8B
0x140018f84  mov     ebx, 2
0x140018f89  jmp     short loc_140018F93
0x140018f8b  mov     ebx, r12d
0x140018f8e  test    edi, edi
0x140018f90  setnz   bl
0x140018f93  mov     edx, ebx
0x140018f95  test    ebx, ebx
0x140018f97  jz      short loc_140018FB6
0x140018f99  sub     edx, 1
0x140018f9c  jz      short loc_140018FB1
0x140018f9e  cmp     edx, 1
0x140018fa1  jz      short loc_140018FAA
0x140018fa3  mov     eax, 80004001h
0x140018fa8  jmp     short loc_140018FD2
0x140018faa  mov     eax, 4
0x140018faf  jmp     short loc_140018FC6
0x140018fb1  mov     eax, r12d
0x140018fb4  jmp     short loc_140018FC6
0x140018fb6  lea     rcx, [rbp+arg_18]; enum FeedbackFrequencySetting *
0x140018fba  call    ?GetLocalSiufState@@YAJPEAW4FeedbackFrequencySetting@@@Z; GetLocalSiufState(FeedbackFrequencySetting *)
0x140018fbf  test    eax, eax
0x140018fc1  js      short loc_140018FD2
0x140018fc3  mov     eax, [rbp+arg_18]
0x140018fc6  mov     [r14], eax
0x140018fc9  test    rsi, rsi
0x140018fcc  jz      short loc_140018FD0
0x140018fce  mov     [rsi], ebx
0x140018fd0  xor     eax, eax
0x140018fd2  add     rsp, 40h
0x140018fd6  pop     r15
0x140018fd8  pop     r14
0x140018fda  pop     r12
0x140018fdc  pop     rdi
0x140018fdd  pop     rsi
0x140018fde  pop     rbx
0x140018fdf  pop     rbp
0x140018fe0  retn
```
