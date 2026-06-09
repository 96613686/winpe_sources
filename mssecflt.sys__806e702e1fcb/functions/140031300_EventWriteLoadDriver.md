# EventWriteLoadDriver

- ea: `0x140031300`
- end: `0x140031598`
- name: `EventWriteLoadDriver`
- size: `664`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, wchar_t *Str, char, __int64, __int64, __int64, char, char, char, char, char, char, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003205c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140031300`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140031572`
- `ntoskrnl!EtwWrite` at `0x140031572`
- `ntoskrnl!RtlLengthSid` at `0x14003138a`
- `ntoskrnl!RtlLengthSid` at `0x14003138a`

## pseudocode

```c
__int64 __fastcall EventWriteLoadDriver(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        wchar_t *Str,
        char a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        char a12,
        char a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20,
        char a21,
        char a22)
{
  PSID v22; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v26; // eax
  const wchar_t *v27; // rbx
  int v28; // ecx
  const WCHAR *v29; // rax
  unsigned int v30; // ebx
  __int64 v31; // [rsp+70h] [rbp+38h] BYREF
  int v32; // [rsp+78h] [rbp+40h] BYREF
  __int64 v33; // [rsp+80h] [rbp+48h] BYREF
  int v34; // [rsp+88h] [rbp+50h] BYREF

  v34 = a4;
  v33 = a3;
  v32 = a2;
  v31 = a1;
  v22 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(22);
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
  if ( v22 )
    v26 = RtlLengthSid(v22);
  else
    v26 = 0;
  UserData[8] = v22;
  v27 = Str;
  *((_DWORD *)UserData + 18) = v26;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a6;
  UserData[11] = 4;
  if ( v27 )
    v28 = 2 * wcslen_0(v27) + 2;
  else
    v28 = 2;
  *((_DWORD *)UserData + 26) = v28;
  v29 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  if ( v27 )
    v29 = v27;
  UserData[15] = 4;
  UserData[12] = v29;
  UserData[17] = 32;
  UserData[14] = &a8;
  UserData[16] = a9;
  UserData[18] = a10;
  UserData[20] = a11;
  UserData[22] = &a12;
  UserData[24] = &a13;
  UserData[26] = &a14;
  UserData[28] = &a15;
  UserData[30] = &a16;
  UserData[32] = &a17;
  UserData[34] = &a18;
  UserData[36] = &a19;
  UserData[38] = &a20;
  UserData[40] = &a21;
  UserData[42] = &a22;
  UserData[19] = 20;
  UserData[21] = 16;
  UserData[23] = 4;
  UserData[25] = 4;
  UserData[27] = 4;
  UserData[29] = 4;
  UserData[31] = 4;
  UserData[33] = 4;
  UserData[35] = 4;
  UserData[37] = 8;
  UserData[39] = 8;
  UserData[41] = 8;
  UserData[43] = 64;
  v30 = EtwWrite(Microsoft_Windows_SECHandle, &Event24, 0, 0x16u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v30;
}

```

## disassembly

