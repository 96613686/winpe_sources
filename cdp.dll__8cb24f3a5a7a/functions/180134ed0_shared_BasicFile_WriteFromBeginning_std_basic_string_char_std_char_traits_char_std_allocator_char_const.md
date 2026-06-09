# shared::BasicFile::WriteFromBeginning(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180134ed0`
- end: `0x180135063`
- name: `?WriteFromBeginning@BasicFile@shared@@UEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `403`
- prototype: `BOOL __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180133350`
- `0x1801333f0`
- `0x180134ed0`
- `0x180135158`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180134f37`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180134f37`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180134f9e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135002`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180134f9e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180135002`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180135048`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180135048`

## string_xrefs

- `0x180134f54`: `Failed to move file pointer to beginning of file`
- `0x180134f0d`: `Failed to write, file must first be opened/created`
- `0x180134fbb`: `Failed to write UTF8 BOM to file`
- `0x18013501f`: `Failed to write string contents to file`

## pseudocode

```c
BOOL __fastcall shared::BasicFile::WriteFromBeginning(__int64 a1, _DWORD *a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  DWORD v6; // r8d
  const char *v8; // [rsp+30h] [rbp-50h] BYREF
  int v9; // [rsp+38h] [rbp-48h]
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-40h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+10h] BYREF

  v4 = *(void **)(a1 + 8);
  if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = ".\\basicfile.cpp";
    v9 = 123;
    v5 = cdp::MakeException<cdp::HResultException<-2147221245>,>(
           pExceptionObject,
           &v8,
           "Failed to write, file must first be opened/created");
    cdp::CdpThrow<cdp::HResultException<-2147221245>>(&v8, v5);
  }
  if ( !SetFilePointerEx(v4, 0, 0, 0) )
  {
    v8 = ".\\basicfile.cpp";
    v9 = 128;
    cdp::MakeException<cdp::HResultException<-2147467259>,>(
      pExceptionObject,
      &v8,
      "Failed to move file pointer to beginning of file");
    throw (cdp::HResultException<-2147467259> *)pExceptionObject;
  }
  NumberOfBytesWritten = 0;
  if ( !WriteFile(*(HANDLE *)(a1 + 8), &cdp::UTF8BOM, 3u, &NumberOfBytesWritten, 0) )
  {
    v8 = ".\\basicfile.cpp";
    v9 = 134;
    cdp::MakeException<cdp::HResultException<-2147467259>,>(pExceptionObject, &v8, "Failed to write UTF8 BOM to file");
    throw (cdp::HResultException<-2147467259> *)pExceptionObject;
  }
  v6 = a2[4];
  if ( *((_QWORD *)a2 + 3) > 0xFu )
    a2 = *(_DWORD **)a2;
  if ( !WriteFile(*(HANDLE *)(a1 + 8), a2, v6, &NumberOfBytesWritten, 0) )
  {
    v8 = ".\\basicfile.cpp";
    v9 = 139;
    cdp::MakeException<cdp::HResultException<-2147467259>,>(
      pExceptionObject,
      &v8,
      "Failed to write string contents to file");
    throw (cdp::HResultException<-2147467259> *)pExceptionObject;
  }
  return SetEndOfFile(*(HANDLE *)(a1 + 8));
}

