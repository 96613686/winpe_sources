# EventDasdAccessWrite

- ea: `0x140004e08`
- end: `0x140004fb0`
- name: `EventDasdAccessWrite`
- size: `424`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, char, PSID Sid, char, wchar_t *Str, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400057a8`

## callees

- `0x140004e08`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140004f88`
- `ntoskrnl!EtwWrite` at `0x140004f88`
- `ntoskrnl!RtlLengthSid` at `0x140004e95`
- `ntoskrnl!RtlLengthSid` at `0x140004e95`

## pseudocode

```c
__int64 EventDasdAccessWrite(
        PCEVENT_DESCRIPTOR EventDescriptor,
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
  const wchar_t *v15; // rbx
  int v16; // ecx
  const WCHAR *v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // [rsp+78h] [rbp+48h] BYREF
  int v20; // [rsp+80h] [rbp+50h] BYREF
  __int64 v21; // [rsp+88h] [rbp+58h] BYREF
  __int64 v22; // [rsp+B8h] [rbp+88h] BYREF
  va_list va; // [rsp+B8h] [rbp+88h]
  __int64 v24; // [rsp+C0h] [rbp+90h] BYREF
  va_list va1; // [rsp+C0h] [rbp+90h]
  __int64 v26; // [rsp+C8h] [rbp+98h] BYREF
  va_list va2; // [rsp+C8h] [rbp+98h]
  va_list va3; // [rsp+D0h] [rbp+A0h] BYREF

  va_start(va3, a9);
  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
  v22 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v24 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v26 = va_arg(va3, _QWORD);
  v21 = a4;
  v20 = a3;
  v19 = a2;
  v9 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(12);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v19;
  EtwDescriptorBuffer[2] = &v20;
  EtwDescriptorBuffer[4] = &v21;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v9 )
    v14 = RtlLengthSid(v9);
  else
    v14 = 0;
  UserData[8] = v9;
  v15 = Str;
  *((_DWORD *)UserData + 18) = v14;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a7;
  UserData[11] = 4;
  if ( v15 )
    v16 = 2 * wcslen_0(v15) + 2;
  else
    v16 = 2;
  *((_DWORD *)UserData + 26) = v16;
  v17 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  UserData[15] = 8;
  if ( v15 )
    v17 = v15;
  UserData[17] = 8;
  UserData[12] = v17;
  UserData[19] = 4;
  UserData[14] = &a9;
  UserData[21] = 8;
  UserData[16] = va;
  UserData[18] = va1;
  UserData[20] = va2;
  UserData[22] = va3;
  UserData[23] = 4;
  v18 = EtwWrite(Microsoft_Windows_SECHandle, EventDescriptor, 0, 0xCu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v18;
}

```

## disassembly

