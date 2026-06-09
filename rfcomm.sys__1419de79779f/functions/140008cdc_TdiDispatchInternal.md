# TdiDispatchInternal

- ea: `0x140008cdc`
- end: `0x140008fcc`
- name: `TdiDispatchInternal`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005cfc`

## callees

- `0x140008cdc`
- `0x14000b808`
- `0x14000bcd8`
- `0x14000cd4c`
- `0x14000ce70`
- `0x14000d020`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dcb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dcb`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008ebd`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008ebd`

## string_xrefs

- `0x140008dae`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140008f86`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140008fa6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiDispatchInternal(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  unsigned int v4; // r8d
  int v5; // r9d
  __int64 v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rbp
  __int64 v10; // r13
  _QWORD *v11; // rsi
  __int64 v12; // rax
  _QWORD *v13; // rdi
  _QWORD *i; // rax
  __int64 v15; // r15
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  __int64 (__fastcall *v20)(__int64, __int64, __int64, __int64); // rax
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  __int64 *v25; // [rsp+20h] [rbp-78h]
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v26 = 0;
  v4 = 0;
  v5 = *(unsigned __int8 *)(v2 + 1);
  while ( 1 )
  {
    v6 = 7LL * v4;
    if ( LODWORD(g_TdiDispatchTable[v6]) == v5 )
      break;
    if ( ++v4 >= 0xA )
      goto LABEL_6;
  }
  if ( !&g_TdiDispatchTable[v6] )
  {
LABEL_6:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_c(WPP_GLOBAL_Control->DeviceExtension, a2, v4, v5);
    return (unsigned int)-1073741822;
  }
  v8 = *(_QWORD *)(v2 + 48);
  v9 = 0;
  v10 = *(_QWORD *)(a1 + 64);
  v11 = 0;
  v12 = *(_QWORD *)(v8 + 32);
  if ( v12 == 2 )
  {
    v13 = *(_QWORD **)(v8 + 24);
    *(_BYTE *)(v10 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 48));
    for ( i = *(_QWORD **)(v10 + 96); i != (_QWORD *)(v10 + 96); i = (_QWORD *)*i )
    {
      if ( v13 == i )
      {
        v11 = v13;
        RefObj_AddRefEx(v13 + 3, 542134857, 4535, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
        break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 48), *(_BYTE *)(v10 + 56));
    v15 = (__int64)v11;
  }
  else
  {
    v15 = 0;
    if ( v12 == 1 )
    {
      v9 = ValidateAndReferenceAddr(*(_QWORD *)(a1 + 64), *(_QWORD *)(v8 + 24));
      v15 = v9;
    }
  }
  v16 = HIDWORD(g_TdiDispatchTable[v6]);
  if ( v16 != 1 )
  {
    if ( v16 == 2 && !v11 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sq(WPP_GLOBAL_Control->DeviceExtension, v8, v4, 154);
      v7 = -1073741816;
      goto LABEL_38;
    }
    goto LABEL_29;
  }
  if ( v9 )
  {
LABEL_29:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      KeGetCurrentIrql();
      WPP_RECORDER_SF_sqqqd(WPP_GLOBAL_Control->DeviceExtension, v17, v18, v19);
    }
    v20 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))g_TdiDispatchTable[v6 + 2];
    if ( v20 )
    {
      v25 = &v26;
      v7 = v20(v10, a2, v15, v2 + 8);
    }
    else
    {
      v7 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = NtStatusTxt(v7);
      WPP_RECORDER_SF_ssi(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&qword_140022018[v6],
        v22,
        v23,
        (_DWORD)v25,
        (__int64)&qword_140022018[v6],
        v21,
        v26);
    }
    goto LABEL_36;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(WPP_GLOBAL_Control->DeviceExtension, v8, v4, 153);
  v7 = -1073741816;
LABEL_36:
  if ( v11 )
    RefObj_ReleaseEx(v11 + 3, 542134857, 4702, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
LABEL_38:
  if ( v9 )
    RefObj_ReleaseEx(v9 + 24, 542134857, 4707, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  return v7;
}

```

## disassembly

