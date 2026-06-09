# EventWriteOpenProcess

- ea: `0x14002b76c`
- end: `0x14002b917`
- name: `EventWriteOpenProcess`
- size: `427`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, char, PSID Sid, char, char, char, wchar_t *Str, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002be2c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x14002b76c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002b8ef`
- `ntoskrnl!EtwWrite` at `0x14002b8ef`
- `ntoskrnl!RtlLengthSid` at `0x14002b7f9`
- `ntoskrnl!RtlLengthSid` at `0x14002b7f9`

## pseudocode

```c
__int64 EventWriteOpenProcess(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        int a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        char a8,
        char a9,
        wchar_t *Str,
        ...)
{
  PSID v10; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v15; // eax
  const wchar_t *v16; // rbx
  int v17; // ecx
  const WCHAR *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // [rsp+78h] [rbp+48h] BYREF
  int v21; // [rsp+80h] [rbp+50h] BYREF
  __int64 v22; // [rsp+88h] [rbp+58h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+90h] BYREF
  va_list va; // [rsp+C0h] [rbp+90h]
  __int64 v25; // [rsp+C8h] [rbp+98h] BYREF
  va_list va1; // [rsp+C8h] [rbp+98h]
  va_list va2; // [rsp+D0h] [rbp+A0h] BYREF

  va_start(va2, Str);
  va_start(va1, Str);
  va_start(va, Str);
  v23 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v25 = va_arg(va2, _QWORD);
  v22 = a4;
  v21 = a3;
  v20 = a2;
  v10 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(12);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v20;
  EtwDescriptorBuffer[2] = &v21;
  EtwDescriptorBuffer[4] = &v22;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v10 )
    v15 = RtlLengthSid(v10);
  else
    v15 = 0;
  *((_DWORD *)UserData + 18) = v15;
  UserData[10] = &a7;
  UserData[8] = v10;
  v16 = Str;
  UserData[12] = &a8;
  UserData[14] = &a9;
  *((_DWORD *)UserData + 19) = 0;
  UserData[11] = 4;
  UserData[13] = 4;
  UserData[15] = 8;
  if ( v16 )
    v17 = 2 * wcslen_0(v16) + 2;
  else
    v17 = 2;
  *((_DWORD *)UserData + 34) = v17;
  v18 = &SourceString;
  *((_DWORD *)UserData + 35) = 0;
  UserData[19] = 4;
  if ( v16 )
    v18 = v16;
  UserData[21] = 8;
  UserData[16] = v18;
  UserData[23] = 8;
  UserData[18] = va;
  UserData[20] = va1;
  UserData[22] = va2;
  v19 = EtwWrite(Microsoft_Windows_SECHandle, EventDescriptor, 0, 0xCu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v19;
}

