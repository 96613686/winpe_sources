# IASReportSecurityEvent

- ea: `0x18000ca80`
- end: `0x18000cac8`
- name: `IASReportSecurityEvent`
- size: `72`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ca80`
- `0x180019010`

## pseudocode

```c
__int64 IASReportSecurityEvent()
{
  __int64 result; // rax
  const _com_error *v1; // rbx
  const _com_error *v2; // [rsp+38h] [rbp-10h] BYREF

  if ( !pAuditChannel )
    return 2147500035LL;
  try
  {
    result = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pAuditChannel + 32LL))(pAuditChannel);
  }
  catch ( const _com_error *v2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v1 = v2;
    }
    else
    {
      v1 = v2;
      WppDbgPrint("IASReportSecurityEvent failed  0x%x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_8ed8de69590d30c8f13474de64c7f7ed_Traceguids,
        (unsigned int)"NPSSVC",
        *((_DWORD *)v1 + 2));
    }
    return *((unsigned int *)v1 + 2);
  }
  result = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pAuditChannel + 32LL))(pAuditChannel);
}

```

## disassembly

```asm
0x18000ca80  sub     rsp, 48h
0x18000ca84  movzx   r10d, cx
0x18000ca88  cmp     cs:?pAuditChannel@@3PEAUIAuditSink@@EA, 0; IAuditSink * pAuditChannel
0x18000ca90  jnz     short loc_18000CA99
0x18000ca92  mov     eax, 80004003h
0x18000ca97  jmp     short loc_18000CAC2
0x18000ca99  mov     rcx, cs:?pAuditChannel@@3PEAUIAuditSink@@EA; IAuditSink * pAuditChannel
0x18000caa0  mov     rax, [rcx]
0x18000caa3  mov     [rsp+48h+var_28], r9
0x18000caa8  movzx   r9d, r8w
0x18000caac  mov     r8d, edx
0x18000caaf  movzx   edx, r10w
0x18000cab3  mov     rax, [rax+20h]
0x18000cab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cabc  jmp     short loc_18000CAC2
0x18000cabe  mov     eax, [rsp+48h+var_18]
0x18000cac2  add     rsp, 48h
0x18000cac6  retn
```
