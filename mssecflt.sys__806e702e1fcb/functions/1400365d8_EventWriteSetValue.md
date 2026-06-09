# EventWriteSetValue

- ea: `0x1400365d8`
- end: `0x14003685f`
- name: `EventWriteSetValue`
- size: `647`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char, int, __int64, char, char, int, __int64, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038164`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x1400365d8`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x140036835`
- `ntoskrnl!EtwWriteEx` at `0x140036835`
- `ntoskrnl!RtlLengthSid` at `0x140036667`
- `ntoskrnl!RtlLengthSid` at `0x140036667`

## pseudocode

```c
__int64 EventWriteSetValue(
        ULONG64 Filter,
        __int64 a2,
        int a3,
        __int64 a4,
        char a5,
        PSID Sid,
        char a7,
        wchar_t *Str,
        wchar_t *a9,
        char a10,
        char a11,
        int a12,
        __int64 a13,
        char a14,
        char a15,
        ...)
{
  PSID v15; // rbx
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
  __int64 v31; // rax
  int v32; // ecx
  unsigned int v33; // ebx
  __int64 v34; // [rsp+98h] [rbp+50h] BYREF
  int v35; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v36; // [rsp+A8h] [rbp+60h] BYREF
  __int64 v37; // [rsp+108h] [rbp+C0h] BYREF
  va_list va; // [rsp+108h] [rbp+C0h]
  __int64 v39; // [rsp+110h] [rbp+C8h]
  __int64 v40; // [rsp+118h] [rbp+D0h] BYREF
  va_list va1; // [rsp+118h] [rbp+D0h]
  va_list va2; // [rsp+120h] [rbp+D8h] BYREF

  va_start(va2, a15);
  va_start(va1, a15);
  va_start(va, a15);
  v37 = va_arg(va1, _QWORD);
  v39 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v40 = va_arg(va2, _QWORD);
  v36 = a4;
  v35 = a3;
  v34 = a2;
  v15 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(18);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v34;
  EtwDescriptorBuffer[2] = &v35;
  EtwDescriptorBuffer[4] = &v36;
  EtwDescriptorBuffer[6] = &a5;
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
  UserData[10] = &a7;
  UserData[11] = 4;
  if ( v22 )
    v23 = 2 * wcslen_0(v22) + 2;
  else
    v23 = 2;
  *((_DWORD *)UserData + 26) = v23;
  v24 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v25 = &SourceString;
  if ( v22 )
    v25 = v22;
  v26 = a9;
  UserData[12] = v25;
  v27 = v26 == 0;
  if ( v26 )
  {
    v28 = wcslen_0(v26);
    v27 = v26 == 0;
    v21 = 2 * v28 + 2;
  }
  *((_DWORD *)UserData + 30) = v21;
  UserData[16] = &a10;
  *((_DWORD *)UserData + 31) = 0;
  UserData[18] = &a11;
  if ( !v27 )
    v24 = v26;
  UserData[14] = v24;
  UserData[20] = &a12;
  v29 = a13;
  UserData[17] = 4;
  UserData[19] = 4;
  UserData[21] = 4;
  v30 = a12;
  UserData[22] = v29;
  UserData[24] = &a14;
  UserData[26] = &a15;
  UserData[28] = va;
  v31 = v39;
  *((_DWORD *)UserData + 46) = v30;
  *((_DWORD *)UserData + 47) = 0;
  UserData[25] = 4;
  UserData[27] = 4;
  UserData[29] = 4;
  v32 = v37;
  UserData[30] = v31;
  UserData[32] = va1;
  UserData[34] = va2;
  *((_DWORD *)UserData + 62) = v32;
  *((_DWORD *)UserData + 63) = 0;
  UserData[33] = 8;
  UserData[35] = 1;
  v33 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event13, Filter, 0, 0, 0, 0x12u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v33;
}

