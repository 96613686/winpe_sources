# GetUserSid(void *,void * *)

- ea: `0x1800127a0`
- end: `0x18001296e`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `462`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012508`
- `0x180037544`
- `0x180045750`
- `0x180050f9c`

## callees

- `0x180005370`
- `0x180011c00`
- `0x18001214c`
- `0x1800127a0`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800127dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800127dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012859`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800128ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012899`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001287b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001287b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012830`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012830`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012813`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001291a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012813`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001291a`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rbx
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  int v13; // eax
  BOOL v14; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  TokenInformation = HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = (PSID *)TokenInformation;
  if ( !TokenInformation )
    return 2147942414LL;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v13 = ResultFromHeapReAlloc(v5, TokenInformationLength, &TokenInformation);
      v5 = (PSID *)TokenInformation;
      Error = v13;
      if ( v13 < 0 )
        goto LABEL_9;
      v14 = GetTokenInformation(
              TokenHandle,
              TokenUser,
              TokenInformation,
              TokenInformationLength,
              &TokenInformationLength);
      Error = ResultFromWin32Bool(v14);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, LengthSid);
    v10 = v9;
    if ( !v9 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v9, *v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v10);
        goto LABEL_9;
      }
    }
    *a2 = v10;
  }
LABEL_9:
  if ( v5 )
  {
    v11 = GetProcessHeap();
    if ( !HeapFree(v11, 0, v5) )
      ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800127a0  mov     [rsp+arg_0], rbx
0x1800127a5  push    rsi
0x1800127a6  push    rdi
0x1800127a7  push    r14
0x1800127a9  sub     rsp, 30h
0x1800127ad  mov     r14, rdx
0x1800127b0  mov     qword ptr [rdx], 0
0x1800127b7  mov     rsi, rcx
0x1800127ba  mov     [rsp+48h+TokenInformationLength], 0C8h
0x1800127c2  call    cs:__imp_GetProcessHeap
0x1800127c9  nop     dword ptr [rax+rax+00h]
0x1800127ce  mov     edx, 8; dwFlags
0x1800127d3  mov     r8d, 0C8h; dwBytes
0x1800127d9  mov     rcx, rax; hHeap
0x1800127dc  call    cs:__imp_HeapAlloc
0x1800127e3  nop     dword ptr [rax+rax+00h]
0x1800127e8  mov     [rsp+48h+TokenInformation], rax
0x1800127ed  mov     rbx, rax
0x1800127f0  test    rax, rax
0x1800127f3  jz      loc_180012964
0x1800127f9  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800127fe  lea     rax, [rsp+48h+TokenInformationLength]
0x180012803  mov     r8, rbx; TokenInformation
0x180012806  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001280b  mov     edx, 1; TokenInformationClass
0x180012810  mov     rcx, rsi; TokenHandle
0x180012813  call    cs:__imp_GetTokenInformation
0x18001281a  nop     dword ptr [rax+rax+00h]
0x18001281f  test    eax, eax
0x180012821  jz      loc_1800128D2
0x180012827  xor     edi, edi
0x180012829  test    edi, edi
0x18001282b  js      short loc_180012894
0x18001282d  mov     rcx, [rbx]; pSid
0x180012830  call    cs:__imp_GetLengthSid
0x180012837  nop     dword ptr [rax+rax+00h]
0x18001283c  mov     edi, eax
0x18001283e  mov     [rsp+48h+TokenInformationLength], edi
0x180012842  call    cs:__imp_GetProcessHeap
0x180012849  nop     dword ptr [rax+rax+00h]
0x18001284e  mov     r8d, edi; dwBytes
0x180012851  mov     edx, 8; dwFlags
0x180012856  mov     rcx, rax; hHeap
0x180012859  call    cs:__imp_HeapAlloc
0x180012860  nop     dword ptr [rax+rax+00h]
0x180012865  mov     rsi, rax
0x180012868  test    rax, rax
0x18001286b  jz      loc_180012950
0x180012871  mov     r8, [rbx]; pSourceSid
0x180012874  mov     rdx, rax; pDestinationSid
0x180012877  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x18001287b  call    cs:__imp_CopySid
0x180012882  nop     dword ptr [rax+rax+00h]
0x180012887  test    eax, eax
0x180012889  jz      loc_180012934
0x18001288f  xor     edi, edi
0x180012891  mov     [r14], rsi
0x180012894  test    rbx, rbx
0x180012897  jz      short loc_1800128C1
0x180012899  call    cs:__imp_GetProcessHeap
0x1800128a0  nop     dword ptr [rax+rax+00h]
0x1800128a5  mov     r8, rbx; lpMem
0x1800128a8  xor     edx, edx; dwFlags
0x1800128aa  mov     rcx, rax; hHeap
0x1800128ad  call    cs:__imp_HeapFree
0x1800128b4  nop     dword ptr [rax+rax+00h]
0x1800128b9  test    eax, eax
0x1800128bb  jz      loc_18001295A
0x1800128c1  mov     eax, edi
0x1800128c3  mov     rbx, [rsp+48h+arg_0]
0x1800128c8  add     rsp, 30h
0x1800128cc  pop     r14
0x1800128ce  pop     rdi
0x1800128cf  pop     rsi
0x1800128d0  retn
0x1800128d2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800128d7  mov     edi, eax
0x1800128d9  cmp     eax, 8007007Ah
0x1800128de  jnz     loc_180012829
0x1800128e4  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x1800128e8  lea     r8, [rsp+48h+TokenInformation]; void **
0x1800128ed  mov     rcx, rbx; lpMem
0x1800128f0  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800128f5  mov     rbx, [rsp+48h+TokenInformation]
0x1800128fa  mov     edi, eax
0x1800128fc  test    eax, eax
0x1800128fe  js      short loc_180012894
0x180012900  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180012905  lea     rax, [rsp+48h+TokenInformationLength]
0x18001290a  mov     r8, rbx; TokenInformation
0x18001290d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180012912  mov     edx, 1; TokenInformationClass
0x180012917  mov     rcx, rsi; TokenHandle
0x18001291a  call    cs:__imp_GetTokenInformation
0x180012921  nop     dword ptr [rax+rax+00h]
0x180012926  mov     ecx, eax; int
0x180012928  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001292d  mov     edi, eax
0x18001292f  jmp     loc_180012829
0x180012934  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012939  mov     edi, eax
0x18001293b  test    eax, eax
0x18001293d  jns     loc_180012891
0x180012943  mov     rcx, rsi; lpMem
0x180012946  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001294b  jmp     loc_180012894
0x180012950  mov     edi, 8007000Eh
0x180012955  jmp     loc_180012894
0x18001295a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001295f  jmp     loc_1800128C1
0x180012964  mov     eax, 8007000Eh
0x180012969  jmp     loc_1800128C3
```
