# CiLogFileAndCatalogEvent

- ea: `0x1800911bc`
- end: `0x1800912ba`
- name: `CiLogFileAndCatalogEvent`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008f670`

## callees

- `0x18002c0d0`
- `0x1800911bc`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1800911f8`
- `ntoskrnl!EtwEventEnabled` at `0x1800911f8`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009126d`
- `ntoskrnl!IoGetActivityIdThread` at `0x18009126d`
- `ntoskrnl!EtwWrite` at `0x180091295`
- `ntoskrnl!EtwWrite` at `0x180091295`

## pseudocode

```c
NTSTATUS __fastcall CiLogFileAndCatalogEvent(unsigned __int16 *a1, unsigned __int16 *a2, const EVENT_DESCRIPTOR *a3)
{
  unsigned __int16 v7; // ax
  __int64 v8; // rcx
  const GUID *ActivityIdThread; // rax
  __int16 v10; // [rsp+30h] [rbp-29h] BYREF
  __int16 v11; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-19h] BYREF
  __int64 v13; // [rsp+50h] [rbp-9h]
  int v14; // [rsp+58h] [rbp-1h]
  int v15; // [rsp+5Ch] [rbp+3h]
  __int16 *v16; // [rsp+60h] [rbp+7h]
  __int64 v17; // [rsp+68h] [rbp+Fh]
  __int64 v18; // [rsp+70h] [rbp+17h]
  int v19; // [rsp+78h] [rbp+1Fh]
  int v20; // [rsp+7Ch] [rbp+23h]

  v10 = 0;
  v11 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, a3) )
    return 0;
  v7 = *a1;
  v14 = *a1;
  v8 = *a2;
  v10 = v7 >> 1;
  UserData.Ptr = (ULONGLONG)&v10;
  v13 = *((_QWORD *)a1 + 1);
  v11 = (unsigned __int16)v8 >> 1;
  v16 = &v11;
  v18 = *((_QWORD *)a2 + 1);
  *(_QWORD *)&UserData.Size = 2;
  v15 = 0;
  v17 = 2;
  v19 = v8;
  v20 = 0;
  ActivityIdThread = (const GUID *)IoGetActivityIdThread(v8);
  return EtwWrite(g_EtwEventHandle, a3, ActivityIdThread, 4u, &UserData);
}

```

## disassembly

```asm
0x1800911bc  push    rbp
0x1800911be  push    rbx
0x1800911bf  push    rsi
0x1800911c0  push    rdi
0x1800911c1  lea     rbp, [rsp-3Fh]
0x1800911c6  sub     rsp, 98h
0x1800911cd  mov     rax, cs:__security_cookie
0x1800911d4  xor     rax, rsp
0x1800911d7  mov     [rbp+57h+var_30], rax
0x1800911db  xor     eax, eax
0x1800911dd  mov     rdi, rdx
0x1800911e0  mov     rsi, rcx
0x1800911e3  mov     [rbp+57h+var_80], ax
0x1800911e7  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800911ee  mov     rdx, r8; EventDescriptor
0x1800911f1  mov     [rbp+57h+var_7C], ax
0x1800911f5  mov     rbx, r8
0x1800911f8  call    cs:__imp_EtwEventEnabled
0x1800911ff  nop     dword ptr [rax+rax+00h]
0x180091204  test    al, al
0x180091206  jnz     short loc_18009120F
0x180091208  xor     eax, eax
0x18009120a  jmp     loc_1800912A1
0x18009120f  movzx   ecx, word ptr [rsi]
0x180091212  movzx   eax, cx
0x180091215  mov     [rbp+57h+var_58], ecx
0x180091218  movzx   ecx, word ptr [rdi]
0x18009121b  shr     ax, 1
0x18009121e  mov     [rbp+57h+var_80], ax
0x180091222  lea     rax, [rbp+57h+var_80]
0x180091226  mov     [rbp+57h+var_70.Ptr], rax
0x18009122a  mov     rax, [rsi+8]
0x18009122e  mov     [rbp+57h+var_60], rax
0x180091232  movzx   eax, cx
0x180091235  shr     ax, 1
0x180091238  mov     [rbp+57h+var_7C], ax
0x18009123c  lea     rax, [rbp+57h+var_7C]
0x180091240  mov     [rbp+57h+var_50], rax
0x180091244  mov     rax, [rdi+8]
0x180091248  mov     [rbp+57h+var_40], rax
0x18009124c  mov     qword ptr [rbp+57h+var_70.Size], 2
0x180091254  mov     [rbp+57h+var_54], 0
0x18009125b  mov     [rbp+57h+var_48], 2
0x180091263  mov     [rbp+57h+var_38], ecx
0x180091266  mov     [rbp+57h+var_34], 0
0x18009126d  call    cs:__imp_IoGetActivityIdThread
0x180091274  nop     dword ptr [rax+rax+00h]
0x180091279  lea     rcx, [rbp+57h+var_70]
0x18009127d  mov     r9d, 4; UserDataCount
0x180091283  mov     [rsp+0B0h+UserData], rcx; UserData
0x180091288  mov     r8, rax; ActivityId
0x18009128b  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180091292  mov     rdx, rbx; EventDescriptor
0x180091295  call    cs:__imp_EtwWrite
0x18009129c  nop     dword ptr [rax+rax+00h]
0x1800912a1  mov     rcx, [rbp+57h+var_30]
0x1800912a5  xor     rcx, rsp; StackCookie
0x1800912a8  call    __security_check_cookie
0x1800912ad  add     rsp, 98h
0x1800912b4  pop     rdi
0x1800912b5  pop     rsi
0x1800912b6  pop     rbx
0x1800912b7  pop     rbp
0x1800912b8  retn
```