```asm
0x140004e08  mov     [rsp-38h+arg_18], r9
0x140004e0d  mov     [rsp-38h+arg_10], r8d
0x140004e12  mov     [rsp-38h+arg_8], rdx
0x140004e17  push    rbp
0x140004e18  push    rbx
0x140004e19  push    rsi
0x140004e1a  push    rdi
0x140004e1b  push    r12
0x140004e1d  push    r14
0x140004e1f  push    r15
0x140004e21  mov     rbp, rsp
0x140004e24  sub     rsp, 30h
0x140004e28  mov     rbx, [rbp+Sid]
0x140004e2c  mov     rsi, rcx
0x140004e2f  mov     ecx, 0Ch
0x140004e34  call    SecGetEtwDescriptorBuffer
0x140004e39  xor     r14d, r14d
0x140004e3c  mov     rdi, rax
0x140004e3f  test    rax, rax
0x140004e42  jnz     short loc_140004E4E
0x140004e44  mov     eax, 0C000009Ah
0x140004e49  jmp     loc_140004FA0
0x140004e4e  mov     qword ptr [rdi+8], 8
0x140004e56  lea     rax, [rbp+arg_8]
0x140004e5a  mov     [rdi], rax
0x140004e5d  lea     rax, [rbp+arg_10]
0x140004e61  mov     [rdi+10h], rax
0x140004e65  lea     rax, [rbp+arg_18]
0x140004e69  mov     [rdi+20h], rax
0x140004e6d  lea     rax, [rbp+arg_20]
0x140004e71  mov     [rdi+30h], rax
0x140004e75  mov     qword ptr [rdi+18h], 4
0x140004e7d  mov     qword ptr [rdi+28h], 8
0x140004e85  mov     qword ptr [rdi+38h], 4
0x140004e8d  test    rbx, rbx
0x140004e90  jz      short loc_140004EA3
0x140004e92  mov     rcx, rbx; Sid
0x140004e95  call    cs:__imp_RtlLengthSid
0x140004e9c  nop     dword ptr [rax+rax+00h]
0x140004ea1  jmp     short loc_140004EA6
0x140004ea3  mov     eax, r14d
0x140004ea6  mov     [rdi+40h], rbx
0x140004eaa  mov     rbx, [rbp+Str]
0x140004eae  mov     [rdi+48h], eax
0x140004eb1  lea     rax, [rbp+arg_30]
0x140004eb5  mov     [rdi+4Ch], r14d
0x140004eb9  mov     [rdi+50h], rax
0x140004ebd  mov     qword ptr [rdi+58h], 4
0x140004ec5  test    rbx, rbx
0x140004ec8  jz      short loc_140004EDB
0x140004eca  mov     rcx, rbx; Str
0x140004ecd  call    wcslen_0
0x140004ed2  lea     ecx, ds:2[rax*2]
0x140004ed9  jmp     short loc_140004EE0
0x140004edb  mov     ecx, 2
0x140004ee0  mov     [rdi+68h], ecx
0x140004ee3  lea     rax, SourceString
0x140004eea  mov     [rdi+6Ch], r14d
0x140004eee  test    rbx, rbx
0x140004ef1  mov     qword ptr [rdi+78h], 8
0x140004ef9  mov     r9d, 0Ch; UserDataCount
0x140004eff  cmovnz  rax, rbx
0x140004f03  mov     qword ptr [rdi+88h], 8
0x140004f0e  mov     [rdi+60h], rax
0x140004f12  xor     r8d, r8d; ActivityId
0x140004f15  lea     rax, [rbp+arg_40]
0x140004f1c  mov     qword ptr [rdi+98h], 4
0x140004f27  mov     [rdi+70h], rax
0x140004f2b  mov     rdx, rsi; EventDescriptor
0x140004f2e  lea     rax, [rbp+arg_48]
0x140004f35  mov     qword ptr [rdi+0A8h], 8
0x140004f40  mov     [rdi+80h], rax
0x140004f47  lea     rax, [rbp+arg_50]
0x140004f4e  mov     [rdi+90h], rax
0x140004f55  lea     rax, [rbp+arg_58]
0x140004f5c  mov     [rdi+0A0h], rax
0x140004f63  lea     rax, [rbp+arg_60]
0x140004f6a  mov     [rdi+0B0h], rax
0x140004f71  mov     qword ptr [rdi+0B8h], 4
0x140004f7c  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140004f83  mov     [rsp+30h+UserData], rdi; UserData
0x140004f88  call    cs:__imp_EtwWrite
0x140004f8f  nop     dword ptr [rax+rax+00h]
0x140004f94  mov     rcx, rdi; ListEntry
0x140004f97  mov     ebx, eax
0x140004f99  call    SecReleaseEtwDescriptorBuffer
0x140004f9e  mov     eax, ebx
0x140004fa0  add     rsp, 30h
0x140004fa4  pop     r15
0x140004fa6  pop     r14
0x140004fa8  pop     r12
0x140004faa  pop     rdi
0x140004fab  pop     rsi
0x140004fac  pop     rbx
0x140004fad  pop     rbp
0x140004fae  retn
```
