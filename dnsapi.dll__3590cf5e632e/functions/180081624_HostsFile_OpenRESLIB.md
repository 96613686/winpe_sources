# HostsFile_OpenRESLIB

- ea: `0x180081624`
- end: `0x180081868`
- name: `HostsFile_OpenRESLIB`
- size: `580`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180001d00`
- `0x180081528`
- `0x180097860`

## callees

- `0x180064e58`
- `0x18006635c`
- `0x18006e12c`
- `0x180075cbc`
- `0x180081624`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800b5560`
- `0x1800c1038`
- `0x1800cafd4`
- `0x1800dc27c`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180081789`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180081789`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180081806`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180081806`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800816bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800816bd`

## string_xrefs

- `0x180081797`: `s:\windows\system32`
- `0x180081721`: `t:\windows\system32`

## pseudocode

```c
__int64 __fastcall HostsFile_OpenRESLIB(__int64 a1)
{
  const char *v2; // rdi
  int v3; // esi
  __m128 v4; // xmm0
  void *v5; // rcx
  const char *v6; // r8
  HANDLE FileA; // rax
  CHAR Buffer[288]; // [rsp+40h] [rbp-138h] BYREF

  memset_0(Buffer, 0, 0x11Du);
  v2 = *(const char **)(a1 + 8);
  v3 = 0;
  if ( (BYTE2(xmmword_1801119E0) & 4) != 0 )
    WPP_SF_(1042, 10, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids);
  *(_DWORD *)(a1 + 2304) = 1000;
  v4 = _mm_movelh_ps((__m128)(unsigned __int64)(a1 + 296), (__m128)(unsigned __int64)(a1 + 296));
  *(__m128 *)(a1 + 2312) = v4;
  *(__m128 *)(a1 + 2328) = v4;
  v5 = *(void **)a1;
  *(_DWORD *)(a1 + 2344) = 0;
  if ( v5 )
  {
    SetFilePointer(v5, 0, 0, 0);
    goto LABEL_28;
  }
  if ( !v2 || !strcmp_0("hosts", v2) )
  {
LABEL_9:
    if ( g_fVelocityDisableInternalExports && g_dwProductType == -1 )
      GetXboxProductType();
    if ( g_dwProductType == 194 )
    {
      v6 = "t:\\windows\\system32";
    }
    else
    {
      if ( !(unsigned int)Util_IsRunningOnXbox() )
      {
        if ( g_fVelocityDisableInternalExports && g_dwProductType == -1 )
          GetXboxProductType();
        if ( g_dwProductType != 192 )
        {
          GetSystemDirectoryA(Buffer, 0x104u);
LABEL_24:
          StringCchCatA(Buffer, 0x11Cu, "\\drivers\\etc\\hosts");
          if ( v3 )
            StringCchCatA(Buffer, 0x11Cu, ".ics");
          FileA = CreateFileA(Buffer, 0x80000000, 1u, 0, 3u, 0, 0);
          *(_QWORD *)a1 = FileA;
          if ( FileA == (HANDLE)-1LL )
            *(_QWORD *)a1 = 0;
          goto LABEL_28;
        }
      }
      v6 = "s:\\windows\\system32";
    }
    StringCchCopyA(Buffer, 0x104u, v6);
    goto LABEL_24;
  }
  if ( !strcmp_0("hosts.ics", v2) )
  {
    v3 = 1;
    goto LABEL_9;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_s(1035, 11, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids, v2);
LABEL_28:
  if ( *(_QWORD *)a1 )
  {
    hostsFileSniffBom(a1);
    return 1;
  }
  else
  {
    if ( !v3 )
      DNSETW_TRACE_HOST_FILE_ERROR();
    return 0;
  }
}

```

## disassembly

```asm
0x180081624  mov     [rsp+arg_8], rbx
0x180081629  mov     [rsp+arg_10], rsi
0x18008162e  push    rdi
0x18008162f  sub     rsp, 170h
0x180081636  mov     rax, cs:__security_cookie
0x18008163d  xor     rax, rsp
0x180081640  mov     [rsp+178h+var_18], rax
0x180081648  mov     rbx, rcx
0x18008164b  xor     edx, edx; Val
0x18008164d  lea     rcx, [rsp+178h+Buffer]; void *
0x180081652  mov     r8d, 11Dh; Size
0x180081658  call    memset_0
0x18008165d  mov     rdi, [rbx+8]
0x180081661  xor     esi, esi
0x180081663  test    byte ptr cs:xmmword_1801119E0+2, 4
0x18008166a  jz      short loc_180081680
0x18008166c  lea     edx, [rsi+0Ah]
0x18008166f  mov     ecx, 412h
0x180081674  lea     r8, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids
0x18008167b  call    WPP_SF_
0x180081680  mov     dword ptr [rbx+900h], 3E8h
0x18008168a  lea     rax, [rbx+128h]
0x180081691  movq    xmm0, rax
0x180081696  movlhps xmm0, xmm0
0x180081699  movups  xmmword ptr [rbx+908h], xmm0
0x1800816a0  movups  xmmword ptr [rbx+918h], xmm0
0x1800816a7  mov     rcx, [rbx]; hFile
0x1800816aa  mov     [rbx+928h], esi
0x1800816b0  test    rcx, rcx
0x1800816b3  jz      short loc_1800816CE
0x1800816b5  xor     r9d, r9d; dwMoveMethod
0x1800816b8  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800816bb  xor     edx, edx; lDistanceToMove
0x1800816bd  call    cs:__imp_SetFilePointer
0x1800816c4  nop     dword ptr [rax+rax+00h]
0x1800816c9  jmp     loc_180081822
0x1800816ce  test    rdi, rdi
0x1800816d1  jz      short loc_1800816FC
0x1800816d3  mov     rdx, rdi; Str2
0x1800816d6  lea     rcx, Str1; "hosts"
0x1800816dd  call    strcmp_0
0x1800816e2  test    eax, eax
0x1800816e4  jz      short loc_1800816FC
0x1800816e6  mov     rdx, rdi; Str2
0x1800816e9  lea     rcx, aHostsIcs; "hosts.ics"
0x1800816f0  call    strcmp_0
0x1800816f5  test    eax, eax
0x1800816f7  jnz     short loc_18008172A
0x1800816f9  lea     esi, [rax+1]
0x1800816fc  or      edi, 0FFFFFFFFh
0x1800816ff  cmp     cs:g_fVelocityDisableInternalExports, 0
0x180081706  jz      short loc_180081715
0x180081708  cmp     cs:g_dwProductType, edi
0x18008170e  jnz     short loc_180081715
0x180081710  call    GetXboxProductType
0x180081715  cmp     cs:g_dwProductType, 0C2h
0x18008171f  jnz     short loc_180081755
0x180081721  lea     r8, aTWindowsSystem; "t:\\windows\\system32"
0x180081728  jmp     short loc_18008179E
0x18008172a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180081731  jz      loc_180081822
0x180081737  mov     edx, 0Bh
0x18008173c  lea     r8, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids
0x180081743  mov     ecx, 40Bh
0x180081748  mov     r9, rdi
0x18008174b  call    WPP_SF_s
0x180081750  jmp     loc_180081822
0x180081755  call    Util_IsRunningOnXbox
0x18008175a  test    eax, eax
0x18008175c  jnz     short loc_180081797
0x18008175e  cmp     cs:g_fVelocityDisableInternalExports, eax
0x180081764  jz      short loc_180081773
0x180081766  cmp     cs:g_dwProductType, edi
0x18008176c  jnz     short loc_180081773
0x18008176e  call    GetXboxProductType
0x180081773  cmp     cs:g_dwProductType, 0C0h
0x18008177d  jz      short loc_180081797
0x18008177f  mov     edx, 104h; uSize
0x180081784  lea     rcx, [rsp+178h+Buffer]; lpBuffer
0x180081789  call    cs:__imp_GetSystemDirectoryA
0x180081790  nop     dword ptr [rax+rax+00h]
0x180081795  jmp     short loc_1800817AD
0x180081797  lea     r8, aSWindowsSystem; "s:\\windows\\system32"
0x18008179e  mov     edx, 104h; cchDest
0x1800817a3  lea     rcx, [rsp+178h+Buffer]; pszDest
0x1800817a8  call    StringCchCopyA
0x1800817ad  mov     edi, 11Ch
0x1800817b2  lea     r8, aDriversEtcHost; "\\drivers\\etc\\hosts"
0x1800817b9  mov     edx, edi; cchDest
0x1800817bb  lea     rcx, [rsp+178h+Buffer]; pszDest
0x1800817c0  call    StringCchCatA
0x1800817c5  test    esi, esi
0x1800817c7  jz      short loc_1800817DC
0x1800817c9  lea     r8, aIcs; ".ics"
0x1800817d0  mov     edx, edi; cchDest
0x1800817d2  lea     rcx, [rsp+178h+Buffer]; pszDest
0x1800817d7  call    StringCchCatA
0x1800817dc  xor     r9d, r9d; lpSecurityAttributes
0x1800817df  mov     [rsp+178h+hTemplateFile], 0; hTemplateFile
0x1800817e8  mov     [rsp+178h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800817f0  lea     rcx, [rsp+178h+Buffer]; lpFileName
0x1800817f5  mov     edx, 80000000h; dwDesiredAccess
0x1800817fa  mov     [rsp+178h+dwCreationDisposition], 3; dwCreationDisposition
0x180081802  lea     r8d, [r9+1]; dwShareMode
0x180081806  call    cs:__imp_CreateFileA
0x18008180d  nop     dword ptr [rax+rax+00h]
0x180081812  mov     [rbx], rax
0x180081815  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180081819  jnz     short loc_180081822
0x18008181b  mov     qword ptr [rbx], 0
0x180081822  cmp     qword ptr [rbx], 0
0x180081826  jz      short loc_180081837
0x180081828  mov     rcx, rbx
0x18008182b  call    hostsFileSniffBom
0x180081830  mov     eax, 1
0x180081835  jmp     short loc_180081842
0x180081837  test    esi, esi
0x180081839  jnz     short loc_180081840
0x18008183b  call    DNSETW_TRACE_HOST_FILE_ERROR
0x180081840  xor     eax, eax
0x180081842  mov     rcx, [rsp+178h+var_18]
0x18008184a  xor     rcx, rsp; StackCookie
0x18008184d  call    __security_check_cookie
0x180081852  lea     r11, [rsp+178h+var_8]
0x18008185a  mov     rbx, [r11+18h]
0x18008185e  mov     rsi, [r11+20h]
0x180081862  mov     rsp, r11
0x180081865  pop     rdi
0x180081866  retn
```
