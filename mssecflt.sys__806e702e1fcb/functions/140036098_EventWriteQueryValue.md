# EventWriteQueryValue

- ea: `0x140036098`
- end: `0x140036258`
- name: `EventWriteQueryValue`
- size: `448`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400373fc`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140036098`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140036232`
- `ntoskrnl!EtwWriteEx` at `0x140036232`
- `ntoskrnl!RtlLengthSid` at `0x140036134`
- `ntoskrnl!RtlLengthSid` at `0x140036134`

## pseudocode

```c
__int64 EventWriteQueryValue(
        ULONG64 Filter,
        __int64 a2,
        int a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        wchar_t *Str,
        wchar_t *a9,
        ...)
{
  PSID v9; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v14; // eax
  int v15; // esi
  const wchar_t *v16; // rbx
  int v17; // ecx
  const WCHAR *v18; // rbp
  const WCHAR *v19; // rax
  const wchar_t *v20; // rbx
  bool v21; // zf
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+88h] [rbp+10h] BYREF
  int v25; // [rsp+90h] [rbp+18h] BYREF
  __int64 v26; // [rsp+98h] [rbp+20h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+50h] BYREF
  va_list va; // [rsp+C8h] [rbp+50h]
  va_list va1; // [rsp+D0h] [rbp+58h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v27 = va_arg(va1, _QWORD);
  v26 = a4;
  v25 = a3;
  v24 = a2;
  v9 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(10);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v24;
  EtwDescriptorBuffer[2] = &v25;
  EtwDescriptorBuffer[4] = &v26;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v9 )
    v14 = RtlLengthSid(v9);
  else
    v14 = 0;
  UserData[8] = v9;
  v15 = 2;
  v16 = Str;
  *((_DWORD *)UserData + 18) = v14;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a7;
  UserData[11] = 4;
  if ( v16 )
    v17 = 2 * wcslen_0(v16) + 2;
  else
    v17 = 2;
  *((_DWORD *)UserData + 26) = v17;
  v18 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v19 = &SourceString;
  if ( v16 )
    v19 = v16;
  v20 = a9;
  UserData[12] = v19;
  v21 = v20 == 0;
  if ( v20 )
  {
    v22 = wcslen_0(v20);
    v21 = v20 == 0;
    v15 = 2 * v22 + 2;
  }
  if ( !v21 )
    v18 = v20;
  UserData[14] = v18;
  UserData[16] = va;
  *((_DWORD *)UserData + 30) = v15;
  UserData[18] = va1;
  *((_DWORD *)UserData + 31) = 0;
  UserData[17] = 8;
  UserData[19] = 1;
  v23 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event41, Filter, 0, 0, 0, 0xAu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v23;
}