```

## disassembly

```asm
0x180134ed0  mov     [rsp-8+arg_8], rbx
0x180134ed5  mov     [rsp-8+arg_10], rdi
0x180134eda  push    rbp
0x180134edb  mov     rbp, rsp
0x180134ede  sub     rsp, 80h
0x180134ee5  mov     rbx, rdx
0x180134ee8  mov     rdi, rcx
0x180134eeb  mov     rcx, [rcx+8]; hFile
0x180134eef  lea     rax, [rcx+1]
0x180134ef3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180134ef9  jnz     short loc_180134F2F
0x180134efb  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180134f02  mov     [rbp+var_50], rax
0x180134f06  mov     [rbp+var_48], 7Bh ; '{'
0x180134f0d  lea     r8, aFailedToWriteF; "Failed to write, file must first be ope"...
0x180134f14  lea     rdx, [rbp+var_50]
0x180134f18  lea     rcx, [rbp+pExceptionObject]
0x180134f1c  call    ??$MakeException@V?$HResultException@$0?HPPLPOPN@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPOPN@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147221245>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180134f21  nop
0x180134f22  mov     rdx, rax
0x180134f25  lea     rcx, [rbp+var_50]
0x180134f29  call    ??$CdpThrow@V?$HResultException@$0?HPPLPOPN@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPOPN@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147221245>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147221245> &&)
0x180134f2f  xor     edx, edx; liDistanceToMove
0x180134f31  xor     r9d, r9d; dwMoveMethod
0x180134f34  xor     r8d, r8d; lpNewFilePointer
0x180134f37  call    cs:__imp_SetFilePointerEx
0x180134f3d  cmp     eax, 1
0x180134f40  jz      short loc_180134F79
0x180134f42  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180134f49  mov     [rbp+var_50], rax
0x180134f4d  mov     [rbp+var_48], 80h
0x180134f54  lea     r8, aFailedToMoveFi; "Failed to move file pointer to beginnin"...
0x180134f5b  lea     rdx, [rbp+var_50]
0x180134f5f  lea     rcx, [rbp+pExceptionObject]
0x180134f63  call    ??$MakeException@V?$HResultException@$0?HPPPLPPL@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPL@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467259>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180134f68  lea     rdx, _TI5?AV?$HResultException@$0?HPPPLPPL@@cdp@@; pThrowInfo
0x180134f6f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180134f73  call    _CxxThrowException_0
0x180134f79  mov     [rbp+NumberOfBytesWritten], 0
0x180134f80  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x180134f89  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180134f8d  mov     r8d, 3; nNumberOfBytesToWrite
0x180134f93  lea     rdx, ?UTF8BOM@cdp@@3QBDB; lpBuffer
0x180134f9a  mov     rcx, [rdi+8]; hFile
0x180134f9e  call    cs:__imp_WriteFile
0x180134fa4  cmp     eax, 1
0x180134fa7  jz      short loc_180134FE0
0x180134fa9  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180134fb0  mov     [rbp+var_50], rax
0x180134fb4  mov     [rbp+var_48], 86h
0x180134fbb  lea     r8, aFailedToWriteU; "Failed to write UTF8 BOM to file"
0x180134fc2  lea     rdx, [rbp+var_50]
0x180134fc6  lea     rcx, [rbp+pExceptionObject]
0x180134fca  call    ??$MakeException@V?$HResultException@$0?HPPPLPPL@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPL@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467259>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180134fcf  lea     rdx, _TI5?AV?$HResultException@$0?HPPPLPPL@@cdp@@; pThrowInfo
0x180134fd6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180134fda  call    _CxxThrowException_0
0x180134fe0  mov     r8d, [rbx+10h]; nNumberOfBytesToWrite
0x180134fe4  cmp     qword ptr [rbx+18h], 0Fh
0x180134fe9  jbe     short loc_180134FEE
0x180134feb  mov     rbx, [rbx]
0x180134fee  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x180134ff7  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180134ffb  mov     rdx, rbx; lpBuffer
0x180134ffe  mov     rcx, [rdi+8]; hFile
0x180135002  call    cs:__imp_WriteFile
0x180135008  cmp     eax, 1
0x18013500b  jz      short loc_180135044
0x18013500d  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180135014  mov     [rbp+var_50], rax
0x180135018  mov     [rbp+var_48], 8Bh
0x18013501f  lea     r8, aFailedToWriteS; "Failed to write string contents to file"
0x180135026  lea     rdx, [rbp+var_50]
0x18013502a  lea     rcx, [rbp+pExceptionObject]
0x18013502e  call    ??$MakeException@V?$HResultException@$0?HPPPLPPL@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPL@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467259>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180135033  lea     rdx, _TI5?AV?$HResultException@$0?HPPPLPPL@@cdp@@; pThrowInfo
0x18013503a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18013503e  call    _CxxThrowException_0
0x180135044  mov     rcx, [rdi+8]; hFile
0x180135048  call    cs:__imp_SetEndOfFile
0x18013504e  lea     r11, [rsp+80h+var_s0]
0x180135056  mov     rbx, [r11+18h]
0x18013505a  mov     rdi, [r11+20h]
0x18013505e  mov     rsp, r11
0x180135061  pop     rbp
0x180135062  retn
```
