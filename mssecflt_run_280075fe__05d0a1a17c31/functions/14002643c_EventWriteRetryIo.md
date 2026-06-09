# EventWriteRetryIo

- ea: `0x14002643c`
- end: `0x14002662f`
- name: `EventWriteRetryIo`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005d90`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140011650`
- `0x14002643c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400265f5`
- `ntoskrnl!EtwWrite` at `0x1400265f5`

## pseudocode

```c
PSLIST_ENTRY __fastcall EventWriteRetryIo(
        __int64 a1,
        const wchar_t *a2,
        unsigned __int8 a3,
        int a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        char a10,
        char a11,
        char a12,
        char a13,
        char a14,
        char a15)
{
  __int16 v16; // si
  PSLIST_ENTRY result; // rax
  PSLIST_ENTRY UserData; // rbx
  int v19; // eax
  __int16 v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+90h] [rbp+30h] BYREF
  int v25; // [rsp+A8h] [rbp+48h] BYREF

  v25 = a4;
  v24 = a1;
  v21 = a7;
  v22 = a8;
  v23 = a9;
  v16 = a3;
  result = SecGetEtwDescriptorBuffer(0xFu);
  UserData = result;
  if ( result )
  {
    *((_QWORD *)&result->Next + 1) = 8;
    result->Next = (struct _SLIST_ENTRY *)&v24;
    *((_QWORD *)&result[1].Next + 1) = 8;
    result[1].Next = (struct _SLIST_ENTRY *)&v21;
    result[2].Next = (struct _SLIST_ENTRY *)&v22;
    result[3].Next = (struct _SLIST_ENTRY *)&v23;
    result[4].Next = (struct _SLIST_ENTRY *)&a10;
    result[5].Next = (struct _SLIST_ENTRY *)&a11;
    result[6].Next = (struct _SLIST_ENTRY *)&a12;
    *((_QWORD *)&result[2].Next + 1) = 8;
    *((_QWORD *)&result[3].Next + 1) = 8;
    *((_QWORD *)&result[4].Next + 1) = 4;
    *((_QWORD *)&result[5].Next + 1) = 4;
    *((_QWORD *)&result[6].Next + 1) = 4;
    v19 = wcslen_0(a2);
    UserData[7].Next = (struct _SLIST_ENTRY *)a2;
    *((_DWORD *)&UserData[7].Next + 3) = 0;
    *((_QWORD *)&UserData[8].Next + 1) = 4;
    *((_QWORD *)&UserData[9].Next + 1) = 8;
    *((_DWORD *)&UserData[7].Next + 2) = 2 * v19 + 2;
    UserData[8].Next = (struct _SLIST_ENTRY *)&a13;
    UserData[9].Next = (struct _SLIST_ENTRY *)&a15;
    UserData[10].Next = (struct _SLIST_ENTRY *)&a14;
    *((_QWORD *)&UserData[10].Next + 1) = 8;
    v20 = v16;
    UserData[11].Next = (struct _SLIST_ENTRY *)&v20;
    UserData[12].Next = (struct _SLIST_ENTRY *)&v25;
    UserData[13].Next = (struct _SLIST_ENTRY *)&a5;
    UserData[14].Next = (struct _SLIST_ENTRY *)&a6;
    *((_QWORD *)&UserData[11].Next + 1) = 2;
    *((_QWORD *)&UserData[12].Next + 1) = 4;
    *((_QWORD *)&UserData[13].Next + 1) = 4;
    *((_QWORD *)&UserData[14].Next + 1) = 4;
    EtwWrite(Microsoft_Windows_SECHandle, &Event54, 0, 0xFu, (PEVENT_DATA_DESCRIPTOR)UserData);
    return (PSLIST_ENTRY)SecReleaseEtwDescriptorBuffer(UserData);
  }
  return result;
}

```

## disassembly

