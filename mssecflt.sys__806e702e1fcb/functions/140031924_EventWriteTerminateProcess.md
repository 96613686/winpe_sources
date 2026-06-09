# EventWriteTerminateProcess

- ea: `0x140031924`
- end: `0x140031b35`
- name: `EventWriteTerminateProcess`
- size: `529`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400327d8`

## callees

- `0x140007520`
- `0x140008714`
- `0x14000876c`
- `0x140009b80`
- `0x14001008c`
- `0x140011650`
- `0x140031924`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140031aef`
- `ntoskrnl!EtwWrite` at `0x140031aef`
- `ntoskrnl!RtlLengthSid` at `0x1400319d7`
- `ntoskrnl!RtlLengthSid` at `0x1400319d7`

## pseudocode

```c
__int64 __fastcall EventWriteTerminateProcess(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        __int64 a7,
        const wchar_t *a8,
        char a9)
{
  PSID v9; // rdi
  __int64 v10; // r14
  const wchar_t *v11; // rsi
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rbx
  ULONG v15; // eax
  unsigned __int8 v16; // al
  wchar_t *v17; // rdi
  const WCHAR *v18; // rcx
  bool v19; // zf
  const WCHAR *v20; // rax
  int v21; // eax
  unsigned int v22; // esi
  int v23; // [rsp+40h] [rbp-20h] BYREF
  int v24; // [rsp+44h] [rbp-1Ch] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-18h] BYREF
  int v26; // [rsp+50h] [rbp-10h] BYREF
  int v27; // [rsp+54h] [rbp-Ch] BYREF
  __int64 v28; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v30; // [rsp+B0h] [rbp+50h] BYREF
  int v31; // [rsp+B8h] [rbp+58h] BYREF

  v31 = a4;
  v30 = a3;
  v29 = a2;
  v28 = a1;
  v9 = Sid;
  v10 = a7;
  v11 = a8;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(11);
  UserData = EtwDescriptorBuffer;
  v24 = 0;
  v23 = 0;
  v26 = 0;
  Str = 0;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v28;
  EtwDescriptorBuffer[2] = &v29;
  EtwDescriptorBuffer[4] = &v30;
  EtwDescriptorBuffer[6] = &v31;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v9 )
    v15 = RtlLengthSid(v9);
  else
    v15 = 0;
  *((_DWORD *)UserData + 18) = v15;
  UserData[8] = v9;
  UserData[10] = &a6;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  v16 = SecTruncateCommandLine(0, v10, v11, &v24, &v23, &v26, &Str);
  v17 = Str;
  v18 = &SourceString;
  v27 = v16;
  v19 = v16 == 0;
  v20 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  if ( !v19 )
    v11 = v17;
  if ( v10 )
    v20 = (const WCHAR *)v10;
  UserData[12] = v20;
  if ( v11 )
    v18 = v11;
  *((_DWORD *)UserData + 26) = v23;
  *((_DWORD *)UserData + 30) = v26;
  UserData[16] = &a9;
  UserData[18] = &v27;
  UserData[14] = v18;
  *((_DWORD *)UserData + 31) = 0;
  UserData[17] = 8;
  UserData[19] = 4;
  if ( v11 )
    v21 = 2 * wcslen_0(v11) + 2;
  else
    v21 = 2;
  v26 = v21;
  UserData[21] = 4;
  UserData[20] = &v26;
  v22 = EtwWrite(Microsoft_Windows_SECHandle, &Event22, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
  if ( v17 )
    SecFreePool(v17, 0x74736353u);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v22;
}

```

## disassembly

