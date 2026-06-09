# I_OpenBlob(ulong,uchar *,ulong)

- ea: `0x180039d5c`
- end: `0x180039dea`
- name: `?I_OpenBlob@@YAPEAXKPEAEK@Z`
- size: `142`
- prototype: `void *__fastcall(DWORD, unsigned __int8 *, DWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180035384`
- `0x180036160`
- `0x180039994`
- `0x180039df0`

## callees

- `0x180039d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039dcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039dcf`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180039d98`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180039d98`
- `CRYPT32!CryptMsgUpdate` at `0x180039db5`
- `CRYPT32!CryptMsgUpdate` at `0x180039db5`
- `CRYPT32!CryptMsgClose` at `0x180039dc2`
- `CRYPT32!CryptMsgClose` at `0x180039dc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall I_OpenBlob(DWORD a1, unsigned __int8 *a2, DWORD a3)
{
  HCRYPTMSG v5; // rax
  void *v6; // rbx

  if ( !a1 || !a2 || !a3 )
  {
    SetLastError(0xA0u);
    return 0;
  }
  v5 = CryptMsgOpenToDecode(a1, 0, 0, 0, 0, 0);
  v6 = v5;
  if ( v5 && !CryptMsgUpdate(v5, a2, a3, 1) )
  {
    CryptMsgClose(v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180039d5c  mov     rax, rsp
0x180039d5f  mov     [rax+8], rbx
0x180039d63  mov     [rax+10h], rsi
0x180039d67  push    rdi
0x180039d68  sub     rsp, 30h
0x180039d6c  mov     edi, r8d
0x180039d6f  mov     rsi, rdx
0x180039d72  test    ecx, ecx
0x180039d74  jz      short loc_180039DCA
0x180039d76  test    rdx, rdx
0x180039d79  jz      short loc_180039DCA
0x180039d7b  test    r8d, r8d
0x180039d7e  jz      short loc_180039DCA
0x180039d80  mov     qword ptr [rax-10h], 0
0x180039d88  xor     r9d, r9d; hCryptProv
0x180039d8b  xor     r8d, r8d; dwMsgType
0x180039d8e  mov     qword ptr [rax-18h], 0
0x180039d96  xor     edx, edx; dwFlags
0x180039d98  call    cs:__imp_CryptMsgOpenToDecode
0x180039d9e  mov     rbx, rax
0x180039da1  test    rax, rax
0x180039da4  jz      short loc_180039DD7
0x180039da6  mov     r9d, 1; fFinal
0x180039dac  mov     r8d, edi; cbData
0x180039daf  mov     rdx, rsi; pbData
0x180039db2  mov     rcx, rax; hCryptMsg
0x180039db5  call    cs:__imp_CryptMsgUpdate
0x180039dbb  test    eax, eax
0x180039dbd  jnz     short loc_180039DD7
0x180039dbf  mov     rcx, rbx; hCryptMsg
0x180039dc2  call    cs:__imp_CryptMsgClose
0x180039dc8  jmp     short loc_180039DD5
0x180039dca  mov     ecx, 0A0h; dwErrCode
0x180039dcf  call    cs:__imp_SetLastError
0x180039dd5  xor     ebx, ebx
0x180039dd7  mov     rsi, [rsp+38h+arg_8]
0x180039ddc  mov     rax, rbx
0x180039ddf  mov     rbx, [rsp+38h+arg_0]
0x180039de4  add     rsp, 30h
0x180039de8  pop     rdi
0x180039de9  retn
```
