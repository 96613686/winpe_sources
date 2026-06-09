# CExCollection::GetLocalStoragePathname(char const *)

- ea: `0x180060980`
- end: `0x180060bed`
- name: `?GetLocalStoragePathname@CExCollection@@QEAAPEBDPEBD@Z`
- size: `621`
- prototype: `const char *__fastcall(CExCollection *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005c430`
- `0x180074580`

## callees

- `0x1800029b8`
- `0x1800095c8`
- `0x18004e6a8`
- `0x18004e73c`
- `0x18004f794`
- `0x180060980`
- `0x180063804`
- `0x180067c20`
- `0x180075c66`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180060b78`
- `KERNEL32!CloseHandle` at `0x180060b78`
- `KERNEL32!CreateFileA` at `0x180060b34`
- `KERNEL32!CreateFileA` at `0x180060b34`
- `KERNEL32!GetDriveTypeA` at `0x180060a5c`
- `KERNEL32!GetDriveTypeA` at `0x180060a5c`
- `KERNEL32!DeleteFileA` at `0x180060b81`
- `KERNEL32!DeleteFileA` at `0x180060b81`
- `KERNEL32!GetFullPathNameA` at `0x180060a31`
- `KERNEL32!GetFullPathNameA` at `0x180060a31`

## pseudocode

```c
BYTE *__fastcall CExCollection::GetLocalStoragePathname(CExCollection *this, const char *a2)
{
  BYTE *result; // rax
  const char *v5; // r8
  UINT DriveTypeA; // eax
  const char *FilePortion; // rax
  __int64 v8; // rdx
  _BYTE *v9; // rax
  HANDLE v10; // rax
  const char *v11; // rax
  _BYTE *v12; // rax
  const char *v13; // rdx
  CHAR RootPathName; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+41h] [rbp-BFh]
  __int16 v16; // [rsp+42h] [rbp-BEh]
  LPSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  char v19[272]; // [rsp+70h] [rbp-90h] BYREF

  if ( !a2 && MEMORY[0] )
    return 0;
  if ( strcmp_0(a2, ".chw") || (result = (BYTE *)*((_QWORD *)this + 138)) == 0 )
  {
    if ( *((_DWORD *)this + 274) )
      v5 = *(const char **)(*((_QWORD *)this + 1) + 136LL);
    else
      v5 = (const char *)*((_QWORD *)this + 9);
    StringCchCopyA((char *)&Buffer, 0x104u, v5);
    FilePart = 0;
    GetFullPathNameA((LPCSTR)&Buffer, 0x104u, (LPSTR)&Buffer, &FilePart);
    StringCchCopyA(&RootPathName, 4u, (const char *)&Buffer);
    if ( v15 == 58 )
    {
      v16 = 92;
      DriveTypeA = GetDriveTypeA(&RootPathName);
      if ( ((DriveTypeA - 3) & 0xFFFFFFFC) == 0 && DriveTypeA != 5 )
        goto LABEL_16;
    }
    else if ( RootPathName == 92 && v15 == 92 )
    {
      goto LABEL_16;
    }
    FilePortion = FindFilePortion((const char *)&Buffer);
    StringCchCopyA(v19, 0x104u, FilePortion);
    HHGetUserDataPath(&Buffer, 0x104u);
    CatPath((char *)&Buffer, v19, 0x104u);
LABEL_16:
    if ( !strcmp_0(a2, ".chw") )
    {
      LOBYTE(v8) = 46;
      v9 = (_BYTE *)StrRChr(&Buffer, v8);
      if ( v9 )
        *v9 = 0;
      StringCchCatA((char *)&Buffer, 0x104u, ".foo");
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = 0;
      v10 = CreateFileA((LPCSTR)&Buffer, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
      if ( v10 == (HANDLE)-1LL )
      {
        v11 = FindFilePortion((const char *)&Buffer);
        StringCchCopyA(v19, 0x104u, v11);
        HHGetUserDataPath(&Buffer, 0x104u);
        CatPath((char *)&Buffer, v19, 0x104u);
      }
      else
      {
        CloseHandle(v10);
        DeleteFileA((LPCSTR)&Buffer);
      }
    }
    LOBYTE(v8) = 46;
    v12 = (_BYTE *)StrRChr(&Buffer, v8);
    if ( v12 )
      *v12 = 0;
    StringCchCatA((char *)&Buffer, 0x104u, a2);
    if ( !strcmp_0(a2, ".chw") )
      CExCollection::SetWordWheelPathname(this, v13);
    return &Buffer;
  }
  return result;
}

