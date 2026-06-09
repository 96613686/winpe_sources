# CTypeInfo2::AddressOfModuleFunc(InfoDef *,tagFuncDescr *,void * *)

- ea: `0x18004bcbc`
- end: `0x18004bfc6`
- name: `?AddressOfModuleFunc@CTypeInfo2@@QEAAJPEAVInfoDef@@PEAUtagFuncDescr@@PEAPEAX@Z`
- size: `778`
- prototype: `__int64 __fastcall(CTypeInfo2 *__hidden this, struct InfoDef *, struct tagFuncDescr *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18004bb90`

## callees

- `0x180030014`
- `0x18004bcbc`
- `0x18004d900`
- `0x18004dcf0`
- `0x18004e530`
- `0x180067b34`
- `0x18006d5b8`
- `0x18006d734`
- `0x18009a624`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18004be46`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18004be46`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004bf8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004bf8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004befe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bf54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004befe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bf54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18004be89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18004be89`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004be78`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004be9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004be78`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18004be9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bf83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bf83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004be5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004be5d`

## pseudocode

```c
__int64 __fastcall CTypeInfo2::AddressOfModuleFunc(
        CTypeLib2 **this,
        struct InfoDef *a2,
        struct tagFuncDescr *a3,
        FARPROC *a4)
{
  __int64 result; // rax
  char *v8; // rdx
  unsigned int v9; // ecx
  int v10; // r15d
  unsigned int *v11; // rdi
  CTypeLib2 *v12; // rax
  unsigned __int16 *v13; // r14
  unsigned int v14; // r8d
  unsigned __int16 *v15; // rdx
  unsigned __int16 v16; // ax
  unsigned __int64 v17; // rbx
  unsigned __int8 *v18; // rax
  HMODULE Library; // rsi
  UINT v20; // ebx
  DWORD LastError; // edi
  DWORD v22; // edi
  DWORD v23; // edi
  unsigned int v24; // ebx
  FARPROC ProcAddress; // rax
  unsigned __int16 v26; // ax
  unsigned __int64 v27; // rdi
  FARPROC v28; // rax
  unsigned __int8 v30[272]; // [rsp+30h] [rbp-D0h] BYREF
  CHAR Str[272]; // [rsp+140h] [rbp+40h] BYREF

  result = CTypeLib2::EnsureStringsReadable(this[4]);
  if ( (int)result >= 0 )
  {
    v8 = (char *)a3
       + *(unsigned __int16 *)a3
       - *((unsigned __int16 *)a3 + 10) * ((*((_WORD *)a3 + 8) & 0x1000) != 0 ? 16LL : 12LL);
    if ( v8 <= (char *)a3 + 40 || (v9 = *((_DWORD *)a3 + 10), v9 == -1) )
    {
      v9 = *((_DWORD *)a2 + 26);
      if ( v9 == -1 )
        return 2147647535LL;
      v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    v11 = (unsigned int *)((char *)a3 + 32);
    if ( v8 > (char *)a3 + 32 )
    {
      v12 = this[4];
      v13 = 0;
      v14 = *((_DWORD *)v12 + 57);
      if ( v9 < v14 )
        v15 = (unsigned __int16 *)(*((_QWORD *)v12 + 30) + v9);
      else
        v15 = 0;
      if ( (*((_WORD *)a3 + 8) & 0x2000) == 0 && *v11 < v14 )
        v13 = (unsigned __int16 *)(*((_QWORD *)v12 + 30) + *v11);
      v16 = *v15;
      if ( *v15 >= 0x102u )
        v16 = 258;
      v17 = v16;
      memcpy_0(Str, v15 + 1, v16);
      if ( v17 < 0x104 )
      {
        Str[v17] = 0;
        memset_0(v30, 0, 0x108u);
        if ( (Str[0] == 92 || mbschr((const unsigned __int8 *)Str, 0x3Au))
          && (unsigned int)OpenLongFileA(Str, (__int64)v30, 0x4000) == -1 )
        {
          v18 = mbsrchr((const unsigned __int8 *)Str, 0x5Cu);
          if ( !v18 )
            v18 = mbsrchr((const unsigned __int8 *)Str, 0x3Au);
          strcpy_s(Str, 0x104u, (const char *)v18);
        }
        if ( !v10 )
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this[4] + 608));
        Library = (HMODULE)this[6];
        if ( (unsigned __int64)Library < 0x20 || v10 )
        {
          v20 = SetErrorMode(0x8001u);
          Library = LoadLibraryExA(Str, 0, 0);
          LastError = GetLastError();
          SetErrorMode(v20);
          if ( (unsigned __int64)Library < 0x20 )
          {
            if ( LastError )
            {
              v22 = LastError - 2;
              if ( v22 )
              {
                v23 = v22 - 1;
                if ( !v23 )
                {
                  v24 = -2147287037;
                  goto LABEL_36;
                }
                if ( v23 - 123 >= 2 )
                {
                  v24 = -2147312566;
                  goto LABEL_36;
                }
              }
              v24 = -2147287038;
            }
            else
            {
              v24 = -2147024882;
            }
LABEL_36:
            if ( v10 )
              return v24;
LABEL_48:
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this[4] + 608));
            return v24;
          }
          v11 = (unsigned int *)((char *)a3 + 32);
        }
        if ( (*((_WORD *)a3 + 8) & 0x2000) != 0 )
        {
          ProcAddress = GetProcAddress(Library, (LPCSTR)*(unsigned __int16 *)v11);
          *a4 = ProcAddress;
          v24 = ProcAddress == 0 ? 0x8002802F : 0;
LABEL_46:
          if ( v10 )
          {
            FreeLibrary(Library);
            return v24;
          }
          this[6] = (CTypeLib2 *)Library;
          goto LABEL_48;
        }
        v26 = *v13;
        if ( *v13 >= 0x102u )
          v26 = 258;
        v27 = v26;
        memcpy_0(Str, v13 + 1, v26);
        if ( v27 < 0x104 )
        {
          v24 = 0;
          Str[v27] = 0;
          v28 = GetProcAddress(Library, Str);
          *a4 = v28;
          if ( !v28 )
            v24 = -2147319761;
          goto LABEL_46;
        }
      }
      _report_rangecheckfailure();
    }
    return 2147647535LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004bcbc  push    rbp
0x18004bcbe  push    rbx
0x18004bcbf  push    rsi
0x18004bcc0  push    rdi
0x18004bcc1  push    r12
0x18004bcc3  push    r13
0x18004bcc5  push    r14
0x18004bcc7  push    r15
0x18004bcc9  lea     rbp, [rsp-168h]
0x18004bcd1  sub     rsp, 268h
0x18004bcd8  mov     rax, cs:__security_cookie
0x18004bcdf  xor     rax, rsp
0x18004bce2  mov     [rbp+1A0h+var_50], rax
0x18004bce9  mov     r12, rcx
0x18004bcec  mov     [rsp+2A0h+var_280], r9
0x18004bcf1  mov     rcx, [rcx+20h]; this
0x18004bcf5  mov     r13, r8
0x18004bcf8  mov     rbx, rdx
0x18004bcfb  call    ?EnsureStringsReadable@CTypeLib2@@QEAAJXZ; CTypeLib2::EnsureStringsReadable(void)
0x18004bd00  test    eax, eax
0x18004bd02  js      loc_18004BFA3
0x18004bd08  movzx   eax, word ptr [r13+10h]
0x18004bd0d  mov     ecx, 1000h
0x18004bd12  movzx   edx, word ptr [r13+0]
0x18004bd17  and     ax, cx
0x18004bd1a  neg     ax
0x18004bd1d  movzx   eax, word ptr [r13+14h]
0x18004bd22  sbb     rcx, rcx
0x18004bd25  and     ecx, 4
0x18004bd28  add     rcx, 0Ch
0x18004bd2c  imul    rcx, rax
0x18004bd30  or      eax, 0FFFFFFFFh
0x18004bd33  sub     rdx, rcx
0x18004bd36  lea     rcx, [r13+28h]
0x18004bd3a  add     rdx, r13
0x18004bd3d  cmp     rdx, rcx
0x18004bd40  jbe     short loc_18004BD50
0x18004bd42  mov     ecx, [rcx]
0x18004bd44  cmp     ecx, eax
0x18004bd46  jz      short loc_18004BD50
0x18004bd48  mov     r15d, 1
0x18004bd4e  jmp     short loc_18004BD5E
0x18004bd50  mov     ecx, [rbx+68h]
0x18004bd53  cmp     ecx, eax
0x18004bd55  jz      loc_18004BF9E
0x18004bd5b  xor     r15d, r15d
0x18004bd5e  lea     rdi, [r13+20h]
0x18004bd62  cmp     rdx, rdi
0x18004bd65  jbe     loc_18004BF9E
0x18004bd6b  mov     rax, [r12+20h]
0x18004bd70  xor     r14d, r14d
0x18004bd73  mov     r8d, [rax+0E4h]
0x18004bd7a  cmp     ecx, r8d
0x18004bd7d  jb      short loc_18004BD83
0x18004bd7f  xor     edx, edx
0x18004bd81  jmp     short loc_18004BD8C
0x18004bd83  mov     edx, ecx
0x18004bd85  add     rdx, [rax+0F0h]
0x18004bd8c  mov     ecx, 2000h
0x18004bd91  test    [r13+10h], cx
0x18004bd96  jnz     short loc_18004BDA7
0x18004bd98  cmp     [rdi], r8d
0x18004bd9b  jnb     short loc_18004BDA7
0x18004bd9d  mov     r14d, [rdi]
0x18004bda0  add     r14, [rax+0F0h]
0x18004bda7  movzx   eax, word ptr [rdx]
0x18004bdaa  mov     ecx, 102h
0x18004bdaf  cmp     ax, cx
0x18004bdb2  jb      short loc_18004BDB6
0x18004bdb4  mov     eax, ecx
0x18004bdb6  movzx   ebx, ax
0x18004bdb9  lea     rcx, [rbp+1A0h+Str]; void *
0x18004bdbd  mov     r8d, ebx; Size
0x18004bdc0  add     rdx, 2; Src
0x18004bdc4  call    memcpy_0
0x18004bdc9  mov     esi, 104h
0x18004bdce  cmp     rbx, rsi
0x18004bdd1  jnb     loc_18004BF98
0x18004bdd7  xor     edx, edx; Val
0x18004bdd9  mov     [rbp+rbx+1A0h+Str], 0
0x18004bdde  lea     r8d, [rsi+4]; Size
0x18004bde2  lea     rcx, [rsp+2A0h+var_270]; void *
0x18004bde7  call    memset_0
0x18004bdec  cmp     [rbp+1A0h+Str], 5Ch ; '\'
0x18004bdf0  mov     ebx, 3Ah ; ':'
0x18004bdf5  jz      short loc_18004BE07
0x18004bdf7  mov     edx, ebx; C
0x18004bdf9  lea     rcx, [rbp+1A0h+Str]; Str
0x18004bdfd  call    _mbschr
0x18004be02  test    rax, rax
0x18004be05  jz      short loc_18004BE4C
0x18004be07  mov     r8d, 4000h
0x18004be0d  lea     rdx, [rsp+2A0h+var_270]
0x18004be12  lea     rcx, [rbp+1A0h+Str]; lpFileName
0x18004be16  call    OpenLongFileA
0x18004be1b  cmp     eax, 0FFFFFFFFh
0x18004be1e  jnz     short loc_18004BE4C
0x18004be20  lea     edx, [rax+5Dh]; C
0x18004be23  lea     rcx, [rbp+1A0h+Str]; String
0x18004be27  call    _mbsrchr
0x18004be2c  test    rax, rax
0x18004be2f  jnz     short loc_18004BE3C
0x18004be31  mov     edx, ebx; C
0x18004be33  lea     rcx, [rbp+1A0h+Str]; String
0x18004be37  call    _mbsrchr
0x18004be3c  mov     r8, rax; Source
0x18004be3f  lea     rcx, [rbp+1A0h+Str]; Destination
0x18004be43  mov     rdx, rsi; SizeInBytes
0x18004be46  call    cs:__imp_strcpy_s
0x18004be4c  test    r15d, r15d
0x18004be4f  jnz     short loc_18004BE63
0x18004be51  mov     rcx, [r12+20h]
0x18004be56  add     rcx, 260h; lpCriticalSection
0x18004be5d  call    cs:__imp_EnterCriticalSection
0x18004be63  mov     rsi, [r12+30h]
0x18004be68  cmp     rsi, 20h ; ' '
0x18004be6c  jb      short loc_18004BE73
0x18004be6e  test    r15d, r15d
0x18004be71  jz      short loc_18004BEEC
0x18004be73  mov     ecx, 8001h; uMode
0x18004be78  call    cs:__imp_SetErrorMode
0x18004be7e  xor     r8d, r8d; dwFlags
0x18004be81  lea     rcx, [rbp+1A0h+Str]; lpLibFileName
0x18004be85  xor     edx, edx; hFile
0x18004be87  mov     ebx, eax
0x18004be89  call    cs:__imp_LoadLibraryExA
0x18004be8f  mov     rsi, rax
0x18004be92  call    cs:__imp_GetLastError
0x18004be98  mov     ecx, ebx; uMode
0x18004be9a  mov     edi, eax
0x18004be9c  call    cs:__imp_SetErrorMode
0x18004bea2  cmp     rsi, 20h ; ' '
0x18004bea6  jnb     short loc_18004BEE8
0x18004bea8  test    edi, edi
0x18004beaa  jz      short loc_18004BED5
0x18004beac  sub     edi, 2
0x18004beaf  jz      short loc_18004BECE
0x18004beb1  sub     edi, 1
0x18004beb4  jz      short loc_18004BEC7
0x18004beb6  sub     edi, 7Bh ; '{'
0x18004beb9  jz      short loc_18004BECE
0x18004bebb  cmp     edi, 1
0x18004bebe  jz      short loc_18004BECE
0x18004bec0  mov     ebx, 80029C4Ah
0x18004bec5  jmp     short loc_18004BEDA
0x18004bec7  mov     ebx, 80030003h
0x18004becc  jmp     short loc_18004BEDA
0x18004bece  mov     ebx, 80030002h
0x18004bed3  jmp     short loc_18004BEDA
0x18004bed5  mov     ebx, 8007000Eh
0x18004beda  test    r15d, r15d
0x18004bedd  jnz     loc_18004BF94
0x18004bee3  jmp     loc_18004BF77
0x18004bee8  lea     rdi, [r13+20h]
0x18004beec  mov     eax, 2000h
0x18004bef1  test    [r13+10h], ax
0x18004bef6  jz      short loc_18004BF1B
0x18004bef8  movzx   edx, word ptr [rdi]; lpProcName
0x18004befb  mov     rcx, rsi; hModule
0x18004befe  call    cs:__imp_GetProcAddress
0x18004bf04  mov     rcx, [rsp+2A0h+var_280]
0x18004bf09  mov     [rcx], rax
0x18004bf0c  neg     rax
0x18004bf0f  sbb     ebx, ebx
0x18004bf11  not     ebx
0x18004bf13  and     ebx, 8002802Fh
0x18004bf19  jmp     short loc_18004BF6D
0x18004bf1b  movzx   eax, word ptr [r14]
0x18004bf1f  mov     ecx, 102h
0x18004bf24  cmp     ax, cx
0x18004bf27  jb      short loc_18004BF2B
0x18004bf29  mov     eax, ecx
0x18004bf2b  movzx   edi, ax
0x18004bf2e  lea     rdx, [r14+2]; Src
0x18004bf32  mov     r8d, edi; Size
0x18004bf35  lea     rcx, [rbp+1A0h+Str]; void *
0x18004bf39  call    memcpy_0
0x18004bf3e  cmp     rdi, 104h
0x18004bf45  jnb     short loc_18004BF98
0x18004bf47  xor     ebx, ebx
0x18004bf49  lea     rdx, [rbp+1A0h+Str]; lpProcName
0x18004bf4d  mov     rcx, rsi; hModule
0x18004bf50  mov     [rbp+rdi+1A0h+Str], bl
0x18004bf54  call    cs:__imp_GetProcAddress
0x18004bf5a  mov     rcx, [rsp+2A0h+var_280]
0x18004bf5f  test    rax, rax
0x18004bf62  mov     [rcx], rax
0x18004bf65  mov     ecx, 8002802Fh
0x18004bf6a  cmovz   ebx, ecx
0x18004bf6d  test    r15d, r15d
0x18004bf70  jnz     short loc_18004BF8B
0x18004bf72  mov     [r12+30h], rsi
0x18004bf77  mov     rcx, [r12+20h]
0x18004bf7c  add     rcx, 260h; lpCriticalSection
0x18004bf83  call    cs:__imp_LeaveCriticalSection
0x18004bf89  jmp     short loc_18004BF94
0x18004bf8b  mov     rcx, rsi; hLibModule
0x18004bf8e  call    cs:__imp_FreeLibrary
0x18004bf94  mov     eax, ebx
0x18004bf96  jmp     short loc_18004BFA3
0x18004bf98  call    __report_rangecheckfailure
0x18004bf9e  mov     eax, 8002802Fh
0x18004bfa3  mov     rcx, [rbp+1A0h+var_50]
0x18004bfaa  xor     rcx, rsp; StackCookie
0x18004bfad  call    __security_check_cookie
0x18004bfb2  add     rsp, 268h
0x18004bfb9  pop     r15
0x18004bfbb  pop     r14
0x18004bfbd  pop     r13
0x18004bfbf  pop     r12
0x18004bfc1  pop     rdi
0x18004bfc2  pop     rsi
0x18004bfc3  pop     rbx
0x18004bfc4  pop     rbp
0x18004bfc5  retn
```
