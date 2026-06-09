# SupplicantGetUserTokenFromRuntimeState

- ea: `0x180029b74`
- end: `0x180029cae`
- name: `SupplicantGetUserTokenFromRuntimeState`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002470`
- `0x180002a30`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180029b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c12`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180029c08`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180029c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029be4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180029be4`

## pseudocode

```c
__int64 __fastcall SupplicantGetUserTokenFromRuntimeState(__int64 a1, HANDLE *a2)
{
  DWORD v2; // edi
  void *v5; // rbp
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  HANDLE TargetHandle; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  TargetHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 157, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  *a2 = 0;
  v5 = *(void **)(*(_QWORD *)(a1 + 408) + 8LL);
  if ( !v5 )
    goto LABEL_13;
  CurrentProcess = GetCurrentProcess();
  v7 = GetCurrentProcess();
  if ( DuplicateHandle(v7, v5, CurrentProcess, &TargetHandle, 0, 0, 2u)
    || (LastError = GetLastError(), (v2 = LastError) == 0) )
  {
    *a2 = TargetHandle;
    goto LABEL_13;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 158, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, LastError);
    v9 = WPP_GLOBAL_Control;
  }
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
LABEL_13:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 159, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180029b74  mov     [rsp+arg_8], rbx
0x180029b79  mov     [rsp+arg_10], rbp
0x180029b7e  push    rsi
0x180029b7f  push    rdi
0x180029b80  push    r15
0x180029b82  sub     rsp, 40h
0x180029b86  xor     edi, edi
0x180029b88  mov     rsi, rdx
0x180029b8b  mov     [rsp+58h+TargetHandle], rdi
0x180029b90  mov     rbx, rcx
0x180029b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b9a  lea     r15, WPP_GLOBAL_Control
0x180029ba1  cmp     rcx, r15
0x180029ba4  jz      short loc_180029BC4
0x180029ba6  test    dword ptr [rcx+44h], 800h
0x180029bad  jz      short loc_180029BC4
0x180029baf  mov     rcx, [rcx+38h]
0x180029bb3  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180029bba  mov     edx, 9Dh
0x180029bbf  call    WPP_SF_
0x180029bc4  mov     [rsi], rdi
0x180029bc7  mov     rax, [rbx+198h]
0x180029bce  mov     rbp, [rax+8]
0x180029bd2  test    rbp, rbp
0x180029bd5  jz      loc_180029C6C
0x180029bdb  call    cs:__imp_GetCurrentProcess
0x180029be1  mov     rbx, rax
0x180029be4  call    cs:__imp_GetCurrentProcess
0x180029bea  mov     [rsp+58h+dwOptions], 2; dwOptions
0x180029bf2  lea     r9, [rsp+58h+TargetHandle]; lpTargetHandle
0x180029bf7  mov     rcx, rax; hSourceProcessHandle
0x180029bfa  mov     [rsp+58h+bInheritHandle], edi; bInheritHandle
0x180029bfe  mov     r8, rbx; hTargetProcessHandle
0x180029c01  mov     [rsp+58h+dwDesiredAccess], edi; dwDesiredAccess
0x180029c05  mov     rdx, rbp; hSourceHandle
0x180029c08  call    cs:__imp_DuplicateHandle
0x180029c0e  test    eax, eax
0x180029c10  jnz     short loc_180029C64
0x180029c12  call    cs:__imp_GetLastError
0x180029c18  mov     edi, eax
0x180029c1a  test    eax, eax
0x180029c1c  jz      short loc_180029C64
0x180029c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c25  cmp     rcx, r15
0x180029c28  jz      short loc_180029C4F
0x180029c2a  test    byte ptr [rcx+44h], 1
0x180029c2e  jz      short loc_180029C4F
0x180029c30  mov     rcx, [rcx+38h]
0x180029c34  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180029c3b  mov     edx, 9Eh
0x180029c40  mov     r9d, eax
0x180029c43  call    WPP_SF_d
0x180029c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c4f  mov     rax, [rsp+58h+TargetHandle]
0x180029c54  test    rax, rax
0x180029c57  jz      short loc_180029C73
0x180029c59  mov     rcx, rax; hObject
0x180029c5c  call    cs:__imp_CloseHandle
0x180029c62  jmp     short loc_180029C6C
0x180029c64  mov     rax, [rsp+58h+TargetHandle]
0x180029c69  mov     [rsi], rax
0x180029c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c73  cmp     rcx, r15
0x180029c76  jz      short loc_180029C99
0x180029c78  test    dword ptr [rcx+44h], 800h
0x180029c7f  jz      short loc_180029C99
0x180029c81  mov     rcx, [rcx+38h]
0x180029c85  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180029c8c  mov     edx, 9Fh
0x180029c91  mov     r9d, edi
0x180029c94  call    WPP_SF_D
0x180029c99  mov     rbx, [rsp+58h+arg_8]
0x180029c9e  mov     eax, edi
0x180029ca0  mov     rbp, [rsp+58h+arg_10]
0x180029ca5  add     rsp, 40h
0x180029ca9  pop     r15
0x180029cab  pop     rdi
0x180029cac  pop     rsi
0x180029cad  retn
```
