# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18001de68`
- end: `0x18001df42`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001dde0`

## callees

- `0x18001dc5c`
- `0x18001de68`
- `0x180027ba0`
- `0x180027c80`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18001df14`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x18001df14`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v6; // rax
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
0x18001de68  push    rbx
0x18001de6a  push    rbp
0x18001de6b  push    rsi
0x18001de6c  push    rdi
0x18001de6d  push    r14
0x18001de6f  sub     rsp, 70h
0x18001de73  mov     rax, cs:__security_cookie
0x18001de7a  xor     rax, rsp
0x18001de7d  mov     [rsp+98h+var_30], rax
0x18001de82  mov     r9, rdx
0x18001de85  mov     rbx, rdx
0x18001de88  mov     rdx, [rcx+8]
0x18001de8c  mov     rbp, rcx
0x18001de8f  shr     r9, 20h
0x18001de93  lea     rcx, [rsp+98h+var_60]
0x18001de98  mov     esi, r8d
0x18001de9b  call    wil_details_FeatureReporting_RecordUsageInCache
0x18001dea0  mov     r14d, 1
0x18001dea6  movups  xmm1, xmmword ptr [rax]
0x18001dea9  movups  [rsp+98h+var_48], xmm1
0x18001deae  movsd   xmm0, qword ptr [rax+10h]
0x18001deb3  mov     rax, cs:g_wil_details_recordFeatureUsage
0x18001deba  movsd   [rsp+98h+var_38], xmm0
0x18001dec0  test    rax, rax
0x18001dec3  jz      short loc_18001DEE0
0x18001dec5  mov     r9, [rbp+8]
0x18001dec9  lea     rcx, [rsp+98h+var_48]
0x18001dece  mov     [rsp+98h+var_78], rcx
0x18001ded3  mov     r8d, r14d
0x18001ded6  mov     ecx, [rbp+18h]
0x18001ded9  mov     edx, esi
0x18001dedb  call    _guard_dispatch_icall
0x18001dee0  bt      ebx, 0Ah
0x18001dee4  jnb     short loc_18001DF20
0x18001dee6  cmp     esi, 0FEh
0x18001deec  jz      short loc_18001DF20
0x18001deee  mov     eax, [rbp+18h]
0x18001def1  mov     [rsp+98h+var_68], 0
0x18001defa  mov     dword ptr [rsp+98h+var_68], eax
0x18001defe  mov     word ptr [rsp+98h+var_68+4], si
0x18001df03  bt      ebx, 0Bh
0x18001df07  jnb     short loc_18001DF0F
0x18001df09  or      word ptr [rsp+98h+var_68+6], r14w
0x18001df0f  lea     rcx, [rsp+98h+var_68]
0x18001df14  call    cs:__imp_RtlNotifyFeatureUsage
0x18001df1b  nop     dword ptr [rax+rax+00h]
0x18001df20  xor     eax, eax
0x18001df22  cmp     dword ptr [rsp+98h+var_38], eax
0x18001df26  setz    al
0x18001df29  mov     rcx, [rsp+98h+var_30]
0x18001df2e  xor     rcx, rsp; StackCookie
0x18001df31  call    __security_check_cookie
0x18001df36  add     rsp, 70h
0x18001df3a  pop     r14
0x18001df3c  pop     rdi
0x18001df3d  pop     rsi
0x18001df3e  pop     rbp
0x18001df3f  pop     rbx
0x18001df40  retn
```
