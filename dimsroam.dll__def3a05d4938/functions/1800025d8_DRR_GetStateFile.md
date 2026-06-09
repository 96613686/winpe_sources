# DRR_GetStateFile

- ea: `0x1800025d8`
- end: `0x1800027d0`
- name: `DRR_GetStateFile`
- size: `504`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003300`

## callees

- `0x1800025d8`
- `0x1800035cc`
- `0x1800035f4`
- `0x18000d892`
- `0x18000d8d0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000267a`
- `msvcrt!wcscat_s` at `0x18000267a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800026a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002621`
- `USERENV!GetUserProfileDirectoryW` at `0x180002615`
- `USERENV!GetUserProfileDirectoryW` at `0x180002615`

## pseudocode

```c
__int64 DRR_GetStateFile()
{
  DWORD LastError; // edi
  __int64 v1; // rbx
  size_t v2; // rbx
  char *v3; // rdx
  DWORD cchSize[4]; // [rsp+20h] [rbp-238h] BYREF
  wchar_t ProfileDir[264]; // [rsp+30h] [rbp-228h] BYREF

  cchSize[0] = 245;
  if ( GetUserProfileDirectoryW(*(&xmmword_180013840 + 1), ProfileDir, cchSize) )
  {
    wcscat_s(ProfileDir, 0x104u, L"\\AppData\\Local");
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids, LastError);
      goto LABEL_13;
    }
  }
  v1 = -1;
  do
    ++v1;
  while ( ProfileDir[v1] );
  qword_180013868 = v1 + 25;
  Src = LocalAlloc(0, 4 * (v1 + 25) + 4);
  if ( Src )
  {
    v2 = 2 * v1;
    lpFileName = (LPCWSTR)((char *)Src + 2 * qword_180013868 + 2);
    memcpy_0(Src, ProfileDir, v2);
    *(_WORD *)((char *)Src + v2) = 92;
    v3 = (char *)Src;
    *(_OWORD *)((char *)Src + v2 + 2) = xmmword_18000FA70;
    *(_OWORD *)&v3[v2 + 18] = xmmword_18000FA80;
    *(_OWORD *)&v3[v2 + 34] = xmmword_18000FA90;
    *(_WORD *)&v3[v2 + 50] = 0;
    memcpy_0((void *)lpFileName, Src, 2 * qword_180013868 + 2);
    lpFileName[qword_180013868 - 1] = 126;
    return LastError;
  }
  LastError = 14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids);
LABEL_13:
  LocalFree(Src);
  Src = 0;
  return LastError;
}

