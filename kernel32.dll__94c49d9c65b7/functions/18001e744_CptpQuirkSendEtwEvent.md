# CptpQuirkSendEtwEvent

- ea: `0x18001e744`
- end: `0x18001e9ac`
- name: `CptpQuirkSendEtwEvent`
- size: `616`
- prototype: `__int64 __usercall@<rax>(wchar_t *String@<rcx>, wchar_t *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ce20`
- `0x18001d720`
- `0x18001d878`
- `0x18001ddf0`
- `0x180070300`

## callees

- `0x18001e744`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001e7bc`
- `ntdll!EtwEventEnabled` at `0x18001e7bc`
- `ntdll!EtwEventWrite` at `0x18001e93f`
- `ntdll!EtwEventWrite` at `0x18001e93f`
- `ntdll!wcslen` at `0x18001e87e`
- `ntdll!wcslen` at `0x18001e8a6`
- `ntdll!wcslen` at `0x18001e8ed`
- `ntdll!wcslen` at `0x18001e90b`
- `ntdll!wcslen` at `0x18001e87e`
- `ntdll!wcslen` at `0x18001e8a6`
- `ntdll!wcslen` at `0x18001e8ed`
- `ntdll!wcslen` at `0x18001e90b`
- `KERNELBASE!GetPackageFullName` at `0x18001e97e`
- `KERNELBASE!GetPackageFullName` at `0x18001e97e`
- `KERNELBASE!GetCurrentPackageFullName` at `0x18001e804`
- `KERNELBASE!GetCurrentPackageFullName` at `0x18001e804`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001e82e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001e82e`

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
0x18001e744  mov     [rsp-8+arg_8], edx
0x18001e748  push    rbp
0x18001e749  push    rbx
0x18001e74a  push    rsi
0x18001e74b  push    rdi
0x18001e74c  push    r14
0x18001e74e  push    r15
0x18001e750  lea     rbp, [rsp-0C8h]
0x18001e758  sub     rsp, 1C8h
0x18001e75f  mov     rax, cs:__security_cookie
0x18001e766  xor     rax, rsp
0x18001e769  mov     [rbp+0F0h+var_40], rax
0x18001e770  mov     rbx, [rbp+0F0h+String]
0x18001e777  xor     eax, eax
0x18001e779  mov     r14, rcx
0x18001e77c  mov     [rsp+1F0h+var_1C8], 0
0x18001e784  mov     rcx, cs:QuirksEtwProvider
0x18001e78b  mov     rdi, r9
0x18001e78e  mov     [rsp+1F0h+packageFullNameLength], 0
0x18001e796  mov     rsi, r8
0x18001e799  mov     [rsp+1F0h+var_1D0], ax
0x18001e79e  mov     [rsp+1F0h+var_1C4], eax
0x18001e7a2  test    rcx, rcx
0x18001e7a5  jz      loc_18001E953
0x18001e7ab  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001e7af  jz      loc_18001E989
0x18001e7b5  lea     rdx, QUIRKS_DEBUG_EVENT
0x18001e7bc  call    cs:__imp_EtwEventEnabled
0x18001e7c2  test    al, al
0x18001e7c4  jz      loc_18001E953
0x18001e7ca  test    rsi, rsi
0x18001e7cd  jz      loc_18001E999
0x18001e7d3  test    rdi, rdi
0x18001e7d6  jnz     short loc_18001E816
0x18001e7d8  xor     edx, edx; Val
0x18001e7da  mov     [rsp+1F0h+packageFullNameLength], 80h
0x18001e7e2  mov     r8d, 100h; Size
0x18001e7e8  lea     rcx, [rbp+0F0h+packageFullName]; void *
0x18001e7ec  call    memset_0
0x18001e7f1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001e7f5  jnz     loc_18001E972
0x18001e7fb  lea     rdx, [rbp+0F0h+packageFullName]; packageFullName
0x18001e7ff  lea     rcx, [rsp+1F0h+packageFullNameLength]; packageFullNameLength
0x18001e804  call    cs:__imp_GetCurrentPackageFullName
0x18001e80a  test    eax, eax
0x18001e80c  jnz     loc_18001E9A2
0x18001e812  lea     rdi, [rbp+0F0h+packageFullName]
0x18001e816  test    rbx, rbx
0x18001e819  lea     r15, [rsp+1F0h+var_1D0]
0x18001e81e  cmovnz  r15, rbx
0x18001e822  test    rsi, rsi
0x18001e825  jnz     short loc_18001E82B
0x18001e827  xor     eax, eax
0x18001e829  jmp     short loc_18001E834
0x18001e82b  mov     rcx, rsi; Process
0x18001e82e  call    cs:__imp_GetProcessId
0x18001e834  test    byte ptr [r14+228h], 3
0x18001e83c  mov     rcx, r14; String
0x18001e83f  mov     [rsp+1F0h+var_1C8], eax
0x18001e843  mov     eax, 0
0x18001e848  setnz   al
0x18001e84b  mov     [rsp+1F0h+var_1B8], 4
0x18001e854  mov     [rsp+1F0h+var_1C4], eax
0x18001e858  xor     eax, eax
0x18001e85a  mov     [rsp+1F0h+var_1D0], ax
0x18001e85f  lea     rax, [rsp+1F0h+var_1C8]
0x18001e864  mov     [rsp+1F0h+var_1C0], rax
0x18001e869  lea     rax, [r14+114h]
0x18001e870  mov     [rsp+1F0h+var_1B0], rax
0x18001e875  mov     [rsp+1F0h+var_1A8], 4
0x18001e87e  call    cs:__imp_wcslen
0x18001e884  lea     rbx, [r14+128h]
0x18001e88b  mov     [rsp+1F0h+var_1A0], r14
0x18001e890  mov     rcx, rbx; String
0x18001e893  mov     [rsp+1F0h+var_194], 0
0x18001e89b  lea     eax, ds:2[rax*2]
0x18001e8a2  mov     [rsp+1F0h+var_198], eax
0x18001e8a6  call    cs:__imp_wcslen
0x18001e8ac  mov     rcx, rdi; String
0x18001e8af  mov     [rsp+1F0h+var_190], rbx
0x18001e8b4  mov     [rsp+1F0h+var_184], 0
0x18001e8bc  mov     [rsp+1F0h+var_178], 1
0x18001e8c5  lea     eax, ds:2[rax*2]
0x18001e8cc  mov     [rbp+0F0h+var_168], 1
0x18001e8d4  mov     [rsp+1F0h+var_188], eax
0x18001e8d8  lea     rax, [rbp+0F0h+arg_8]
0x18001e8df  mov     [rsp+1F0h+var_180], rax
0x18001e8e4  lea     rax, [rsp+1F0h+var_1C4]
0x18001e8e9  mov     [rbp+0F0h+var_170], rax
0x18001e8ed  call    cs:__imp_wcslen
0x18001e8f3  mov     rcx, r15; String
0x18001e8f6  mov     [rbp+0F0h+var_160], rdi
0x18001e8fa  mov     [rbp+0F0h+var_154], 0
0x18001e901  lea     eax, ds:2[rax*2]
0x18001e908  mov     [rbp+0F0h+var_158], eax
0x18001e90b  call    cs:__imp_wcslen
0x18001e911  mov     rcx, cs:QuirksEtwProvider
0x18001e918  lea     r9, [rsp+1F0h+var_1C0]
0x18001e91d  mov     r8d, 8
0x18001e923  mov     [rbp+0F0h+var_150], r15
0x18001e927  lea     rdx, QUIRKS_DEBUG_EVENT
0x18001e92e  mov     [rbp+0F0h+var_144], 0
0x18001e935  lea     eax, ds:2[rax*2]
0x18001e93c  mov     [rbp+0F0h+var_148], eax
0x18001e93f  call    cs:__imp_EtwEventWrite
0x18001e945  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001e949  jnz     short loc_18001E953
0x18001e94b  or      dword ptr [r14+228h], 10h
0x18001e953  mov     rcx, [rbp+0F0h+var_40]
0x18001e95a  xor     rcx, rsp; StackCookie
0x18001e95d  call    __security_check_cookie
0x18001e962  add     rsp, 1C8h
0x18001e969  pop     r15
0x18001e96b  pop     r14
0x18001e96d  pop     rdi
0x18001e96e  pop     rsi
0x18001e96f  pop     rbx
0x18001e970  pop     rbp
0x18001e971  retn
0x18001e972  lea     r8, [rbp+0F0h+packageFullName]; packageFullName
0x18001e976  mov     rcx, rsi; hProcess
0x18001e979  lea     rdx, [rsp+1F0h+packageFullNameLength]; packageFullNameLength
0x18001e97e  call    cs:__imp_GetPackageFullName
0x18001e984  jmp     loc_18001E80A
0x18001e989  test    byte ptr [r14+228h], 10h
0x18001e991  jz      loc_18001E7B5
0x18001e997  jmp     short loc_18001E953
0x18001e999  test    rdi, rdi
0x18001e99c  jnz     loc_18001E816
0x18001e9a2  lea     rdi, [rsp+1F0h+var_1D0]
0x18001e9a7  jmp     loc_18001E816
```