```asm
0x140031300  mov     rax, rsp
0x140031303  mov     [rax+20h], r9d
0x140031307  mov     [rax+18h], r8
0x14003130b  mov     [rax+10h], edx
0x14003130e  mov     [rax+8], rcx
0x140031312  push    rbp
0x140031313  push    rbx
0x140031314  push    rsi
0x140031315  push    rdi
0x140031316  push    r14
0x140031318  push    r15
0x14003131a  mov     rbp, rsp
0x14003131d  sub     rsp, 38h
0x140031321  mov     rbx, [rbp+Sid]
0x140031325  mov     ecx, 16h
0x14003132a  call    SecGetEtwDescriptorBuffer
0x14003132f  xor     esi, esi
0x140031331  mov     rdi, rax
0x140031334  test    rax, rax
0x140031337  jnz     short loc_140031343
0x140031339  mov     eax, 0C000009Ah
0x14003133e  jmp     loc_14003158A
0x140031343  mov     qword ptr [rdi+8], 8
0x14003134b  lea     rax, [rbp+arg_0]
0x14003134f  mov     [rdi], rax
0x140031352  lea     rax, [rbp+arg_8]
0x140031356  mov     [rdi+10h], rax
0x14003135a  lea     rax, [rbp+arg_10]
0x14003135e  mov     [rdi+20h], rax
0x140031362  lea     rax, [rbp+arg_18]
0x140031366  mov     [rdi+30h], rax
0x14003136a  mov     qword ptr [rdi+18h], 4
0x140031372  mov     qword ptr [rdi+28h], 8
0x14003137a  mov     qword ptr [rdi+38h], 4
0x140031382  test    rbx, rbx
0x140031385  jz      short loc_140031398
0x140031387  mov     rcx, rbx; Sid
0x14003138a  call    cs:__imp_RtlLengthSid
0x140031391  nop     dword ptr [rax+rax+00h]
0x140031396  jmp     short loc_14003139A
0x140031398  mov     eax, esi
0x14003139a  mov     [rdi+40h], rbx
0x14003139e  mov     rbx, [rbp+Str]
0x1400313a2  mov     [rdi+48h], eax
0x1400313a5  lea     rax, [rbp+arg_28]
0x1400313a9  mov     [rdi+4Ch], esi
0x1400313ac  mov     [rdi+50h], rax
0x1400313b0  mov     qword ptr [rdi+58h], 4
0x1400313b8  test    rbx, rbx
0x1400313bb  jz      short loc_1400313CE
0x1400313bd  mov     rcx, rbx; Str
0x1400313c0  call    wcslen_0
0x1400313c5  lea     ecx, ds:2[rax*2]
0x1400313cc  jmp     short loc_1400313D3
0x1400313ce  mov     ecx, 2
0x1400313d3  test    rbx, rbx
0x1400313d6  mov     [rdi+68h], ecx
0x1400313d9  lea     rax, SourceString
0x1400313e0  mov     [rdi+6Ch], esi
0x1400313e3  cmovnz  rax, rbx
0x1400313e7  mov     qword ptr [rdi+78h], 4
0x1400313ef  mov     [rdi+60h], rax
0x1400313f3  lea     rdx, Event24; EventDescriptor
0x1400313fa  lea     rax, [rbp+arg_38]
0x1400313fe  mov     qword ptr [rdi+88h], 20h ; ' '
0x140031409  mov     [rdi+70h], rax
0x14003140d  mov     r9d, 16h; UserDataCount
0x140031413  mov     rax, [rbp+arg_40]
0x140031417  xor     r8d, r8d; ActivityId
0x14003141a  mov     [rdi+80h], rax
0x140031421  mov     rax, [rbp+arg_48]
0x140031428  mov     [rdi+90h], rax
0x14003142f  mov     rax, [rbp+arg_50]
0x140031436  mov     [rdi+0A0h], rax
0x14003143d  lea     rax, [rbp+arg_58]
0x140031444  mov     [rdi+0B0h], rax
0x14003144b  lea     rax, [rbp+arg_60]
0x140031452  mov     [rdi+0C0h], rax
0x140031459  lea     rax, [rbp+arg_68]
0x140031460  mov     [rdi+0D0h], rax
0x140031467  lea     rax, [rbp+arg_70]
0x14003146e  mov     [rdi+0E0h], rax
0x140031475  lea     rax, [rbp+arg_78]
0x14003147c  mov     [rdi+0F0h], rax
0x140031483  lea     rax, [rbp+arg_80]
0x14003148a  mov     [rdi+100h], rax
0x140031491  lea     rax, [rbp+arg_88]
0x140031498  mov     [rdi+110h], rax
0x14003149f  lea     rax, [rbp+arg_90]
0x1400314a6  mov     [rdi+120h], rax
0x1400314ad  lea     rax, [rbp+arg_98]
0x1400314b4  mov     [rdi+130h], rax
0x1400314bb  lea     rax, [rbp+arg_A0]
0x1400314c2  mov     [rdi+140h], rax
0x1400314c9  lea     rax, [rbp+arg_A8]
0x1400314d0  mov     [rdi+150h], rax
0x1400314d7  mov     qword ptr [rdi+98h], 14h
0x1400314e2  mov     qword ptr [rdi+0A8h], 10h
0x1400314ed  mov     qword ptr [rdi+0B8h], 4
0x1400314f8  mov     qword ptr [rdi+0C8h], 4
0x140031503  mov     qword ptr [rdi+0D8h], 4
0x14003150e  mov     qword ptr [rdi+0E8h], 4
0x140031519  mov     qword ptr [rdi+0F8h], 4
0x140031524  mov     qword ptr [rdi+108h], 4
0x14003152f  mov     qword ptr [rdi+118h], 4
0x14003153a  mov     qword ptr [rdi+128h], 8
0x140031545  mov     qword ptr [rdi+138h], 8
0x140031550  mov     qword ptr [rdi+148h], 8
0x14003155b  mov     qword ptr [rdi+158h], 40h ; '@'
0x140031566  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14003156d  mov     [rsp+38h+UserData], rdi; UserData
0x140031572  call    cs:__imp_EtwWrite
0x140031579  nop     dword ptr [rax+rax+00h]
0x14003157e  mov     rcx, rdi; ListEntry
0x140031581  mov     ebx, eax
0x140031583  call    SecReleaseEtwDescriptorBuffer
0x140031588  mov     eax, ebx
0x14003158a  add     rsp, 38h
0x14003158e  pop     r15
0x140031590  pop     r14
0x140031592  pop     rdi
0x140031593  pop     rsi
0x140031594  pop     rbx
0x140031595  pop     rbp
0x140031596  retn
```
