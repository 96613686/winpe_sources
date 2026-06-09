# CiLogHvciFailure

- ea: `0x18006ce34`
- end: `0x18006cf9c`
- name: `CiLogHvciFailure`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180076d8c`

## callees

- `0x18002bf20`
- `0x18006ce34`
- `0x1800a00f8`
- `0x1800a0390`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006ce94`
- `ntoskrnl!EtwEventEnabled` at `0x18006ce94`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cf3b`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006cf3b`
- `ntoskrnl!EtwWrite` at `0x18006cf63`
- `ntoskrnl!EtwWrite` at `0x18006cf63`

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
0x18006ce34  mov     [rsp-8+arg_0], rbx
0x18006ce39  mov     [rsp-8+arg_18], r9d
0x18006ce3e  push    rbp
0x18006ce3f  push    rsi
0x18006ce40  push    rdi
0x18006ce41  lea     rbp, [rsp-3Fh]
0x18006ce46  sub     rsp, 0C0h
0x18006ce4d  mov     rax, cs:__security_cookie
0x18006ce54  xor     rax, rsp
0x18006ce57  mov     [rbp+4Fh+var_20], rax
0x18006ce5b  xor     eax, eax
0x18006ce5d  lea     rbx, CiHvciAuditFailure
0x18006ce64  test    cl, cl
0x18006ce66  mov     [rbp+4Fh+var_A0], ax
0x18006ce6a  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006ce71  mov     rdi, rdx
0x18006ce74  mov     [rbp+4Fh+var_98], rax
0x18006ce78  xorps   xmm0, xmm0
0x18006ce7b  mov     [rbp+4Fh+var_9C], ax
0x18006ce7f  mov     rsi, r8
0x18006ce82  lea     rax, CiHvciFailure
0x18006ce89  cmovz   rbx, rax
0x18006ce8d  mov     rdx, rbx; EventDescriptor
0x18006ce90  movups  [rbp+4Fh+var_90], xmm0
0x18006ce94  call    cs:__imp_EtwEventEnabled
0x18006ce9b  nop     dword ptr [rax+rax+00h]
0x18006cea0  test    al, al
0x18006cea2  jnz     short loc_18006CEAB
0x18006cea4  xor     eax, eax
0x18006cea6  jmp     loc_18006CF7C
0x18006ceab  movzx   edx, word ptr [rdi]
0x18006ceae  lea     r8, [rbp+4Fh+var_98]
0x18006ceb2  movzx   eax, dx
0x18006ceb5  mov     [rbp+4Fh+var_68], edx
0x18006ceb8  shr     ax, 1
0x18006cebb  lea     rdx, [rbp+4Fh+var_90]
0x18006cebf  mov     [rbp+4Fh+var_A0], ax
0x18006cec3  mov     rcx, rsi
0x18006cec6  lea     rax, [rbp+4Fh+var_A0]
0x18006ceca  mov     qword ptr [rbp+4Fh+var_80.Size], 2
0x18006ced2  mov     [rbp+4Fh+var_80.Ptr], rax
0x18006ced6  mov     rax, [rdi+8]
0x18006ceda  mov     [rbp+4Fh+var_70], rax
0x18006cede  lea     rax, [rbp+4Fh+arg_18]
0x18006cee2  mov     [rbp+4Fh+var_60], rax
0x18006cee6  lea     rax, [rbp+4Fh+arg_20]
0x18006ceea  mov     [rbp+4Fh+var_50], rax
0x18006ceee  mov     [rbp+4Fh+var_64], 0
0x18006cef5  mov     [rbp+4Fh+var_58], 4
0x18006cefd  mov     [rbp+4Fh+var_48], 4
0x18006cf05  call    CipQueryProcessName
0x18006cf0a  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006cf0e  shr     ax, 1
0x18006cf11  mov     [rbp+4Fh+var_9C], ax
0x18006cf15  lea     rax, [rbp+4Fh+var_9C]
0x18006cf19  mov     [rbp+4Fh+var_40], rax
0x18006cf1d  mov     rax, qword ptr [rbp+4Fh+var_90+8]
0x18006cf21  mov     [rbp+4Fh+var_30], rax
0x18006cf25  movzx   eax, word ptr [rbp+4Fh+var_90]
0x18006cf29  mov     [rbp+4Fh+var_28], eax
0x18006cf2c  mov     [rbp+4Fh+var_38], 2
0x18006cf34  mov     [rbp+4Fh+var_24], 0
0x18006cf3b  call    cs:__imp_IoGetActivityIdThread
0x18006cf42  nop     dword ptr [rax+rax+00h]
0x18006cf47  lea     rcx, [rbp+4Fh+var_80]
0x18006cf4b  mov     r9d, 6; UserDataCount
0x18006cf51  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006cf56  mov     r8, rax; ActivityId
0x18006cf59  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cf60  mov     rdx, rbx; EventDescriptor
0x18006cf63  call    cs:__imp_EtwWrite
0x18006cf6a  nop     dword ptr [rax+rax+00h]
0x18006cf6f  mov     rcx, [rbp+4Fh+var_98]
0x18006cf73  mov     ebx, eax
0x18006cf75  call    CipReleaseProcessName
0x18006cf7a  mov     eax, ebx
0x18006cf7c  mov     rcx, [rbp+4Fh+var_20]
0x18006cf80  xor     rcx, rsp; StackCookie
0x18006cf83  call    __security_check_cookie
0x18006cf88  mov     rbx, [rsp+0D0h+arg_0]
0x18006cf90  add     rsp, 0C0h
0x18006cf97  pop     rdi
0x18006cf98  pop     rsi
0x18006cf99  pop     rbp
0x18006cf9a  retn
```
