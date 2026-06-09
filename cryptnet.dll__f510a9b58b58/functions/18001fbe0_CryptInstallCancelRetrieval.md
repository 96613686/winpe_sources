# CryptInstallCancelRetrieval

- ea: `0x18001fbe0`
- end: `0x18001fc68`
- name: `CryptInstallCancelRetrieval`
- size: `136`
- prototype: `BOOL __stdcall(PFN_CRYPT_CANCEL_RETRIEVAL pfnCancel, const void *pvArg, DWORD dwFlags, void *pvReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x18000a990`
- `0x180010b00`
- `0x18001fbe0`
- `0x18001fc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fbff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fbff`
- `CRYPT32!I_CryptSetTls` at `0x18001fc3d`
- `CRYPT32!I_CryptSetTls` at `0x18001fc3d`

## pseudocode

```c
BOOL __stdcall CryptInstallCancelRetrieval(
        PFN_CRYPT_CANCEL_RETRIEVAL pfnCancel,
        const void *pvArg,
        DWORD dwFlags,
        void *pvReserved)
{
  DWORD v6; // ecx
  PFN_CRYPT_CANCEL_RETRIEVAL *v7; // rax
  PFN_CRYPT_CANCEL_RETRIEVAL *v8; // rbx

  if ( !pfnCancel )
  {
    v6 = -2147024809;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  v7 = (PFN_CRYPT_CANCEL_RETRIEVAL *)PkiAlloc(0x10u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_3;
  }
  *v7 = pfnCancel;
  v7[1] = (PFN_CRYPT_CANCEL_RETRIEVAL)pvArg;
  if ( CryptUninstallCancelRetrieval(0, 0) && (unsigned int)I_CryptSetTls((unsigned int)hCryptNetCancelTls, v8) )
    return 1;
  operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x18001fbe0  mov     [rsp+arg_0], rbx
0x18001fbe5  mov     [rsp+arg_8], rsi
0x18001fbea  push    rdi
0x18001fbeb  sub     rsp, 20h
0x18001fbef  mov     rsi, rdx
0x18001fbf2  mov     rdi, rcx
0x18001fbf5  test    rcx, rcx
0x18001fbf8  jnz     short loc_18001FC07
0x18001fbfa  mov     ecx, 80070057h; dwErrCode
0x18001fbff  call    cs:__imp_SetLastError
0x18001fc05  jmp     short loc_18001FC56
0x18001fc07  mov     ecx, 10h; uBytes
0x18001fc0c  call    PkiAlloc
0x18001fc11  mov     rbx, rax
0x18001fc14  test    rax, rax
0x18001fc17  jnz     short loc_18001FC20
0x18001fc19  mov     ecx, 8007000Eh
0x18001fc1e  jmp     short loc_18001FBFF
0x18001fc20  xor     edx, edx; pvReserved
0x18001fc22  mov     [rax], rdi
0x18001fc25  xor     ecx, ecx; dwFlags
0x18001fc27  mov     [rax+8], rsi
0x18001fc2b  call    CryptUninstallCancelRetrieval
0x18001fc30  test    eax, eax
0x18001fc32  jz      short loc_18001FC4E
0x18001fc34  mov     ecx, cs:hCryptNetCancelTls
0x18001fc3a  mov     rdx, rbx
0x18001fc3d  call    cs:__imp_I_CryptSetTls
0x18001fc43  test    eax, eax
0x18001fc45  jz      short loc_18001FC4E
0x18001fc47  mov     eax, 1
0x18001fc4c  jmp     short loc_18001FC58
0x18001fc4e  mov     rcx, rbx; hMem
0x18001fc51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fc56  xor     eax, eax
0x18001fc58  mov     rbx, [rsp+28h+arg_0]
0x18001fc5d  mov     rsi, [rsp+28h+arg_8]
0x18001fc62  add     rsp, 20h
0x18001fc66  pop     rdi
0x18001fc67  retn
```
