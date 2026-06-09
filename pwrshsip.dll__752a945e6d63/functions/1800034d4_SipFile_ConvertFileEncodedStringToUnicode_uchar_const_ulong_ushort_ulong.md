# SipFile::ConvertFileEncodedStringToUnicode(uchar const *,ulong,ushort * *,ulong *)

- ea: `0x1800034d4`
- end: `0x180003640`
- name: `?ConvertFileEncodedStringToUnicode@SipFile@@IEAAKPEBEKPEAPEAGPEAK@Z`
- size: `364`
- prototype: `__int64 __fastcall(SipFile *this, LPCCH lpMultiByteStr, int cbMultiByte, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001e40`
- `0x180004650`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800034d4`
- `0x180003fe4`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800035ad`
- `KERNEL32!MultiByteToWideChar` at `0x180003601`
- `KERNEL32!MultiByteToWideChar` at `0x1800035ad`
- `KERNEL32!MultiByteToWideChar` at `0x180003601`
- `KERNEL32!GetLastError` at `0x1800035b9`
- `KERNEL32!GetLastError` at `0x1800035b9`

## pseudocode

```c
__int64 __fastcall SipFile::ConvertFileEncodedStringToUnicode(
        SipFile *this,
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  unsigned int *v9; // rdi
  unsigned int FileType; // ebx
  UINT v11; // ebp
  unsigned int v12; // eax
  __int64 cchWideChar; // rsi
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v15; // r14
  int v17; // [rsp+98h] [rbp+20h] BYREF

  if ( !a4 )
    return 87;
  v9 = a5;
  if ( !a5 )
    return 87;
  *a4 = 0;
  *v9 = 0;
  if ( !lpMultiByteStr || !cbMultiByte )
    return 87;
  v17 = 0;
  FileType = SipFile::GetFileType(this, (enum FileType *)&v17);
  if ( !FileType )
  {
    if ( v17 == 2 )
    {
      *a4 = 0;
      *v9 = 0;
    }
    else
    {
      v17 = 0;
      FileType = SipFile::GetFileType(this, (enum FileType *)&v17);
      if ( !FileType )
      {
        if ( v17 == 1 )
        {
          v11 = 0;
        }
        else
        {
          if ( v17 != 4 )
            return 13;
          v11 = 65001;
        }
        v12 = MultiByteToWideChar(v11, 0, lpMultiByteStr, cbMultiByte, 0, 0);
        cchWideChar = v12;
        if ( v12 )
        {
          lpWideCharStr = (WCHAR *)operator new(saturated_mul(v12 + 1, 2u));
          v15 = lpWideCharStr;
          if ( lpWideCharStr )
          {
            if ( (_DWORD)cchWideChar == MultiByteToWideChar(
                                          v11,
                                          0,
                                          lpMultiByteStr,
                                          cbMultiByte,
                                          lpWideCharStr,
                                          cchWideChar) )
            {
              v15[cchWideChar] = 0;
              *a4 = v15;
              *v9 = cchWideChar;
            }
            else
            {
              operator delete(v15);
              return 122;
            }
          }
          else
          {
            return 8;
          }
        }
        else
        {
          return GetLastError();
        }
      }
    }
  }
  return FileType;
}

```

## disassembly

