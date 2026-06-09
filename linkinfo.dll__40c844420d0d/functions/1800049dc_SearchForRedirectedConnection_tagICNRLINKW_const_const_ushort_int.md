# SearchForRedirectedConnection(tagICNRLINKW const * const,ushort *,int)

- ea: `0x1800049dc`
- end: `0x180004b47`
- name: `?SearchForRedirectedConnection@@YAHQEBUtagICNRLINKW@@PEAGH@Z`
- size: `363`
- prototype: `int(const struct tagICNRLINKW *const, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800044f0`

## callees

- `0x180001ae0`
- `0x1800044cc`
- `0x1800049dc`
- `0x180005721`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004aa7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004aa7`
- `MPR!WNetCloseEnum` at `0x180004b11`
- `MPR!WNetCloseEnum` at `0x180004b11`
- `MPR!WNetEnumResourceW` at `0x180004adf`
- `MPR!WNetEnumResourceW` at `0x180004adf`
- `MPR!WNetOpenEnumW` at `0x180004a2d`
- `MPR!WNetOpenEnumW` at `0x180004a2d`

## pseudocode

```c
__int64 __fastcall SearchForRedirectedConnection(const struct tagICNRLINKW *const a1, unsigned __int16 *a2)
{
  unsigned int v2; // esi
  __int64 v5; // rdx
  const CHAR *v6; // r8
  WCHAR *v7; // rbx
  DWORD BufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cCount; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE hEnum; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE Buffer[16]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  WCHAR WideCharStr[264]; // [rsp+250h] [rbp+150h] BYREF

  v2 = 0;
  hEnum = 0;
  if ( !WNetOpenEnumW(1u, 1u, 0x12u, 0, &hEnum) )
  {
    cCount = 1;
    memset_0(Buffer, 0, 0x208u);
    BufferSize = 520;
    while ( !WNetEnumResourceW(hEnum, &cCount, Buffer, &BufferSize) )
    {
      v5 = v14;
      if ( v14 && v13 )
      {
        v6 = (char *)a1 + *((unsigned int *)a1 + 2);
        if ( v6 == (char *)a1 + 20 )
        {
          v7 = WideCharStr;
          MultiByteToWideChar(0, 0, v6, -1, WideCharStr, 260);
          v5 = v14;
        }
        else
        {
          v7 = (WCHAR *)((char *)a1 + *((unsigned int *)a1 + 5));
        }
        if ( !(unsigned int)CompareNetNames(v7, v5) )
        {
          StringCchCopyW(a2, 0x104u, v13);
          v2 = 1;
          break;
        }
      }
    }
    WNetCloseEnum(hEnum);
  }
  return v2;
}

