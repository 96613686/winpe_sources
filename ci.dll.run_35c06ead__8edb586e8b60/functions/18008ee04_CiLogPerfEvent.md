# CiLogPerfEvent

- ea: `0x18008ee04`
- end: `0x18008ef6e`
- name: `CiLogPerfEvent`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18008ef74`

## callees

- `0x18002c0d0`
- `0x18008ee04`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18008ee4f`
- `ntoskrnl!EtwEventEnabled` at `0x18008ee4f`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008ef14`
- `ntoskrnl!IoGetActivityIdThread` at `0x18008ef14`
- `ntoskrnl!EtwWrite` at `0x18008ef40`
- `ntoskrnl!EtwWrite` at `0x18008ef40`

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
0x18008ee04  mov     rax, rsp
0x18008ee07  mov     [rax+8], rbx
0x18008ee0b  mov     [rax+10h], rdi
0x18008ee0f  mov     [rax+20h], r9b
0x18008ee13  mov     [rax+18h], r8b
0x18008ee17  push    rbp
0x18008ee18  lea     rbp, [rax-3Fh]
0x18008ee1c  sub     rsp, 0E0h
0x18008ee23  mov     rax, cs:__security_cookie
0x18008ee2a  xor     rax, rsp
0x18008ee2d  mov     [rbp+37h+var_10], rax
0x18008ee31  xor     eax, eax
0x18008ee33  mov     rbx, rdx
0x18008ee36  mov     rdi, rcx
0x18008ee39  mov     [rbp+37h+var_B0], ax
0x18008ee3d  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008ee44  lea     rdx, SiPolicyPerformance; EventDescriptor
0x18008ee4b  mov     [rbp+37h+var_AC], ax
0x18008ee4f  call    cs:__imp_EtwEventEnabled
0x18008ee56  nop     dword ptr [rax+rax+00h]
0x18008ee5b  test    al, al
0x18008ee5d  jnz     short loc_18008EE66
0x18008ee5f  xor     eax, eax
0x18008ee61  jmp     loc_18008EF4C
0x18008ee66  movzx   ecx, word ptr [rdi]
0x18008ee69  movzx   edx, word ptr [rbx]
0x18008ee6c  movzx   eax, cx
0x18008ee6f  shr     ax, 1
0x18008ee72  mov     [rbp+37h+var_B0], ax
0x18008ee76  movzx   eax, dx
0x18008ee79  shr     ax, 1
0x18008ee7c  mov     [rbp+37h+var_AC], ax
0x18008ee80  lea     rax, [rbp+37h+var_B0]
0x18008ee84  mov     [rbp+37h+var_A0.Ptr], rax
0x18008ee88  mov     rax, [rdi+8]
0x18008ee8c  mov     [rbp+37h+var_90], rax
0x18008ee90  lea     rax, [rbp+37h+var_AC]
0x18008ee94  mov     [rbp+37h+var_80], rax
0x18008ee98  mov     rax, [rbx+8]
0x18008ee9c  mov     [rbp+37h+var_70], rax
0x18008eea0  lea     rax, [rbp+37h+arg_10]
0x18008eea4  mov     [rbp+37h+var_60], rax
0x18008eea8  lea     rax, [rbp+37h+arg_18]
0x18008eeac  mov     [rbp+37h+var_50], rax
0x18008eeb0  lea     rax, [rbp+37h+arg_20]
0x18008eeb4  mov     [rbp+37h+var_40], rax
0x18008eeb8  lea     rax, [rbp+37h+arg_28]
0x18008eebc  mov     [rbp+37h+var_30], rax
0x18008eec0  lea     rax, [rbp+37h+arg_30]
0x18008eec4  mov     [rbp+37h+var_20], rax
0x18008eec8  mov     qword ptr [rbp+37h+var_A0.Size], 2
0x18008eed0  mov     [rbp+37h+var_88], ecx
0x18008eed3  mov     [rbp+37h+var_84], 0
0x18008eeda  mov     [rbp+37h+var_78], 2
0x18008eee2  mov     [rbp+37h+var_68], edx
0x18008eee5  mov     [rbp+37h+var_64], 0
0x18008eeec  mov     [rbp+37h+var_58], 1
0x18008eef4  mov     [rbp+37h+var_48], 1
0x18008eefc  mov     [rbp+37h+var_38], 8
0x18008ef04  mov     [rbp+37h+var_28], 8
0x18008ef0c  mov     [rbp+37h+var_18], 4
0x18008ef14  call    cs:__imp_IoGetActivityIdThread
0x18008ef1b  nop     dword ptr [rax+rax+00h]
0x18008ef20  lea     rcx, [rbp+37h+var_A0]
0x18008ef24  mov     r9d, 9; UserDataCount
0x18008ef2a  mov     [rsp+0E0h+UserData], rcx; UserData
0x18008ef2f  lea     rdx, SiPolicyPerformance; EventDescriptor
0x18008ef36  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18008ef3d  mov     r8, rax; ActivityId
0x18008ef40  call    cs:__imp_EtwWrite
0x18008ef47  nop     dword ptr [rax+rax+00h]
0x18008ef4c  mov     rcx, [rbp+37h+var_10]
0x18008ef50  xor     rcx, rsp; StackCookie
0x18008ef53  call    __security_check_cookie
0x18008ef58  lea     r11, [rsp+0E0h+var_s0]
0x18008ef60  mov     rbx, [r11+10h]
0x18008ef64  mov     rdi, [r11+18h]
0x18008ef68  mov     rsp, r11
0x18008ef6b  pop     rbp
0x18008ef6c  retn
```
