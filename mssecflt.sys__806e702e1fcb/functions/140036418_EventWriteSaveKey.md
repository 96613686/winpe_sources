# EventWriteSaveKey

- ea: `0x140036418`
- end: `0x1400365d8`
- name: `EventWriteSaveKey`
- size: `448`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037a04`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140036418`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x1400365b2`
- `ntoskrnl!EtwWriteEx` at `0x1400365b2`
- `ntoskrnl!RtlLengthSid` at `0x1400364b4`
- `ntoskrnl!RtlLengthSid` at `0x1400364b4`

## pseudocode

```c
__int64 EventWriteSaveKey(
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
  v23 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event44, Filter, 0, 0, 0, 0xAu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v23;
}

```

## disassembly

```asm
0x140036418  mov     [rsp+arg_18], r9
0x14003641d  mov     [rsp+arg_10], r8d
0x140036422  mov     [rsp+arg_8], rdx
0x140036427  push    rbx
0x140036428  push    rbp
0x140036429  push    rsi
0x14003642a  push    rdi
0x14003642b  push    r14
0x14003642d  push    r15
0x14003642f  sub     rsp, 48h
0x140036433  mov     rbx, [rsp+78h+Sid]
0x14003643b  mov     r14, rcx
0x14003643e  mov     ecx, 0Ah
0x140036443  call    SecGetEtwDescriptorBuffer
0x140036448  xor     r15d, r15d
0x14003644b  mov     rdi, rax
0x14003644e  test    rax, rax
0x140036451  jnz     short loc_14003645D
0x140036453  mov     eax, 0C000009Ah
0x140036458  jmp     loc_1400365CA
0x14003645d  mov     qword ptr [rdi+8], 8
0x140036465  lea     rax, [rsp+78h+arg_8]
0x14003646d  mov     [rdi], rax
0x140036470  lea     rax, [rsp+78h+arg_10]
0x140036478  mov     [rdi+10h], rax
0x14003647c  lea     rax, [rsp+78h+arg_18]
0x140036484  mov     [rdi+20h], rax
0x140036488  lea     rax, [rsp+78h+arg_20]
0x140036490  mov     [rdi+30h], rax
0x140036494  mov     qword ptr [rdi+18h], 4
0x14003649c  mov     qword ptr [rdi+28h], 8
0x1400364a4  mov     qword ptr [rdi+38h], 4
0x1400364ac  test    rbx, rbx
0x1400364af  jz      short loc_1400364C2
0x1400364b1  mov     rcx, rbx; Sid
0x1400364b4  call    cs:__imp_RtlLengthSid
0x1400364bb  nop     dword ptr [rax+rax+00h]
0x1400364c0  jmp     short loc_1400364C5
0x1400364c2  mov     eax, r15d
0x1400364c5  mov     [rdi+40h], rbx
0x1400364c9  mov     esi, 2
0x1400364ce  mov     rbx, [rsp+78h+Str]
0x1400364d6  mov     [rdi+48h], eax
0x1400364d9  lea     rax, [rsp+78h+arg_30]
0x1400364e1  mov     [rdi+4Ch], r15d
0x1400364e5  mov     [rdi+50h], rax
0x1400364e9  mov     qword ptr [rdi+58h], 4
0x1400364f1  test    rbx, rbx
0x1400364f4  jz      short loc_140036507
0x1400364f6  mov     rcx, rbx; Str
0x1400364f9  call    wcslen_0
0x1400364fe  lea     ecx, ds:2[rax*2]
0x140036505  jmp     short loc_140036509
0x140036507  mov     ecx, esi
0x140036509  test    rbx, rbx
0x14003650c  mov     [rdi+68h], ecx
0x14003650f  lea     rbp, SourceString
0x140036516  mov     [rdi+6Ch], r15d
0x14003651a  mov     rax, rbp
0x14003651d  cmovnz  rax, rbx
0x140036521  mov     rbx, [rsp+78h+arg_40]
0x140036529  mov     [rdi+60h], rax
0x14003652d  test    rbx, rbx
0x140036530  jz      short loc_140036544
0x140036532  mov     rcx, rbx; Str
0x140036535  call    wcslen_0
0x14003653a  test    rbx, rbx
0x14003653d  lea     esi, ds:2[rax*2]
0x140036544  cmovnz  rbp, rbx
0x140036548  mov     [rsp+78h+UserData], rdi; UserData
0x14003654d  lea     rax, [rsp+78h+arg_48]
0x140036555  mov     [rdi+70h], rbp
0x140036559  mov     [rdi+80h], rax
0x140036560  lea     rdx, Event44; EventDescriptor
0x140036567  lea     rax, [rsp+78h+arg_50]
0x14003656f  mov     [rdi+78h], esi
0x140036572  mov     [rdi+90h], rax
0x140036579  xor     r9d, r9d; Flags
0x14003657c  mov     [rdi+7Ch], r15d
0x140036580  mov     r8, r14; Filter
0x140036583  mov     qword ptr [rdi+88h], 8
0x14003658e  mov     qword ptr [rdi+98h], 1
0x140036599  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400365a0  mov     [rsp+78h+UserDataCount], 0Ah; UserDataCount
0x1400365a8  mov     [rsp+78h+RelatedActivityId], r15; RelatedActivityId
0x1400365ad  mov     [rsp+78h+ActivityId], r15; ActivityId
0x1400365b2  call    cs:__imp_EtwWriteEx
0x1400365b9  nop     dword ptr [rax+rax+00h]
0x1400365be  mov     rcx, rdi; ListEntry
0x1400365c1  mov     ebx, eax
0x1400365c3  call    SecReleaseEtwDescriptorBuffer
0x1400365c8  mov     eax, ebx
0x1400365ca  add     rsp, 48h
0x1400365ce  pop     r15
0x1400365d0  pop     r14
0x1400365d2  pop     rdi
0x1400365d3  pop     rsi
0x1400365d4  pop     rbp
0x1400365d5  pop     rbx
0x1400365d6  retn
```
