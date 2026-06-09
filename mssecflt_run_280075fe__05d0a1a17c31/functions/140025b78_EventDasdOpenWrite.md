# EventDasdOpenWrite

- ea: `0x140025b78`
- end: `0x140025cf7`
- name: `EventDasdOpenWrite`
- size: `383`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140026d08`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140025b78`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140025cd4`
- `ntoskrnl!EtwWrite` at `0x140025cd4`
- `ntoskrnl!RtlLengthSid` at `0x140025bfd`
- `ntoskrnl!RtlLengthSid` at `0x140025bfd`

## pseudocode

```c
__int64 __fastcall EventDasdOpenWrite(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        wchar_t *Str,
        char a8,
        char a9,
        char a10,
        char a11)
{
  PSID v11; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v15; // eax
  const wchar_t *v16; // rbx
  int v17; // ecx
  const WCHAR *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // [rsp+60h] [rbp+28h] BYREF
  int v21; // [rsp+68h] [rbp+30h] BYREF
  __int64 v22; // [rsp+70h] [rbp+38h] BYREF
  int v23; // [rsp+78h] [rbp+40h] BYREF

  v23 = a4;
  v22 = a3;
  v21 = a2;
  v20 = a1;
  v11 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(11);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v20;
  EtwDescriptorBuffer[2] = &v21;
  EtwDescriptorBuffer[4] = &v22;
  EtwDescriptorBuffer[6] = &v23;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v11 )
    v15 = RtlLengthSid(v11);
  else
    v15 = 0;
  UserData[8] = v11;
  v16 = Str;
  *((_DWORD *)UserData + 18) = v15;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a6;
  UserData[11] = 4;
  if ( v16 )
    v17 = 2 * wcslen_0(v16) + 2;
  else
    v17 = 2;
  *((_DWORD *)UserData + 26) = v17;
  v18 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  UserData[15] = 4;
  UserData[17] = 4;
  if ( v16 )
    v18 = v16;
  UserData[19] = 8;
  UserData[12] = v18;
  UserData[21] = 4;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  v19 = EtwWrite(Microsoft_Windows_SECHandle, &Event15, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v19;
}

```

## disassembly

```asm
0x140025b78  mov     rax, rsp
0x140025b7b  mov     [rax+20h], r9d
0x140025b7f  mov     [rax+18h], r8
0x140025b83  mov     [rax+10h], edx
0x140025b86  mov     [rax+8], rcx
0x140025b8a  push    rbp
0x140025b8b  push    rbx
0x140025b8c  push    rdi
0x140025b8d  push    r14
0x140025b8f  mov     rbp, rsp
0x140025b92  sub     rsp, 38h
0x140025b96  mov     rbx, [rbp+Sid]
0x140025b9a  mov     ecx, 0Bh
0x140025b9f  call    SecGetEtwDescriptorBuffer
0x140025ba4  mov     rdi, rax
0x140025ba7  test    rax, rax
0x140025baa  jnz     short loc_140025BB6
0x140025bac  mov     eax, 0C000009Ah
0x140025bb1  jmp     loc_140025CEC
0x140025bb6  mov     qword ptr [rdi+8], 8
0x140025bbe  lea     rax, [rbp+arg_0]
0x140025bc2  mov     [rdi], rax
0x140025bc5  lea     rax, [rbp+arg_8]
0x140025bc9  mov     [rdi+10h], rax
0x140025bcd  lea     rax, [rbp+arg_10]
0x140025bd1  mov     [rdi+20h], rax
0x140025bd5  lea     rax, [rbp+arg_18]
0x140025bd9  mov     [rdi+30h], rax
0x140025bdd  mov     qword ptr [rdi+18h], 4
0x140025be5  mov     qword ptr [rdi+28h], 8
0x140025bed  mov     qword ptr [rdi+38h], 4
0x140025bf5  test    rbx, rbx
0x140025bf8  jz      short loc_140025C0B
0x140025bfa  mov     rcx, rbx; Sid
0x140025bfd  call    cs:__imp_RtlLengthSid
0x140025c04  nop     dword ptr [rax+rax+00h]
0x140025c09  jmp     short loc_140025C0D
0x140025c0b  xor     eax, eax
0x140025c0d  mov     [rdi+40h], rbx
0x140025c11  mov     rbx, [rbp+Str]
0x140025c15  mov     [rdi+48h], eax
0x140025c18  lea     rax, [rbp+arg_28]
0x140025c1c  mov     dword ptr [rdi+4Ch], 0
0x140025c23  mov     [rdi+50h], rax
0x140025c27  mov     qword ptr [rdi+58h], 4
0x140025c2f  test    rbx, rbx
0x140025c32  jz      short loc_140025C45
0x140025c34  mov     rcx, rbx; Str
0x140025c37  call    wcslen_0
0x140025c3c  lea     ecx, ds:2[rax*2]
0x140025c43  jmp     short loc_140025C4A
0x140025c45  mov     ecx, 2
0x140025c4a  mov     [rdi+68h], ecx
0x140025c4d  lea     rax, SourceString
0x140025c54  mov     dword ptr [rdi+6Ch], 0
0x140025c5b  lea     rdx, Event15; EventDescriptor
0x140025c62  mov     qword ptr [rdi+78h], 4
0x140025c6a  test    rbx, rbx
0x140025c6d  mov     qword ptr [rdi+88h], 4
0x140025c78  mov     r9d, 0Bh; UserDataCount
0x140025c7e  cmovnz  rax, rbx
0x140025c82  mov     qword ptr [rdi+98h], 8
0x140025c8d  mov     [rdi+60h], rax
0x140025c91  xor     r8d, r8d; ActivityId
0x140025c94  lea     rax, [rbp+arg_38]
0x140025c98  mov     qword ptr [rdi+0A8h], 4
0x140025ca3  mov     [rdi+70h], rax
0x140025ca7  lea     rax, [rbp+arg_40]
0x140025cab  mov     [rdi+80h], rax
0x140025cb2  lea     rax, [rbp+arg_48]
0x140025cb6  mov     [rdi+90h], rax
0x140025cbd  lea     rax, [rbp+arg_50]
0x140025cc1  mov     [rdi+0A0h], rax
0x140025cc8  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140025ccf  mov     [rsp+38h+UserData], rdi; UserData
0x140025cd4  call    cs:__imp_EtwWrite
0x140025cdb  nop     dword ptr [rax+rax+00h]
0x140025ce0  mov     rcx, rdi; ListEntry
0x140025ce3  mov     ebx, eax
0x140025ce5  call    SecReleaseEtwDescriptorBuffer
0x140025cea  mov     eax, ebx
0x140025cec  add     rsp, 38h
0x140025cf0  pop     r14
0x140025cf2  pop     rdi
0x140025cf3  pop     rbx
0x140025cf4  pop     rbp
0x140025cf5  retn
```
