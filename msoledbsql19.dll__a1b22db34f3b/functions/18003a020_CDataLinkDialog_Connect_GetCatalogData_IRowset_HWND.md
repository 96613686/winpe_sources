# CDataLinkDialog_Connect::GetCatalogData(IRowset *,HWND__ *)

- ea: `0x18003a020`
- end: `0x18003a302`
- name: `?GetCatalogData@CDataLinkDialog_Connect@@AEAAJPEAUIRowset@@PEAUHWND__@@@Z`
- size: `738`
- prototype: `int(CDataLinkDialog_Connect *__hidden this, struct IRowset *, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003bc30`

## callees

- `0x180003090`
- `0x180003488`
- `0x180003d80`
- `0x18003a020`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003a229`
- `ole32!CoTaskMemFree` at `0x18003a229`
- `USER32!SendMessageW` at `0x18003a088`
- `USER32!SendMessageW` at `0x18003a21e`
- `USER32!SendMessageW` at `0x18003a088`
- `USER32!SendMessageW` at `0x18003a21e`

## pseudocode

```c
__int64 __fastcall CDataLinkDialog_Connect::GetCatalogData(CDataLinkDialog_Connect *this, struct IRowset *a2, HWND a3)
{
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v9; // eax
  int v10; // [rsp+40h] [rbp-D8h]
  int pExceptionObject; // [rsp+44h] [rbp-D4h] BYREF
  int v12; // [rsp+48h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+4Ch] [rbp-CCh] BYREF
  __int64 v14; // [rsp+58h] [rbp-C0h]
  LPARAM lParam[2]; // [rsp+60h] [rbp-B8h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+80h] [rbp-98h] BYREF
  __int64 v19; // [rsp+88h] [rbp-90h] BYREF
  _QWORD v20[2]; // [rsp+90h] [rbp-88h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-78h]
  __int128 v22; // [rsp+B0h] [rbp-68h]
  __int128 v23; // [rsp+C0h] [rbp-58h]
  __int128 v24; // [rsp+D0h] [rbp-48h]
  __int64 v25; // [rsp+E0h] [rbp-38h]

  v14 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v16 = &v19;
  *(_OWORD *)lParam = 0;
  SendMessageW(a3, 0x14Bu, 0, 0);
  try
  {
    v5 = ((__int64 (*)(void))a2->lpVtbl->QueryInterface)();
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(off_180260360[0], 2653193);
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    _mm_lfence();
    v21 = 0u;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0x408200000000LL;
    v20[0] = 1;
    v20[1] = 8;
    DWORD2(v23) = 5;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, __int64, __int64 *, _QWORD))(*(_QWORD *)v14 + 32LL))(
           v14,
           2,
           1,
           v20,
           16,
           &v17,
           0);
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(off_180260360[0], 2668553);
      v12 = v6;
      throw (long *)&v12;
    }
    do
    {
      v7 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD, _QWORD, __int64, __int64 *, __int64 **))a2->lpVtbl->GetNextRows)(
             a2,
             0,
             0,
             1,
             &v18,
             &v16);
      if ( !v18 )
        break;
      v7 = ((__int64 (__fastcall *)(struct IRowset *, __int64, __int64, LPARAM *))a2->lpVtbl->GetData)(
             a2,
             v19,
             v17,
             lParam);
      ((void (__fastcall *)(struct IRowset *, __int64, __int64 *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->ReleaseRows)(
        a2,
        1,
        v16,
        0,
        0,
        0);
      if ( v7 >= 0 && !LODWORD(lParam[0]) && lParam[1] )
      {
        SendMessageW(a3, 0x143u, 0, lParam[1]);
        CoTaskMemFree((LPVOID)lParam[1]);
        lParam[1] = 0;
      }
    }
    while ( v7 != 265926 );
  }
  catch ( long v13 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v9 = bidTraceHR(off_180260360[0], 2702345, v13);
    else
      v9 = v13;
    v10 = v9;
    if ( lParam[1] )
      CoTaskMemFree((LPVOID)lParam[1]);
    v7 = v10;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 48LL))(v14, v17, 0);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003a020  mov     [rsp+arg_0], rbx
