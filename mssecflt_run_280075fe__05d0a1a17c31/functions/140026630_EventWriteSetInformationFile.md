# EventWriteSetInformationFile

- ea: `0x140026630`
- end: `0x14002685c`
- name: `EventWriteSetInformationFile`
- size: `556`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char, char, wchar_t *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002792c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140026630`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140026832`
- `ntoskrnl!EtwWrite` at `0x140026832`
- `ntoskrnl!RtlLengthSid` at `0x1400266bf`
- `ntoskrnl!RtlLengthSid` at `0x1400266bf`

## pseudocode

```c
__int64 EventWriteSetInformationFile(
        PCEVENT_DESCRIPTOR EventDescriptor,
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
        char a12,
        wchar_t *a13,
        ...)
{
  PSID v13; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v18; // eax
  int v19; // esi
  const wchar_t *v20; // rbx
  int v21; // ecx
  const WCHAR *v22; // r14
  const WCHAR *v23; // rax
  const wchar_t *v24; // rbx
  int v25; // ecx
  const WCHAR *v26; // rax
  const wchar_t *v27; // rbx
  bool v28; // zf
  int v29; // eax
  __int64 v30; // rax
  int v31; // ecx
  unsigned int v32; // ebx
  __int64 v33; // [rsp+88h] [rbp+50h] BYREF
  int v34; // [rsp+90h] [rbp+58h] BYREF
  __int64 v35; // [rsp+98h] [rbp+60h] BYREF
  __int64 v36; // [rsp+E8h] [rbp+B0h] BYREF
  va_list va; // [rsp+E8h] [rbp+B0h]
  __int64 v38; // [rsp+F0h] [rbp+B8h]
  va_list va1; // [rsp+F8h] [rbp+C0h] BYREF

  va_start(va1, a13);
  va_start(va, a13);
  v36 = va_arg(va1, _QWORD);
  v38 = va_arg(va1, _QWORD);
  v35 = a4;
  v34 = a3;
  v33 = a2;
  v13 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(14);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v33;
  EtwDescriptorBuffer[2] = &v34;
  EtwDescriptorBuffer[4] = &v35;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v13 )
    v18 = RtlLengthSid(v13);
  else
    v18 = 0;
  UserData[8] = v13;
  v19 = 2;
  v20 = Str;
  *((_DWORD *)UserData + 18) = v18;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a7;
  UserData[11] = 4;
  if ( v20 )
    v21 = 2 * wcslen_0(v20) + 2;
  else
    v21 = 2;
  *((_DWORD *)UserData + 26) = v21;
  v22 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v23 = &SourceString;
  if ( v20 )
    v23 = v20;
  v24 = a9;
  UserData[12] = v23;
  if ( v24 )
    v25 = 2 * wcslen_0(v24) + 2;
  else
    v25 = 2;
  *((_DWORD *)UserData + 30) = v25;
  v26 = &SourceString;
  *((_DWORD *)UserData + 31) = 0;
  if ( v24 )
    v26 = v24;
  UserData[17] = 4;
  v27 = a13;
  UserData[14] = v26;
  UserData[16] = &a10;
  UserData[18] = &a11;
  UserData[20] = &a12;
  UserData[19] = 8;
  UserData[21] = 1;
  v28 = v27 == 0;
  if ( v27 )
  {
    v29 = wcslen_0(v27);
    v28 = v27 == 0;
    v19 = 2 * v29 + 2;
  }
  if ( !v28 )
    v22 = v27;
  *((_DWORD *)UserData + 46) = v19;
  UserData[22] = v22;
  UserData[24] = va;
  v30 = v38;
  *((_DWORD *)UserData + 47) = 0;
  UserData[25] = 4;
  v31 = v36;
  UserData[26] = v30;
  *((_DWORD *)UserData + 54) = v31;
  *((_DWORD *)UserData + 55) = 0;
  v32 = EtwWrite(Microsoft_Windows_SECHandle, EventDescriptor, 0, 0xEu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v32;
}

```

## disassembly

