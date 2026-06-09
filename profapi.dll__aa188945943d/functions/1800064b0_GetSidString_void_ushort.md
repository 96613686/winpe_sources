# GetSidString(void *,ushort * *)

- ea: `0x1800064b0`
- end: `0x18000668a`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `474`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002650`
- `0x180003914`
- `0x180009e70`
- `0x180009f90`
- `0x18000ce3c`
- `0x18000cf24`

## callees

- `0x1800063e0`
- `0x1800064b0`
- `0x180006a9c`
- `0x180007c60`
- `0x18001214c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000658d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000658d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000654b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000654b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000653a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000657f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000653a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000657f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006597`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006567`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006567`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000652e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000652e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006517`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000663c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006517`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000663c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800065b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800065b2`

## pseudocode

```c
__int64 __fastcall GetSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v5; // rbx
  void *v6; // rsi
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v9; // rax
  void *v10; // rax
  void *v11; // rbp
  HANDLE v12; // rax
  int v13; // ebx
  int v15; // eax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = StringSid;
  if ( !StringSid )
    return (unsigned int)-2147024882;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v15 = ResultFromHeapReAlloc(v5, TokenInformationLength, (void **)&StringSid);
      v5 = StringSid;
      Error = v15;
      if ( v15 < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error < 0 )
    goto LABEL_9;
  LengthSid = GetLengthSid(*(PSID *)v5);
  TokenInformationLength = LengthSid;
  v9 = GetProcessHeap();
  v10 = HeapAlloc(v9, 8u, LengthSid);
  v11 = v10;
  if ( v10 )
  {
    if ( CopySid(TokenInformationLength, v10, *(PSID *)v5) )
    {
      Error = 0;
LABEL_8:
      v6 = v11;
      goto LABEL_9;
    }
    Error = ResultFromKnownLastError();
    if ( Error >= 0 )
      goto LABEL_8;
    ResultFromHeapFree(v11);
  }
  else
  {
    Error = -2147024882;
  }
LABEL_9:
  if ( v5 )
  {
    v12 = GetProcessHeap();
    if ( !HeapFree(v12, 0, v5) )
      GetLastError();
  }
  if ( Error >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(v6, &StringSid) )
    {
      v13 = 0;
    }
    else
    {
      v13 = ResultFromKnownLastError();
      if ( v13 < 0 )
        goto LABEL_16;
    }
    *a2 = StringSid;
LABEL_16:
    ResultFromHeapFree(v6);
    return (unsigned int)v13;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800064b0  mov     [rsp+arg_0], rbx
0x1800064b5  mov     [rsp+arg_8], rbp
0x1800064ba  push    rsi
0x1800064bb  push    rdi
0x1800064bc  push    r14
0x1800064be  sub     rsp, 30h
0x1800064c2  mov     r14, rdx
0x1800064c5  mov     [rsp+48h+TokenInformationLength], 0C8h
0x1800064cd  mov     rbp, rcx
0x1800064d0  call    cs:__imp_GetProcessHeap
0x1800064d6  mov     edx, 8; dwFlags
0x1800064db  mov     r8d, 0C8h; dwBytes
0x1800064e1  mov     rcx, rax; hHeap
0x1800064e4  call    cs:__imp_HeapAlloc
0x1800064ea  mov     [rsp+48h+StringSid], rax
0x1800064ef  mov     rbx, rax
0x1800064f2  test    rax, rax
0x1800064f5  jz      loc_1800065E7
0x1800064fb  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180006500  lea     rax, [rsp+48h+TokenInformationLength]
0x180006505  mov     r8, rbx; TokenInformation
0x180006508  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000650d  mov     edx, 1; TokenInformationClass
0x180006512  mov     rcx, rbp; TokenHandle
0x180006515  xor     esi, esi
0x180006517  call    cs:__imp_GetTokenInformation
0x18000651d  test    eax, eax
0x18000651f  jz      loc_1800065F0
0x180006525  xor     edi, edi
0x180006527  test    edi, edi
0x180006529  js      short loc_18000657A
0x18000652b  mov     rcx, [rbx]; pSid
0x18000652e  call    cs:__imp_GetLengthSid
0x180006534  mov     edi, eax
0x180006536  mov     [rsp+48h+TokenInformationLength], edi
0x18000653a  call    cs:__imp_GetProcessHeap
0x180006540  mov     r8d, edi; dwBytes
0x180006543  mov     edx, 8; dwFlags
0x180006548  mov     rcx, rax; hHeap
0x18000654b  call    cs:__imp_HeapAlloc
0x180006551  mov     rbp, rax
0x180006554  test    rax, rax
0x180006557  jz      loc_180006680
0x18000655d  mov     r8, [rbx]; pSourceSid
0x180006560  mov     rdx, rax; pDestinationSid
0x180006563  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180006567  call    cs:__imp_CopySid
0x18000656d  test    eax, eax
0x18000656f  jz      loc_180006650
0x180006575  xor     edi, edi
0x180006577  mov     rsi, rbp
0x18000657a  test    rbx, rbx
0x18000657d  jz      short loc_18000659D
0x18000657f  call    cs:__imp_GetProcessHeap
0x180006585  mov     r8, rbx; lpMem
0x180006588  xor     edx, edx; dwFlags
0x18000658a  mov     rcx, rax; hHeap
0x18000658d  call    cs:__imp_HeapFree
0x180006593  test    eax, eax
0x180006595  jnz     short loc_18000659D
0x180006597  call    cs:__imp_GetLastError
0x18000659d  test    edi, edi
0x18000659f  js      short loc_1800065EC
0x1800065a1  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800065a6  mov     [rsp+48h+StringSid], 0
0x1800065af  mov     rcx, rsi; Sid
0x1800065b2  call    cs:__imp_ConvertSidToStringSidW
0x1800065b8  test    eax, eax
0x1800065ba  jz      loc_18000666C
0x1800065c0  xor     ebx, ebx
0x1800065c2  mov     rdx, [rsp+48h+StringSid]
0x1800065c7  mov     [r14], rdx
0x1800065ca  mov     rcx, rsi; lpMem
0x1800065cd  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800065d2  mov     eax, ebx
0x1800065d4  mov     rbx, [rsp+48h+arg_0]
0x1800065d9  mov     rbp, [rsp+48h+arg_8]
0x1800065de  add     rsp, 30h
0x1800065e2  pop     r14
0x1800065e4  pop     rdi
0x1800065e5  pop     rsi
0x1800065e6  retn
0x1800065e7  mov     edi, 8007000Eh
0x1800065ec  mov     eax, edi
0x1800065ee  jmp     short loc_1800065D4
0x1800065f0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800065f5  mov     edi, eax
0x1800065f7  cmp     eax, 8007007Ah
0x1800065fc  jnz     loc_180006527
0x180006602  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180006606  lea     r8, [rsp+48h+StringSid]; void **
0x18000660b  mov     rcx, rbx; lpMem
0x18000660e  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180006613  mov     rbx, [rsp+48h+StringSid]
0x180006618  mov     edi, eax
0x18000661a  test    eax, eax
0x18000661c  js      loc_18000657A
0x180006622  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180006627  lea     rax, [rsp+48h+TokenInformationLength]
0x18000662c  mov     r8, rbx; TokenInformation
0x18000662f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180006634  mov     edx, 1; TokenInformationClass
0x180006639  mov     rcx, rbp; TokenHandle
0x18000663c  call    cs:__imp_GetTokenInformation
0x180006642  mov     ecx, eax; int
0x180006644  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180006649  mov     edi, eax
0x18000664b  jmp     loc_180006527
0x180006650  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006655  mov     edi, eax
0x180006657  test    eax, eax
0x180006659  jns     loc_180006577
0x18000665f  mov     rcx, rbp; lpMem
0x180006662  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180006667  jmp     loc_18000657A
0x18000666c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006671  mov     ebx, eax
0x180006673  test    eax, eax
0x180006675  jns     loc_1800065C2
0x18000667b  jmp     loc_1800065CA
0x180006680  mov     edi, 8007000Eh
0x180006685  jmp     loc_18000657A
```
