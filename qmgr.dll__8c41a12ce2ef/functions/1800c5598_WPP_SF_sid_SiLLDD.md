# WPP_SF__sid_SiLLDD

- ea: `0x1800c5598`
- end: `0x1800c56dd`
- name: `WPP_SF__sid_SiLLDD`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c2500`

## callees

- `0x1800c5598`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800c56c5`
- `ntdll!EtwTraceMessage` at `0x1800c56c5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c55f7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c561b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c55f7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c561b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c5604`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c5604`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_SiLLDD(__int64 a1, __int64 a2, __int64 a3, char *a4, const wchar_t *a5)
{
  const wchar_t *v5; // rdi
  char *v6; // rbx
  __int64 v8; // rax
  DWORD LengthSid; // esi

  v5 = a5;
  v6 = a4;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
  }
  if ( !a5 )
    v5 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v6);
  }
  else
  {
    LengthSid = 5;
    if ( !v6 )
    {
LABEL_11:
      v6 = "NULL";
      return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, 10, v6, LengthSid, v5);
    }
  }
  if ( !IsValidSid(v6) )
    goto LABEL_11;
  return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, 10, v6, LengthSid, v5);
}

```

## disassembly

```asm
0x1800c5598  push    rbx
0x1800c559a  push    rbp
0x1800c559b  push    rsi
0x1800c559c  push    rdi
0x1800c559d  push    r12
0x1800c559f  push    r14
0x1800c55a1  push    r15
0x1800c55a3  sub     rsp, 0A0h
0x1800c55aa  mov     rdi, [rsp+0D8h+arg_20]
0x1800c55b2  xor     r15d, r15d
0x1800c55b5  mov     rbx, r9
0x1800c55b8  mov     r14, rcx
0x1800c55bb  mov     r12d, 0Ah
0x1800c55c1  test    rdi, rdi
0x1800c55c4  jz      short loc_1800C55DE
0x1800c55c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c55ca  inc     rax
0x1800c55cd  cmp     [rdi+rax*2], r15w
0x1800c55d2  jnz     short loc_1800C55CA
0x1800c55d4  lea     rbp, ds:2[rax*2]
0x1800c55dc  jmp     short loc_1800C55E1
0x1800c55de  mov     rbp, r12
0x1800c55e1  test    rdi, rdi
0x1800c55e4  lea     rax, aNull_1; "NULL"
0x1800c55eb  cmovz   rdi, rax
0x1800c55ef  test    rbx, rbx
0x1800c55f2  jz      short loc_1800C560E
0x1800c55f4  mov     rcx, rbx; pSid
0x1800c55f7  call    cs:__imp_IsValidSid
0x1800c55fd  test    eax, eax
0x1800c55ff  jz      short loc_1800C560E
0x1800c5601  mov     rcx, rbx; pSid
0x1800c5604  call    cs:__imp_GetLengthSid
0x1800c560a  mov     esi, eax
0x1800c560c  jmp     short loc_1800C5618
0x1800c560e  mov     esi, 5
0x1800c5613  test    rbx, rbx
0x1800c5616  jz      short loc_1800C5625
0x1800c5618  mov     rcx, rbx; pSid
0x1800c561b  call    cs:__imp_IsValidSid
0x1800c5621  test    eax, eax
0x1800c5623  jnz     short loc_1800C562C
0x1800c5625  lea     rbx, aNull; "NULL"
0x1800c562c  mov     [rsp+0D8h+var_48], r15
0x1800c5634  lea     rcx, [rsp+0D8h+arg_48]
0x1800c563c  mov     edx, 4
0x1800c5641  mov     eax, esi
0x1800c5643  mov     [rsp+0D8h+var_50], rdx
0x1800c564b  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800c5652  mov     [rsp+0D8h+var_58], rcx
0x1800c565a  mov     r9d, r12d
0x1800c565d  mov     [rsp+0D8h+var_60], rdx
0x1800c5662  lea     rcx, [rsp+0D8h+arg_40]
0x1800c566a  mov     [rsp+0D8h+var_68], rcx
0x1800c566f  lea     rcx, [rsp+0D8h+arg_38]
0x1800c5677  mov     [rsp+0D8h+var_70], rdx
0x1800c567c  mov     [rsp+0D8h+var_78], rcx
0x1800c5681  lea     rcx, [rsp+0D8h+arg_30]
0x1800c5689  mov     [rsp+0D8h+var_80], rdx
0x1800c568e  mov     edx, 2Bh ; '+'
0x1800c5693  mov     [rsp+0D8h+var_88], rcx
0x1800c5698  lea     rcx, [rsp+0D8h+arg_28]
0x1800c56a0  mov     [rsp+0D8h+var_90], 8
0x1800c56a9  mov     [rsp+0D8h+var_98], rcx
0x1800c56ae  mov     rcx, r14
0x1800c56b1  mov     [rsp+0D8h+var_A0], rbp
0x1800c56b6  mov     [rsp+0D8h+var_A8], rdi
0x1800c56bb  mov     [rsp+0D8h+var_B0], rax
0x1800c56c0  mov     [rsp+0D8h+var_B8], rbx
0x1800c56c5  call    cs:__imp_EtwTraceMessage
0x1800c56cb  add     rsp, 0A0h
0x1800c56d2  pop     r15
0x1800c56d4  pop     r14
0x1800c56d6  pop     r12
0x1800c56d8  pop     rdi
0x1800c56d9  pop     rsi
0x1800c56da  pop     rbp
0x1800c56db  pop     rbx
0x1800c56dc  retn
```