```

## disassembly

```asm
0x1800049dc  mov     [rsp-8+arg_10], rbx
0x1800049e1  mov     [rsp-8+arg_18], rsi
0x1800049e6  push    rbp
0x1800049e7  push    rdi
0x1800049e8  push    r14
0x1800049ea  lea     rbp, [rsp-370h]
0x1800049f2  sub     rsp, 470h
0x1800049f9  mov     rax, cs:__security_cookie
0x180004a00  xor     rax, rsp
0x180004a03  mov     [rbp+380h+var_20], rax
0x180004a0a  xor     esi, esi
0x180004a0c  lea     rax, [rsp+480h+hEnum]
0x180004a11  mov     r14, rdx
0x180004a14  mov     [rsp+480h+hEnum], rsi
0x180004a19  mov     rdi, rcx
0x180004a1c  mov     [rsp+480h+lphEnum], rax; lphEnum
0x180004a21  xor     r9d, r9d; lpNetResource
0x180004a24  lea     edx, [rsi+1]; dwType
0x180004a27  mov     ecx, edx; dwScope
0x180004a29  lea     r8d, [rsi+12h]; dwUsage
0x180004a2d  call    cs:__imp_WNetOpenEnumW
0x180004a34  nop     dword ptr [rax+rax+00h]
0x180004a39  test    eax, eax
0x180004a3b  jnz     loc_180004B1D
0x180004a41  mov     ebx, 208h
0x180004a46  mov     [rsp+480h+cCount], 1
0x180004a4e  mov     r8d, ebx; Size
0x180004a51  lea     rcx, [rsp+480h+Buffer]; void *
0x180004a56  xor     edx, edx; Val
0x180004a58  call    memset_0
0x180004a5d  mov     [rsp+480h+BufferSize], ebx
0x180004a61  jmp     short loc_180004ACB
0x180004a63  mov     rdx, [rsp+480h+var_428]
0x180004a68  test    rdx, rdx
0x180004a6b  jz      short loc_180004ACB
0x180004a6d  cmp     [rsp+480h+var_430], rsi
0x180004a72  jz      short loc_180004ACB
0x180004a74  mov     r8d, [rdi+8]
0x180004a78  lea     rax, [rdi+14h]
0x180004a7c  add     r8, rdi; lpMultiByteStr
0x180004a7f  cmp     r8, rax
0x180004a82  jnz     short loc_180004ABA
0x180004a84  lea     rax, [rbp+380h+WideCharStr]
0x180004a8b  mov     [rsp+480h+cchWideChar], 104h; cchWideChar
0x180004a93  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004a97  mov     [rsp+480h+lphEnum], rax; lpWideCharStr
0x180004a9c  xor     edx, edx; dwFlags
0x180004a9e  lea     rbx, [rbp+380h+WideCharStr]
0x180004aa5  xor     ecx, ecx; CodePage
0x180004aa7  call    cs:__imp_MultiByteToWideChar
0x180004aae  nop     dword ptr [rax+rax+00h]
0x180004ab3  mov     rdx, [rsp+480h+var_428]
0x180004ab8  jmp     short loc_180004ABF
0x180004aba  mov     ebx, [rax]
0x180004abc  add     rbx, rdi
0x180004abf  mov     rcx, rbx
0x180004ac2  call    ?CompareNetNames@@YA?AW4_comparisonresult@@PEBG0@Z; CompareNetNames(ushort const *,ushort const *)
0x180004ac7  test    eax, eax
0x180004ac9  jz      short loc_180004AF5
0x180004acb  mov     rcx, [rsp+480h+hEnum]; hEnum
0x180004ad0  lea     r9, [rsp+480h+BufferSize]; lpBufferSize
0x180004ad5  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x180004ada  lea     rdx, [rsp+480h+cCount]; lpcCount
0x180004adf  call    cs:__imp_WNetEnumResourceW
0x180004ae6  nop     dword ptr [rax+rax+00h]
0x180004aeb  test    eax, eax
0x180004aed  jz      loc_180004A63
0x180004af3  jmp     short loc_180004B0C
0x180004af5  mov     r8, [rsp+480h+var_430]; unsigned __int16 *
0x180004afa  mov     edx, 104h; unsigned __int64
0x180004aff  mov     rcx, r14; unsigned __int16 *
0x180004b02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b07  mov     esi, 1
0x180004b0c  mov     rcx, [rsp+480h+hEnum]; hEnum
0x180004b11  call    cs:__imp_WNetCloseEnum
0x180004b18  nop     dword ptr [rax+rax+00h]
0x180004b1d  mov     eax, esi
0x180004b1f  mov     rcx, [rbp+380h+var_20]
0x180004b26  xor     rcx, rsp; StackCookie
0x180004b29  call    __security_check_cookie
0x180004b2e  lea     r11, [rsp+480h+var_10]
0x180004b36  mov     rbx, [r11+30h]
0x180004b3a  mov     rsi, [r11+38h]
0x180004b3e  mov     rsp, r11
0x180004b41  pop     r14
0x180004b43  pop     rdi
0x180004b44  pop     rbp
0x180004b45  retn
```
