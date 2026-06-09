# FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1

- ea: `0x180007010`
- end: `0x1800071a0`
- name: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180006db4`

## callees

- `0x180007010`
- `0x1800071a8`
- `0x180007e38`
- `0x180011500`
- `0x1800120e0`

## string_xrefs

- `0x180007111`: `FwppDeepCopyFromVerIndependent_UINT16`
- `0x180007129`: `FwppDeepCopyFromVerIndependent_UINT16`
- `0x180007067`: `FwppDeepCopyFromVerIndependent_UINT32`
- `0x1800070f5`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1`
- `0x18000718c`: `FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1(
        __int64 a1,
        struct _SID_AND_ATTRIBUTES *a2)
{
  DWORD *p_Attributes; // rcx
  __int64 v5; // rbx
  __int64 v7; // rax
  const char *v8; // rdx

  if ( !a1 || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1", 3223453724LL);
    if ( !v5 )
      return v5;
    goto LABEL_17;
  }
  v5 = FwppDeepCopyFromVerIndependent_UINT64(a1, a2);
  if ( !v5 )
  {
    if ( a1 == -8 || (p_Attributes = &a2->Attributes, a2 == (struct _SID_AND_ATTRIBUTES *)-8LL) )
    {
      v7 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_UINT16", 3223453724LL);
      v5 = v7;
      if ( v7 )
      {
        v8 = "FwppDeepCopyFromVerIndependent_UINT16";
LABEL_16:
        WfpReportError(v7, v8);
        goto LABEL_17;
      }
    }
    else
    {
      *(_WORD *)p_Attributes = *(_WORD *)(a1 + 8);
    }
    if ( a1 == -12 || (p_Attributes = &a2->Attributes + 1, a2 == (struct _SID_AND_ATTRIBUTES *)-12LL) )
    {
      v7 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_UINT32", 3223453724LL);
      v5 = v7;
      if ( v7 )
        goto LABEL_25;
    }
    else
    {
      *p_Attributes = *(_DWORD *)(a1 + 12);
    }
    if ( a1 != -16 )
    {
      p_Attributes = (DWORD *)&a2[1];
      if ( a2 != (struct _SID_AND_ATTRIBUTES *)-16LL )
      {
        *p_Attributes = *(_DWORD *)(a1 + 16);
        goto LABEL_13;
      }
    }
    v7 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_UINT32", 3223453724LL);
    v5 = v7;
    if ( !v7 )
    {
LABEL_13:
      if ( a1 != -20 )
      {
        p_Attributes = (DWORD *)&a2[1].Sid + 1;
        if ( a2 != (struct _SID_AND_ATTRIBUTES *)-20LL )
        {
          v5 = 0;
          *p_Attributes = *(_DWORD *)(a1 + 20);
          return v5;
        }
      }
      v7 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_UINT32", 3223453724LL);
      v5 = v7;
      if ( !v7 )
        return v5;
    }
LABEL_25:
    v8 = "FwppDeepCopyFromVerIndependent_UINT32";
    goto LABEL_16;
  }
LABEL_17:
  FeFreeGroupsCallback(a2);
  if ( v5 )
    WfpReportError(v5, "FwppDeepCopyFromVerIndependent_FWPM_NET_EVENT_CLASSIFY_DROP1");
  return v5;
}

```

## disassembly

