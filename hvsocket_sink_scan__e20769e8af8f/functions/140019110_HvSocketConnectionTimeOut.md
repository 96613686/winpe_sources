# HvSocketConnectionTimeOut

- ea: `0x140019110`
- end: `0x140019261`
- name: `HvSocketConnectionTimeOut`
- size: `337`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005280`

## callees

- `0x140001008`
- `0x140001ac8`
- `0x140001fa0`
- `0x1400023b0`
- `0x14000bfa0`
- `0x140019110`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140019165`
- `ntoskrnl!PsGetProcessId` at `0x140019165`

## pseudocode

```c
char __fastcall HvSocketConnectionTimeOut(_DWORD *P)
{
  int v1; // edi
  char result; // al
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // edi
  struct _KPROCESS *v7; // rcx
  unsigned int ProcessId; // eax
  bool v9; // al
  bool v10; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-29h] BYREF
  const char *v13; // [rsp+60h] [rbp-9h]
  __int64 v14; // [rsp+68h] [rbp-1h]
  __int64 *v15; // [rsp+70h] [rbp+7h]
  __int64 v16; // [rsp+78h] [rbp+Fh]
  char *v17; // [rsp+80h] [rbp+17h]
  __int64 v18; // [rsp+88h] [rbp+1Fh]
  char *v19; // [rsp+90h] [rbp+27h]
  __int64 v20; // [rsp+98h] [rbp+2Fh]
  bool *v21; // [rsp+A0h] [rbp+37h]
  __int64 v22; // [rsp+A8h] [rbp+3Fh]

  v1 = P[129];
  result = HvSocketBeginProcessingConnection(P);
  if ( result )
  {
    P[129] |= 1u;
    v6 = v1 & 0x30;
    v7 = (struct _KPROCESS *)*((_QWORD *)P + 34);
    if ( v7 )
      ProcessId = (unsigned int)PsGetProcessId(v7);
    else
      ProcessId = 0;
    if ( (unsigned int)dword_140013058 > 3 )
    {
      v11 = ProcessId;
      v13 = "A Hyper-V socket connection has timed out.";
      v15 = &v11;
      v14 = 43;
      v17 = (char *)(P + 35);
      v19 = (char *)(P + 39);
      v9 = (P[129] & 2) != 0;
      v16 = 8;
      v10 = v9;
      v21 = &v10;
      v18 = 16;
      v20 = 16;
      v22 = 1;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140013058, (unsigned __int8 *)&byte_140011291, v4, v5, 7u, &v12);
    }
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)P + 14) + 1204LL));
    if ( v6 == 32 )
    {
      LODWORD(v11) = -1073741258;
      return VmbusTlConnectComplete((char *)P, (int *)&v11);
    }
    else
    {
      return VmbusTlCommonCancelConnection(P);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019110  mov     [rsp-8+arg_8], rbx
0x140019115  mov     [rsp-8+arg_10], rdi
0x14001911a  push    rbp
0x14001911b  lea     rbp, [rsp-57h]
0x140019120  sub     rsp, 0C0h
0x140019127  mov     rax, cs:__security_cookie
0x14001912e  xor     rax, rsp
0x140019131  mov     [rbp+57h+var_10], rax
0x140019135  mov     edi, [rcx+204h]
0x14001913b  mov     rbx, rcx
0x14001913e  call    HvSocketBeginProcessingConnection
0x140019143  test    al, al
0x140019145  jz      loc_14001923F
0x14001914b  or      dword ptr [rbx+204h], 1
0x140019152  and     edi, 30h
0x140019155  mov     rcx, [rbx+110h]; Process
0x14001915c  test    rcx, rcx
0x14001915f  jnz     short loc_140019165
0x140019161  xor     eax, eax
0x140019163  jmp     short loc_140019171
0x140019165  call    cs:__imp_PsGetProcessId
0x14001916c  nop     dword ptr [rax+rax+00h]
0x140019171  mov     ecx, cs:dword_140013058
0x140019177  cmp     ecx, 3
0x14001917a  jbe     loc_140019210
0x140019180  mov     eax, eax
0x140019182  lea     rcx, aAHyperVSocketC_1; "A Hyper-V socket connection has timed o"...
0x140019189  mov     [rbp+57h+var_88], rax
0x14001918d  lea     rdx, byte_140011291; int
0x140019194  lea     rax, [rbp+57h+var_88]
0x140019198  mov     [rbp+57h+var_60], rcx
0x14001919c  mov     [rbp+57h+var_50], rax
0x1400191a0  lea     rcx, dword_140013058; int
0x1400191a7  lea     rax, [rbx+8Ch]
0x1400191ae  mov     [rbp+57h+var_58], 2Bh ; '+'
0x1400191b6  mov     [rbp+57h+var_40], rax
0x1400191ba  lea     rax, [rbx+9Ch]
0x1400191c1  mov     [rbp+57h+var_30], rax
0x1400191c5  mov     eax, [rbx+204h]
0x1400191cb  shr     eax, 1
0x1400191cd  and     al, 1
0x1400191cf  mov     [rbp+57h+var_48], 8
0x1400191d7  mov     [rbp+57h+var_90], al
0x1400191da  lea     rax, [rbp+57h+var_90]
0x1400191de  mov     [rbp+57h+var_20], rax
0x1400191e2  lea     rax, [rbp+57h+var_80]
0x1400191e6  mov     [rsp+0C0h+var_98], rax; __int64
0x1400191eb  mov     [rsp+0C0h+var_A0], 7; ULONG
0x1400191f3  mov     [rbp+57h+var_38], 10h
0x1400191fb  mov     [rbp+57h+var_28], 10h
0x140019203  mov     [rbp+57h+var_18], 1
0x14001920b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140019210  mov     rax, [rbx+70h]
0x140019214  lock inc dword ptr [rax+4B4h]
0x14001921b  mov     rcx, rbx; P
0x14001921e  cmp     edi, 20h ; ' '
0x140019221  jnz     short loc_140019235
0x140019223  lea     rdx, [rbp+57h+var_88]
0x140019227  mov     dword ptr [rbp+57h+var_88], 0C0000236h
0x14001922e  call    VmbusTlConnectComplete
0x140019233  jmp     short loc_14001923F
0x140019235  xor     r8d, r8d
0x140019238  xor     edx, edx
0x14001923a  call    VmbusTlCommonCancelConnection
0x14001923f  mov     rcx, [rbp+57h+var_10]
0x140019243  xor     rcx, rsp; StackCookie
0x140019246  call    __security_check_cookie
0x14001924b  lea     r11, [rsp+0C0h+var_s0]
0x140019253  mov     rbx, [r11+18h]
0x140019257  mov     rdi, [r11+20h]
0x14001925b  mov     rsp, r11
0x14001925e  pop     rbp
0x14001925f  retn
```
