# HostsFile_OpenRESLIB

- ea: `0x18003cac0`
- end: `0x18003ccbd`
- name: `HostsFile_OpenRESLIB`
- size: `509`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18001490c`
- `0x18003c9d0`

## callees

- `0x18003cac0`
- `0x18003ccc4`
- `0x18003db54`
- `0x180046ec0`
- `0x180047818`
- `0x18005cc00`
- `0x18005ccd8`
- `0x18005cd58`
- `0x18005ecb8`
- `0x18005ecf4`
- `0x1800794f4`
- `0x1800865fc`
- `0x180086700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003cc62`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003cc62`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003cb59`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003cb59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18003cbeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x18003cbeb`

## string_xrefs

- `0x18003cb9b`: `t:\windows\system32`
- `0x18003cbf3`: `s:\windows\system32`

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
  if ( (BYTE2(xmmword_1800AB5A0) & 4) != 0 )
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
    goto LABEL_22;
  }
  if ( !v2 || !strcmp_0("hosts", v2) )
  {
LABEL_9:
    if ( (unsigned int)Util_IsRunningOnXboxGameOS() )
    {
      v6 = "t:\\windows\\system32";
    }
    else
    {
      if ( !(unsigned int)Util_IsRunningOnXbox() && !(unsigned int)Util_IsRunningOnXboxSystemOS() )
      {
        GetSystemDirectoryA(Buffer, 0x104u);
LABEL_18:
        StringCchCatA(Buffer, 0x11Cu, "\\drivers\\etc\\hosts");
        if ( v3 )
          StringCchCatA(Buffer, 0x11Cu, ".ics");
        FileA = CreateFileA(Buffer, 0x80000000, 1u, 0, 3u, 0, 0);
        *(_QWORD *)a1 = FileA;
        if ( FileA == (HANDLE)-1LL )
          *(_QWORD *)a1 = 0;
        goto LABEL_22;
      }
      v6 = "s:\\windows\\system32";
    }
    StringCchCopyA(Buffer, 0x104u, v6);
    goto LABEL_18;
  }
  if ( !strcmp_0("hosts.ics", v2) )
  {
    v3 = 1;
    goto LABEL_9;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_s(1035, 11, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids, v2);
LABEL_22:
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
0x18003cac0  mov     [rsp+arg_8], rbx
0x18003cac5  mov     [rsp+arg_10], rsi
0x18003caca  push    rdi
0x18003cacb  sub     rsp, 170h
0x18003cad2  mov     rax, cs:__security_cookie
0x18003cad9  xor     rax, rsp
0x18003cadc  mov     [rsp+178h+var_18], rax
0x18003cae4  mov     rbx, rcx
0x18003cae7  xor     edx, edx; Val
0x18003cae9  lea     rcx, [rsp+178h+Buffer]; void *
0x18003caee  mov     r8d, 11Dh; Size
0x18003caf4  call    memset_0
0x18003caf9  mov     rdi, [rbx+8]
0x18003cafd  xor     esi, esi
0x18003caff  test    byte ptr cs:xmmword_1800AB5A0+2, 4
0x18003cb06  jz      short loc_18003CB1C
0x18003cb08  lea     edx, [rsi+0Ah]
0x18003cb0b  mov     ecx, 412h
0x18003cb10  lea     r8, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids
0x18003cb17  call    WPP_SF_
0x18003cb1c  mov     dword ptr [rbx+900h], 3E8h
0x18003cb26  lea     rax, [rbx+128h]
0x18003cb2d  movq    xmm0, rax
0x18003cb32  movlhps xmm0, xmm0
0x18003cb35  movups  xmmword ptr [rbx+908h], xmm0
0x18003cb3c  movups  xmmword ptr [rbx+918h], xmm0
0x18003cb43  mov     rcx, [rbx]; hFile
0x18003cb46  mov     [rbx+928h], esi
0x18003cb4c  test    rcx, rcx
0x18003cb4f  jz      short loc_18003CB64
0x18003cb51  xor     r9d, r9d; dwMoveMethod
0x18003cb54  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003cb57  xor     edx, edx; lDistanceToMove
0x18003cb59  call    cs:__imp_SetFilePointer
0x18003cb5f  jmp     loc_18003CC78
0x18003cb64  test    rdi, rdi
0x18003cb67  jz      short loc_18003CB92
0x18003cb69  mov     rdx, rdi; Str2
0x18003cb6c  lea     rcx, Str1; "hosts"
0x18003cb73  call    strcmp_0
0x18003cb78  test    eax, eax
0x18003cb7a  jz      short loc_18003CB92
0x18003cb7c  mov     rdx, rdi; Str2
0x18003cb7f  lea     rcx, aHostsIcs; "hosts.ics"
0x18003cb86  call    strcmp_0
0x18003cb8b  test    eax, eax
0x18003cb8d  jnz     short loc_18003CBA4
0x18003cb8f  lea     esi, [rax+1]
0x18003cb92  call    Util_IsRunningOnXboxGameOS
0x18003cb97  test    eax, eax
0x18003cb99  jz      short loc_18003CBCF
0x18003cb9b  lea     r8, aTWindowsSystem; "t:\\windows\\system32"
0x18003cba2  jmp     short loc_18003CBFA
0x18003cba4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003cbab  jz      loc_18003CC78
0x18003cbb1  mov     edx, 0Bh
0x18003cbb6  lea     r8, WPP_0f3365124f1337a30f25cbd03c60c357_Traceguids
0x18003cbbd  mov     ecx, 40Bh
0x18003cbc2  mov     r9, rdi
0x18003cbc5  call    WPP_SF_s
0x18003cbca  jmp     loc_18003CC78
0x18003cbcf  call    Util_IsRunningOnXbox
0x18003cbd4  test    eax, eax
0x18003cbd6  jnz     short loc_18003CBF3
0x18003cbd8  call    Util_IsRunningOnXboxSystemOS
0x18003cbdd  test    eax, eax
0x18003cbdf  jnz     short loc_18003CBF3
0x18003cbe1  mov     edx, 104h; uSize
0x18003cbe6  lea     rcx, [rsp+178h+Buffer]; lpBuffer
0x18003cbeb  call    cs:__imp_GetSystemDirectoryA
0x18003cbf1  jmp     short loc_18003CC09
0x18003cbf3  lea     r8, aSWindowsSystem_0; "s:\\windows\\system32"
0x18003cbfa  mov     edx, 104h; cchDest
0x18003cbff  lea     rcx, [rsp+178h+Buffer]; pszDest
0x18003cc04  call    StringCchCopyA
0x18003cc09  mov     edi, 11Ch
0x18003cc0e  lea     r8, aDriversEtcHost; "\\drivers\\etc\\hosts"
0x18003cc15  mov     edx, edi; cchDest
0x18003cc17  lea     rcx, [rsp+178h+Buffer]; pszDest
0x18003cc1c  call    StringCchCatA
0x18003cc21  test    esi, esi
0x18003cc23  jz      short loc_18003CC38
0x18003cc25  lea     r8, aIcs; ".ics"
0x18003cc2c  mov     edx, edi; cchDest
0x18003cc2e  lea     rcx, [rsp+178h+Buffer]; pszDest
0x18003cc33  call    StringCchCatA
0x18003cc38  xor     r9d, r9d; lpSecurityAttributes
0x18003cc3b  mov     [rsp+178h+hTemplateFile], 0; hTemplateFile
0x18003cc44  mov     [rsp+178h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18003cc4c  lea     rcx, [rsp+178h+Buffer]; lpFileName
0x18003cc51  mov     edx, 80000000h; dwDesiredAccess
0x18003cc56  mov     [rsp+178h+dwCreationDisposition], 3; dwCreationDisposition
0x18003cc5e  lea     r8d, [r9+1]; dwShareMode
0x18003cc62  call    cs:__imp_CreateFileA
0x18003cc68  mov     [rbx], rax
0x18003cc6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003cc6f  jnz     short loc_18003CC78
0x18003cc71  mov     qword ptr [rbx], 0
0x18003cc78  cmp     qword ptr [rbx], 0
0x18003cc7c  jz      short loc_18003CC8D
0x18003cc7e  mov     rcx, rbx
0x18003cc81  call    hostsFileSniffBom
0x18003cc86  mov     eax, 1
0x18003cc8b  jmp     short loc_18003CC98
0x18003cc8d  test    esi, esi
0x18003cc8f  jnz     short loc_18003CC96
0x18003cc91  call    DNSETW_TRACE_HOST_FILE_ERROR
0x18003cc96  xor     eax, eax
0x18003cc98  mov     rcx, [rsp+178h+var_18]
0x18003cca0  xor     rcx, rsp; StackCookie
0x18003cca3  call    __security_check_cookie
0x18003cca8  lea     r11, [rsp+178h+var_8]
0x18003ccb0  mov     rbx, [r11+18h]
0x18003ccb4  mov     rsi, [r11+20h]
0x18003ccb8  mov     rsp, r11
0x18003ccbb  pop     rdi
0x18003ccbc  retn
```
