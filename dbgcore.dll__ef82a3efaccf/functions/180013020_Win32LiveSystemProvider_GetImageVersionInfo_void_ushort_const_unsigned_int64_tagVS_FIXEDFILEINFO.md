# Win32LiveSystemProvider::GetImageVersionInfo(void *,ushort const *,unsigned __int64,tagVS_FIXEDFILEINFO *)

- ea: `0x180013020`
- end: `0x180013295`
- name: `?GetImageVersionInfo@Win32LiveSystemProvider@@UEAAJPEAXPEBG_KPEAUtagVS_FIXEDFILEINFO@@@Z`
- size: `629`
- prototype: `int(Win32LiveSystemProvider *__hidden this, void *, const unsigned __int16 *, unsigned __int64, struct tagVS_FIXEDFILEINFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001710`
- `0x180013020`
- `0x180014b0c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013231`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001312a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001312a`

## pseudocode

```c
unsigned int __fastcall Win32LiveSystemProvider::GetImageVersionInfo(
        __int64 (__fastcall **this)(const unsigned __int16 *, int *),
        void *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct tagVS_FIXEDFILEINFO *a5)
{
  unsigned int result; // eax
  __int64 (__fastcall *v8)(const unsigned __int16 *, int *); // rax
  unsigned int v9; // ebx
  int v10; // esi
  signed int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // r14
  int v15; // eax
  signed int LastError; // eax
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  struct tagVS_FIXEDFILEINFO *v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 MultiByteStr[184]; // [rsp+50h] [rbp-B0h] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  result = Win32LiveSystemProvider::LoadVersion((Win32LiveSystemProvider *)this);
  if ( !result )
  {
    if ( this[71] )
    {
      v8 = this[68];
      v9 = 0;
      if ( !v8 )
        goto LABEL_6;
      if ( this[70] )
      {
        v9 = v8(a3, &v17);
LABEL_6:
        if ( this[68] )
        {
          v10 = 0;
          if ( v9 )
          {
LABEL_18:
            v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)this[6] + 8LL))(this[6], v9);
            v14 = v13;
            if ( !v13 )
              return -2147024882;
            if ( v10 )
              v15 = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, _QWORD, __int64))this[69])(
                      MultiByteStr,
                      0,
                      v9,
                      v13);
            else
              v15 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, _QWORD, __int64))this[70])(
                      a3,
                      0,
                      v9,
                      v13);
            if ( v15
              && ((unsigned int (__fastcall *)(__int64, const char *, struct tagVS_FIXEDFILEINFO **, int *))this[71])(
                   v14,
                   "\\",
                   &v19,
                   &v18)
              && v18 == 52 )
            {
              v12 = 0;
              *a5 = *v19;
            }
            else if ( GetLastError() )
            {
              LastError = GetLastError();
              v12 = LastError;
              if ( LastError > 0 )
                v12 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              v12 = -2147467259;
            }
            (*(void (__fastcall **)(__int64 (__fastcall *)(const unsigned __int16 *, int *), __int64))(*(_QWORD *)this[6] + 24LL))(
              this[6],
              v14);
            return v12;
          }
          if ( GetLastError() != 120 )
          {
LABEL_12:
            if ( !GetLastError() )
              return -2147467259;
            v11 = GetLastError();
            v12 = v11;
            if ( v11 > 0 )
              return (unsigned __int16)v11 | 0x80070000;
            return v12;
          }
        }
        if ( this[67] && this[69] )
        {
          if ( WideCharToMultiByte(0, 0x400u, a3, -1, (LPSTR)MultiByteStr, 360, 0, 0) )
          {
            v9 = this[67](MultiByteStr, &v17);
            v10 = 1;
            if ( v9 )
              goto LABEL_18;
          }
          goto LABEL_12;
        }
      }
    }
    return -2147467263;
  }
  return result;
}

