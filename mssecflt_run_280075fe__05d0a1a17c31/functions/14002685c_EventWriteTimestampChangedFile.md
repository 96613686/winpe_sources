# EventWriteTimestampChangedFile

- ea: `0x14002685c`
- end: `0x140026a7f`
- name: `EventWriteTimestampChangedFile`
- size: `547`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140027c2c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x14002685c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140026a5b`
- `ntoskrnl!EtwWriteEx` at `0x140026a5b`
- `ntoskrnl!RtlLengthSid` at `0x1400268e4`
- `ntoskrnl!RtlLengthSid` at `0x1400268e4`

## pseudocode

```c
__int64 __fastcall EventWriteTimestampChangedFile(
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
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        char a17)
{
  PSID v17; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v21; // eax
  const wchar_t *v22; // rbx
  int v23; // ecx
  const WCHAR *v24; // rax
  unsigned int v25; // ebx
  __int64 v26; // [rsp+70h] [rbp+30h] BYREF
  int v27; // [rsp+78h] [rbp+38h] BYREF
  __int64 v28; // [rsp+80h] [rbp+40h] BYREF
  int v29; // [rsp+88h] [rbp+48h] BYREF

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v26 = a1;
  v17 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(17);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v26;
  EtwDescriptorBuffer[2] = &v27;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[4] = &v28;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[6] = &v29;
  EtwDescriptorBuffer[7] = 4;
  if ( v17 )
    v21 = RtlLengthSid(v17);
  else
    v21 = 0;
  UserData[8] = v17;
  v22 = Str;
  *((_DWORD *)UserData + 18) = v21;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a6;
  UserData[11] = 4;
  if ( v22 )
    v23 = 2 * wcslen_0(v22) + 2;
  else
    v23 = 2;
  *((_DWORD *)UserData + 26) = v23;
  v24 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  if ( v22 )
    v24 = v22;
  UserData[12] = v24;
  UserData[15] = 8;
  UserData[14] = &a8;
  UserData[17] = 8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[19] = 8;
  UserData[20] = &a11;
  UserData[21] = 8;
  UserData[22] = &a12;
  UserData[23] = 8;
  UserData[24] = &a13;
  UserData[25] = 8;
  UserData[26] = &a14;
  UserData[27] = 8;
  UserData[28] = &a15;
  UserData[29] = 8;
  UserData[30] = &a16;
  UserData[31] = 4;
  UserData[32] = &a17;
  UserData[33] = 8;
  v25 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event35, 0, 0, 0, 0, 0x11u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v25;
}