0x18003a025  push    rsi
0x18003a026  push    rdi
0x18003a027  push    r14
0x18003a029  sub     rsp, 100h
0x18003a030  mov     rax, cs:__security_cookie
0x18003a037  xor     rax, rsp
0x18003a03a  mov     [rsp+118h+var_28], rax
0x18003a042  mov     rsi, r8
0x18003a045  mov     rdi, rdx
0x18003a048  xor     r14d, r14d
0x18003a04b  mov     [rsp+118h+var_C0], r14
0x18003a050  mov     [rsp+118h+var_A0], r14
0x18003a055  mov     [rsp+118h+var_98], r14
0x18003a05d  mov     [rsp+118h+var_90], r14
0x18003a065  lea     rax, [rsp+118h+var_90]
0x18003a06d  mov     [rsp+118h+var_A8], rax
0x18003a072  xorps   xmm0, xmm0
0x18003a075  movups  xmmword ptr [rsp+118h+lParam], xmm0
0x18003a07a  xor     r9d, r9d; lParam
0x18003a07d  xor     r8d, r8d; wParam
0x18003a080  mov     edx, 14Bh; Msg
0x18003a085  mov     rcx, rsi; hWnd
0x18003a088  call    cs:__imp_SendMessageW
0x18003a08e  mov     rax, [rdi]
0x18003a091  lea     r8, [rsp+118h+var_C0]
0x18003a096  lea     rdx, IID_IAccessor
0x18003a09d  mov     rcx, rdi
0x18003a0a0  mov     rax, [rax]
0x18003a0a3  call    cs:__guard_dispatch_icall_fptr
0x18003a0a9  mov     ebx, eax
0x18003a0ab  test    eax, eax
0x18003a0ad  js      loc_18003A2A2
0x18003a0b3  lfence
0x18003a0b6  xorps   xmm0, xmm0
0x18003a0b9  xor     eax, eax
0x18003a0bb  movups  [rsp+118h+var_88], xmm0
0x18003a0c3  movups  [rsp+118h+var_78], xmm0
0x18003a0cb  movups  [rsp+118h+var_68], xmm0
0x18003a0d3  movups  [rsp+118h+var_58], xmm0
0x18003a0db  movups  [rsp+118h+var_48], xmm0
0x18003a0e3  mov     [rsp+118h+var_38], rax
0x18003a0eb  mov     qword ptr [rsp+118h+var_88], 1
0x18003a0f7  mov     qword ptr [rsp+118h+var_88+8], 8
0x18003a103  mov     qword ptr [rsp+118h+var_78+8], r14
0x18003a10b  mov     dword ptr [rsp+118h+var_58+8], 5
0x18003a116  mov     eax, 4082h
0x18003a11b  mov     word ptr [rsp+118h+var_38+4], ax
0x18003a123  mov     rcx, [rsp+118h+var_C0]
0x18003a128  mov     rax, [rcx]
0x18003a12b  mov     [rsp+118h+var_E8], r14
0x18003a130  lea     rdx, [rsp+118h+var_A0]
0x18003a135  mov     [rsp+118h+var_F0], rdx
0x18003a13a  mov     [rsp+118h+var_F8], 10h
0x18003a143  lea     r9, [rsp+118h+var_88]
0x18003a14b  mov     edx, 2
0x18003a150  mov     r8d, 1
0x18003a156  mov     rax, [rax+20h]
0x18003a15a  call    cs:__guard_dispatch_icall_fptr
0x18003a160  mov     ebx, eax
0x18003a162  test    eax, eax
0x18003a164  js      loc_18003A2D1
0x18003a16a  nop     word ptr [rax+rax+00h]
0x18003a170  mov     rax, [rdi]
0x18003a173  lea     rcx, [rsp+118h+var_A8]
0x18003a178  mov     [rsp+118h+var_F0], rcx
0x18003a17d  lea     rcx, [rsp+118h+var_98]
0x18003a185  mov     [rsp+118h+var_F8], rcx
0x18003a18a  mov     r9d, 1
0x18003a190  xor     r8d, r8d
0x18003a193  xor     edx, edx
0x18003a195  mov     rcx, rdi
0x18003a198  mov     rax, [rax+28h]
0x18003a19c  call    cs:__guard_dispatch_icall_fptr
0x18003a1a2  mov     ebx, eax
0x18003a1a4  cmp     [rsp+118h+var_98], 0
0x18003a1ad  jz      loc_18003A240
0x18003a1b3  mov     rax, [rdi]
0x18003a1b6  lea     r9, [rsp+118h+lParam]
0x18003a1bb  mov     r8, [rsp+118h+var_A0]
0x18003a1c0  mov     rdx, [rsp+118h+var_90]
0x18003a1c8  mov     rcx, rdi
0x18003a1cb  mov     rax, [rax+20h]
0x18003a1cf  call    cs:__guard_dispatch_icall_fptr
0x18003a1d5  mov     ebx, eax
0x18003a1d7  mov     rax, [rdi]
0x18003a1da  mov     [rsp+118h+var_F0], r14
0x18003a1df  mov     [rsp+118h+var_F8], r14
0x18003a1e4  xor     r9d, r9d
0x18003a1e7  mov     r8, [rsp+118h+var_A8]
0x18003a1ec  mov     edx, 1
0x18003a1f1  mov     rcx, rdi
0x18003a1f4  mov     rax, [rax+30h]
0x18003a1f8  call    cs:__guard_dispatch_icall_fptr
0x18003a1fe  test    ebx, ebx
0x18003a200  js      short loc_18003A234
0x18003a202  cmp     dword ptr [rsp+118h+lParam], 0
0x18003a207  jnz     short loc_18003A234
0x18003a209  mov     r9, [rsp+118h+lParam+8]; lParam
0x18003a20e  test    r9, r9
0x18003a211  jz      short loc_18003A234
0x18003a213  xor     r8d, r8d; wParam
0x18003a216  mov     edx, 143h; Msg
0x18003a21b  mov     rcx, rsi; hWnd
0x18003a21e  call    cs:__imp_SendMessageW
0x18003a224  mov     rcx, [rsp+118h+lParam+8]; pv
0x18003a229  call    cs:__imp_CoTaskMemFree
0x18003a22f  mov     [rsp+118h+lParam+8], r14
0x18003a234  cmp     ebx, 40EC6h
0x18003a23a  jnz     loc_18003A170
0x18003a240  jmp     short loc_18003A246
0x18003a242  mov     ebx, [rsp+118h+var_D8]
0x18003a246  mov     rdx, [rsp+118h+var_A0]
0x18003a24b  test    rdx, rdx
0x18003a24e  jz      short loc_18003A265
0x18003a250  mov     rcx, [rsp+118h+var_C0]
0x18003a255  mov     rax, [rcx]
0x18003a258  xor     r8d, r8d
0x18003a25b  mov     rax, [rax+30h]
0x18003a25f  call    cs:__guard_dispatch_icall_fptr
0x18003a265  mov     rcx, [rsp+118h+var_C0]
0x18003a26a  test    rcx, rcx
0x18003a26d  jz      short loc_18003A27C
0x18003a26f  mov     rdx, [rcx]
0x18003a272  mov     rax, [rdx+10h]
0x18003a276  call    cs:__guard_dispatch_icall_fptr
0x18003a27c  mov     eax, ebx
0x18003a27e  mov     rcx, [rsp+118h+var_28]
0x18003a286  xor     rcx, rsp; StackCookie
0x18003a289  call    __security_check_cookie
0x18003a28e  mov     rbx, [rsp+118h+arg_0]
0x18003a296  add     rsp, 100h
0x18003a29d  pop     r14
0x18003a29f  pop     rdi
0x18003a2a0  pop     rsi
0x18003a2a1  retn
0x18003a2a2  test    byte ptr cs:_bidGblFlags, 2
0x18003a2a9  jz      short loc_18003A2BC
0x18003a2ab  mov     edx, 287C09h
0x18003a2b0  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003a2b7  call    _bidTraceMark
0x18003a2bc  mov     [rsp+118h+pExceptionObject], ebx
0x18003a2c0  lea     rdx, _TI1J; pThrowInfo
0x18003a2c7  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18003a2cc  call    _CxxThrowException_0
0x18003a2d1  test    byte ptr cs:_bidGblFlags, 2
0x18003a2d8  jz      short loc_18003A2EB
0x18003a2da  mov     edx, 28B809h
0x18003a2df  mov     rcx, cs:off_180260360; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18003a2e6  call    _bidTraceMark
0x18003a2eb  mov     [rsp+118h+var_D0], ebx
0x18003a2ef  lea     rdx, _TI1J; pThrowInfo
0x18003a2f6  lea     rcx, [rsp+118h+var_D0]; pExceptionObject
0x18003a2fb  call    _CxxThrowException_0
```
