# GetCORSystemDirectory

- ea: `0x18002d658`
- end: `0x18002d7fa`
- name: `GetCORSystemDirectory`
- size: `418`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180006530`
- `0x18002d2a8`
- `0x18002d34c`

## callees

- `0x180008710`
- `0x18000c1a8`
- `0x180028f48`
- `0x180029b38`
- `0x18002a7c8`
- `0x18002ba30`
- `0x18002d658`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18002d6b3`
- `KERNEL32!GetModuleFileNameW` at `0x18002d6b3`
- `KERNEL32!GetFileAttributesW` at `0x18002d76d`
- `KERNEL32!GetFileAttributesW` at `0x18002d7af`
- `KERNEL32!GetFileAttributesW` at `0x18002d76d`
- `KERNEL32!GetFileAttributesW` at `0x18002d7af`

## pseudocode

```c
__int64 __fastcall GetCORSystemDirectory(void *a1, __int64 a2, __int64 a3)
{
  CLRFullPath *v5; // rcx
  int v6; // ebx
  CLRFullPath *v7; // rcx
  const WCHAR *v8; // rax
  CLRFullPath *v9; // rcx
  const wchar_t *FullPath; // r8
  _OWORD v11[3]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  __int64 v13; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+78h] [rbp-88h]
  __int64 v17; // [rsp+80h] [rbp-80h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  int v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A0h] [rbp-60h]
  WCHAR Filename[264]; // [rsp+B0h] [rbp-50h] BYREF

  if ( !a3 )
    return 2147500035LL;
  if ( !g_hMod )
  {
    v14 = 0;
    v13 = 1;
    v12 = 0;
    DWORD2(v12) = 1;
    memset(v11, 0, sizeof(v11));
    v15 = 0;
    v16 = 1;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = -1;
    v6 = RuntimeRequest::RequestRuntimeDll((RuntimeRequest *)v11, 1, 0);
    if ( v6 >= 0 )
    {
      if ( !CLRFullPath::GetFullPath(v5) || (v8 = CLRFullPath::GetFullPath(v7), GetFileAttributesW(v8) == -1) )
      {
        if ( !lpFileName || GetFileAttributesW(lpFileName) == -1 )
        {
          v6 = -2147024894;
          goto LABEL_16;
        }
        FullPath = lpFileName;
      }
      else
      {
        FullPath = CLRFullPath::GetFullPath(v9);
      }
      wcscpy_s(Filename, 0x104u, FullPath);
      v6 = CopySystemDirectory(Filename, a1);
    }
LABEL_16:
    RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v11);
    return (unsigned int)v6;
  }
  if ( GetModuleFileNameW(g_hMod, Filename, 0x104u) )
    return CopySystemDirectory(Filename, a1);
  else
    return HRESULT_FROM_GetLastError();
}

```

## disassembly

