# RAXferWorker::SendFileControlBlock(void)

- ea: `0x140046bc4`
- end: `0x140046dab`
- name: `?SendFileControlBlock@RAXferWorker@@QEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(RAXferWorker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140046428`

## callees

- `0x140034ce4`
- `0x14003bda4`
- `0x140045494`
- `0x140046bc4`
- `0x14004a190`
- `0x14004d010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140046d64`
- `KERNEL32!DeleteFileW` at `0x140046d64`
- `KERNEL32!GetLastError` at `0x140046cc4`
- `KERNEL32!GetLastError` at `0x140046cc4`
- `KERNEL32!GetFileSize` at `0x140046cb1`
- `KERNEL32!GetFileSize` at `0x140046cb1`
- `msvcrt!free` at `0x140046d74`
- `msvcrt!free` at `0x140046d74`
- `OLEAUT32!__imp_SysFreeString` at `0x140046d42`
- `OLEAUT32!__imp_SysFreeString` at `0x140046d42`

## pseudocode

```c
__int64 __fastcall RAXferWorker::SendFileControlBlock(RAXferWorker *this)
{
  struct IRDPSRAPIVirtualChannel *v2; // rbx
  __int64 v3; // rsi
  unsigned int (__fastcall ***v4)(_QWORD); // rcx
  unsigned int v5; // r9d
  int ControlVC; // edi
  void *v7; // rcx
  DWORD FileSize; // eax
  __int64 v9; // rdi
  signed int v10; // eax
  CEventLogger *v11; // rcx
  const WCHAR *v12; // rcx
  __int128 v14; // [rsp+30h] [rbp-20h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h]
  DWORD FileSizeHigh; // [rsp+80h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+38h] BYREF
  struct IRDPSRAPIVirtualChannel *v18; // [rsp+90h] [rbp+40h] BYREF

  FileSizeHigh = 0;
  v2 = 0;
  v18 = 0;
  bstrString = 0;
  v14 = 0;
  v15 = 0;
  v3 = 0;
  v4 = (unsigned int (__fastcall ***)(_QWORD))*((_QWORD *)this + 76);
  if ( !v4 )
  {
    v5 = 730;
LABEL_3:
    ControlVC = -2147467261;
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
      v5,
      L"RAXferWorker::SendFileControlBlock",
      0x80004003);
    goto LABEL_19;
  }
  if ( (**v4)(v4) )
    goto LABEL_6;
  v3 = *((_QWORD *)this + 76);
  ControlVC = CRATicket::GetControlVC(*((CRATicket **)this + 77), &v18, 0);
  if ( ControlVC < 0 )
  {
    v2 = v18;
    goto LABEL_19;
  }
  v2 = v18;
  if ( !v18 )
    goto LABEL_19;
  if ( *(_DWORD *)(v3 + 20) != 1 )
  {
LABEL_6:
    ControlVC = -2147418113;
    goto LABEL_19;
  }
  *(_QWORD *)&v14 = *(_QWORD *)(v3 + 48);
  DWORD2(v15) = *(_DWORD *)(v3 + 84);
  v7 = *(void **)(v3 + 40);
  if ( !v7 )
  {
    v5 = 765;
    goto LABEL_3;
  }
  FileSize = GetFileSize(v7, &FileSizeHigh);
  v9 = FileSize;
  if ( FileSize == -1 && GetLastError() )
  {
    ControlVC = -2147467259;
  }
  else
  {
    *((_QWORD *)&v14 + 1) = v9;
    *(_QWORD *)&v15 = (char *)this + 632;
    v10 = ComposeXMLControlBlock(
            (unsigned __int16 **)&v14,
            (struct CFileWorkItem *)v3,
            *(unsigned __int16 **)(*((_QWORD *)this + 77) + 520LL),
            &bstrString);
    ControlVC = v10;
    if ( v10 >= 0 )
      ControlVC = SendStringOverVC(v2, bstrString, *(_DWORD *)(v3 + 32), *(_DWORD *)(v3 + 72));
    else
      CEventLogger::LogError(
        v11,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raftp.cpp",
        0x30Eu,
        L"RAXferWorker::SendFileControlBlock",
        v10);
  }
LABEL_19:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v3 )
  {
    v12 = *(const WCHAR **)(v3 + 64);
    if ( v12 )
    {
      DeleteFileW(v12);
      free(*(void **)(v3 + 64));
      *(_QWORD *)(v3 + 64) = 0;
    }
  }
  if ( v2 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v2->lpVtbl->Release)(v2);
  return (unsigned int)ControlVC;
}

```

