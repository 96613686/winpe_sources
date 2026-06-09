# SipFile::ConvertUnicodeStringToFileEncoding(ushort const *,ulong,uchar * *,ulong *)

- ea: `0x180003648`
- end: `0x1800037b6`
- name: `?ConvertUnicodeStringToFileEncoding@SipFile@@IEAAKPEBGKPEAPEAEPEAK@Z`
- size: `366`
- prototype: `unsigned int __usercall@<eax>(SipFile *__hidden this@<rcx>, LPCWCH lpWideCharStr@<rdx>, unsigned int cchWideChar@<r8d>, unsigned __int8 **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800025b0`
- `0x180004fd4`

## callees

- `0x180001008`
- `0x180001014`
- `0x180003648`
- `0x180003fe4`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180003727`
- `KERNEL32!WideCharToMultiByte` at `0x180003778`
- `KERNEL32!WideCharToMultiByte` at `0x180003727`
- `KERNEL32!WideCharToMultiByte` at `0x180003778`
- `KERNEL32!GetLastError` at `0x180003733`
- `KERNEL32!GetLastError` at `0x180003733`

## pseudocode

```c
__int64 __fastcall SipFile::ConvertUnicodeStringToFileEncoding(
        SipFile *this,
        LPCWCH lpWideCharStr,
        int cchWideChar,
        CHAR **a4,
        unsigned int *a5)
{
  __int64 cbMultiByte; // rbp
  unsigned int *v10; // rsi
  unsigned int FileType; // ebx
  UINT v12; // r15d
  unsigned int v13; // eax
  CHAR *lpMultiByteStr; // rax
  CHAR *v15; // rdi
  int v17; // [rsp+A8h] [rbp+20h] BYREF

  LODWORD(cbMultiByte) = 0;
  v17 = 0;
  if ( !a4 )
    return 87;
  v10 = a5;
  if ( !a5 )
    return 87;
  *a4 = 0;
  *v10 = 0;
  if ( !lpWideCharStr || !cchWideChar )
    return 87;
  FileType = SipFile::GetFileType(this, (enum FileType *)&v17);
  if ( !FileType )
  {
    if ( v17 == 2 )
    {
      *a4 = 0;
    }
    else
    {
      v17 = 0;
      FileType = SipFile::GetFileType(this, (enum FileType *)&v17);
      if ( FileType )
        return FileType;
      if ( v17 == 1 )
      {
        v12 = 0;
      }
      else
      {
        if ( v17 != 4 )
          return 13;
        v12 = 65001;
      }
      v13 = WideCharToMultiByte(v12, 0, lpWideCharStr, cchWideChar, 0, 0, 0, 0);
      cbMultiByte = v13;
      if ( !v13 )
        return GetLastError();
      lpMultiByteStr = (CHAR *)operator new(v13 + 1);
      v15 = lpMultiByteStr;
      if ( !lpMultiByteStr )
        return 8;
      if ( (_DWORD)cbMultiByte != WideCharToMultiByte(
                                    v12,
                                    0,
                                    lpWideCharStr,
                                    cchWideChar,
                                    lpMultiByteStr,
                                    cbMultiByte,
                                    0,
                                    0) )
      {
        operator delete(v15);
        return 122;
      }
      v15[cbMultiByte] = 0;
      *a4 = v15;
    }
    *v10 = cbMultiByte;
  }
  return FileType;
}

