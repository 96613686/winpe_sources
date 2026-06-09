# EventWriteQueryKeyInfo

- ea: `0x140007a30`
- end: `0x140007bae`
- name: `EventWriteQueryKeyInfo`
- size: `382`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003715c`

## callees

- `0x140007a30`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140007b8d`
- `ntoskrnl!EtwWriteEx` at `0x140007b8d`
- `ntoskrnl!RtlLengthSid` at `0x140007abb`
- `ntoskrnl!RtlLengthSid` at `0x140007abb`

## pseudocode

```c
__int64 EventWriteQueryKeyInfo(ULONG64 Filter, __int64 a2, int a3, __int64 a4, char a5, PSID Sid, ...)
{
  PSID v6; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v11; // eax
  const wchar_t *v12; // rbx
  int v13; // ecx
  const WCHAR *v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  int v17; // [rsp+70h] [rbp+18h] BYREF
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF
  __int64 v19; // [rsp+90h] [rbp+38h] BYREF
  va_list va; // [rsp+90h] [rbp+38h]
  wchar_t *Str; // [rsp+98h] [rbp+40h]
  __int64 v22; // [rsp+A0h] [rbp+48h] BYREF
  va_list va1; // [rsp+A0h] [rbp+48h]
  va_list va2; // [rsp+A8h] [rbp+50h] BYREF

  va_start(va2, Sid);
  va_start(va1, Sid);
  va_start(va, Sid);
  v19 = va_arg(va1, _QWORD);
  Str = va_arg(va1, wchar_t *);
  va_copy(va2, va1);
  v22 = va_arg(va2, _QWORD);
  v18 = a4;
  v17 = a3;
  v16 = a2;
  v6 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(9);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v16;
  EtwDescriptorBuffer[2] = &v17;
  EtwDescriptorBuffer[4] = &v18;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v6 )
    v11 = RtlLengthSid(v6);
  else
    v11 = 0;
  UserData[8] = v6;
  v12 = Str;
  *((_DWORD *)UserData + 18) = v11;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = va;
  UserData[11] = 4;
  if ( v12 )
    v13 = 2 * wcslen_0(v12) + 2;
  else
    v13 = 2;
  v14 = &SourceString;
  *((_DWORD *)UserData + 26) = v13;
  *((_DWORD *)UserData + 27) = 0;
  UserData[15] = 8;
  if ( v12 )
    v14 = v12;
  UserData[17] = 1;
  UserData[12] = v14;
  UserData[14] = va1;
  UserData[16] = va2;
  v15 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event58, Filter, 0, 0, 0, 9u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v15;
}

```

## disassembly

```asm
0x140007a30  mov     [rsp+arg_18], r9
0x140007a35  mov     [rsp+arg_10], r8d
0x140007a3a  mov     [rsp+arg_8], rdx
0x140007a3f  push    rbx
0x140007a40  push    rsi
0x140007a41  push    rdi
0x140007a42  sub     rsp, 40h
0x140007a46  mov     rbx, [rsp+58h+Sid]
0x140007a4e  mov     rsi, rcx
0x140007a51  mov     ecx, 9
0x140007a56  call    SecGetEtwDescriptorBuffer
0x140007a5b  mov     rdi, rax
0x140007a5e  test    rax, rax
0x140007a61  jnz     short loc_140007A6D
0x140007a63  mov     eax, 0C000009Ah
0x140007a68  jmp     loc_140007BA5
0x140007a6d  mov     qword ptr [rdi+8], 8
0x140007a75  lea     rax, [rsp+58h+arg_8]
0x140007a7a  mov     [rdi], rax
0x140007a7d  lea     rax, [rsp+58h+arg_10]
0x140007a82  mov     [rdi+10h], rax
0x140007a86  lea     rax, [rsp+58h+arg_18]
0x140007a8b  mov     [rdi+20h], rax
0x140007a8f  lea     rax, [rsp+58h+arg_20]
0x140007a97  mov     [rdi+30h], rax
0x140007a9b  mov     qword ptr [rdi+18h], 4
0x140007aa3  mov     qword ptr [rdi+28h], 8
0x140007aab  mov     qword ptr [rdi+38h], 4
0x140007ab3  test    rbx, rbx
0x140007ab6  jz      short loc_140007AC9
0x140007ab8  mov     rcx, rbx; Sid
0x140007abb  call    cs:__imp_RtlLengthSid
0x140007ac2  nop     dword ptr [rax+rax+00h]
0x140007ac7  jmp     short loc_140007ACB
0x140007ac9  xor     eax, eax
0x140007acb  mov     [rdi+40h], rbx
0x140007acf  mov     rbx, [rsp+58h+Str]
0x140007ad7  mov     [rdi+48h], eax
0x140007ada  lea     rax, [rsp+58h+arg_30]
0x140007ae2  mov     dword ptr [rdi+4Ch], 0
0x140007ae9  mov     [rdi+50h], rax
0x140007aed  mov     qword ptr [rdi+58h], 4
0x140007af5  test    rbx, rbx
0x140007af8  jz      short loc_140007B0B
0x140007afa  mov     rcx, rbx; Str
0x140007afd  call    wcslen_0
0x140007b02  lea     ecx, ds:2[rax*2]
0x140007b09  jmp     short loc_140007B10
0x140007b0b  mov     ecx, 2
0x140007b10  mov     [rsp+58h+UserData], rdi; UserData
0x140007b15  lea     rax, SourceString
0x140007b1c  mov     [rdi+68h], ecx
0x140007b1f  lea     rdx, Event58; EventDescriptor
0x140007b26  mov     dword ptr [rdi+6Ch], 0
0x140007b2d  test    rbx, rbx
0x140007b30  mov     qword ptr [rdi+78h], 8
0x140007b38  mov     r8, rsi; Filter
0x140007b3b  cmovnz  rax, rbx
0x140007b3f  mov     qword ptr [rdi+88h], 1
0x140007b4a  mov     [rdi+60h], rax
0x140007b4e  xor     r9d, r9d; Flags
0x140007b51  lea     rax, [rsp+58h+arg_40]
0x140007b59  mov     [rsp+58h+UserDataCount], 9; UserDataCount
0x140007b61  mov     [rdi+70h], rax
0x140007b65  lea     rax, [rsp+58h+arg_48]
0x140007b6d  mov     [rdi+80h], rax
0x140007b74  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140007b7b  mov     [rsp+58h+RelatedActivityId], 0; RelatedActivityId
0x140007b84  mov     [rsp+58h+ActivityId], 0; ActivityId
0x140007b8d  call    cs:__imp_EtwWriteEx
0x140007b94  nop     dword ptr [rax+rax+00h]
0x140007b99  mov     rcx, rdi; ListEntry
0x140007b9c  mov     ebx, eax
0x140007b9e  call    SecReleaseEtwDescriptorBuffer
0x140007ba3  mov     eax, ebx
0x140007ba5  add     rsp, 40h
0x140007ba9  pop     rdi
0x140007baa  pop     rsi
0x140007bab  pop     rbx
0x140007bac  retn
```
