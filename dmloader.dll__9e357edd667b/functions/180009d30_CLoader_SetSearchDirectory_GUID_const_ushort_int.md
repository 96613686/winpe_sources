# CLoader::SetSearchDirectory(_GUID const &,ushort *,int)

- ea: `0x180009d30`
- end: `0x180009f52`
- name: `?SetSearchDirectory@CLoader@@UEAAJAEBU_GUID@@PEAGH@Z`
- size: `546`
- prototype: `__int64 __fastcall(CLoader *__hidden this, const struct _GUID *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800015d0`
- `0x180006bfc`
- `0x1800089e4`
- `0x180009d30`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000c5d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009dfc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009dfc`

## pseudocode

```c
__int64 __fastcall CLoader::SetSearchDirectory(CLoader *this, const struct _GUID *a2, unsigned __int16 *a3, int a4)
{
  __int64 v8; // r15
  WCHAR *v9; // rax
  __int64 v10; // r14
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  int Class; // ebx
  WCHAR *v14; // rcx
  __int64 v15; // rax
  DWORD FileAttributesW; // eax
  CClass *v17; // rdi
  int v18; // eax
  WCHAR *v19; // rcx
  _WORD *v20; // rax
  _WORD *v21; // rcx
  __int128 v22; // xmm0
  unsigned __int64 v23; // rdx
  struct CClass *v24; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v25[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  __int128 v27; // [rsp+4Ch] [rbp-B4h]
  WCHAR FileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  if ( !a3 )
    return 2147500035LL;
  v8 = 2147483646;
  v9 = FileName;
  v10 = 260;
  v11 = 2147483646;
  v12 = 260;
  Class = -2005397119;
  do
  {
    if ( !v11 )
      break;
    if ( !*a3 )
      break;
    *v9++ = *a3++;
    --v11;
    --v12;
  }
  while ( v12 );
  v14 = v9 - 1;
  if ( v12 )
    v14 = v9;
  v15 = -1;
  *v14 = 0;
  do
    ++v15;
  while ( FileName[v15] );
  if ( FileName[v15 - 1] != 92 )
    StringCchCatW(FileName, v12, L"\\");
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_DirectMusicAllTypes.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_DirectMusicAllTypes.Data4 )
    {
      v17 = (CClass *)*((_QWORD *)this + 3);
      Class = 0;
      if ( v17 )
      {
        do
        {
          v18 = CClass::SetSearchDirectory(v17, FileName, a4);
          v17 = *(CClass **)v17;
          if ( v18 == 1 )
            Class = 1;
        }
        while ( v17 );
        v8 = 2147483646;
      }
      v19 = FileName;
      v20 = (_WORD *)((char *)this + 32);
      do
      {
        if ( !v8 )
          break;
        if ( !*v19 )
          break;
        *v20++ = *v19++;
        --v8;
        --v10;
      }
      while ( v10 );
      v21 = v20 - 1;
      if ( v10 )
        v21 = v20;
      *v21 = 0;
      *((_DWORD *)this + 138) = 1;
    }
    else
    {
      v24 = 0;
      CDescriptor::CDescriptor((CDescriptor *)v25);
      v22 = (__int128)*a2;
      v26 = 2;
      v27 = v22;
      Class = CLoader::GetClass(this, (struct CDescriptor *)v25, &v24, 1);
      if ( Class >= 0 )
        Class = CClass::SetSearchDirectory(v24, FileName, a4);
      CDescriptor::~CDescriptor((CDescriptor *)v25, v23);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  }
  return (unsigned int)Class;
}

