# CptpQuirkSendEtwEvent

- ea: `0x18001c5a0`
- end: `0x18001c83f`
- name: `CptpQuirkSendEtwEvent`
- size: `671`
- prototype: `__int64 __usercall@<rax>(wchar_t *String@<rcx>, wchar_t *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ab70`
- `0x18001b4f0`
- `0x18001b648`
- `0x18001bbe0`
- `0x180077f20`

## callees

- `0x18001c5a0`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001c618`
- `ntdll!EtwEventEnabled` at `0x18001c618`
- `ntdll!EtwEventWrite` at `0x18001c7c5`
- `ntdll!EtwEventWrite` at `0x18001c7c5`
- `ntdll!wcslen` at `0x18001c6ec`
- `ntdll!wcslen` at `0x18001c71a`
- `ntdll!wcslen` at `0x18001c767`
- `ntdll!wcslen` at `0x18001c78b`
- `ntdll!wcslen` at `0x18001c6ec`
- `ntdll!wcslen` at `0x18001c71a`
- `ntdll!wcslen` at `0x18001c767`
- `ntdll!wcslen` at `0x18001c78b`
- `KERNELBASE!GetPackageFullName` at `0x18001c80b`
- `KERNELBASE!GetPackageFullName` at `0x18001c80b`
- `KERNELBASE!GetCurrentPackageFullName` at `0x18001c666`
- `KERNELBASE!GetCurrentPackageFullName` at `0x18001c666`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001c696`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001c696`

## pseudocode

```c
__int64 __fastcall CptpQuirkSendEtwEvent(wchar_t *String, int a2, void *a3, WCHAR *a4, wchar_t *Stringa)
{
  wchar_t *v5; // rbx
  __int64 result; // rax
  LONG CurrentPackageFullName; // eax
  const wchar_t *v11; // r15
  DWORD ProcessId; // eax
  bool v13; // zf
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _WORD v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 packageFullNameLength; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v20; // [rsp+28h] [rbp-D8h] BYREF
  BOOL v21; // [rsp+2Ch] [rbp-D4h] BYREF
  _QWORD v22[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+5Ch] [rbp-A4h]
  wchar_t *v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+6Ch] [rbp-94h]
  int *v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  BOOL *v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  WCHAR *v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  WCHAR packageFullName[128]; // [rsp+B0h] [rbp-50h] BYREF
  int v39; // [rsp+208h] [rbp+108h] BYREF

  v39 = a2;
  v5 = Stringa;
  result = 0;
  v20 = 0;
  packageFullNameLength = 0;
  v18[0] = 0;
  v21 = 0;
  if ( !QuirksEtwProvider || a3 == (void *)-1LL && (String[276] & 0x10) != 0 )
    return result;
  result = EtwEventEnabled(QuirksEtwProvider, QUIRKS_DEBUG_EVENT);
  if ( !(_BYTE)result )
    return result;
  if ( !a3 )
  {
    if ( a4 )
      goto LABEL_10;
    goto LABEL_22;
  }
  if ( !a4 )
  {
    packageFullNameLength = 128;
    memset_0(packageFullName, 0, sizeof(packageFullName));
    if ( a3 == (void *)-1LL )
      CurrentPackageFullName = GetCurrentPackageFullName(&packageFullNameLength, packageFullName);
    else
      CurrentPackageFullName = GetPackageFullName(a3, &packageFullNameLength, packageFullName);
    if ( !CurrentPackageFullName )
    {
      a4 = packageFullName;
      goto LABEL_10;
    }
LABEL_22:
    a4 = v18;
  }
LABEL_10:
  v11 = v18;
  if ( v5 )
    v11 = v5;
  if ( a3 )
    ProcessId = GetProcessId(a3);
  else
    ProcessId = 0;
  v13 = (String[276] & 3) == 0;
  v20 = ProcessId;
  v22[1] = 4;
  v21 = !v13;
  v18[0] = 0;
  v22[0] = &v20;
  v22[2] = String + 138;
  v22[3] = 4;
  v14 = wcslen(String);
  v22[4] = String;
  v24 = 0;
  v23 = 2 * v14 + 2;
  v15 = wcslen(String + 148);
  v25 = String + 148;
  v27 = 0;
  v29 = 1;
  v31 = 1;
  v26 = 2 * v15 + 2;
  v28 = &v39;
  v30 = &v21;
  v16 = wcslen(a4);
  v32 = a4;
  v34 = 0;
  v33 = 2 * v16 + 2;
  v17 = wcslen(v11);
  v35 = v11;
  v37 = 0;
  v36 = 2 * v17 + 2;
  result = EtwEventWrite(QuirksEtwProvider, QUIRKS_DEBUG_EVENT, 8, v22);
  if ( a3 == (void *)-1LL )
    *((_DWORD *)String + 138) |= 0x10u;
  return result;
}

