# CoTemplate_qcsh

- ea: `0x14000f1b8`
- end: `0x14000f26d`
- name: `CoTemplate_qcsh`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f8e0`

## callees

- `0x14000f1b8`
- `0x140013200`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14000f255`
- `ADVAPI32!EventWrite` at `0x14000f255`

## pseudocode

```c
ULONG __fastcall CoTemplate_qcsh(__int64 a1, __int64 a2, int a3, char a4, const char *a5, char a6)
{
  __int64 v6; // rcx
  int v7; // ecx
  const char *v8; // rax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-50h] BYREF
  char *v11; // [rsp+30h] [rbp-40h]
  __int64 v12; // [rsp+38h] [rbp-38h]
  const char *v13; // [rsp+40h] [rbp-30h]
  int v14; // [rsp+48h] [rbp-28h]
  int v15; // [rsp+4Ch] [rbp-24h]
  char *v16; // [rsp+50h] [rbp-20h]
  __int64 v17; // [rsp+58h] [rbp-18h]
  int v18; // [rsp+90h] [rbp+20h] BYREF
  char v19; // [rsp+98h] [rbp+28h] BYREF

  v19 = a4;
  v18 = a3;
  UserData.Ptr = (ULONGLONG)&v18;
  v12 = 1;
  v11 = &v19;
  *(_QWORD *)&UserData.Size = 4;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  v14 = v7;
  v15 = 0;
  v8 = "NULL";
  if ( a5 )
    v8 = a5;
  v17 = 2;
  v13 = v8;
  v16 = &a6;
  return EventWrite(0, &StressLogEvent_V1, 4u, &UserData);
}

```

## disassembly

```asm
0x14000f1b8  mov     [rsp-8+arg_18], r9b
0x14000f1bd  mov     [rsp-8+arg_10], r8d
0x14000f1c2  push    rbp
0x14000f1c3  mov     rbp, rsp
0x14000f1c6  sub     rsp, 70h
0x14000f1ca  mov     rax, cs:__security_cookie
0x14000f1d1  xor     rax, rsp
0x14000f1d4  mov     [rbp+var_10], rax
0x14000f1d8  mov     rdx, [rbp+arg_20]
0x14000f1dc  lea     rax, [rbp+arg_10]
0x14000f1e0  mov     [rbp+UserData.Ptr], rax
0x14000f1e4  xor     r8d, r8d
0x14000f1e7  mov     [rbp+var_38], 1
0x14000f1ef  lea     rax, [rbp+arg_18]
0x14000f1f3  mov     [rbp+var_40], rax
0x14000f1f7  mov     r10d, 4
0x14000f1fd  mov     qword ptr [rbp+UserData.Size], r10
0x14000f201  test    rdx, rdx
0x14000f204  jz      short loc_14000F217
0x14000f206  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f20a  inc     rcx
0x14000f20d  cmp     [rdx+rcx], r8b
0x14000f211  jnz     short loc_14000F20A
0x14000f213  inc     ecx
0x14000f215  jmp     short loc_14000F21C
0x14000f217  mov     ecx, 5
0x14000f21c  test    rdx, rdx
0x14000f21f  mov     [rbp+var_28], ecx
0x14000f222  mov     [rbp+var_24], r8d
0x14000f226  lea     rax, aNull; "NULL"
0x14000f22d  cmovnz  rax, rdx
0x14000f231  mov     [rbp+var_18], 2
0x14000f239  mov     [rbp+var_30], rax
0x14000f23d  lea     r9, [rbp+UserData]; UserData
0x14000f241  lea     rax, [rbp+arg_28]
0x14000f245  mov     r8d, r10d; UserDataCount
0x14000f248  lea     rdx, StressLogEvent_V1; EventDescriptor
0x14000f24f  mov     [rbp+var_20], rax
0x14000f253  xor     ecx, ecx; RegHandle
0x14000f255  call    cs:__imp_EventWrite
0x14000f25b  mov     rcx, [rbp+var_10]
0x14000f25f  xor     rcx, rsp; StackCookie
0x14000f262  call    __security_check_cookie
0x14000f267  add     rsp, 70h
0x14000f26b  pop     rbp
0x14000f26c  retn
```
