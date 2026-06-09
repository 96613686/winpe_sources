# CiLogHvciFailure

- ea: `0x18006d114`
- end: `0x18006d27c`
- name: `CiLogHvciFailure`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18007706c`

## callees

- `0x18002c0d0`
- `0x18006d114`
- `0x18008f038`
- `0x18008f2d0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006d174`
- `ntoskrnl!EtwEventEnabled` at `0x18006d174`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d21b`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006d21b`
- `ntoskrnl!EtwWrite` at `0x18006d243`
- `ntoskrnl!EtwWrite` at `0x18006d243`

## pseudocode

```c
__int64 __fastcall CiLogHvciFailure(char a1, unsigned __int16 *a2, __int64 a3, int a4, char a5)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  unsigned __int16 v9; // ax
  __int64 v10; // rcx
  const GUID *ActivityIdThread; // rax
  unsigned int v12; // ebx
  __int16 v13; // [rsp+30h] [rbp-51h] BYREF
  __int16 v14; // [rsp+34h] [rbp-4Dh] BYREF
  __int64 v15; // [rsp+38h] [rbp-49h] BYREF
  __int128 v16; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-31h] BYREF
  __int64 v18; // [rsp+60h] [rbp-21h]
  int v19; // [rsp+68h] [rbp-19h]
  int v20; // [rsp+6Ch] [rbp-15h]
  int *v21; // [rsp+70h] [rbp-11h]
  __int64 v22; // [rsp+78h] [rbp-9h]
  char *v23; // [rsp+80h] [rbp-1h]
  __int64 v24; // [rsp+88h] [rbp+7h]
  __int16 *v25; // [rsp+90h] [rbp+Fh]
  __int64 v26; // [rsp+98h] [rbp+17h]
  __int64 v27; // [rsp+A0h] [rbp+1Fh]
  int v28; // [rsp+A8h] [rbp+27h]
  int v29; // [rsp+ACh] [rbp+2Bh]
  int v30; // [rsp+F8h] [rbp+77h] BYREF

  v30 = a4;
  v5 = (const EVENT_DESCRIPTOR *)CiHvciAuditFailure;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( !a1 )
    v5 = &CiHvciFailure;
  v16 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, v5) )
    return 0;
  v9 = *a2;
  v19 = *a2;
  v13 = v9 >> 1;
  *(_QWORD *)&UserData.Size = 2;
  UserData.Ptr = (ULONGLONG)&v13;
  v18 = *((_QWORD *)a2 + 1);
  v21 = &v30;
  v23 = &a5;
  v20 = 0;
  v22 = 4;
  v24 = 4;
  CipQueryProcessName(a3, &v16, &v15);
  v14 = (unsigned __int16)v16 >> 1;
  v25 = &v14;
  v27 = *((_QWORD *)&v16 + 1);
  v28 = (unsigned __int16)v16;
  v26 = 2;
  v29 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v10);
  v12 = EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
  CipReleaseProcessName(v15);
  return v12;
}