```

## disassembly

```asm
0x180060980  mov     [rsp-8+arg_10], rbx
0x180060985  mov     [rsp-8+arg_18], rdi
0x18006098a  push    rbp
0x18006098b  push    r14
0x18006098d  push    r15
0x18006098f  lea     rbp, [rsp-90h]
0x180060997  sub     rsp, 190h
0x18006099e  mov     rax, cs:__security_cookie
0x1800609a5  xor     rax, rsp
0x1800609a8  mov     [rbp+0A0h+var_20], rax
0x1800609af  mov     rdi, rdx
0x1800609b2  mov     rbx, rcx
0x1800609b5  test    rdx, rdx
0x1800609b8  jnz     short loc_1800609C5
0x1800609ba  cmp     [rdx], dl
0x1800609bc  jz      short loc_1800609C5
0x1800609be  xor     eax, eax
0x1800609c0  jmp     loc_180060BC5
0x1800609c5  lea     rdx, aChw; ".chw"
0x1800609cc  mov     rcx, rdi; Str1
0x1800609cf  call    strcmp_0
0x1800609d4  test    eax, eax
0x1800609d6  jnz     short loc_1800609E8
0x1800609d8  mov     rax, [rbx+450h]
0x1800609df  test    rax, rax
0x1800609e2  jnz     loc_180060BC5
0x1800609e8  cmp     dword ptr [rbx+448h], 0
0x1800609ef  jnz     short loc_1800609F7
0x1800609f1  mov     r8, [rbx+48h]
0x1800609f5  jmp     short loc_180060A02
0x1800609f7  mov     rax, [rbx+8]
0x1800609fb  mov     r8, [rax+88h]; char *
0x180060a02  mov     r15d, 104h
0x180060a08  lea     r14, Buffer
0x180060a0f  mov     edx, r15d; unsigned __int64
0x180060a12  mov     rcx, r14; char *
0x180060a15  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180060a1a  lea     r9, [rsp+1A0h+FilePart]; lpFilePart
0x180060a1f  mov     [rsp+1A0h+FilePart], 0
0x180060a28  mov     r8, r14; lpBuffer
0x180060a2b  mov     edx, r15d; nBufferLength
0x180060a2e  mov     rcx, r14; lpFileName
0x180060a31  call    cs:__imp_GetFullPathNameA
0x180060a37  mov     r8, r14; char *
0x180060a3a  lea     rcx, [rsp+1A0h+RootPathName]; char *
0x180060a3f  mov     edx, 4; unsigned __int64
0x180060a44  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180060a49  cmp     [rsp+1A0h+var_15F], 3Ah ; ':'
0x180060a4e  jnz     short loc_180060A74
0x180060a50  lea     rcx, [rsp+1A0h+RootPathName]; lpRootPathName
0x180060a55  mov     [rsp+1A0h+var_15E], 5Ch ; '\'
0x180060a5c  call    cs:__imp_GetDriveTypeA
0x180060a62  lea     ecx, [rax-3]
0x180060a65  test    ecx, 0FFFFFFFCh
0x180060a6b  jnz     short loc_180060A82
0x180060a6d  cmp     eax, 5
0x180060a70  jnz     short loc_180060AB5
0x180060a72  jmp     short loc_180060A82
0x180060a74  cmp     [rsp+1A0h+RootPathName], 5Ch ; '\'
0x180060a79  jnz     short loc_180060A82
0x180060a7b  cmp     [rsp+1A0h+var_15F], 5Ch ; '\'
0x180060a80  jz      short loc_180060AB5
0x180060a82  mov     rcx, r14; char *
0x180060a85  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x180060a8a  mov     r8, rax; char *
0x180060a8d  lea     rcx, [rsp+1A0h+var_130]; char *
0x180060a92  mov     rdx, r15; unsigned __int64
0x180060a95  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180060a9a  mov     rdx, r15; unsigned __int64
0x180060a9d  mov     rcx, r14; lpData
0x180060aa0  call    ?HHGetUserDataPath@@YAHPEAD_K@Z; HHGetUserDataPath(char *,unsigned __int64)
0x180060aa5  mov     r8, r15; unsigned __int64
0x180060aa8  lea     rdx, [rsp+1A0h+var_130]; char *
0x180060aad  mov     rcx, r14; char *
0x180060ab0  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180060ab5  lea     rdx, aChw; ".chw"
0x180060abc  mov     rcx, rdi; Str1
0x180060abf  call    strcmp_0
0x180060ac4  test    eax, eax
0x180060ac6  jnz     loc_180060B87
0x180060acc  mov     dl, 2Eh ; '.'
0x180060ace  mov     rcx, r14
0x180060ad1  call    StrRChr
0x180060ad6  test    rax, rax
0x180060ad9  jz      short loc_180060ADE
0x180060adb  mov     byte ptr [rax], 0
0x180060ade  lea     r8, aFoo; ".foo"
0x180060ae5  mov     rdx, r15; unsigned __int64
0x180060ae8  mov     rcx, r14; char *
0x180060aeb  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180060af0  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x180060af9  lea     r9, [rsp+1A0h+SecurityAttributes]; lpSecurityAttributes
0x180060afe  mov     [rsp+1A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180060b06  xor     r8d, r8d; dwShareMode
0x180060b09  mov     edx, 40000000h; dwDesiredAccess
0x180060b0e  mov     [rsp+1A0h+dwCreationDisposition], 2; dwCreationDisposition
0x180060b16  mov     rcx, r14; lpFileName
0x180060b19  mov     qword ptr [rsp+1A0h+SecurityAttributes.nLength], 18h
0x180060b22  mov     qword ptr [rsp+1A0h+SecurityAttributes.bInheritHandle], 0
0x180060b2b  mov     [rsp+1A0h+SecurityAttributes.lpSecurityDescriptor], 0
0x180060b34  call    cs:__imp_CreateFileA
0x180060b3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060b3e  jnz     short loc_180060B75
0x180060b40  mov     rcx, r14; char *
0x180060b43  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x180060b48  mov     r8, rax; char *
0x180060b4b  lea     rcx, [rsp+1A0h+var_130]; char *
0x180060b50  mov     rdx, r15; unsigned __int64
0x180060b53  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180060b58  mov     rdx, r15; unsigned __int64
0x180060b5b  mov     rcx, r14; lpData
0x180060b5e  call    ?HHGetUserDataPath@@YAHPEAD_K@Z; HHGetUserDataPath(char *,unsigned __int64)
0x180060b63  mov     r8, r15; unsigned __int64
0x180060b66  lea     rdx, [rsp+1A0h+var_130]; char *
0x180060b6b  mov     rcx, r14; char *
0x180060b6e  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180060b73  jmp     short loc_180060B87
0x180060b75  mov     rcx, rax; hObject
0x180060b78  call    cs:__imp_CloseHandle
0x180060b7e  mov     rcx, r14; lpFileName
0x180060b81  call    cs:__imp_DeleteFileA
0x180060b87  mov     dl, 2Eh ; '.'
0x180060b89  mov     rcx, r14
0x180060b8c  call    StrRChr
0x180060b91  test    rax, rax
0x180060b94  jz      short loc_180060B99
0x180060b96  mov     byte ptr [rax], 0
0x180060b99  mov     r8, rdi; char *
0x180060b9c  mov     rdx, r15; unsigned __int64
0x180060b9f  mov     rcx, r14; char *
0x180060ba2  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180060ba7  lea     rdx, aChw; ".chw"
0x180060bae  mov     rcx, rdi; Str1
0x180060bb1  call    strcmp_0
0x180060bb6  test    eax, eax
0x180060bb8  jnz     short loc_180060BC2
0x180060bba  mov     rcx, rbx; this
0x180060bbd  call    ?SetWordWheelPathname@CExCollection@@AEAAPEBDPEBD@Z; CExCollection::SetWordWheelPathname(char const *)
0x180060bc2  mov     rax, r14
0x180060bc5  mov     rcx, [rbp+0A0h+var_20]
0x180060bcc  xor     rcx, rsp; StackCookie
0x180060bcf  call    __security_check_cookie
0x180060bd4  lea     r11, [rsp+1A0h+var_10]
0x180060bdc  mov     rbx, [r11+30h]
0x180060be0  mov     rdi, [r11+38h]
0x180060be4  mov     rsp, r11
0x180060be7  pop     r15
0x180060be9  pop     r14
0x180060beb  pop     rbp
0x180060bec  retn
```
