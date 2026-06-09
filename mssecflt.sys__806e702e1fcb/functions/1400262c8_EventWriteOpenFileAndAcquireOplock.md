# EventWriteOpenFileAndAcquireOplock

- ea: `0x1400262c8`
- end: `0x14002643c`
- name: `EventWriteOpenFileAndAcquireOplock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005980`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140011650`
- `0x1400262c8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14002640e`
- `ntoskrnl!EtwWrite` at `0x14002640e`

## pseudocode

```c
PSLIST_ENTRY __fastcall EventWriteOpenFileAndAcquireOplock(
        __int64 a1,
        const wchar_t *a2,
        int a3,
        int a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        char a11)
{
  PSLIST_ENTRY result; // rax
  PSLIST_ENTRY UserData; // rbx
  int v14; // eax
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+70h] [rbp+20h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF

  v20 = a4;
  v19 = a3;
  v18 = a1;
  v15 = a6;
  v16 = a7;
  v17 = a8;
  result = SecGetEtwDescriptorBuffer(0xBu);
  UserData = result;
  if ( result )
  {
    *((_QWORD *)&result->Next + 1) = 8;
    result->Next = (struct _SLIST_ENTRY *)&v18;
    *((_QWORD *)&result[1].Next + 1) = 8;
    result[1].Next = (struct _SLIST_ENTRY *)&v15;
    result[2].Next = (struct _SLIST_ENTRY *)&v16;
    result[3].Next = (struct _SLIST_ENTRY *)&v17;
    result[4].Next = (struct _SLIST_ENTRY *)&a9;
    result[5].Next = (struct _SLIST_ENTRY *)&a10;
    result[6].Next = (struct _SLIST_ENTRY *)&a11;
    *((_QWORD *)&result[2].Next + 1) = 8;
    *((_QWORD *)&result[3].Next + 1) = 8;
    *((_QWORD *)&result[4].Next + 1) = 4;
    *((_QWORD *)&result[5].Next + 1) = 4;
    *((_QWORD *)&result[6].Next + 1) = 4;
    v14 = wcslen_0(a2);
    UserData[7].Next = (struct _SLIST_ENTRY *)a2;
    *((_DWORD *)&UserData[7].Next + 3) = 0;
    *((_QWORD *)&UserData[8].Next + 1) = 4;
    *((_QWORD *)&UserData[9].Next + 1) = 4;
    *((_DWORD *)&UserData[7].Next + 2) = 2 * v14 + 2;
    UserData[8].Next = (struct _SLIST_ENTRY *)&v19;
    UserData[9].Next = (struct _SLIST_ENTRY *)&v20;
    UserData[10].Next = (struct _SLIST_ENTRY *)&a5;
    *((_QWORD *)&UserData[10].Next + 1) = 4;
    EtwWrite(Microsoft_Windows_SECHandle, &Event53, 0, 0xBu, (PEVENT_DATA_DESCRIPTOR)UserData);
    return (PSLIST_ENTRY)SecReleaseEtwDescriptorBuffer(UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1400262c8  mov     rax, rsp
0x1400262cb  mov     [rax+10h], rbx
0x1400262cf  mov     [rax+20h], r9d
0x1400262d3  mov     [rax+18h], r8d
0x1400262d7  mov     [rax+8], rcx
0x1400262db  push    rbp
0x1400262dc  push    rsi
0x1400262dd  push    rdi
0x1400262de  mov     rbp, rsp
0x1400262e1  sub     rsp, 50h
0x1400262e5  mov     rax, cs:__security_cookie
0x1400262ec  xor     rax, rsp
0x1400262ef  mov     [rbp+var_8], rax
0x1400262f3  mov     rax, [rbp+arg_28]
0x1400262f7  mov     ecx, 0Bh
0x1400262fc  mov     [rbp+var_20], rax
0x140026300  mov     rdi, rdx
0x140026303  mov     rax, [rbp+arg_30]
0x140026307  mov     [rbp+var_18], rax
0x14002630b  mov     rax, [rbp+arg_38]
0x14002630f  mov     [rbp+var_10], rax
0x140026313  call    SecGetEtwDescriptorBuffer
0x140026318  mov     rbx, rax
0x14002631b  test    rax, rax
0x14002631e  jz      loc_140026422
0x140026324  lea     rax, [rbp+arg_0]
0x140026328  mov     qword ptr [rbx+8], 8
0x140026330  mov     [rbx], rax
0x140026333  mov     rcx, rdi; Str
0x140026336  lea     rax, [rbp+var_20]
0x14002633a  mov     qword ptr [rbx+18h], 8
0x140026342  mov     [rbx+10h], rax
0x140026346  lea     rax, [rbp+var_18]
0x14002634a  mov     [rbx+20h], rax
0x14002634e  lea     rax, [rbp+var_10]
0x140026352  mov     [rbx+30h], rax
0x140026356  lea     rax, [rbp+arg_40]
0x14002635a  mov     [rbx+40h], rax
0x14002635e  lea     rax, [rbp+arg_48]
0x140026362  mov     [rbx+50h], rax
0x140026366  lea     rax, [rbp+arg_50]
0x14002636a  mov     [rbx+60h], rax
0x14002636e  mov     qword ptr [rbx+28h], 8
0x140026376  mov     qword ptr [rbx+38h], 8
0x14002637e  mov     qword ptr [rbx+48h], 4
0x140026386  mov     qword ptr [rbx+58h], 4
0x14002638e  mov     qword ptr [rbx+68h], 4
0x140026396  call    wcslen_0
0x14002639b  mov     [rbx+70h], rdi
0x14002639f  lea     rdx, Event53; EventDescriptor
0x1400263a6  mov     dword ptr [rbx+7Ch], 0
0x1400263ad  mov     r9d, 0Bh; UserDataCount
0x1400263b3  mov     qword ptr [rbx+88h], 4
0x1400263be  xor     r8d, r8d; ActivityId
0x1400263c1  lea     eax, ds:2[rax*2]
0x1400263c8  mov     qword ptr [rbx+98h], 4
0x1400263d3  mov     [rbx+78h], eax
0x1400263d6  lea     rax, [rbp+arg_10]
0x1400263da  mov     [rbx+80h], rax
0x1400263e1  lea     rax, [rbp+arg_18]
0x1400263e5  mov     [rbx+90h], rax
0x1400263ec  lea     rax, [rbp+arg_20]
0x1400263f0  mov     [rbx+0A0h], rax
0x1400263f7  mov     qword ptr [rbx+0A8h], 4
0x140026402  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140026409  mov     [rsp+50h+UserData], rbx; UserData
0x14002640e  call    cs:__imp_EtwWrite
0x140026415  nop     dword ptr [rax+rax+00h]
0x14002641a  mov     rcx, rbx; ListEntry
0x14002641d  call    SecReleaseEtwDescriptorBuffer
0x140026422  mov     rcx, [rbp+var_8]
0x140026426  xor     rcx, rsp; StackCookie
0x140026429  call    __security_check_cookie
0x14002642e  mov     rbx, [rsp+50h+arg_8]
0x140026433  add     rsp, 50h
0x140026437  pop     rdi
0x140026438  pop     rsi
0x140026439  pop     rbp
0x14002643a  retn
```