```

## disassembly

```asm
0x180003648  mov     rax, rsp
0x18000364b  push    rbx
0x18000364c  push    rbp
0x18000364d  push    rsi
0x18000364e  push    rdi
0x18000364f  push    r12
0x180003651  push    r13
0x180003653  push    r14
0x180003655  push    r15
0x180003657  sub     rsp, 48h
0x18000365b  xor     ebp, ebp
0x18000365d  mov     r14, r9
0x180003660  mov     [rax+20h], ebp
0x180003663  mov     r12d, r8d
0x180003666  mov     r13, rdx
0x180003669  mov     rdi, rcx
0x18000366c  test    r9, r9
0x18000366f  jz      loc_18000379E
0x180003675  mov     rsi, [rsp+88h+arg_20]
0x18000367d  test    rsi, rsi
0x180003680  jz      loc_18000379E
0x180003686  mov     [r9], rbp
0x180003689  mov     [rsi], ebp
0x18000368b  test    rdx, rdx
0x18000368e  jz      loc_18000379E
0x180003694  test    r8d, r8d
0x180003697  jz      loc_18000379E
0x18000369d  lea     rdx, [rax+20h]; enum FileType *
0x1800036a1  call    ?GetFileType@SipFile@@QEAAKPEAW4FileType@@@Z; SipFile::GetFileType(FileType *)
0x1800036a6  mov     ebx, eax
0x1800036a8  test    eax, eax
0x1800036aa  jnz     loc_1800037A3
0x1800036b0  cmp     [rsp+88h+arg_18], 2
0x1800036b8  jnz     short loc_1800036C4
0x1800036ba  mov     [r14], rbp
0x1800036bd  mov     [rsi], ebp
0x1800036bf  jmp     loc_1800037A3
0x1800036c4  lea     rdx, [rsp+88h+arg_18]; enum FileType *
0x1800036cc  mov     [rsp+88h+arg_18], ebp
0x1800036d3  mov     rcx, rdi; this
0x1800036d6  call    ?GetFileType@SipFile@@QEAAKPEAW4FileType@@@Z; SipFile::GetFileType(FileType *)
0x1800036db  mov     ebx, eax
0x1800036dd  test    eax, eax
0x1800036df  jnz     loc_1800037A3
0x1800036e5  mov     ecx, [rsp+88h+arg_18]
0x1800036ec  sub     ecx, 1
0x1800036ef  jz      short loc_180003706
0x1800036f1  cmp     ecx, 3
0x1800036f4  jz      short loc_1800036FE
0x1800036f6  lea     ebx, [rax+0Dh]
0x1800036f9  jmp     loc_1800037A3
0x1800036fe  mov     r15d, 0FDE9h
0x180003704  jmp     short loc_180003709
0x180003706  mov     r15d, ebp
0x180003709  mov     [rsp+88h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18000370e  mov     r9d, r12d; cchWideChar
0x180003711  mov     [rsp+88h+lpDefaultChar], rbp; lpDefaultChar
0x180003716  mov     r8, r13; lpWideCharStr
0x180003719  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x18000371d  xor     edx, edx; dwFlags
0x18000371f  mov     ecx, r15d; CodePage
0x180003722  mov     [rsp+88h+lpMultiByteStr], rbp; lpMultiByteStr
0x180003727  call    cs:__imp_WideCharToMultiByte
0x18000372d  mov     ebp, eax
0x18000372f  test    eax, eax
0x180003731  jnz     short loc_18000373D
0x180003733  call    cs:__imp_GetLastError
0x180003739  mov     ebx, eax
0x18000373b  jmp     short loc_1800037A3
0x18000373d  lea     ecx, [rbp+1]; Size
0x180003740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003745  mov     rdi, rax
0x180003748  test    rax, rax
0x18000374b  jnz     short loc_180003752
0x18000374d  lea     ebx, [rax+8]
0x180003750  jmp     short loc_1800037A3
0x180003752  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000375b  mov     r9d, r12d; cchWideChar
0x18000375e  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x180003767  mov     r8, r13; lpWideCharStr
0x18000376a  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x18000376e  xor     edx, edx; dwFlags
0x180003770  mov     ecx, r15d; CodePage
0x180003773  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x180003778  call    cs:__imp_WideCharToMultiByte
0x18000377e  cmp     ebp, eax
0x180003780  jnz     short loc_18000378F
0x180003782  mov     byte ptr [rbp+rdi+0], 0
0x180003787  mov     [r14], rdi
0x18000378a  jmp     loc_1800036BD
0x18000378f  mov     rcx, rdi; Block
0x180003792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003797  mov     ebx, 7Ah ; 'z'
0x18000379c  jmp     short loc_1800037A3
0x18000379e  mov     ebx, 57h ; 'W'
0x1800037a3  mov     eax, ebx
0x1800037a5  add     rsp, 48h
0x1800037a9  pop     r15
0x1800037ab  pop     r14
0x1800037ad  pop     r13
0x1800037af  pop     r12
0x1800037b1  pop     rdi
0x1800037b2  pop     rsi
0x1800037b3  pop     rbp
0x1800037b4  pop     rbx
0x1800037b5  retn
```
