# details::GetBinaryVersion(ushort *,ulong,ushort *,ulong *)

- ea: `0x1800260b8`
- end: `0x180026437`
- name: `?GetBinaryVersion@details@@YAKPEAGK0PEAK@Z`
- size: `895`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180025be0`

## callees

- `0x18002283c`
- `0x1800260b8`
- `0x180026790`
- `0x180026eb0`
- `0x180047240`
- `0x180047880`
- `0x180047f54`
- `0x180047f78`
- `0x1800561fc`
- `0x18005a548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800261a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1800261a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002630f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002630f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026346`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002629a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002629a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180026305`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180026305`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800262c4`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x1800262c4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002633c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002633c`

## string_xrefs

- `0x180026211`: `system32\`

## pseudocode

```c
errno_t __fastcall details::GetBinaryVersion(
        unsigned __int16 *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  unsigned __int16 *v9; // r8
  __int64 v10; // rax
  wchar_t *v11; // rcx
  unsigned __int16 v12; // r9
  errno_t result; // eax
  DWORD v14; // eax
  DWORD FileVersionInfoSizeW; // eax
  size_t v16; // rbx
  void *v17; // rdi
  DWORD v18; // ebx
  DWORD LastError; // ebx
  int v20; // eax
  unsigned __int64 v21; // rdx
  errno_t v22; // ebx
  int v23; // eax
  errno_t v24; // ebx
  int v25; // [rsp+20h] [rbp-498h]
  int v26; // [rsp+28h] [rbp-490h]
  int v27; // [rsp+30h] [rbp-488h]
  unsigned __int64 v28; // [rsp+40h] [rbp-478h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-470h] BYREF
  unsigned int puLen; // [rsp+50h] [rbp-468h] BYREF
  void *v31; // [rsp+58h] [rbp-460h] BYREF
  wchar_t String[264]; // [rsp+60h] [rbp-458h] BYREF
  WCHAR Src[264]; // [rsp+270h] [rbp-248h] BYREF

  memset_0(String, 0, 0x208u);
  memset_0(Src, 0, 0x208u);
  lpBuffer = 0;
  puLen = 0;
  v28 = 0;
  if ( !a1 || a2 < 8 || !a3 || !a4 || *a4 < 0x10 )
    return 87;
  v8 = 2147483646;
  v9 = a1;
  v10 = 260;
  v11 = String;
  while ( v8 )
  {
    v12 = *v9;
    if ( *v9 )
    {
      ++v9;
      *v11++ = v12;
      --v8;
      if ( --v10 )
        continue;
    }
    if ( !v10 )
      return 122;
    break;
  }
  *v11 = 0;
  result = _wcslwr_s(String, 0x104u);
  if ( !result )
  {
    if ( !memcmp_0(L"\\systemroot\\", String, 0x18u) )
    {
      result = StringCchPrintfW(Src, 0x104u, L"%%SystemRoot%%\\%s", a1 + 12);
      if ( result < 0 )
      {
        if ( (result & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)result;
        return result;
      }
    }
    else if ( !memcmp_0(L"system32\\", String, 0x12u) )
    {
      result = StringCchPrintfW(Src, 0x104u, L"%%SystemRoot%%\\%s", a1);
      if ( result < 0 )
      {
        if ( (result & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)result;
        return result;
      }
    }
    else
    {
      result = StringCchCopyW(Src, 0x104u, a1);
      if ( result < 0 )
      {
        if ( (result & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)result;
        return result;
      }
    }
    memset_0(String, 0, 0x208u);
    v14 = ExpandEnvironmentStringsW(Src, String, 0x104u);
    if ( !v14 )
      return GetLastError();
    if ( v14 > 0x104 )
      return 14;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(String, 0);
    v16 = FileVersionInfoSizeW;
    if ( !FileVersionInfoSizeW )
      return GetLastError();
    try
    {
      v17 = operator new[](FileVersionInfoSizeW);
      memset_0(v17, 0, v16);
      v31 = v17;
      if ( GetFileVersionInfoW(String, 0, v16, v17) )
      {
        if ( VerQueryValueW(v17, L"\\", &lpBuffer, &puLen) )
        {
          v27 = *((unsigned __int16 *)lpBuffer + 6);
          v26 = *((unsigned __int16 *)lpBuffer + 7);
          v25 = *((unsigned __int16 *)lpBuffer + 4);
          v20 = StringCbPrintfW(a3, *a4, L"%d.%d.%d.%d", *((unsigned __int16 *)lpBuffer + 5), v25, v26, v27);
          v22 = v20;
          if ( v20 >= 0 )
          {
            v23 = StringCbLengthW(a3, v21, &v28);
            v24 = v23;
            if ( v23 >= 0 )
            {
              *a4 = v28 + 2;
              std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v31);
              result = 0;
            }
            else
            {
              if ( (v23 & 0x1FFF0000) == 0x70000 )
                v24 = (unsigned __int16)v23;
              std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v31);
              result = v24;
            }
          }
          else
          {
            if ( (v20 & 0x1FFF0000) == 0x70000 )
              v22 = (unsigned __int16)v20;
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v31);
            result = v22;
          }
        }
        else
        {
          LastError = GetLastError();
          std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v31);
          result = LastError;
        }
      }
      else
      {
        v18 = GetLastError();
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v31);
        result = v18;
      }
    }
    catch ( ... )
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800260b8  mov     [rsp+arg_8], rbx
0x1800260bd  push    rsi
0x1800260be  push    rdi
0x1800260bf  push    r12
0x1800260c1  push    r14
0x1800260c3  push    r15
0x1800260c5  sub     rsp, 490h
0x1800260cc  mov     rax, cs:__security_cookie
0x1800260d3  xor     rax, rsp
0x1800260d6  mov     [rsp+4B8h+var_38], rax
0x1800260de  mov     r14, r9
0x1800260e1  mov     r15, r8
0x1800260e4  mov     edi, edx
0x1800260e6  mov     rbx, rcx
0x1800260e9  xor     r12d, r12d
0x1800260ec  mov     esi, 208h
0x1800260f1  mov     r8d, esi; Size
0x1800260f4  xor     edx, edx; Val
0x1800260f6  lea     rcx, [rsp+4B8h+String]; void *
0x1800260fb  call    memset_0
0x180026100  mov     r8d, esi; Size
0x180026103  xor     edx, edx; Val
0x180026105  lea     rcx, [rsp+4B8h+Src]; void *
0x18002610d  call    memset_0
0x180026112  mov     [rsp+4B8h+lpBuffer], r12
0x180026117  mov     [rsp+4B8h+puLen], r12d
0x18002611c  mov     [rsp+4B8h+var_478], r12
0x180026121  test    rbx, rbx
0x180026124  jz      loc_180026402
0x18002612a  cmp     edi, 8
0x18002612d  jb      loc_180026402
0x180026133  test    r15, r15
0x180026136  jz      loc_180026402
0x18002613c  test    r14, r14
0x18002613f  jz      loc_180026402
0x180026145  cmp     dword ptr [r14], 10h
0x180026149  jb      loc_180026402
0x18002614f  mov     edx, 7FFFFFFEh
0x180026154  mov     r8, rbx
0x180026157  mov     edi, 104h
0x18002615c  mov     eax, edi
0x18002615e  lea     rcx, [rsp+4B8h+String]
0x180026163  test    rdx, rdx
0x180026166  jz      short loc_180026196
0x180026168  movzx   r9d, word ptr [r8]
0x18002616c  test    r9w, r9w
0x180026170  jz      short loc_180026187
0x180026172  add     r8, 2
0x180026176  mov     [rcx], r9w
0x18002617a  add     rcx, 2
0x18002617e  dec     rdx
0x180026181  sub     rax, 1
0x180026185  jnz     short loc_180026163
0x180026187  test    rax, rax
0x18002618a  jnz     short loc_180026196
0x18002618c  mov     eax, 7Ah ; 'z'
0x180026191  jmp     loc_18002640E
0x180026196  mov     [rcx], r12w
0x18002619a  mov     rdx, rdi; SizeInWords
0x18002619d  lea     rcx, [rsp+4B8h+String]; String
0x1800261a2  call    cs:__imp__wcslwr_s
0x1800261a8  test    eax, eax
0x1800261aa  jnz     loc_18002640E
0x1800261b0  mov     r8d, 18h; Size
0x1800261b6  lea     rdx, [rsp+4B8h+String]; Buf2
0x1800261bb  lea     rcx, aSystemroot; "\\systemroot\\"
0x1800261c2  call    memcmp_0
0x1800261c7  test    eax, eax
0x1800261c9  jnz     short loc_180026206
0x1800261cb  lea     r9, [rbx+18h]
0x1800261cf  lea     r8, aSystemrootS; "%%SystemRoot%%\\%s"
0x1800261d6  mov     rdx, rdi; unsigned __int64
0x1800261d9  lea     rcx, [rsp+4B8h+Src]; unsigned __int16 *
0x1800261e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800261e6  test    eax, eax
0x1800261e8  jns     loc_18002627B
0x1800261ee  mov     ecx, eax
0x1800261f0  and     ecx, 1FFF0000h
0x1800261f6  cmp     ecx, 70000h
0x1800261fc  jnz     short loc_180026201
0x1800261fe  movzx   eax, ax
0x180026201  jmp     loc_18002640E
0x180026206  mov     r8d, 12h; Size
0x18002620c  lea     rdx, [rsp+4B8h+String]; Buf2
0x180026211  lea     rcx, aSystem32; "system32\\"
0x180026218  call    memcmp_0
0x18002621d  mov     rdx, rdi; unsigned __int64
0x180026220  lea     rcx, [rsp+4B8h+Src]; unsigned __int16 *
0x180026228  test    eax, eax
0x18002622a  jnz     short loc_180026257
0x18002622c  mov     r9, rbx
0x18002622f  lea     r8, aSystemrootS; "%%SystemRoot%%\\%s"
0x180026236  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002623b  test    eax, eax
0x18002623d  jns     short loc_18002627B
0x18002623f  mov     ecx, eax
0x180026241  and     ecx, 1FFF0000h
0x180026247  cmp     ecx, 70000h
0x18002624d  jnz     short loc_180026252
0x18002624f  movzx   eax, ax
0x180026252  jmp     loc_18002640E
0x180026257  mov     r8, rbx; unsigned __int16 *
0x18002625a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002625f  test    eax, eax
0x180026261  jns     short loc_18002627B
0x180026263  mov     ecx, eax
0x180026265  and     ecx, 1FFF0000h
0x18002626b  cmp     ecx, 70000h
0x180026271  jnz     short loc_180026276
0x180026273  movzx   eax, ax
0x180026276  jmp     loc_18002640E
0x18002627b  mov     r8, rsi; Size
0x18002627e  xor     edx, edx; Val
0x180026280  lea     rcx, [rsp+4B8h+String]; void *
0x180026285  call    memset_0
0x18002628a  mov     r8d, edi; nSize
0x18002628d  lea     rdx, [rsp+4B8h+String]; lpDst
0x180026292  lea     rcx, [rsp+4B8h+Src]; lpSrc
0x18002629a  call    cs:__imp_ExpandEnvironmentStringsW
0x1800262a0  test    eax, eax
0x1800262a2  jnz     short loc_1800262AF
0x1800262a4  call    cs:__imp_GetLastError
0x1800262aa  jmp     loc_18002640E
0x1800262af  cmp     eax, edi
0x1800262b1  jbe     short loc_1800262BD
0x1800262b3  mov     eax, 0Eh
0x1800262b8  jmp     loc_18002640E
0x1800262bd  xor     edx, edx; lpdwHandle
0x1800262bf  lea     rcx, [rsp+4B8h+String]; lptstrFilename
0x1800262c4  call    cs:__imp_GetFileVersionInfoSizeW
0x1800262ca  mov     ebx, eax
0x1800262cc  test    eax, eax
0x1800262ce  jnz     short loc_1800262DB
0x1800262d0  call    cs:__imp_GetLastError
0x1800262d6  jmp     loc_18002640E
0x1800262db  mov     rcx, rbx; unsigned __int64
0x1800262de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800262e3  mov     rdi, rax
0x1800262e6  mov     r8, rbx; Size
0x1800262e9  xor     edx, edx; Val
0x1800262eb  mov     rcx, rax; void *
0x1800262ee  call    memset_0
0x1800262f3  mov     [rsp+4B8h+var_460], rdi
0x1800262f8  mov     r9, rdi; lpData
0x1800262fb  mov     r8d, ebx; dwLen
0x1800262fe  xor     edx, edx; dwHandle
0x180026300  lea     rcx, [rsp+4B8h+String]; lptstrFilename
0x180026305  call    cs:__imp_GetFileVersionInfoW
0x18002630b  test    eax, eax
0x18002630d  jnz     short loc_180026328
0x18002630f  call    cs:__imp_GetLastError
0x180026315  mov     ebx, eax
0x180026317  lea     rcx, [rsp+4B8h+var_460]
0x18002631c  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180026321  mov     eax, ebx
0x180026323  jmp     loc_18002640E
0x180026328  lea     r9, [rsp+4B8h+puLen]; puLen
0x18002632d  lea     r8, [rsp+4B8h+lpBuffer]; lplpBuffer
0x180026332  lea     rdx, SubBlock; "\\"
0x180026339  mov     rcx, rdi; pBlock
0x18002633c  call    cs:__imp_VerQueryValueW
0x180026342  test    eax, eax
0x180026344  jnz     short loc_18002635F
0x180026346  call    cs:__imp_GetLastError
0x18002634c  mov     ebx, eax
0x18002634e  lea     rcx, [rsp+4B8h+var_460]
0x180026353  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180026358  mov     eax, ebx
0x18002635a  jmp     loc_18002640E
0x18002635f  mov     rcx, [rsp+4B8h+lpBuffer]
0x180026364  movzx   r8d, word ptr [rcx+0Ch]
0x180026369  movzx   r10d, word ptr [rcx+0Eh]
0x18002636e  movzx   eax, word ptr [rcx+8]
0x180026372  movzx   r9d, word ptr [rcx+0Ah]
0x180026377  mov     edx, [r14]; unsigned __int64
0x18002637a  mov     [rsp+4B8h+var_488], r8d
0x18002637f  mov     [rsp+4B8h+var_490], r10d
0x180026384  mov     [rsp+4B8h+var_498], eax
0x180026388  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18002638f  mov     rcx, r15; unsigned __int16 *
0x180026392  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026397  mov     ebx, eax
0x180026399  test    eax, eax
0x18002639b  jns     short loc_1800263BA
0x18002639d  and     eax, 1FFF0000h
0x1800263a2  cmp     eax, 70000h
0x1800263a7  jnz     short loc_1800263AC
0x1800263a9  movzx   ebx, bx
0x1800263ac  lea     rcx, [rsp+4B8h+var_460]
0x1800263b1  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800263b6  mov     eax, ebx
0x1800263b8  jmp     short loc_18002640E
0x1800263ba  lea     r8, [rsp+4B8h+var_478]; unsigned __int64 *
0x1800263bf  mov     rcx, r15; unsigned __int16 *
0x1800263c2  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800263c7  mov     ebx, eax
0x1800263c9  test    eax, eax
0x1800263cb  jns     short loc_1800263EA
0x1800263cd  and     eax, 1FFF0000h
0x1800263d2  cmp     eax, 70000h
0x1800263d7  jnz     short loc_1800263DC
0x1800263d9  movzx   ebx, bx
0x1800263dc  lea     rcx, [rsp+4B8h+var_460]
0x1800263e1  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800263e6  mov     eax, ebx
0x1800263e8  jmp     short loc_18002640E
0x1800263ea  mov     eax, dword ptr [rsp+4B8h+var_478]
0x1800263ee  add     eax, 2
0x1800263f1  mov     [r14], eax
0x1800263f4  lea     rcx, [rsp+4B8h+var_460]
0x1800263f9  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800263fe  xor     eax, eax
0x180026400  jmp     short loc_18002640E
0x180026402  mov     eax, 57h ; 'W'
0x180026407  jmp     short loc_18002640E
0x180026409  mov     eax, 0Eh
0x18002640e  mov     rcx, [rsp+4B8h+var_38]
0x180026416  xor     rcx, rsp; StackCookie
0x180026419  call    __security_check_cookie
0x18002641e  mov     rbx, [rsp+4B8h+arg_8]
0x180026426  add     rsp, 490h
0x18002642d  pop     r15
0x18002642f  pop     r14
0x180026431  pop     r12
0x180026433  pop     rdi
0x180026434  pop     rsi
0x180026435  retn
```
