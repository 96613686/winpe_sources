# GetVersionInformation(VERSION_INFO_TYPE,ushort const *,ushort *,ulong)

- ea: `0x1800189a0`
- end: `0x180018cbe`
- name: `?GetVersionInformation@@YAHW4VERSION_INFO_TYPE@@PEBGPEAGK@Z`
- size: `798`
- prototype: `int __high(enum VERSION_INFO_TYPE, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018cc4`

## callees

- `0x180007ae0`
- `0x180007b54`
- `0x1800189a0`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180018acf`
- `KERNEL32!HeapAlloc` at `0x180018acf`
- `KERNEL32!GetProcessHeap` at `0x180018abe`
- `KERNEL32!GetProcessHeap` at `0x180018c79`
- `KERNEL32!GetProcessHeap` at `0x180018abe`
- `KERNEL32!GetProcessHeap` at `0x180018c79`
- `KERNEL32!HeapFree` at `0x180018c87`
- `KERNEL32!HeapFree` at `0x180018c87`
- `SHLWAPI!PathFileExistsW` at `0x1800189fa`
- `SHLWAPI!PathFileExistsW` at `0x1800189fa`
- `VERSION!GetFileVersionInfoW` at `0x180018af5`
- `VERSION!GetFileVersionInfoW` at `0x180018af5`
- `VERSION!VerQueryValueW` at `0x180018b25`
- `VERSION!VerQueryValueW` at `0x180018b84`
- `VERSION!VerQueryValueW` at `0x180018be1`
- `VERSION!VerQueryValueW` at `0x180018c1a`
- `VERSION!VerQueryValueW` at `0x180018c53`
- `VERSION!VerQueryValueW` at `0x180018b25`
- `VERSION!VerQueryValueW` at `0x180018b84`
- `VERSION!VerQueryValueW` at `0x180018be1`
- `VERSION!VerQueryValueW` at `0x180018c1a`
- `VERSION!VerQueryValueW` at `0x180018c53`
- `VERSION!GetFileVersionInfoSizeW` at `0x180018aa7`
- `VERSION!GetFileVersionInfoSizeW` at `0x180018aa7`

## string_xrefs

- `0x180018a39`: `CompanyName`

## pseudocode

```c
BOOL __fastcall GetVersionInformation(int a1, const WCHAR *a2, unsigned __int16 *a3, unsigned int a4)
{
  unsigned __int64 v4; // r13
  const WCHAR *v7; // rdi
  BOOL result; // eax
  char v9; // r15
  int v10; // ebx
  int v11; // ebx
  signed int v12; // ebx
  const wchar_t *v13; // rsi
  __int64 v14; // rax
  WCHAR *v15; // r8
  __int64 v16; // rdx
  WCHAR *v17; // rcx
  DWORD FileVersionInfoSizeW; // eax
  SIZE_T v19; // r14
  HANDLE ProcessHeap; // rax
  void *v21; // rax
  void *v22; // rdi
  HANDLE v23; // rax
  unsigned int puLen; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwHandle; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v28; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubBlock[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR tstrFilename[264]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = a4;
  puLen = 0;
  dwHandle = 0;
  v26 = 0;
  lpBuffer = 0;
  v7 = a2;
  v28 = 0;
  result = PathFileExistsW(a2);
  if ( result )
  {
    v9 = 0;
    if ( a1 )
    {
      v10 = a1 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
          {
            v12 = -2147024809;
            return v12 >= 0;
          }
          v13 = 0;
          v9 = 1;
        }
        else
        {
          v13 = L"ProductName";
        }
      }
      else
      {
        v13 = L"CompanyName";
      }
    }
    else
    {
      v13 = L"FileDescription";
    }
    v14 = 2147483646;
    v15 = tstrFilename;
    v16 = 260;
    do
    {
      if ( !v14 )
        break;
      if ( !*v7 )
        break;
      *v15++ = *v7++;
      --v14;
      --v16;
    }
    while ( v16 );
    v17 = v15 - 1;
    v12 = v16 == 0 ? 0x8007007A : 0;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
    if ( !v16 )
      return v12 >= 0;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(tstrFilename, &dwHandle);
    v19 = FileVersionInfoSizeW;
    if ( !FileVersionInfoSizeW )
    {
      v12 = -2147467259;
      return v12 >= 0;
    }
    ProcessHeap = GetProcessHeap();
    v21 = HeapAlloc(ProcessHeap, 8u, v19);
    v22 = v21;
    if ( !v21 )
    {
      v12 = -2147024882;
      return v12 >= 0;
    }
    if ( !GetFileVersionInfoW(tstrFilename, dwHandle, v19, v21) )
    {
      v12 = -2147467259;
LABEL_39:
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
      return v12 >= 0;
    }
    if ( v9 )
    {
      if ( VerQueryValueW(v22, L"\\", &lpBuffer, &puLen) )
      {
        v12 = StringCchPrintfW(
                a3,
                v4,
                L"%d.%d.%d.%d",
                *((unsigned __int16 *)lpBuffer + 5),
                *((unsigned __int16 *)lpBuffer + 4),
                *((unsigned __int16 *)lpBuffer + 7),
                *((unsigned __int16 *)lpBuffer + 6));
        if ( v12 < 0 )
          goto LABEL_39;
      }
    }
    else
    {
      if ( !VerQueryValueW(v22, L"\\VarFileInfo\\Translation", &v28, &puLen) || !puLen )
        goto LABEL_32;
      v12 = StringCchPrintfW(
              SubBlock,
              0x3Cu,
              L"\\StringFileInfo\\%04X%04X\\%s",
              *(unsigned __int16 *)v28,
              *((unsigned __int16 *)v28 + 1),
              v13);
      if ( v12 < 0 )
        goto LABEL_39;
      if ( !VerQueryValueW(v22, SubBlock, (LPVOID *)&v26, &puLen) )
      {
LABEL_32:
        v12 = StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\040904E4\\%s", v13);
        if ( v12 < 0 )
          goto LABEL_39;
        if ( !VerQueryValueW(v22, SubBlock, (LPVOID *)&v26, &puLen) )
        {
          v12 = StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\04090000\\%s", v13);
          if ( v12 < 0 )
            goto LABEL_39;
          VerQueryValueW(v22, SubBlock, (LPVOID *)&v26, &puLen);
        }
      }
    }
    v12 = 0;
    if ( v26 )
    {
      if ( *v26 )
        v12 = StringCchCopyW(a3, v4, v26);
    }
    goto LABEL_39;
  }
  return result;
}

