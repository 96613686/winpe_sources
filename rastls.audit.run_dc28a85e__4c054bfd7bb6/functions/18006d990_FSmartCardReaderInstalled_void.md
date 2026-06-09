# FSmartCardReaderInstalled(void)

- ea: `0x18006d990`
- end: `0x18006da0d`
- name: `?FSmartCardReaderInstalled@@YAHXZ`
- size: `125`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180074168`

## callees

- `0x18006d990`

## import_xrefs

- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18006d9b5`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18006d9b5`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18006d9d4`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18006d9d4`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18006d9f8`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18006d9f8`

## pseudocode

```c
_BOOL8 FSmartCardReaderInstalled(void)
{
  BOOL v0; // ebx
  DWORD pcchReaders; // [rsp+30h] [rbp+8h] BYREF
  SCARDCONTEXT phContext; // [rsp+38h] [rbp+10h] BYREF

  pcchReaders = 0;
  phContext = 0;
  v0 = 0;
  if ( !SCardEstablishContext(0, 0, 0, &phContext) && !SCardListReadersW(phContext, 0, 0, &pcchReaders) )
    v0 = pcchReaders > 4;
  if ( phContext )
    SCardReleaseContext(phContext);
  return v0;
}

```

## disassembly

```asm
0x18006d990  push    rbx
0x18006d992  sub     rsp, 20h
0x18006d996  lea     r9, [rsp+28h+phContext]; phContext
0x18006d99b  mov     [rsp+28h+pcchReaders], 0
0x18006d9a3  xor     r8d, r8d; pvReserved2
0x18006d9a6  mov     [rsp+28h+phContext], 0
0x18006d9af  xor     edx, edx; pvReserved1
0x18006d9b1  xor     ecx, ecx; dwScope
0x18006d9b3  xor     ebx, ebx
0x18006d9b5  call    cs:__imp_SCardEstablishContext
0x18006d9bc  nop     dword ptr [rax+rax+00h]
0x18006d9c1  test    eax, eax
0x18006d9c3  jnz     short loc_18006D9EE
0x18006d9c5  mov     rcx, [rsp+28h+phContext]; hContext
0x18006d9ca  lea     r9, [rsp+28h+pcchReaders]; pcchReaders
0x18006d9cf  xor     r8d, r8d; mszReaders
0x18006d9d2  xor     edx, edx; mszGroups
0x18006d9d4  call    cs:__imp_SCardListReadersW
0x18006d9db  nop     dword ptr [rax+rax+00h]
0x18006d9e0  test    eax, eax
0x18006d9e2  jnz     short loc_18006D9EE
0x18006d9e4  cmp     [rsp+28h+pcchReaders], 4
0x18006d9e9  jbe     short loc_18006D9EE
0x18006d9eb  lea     ebx, [rax+1]
0x18006d9ee  mov     rcx, [rsp+28h+phContext]; hContext
0x18006d9f3  test    rcx, rcx
0x18006d9f6  jz      short loc_18006DA04
0x18006d9f8  call    cs:__imp_SCardReleaseContext
0x18006d9ff  nop     dword ptr [rax+rax+00h]
0x18006da04  mov     eax, ebx
0x18006da06  add     rsp, 20h
0x18006da0a  pop     rbx
0x18006da0b  retn
```