```

## disassembly

```asm
0x140036098  mov     [rsp+arg_18], r9
0x14003609d  mov     [rsp+arg_10], r8d
0x1400360a2  mov     [rsp+arg_8], rdx
0x1400360a7  push    rbx
0x1400360a8  push    rbp
0x1400360a9  push    rsi
0x1400360aa  push    rdi
0x1400360ab  push    r14
0x1400360ad  push    r15
0x1400360af  sub     rsp, 48h
0x1400360b3  mov     rbx, [rsp+78h+Sid]
0x1400360bb  mov     r14, rcx
0x1400360be  mov     ecx, 0Ah
0x1400360c3  call    SecGetEtwDescriptorBuffer
0x1400360c8  xor     r15d, r15d
0x1400360cb  mov     rdi, rax
0x1400360ce  test    rax, rax
0x1400360d1  jnz     short loc_1400360DD
0x1400360d3  mov     eax, 0C000009Ah
0x1400360d8  jmp     loc_14003624A
0x1400360dd  mov     qword ptr [rdi+8], 8
0x1400360e5  lea     rax, [rsp+78h+arg_8]
0x1400360ed  mov     [rdi], rax
0x1400360f0  lea     rax, [rsp+78h+arg_10]
0x1400360f8  mov     [rdi+10h], rax
0x1400360fc  lea     rax, [rsp+78h+arg_18]
0x140036104  mov     [rdi+20h], rax
0x140036108  lea     rax, [rsp+78h+arg_20]
0x140036110  mov     [rdi+30h], rax
0x140036114  mov     qword ptr [rdi+18h], 4
0x14003611c  mov     qword ptr [rdi+28h], 8
0x140036124  mov     qword ptr [rdi+38h], 4
0x14003612c  test    rbx, rbx
0x14003612f  jz      short loc_140036142
0x140036131  mov     rcx, rbx; Sid
0x140036134  call    cs:__imp_RtlLengthSid
0x14003613b  nop     dword ptr [rax+rax+00h]
0x140036140  jmp     short loc_140036145
0x140036142  mov     eax, r15d
0x140036145  mov     [rdi+40h], rbx
0x140036149  mov     esi, 2
0x14003614e  mov     rbx, [rsp+78h+Str]
0x140036156  mov     [rdi+48h], eax
0x140036159  lea     rax, [rsp+78h+arg_30]
0x140036161  mov     [rdi+4Ch], r15d
0x140036165  mov     [rdi+50h], rax
0x140036169  mov     qword ptr [rdi+58h], 4
0x140036171  test    rbx, rbx
0x140036174  jz      short loc_140036187
0x140036176  mov     rcx, rbx; Str
0x140036179  call    wcslen_0
0x14003617e  lea     ecx, ds:2[rax*2]
0x140036185  jmp     short loc_140036189
0x140036187  mov     ecx, esi
0x140036189  test    rbx, rbx
0x14003618c  mov     [rdi+68h], ecx
0x14003618f  lea     rbp, SourceString
0x140036196  mov     [rdi+6Ch], r15d
0x14003619a  mov     rax, rbp
0x14003619d  cmovnz  rax, rbx
0x1400361a1  mov     rbx, [rsp+78h+arg_40]
0x1400361a9  mov     [rdi+60h], rax
0x1400361ad  test    rbx, rbx
0x1400361b0  jz      short loc_1400361C4
0x1400361b2  mov     rcx, rbx; Str
0x1400361b5  call    wcslen_0
0x1400361ba  test    rbx, rbx
0x1400361bd  lea     esi, ds:2[rax*2]
0x1400361c4  cmovnz  rbp, rbx
0x1400361c8  mov     [rsp+78h+UserData], rdi; UserData
0x1400361cd  lea     rax, [rsp+78h+arg_48]
0x1400361d5  mov     [rdi+70h], rbp
0x1400361d9  mov     [rdi+80h], rax
0x1400361e0  lea     rdx, Event41; EventDescriptor
0x1400361e7  lea     rax, [rsp+78h+arg_50]
0x1400361ef  mov     [rdi+78h], esi
0x1400361f2  mov     [rdi+90h], rax
0x1400361f9  xor     r9d, r9d; Flags
0x1400361fc  mov     [rdi+7Ch], r15d
0x140036200  mov     r8, r14; Filter
0x140036203  mov     qword ptr [rdi+88h], 8
0x14003620e  mov     qword ptr [rdi+98h], 1
0x140036219  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140036220  mov     [rsp+78h+UserDataCount], 0Ah; UserDataCount
0x140036228  mov     [rsp+78h+RelatedActivityId], r15; RelatedActivityId
0x14003622d  mov     [rsp+78h+ActivityId], r15; ActivityId
0x140036232  call    cs:__imp_EtwWriteEx
0x140036239  nop     dword ptr [rax+rax+00h]
0x14003623e  mov     rcx, rdi; ListEntry
0x140036241  mov     ebx, eax
0x140036243  call    SecReleaseEtwDescriptorBuffer
0x140036248  mov     eax, ebx
0x14003624a  add     rsp, 48h
0x14003624e  pop     r15
0x140036250  pop     r14
0x140036252  pop     rdi
0x140036253  pop     rsi
0x140036254  pop     rbp
0x140036255  pop     rbx
0x140036256  retn
```
