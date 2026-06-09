# GetCorSvcInstaller(void)

- ea: `0x140008010`
- end: `0x1400081a5`
- name: `?GetCorSvcInstaller@@YAPEAUICorSvcInstaller@@XZ`
- size: `405`
- prototype: `struct ICorSvcInstaller *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140008548`

## callees

- `0x140007f1c`
- `0x140008010`
- `0x14000e4f4`
- `0x140013f30`

## pseudocode

```c
struct ICorSvcInstaller *GetCorSvcInstaller(void)
{
  struct ICorSvc *CorService; // rsi
  int v1; // eax
  struct ICorSvc *v2; // rdi
  int v3; // eax
  __int64 v4; // rbx
  __int64 v6; // [rsp+28h] [rbp-38h] BYREF
  int v7; // [rsp+30h] [rbp-30h]
  struct ICorSvc *v8; // [rsp+38h] [rbp-28h] BYREF
  int v9; // [rsp+40h] [rbp-20h]
  struct ICorSvc *v10; // [rsp+48h] [rbp-18h]
  BOOL v11; // [rsp+50h] [rbp-10h]

  CorService = GetCorService();
  v10 = CorService;
  v11 = CorService != 0;
  v9 = 0;
  v8 = 0;
  v1 = (*(__int64 (__fastcall **)(struct ICorSvc *, struct ICorSvc **))(*(_QWORD *)CorService + 24LL))(CorService, &v8);
  if ( v1 < 0 )
    ThrowHR(v1);
  v2 = v8;
  v9 = 0;
  if ( CorService )
  {
    (*(void (__fastcall **)(struct ICorSvc *))(*(_QWORD *)CorService + 16LL))(CorService);
    v11 = 0;
  }
  v10 = v2;
  v11 = v2 != 0;
  v7 = 0;
  v6 = 0;
  v3 = (**(__int64 (__fastcall ***)(struct ICorSvc *, GUID *, __int64 *))v2)(v2, &IID_ICorSvcInstaller, &v6);
  if ( v3 < 0 )
    ThrowHR(v3);
  v7 = 0;
  (*(void (__fastcall **)(__int64, void ***))(*(_QWORD *)v6 + 48LL))(v6, off_1400270E0);
  v4 = v6;
  if ( v7 )
  {
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v7 = 0;
  }
  if ( v2 )
  {
    (*(void (__fastcall **)(struct ICorSvc *))(*(_QWORD *)v2 + 16LL))(v2);
    v11 = 0;
  }
  return (struct ICorSvcInstaller *)v4;
}

```

## disassembly