```asm
0x180007010  push    rbx
0x180007012  push    rsi
0x180007013  push    rdi
0x180007014  push    r14
0x180007016  sub     rsp, 28h
0x18000701a  mov     rdi, rdx
0x18000701d  mov     rsi, rcx
0x180007020  test    rcx, rcx
0x180007023  jz      loc_1800070EF
0x180007029  test    rdx, rdx
0x18000702c  jz      loc_1800070EF
0x180007032  call    FwppDeepCopyFromVerIndependent_UINT64
0x180007037  mov     rbx, rax
0x18000703a  test    rax, rax
0x18000703d  jnz     loc_1800070D0
0x180007043  lea     rax, [rsi+8]
0x180007047  test    rax, rax
0x18000704a  jz      loc_18000710B
0x180007050  lea     rcx, [rdi+8]
0x180007054  test    rcx, rcx
0x180007057  jz      loc_18000710B
0x18000705d  movzx   eax, word ptr [rax]
0x180007060  mov     [rcx], ax
0x180007063  lea     rax, [rsi+0Ch]
0x180007067  lea     r14, aFwppdeepcopyfr_117; "FwppDeepCopyFromVerIndependent_UINT32"
0x18000706e  test    rax, rax
0x180007071  jz      loc_180007132
0x180007077  lea     rcx, [rdi+0Ch]
0x18000707b  test    rcx, rcx
0x18000707e  jz      loc_180007132
0x180007084  mov     eax, [rax]
0x180007086  mov     [rcx], eax
0x180007088  lea     rax, [rsi+10h]
0x18000708c  test    rax, rax
0x18000708f  jz      loc_180007154
0x180007095  lea     rcx, [rdi+10h]
0x180007099  test    rcx, rcx
0x18000709c  jz      loc_180007154
0x1800070a2  mov     eax, [rax]
0x1800070a4  mov     [rcx], eax
0x1800070a6  lea     rax, [rsi+14h]
0x1800070aa  test    rax, rax
0x1800070ad  jz      loc_180007170
0x1800070b3  lea     rcx, [rdi+14h]
0x1800070b7  test    rcx, rcx
0x1800070ba  jz      loc_180007170
0x1800070c0  mov     eax, [rax]
0x1800070c2  xor     ebx, ebx
0x1800070c4  mov     [rcx], eax
0x1800070c6  jmp     short loc_1800070E1
0x1800070c8  mov     rcx, rax
0x1800070cb  call    WfpReportError
0x1800070d0  mov     rcx, rdi; pSidAttrArray
0x1800070d3  call    FeFreeGroupsCallback
0x1800070d8  test    rbx, rbx
0x1800070db  jnz     loc_18000718C
0x1800070e1  mov     rax, rbx
0x1800070e4  add     rsp, 28h
0x1800070e8  pop     r14
0x1800070ea  pop     rdi
0x1800070eb  pop     rsi
0x1800070ec  pop     rbx
0x1800070ed  retn
0x1800070ef  mov     r8d, 0C022001Ch
0x1800070f5  lea     rdx, aFwppdeepcopyfr_15; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x1800070fc  call    WfpReportSysErrorAsNtStatus
0x180007101  mov     rbx, rax
0x180007104  test    rax, rax
0x180007107  jnz     short loc_1800070D0
0x180007109  jmp     short loc_1800070E1
0x18000710b  mov     r8d, 0C022001Ch
0x180007111  lea     rdx, aFwppdeepcopyfr_58; "FwppDeepCopyFromVerIndependent_UINT16"
0x180007118  call    WfpReportSysErrorAsNtStatus
0x18000711d  mov     rbx, rax
0x180007120  test    rax, rax
0x180007123  jz      loc_180007063
0x180007129  lea     rdx, aFwppdeepcopyfr_58; "FwppDeepCopyFromVerIndependent_UINT16"
0x180007130  jmp     short loc_1800070C8
0x180007132  mov     r8d, 0C022001Ch
0x180007138  mov     rdx, r14
0x18000713b  call    WfpReportSysErrorAsNtStatus
0x180007140  mov     rbx, rax
0x180007143  test    rax, rax
0x180007146  jz      loc_180007088
0x18000714c  mov     rdx, r14
0x18000714f  jmp     loc_1800070C8
0x180007154  mov     r8d, 0C022001Ch
0x18000715a  mov     rdx, r14
0x18000715d  call    WfpReportSysErrorAsNtStatus
0x180007162  mov     rbx, rax
0x180007165  test    rax, rax
0x180007168  jz      loc_1800070A6
0x18000716e  jmp     short loc_18000714C
0x180007170  mov     r8d, 0C022001Ch
0x180007176  mov     rdx, r14
0x180007179  call    WfpReportSysErrorAsNtStatus
0x18000717e  mov     rbx, rax
0x180007181  test    rax, rax
0x180007184  jz      loc_1800070E1
0x18000718a  jmp     short loc_18000714C
0x18000718c  lea     rdx, aFwppdeepcopyfr_15; "FwppDeepCopyFromVerIndependent_FWPM_NET"...
0x180007193  mov     rcx, rbx
0x180007196  call    WfpReportError
0x18000719b  jmp     loc_1800070E1
```
