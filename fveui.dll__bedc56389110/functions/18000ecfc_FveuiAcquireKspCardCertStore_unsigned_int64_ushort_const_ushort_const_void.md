# FveuiAcquireKspCardCertStore(unsigned __int64,ushort const *,ushort const *,void * *)

- ea: `0x18000ecfc`
- end: `0x18000ee4c`
- name: `?FveuiAcquireKspCardCertStore@@YAJ_KPEBG1PEAPEAX@Z`
- size: `336`
- prototype: `__int64 __fastcall(SCARDCONTEXT hContext, LPCWSTR szCardName, PBYTE pbInput, PBYTE pbOutput)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ee54`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x18000ecfc`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18000ee25`
- `ncrypt!NCryptFreeObject` at `0x18000ee25`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000eda4`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000eda4`
- `ncrypt!NCryptSetProperty` at `0x18000edda`
- `ncrypt!NCryptSetProperty` at `0x18000edda`
- `ncrypt!NCryptGetProperty` at `0x18000ee08`
- `ncrypt!NCryptGetProperty` at `0x18000ee08`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000ed77`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18000ed77`

## string_xrefs

- `0x18000edd3`: `SmartCardReader`

## pseudocode

```c
__int64 __fastcall FveuiAcquireKspCardCertStore(
        SCARDCONTEXT hContext,
        LPCWSTR szCardName,
        PBYTE pbInput,
        PBYTE pbOutput)
{
  LONG CardTypeProviderNameW; // eax
  unsigned int v9; // ebx
  bool v10; // cc
  __int64 v11; // r9
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchProvider; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcbResult; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR szProvider; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[526]; // [rsp+42h] [rbp-BEh] BYREF

  szProvider = 0;
  memset_0(v17, 0, 0x206u);
  pcchProvider = 260;
  phProvider = 0;
  pcbResult = 0;
  CardTypeProviderNameW = SCardGetCardTypeProviderNameW(hContext, szCardName, 3u, &szProvider, &pcchProvider);
  v9 = CardTypeProviderNameW;
  v10 = CardTypeProviderNameW <= 0;
  if ( CardTypeProviderNameW )
    goto LABEL_2;
  CardTypeProviderNameW = NCryptOpenStorageProvider(&phProvider, &szProvider, 0);
  v9 = CardTypeProviderNameW;
  v10 = CardTypeProviderNameW <= 0;
  if ( CardTypeProviderNameW )
    goto LABEL_2;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&pbInput[2 * v11] );
  CardTypeProviderNameW = NCryptSetProperty(phProvider, L"SmartCardReader", pbInput, 2 * v11 + 2, 0);
  v9 = CardTypeProviderNameW;
  v10 = CardTypeProviderNameW <= 0;
  if ( CardTypeProviderNameW
    || (CardTypeProviderNameW = NCryptGetProperty(phProvider, L"SmartCardUserCertStore", pbOutput, 8u, &pcbResult, 0),
        v9 = CardTypeProviderNameW,
        v10 = CardTypeProviderNameW <= 0,
        CardTypeProviderNameW) )
  {
LABEL_2:
    if ( !v10 )
      v9 = (unsigned __int16)CardTypeProviderNameW | 0x80070000;
  }
  else
  {
    v9 = 0;
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return v9;
}

```

## disassembly

