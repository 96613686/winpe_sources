# CListView32::LVGetDescription_ReportView(HWND__ *,int,ushort * *)

- ea: `0x18002f2bc`
- end: `0x18002f4a2`
- name: `?LVGetDescription_ReportView@CListView32@@AEAAJPEAUHWND__@@HPEAPEAG@Z`
- size: `486`
- prototype: `int(CListView32 *__hidden this, HWND, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800303f0`

## callees

- `0x180006c58`
- `0x18000771c`
- `0x18000b890`
- `0x18002ef5c`
- `0x18002f2bc`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f40a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f40a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f43f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f474`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f43f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f474`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f39f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f39f`
- `USER32!SendMessageW` at `0x18002f2f5`
- `USER32!SendMessageW` at `0x18002f2f5`

## pseudocode

```c
int __fastcall CListView32::LVGetDescription_ReportView(CListView32 *this, HWND a2, int a3, unsigned __int16 **a4)
{
  HWND v6; // rax
  int v7; // edx
  int result; // eax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  SIZE_T v11; // r15
  unsigned __int64 v12; // rdi
  void *v13; // rsi
  int *v14; // r14
  int v15; // eax
  HANDLE v16; // r12
  int v17; // edi
  int i; // ecx
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // [rsp+30h] [rbp-20h] BYREF
  _DWORD v22[2]; // [rsp+38h] [rbp-18h] BYREF
  HANDLE hProcess; // [rsp+40h] [rbp-10h] BYREF

  v6 = (HWND)SendMessageW(a2, 0x101Fu, 0, 0);
  if ( !v6 )
    return -2147352573;
  v7 = *((_DWORD *)this + 25);
  v22[1] = *((_DWORD *)this + 17);
  v22[0] = v7;
  v21 = 0;
  result = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)v22, v6, 0x1200u, 0, 0, &v21);
  if ( result < 0 )
    return result;
  v9 = (int)v21;
  if ( (int)v21 < 2 )
    return -2147352573;
  v10 = 4LL * (unsigned int)v21;
  if ( v10 > 0xFFFFFFFF )
    return -2147024362;
  v11 = (unsigned int)v10;
  v12 = 2LL * (unsigned int)v10;
  if ( v12 > 0xFFFFFFFF )
    return -2147024362;
  hProcess = 0;
  v13 = SharedAlloc((unsigned int)v10, a2, &hProcess);
  if ( !v13 )
    return -2147024882;
  v14 = (int *)LocalAlloc(0x40u, (unsigned int)v12);
  if ( !v14 )
  {
    SharedFree(v13, hProcess);
    return -2147024882;
  }
  v15 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)v22, a2, 0x103Bu, v9, (__int64)v13, &v21);
  v16 = hProcess;
  v17 = v15;
  if ( v15 < 0 )
    goto LABEL_19;
  if ( !v21 )
  {
    v17 = -2147024882;
LABEL_19:
    SharedFree(v13, v16);
    LocalFree(v14);
    return v17;
  }
  ReadProcessMemory(hProcess, v13, v14, v11, 0);
  for ( i = 0; i < (int)v9; ++i )
  {
    v19 = v14[i];
    if ( (int)v19 < 0 || (int)v19 >= (int)v9 )
    {
      v17 = -2147467259;
      goto LABEL_19;
    }
    v14[v9 + v19] = i;
  }
  v20 = LVBuildDescriptionString(a2, a3, &v14[v9], v9, a4);
  SharedFree(v13, v16);
  LocalFree(v14);
  return v20;
}

