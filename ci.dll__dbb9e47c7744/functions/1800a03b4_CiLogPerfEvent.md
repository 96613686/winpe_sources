# CiLogPerfEvent

- ea: `0x1800a03b4`
- end: `0x1800a051e`
- name: `CiLogPerfEvent`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800a0034`

## callees

- `0x18002bf20`
- `0x1800a03b4`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1800a03ff`
- `ntoskrnl!EtwEventEnabled` at `0x1800a03ff`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a04c4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1800a04c4`
- `ntoskrnl!EtwWrite` at `0x1800a04f0`
- `ntoskrnl!EtwWrite` at `0x1800a04f0`

## pseudocode

```c
NTSTATUS __fastcall CiLogPerfEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        char a3,
        char a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v10; // rcx
  int v11; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v13; // [rsp+38h] [rbp-79h] BYREF
  __int16 v14; // [rsp+3Ch] [rbp-75h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-69h] BYREF
  __int64 v16; // [rsp+58h] [rbp-59h]
  int v17; // [rsp+60h] [rbp-51h]
  int v18; // [rsp+64h] [rbp-4Dh]
  __int16 *v19; // [rsp+68h] [rbp-49h]
  __int64 v20; // [rsp+70h] [rbp-41h]
  __int64 v21; // [rsp+78h] [rbp-39h]
  int v22; // [rsp+80h] [rbp-31h]
  int v23; // [rsp+84h] [rbp-2Dh]
  char *v24; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h]
  char *v26; // [rsp+98h] [rbp-19h]
  __int64 v27; // [rsp+A0h] [rbp-11h]
  char *v28; // [rsp+A8h] [rbp-9h]
  __int64 v29; // [rsp+B0h] [rbp-1h]
  char *v30; // [rsp+B8h] [rbp+7h]
  __int64 v31; // [rsp+C0h] [rbp+Fh]
  char *v32; // [rsp+C8h] [rbp+17h]
  __int64 v33; // [rsp+D0h] [rbp+1Fh]
  char v34; // [rsp+108h] [rbp+57h] BYREF
  char v35; // [rsp+110h] [rbp+5Fh] BYREF

  v35 = a4;
  v34 = a3;
  v13 = 0;
  v14 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, &SiPolicyPerformance) )
    return 0;
  v10 = *a1;
  v11 = *a2;
  v13 = *a1 >> 1;
  v14 = (unsigned __int16)v11 >> 1;
  UserData.Ptr = (ULONGLONG)&v13;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v14;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v34;
  v26 = &v35;
  v28 = &a5;
  v30 = &a6;
  v32 = &a7;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v10;
  v18 = 0;
  v20 = 2;
  v22 = v11;
  v23 = 0;
  v25 = 1;
  v27 = 1;
  v29 = 8;
  v31 = 8;
  v33 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v10);
  return EtwWrite(g_EtwEventHandle, &SiPolicyPerformance, ActivityIdThread, 9u, &UserData);
}

