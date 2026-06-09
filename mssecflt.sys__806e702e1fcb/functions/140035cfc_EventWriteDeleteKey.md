# EventWriteDeleteKey

- ea: `0x140035cfc`
- end: `0x140035e7a`
- name: `EventWriteDeleteKey`
- size: `382`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036df4`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140035cfc`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140035e59`
- `ntoskrnl!EtwWriteEx` at `0x140035e59`
- `ntoskrnl!RtlLengthSid` at `0x140035d87`
- `ntoskrnl!RtlLengthSid` at `0x140035d87`

## pseudocode

```c
__int64 EventWriteDeleteKey(ULONG64 Filter, __int64 a2, int a3, __int64 a4, char a5, PSID Sid, ...)
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
  v15 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event9, Filter, 0, 0, 0, 9u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v15;
}

```

## disassembly

```asm
0x140035cfc  mov     [rsp+arg_18], r9
0x140035d01  mov     [rsp+arg_10], r8d
0x140035d06  mov     [rsp+arg_8], rdx
0x140035d0b  push    rbx
0x140035d0c  push    rsi
0x140035d0d  push    rdi
0x140035d0e  sub     rsp, 40h
0x140035d12  mov     rbx, [rsp+58h+Sid]
0x140035d1a  mov     rsi, rcx
0x140035d1d  mov     ecx, 9
0x140035d22  call    SecGetEtwDescriptorBuffer
0x140035d27  mov     rdi, rax
0x140035d2a  test    rax, rax
0x140035d2d  jnz     short loc_140035D39
0x140035d2f  mov     eax, 0C000009Ah
0x140035d34  jmp     loc_140035E71
0x140035d39  mov     qword ptr [rdi+8], 8
0x140035d41  lea     rax, [rsp+58h+arg_8]
0x140035d46  mov     [rdi], rax
0x140035d49  lea     rax, [rsp+58h+arg_10]
0x140035d4e  mov     [rdi+10h], rax
0x140035d52  lea     rax, [rsp+58h+arg_18]
0x140035d57  mov     [rdi+20h], rax
0x140035d5b  lea     rax, [rsp+58h+arg_20]
0x140035d63  mov     [rdi+30h], rax
0x140035d67  mov     qword ptr [rdi+18h], 4
0x140035d6f  mov     qword ptr [rdi+28h], 8
0x140035d77  mov     qword ptr [rdi+38h], 4
0x140035d7f  test    rbx, rbx
0x140035d82  jz      short loc_140035D95
0x140035d84  mov     rcx, rbx; Sid
0x140035d87  call    cs:__imp_RtlLengthSid
0x140035d8e  nop     dword ptr [rax+rax+00h]
0x140035d93  jmp     short loc_140035D97
0x140035d95  xor     eax, eax
0x140035d97  mov     [rdi+40h], rbx
0x140035d9b  mov     rbx, [rsp+58h+Str]
0x140035da3  mov     [rdi+48h], eax
0x140035da6  lea     rax, [rsp+58h+arg_30]
0x140035dae  mov     dword ptr [rdi+4Ch], 0
0x140035db5  mov     [rdi+50h], rax
0x140035db9  mov     qword ptr [rdi+58h], 4
0x140035dc1  test    rbx, rbx
0x140035dc4  jz      short loc_140035DD7
0x140035dc6  mov     rcx, rbx; Str
0x140035dc9  call    wcslen_0
0x140035dce  lea     ecx, ds:2[rax*2]
0x140035dd5  jmp     short loc_140035DDC
0x140035dd7  mov     ecx, 2
0x140035ddc  mov     [rsp+58h+UserData], rdi; UserData
0x140035de1  lea     rax, SourceString
0x140035de8  mov     [rdi+68h], ecx
0x140035deb  lea     rdx, Event9; EventDescriptor
0x140035df2  mov     dword ptr [rdi+6Ch], 0
0x140035df9  test    rbx, rbx
0x140035dfc  mov     qword ptr [rdi+78h], 8
0x140035e04  mov     r8, rsi; Filter
0x140035e07  cmovnz  rax, rbx
0x140035e0b  mov     qword ptr [rdi+88h], 1
0x140035e16  mov     [rdi+60h], rax
0x140035e1a  xor     r9d, r9d; Flags
0x140035e1d  lea     rax, [rsp+58h+arg_40]
0x140035e25  mov     [rsp+58h+UserDataCount], 9; UserDataCount
0x140035e2d  mov     [rdi+70h], rax
0x140035e31  lea     rax, [rsp+58h+arg_48]
0x140035e39  mov     [rdi+80h], rax
0x140035e40  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140035e47  mov     [rsp+58h+RelatedActivityId], 0; RelatedActivityId
0x140035e50  mov     [rsp+58h+ActivityId], 0; ActivityId
0x140035e59  call    cs:__imp_EtwWriteEx
0x140035e60  nop     dword ptr [rax+rax+00h]
0x140035e65  mov     rcx, rdi; ListEntry
0x140035e68  mov     ebx, eax
0x140035e6a  call    SecReleaseEtwDescriptorBuffer
0x140035e6f  mov     eax, ebx
0x140035e71  add     rsp, 40h
0x140035e75  pop     rdi
0x140035e76  pop     rsi
0x140035e77  pop     rbx
0x140035e78  retn
```