```asm
0x140031924  mov     rax, rsp
0x140031927  mov     [rax+20h], r9d
0x14003192b  mov     [rax+18h], r8
0x14003192f  mov     [rax+10h], edx
0x140031932  mov     [rax+8], rcx
0x140031936  push    rbp
0x140031937  push    rbx
0x140031938  push    rsi
0x140031939  push    rdi
0x14003193a  push    r12
0x14003193c  push    r14
0x14003193e  push    r15
0x140031940  mov     rbp, rsp
0x140031943  sub     rsp, 60h
0x140031947  mov     rax, cs:__security_cookie
0x14003194e  xor     rax, rsp
0x140031951  mov     [rbp+var_8], rax
0x140031955  mov     rdi, [rbp+Sid]
0x140031959  mov     ecx, 0Bh
0x14003195e  mov     r14, [rbp+arg_30]
0x140031962  mov     rsi, [rbp+arg_38]
0x140031966  call    SecGetEtwDescriptorBuffer
0x14003196b  xor     r15d, r15d
0x14003196e  mov     rbx, rax
0x140031971  mov     [rbp+var_1C], r15d
0x140031975  mov     [rbp+var_20], r15d
0x140031979  mov     [rbp+var_10], r15d
0x14003197d  mov     [rbp+Str], r15
0x140031981  test    rax, rax
0x140031984  jnz     short loc_140031990
0x140031986  mov     eax, 0C000009Ah
0x14003198b  jmp     loc_140031B19
0x140031990  mov     qword ptr [rbx+8], 8
0x140031998  lea     rax, [rbp+arg_0]
0x14003199c  mov     [rbx], rax
0x14003199f  lea     rax, [rbp+arg_8]
0x1400319a3  mov     [rbx+10h], rax
0x1400319a7  lea     rax, [rbp+arg_10]
0x1400319ab  mov     [rbx+20h], rax
0x1400319af  lea     rax, [rbp+arg_18]
0x1400319b3  mov     [rbx+30h], rax
0x1400319b7  mov     qword ptr [rbx+18h], 4
0x1400319bf  mov     qword ptr [rbx+28h], 8
0x1400319c7  mov     qword ptr [rbx+38h], 4
0x1400319cf  test    rdi, rdi
0x1400319d2  jz      short loc_1400319E5
0x1400319d4  mov     rcx, rdi; Sid
0x1400319d7  call    cs:__imp_RtlLengthSid
0x1400319de  nop     dword ptr [rax+rax+00h]
0x1400319e3  jmp     short loc_1400319E8
0x1400319e5  mov     eax, r15d
0x1400319e8  mov     [rbx+48h], eax
0x1400319eb  lea     r9, [rbp+var_1C]
0x1400319ef  lea     rax, [rbp+arg_28]
0x1400319f3  mov     [rbx+40h], rdi
0x1400319f7  mov     [rbx+50h], rax
0x1400319fb  mov     r8, rsi
0x1400319fe  lea     rax, [rbp+Str]
0x140031a02  mov     [rbx+4Ch], r15d
0x140031a06  mov     [rsp+60h+var_30], rax
0x140031a0b  mov     rdx, r14
0x140031a0e  lea     rax, [rbp+var_10]
0x140031a12  mov     qword ptr [rbx+58h], 4
0x140031a1a  mov     [rsp+60h+var_38], rax
0x140031a1f  xor     ecx, ecx
0x140031a21  lea     rax, [rbp+var_20]
0x140031a25  mov     [rsp+60h+UserData], rax
0x140031a2a  call    SecTruncateCommandLine
0x140031a2f  mov     rdi, [rbp+Str]
0x140031a33  lea     rcx, SourceString
0x140031a3a  movzx   eax, al
0x140031a3d  mov     [rbp+var_C], eax
0x140031a40  test    eax, eax
0x140031a42  mov     rax, rcx
0x140031a45  mov     [rbx+6Ch], r15d
0x140031a49  cmovnz  rsi, rdi
0x140031a4d  test    r14, r14
0x140031a50  cmovnz  rax, r14
0x140031a54  test    rsi, rsi
0x140031a57  mov     [rbx+60h], rax
0x140031a5b  mov     eax, [rbp+var_20]
0x140031a5e  cmovnz  rcx, rsi
0x140031a62  mov     [rbx+68h], eax
0x140031a65  mov     eax, [rbp+var_10]
0x140031a68  mov     [rbx+78h], eax
0x140031a6b  lea     rax, [rbp+arg_40]
0x140031a72  mov     [rbx+80h], rax
0x140031a79  lea     rax, [rbp+var_C]
0x140031a7d  mov     [rbx+90h], rax
0x140031a84  mov     [rbx+70h], rcx
0x140031a88  mov     [rbx+7Ch], r15d
0x140031a8c  mov     qword ptr [rbx+88h], 8
0x140031a97  mov     qword ptr [rbx+98h], 4
0x140031aa2  jnz     short loc_140031AAB
0x140031aa4  mov     eax, 2
0x140031aa9  jmp     short loc_140031ABA
0x140031aab  mov     rcx, rsi; Str
0x140031aae  call    wcslen_0
0x140031ab3  lea     eax, ds:2[rax*2]
0x140031aba  mov     [rbp+var_10], eax
0x140031abd  lea     rdx, Event22; EventDescriptor
0x140031ac4  lea     rax, [rbp+var_10]
0x140031ac8  mov     qword ptr [rbx+0A8h], 4
0x140031ad3  mov     [rbx+0A0h], rax
0x140031ada  mov     r9d, 0Bh; UserDataCount
0x140031ae0  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140031ae7  xor     r8d, r8d; ActivityId
0x140031aea  mov     [rsp+60h+UserData], rbx; UserData
0x140031aef  call    cs:__imp_EtwWrite
0x140031af6  nop     dword ptr [rax+rax+00h]
0x140031afb  mov     esi, eax
0x140031afd  test    rdi, rdi
0x140031b00  jz      short loc_140031B0F
0x140031b02  mov     edx, 74736353h; Tag
0x140031b07  mov     rcx, rdi; P
0x140031b0a  call    SecFreePool
0x140031b0f  mov     rcx, rbx; ListEntry
0x140031b12  call    SecReleaseEtwDescriptorBuffer
0x140031b17  mov     eax, esi
0x140031b19  mov     rcx, [rbp+var_8]
0x140031b1d  xor     rcx, rsp; StackCookie
0x140031b20  call    __security_check_cookie
0x140031b25  add     rsp, 60h
0x140031b29  pop     r15
0x140031b2b  pop     r14
0x140031b2d  pop     r12
0x140031b2f  pop     rdi
0x140031b30  pop     rsi
0x140031b31  pop     rbx
0x140031b32  pop     rbp
0x140031b33  retn
```