```

## disassembly

```asm
0x180013020  mov     [rsp-8+arg_8], rbx
0x180013025  mov     [rsp-8+arg_18], rsi
0x18001302a  push    rbp
0x18001302b  push    rdi
0x18001302c  push    r12
0x18001302e  push    r14
0x180013030  push    r15
0x180013032  lea     rbp, [rsp-0D0h]
0x18001303a  sub     rsp, 1D0h
0x180013041  mov     rax, cs:__security_cookie
0x180013048  xor     rax, rsp
0x18001304b  mov     [rbp+0F0h+var_30], rax
0x180013052  mov     r15, [rbp+0F0h+arg_20]
0x180013059  mov     r12, r8
0x18001305c  mov     rdi, rcx
0x18001305f  mov     [rsp+1F0h+var_1B0], 0
0x180013067  mov     [rsp+1F0h+var_1AC], 0
0x18001306f  mov     [rsp+1F0h+var_1A8], 0
0x180013078  call    ?LoadVersion@Win32LiveSystemProvider@@IEAAJXZ; Win32LiveSystemProvider::LoadVersion(void)
0x18001307d  test    eax, eax
0x18001307f  jnz     loc_18001326A
0x180013085  cmp     qword ptr [rdi+238h], 0
0x18001308d  jz      loc_180013265
0x180013093  mov     rax, [rdi+220h]
0x18001309a  xor     ebx, ebx
0x18001309c  test    rax, rax
0x18001309f  jz      short loc_1800130BD
0x1800130a1  cmp     [rdi+230h], rbx
0x1800130a8  jz      loc_180013265
0x1800130ae  lea     rdx, [rsp+1F0h+var_1B0]
0x1800130b3  mov     rcx, r12
0x1800130b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130bb  mov     ebx, eax
0x1800130bd  cmp     qword ptr [rdi+220h], 0
0x1800130c5  jz      short loc_1800130DC
0x1800130c7  xor     esi, esi
0x1800130c9  test    ebx, ebx
0x1800130cb  jnz     loc_180013182
0x1800130d1  call    cs:__imp_GetLastError
0x1800130d7  cmp     eax, 78h ; 'x'
0x1800130da  jnz     short loc_180013134
0x1800130dc  cmp     qword ptr [rdi+218h], 0
0x1800130e4  jz      loc_180013265
0x1800130ea  cmp     qword ptr [rdi+228h], 0
0x1800130f2  jz      loc_180013265
0x1800130f8  mov     [rsp+1F0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180013101  lea     rax, [rsp+1F0h+MultiByteStr]
0x180013106  mov     [rsp+1F0h+lpDefaultChar], 0; lpDefaultChar
0x18001310f  or      r9d, 0FFFFFFFFh; cchWideChar
0x180013113  mov     [rsp+1F0h+cbMultiByte], 168h; cbMultiByte
0x18001311b  mov     r8, r12; lpWideCharStr
0x18001311e  mov     edx, 400h; dwFlags
0x180013123  mov     [rsp+1F0h+lpMultiByteStr], rax; lpMultiByteStr
0x180013128  xor     ecx, ecx; CodePage
0x18001312a  call    cs:__imp_WideCharToMultiByte
0x180013130  test    eax, eax
0x180013132  jnz     short loc_180013161
0x180013134  call    cs:__imp_GetLastError
0x18001313a  test    eax, eax
0x18001313c  jz      short loc_180013155
0x18001313e  call    cs:__imp_GetLastError
0x180013144  mov     ebx, eax
0x180013146  test    eax, eax
0x180013148  jle     short loc_18001315A
0x18001314a  movzx   ebx, ax
0x18001314d  or      ebx, 80070000h
0x180013153  jmp     short loc_18001315A
0x180013155  mov     ebx, 80004005h
0x18001315a  mov     eax, ebx
0x18001315c  jmp     loc_18001326A
0x180013161  mov     rax, [rdi+218h]
0x180013168  lea     rdx, [rsp+1F0h+var_1B0]
0x18001316d  lea     rcx, [rsp+1F0h+MultiByteStr]
0x180013172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013177  mov     ebx, eax
0x180013179  mov     esi, 1
0x18001317e  test    eax, eax
0x180013180  jz      short loc_180013134
0x180013182  mov     rcx, [rdi+30h]
0x180013186  mov     edx, ebx
0x180013188  mov     rax, [rcx]
0x18001318b  mov     rax, [rax+8]
0x18001318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013194  mov     r14, rax
0x180013197  test    rax, rax
0x18001319a  jnz     short loc_1800131A6
0x18001319c  mov     eax, 8007000Eh
0x1800131a1  jmp     loc_18001326A
0x1800131a6  xor     edx, edx
0x1800131a8  mov     r9, r14
0x1800131ab  mov     r8d, ebx
0x1800131ae  test    esi, esi
0x1800131b0  jz      short loc_1800131C0
0x1800131b2  mov     rax, [rdi+228h]
0x1800131b9  lea     rcx, [rsp+1F0h+MultiByteStr]
0x1800131be  jmp     short loc_1800131CA
0x1800131c0  mov     rax, [rdi+230h]
0x1800131c7  mov     rcx, r12
0x1800131ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131cf  test    eax, eax
0x1800131d1  jz      short loc_180013227
0x1800131d3  mov     rax, [rdi+238h]
0x1800131da  lea     r9, [rsp+1F0h+var_1AC]
0x1800131df  lea     r8, [rsp+1F0h+var_1A8]
0x1800131e4  mov     rcx, r14
0x1800131e7  lea     rdx, asc_180030900; "\\"
0x1800131ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f3  test    eax, eax
0x1800131f5  jz      short loc_180013227
0x1800131f7  cmp     [rsp+1F0h+var_1AC], 34h ; '4'
0x1800131fc  jnz     short loc_180013227
0x1800131fe  mov     rax, [rsp+1F0h+var_1A8]
0x180013203  xor     ebx, ebx
0x180013205  movups  xmm0, xmmword ptr [rax]
0x180013208  movups  xmmword ptr [r15], xmm0
0x18001320c  movups  xmm1, xmmword ptr [rax+10h]
0x180013210  movups  xmmword ptr [r15+10h], xmm1
0x180013215  movups  xmm0, xmmword ptr [rax+20h]
0x180013219  movups  xmmword ptr [r15+20h], xmm0
0x18001321e  mov     eax, [rax+30h]
0x180013221  mov     [r15+30h], eax
0x180013225  jmp     short loc_18001324D
0x180013227  call    cs:__imp_GetLastError
0x18001322d  test    eax, eax
0x18001322f  jz      short loc_180013248
0x180013231  call    cs:__imp_GetLastError
0x180013237  mov     ebx, eax
0x180013239  test    eax, eax
0x18001323b  jle     short loc_18001324D
0x18001323d  movzx   ebx, ax
0x180013240  or      ebx, 80070000h
0x180013246  jmp     short loc_18001324D
0x180013248  mov     ebx, 80004005h
0x18001324d  mov     rcx, [rdi+30h]
0x180013251  mov     rdx, [rcx]
0x180013254  mov     rax, [rdx+18h]
0x180013258  mov     rdx, r14
0x18001325b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013260  jmp     loc_18001315A
0x180013265  mov     eax, 80004001h
0x18001326a  mov     rcx, [rbp+0F0h+var_30]
0x180013271  xor     rcx, rsp; StackCookie
0x180013274  call    __security_check_cookie
0x180013279  lea     r11, [rsp+1F0h+var_20]
0x180013281  mov     rbx, [r11+38h]
0x180013285  mov     rsi, [r11+48h]
0x180013289  mov     rsp, r11
0x18001328c  pop     r15
0x18001328e  pop     r14
0x180013290  pop     r12
0x180013292  pop     rdi
0x180013293  pop     rbp
0x180013294  retn
```
