# RegSvcLogEvent

- ea: `0x180016c10`
- end: `0x180016cc9`
- name: `RegSvcLogEvent`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ad14`

## callees

- `0x180007740`
- `0x180016c10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180016cae`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180016cae`

## pseudocode

```c
ULONG __fastcall RegSvcLogEvent(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v4; // r9d
  int v5; // r8d
  __int64 v6; // rax
  ULONG result; // eax
  __int16 v8; // [rsp+20h] [rbp-60h] BYREF
  __int16 v9; // [rsp+24h] [rbp-5Ch] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-40h]
  int v12; // [rsp+48h] [rbp-38h]
  int v13; // [rsp+4Ch] [rbp-34h]
  __int16 *v14; // [rsp+50h] [rbp-30h]
  __int64 v15; // [rsp+58h] [rbp-28h]
  __int64 v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+68h] [rbp-18h]
  int v18; // [rsp+6Ch] [rbp-14h]

  if ( RegSvcEtwHandle )
  {
    v4 = *a3;
    v5 = *a2;
    v9 = (unsigned __int16)v4 >> 1;
    v8 = (unsigned __int16)v5 >> 1;
    UserData.Ptr = (ULONGLONG)&v8;
    v11 = *((_QWORD *)a2 + 1);
    v14 = &v9;
    v6 = *((_QWORD *)a3 + 1);
    v12 = v5;
    v17 = v4;
    v16 = v6;
    *(_QWORD *)&UserData.Size = 2;
    v13 = 0;
    v15 = 2;
    v18 = 0;
    return EventWrite(RegSvcEtwHandle, &REGSVC_ALLOWED_EXACT_PATH_EVENT, 4u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180016c10  push    rbp
0x180016c12  mov     rbp, rsp
0x180016c15  sub     rsp, 80h
0x180016c1c  mov     rax, cs:__security_cookie
0x180016c23  xor     rax, rsp
0x180016c26  mov     [rbp+var_10], rax
0x180016c2a  mov     rcx, cs:RegSvcEtwHandle; RegHandle
0x180016c31  mov     r10, r8
0x180016c34  test    rcx, rcx
0x180016c37  jz      short loc_180016CB4
0x180016c39  movzx   r9d, word ptr [r8]
0x180016c3d  movzx   r8d, word ptr [rdx]
0x180016c41  movzx   eax, r9w
0x180016c45  shr     ax, 1
0x180016c48  mov     [rbp+var_5C], ax
0x180016c4c  movzx   eax, r8w
0x180016c50  shr     ax, 1
0x180016c53  mov     [rbp+var_60], ax
0x180016c57  lea     rax, [rbp+var_60]
0x180016c5b  mov     [rbp+UserData.Ptr], rax
0x180016c5f  mov     rax, [rdx+8]
0x180016c63  lea     rdx, REGSVC_ALLOWED_EXACT_PATH_EVENT; EventDescriptor
0x180016c6a  mov     [rbp+var_40], rax
0x180016c6e  lea     rax, [rbp+var_5C]
0x180016c72  mov     [rbp+var_30], rax
0x180016c76  mov     rax, [r10+8]
0x180016c7a  mov     [rbp+var_38], r8d
0x180016c7e  mov     r8d, 4; UserDataCount
0x180016c84  mov     [rbp+var_18], r9d
0x180016c88  lea     r9, [rbp+UserData]; UserData
0x180016c8c  mov     [rbp+var_20], rax
0x180016c90  mov     qword ptr [rbp+UserData.Size], 2
0x180016c98  mov     [rbp+var_34], 0
0x180016c9f  mov     [rbp+var_28], 2
0x180016ca7  mov     [rbp+var_14], 0
0x180016cae  call    cs:__imp_EventWrite
0x180016cb4  mov     rcx, [rbp+var_10]
0x180016cb8  xor     rcx, rsp; StackCookie
0x180016cbb  call    __security_check_cookie
0x180016cc0  add     rsp, 80h
0x180016cc7  pop     rbp
0x180016cc8  retn
```
