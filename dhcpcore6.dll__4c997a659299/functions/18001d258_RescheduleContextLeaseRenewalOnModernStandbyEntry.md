# RescheduleContextLeaseRenewalOnModernStandbyEntry

- ea: `0x18001d258`
- end: `0x18001d3f0`
- name: `RescheduleContextLeaseRenewalOnModernStandbyEntry`
- size: `408`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001d3f8`

## callees

- `0x180008d70`
- `0x18001d258`
- `0x180028764`
- `0x180031920`
- `0x1800338c0`
- `0x180034458`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001d272`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001d272`

## string_xrefs

- `0x18001d3a7`: `Rescheduled`

## pseudocode

```c
__int64 __fastcall RescheduleContextLeaseRenewalOnModernStandbyEntry(__int64 a1)
{
  char v2; // r14
  int v3; // r12d
  __int64 result; // rax
  int v5; // r8d
  unsigned __int64 v6; // rbp
  _QWORD *v7; // rdx
  __int64 v8; // r15
  char v9; // si
  int v10; // ecx
  _DWORD *v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // r9
  const char *v14; // r9

  v2 = 0;
  v3 = 0;
  result = _time64(0);
  v6 = *(_QWORD *)(a1 + 544);
  v7 = (_QWORD *)(a1 + 104);
  v8 = result;
  if ( (_QWORD *)*v7 == v7
    || ((LODWORD(v7) = g_fVelocityDhcpv6ContextBitfieldUpdate,
         result = a1 + 8860,
         v9 = 1,
         !g_fVelocityDhcpv6ContextBitfieldUpdate)
      ? (v10 = (*(_DWORD *)result >> 4) & 1)
      : (v10 = *(_DWORD *)(a1 + 8876), LODWORD(v7) = g_fVelocityDhcpv6ContextBitfieldUpdate),
        !v10
     || (!(_DWORD)v7 ? (result = (*(_DWORD *)result >> 5) & 1) : (result = *(unsigned int *)(a1 + 8880)), (_DWORD)result)) )
  {
    v9 = 0;
    v11 = (_DWORD *)(a1 + 600);
  }
  else
  {
    v11 = (_DWORD *)(a1 + 600);
    if ( *(_DWORD *)(a1 + 600) )
    {
      result = 0x7FFFFFFFFFFFFFFFLL;
      if ( v6 != 0x7FFFFFFFFFFFFFFFLL )
      {
        result = CalculateTimeToSleep(a1);
        LODWORD(v7) = result;
        v13 = (unsigned int)result + v8;
        if ( v13 < (unsigned int)result )
        {
          v2 = 22;
          if ( (xmmword_1800423E0 & 2) != 0 )
            result = WPP_SF_D(1025, 55, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, 2147942934LL);
        }
        else if ( v13 > v6 )
        {
          result = ScheduleDhcpv6Renewal(a1, (unsigned int)result, 0);
          v3 = 1;
        }
        else
        {
          if ( (xmmword_1800423E0 & 0x10) == 0 )
            return result;
          result = WPP_SF_ii(v12, 56, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
        }
      }
    }
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    v14 = "Rescheduled";
    if ( !v3 )
      v14 = "Not rescheduling";
    return WPP_SF_s_guid_JlliiD(
             (int)a1 + 9136,
             (_DWORD)v7,
             v5,
             (_DWORD)v14,
             a1 + 9136,
             *(_QWORD *)(a1 + 24),
             v9,
             *v11,
             v6,
             *(_QWORD *)(a1 + 544),
             v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001d258  push    rbx
0x18001d25a  push    rbp
0x18001d25b  push    rsi
0x18001d25c  push    rdi
0x18001d25d  push    r12
0x18001d25f  push    r14
0x18001d261  push    r15
0x18001d263  sub     rsp, 60h
0x18001d267  mov     rdi, rcx
0x18001d26a  xor     r14d, r14d
0x18001d26d  xor     ecx, ecx; Time
0x18001d26f  xor     r12d, r12d
0x18001d272  call    cs:__imp__time64
0x18001d279  nop     dword ptr [rax+rax+00h]
0x18001d27e  mov     rbp, [rdi+220h]
0x18001d285  lea     rdx, [rdi+68h]
0x18001d289  mov     r15, rax
0x18001d28c  cmp     [rdx], rdx
0x18001d28f  jz      loc_18001D37F
0x18001d295  mov     edx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001d29b  lea     rax, [rdi+229Ch]
0x18001d2a2  lea     esi, [r14+1]
0x18001d2a6  test    edx, edx
0x18001d2a8  jz      short loc_18001D2B8
0x18001d2aa  mov     ecx, [rdi+22ACh]
0x18001d2b0  mov     edx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x18001d2b6  jmp     short loc_18001D2BF
0x18001d2b8  mov     ecx, [rax]
0x18001d2ba  shr     ecx, 4
0x18001d2bd  and     ecx, esi
0x18001d2bf  test    ecx, ecx
0x18001d2c1  jz      loc_18001D37F
0x18001d2c7  test    edx, edx
0x18001d2c9  jz      short loc_18001D2D3
0x18001d2cb  mov     eax, [rdi+22B0h]
0x18001d2d1  jmp     short loc_18001D2DA
0x18001d2d3  mov     eax, [rax]
0x18001d2d5  shr     eax, 5
0x18001d2d8  and     eax, esi
0x18001d2da  test    eax, eax
0x18001d2dc  jnz     loc_18001D37F
0x18001d2e2  lea     rbx, [rdi+258h]
0x18001d2e9  cmp     [rbx], r12d
0x18001d2ec  jz      loc_18001D388
0x18001d2f2  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001d2fc  cmp     rbp, rax
0x18001d2ff  jz      loc_18001D388
0x18001d305  mov     rcx, rdi
0x18001d308  call    CalculateTimeToSleep
0x18001d30d  mov     edx, eax
0x18001d30f  lea     r9, [rdx+r15]
0x18001d313  cmp     r9, rdx
0x18001d316  jb      short loc_18001D352
0x18001d318  cmp     r9, rbp
0x18001d31b  ja      short loc_18001D342
0x18001d31d  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001d324  jz      loc_18001D3E0
0x18001d32a  mov     edx, 38h ; '8'
0x18001d32f  mov     [rsp+98h+var_78], rbp
0x18001d334  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001d33b  call    WPP_SF_ii
0x18001d340  jmp     short loc_18001D388
0x18001d342  xor     r8d, r8d
0x18001d345  mov     rcx, rdi
0x18001d348  call    ScheduleDhcpv6Renewal
0x18001d34d  mov     r12d, esi
0x18001d350  jmp     short loc_18001D388
0x18001d352  mov     r14d, 80070216h
0x18001d358  test    byte ptr cs:xmmword_1800423E0, 2
0x18001d35f  jz      short loc_18001D388
0x18001d361  mov     edx, 37h ; '7'
0x18001d366  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18001d36d  mov     ecx, 401h
0x18001d372  mov     r9d, 80070216h
0x18001d378  call    WPP_SF_D
0x18001d37d  jmp     short loc_18001D388
0x18001d37f  xor     esi, esi
0x18001d381  lea     rbx, [rdi+258h]
0x18001d388  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001d38f  jz      short loc_18001D3E0
0x18001d391  mov     [rsp+98h+var_48], r14d
0x18001d396  lea     rax, aNotReschedulin; "Not rescheduling"
0x18001d39d  test    r12d, r12d
0x18001d3a0  lea     rcx, [rdi+23B0h]
0x18001d3a7  lea     r9, aRescheduled; "Rescheduled"
0x18001d3ae  cmovz   r9, rax
0x18001d3b2  mov     rax, [rdi+220h]
0x18001d3b9  mov     [rsp+98h+var_50], rax
0x18001d3be  mov     eax, [rbx]
0x18001d3c0  mov     [rsp+98h+var_58], rbp
0x18001d3c5  mov     [rsp+98h+var_60], eax
0x18001d3c9  mov     rax, [rdi+18h]
0x18001d3cd  mov     [rsp+98h+var_68], esi
0x18001d3d1  mov     [rsp+98h+var_70], rax
0x18001d3d6  mov     [rsp+98h+var_78], rcx
0x18001d3db  call    WPP_SF_s_guid_JlliiD
0x18001d3e0  add     rsp, 60h
0x18001d3e4  pop     r15
0x18001d3e6  pop     r14
0x18001d3e8  pop     r12
0x18001d3ea  pop     rdi
0x18001d3eb  pop     rsi
0x18001d3ec  pop     rbp
0x18001d3ed  pop     rbx
0x18001d3ee  retn
```