```asm
0x140008cdc  mov     rax, rsp
0x140008cdf  push    rbx
0x140008ce0  push    rbp
0x140008ce1  push    rsi
0x140008ce2  push    rdi
0x140008ce3  push    r12
0x140008ce5  push    r13
0x140008ce7  push    r14
0x140008ce9  push    r15
0x140008ceb  sub     rsp, 58h
0x140008cef  mov     rbx, [rdx+0B8h]
0x140008cf6  lea     r10, g_TdiDispatchTable
0x140008cfd  mov     qword ptr [rax+8], 0
0x140008d05  mov     r12, rdx
0x140008d08  xor     r8d, r8d
0x140008d0b  movzx   r9d, byte ptr [rbx+1]
0x140008d10  mov     eax, r8d
0x140008d13  imul    r14, rax, 38h ; '8'
0x140008d17  lea     rax, [r14+r10]
0x140008d1b  cmp     [rax], r9d
0x140008d1e  jz      short loc_140008D2B
0x140008d20  inc     r8d
0x140008d23  cmp     r8d, 0Ah
0x140008d27  jb      short loc_140008D10
0x140008d29  jmp     short loc_140008D30
0x140008d2b  test    rax, rax
0x140008d2e  jnz     short loc_140008D5F
0x140008d30  lea     rdi, WPP_RECORDER_INITIALIZED
0x140008d37  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008d3e  jz      short loc_140008D55
0x140008d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d47  mov     byte ptr [rsp+98h+var_70], r9b
0x140008d4c  mov     rcx, [rcx+40h]
0x140008d50  call    WPP_RECORDER_SF_c
0x140008d55  mov     ebx, 0C0000002h
0x140008d5a  jmp     loc_140008FB8
0x140008d5f  mov     rdx, [rbx+30h]
0x140008d63  xor     ebp, ebp
0x140008d65  mov     r13, [rcx+40h]
0x140008d69  xor     esi, esi
0x140008d6b  mov     rax, [rdx+20h]
0x140008d6f  cmp     rax, 2
0x140008d73  jnz     short loc_140008DDC
0x140008d75  mov     rdi, [rdx+18h]
0x140008d79  lea     rcx, [r13+30h]; SpinLock
0x140008d7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008d84  nop     dword ptr [rax+rax+00h]
0x140008d89  lea     rcx, [r13+60h]
0x140008d8d  mov     [r13+38h], al
0x140008d91  mov     rax, [rcx]
0x140008d94  jmp     short loc_140008D9E
0x140008d96  cmp     rdi, rax
0x140008d99  jz      short loc_140008DA5
0x140008d9b  mov     rax, [rax]
0x140008d9e  cmp     rax, rcx
0x140008da1  jnz     short loc_140008D96
0x140008da3  jmp     short loc_140008DC3
0x140008da5  lea     rcx, [rdi+18h]
0x140008da9  mov     edx, 20505249h
0x140008dae  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008db5  mov     r8d, 11B7h
0x140008dbb  mov     rsi, rdi
0x140008dbe  call    RefObj_AddRefEx
0x140008dc3  mov     dl, [r13+38h]; NewIrql
0x140008dc7  lea     rcx, [r13+30h]; SpinLock
0x140008dcb  call    cs:__imp_KeReleaseSpinLock
0x140008dd2  nop     dword ptr [rax+rax+00h]
0x140008dd7  mov     r15, rsi
0x140008dda  jmp     short loc_140008DF7
0x140008ddc  xor     r15d, r15d
0x140008ddf  cmp     rax, 1
0x140008de3  jnz     short loc_140008DFE
0x140008de5  mov     rdx, [rdx+18h]
0x140008de9  mov     rcx, r13
0x140008dec  call    ValidateAndReferenceAddr
0x140008df1  mov     rbp, rax
0x140008df4  mov     r15, rax
0x140008df7  lea     r10, g_TdiDispatchTable
0x140008dfe  mov     eax, [r14+r10+4]
0x140008e03  cmp     eax, 1
0x140008e06  jnz     short loc_140008E5A
0x140008e08  test    rbp, rbp
0x140008e0b  jnz     loc_140008EAD
0x140008e11  lea     rdi, WPP_RECORDER_INITIALIZED
0x140008e18  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008e1f  jz      short loc_140008E50
0x140008e21  mov     rax, [rbx+30h]
0x140008e25  lea     rcx, [r10+18h]
0x140008e29  add     rcx, r14
0x140008e2c  mov     r9d, 99h
0x140008e32  mov     rax, [rax+18h]
0x140008e36  mov     [rsp+98h+var_68], rax
0x140008e3b  mov     [rsp+98h+var_70], rcx
0x140008e40  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e47  mov     rcx, [rcx+40h]
0x140008e4b  call    WPP_RECORDER_SF_sq
0x140008e50  mov     ebx, 0C0000008h
0x140008e55  jmp     loc_140008F78
0x140008e5a  cmp     eax, 2
0x140008e5d  jnz     short loc_140008EAD
0x140008e5f  test    rsi, rsi
0x140008e62  jnz     short loc_140008EAD
0x140008e64  lea     rdi, WPP_RECORDER_INITIALIZED
0x140008e6b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008e72  jz      short loc_140008EA3
0x140008e74  mov     rax, [rbx+30h]
0x140008e78  lea     rcx, [r10+18h]
0x140008e7c  add     rcx, r14
0x140008e7f  mov     r9d, 9Ah
0x140008e85  mov     rax, [rax+18h]
0x140008e89  mov     [rsp+98h+var_68], rax
0x140008e8e  mov     [rsp+98h+var_70], rcx
0x140008e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e9a  mov     rcx, [rcx+40h]
0x140008e9e  call    WPP_RECORDER_SF_sq
0x140008ea3  mov     ebx, 0C0000008h
0x140008ea8  jmp     loc_140008F98
0x140008ead  lea     rdi, WPP_RECORDER_INITIALIZED
0x140008eb4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008ebb  jz      short loc_140008F04
0x140008ebd  call    cs:__imp_KeGetCurrentIrql
0x140008ec4  nop     dword ptr [rax+rax+00h]
0x140008ec9  movzx   eax, al
0x140008ecc  lea     rcx, g_TdiDispatchTable
0x140008ed3  add     rcx, 18h
0x140008ed7  mov     [rsp+98h+var_50], eax
0x140008edb  add     rcx, r14
0x140008ede  mov     [rsp+98h+var_58], rbp
0x140008ee3  mov     [rsp+98h+var_60], rsi
0x140008ee8  mov     [rsp+98h+var_70], rcx
0x140008eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ef4  mov     rcx, [rcx+40h]
0x140008ef8  call    WPP_RECORDER_SF_sqqqd
0x140008efd  lea     r10, g_TdiDispatchTable
0x140008f04  mov     rax, [r14+r10+10h]
0x140008f09  test    rax, rax
0x140008f0c  jz      short loc_140008F31
0x140008f0e  lea     rcx, [rsp+98h+arg_0]
0x140008f16  mov     r8, r15
0x140008f19  mov     [rsp+98h+var_78], rcx
0x140008f1e  lea     r9, [rbx+8]
0x140008f22  mov     rcx, r13
0x140008f25  mov     rdx, r12
0x140008f28  call    _guard_dispatch_icall
0x140008f2d  mov     ebx, eax
0x140008f2f  jmp     short loc_140008F33
0x140008f31  xor     ebx, ebx
0x140008f33  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008f3a  jz      short loc_140008F78
0x140008f3c  mov     ecx, ebx
0x140008f3e  call    NtStatusTxt
0x140008f43  mov     rcx, [rsp+98h+arg_0]
0x140008f4b  lea     rdx, g_TdiDispatchTable
0x140008f52  mov     [rsp+98h+var_60], rcx
0x140008f57  add     rdx, 18h
0x140008f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f62  add     rdx, r14
0x140008f65  mov     [rsp+98h+var_68], rax
0x140008f6a  mov     [rsp+98h+var_70], rdx
0x140008f6f  mov     rcx, [rcx+40h]
0x140008f73  call    WPP_RECORDER_SF_ssi
0x140008f78  test    rsi, rsi
0x140008f7b  jz      short loc_140008F98
0x140008f7d  lea     rcx, [rsi+18h]
0x140008f81  mov     edx, 20505249h
0x140008f86  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008f8d  mov     r8d, 125Eh
0x140008f93  call    RefObj_ReleaseEx
0x140008f98  test    rbp, rbp
0x140008f9b  jz      short loc_140008FB8
0x140008f9d  lea     rcx, [rbp+18h]
0x140008fa1  mov     edx, 20505249h
0x140008fa6  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008fad  mov     r8d, 1263h
0x140008fb3  call    RefObj_ReleaseEx
0x140008fb8  mov     eax, ebx
0x140008fba  add     rsp, 58h
0x140008fbe  pop     r15
0x140008fc0  pop     r14
0x140008fc2  pop     r13
0x140008fc4  pop     r12
0x140008fc6  pop     rdi
0x140008fc7  pop     rsi
0x140008fc8  pop     rbp
0x140008fc9  pop     rbx
0x140008fca  retn
```
