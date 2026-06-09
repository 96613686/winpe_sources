# FileSendReceiveUrlRequest

- ea: `0x18002615c`
- end: `0x18002624c`
- name: `FileSendReceiveUrlRequest`
- size: `240`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a250`

## callees

- `0x1800013fc`
- `0x180002d24`
- `0x18000a990`
- `0x18001961c`
- `0x18002615c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002618d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002618d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026211`
- `CRYPT32!CryptMemAlloc` at `0x18002617a`
- `CRYPT32!CryptMemAlloc` at `0x18002617a`
- `CRYPT32!CryptMemFree` at `0x180026236`
- `CRYPT32!CryptMemFree` at `0x180026236`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800261b2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800261b2`

## pseudocode

```c
__int64 __fastcall FileSendReceiveUrlRequest(__int64 a1, __int64 a2)
{
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rdi
  unsigned int v7; // ebx
  int v8; // r9d
  unsigned int v9; // edx
  int v10; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  int v13; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  v4 = (unsigned __int8 *)CryptMemAlloc(*(_DWORD *)(a1 + 8));
  v5 = v4;
  if ( !v4 )
  {
    SetLastError(0x8007000E);
    return 0;
  }
  v13 = ReadFile(*(HANDLE *)a1, v4, *(_DWORD *)(a1 + 8), &NumberOfBytesRead, 0);
  v7 = v13;
  if ( v13 != 1 )
    goto LABEL_9;
  CCryptBlobArray::CCryptBlobArray((CCryptBlobArray *)&v10, 1u, 1u, &v13);
  v9 = *(_DWORD *)(a1 + 8);
  if ( NumberOfBytesRead != v9 )
  {
    SetLastError(0x80004005);
    v7 = 0;
    goto LABEL_8;
  }
  v7 = CCryptBlobArray::AddBlob((CCryptBlobArray *)&v10, v9, v5, v8);
  if ( v7 != 1 )
  {
LABEL_8:
    operator delete(hMem);
LABEL_9:
    if ( !v7 )
    {
      CryptDiagAddActionWithLastError(L"FileRetrieval");
      CryptMemFree(v5);
    }
    return v7;
  }
  *(_DWORD *)a2 = v10;
  *(_QWORD *)(a2 + 8) = hMem;
  return v7;
}

```

## disassembly

```asm
0x18002615c  mov     [rsp+arg_8], rbx
0x180026161  push    rsi
0x180026162  push    rdi
0x180026163  push    r14
0x180026165  sub     rsp, 50h
0x180026169  mov     rsi, rcx
0x18002616c  mov     [rsp+68h+NumberOfBytesRead], 0
0x180026174  mov     ecx, [rcx+8]; cbSize
0x180026177  mov     r14, rdx
0x18002617a  call    cs:__imp_CryptMemAlloc
0x180026180  mov     rdi, rax
0x180026183  test    rax, rax
0x180026186  jnz     short loc_18002619A
0x180026188  mov     ecx, 8007000Eh; dwErrCode
0x18002618d  call    cs:__imp_SetLastError
0x180026193  xor     eax, eax
0x180026195  jmp     loc_18002623E
0x18002619a  mov     r8d, [rsi+8]; nNumberOfBytesToRead
0x18002619e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800261a3  mov     rcx, [rsi]; hFile
0x1800261a6  mov     rdx, rdi; lpBuffer
0x1800261a9  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800261b2  call    cs:__imp_ReadFile
0x1800261b8  mov     [rsp+68h+arg_10], eax
0x1800261bf  mov     ebx, eax
0x1800261c1  cmp     eax, 1
0x1800261c4  jnz     short loc_180026223
0x1800261c6  lea     r9, [rsp+68h+arg_10]; int *
0x1800261ce  mov     edx, eax; unsigned int
0x1800261d0  mov     r8d, eax; unsigned int
0x1800261d3  lea     rcx, [rsp+68h+var_38]; this
0x1800261d8  call    ??0CCryptBlobArray@@QEAA@KKAEAH@Z; CCryptBlobArray::CCryptBlobArray(ulong,ulong,int &)
0x1800261dd  mov     edx, [rsi+8]; unsigned int
0x1800261e0  cmp     [rsp+68h+NumberOfBytesRead], edx
0x1800261e4  jnz     short loc_18002620C
0x1800261e6  mov     r8, rdi; unsigned __int8 *
0x1800261e9  lea     rcx, [rsp+68h+var_38]; this
0x1800261ee  call    ?AddBlob@CCryptBlobArray@@QEAAHKPEAEH@Z; CCryptBlobArray::AddBlob(ulong,uchar *,int)
0x1800261f3  mov     ebx, eax
0x1800261f5  cmp     eax, 1
0x1800261f8  jnz     short loc_180026219
0x1800261fa  mov     eax, [rsp+68h+var_38]
0x1800261fe  mov     [r14], eax
0x180026201  mov     rax, [rsp+68h+hMem]
0x180026206  mov     [r14+8], rax
0x18002620a  jmp     short loc_18002623C
0x18002620c  mov     ecx, 80004005h; dwErrCode
0x180026211  call    cs:__imp_SetLastError
0x180026217  xor     ebx, ebx
0x180026219  mov     rcx, [rsp+68h+hMem]; hMem
0x18002621e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026223  test    ebx, ebx
0x180026225  jnz     short loc_18002623C
0x180026227  lea     rcx, aFileretrieval; "FileRetrieval"
0x18002622e  call    CryptDiagAddActionWithLastError
0x180026233  mov     rcx, rdi; pv
0x180026236  call    cs:__imp_CryptMemFree
0x18002623c  mov     eax, ebx
0x18002623e  mov     rbx, [rsp+68h+arg_8]
0x180026243  add     rsp, 50h
0x180026247  pop     r14
0x180026249  pop     rdi
0x18002624a  pop     rsi
0x18002624b  retn
```
