# GetNotificationDescription

- ea: `0x1800179c0`
- end: `0x180017aba`
- name: `GetNotificationDescription`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800127a0`

## callees

- `0x180005440`
- `0x1800179c0`
- `0x1800214f0`

## string_xrefs

- `0x180017a7f`: `ResultUpdate`

## pseudocode

```c
const wchar_t *__fastcall GetNotificationDescription(unsigned int a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  const wchar_t *v5; // rbx
  unsigned int v6; // ebx
  unsigned int v7; // ebx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 == 1 )
  {
    v5 = L"ResultUpdate";
    goto LABEL_22;
  }
  if ( a1 > 0x10002 )
  {
    v6 = a1 - 65539;
    if ( !v6 )
    {
      v5 = L"EapAttributes";
      goto LABEL_22;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      v5 = L"DiagnosticsHint";
      goto LABEL_22;
    }
    if ( v7 == 1 )
    {
      v5 = L"OneXNetworkIdentified";
      goto LABEL_22;
    }
    goto LABEL_17;
  }
  if ( a1 == 65538 )
  {
    v5 = L"NetworkInfo";
    goto LABEL_22;
  }
  v3 = a1 - 2;
  if ( !v3 )
  {
    v5 = L"AuthRestarted";
    goto LABEL_22;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v5 = L"InvalidNotification";
    goto LABEL_22;
  }
  if ( v4 != 65534 )
  {
LABEL_17:
    v5 = L"Unknown";
    goto LABEL_22;
  }
  v5 = L"StateTransition";
LABEL_22:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x800) != 0 )
    WPP_SF_D(v2[7], 11, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return v5;
}

```

## disassembly

```asm
0x1800179c0  mov     [rsp+arg_0], rbx
0x1800179c5  push    rdi
0x1800179c6  sub     rsp, 20h
0x1800179ca  mov     ebx, ecx
0x1800179cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179d3  lea     rdi, WPP_GLOBAL_Control
0x1800179da  cmp     rcx, rdi
0x1800179dd  jz      short loc_180017A04
0x1800179df  test    dword ptr [rcx+44h], 800h
0x1800179e6  jz      short loc_180017A04
0x1800179e8  mov     rcx, [rcx+38h]
0x1800179ec  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800179f3  mov     edx, 0Ah
0x1800179f8  call    WPP_SF_
0x1800179fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a04  cmp     ebx, 1
0x180017a07  jz      short loc_180017A7F
0x180017a09  cmp     ebx, 10002h
0x180017a0f  ja      short loc_180017A49
0x180017a11  jz      short loc_180017A40
0x180017a13  sub     ebx, 2
0x180017a16  jz      short loc_180017A37
0x180017a18  sub     ebx, 1
0x180017a1b  jz      short loc_180017A2E
0x180017a1d  cmp     ebx, 0FFFEh
0x180017a23  jnz     short loc_180017A5B
0x180017a25  lea     rbx, aStatetransitio; "StateTransition"
0x180017a2c  jmp     short loc_180017A86
0x180017a2e  lea     rbx, aInvalidnotific; "InvalidNotification"
0x180017a35  jmp     short loc_180017A86
0x180017a37  lea     rbx, aAuthrestarted; "AuthRestarted"
0x180017a3e  jmp     short loc_180017A86
0x180017a40  lea     rbx, aNetworkinfo; "NetworkInfo"
0x180017a47  jmp     short loc_180017A86
0x180017a49  sub     ebx, 10003h
0x180017a4f  jz      short loc_180017A76
0x180017a51  sub     ebx, 1
0x180017a54  jz      short loc_180017A6D
0x180017a56  cmp     ebx, 1
0x180017a59  jz      short loc_180017A64
0x180017a5b  lea     rbx, aUnknown; "Unknown"
0x180017a62  jmp     short loc_180017A86
0x180017a64  lea     rbx, aOnexnetworkide; "OneXNetworkIdentified"
0x180017a6b  jmp     short loc_180017A86
0x180017a6d  lea     rbx, aDiagnosticshin; "DiagnosticsHint"
0x180017a74  jmp     short loc_180017A86
0x180017a76  lea     rbx, aEapattributes; "EapAttributes"
0x180017a7d  jmp     short loc_180017A86
0x180017a7f  lea     rbx, aResultupdate; "ResultUpdate"
0x180017a86  cmp     rcx, rdi
0x180017a89  jz      short loc_180017AAC
0x180017a8b  test    dword ptr [rcx+44h], 800h
0x180017a92  jz      short loc_180017AAC
0x180017a94  mov     rcx, [rcx+38h]
0x180017a98  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180017a9f  mov     edx, 0Bh
0x180017aa4  xor     r9d, r9d
0x180017aa7  call    WPP_SF_D
0x180017aac  mov     rax, rbx
0x180017aaf  mov     rbx, [rsp+28h+arg_0]
0x180017ab4  add     rsp, 20h
0x180017ab8  pop     rdi
0x180017ab9  retn
```