```

## disassembly

```asm
0x1400365d8  mov     [rsp-40h+arg_18], r9
0x1400365dd  mov     [rsp-40h+arg_10], r8d
0x1400365e2  mov     [rsp-40h+arg_8], rdx
0x1400365e7  push    rbp
0x1400365e8  push    rbx
0x1400365e9  push    rsi
0x1400365ea  push    rdi
0x1400365eb  push    r12
0x1400365ed  push    r13
0x1400365ef  push    r14
0x1400365f1  push    r15
0x1400365f3  mov     rbp, rsp
0x1400365f6  sub     rsp, 48h
0x1400365fa  mov     rbx, [rbp+Sid]
0x1400365fe  mov     r15, rcx
0x140036601  mov     ecx, 12h
0x140036606  call    SecGetEtwDescriptorBuffer
0x14003660b  xor     r12d, r12d
0x14003660e  mov     rdi, rax
0x140036611  test    rax, rax
0x140036614  jnz     short loc_140036620
0x140036616  mov     eax, 0C000009Ah
0x14003661b  jmp     loc_14003684D
0x140036620  mov     qword ptr [rdi+8], 8
0x140036628  lea     rax, [rbp+arg_8]
0x14003662c  mov     [rdi], rax
0x14003662f  lea     rax, [rbp+arg_10]
0x140036633  mov     [rdi+10h], rax
0x140036637  lea     rax, [rbp+arg_18]
0x14003663b  mov     [rdi+20h], rax
0x14003663f  lea     rax, [rbp+arg_20]
0x140036643  mov     [rdi+30h], rax
0x140036647  mov     qword ptr [rdi+18h], 4
0x14003664f  mov     qword ptr [rdi+28h], 8
0x140036657  mov     qword ptr [rdi+38h], 4
0x14003665f  test    rbx, rbx
0x140036662  jz      short loc_140036675
0x140036664  mov     rcx, rbx; Sid
0x140036667  call    cs:__imp_RtlLengthSid
0x14003666e  nop     dword ptr [rax+rax+00h]
0x140036673  jmp     short loc_140036678
0x140036675  mov     eax, r12d
0x140036678  mov     [rdi+40h], rbx
0x14003667c  mov     esi, 2
0x140036681  mov     rbx, [rbp+Str]
0x140036688  mov     [rdi+48h], eax
0x14003668b  lea     rax, [rbp+arg_30]
0x14003668f  mov     [rdi+4Ch], r12d
0x140036693  mov     [rdi+50h], rax
0x140036697  mov     qword ptr [rdi+58h], 4
0x14003669f  test    rbx, rbx
0x1400366a2  jz      short loc_1400366B5
0x1400366a4  mov     rcx, rbx; Str
0x1400366a7  call    wcslen_0
0x1400366ac  lea     ecx, ds:2[rax*2]
0x1400366b3  jmp     short loc_1400366B7
0x1400366b5  mov     ecx, esi
0x1400366b7  test    rbx, rbx
0x1400366ba  mov     [rdi+68h], ecx
0x1400366bd  lea     r14, SourceString
0x1400366c4  mov     [rdi+6Ch], r12d
0x1400366c8  mov     rax, r14
0x1400366cb  cmovnz  rax, rbx
0x1400366cf  mov     rbx, [rbp+arg_40]
0x1400366d6  mov     [rdi+60h], rax
0x1400366da  test    rbx, rbx
0x1400366dd  jz      short loc_1400366F1
0x1400366df  mov     rcx, rbx; Str
0x1400366e2  call    wcslen_0
0x1400366e7  test    rbx, rbx
0x1400366ea  lea     esi, ds:2[rax*2]
0x1400366f1  mov     [rdi+78h], esi
0x1400366f4  lea     rax, [rbp+arg_48]
0x1400366fb  mov     [rdi+80h], rax
0x140036702  lea     rdx, Event13; EventDescriptor
0x140036709  mov     [rdi+7Ch], r12d
0x14003670d  lea     rax, [rbp+arg_50]
0x140036714  mov     [rdi+90h], rax
0x14003671b  cmovnz  r14, rbx
0x14003671f  mov     [rdi+70h], r14
0x140036723  lea     rax, [rbp+arg_58]
0x14003672a  mov     [rdi+0A0h], rax
0x140036731  xor     r9d, r9d; Flags
0x140036734  mov     rax, [rbp+arg_60]
0x14003673b  mov     r8, r15; Filter
0x14003673e  mov     qword ptr [rdi+88h], 4
0x140036749  mov     qword ptr [rdi+98h], 4
0x140036754  mov     qword ptr [rdi+0A8h], 4
0x14003675f  mov     ecx, [rbp+arg_58]
0x140036765  mov     [rdi+0B0h], rax
0x14003676c  lea     rax, [rbp+arg_68]
0x140036773  mov     [rdi+0C0h], rax
0x14003677a  lea     rax, [rbp+arg_70]
0x140036781  mov     [rdi+0D0h], rax
0x140036788  lea     rax, [rbp+arg_78]
0x14003678f  mov     [rdi+0E0h], rax
0x140036796  mov     rax, [rbp+arg_80]
0x14003679d  mov     [rdi+0B8h], ecx
0x1400367a3  mov     [rdi+0BCh], r12d
0x1400367aa  mov     qword ptr [rdi+0C8h], 4
0x1400367b5  mov     qword ptr [rdi+0D8h], 4
0x1400367c0  mov     qword ptr [rdi+0E8h], 4
0x1400367cb  mov     ecx, dword ptr [rbp+arg_78]
0x1400367d1  mov     [rdi+0F0h], rax
0x1400367d8  lea     rax, [rbp+arg_88]
0x1400367df  mov     [rdi+100h], rax
0x1400367e6  lea     rax, [rbp+arg_90]
0x1400367ed  mov     [rsp+48h+UserData], rdi; UserData
0x1400367f2  mov     [rdi+110h], rax
0x1400367f9  mov     [rdi+0F8h], ecx
0x1400367ff  mov     [rdi+0FCh], r12d
0x140036806  mov     qword ptr [rdi+108h], 8
0x140036811  mov     qword ptr [rdi+118h], 1
0x14003681c  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140036823  mov     [rsp+48h+UserDataCount], 12h; UserDataCount
0x14003682b  mov     [rsp+48h+RelatedActivityId], r12; RelatedActivityId
0x140036830  mov     [rsp+48h+ActivityId], r12; ActivityId
0x140036835  call    cs:__imp_EtwWriteEx
0x14003683c  nop     dword ptr [rax+rax+00h]
0x140036841  mov     rcx, rdi; ListEntry
0x140036844  mov     ebx, eax
0x140036846  call    SecReleaseEtwDescriptorBuffer
0x14003684b  mov     eax, ebx
0x14003684d  add     rsp, 48h
0x140036851  pop     r15
0x140036853  pop     r14
0x140036855  pop     r13
0x140036857  pop     r12
0x140036859  pop     rdi
0x14003685a  pop     rsi
0x14003685b  pop     rbx
0x14003685c  pop     rbp
0x14003685d  retn
```