```asm
0x140026630  mov     [rsp-40h+arg_18], r9
0x140026635  mov     [rsp-40h+arg_10], r8d
0x14002663a  mov     [rsp-40h+arg_8], rdx
0x14002663f  push    rbp
0x140026640  push    rbx
0x140026641  push    rsi
0x140026642  push    rdi
0x140026643  push    r12
0x140026645  push    r13
0x140026647  push    r14
0x140026649  push    r15
0x14002664b  mov     rbp, rsp
0x14002664e  sub     rsp, 38h
0x140026652  mov     rbx, [rbp+Sid]
0x140026656  mov     r15, rcx
0x140026659  mov     ecx, 0Eh
0x14002665e  call    SecGetEtwDescriptorBuffer
0x140026663  xor     r12d, r12d
0x140026666  mov     rdi, rax
0x140026669  test    rax, rax
0x14002666c  jnz     short loc_140026678
0x14002666e  mov     eax, 0C000009Ah
0x140026673  jmp     loc_14002684A
0x140026678  mov     qword ptr [rdi+8], 8
0x140026680  lea     rax, [rbp+arg_8]
0x140026684  mov     [rdi], rax
0x140026687  lea     rax, [rbp+arg_10]
0x14002668b  mov     [rdi+10h], rax
0x14002668f  lea     rax, [rbp+arg_18]
0x140026693  mov     [rdi+20h], rax
0x140026697  lea     rax, [rbp+arg_20]
0x14002669b  mov     [rdi+30h], rax
0x14002669f  mov     qword ptr [rdi+18h], 4
0x1400266a7  mov     qword ptr [rdi+28h], 8
0x1400266af  mov     qword ptr [rdi+38h], 4
0x1400266b7  test    rbx, rbx
0x1400266ba  jz      short loc_1400266CD
0x1400266bc  mov     rcx, rbx; Sid
0x1400266bf  call    cs:__imp_RtlLengthSid
0x1400266c6  nop     dword ptr [rax+rax+00h]
0x1400266cb  jmp     short loc_1400266D0
0x1400266cd  mov     eax, r12d
0x1400266d0  mov     [rdi+40h], rbx
0x1400266d4  mov     esi, 2
0x1400266d9  mov     rbx, [rbp+Str]
0x1400266e0  mov     [rdi+48h], eax
0x1400266e3  lea     rax, [rbp+arg_30]
0x1400266e7  mov     [rdi+4Ch], r12d
0x1400266eb  mov     [rdi+50h], rax
0x1400266ef  mov     qword ptr [rdi+58h], 4
0x1400266f7  test    rbx, rbx
0x1400266fa  jz      short loc_14002670D
0x1400266fc  mov     rcx, rbx; Str
0x1400266ff  call    wcslen_0
0x140026704  lea     ecx, ds:2[rax*2]
0x14002670b  jmp     short loc_14002670F
0x14002670d  mov     ecx, esi
0x14002670f  test    rbx, rbx
0x140026712  mov     [rdi+68h], ecx
0x140026715  lea     r14, SourceString
0x14002671c  mov     [rdi+6Ch], r12d
0x140026720  mov     rax, r14
0x140026723  cmovnz  rax, rbx
0x140026727  mov     rbx, [rbp+arg_40]
0x14002672e  mov     [rdi+60h], rax
0x140026732  test    rbx, rbx
0x140026735  jz      short loc_140026748
0x140026737  mov     rcx, rbx; Str
0x14002673a  call    wcslen_0
0x14002673f  lea     ecx, ds:2[rax*2]
0x140026746  jmp     short loc_14002674A
0x140026748  mov     ecx, esi
0x14002674a  test    rbx, rbx
0x14002674d  mov     [rdi+78h], ecx
0x140026750  mov     rax, r14
0x140026753  mov     [rdi+7Ch], r12d
0x140026757  cmovnz  rax, rbx
0x14002675b  mov     qword ptr [rdi+88h], 4
0x140026766  mov     rbx, [rbp+arg_60]
0x14002676d  mov     [rdi+70h], rax
0x140026771  lea     rax, [rbp+arg_48]
0x140026778  mov     [rdi+80h], rax
0x14002677f  lea     rax, [rbp+arg_50]
0x140026786  mov     [rdi+90h], rax
0x14002678d  lea     rax, [rbp+arg_58]
0x140026794  mov     [rdi+0A0h], rax
0x14002679b  mov     qword ptr [rdi+98h], 8
0x1400267a6  mov     qword ptr [rdi+0A8h], 1
0x1400267b1  test    rbx, rbx
0x1400267b4  jz      short loc_1400267C8
0x1400267b6  mov     rcx, rbx; Str
0x1400267b9  call    wcslen_0
0x1400267be  test    rbx, rbx
0x1400267c1  lea     esi, ds:2[rax*2]
0x1400267c8  cmovnz  r14, rbx
0x1400267cc  mov     [rdi+0B8h], esi
0x1400267d2  mov     [rdi+0B0h], r14
0x1400267d9  lea     rax, [rbp+arg_68]
0x1400267e0  mov     [rdi+0C0h], rax
0x1400267e7  mov     r9d, 0Eh; UserDataCount
0x1400267ed  mov     rax, [rbp+arg_70]
0x1400267f4  xor     r8d, r8d; ActivityId
0x1400267f7  mov     [rdi+0BCh], r12d
0x1400267fe  mov     rdx, r15; EventDescriptor
0x140026801  mov     qword ptr [rdi+0C8h], 4
0x14002680c  mov     ecx, dword ptr [rbp+arg_68]
0x140026812  mov     [rdi+0D0h], rax
0x140026819  mov     [rdi+0D8h], ecx
0x14002681f  mov     [rdi+0DCh], r12d
0x140026826  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002682d  mov     [rsp+38h+UserData], rdi; UserData
0x140026832  call    cs:__imp_EtwWrite
0x140026839  nop     dword ptr [rax+rax+00h]
0x14002683e  mov     rcx, rdi; ListEntry
0x140026841  mov     ebx, eax
0x140026843  call    SecReleaseEtwDescriptorBuffer
0x140026848  mov     eax, ebx
0x14002684a  add     rsp, 38h
0x14002684e  pop     r15
0x140026850  pop     r14
0x140026852  pop     r13
0x140026854  pop     r12
0x140026856  pop     rdi
0x140026857  pop     rsi
0x140026858  pop     rbx
0x140026859  pop     rbp
0x14002685a  retn
```
