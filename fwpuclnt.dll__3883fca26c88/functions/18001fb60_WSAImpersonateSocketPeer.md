# WSAImpersonateSocketPeer

- ea: `0x18001fb60`
- end: `0x18001fd50`
- name: `WSAImpersonateSocketPeer`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012bd0`
- `0x18001346a`
- `0x18001fb60`
- `0x18001fd60`
- `0x18004a0d1`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fcc4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fcc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fcf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fc3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd26`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fc53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fc53`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fc21`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fc21`
- `WS2_32!__imp_WSASetLastError` at `0x18001fba7`
- `WS2_32!__imp_WSASetLastError` at `0x18001fcd9`
- `WS2_32!__imp_WSASetLastError` at `0x18001fba7`
- `WS2_32!__imp_WSASetLastError` at `0x18001fcd9`

## pseudocode

```c
__int64 __fastcall WSAImpersonateSocketPeer(__int64 a1, const void *a2, unsigned int a3)
{
  size_t v3; // rdi
  int v6; // ecx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rdi
  void *v11; // rdx
  int v12; // ecx
  void *v13; // rcx
  void *v14; // rcx
  HANDLE v15; // rax
  _DWORD dwBytes[4]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v18[4]; // [rsp+50h] [rbp-B8h] BYREF
  int v19; // [rsp+54h] [rbp-B4h]
  _BYTE v20[128]; // [rsp+58h] [rbp-B0h] BYREF
  int v21; // [rsp+D8h] [rbp-30h]

  v3 = a3;
  v19 = 0;
  dwBytes[0] = 0;
  if ( a3 && !a2 || a3 > 0x80 )
  {
    v6 = 10022;
LABEL_5:
    WSASetLastError(v6);
    return (unsigned int)-1;
  }
  memset_0(v18, 0, 0x90u);
  if ( a2 )
    memcpy_0(v20, a2, v3);
  v21 = 4;
  v7 = WSAQuerySocketSecurity(a1, v18, 144, 0, dwBytes, 0, 0);
  if ( WSAGetLastError() == 10040 )
  {
    v8 = dwBytes[0];
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, v8);
    if ( !v10 )
    {
      v6 = 10055;
      goto LABEL_5;
    }
    v7 = WSAQuerySocketSecurity(a1, v18, 144, v10, dwBytes, 0, 0);
    if ( v7 )
      goto LABEL_18;
    v11 = (void *)v10[1];
    if ( v11 || (v11 = (void *)v10[2]) != 0 )
    {
      if ( SetThreadToken(0, v11) )
      {
LABEL_18:
        v13 = (void *)v10[1];
        if ( v13 )
          CloseHandle(v13);
        v14 = (void *)v10[2];
        if ( v14 )
          CloseHandle(v14);
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v10);
        return v7;
      }
      v12 = 10013;
    }
    else
    {
      v12 = 10045;
    }
    WSASetLastError(v12);
    v7 = -1;
    goto LABEL_18;
  }
  return v7;
}

