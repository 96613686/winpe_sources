# EventWriteRemoteThread

- ea: `0x14002e97c`
- end: `0x14002ebf6`
- name: `EventWriteRemoteThread`
- size: `634`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, char, char, wchar_t *Str, char, char, __int64, char, char, char, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ec70`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x14002e97c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002ebcf`
- `ntoskrnl!EtwWrite` at `0x14002ebcf`
- `ntoskrnl!RtlLengthSid` at `0x14002ea08`
- `ntoskrnl!RtlLengthSid` at `0x14002ea08`

## pseudocode

```c
__int64 __fastcall EventWriteRemoteThread(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        char a7,
        char a8,
        wchar_t *Str,
        char a10,
        char a11,
        __int64 a12,
        char a13,
        char a14,
        char a15,
        unsigned __int16 *a16)
{
  PSID v16; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v20; // eax
  int v21; // ebx
  int v22; // ecx
  bool v23; // zf
  const WCHAR *v24; // rdx
  const WCHAR *v25; // rax
  __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // [rsp+70h] [rbp+38h] BYREF
  int v30; // [rsp+78h] [rbp+40h] BYREF
  __int64 v31; // [rsp+80h] [rbp+48h] BYREF
  int v32; // [rsp+88h] [rbp+50h] BYREF

  v32 = a4;
  v31 = a3;
  v30 = a2;
  v29 = a1;
  v16 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(20);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v29;
  EtwDescriptorBuffer[2] = &v30;
  EtwDescriptorBuffer[4] = &v31;
  EtwDescriptorBuffer[6] = &v32;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v16 )
    v20 = RtlLengthSid(v16);
  else
    v20 = 0;
  *((_DWORD *)UserData + 18) = v20;
  UserData[10] = &a6;
  UserData[12] = &a7;
  UserData[8] = v16;
  v21 = 2;
  UserData[14] = &a8;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  UserData[13] = 4;
  UserData[15] = 8;
  if ( Str )
    v22 = 2 * wcslen_0(Str) + 2;
  else
    v22 = 2;
  v23 = Str == 0;
  v24 = &SourceString;
  v25 = &SourceString;
  *((_DWORD *)UserData + 34) = v22;
  if ( !v23 )
    v25 = Str;
  v26 = a12;
  UserData[16] = v25;
  UserData[18] = &a10;
  UserData[20] = &a11;
  UserData[22] = &a13;
  UserData[24] = v26 + 8;
  UserData[26] = v26 + 16;
  UserData[28] = v26 + 40;
  UserData[30] = v26 + 24;
  UserData[32] = v26 + 36;
  UserData[34] = &a14;
  UserData[36] = &a15;
  v27 = a16;
  *((_DWORD *)UserData + 35) = 0;
  UserData[19] = 4;
  UserData[21] = 8;
  UserData[23] = 4;
  UserData[25] = 8;
  UserData[27] = 4;
  UserData[29] = 4;
  UserData[31] = 8;
  UserData[33] = 4;
  UserData[35] = 8;
  UserData[37] = 8;
  if ( v27 )
  {
    v21 = *v27;
    v24 = (const WCHAR *)*((_QWORD *)v27 + 1);
  }
  UserData[38] = v24;
  *((_DWORD *)UserData + 78) = v21;
  *((_DWORD *)UserData + 79) = 0;
  v28 = EtwWrite(Microsoft_Windows_SECHandle, &Event18, 0, 0x14u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v28;
}

```

## disassembly

