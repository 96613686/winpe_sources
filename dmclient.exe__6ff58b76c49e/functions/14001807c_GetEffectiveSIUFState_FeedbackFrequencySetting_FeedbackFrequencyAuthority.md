# GetEffectiveSIUFState(FeedbackFrequencySetting *,FeedbackFrequencyAuthority *)

- ea: `0x14001807c`
- end: `0x140018207`
- name: `?GetEffectiveSIUFState@@YAJPEAW4FeedbackFrequencySetting@@PEAW4FeedbackFrequencyAuthority@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(enum FeedbackFrequencySetting *, enum FeedbackFrequencyAuthority *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000c47c`

## callees

- `0x14001807c`
- `0x140018210`
- `0x140018344`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001810b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001810b`

## pseudocode

```c
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
0x14001807c  push    rbp
0x14001807e  push    rbx
0x14001807f  push    rsi
0x140018080  push    rdi
0x140018081  push    r12
0x140018083  push    r14
0x140018085  push    r15
0x140018087  mov     rbp, rsp
0x14001808a  sub     rsp, 40h
0x14001808e  mov     rsi, rdx
0x140018091  mov     r14, rcx
0x140018094  xor     r12d, r12d
0x140018097  mov     [rbp+arg_18], r12d
0x14001809b  test    rcx, rcx
0x14001809e  jnz     short loc_1400180AA
0x1400180a0  mov     eax, 80004003h
0x1400180a5  jmp     loc_1400181F8
0x1400180aa  mov     [rbp+arg_0], r12d
0x1400180ae  lea     rcx, [rbp+arg_0]; unsigned int *
0x1400180b2  call    ?GetNotificationStateFromPolicy@@YAJPEAK@Z; GetNotificationStateFromPolicy(ulong *)
0x1400180b7  mov     ebx, eax
0x1400180b9  test    eax, eax
0x1400180bb  jns     short loc_1400180D0
0x1400180bd  cmp     eax, 80070002h
0x1400180c2  jz      short loc_1400180CB
0x1400180c4  cmp     eax, 80004001h
0x1400180c9  jnz     short loc_140018131
0x1400180cb  mov     eax, r12d
0x1400180ce  jmp     short loc_1400180D3
0x1400180d0  mov     eax, [rbp+arg_0]
0x1400180d3  mov     r15d, r12d
0x1400180d6  mov     edi, 1
0x1400180db  cmp     eax, edi
0x1400180dd  setz    r15b
0x1400180e1  mov     [rbp+arg_10], r12w
0x1400180e6  mov     word ptr [rbp+arg_0], r12w
0x1400180eb  mov     [rbp+var_10], r12
0x1400180ef  lea     rax, [rbp+var_10]
0x1400180f3  mov     [rsp+40h+ppv], rax; ppv
0x1400180f8  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x1400180ff  mov     r8d, edi; dwClsContext
0x140018102  xor     edx, edx; pUnkOuter
0x140018104  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x14001810b  call    cs:__imp_CoCreateInstance
0x140018111  mov     ebx, eax
0x140018113  test    eax, eax
0x140018115  jns     short loc_140018138
0x140018117  mov     rcx, [rbp+var_10]
0x14001811b  test    rcx, rcx
0x14001811e  jz      short loc_140018131
0x140018120  mov     [rbp+var_10], r12
0x140018124  mov     rax, [rcx]
0x140018127  mov     rax, [rax+10h]
0x14001812b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018130  nop
0x140018131  mov     eax, ebx
0x140018133  jmp     loc_1400181F8
0x140018138  mov     rcx, [rbp+var_10]
0x14001813c  mov     rax, [rcx]
0x14001813f  lea     rdx, [rbp+arg_10]
0x140018143  mov     rax, [rax+18h]
0x140018147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001814c  test    eax, eax
0x14001814e  jns     short loc_140018155
0x140018150  mov     [rbp+arg_10], r12w
0x140018155  mov     rcx, [rbp+var_10]
0x140018159  mov     rax, [rcx]
0x14001815c  lea     rdx, [rbp+arg_0]
0x140018160  mov     rax, [rax+70h]
0x140018164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018169  or      ecx, 0FFFFFFFFh
0x14001816c  test    eax, eax
0x14001816e  jns     short loc_140018179
0x140018170  movzx   eax, cx
0x140018173  mov     word ptr [rbp+arg_0], cx
0x140018177  jmp     short loc_14001817D
0x140018179  movzx   eax, word ptr [rbp+arg_0]
0x14001817d  cmp     [rbp+arg_10], cx
0x140018181  jz      short loc_14001818B
0x140018183  test    ax, ax
0x140018186  jz      short loc_14001818B
0x140018188  mov     edi, r12d
0x14001818b  mov     rcx, [rbp+var_10]
0x14001818f  test    rcx, rcx
0x140018192  jz      short loc_1400181A5
0x140018194  mov     [rbp+var_10], r12
0x140018198  mov     rax, [rcx]
0x14001819b  mov     rax, [rax+10h]
0x14001819f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181a4  nop
0x1400181a5  test    r15d, r15d
0x1400181a8  jz      short loc_1400181B1
0x1400181aa  mov     ebx, 2
0x1400181af  jmp     short loc_1400181B9
0x1400181b1  mov     ebx, r12d
0x1400181b4  test    edi, edi
0x1400181b6  setnz   bl
0x1400181b9  mov     edx, ebx
0x1400181bb  test    ebx, ebx
0x1400181bd  jz      short loc_1400181DC
0x1400181bf  sub     edx, 1
0x1400181c2  jz      short loc_1400181D7
0x1400181c4  cmp     edx, 1
0x1400181c7  jz      short loc_1400181D0
0x1400181c9  mov     eax, 80004001h
0x1400181ce  jmp     short loc_1400181F8
0x1400181d0  mov     eax, 4
0x1400181d5  jmp     short loc_1400181EC
0x1400181d7  mov     eax, r12d
0x1400181da  jmp     short loc_1400181EC
0x1400181dc  lea     rcx, [rbp+arg_18]; enum FeedbackFrequencySetting *
0x1400181e0  call    ?GetLocalSiufState@@YAJPEAW4FeedbackFrequencySetting@@@Z; GetLocalSiufState(FeedbackFrequencySetting *)
0x1400181e5  test    eax, eax
0x1400181e7  js      short loc_1400181F8
0x1400181e9  mov     eax, [rbp+arg_18]
0x1400181ec  mov     [r14], eax
0x1400181ef  test    rsi, rsi
0x1400181f2  jz      short loc_1400181F6
0x1400181f4  mov     [rsi], ebx
0x1400181f6  xor     eax, eax
0x1400181f8  add     rsp, 40h
0x1400181fc  pop     r15
0x1400181fe  pop     r14
0x140018200  pop     r12
0x140018202  pop     rdi
0x140018203  pop     rsi
0x140018204  pop     rbx
0x140018205  pop     rbp
0x140018206  retn
```
