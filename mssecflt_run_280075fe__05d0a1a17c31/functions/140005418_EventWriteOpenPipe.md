# EventWriteOpenPipe

- ea: `0x140005418`
- end: `0x140005636`
- name: `EventWriteOpenPipe`
- size: `542`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, char, char, char, char, wchar_t *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005a90`

## callees

- `0x140005418`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000560e`
- `ntoskrnl!EtwWrite` at `0x14000560e`
- `ntoskrnl!RtlLengthSid` at `0x1400054a5`
- `ntoskrnl!RtlLengthSid` at `0x1400054a5`

## pseudocode

```c
__int64 __fastcall EventWriteOpenPipe(
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
        wchar_t *a13,
        int a14,
        __int64 a15)
{
  PSID v15; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v19; // eax
  int v20; // esi
  const wchar_t *v21; // rbx
  int v22; // ecx
  const WCHAR *v23; // r14
  const WCHAR *v24; // rax
  const wchar_t *v25; // rbx
  bool v26; // zf
  int v27; // eax
  __int64 v28; // rax
  int v29; // ecx
  unsigned int v30; // ebx
  __int64 v31; // [rsp+70h] [rbp+40h] BYREF
  int v32; // [rsp+78h] [rbp+48h] BYREF
  __int64 v33; // [rsp+80h] [rbp+50h] BYREF
  int v34; // [rsp+88h] [rbp+58h] BYREF

  v34 = a4;
  v33 = a3;
  v32 = a2;
  v31 = a1;
  v15 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(15);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v31;
  EtwDescriptorBuffer[2] = &v32;
  EtwDescriptorBuffer[4] = &v33;
  EtwDescriptorBuffer[6] = &v34;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v15 )
    v19 = RtlLengthSid(v15);
  else
    v19 = 0;
  UserData[8] = v15;
  v20 = 2;
  v21 = Str;
  *((_DWORD *)UserData + 18) = v19;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a6;
  UserData[11] = 4;
  if ( v21 )
    v22 = 2 * wcslen_0(v21) + 2;
  else
    v22 = 2;
  *((_DWORD *)UserData + 26) = v22;
  v23 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v24 = &SourceString;
  UserData[15] = 4;
  if ( v21 )
    v24 = v21;
  UserData[17] = 4;
  v25 = a13;
  UserData[12] = v24;
  UserData[14] = &a8;
  UserData[16] = &a9;
  UserData[18] = &a10;
  UserData[20] = &a11;
  UserData[22] = &a12;
  UserData[19] = 4;
  UserData[21] = 4;
  UserData[23] = 8;
  v26 = v25 == 0;
  if ( v25 )
  {
    v27 = wcslen_0(v25);
    v26 = v25 == 0;
    v20 = 2 * v27 + 2;
  }
  if ( !v26 )
    v23 = v25;
  *((_DWORD *)UserData + 50) = v20;
  UserData[24] = v23;
  UserData[26] = &a14;
  v28 = a15;
  *((_DWORD *)UserData + 51) = 0;
  UserData[27] = 4;
  v29 = a14;
  UserData[28] = v28;
  *((_DWORD *)UserData + 58) = v29;
  *((_DWORD *)UserData + 59) = 0;
  v30 = EtwWrite(Microsoft_Windows_SECHandle, &Event17, 0, 0xFu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v30;
}

```

## disassembly