```

## disassembly

```asm
0x1800a03b4  mov     rax, rsp
0x1800a03b7  mov     [rax+8], rbx
0x1800a03bb  mov     [rax+10h], rdi
0x1800a03bf  mov     [rax+20h], r9b
0x1800a03c3  mov     [rax+18h], r8b
0x1800a03c7  push    rbp
0x1800a03c8  lea     rbp, [rax-3Fh]
0x1800a03cc  sub     rsp, 0E0h
0x1800a03d3  mov     rax, cs:__security_cookie
0x1800a03da  xor     rax, rsp
0x1800a03dd  mov     [rbp+37h+var_10], rax
0x1800a03e1  xor     eax, eax
0x1800a03e3  mov     rbx, rdx
0x1800a03e6  mov     rdi, rcx
0x1800a03e9  mov     [rbp+37h+var_B0], ax
0x1800a03ed  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a03f4  lea     rdx, SiPolicyPerformance; EventDescriptor
0x1800a03fb  mov     [rbp+37h+var_AC], ax
0x1800a03ff  call    cs:__imp_EtwEventEnabled
0x1800a0406  nop     dword ptr [rax+rax+00h]
0x1800a040b  test    al, al
0x1800a040d  jnz     short loc_1800A0416
0x1800a040f  xor     eax, eax
0x1800a0411  jmp     loc_1800A04FC
0x1800a0416  movzx   ecx, word ptr [rdi]
0x1800a0419  movzx   edx, word ptr [rbx]
0x1800a041c  movzx   eax, cx
0x1800a041f  shr     ax, 1
0x1800a0422  mov     [rbp+37h+var_B0], ax
0x1800a0426  movzx   eax, dx
0x1800a0429  shr     ax, 1
0x1800a042c  mov     [rbp+37h+var_AC], ax
0x1800a0430  lea     rax, [rbp+37h+var_B0]
0x1800a0434  mov     [rbp+37h+var_A0.Ptr], rax
0x1800a0438  mov     rax, [rdi+8]
0x1800a043c  mov     [rbp+37h+var_90], rax
0x1800a0440  lea     rax, [rbp+37h+var_AC]
0x1800a0444  mov     [rbp+37h+var_80], rax
0x1800a0448  mov     rax, [rbx+8]
0x1800a044c  mov     [rbp+37h+var_70], rax
0x1800a0450  lea     rax, [rbp+37h+arg_10]
0x1800a0454  mov     [rbp+37h+var_60], rax
0x1800a0458  lea     rax, [rbp+37h+arg_18]
0x1800a045c  mov     [rbp+37h+var_50], rax
0x1800a0460  lea     rax, [rbp+37h+arg_20]
0x1800a0464  mov     [rbp+37h+var_40], rax
0x1800a0468  lea     rax, [rbp+37h+arg_28]
0x1800a046c  mov     [rbp+37h+var_30], rax
0x1800a0470  lea     rax, [rbp+37h+arg_30]
0x1800a0474  mov     [rbp+37h+var_20], rax
0x1800a0478  mov     qword ptr [rbp+37h+var_A0.Size], 2
0x1800a0480  mov     [rbp+37h+var_88], ecx
0x1800a0483  mov     [rbp+37h+var_84], 0
0x1800a048a  mov     [rbp+37h+var_78], 2
0x1800a0492  mov     [rbp+37h+var_68], edx
0x1800a0495  mov     [rbp+37h+var_64], 0
0x1800a049c  mov     [rbp+37h+var_58], 1
0x1800a04a4  mov     [rbp+37h+var_48], 1
0x1800a04ac  mov     [rbp+37h+var_38], 8
0x1800a04b4  mov     [rbp+37h+var_28], 8
0x1800a04bc  mov     [rbp+37h+var_18], 4
0x1800a04c4  call    cs:__imp_IoGetActivityIdThread
0x1800a04cb  nop     dword ptr [rax+rax+00h]
0x1800a04d0  lea     rcx, [rbp+37h+var_A0]
0x1800a04d4  mov     r9d, 9; UserDataCount
0x1800a04da  mov     [rsp+0E0h+UserData], rcx; UserData
0x1800a04df  lea     rdx, SiPolicyPerformance; EventDescriptor
0x1800a04e6  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800a04ed  mov     r8, rax; ActivityId
0x1800a04f0  call    cs:__imp_EtwWrite
0x1800a04f7  nop     dword ptr [rax+rax+00h]
0x1800a04fc  mov     rcx, [rbp+37h+var_10]
0x1800a0500  xor     rcx, rsp; StackCookie
0x1800a0503  call    __security_check_cookie
0x1800a0508  lea     r11, [rsp+0E0h+var_s0]
0x1800a0510  mov     rbx, [r11+10h]
0x1800a0514  mov     rdi, [r11+18h]
0x1800a0518  mov     rsp, r11
0x1800a051b  pop     rbp
0x1800a051c  retn
```
