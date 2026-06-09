# EventWriteCreateFile

- ea: `0x140025cf8`
- end: `0x140025efd`
- name: `EventWriteCreateFile`
- size: `517`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char, wchar_t *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140026ec4`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140025cf8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140025ed5`
- `ntoskrnl!EtwWrite` at `0x140025ed5`
- `ntoskrnl!RtlLengthSid` at `0x140025d85`
- `ntoskrnl!RtlLengthSid` at `0x140025d85`

## pseudocode

```c
__int64 __fastcall EventWriteCreateFile(
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
        char a11,
        wchar_t *a12,
        int a13,
        __int64 a14)
{
  PSID v14; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v18; // eax
  int v19; // esi
  const wchar_t *v20; // rbx
  int v21; // ecx
  const WCHAR *v22; // r14
  const WCHAR *v23; // rax
  const wchar_t *v24; // rbx
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rax
  int v28; // ecx
  unsigned int v29; // ebx
  __int64 v30; // [rsp+70h] [rbp+40h] BYREF
  int v31; // [rsp+78h] [rbp+48h] BYREF
  __int64 v32; // [rsp+80h] [rbp+50h] BYREF
  int v33; // [rsp+88h] [rbp+58h] BYREF

  v33 = a4;
  v32 = a3;
  v31 = a2;
  v30 = a1;
  v14 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(14);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v30;
  EtwDescriptorBuffer[2] = &v31;
  EtwDescriptorBuffer[4] = &v32;
  EtwDescriptorBuffer[6] = &v33;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v14 )
    v18 = RtlLengthSid(v14);
  else
    v18 = 0;
  UserData[8] = v14;
  v19 = 2;
  v20 = Str;
  *((_DWORD *)UserData + 18) = v18;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a6;
  UserData[11] = 4;
  if ( v20 )
    v21 = 2 * wcslen_0(v20) + 2;
  else
    v21 = 2;
  *((_DWORD *)UserData + 26) = v21;
  v22 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v23 = &SourceString;
  UserData[15] = 4;
  if ( v20 )
    v23 = v20;
  UserData[17] = 4;
  v24 = a12;
  UserData[12] = v23;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  UserData[19] = 8;
  UserData[21] = 1;
  v25 = v24 == 0;
  if ( v24 )
  {
    v26 = wcslen_0(v24);
    v25 = v24 == 0;
    v19 = 2 * v26 + 2;
  }
  if ( !v25 )
    v22 = v24;
  *((_DWORD *)UserData + 46) = v19;
  UserData[22] = v22;
  UserData[24] = &a13;
  v27 = a14;
  *((_DWORD *)UserData + 47) = 0;
  UserData[25] = 4;
  v28 = a13;
  UserData[26] = v27;
  *((_DWORD *)UserData + 54) = v28;
  *((_DWORD *)UserData + 55) = 0;
  v29 = EtwWrite(Microsoft_Windows_SECHandle, &Event4, 0, 0xEu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v29;
}

```

## disassembly