```

## disassembly

```asm
0x18001c5a0  mov     [rsp-8+arg_8], edx
0x18001c5a4  push    rbp
0x18001c5a5  push    rbx
0x18001c5a6  push    rsi
0x18001c5a7  push    rdi
0x18001c5a8  push    r14
0x18001c5aa  push    r15
0x18001c5ac  lea     rbp, [rsp-0C8h]
0x18001c5b4  sub     rsp, 1C8h
0x18001c5bb  mov     rax, cs:__security_cookie
0x18001c5c2  xor     rax, rsp
0x18001c5c5  mov     [rbp+0F0h+var_40], rax
0x18001c5cc  mov     rbx, [rbp+0F0h+String]
0x18001c5d3  xor     eax, eax
0x18001c5d5  mov     r14, rcx
0x18001c5d8  mov     [rsp+1F0h+var_1C8], 0
0x18001c5e0  mov     rcx, cs:QuirksEtwProvider
0x18001c5e7  mov     rdi, r9
0x18001c5ea  mov     [rsp+1F0h+packageFullNameLength], 0
0x18001c5f2  mov     rsi, r8
0x18001c5f5  mov     [rsp+1F0h+var_1D0], ax
0x18001c5fa  mov     [rsp+1F0h+var_1C4], eax
0x18001c5fe  test    rcx, rcx
0x18001c601  jz      loc_18001C7DF
0x18001c607  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001c60b  jz      loc_18001C81C
0x18001c611  lea     rdx, QUIRKS_DEBUG_EVENT
0x18001c618  call    cs:__imp_EtwEventEnabled
0x18001c61f  nop     dword ptr [rax+rax+00h]
0x18001c624  test    al, al
0x18001c626  jz      loc_18001C7DF
0x18001c62c  test    rsi, rsi
0x18001c62f  jz      loc_18001C82C
0x18001c635  test    rdi, rdi
0x18001c638  jnz     short loc_18001C67E
0x18001c63a  xor     edx, edx; Val
0x18001c63c  mov     [rsp+1F0h+packageFullNameLength], 80h
0x18001c644  mov     r8d, 100h; Size
0x18001c64a  lea     rcx, [rbp+0F0h+packageFullName]; void *
0x18001c64e  call    memset_0
0x18001c653  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001c657  jnz     loc_18001C7FF
0x18001c65d  lea     rdx, [rbp+0F0h+packageFullName]; packageFullName
0x18001c661  lea     rcx, [rsp+1F0h+packageFullNameLength]; packageFullNameLength
0x18001c666  call    cs:__imp_GetCurrentPackageFullName
0x18001c66d  nop     dword ptr [rax+rax+00h]
0x18001c672  test    eax, eax
0x18001c674  jnz     loc_18001C835
0x18001c67a  lea     rdi, [rbp+0F0h+packageFullName]
0x18001c67e  test    rbx, rbx
0x18001c681  lea     r15, [rsp+1F0h+var_1D0]
0x18001c686  cmovnz  r15, rbx
0x18001c68a  test    rsi, rsi
0x18001c68d  jnz     short loc_18001C693
0x18001c68f  xor     eax, eax
0x18001c691  jmp     short loc_18001C6A2
0x18001c693  mov     rcx, rsi; Process
0x18001c696  call    cs:__imp_GetProcessId
0x18001c69d  nop     dword ptr [rax+rax+00h]
0x18001c6a2  test    byte ptr [r14+228h], 3
0x18001c6aa  mov     rcx, r14; String
0x18001c6ad  mov     [rsp+1F0h+var_1C8], eax
0x18001c6b1  mov     eax, 0
0x18001c6b6  setnz   al
0x18001c6b9  mov     [rsp+1F0h+var_1B8], 4
0x18001c6c2  mov     [rsp+1F0h+var_1C4], eax
0x18001c6c6  xor     eax, eax
0x18001c6c8  mov     [rsp+1F0h+var_1D0], ax
0x18001c6cd  lea     rax, [rsp+1F0h+var_1C8]
0x18001c6d2  mov     [rsp+1F0h+var_1C0], rax
0x18001c6d7  lea     rax, [r14+114h]
0x18001c6de  mov     [rsp+1F0h+var_1B0], rax
0x18001c6e3  mov     [rsp+1F0h+var_1A8], 4
0x18001c6ec  call    cs:__imp_wcslen
0x18001c6f3  nop     dword ptr [rax+rax+00h]
0x18001c6f8  lea     rbx, [r14+128h]
0x18001c6ff  mov     [rsp+1F0h+var_1A0], r14
0x18001c704  mov     rcx, rbx; String
0x18001c707  mov     [rsp+1F0h+var_194], 0
0x18001c70f  lea     eax, ds:2[rax*2]
0x18001c716  mov     [rsp+1F0h+var_198], eax
0x18001c71a  call    cs:__imp_wcslen
0x18001c721  nop     dword ptr [rax+rax+00h]
0x18001c726  mov     rcx, rdi; String
0x18001c729  mov     [rsp+1F0h+var_190], rbx
0x18001c72e  mov     [rsp+1F0h+var_184], 0
0x18001c736  mov     [rsp+1F0h+var_178], 1
0x18001c73f  lea     eax, ds:2[rax*2]
0x18001c746  mov     [rbp+0F0h+var_168], 1
0x18001c74e  mov     [rsp+1F0h+var_188], eax
0x18001c752  lea     rax, [rbp+0F0h+arg_8]
0x18001c759  mov     [rsp+1F0h+var_180], rax
0x18001c75e  lea     rax, [rsp+1F0h+var_1C4]
0x18001c763  mov     [rbp+0F0h+var_170], rax
0x18001c767  call    cs:__imp_wcslen
0x18001c76e  nop     dword ptr [rax+rax+00h]
0x18001c773  mov     rcx, r15; String
0x18001c776  mov     [rbp+0F0h+var_160], rdi
0x18001c77a  mov     [rbp+0F0h+var_154], 0
0x18001c781  lea     eax, ds:2[rax*2]
0x18001c788  mov     [rbp+0F0h+var_158], eax
0x18001c78b  call    cs:__imp_wcslen
0x18001c792  nop     dword ptr [rax+rax+00h]
0x18001c797  mov     rcx, cs:QuirksEtwProvider
0x18001c79e  lea     r9, [rsp+1F0h+var_1C0]
0x18001c7a3  mov     r8d, 8
0x18001c7a9  mov     [rbp+0F0h+var_150], r15
0x18001c7ad  lea     rdx, QUIRKS_DEBUG_EVENT
0x18001c7b4  mov     [rbp+0F0h+var_144], 0
0x18001c7bb  lea     eax, ds:2[rax*2]
0x18001c7c2  mov     [rbp+0F0h+var_148], eax
0x18001c7c5  call    cs:__imp_EtwEventWrite
0x18001c7cc  nop     dword ptr [rax+rax+00h]
0x18001c7d1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001c7d5  jnz     short loc_18001C7DF
0x18001c7d7  or      dword ptr [r14+228h], 10h
0x18001c7df  mov     rcx, [rbp+0F0h+var_40]
0x18001c7e6  xor     rcx, rsp; StackCookie
0x18001c7e9  call    __security_check_cookie
0x18001c7ee  add     rsp, 1C8h
0x18001c7f5  pop     r15
0x18001c7f7  pop     r14
0x18001c7f9  pop     rdi
0x18001c7fa  pop     rsi
0x18001c7fb  pop     rbx
0x18001c7fc  pop     rbp
0x18001c7fd  retn
0x18001c7ff  lea     r8, [rbp+0F0h+packageFullName]; packageFullName
0x18001c803  mov     rcx, rsi; hProcess
0x18001c806  lea     rdx, [rsp+1F0h+packageFullNameLength]; packageFullNameLength
0x18001c80b  call    cs:__imp_GetPackageFullName
0x18001c812  nop     dword ptr [rax+rax+00h]
0x18001c817  jmp     loc_18001C672
0x18001c81c  test    byte ptr [r14+228h], 10h
0x18001c824  jz      loc_18001C611
0x18001c82a  jmp     short loc_18001C7DF
0x18001c82c  test    rdi, rdi
0x18001c82f  jnz     loc_18001C67E
0x18001c835  lea     rdi, [rsp+1F0h+var_1D0]
0x18001c83a  jmp     loc_18001C67E
```
