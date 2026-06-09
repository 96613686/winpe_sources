# File::ReallyOpen(ushort *,Err &)

- ea: `0x1002ebe0`
- end: `0x1002ed7e`
- name: `?ReallyOpen@File@@AAEXPAGAAVErr@@@Z`
- size: `414`
- prototype: `void __thiscall(File *__hidden this, LPCWSTR lpFileName, struct Err *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1001fe30`
- `0x1002e140`
- `0x1002e370`

## callees

- `0x10025ee0`
- `0x1002ebe0`
- `0x1002ed90`
- `0x1004eda0`
- `0x1005d6b4`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002ecf2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1002ecf2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1002ec88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1002ec88`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1002ed44`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1002ed44`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1002ecc7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1002ecc7`

## pseudocode

```c
void __thiscall File::ReallyOpen(File *this, LPCWSTR lpFileName, struct Err *a3)
{
  int v3; // eax
  DWORD v4; // edi
  DWORD v5; // ebx
  DWORD v6; // esi
  bool v7; // zf
  DWORD v8; // eax
  struct Err *v9; // ecx
  HANDLE FileW; // esi
  HANDLE FileA; // eax
  int v12; // ecx
  DWORD dwFlagsAndAttributes; // [esp+10h] [ebp-258h]
  int v15; // [esp+1Ch] [ebp-24Ch] BYREF
  LPCSTR v16; // [esp+20h] [ebp-248h]
  char v17; // [esp+24h] [ebp-244h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [esp+230h] [ebp-38h] BYREF

  v3 = *((_DWORD *)this + 4);
  v4 = (((v3 & 1) == 0) | 0xFFFFFFFE) << 30;
  if ( (v3 & 8) != 0 )
  {
    v5 = 4;
  }
  else if ( (v3 & 0x10) != 0 )
  {
    v5 = ((v3 & 0x20) != 0) + 1;
  }
  else
  {
    v5 = 3;
  }
  if ( (v3 & 2) != 0 || (v3 & 4) != 0 )
    v6 = (v3 & 4) != 0;
  else
    v6 = 3;
  v7 = (v3 & 0x40) == 0;
  v8 = 336658816;
  if ( v7 )
    v8 = 269549696;
  dwFlagsAndAttributes = v8;
  if ( wrap )
  {
    FileW = CreateFileW(lpFileName, v4, v6, 0, v5, v8, 0);
  }
  else
  {
    v15 = 0;
    v16 = 0;
    CStrIn::Init((CStrIn *)&v15, lpFileName, -1);
    FileA = CreateFileA(v16, v4, v6, 0, v5, dwFlagsAndAttributes, 0);
    v9 = (struct Err *)v16;
    FileW = FileA;
    if ( v16 != &v17 && (unsigned int)v16 >> 16 && v15 != -1 )
      _free((void *)v16);
  }
  *(_DWORD *)this = FileW;
  if ( FileW == (HANDLE)-1 )
  {
    System::ErrGetLastError(v9);
    File::SetExtErrInfo(this, a3, lpFileName);
  }
  else
  {
    *((_DWORD *)this + 1) = lpFileName;
    if ( GetFileInformationByHandle(FileW, &FileInformation)
      && (FileInformation.dwFileAttributes & 1) != 0
      && (*((_BYTE *)this + 16) & 1) == 0 )
    {
      Err::SetError(a3, -1032, v12);
    }
  }
}

```

## disassembly