```asm
0x1800034d4  mov     rax, rsp
0x1800034d7  push    rbx
0x1800034d8  push    rbp
0x1800034d9  push    rsi
0x1800034da  push    rdi
0x1800034db  push    r12
0x1800034dd  push    r13
0x1800034df  push    r14
0x1800034e1  push    r15
0x1800034e3  sub     rsp, 38h
0x1800034e7  xor     r14d, r14d
0x1800034ea  mov     r15, r9
0x1800034ed  mov     r12d, r8d
0x1800034f0  mov     r13, rdx
0x1800034f3  mov     rsi, rcx
0x1800034f6  test    r9, r9
0x1800034f9  jz      loc_180003628
0x1800034ff  mov     rdi, [rsp+78h+arg_20]
0x180003507  test    rdi, rdi
0x18000350a  jz      loc_180003628
0x180003510  mov     [r9], r14
0x180003513  mov     [rdi], r14d
0x180003516  test    rdx, rdx
0x180003519  jz      loc_180003628
0x18000351f  test    r8d, r8d
0x180003522  jz      loc_180003628
0x180003528  lea     rdx, [rax+20h]; enum FileType *
0x18000352c  mov     [rax+20h], r14d
0x180003530  call    ?GetFileType@SipFile@@QEAAKPEAW4FileType@@@Z; SipFile::GetFileType(FileType *)
0x180003535  mov     ebx, eax
0x180003537  test    eax, eax
0x180003539  jnz     loc_18000362D
0x18000353f  cmp     [rsp+78h+arg_18], 2
0x180003547  jnz     short loc_180003554
0x180003549  mov     [r15], r14
0x18000354c  mov     [rdi], r14d
0x18000354f  jmp     loc_18000362D
0x180003554  lea     rdx, [rsp+78h+arg_18]; enum FileType *
0x18000355c  mov     [rsp+78h+arg_18], r14d
0x180003564  mov     rcx, rsi; this
0x180003567  call    ?GetFileType@SipFile@@QEAAKPEAW4FileType@@@Z; SipFile::GetFileType(FileType *)
0x18000356c  mov     ebx, eax
0x18000356e  test    eax, eax
0x180003570  jnz     loc_18000362D
0x180003576  mov     ecx, [rsp+78h+arg_18]
0x18000357d  sub     ecx, 1
0x180003580  jz      short loc_180003596
0x180003582  cmp     ecx, 3
0x180003585  jz      short loc_18000358F
0x180003587  lea     ebx, [rax+0Dh]
0x18000358a  jmp     loc_18000362D
0x18000358f  mov     ebp, 0FDE9h
0x180003594  jmp     short loc_180003599
0x180003596  mov     ebp, r14d
0x180003599  mov     [rsp+78h+cchWideChar], r14d; cchWideChar
0x18000359e  mov     r9d, r12d; cbMultiByte
0x1800035a1  mov     r8, r13; lpMultiByteStr
0x1800035a4  mov     [rsp+78h+lpWideCharStr], r14; lpWideCharStr
0x1800035a9  xor     edx, edx; dwFlags
0x1800035ab  mov     ecx, ebp; CodePage
0x1800035ad  call    cs:__imp_MultiByteToWideChar
0x1800035b3  mov     esi, eax
0x1800035b5  test    eax, eax
0x1800035b7  jnz     short loc_1800035C3
0x1800035b9  call    cs:__imp_GetLastError
0x1800035bf  mov     ebx, eax
0x1800035c1  jmp     short loc_18000362D
0x1800035c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800035ca  lea     edx, [rsi+1]
0x1800035cd  mov     eax, 2
0x1800035d2  mul     rdx
0x1800035d5  cmovb   rax, rcx
0x1800035d9  mov     rcx, rax; Size
0x1800035dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035e1  mov     r14, rax
0x1800035e4  test    rax, rax
0x1800035e7  jnz     short loc_1800035EE
0x1800035e9  lea     ebx, [rax+8]
0x1800035ec  jmp     short loc_18000362D
0x1800035ee  mov     [rsp+78h+cchWideChar], esi; cchWideChar
0x1800035f2  mov     r9d, r12d; cbMultiByte
0x1800035f5  mov     r8, r13; lpMultiByteStr
0x1800035f8  mov     [rsp+78h+lpWideCharStr], r14; lpWideCharStr
0x1800035fd  xor     edx, edx; dwFlags
0x1800035ff  mov     ecx, ebp; CodePage
0x180003601  call    cs:__imp_MultiByteToWideChar
0x180003607  cmp     esi, eax
0x180003609  jnz     short loc_180003619
0x18000360b  xor     eax, eax
0x18000360d  mov     [r14+rsi*2], ax
0x180003612  mov     [r15], r14
0x180003615  mov     [rdi], esi
0x180003617  jmp     short loc_18000362D
0x180003619  mov     rcx, r14; Block
0x18000361c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003621  mov     ebx, 7Ah ; 'z'
0x180003626  jmp     short loc_18000362D
0x180003628  mov     ebx, 57h ; 'W'
0x18000362d  mov     eax, ebx
0x18000362f  add     rsp, 38h
0x180003633  pop     r15
0x180003635  pop     r14
0x180003637  pop     r13
0x180003639  pop     r12
0x18000363b  pop     rdi
0x18000363c  pop     rsi
0x18000363d  pop     rbp
0x18000363e  pop     rbx
0x18000363f  retn
```
