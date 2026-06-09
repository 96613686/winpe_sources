# WPP_SF__sid_SiDD

- ea: `0x1800c5480`
- end: `0x1800c5591`
- name: `WPP_SF__sid_SiDD`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800490d0`
- `0x18009753c`

## callees

- `0x1800c5480`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800c557b`
- `ntdll!EtwTraceMessage` at `0x1800c557b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c54d9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c54fd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c54d9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c54fd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c54e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c54e6`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_SiDD(__int64 a1, __int64 a2, __int64 a3, char *a4, const wchar_t *a5)
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
      return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, 11, v6, LengthSid, v5);
    }
  }
  if ( !IsValidSid(v6) )
    goto LABEL_11;
  return EtwTraceMessage(a1, 43, &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids, 11, v6, LengthSid, v5);
}

```

## disassembly

```asm
0x1800c5480  push    rbx
0x1800c5482  push    rbp
0x1800c5483  push    rsi
0x1800c5484  push    rdi
0x1800c5485  push    r14
0x1800c5487  push    r15
0x1800c5489  sub     rsp, 88h
0x1800c5490  mov     rdi, [rsp+0B8h+arg_20]
0x1800c5498  xor     r15d, r15d
0x1800c549b  mov     rbx, r9
0x1800c549e  mov     r14, rcx
0x1800c54a1  test    rdi, rdi
0x1800c54a4  jz      short loc_1800C54BE
0x1800c54a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c54aa  inc     rax
0x1800c54ad  cmp     [rdi+rax*2], r15w
0x1800c54b2  jnz     short loc_1800C54AA
0x1800c54b4  lea     rbp, ds:2[rax*2]
0x1800c54bc  jmp     short loc_1800C54C3
0x1800c54be  mov     ebp, 0Ah
0x1800c54c3  test    rdi, rdi
0x1800c54c6  lea     rax, aNull_1; "NULL"
0x1800c54cd  cmovz   rdi, rax
0x1800c54d1  test    rbx, rbx
0x1800c54d4  jz      short loc_1800C54F0
0x1800c54d6  mov     rcx, rbx; pSid
0x1800c54d9  call    cs:__imp_IsValidSid
0x1800c54df  test    eax, eax
0x1800c54e1  jz      short loc_1800C54F0
0x1800c54e3  mov     rcx, rbx; pSid
0x1800c54e6  call    cs:__imp_GetLengthSid
0x1800c54ec  mov     esi, eax
0x1800c54ee  jmp     short loc_1800C54FA
0x1800c54f0  mov     esi, 5
0x1800c54f5  test    rbx, rbx
0x1800c54f8  jz      short loc_1800C5507
0x1800c54fa  mov     rcx, rbx; pSid
0x1800c54fd  call    cs:__imp_IsValidSid
0x1800c5503  test    eax, eax
0x1800c5505  jnz     short loc_1800C550E
0x1800c5507  lea     rbx, aNull; "NULL"
0x1800c550e  mov     [rsp+0B8h+var_48], r15
0x1800c5513  lea     rcx, [rsp+0B8h+arg_38]
0x1800c551b  mov     r9d, 0Bh
0x1800c5521  mov     eax, esi
0x1800c5523  lea     r8, WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids
0x1800c552a  lea     edx, [r9-7]
0x1800c552e  mov     [rsp+0B8h+var_50], rdx
0x1800c5533  mov     [rsp+0B8h+var_58], rcx
0x1800c5538  lea     rcx, [rsp+0B8h+arg_30]
0x1800c5540  mov     [rsp+0B8h+var_60], rdx
0x1800c5545  lea     edx, [r9+20h]
0x1800c5549  mov     [rsp+0B8h+var_68], rcx
0x1800c554e  lea     rcx, [rsp+0B8h+arg_28]
0x1800c5556  mov     [rsp+0B8h+var_70], 8
0x1800c555f  mov     [rsp+0B8h+var_78], rcx
0x1800c5564  mov     rcx, r14
0x1800c5567  mov     [rsp+0B8h+var_80], rbp
0x1800c556c  mov     [rsp+0B8h+var_88], rdi
0x1800c5571  mov     [rsp+0B8h+var_90], rax
0x1800c5576  mov     [rsp+0B8h+var_98], rbx
0x1800c557b  call    cs:__imp_EtwTraceMessage
0x1800c5581  add     rsp, 88h
0x1800c5588  pop     r15
0x1800c558a  pop     r14
0x1800c558c  pop     rdi
0x1800c558d  pop     rsi
0x1800c558e  pop     rbp
0x1800c558f  pop     rbx
0x1800c5590  retn
```
