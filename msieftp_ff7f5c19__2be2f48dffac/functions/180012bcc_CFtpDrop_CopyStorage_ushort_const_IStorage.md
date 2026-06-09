# CFtpDrop::CopyStorage(ushort const *,IStorage *)

- ea: `0x180012bcc`
- end: `0x180012e22`
- name: `?CopyStorage@CFtpDrop@@IEAAJPEBGPEAUIStorage@@@Z`
- size: `598`
- prototype: `int(CFtpDrop *__hidden this, const unsigned __int16 *, struct IStorage *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001262c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180012060`
- `0x180012bcc`
- `0x180013a80`
- `0x180014c6c`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012dcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d99`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180012dc2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180012dc2`
- `ole32!StgCreateDocfile` at `0x180012c10`
- `ole32!StgCreateDocfile` at `0x180012c10`

## pseudocode

```c
__int64 __fastcall CFtpDrop::CopyStorage(HWND *this, const unsigned __int16 *a2, struct IStorage *a3)
{
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r9d
  int v9; // edi
  int v10; // edx
  unsigned int v11; // r9d
  int v12; // r12d
  const unsigned __int16 *v13; // rcx
  CDropOperation *v14; // r14
  int v15; // edx
  unsigned int v16; // r9d
  int v17; // eax
  unsigned __int16 *v18; // r15
  CDropOperation *v19; // rbx
  int v20; // r8d
  unsigned int v22; // [rsp+28h] [rbp-71h]
  unsigned int v23; // [rsp+30h] [rbp-69h]
  IStorage *ppstgOpen; // [rsp+40h] [rbp-59h] BYREF
  CDropOperation *v25; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR lpFileName[10]; // [rsp+60h] [rbp-39h] BYREF

  ppstgOpen = 0;
  v6 = StgCreateDocfile(0, 0x1012u, 0, &ppstgOpen);
  v9 = v6;
  if ( v6 < 0 )
  {
    v20 = v6;
    goto LABEL_16;
  }
  memset_0(lpFileName, 0, sizeof(lpFileName));
  v9 = ((__int64 (__fastcall *)(IStorage *, LPCWSTR *, _QWORD))ppstgOpen->lpVtbl->Stat)(ppstgOpen, lpFileName, 0);
  if ( v9 < 0 )
  {
    ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    v20 = v9;
LABEL_16:
    DisplayWininetError(this[4], v7, v20, v8, 0x19Du, v22, v23, 0);
    return (unsigned int)v9;
  }
  v9 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, IStorage *))a3->lpVtbl->CopyTo)(
         a3,
         0,
         0,
         0,
         ppstgOpen);
  ((void (__fastcall *)(IStorage *, __int64))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 1);
  ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
  ppstgOpen = 0;
  if ( v9 < 0 )
  {
    DisplayWininetError(this[4], v10, v9, v11, 0x19Du, v22, v23, 0);
  }
  else
  {
    v12 = *((_DWORD *)this + 12);
    v13 = lpFileName[0];
    *((_DWORD *)this + 12) = 1;
    v26 = 0;
    v14 = 0;
    v9 = LocalAllocStringDoubleNullTerminate(v13, &v26);
    v25 = 0;
    if ( v9 >= 0 )
    {
      v17 = LocalAllocStringDoubleNullTerminate(a2, (unsigned __int16 **)&v25);
      v14 = v25;
      v9 = v17;
    }
    v18 = v26;
    v25 = 0;
    if ( v9 < 0 )
      goto LABEL_9;
    v23 = *((_DWORD *)this + 16);
    v22 = *((_DWORD *)this + 12);
    v9 = CDropOperation_Create(this[2], this[4], v26, v14, &v25);
    if ( v9 < 0
      || (v19 = v25,
          v18 = 0,
          v14 = 0,
          (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)v25 + 8LL))(v25),
          v9 = CDropOperation::_ThreadProcCB(v19),
          (*(void (__fastcall **)(CDropOperation *))(*(_QWORD *)v19 + 16LL))(v19),
          v9 < 0) )
    {
LABEL_9:
      if ( v9 != -2147023673 )
        DisplayWininetError(this[4], v15, v9, v16, 0x195u, v22, v23, 0);
    }
    *((_DWORD *)this + 12) = v12;
    LocalFree(v18);
    LocalFree(v14);
  }
  DeleteFileW(lpFileName[0]);
  CoTaskMemFree((LPVOID)lpFileName[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012bcc  push    rbp
0x180012bce  push    rbx
0x180012bcf  push    rsi
0x180012bd0  push    rdi
0x180012bd1  push    r12
0x180012bd3  push    r14
0x180012bd5  push    r15
0x180012bd7  lea     rbp, [rsp-27h]
0x180012bdc  sub     rsp, 0C0h
0x180012be3  mov     rax, cs:__security_cookie
0x180012bea  xor     rax, rsp
0x180012bed  mov     [rbp+57h+var_40], rax
0x180012bf1  mov     r14, r8
0x180012bf4  mov     [rbp+57h+ppstgOpen], 0
0x180012bfc  mov     rbx, rdx
0x180012bff  lea     r9, [rbp+57h+ppstgOpen]; ppstgOpen
0x180012c03  mov     rsi, rcx
0x180012c06  xor     r8d, r8d; reserved
0x180012c09  mov     edx, 1012h; grfMode
0x180012c0e  xor     ecx, ecx; pwcsName
0x180012c10  call    cs:__imp_StgCreateDocfile
0x180012c16  mov     edi, eax
0x180012c18  test    eax, eax
0x180012c1a  js      loc_180012DE5
0x180012c20  xor     edx, edx; Val
0x180012c22  lea     rcx, [rbp+57h+lpFileName]; void *
0x180012c26  lea     r8d, [rdx+50h]; Size
0x180012c2a  call    memset_0
0x180012c2f  mov     rcx, [rbp+57h+ppstgOpen]
0x180012c33  lea     rdx, [rbp+57h+lpFileName]
0x180012c37  xor     r8d, r8d
0x180012c3a  mov     rax, [rcx]
0x180012c3d  mov     rax, [rax+88h]
0x180012c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c49  mov     rcx, [rbp+57h+ppstgOpen]
0x180012c4d  mov     edi, eax
0x180012c4f  test    eax, eax
0x180012c51  js      loc_180012DD4
0x180012c57  mov     rax, [r14]
0x180012c5a  xor     r9d, r9d
0x180012c5d  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180012c62  xor     r8d, r8d
0x180012c65  xor     edx, edx
0x180012c67  mov     rcx, r14
0x180012c6a  mov     rax, [rax+38h]
0x180012c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c73  mov     rcx, [rbp+57h+ppstgOpen]
0x180012c77  mov     edi, eax
0x180012c79  mov     r14d, 1
0x180012c7f  mov     edx, r14d
0x180012c82  mov     rax, [rcx]
0x180012c85  mov     rax, [rax+48h]
0x180012c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c8e  mov     rcx, [rbp+57h+ppstgOpen]
0x180012c92  mov     rax, [rcx]
0x180012c95  mov     rax, [rax+10h]
0x180012c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9e  mov     [rbp+57h+ppstgOpen], 0
0x180012ca6  test    edi, edi
0x180012ca8  js      loc_180012DA1
0x180012cae  mov     r12d, [rsi+30h]
0x180012cb2  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x180012cb6  mov     rcx, [rbp+57h+lpFileName]; unsigned __int16 *
0x180012cba  mov     [rsi+30h], r14d
0x180012cbe  mov     [rbp+57h+var_A0], 0
0x180012cc6  call    ?LocalAllocStringDoubleNullTerminate@@YAJPEBGPEAPEAG@Z; LocalAllocStringDoubleNullTerminate(ushort const *,ushort * *)
0x180012ccb  xor     r14d, r14d
0x180012cce  mov     edi, eax
0x180012cd0  mov     [rbp+57h+var_A8], r14
0x180012cd4  test    eax, eax
0x180012cd6  js      short loc_180012CEA
0x180012cd8  lea     rdx, [rbp+57h+var_A8]; unsigned __int16 **
0x180012cdc  mov     rcx, rbx; unsigned __int16 *
0x180012cdf  call    ?LocalAllocStringDoubleNullTerminate@@YAJPEBGPEAPEAG@Z; LocalAllocStringDoubleNullTerminate(ushort const *,ushort * *)
0x180012ce4  mov     r14, [rbp+57h+var_A8]
0x180012ce8  mov     edi, eax
0x180012cea  mov     r15, [rbp+57h+var_A0]
0x180012cee  mov     [rbp+57h+var_A8], 0
0x180012cf6  test    edi, edi
0x180012cf8  js      short loc_180012D64
0x180012cfa  mov     eax, [rsi+40h]
0x180012cfd  mov     r9, r14
0x180012d00  mov     rdx, [rsi+20h]
0x180012d04  mov     r8, r15
0x180012d07  mov     rcx, [rsi+10h]
0x180012d0b  mov     dword ptr [rsp+0F0h+var_B8], eax
0x180012d0f  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x180012d13  mov     eax, [rsi+30h]
0x180012d16  mov     [rsp+0F0h+var_C8], eax; unsigned int
0x180012d1a  lea     rax, [rbp+57h+var_A8]
0x180012d1e  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180012d23  call    ?CDropOperation_Create@@YAJPEAVCFtpFolder@@PEAUHWND__@@PEBG2PEAPEAVCDropOperation@@KW4OPS@@H@Z; CDropOperation_Create(CFtpFolder *,HWND__ *,ushort const *,ushort const *,CDropOperation * *,ulong,OPS,int)
0x180012d28  mov     edi, eax
0x180012d2a  test    eax, eax
0x180012d2c  js      short loc_180012D64
0x180012d2e  mov     rbx, [rbp+57h+var_A8]
0x180012d32  xor     r15d, r15d
0x180012d35  mov     rcx, rbx
0x180012d38  xor     r14d, r14d
0x180012d3b  mov     rax, [rbx]
0x180012d3e  mov     rax, [rax+8]
0x180012d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d47  mov     rcx, rbx; this
0x180012d4a  call    ?_ThreadProcCB@CDropOperation@@IEAAJXZ; CDropOperation::_ThreadProcCB(void)
0x180012d4f  mov     edi, eax
0x180012d51  mov     rcx, rbx
0x180012d54  mov     rax, [rbx]
0x180012d57  mov     rax, [rax+10h]
0x180012d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d60  test    edi, edi
0x180012d62  jns     short loc_180012D89
0x180012d64  cmp     edi, 800704C7h
0x180012d6a  jz      short loc_180012D89
0x180012d6c  mov     rcx, [rsi+20h]; HWND
0x180012d70  mov     r8d, edi; int
0x180012d73  mov     [rsp+0F0h+var_B8], 0; struct IProgressDialog *
0x180012d7c  mov     [rsp+0F0h+var_D0], 195h; unsigned int
0x180012d84  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180012d89  mov     rcx, r15; hMem
0x180012d8c  mov     [rsi+30h], r12d
0x180012d90  call    cs:__imp_LocalFree
0x180012d96  mov     rcx, r14; hMem
0x180012d99  call    cs:__imp_LocalFree
0x180012d9f  jmp     short loc_180012DBE
0x180012da1  mov     rcx, [rsi+20h]; HWND
0x180012da5  mov     r8d, edi; int
0x180012da8  mov     [rsp+0F0h+var_B8], 0; struct IProgressDialog *
0x180012db1  mov     [rsp+0F0h+var_D0], 19Dh; unsigned int
0x180012db9  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180012dbe  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180012dc2  call    cs:__imp_DeleteFileW
0x180012dc8  mov     rcx, [rbp+57h+lpFileName]; pv
0x180012dcc  call    cs:__imp_CoTaskMemFree
0x180012dd2  jmp     short loc_180012E02
0x180012dd4  mov     rax, [rcx]
0x180012dd7  mov     rax, [rax+10h]
0x180012ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012de0  mov     r8d, edi
0x180012de3  jmp     short loc_180012DE8
0x180012de5  mov     r8d, eax; int
0x180012de8  mov     rcx, [rsi+20h]; HWND
0x180012dec  mov     [rsp+0F0h+var_B8], 0; struct IProgressDialog *
0x180012df5  mov     [rsp+0F0h+var_D0], 19Dh; unsigned int
0x180012dfd  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180012e02  mov     eax, edi
0x180012e04  mov     rcx, [rbp+57h+var_40]
0x180012e08  xor     rcx, rsp; StackCookie
0x180012e0b  call    __security_check_cookie
0x180012e10  add     rsp, 0C0h
0x180012e17  pop     r15
0x180012e19  pop     r14
0x180012e1b  pop     r12
0x180012e1d  pop     rdi
0x180012e1e  pop     rsi
0x180012e1f  pop     rbx
0x180012e20  pop     rbp
0x180012e21  retn
```
