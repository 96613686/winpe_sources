# CiLogSdlEvent

- ea: `0x18006dc2c`
- end: `0x18006dd56`
- name: `CiLogSdlEvent`
- size: `298`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064be8`

## callees

- `0x18002c0d0`
- `0x18006dc2c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006dc74`
- `ntoskrnl!EtwEventEnabled` at `0x18006dc74`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006dd09`
- `ntoskrnl!IoGetActivityIdThread` at `0x18006dd09`
- `ntoskrnl!EtwWrite` at `0x18006dd31`
- `ntoskrnl!EtwWrite` at `0x18006dd31`

## pseudocode

```c
NTSTATUS __fastcall CiLogSdlEvent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  int v9; // ecx
  int v10; // edx
  const GUID *ActivityIdThread; // rax
  __int16 v12; // [rsp+30h] [rbp-51h] BYREF
  __int16 v13; // [rsp+34h] [rbp-4Dh] BYREF
  int v14; // [rsp+38h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-41h] BYREF
  __int64 v16; // [rsp+50h] [rbp-31h]
  int v17; // [rsp+58h] [rbp-29h]
  int v18; // [rsp+5Ch] [rbp-25h]
  __int16 *v19; // [rsp+60h] [rbp-21h]
  __int64 v20; // [rsp+68h] [rbp-19h]
  __int64 v21; // [rsp+70h] [rbp-11h]
  int v22; // [rsp+78h] [rbp-9h]
  int v23; // [rsp+7Ch] [rbp-5h]
  int *v24; // [rsp+80h] [rbp-1h]
  __int64 v25; // [rsp+88h] [rbp+7h]
  int *v26; // [rsp+90h] [rbp+Fh]
  __int64 v27; // [rsp+98h] [rbp+17h]
  int v28; // [rsp+F8h] [rbp+77h] BYREF

  v28 = a4;
  v5 = EventDescriptor;
  v14 = 1;
  v12 = 0;
  v13 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, EventDescriptor) )
    return 0;
  v9 = *a1;
  v10 = *a2;
  v12 = *a1 >> 1;
  v13 = (unsigned __int16)v10 >> 1;
  UserData.Ptr = (ULONGLONG)&v12;
  v16 = *((_QWORD *)a1 + 1);
  v19 = &v13;
  v21 = *((_QWORD *)a2 + 1);
  v24 = &v14;
  v26 = &v28;
  *(_QWORD *)&UserData.Size = 2;
  v17 = v9;
  v18 = 0;
  v20 = 2;
  v22 = v10;
  v23 = 0;
  v25 = 1;
  v27 = 4;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread();
  return EtwWrite(g_EtwEventHandle, v5, ActivityIdThread, 6u, &UserData);
}

```

## disassembly

```asm
0x18006dc2c  mov     [rsp-8+arg_18], r9d
0x18006dc31  push    rbp
0x18006dc32  push    rbx
0x18006dc33  push    rsi
0x18006dc34  push    rdi
0x18006dc35  lea     rbp, [rsp-37h]
0x18006dc3a  sub     rsp, 0B8h
0x18006dc41  mov     rax, cs:__security_cookie
0x18006dc48  xor     rax, rsp
0x18006dc4b  mov     [rbp+4Fh+var_30], rax
0x18006dc4f  mov     rbx, [rbp+4Fh+EventDescriptor]
0x18006dc53  xor     eax, eax
0x18006dc55  mov     rdi, rdx
0x18006dc58  mov     [rbp+4Fh+var_98], 1
0x18006dc5f  mov     rsi, rcx
0x18006dc62  mov     [rbp+4Fh+var_A0], ax
0x18006dc66  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006dc6d  mov     rdx, rbx; EventDescriptor
0x18006dc70  mov     [rbp+4Fh+var_9C], ax
0x18006dc74  call    cs:__imp_EtwEventEnabled
0x18006dc7b  nop     dword ptr [rax+rax+00h]
0x18006dc80  test    al, al
0x18006dc82  jnz     short loc_18006DC8B
0x18006dc84  xor     eax, eax
0x18006dc86  jmp     loc_18006DD3D
0x18006dc8b  movzx   ecx, word ptr [rsi]
0x18006dc8e  movzx   edx, word ptr [rdi]
0x18006dc91  movzx   eax, cx
0x18006dc94  shr     ax, 1
0x18006dc97  mov     [rbp+4Fh+var_A0], ax
0x18006dc9b  movzx   eax, dx
0x18006dc9e  shr     ax, 1
0x18006dca1  mov     [rbp+4Fh+var_9C], ax
0x18006dca5  lea     rax, [rbp+4Fh+var_A0]
0x18006dca9  mov     [rbp+4Fh+var_90.Ptr], rax
0x18006dcad  mov     rax, [rsi+8]
0x18006dcb1  mov     [rbp+4Fh+var_80], rax
0x18006dcb5  lea     rax, [rbp+4Fh+var_9C]
0x18006dcb9  mov     [rbp+4Fh+var_70], rax
0x18006dcbd  mov     rax, [rdi+8]
0x18006dcc1  mov     [rbp+4Fh+var_60], rax
0x18006dcc5  lea     rax, [rbp+4Fh+var_98]
0x18006dcc9  mov     [rbp+4Fh+var_50], rax
0x18006dccd  lea     rax, [rbp+4Fh+arg_18]
0x18006dcd1  mov     [rbp+4Fh+var_40], rax
0x18006dcd5  mov     qword ptr [rbp+4Fh+var_90.Size], 2
0x18006dcdd  mov     [rbp+4Fh+var_78], ecx
0x18006dce0  mov     [rbp+4Fh+var_74], 0
0x18006dce7  mov     [rbp+4Fh+var_68], 2
0x18006dcef  mov     [rbp+4Fh+var_58], edx
0x18006dcf2  mov     [rbp+4Fh+var_54], 0
0x18006dcf9  mov     [rbp+4Fh+var_48], 1
0x18006dd01  mov     [rbp+4Fh+var_38], 4
0x18006dd09  call    cs:__imp_IoGetActivityIdThread
0x18006dd10  nop     dword ptr [rax+rax+00h]
0x18006dd15  lea     rcx, [rbp+4Fh+var_90]
0x18006dd19  mov     r9d, 6; UserDataCount
0x18006dd1f  mov     [rsp+0D0h+UserData], rcx; UserData
0x18006dd24  mov     r8, rax; ActivityId
0x18006dd27  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006dd2e  mov     rdx, rbx; EventDescriptor
0x18006dd31  call    cs:__imp_EtwWrite
0x18006dd38  nop     dword ptr [rax+rax+00h]
0x18006dd3d  mov     rcx, [rbp+4Fh+var_30]
0x18006dd41  xor     rcx, rsp; StackCookie
0x18006dd44  call    __security_check_cookie
0x18006dd49  add     rsp, 0B8h
0x18006dd50  pop     rdi
0x18006dd51  pop     rsi
0x18006dd52  pop     rbx
0x18006dd53  pop     rbp
0x18006dd54  retn
```
