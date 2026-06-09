# GetSidString(void *,ushort * *)

- ea: `0x180011c40`
- end: `0x180011e9b`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `603`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034a88`

## callees

- `0x180005370`
- `0x180011c00`
- `0x180011c40`
- `0x18001214c`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011cf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011db1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011db1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ce2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ce2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d9d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011d1b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180011d1b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011cd0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180011cd0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011cb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011e27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011cb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011e27`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011d7a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011d7a`

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
  HANDLE v14; // rax
  int v16; // eax
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
      v16 = ResultFromHeapReAlloc(v5, TokenInformationLength, (void **)&StringSid);
      v5 = StringSid;
      Error = v16;
      if ( v16 < 0 )
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
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v5);
    TokenInformationLength = LengthSid;
    v9 = GetProcessHeap();
    v10 = HeapAlloc(v9, 8u, LengthSid);
    v11 = v10;
    if ( !v10 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v10, *(PSID *)v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v11);
        goto LABEL_9;
      }
    }
    v6 = v11;
  }
LABEL_9:
  if ( v5 )
  {
    v12 = GetProcessHeap();
    if ( !HeapFree(v12, 0, v5) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
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
  if ( v6 )
  {
    v14 = GetProcessHeap();
    if ( !HeapFree(v14, 0, v6) )
      ResultFromKnownLastError();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180011c40  mov     [rsp+arg_0], rbx
0x180011c45  mov     [rsp+arg_8], rbp
0x180011c4a  push    rsi
0x180011c4b  push    rdi
0x180011c4c  push    r14
0x180011c4e  sub     rsp, 30h
0x180011c52  mov     r14, rdx
0x180011c55  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180011c5d  mov     rbp, rcx
0x180011c60  call    cs:__imp_GetProcessHeap
0x180011c67  nop     dword ptr [rax+rax+00h]
0x180011c6c  mov     edx, 8; dwFlags
0x180011c71  mov     r8d, 0C8h; dwBytes
0x180011c77  mov     rcx, rax; hHeap
0x180011c7a  call    cs:__imp_HeapAlloc
0x180011c81  nop     dword ptr [rax+rax+00h]
0x180011c86  mov     [rsp+48h+StringSid], rax
0x180011c8b  mov     rbx, rax
0x180011c8e  test    rax, rax
0x180011c91  jz      loc_180011E8F
0x180011c97  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180011c9c  lea     rax, [rsp+48h+TokenInformationLength]
0x180011ca1  mov     r8, rbx; TokenInformation
0x180011ca4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180011ca9  mov     edx, 1; TokenInformationClass
0x180011cae  mov     rcx, rbp; TokenHandle
0x180011cb1  xor     esi, esi
0x180011cb3  call    cs:__imp_GetTokenInformation
0x180011cba  nop     dword ptr [rax+rax+00h]
0x180011cbf  test    eax, eax
0x180011cc1  jz      loc_180011DDB
0x180011cc7  xor     edi, edi
0x180011cc9  test    edi, edi
0x180011ccb  js      short loc_180011D34
0x180011ccd  mov     rcx, [rbx]; pSid
0x180011cd0  call    cs:__imp_GetLengthSid
0x180011cd7  nop     dword ptr [rax+rax+00h]
0x180011cdc  mov     edi, eax
0x180011cde  mov     [rsp+48h+TokenInformationLength], edi
0x180011ce2  call    cs:__imp_GetProcessHeap
0x180011ce9  nop     dword ptr [rax+rax+00h]
0x180011cee  mov     r8d, edi; dwBytes
0x180011cf1  mov     edx, 8; dwFlags
0x180011cf6  mov     rcx, rax; hHeap
0x180011cf9  call    cs:__imp_HeapAlloc
0x180011d00  nop     dword ptr [rax+rax+00h]
0x180011d05  mov     rbp, rax
0x180011d08  test    rax, rax
0x180011d0b  jz      loc_180011E71
0x180011d11  mov     r8, [rbx]; pSourceSid
0x180011d14  mov     rdx, rax; pDestinationSid
0x180011d17  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180011d1b  call    cs:__imp_CopySid
0x180011d22  nop     dword ptr [rax+rax+00h]
0x180011d27  test    eax, eax
0x180011d29  jz      loc_180011E55
0x180011d2f  xor     edi, edi
0x180011d31  mov     rsi, rbp
0x180011d34  test    rbx, rbx
0x180011d37  jz      short loc_180011D61
0x180011d39  call    cs:__imp_GetProcessHeap
0x180011d40  nop     dword ptr [rax+rax+00h]
0x180011d45  mov     r8, rbx; lpMem
0x180011d48  xor     edx, edx; dwFlags
0x180011d4a  mov     rcx, rax; hHeap
0x180011d4d  call    cs:__imp_HeapFree
0x180011d54  nop     dword ptr [rax+rax+00h]
0x180011d59  test    eax, eax
0x180011d5b  jz      loc_180011E7B
0x180011d61  test    edi, edi
0x180011d63  js      loc_180011E94
0x180011d69  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180011d6e  mov     [rsp+48h+StringSid], 0
0x180011d77  mov     rcx, rsi; Sid
0x180011d7a  call    cs:__imp_ConvertSidToStringSidW
0x180011d81  nop     dword ptr [rax+rax+00h]
0x180011d86  test    eax, eax
0x180011d88  jz      loc_180011E41
0x180011d8e  xor     ebx, ebx
0x180011d90  mov     rax, [rsp+48h+StringSid]
0x180011d95  mov     [r14], rax
0x180011d98  test    rsi, rsi
0x180011d9b  jz      short loc_180011DC5
0x180011d9d  call    cs:__imp_GetProcessHeap
0x180011da4  nop     dword ptr [rax+rax+00h]
0x180011da9  mov     r8, rsi; lpMem
0x180011dac  xor     edx, edx; dwFlags
0x180011dae  mov     rcx, rax; hHeap
0x180011db1  call    cs:__imp_HeapFree
0x180011db8  nop     dword ptr [rax+rax+00h]
0x180011dbd  test    eax, eax
0x180011dbf  jz      loc_180011E85
0x180011dc5  mov     eax, ebx
0x180011dc7  mov     rbx, [rsp+48h+arg_0]
0x180011dcc  mov     rbp, [rsp+48h+arg_8]
0x180011dd1  add     rsp, 30h
0x180011dd5  pop     r14
0x180011dd7  pop     rdi
0x180011dd8  pop     rsi
0x180011dd9  retn
0x180011ddb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011de0  mov     edi, eax
0x180011de2  cmp     eax, 8007007Ah
0x180011de7  jnz     loc_180011CC9
0x180011ded  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180011df1  lea     r8, [rsp+48h+StringSid]; void **
0x180011df6  mov     rcx, rbx; lpMem
0x180011df9  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180011dfe  mov     rbx, [rsp+48h+StringSid]
0x180011e03  mov     edi, eax
0x180011e05  test    eax, eax
0x180011e07  js      loc_180011D34
0x180011e0d  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180011e12  lea     rax, [rsp+48h+TokenInformationLength]
0x180011e17  mov     r8, rbx; TokenInformation
0x180011e1a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180011e1f  mov     edx, 1; TokenInformationClass
0x180011e24  mov     rcx, rbp; TokenHandle
0x180011e27  call    cs:__imp_GetTokenInformation
0x180011e2e  nop     dword ptr [rax+rax+00h]
0x180011e33  mov     ecx, eax; int
0x180011e35  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180011e3a  mov     edi, eax
0x180011e3c  jmp     loc_180011CC9
0x180011e41  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011e46  mov     ebx, eax
0x180011e48  test    eax, eax
0x180011e4a  jns     loc_180011D90
0x180011e50  jmp     loc_180011D98
0x180011e55  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011e5a  mov     edi, eax
0x180011e5c  test    eax, eax
0x180011e5e  jns     loc_180011D31
0x180011e64  mov     rcx, rbp; lpMem
0x180011e67  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180011e6c  jmp     loc_180011D34
0x180011e71  mov     edi, 8007000Eh
0x180011e76  jmp     loc_180011D34
0x180011e7b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011e80  jmp     loc_180011D61
0x180011e85  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011e8a  jmp     loc_180011DC5
0x180011e8f  mov     edi, 8007000Eh
0x180011e94  mov     eax, edi
0x180011e96  jmp     loc_180011DC7
```