```asm
0x14002643c  mov     rax, rsp
0x14002643f  mov     [rax+10h], rbx
0x140026443  mov     [rax+18h], rsi
0x140026447  mov     [rax+20h], r9d
0x14002644b  mov     [rax+8], rcx
0x14002644f  push    rbp
0x140026450  push    rdi
0x140026451  push    r12
0x140026453  push    r14
0x140026455  push    r15
0x140026457  mov     rbp, rsp
0x14002645a  sub     rsp, 60h
0x14002645e  mov     rax, cs:__security_cookie
0x140026465  xor     rax, rsp
0x140026468  mov     [rbp+var_10], rax
0x14002646c  mov     rax, [rbp+arg_30]
0x140026470  mov     ecx, 0Fh
0x140026475  mov     [rbp+var_28], rax
0x140026479  mov     rdi, rdx
0x14002647c  mov     rax, [rbp+arg_38]
0x140026480  mov     [rbp+var_20], rax
0x140026484  mov     rax, [rbp+arg_40]
0x140026488  mov     [rbp+var_18], rax
0x14002648c  movzx   esi, r8b
0x140026490  call    SecGetEtwDescriptorBuffer
0x140026495  xor     r12d, r12d
0x140026498  mov     rbx, rax
0x14002649b  test    rax, rax
0x14002649e  jz      loc_140026609
0x1400264a4  lea     rax, [rbp+arg_0]
0x1400264a8  mov     qword ptr [rbx+8], 8
0x1400264b0  mov     [rbx], rax
0x1400264b3  mov     rcx, rdi; Str
0x1400264b6  lea     rax, [rbp+var_28]
0x1400264ba  mov     qword ptr [rbx+18h], 8
0x1400264c2  mov     [rbx+10h], rax
0x1400264c6  lea     rax, [rbp+var_20]
0x1400264ca  mov     [rbx+20h], rax
0x1400264ce  lea     rax, [rbp+var_18]
0x1400264d2  mov     [rbx+30h], rax
0x1400264d6  lea     rax, [rbp+arg_48]
0x1400264da  mov     [rbx+40h], rax
0x1400264de  lea     rax, [rbp+arg_50]
0x1400264e5  mov     [rbx+50h], rax
0x1400264e9  lea     rax, [rbp+arg_58]
0x1400264f0  mov     [rbx+60h], rax
0x1400264f4  mov     qword ptr [rbx+28h], 8
0x1400264fc  mov     qword ptr [rbx+38h], 8
0x140026504  mov     qword ptr [rbx+48h], 4
0x14002650c  mov     qword ptr [rbx+58h], 4
0x140026514  mov     qword ptr [rbx+68h], 4
0x14002651c  call    wcslen_0
0x140026521  mov     [rbx+70h], rdi
0x140026525  lea     r9d, [r12+0Fh]; UserDataCount
0x14002652a  mov     [rbx+7Ch], r12d
0x14002652e  lea     rdx, Event54; EventDescriptor
0x140026535  mov     qword ptr [rbx+88h], 4
0x140026540  xor     r8d, r8d; ActivityId
0x140026543  lea     eax, ds:2[rax*2]
0x14002654a  mov     qword ptr [rbx+98h], 8
0x140026555  mov     [rbx+78h], eax
0x140026558  lea     rax, [rbp+arg_60]
0x14002655f  mov     [rbx+80h], rax
0x140026566  lea     rax, [rbp+arg_70]
0x14002656d  mov     [rbx+90h], rax
0x140026574  lea     rax, [rbp+arg_68]
0x14002657b  mov     [rbx+0A0h], rax
0x140026582  lea     rax, [rbp+var_30]
0x140026586  mov     qword ptr [rbx+0A8h], 8
0x140026591  mov     [rbp+var_30], si
0x140026595  mov     [rbx+0B0h], rax
0x14002659c  lea     rax, [rbp+arg_18]
0x1400265a0  mov     [rbx+0C0h], rax
0x1400265a7  lea     rax, [rbp+arg_20]
0x1400265ab  mov     [rbx+0D0h], rax
0x1400265b2  lea     rax, [rbp+arg_28]
0x1400265b6  mov     [rbx+0E0h], rax
0x1400265bd  mov     qword ptr [rbx+0B8h], 2
0x1400265c8  mov     qword ptr [rbx+0C8h], 4
0x1400265d3  mov     qword ptr [rbx+0D8h], 4
0x1400265de  mov     qword ptr [rbx+0E8h], 4
0x1400265e9  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400265f0  mov     [rsp+60h+UserData], rbx; UserData
0x1400265f5  call    cs:__imp_EtwWrite
0x1400265fc  nop     dword ptr [rax+rax+00h]
0x140026601  mov     rcx, rbx; ListEntry
0x140026604  call    SecReleaseEtwDescriptorBuffer
0x140026609  mov     rcx, [rbp+var_10]
0x14002660d  xor     rcx, rsp; StackCookie
0x140026610  call    __security_check_cookie
0x140026615  lea     r11, [rsp+60h+var_s0]
0x14002661a  mov     rbx, [r11+38h]
0x14002661e  mov     rsi, [r11+40h]
0x140026622  mov     rsp, r11
0x140026625  pop     r15
0x140026627  pop     r14
0x140026629  pop     r12
0x14002662b  pop     rdi
0x14002662c  pop     rbp
0x14002662d  retn
```