```

## disassembly

```asm
0x18002f2bc  mov     rax, rsp
0x18002f2bf  mov     [rax+8], rbx
0x18002f2c3  mov     [rax+20h], r9
0x18002f2c7  mov     [rax+18h], r8d
0x18002f2cb  mov     [rax+10h], rdx
0x18002f2cf  push    rbp
0x18002f2d0  push    rsi
0x18002f2d1  push    rdi
0x18002f2d2  push    r12
0x18002f2d4  push    r13
0x18002f2d6  push    r14
0x18002f2d8  push    r15
0x18002f2da  mov     rbp, rsp
0x18002f2dd  sub     rsp, 50h
0x18002f2e1  mov     r12, rdx
0x18002f2e4  mov     rbx, rcx
0x18002f2e7  mov     rcx, r12; hWnd
0x18002f2ea  xor     r9d, r9d; lParam
0x18002f2ed  xor     r8d, r8d; wParam
0x18002f2f0  mov     edx, 101Fh; Msg
0x18002f2f5  call    cs:__imp_SendMessageW
0x18002f2fb  xor     r13d, r13d
0x18002f2fe  test    rax, rax
0x18002f301  jz      loc_18002F485
0x18002f307  mov     ecx, [rbx+44h]
0x18002f30a  xor     r9d, r9d; unsigned __int64
0x18002f30d  mov     edx, [rbx+64h]
0x18002f310  mov     r8d, 1200h; unsigned int
0x18002f316  mov     [rbp+var_14], ecx
0x18002f319  lea     rcx, [rbp+var_20]
0x18002f31d  mov     [rsp+50h+var_28], rcx; __int64 *
0x18002f322  lea     rcx, [rbp+var_18]; struct OLEACC_TIMEOUTDATA *
0x18002f326  mov     [rbp+var_18], edx
0x18002f329  mov     rdx, rax; HWND
0x18002f32c  mov     [rbp+var_20], r13
0x18002f330  mov     [rsp+50h+lpNumberOfBytesRead], r13; __int64
0x18002f335  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002f33a  test    eax, eax
0x18002f33c  js      loc_18002F48A
0x18002f342  movsxd  rbx, dword ptr [rbp+var_20]
0x18002f346  cmp     ebx, 2
0x18002f349  jl      loc_18002F485
0x18002f34f  mov     eax, ebx
0x18002f351  mov     ecx, 0FFFFFFFFh
0x18002f356  shl     rax, 2
0x18002f35a  cmp     rax, rcx
0x18002f35d  ja      loc_18002F47E
0x18002f363  mov     r15d, eax
0x18002f366  lea     rdi, [r15+r15]
0x18002f36a  cmp     rdi, rcx
0x18002f36d  ja      loc_18002F47E
0x18002f373  lea     r8, [rbp+hProcess]; void **
0x18002f377  mov     [rbp+hProcess], r13
0x18002f37b  mov     rdx, r12; HWND
0x18002f37e  mov     ecx, r15d; dwSize
0x18002f381  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002f386  mov     rsi, rax
0x18002f389  test    rax, rax
0x18002f38c  jnz     short loc_18002F398
0x18002f38e  mov     eax, 8007000Eh
0x18002f393  jmp     loc_18002F48A
0x18002f398  mov     edx, edi; uBytes
0x18002f39a  mov     ecx, 40h ; '@'; uFlags
0x18002f39f  call    cs:__imp_LocalAlloc
0x18002f3a5  mov     r14, rax
0x18002f3a8  test    rax, rax
0x18002f3ab  jnz     short loc_18002F3BB
0x18002f3ad  mov     rdx, [rbp+hProcess]; hProcess
0x18002f3b1  mov     rcx, rsi; lpAddress
0x18002f3b4  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002f3b9  jmp     short loc_18002F38E
0x18002f3bb  lea     rax, [rbp+var_20]
0x18002f3bf  mov     r9, rbx; unsigned __int64
0x18002f3c2  mov     [rsp+50h+var_28], rax; __int64 *
0x18002f3c7  lea     rcx, [rbp+var_18]; struct OLEACC_TIMEOUTDATA *
0x18002f3cb  mov     r8d, 103Bh; unsigned int
0x18002f3d1  mov     [rsp+50h+lpNumberOfBytesRead], rsi; __int64
0x18002f3d6  mov     rdx, r12; HWND
0x18002f3d9  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002f3de  mov     r12, [rbp+hProcess]
0x18002f3e2  mov     edi, eax
0x18002f3e4  test    eax, eax
0x18002f3e6  js      short loc_18002F431
0x18002f3e8  cmp     [rbp+var_20], r13
0x18002f3ec  jnz     short loc_18002F3F5
0x18002f3ee  mov     edi, 8007000Eh
0x18002f3f3  jmp     short loc_18002F431
0x18002f3f5  mov     r9, r15; nSize
0x18002f3f8  mov     [rsp+50h+lpNumberOfBytesRead], r13; lpNumberOfBytesRead
0x18002f3fd  mov     r8, r14; lpBuffer
0x18002f400  lea     rdi, [r14+rbx*4]
0x18002f404  mov     rdx, rsi; lpBaseAddress
0x18002f407  mov     rcx, r12; hProcess
0x18002f40a  call    cs:__imp_ReadProcessMemory
0x18002f410  xor     ecx, ecx
0x18002f412  cmp     ecx, ebx
0x18002f414  jge     short loc_18002F449
0x18002f416  movsxd  rax, ecx
0x18002f419  movsxd  rdx, dword ptr [r14+rax*4]
0x18002f41d  test    edx, edx
0x18002f41f  js      short loc_18002F42C
0x18002f421  cmp     edx, ebx
0x18002f423  jge     short loc_18002F42C
0x18002f425  mov     [rdi+rdx*4], ecx
0x18002f428  inc     ecx
0x18002f42a  jmp     short loc_18002F412
0x18002f42c  mov     edi, 80004005h
0x18002f431  mov     rdx, r12; hProcess
0x18002f434  mov     rcx, rsi; lpAddress
0x18002f437  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002f43c  mov     rcx, r14; hMem
0x18002f43f  call    cs:__imp_LocalFree
0x18002f445  mov     eax, edi
0x18002f447  jmp     short loc_18002F48A
0x18002f449  mov     rax, [rbp+arg_18]
0x18002f44d  mov     r9d, ebx; int
0x18002f450  mov     edx, [rbp+arg_10]; int
0x18002f453  mov     r8, rdi; int *
0x18002f456  mov     rcx, [rbp+arg_8]; HWND
0x18002f45a  mov     [rsp+50h+lpNumberOfBytesRead], rax; unsigned __int16 **
0x18002f45f  call    ?LVBuildDescriptionString@@YAJPEAUHWND__@@HPEAHHPEAPEAG@Z; LVBuildDescriptionString(HWND__ *,int,int *,int,ushort * *)
0x18002f464  mov     rdx, r12; hProcess
0x18002f467  mov     rcx, rsi; lpAddress
0x18002f46a  mov     ebx, eax
0x18002f46c  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002f471  mov     rcx, r14; hMem
0x18002f474  call    cs:__imp_LocalFree
0x18002f47a  mov     eax, ebx
0x18002f47c  jmp     short loc_18002F48A
0x18002f47e  mov     eax, 80070216h
0x18002f483  jmp     short loc_18002F48A
0x18002f485  mov     eax, 80020003h
0x18002f48a  mov     rbx, [rsp+50h+arg_0]
0x18002f492  add     rsp, 50h
0x18002f496  pop     r15
0x18002f498  pop     r14
0x18002f49a  pop     r13
0x18002f49c  pop     r12
0x18002f49e  pop     rdi
0x18002f49f  pop     rsi
0x18002f4a0  pop     rbp
0x18002f4a1  retn
```