```

## disassembly

```asm
0x18006d114  mov     [rsp-8+arg_0], rbx
0x18006d119  mov     [rsp-8+arg_18], r9d
0x18006d11e  push    rbp
0x18006d11f  push    rsi
0x18006d120  push    rdi
0x18006d121  lea     rbp, [rsp-3Fh]
0x18006d126  sub     rsp, 0C0h
0x18006d12d  mov     rax, cs:__security_cookie
0x18006d134  xor     rax, rsp
0x18006d137  mov     [rbp+4Fh+var_20], rax
0x18006d13b  xor     eax, eax
0x18006d13d  lea     rbx, CiHvciAuditFailure
0x18006d144  test    cl, cl
0x18006d146  mov     [rbp+4Fh+var_A0], ax
0x18006d14a  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d151  mov     rdi, rdx
0x18006d154  mov     [rbp+4Fh+var_98], rax
0x18006d158  xorps   xmm0, xmm0
0x18006d15b  mov     [rbp+4Fh+var_9C], ax
0x18006d15f  mov     rsi, r8
0x18006d162  lea     rax, CiHvciFailure
0x18006d169  cmovz   rbx, rax
0x18006d16d  mov     rdx, rbx; EventDescriptor
0x18006d170  movups  [rbp+4Fh+var_90], xmm0
0x18006d174  call    cs:__imp_EtwEventEnabled
0x18006d17b  nop     dword ptr [rax+rax+00h]
0x18006d180  test    al, al
0x18006d182  jnz     short loc_18006D18B
0x18006d184  xor     eax, eax
0x18006d186  jmp     loc_18006D25C
0x18006d18b  movzx   edx, word ptr [rdi]
0x18006d18e  lea     r8, [rbp+4Fh+var_98]
0x18006d192  movzx   eax, dx
0x18006d195  mov     [rbp+4Fh+var_68], edx
0x18006d198  shr     ax, 1
0x18006d19b  lea     rdx, [rbp+4Fh+var_90]
0x18006d19f  mov     [rbp+4Fh+var_A0], ax
0x18006d1a3  mov     rcx, rsi
0x18006d1a6  lea     rax, [rbp+4Fh+var_A0]
0x18006d1aa  mov     qword ptr [rbp+4Fh+var_80.Size], 2
0x18006d1b2  mov     [rbp+4Fh+var_80.Ptr], rax
0x18006d1b6  mov     rax, [rdi+8]
0x18006d1ba  mov     [rbp+4Fh+var_70], rax
0x18006d1be  lea     rax, [rbp+4Fh+arg_18]
0x18006d1c2  mov     [rbp+4Fh+var_60], rax
0x18006d1c6  lea     rax, [rbp+4Fh+arg_20]
0x18006d1ca  mov     [rbp+4Fh+var_50], rax
0x18006d1ce  mov     [rbp+4Fh+var_64], 0
0x18006d1d5  mov     [rbp+4Fh+var_58], 4
0x18006d1dd  mov     [rbp+4Fh+var_48], 4
0x18006d1e5  call    CipQueryProcessName
0x18006d1ea  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006d1ee  shr     ax, 1
0x18006d1f1  mov     [rbp+4Fh+var_9C], ax
0x18006d1f5  lea     rax, [rbp+4Fh+var_9C]
0x18006d1f9  mov     [rbp+4Fh+var_40], rax
0x18006d1fd  mov     rax, qword ptr [rbp+4Fh+var_90+8]
0x18006d201  mov     [rbp+4Fh+var_30], rax
0x18006d205  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006d209  mov     [rbp+4Fh+var_28], eax
0x18006d20c  mov     [rbp+4Fh+var_38], 2
0x18006d214  mov     [rbp+4Fh+var_24], 0
0x18006d21b  call    cs:__imp_IoGetActivityIdThread
0x18006d222  nop     dword ptr [rax+rax+00h]
0x18006d227  lea     rcx, [rbp+4Fh+var_80]
0x18006d22b  mov     r9d, 6; UserDataCount
0x18006d231  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006d236  mov     r8, rax; ActivityId
0x18006d239  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006d240  mov     rdx, rbx; EventDescriptor
0x18006d243  call    cs:__imp_EtwWrite
0x18006d24a  nop     dword ptr [rax+rax+00h]
0x18006d24f  mov     rcx, [rbp+4Fh+var_98]
0x18006d253  mov     ebx, eax
0x18006d255  call    CipReleaseProcessName
0x18006d25a  mov     eax, ebx
0x18006d25c  mov     rcx, [rbp+4Fh+var_20]
0x18006d260  xor     rcx, rsp; StackCookie
0x18006d263  call    __security_check_cookie
0x18006d268  mov     rbx, [rsp+0D0h+arg_0]
0x18006d270  add     rsp, 0C0h
0x18006d277  pop     rdi
0x18006d278  pop     rsi
0x18006d279  pop     rbp
0x18006d27a  retn
```
