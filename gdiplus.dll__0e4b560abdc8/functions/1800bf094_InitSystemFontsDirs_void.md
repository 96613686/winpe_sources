# InitSystemFontsDirs(void)

- ea: `0x1800bf094`
- end: `0x1800bf24f`
- name: `?InitSystemFontsDirs@@YAHXZ`
- size: `443`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e2458`

## callees

- `0x18001f950`
- `0x1800bf094`
- `0x1800e5044`
- `0x1800e9380`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800bf19c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800bf1e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800bf19c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800bf1e8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800bf0d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800bf0d0`

## pseudocode

```c
__int64 InitSystemFontsDirs(void)
{
  UINT SystemDirectoryW; // ebx
  UINT v1; // ecx
  __int64 i; // rax
  __int64 v3; // rax
  const WCHAR *v4; // rdi
  size_t v5; // rbx
  int v6; // eax
  int cbMultiByte; // ebx
  char *lpMultiByteStr; // rax
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( Globals::FontsDirW )
    return 1;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( SystemDirectoryW - 1 <= 0x103 )
  {
    v1 = SystemDirectoryW - 1;
    for ( i = (int)(SystemDirectoryW - 1); i >= 0; --i )
    {
      if ( Buffer[i] == 92 )
      {
        SystemDirectoryW = v1;
        break;
      }
      --v1;
    }
    if ( SystemDirectoryW )
    {
      v3 = 2LL * (SystemDirectoryW + 7);
      if ( !is_mul_ok(SystemDirectoryW + 7, 2u) )
        v3 = -1;
      Globals::FontsDirW = (LPCWSTR)GpMallocEx(v3, 0);
      v4 = Globals::FontsDirW;
      if ( Globals::FontsDirW )
      {
        v5 = SystemDirectoryW;
        memcpy_0((void *)Globals::FontsDirW, Buffer, v5 * 2);
        *(_QWORD *)&v4[v5] = 0x6E006F0066005CLL;
        *(_DWORD *)&v4[v5 + 4] = 7536756;
        v4[v5 + 6] = 0;
        v6 = WideCharToMultiByte(0, 0, v4, -1, 0, 0, 0, 0);
        cbMultiByte = v6;
        if ( v6 )
        {
          lpMultiByteStr = (char *)GpMallocEx(v6, 0);
          Globals::FontsDirA = lpMultiByteStr;
          if ( lpMultiByteStr )
          {
            if ( WideCharToMultiByte(0, 0, Globals::FontsDirW, -1, lpMultiByteStr, cbMultiByte, 0, 0) == cbMultiByte )
              return 1;
          }
        }
        GpFree(Globals::FontsDirW);
        Globals::FontsDirW = 0;
        GpFree(Globals::FontsDirA);
        Globals::FontsDirA = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800bf094  mov     [rsp+arg_0], rbx
0x1800bf099  mov     [rsp+arg_8], rbp
0x1800bf09e  push    rdi
0x1800bf09f  sub     rsp, 260h
0x1800bf0a6  mov     rax, cs:__security_cookie
0x1800bf0ad  xor     rax, rsp
0x1800bf0b0  mov     [rsp+268h+var_18], rax
0x1800bf0b8  cmp     cs:?FontsDirW@Globals@@3PEAGEA, 0; ushort * Globals::FontsDirW
0x1800bf0c0  jnz     loc_1800BF1F8
0x1800bf0c6  mov     edx, 105h; uSize
0x1800bf0cb  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x1800bf0d0  call    cs:__imp_GetSystemDirectoryW
0x1800bf0d7  nop     dword ptr [rax+rax+00h]
0x1800bf0dc  mov     ebx, eax
0x1800bf0de  dec     eax
0x1800bf0e0  cmp     eax, 103h
0x1800bf0e5  ja      loc_1800BF24B
0x1800bf0eb  lea     ecx, [rbx-1]
0x1800bf0ee  movsxd  rax, ecx
0x1800bf0f1  test    rax, rax
0x1800bf0f4  js      short loc_1800BF107
0x1800bf0f6  cmp     [rsp+rax*2+268h+Buffer], 5Ch ; '\'
0x1800bf0fc  jz      short loc_1800BF105
0x1800bf0fe  dec     ecx
0x1800bf100  dec     rax
0x1800bf103  jmp     short loc_1800BF0F1
0x1800bf105  mov     ebx, ecx
0x1800bf107  test    ebx, ebx
0x1800bf109  jz      loc_1800BF24B
0x1800bf10f  lea     ecx, [rbx+7]
0x1800bf112  mov     eax, 2
0x1800bf117  mul     rcx
0x1800bf11a  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800bf121  cmovo   rax, rbp
0x1800bf125  xor     edx, edx
0x1800bf127  mov     rcx, rax
0x1800bf12a  call    GpMallocEx
0x1800bf12f  mov     cs:?FontsDirW@Globals@@3PEAGEA, rax; ushort * Globals::FontsDirW
0x1800bf136  mov     rdi, rax
0x1800bf139  test    rax, rax
0x1800bf13c  jz      loc_1800BF24B
0x1800bf142  mov     eax, ebx
0x1800bf144  lea     rdx, [rsp+268h+Buffer]; Src
0x1800bf149  mov     rcx, rdi; void *
0x1800bf14c  lea     rbx, [rax+rax]
0x1800bf150  mov     r8, rbx; Size
0x1800bf153  call    memcpy_0
0x1800bf158  movsd   xmm0, cs:qword_1801887C0
0x1800bf160  mov     r9d, ebp; cchWideChar
0x1800bf163  and     [rsp+268h+var_230], 0
0x1800bf169  mov     r8, rdi; lpWideCharStr
0x1800bf16c  and     [rsp+268h+var_238], 0
0x1800bf172  xor     edx, edx; dwFlags
0x1800bf174  and     [rsp+268h+cbMultiByte], 0
0x1800bf179  xor     ecx, ecx; CodePage
0x1800bf17b  and     [rsp+268h+lpMultiByteStr], 0
0x1800bf181  movsd   qword ptr [rbx+rdi], xmm0
0x1800bf186  mov     eax, cs:dword_1801887C8
0x1800bf18c  mov     [rbx+rdi+8], eax
0x1800bf190  movzx   eax, cs:word_1801887CC
0x1800bf197  mov     [rbx+rdi+0Ch], ax
0x1800bf19c  call    cs:__imp_WideCharToMultiByte
0x1800bf1a3  nop     dword ptr [rax+rax+00h]
0x1800bf1a8  movsxd  rbx, eax
0x1800bf1ab  test    eax, eax
0x1800bf1ad  jz      short loc_1800BF223
0x1800bf1af  mov     rcx, rbx
0x1800bf1b2  xor     edx, edx
0x1800bf1b4  call    GpMallocEx
0x1800bf1b9  mov     cs:?FontsDirA@Globals@@3PEADEA, rax; char * Globals::FontsDirA
0x1800bf1c0  test    rax, rax
0x1800bf1c3  jz      short loc_1800BF223
0x1800bf1c5  and     [rsp+268h+var_230], 0
0x1800bf1cb  mov     r9d, ebp; cchWideChar
0x1800bf1ce  and     [rsp+268h+var_238], 0
0x1800bf1d4  xor     edx, edx; dwFlags
0x1800bf1d6  mov     r8, cs:?FontsDirW@Globals@@3PEAGEA; lpWideCharStr
0x1800bf1dd  xor     ecx, ecx; CodePage
0x1800bf1df  mov     [rsp+268h+cbMultiByte], ebx; cbMultiByte
0x1800bf1e3  mov     [rsp+268h+lpMultiByteStr], rax; lpMultiByteStr
0x1800bf1e8  call    cs:__imp_WideCharToMultiByte
0x1800bf1ef  nop     dword ptr [rax+rax+00h]
0x1800bf1f4  cmp     eax, ebx
0x1800bf1f6  jnz     short loc_1800BF223
0x1800bf1f8  mov     eax, 1
0x1800bf1fd  mov     rcx, [rsp+268h+var_18]
0x1800bf205  xor     rcx, rsp; StackCookie
0x1800bf208  call    __security_check_cookie
0x1800bf20d  lea     r11, [rsp+268h+var_8]
0x1800bf215  mov     rbx, [r11+10h]
0x1800bf219  mov     rbp, [r11+18h]
0x1800bf21d  mov     rsp, r11
0x1800bf220  pop     rdi
0x1800bf221  retn
0x1800bf223  mov     rcx, cs:?FontsDirW@Globals@@3PEAGEA; ushort * Globals::FontsDirW
0x1800bf22a  call    GpFree
0x1800bf22f  mov     rcx, cs:?FontsDirA@Globals@@3PEADEA; char * Globals::FontsDirA
0x1800bf236  and     cs:?FontsDirW@Globals@@3PEAGEA, 0; ushort * Globals::FontsDirW
0x1800bf23e  call    GpFree
0x1800bf243  and     cs:?FontsDirA@Globals@@3PEADEA, 0; char * Globals::FontsDirA
0x1800bf24b  xor     eax, eax
0x1800bf24d  jmp     short loc_1800BF1FD
```
