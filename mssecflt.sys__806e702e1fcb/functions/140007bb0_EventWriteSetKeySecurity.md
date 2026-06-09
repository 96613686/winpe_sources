# EventWriteSetKeySecurity

- ea: `0x140007bb0`
- end: `0x140007db1`
- name: `EventWriteSetKeySecurity`
- size: `513`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, char, char, wchar_t *, wchar_t *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037d30`

## callees

- `0x140007bb0`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140007d89`
- `ntoskrnl!EtwWriteEx` at `0x140007d89`
- `ntoskrnl!RtlLengthSid` at `0x140007c3d`
- `ntoskrnl!RtlLengthSid` at `0x140007c3d`

## pseudocode

```c
__int64 EventWriteSetKeySecurity(
        ULONG64 Filter,
        __int64 a2,
        int a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        wchar_t *Str,
        char a9,
        ...)
{
  PSID v9; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v14; // eax
  const wchar_t *v15; // rsi
  int v16; // ebx
  int v17; // ecx
  const WCHAR *v18; // r14
  const WCHAR *v19; // rax
  const wchar_t *v20; // rsi
  int v21; // ecx
  const WCHAR *v22; // rax
  const wchar_t *v23; // rsi
  bool v24; // zf
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // [rsp+88h] [rbp+48h] BYREF
  int v28; // [rsp+90h] [rbp+50h] BYREF
  __int64 v29; // [rsp+98h] [rbp+58h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+88h] BYREF
  va_list va; // [rsp+C8h] [rbp+88h]
  wchar_t *v32; // [rsp+D0h] [rbp+90h]
  wchar_t *v33; // [rsp+D8h] [rbp+98h]
  va_list va1; // [rsp+E0h] [rbp+A0h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v30 = va_arg(va1, _QWORD);
  v32 = va_arg(va1, wchar_t *);
  v33 = va_arg(va1, wchar_t *);
  v29 = a4;
  v28 = a3;
  v27 = a2;
  v9 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(12);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v27;
  EtwDescriptorBuffer[2] = &v28;
  EtwDescriptorBuffer[4] = &v29;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v9 )
    v14 = RtlLengthSid(v9);
  else
    v14 = 0;
  v15 = Str;
  *((_DWORD *)UserData + 18) = v14;
  UserData[8] = v9;
  v16 = 2;
  UserData[10] = &a7;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  if ( v15 )
    v17 = 2 * wcslen_0(v15) + 2;
  else
    v17 = 2;
  *((_DWORD *)UserData + 26) = v17;
  v18 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v19 = &SourceString;
  UserData[15] = 8;
  if ( v15 )
    v19 = v15;
  UserData[17] = 4;
  v20 = v32;
  UserData[12] = v19;
  UserData[14] = &a9;
  UserData[16] = va;
  if ( v20 )
    v21 = 2 * wcslen_0(v20) + 2;
  else
    v21 = 2;
  *((_DWORD *)UserData + 38) = v21;
  v22 = &SourceString;
  *((_DWORD *)UserData + 39) = 0;
  if ( v20 )
    v22 = v20;
  v23 = v33;
  UserData[18] = v22;
  v24 = v23 == 0;
  if ( v23 )
  {
    v25 = wcslen_0(v23);
    v24 = v23 == 0;
    v16 = 2 * v25 + 2;
  }
  if ( !v24 )
    v18 = v23;
  UserData[20] = v18;
  UserData[22] = va1;
  *((_DWORD *)UserData + 42) = v16;
  *((_DWORD *)UserData + 43) = 0;
  UserData[23] = 1;
  v26 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event45, Filter, 0, 0, 0, 0xCu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v26;
}

```

## disassembly