```asm
0x140005418  mov     rax, rsp
0x14000541b  mov     [rax+20h], r9d
0x14000541f  mov     [rax+18h], r8
0x140005423  mov     [rax+10h], edx
0x140005426  mov     [rax+8], rcx
0x14000542a  push    rbp
0x14000542b  push    rbx
0x14000542c  push    rsi
0x14000542d  push    rdi
0x14000542e  push    r12
0x140005430  push    r14
0x140005432  push    r15
0x140005434  mov     rbp, rsp
0x140005437  sub     rsp, 30h
0x14000543b  mov     rbx, [rbp+Sid]
0x14000543f  mov     ecx, 0Fh
0x140005444  call    SecGetEtwDescriptorBuffer
0x140005449  xor     r15d, r15d
0x14000544c  mov     rdi, rax
0x14000544f  test    rax, rax
0x140005452  jnz     short loc_14000545E
0x140005454  mov     eax, 0C000009Ah
0x140005459  jmp     loc_140005626
0x14000545e  mov     qword ptr [rdi+8], 8
0x140005466  lea     rax, [rbp+arg_0]
0x14000546a  mov     [rdi], rax
0x14000546d  lea     rax, [rbp+arg_8]
0x140005471  mov     [rdi+10h], rax
0x140005475  lea     rax, [rbp+arg_10]
0x140005479  mov     [rdi+20h], rax
0x14000547d  lea     rax, [rbp+arg_18]
0x140005481  mov     [rdi+30h], rax
0x140005485  mov     qword ptr [rdi+18h], 4
0x14000548d  mov     qword ptr [rdi+28h], 8
0x140005495  mov     qword ptr [rdi+38h], 4
0x14000549d  test    rbx, rbx
0x1400054a0  jz      short loc_1400054B3
0x1400054a2  mov     rcx, rbx; Sid
0x1400054a5  call    cs:__imp_RtlLengthSid
0x1400054ac  nop     dword ptr [rax+rax+00h]
0x1400054b1  jmp     short loc_1400054B6
0x1400054b3  mov     eax, r15d
0x1400054b6  mov     [rdi+40h], rbx
0x1400054ba  mov     esi, 2
0x1400054bf  mov     rbx, [rbp+Str]
0x1400054c3  mov     [rdi+48h], eax
0x1400054c6  lea     rax, [rbp+arg_28]
0x1400054ca  mov     [rdi+4Ch], r15d
0x1400054ce  mov     [rdi+50h], rax
0x1400054d2  mov     qword ptr [rdi+58h], 4
0x1400054da  test    rbx, rbx
0x1400054dd  jz      short loc_1400054F0
0x1400054df  mov     rcx, rbx; Str
0x1400054e2  call    wcslen_0
0x1400054e7  lea     ecx, ds:2[rax*2]
0x1400054ee  jmp     short loc_1400054F2
0x1400054f0  mov     ecx, esi
0x1400054f2  test    rbx, rbx
0x1400054f5  mov     [rdi+68h], ecx
0x1400054f8  lea     r14, SourceString
0x1400054ff  mov     [rdi+6Ch], r15d
0x140005503  mov     rax, r14
0x140005506  mov     qword ptr [rdi+78h], 4
0x14000550e  cmovnz  rax, rbx
0x140005512  mov     qword ptr [rdi+88h], 4
0x14000551d  mov     rbx, [rbp+arg_60]
0x140005524  mov     [rdi+60h], rax
0x140005528  lea     rax, [rbp+arg_38]
0x14000552c  mov     [rdi+70h], rax
0x140005530  lea     rax, [rbp+arg_40]
0x140005537  mov     [rdi+80h], rax
0x14000553e  lea     rax, [rbp+arg_48]
0x140005545  mov     [rdi+90h], rax
0x14000554c  lea     rax, [rbp+arg_50]
0x140005553  mov     [rdi+0A0h], rax
0x14000555a  lea     rax, [rbp+arg_58]
0x140005561  mov     [rdi+0B0h], rax
0x140005568  mov     qword ptr [rdi+98h], 4
0x140005573  mov     qword ptr [rdi+0A8h], 4
0x14000557e  mov     qword ptr [rdi+0B8h], 8
0x140005589  test    rbx, rbx
0x14000558c  jz      short loc_1400055A0
0x14000558e  mov     rcx, rbx; Str
0x140005591  call    wcslen_0
0x140005596  test    rbx, rbx
0x140005599  lea     esi, ds:2[rax*2]
0x1400055a0  cmovnz  r14, rbx
0x1400055a4  mov     [rdi+0C8h], esi
0x1400055aa  mov     [rdi+0C0h], r14
0x1400055b1  lea     rax, [rbp+arg_68]
0x1400055b8  mov     [rdi+0D0h], rax
0x1400055bf  lea     rdx, Event17; EventDescriptor
0x1400055c6  mov     rax, [rbp+arg_70]
0x1400055cd  mov     r9d, 0Fh; UserDataCount
0x1400055d3  mov     [rdi+0CCh], r15d
0x1400055da  xor     r8d, r8d; ActivityId
0x1400055dd  mov     qword ptr [rdi+0D8h], 4
0x1400055e8  mov     ecx, [rbp+arg_68]
0x1400055ee  mov     [rdi+0E0h], rax
0x1400055f5  mov     [rdi+0E8h], ecx
0x1400055fb  mov     [rdi+0ECh], r15d
0x140005602  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140005609  mov     [rsp+30h+UserData], rdi; UserData
0x14000560e  call    cs:__imp_EtwWrite
0x140005615  nop     dword ptr [rax+rax+00h]
0x14000561a  mov     rcx, rdi; ListEntry
0x14000561d  mov     ebx, eax
0x14000561f  call    SecReleaseEtwDescriptorBuffer
0x140005624  mov     eax, ebx
0x140005626  add     rsp, 30h
0x14000562a  pop     r15
0x14000562c  pop     r14
0x14000562e  pop     r12
0x140005630  pop     rdi
0x140005631  pop     rsi
0x140005632  pop     rbx
0x140005633  pop     rbp
0x140005634  retn
```
