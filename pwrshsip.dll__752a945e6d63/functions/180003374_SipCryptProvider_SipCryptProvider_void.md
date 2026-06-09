# SipCryptProvider::~SipCryptProvider(void)

- ea: `0x180003374`
- end: `0x1800033b3`
- name: `??1SipCryptProvider@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(SipCryptProvider *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dd4`
- `0x180003ed8`
- `0x180004220`
- `0x1800042ec`
- `0x1800050b0`

## callees

- `0x180003374`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800033a2`
- `KERNEL32!SetLastError` at `0x1800033a2`
- `KERNEL32!GetLastError` at `0x180003388`
- `KERNEL32!GetLastError` at `0x180003388`
- `ADVAPI32!CryptReleaseContext` at `0x180003396`
- `ADVAPI32!CryptReleaseContext` at `0x180003396`

## pseudocode

```c
void __fastcall SipCryptProvider::~SipCryptProvider(SipCryptProvider *this)
{
  DWORD LastError; // edi

  if ( *((_QWORD *)this + 1) )
  {
    LastError = GetLastError();
    if ( !CryptReleaseContext(*((_QWORD *)this + 1), 0) )
      SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180003374  mov     [rsp+arg_0], rbx
0x180003379  push    rdi
0x18000337a  sub     rsp, 20h
0x18000337e  cmp     qword ptr [rcx+8], 0
0x180003383  mov     rbx, rcx
0x180003386  jz      short loc_1800033A8
0x180003388  call    cs:__imp_GetLastError
0x18000338e  mov     rcx, [rbx+8]; hProv
0x180003392  xor     edx, edx; dwFlags
0x180003394  mov     edi, eax
0x180003396  call    cs:__imp_CryptReleaseContext
0x18000339c  test    eax, eax
0x18000339e  jnz     short loc_1800033A8
0x1800033a0  mov     ecx, edi; dwErrCode
0x1800033a2  call    cs:__imp_SetLastError
0x1800033a8  mov     rbx, [rsp+28h+arg_0]
0x1800033ad  add     rsp, 20h
0x1800033b1  pop     rdi
0x1800033b2  retn
```