```

## disassembly

```asm
0x14002b76c  mov     [rsp-38h+arg_18], r9
0x14002b771  mov     [rsp-38h+arg_10], r8d
0x14002b776  mov     [rsp-38h+arg_8], rdx
0x14002b77b  push    rbp
0x14002b77c  push    rbx
0x14002b77d  push    rsi
0x14002b77e  push    rdi
0x14002b77f  push    r12
0x14002b781  push    r14
0x14002b783  push    r15
0x14002b785  mov     rbp, rsp
0x14002b788  sub     rsp, 30h
0x14002b78c  mov     rbx, [rbp+Sid]
0x14002b790  mov     rsi, rcx
0x14002b793  mov     ecx, 0Ch
0x14002b798  call    SecGetEtwDescriptorBuffer
0x14002b79d  xor     r14d, r14d
0x14002b7a0  mov     rdi, rax
0x14002b7a3  test    rax, rax
0x14002b7a6  jnz     short loc_14002B7B2
0x14002b7a8  mov     eax, 0C000009Ah
0x14002b7ad  jmp     loc_14002B907
0x14002b7b2  mov     qword ptr [rdi+8], 8
0x14002b7ba  lea     rax, [rbp+arg_8]
0x14002b7be  mov     [rdi], rax
0x14002b7c1  lea     rax, [rbp+arg_10]
0x14002b7c5  mov     [rdi+10h], rax
0x14002b7c9  lea     rax, [rbp+arg_18]
0x14002b7cd  mov     [rdi+20h], rax
0x14002b7d1  lea     rax, [rbp+arg_20]
0x14002b7d5  mov     [rdi+30h], rax
0x14002b7d9  mov     qword ptr [rdi+18h], 4
0x14002b7e1  mov     qword ptr [rdi+28h], 8
0x14002b7e9  mov     qword ptr [rdi+38h], 4
0x14002b7f1  test    rbx, rbx
0x14002b7f4  jz      short loc_14002B807
0x14002b7f6  mov     rcx, rbx; Sid
0x14002b7f9  call    cs:__imp_RtlLengthSid
0x14002b800  nop     dword ptr [rax+rax+00h]
0x14002b805  jmp     short loc_14002B80A
0x14002b807  mov     eax, r14d
0x14002b80a  mov     [rdi+48h], eax
0x14002b80d  lea     rax, [rbp+arg_30]
0x14002b811  mov     [rdi+50h], rax
0x14002b815  lea     rax, [rbp+arg_38]
0x14002b819  mov     [rdi+40h], rbx
0x14002b81d  mov     rbx, [rbp+Str]
0x14002b824  mov     [rdi+60h], rax
0x14002b828  lea     rax, [rbp+arg_40]
0x14002b82f  mov     [rdi+70h], rax
0x14002b833  mov     [rdi+4Ch], r14d
0x14002b837  mov     qword ptr [rdi+58h], 4
0x14002b83f  mov     qword ptr [rdi+68h], 4
0x14002b847  mov     qword ptr [rdi+78h], 8
0x14002b84f  test    rbx, rbx
0x14002b852  jz      short loc_14002B865
0x14002b854  mov     rcx, rbx; Str
0x14002b857  call    wcslen_0
0x14002b85c  lea     ecx, ds:2[rax*2]
0x14002b863  jmp     short loc_14002B86A
0x14002b865  mov     ecx, 2
0x14002b86a  mov     [rdi+88h], ecx
0x14002b870  lea     rax, SourceString
0x14002b877  mov     [rdi+8Ch], r14d
0x14002b87e  test    rbx, rbx
0x14002b881  mov     qword ptr [rdi+98h], 4
0x14002b88c  mov     r9d, 0Ch; UserDataCount
0x14002b892  cmovnz  rax, rbx
0x14002b896  mov     qword ptr [rdi+0A8h], 8
0x14002b8a1  mov     [rdi+80h], rax
0x14002b8a8  xor     r8d, r8d; ActivityId
0x14002b8ab  lea     rax, [rbp+arg_50]
0x14002b8b2  mov     qword ptr [rdi+0B8h], 8
0x14002b8bd  mov     [rdi+90h], rax
0x14002b8c4  mov     rdx, rsi; EventDescriptor
0x14002b8c7  lea     rax, [rbp+arg_58]
0x14002b8ce  mov     [rsp+30h+UserData], rdi; UserData
0x14002b8d3  mov     [rdi+0A0h], rax
0x14002b8da  lea     rax, [rbp+arg_60]
0x14002b8e1  mov     [rdi+0B0h], rax
0x14002b8e8  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002b8ef  call    cs:__imp_EtwWrite
0x14002b8f6  nop     dword ptr [rax+rax+00h]
0x14002b8fb  mov     rcx, rdi; ListEntry
0x14002b8fe  mov     ebx, eax
0x14002b900  call    SecReleaseEtwDescriptorBuffer
0x14002b905  mov     eax, ebx
0x14002b907  add     rsp, 30h
0x14002b90b  pop     r15
0x14002b90d  pop     r14
0x14002b90f  pop     r12
0x14002b911  pop     rdi
0x14002b912  pop     rsi
0x14002b913  pop     rbx
0x14002b914  pop     rbp
0x14002b915  retn
```