```asm
0x1002ebe0  mov     edi, edi
0x1002ebe2  push    ebp
0x1002ebe3  mov     ebp, esp
0x1002ebe5  sub     esp, 25Ch
0x1002ebeb  mov     eax, ___security_cookie
0x1002ebf0  xor     eax, ebp
0x1002ebf2  mov     [ebp+var_4], eax
0x1002ebf5  mov     eax, [ebp+arg_4]
0x1002ebf8  mov     edx, [ebp+lpFileName]
0x1002ebfb  push    ebx
0x1002ebfc  push    esi
0x1002ebfd  push    edi
0x1002ebfe  mov     [ebp+var_254], eax
0x1002ec04  mov     eax, [ecx+10h]
0x1002ec07  mov     edi, eax
0x1002ec09  not     edi
0x1002ec0b  mov     [ebp+var_25C], ecx
0x1002ec11  and     edi, 1
0x1002ec14  mov     [ebp+var_250], edx
0x1002ec1a  or      edi, 0FFFFFFFEh
0x1002ec1d  shl     edi, 1Eh
0x1002ec20  test    al, 8
0x1002ec22  jz      short loc_1002EC2B
0x1002ec24  mov     ebx, 4
0x1002ec29  jmp     short loc_1002EC41
0x1002ec2b  test    al, 10h
0x1002ec2d  jz      short loc_1002EC3C
0x1002ec2f  test    al, 20h
0x1002ec31  mov     ebx, 0
0x1002ec36  setnz   bl
0x1002ec39  inc     ebx
0x1002ec3a  jmp     short loc_1002EC41
0x1002ec3c  mov     ebx, 3
0x1002ec41  mov     esi, eax
0x1002ec43  shl     esi, 1Dh
0x1002ec46  test    al, 2
0x1002ec48  jnz     short loc_1002EC55
0x1002ec4a  test    esi, esi
0x1002ec4c  js      short loc_1002EC55
0x1002ec4e  mov     esi, 3
0x1002ec53  jmp     short loc_1002EC61
0x1002ec55  and     esi, 80000000h
0x1002ec5b  neg     esi
0x1002ec5d  sbb     esi, esi
0x1002ec5f  neg     esi
0x1002ec61  test    al, 40h
0x1002ec63  mov     ecx, 10110080h
0x1002ec68  mov     eax, 14110180h
0x1002ec6d  cmovz   eax, ecx
0x1002ec70  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002ec77  mov     [ebp+dwFlagsAndAttributes], eax
0x1002ec7d  jz      short loc_1002EC92
0x1002ec7f  push    0; hTemplateFile
0x1002ec81  push    eax; dwFlagsAndAttributes
0x1002ec82  push    ebx; dwCreationDisposition
0x1002ec83  push    0; lpSecurityAttributes
0x1002ec85  push    esi; dwShareMode
0x1002ec86  push    edi; dwDesiredAccess
0x1002ec87  push    edx; lpFileName
0x1002ec88  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1002ec8e  mov     esi, eax
0x1002ec90  jmp     short loc_1002ECFB
0x1002ec92  push    0FFFFFFFFh; int
0x1002ec94  push    edx; lpWideCharStr
0x1002ec95  lea     ecx, [ebp+var_24C]; this
0x1002ec9b  mov     [ebp+var_24C], 0
0x1002eca5  mov     [ebp+var_248], 0
0x1002ecaf  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x1002ecb4  push    0; hTemplateFile
0x1002ecb6  push    [ebp+dwFlagsAndAttributes]; dwFlagsAndAttributes
0x1002ecbc  push    ebx; dwCreationDisposition
0x1002ecbd  push    0; lpSecurityAttributes
0x1002ecbf  push    esi; dwShareMode
0x1002ecc0  push    edi; dwDesiredAccess
0x1002ecc1  push    [ebp+var_248]; lpFileName
0x1002ecc7  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x1002eccd  mov     ecx, [ebp+var_248]
0x1002ecd3  mov     esi, eax
0x1002ecd5  lea     eax, [ebp+var_244]
0x1002ecdb  cmp     ecx, eax
0x1002ecdd  jz      short loc_1002ECFB
0x1002ecdf  mov     eax, ecx
0x1002ece1  shr     eax, 10h
0x1002ece4  test    eax, eax
0x1002ece6  jz      short loc_1002ECFB
0x1002ece8  cmp     [ebp+var_24C], 0FFFFFFFFh
0x1002ecef  jz      short loc_1002ECFB
0x1002ecf1  push    ecx; Block
0x1002ecf2  call    ds:__imp__free
0x1002ecf8  add     esp, 4
0x1002ecfb  mov     ebx, [ebp+var_25C]
0x1002ed01  mov     [ebx], esi
0x1002ed03  cmp     esi, 0FFFFFFFFh
0x1002ed06  jnz     short loc_1002ED36
0x1002ed08  mov     esi, [ebp+var_254]
0x1002ed0e  push    esi
0x1002ed0f  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002ed14  mov     eax, [ebp+var_250]
0x1002ed1a  mov     ecx, ebx; this
0x1002ed1c  push    eax; unsigned __int16 *
0x1002ed1d  push    esi; struct Err *
0x1002ed1e  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002ed23  pop     edi
0x1002ed24  pop     esi
0x1002ed25  pop     ebx
0x1002ed26  mov     ecx, [ebp+var_4]
0x1002ed29  xor     ecx, ebp; StackCookie
0x1002ed2b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002ed30  mov     esp, ebp
0x1002ed32  pop     ebp
0x1002ed33  retn    8
0x1002ed36  mov     eax, [ebp+var_250]
0x1002ed3c  mov     [ebx+4], eax
0x1002ed3f  lea     eax, [ebp+FileInformation]
0x1002ed42  push    eax; lpFileInformation
0x1002ed43  push    esi; hFile
0x1002ed44  call    ds:__imp__GetFileInformationByHandle@8; GetFileInformationByHandle(x,x)
0x1002ed4a  test    eax, eax
0x1002ed4c  jz      short loc_1002ED6B
0x1002ed4e  test    byte ptr [ebp+FileInformation.dwFileAttributes], 1
0x1002ed52  jz      short loc_1002ED6B
0x1002ed54  test    byte ptr [ebx+10h], 1
0x1002ed58  jnz     short loc_1002ED6B
0x1002ed5a  push    ecx
0x1002ed5b  mov     ecx, [ebp+var_254]
0x1002ed61  push    0FFFFFBF8h
0x1002ed66  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002ed6b  mov     ecx, [ebp+var_4]
0x1002ed6e  pop     edi
0x1002ed6f  pop     esi
0x1002ed70  xor     ecx, ebp; StackCookie
0x1002ed72  pop     ebx
0x1002ed73  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002ed78  mov     esp, ebp
0x1002ed7a  pop     ebp
0x1002ed7b  retn    8
```