```

## disassembly

```asm
0x14002685c  mov     rax, rsp
0x14002685f  mov     [rax+20h], r9d
0x140026863  mov     [rax+18h], r8
0x140026867  mov     [rax+10h], edx
0x14002686a  mov     [rax+8], rcx
0x14002686e  push    rbp
0x14002686f  push    rbx
0x140026870  push    rsi
0x140026871  push    rdi
0x140026872  push    r15
0x140026874  mov     rbp, rsp
0x140026877  sub     rsp, 40h
0x14002687b  mov     rbx, [rbp+Sid]
0x14002687f  mov     ecx, 11h
0x140026884  call    SecGetEtwDescriptorBuffer
0x140026889  xor     esi, esi
0x14002688b  mov     rdi, rax
0x14002688e  test    rax, rax
0x140026891  jnz     short loc_14002689D
0x140026893  mov     eax, 0C000009Ah
0x140026898  jmp     loc_140026A73
0x14002689d  mov     qword ptr [rdi+8], 8
0x1400268a5  lea     rax, [rbp+arg_0]
0x1400268a9  mov     [rdi], rax
0x1400268ac  lea     rax, [rbp+arg_8]
0x1400268b0  mov     [rdi+10h], rax
0x1400268b4  lea     rax, [rbp+arg_10]
0x1400268b8  mov     qword ptr [rdi+18h], 4
0x1400268c0  mov     [rdi+20h], rax
0x1400268c4  lea     rax, [rbp+arg_18]
0x1400268c8  mov     qword ptr [rdi+28h], 8
0x1400268d0  mov     [rdi+30h], rax
0x1400268d4  mov     qword ptr [rdi+38h], 4
0x1400268dc  test    rbx, rbx
0x1400268df  jz      short loc_1400268F2
0x1400268e1  mov     rcx, rbx; Sid
0x1400268e4  call    cs:__imp_RtlLengthSid
0x1400268eb  nop     dword ptr [rax+rax+00h]
0x1400268f0  jmp     short loc_1400268F4
0x1400268f2  mov     eax, esi
0x1400268f4  mov     [rdi+40h], rbx
0x1400268f8  mov     rbx, [rbp+Str]
0x1400268fc  mov     [rdi+48h], eax
0x1400268ff  lea     rax, [rbp+arg_28]
0x140026903  mov     [rdi+4Ch], esi
0x140026906  mov     [rdi+50h], rax
0x14002690a  mov     qword ptr [rdi+58h], 4
0x140026912  test    rbx, rbx
0x140026915  jz      short loc_140026928
0x140026917  mov     rcx, rbx; Str
0x14002691a  call    wcslen_0
0x14002691f  lea     ecx, ds:2[rax*2]
0x140026926  jmp     short loc_14002692D
0x140026928  mov     ecx, 2
0x14002692d  mov     [rdi+68h], ecx
0x140026930  lea     rax, SourceString
0x140026937  mov     [rdi+6Ch], esi
0x14002693a  lea     rdx, Event35; EventDescriptor
0x140026941  mov     [rsp+40h+UserData], rdi; UserData
0x140026946  test    rbx, rbx
0x140026949  mov     [rsp+40h+UserDataCount], 11h; UserDataCount
0x140026951  cmovnz  rax, rbx
0x140026955  mov     [rsp+40h+RelatedActivityId], rsi; RelatedActivityId
0x14002695a  mov     [rdi+60h], rax
0x14002695e  xor     r9d, r9d; Flags
0x140026961  mov     qword ptr [rdi+78h], 8
0x140026969  lea     rax, [rbp+arg_38]
0x14002696d  mov     [rdi+70h], rax
0x140026971  xor     r8d, r8d; Filter
0x140026974  mov     qword ptr [rdi+88h], 8
0x14002697f  lea     rax, [rbp+arg_40]
0x140026983  mov     [rdi+80h], rax
0x14002698a  lea     rax, [rbp+arg_48]
0x14002698e  mov     [rdi+90h], rax
0x140026995  lea     rax, [rbp+arg_50]
0x14002699c  mov     qword ptr [rdi+98h], 8
0x1400269a7  mov     [rdi+0A0h], rax
0x1400269ae  lea     rax, [rbp+arg_58]
0x1400269b5  mov     qword ptr [rdi+0A8h], 8
0x1400269c0  mov     [rdi+0B0h], rax
0x1400269c7  lea     rax, [rbp+arg_60]
0x1400269ce  mov     qword ptr [rdi+0B8h], 8
0x1400269d9  mov     [rdi+0C0h], rax
0x1400269e0  lea     rax, [rbp+arg_68]
0x1400269e7  mov     qword ptr [rdi+0C8h], 8
0x1400269f2  mov     [rdi+0D0h], rax
0x1400269f9  lea     rax, [rbp+arg_70]
0x140026a00  mov     qword ptr [rdi+0D8h], 8
0x140026a0b  mov     [rdi+0E0h], rax
0x140026a12  lea     rax, [rbp+arg_78]
0x140026a19  mov     qword ptr [rdi+0E8h], 8
0x140026a24  mov     [rdi+0F0h], rax
0x140026a2b  lea     rax, [rbp+arg_80]
0x140026a32  mov     qword ptr [rdi+0F8h], 4
0x140026a3d  mov     [rdi+100h], rax
0x140026a44  mov     qword ptr [rdi+108h], 8
0x140026a4f  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140026a56  mov     [rsp+40h+ActivityId], rsi; ActivityId
0x140026a5b  call    cs:__imp_EtwWriteEx
0x140026a62  nop     dword ptr [rax+rax+00h]
0x140026a67  mov     rcx, rdi; ListEntry
0x140026a6a  mov     ebx, eax
0x140026a6c  call    SecReleaseEtwDescriptorBuffer
0x140026a71  mov     eax, ebx
0x140026a73  add     rsp, 40h
0x140026a77  pop     r15
0x140026a79  pop     rdi
0x140026a7a  pop     rsi
0x140026a7b  pop     rbx
0x140026a7c  pop     rbp
0x140026a7d  retn
```
