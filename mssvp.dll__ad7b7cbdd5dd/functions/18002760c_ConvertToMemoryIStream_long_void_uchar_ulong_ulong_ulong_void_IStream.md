# ConvertToMemoryIStream(long (*)(void *,uchar *,ulong,ulong *),ulong,void *,IStream * *)

- ea: `0x18002760c`
- end: `0x180027775`
- name: `?ConvertToMemoryIStream@@YAJP6AJPEAXPEAEKPEAK@ZK0PEAPEAUIStream@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(IStream *, unsigned int, void *, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028254`

## callees

- `0x180005210`
- `0x18000557c`
- `0x18002760c`
- `0x180028238`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276c2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800276f1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800276f1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180027637`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180027637`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002774b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002774b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800276b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800276b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180027655`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180027655`

## pseudocode

```c
__int64 __fastcall ConvertToMemoryIStream(IStream *a1, unsigned int a2, void *a3, struct IStream **a4)
{
  int Error; // ebx
  HGLOBAL v8; // rdi
  unsigned __int8 *v9; // rbp
  unsigned int v10; // esi
  signed int LastError; // eax
  LPSTREAM v12; // rax
  struct IStream *v13; // rax
  LPSTREAM ppstm; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+68h] [rbp+10h] BYREF

  ppstm = a1;
  Error = 0;
  v8 = GlobalAlloc(2u, a2);
  if ( !v8 )
    Error = ResultFromLastError();
  v9 = 0;
  if ( Error >= 0 )
  {
    v9 = (unsigned __int8 *)GlobalLock(v8);
    if ( !v9 )
      Error = ResultFromLastError();
  }
  v10 = 0;
  if ( Error >= 0 )
  {
    while ( Error >= 0 && v10 < a2 )
    {
      v16 = 0;
      Error = StreamCallback(a3, &v9[v10], a2 - v10, &v16);
      if ( Error >= 0 )
      {
        v10 += v16;
        if ( Error == 1 || !v16 )
        {
          Error = 0;
          break;
        }
      }
    }
  }
  if ( v9 )
  {
    if ( !GlobalUnlock(v8) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          Error = (unsigned __int16)LastError | 0x80070000;
        else
          Error = LastError;
      }
    }
  }
  v12 = 0;
  ppstm = 0;
  if ( Error >= 0 )
  {
    Error = CreateStreamOnHGlobal(v8, 1, &ppstm);
    if ( Error >= 0 )
    {
      Error = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD))(*(_QWORD *)ppstm + 48LL))(ppstm, v10);
      if ( Error >= 0 )
      {
        v13 = ppstm;
        ppstm = 0;
        *a4 = v13;
        goto LABEL_27;
      }
    }
    v12 = ppstm;
  }
  if ( v8 && !v12 )
    GlobalFree(v8);
LABEL_27:
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppstm);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002760c  mov     [rsp+arg_10], rbx
0x180027611  mov     [rsp+arg_18], rbp
0x180027616  mov     [rsp+ppstm], rcx
0x18002761b  push    rsi
0x18002761c  push    rdi
0x18002761d  push    r12
0x18002761f  push    r14
0x180027621  push    r15
0x180027623  sub     rsp, 30h
0x180027627  mov     r12, r9
0x18002762a  mov     r15, r8
0x18002762d  mov     r14d, edx
0x180027630  xor     ebx, ebx
0x180027632  mov     edx, edx; dwBytes
0x180027634  lea     ecx, [rbx+2]; uFlags
0x180027637  call    cs:__imp_GlobalAlloc
0x18002763d  mov     rdi, rax
0x180027640  test    rax, rax
0x180027643  jnz     short loc_18002764C
0x180027645  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002764a  mov     ebx, eax
0x18002764c  xor     ebp, ebp
0x18002764e  test    ebx, ebx
0x180027650  js      short loc_18002766A
0x180027652  mov     rcx, rdi; hMem
0x180027655  call    cs:__imp_GlobalLock
0x18002765b  mov     rbp, rax
0x18002765e  test    rax, rax
0x180027661  jnz     short loc_18002766A
0x180027663  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180027668  mov     ebx, eax
0x18002766a  xor     esi, esi
0x18002766c  test    ebx, ebx
0x18002766e  js      short loc_1800276B0
0x180027670  test    ebx, ebx
0x180027672  js      short loc_1800276B0
0x180027674  cmp     esi, r14d
0x180027677  jnb     short loc_1800276B0
0x180027679  mov     [rsp+58h+arg_8], 0
0x180027681  mov     r8d, r14d
0x180027684  sub     r8d, esi; unsigned int
0x180027687  mov     edx, esi
0x180027689  add     rdx, rbp; unsigned __int8 *
0x18002768c  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x180027691  mov     rcx, r15; void *
0x180027694  call    ?StreamCallback@@YAJPEAXPEAEKPEAK@Z; StreamCallback(void *,uchar *,ulong,ulong *)
0x180027699  mov     ebx, eax
0x18002769b  test    eax, eax
0x18002769d  js      short loc_180027670
0x18002769f  mov     eax, [rsp+58h+arg_8]
0x1800276a3  add     esi, eax
0x1800276a5  cmp     ebx, 1
0x1800276a8  jz      short loc_1800276AE
0x1800276aa  test    eax, eax
0x1800276ac  jnz     short loc_180027670
0x1800276ae  xor     ebx, ebx
0x1800276b0  test    rbp, rbp
0x1800276b3  jz      short loc_1800276DB
0x1800276b5  mov     rcx, rdi; hMem
0x1800276b8  call    cs:__imp_GlobalUnlock
0x1800276be  test    eax, eax
0x1800276c0  jnz     short loc_1800276DB
0x1800276c2  call    cs:__imp_GetLastError
0x1800276c8  test    eax, eax
0x1800276ca  jz      short loc_1800276DB
0x1800276cc  jg      short loc_1800276D2
0x1800276ce  mov     ebx, eax
0x1800276d0  jmp     short loc_1800276DB
0x1800276d2  movzx   ebx, ax
0x1800276d5  or      ebx, 80070000h
0x1800276db  xor     eax, eax
0x1800276dd  mov     [rsp+58h+ppstm], rax
0x1800276e2  test    ebx, ebx
0x1800276e4  js      short loc_18002773E
0x1800276e6  lea     r8, [rsp+58h+ppstm]; ppstm
0x1800276eb  lea     edx, [rax+1]; fDeleteOnRelease
0x1800276ee  mov     rcx, rdi; hGlobal
0x1800276f1  call    cs:__imp_CreateStreamOnHGlobal
0x1800276f7  mov     ebx, eax
0x1800276f9  test    eax, eax
0x1800276fb  js      short loc_180027739
0x1800276fd  mov     dword ptr [rsp+58h+var_38], esi
0x180027701  mov     dword ptr [rsp+58h+var_38+4], 0
0x180027709  mov     rcx, [rsp+58h+ppstm]
0x18002770e  mov     rax, [rcx]
0x180027711  mov     rdx, [rsp+58h+var_38]
0x180027716  mov     rax, [rax+30h]
0x18002771a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002771f  mov     ebx, eax
0x180027721  test    eax, eax
0x180027723  js      short loc_180027739
0x180027725  mov     rax, [rsp+58h+ppstm]
0x18002772a  mov     [rsp+58h+ppstm], 0
0x180027733  mov     [r12], rax
0x180027737  jmp     short loc_180027752
0x180027739  mov     rax, [rsp+58h+ppstm]
0x18002773e  test    rdi, rdi
0x180027741  jz      short loc_180027752
0x180027743  test    rax, rax
0x180027746  jnz     short loc_180027752
0x180027748  mov     rcx, rdi; hMem
0x18002774b  call    cs:__imp_GlobalFree
0x180027751  nop
0x180027752  lea     rcx, [rsp+58h+ppstm]
0x180027757  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002775c  mov     eax, ebx
0x18002775e  mov     rbx, [rsp+58h+arg_10]
0x180027763  mov     rbp, [rsp+58h+arg_18]
0x180027768  add     rsp, 30h
0x18002776c  pop     r15
0x18002776e  pop     r14
0x180027770  pop     r12
0x180027772  pop     rdi
0x180027773  pop     rsi
0x180027774  retn
```
