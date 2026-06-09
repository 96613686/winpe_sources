# EventWriteCreateKey

- ea: `0x140035b7c`
- end: `0x140035cfa`
- name: `EventWriteCreateKey`
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
- `0x140035b7c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140035cd9`
- `ntoskrnl!EtwWriteEx` at `0x140035cd9`
- `ntoskrnl!RtlLengthSid` at `0x140035c07`
- `ntoskrnl!RtlLengthSid` at `0x140035c07`

## pseudocode

```c
__int64 EventWriteCreateKey(ULONG64 Filter, __int64 a2, int a3, __int64 a4, char a5, PSID Sid, ...)
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
  v15 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event8, Filter, 0, 0, 0, 9u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v15;
}

```

## disassembly

```asm
0x140035b7c  mov     [rsp+arg_18], r9
0x140035b81  mov     [rsp+arg_10], r8d
0x140035b86  mov     [rsp+arg_8], rdx
0x140035b8b  push    rbx
0x140035b8c  push    rsi
0x140035b8d  push    rdi
0x140035b8e  sub     rsp, 40h
0x140035b92  mov     rbx, [rsp+58h+Sid]
0x140035b9a  mov     rsi, rcx
0x140035b9d  mov     ecx, 9
0x140035ba2  call    SecGetEtwDescriptorBuffer
0x140035ba7  mov     rdi, rax
0x140035baa  test    rax, rax
0x140035bad  jnz     short loc_140035BB9
0x140035baf  mov     eax, 0C000009Ah
0x140035bb4  jmp     loc_140035CF1
0x140035bb9  mov     qword ptr [rdi+8], 8
0x140035bc1  lea     rax, [rsp+58h+arg_8]
0x140035bc6  mov     [rdi], rax
0x140035bc9  lea     rax, [rsp+58h+arg_10]
0x140035bce  mov     [rdi+10h], rax
0x140035bd2  lea     rax, [rsp+58h+arg_18]
0x140035bd7  mov     [rdi+20h], rax
0x140035bdb  lea     rax, [rsp+58h+arg_20]
0x140035be3  mov     [rdi+30h], rax
0x140035be7  mov     qword ptr [rdi+18h], 4
0x140035bef  mov     qword ptr [rdi+28h], 8
0x140035bf7  mov     qword ptr [rdi+38h], 4
0x140035bff  test    rbx, rbx
0x140035c02  jz      short loc_140035C15
0x140035c04  mov     rcx, rbx; Sid
0x140035c07  call    cs:__imp_RtlLengthSid
0x140035c0e  nop     dword ptr [rax+rax+00h]
0x140035c13  jmp     short loc_140035C17
0x140035c15  xor     eax, eax
0x140035c17  mov     [rdi+40h], rbx
0x140035c1b  mov     rbx, [rsp+58h+Str]
0x140035c23  mov     [rdi+48h], eax
0x140035c26  lea     rax, [rsp+58h+arg_30]
0x140035c2e  mov     dword ptr [rdi+4Ch], 0
0x140035c35  mov     [rdi+50h], rax
0x140035c39  mov     qword ptr [rdi+58h], 4
0x140035c41  test    rbx, rbx
0x140035c44  jz      short loc_140035C57
0x140035c46  mov     rcx, rbx; Str
0x140035c49  call    wcslen_0
0x140035c4e  lea     ecx, ds:2[rax*2]
0x140035c55  jmp     short loc_140035C5C
0x140035c57  mov     ecx, 2
0x140035c5c  mov     [rsp+58h+UserData], rdi; UserData
0x140035c61  lea     rax, SourceString
0x140035c68  mov     [rdi+68h], ecx
0x140035c6b  lea     rdx, Event8; EventDescriptor
0x140035c72  mov     dword ptr [rdi+6Ch], 0
0x140035c79  test    rbx, rbx
0x140035c7c  mov     qword ptr [rdi+78h], 8
0x140035c84  mov     r8, rsi; Filter
0x140035c87  cmovnz  rax, rbx
0x140035c8b  mov     qword ptr [rdi+88h], 1
0x140035c96  mov     [rdi+60h], rax
0x140035c9a  xor     r9d, r9d; Flags
0x140035c9d  lea     rax, [rsp+58h+arg_40]
0x140035ca5  mov     [rsp+58h+UserDataCount], 9; UserDataCount
0x140035cad  mov     [rdi+70h], rax
0x140035cb1  lea     rax, [rsp+58h+arg_48]
0x140035cb9  mov     [rdi+80h], rax
0x140035cc0  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140035cc7  mov     [rsp+58h+RelatedActivityId], 0; RelatedActivityId
0x140035cd0  mov     [rsp+58h+ActivityId], 0; ActivityId
0x140035cd9  call    cs:__imp_EtwWriteEx
0x140035ce0  nop     dword ptr [rax+rax+00h]
0x140035ce5  mov     rcx, rdi; ListEntry
0x140035ce8  mov     ebx, eax
0x140035cea  call    SecReleaseEtwDescriptorBuffer
0x140035cef  mov     eax, ebx
0x140035cf1  add     rsp, 40h
0x140035cf5  pop     rdi
0x140035cf6  pop     rsi
0x140035cf7  pop     rbx
0x140035cf8  retn
```