```

## disassembly

```asm
0x1800025d8  mov     [rsp+arg_0], rbx
0x1800025dd  mov     [rsp+arg_8], rsi
0x1800025e2  push    rdi
0x1800025e3  sub     rsp, 250h
0x1800025ea  mov     rax, cs:__security_cookie
0x1800025f1  xor     rax, rsp
0x1800025f4  mov     [rsp+258h+var_18], rax
0x1800025fc  mov     rcx, qword ptr cs:xmmword_180013840+8; hToken
0x180002603  lea     r8, [rsp+258h+cchSize]; lpcchSize
0x180002608  lea     rdx, [rsp+258h+ProfileDir]; lpProfileDir
0x18000260d  mov     [rsp+258h+cchSize], 0F5h
0x180002615  call    cs:__imp_GetUserProfileDirectoryW
0x18000261b  xor     esi, esi
0x18000261d  test    eax, eax
0x18000261f  jnz     short loc_180002669
0x180002621  call    cs:__imp_GetLastError
0x180002627  mov     edi, eax
0x180002629  test    eax, eax
0x18000262b  jz      short loc_180002682
0x18000262d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002634  lea     rax, WPP_GLOBAL_Control
0x18000263b  cmp     rcx, rax
0x18000263e  jz      loc_1800026ED
0x180002644  test    byte ptr [rcx+1Ch], 2
0x180002648  jz      loc_1800026ED
0x18000264e  mov     rcx, [rcx+10h]
0x180002652  lea     edx, [rsi+0Fh]
0x180002655  mov     r9d, edi
0x180002658  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x18000265f  call    WPP_SF_D
0x180002664  jmp     loc_1800026ED
0x180002669  lea     r8, aAppdataLocal; "\\AppData\\Local"
0x180002670  mov     edx, 104h; SizeInWords
0x180002675  lea     rcx, [rsp+258h+ProfileDir]; Destination
0x18000267a  call    cs:__imp_wcscat_s
0x180002680  mov     edi, esi
0x180002682  lea     rax, [rsp+258h+ProfileDir]
0x180002687  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000268b  inc     rbx
0x18000268e  cmp     [rax+rbx*2], si
0x180002692  jnz     short loc_18000268B
0x180002694  lea     rdx, [rbx+19h]
0x180002698  xor     ecx, ecx; uFlags
0x18000269a  mov     cs:qword_180013868, rdx
0x1800026a1  lea     rdx, ds:4[rdx*4]; uBytes
0x1800026a9  call    cs:__imp_LocalAlloc
0x1800026af  mov     cs:Src, rax
0x1800026b6  mov     r9, rax
0x1800026b9  test    rax, rax
0x1800026bc  jnz     short loc_180002706
0x1800026be  lea     edi, [rax+0Eh]
0x1800026c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026c8  lea     rax, WPP_GLOBAL_Control
0x1800026cf  cmp     rcx, rax
0x1800026d2  jz      short loc_1800026ED
0x1800026d4  test    byte ptr [rcx+1Ch], 2
0x1800026d8  jz      short loc_1800026ED
0x1800026da  mov     rcx, [rcx+10h]
0x1800026de  lea     edx, [rdi+2]
0x1800026e1  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x1800026e8  call    WPP_SF_
0x1800026ed  mov     rcx, cs:Src; hMem
0x1800026f4  call    cs:__imp_LocalFree
0x1800026fa  mov     cs:Src, rsi
0x180002701  jmp     loc_1800027A9
0x180002706  mov     rax, cs:qword_180013868
0x18000270d  lea     rdx, [rsp+258h+ProfileDir]; Src
0x180002712  inc     rax
0x180002715  add     rbx, rbx
0x180002718  mov     r8, rbx; Size
0x18000271b  lea     rcx, [r9+rax*2]
0x18000271f  mov     cs:lpFileName, rcx
0x180002726  mov     rcx, r9; void *
0x180002729  call    memcpy_0
0x18000272e  mov     rax, cs:Src
0x180002735  mov     word ptr [rbx+rax], 5Ch ; '\'
0x18000273b  mov     rdx, cs:Src
0x180002742  movups  xmm0, cs:xmmword_18000FA70
0x180002749  movups  xmmword ptr [rbx+rdx+2], xmm0
0x18000274e  movups  xmm1, cs:xmmword_18000FA80
0x180002755  movups  xmmword ptr [rbx+rdx+12h], xmm1
0x18000275a  movups  xmm0, cs:xmmword_18000FA90
0x180002761  movups  xmmword ptr [rbx+rdx+22h], xmm0
0x180002766  movzx   ecx, cs:word_18000FAA0
0x18000276d  mov     [rbx+rdx+32h], cx
0x180002772  mov     r8, cs:qword_180013868
0x180002779  mov     rdx, cs:Src; Src
0x180002780  mov     rcx, cs:lpFileName; void *
0x180002787  lea     r8, ds:2[r8*2]; Size
0x18000278f  call    memcpy_0
0x180002794  mov     rdx, cs:qword_180013868
0x18000279b  mov     rcx, cs:lpFileName
0x1800027a2  mov     word ptr [rcx+rdx*2-2], 7Eh ; '~'
0x1800027a9  mov     eax, edi
0x1800027ab  mov     rcx, [rsp+258h+var_18]
0x1800027b3  xor     rcx, rsp; StackCookie
0x1800027b6  call    __security_check_cookie
0x1800027bb  lea     r11, [rsp+258h+var_8]
0x1800027c3  mov     rbx, [r11+10h]
0x1800027c7  mov     rsi, [r11+18h]
0x1800027cb  mov     rsp, r11
0x1800027ce  pop     rdi
0x1800027cf  retn
```