```asm
0x18000ecfc  push    rbp
0x18000ecfe  push    rbx
0x18000ecff  push    rsi
0x18000ed00  push    rdi
0x18000ed01  push    r14
0x18000ed03  push    r15
0x18000ed05  lea     rbp, [rsp-168h]
0x18000ed0d  sub     rsp, 268h
0x18000ed14  mov     rax, cs:__security_cookie
0x18000ed1b  xor     rax, rsp
0x18000ed1e  mov     [rbp+190h+var_40], rax
0x18000ed25  mov     rsi, r8
0x18000ed28  mov     rdi, rdx
0x18000ed2b  mov     rbx, rcx
0x18000ed2e  xor     r15d, r15d
0x18000ed31  xor     edx, edx; Val
0x18000ed33  mov     [rsp+290h+szProvider], r15w
0x18000ed39  mov     r8d, 206h; Size
0x18000ed3f  lea     rcx, [rsp+290h+var_24E]; void *
0x18000ed44  mov     r14, r9
0x18000ed47  call    memset_0
0x18000ed4c  lea     rax, [rsp+290h+var_258]
0x18000ed51  mov     [rsp+290h+var_258], 104h
0x18000ed59  lea     r9, [rsp+290h+szProvider]; szProvider
0x18000ed5e  mov     [rsp+290h+pcchProvider], rax; pcchProvider
0x18000ed63  lea     r8d, [r15+3]; dwProviderId
0x18000ed67  mov     [rsp+290h+phProvider], r15
0x18000ed6c  mov     rdx, rdi; szCardName
0x18000ed6f  mov     [rsp+290h+pcbResult], r15d
0x18000ed74  mov     rcx, rbx; hContext
0x18000ed77  call    cs:__imp_SCardGetCardTypeProviderNameW
0x18000ed7d  mov     ebx, eax
0x18000ed7f  test    eax, eax
0x18000ed81  jz      short loc_18000ED97
0x18000ed83  jle     loc_18000EE1B
0x18000ed89  movzx   ebx, ax
0x18000ed8c  or      ebx, 80070000h
0x18000ed92  jmp     loc_18000EE1B
0x18000ed97  xor     r8d, r8d; dwFlags
0x18000ed9a  lea     rdx, [rsp+290h+szProvider]; pszProviderName
0x18000ed9f  lea     rcx, [rsp+290h+phProvider]; phProvider
0x18000eda4  call    cs:__imp_NCryptOpenStorageProvider
0x18000edaa  mov     ebx, eax
0x18000edac  test    eax, eax
0x18000edae  jnz     short loc_18000ED83
0x18000edb0  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000edb4  inc     r9
0x18000edb7  cmp     [rsi+r9*2], r15w
0x18000edbc  jnz     short loc_18000EDB4
0x18000edbe  mov     rcx, [rsp+290h+phProvider]; hObject
0x18000edc3  lea     r9d, ds:2[r9*2]; cbInput
0x18000edcb  mov     r8, rsi; pbInput
0x18000edce  mov     dword ptr [rsp+290h+pcchProvider], r15d; dwFlags
0x18000edd3  lea     rdx, pszProperty; "SmartCardReader"
0x18000edda  call    cs:__imp_NCryptSetProperty
0x18000ede0  mov     ebx, eax
0x18000ede2  test    eax, eax
0x18000ede4  jnz     short loc_18000ED83
0x18000ede6  mov     rcx, [rsp+290h+phProvider]; hObject
0x18000edeb  lea     rax, [rsp+290h+pcbResult]
0x18000edf0  mov     [rsp+290h+dwFlags], r15d; dwFlags
0x18000edf5  lea     r9d, [rbx+8]; cbOutput
0x18000edf9  mov     r8, r14; pbOutput
0x18000edfc  mov     [rsp+290h+pcchProvider], rax; pcbResult
0x18000ee01  lea     rdx, aSmartcarduserc; "SmartCardUserCertStore"
0x18000ee08  call    cs:__imp_NCryptGetProperty
0x18000ee0e  mov     ebx, eax
0x18000ee10  test    eax, eax
0x18000ee12  jnz     loc_18000ED83
0x18000ee18  mov     ebx, r15d
0x18000ee1b  mov     rcx, [rsp+290h+phProvider]; hObject
0x18000ee20  test    rcx, rcx
0x18000ee23  jz      short loc_18000EE2B
0x18000ee25  call    cs:__imp_NCryptFreeObject
0x18000ee2b  mov     eax, ebx
0x18000ee2d  mov     rcx, [rbp+190h+var_40]
0x18000ee34  xor     rcx, rsp; StackCookie
0x18000ee37  call    __security_check_cookie
0x18000ee3c  add     rsp, 268h
0x18000ee43  pop     r15
0x18000ee45  pop     r14
0x18000ee47  pop     rdi
0x18000ee48  pop     rsi
0x18000ee49  pop     rbx
0x18000ee4a  pop     rbp
0x18000ee4b  retn
```
