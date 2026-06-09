# IsInInfDir

- ea: `0x180035ef8`
- end: `0x18003607a`
- name: `IsInInfDir`
- size: `386`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800113c0`
- `0x18001de14`
- `0x180026820`
- `0x180027414`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x18000d7e0`
- `0x180035ef8`
- `0x1800363c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180035f4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180035f4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036039`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036039`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036052`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036052`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003600a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18003600a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180035fad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180035fad`

## pseudocode

```c
__int64 __fastcall IsInInfDir(__int64 a1)
{
  const wchar_t *v2; // rax
  wchar_t *v3; // rdi
  wchar_t v4; // ax
  wchar_t *v5; // rcx
  unsigned int valid; // ebx
  UINT SystemWindowsDirectoryW; // eax
  __int64 v8; // r8
  WCHAR Buffer[264]; // [rsp+20h] [rbp-458h] BYREF
  WCHAR v11[264]; // [rsp+230h] [rbp-248h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v11, 0, 0x208u);
  if ( a1 )
  {
    v2 = (const wchar_t *)_o__wcsdup(a1);
    v3 = (wchar_t *)v2;
    if ( v2 )
    {
      if ( wcschr(v2, 0x2Fu) )
      {
        v4 = *v3;
        if ( *v3 )
        {
          v5 = v3;
          do
          {
            if ( v4 == 47 )
              *v5 = 92;
            v4 = *++v5;
          }
          while ( *v5 );
        }
      }
    }
    valid = IsValidInfPath(v3);
    if ( valid )
    {
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
      if ( SystemWindowsDirectoryW - 1 <= 0x102
        && (Buffer[SystemWindowsDirectoryW - 1] == 92 || StringCchCatW(Buffer, 0x104u, L"\\") >= 0)
        && StringCchCatW(Buffer, 0x104u, L"INF\\") >= 0
        && GetFullPathNameW(v3, 0x104u, v11, 0) - 1 <= 0x102 )
      {
        v8 = -1;
        do
          ++v8;
        while ( Buffer[v8] );
        valid = _o__wcsnicmp(Buffer, v11) == 0;
      }
      else
      {
        valid = 0;
      }
    }
    if ( v3 )
      free(v3);
  }
  else
  {
    return 0;
  }
  return valid;
}

```

## disassembly

```asm
0x180035ef8  push    rbx
0x180035efa  push    rbp
0x180035efb  push    rsi
0x180035efc  push    rdi
0x180035efd  sub     rsp, 458h
0x180035f04  mov     rax, cs:__security_cookie
0x180035f0b  xor     rax, rsp
0x180035f0e  mov     [rsp+478h+var_38], rax
0x180035f16  mov     rbx, rcx
0x180035f19  mov     edi, 208h
0x180035f1e  mov     r8d, edi; Size
0x180035f21  lea     rcx, [rsp+478h+Buffer]; void *
0x180035f26  xor     edx, edx; Val
0x180035f28  call    memset_0
0x180035f2d  mov     r8d, edi; Size
0x180035f30  lea     rcx, [rsp+478h+var_248]; void *
0x180035f38  xor     edx, edx; Val
0x180035f3a  call    memset_0
0x180035f3f  xor     esi, esi
0x180035f41  test    rbx, rbx
0x180035f44  jz      loc_18003605A
0x180035f4a  mov     rcx, rbx
0x180035f4d  call    cs:__imp__o__wcsdup
0x180035f53  lea     ebp, [rsi+5Ch]
0x180035f56  mov     rdi, rax
0x180035f59  test    rax, rax
0x180035f5c  jz      short loc_180035F8F
0x180035f5e  lea     ebx, [rsi+2Fh]
0x180035f61  mov     rcx, rax; Str
0x180035f64  mov     edx, ebx; Ch
0x180035f66  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180035f6b  test    rax, rax
0x180035f6e  jz      short loc_180035F8F
0x180035f70  movzx   eax, word ptr [rdi]
0x180035f73  test    ax, ax
0x180035f76  jz      short loc_180035F8F
0x180035f78  mov     rcx, rdi
0x180035f7b  cmp     ax, bx
0x180035f7e  jnz     short loc_180035F83
0x180035f80  mov     [rcx], bp
0x180035f83  add     rcx, 2
0x180035f87  movzx   eax, word ptr [rcx]
0x180035f8a  test    ax, ax
0x180035f8d  jnz     short loc_180035F7B
0x180035f8f  mov     rcx, rdi; Str
0x180035f92  call    IsValidInfPath
0x180035f97  mov     ebx, eax
0x180035f99  test    eax, eax
0x180035f9b  jz      loc_18003604A
0x180035fa1  mov     ebx, 104h
0x180035fa6  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x180035fab  mov     edx, ebx; uSize
0x180035fad  call    cs:__imp_GetSystemWindowsDirectoryW
0x180035fb3  lea     ecx, [rax-1]
0x180035fb6  cmp     ecx, 102h
0x180035fbc  ja      loc_180036048
0x180035fc2  dec     eax
0x180035fc4  cmp     [rsp+rax*2+478h+Buffer], bp
0x180035fc9  jz      short loc_180035FE2
0x180035fcb  lea     r8, SubBlock; "\\"
0x180035fd2  mov     edx, ebx; unsigned __int64
0x180035fd4  lea     rcx, [rsp+478h+Buffer]; unsigned __int16 *
0x180035fd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035fde  test    eax, eax
0x180035fe0  js      short loc_180036048
0x180035fe2  lea     r8, aInf_0; "INF\\"
0x180035fe9  mov     rdx, rbx; unsigned __int64
0x180035fec  lea     rcx, [rsp+478h+Buffer]; unsigned __int16 *
0x180035ff1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035ff6  test    eax, eax
0x180035ff8  js      short loc_180036048
0x180035ffa  xor     r9d, r9d; lpFilePart
0x180035ffd  lea     r8, [rsp+478h+var_248]; lpBuffer
0x180036005  mov     edx, ebx; nBufferLength
0x180036007  mov     rcx, rdi; lpFileName
0x18003600a  call    cs:__imp_GetFullPathNameW
0x180036010  dec     eax
0x180036012  cmp     eax, 102h
0x180036017  ja      short loc_180036048
0x180036019  lea     rax, [rsp+478h+Buffer]
0x18003601e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180036022  inc     r8
0x180036025  cmp     [rax+r8*2], si
0x18003602a  jnz     short loc_180036022
0x18003602c  lea     rdx, [rsp+478h+var_248]
0x180036034  lea     rcx, [rsp+478h+Buffer]
0x180036039  call    cs:__imp__o__wcsnicmp
0x18003603f  test    eax, eax
0x180036041  mov     ebx, esi
0x180036043  setz    bl
0x180036046  jmp     short loc_18003604A
0x180036048  mov     ebx, esi
0x18003604a  test    rdi, rdi
0x18003604d  jz      short loc_18003605C
0x18003604f  mov     rcx, rdi; Block
0x180036052  call    cs:__imp_free
0x180036058  jmp     short loc_18003605C
0x18003605a  mov     ebx, esi
0x18003605c  mov     eax, ebx
0x18003605e  mov     rcx, [rsp+478h+var_38]
0x180036066  xor     rcx, rsp; StackCookie
0x180036069  call    __security_check_cookie
0x18003606e  add     rsp, 458h
0x180036075  pop     rdi
0x180036076  pop     rsi
0x180036077  pop     rbp
0x180036078  pop     rbx
0x180036079  retn
```