```asm
0x140007bb0  mov     [rsp-38h+arg_18], r9
0x140007bb5  mov     [rsp-38h+arg_10], r8d
0x140007bba  mov     [rsp-38h+arg_8], rdx
0x140007bbf  push    rbp
0x140007bc0  push    rbx
0x140007bc1  push    rsi
0x140007bc2  push    rdi
0x140007bc3  push    r12
0x140007bc5  push    r14
0x140007bc7  push    r15
0x140007bc9  mov     rbp, rsp
0x140007bcc  sub     rsp, 40h
0x140007bd0  mov     rbx, [rbp+Sid]
0x140007bd4  mov     r15, rcx
0x140007bd7  mov     ecx, 0Ch
0x140007bdc  call    SecGetEtwDescriptorBuffer
0x140007be1  xor     r12d, r12d
0x140007be4  mov     rdi, rax
0x140007be7  test    rax, rax
0x140007bea  jnz     short loc_140007BF6
0x140007bec  mov     eax, 0C000009Ah
0x140007bf1  jmp     loc_140007DA1
0x140007bf6  mov     qword ptr [rdi+8], 8
0x140007bfe  lea     rax, [rbp+arg_8]
0x140007c02  mov     [rdi], rax
0x140007c05  lea     rax, [rbp+arg_10]
0x140007c09  mov     [rdi+10h], rax
0x140007c0d  lea     rax, [rbp+arg_18]
0x140007c11  mov     [rdi+20h], rax
0x140007c15  lea     rax, [rbp+arg_20]
0x140007c19  mov     [rdi+30h], rax
0x140007c1d  mov     qword ptr [rdi+18h], 4
0x140007c25  mov     qword ptr [rdi+28h], 8
0x140007c2d  mov     qword ptr [rdi+38h], 4
0x140007c35  test    rbx, rbx
0x140007c38  jz      short loc_140007C4B
0x140007c3a  mov     rcx, rbx; Sid
0x140007c3d  call    cs:__imp_RtlLengthSid
0x140007c44  nop     dword ptr [rax+rax+00h]
0x140007c49  jmp     short loc_140007C4E
0x140007c4b  mov     eax, r12d
0x140007c4e  mov     rsi, [rbp+Str]
0x140007c52  mov     [rdi+48h], eax
0x140007c55  lea     rax, [rbp+arg_30]
0x140007c59  mov     [rdi+40h], rbx
0x140007c5d  mov     ebx, 2
0x140007c62  mov     [rdi+50h], rax
0x140007c66  mov     [rdi+4Ch], r12d
0x140007c6a  mov     qword ptr [rdi+58h], 4
0x140007c72  test    rsi, rsi
0x140007c75  jz      short loc_140007C88
0x140007c77  mov     rcx, rsi; Str
0x140007c7a  call    wcslen_0
0x140007c7f  lea     ecx, ds:2[rax*2]
0x140007c86  jmp     short loc_140007C8A
0x140007c88  mov     ecx, ebx
0x140007c8a  test    rsi, rsi
0x140007c8d  mov     [rdi+68h], ecx
0x140007c90  lea     r14, SourceString
0x140007c97  mov     [rdi+6Ch], r12d
0x140007c9b  mov     rax, r14
0x140007c9e  mov     qword ptr [rdi+78h], 8
0x140007ca6  cmovnz  rax, rsi
0x140007caa  mov     qword ptr [rdi+88h], 4
0x140007cb5  mov     rsi, [rbp+arg_50]
0x140007cbc  mov     [rdi+60h], rax
0x140007cc0  lea     rax, [rbp+arg_40]
0x140007cc7  mov     [rdi+70h], rax
0x140007ccb  lea     rax, [rbp+arg_48]
0x140007cd2  mov     [rdi+80h], rax
0x140007cd9  test    rsi, rsi
0x140007cdc  jz      short loc_140007CEF
0x140007cde  mov     rcx, rsi; Str
0x140007ce1  call    wcslen_0
0x140007ce6  lea     ecx, ds:2[rax*2]
0x140007ced  jmp     short loc_140007CF1
0x140007cef  mov     ecx, ebx
0x140007cf1  test    rsi, rsi
0x140007cf4  mov     [rdi+98h], ecx
0x140007cfa  mov     rax, r14
0x140007cfd  mov     [rdi+9Ch], r12d
0x140007d04  cmovnz  rax, rsi
0x140007d08  mov     rsi, [rbp+arg_58]
0x140007d0f  mov     [rdi+90h], rax
0x140007d16  test    rsi, rsi
0x140007d19  jz      short loc_140007D2D
0x140007d1b  mov     rcx, rsi; Str
0x140007d1e  call    wcslen_0
0x140007d23  test    rsi, rsi
0x140007d26  lea     ebx, ds:2[rax*2]
0x140007d2d  cmovnz  r14, rsi
0x140007d31  mov     [rsp+40h+UserData], rdi; UserData
0x140007d36  lea     rax, [rbp+arg_60]
0x140007d3d  mov     [rdi+0A0h], r14
0x140007d44  mov     [rdi+0B0h], rax
0x140007d4b  lea     rdx, Event45; EventDescriptor
0x140007d52  mov     [rdi+0A8h], ebx
0x140007d58  xor     r9d, r9d; Flags
0x140007d5b  mov     [rdi+0ACh], r12d
0x140007d62  mov     r8, r15; Filter
0x140007d65  mov     qword ptr [rdi+0B8h], 1
0x140007d70  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140007d77  mov     [rsp+40h+UserDataCount], 0Ch; UserDataCount
0x140007d7f  mov     [rsp+40h+RelatedActivityId], r12; RelatedActivityId
0x140007d84  mov     [rsp+40h+ActivityId], r12; ActivityId
0x140007d89  call    cs:__imp_EtwWriteEx
0x140007d90  nop     dword ptr [rax+rax+00h]
0x140007d95  mov     rcx, rdi; ListEntry
0x140007d98  mov     ebx, eax
0x140007d9a  call    SecReleaseEtwDescriptorBuffer
0x140007d9f  mov     eax, ebx
0x140007da1  add     rsp, 40h
0x140007da5  pop     r15
0x140007da7  pop     r14
0x140007da9  pop     r12
0x140007dab  pop     rdi
0x140007dac  pop     rsi
0x140007dad  pop     rbx
0x140007dae  pop     rbp
0x140007daf  retn
```
