# EventWriteDeleteValue

- ea: `0x140035e7c`
- end: `0x140036097`
- name: `EventWriteDeleteValue`
- size: `539`
- prototype: `__int64 __usercall@<rax>(ULONG64 Filter@<rcx>, char, PSID Sid, char, wchar_t *Str, wchar_t *, char, char, int, __int64, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140036860`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140035e7c`

## import_xrefs

- `ntoskrnl!EtwWriteEx` at `0x14003606d`
- `ntoskrnl!EtwWriteEx` at `0x14003606d`
- `ntoskrnl!RtlLengthSid` at `0x140035f0b`
- `ntoskrnl!RtlLengthSid` at `0x140035f0b`

## pseudocode

```c
__int64 EventWriteDeleteValue(
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
        ...)
{
  PSID v11; // rbx
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rdi
  ULONG v16; // eax
  int v17; // esi
  const wchar_t *v18; // rbx
  int v19; // ecx
  const WCHAR *v20; // r14
  const WCHAR *v21; // rax
  const wchar_t *v22; // rbx
  bool v23; // zf
  int v24; // eax
  __int64 v25; // rax
  int v26; // ecx
  unsigned int v27; // ebx
  __int64 v28; // [rsp+98h] [rbp+50h] BYREF
  int v29; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+60h] BYREF
  __int64 v31; // [rsp+E8h] [rbp+A0h] BYREF
  va_list va; // [rsp+E8h] [rbp+A0h]
  __int64 v33; // [rsp+F0h] [rbp+A8h]
  __int64 v34; // [rsp+F8h] [rbp+B0h] BYREF
  va_list va1; // [rsp+F8h] [rbp+B0h]
  va_list va2; // [rsp+100h] [rbp+B8h] BYREF

  va_start(va2, a11);
  va_start(va1, a11);
  va_start(va, a11);
  v31 = va_arg(va1, _QWORD);
  v33 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v34 = va_arg(va2, _QWORD);
  v30 = a4;
  v29 = a3;
  v28 = a2;
  v11 = Sid;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(14);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v28;
  EtwDescriptorBuffer[2] = &v29;
  EtwDescriptorBuffer[4] = &v30;
  EtwDescriptorBuffer[6] = &a5;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v11 )
    v16 = RtlLengthSid(v11);
  else
    v16 = 0;
  UserData[8] = v11;
  v17 = 2;
  v18 = Str;
  *((_DWORD *)UserData + 18) = v16;
  *((_DWORD *)UserData + 19) = 0;
  UserData[10] = &a7;
  UserData[11] = 4;
  if ( v18 )
    v19 = 2 * wcslen_0(v18) + 2;
  else
    v19 = 2;
  *((_DWORD *)UserData + 26) = v19;
  v20 = &SourceString;
  *((_DWORD *)UserData + 27) = 0;
  v21 = &SourceString;
  if ( v18 )
    v21 = v18;
  v22 = a9;
  UserData[12] = v21;
  v23 = v22 == 0;
  if ( v22 )
  {
    v24 = wcslen_0(v22);
    v23 = v22 == 0;
    v17 = 2 * v24 + 2;
  }
  if ( !v23 )
    v20 = v22;
  *((_DWORD *)UserData + 30) = v17;
  UserData[14] = v20;
  UserData[16] = &a10;
  *((_DWORD *)UserData + 31) = 0;
  UserData[18] = &a11;
  UserData[17] = 4;
  UserData[20] = va;
  v25 = v33;
  UserData[19] = 4;
  UserData[21] = 4;
  v26 = v31;
  UserData[22] = v25;
  UserData[24] = va1;
  UserData[26] = va2;
  *((_DWORD *)UserData + 46) = v26;
  *((_DWORD *)UserData + 47) = 0;
  UserData[25] = 8;
  UserData[27] = 1;
  v27 = EtwWriteEx(Microsoft_Windows_SECHandle, &Event16, Filter, 0, 0, 0, 0xEu, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v27;
}

