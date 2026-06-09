# _InternalGetDefaultSecurityDescriptor_::_1_::catch$38

- ea: `0x180030628`
- end: `0x180030681`
- name: `_InternalGetDefaultSecurityDescriptor_::_1_::catch$38`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013940`
- `0x180030628`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall InternalGetDefaultSecurityDescriptor_::_1_::catch_38(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 240) + 16LL))(*(_QWORD *)(a2 + 240));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 96) = v3;
  if ( v3 < 0 )
    LogMsgHR(v3, (wchar_t *)L"acssctrl/secdscrp", 0x1F8u);
  return 0;
}

```

## disassembly

```asm
0x180030628  mov     [rsp+arg_8], rdx
0x18003062d  push    rbp
0x18003062e  sub     rsp, 60h
0x180030632  mov     rbp, rdx
0x180030635  mov     rcx, [rbp+0F0h]
0x18003063c  mov     rax, [rcx]
0x18003063f  mov     rax, [rax+10h]
0x180030643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030648  test    eax, eax
0x18003064a  jle     short loc_180030654
0x18003064c  movzx   eax, ax
0x18003064f  or      eax, 80070000h
0x180030654  mov     [rbp+60h], eax
0x180030657  test    eax, eax
0x180030659  jns     short loc_180030670
0x18003065b  mov     r8d, 1F8h; unsigned __int16
0x180030661  lea     rdx, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180030668  mov     ecx, eax; int
0x18003066a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003066f  nop
0x180030670  mov     rax, 0
0x18003067a  add     rsp, 60h
0x18003067e  pop     rbp
0x18003067f  retn
```