```

## disassembly

```asm
0x1800189a0  mov     [rsp-8+arg_0], rbx
0x1800189a5  push    rbp
0x1800189a6  push    rsi
0x1800189a7  push    rdi
0x1800189a8  push    r12
0x1800189aa  push    r13
0x1800189ac  push    r14
0x1800189ae  push    r15
0x1800189b0  lea     rbp, [rsp-200h]
0x1800189b8  sub     rsp, 300h
0x1800189bf  mov     rax, cs:__security_cookie
0x1800189c6  xor     rax, rsp
0x1800189c9  mov     [rbp+230h+var_40], rax
0x1800189d0  xor     r14d, r14d
0x1800189d3  mov     r13d, r9d
0x1800189d6  mov     ebx, ecx
0x1800189d8  mov     [rsp+330h+puLen], r14d
0x1800189dd  mov     rcx, rdx; pszPath
0x1800189e0  mov     [rsp+330h+dwHandle], r14d
0x1800189e5  mov     [rsp+330h+var_2E8], r14
0x1800189ea  mov     r12, r8
0x1800189ed  mov     [rsp+330h+lpBuffer], r14
0x1800189f2  mov     rdi, rdx
0x1800189f5  mov     [rsp+330h+var_2D8], r14
0x1800189fa  call    cs:__imp_PathFileExistsW
0x180018a00  test    eax, eax
0x180018a02  jz      loc_180018C94
0x180018a08  mov     r15b, r14b
0x180018a0b  test    ebx, ebx
0x180018a0d  jz      short loc_180018A42
0x180018a0f  sub     ebx, 1
0x180018a12  jz      short loc_180018A39
0x180018a14  sub     ebx, 1
0x180018a17  jz      short loc_180018A30
0x180018a19  cmp     ebx, 1
0x180018a1c  jz      short loc_180018A28
0x180018a1e  mov     ebx, 80070057h
0x180018a23  jmp     loc_180018C8D
0x180018a28  mov     rsi, r14
0x180018a2b  mov     r15b, 1
0x180018a2e  jmp     short loc_180018A49
0x180018a30  lea     rsi, aProductname; "ProductName"
0x180018a37  jmp     short loc_180018A49
0x180018a39  lea     rsi, aCompanyname; "CompanyName"
0x180018a40  jmp     short loc_180018A49
0x180018a42  lea     rsi, aFiledescriptio; "FileDescription"
0x180018a49  mov     eax, 7FFFFFFEh
0x180018a4e  lea     r8, [rbp+230h+tstrFilename]
0x180018a52  mov     edx, 104h
0x180018a57  test    rax, rax
0x180018a5a  jz      short loc_180018A79
0x180018a5c  movzx   ecx, word ptr [rdi]
0x180018a5f  test    cx, cx
0x180018a62  jz      short loc_180018A79
0x180018a64  mov     [r8], cx
0x180018a68  add     rdi, 2
0x180018a6c  add     r8, 2
0x180018a70  dec     rax
0x180018a73  sub     rdx, 1
0x180018a77  jnz     short loc_180018A57
0x180018a79  mov     rax, rdx
0x180018a7c  lea     rcx, [r8-2]
0x180018a80  neg     rax
0x180018a83  sbb     ebx, ebx
0x180018a85  not     ebx
0x180018a87  and     ebx, 8007007Ah
0x180018a8d  test    rdx, rdx
0x180018a90  cmovnz  rcx, r8
0x180018a94  mov     [rcx], r14w
0x180018a98  jz      loc_180018C8D
0x180018a9e  lea     rdx, [rsp+330h+dwHandle]; lpdwHandle
0x180018aa3  lea     rcx, [rbp+230h+tstrFilename]; lptstrFilename
0x180018aa7  call    cs:__imp_GetFileVersionInfoSizeW
0x180018aad  mov     r14d, eax
0x180018ab0  test    eax, eax
0x180018ab2  jnz     short loc_180018ABE
0x180018ab4  mov     ebx, 80004005h
0x180018ab9  jmp     loc_180018C8D
0x180018abe  call    cs:__imp_GetProcessHeap
0x180018ac4  mov     r8, r14; dwBytes
0x180018ac7  mov     edx, 8; dwFlags
0x180018acc  mov     rcx, rax; hHeap
0x180018acf  call    cs:__imp_HeapAlloc
0x180018ad5  mov     rdi, rax
0x180018ad8  test    rax, rax
0x180018adb  jnz     short loc_180018AE7
0x180018add  mov     ebx, 8007000Eh
0x180018ae2  jmp     loc_180018C8D
0x180018ae7  mov     edx, [rsp+330h+dwHandle]; dwHandle
0x180018aeb  lea     rcx, [rbp+230h+tstrFilename]; lptstrFilename
0x180018aef  mov     r9, rdi; lpData
0x180018af2  mov     r8d, r14d; dwLen
0x180018af5  call    cs:__imp_GetFileVersionInfoW
0x180018afb  xor     r14d, r14d
0x180018afe  test    eax, eax
0x180018b00  jnz     short loc_180018B0C
0x180018b02  mov     ebx, 80004005h
0x180018b07  jmp     loc_180018C79
0x180018b0c  lea     r9, [rsp+330h+puLen]; puLen
0x180018b11  mov     rcx, rdi; pBlock
0x180018b14  test    r15b, r15b
0x180018b17  jz      short loc_180018B78
0x180018b19  lea     r8, [rsp+330h+lpBuffer]; lplpBuffer
0x180018b1e  lea     rdx, asc_18001D1B4; "\\"
0x180018b25  call    cs:__imp_VerQueryValueW
0x180018b2b  test    eax, eax
0x180018b2d  jz      loc_180018C59
0x180018b33  mov     rdx, [rsp+330h+lpBuffer]
0x180018b38  movzx   ecx, word ptr [rdx+0Eh]
0x180018b3c  movzx   r8d, word ptr [rdx+8]
0x180018b41  movzx   eax, word ptr [rdx+0Ch]
0x180018b45  movzx   r9d, word ptr [rdx+0Ah]
0x180018b4a  mov     rdx, r13; unsigned __int64
0x180018b4d  mov     [rsp+330h+var_300], eax
0x180018b51  mov     dword ptr [rsp+330h+var_308], ecx
0x180018b55  mov     rcx, r12; unsigned __int16 *
0x180018b58  mov     [rsp+330h+var_310], r8d
0x180018b5d  lea     r8, aDDDD; "%d.%d.%d.%d"
0x180018b64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018b69  mov     ebx, eax
0x180018b6b  test    eax, eax
0x180018b6d  js      loc_180018C79
0x180018b73  jmp     loc_180018C59
0x180018b78  lea     r8, [rsp+330h+var_2D8]; lplpBuffer
0x180018b7d  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180018b84  call    cs:__imp_VerQueryValueW
0x180018b8a  mov     r15d, 3Ch ; '<'
0x180018b90  test    eax, eax
0x180018b92  jz      short loc_180018BEB
0x180018b94  cmp     [rsp+330h+puLen], r14d
0x180018b99  jbe     short loc_180018BEB
0x180018b9b  mov     rax, [rsp+330h+var_2D8]
0x180018ba0  lea     r8, aStringfileinfo_2; "\\StringFileInfo\\%04X%04X\\%s"
0x180018ba7  mov     [rsp+330h+var_308], rsi
0x180018bac  mov     edx, r15d; unsigned __int64
0x180018baf  movzx   ecx, word ptr [rax+2]
0x180018bb3  movzx   r9d, word ptr [rax]
0x180018bb7  mov     [rsp+330h+var_310], ecx
0x180018bbb  lea     rcx, [rsp+330h+SubBlock]; unsigned __int16 *
0x180018bc0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018bc5  mov     ebx, eax
0x180018bc7  test    eax, eax
0x180018bc9  js      loc_180018C79
0x180018bcf  lea     r9, [rsp+330h+puLen]; puLen
0x180018bd4  mov     rcx, rdi; pBlock
0x180018bd7  lea     r8, [rsp+330h+var_2E8]; lplpBuffer
0x180018bdc  lea     rdx, [rsp+330h+SubBlock]; lpSubBlock
0x180018be1  call    cs:__imp_VerQueryValueW
0x180018be7  test    eax, eax
0x180018be9  jnz     short loc_180018C59
0x180018beb  mov     r9, rsi
0x180018bee  lea     r8, aStringfileinfo_9; "\\StringFileInfo\\040904E4\\%s"
0x180018bf5  mov     rdx, r15; unsigned __int64
0x180018bf8  lea     rcx, [rsp+330h+SubBlock]; unsigned __int16 *
0x180018bfd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018c02  mov     ebx, eax
0x180018c04  test    eax, eax
0x180018c06  js      short loc_180018C79
0x180018c08  lea     r9, [rsp+330h+puLen]; puLen
0x180018c0d  mov     rcx, rdi; pBlock
0x180018c10  lea     r8, [rsp+330h+var_2E8]; lplpBuffer
0x180018c15  lea     rdx, [rsp+330h+SubBlock]; lpSubBlock
0x180018c1a  call    cs:__imp_VerQueryValueW
0x180018c20  test    eax, eax
0x180018c22  jnz     short loc_180018C59
0x180018c24  mov     r9, rsi
0x180018c27  lea     r8, aStringfileinfo_1; "\\StringFileInfo\\04090000\\%s"
0x180018c2e  mov     rdx, r15; unsigned __int64
0x180018c31  lea     rcx, [rsp+330h+SubBlock]; unsigned __int16 *
0x180018c36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018c3b  mov     ebx, eax
0x180018c3d  test    eax, eax
0x180018c3f  js      short loc_180018C79
0x180018c41  lea     r9, [rsp+330h+puLen]; puLen
0x180018c46  mov     rcx, rdi; pBlock
0x180018c49  lea     r8, [rsp+330h+var_2E8]; lplpBuffer
0x180018c4e  lea     rdx, [rsp+330h+SubBlock]; lpSubBlock
0x180018c53  call    cs:__imp_VerQueryValueW
0x180018c59  mov     r8, [rsp+330h+var_2E8]; unsigned __int16 *
0x180018c5e  mov     ebx, r14d
0x180018c61  test    r8, r8
0x180018c64  jz      short loc_180018C79
0x180018c66  cmp     r14w, [r8]
0x180018c6a  jz      short loc_180018C79
0x180018c6c  mov     rdx, r13; unsigned __int64
0x180018c6f  mov     rcx, r12; unsigned __int16 *
0x180018c72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018c77  mov     ebx, eax
0x180018c79  call    cs:__imp_GetProcessHeap
0x180018c7f  mov     r8, rdi; lpMem
0x180018c82  xor     edx, edx; dwFlags
0x180018c84  mov     rcx, rax; hHeap
0x180018c87  call    cs:__imp_HeapFree
0x180018c8d  not     ebx
0x180018c8f  shr     ebx, 1Fh
0x180018c92  mov     eax, ebx
0x180018c94  mov     rcx, [rbp+230h+var_40]
0x180018c9b  xor     rcx, rsp; StackCookie
0x180018c9e  call    __security_check_cookie
0x180018ca3  mov     rbx, [rsp+330h+arg_0]
0x180018cab  add     rsp, 300h
0x180018cb2  pop     r15
0x180018cb4  pop     r14
0x180018cb6  pop     r13
0x180018cb8  pop     r12
0x180018cba  pop     rdi
0x180018cbb  pop     rsi
0x180018cbc  pop     rbp
0x180018cbd  retn
```
