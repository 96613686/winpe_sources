# CreateTemporaryJobPartition

- ea: `0x1400c91d0`
- end: `0x1400c93ad`
- name: `CreateTemporaryJobPartition`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400c9a50`

## callees

- `0x140004268`
- `0x140058f50`
- `0x1400c91d0`

## import_xrefs

- `ntoskrnl!ZwManagePartition` at `0x1400c9346`
- `ntoskrnl!ZwManagePartition` at `0x1400c9346`
- `ntoskrnl!ObCloseHandle` at `0x1400c92de`
- `ntoskrnl!ObCloseHandle` at `0x1400c92de`
- `ntoskrnl!ZwOpenPartition` at `0x1400c9248`
- `ntoskrnl!ZwOpenPartition` at `0x1400c9248`
- `ntoskrnl!ZwCreatePartition` at `0x1400c926d`
- `ntoskrnl!ZwCreatePartition` at `0x1400c926d`
- `watchdog!WdLogSingleEntry0` at `0x1400c9288`
- `watchdog!WdLogSingleEntry0` at `0x1400c9288`
- `watchdog!WdLogSingleEntry1` at `0x1400c9361`
- `watchdog!WdLogSingleEntry1` at `0x1400c9361`

## string_xrefs

- `0x1400c929d`: `Failed to open or create temporary test partition`

## pseudocode

```c
__int64 __fastcall CreateTemporaryJobPartition(_QWORD *a1)
{
  __int64 v2; // rdi
  int v3; // ecx
  int v4; // r8d
  HANDLE v5; // rax
  int v7; // eax
  int v8; // ecx
  int v9; // r8d
  HANDLE Handle; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v11[4]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v12; // [rsp+78h] [rbp+1Fh]
  __int128 v13; // [rsp+88h] [rbp+2Fh] BYREF
  __int128 v14; // [rsp+98h] [rbp+3Fh] BYREF

  Handle = 0;
  v14 = 0;
  v11[0] = 48;
  v11[3] = 576;
  v13 = *(_OWORD *)L"DF";
  v11[1] = 0;
  v11[2] = &v13;
  v12 = 0;
  LODWORD(v2) = ZwOpenPartition(&Handle, 2031619, v11);
  if ( (_DWORD)v2 == -1073741772 )
    LODWORD(v2) = ZwCreatePartition(0, &Handle, 2031619, v11);
  if ( (int)v2 >= 0 )
  {
    *(_QWORD *)&v14 = 0x2000;
    *((_QWORD *)&v14 + 1) = 0x11FFFFFFFFLL;
    v7 = ZwManagePartition(Handle, -2, 1, &v14, 16);
    v2 = v7;
    if ( v7 < 0 )
    {
      WdLogSingleEntry1(1, v7);
      WdLogGlobalForLineNumber = 457;
      DxgkLogInternalTriageEvent(
        v8,
        0x40000,
        v9,
        (unsigned int)L"Failed to transfer pages to test partition, Status=0x%x",
        v2,
        0,
        0,
        0);
      return (unsigned int)v2;
    }
    goto LABEL_6;
  }
  WdLogSingleEntry0(1);
  WdLogGlobalForLineNumber = 438;
  DxgkLogInternalTriageEvent(
    v3,
    0x40000,
    v4,
    (unsigned int)L"Failed to open or create temporary test partition",
    438,
    0,
    0,
    0);
  v5 = Handle;
  if ( Handle )
  {
    ObCloseHandle(Handle, 0);
LABEL_6:
    v5 = Handle;
  }
  *a1 = v5;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400c91d0  mov     [rsp-8+arg_8], rbx
0x1400c91d5  mov     [rsp-8+arg_10], rdi
0x1400c91da  push    rbp
0x1400c91db  lea     rbp, [rsp-57h]
0x1400c91e0  sub     rsp, 0B0h
0x1400c91e7  mov     rax, cs:__security_cookie
0x1400c91ee  xor     rax, rsp
0x1400c91f1  mov     [rbp+57h+var_8], rax
0x1400c91f5  xorps   xmm0, xmm0
0x1400c91f8  mov     [rbp+57h+Handle], 0
0x1400c9200  movups  [rbp+57h+var_18], xmm0
0x1400c9204  mov     rbx, rcx
0x1400c9207  lea     rax, [rbp+57h+var_28]
0x1400c920b  movups  xmm0, xmmword ptr cs:aDf; "DF"
0x1400c9212  lea     r8, [rbp+57h+var_58]
0x1400c9216  mov     [rbp+57h+var_58], 30h ; '0'
0x1400c921e  mov     edx, 1F0003h
0x1400c9223  mov     [rbp+57h+var_40], 240h
0x1400c922b  movdqu  [rbp+57h+var_28], xmm0
0x1400c9230  mov     [rbp+57h+var_50], 0
0x1400c9238  lea     rcx, [rbp+57h+Handle]
0x1400c923c  xorps   xmm0, xmm0
0x1400c923f  mov     [rbp+57h+var_48], rax
0x1400c9243  movdqu  [rbp+57h+var_38], xmm0
0x1400c9248  call    cs:__imp_ZwOpenPartition
0x1400c924f  nop     dword ptr [rax+rax+00h]
0x1400c9254  mov     edi, eax
0x1400c9256  cmp     eax, 0C0000034h
0x1400c925b  jnz     short loc_1400C927B
0x1400c925d  lea     r9, [rbp+57h+var_58]
0x1400c9261  mov     r8d, 1F0003h
0x1400c9267  lea     rdx, [rbp+57h+Handle]
0x1400c926b  xor     ecx, ecx
0x1400c926d  call    cs:__imp_ZwCreatePartition
0x1400c9274  nop     dword ptr [rax+rax+00h]
0x1400c9279  mov     edi, eax
0x1400c927b  test    edi, edi
0x1400c927d  jns     loc_1400C9315
0x1400c9283  mov     ecx, 1
0x1400c9288  call    cs:__imp_WdLogSingleEntry0
0x1400c928f  nop     dword ptr [rax+rax+00h]
0x1400c9294  mov     [rsp+0B0h+var_78], 0
0x1400c929d  lea     r9, aFailedToOpenOr; "Failed to open or create temporary test"...
0x1400c92a4  mov     eax, 1B6h
0x1400c92a9  mov     [rsp+0B0h+var_80], 0
0x1400c92b2  mov     [rsp+0B0h+var_88], 0
0x1400c92bb  mov     edx, 40000h
0x1400c92c0  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c92c6  mov     [rsp+0B0h+var_90], rax
0x1400c92cb  call    DxgkLogInternalTriageEvent
0x1400c92d0  mov     rax, [rbp+57h+Handle]
0x1400c92d4  test    rax, rax
0x1400c92d7  jz      short loc_1400C92EE
0x1400c92d9  xor     edx, edx; PreviousMode
0x1400c92db  mov     rcx, rax; Handle
0x1400c92de  call    cs:__imp_ObCloseHandle
0x1400c92e5  nop     dword ptr [rax+rax+00h]
0x1400c92ea  mov     rax, [rbp+57h+Handle]
0x1400c92ee  mov     [rbx], rax
0x1400c92f1  mov     eax, edi
0x1400c92f3  mov     rcx, [rbp+57h+var_8]
0x1400c92f7  xor     rcx, rsp; StackCookie
0x1400c92fa  call    __security_check_cookie
0x1400c92ff  lea     r11, [rsp+0B0h+var_s0]
0x1400c9307  mov     rbx, [r11+18h]
0x1400c930b  mov     rdi, [r11+20h]
0x1400c930f  mov     rsp, r11
0x1400c9312  pop     rbp
0x1400c9313  retn
0x1400c9315  mov     rcx, [rbp+57h+Handle]
0x1400c9319  lea     r9, [rbp+57h+var_18]
0x1400c931d  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x1400c9324  mov     qword ptr [rbp+57h+var_18], 2000h
0x1400c932c  mov     dword ptr [rbp+57h+var_18+8], 0FFFFFFFFh
0x1400c9333  mov     dword ptr [rbp+57h+var_18+0Ch], 11h
0x1400c933a  mov     dword ptr [rsp+0B0h+var_90], 10h
0x1400c9342  lea     r8d, [rdx+3]
0x1400c9346  call    cs:__imp_ZwManagePartition
0x1400c934d  nop     dword ptr [rax+rax+00h]
0x1400c9352  movsxd  rdi, eax
0x1400c9355  test    eax, eax
0x1400c9357  jns     short loc_1400C92EA
0x1400c9359  mov     rdx, rdi
0x1400c935c  mov     ecx, 1
0x1400c9361  call    cs:__imp_WdLogSingleEntry1
0x1400c9368  nop     dword ptr [rax+rax+00h]
0x1400c936d  mov     [rsp+0B0h+var_78], 0
0x1400c9376  lea     r9, aFailedToTransf; "Failed to transfer pages to test partit"...
0x1400c937d  mov     [rsp+0B0h+var_80], 0
0x1400c9386  mov     edx, 40000h
0x1400c938b  mov     [rsp+0B0h+var_88], 0
0x1400c9394  mov     [rsp+0B0h+var_90], rdi
0x1400c9399  mov     cs:WdLogGlobalForLineNumber, 1C9h
0x1400c93a3  call    DxgkLogInternalTriageEvent
0x1400c93a8  jmp     loc_1400C92F1
```
