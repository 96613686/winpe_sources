# CompareTerminalServicesSessionName(ushort *,void *,ulong *,int *)

- ea: `0x18003f1d4`
- end: `0x18003f372`
- name: `?CompareTerminalServicesSessionName@@YAJPEAGPEAXPEAKPEAH@Z`
- size: `414`
- prototype: `__int64 __fastcall(wchar_t *String2, void *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f608`

## callees

- `0x180035730`
- `0x18003f1d4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003f2e3`
- `msvcrt!_wcsicmp` at `0x18003f2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f356`
- `WTSAPI32!WTSFreeMemory` at `0x18003f32a`
- `WTSAPI32!WTSFreeMemory` at `0x18003f339`
- `WTSAPI32!WTSFreeMemory` at `0x18003f348`
- `WTSAPI32!WTSFreeMemory` at `0x18003f32a`
- `WTSAPI32!WTSFreeMemory` at `0x18003f339`
- `WTSAPI32!WTSFreeMemory` at `0x18003f348`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f24b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f28a`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f304`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f24b`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f28a`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x18003f304`

## pseudocode

```c
__int64 __fastcall CompareTerminalServicesSessionName(wchar_t *String2, void *a2, unsigned int *a3, int *a4)
{
  DWORD v8; // edx
  unsigned __int16 *v9; // rdi
  signed int LastError; // eax
  signed int v11; // ebx
  SIZE_T v12; // rbx
  DWORD v13; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR v14; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR v15; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR ppBuffer; // [rsp+48h] [rbp-8h] BYREF
  DWORD pBytesReturned; // [rsp+80h] [rbp+30h] BYREF
  DWORD v18; // [rsp+88h] [rbp+38h] BYREF
  int v19; // [rsp+8Ch] [rbp+3Ch]

  v19 = HIDWORD(a2);
  v15 = 0;
  v18 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  v14 = 0;
  v13 = 0;
  if ( !String2 )
    return 2147942487LL;
  v8 = *a3;
  v9 = 0;
  *a4 = 0;
  if ( !WTSQuerySessionInformationW(0, v8, WTSDomainName, &ppBuffer, &pBytesReturned)
    || !WTSQuerySessionInformationW(0, *a3, WTSUserName, &v15, &v18) )
  {
    goto LABEL_4;
  }
  v12 = 2 * (pBytesReturned + v18) + 4;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(v12);
  if ( v9 )
  {
    v11 = StringCbPrintfW(v9, v12, L"%s\\%s", ppBuffer, v15);
    if ( v11 < 0 || _wcsicmp(v9, String2) )
      goto LABEL_13;
    if ( WTSQuerySessionInformationW(0, *a3, WTSSessionId, &v14, &v13) )
    {
      *a3 = *(_DWORD *)v14;
      *a4 = 1;
      goto LABEL_13;
    }
LABEL_4:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_13;
  }
  v11 = -2147024882;
LABEL_13:
  if ( v14 )
    WTSFreeMemory(v14);
  if ( v15 )
    WTSFreeMemory(v15);
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003f1d4  mov     [rsp-28h+arg_10], rbx
0x18003f1d9  mov     qword ptr [rsp-28h+arg_8], rdx
0x18003f1de  push    rbp
0x18003f1df  push    rsi
0x18003f1e0  push    rdi
0x18003f1e1  push    r14
0x18003f1e3  push    r15
0x18003f1e5  mov     rbp, rsp
0x18003f1e8  sub     rsp, 50h
0x18003f1ec  mov     [rbp+var_10], 0
0x18003f1f4  mov     r15, r9
0x18003f1f7  mov     [rbp+arg_8], 0
0x18003f1fe  mov     rsi, r8
0x18003f201  mov     [rbp+ppBuffer], 0
0x18003f209  mov     r14, rcx
0x18003f20c  mov     [rbp+arg_0], 0
0x18003f213  mov     [rbp+var_18], 0
0x18003f21b  mov     [rbp+var_20], 0
0x18003f222  test    rcx, rcx
0x18003f225  jnz     short loc_18003F231
0x18003f227  mov     eax, 80070057h
0x18003f22c  jmp     loc_18003F35E
0x18003f231  mov     edx, [rsi]; SessionId
0x18003f233  lea     rax, [rbp+arg_0]
0x18003f237  xor     edi, edi
0x18003f239  mov     [rsp+50h+pBytesReturned], rax; pBytesReturned
0x18003f23e  mov     [r9], edi
0x18003f241  xor     ecx, ecx; hServer
0x18003f243  lea     r9, [rbp+ppBuffer]; ppBuffer
0x18003f247  lea     r8d, [rdi+7]; WTSInfoClass
0x18003f24b  call    cs:__imp_WTSQuerySessionInformationW
0x18003f251  test    eax, eax
0x18003f253  jnz     short loc_18003F273
0x18003f255  call    cs:__imp_GetLastError
0x18003f25b  mov     ebx, eax
0x18003f25d  test    eax, eax
0x18003f25f  jle     loc_18003F321
0x18003f265  movzx   ebx, ax
0x18003f268  or      ebx, 80070000h
0x18003f26e  jmp     loc_18003F321
0x18003f273  mov     edx, [rsi]; SessionId
0x18003f275  lea     rax, [rbp+arg_8]
0x18003f279  lea     r9, [rbp+var_10]; ppBuffer
0x18003f27d  mov     [rsp+50h+pBytesReturned], rax; pBytesReturned
0x18003f282  mov     r8d, 5; WTSInfoClass
0x18003f288  xor     ecx, ecx; hServer
0x18003f28a  call    cs:__imp_WTSQuerySessionInformationW
0x18003f290  test    eax, eax
0x18003f292  jz      short loc_18003F255
0x18003f294  mov     ecx, [rbp+arg_8]
0x18003f297  add     ecx, [rbp+arg_0]
0x18003f29a  lea     ecx, ds:4[rcx*2]; cb
0x18003f2a1  mov     ebx, ecx
0x18003f2a3  call    cs:__imp_CoTaskMemAlloc
0x18003f2a9  mov     rdi, rax
0x18003f2ac  test    rax, rax
0x18003f2af  jnz     short loc_18003F2B8
0x18003f2b1  mov     ebx, 8007000Eh
0x18003f2b6  jmp     short loc_18003F321
0x18003f2b8  mov     rax, [rbp+var_10]
0x18003f2bc  lea     r8, aSS; "%s\\%s"
0x18003f2c3  mov     r9, [rbp+ppBuffer]
0x18003f2c7  mov     rdx, rbx; unsigned __int64
0x18003f2ca  mov     rcx, rdi; unsigned __int16 *
0x18003f2cd  mov     [rsp+50h+pBytesReturned], rax
0x18003f2d2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f2d7  mov     ebx, eax
0x18003f2d9  test    eax, eax
0x18003f2db  js      short loc_18003F321
0x18003f2dd  mov     rdx, r14; String2
0x18003f2e0  mov     rcx, rdi; String1
0x18003f2e3  call    cs:__imp__wcsicmp
0x18003f2e9  test    eax, eax
0x18003f2eb  jnz     short loc_18003F321
0x18003f2ed  mov     edx, [rsi]; SessionId
0x18003f2ef  lea     rax, [rbp+var_20]
0x18003f2f3  lea     r9, [rbp+var_18]; ppBuffer
0x18003f2f7  mov     [rsp+50h+pBytesReturned], rax; pBytesReturned
0x18003f2fc  mov     r8d, 4; WTSInfoClass
0x18003f302  xor     ecx, ecx; hServer
0x18003f304  call    cs:__imp_WTSQuerySessionInformationW
0x18003f30a  test    eax, eax
0x18003f30c  jz      loc_18003F255
0x18003f312  mov     rax, [rbp+var_18]
0x18003f316  mov     ecx, [rax]
0x18003f318  mov     [rsi], ecx
0x18003f31a  mov     dword ptr [r15], 1
0x18003f321  mov     rcx, [rbp+var_18]; pMemory
0x18003f325  test    rcx, rcx
0x18003f328  jz      short loc_18003F330
0x18003f32a  call    cs:__imp_WTSFreeMemory
0x18003f330  mov     rcx, [rbp+var_10]; pMemory
0x18003f334  test    rcx, rcx
0x18003f337  jz      short loc_18003F33F
0x18003f339  call    cs:__imp_WTSFreeMemory
0x18003f33f  mov     rcx, [rbp+ppBuffer]; pMemory
0x18003f343  test    rcx, rcx
0x18003f346  jz      short loc_18003F34E
0x18003f348  call    cs:__imp_WTSFreeMemory
0x18003f34e  test    rdi, rdi
0x18003f351  jz      short loc_18003F35C
0x18003f353  mov     rcx, rdi; pv
0x18003f356  call    cs:__imp_CoTaskMemFree
0x18003f35c  mov     eax, ebx
0x18003f35e  mov     rbx, [rsp+50h+arg_10]
0x18003f366  add     rsp, 50h
0x18003f36a  pop     r15
0x18003f36c  pop     r14
0x18003f36e  pop     rdi
0x18003f36f  pop     rsi
0x18003f370  pop     rbp
0x18003f371  retn
```
