# CiLogHvciFailure

- ea: `0x18006c060`
- end: `0x18006c1c8`
- name: `CiLogHvciFailure`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800757dc`

## callees

- `0x18002bef0`
- `0x18006c060`
- `0x18009eac8`
- `0x18009ed60`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006c0c0`
- `ntoskrnl!EtwEventEnabled` at `0x18006c0c0`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c167`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006c167`
- `ntoskrnl!EtwWrite` at `0x18006c18f`
- `ntoskrnl!EtwWrite` at `0x18006c18f`

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
0x18006c060  mov     [rsp-8+arg_0], rbx
0x18006c065  mov     [rsp-8+arg_18], r9d
0x18006c06a  push    rbp
0x18006c06b  push    rsi
0x18006c06c  push    rdi
0x18006c06d  lea     rbp, [rsp-3Fh]
0x18006c072  sub     rsp, 0C0h
0x18006c079  mov     rax, cs:__security_cookie
0x18006c080  xor     rax, rsp
0x18006c083  mov     [rbp+4Fh+var_20], rax
0x18006c087  xor     eax, eax
0x18006c089  lea     rbx, CiHvciAuditFailure
0x18006c090  test    cl, cl
0x18006c092  mov     [rbp+4Fh+var_A0], ax
0x18006c096  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c09d  mov     rdi, rdx
0x18006c0a0  mov     [rbp+4Fh+var_98], rax
0x18006c0a4  xorps   xmm0, xmm0
0x18006c0a7  mov     [rbp+4Fh+var_9C], ax
0x18006c0ab  mov     rsi, r8
0x18006c0ae  lea     rax, CiHvciFailure
0x18006c0b5  cmovz   rbx, rax
0x18006c0b9  mov     rdx, rbx; EventDescriptor
0x18006c0bc  movups  [rbp+4Fh+var_90], xmm0
0x18006c0c0  call    cs:__imp_EtwEventEnabled
0x18006c0c7  nop     dword ptr [rax+rax+00h]
0x18006c0cc  test    al, al
0x18006c0ce  jnz     short loc_18006C0D7
0x18006c0d0  xor     eax, eax
0x18006c0d2  jmp     loc_18006C1A8
0x18006c0d7  movzx   edx, word ptr [rdi]
0x18006c0da  lea     r8, [rbp+4Fh+var_98]
0x18006c0de  movzx   eax, dx
0x18006c0e1  mov     [rbp+4Fh+var_68], edx
0x18006c0e4  shr     ax, 1
0x18006c0e7  lea     rdx, [rbp+4Fh+var_90]
0x18006c0eb  mov     [rbp+4Fh+var_A0], ax
0x18006c0ef  mov     rcx, rsi
0x18006c0f2  lea     rax, [rbp+4Fh+var_A0]
0x18006c0f6  mov     qword ptr [rbp+4Fh+var_80.Size], 2
0x18006c0fe  mov     [rbp+4Fh+var_80.Ptr], rax
0x18006c102  mov     rax, [rdi+8]
0x18006c106  mov     [rbp+4Fh+var_70], rax
0x18006c10a  lea     rax, [rbp+4Fh+arg_18]
0x18006c10e  mov     [rbp+4Fh+var_60], rax
0x18006c112  lea     rax, [rbp+4Fh+arg_20]
0x18006c116  mov     [rbp+4Fh+var_50], rax
0x18006c11a  mov     [rbp+4Fh+var_64], 0
0x18006c121  mov     [rbp+4Fh+var_58], 4
0x18006c129  mov     [rbp+4Fh+var_48], 4
0x18006c131  call    CipQueryProcessName
0x18006c136  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006c13a  shr     ax, 1
0x18006c13d  mov     [rbp+4Fh+var_9C], ax
0x18006c141  lea     rax, [rbp+4Fh+var_9C]
0x18006c145  mov     [rbp+4Fh+var_40], rax
0x18006c149  mov     rax, qword ptr [rbp+4Fh+var_90+8]
0x18006c14d  mov     [rbp+4Fh+var_30], rax
0x18006c151  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006c155  mov     [rbp+4Fh+var_28], eax
0x18006c158  mov     [rbp+4Fh+var_38], 2
0x18006c160  mov     [rbp+4Fh+var_24], 0
0x18006c167  call    cs:__imp_IoGetActivityIdThread
0x18006c16e  nop     dword ptr [rax+rax+00h]
0x18006c173  lea     rcx, [rbp+4Fh+var_80]
0x18006c177  mov     r9d, 6; UserDataCount
0x18006c17d  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006c182  mov     r8, rax; ActivityId
0x18006c185  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006c18c  mov     rdx, rbx; EventDescriptor
0x18006c18f  call    cs:__imp_EtwWrite
0x18006c196  nop     dword ptr [rax+rax+00h]
0x18006c19b  mov     rcx, [rbp+4Fh+var_98]
0x18006c19f  mov     ebx, eax
0x18006c1a1  call    CipReleaseProcessName
0x18006c1a6  mov     eax, ebx
0x18006c1a8  mov     rcx, [rbp+4Fh+var_20]
0x18006c1ac  xor     rcx, rsp; StackCookie
0x18006c1af  call    __security_check_cookie
0x18006c1b4  mov     rbx, [rsp+0D0h+arg_0]
0x18006c1bc  add     rsp, 0C0h
0x18006c1c3  pop     rdi
0x18006c1c4  pop     rsi
0x18006c1c5  pop     rbp
0x18006c1c6  retn
```