```

## disassembly

```asm
0x140035e7c  mov     [rsp-40h+arg_18], r9
0x140035e81  mov     [rsp-40h+arg_10], r8d
0x140035e86  mov     [rsp-40h+arg_8], rdx
0x140035e8b  push    rbp
0x140035e8c  push    rbx
0x140035e8d  push    rsi
0x140035e8e  push    rdi
0x140035e8f  push    r12
0x140035e91  push    r13
0x140035e93  push    r14
0x140035e95  push    r15
0x140035e97  mov     rbp, rsp
0x140035e9a  sub     rsp, 48h
0x140035e9e  mov     rbx, [rbp+Sid]
0x140035ea2  mov     r15, rcx
0x140035ea5  mov     ecx, 0Eh
0x140035eaa  call    SecGetEtwDescriptorBuffer
0x140035eaf  xor     r12d, r12d
0x140035eb2  mov     rdi, rax
0x140035eb5  test    rax, rax
0x140035eb8  jnz     short loc_140035EC4
0x140035eba  mov     eax, 0C000009Ah
0x140035ebf  jmp     loc_140036085
0x140035ec4  mov     qword ptr [rdi+8], 8
0x140035ecc  lea     rax, [rbp+arg_8]
0x140035ed0  mov     [rdi], rax
0x140035ed3  lea     rax, [rbp+arg_10]
0x140035ed7  mov     [rdi+10h], rax
0x140035edb  lea     rax, [rbp+arg_18]
0x140035edf  mov     [rdi+20h], rax
0x140035ee3  lea     rax, [rbp+arg_20]
0x140035ee7  mov     [rdi+30h], rax
0x140035eeb  mov     qword ptr [rdi+18h], 4
0x140035ef3  mov     qword ptr [rdi+28h], 8
0x140035efb  mov     qword ptr [rdi+38h], 4
0x140035f03  test    rbx, rbx
0x140035f06  jz      short loc_140035F19
0x140035f08  mov     rcx, rbx; Sid
0x140035f0b  call    cs:__imp_RtlLengthSid
0x140035f12  nop     dword ptr [rax+rax+00h]
0x140035f17  jmp     short loc_140035F1C
0x140035f19  mov     eax, r12d
0x140035f1c  mov     [rdi+40h], rbx
0x140035f20  mov     esi, 2
0x140035f25  mov     rbx, [rbp+Str]
0x140035f2c  mov     [rdi+48h], eax
0x140035f2f  lea     rax, [rbp+arg_30]
0x140035f33  mov     [rdi+4Ch], r12d
0x140035f37  mov     [rdi+50h], rax
0x140035f3b  mov     qword ptr [rdi+58h], 4
0x140035f43  test    rbx, rbx
0x140035f46  jz      short loc_140035F59
0x140035f48  mov     rcx, rbx; Str
0x140035f4b  call    wcslen_0
0x140035f50  lea     ecx, ds:2[rax*2]
0x140035f57  jmp     short loc_140035F5B
0x140035f59  mov     ecx, esi
0x140035f5b  test    rbx, rbx
0x140035f5e  mov     [rdi+68h], ecx
0x140035f61  lea     r14, SourceString
0x140035f68  mov     [rdi+6Ch], r12d
0x140035f6c  mov     rax, r14
0x140035f6f  cmovnz  rax, rbx
0x140035f73  mov     rbx, [rbp+arg_40]
0x140035f7a  mov     [rdi+60h], rax
0x140035f7e  test    rbx, rbx
0x140035f81  jz      short loc_140035F95
0x140035f83  mov     rcx, rbx; Str
0x140035f86  call    wcslen_0
0x140035f8b  test    rbx, rbx
0x140035f8e  lea     esi, ds:2[rax*2]
0x140035f95  cmovnz  r14, rbx
0x140035f99  mov     [rdi+78h], esi
0x140035f9c  mov     [rdi+70h], r14
0x140035fa0  lea     rax, [rbp+arg_48]
0x140035fa7  mov     [rdi+80h], rax
0x140035fae  lea     rdx, Event16; EventDescriptor
0x140035fb5  mov     [rdi+7Ch], r12d
0x140035fb9  lea     rax, [rbp+arg_50]
0x140035fc0  mov     [rdi+90h], rax
0x140035fc7  xor     r9d, r9d; Flags
0x140035fca  mov     qword ptr [rdi+88h], 4
0x140035fd5  lea     rax, [rbp+arg_58]
0x140035fdc  mov     [rdi+0A0h], rax
0x140035fe3  mov     r8, r15; Filter
0x140035fe6  mov     rax, [rbp+arg_60]
0x140035fed  mov     qword ptr [rdi+98h], 4
0x140035ff8  mov     qword ptr [rdi+0A8h], 4
0x140036003  mov     ecx, dword ptr [rbp+arg_58]
0x140036009  mov     [rdi+0B0h], rax
0x140036010  lea     rax, [rbp+arg_68]
0x140036017  mov     [rdi+0C0h], rax
0x14003601e  lea     rax, [rbp+arg_70]
0x140036025  mov     [rsp+48h+UserData], rdi; UserData
0x14003602a  mov     [rdi+0D0h], rax
0x140036031  mov     [rdi+0B8h], ecx
0x140036037  mov     [rdi+0BCh], r12d
0x14003603e  mov     qword ptr [rdi+0C8h], 8
0x140036049  mov     qword ptr [rdi+0D8h], 1
0x140036054  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14003605b  mov     [rsp+48h+UserDataCount], 0Eh; UserDataCount
0x140036063  mov     [rsp+48h+RelatedActivityId], r12; RelatedActivityId
0x140036068  mov     [rsp+48h+ActivityId], r12; ActivityId
0x14003606d  call    cs:__imp_EtwWriteEx
0x140036074  nop     dword ptr [rax+rax+00h]
0x140036079  mov     rcx, rdi; ListEntry
0x14003607c  mov     ebx, eax
0x14003607e  call    SecReleaseEtwDescriptorBuffer
0x140036083  mov     eax, ebx
0x140036085  add     rsp, 48h
0x140036089  pop     r15
0x14003608b  pop     r14
0x14003608d  pop     r13
0x14003608f  pop     r12
0x140036091  pop     rdi
0x140036092  pop     rsi
0x140036093  pop     rbx
0x140036094  pop     rbp
0x140036095  retn
```
