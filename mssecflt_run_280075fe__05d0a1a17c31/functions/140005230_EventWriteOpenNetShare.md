# EventWriteOpenNetShare

- ea: `0x140005230`
- end: `0x140005416`
- name: `EventWriteOpenNetShare`
- size: `486`
- prototype: `__int64 __fastcall(int, int, int, int, char, PSID Sid, char, wchar_t *Str, wchar_t *, wchar_t *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140027ec4`

## callees

- `0x140005230`
- `0x140008714`
- `0x14000876c`
- `0x14001008c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400053f4`
- `ntoskrnl!EtwWrite` at `0x1400053f4`
- `ntoskrnl!RtlLengthSid` at `0x1400052cd`
- `ntoskrnl!RtlLengthSid` at `0x1400052cd`

## pseudocode

```c
__int64 EventWriteOpenNetShare(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        wchar_t *Str,
        wchar_t *a9,
        wchar_t *a10,
        ...)
{
  PSID v10; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v14; // eax
  int v15; // esi
  const wchar_t *v16; // rbx
  int v17; // ecx
  const WCHAR *v18; // rbp
  const WCHAR *v19; // rax
  const wchar_t *v20; // rbx
  int v21; // ecx
  const WCHAR *v22; // rax
  const wchar_t *v23; // rbx
  bool v24; // zf
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // [rsp+60h] [rbp+8h] BYREF
  int v28; // [rsp+68h] [rbp+10h] BYREF
  __int64 v29; // [rsp+70h] [rbp+18h] BYREF
  __int64 v30; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+B0h] [rbp+58h] BYREF

  va_start(va, a10);
  v30 = a4;
  v29 = a3;
  v28 = a2;
  v27 = a1;
  v10 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(11);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v27;
  EtwDescriptorBuffer[2] = &v28;
  EtwDescriptorBuffer[4] = &v29;
  EtwDescriptorBuffer[6] = &v30;
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
  v15 = 2;
  v16 = Str;
  *((_DWORD *)UserData + 22) = v14;
  *((_DWORD *)UserData + 23) = 0;
  UserData[12] = &a7;
  UserData[13] = 4;
  if ( v16 )
    v17 = 2 * wcslen_0(v16) + 2;
  else
    v17 = 2;
  *((_DWORD *)UserData + 30) = v17;
  v18 = &SourceString;
  *((_DWORD *)UserData + 31) = 0;
  v19 = &SourceString;
  if ( v16 )
    v19 = v16;
  v20 = a9;
  UserData[14] = v19;
  if ( v20 )
    v21 = 2 * wcslen_0(v20) + 2;
  else
    v21 = 2;
  *((_DWORD *)UserData + 34) = v21;
  v22 = &SourceString;
  *((_DWORD *)UserData + 35) = 0;
  if ( v20 )
    v22 = v20;
  v23 = a10;
  UserData[16] = v22;
  v24 = v23 == 0;
  if ( v23 )
  {
    v25 = wcslen_0(v23);
    v24 = v23 == 0;
    v15 = 2 * v25 + 2;
  }
  if ( !v24 )
    v18 = v23;
  *((_DWORD *)UserData + 38) = v15;
  UserData[18] = v18;
  UserData[20] = va;
  *((_DWORD *)UserData + 39) = 0;
  UserData[21] = 1;
  v26 = EtwWrite(Microsoft_Windows_SECHandle, &Event26, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v26;
}

```

## disassembly

