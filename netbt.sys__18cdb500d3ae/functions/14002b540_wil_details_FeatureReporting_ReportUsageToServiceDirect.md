# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14002b540`
- end: `0x14002b61a`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14002b4b8`

## callees

- `0x14002b334`
- `0x14002b540`
- `0x140030f40`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14002b5ec`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x14002b5ec`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int *v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *((_QWORD *)v6 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x14002b540  push    rbx
0x14002b542  push    rbp
0x14002b543  push    rsi
0x14002b544  push    rdi
0x14002b545  push    r14
0x14002b547  sub     rsp, 70h
0x14002b54b  mov     rax, cs:__security_cookie
0x14002b552  xor     rax, rsp
0x14002b555  mov     [rsp+98h+var_30], rax
0x14002b55a  mov     r9, rdx
0x14002b55d  mov     rbx, rdx
0x14002b560  mov     rdx, [rcx+8]
0x14002b564  mov     rbp, rcx
0x14002b567  shr     r9, 20h
0x14002b56b  lea     rcx, [rsp+98h+var_60]
0x14002b570  mov     esi, r8d
0x14002b573  call    wil_details_FeatureReporting_RecordUsageInCache
0x14002b578  mov     r14d, 1
0x14002b57e  movups  xmm1, xmmword ptr [rax]
0x14002b581  movups  [rsp+98h+var_48], xmm1
0x14002b586  movsd   xmm0, qword ptr [rax+10h]
0x14002b58b  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14002b592  movsd   [rsp+98h+var_38], xmm0
0x14002b598  test    rax, rax
0x14002b59b  jz      short loc_14002B5B8
0x14002b59d  mov     r9, [rbp+8]
0x14002b5a1  lea     rcx, [rsp+98h+var_48]
0x14002b5a6  mov     [rsp+98h+var_78], rcx
0x14002b5ab  mov     r8d, r14d
0x14002b5ae  mov     ecx, [rbp+18h]
0x14002b5b1  mov     edx, esi
0x14002b5b3  call    _guard_dispatch_icall
0x14002b5b8  bt      ebx, 0Ah
0x14002b5bc  jnb     short loc_14002B5F8
0x14002b5be  cmp     esi, 0FEh
0x14002b5c4  jz      short loc_14002B5F8
0x14002b5c6  mov     eax, [rbp+18h]
0x14002b5c9  mov     [rsp+98h+var_68], 0
0x14002b5d2  mov     dword ptr [rsp+98h+var_68], eax
0x14002b5d6  mov     word ptr [rsp+98h+var_68+4], si
0x14002b5db  bt      ebx, 0Bh
0x14002b5df  jnb     short loc_14002B5E7
0x14002b5e1  or      word ptr [rsp+98h+var_68+6], r14w
0x14002b5e7  lea     rcx, [rsp+98h+var_68]
0x14002b5ec  call    cs:__imp_RtlNotifyFeatureUsage
0x14002b5f3  nop     dword ptr [rax+rax+00h]
0x14002b5f8  xor     eax, eax
0x14002b5fa  cmp     dword ptr [rsp+98h+var_38], eax
0x14002b5fe  setz    al
0x14002b601  mov     rcx, [rsp+98h+var_30]
0x14002b606  xor     rcx, rsp; StackCookie
0x14002b609  call    __security_check_cookie
0x14002b60e  add     rsp, 70h
0x14002b612  pop     r14
0x14002b614  pop     rdi
0x14002b615  pop     rsi
0x14002b616  pop     rbp
0x14002b617  pop     rbx
0x14002b618  retn
```
