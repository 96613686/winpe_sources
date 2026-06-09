# EventWriteUnauthorizedFileOpenAttempt

- ea: `0x140005638`
- end: `0x1400057a5`
- name: `EventWriteUnauthorizedFileOpenAttempt`
- size: `365`
- prototype: `__int64 __fastcall(int, int, int, int, char, PSID Sid, char, wchar_t *Str, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400280f8`

## callees

- `0x140005638`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140005784`
- `ntoskrnl!EtwWrite` at `0x140005784`
- `ntoskrnl!RtlLengthSid` at `0x1400056cb`
- `ntoskrnl!RtlLengthSid` at `0x1400056cb`

## pseudocode

```c
__int64 __fastcall EventWriteUnauthorizedFileOpenAttempt(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        wchar_t *Str,
        int a9,
        __int64 a10)
{
  PSID v10; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v14; // eax
  const wchar_t *v15; // rbx
  int v16; // ecx
  const WCHAR *v17; // rax
  int v18; // ecx
  unsigned int v19; // ebx
  __int64 v20; // [rsp+50h] [rbp+20h] BYREF
  int v21; // [rsp+58h] [rbp+28h] BYREF
  __int64 v22; // [rsp+60h] [rbp+30h] BYREF
  __int64 v23; // [rsp+68h] [rbp+38h] BYREF

  v23 = a4;
  v22 = a3;
  v21 = a2;
  v20 = a1;
  v10 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(10);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v20;
  EtwDescriptorBuffer[2] = &v21;
  EtwDescriptorBuffer[4] = &v22;
  EtwDescriptorBuffer[6] = &v23;
  EtwDescriptorBuffer[8] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 8;
  EtwDescriptorBuffer[9] = 4;
  if ( v10 )
    v14 = RtlLengthSid(v10);
  else
    v14 = 0;
  UserData[10] = v10;
  v15 = Str;
  *((_DWORD *)UserData + 22) = v14;
  *((_DWORD *)UserData + 23) = 0;
  UserData[12] = &a7;
  UserData[13] = 1;
  if ( v15 )
    v16 = 2 * wcslen_0(v15) + 2;
  else
    v16 = 2;
  *((_DWORD *)UserData + 30) = v16;
  v17 = &SourceString;
  *((_DWORD *)UserData + 31) = 0;
  UserData[17] = 4;
  if ( v15 )
    v17 = v15;
  UserData[14] = v17;
  UserData[16] = &a9;
  v18 = a9;
  UserData[18] = a10;
  *((_DWORD *)UserData + 38) = v18;
  *((_DWORD *)UserData + 39) = 0;
  v19 = EtwWrite(Microsoft_Windows_SECHandle, &Event31, 0, 0xAu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v19;
}

```

## disassembly

```asm
0x140005638  mov     rax, rsp
0x14000563b  mov     [rax+20h], r9
0x14000563f  mov     [rax+18h], r8
0x140005643  mov     [rax+10h], edx
0x140005646  mov     [rax+8], rcx
0x14000564a  push    rbp
0x14000564b  push    rbx
0x14000564c  push    rdi
0x14000564d  mov     rbp, rsp
0x140005650  sub     rsp, 30h
0x140005654  mov     rbx, [rbp+Sid]
0x140005658  mov     ecx, 0Ah
0x14000565d  call    SecGetEtwDescriptorBuffer
0x140005662  mov     rdi, rax
0x140005665  test    rax, rax
0x140005668  jnz     short loc_140005674
0x14000566a  mov     eax, 0C000009Ah
0x14000566f  jmp     loc_14000579C
0x140005674  mov     qword ptr [rdi+8], 8
0x14000567c  lea     rax, [rbp+arg_0]
0x140005680  mov     [rdi], rax
0x140005683  lea     rax, [rbp+arg_8]
0x140005687  mov     [rdi+10h], rax
0x14000568b  lea     rax, [rbp+arg_10]
0x14000568f  mov     [rdi+20h], rax
0x140005693  lea     rax, [rbp+arg_18]
0x140005697  mov     [rdi+30h], rax
0x14000569b  lea     rax, [rbp+arg_20]
0x14000569f  mov     [rdi+40h], rax
0x1400056a3  mov     qword ptr [rdi+18h], 4
0x1400056ab  mov     qword ptr [rdi+28h], 8
0x1400056b3  mov     qword ptr [rdi+38h], 8
0x1400056bb  mov     qword ptr [rdi+48h], 4
0x1400056c3  test    rbx, rbx
0x1400056c6  jz      short loc_1400056D9
0x1400056c8  mov     rcx, rbx; Sid
0x1400056cb  call    cs:__imp_RtlLengthSid
0x1400056d2  nop     dword ptr [rax+rax+00h]
0x1400056d7  jmp     short loc_1400056DB
0x1400056d9  xor     eax, eax
0x1400056db  mov     [rdi+50h], rbx
0x1400056df  mov     rbx, [rbp+Str]
0x1400056e3  mov     [rdi+58h], eax
0x1400056e6  lea     rax, [rbp+arg_30]
0x1400056ea  mov     dword ptr [rdi+5Ch], 0
0x1400056f1  mov     [rdi+60h], rax
0x1400056f5  mov     qword ptr [rdi+68h], 1
0x1400056fd  test    rbx, rbx
0x140005700  jz      short loc_140005713
0x140005702  mov     rcx, rbx; Str
0x140005705  call    wcslen_0
0x14000570a  lea     ecx, ds:2[rax*2]
0x140005711  jmp     short loc_140005718
0x140005713  mov     ecx, 2
0x140005718  mov     [rdi+78h], ecx
0x14000571b  lea     rax, SourceString
0x140005722  mov     dword ptr [rdi+7Ch], 0
0x140005729  lea     rdx, Event31; EventDescriptor
0x140005730  mov     qword ptr [rdi+88h], 4
0x14000573b  test    rbx, rbx
0x14000573e  mov     r9d, 0Ah; UserDataCount
0x140005744  mov     [rsp+30h+UserData], rdi; UserData
0x140005749  cmovnz  rax, rbx
0x14000574d  xor     r8d, r8d; ActivityId
0x140005750  mov     [rdi+70h], rax
0x140005754  lea     rax, [rbp+arg_40]
0x140005758  mov     [rdi+80h], rax
0x14000575f  mov     ecx, [rbp+arg_40]
0x140005762  mov     rax, [rbp+arg_48]
0x140005766  mov     [rdi+90h], rax
0x14000576d  mov     [rdi+98h], ecx
0x140005773  mov     dword ptr [rdi+9Ch], 0
0x14000577d  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140005784  call    cs:__imp_EtwWrite
0x14000578b  nop     dword ptr [rax+rax+00h]
0x140005790  mov     rcx, rdi; ListEntry
0x140005793  mov     ebx, eax
0x140005795  call    SecReleaseEtwDescriptorBuffer
0x14000579a  mov     eax, ebx
0x14000579c  add     rsp, 30h
0x1400057a0  pop     rdi
0x1400057a1  pop     rbx
0x1400057a2  pop     rbp
0x1400057a3  retn
```
