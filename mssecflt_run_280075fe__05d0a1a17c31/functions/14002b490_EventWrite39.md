# EventWrite39

- ea: `0x14002b490`
- end: `0x14002b5eb`
- name: `EventWrite39`
- size: `347`
- prototype: `__int64 __fastcall(int, int, int, int, char, PSID Sid, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002c080`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14002b490`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002b5c6`
- `ntoskrnl!EtwWrite` at `0x14002b5c6`
- `ntoskrnl!RtlLengthSid` at `0x14002b527`
- `ntoskrnl!RtlLengthSid` at `0x14002b527`

## pseudocode

```c
__int64 __fastcall EventWrite39(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        char a5,
        PSID Sid,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  PSID v11; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF
  __int64 v19; // [rsp+70h] [rbp+40h] BYREF
  int v20; // [rsp+78h] [rbp+48h] BYREF

  v20 = a4;
  v19 = a3;
  v18 = a2;
  v17 = a1;
  v11 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(11);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v17;
  EtwDescriptorBuffer[2] = &v18;
  EtwDescriptorBuffer[4] = &v19;
  EtwDescriptorBuffer[6] = &v20;
  EtwDescriptorBuffer[8] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  EtwDescriptorBuffer[9] = 4;
  if ( v11 )
    v15 = RtlLengthSid(v11);
  else
    v15 = 0;
  *((_DWORD *)UserData + 22) = v15;
  UserData[10] = v11;
  UserData[12] = &a7;
  *((_DWORD *)UserData + 23) = 0;
  UserData[14] = &a8;
  UserData[13] = 4;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  UserData[15] = 8;
  UserData[17] = 4;
  UserData[19] = 8;
  UserData[21] = 8;
  v16 = EtwWrite(Microsoft_Windows_SECHandle, &Event39, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v16;
}

```

## disassembly

```asm
0x14002b490  mov     rax, rsp
0x14002b493  mov     [rax+20h], r9d
0x14002b497  mov     [rax+18h], r8
0x14002b49b  mov     [rax+10h], edx
0x14002b49e  mov     [rax+8], rcx
0x14002b4a2  push    rbp
0x14002b4a3  push    rbx
0x14002b4a4  push    rdi
0x14002b4a5  push    r14
0x14002b4a7  push    r15
0x14002b4a9  mov     rbp, rsp
0x14002b4ac  sub     rsp, 30h
0x14002b4b0  mov     rbx, [rbp+Sid]
0x14002b4b4  mov     ecx, 0Bh
0x14002b4b9  call    SecGetEtwDescriptorBuffer
0x14002b4be  mov     rdi, rax
0x14002b4c1  test    rax, rax
0x14002b4c4  jnz     short loc_14002B4D0
0x14002b4c6  mov     eax, 0C000009Ah
0x14002b4cb  jmp     loc_14002B5DE
0x14002b4d0  mov     qword ptr [rdi+8], 8
0x14002b4d8  lea     rax, [rbp+arg_0]
0x14002b4dc  mov     [rdi], rax
0x14002b4df  lea     rax, [rbp+arg_8]
0x14002b4e3  mov     [rdi+10h], rax
0x14002b4e7  lea     rax, [rbp+arg_10]
0x14002b4eb  mov     [rdi+20h], rax
0x14002b4ef  lea     rax, [rbp+arg_18]
0x14002b4f3  mov     [rdi+30h], rax
0x14002b4f7  lea     rax, [rbp+arg_20]
0x14002b4fb  mov     [rdi+40h], rax
0x14002b4ff  mov     qword ptr [rdi+18h], 4
0x14002b507  mov     qword ptr [rdi+28h], 8
0x14002b50f  mov     qword ptr [rdi+38h], 4
0x14002b517  mov     qword ptr [rdi+48h], 4
0x14002b51f  test    rbx, rbx
0x14002b522  jz      short loc_14002B535
0x14002b524  mov     rcx, rbx; Sid
0x14002b527  call    cs:__imp_RtlLengthSid
0x14002b52e  nop     dword ptr [rax+rax+00h]
0x14002b533  jmp     short loc_14002B537
0x14002b535  xor     eax, eax
0x14002b537  mov     [rdi+58h], eax
0x14002b53a  lea     rdx, Event39; EventDescriptor
0x14002b541  lea     rax, [rbp+arg_30]
0x14002b545  mov     [rdi+50h], rbx
0x14002b549  mov     [rdi+60h], rax
0x14002b54d  mov     r9d, 0Bh; UserDataCount
0x14002b553  lea     rax, [rbp+arg_38]
0x14002b557  mov     dword ptr [rdi+5Ch], 0
0x14002b55e  mov     [rdi+70h], rax
0x14002b562  xor     r8d, r8d; ActivityId
0x14002b565  lea     rax, [rbp+arg_40]
0x14002b569  mov     qword ptr [rdi+68h], 4
0x14002b571  mov     [rdi+80h], rax
0x14002b578  lea     rax, [rbp+arg_48]
0x14002b57c  mov     [rdi+90h], rax
0x14002b583  lea     rax, [rbp+arg_50]
0x14002b58a  mov     [rdi+0A0h], rax
0x14002b591  mov     qword ptr [rdi+78h], 8
0x14002b599  mov     qword ptr [rdi+88h], 4
0x14002b5a4  mov     qword ptr [rdi+98h], 8
0x14002b5af  mov     qword ptr [rdi+0A8h], 8
0x14002b5ba  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002b5c1  mov     [rsp+30h+UserData], rdi; UserData
0x14002b5c6  call    cs:__imp_EtwWrite
0x14002b5cd  nop     dword ptr [rax+rax+00h]
0x14002b5d2  mov     rcx, rdi; ListEntry
0x14002b5d5  mov     ebx, eax
0x14002b5d7  call    SecReleaseEtwDescriptorBuffer
0x14002b5dc  mov     eax, ebx
0x14002b5de  add     rsp, 30h
0x14002b5e2  pop     r15
0x14002b5e4  pop     r14
0x14002b5e6  pop     rdi
0x14002b5e7  pop     rbx
0x14002b5e8  pop     rbp
0x14002b5e9  retn
```