```asm
0x18002d658  mov     [rsp-8+arg_8], rbx
0x18002d65d  mov     [rsp-8+arg_18], rsi
0x18002d662  push    rbp
0x18002d663  push    rdi
0x18002d664  push    r14
0x18002d666  lea     rbp, [rsp-1D0h]
0x18002d66e  sub     rsp, 2D0h
0x18002d675  mov     rax, cs:__security_cookie
0x18002d67c  xor     rax, rsp
0x18002d67f  mov     [rbp+1E0h+var_20], rax
0x18002d686  mov     rdi, r8
0x18002d689  mov     esi, edx
0x18002d68b  mov     r14, rcx
0x18002d68e  test    r8, r8
0x18002d691  jnz     short loc_18002D69D
0x18002d693  mov     eax, 80004003h
0x18002d698  jmp     loc_18002D7D3
0x18002d69d  mov     rcx, cs:?g_hMod@@3PEAUHINSTANCE__@@EA; hModule
0x18002d6a4  test    rcx, rcx
0x18002d6a7  jz      short loc_18002D6DE
0x18002d6a9  mov     r8d, 104h; nSize
0x18002d6af  lea     rdx, [rbp+1E0h+Filename]; lpFilename
0x18002d6b3  call    cs:__imp_GetModuleFileNameW
0x18002d6b9  test    eax, eax
0x18002d6bb  jnz     short loc_18002D6C7
0x18002d6bd  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18002d6c2  jmp     loc_18002D7D3
0x18002d6c7  mov     r9, rdi
0x18002d6ca  lea     rcx, [rbp+1E0h+Filename]; Src
0x18002d6ce  mov     r8d, esi
0x18002d6d1  mov     rdx, r14; void *
0x18002d6d4  call    CopySystemDirectory
0x18002d6d9  jmp     loc_18002D7D3
0x18002d6de  mov     edx, 1; int
0x18002d6e3  mov     [rsp+2E0h+var_278], 0
0x18002d6eb  xorps   xmm1, xmm1
0x18002d6ee  mov     [rsp+2E0h+var_280], rdx
0x18002d6f3  xorps   xmm0, xmm0
0x18002d6f6  movdqa  [rsp+2E0h+var_2B0], xmm1
0x18002d6fc  movups  [rsp+2E0h+var_290], xmm1
0x18002d701  xor     r8d, r8d; int *
0x18002d704  mov     dword ptr [rsp+2E0h+var_290+8], edx
0x18002d708  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18002d70d  movdqa  [rsp+2E0h+var_2C0], xmm0
0x18002d713  movdqa  [rsp+2E0h+var_2A0], xmm0
0x18002d719  mov     [rsp+2E0h+var_270], 0
0x18002d722  mov     [rsp+2E0h+var_268], edx
0x18002d726  mov     [rbp+1E0h+var_260], 0
0x18002d72e  mov     [rbp+1E0h+var_258], 0
0x18002d736  mov     [rbp+1E0h+var_250], 0
0x18002d73e  mov     [rbp+1E0h+var_248], 0
0x18002d745  mov     [rbp+1E0h+var_240], 0FFFFFFFFFFFFFFFFh
0x18002d74d  call    ?RequestRuntimeDll@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::RequestRuntimeDll(int,int *)
0x18002d752  mov     ebx, eax
0x18002d754  test    eax, eax
0x18002d756  js      short loc_18002D7C7
0x18002d758  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002d75d  or      ebx, 0FFFFFFFFh
0x18002d760  test    rax, rax
0x18002d763  jz      short loc_18002D7A3
0x18002d765  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002d76a  mov     rcx, rax; lpFileName
0x18002d76d  call    cs:__imp_GetFileAttributesW
0x18002d773  cmp     eax, ebx
0x18002d775  jz      short loc_18002D7A3
0x18002d777  call    ?GetFullPath@CLRFullPath@@QEAAPEAGXZ; CLRFullPath::GetFullPath(void)
0x18002d77c  mov     r8, rax; Source
0x18002d77f  mov     edx, 104h; SizeInWords
0x18002d784  lea     rcx, [rbp+1E0h+Filename]; Destination
0x18002d788  call    wcscpy_s
0x18002d78d  mov     r9, rdi
0x18002d790  lea     rcx, [rbp+1E0h+Filename]; Src
0x18002d794  mov     r8d, esi
0x18002d797  mov     rdx, r14; void *
0x18002d79a  call    CopySystemDirectory
0x18002d79f  mov     ebx, eax
0x18002d7a1  jmp     short loc_18002D7C7
0x18002d7a3  mov     rcx, cs:lpFileName; lpFileName
0x18002d7aa  test    rcx, rcx
0x18002d7ad  jz      short loc_18002D7C2
0x18002d7af  call    cs:__imp_GetFileAttributesW
0x18002d7b5  cmp     eax, ebx
0x18002d7b7  jz      short loc_18002D7C2
0x18002d7b9  mov     r8, cs:lpFileName
0x18002d7c0  jmp     short loc_18002D77F
0x18002d7c2  mov     ebx, 80070002h
0x18002d7c7  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18002d7cc  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002d7d1  mov     eax, ebx
0x18002d7d3  mov     rcx, [rbp+1E0h+var_20]
0x18002d7da  xor     rcx, rsp; StackCookie
0x18002d7dd  call    __security_check_cookie
0x18002d7e2  lea     r11, [rsp+2E0h+var_10]
0x18002d7ea  mov     rbx, [r11+28h]
0x18002d7ee  mov     rsi, [r11+38h]
0x18002d7f2  mov     rsp, r11
0x18002d7f5  pop     r14
0x18002d7f7  pop     rdi
0x18002d7f8  pop     rbp
0x18002d7f9  retn
```
