# WPP_SF__sid_

- ea: `0x180058c28`
- end: `0x180058cd3`
- name: `WPP_SF__sid_`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180057480`

## callees

- `0x180058c28`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180058cb6`
- `ntdll!EtwTraceMessage` at `0x180058cb6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180058c58`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180058c58`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180058c45`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180058c75`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180058c45`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180058c75`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  char *v4; // rbx
  DWORD LengthSid; // edi

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
      return EtwTraceMessage(a1, 43, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 462, v4, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v4) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, 462, v4, LengthSid, 0);
}

```

## disassembly

```asm
0x180058c28  mov     [rsp+arg_0], rbx
0x180058c2d  mov     [rsp+arg_8], rsi
0x180058c32  push    rdi
0x180058c33  sub     rsp, 40h
0x180058c37  mov     rbx, r9
0x180058c3a  mov     rsi, rcx
0x180058c3d  test    r9, r9
0x180058c40  jz      short loc_180058C68
0x180058c42  mov     rcx, rbx; pSid
0x180058c45  call    cs:__imp_IsValidSid
0x180058c4c  nop     dword ptr [rax+rax+00h]
0x180058c51  test    eax, eax
0x180058c53  jz      short loc_180058C68
0x180058c55  mov     rcx, rbx; pSid
0x180058c58  call    cs:__imp_GetLengthSid
0x180058c5f  nop     dword ptr [rax+rax+00h]
0x180058c64  mov     edi, eax
0x180058c66  jmp     short loc_180058C72
0x180058c68  mov     edi, 5
0x180058c6d  test    rbx, rbx
0x180058c70  jz      short loc_180058C85
0x180058c72  mov     rcx, rbx; pSid
0x180058c75  call    cs:__imp_IsValidSid
0x180058c7c  nop     dword ptr [rax+rax+00h]
0x180058c81  test    eax, eax
0x180058c83  jnz     short loc_180058C8C
0x180058c85  lea     rbx, aNull_0; "NULL"
0x180058c8c  mov     eax, edi
0x180058c8e  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180058c95  mov     [rsp+48h+var_18], 0
0x180058c9e  mov     r9d, 1CEh
0x180058ca4  mov     [rsp+48h+var_20], rax
0x180058ca9  mov     edx, 2Bh ; '+'
0x180058cae  mov     rcx, rsi
0x180058cb1  mov     [rsp+48h+var_28], rbx
0x180058cb6  call    cs:__imp_EtwTraceMessage
0x180058cbd  nop     dword ptr [rax+rax+00h]
0x180058cc2  mov     rbx, [rsp+48h+arg_0]
0x180058cc7  mov     rsi, [rsp+48h+arg_8]
0x180058ccc  add     rsp, 40h
0x180058cd0  pop     rdi
0x180058cd1  retn
```