```asm
0x140025cf8  mov     rax, rsp
0x140025cfb  mov     [rax+20h], r9d
0x140025cff  mov     [rax+18h], r8
0x140025d03  mov     [rax+10h], edx
0x140025d06  mov     [rax+8], rcx
0x140025d0a  push    rbp
0x140025d0b  push    rbx
0x140025d0c  push    rsi
0x140025d0d  push    rdi
0x140025d0e  push    r12
0x140025d10  push    r14
0x140025d12  push    r15
0x140025d14  mov     rbp, rsp
0x140025d17  sub     rsp, 30h
0x140025d1b  mov     rbx, [rbp+Sid]
0x140025d1f  mov     ecx, 0Eh
0x140025d24  call    SecGetEtwDescriptorBuffer
0x140025d29  xor     r15d, r15d
0x140025d2c  mov     rdi, rax
0x140025d2f  test    rax, rax
0x140025d32  jnz     short loc_140025D3E
0x140025d34  mov     eax, 0C000009Ah
0x140025d39  jmp     loc_140025EED
0x140025d3e  mov     qword ptr [rdi+8], 8
0x140025d46  lea     rax, [rbp+arg_0]
0x140025d4a  mov     [rdi], rax
0x140025d4d  lea     rax, [rbp+arg_8]
0x140025d51  mov     [rdi+10h], rax
0x140025d55  lea     rax, [rbp+arg_10]
0x140025d59  mov     [rdi+20h], rax
0x140025d5d  lea     rax, [rbp+arg_18]
0x140025d61  mov     [rdi+30h], rax
0x140025d65  mov     qword ptr [rdi+18h], 4
0x140025d6d  mov     qword ptr [rdi+28h], 8
0x140025d75  mov     qword ptr [rdi+38h], 4
0x140025d7d  test    rbx, rbx
0x140025d80  jz      short loc_140025D93
0x140025d82  mov     rcx, rbx; Sid
0x140025d85  call    cs:__imp_RtlLengthSid
0x140025d8c  nop     dword ptr [rax+rax+00h]
0x140025d91  jmp     short loc_140025D96
0x140025d93  mov     eax, r15d
0x140025d96  mov     [rdi+40h], rbx
0x140025d9a  mov     esi, 2
0x140025d9f  mov     rbx, [rbp+Str]
0x140025da3  mov     [rdi+48h], eax
0x140025da6  lea     rax, [rbp+arg_28]
0x140025daa  mov     [rdi+4Ch], r15d
0x140025dae  mov     [rdi+50h], rax
0x140025db2  mov     qword ptr [rdi+58h], 4
0x140025dba  test    rbx, rbx
0x140025dbd  jz      short loc_140025DD0
0x140025dbf  mov     rcx, rbx; Str
0x140025dc2  call    wcslen_0
0x140025dc7  lea     ecx, ds:2[rax*2]
0x140025dce  jmp     short loc_140025DD2
0x140025dd0  mov     ecx, esi
0x140025dd2  test    rbx, rbx
0x140025dd5  mov     [rdi+68h], ecx
0x140025dd8  lea     r14, SourceString
0x140025ddf  mov     [rdi+6Ch], r15d
0x140025de3  mov     rax, r14
0x140025de6  mov     qword ptr [rdi+78h], 4
0x140025dee  cmovnz  rax, rbx
0x140025df2  mov     qword ptr [rdi+88h], 4
0x140025dfd  mov     rbx, [rbp+arg_58]
0x140025e04  mov     [rdi+60h], rax
0x140025e08  lea     rax, [rbp+arg_38]
0x140025e0c  mov     [rdi+70h], rax
0x140025e10  lea     rax, [rbp+arg_40]
0x140025e17  mov     [rdi+80h], rax
0x140025e1e  lea     rax, [rbp+arg_48]
0x140025e25  mov     [rdi+90h], rax
0x140025e2c  lea     rax, [rbp+arg_50]
0x140025e33  mov     [rdi+0A0h], rax
0x140025e3a  mov     qword ptr [rdi+98h], 8
0x140025e45  mov     qword ptr [rdi+0A8h], 1
0x140025e50  test    rbx, rbx
0x140025e53  jz      short loc_140025E67
0x140025e55  mov     rcx, rbx; Str
0x140025e58  call    wcslen_0
0x140025e5d  test    rbx, rbx
0x140025e60  lea     esi, ds:2[rax*2]
0x140025e67  cmovnz  r14, rbx
0x140025e6b  mov     [rdi+0B8h], esi
0x140025e71  mov     [rdi+0B0h], r14
0x140025e78  lea     rax, [rbp+arg_60]
0x140025e7f  mov     [rdi+0C0h], rax
0x140025e86  lea     rdx, Event4; EventDescriptor
0x140025e8d  mov     rax, [rbp+arg_68]
0x140025e94  mov     r9d, 0Eh; UserDataCount
0x140025e9a  mov     [rdi+0BCh], r15d
0x140025ea1  xor     r8d, r8d; ActivityId
0x140025ea4  mov     qword ptr [rdi+0C8h], 4
0x140025eaf  mov     ecx, [rbp+arg_60]
0x140025eb5  mov     [rdi+0D0h], rax
0x140025ebc  mov     [rdi+0D8h], ecx
0x140025ec2  mov     [rdi+0DCh], r15d
0x140025ec9  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140025ed0  mov     [rsp+30h+UserData], rdi; UserData
0x140025ed5  call    cs:__imp_EtwWrite
0x140025edc  nop     dword ptr [rax+rax+00h]
0x140025ee1  mov     rcx, rdi; ListEntry
0x140025ee4  mov     ebx, eax
0x140025ee6  call    SecReleaseEtwDescriptorBuffer
0x140025eeb  mov     eax, ebx
0x140025eed  add     rsp, 30h
0x140025ef1  pop     r15
0x140025ef3  pop     r14
0x140025ef5  pop     r12
0x140025ef7  pop     rdi
0x140025ef8  pop     rsi
0x140025ef9  pop     rbx
0x140025efa  pop     rbp
0x140025efb  retn
```
