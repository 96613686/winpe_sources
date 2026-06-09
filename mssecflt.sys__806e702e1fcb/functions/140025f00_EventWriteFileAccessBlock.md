# EventWriteFileAccessBlock

- ea: `0x140025f00`
- end: `0x1400260b8`
- name: `EventWriteFileAccessBlock`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140026a80`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140025f00`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140026094`
- `ntoskrnl!EtwWrite` at `0x140026094`
- `ntoskrnl!RtlLengthSid` at `0x140025fd6`
- `ntoskrnl!RtlLengthSid` at `0x140025fd6`

## pseudocode

```c
_QWORD *EventWriteFileAccessBlock(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3, ...)
{
  PSID v3; // rsi
  _QWORD *result; // rax
  _QWORD *UserData; // rbx
  wchar_t *v7; // rdi
  int v8; // r14d
  int v9; // ecx
  const WCHAR *v10; // r15
  const WCHAR *v11; // rax
  ULONG v12; // eax
  wchar_t *v13; // rdi
  bool v14; // zf
  int v15; // eax
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF
  int v19; // [rsp+80h] [rbp+50h] BYREF
  __int64 v20; // [rsp+88h] [rbp+58h] BYREF
  va_list va; // [rsp+88h] [rbp+58h]
  __int64 v22; // [rsp+90h] [rbp+60h] BYREF
  va_list va1; // [rsp+90h] [rbp+60h]
  wchar_t *Str; // [rsp+98h] [rbp+68h]
  __int64 v25; // [rsp+A0h] [rbp+70h] BYREF
  va_list va2; // [rsp+A0h] [rbp+70h]
  PSID Sid; // [rsp+A8h] [rbp+78h]
  wchar_t *v28; // [rsp+B0h] [rbp+80h]
  __int64 v29; // [rsp+B8h] [rbp+88h] BYREF
  va_list va3; // [rsp+B8h] [rbp+88h]
  __int64 v31; // [rsp+C0h] [rbp+90h]
  va_list va4; // [rsp+C8h] [rbp+98h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v20 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v22 = va_arg(va2, _QWORD);
  Str = va_arg(va2, wchar_t *);
  va_copy(va3, va2);
  v25 = va_arg(va3, _QWORD);
  Sid = va_arg(va3, PSID);
  v28 = va_arg(va3, wchar_t *);
  va_copy(va4, va3);
  v29 = va_arg(va4, _QWORD);
  v31 = va_arg(va4, _QWORD);
  v19 = a3;
  v18 = a1;
  v3 = Sid;
  result = (_QWORD *)SecGetEtwDescriptorBuffer(11);
  UserData = result;
  if ( result )
  {
    v7 = Str;
    *result = &v18;
    result[2] = &v19;
    result[4] = va;
    result[6] = va1;
    v8 = 2;
    result[1] = 8;
    result[3] = 4;
    result[5] = 8;
    result[7] = 8;
    if ( v7 )
      v9 = 2 * wcslen_0(v7) + 2;
    else
      v9 = 2;
    *((_DWORD *)UserData + 18) = v9;
    v10 = &SourceString;
    *((_DWORD *)UserData + 19) = 0;
    v11 = &SourceString;
    UserData[11] = 4;
    if ( v7 )
      v11 = v7;
    UserData[8] = v11;
    UserData[10] = va2;
    if ( v3 )
      v12 = RtlLengthSid(v3);
    else
      v12 = 0;
    v13 = v28;
    UserData[12] = v3;
    *((_DWORD *)UserData + 26) = v12;
    *((_DWORD *)UserData + 27) = 0;
    v14 = v13 == 0;
    if ( v13 )
    {
      v15 = wcslen_0(v13);
      v14 = v13 == 0;
      v8 = 2 * v15 + 2;
    }
    if ( !v14 )
      v10 = v13;
    *((_DWORD *)UserData + 30) = v8;
    UserData[14] = v10;
    UserData[16] = va3;
    v16 = v31;
    *((_DWORD *)UserData + 31) = 0;
    UserData[17] = 4;
    v17 = v29;
    UserData[18] = v16;
    UserData[20] = va4;
    *((_DWORD *)UserData + 38) = v17;
    *((_DWORD *)UserData + 39) = 0;
    UserData[21] = 4;
    EtwWrite(Microsoft_Windows_SECHandle, a2, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
    return (_QWORD *)SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140025f00  mov     [rsp-38h+arg_18], r9
0x140025f05  mov     [rsp-38h+arg_10], r8d
0x140025f0a  mov     [rsp-38h+arg_0], rcx
0x140025f0f  push    rbp
0x140025f10  push    rbx
0x140025f11  push    rsi
0x140025f12  push    rdi
0x140025f13  push    r12
0x140025f15  push    r14
0x140025f17  push    r15
0x140025f19  mov     rbp, rsp
0x140025f1c  sub     rsp, 30h
0x140025f20  mov     rsi, [rbp+Sid]
0x140025f24  mov     ecx, 0Bh
0x140025f29  mov     r12, rdx
0x140025f2c  call    SecGetEtwDescriptorBuffer
0x140025f31  mov     rbx, rax
0x140025f34  test    rax, rax
0x140025f37  jz      loc_1400260A8
0x140025f3d  mov     rdi, [rbp+Str]
0x140025f41  lea     rax, [rbp+arg_0]
0x140025f45  mov     [rbx], rax
0x140025f48  lea     rax, [rbp+arg_10]
0x140025f4c  mov     [rbx+10h], rax
0x140025f50  lea     rax, [rbp+arg_18]
0x140025f54  mov     [rbx+20h], rax
0x140025f58  lea     rax, [rbp+arg_20]
0x140025f5c  mov     [rbx+30h], rax
0x140025f60  mov     r14d, 2
0x140025f66  mov     qword ptr [rbx+8], 8
0x140025f6e  mov     qword ptr [rbx+18h], 4
0x140025f76  mov     qword ptr [rbx+28h], 8
0x140025f7e  mov     qword ptr [rbx+38h], 8
0x140025f86  test    rdi, rdi
0x140025f89  jz      short loc_140025F9C
0x140025f8b  mov     rcx, rdi; Str
0x140025f8e  call    wcslen_0
0x140025f93  lea     ecx, ds:2[rax*2]
0x140025f9a  jmp     short loc_140025F9F
0x140025f9c  mov     ecx, r14d
0x140025f9f  test    rdi, rdi
0x140025fa2  mov     [rbx+48h], ecx
0x140025fa5  lea     r15, SourceString
0x140025fac  mov     dword ptr [rbx+4Ch], 0
0x140025fb3  mov     rax, r15
0x140025fb6  mov     qword ptr [rbx+58h], 4
0x140025fbe  cmovnz  rax, rdi
0x140025fc2  mov     [rbx+40h], rax
0x140025fc6  lea     rax, [rbp+arg_30]
0x140025fca  mov     [rbx+50h], rax
0x140025fce  test    rsi, rsi
0x140025fd1  jz      short loc_140025FE4
0x140025fd3  mov     rcx, rsi; Sid
0x140025fd6  call    cs:__imp_RtlLengthSid
0x140025fdd  nop     dword ptr [rax+rax+00h]
0x140025fe2  jmp     short loc_140025FE6
0x140025fe4  xor     eax, eax
0x140025fe6  mov     rdi, [rbp+arg_40]
0x140025fed  mov     [rbx+60h], rsi
0x140025ff1  mov     [rbx+68h], eax
0x140025ff4  mov     dword ptr [rbx+6Ch], 0
0x140025ffb  test    rdi, rdi
0x140025ffe  jz      short loc_140026013
0x140026000  mov     rcx, rdi; Str
0x140026003  call    wcslen_0
0x140026008  test    rdi, rdi
0x14002600b  lea     r14d, ds:2[rax*2]
0x140026013  cmovnz  r15, rdi
0x140026017  mov     [rbx+78h], r14d
0x14002601b  mov     [rbx+70h], r15
0x14002601f  lea     rax, [rbp+arg_48]
0x140026026  mov     [rbx+80h], rax
0x14002602d  mov     r9d, 0Bh; UserDataCount
0x140026033  mov     rax, [rbp+arg_50]
0x14002603a  xor     r8d, r8d; ActivityId
0x14002603d  mov     dword ptr [rbx+7Ch], 0
0x140026044  mov     rdx, r12; EventDescriptor
0x140026047  mov     qword ptr [rbx+88h], 4
0x140026052  mov     ecx, dword ptr [rbp+arg_48]
0x140026058  mov     [rbx+90h], rax
0x14002605f  lea     rax, [rbp+arg_58]
0x140026066  mov     [rbx+0A0h], rax
0x14002606d  mov     [rbx+98h], ecx
0x140026073  mov     dword ptr [rbx+9Ch], 0
0x14002607d  mov     qword ptr [rbx+0A8h], 4
0x140026088  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14002608f  mov     [rsp+30h+UserData], rbx; UserData
0x140026094  call    cs:__imp_EtwWrite
0x14002609b  nop     dword ptr [rax+rax+00h]
0x1400260a0  mov     rcx, rbx; ListEntry
0x1400260a3  call    SecReleaseEtwDescriptorBuffer
0x1400260a8  add     rsp, 30h
0x1400260ac  pop     r15
0x1400260ae  pop     r14
0x1400260b0  pop     r12
0x1400260b2  pop     rdi
0x1400260b3  pop     rsi
0x1400260b4  pop     rbx
0x1400260b5  pop     rbp
0x1400260b6  retn
```