```asm
0x140008010  mov     [rsp-28h+arg_8], rbx
0x140008015  mov     [rsp-28h+arg_10], rsi
0x14000801a  push    rbp
0x14000801b  push    rdi
0x14000801c  push    r12
0x14000801e  push    r14
0x140008020  push    r15
0x140008022  mov     rbp, rsp
0x140008025  sub     rsp, 60h
0x140008029  xor     r15d, r15d
0x14000802c  mov     [rbp+var_40], r15d
0x140008030  call    ?GetCorService@@YAPEAUICorSvc@@XZ; GetCorService(void)
0x140008035  mov     rsi, rax
0x140008038  mov     [rbp+var_18], rax
0x14000803c  mov     [rbp+var_10], r15d
0x140008040  mov     r14d, r15d
0x140008043  lea     r12d, [r15+1]
0x140008047  test    rax, rax
0x14000804a  cmovnz  r14d, r12d
0x14000804e  mov     [rbp+var_10], r14d
0x140008052  mov     [rbp+var_28], r15
0x140008056  mov     [rbp+var_20], r15d
0x14000805a  lea     rax, [rbp+var_28]
0x14000805e  mov     [rbp+arg_0], rax
0x140008062  mov     [rbp+var_28], r15
0x140008066  mov     [rbp+var_40], r12d
0x14000806a  mov     rax, [rsi]
0x14000806d  lea     rdx, [rbp+var_28]
0x140008071  mov     rcx, rsi
0x140008074  mov     rax, [rax+18h]
0x140008078  call    cs:__guard_dispatch_icall_fptr
0x14000807e  test    eax, eax
0x140008080  js      loc_14000819D
0x140008086  mov     ebx, r12d
0x140008089  and     ebx, 0FFFFFFFEh
0x14000808c  mov     [rbp+var_40], ebx
0x14000808f  mov     eax, [rbp+var_20]
0x140008092  mov     rdi, [rbp+var_28]
0x140008096  test    rdi, rdi
0x140008099  cmovnz  eax, r12d
0x14000809d  mov     [rbp+var_20], eax
0x1400080a0  mov     [rbp+var_20], r15d
0x1400080a4  test    r14d, r14d
0x1400080a7  jz      short loc_1400080BD
0x1400080a9  mov     rax, [rsi]
0x1400080ac  mov     rcx, rsi
0x1400080af  mov     rax, [rax+10h]
0x1400080b3  call    cs:__guard_dispatch_icall_fptr
0x1400080b9  mov     [rbp+var_10], r15d
0x1400080bd  mov     [rbp+var_18], rdi
0x1400080c1  mov     [rbp+var_10], r15d
0x1400080c5  mov     esi, r15d
0x1400080c8  test    rdi, rdi
0x1400080cb  cmovnz  esi, r12d
0x1400080cf  mov     [rbp+var_10], esi
0x1400080d2  mov     [rbp+var_38], r15
0x1400080d6  mov     [rbp+var_30], r15d
0x1400080da  lea     rax, [rbp+var_38]
0x1400080de  mov     [rbp+arg_0], rax
0x1400080e2  mov     [rbp+var_38], r15
0x1400080e6  or      ebx, 2
0x1400080e9  mov     [rbp+var_40], ebx
0x1400080ec  mov     rax, [rdi]
0x1400080ef  lea     r8, [rbp+var_38]
0x1400080f3  lea     rdx, IID_ICorSvcInstaller
0x1400080fa  mov     rcx, rdi
0x1400080fd  mov     rax, [rax]
0x140008100  call    cs:__guard_dispatch_icall_fptr
0x140008106  test    eax, eax
0x140008108  js      loc_140008195
0x14000810e  and     ebx, 0FFFFFFFDh
0x140008111  mov     [rbp+var_40], ebx
0x140008114  mov     eax, [rbp+var_30]
0x140008117  mov     rcx, [rbp+var_38]
0x14000811b  test    rcx, rcx
0x14000811e  cmovnz  eax, r12d
0x140008122  mov     [rbp+var_30], eax
0x140008125  mov     [rbp+var_30], r15d
0x140008129  mov     rax, [rcx]
0x14000812c  lea     rdx, off_1400270E0
0x140008133  mov     rax, [rax+30h]
0x140008137  call    cs:__guard_dispatch_icall_fptr
0x14000813d  mov     rbx, [rbp+var_38]
0x140008141  cmp     [rbp+var_30], r15d
0x140008145  jz      short loc_140008161
0x140008147  mov     rcx, [rbp+var_38]
0x14000814b  test    rcx, rcx
0x14000814e  jz      short loc_14000815D
0x140008150  mov     rax, [rcx]
0x140008153  mov     rax, [rax+10h]
0x140008157  call    cs:__guard_dispatch_icall_fptr
0x14000815d  mov     [rbp+var_30], r15d
0x140008161  test    esi, esi
0x140008163  jz      short loc_140008179
0x140008165  mov     rdx, [rdi]
0x140008168  mov     rcx, rdi
0x14000816b  mov     rax, [rdx+10h]
0x14000816f  call    cs:__guard_dispatch_icall_fptr
0x140008175  mov     [rbp+var_10], r15d
0x140008179  mov     rax, rbx
0x14000817c  lea     r11, [rsp+60h+var_s0]
0x140008181  mov     rbx, [r11+38h]
0x140008185  mov     rsi, [r11+40h]
0x140008189  mov     rsp, r11
0x14000818c  pop     r15
0x14000818e  pop     r14
0x140008190  pop     r12
0x140008192  pop     rdi
0x140008193  pop     rbp
0x140008194  retn
0x140008195  mov     ecx, eax; int
0x140008197  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x14000819d  mov     ecx, eax; int
0x14000819f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
