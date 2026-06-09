# FILE_HELPER::CreateFileAndWriteEvent(ushort const *,ushort const *,ulong,ulong,ulong,ulong,void *)

- ea: `0x1800412fc`
- end: `0x1800413de`
- name: `?CreateFileAndWriteEvent@FILE_HELPER@@SAPEAXPEBG0KKKKPEAX@Z`
- size: `226`
- prototype: `HANDLE __fastcall(const unsigned __int16 *, const unsigned __int16 *, char, char, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, char *hTransaction)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007e30`
- `0x180017610`
- `0x18001bf40`
- `0x180021ad0`
- `0x180027e44`
- `0x1800392f0`
- `0x1800473ec`
- `0x18004dfb8`

## callees

- `0x1800412fc`
- `0x180042040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041384`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041355`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041355`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18004137b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18004137b`

## pseudocode

```c
HANDLE __fastcall FILE_HELPER::CreateFileAndWriteEvent(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char a3,
        char a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        char *hTransaction)
{
  int v9; // r15d
  HANDLE FileW; // rax
  HANDLE v11; // rdi
  char LastError; // al
  int v13; // edx
  int v14; // ecx
  int v16; // [rsp+B0h] [rbp+8h]

  v16 = (int)a1;
  v9 = (int)a2;
  if ( hTransaction == (char *)-1LL )
    FileW = CreateFileW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  else
    FileW = CreateFileTransactedW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0, hTransaction, 0, 0);
  v11 = FileW;
  LastError = GetLastError();
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
    McTemplateU0zzddddtpd_EtwEventWriteTransfer(
      v14,
      v13,
      v16,
      v9,
      a3,
      a4,
      dwCreationDisposition,
      dwFlagsAndAttributes,
      hTransaction + 1 != 0,
      (char)v11,
      LastError);
  return v11;
}

```

## disassembly

```asm
0x1800412fc  mov     [rsp+arg_0], rcx
0x180041301  push    rbx
0x180041302  push    rbp
0x180041303  push    rsi
0x180041304  push    rdi
0x180041305  push    r12
0x180041307  push    r13
0x180041309  push    r14
0x18004130b  push    r15
0x18004130d  sub     rsp, 68h
0x180041311  mov     rsi, [rsp+0A8h+arg_30]
0x180041319  mov     ebp, r9d
0x18004131c  mov     r12d, [rsp+0A8h+arg_28]
0x180041324  mov     r14d, r8d
0x180041327  mov     r13d, [rsp+0A8h+arg_20]
0x18004132f  mov     r15, rdx
0x180041332  xor     r9d, r9d; lpSecurityAttributes
0x180041335  xor     ebx, ebx
0x180041337  mov     r8d, ebp; dwShareMode
0x18004133a  mov     edx, r14d; dwDesiredAccess
0x18004133d  mov     rcx, r15; lpFileName
0x180041340  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180041344  jnz     short loc_18004135D
0x180041346  mov     [rsp+0A8h+hTemplateFile], rbx; hTemplateFile
0x18004134b  mov     [rsp+0A8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180041350  mov     [rsp+0A8h+dwCreationDisposition], r13d; dwCreationDisposition
0x180041355  call    cs:__imp_CreateFileW
0x18004135b  jmp     short loc_180041381
0x18004135d  mov     [rsp+0A8h+lpExtendedParameter], rbx; lpExtendedParameter
0x180041362  mov     [rsp+0A8h+pusMiniVersion], rbx; pusMiniVersion
0x180041367  mov     [rsp+0A8h+hTransaction], rsi; hTransaction
0x18004136c  mov     [rsp+0A8h+hTemplateFile], rbx; hTemplateFile
0x180041371  mov     [rsp+0A8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180041376  mov     [rsp+0A8h+dwCreationDisposition], r13d; dwCreationDisposition
0x18004137b  call    cs:__imp_CreateFileTransactedW
0x180041381  mov     rdi, rax
0x180041384  call    cs:__imp_GetLastError
0x18004138a  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x180041391  jz      short loc_1800413CA
0x180041393  mov     r8, [rsp+0A8h+arg_0]
0x18004139b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004139f  mov     [rsp+0A8h+var_58], eax
0x1800413a3  mov     r9, r15
0x1800413a6  mov     [rsp+0A8h+lpExtendedParameter], rdi
0x1800413ab  setnz   bl
0x1800413ae  mov     dword ptr [rsp+0A8h+pusMiniVersion], ebx
0x1800413b2  mov     dword ptr [rsp+0A8h+hTransaction], r12d
0x1800413b7  mov     dword ptr [rsp+0A8h+hTemplateFile], r13d
0x1800413bc  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp
0x1800413c0  mov     [rsp+0A8h+dwCreationDisposition], r14d
0x1800413c5  call    McTemplateU0zzddddtpd_EtwEventWriteTransfer
0x1800413ca  mov     rax, rdi
0x1800413cd  add     rsp, 68h
0x1800413d1  pop     r15
0x1800413d3  pop     r14
0x1800413d5  pop     r13
0x1800413d7  pop     r12
0x1800413d9  pop     rdi
0x1800413da  pop     rsi
0x1800413db  pop     rbp
0x1800413dc  pop     rbx
0x1800413dd  retn
```
