# EventWriteModifyDeleteReadSensitiveFile

- ea: `0x1400260b8`
- end: `0x1400262c7`
- name: `EventWriteModifyDeleteReadSensitiveFile`
- size: `527`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, PCEVENT_DESCRIPTOR EventDescriptor, char, char, wchar_t *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140027278`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x1400260b8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002629d`
- `ntoskrnl!EtwWrite` at `0x14002629d`
- `ntoskrnl!RtlLengthSid` at `0x14002614e`
- `ntoskrnl!RtlLengthSid` at `0x14002614e`

## pseudocode

```c
__int64 __fastcall EventWriteModifyDeleteReadSensitiveFile(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        wchar_t *Str,
        char a8,
        char a9,
        PCEVENT_DESCRIPTOR EventDescriptor,
        char a11,
        char a12,
        wchar_t *a13,
        int a14,
        __int64 a15)
{
  PSID v15; // rbx
  const EVENT_DESCRIPTOR *v16; // r15
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v20; // eax
  int v21; // esi
  const wchar_t *v22; // rbx
  int v23; // ecx
  const WCHAR *v24; // r14
  const WCHAR *v25; // rax
  const wchar_t *v26; // rbx
  bool v27; // zf
  int v28; // eax
  __int64 v29; // rax
  int v30; // ecx
  unsigned int v31; // ebx
  __int64 v32; // [rsp+80h] [rbp+48h] BYREF
  int v33; // [rsp+88h] [rbp+50h] BYREF
  __int64 v34; // [rsp+90h] [rbp+58h] BYREF
  int v35; // [rsp+98h] [rbp+60h] BYREF

  v35 = a4;
  v34 = a3;
  v33 = a2;
  v32 = a1;
  v15 = Sid;
  v16 = EventDescriptor;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(14);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v32;
  EtwDescriptorBuffer[2] = &v33;
  EtwDescriptorBuffer[4] = &v34;
  EtwDescriptorBuffer[6] = &v35;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v15 )
    v20 = RtlLengthSid(v15);
  else
    v20 = 0;
  UserData[8] = v15;
  v21 = 2;
  v22 = Str;
  *((_DWORD *)UserData + 18) = v20;
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
  v25 = &SourceString;
  UserData[15] = 4;
  if ( v22 )
    v25 = v22;
  UserData[17] = 8;
  v26 = a13;
  UserData[12] = v25;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a11;
  UserData[20] = &a12;
  UserData[19] = 4;
  UserData[21] = 1;
  v27 = v26 == 0;
  if ( v26 )
  {
    v28 = wcslen_0(v26);
    v27 = v26 == 0;
    v21 = 2 * v28 + 2;
  }
  if ( !v27 )
    v24 = v26;
  *((_DWORD *)UserData + 46) = v21;
  UserData[22] = v24;
  UserData[24] = &a14;
  v29 = a15;
  *((_DWORD *)UserData + 47) = 0;
  UserData[25] = 4;
  v30 = a14;
  UserData[26] = v29;
  *((_DWORD *)UserData + 54) = v30;
  *((_DWORD *)UserData + 55) = 0;
  v31 = EtwWrite(Microsoft_Windows_SECHandle, v16, 0, 0xEu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v31;
}

```

## disassembly

