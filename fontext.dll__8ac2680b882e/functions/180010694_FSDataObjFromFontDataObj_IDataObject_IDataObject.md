# FSDataObjFromFontDataObj(IDataObject *,IDataObject * *)

- ea: `0x180010694`
- end: `0x1800108b1`
- name: `?FSDataObjFromFontDataObj@@YAJPEAUIDataObject@@PEAPEAU1@@Z`
- size: `541`
- prototype: `__int64 __fastcall(struct IDataObject *, struct IDataObject **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800104d0`

## callees

- `0x180010694`
- `0x18002265c`
- `0x18002c4a0`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x1800107c9`
- `SHELL32!SHParseDisplayName` at `0x1800107c9`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800107f2`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800107f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010845`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001085d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001085d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010765`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010765`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010883`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010883`
- `ole32!CreateBindCtx` at `0x1800106f0`
- `ole32!CreateBindCtx` at `0x1800106f0`

## pseudocode

```c
__int64 __fastcall FSDataObjFromFontDataObj(struct IDataObject *a1, struct IDataObject **a2)
{
  HRESULT v3; // ebx
  HRESULT v4; // eax
  unsigned int *v5; // rsi
  LPBC v6; // rdi
  struct IBindCtxVtbl *lpVtbl; // rax
  LPCITEMIDLIST *v8; // r14
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r15
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE ppsiItemArray[12]; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+44h] [rbp-BCh]
  WCHAR pszName[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_QWORD *)ppsiItemArray = 0;
  v3 = DataObj_CopyHIDA(a1, ppsiItemArray);
  if ( v3 >= 0 )
  {
    ppbc = 0;
    v4 = CreateBindCtx(0, &ppbc);
    v5 = *(unsigned int **)ppsiItemArray;
    v3 = v4;
    if ( v4 >= 0 )
    {
      v6 = ppbc;
      *(_DWORD *)ppsiItemArray = 16;
      *(_QWORD *)&ppsiItemArray[4] = 0;
      v15 = 0;
      v3 = ((__int64 (__fastcall *)(LPBC, _BYTE *))ppbc->lpVtbl->GetBindOptions)(ppbc, ppsiItemArray);
      if ( v3 >= 0 )
      {
        lpVtbl = v6->lpVtbl;
        *(_DWORD *)&ppsiItemArray[4] = 2;
        v3 = ((__int64 (__fastcall *)(LPBC, _BYTE *))lpVtbl->SetBindOptions)(v6, ppsiItemArray);
      }
      if ( v3 >= 0 )
      {
        v8 = (LPCITEMIDLIST *)LocalAlloc(0, 8LL * *v5);
        if ( v8 )
        {
          v9 = 0;
          v10 = 0;
          if ( !*v5 )
            goto LABEL_18;
          do
          {
            memset_0(pszName, 0, 0x208u);
            if ( (int)FID_FileName((const struct _ITEMIDLIST *)((char *)v5 + v5[v10 + 2]), 0, pszName) >= 0
              && SHParseDisplayName(pszName, ppbc, (LPITEMIDLIST *)&v8[v9], 0, 0) >= 0 )
            {
              v9 = (unsigned int)(v9 + 1);
            }
            ++v10;
          }
          while ( v10 < *v5 );
          if ( (_DWORD)v9 )
          {
            *(_QWORD *)ppsiItemArray = 0;
            v3 = SHCreateShellItemArrayFromIDLists(v9, v8, (IShellItemArray **)ppsiItemArray);
            if ( v3 >= 0 )
            {
              v3 = (*(__int64 (__fastcall **)(_QWORD, LPBC, const GUID *, GUID *, struct IDataObject **))(**(_QWORD **)ppsiItemArray + 24LL))(
                     *(_QWORD *)ppsiItemArray,
                     ppbc,
                     &BHID_SFUIObject,
                     &GUID_0000010e_0000_0000_c000_000000000046,
                     a2);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)ppsiItemArray + 16LL))(*(_QWORD *)ppsiItemArray);
            }
            v11 = 0;
            do
            {
              CoTaskMemFree((LPVOID)v8[v11]);
              v11 = (unsigned int)(v11 + 1);
            }
            while ( (unsigned int)v11 < (unsigned int)v9 );
          }
          else
          {
LABEL_18:
            v3 = -2147467259;
          }
          LocalFree(v8);
        }
        else
        {
          v3 = -2147024882;
        }
      }
    }
    if ( ppbc )
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    GlobalFree(v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010694  mov     [rsp-8+arg_10], rbx
0x180010699  push    rbp
0x18001069a  push    rsi
0x18001069b  push    rdi
0x18001069c  push    r14
0x18001069e  push    r15
0x1800106a0  lea     rbp, [rsp-170h]
0x1800106a8  sub     rsp, 270h
0x1800106af  mov     rax, cs:__security_cookie
0x1800106b6  xor     rax, rsp
0x1800106b9  mov     [rbp+190h+var_30], rax
0x1800106c0  mov     r15, rdx
0x1800106c3  mov     qword ptr [rsp+290h+ppsiItemArray], 0
0x1800106cc  lea     rdx, [rsp+290h+ppsiItemArray]
0x1800106d1  call    DataObj_CopyHIDA
0x1800106d6  mov     ebx, eax
0x1800106d8  test    eax, eax
0x1800106da  js      loc_180010889
0x1800106e0  lea     rdx, [rsp+290h+ppbc]; ppbc
0x1800106e5  mov     [rsp+290h+ppbc], 0
0x1800106ee  xor     ecx, ecx; reserved
0x1800106f0  call    cs:__imp_CreateBindCtx
0x1800106f6  mov     rsi, qword ptr [rsp+290h+ppsiItemArray]
0x1800106fb  mov     ebx, eax
0x1800106fd  test    eax, eax
0x1800106ff  js      loc_18001086A
0x180010705  mov     rdi, [rsp+290h+ppbc]
0x18001070a  lea     rdx, [rsp+290h+ppsiItemArray]
0x18001070f  xor     eax, eax
0x180010711  mov     dword ptr [rsp+290h+ppsiItemArray], 10h
0x180010719  mov     qword ptr [rsp+290h+ppsiItemArray+4], rax
0x18001071e  mov     rcx, rdi
0x180010721  mov     [rsp+290h+var_24C], eax
0x180010725  mov     rax, [rdi]
0x180010728  mov     rax, [rax+38h]
0x18001072c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010731  mov     ebx, eax
0x180010733  test    eax, eax
0x180010735  js      short loc_180010755
0x180010737  mov     rax, [rdi]
0x18001073a  lea     rdx, [rsp+290h+ppsiItemArray]
0x18001073f  mov     rcx, rdi
0x180010742  mov     dword ptr [rsp+290h+ppsiItemArray+4], 2
0x18001074a  mov     rax, [rax+30h]
0x18001074e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010753  mov     ebx, eax
0x180010755  test    ebx, ebx
0x180010757  js      loc_18001086A
0x18001075d  mov     edx, [rsi]
0x18001075f  xor     ecx, ecx; uFlags
0x180010761  shl     rdx, 3; uBytes
0x180010765  call    cs:__imp_LocalAlloc
0x18001076b  mov     r14, rax
0x18001076e  test    rax, rax
0x180010771  jz      loc_180010865
0x180010777  xor     edi, edi
0x180010779  xor     ebx, ebx
0x18001077b  cmp     [rsi], ebx
0x18001077d  jbe     loc_180010855
0x180010783  xor     edx, edx; Val
0x180010785  lea     rcx, [rsp+290h+pszName]; void *
0x18001078a  mov     r8d, 208h; Size
0x180010790  call    memset_0
0x180010795  movsxd  rax, ebx
0x180010798  lea     r8, [rsp+290h+pszName]; unsigned __int16 *
0x18001079d  xor     edx, edx; unsigned int
0x18001079f  mov     ecx, [rsi+rax*4+8]
0x1800107a3  add     rcx, rsi; struct _ITEMIDLIST *
0x1800107a6  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x1800107ab  test    eax, eax
0x1800107ad  js      short loc_1800107D5
0x1800107af  mov     rdx, [rsp+290h+ppbc]; pbc
0x1800107b4  lea     r8, [r14+rdi*8]; ppidl
0x1800107b8  xor     r9d, r9d; sfgaoIn
0x1800107bb  mov     [rsp+290h+psfgaoOut], 0; psfgaoOut
0x1800107c4  lea     rcx, [rsp+290h+pszName]; pszName
0x1800107c9  call    cs:__imp_SHParseDisplayName
0x1800107cf  test    eax, eax
0x1800107d1  js      short loc_1800107D5
0x1800107d3  inc     edi
0x1800107d5  inc     ebx
0x1800107d7  cmp     ebx, [rsi]
0x1800107d9  jb      short loc_180010783
0x1800107db  test    edi, edi
0x1800107dd  jz      short loc_180010855
0x1800107df  lea     r8, [rsp+290h+ppsiItemArray]; ppsiItemArray
0x1800107e4  mov     qword ptr [rsp+290h+ppsiItemArray], 0
0x1800107ed  mov     rdx, r14; rgpidl
0x1800107f0  mov     ecx, edi; cidl
0x1800107f2  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x1800107f8  mov     ebx, eax
0x1800107fa  test    eax, eax
0x1800107fc  js      short loc_18001083A
0x1800107fe  mov     rcx, qword ptr [rsp+290h+ppsiItemArray]
0x180010803  lea     r9, _GUID_0000010e_0000_0000_c000_000000000046
0x18001080a  mov     rdx, [rsp+290h+ppbc]
0x18001080f  lea     r8, BHID_SFUIObject
0x180010816  mov     [rsp+290h+psfgaoOut], r15
0x18001081b  mov     rax, [rcx]
0x18001081e  mov     rax, [rax+18h]
0x180010822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010827  mov     rcx, qword ptr [rsp+290h+ppsiItemArray]
0x18001082c  mov     ebx, eax
0x18001082e  mov     rax, [rcx]
0x180010831  mov     rax, [rax+10h]
0x180010835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083a  xor     r15d, r15d
0x18001083d  test    edi, edi
0x18001083f  jz      short loc_18001085A
0x180010841  mov     rcx, [r14+r15*8]; pv
0x180010845  call    cs:__imp_CoTaskMemFree
0x18001084b  inc     r15d
0x18001084e  cmp     r15d, edi
0x180010851  jb      short loc_180010841
0x180010853  jmp     short loc_18001085A
0x180010855  mov     ebx, 80004005h
0x18001085a  mov     rcx, r14; hMem
0x18001085d  call    cs:__imp_LocalFree
0x180010863  jmp     short loc_18001086A
0x180010865  mov     ebx, 8007000Eh
0x18001086a  mov     rcx, [rsp+290h+ppbc]
0x18001086f  test    rcx, rcx
0x180010872  jz      short loc_180010880
0x180010874  mov     rax, [rcx]
0x180010877  mov     rax, [rax+10h]
0x18001087b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010880  mov     rcx, rsi; hMem
0x180010883  call    cs:__imp_GlobalFree
0x180010889  mov     eax, ebx
0x18001088b  mov     rcx, [rbp+190h+var_30]
0x180010892  xor     rcx, rsp; StackCookie
0x180010895  call    __security_check_cookie
0x18001089a  mov     rbx, [rsp+290h+arg_10]
0x1800108a2  add     rsp, 270h
0x1800108a9  pop     r15
0x1800108ab  pop     r14
0x1800108ad  pop     rdi
0x1800108ae  pop     rsi
0x1800108af  pop     rbp
0x1800108b0  retn
```