```

## disassembly

```asm
0x180009d30  mov     [rsp-8+arg_10], rbx
0x180009d35  push    rbp
0x180009d36  push    rsi
0x180009d37  push    rdi
0x180009d38  push    r12
0x180009d3a  push    r13
0x180009d3c  push    r14
0x180009d3e  push    r15
0x180009d40  lea     rbp, [rsp-200h]
0x180009d48  sub     rsp, 300h
0x180009d4f  mov     rax, cs:__security_cookie
0x180009d56  xor     rax, rsp
0x180009d59  mov     [rbp+230h+var_40], rax
0x180009d60  xor     r10d, r10d
0x180009d63  mov     r13d, r9d
0x180009d66  mov     rdi, rdx
0x180009d69  mov     rsi, rcx
0x180009d6c  test    r8, r8
0x180009d6f  jnz     short loc_180009D7B
0x180009d71  mov     eax, 80004003h
0x180009d76  jmp     loc_180009F28
0x180009d7b  mov     r15d, 7FFFFFFEh
0x180009d81  lea     rax, [rbp+230h+FileName]
0x180009d85  mov     r14d, 104h
0x180009d8b  mov     ecx, r15d
0x180009d8e  mov     edx, r14d
0x180009d91  mov     ebx, 88781181h
0x180009d96  mov     r11d, 1
0x180009d9c  test    rcx, rcx
0x180009d9f  jz      short loc_180009DBF
0x180009da1  movzx   r9d, word ptr [r8]
0x180009da5  test    r9w, r9w
0x180009da9  jz      short loc_180009DBF
0x180009dab  mov     [rax], r9w
0x180009daf  add     r8, 2
0x180009db3  add     rax, 2
0x180009db7  sub     rcx, r11
0x180009dba  sub     rdx, r11; unsigned __int64
0x180009dbd  jnz     short loc_180009D9C
0x180009dbf  test    rdx, rdx
0x180009dc2  lea     rcx, [rax-2]
0x180009dc6  cmovnz  rcx, rax
0x180009dca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009dce  mov     [rcx], r10w
0x180009dd2  lea     rcx, [rbp+230h+FileName]
0x180009dd6  inc     rax
0x180009dd9  cmp     [rcx+rax*2], r10w
0x180009dde  jnz     short loc_180009DD6
0x180009de0  cmp     [rbp+rax*2+230h+var_252], 5Ch ; '\'
0x180009de6  jz      short loc_180009DF8
0x180009de8  lea     r8, asc_1800121E8; "\\"
0x180009def  lea     rcx, [rbp+230h+FileName]; unsigned __int16 *
0x180009df3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009df8  lea     rcx, [rbp+230h+FileName]; lpFileName
0x180009dfc  call    cs:__imp_GetFileAttributesW
0x180009e02  cmp     eax, 0FFFFFFFFh
0x180009e05  jz      loc_180009F26
0x180009e0b  test    al, 10h
0x180009e0d  jz      loc_180009F26
0x180009e13  lea     r12, [rsi+238h]
0x180009e1a  mov     rcx, r12; lpCriticalSection
0x180009e1d  call    cs:__imp_EnterCriticalSection
0x180009e23  mov     rax, [rdi]
0x180009e26  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data1
0x180009e2d  jnz     loc_180009EBE
0x180009e33  mov     rax, [rdi+8]
0x180009e37  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data4
0x180009e3e  jnz     short loc_180009EBE
0x180009e40  mov     rdi, [rsi+18h]
0x180009e44  xor     r8d, r8d
0x180009e47  mov     ebx, r8d
0x180009e4a  test    rdi, rdi
0x180009e4d  jz      short loc_180009E7A
0x180009e4f  lea     r15d, [r8+1]
0x180009e53  mov     r8d, r13d; int
0x180009e56  lea     rdx, [rbp+230h+FileName]; unsigned __int16 *
0x180009e5a  mov     rcx, rdi; this
0x180009e5d  call    ?SetSearchDirectory@CClass@@QEAAJPEAGH@Z; CClass::SetSearchDirectory(ushort *,int)
0x180009e62  mov     rdi, [rdi]
0x180009e65  cmp     eax, r15d
0x180009e68  cmovz   ebx, r15d
0x180009e6c  test    rdi, rdi
0x180009e6f  jnz     short loc_180009E53
0x180009e71  mov     r15d, 7FFFFFFEh
0x180009e77  xor     r8d, r8d
0x180009e7a  lea     rcx, [rbp+230h+FileName]
0x180009e7e  lea     rax, [rsi+20h]
0x180009e82  test    r15, r15
0x180009e85  jz      short loc_180009EA3
0x180009e87  movzx   edx, word ptr [rcx]
0x180009e8a  test    dx, dx
0x180009e8d  jz      short loc_180009EA3
0x180009e8f  mov     [rax], dx
0x180009e92  add     rcx, 2
0x180009e96  add     rax, 2
0x180009e9a  dec     r15
0x180009e9d  sub     r14, 1
0x180009ea1  jnz     short loc_180009E82
0x180009ea3  test    r14, r14
0x180009ea6  lea     rcx, [rax-2]
0x180009eaa  cmovnz  rcx, rax
0x180009eae  mov     [rcx], r8w
0x180009eb2  mov     dword ptr [rsi+228h], 1
0x180009ebc  jmp     short loc_180009F1D
0x180009ebe  lea     rcx, [rsp+330h+var_300]; this
0x180009ec3  mov     [rsp+330h+var_310], 0
0x180009ecc  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180009ed1  movups  xmm0, xmmword ptr [rdi]
0x180009ed4  mov     r9d, 1; int
0x180009eda  mov     [rsp+330h+var_2F8], 2
0x180009ee2  lea     r8, [rsp+330h+var_310]; struct CClass **
0x180009ee7  mov     rcx, rsi; this
0x180009eea  lea     rdx, [rsp+330h+var_300]; struct CDescriptor *
0x180009eef  movdqu  [rsp+330h+var_2E4], xmm0
0x180009ef5  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x180009efa  mov     ebx, eax
0x180009efc  test    eax, eax
0x180009efe  js      short loc_180009F13
0x180009f00  mov     rcx, [rsp+330h+var_310]; this
0x180009f05  lea     rdx, [rbp+230h+FileName]; unsigned __int16 *
0x180009f09  mov     r8d, r13d; int
0x180009f0c  call    ?SetSearchDirectory@CClass@@QEAAJPEAGH@Z; CClass::SetSearchDirectory(ushort *,int)
0x180009f11  mov     ebx, eax
0x180009f13  lea     rcx, [rsp+330h+var_300]; this
0x180009f18  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x180009f1d  mov     rcx, r12; lpCriticalSection
0x180009f20  call    cs:__imp_LeaveCriticalSection
0x180009f26  mov     eax, ebx
0x180009f28  mov     rcx, [rbp+230h+var_40]
0x180009f2f  xor     rcx, rsp; StackCookie
0x180009f32  call    __security_check_cookie
0x180009f37  mov     rbx, [rsp+330h+arg_10]
0x180009f3f  add     rsp, 300h
0x180009f46  pop     r15
0x180009f48  pop     r14
0x180009f4a  pop     r13
0x180009f4c  pop     r12
0x180009f4e  pop     rdi
0x180009f4f  pop     rsi
0x180009f50  pop     rbp
0x180009f51  retn
```