```asm
0x14002e97c  mov     rax, rsp
0x14002e97f  mov     [rax+20h], r9d
0x14002e983  mov     [rax+18h], r8
0x14002e987  mov     [rax+10h], edx
0x14002e98a  mov     [rax+8], rcx
0x14002e98e  push    rbp
0x14002e98f  push    rbx
0x14002e990  push    rdi
0x14002e991  push    r12
0x14002e993  push    r14
0x14002e995  push    r15
0x14002e997  mov     rbp, rsp
0x14002e99a  sub     rsp, 38h
0x14002e99e  mov     rbx, [rbp+Sid]
0x14002e9a2  mov     ecx, 14h
0x14002e9a7  call    SecGetEtwDescriptorBuffer
0x14002e9ac  xor     r14d, r14d
0x14002e9af  mov     rdi, rax
0x14002e9b2  test    rax, rax
0x14002e9b5  jnz     short loc_14002E9C1
0x14002e9b7  mov     eax, 0C000009Ah
0x14002e9bc  jmp     loc_14002EBE7
0x14002e9c1  mov     qword ptr [rdi+8], 8
0x14002e9c9  lea     rax, [rbp+arg_0]
0x14002e9cd  mov     [rdi], rax
0x14002e9d0  lea     rax, [rbp+arg_8]
0x14002e9d4  mov     [rdi+10h], rax
0x14002e9d8  lea     rax, [rbp+arg_10]
0x14002e9dc  mov     [rdi+20h], rax
0x14002e9e0  lea     rax, [rbp+arg_18]
0x14002e9e4  mov     [rdi+30h], rax
0x14002e9e8  mov     qword ptr [rdi+18h], 4
0x14002e9f0  mov     qword ptr [rdi+28h], 8
0x14002e9f8  mov     qword ptr [rdi+38h], 4
0x14002ea00  test    rbx, rbx
0x14002ea03  jz      short loc_14002EA16
0x14002ea05  mov     rcx, rbx; Sid
0x14002ea08  call    cs:__imp_RtlLengthSid
0x14002ea0f  nop     dword ptr [rax+rax+00h]
0x14002ea14  jmp     short loc_14002EA19
0x14002ea16  mov     eax, r14d
0x14002ea19  mov     [rdi+48h], eax
0x14002ea1c  lea     rax, [rbp+arg_28]
0x14002ea20  mov     [rdi+50h], rax
0x14002ea24  lea     rax, [rbp+arg_30]
0x14002ea28  mov     [rdi+60h], rax
0x14002ea2c  lea     rax, [rbp+arg_38]
0x14002ea30  mov     [rdi+40h], rbx
0x14002ea34  mov     ebx, 2
0x14002ea39  mov     [rdi+70h], rax
0x14002ea3d  mov     [rdi+4Ch], r14d
0x14002ea41  mov     qword ptr [rdi+58h], 4
0x14002ea49  mov     qword ptr [rdi+68h], 4
0x14002ea51  mov     qword ptr [rdi+78h], 8
0x14002ea59  cmp     [rbp+Str], r14
0x14002ea5d  jz      short loc_14002EA71
0x14002ea5f  mov     rcx, [rbp+Str]; Str
0x14002ea63  call    wcslen_0
0x14002ea68  lea     ecx, ds:2[rax*2]
0x14002ea6f  jmp     short loc_14002EA73
0x14002ea71  mov     ecx, ebx
0x14002ea73  cmp     [rbp+Str], r14
0x14002ea77  lea     rdx, SourceString
0x14002ea7e  mov     rax, rdx
0x14002ea81  mov     [rdi+88h], ecx
0x14002ea87  cmovnz  rax, [rbp+Str]
0x14002ea8c  mov     rcx, [rbp+arg_58]
0x14002ea93  mov     [rdi+80h], rax
0x14002ea9a  lea     rax, [rbp+arg_48]
0x14002eaa1  mov     [rdi+90h], rax
0x14002eaa8  lea     rax, [rbp+arg_50]
0x14002eaaf  mov     [rdi+0A0h], rax
0x14002eab6  lea     rax, [rbp+arg_60]
0x14002eabd  mov     [rdi+0B0h], rax
0x14002eac4  lea     rax, [rcx+8]
0x14002eac8  mov     [rdi+0C0h], rax
0x14002eacf  lea     rax, [rcx+10h]
0x14002ead3  mov     [rdi+0D0h], rax
0x14002eada  lea     rax, [rcx+28h]
0x14002eade  mov     [rdi+0E0h], rax
0x14002eae5  lea     rax, [rcx+18h]
0x14002eae9  mov     [rdi+0F0h], rax
0x14002eaf0  lea     rax, [rcx+24h]
0x14002eaf4  mov     [rdi+100h], rax
0x14002eafb  lea     rax, [rbp+arg_68]
0x14002eb02  mov     [rdi+110h], rax
0x14002eb09  lea     rax, [rbp+arg_70]
0x14002eb10  mov     [rdi+120h], rax
0x14002eb17  mov     rax, [rbp+arg_78]
0x14002eb1e  mov     [rdi+8Ch], r14d
0x14002eb25  mov     qword ptr [rdi+98h], 4
0x14002eb30  mov     qword ptr [rdi+0A8h], 8
0x14002eb3b  mov     qword ptr [rdi+0B8h], 4
0x14002eb46  mov     qword ptr [rdi+0C8h], 8
0x14002eb51  mov     qword ptr [rdi+0D8h], 4
0x14002eb5c  mov     qword ptr [rdi+0E8h], 4
0x14002eb67  mov     qword ptr [rdi+0F8h], 8
0x14002eb72  mov     qword ptr [rdi+108h], 4
0x14002eb7d  mov     qword ptr [rdi+118h], 8
0x14002eb88  mov     qword ptr [rdi+128h], 8
0x14002eb93  test    rax, rax
0x14002eb96  jz      short loc_14002EB9F
0x14002eb98  movzx   ebx, word ptr [rax]
0x14002eb9b  mov     rdx, [rax+8]
0x14002eb9f  mov     [rdi+130h], rdx
0x14002eba6  mov     r9d, 14h; UserDataCount
0x14002ebac  mov     [rdi+138h], ebx
0x14002ebb2  lea     rdx, Event18; EventDescriptor
0x14002ebb9  mov     [rdi+13Ch], r14d
0x14002ebc0  xor     r8d, r8d; ActivityId
0x14002ebc3  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002ebca  mov     [rsp+38h+UserData], rdi; UserData
0x14002ebcf  call    cs:__imp_EtwWrite
0x14002ebd6  nop     dword ptr [rax+rax+00h]
0x14002ebdb  mov     rcx, rdi; ListEntry
0x14002ebde  mov     ebx, eax
0x14002ebe0  call    SecReleaseEtwDescriptorBuffer
0x14002ebe5  mov     eax, ebx
0x14002ebe7  add     rsp, 38h
0x14002ebeb  pop     r15
0x14002ebed  pop     r14
0x14002ebef  pop     r12
0x14002ebf1  pop     rdi
0x14002ebf2  pop     rbx
0x14002ebf3  pop     rbp
0x14002ebf4  retn
```
