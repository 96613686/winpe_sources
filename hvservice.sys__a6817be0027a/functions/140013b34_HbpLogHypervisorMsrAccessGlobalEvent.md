# HbpLogHypervisorMsrAccessGlobalEvent

- ea: `0x140013b34`
- end: `0x140013c2c`
- name: `HbpLogHypervisorMsrAccessGlobalEvent`
- size: `248`
- prototype: `NTSTATUS __fastcall(int, char, __int64, __int16, char, char, char, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013dc4`

## callees

- `0x1400020f8`
- `0x140002ae0`
- `0x140013b34`

## pseudocode

```c
NTSTATUS __fastcall HbpLogHypervisorMsrAccessGlobalEvent(
        int a1,
        char a2,
        __int64 a3,
        __int16 a4,
        char a5,
        char a6,
        char a7,
        char a8,
        __int64 a9)
{
  __int64 v9; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-71h] BYREF
  char *v12; // [rsp+38h] [rbp-61h]
  __int64 v13; // [rsp+40h] [rbp-59h]
  __int64 *v14; // [rsp+48h] [rbp-51h]
  __int64 v15; // [rsp+50h] [rbp-49h]
  __int16 *v16; // [rsp+58h] [rbp-41h]
  __int64 v17; // [rsp+60h] [rbp-39h]
  char *v18; // [rsp+68h] [rbp-31h]
  __int64 v19; // [rsp+70h] [rbp-29h]
  char *v20; // [rsp+78h] [rbp-21h]
  __int64 v21; // [rsp+80h] [rbp-19h]
  char *v22; // [rsp+88h] [rbp-11h]
  __int64 v23; // [rsp+90h] [rbp-9h]
  char *v24; // [rsp+98h] [rbp-1h]
  __int64 v25; // [rsp+A0h] [rbp+7h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]
  int v27; // [rsp+B0h] [rbp+17h]
  int v28; // [rsp+B4h] [rbp+1Bh]
  int v29; // [rsp+D8h] [rbp+3Fh] BYREF
  char v30; // [rsp+E0h] [rbp+47h] BYREF
  __int64 v31; // [rsp+E8h] [rbp+4Fh] BYREF
  __int16 v32; // [rsp+F0h] [rbp+57h] BYREF

  v32 = a4;
  v31 = a3;
  v30 = a2;
  v29 = a1;
  UserData.Ptr = (ULONGLONG)&v29;
  *(_QWORD *)&UserData.Size = 4;
  v12 = &v30;
  v14 = &v31;
  v16 = &v32;
  v18 = &a5;
  v20 = &a6;
  v22 = &a7;
  v24 = &a8;
  v9 = -1;
  v13 = 1;
  v15 = 8;
  v17 = 2;
  v19 = 8;
  v21 = 8;
  v23 = 4;
  v25 = 4;
  v26 = a9;
  do
    ++v9;
  while ( *(_BYTE *)(a9 + v9) );
  v28 = 0;
  v27 = v9 + 1;
  return HbEvtpWriteEventLog(&HV_EVENTLOG_RESTRICTED_MSR_ACCESS, 9u, &UserData);
}

```

## disassembly

```asm
0x140013b34  mov     rax, rsp
0x140013b37  mov     [rax+20h], r9w
0x140013b3c  mov     [rax+18h], r8
0x140013b40  mov     [rax+10h], dl
0x140013b43  mov     [rax+8], ecx
0x140013b46  push    rbp
0x140013b47  lea     rbp, [rax-37h]
0x140013b4b  sub     rsp, 0C0h
0x140013b52  mov     rax, cs:__security_cookie
0x140013b59  xor     rax, rsp
0x140013b5c  mov     [rbp+2Fh+var_10], rax
0x140013b60  mov     rcx, [rbp+2Fh+arg_40]
0x140013b64  lea     rax, [rbp+2Fh+arg_0]
0x140013b68  mov     [rbp+2Fh+UserData.Ptr], rax
0x140013b6c  xor     r8d, r8d
0x140013b6f  lea     rax, [rbp+2Fh+arg_8]
0x140013b73  mov     qword ptr [rbp+2Fh+UserData.Size], 4
0x140013b7b  mov     [rbp+2Fh+var_90], rax
0x140013b7f  lea     rax, [rbp+2Fh+arg_10]
0x140013b83  mov     [rbp+2Fh+var_80], rax
0x140013b87  lea     rax, [rbp+2Fh+arg_18]
0x140013b8b  mov     [rbp+2Fh+var_70], rax
0x140013b8f  lea     rax, [rbp+2Fh+arg_20]
0x140013b93  mov     [rbp+2Fh+var_60], rax
0x140013b97  lea     rax, [rbp+2Fh+arg_28]
0x140013b9b  mov     [rbp+2Fh+var_50], rax
0x140013b9f  lea     rax, [rbp+2Fh+arg_30]
0x140013ba3  mov     [rbp+2Fh+var_40], rax
0x140013ba7  lea     rax, [rbp+2Fh+arg_38]
0x140013bab  mov     [rbp+2Fh+var_30], rax
0x140013baf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013bb3  mov     [rbp+2Fh+var_88], 1
0x140013bbb  mov     [rbp+2Fh+var_78], 8
0x140013bc3  mov     [rbp+2Fh+var_68], 2
0x140013bcb  mov     [rbp+2Fh+var_58], 8
0x140013bd3  mov     [rbp+2Fh+var_48], 8
0x140013bdb  mov     [rbp+2Fh+var_38], 4
0x140013be3  mov     [rbp+2Fh+var_28], 4
0x140013beb  mov     [rbp+2Fh+var_20], rcx
0x140013bef  inc     rax
0x140013bf2  cmp     [rcx+rax], r8b
0x140013bf6  jnz     short loc_140013BEF
0x140013bf8  inc     eax
0x140013bfa  mov     [rbp+2Fh+var_14], r8d
0x140013bfe  lea     r8, [rbp+2Fh+UserData]; UserData
0x140013c02  mov     [rbp+2Fh+var_18], eax
0x140013c05  mov     edx, 9; UserDataCount
0x140013c0a  lea     rcx, HV_EVENTLOG_RESTRICTED_MSR_ACCESS; EventDescriptor
0x140013c11  call    HbEvtpWriteEventLog
0x140013c16  mov     rcx, [rbp+2Fh+var_10]
0x140013c1a  xor     rcx, rsp; StackCookie
0x140013c1d  call    __security_check_cookie
0x140013c22  add     rsp, 0C0h
0x140013c29  pop     rbp
0x140013c2a  retn
```
