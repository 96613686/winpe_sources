# EventWriteEnumValueKey

- ea: `0x140007870`
- end: `0x140007a30`
- name: `EventWriteEnumValueKey`
- size: `448`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007db4`

## callees

- `0x140007870`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140007a0a`
- `ntoskrnl!EtwWriteEx` at `0x140007a0a`
- `ntoskrnl!RtlLengthSid` at `0x14000790c`
- `ntoskrnl!RtlLengthSid` at `0x14000790c`

## pseudocode

```c
__int64 EventWriteEnumValueKey(
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
  v23 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event55, Filter, 0, 0, 0, 0xAu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v23;
}

```

## disassembly

```asm
0x140007870  mov     [rsp+arg_18], r9
0x140007875  mov     [rsp+arg_10], r8d
0x14000787a  mov     [rsp+arg_8], rdx
0x14000787f  push    rbx
0x140007880  push    rbp
0x140007881  push    rsi
0x140007882  push    rdi
0x140007883  push    r14
0x140007885  push    r15
0x140007887  sub     rsp, 48h
0x14000788b  mov     rbx, [rsp+78h+Sid]
0x140007893  mov     r14, rcx
0x140007896  mov     ecx, 0Ah
0x14000789b  call    SecGetEtwDescriptorBuffer
0x1400078a0  xor     r15d, r15d
0x1400078a3  mov     rdi, rax
0x1400078a6  test    rax, rax
0x1400078a9  jnz     short loc_1400078B5
0x1400078ab  mov     eax, 0C000009Ah
0x1400078b0  jmp     loc_140007A22
0x1400078b5  mov     qword ptr [rdi+8], 8
0x1400078bd  lea     rax, [rsp+78h+arg_8]
0x1400078c5  mov     [rdi], rax
0x1400078c8  lea     rax, [rsp+78h+arg_10]
0x1400078d0  mov     [rdi+10h], rax
0x1400078d4  lea     rax, [rsp+78h+arg_18]
0x1400078dc  mov     [rdi+20h], rax
0x1400078e0  lea     rax, [rsp+78h+arg_20]
0x1400078e8  mov     [rdi+30h], rax
0x1400078ec  mov     qword ptr [rdi+18h], 4
0x1400078f4  mov     qword ptr [rdi+28h], 8
0x1400078fc  mov     qword ptr [rdi+38h], 4
0x140007904  test    rbx, rbx
0x140007907  jz      short loc_14000791A
0x140007909  mov     rcx, rbx; Sid
0x14000790c  call    cs:__imp_RtlLengthSid
0x140007913  nop     dword ptr [rax+rax+00h]
0x140007918  jmp     short loc_14000791D
0x14000791a  mov     eax, r15d
0x14000791d  mov     [rdi+40h], rbx
0x140007921  mov     esi, 2
0x140007926  mov     rbx, [rsp+78h+Str]
0x14000792e  mov     [rdi+48h], eax
0x140007931  lea     rax, [rsp+78h+arg_30]
0x140007939  mov     [rdi+4Ch], r15d
0x14000793d  mov     [rdi+50h], rax
0x140007941  mov     qword ptr [rdi+58h], 4
0x140007949  test    rbx, rbx
0x14000794c  jz      short loc_14000795F
0x14000794e  mov     rcx, rbx; Str
0x140007951  call    wcslen_0
0x140007956  lea     ecx, ds:2[rax*2]
0x14000795d  jmp     short loc_140007961
0x14000795f  mov     ecx, esi
0x140007961  test    rbx, rbx
0x140007964  mov     [rdi+68h], ecx
0x140007967  lea     rbp, SourceString
0x14000796e  mov     [rdi+6Ch], r15d
0x140007972  mov     rax, rbp
0x140007975  cmovnz  rax, rbx
0x140007979  mov     rbx, [rsp+78h+arg_40]
0x140007981  mov     [rdi+60h], rax
0x140007985  test    rbx, rbx
0x140007988  jz      short loc_14000799C
0x14000798a  mov     rcx, rbx; Str
0x14000798d  call    wcslen_0
0x140007992  test    rbx, rbx
0x140007995  lea     esi, ds:2[rax*2]
0x14000799c  cmovnz  rbp, rbx
0x1400079a0  mov     [rsp+78h+UserData], rdi; UserData
0x1400079a5  lea     rax, [rsp+78h+arg_48]
0x1400079ad  mov     [rdi+70h], rbp
0x1400079b1  mov     [rdi+80h], rax
0x1400079b8  lea     rdx, Event55; EventDescriptor
0x1400079bf  lea     rax, [rsp+78h+arg_50]
0x1400079c7  mov     [rdi+78h], esi
0x1400079ca  mov     [rdi+90h], rax
0x1400079d1  xor     r9d, r9d; Flags
0x1400079d4  mov     [rdi+7Ch], r15d
0x1400079d8  mov     r8, r14; Filter
0x1400079db  mov     qword ptr [rdi+88h], 8
0x1400079e6  mov     qword ptr [rdi+98h], 1
0x1400079f1  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400079f8  mov     [rsp+78h+UserDataCount], 0Ah; UserDataCount
0x140007a00  mov     [rsp+78h+RelatedActivityId], r15; RelatedActivityId
0x140007a05  mov     [rsp+78h+ActivityId], r15; ActivityId
0x140007a0a  call    cs:__imp_EtwWriteEx
0x140007a11  nop     dword ptr [rax+rax+00h]
0x140007a16  mov     rcx, rdi; ListEntry
0x140007a19  mov     ebx, eax
0x140007a1b  call    SecReleaseEtwDescriptorBuffer
0x140007a20  mov     eax, ebx
0x140007a22  add     rsp, 48h
0x140007a26  pop     r15
0x140007a28  pop     r14
0x140007a2a  pop     rdi
0x140007a2b  pop     rsi
0x140007a2c  pop     rbp
0x140007a2d  pop     rbx
0x140007a2e  retn
```