```asm
0x140005230  mov     rax, rsp
0x140005233  mov     [rax+20h], r9
0x140005237  mov     [rax+18h], r8
0x14000523b  mov     [rax+10h], edx
0x14000523e  mov     [rax+8], rcx
0x140005242  push    rbx
0x140005243  push    rbp
0x140005244  push    rsi
0x140005245  push    rdi
0x140005246  sub     rsp, 38h
0x14000524a  mov     rbx, [rsp+58h+Sid]
0x140005252  mov     ecx, 0Bh
0x140005257  call    SecGetEtwDescriptorBuffer
0x14000525c  mov     rdi, rax
0x14000525f  test    rax, rax
0x140005262  jnz     short loc_14000526E
0x140005264  mov     eax, 0C000009Ah
0x140005269  jmp     loc_14000540C
0x14000526e  mov     qword ptr [rdi+8], 8
0x140005276  lea     rax, [rsp+58h+arg_0]
0x14000527b  mov     [rdi], rax
0x14000527e  lea     rax, [rsp+58h+arg_8]
0x140005283  mov     [rdi+10h], rax
0x140005287  lea     rax, [rsp+58h+arg_10]
0x14000528c  mov     [rdi+20h], rax
0x140005290  lea     rax, [rsp+58h+arg_18]
0x140005295  mov     [rdi+30h], rax
0x140005299  lea     rax, [rsp+58h+arg_20]
0x1400052a1  mov     [rdi+40h], rax
0x1400052a5  mov     qword ptr [rdi+18h], 4
0x1400052ad  mov     qword ptr [rdi+28h], 8
0x1400052b5  mov     qword ptr [rdi+38h], 8
0x1400052bd  mov     qword ptr [rdi+48h], 4
0x1400052c5  test    rbx, rbx
0x1400052c8  jz      short loc_1400052DB
0x1400052ca  mov     rcx, rbx; Sid
0x1400052cd  call    cs:__imp_RtlLengthSid
0x1400052d4  nop     dword ptr [rax+rax+00h]
0x1400052d9  jmp     short loc_1400052DD
0x1400052db  xor     eax, eax
0x1400052dd  mov     [rdi+50h], rbx
0x1400052e1  mov     esi, 2
0x1400052e6  mov     rbx, [rsp+58h+Str]
0x1400052ee  mov     [rdi+58h], eax
0x1400052f1  lea     rax, [rsp+58h+arg_30]
0x1400052f9  mov     dword ptr [rdi+5Ch], 0
0x140005300  mov     [rdi+60h], rax
0x140005304  mov     qword ptr [rdi+68h], 4
0x14000530c  test    rbx, rbx
0x14000530f  jz      short loc_140005322
0x140005311  mov     rcx, rbx; Str
0x140005314  call    wcslen_0
0x140005319  lea     ecx, ds:2[rax*2]
0x140005320  jmp     short loc_140005324
0x140005322  mov     ecx, esi
0x140005324  test    rbx, rbx
0x140005327  mov     [rdi+78h], ecx
0x14000532a  lea     rbp, SourceString
0x140005331  mov     dword ptr [rdi+7Ch], 0
0x140005338  mov     rax, rbp
0x14000533b  cmovnz  rax, rbx
0x14000533f  mov     rbx, [rsp+58h+arg_40]
0x140005347  mov     [rdi+70h], rax
0x14000534b  test    rbx, rbx
0x14000534e  jz      short loc_140005361
0x140005350  mov     rcx, rbx; Str
0x140005353  call    wcslen_0
0x140005358  lea     ecx, ds:2[rax*2]
0x14000535f  jmp     short loc_140005363
0x140005361  mov     ecx, esi
0x140005363  test    rbx, rbx
0x140005366  mov     [rdi+88h], ecx
0x14000536c  mov     rax, rbp
0x14000536f  mov     dword ptr [rdi+8Ch], 0
0x140005379  cmovnz  rax, rbx
0x14000537d  mov     rbx, [rsp+58h+arg_48]
0x140005385  mov     [rdi+80h], rax
0x14000538c  test    rbx, rbx
0x14000538f  jz      short loc_1400053A3
0x140005391  mov     rcx, rbx; Str
0x140005394  call    wcslen_0
0x140005399  test    rbx, rbx
0x14000539c  lea     esi, ds:2[rax*2]
0x1400053a3  cmovnz  rbp, rbx
0x1400053a7  mov     [rdi+98h], esi
0x1400053ad  lea     rax, [rsp+58h+arg_50]
0x1400053b5  mov     [rdi+90h], rbp
0x1400053bc  mov     [rdi+0A0h], rax
0x1400053c3  lea     rdx, Event26; EventDescriptor
0x1400053ca  mov     dword ptr [rdi+9Ch], 0
0x1400053d4  mov     r9d, 0Bh; UserDataCount
0x1400053da  mov     qword ptr [rdi+0A8h], 1
0x1400053e5  xor     r8d, r8d; ActivityId
0x1400053e8  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400053ef  mov     [rsp+58h+UserData], rdi; UserData
0x1400053f4  call    cs:__imp_EtwWrite
0x1400053fb  nop     dword ptr [rax+rax+00h]
0x140005400  mov     rcx, rdi; ListEntry
0x140005403  mov     ebx, eax
0x140005405  call    SecReleaseEtwDescriptorBuffer
0x14000540a  mov     eax, ebx
0x14000540c  add     rsp, 38h
0x140005410  pop     rdi
0x140005411  pop     rsi
0x140005412  pop     rbp
0x140005413  pop     rbx
0x140005414  retn
```
