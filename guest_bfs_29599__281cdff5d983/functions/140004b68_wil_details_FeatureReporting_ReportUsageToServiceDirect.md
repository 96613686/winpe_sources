# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140004b68`
- end: `0x140004c42`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002350`
- `0x140004ae0`

## callees

- `0x14000495c`
- `0x140004b68`
- `0x140013860`
- `0x1400138a0`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140004c14`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140004c14`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v5; // esi
  __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(v10, *(_QWORD *)(a1 + 8), a3, HIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *(_QWORD *)(v6 + 16);
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
0x140004b68  push    rbx
0x140004b6a  push    rbp
0x140004b6b  push    rsi
0x140004b6c  push    rdi
0x140004b6d  push    r14
0x140004b6f  sub     rsp, 70h
0x140004b73  mov     rax, cs:__security_cookie
0x140004b7a  xor     rax, rsp
0x140004b7d  mov     [rsp+98h+var_30], rax
0x140004b82  mov     r9, rdx
0x140004b85  mov     rbx, rdx
0x140004b88  mov     rdx, [rcx+8]
0x140004b8c  mov     rbp, rcx
0x140004b8f  shr     r9, 20h
0x140004b93  lea     rcx, [rsp+98h+var_60]
0x140004b98  mov     esi, r8d
0x140004b9b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140004ba0  mov     r14d, 1
0x140004ba6  movups  xmm1, xmmword ptr [rax]
0x140004ba9  movups  [rsp+98h+var_48], xmm1
0x140004bae  movsd   xmm0, qword ptr [rax+10h]
0x140004bb3  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140004bba  movsd   [rsp+98h+var_38], xmm0
0x140004bc0  test    rax, rax
0x140004bc3  jz      short loc_140004BE0
0x140004bc5  mov     r9, [rbp+8]
0x140004bc9  lea     rcx, [rsp+98h+var_48]
0x140004bce  mov     [rsp+98h+var_78], rcx
0x140004bd3  mov     r8d, r14d
0x140004bd6  mov     ecx, [rbp+18h]
0x140004bd9  mov     edx, esi
0x140004bdb  call    _guard_dispatch_icall
0x140004be0  bt      ebx, 0Ah
0x140004be4  jnb     short loc_140004C20
0x140004be6  cmp     esi, 0FEh
0x140004bec  jz      short loc_140004C20
0x140004bee  mov     eax, [rbp+18h]
0x140004bf1  mov     [rsp+98h+var_68], 0
0x140004bfa  mov     dword ptr [rsp+98h+var_68], eax
0x140004bfe  mov     word ptr [rsp+98h+var_68+4], si
0x140004c03  bt      ebx, 0Bh
0x140004c07  jnb     short loc_140004C0F
0x140004c09  or      word ptr [rsp+98h+var_68+6], r14w
0x140004c0f  lea     rcx, [rsp+98h+var_68]
0x140004c14  call    cs:__imp_RtlNotifyFeatureUsage
0x140004c1b  nop     dword ptr [rax+rax+00h]
0x140004c20  xor     eax, eax
0x140004c22  cmp     dword ptr [rsp+98h+var_38], eax
0x140004c26  setz    al
0x140004c29  mov     rcx, [rsp+98h+var_30]
0x140004c2e  xor     rcx, rsp; StackCookie
0x140004c31  call    __security_check_cookie
0x140004c36  add     rsp, 70h
0x140004c3a  pop     r14
0x140004c3c  pop     rdi
0x140004c3d  pop     rsi
0x140004c3e  pop     rbp
0x140004c3f  pop     rbx
0x140004c40  retn
```