## disassembly

```asm
0x140046bc4  push    rbp
0x140046bc6  push    rbx
0x140046bc7  push    rsi
0x140046bc8  push    rdi
0x140046bc9  push    r14
0x140046bcb  mov     rbp, rsp
0x140046bce  sub     rsp, 50h
0x140046bd2  mov     r14, rcx
0x140046bd5  mov     [rbp+FileSizeHigh], 0
0x140046bdc  xor     ebx, ebx
0x140046bde  mov     [rbp+arg_10], rbx
0x140046be2  mov     [rbp+bstrString], rbx
0x140046be6  xorps   xmm0, xmm0
0x140046be9  movups  [rbp+var_20], xmm0
0x140046bed  movups  [rbp+var_10], xmm0
0x140046bf1  xor     esi, esi
0x140046bf3  mov     rcx, [rcx+260h]; this
0x140046bfa  test    rcx, rcx
0x140046bfd  jnz     short loc_140046C36
0x140046bff  mov     r9d, 2DAh; unsigned int
0x140046c05  mov     [rsp+50h+var_28], 80004003h; unsigned int
0x140046c0d  mov     edi, 80004003h
0x140046c12  lea     rax, aRaxferworkerSe; "RAXferWorker::SendFileControlBlock"
0x140046c19  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x140046c1e  lea     r8, aBaseDiagnosisR_15; "base\\diagnosis\\ra\\core\\lib\\raftp.c"...
0x140046c25  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140046c2c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140046c31  jmp     loc_140046D39
0x140046c36  mov     rax, [rcx]
0x140046c39  mov     rax, [rax]
0x140046c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046c41  test    eax, eax
0x140046c43  jz      short loc_140046C4F
0x140046c45  mov     edi, 8000FFFFh
0x140046c4a  jmp     loc_140046D39
0x140046c4f  mov     rsi, [r14+260h]
0x140046c56  xor     r8d, r8d; int
0x140046c59  lea     rdx, [rbp+arg_10]; struct IRDPSRAPIVirtualChannel **
0x140046c5d  mov     rcx, [r14+268h]; this
0x140046c64  call    ?GetControlVC@CRATicket@@QEAAJPEAPEAUIRDPSRAPIVirtualChannel@@H@Z; CRATicket::GetControlVC(IRDPSRAPIVirtualChannel * *,int)
0x140046c69  mov     edi, eax
0x140046c6b  test    eax, eax
0x140046c6d  js      loc_140046D35
0x140046c73  mov     rbx, [rbp+arg_10]
0x140046c77  test    rbx, rbx
0x140046c7a  setz    cl
0x140046c7d  test    cl, cl
0x140046c7f  jnz     loc_140046D39
0x140046c85  cmp     dword ptr [rsi+14h], 1
0x140046c89  jnz     short loc_140046C45
0x140046c8b  mov     rax, [rsi+30h]
0x140046c8f  mov     qword ptr [rbp+var_20], rax
0x140046c93  mov     eax, [rsi+54h]
0x140046c96  mov     dword ptr [rbp+var_10+8], eax
0x140046c99  mov     rcx, [rsi+28h]; hFile
0x140046c9d  test    rcx, rcx
0x140046ca0  jnz     short loc_140046CAD
0x140046ca2  mov     r9d, 2FDh
0x140046ca8  jmp     loc_140046C05
0x140046cad  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x140046cb1  call    cs:__imp_GetFileSize
0x140046cb8  nop     dword ptr [rax+rax+00h]
0x140046cbd  mov     edi, eax
0x140046cbf  cmp     eax, 0FFFFFFFFh
0x140046cc2  jnz     short loc_140046CDB
0x140046cc4  call    cs:__imp_GetLastError
0x140046ccb  nop     dword ptr [rax+rax+00h]
0x140046cd0  test    eax, eax
0x140046cd2  jz      short loc_140046CDB
0x140046cd4  mov     edi, 80004005h
0x140046cd9  jmp     short loc_140046D39
0x140046cdb  mov     qword ptr [rbp+var_20+8], rdi
0x140046cdf  lea     rax, [r14+278h]
0x140046ce6  mov     qword ptr [rbp+var_10], rax
0x140046cea  mov     r8, [r14+268h]
0x140046cf1  lea     r9, [rbp+bstrString]; unsigned __int16 **
0x140046cf5  mov     r8, [r8+208h]; unsigned __int16 *
0x140046cfc  mov     rdx, rsi; struct CFileWorkItem *
0x140046cff  lea     rcx, [rbp+var_20]; struct FILE_ATTRIBUTES *
0x140046d03  call    ?ComposeXMLControlBlock@@YAJPEAUFILE_ATTRIBUTES@@PEAVCFileWorkItem@@PEBGPEAPEAG@Z; ComposeXMLControlBlock(FILE_ATTRIBUTES *,CFileWorkItem *,ushort const *,ushort * *)
0x140046d08  mov     edi, eax
0x140046d0a  test    eax, eax
0x140046d0c  jns     short loc_140046D1D
0x140046d0e  mov     [rsp+50h+var_28], eax
0x140046d12  mov     r9d, 30Eh
0x140046d18  jmp     loc_140046C12
0x140046d1d  mov     r9d, [rsi+48h]; unsigned int
0x140046d21  mov     r8d, [rsi+20h]; int
0x140046d25  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140046d29  mov     rcx, rbx; struct IRDPSRAPIVirtualChannel *
0x140046d2c  call    ?SendStringOverVC@@YAJPEAUIRDPSRAPIVirtualChannel@@PEBGJK@Z; SendStringOverVC(IRDPSRAPIVirtualChannel *,ushort const *,long,ulong)
0x140046d31  mov     edi, eax
0x140046d33  jmp     short loc_140046D39
0x140046d35  mov     rbx, [rbp+arg_10]
0x140046d39  mov     rcx, [rbp+bstrString]; bstrString
0x140046d3d  test    rcx, rcx
0x140046d40  jz      short loc_140046D56
0x140046d42  call    cs:__imp_SysFreeString
0x140046d49  nop     dword ptr [rax+rax+00h]
0x140046d4e  mov     [rbp+bstrString], 0
0x140046d56  test    rsi, rsi
0x140046d59  jz      short loc_140046D88
0x140046d5b  mov     rcx, [rsi+40h]; lpFileName
0x140046d5f  test    rcx, rcx
0x140046d62  jz      short loc_140046D88
0x140046d64  call    cs:__imp_DeleteFileW
0x140046d6b  nop     dword ptr [rax+rax+00h]
0x140046d70  mov     rcx, [rsi+40h]; Block
0x140046d74  call    cs:__imp_free
0x140046d7b  nop     dword ptr [rax+rax+00h]
0x140046d80  mov     qword ptr [rsi+40h], 0
0x140046d88  test    rbx, rbx
0x140046d8b  jz      short loc_140046D9D
0x140046d8d  mov     rax, [rbx]
0x140046d90  mov     rcx, rbx
0x140046d93  mov     rax, [rax+10h]
0x140046d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046d9c  nop
0x140046d9d  mov     eax, edi
0x140046d9f  add     rsp, 50h
0x140046da3  pop     r14
0x140046da5  pop     rdi
0x140046da6  pop     rsi
0x140046da7  pop     rbx
0x140046da8  pop     rbp
0x140046da9  retn
```
