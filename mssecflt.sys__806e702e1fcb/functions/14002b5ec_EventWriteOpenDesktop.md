# EventWriteOpenDesktop

- ea: `0x14002b5ec`
- end: `0x14002b76b`
- name: `EventWriteOpenDesktop`
- size: `383`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002bc14`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x14002b5ec`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002b748`
- `ntoskrnl!EtwWrite` at `0x14002b748`
- `ntoskrnl!RtlLengthSid` at `0x14002b671`
- `ntoskrnl!RtlLengthSid` at `0x14002b671`

## pseudocode

```c
__int64 __fastcall EventWriteOpenDesktop(
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
  UserData[19] = 4;
  UserData[12] = v18;
  UserData[21] = 8;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  v19 = EtwWrite(Microsoft_Windows_SECHandle, &Event20, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v19;
}

```

## disassembly

```asm
0x14002b5ec  mov     rax, rsp
0x14002b5ef  mov     [rax+20h], r9d
0x14002b5f3  mov     [rax+18h], r8
0x14002b5f7  mov     [rax+10h], edx
0x14002b5fa  mov     [rax+8], rcx
0x14002b5fe  push    rbp
0x14002b5ff  push    rbx
0x14002b600  push    rdi
0x14002b601  push    r14
0x14002b603  mov     rbp, rsp
0x14002b606  sub     rsp, 38h
0x14002b60a  mov     rbx, [rbp+Sid]
0x14002b60e  mov     ecx, 0Bh
0x14002b613  call    SecGetEtwDescriptorBuffer
0x14002b618  mov     rdi, rax
0x14002b61b  test    rax, rax
0x14002b61e  jnz     short loc_14002B62A
0x14002b620  mov     eax, 0C000009Ah
0x14002b625  jmp     loc_14002B760
0x14002b62a  mov     qword ptr [rdi+8], 8
0x14002b632  lea     rax, [rbp+arg_0]
0x14002b636  mov     [rdi], rax
0x14002b639  lea     rax, [rbp+arg_8]
0x14002b63d  mov     [rdi+10h], rax
0x14002b641  lea     rax, [rbp+arg_10]
0x14002b645  mov     [rdi+20h], rax
0x14002b649  lea     rax, [rbp+arg_18]
0x14002b64d  mov     [rdi+30h], rax
0x14002b651  mov     qword ptr [rdi+18h], 4
0x14002b659  mov     qword ptr [rdi+28h], 8
0x14002b661  mov     qword ptr [rdi+38h], 4
0x14002b669  test    rbx, rbx
0x14002b66c  jz      short loc_14002B67F
0x14002b66e  mov     rcx, rbx; Sid
0x14002b671  call    cs:__imp_RtlLengthSid
0x14002b678  nop     dword ptr [rax+rax+00h]
0x14002b67d  jmp     short loc_14002B681
0x14002b67f  xor     eax, eax
0x14002b681  mov     [rdi+40h], rbx
0x14002b685  mov     rbx, [rbp+Str]
0x14002b689  mov     [rdi+48h], eax
0x14002b68c  lea     rax, [rbp+arg_28]
0x14002b690  mov     dword ptr [rdi+4Ch], 0
0x14002b697  mov     [rdi+50h], rax
0x14002b69b  mov     qword ptr [rdi+58h], 4
0x14002b6a3  test    rbx, rbx
0x14002b6a6  jz      short loc_14002B6B9
0x14002b6a8  mov     rcx, rbx; Str
0x14002b6ab  call    wcslen_0
0x14002b6b0  lea     ecx, ds:2[rax*2]
0x14002b6b7  jmp     short loc_14002B6BE
0x14002b6b9  mov     ecx, 2
0x14002b6be  mov     [rdi+68h], ecx
0x14002b6c1  lea     rax, SourceString
0x14002b6c8  mov     dword ptr [rdi+6Ch], 0
0x14002b6cf  lea     rdx, Event20; EventDescriptor
0x14002b6d6  mov     qword ptr [rdi+78h], 4
0x14002b6de  test    rbx, rbx
0x14002b6e1  mov     qword ptr [rdi+88h], 4
0x14002b6ec  mov     r9d, 0Bh; UserDataCount
0x14002b6f2  cmovnz  rax, rbx
0x14002b6f6  mov     qword ptr [rdi+98h], 4
0x14002b701  mov     [rdi+60h], rax
0x14002b705  xor     r8d, r8d; ActivityId
0x14002b708  lea     rax, [rbp+arg_38]
0x14002b70c  mov     qword ptr [rdi+0A8h], 8
0x14002b717  mov     [rdi+70h], rax
0x14002b71b  lea     rax, [rbp+arg_40]
0x14002b71f  mov     [rdi+80h], rax
0x14002b726  lea     rax, [rbp+arg_48]
0x14002b72a  mov     [rdi+90h], rax
0x14002b731  lea     rax, [rbp+arg_50]
0x14002b735  mov     [rdi+0A0h], rax
0x14002b73c  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002b743  mov     [rsp+38h+UserData], rdi; UserData
0x14002b748  call    cs:__imp_EtwWrite
0x14002b74f  nop     dword ptr [rax+rax+00h]
0x14002b754  mov     rcx, rdi; ListEntry
0x14002b757  mov     ebx, eax
0x14002b759  call    SecReleaseEtwDescriptorBuffer
0x14002b75e  mov     eax, ebx
0x14002b760  add     rsp, 38h
0x14002b764  pop     r14
0x14002b766  pop     rdi
0x14002b767  pop     rbx
0x14002b768  pop     rbp
0x14002b769  retn
```
