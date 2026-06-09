# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140002af8`
- end: `0x140002bd2`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002a70`

## callees

- `0x1400028ec`
- `0x140002af8`
- `0x140005f30`
- `0x140006010`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140002ba4`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140002ba4`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v5; // esi
  _DWORD *v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *((_QWORD *)v6 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), v5, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x140002af8  push    rbx
0x140002afa  push    rbp
0x140002afb  push    rsi
0x140002afc  push    rdi
0x140002afd  push    r14
0x140002aff  sub     rsp, 70h
0x140002b03  mov     rax, cs:__security_cookie
0x140002b0a  xor     rax, rsp
0x140002b0d  mov     [rsp+98h+var_30], rax
0x140002b12  mov     r9, rdx
0x140002b15  mov     rbx, rdx
0x140002b18  mov     rdx, [rcx+8]
0x140002b1c  mov     rbp, rcx
0x140002b1f  shr     r9, 20h
0x140002b23  lea     rcx, [rsp+98h+var_60]
0x140002b28  mov     esi, r8d
0x140002b2b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140002b30  mov     r14d, 1
0x140002b36  movups  xmm1, xmmword ptr [rax]
0x140002b39  movups  [rsp+98h+var_48], xmm1
0x140002b3e  movsd   xmm0, qword ptr [rax+10h]
0x140002b43  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140002b4a  movsd   [rsp+98h+var_38], xmm0
0x140002b50  test    rax, rax
0x140002b53  jz      short loc_140002B70
0x140002b55  mov     r9, [rbp+8]
0x140002b59  lea     rcx, [rsp+98h+var_48]
0x140002b5e  mov     [rsp+98h+var_78], rcx
0x140002b63  mov     r8d, r14d
0x140002b66  mov     ecx, [rbp+18h]
0x140002b69  mov     edx, esi
0x140002b6b  call    _guard_dispatch_icall
0x140002b70  bt      ebx, 0Ah
0x140002b74  jnb     short loc_140002BB0
0x140002b76  cmp     esi, 0FEh
0x140002b7c  jz      short loc_140002BB0
0x140002b7e  mov     eax, [rbp+18h]
0x140002b81  mov     [rsp+98h+var_68], 0
0x140002b8a  mov     dword ptr [rsp+98h+var_68], eax
0x140002b8e  mov     word ptr [rsp+98h+var_68+4], si
0x140002b93  bt      ebx, 0Bh
0x140002b97  jnb     short loc_140002B9F
0x140002b99  or      word ptr [rsp+98h+var_68+6], r14w
0x140002b9f  lea     rcx, [rsp+98h+var_68]
0x140002ba4  call    cs:__imp_RtlNotifyFeatureUsage
0x140002bab  nop     dword ptr [rax+rax+00h]
0x140002bb0  xor     eax, eax
0x140002bb2  cmp     dword ptr [rsp+98h+var_38], eax
0x140002bb6  setz    al
0x140002bb9  mov     rcx, [rsp+98h+var_30]
0x140002bbe  xor     rcx, rsp; StackCookie
0x140002bc1  call    __security_check_cookie
0x140002bc6  add     rsp, 70h
0x140002bca  pop     r14
0x140002bcc  pop     rdi
0x140002bcd  pop     rsi
0x140002bce  pop     rbp
0x140002bcf  pop     rbx
0x140002bd0  retn
```
