# WPP_SF__sid_D

- ea: `0x1800618f4`
- end: `0x18006199b`
- name: `WPP_SF__sid_D`
- size: `167`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180061024`

## callees

- `0x1800618f4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180061985`
- `ADVAPI32!TraceMessage` at `0x180061985`
- `ADVAPI32!GetLengthSid` at `0x18006191e`
- `ADVAPI32!GetLengthSid` at `0x18006191e`
- `ADVAPI32!IsValidSid` at `0x180061911`
- `ADVAPI32!IsValidSid` at `0x180061935`
- `ADVAPI32!IsValidSid` at `0x180061911`
- `ADVAPI32!IsValidSid` at `0x180061935`

## pseudocode

```c
ULONG WPP_SF__sid_D(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, char *a4, ...)
{
  char *v4; // rbx
  DWORD LengthSid; // edi
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v4);
  }
  else
  {
    LengthSid = 5;
    if ( !v4 )
    {
LABEL_6:
      v4 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids,
               0xCu,
               v4,
               LengthSid,
               va,
               4,
               0);
    }
  }
  if ( !IsValidSid(v4) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids,
           0xCu,
           v4,
           LengthSid,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x1800618f4  mov     [rsp+arg_0], rbx
0x1800618f9  mov     [rsp+arg_8], rsi
0x1800618fe  push    rdi
0x1800618ff  sub     rsp, 50h
0x180061903  mov     rbx, r9
0x180061906  mov     rsi, rcx
0x180061909  test    r9, r9
0x18006190c  jz      short loc_180061928
0x18006190e  mov     rcx, rbx; pSid
0x180061911  call    cs:__imp_IsValidSid
0x180061917  test    eax, eax
0x180061919  jz      short loc_180061928
0x18006191b  mov     rcx, rbx; pSid
0x18006191e  call    cs:__imp_GetLengthSid
0x180061924  mov     edi, eax
0x180061926  jmp     short loc_180061932
0x180061928  mov     edi, 5
0x18006192d  test    rbx, rbx
0x180061930  jz      short loc_18006193F
0x180061932  mov     rcx, rbx; pSid
0x180061935  call    cs:__imp_IsValidSid
0x18006193b  test    eax, eax
0x18006193d  jnz     short loc_180061946
0x18006193f  lea     rbx, aNull; "NULL"
0x180061946  mov     [rsp+58h+var_18], 0
0x18006194f  lea     rcx, [rsp+58h+arg_20]
0x180061957  mov     [rsp+58h+var_20], 4
0x180061960  lea     r8, WPP_54588dc237b33a312ac4912f3ef61e5f_Traceguids; MessageGuid
0x180061967  mov     [rsp+58h+var_28], rcx
0x18006196c  mov     r9d, 0Ch; MessageNumber
0x180061972  mov     eax, edi
0x180061974  mov     rcx, rsi; LoggerHandle
0x180061977  mov     [rsp+58h+var_30], rax
0x18006197c  mov     [rsp+58h+var_38], rbx
0x180061981  lea     edx, [r9+1Fh]; MessageFlags
0x180061985  call    cs:__imp_TraceMessage
0x18006198b  mov     rbx, [rsp+58h+arg_0]
0x180061990  mov     rsi, [rsp+58h+arg_8]
0x180061995  add     rsp, 50h
0x180061999  pop     rdi
0x18006199a  retn
```