```asm
0x1400260b8  mov     rax, rsp
0x1400260bb  mov     [rax+20h], r9d
0x1400260bf  mov     [rax+18h], r8
0x1400260c3  mov     [rax+10h], edx
0x1400260c6  mov     [rax+8], rcx
0x1400260ca  push    rbp
0x1400260cb  push    rbx
0x1400260cc  push    rsi
0x1400260cd  push    rdi
0x1400260ce  push    r12
0x1400260d0  push    r13
0x1400260d2  push    r14
0x1400260d4  push    r15
0x1400260d6  mov     rbp, rsp
0x1400260d9  sub     rsp, 38h
0x1400260dd  mov     rbx, [rbp+Sid]
0x1400260e1  mov     ecx, 0Eh
0x1400260e6  mov     r15, [rbp+EventDescriptor]
0x1400260ed  call    SecGetEtwDescriptorBuffer
0x1400260f2  xor     r12d, r12d
0x1400260f5  mov     rdi, rax
0x1400260f8  test    rax, rax
0x1400260fb  jnz     short loc_140026107
0x1400260fd  mov     eax, 0C000009Ah
0x140026102  jmp     loc_1400262B5
0x140026107  mov     qword ptr [rdi+8], 8
0x14002610f  lea     rax, [rbp+arg_0]
0x140026113  mov     [rdi], rax
0x140026116  lea     rax, [rbp+arg_8]
0x14002611a  mov     [rdi+10h], rax
0x14002611e  lea     rax, [rbp+arg_10]
0x140026122  mov     [rdi+20h], rax
0x140026126  lea     rax, [rbp+arg_18]
0x14002612a  mov     [rdi+30h], rax
0x14002612e  mov     qword ptr [rdi+18h], 4
0x140026136  mov     qword ptr [rdi+28h], 8
0x14002613e  mov     qword ptr [rdi+38h], 4
0x140026146  test    rbx, rbx
0x140026149  jz      short loc_14002615C
0x14002614b  mov     rcx, rbx; Sid
0x14002614e  call    cs:__imp_RtlLengthSid
0x140026155  nop     dword ptr [rax+rax+00h]
0x14002615a  jmp     short loc_14002615F
0x14002615c  mov     eax, r12d
0x14002615f  mov     [rdi+40h], rbx
0x140026163  mov     esi, 2
0x140026168  mov     rbx, [rbp+Str]
0x14002616c  mov     [rdi+48h], eax
0x14002616f  lea     rax, [rbp+arg_28]
0x140026173  mov     [rdi+4Ch], r12d
0x140026177  mov     [rdi+50h], rax
0x14002617b  mov     qword ptr [rdi+58h], 4
0x140026183  test    rbx, rbx
0x140026186  jz      short loc_140026199
0x140026188  mov     rcx, rbx; Str
0x14002618b  call    wcslen_0
0x140026190  lea     ecx, ds:2[rax*2]
0x140026197  jmp     short loc_14002619B
0x140026199  mov     ecx, esi
0x14002619b  test    rbx, rbx
0x14002619e  mov     [rdi+68h], ecx
0x1400261a1  lea     r14, SourceString
0x1400261a8  mov     [rdi+6Ch], r12d
0x1400261ac  mov     rax, r14
0x1400261af  mov     qword ptr [rdi+78h], 4
0x1400261b7  cmovnz  rax, rbx
0x1400261bb  mov     qword ptr [rdi+88h], 8
0x1400261c6  mov     rbx, [rbp+arg_60]
0x1400261cd  mov     [rdi+60h], rax
0x1400261d1  lea     rax, [rbp+arg_38]
0x1400261d8  mov     [rdi+70h], rax
0x1400261dc  lea     rax, [rbp+arg_40]
0x1400261e3  mov     [rdi+80h], rax
0x1400261ea  lea     rax, [rbp+arg_50]
0x1400261f1  mov     [rdi+90h], rax
0x1400261f8  lea     rax, [rbp+arg_58]
0x1400261ff  mov     [rdi+0A0h], rax
0x140026206  mov     qword ptr [rdi+98h], 4
0x140026211  mov     qword ptr [rdi+0A8h], 1
0x14002621c  test    rbx, rbx
0x14002621f  jz      short loc_140026233
0x140026221  mov     rcx, rbx; Str
0x140026224  call    wcslen_0
0x140026229  test    rbx, rbx
0x14002622c  lea     esi, ds:2[rax*2]
0x140026233  cmovnz  r14, rbx
0x140026237  mov     [rdi+0B8h], esi
0x14002623d  mov     [rdi+0B0h], r14
0x140026244  lea     rax, [rbp+arg_68]
0x14002624b  mov     [rdi+0C0h], rax
0x140026252  mov     r9d, 0Eh; UserDataCount
0x140026258  mov     rax, [rbp+arg_70]
0x14002625f  xor     r8d, r8d; ActivityId
0x140026262  mov     [rdi+0BCh], r12d
0x140026269  mov     rdx, r15; EventDescriptor
0x14002626c  mov     qword ptr [rdi+0C8h], 4
0x140026277  mov     ecx, [rbp+arg_68]
0x14002627d  mov     [rdi+0D0h], rax
0x140026284  mov     [rdi+0D8h], ecx
0x14002628a  mov     [rdi+0DCh], r12d
0x140026291  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140026298  mov     [rsp+38h+UserData], rdi; UserData
0x14002629d  call    cs:__imp_EtwWrite
0x1400262a4  nop     dword ptr [rax+rax+00h]
0x1400262a9  mov     rcx, rdi; ListEntry
0x1400262ac  mov     ebx, eax
0x1400262ae  call    SecReleaseEtwDescriptorBuffer
0x1400262b3  mov     eax, ebx
0x1400262b5  add     rsp, 38h
0x1400262b9  pop     r15
0x1400262bb  pop     r14
0x1400262bd  pop     r13
0x1400262bf  pop     r12
0x1400262c1  pop     rdi
0x1400262c2  pop     rsi
0x1400262c3  pop     rbx
0x1400262c4  pop     rbp
0x1400262c5  retn
```