```

## disassembly

```asm
0x18001fb60  push    rbx
0x18001fb62  push    rsi
0x18001fb63  push    rdi
0x18001fb64  sub     rsp, 0F0h
0x18001fb6b  mov     rax, cs:__security_cookie
0x18001fb72  xor     rax, rsp
0x18001fb75  mov     [rsp+108h+var_28], rax
0x18001fb7d  xor     eax, eax
0x18001fb7f  mov     edi, r8d
0x18001fb82  mov     [rsp+108h+var_B4], eax
0x18001fb86  mov     rbx, rdx
0x18001fb89  mov     [rsp+108h+dwBytes], eax
0x18001fb8d  mov     rsi, rcx
0x18001fb90  test    r8d, r8d
0x18001fb93  jz      short loc_18001FB9A
0x18001fb95  test    rdx, rdx
0x18001fb98  jz      short loc_18001FBA2
0x18001fb9a  cmp     edi, 80h
0x18001fba0  jbe     short loc_18001FBBB
0x18001fba2  mov     ecx, 2726h; iError
0x18001fba7  call    cs:__imp_WSASetLastError
0x18001fbae  nop     dword ptr [rax+rax+00h]
0x18001fbb3  or      ebx, 0FFFFFFFFh
0x18001fbb6  jmp     loc_18001FD32
0x18001fbbb  xor     edx, edx; Val
0x18001fbbd  lea     rcx, [rsp+108h+var_B8]; void *
0x18001fbc2  mov     r8d, 90h; Size
0x18001fbc8  call    memset_0
0x18001fbcd  test    rbx, rbx
0x18001fbd0  jz      short loc_18001FBE2
0x18001fbd2  mov     r8, rdi; Size
0x18001fbd5  lea     rcx, [rsp+108h+var_B0]; void *
0x18001fbda  mov     rdx, rbx; Src
0x18001fbdd  call    memcpy_0
0x18001fbe2  mov     [rsp+108h+var_D8], 0
0x18001fbeb  lea     rax, [rsp+108h+dwBytes]
0x18001fbf0  mov     [rsp+108h+var_E0], 0
0x18001fbf9  lea     rdx, [rsp+108h+var_B8]
0x18001fbfe  xor     r9d, r9d
0x18001fc01  mov     [rsp+108h+var_E8], rax
0x18001fc06  mov     r8d, 90h
0x18001fc0c  mov     [rsp+108h+var_30], 4
0x18001fc17  mov     rcx, rsi
0x18001fc1a  call    WSAQuerySocketSecurity
0x18001fc1f  mov     ebx, eax
0x18001fc21  call    cs:__imp_WSAGetLastError
0x18001fc28  nop     dword ptr [rax+rax+00h]
0x18001fc2d  cmp     eax, 2738h
0x18001fc32  jnz     loc_18001FD32
0x18001fc38  mov     ebx, [rsp+108h+dwBytes]
0x18001fc3c  call    cs:__imp_GetProcessHeap
0x18001fc43  nop     dword ptr [rax+rax+00h]
0x18001fc48  mov     r8d, ebx; dwBytes
0x18001fc4b  mov     edx, 8; dwFlags
0x18001fc50  mov     rcx, rax; hHeap
0x18001fc53  call    cs:__imp_HeapAlloc
0x18001fc5a  nop     dword ptr [rax+rax+00h]
0x18001fc5f  mov     rdi, rax
0x18001fc62  test    rax, rax
0x18001fc65  jnz     short loc_18001FC71
0x18001fc67  mov     ecx, 2747h
0x18001fc6c  jmp     loc_18001FBA7
0x18001fc71  mov     [rsp+108h+var_D8], 0
0x18001fc7a  lea     rax, [rsp+108h+dwBytes]
0x18001fc7f  mov     [rsp+108h+var_E0], 0
0x18001fc88  lea     rdx, [rsp+108h+var_B8]
0x18001fc8d  mov     r9, rdi
0x18001fc90  mov     [rsp+108h+var_E8], rax
0x18001fc95  mov     r8d, 90h
0x18001fc9b  mov     rcx, rsi
0x18001fc9e  call    WSAQuerySocketSecurity
0x18001fca3  mov     ebx, eax
0x18001fca5  test    eax, eax
0x18001fca7  jnz     short loc_18001FCE8
0x18001fca9  mov     rdx, [rdi+8]; Token
0x18001fcad  test    rdx, rdx
0x18001fcb0  jnz     short loc_18001FCC2
0x18001fcb2  mov     rdx, [rdi+10h]
0x18001fcb6  test    rdx, rdx
0x18001fcb9  jnz     short loc_18001FCC2
0x18001fcbb  mov     ecx, 273Dh
0x18001fcc0  jmp     short loc_18001FCD9
0x18001fcc2  xor     ecx, ecx; Thread
0x18001fcc4  call    cs:__imp_SetThreadToken
0x18001fccb  nop     dword ptr [rax+rax+00h]
0x18001fcd0  test    eax, eax
0x18001fcd2  jnz     short loc_18001FCE8
0x18001fcd4  mov     ecx, 271Dh; iError
0x18001fcd9  call    cs:__imp_WSASetLastError
0x18001fce0  nop     dword ptr [rax+rax+00h]
0x18001fce5  or      ebx, 0FFFFFFFFh
0x18001fce8  mov     rcx, [rdi+8]; hObject
0x18001fcec  test    rcx, rcx
0x18001fcef  jz      short loc_18001FCFD
0x18001fcf1  call    cs:__imp_CloseHandle
0x18001fcf8  nop     dword ptr [rax+rax+00h]
0x18001fcfd  mov     rcx, [rdi+10h]; hObject
0x18001fd01  test    rcx, rcx
0x18001fd04  jz      short loc_18001FD12
0x18001fd06  call    cs:__imp_CloseHandle
0x18001fd0d  nop     dword ptr [rax+rax+00h]
0x18001fd12  call    cs:__imp_GetProcessHeap
0x18001fd19  nop     dword ptr [rax+rax+00h]
0x18001fd1e  mov     r8, rdi; lpMem
0x18001fd21  xor     edx, edx; dwFlags
0x18001fd23  mov     rcx, rax; hHeap
0x18001fd26  call    cs:__imp_HeapFree
0x18001fd2d  nop     dword ptr [rax+rax+00h]
0x18001fd32  mov     eax, ebx
0x18001fd34  mov     rcx, [rsp+108h+var_28]
0x18001fd3c  xor     rcx, rsp; StackCookie
0x18001fd3f  call    __security_check_cookie
0x18001fd44  add     rsp, 0F0h
0x18001fd4b  pop     rdi
0x18001fd4c  pop     rsi
0x18001fd4d  pop     rbx
0x18001fd4e  retn
```
