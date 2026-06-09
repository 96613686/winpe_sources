# _anonymous_namespace_::LoadPrivateRegistryFile

- ea: `0x1400152a4`
- end: `0x1400153dd`
- name: `_anonymous_namespace_::LoadPrivateRegistryFile`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x14002ae80`

## callees

- `0x140001020`
- `0x1400152a4`

## import_xrefs

- `ADVAPI32!RegLoadAppKeyW` at `0x14001530f`
- `ADVAPI32!RegLoadAppKeyW` at `0x14001530f`
- `KERNEL32!GetFileAttributesExW` at `0x140015392`
- `KERNEL32!GetFileAttributesExW` at `0x140015392`
- `KERNEL32!Sleep` at `0x140015344`
- `KERNEL32!Sleep` at `0x140015344`
- `KERNEL32!GetTickCount` at `0x1400152eb`
- `KERNEL32!GetTickCount` at `0x140015317`
- `KERNEL32!GetTickCount` at `0x14001533a`
- `KERNEL32!GetTickCount` at `0x14001534a`
- `KERNEL32!GetTickCount` at `0x1400152eb`
- `KERNEL32!GetTickCount` at `0x140015317`
- `KERNEL32!GetTickCount` at `0x14001533a`
- `KERNEL32!GetTickCount` at `0x14001534a`
- `SHLWAPI!PathFileExistsW` at `0x1400152da`
- `SHLWAPI!PathFileExistsW` at `0x1400152da`

## pseudocode

```c
__int64 anonymous_namespace_::LoadPrivateRegistryFile()
{
  DWORD v0; // esi
  int v1; // ebp
  DWORD TickCount; // ebx
  unsigned int AppKeyW; // edi
  DWORD v4; // ebx
  DWORD v5; // eax
  __int128 FileInformation; // [rsp+38h] [rbp-40h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h]
  unsigned int v9; // [rsp+58h] [rbp-20h]

  v0 = 100;
  dword_14009D424 = 0;
  byte_14009D410 = !PathFileExistsW(lpFile);
  v1 = 0;
  do
  {
    TickCount = GetTickCount();
    AppKeyW = RegLoadAppKeyW(lpFile, &hKey, 0xF003Fu, 0, 0);
    dword_14009D420 = GetTickCount() - TickCount;
    if ( AppKeyW - 32 > 1 && AppKeyW != 6 && AppKeyW != 183 )
      break;
    v4 = GetTickCount();
    Sleep(v0);
    ++v1;
    dword_14009D424 += GetTickCount() - v4;
    v5 = v0 + 100;
    if ( v0 >= 0x3E8 )
      v5 = v0;
    v0 = v5;
  }
  while ( v1 < 30 );
  v9 = 0;
  FileInformation = 0;
  v8 = 0;
  if ( GetFileAttributesExW(lpFile, GetFileExInfoStandard, &FileInformation) )
    qword_14009D428 = __PAIR64__(HIDWORD(v8), v9);
  return AppKeyW;
}

```

## disassembly

```asm
0x1400152a4  mov     [rsp+arg_0], rbx
0x1400152a9  mov     [rsp+arg_8], rbp
0x1400152ae  mov     [rsp+arg_10], rsi
0x1400152b3  push    rdi
0x1400152b4  sub     rsp, 70h
0x1400152b8  mov     rax, cs:__security_cookie
0x1400152bf  xor     rax, rsp
0x1400152c2  mov     [rsp+78h+var_18], rax
0x1400152c7  mov     rcx, cs:lpFile; pszPath
0x1400152ce  mov     esi, 64h ; 'd'
0x1400152d3  and     cs:dword_14009D424, 0
0x1400152da  call    cs:__imp_PathFileExistsW
0x1400152e0  test    eax, eax
0x1400152e2  setz    cs:byte_14009D410
0x1400152e9  xor     ebp, ebp
0x1400152eb  call    cs:__imp_GetTickCount
0x1400152f1  mov     rcx, cs:lpFile; lpFile
0x1400152f8  lea     rdx, hKey; phkResult
0x1400152ff  and     [rsp+78h+var_58], 0
0x140015304  xor     r9d, r9d; dwOptions
0x140015307  mov     r8d, 0F003Fh; samDesired
0x14001530d  mov     ebx, eax
0x14001530f  call    cs:__imp_RegLoadAppKeyW
0x140015315  mov     edi, eax
0x140015317  call    cs:__imp_GetTickCount
0x14001531d  sub     eax, ebx
0x14001531f  lea     ecx, [rdi-20h]
0x140015322  mov     cs:dword_14009D420, eax
0x140015328  cmp     ecx, 1
0x14001532b  jbe     short loc_14001533A
0x14001532d  cmp     edi, 6
0x140015330  jz      short loc_14001533A
0x140015332  cmp     edi, 0B7h
0x140015338  jnz     short loc_140015371
0x14001533a  call    cs:__imp_GetTickCount
0x140015340  mov     ecx, esi; dwMilliseconds
0x140015342  mov     ebx, eax
0x140015344  call    cs:__imp_Sleep
0x14001534a  call    cs:__imp_GetTickCount
0x140015350  sub     eax, ebx
0x140015352  inc     ebp
0x140015354  add     cs:dword_14009D424, eax
0x14001535a  lea     eax, [rsi+64h]
0x14001535d  cmp     esi, 3E8h
0x140015363  cmovnb  eax, esi
0x140015366  mov     esi, eax
0x140015368  cmp     ebp, 1Eh
0x14001536b  jl      loc_1400152EB
0x140015371  mov     rcx, cs:lpFile; lpFileName
0x140015378  lea     r8, [rsp+78h+FileInformation]; lpFileInformation
0x14001537d  xorps   xmm0, xmm0
0x140015380  xor     eax, eax
0x140015382  xor     edx, edx; fInfoLevelId
0x140015384  mov     [rsp+78h+var_20], eax
0x140015388  movups  [rsp+78h+FileInformation], xmm0
0x14001538d  movups  [rsp+78h+var_30], xmm0
0x140015392  call    cs:__imp_GetFileAttributesExW
0x140015398  test    eax, eax
0x14001539a  jz      short loc_1400153B8
0x14001539c  mov     eax, dword ptr [rsp+78h+var_30+0Ch]
0x1400153a0  mov     dword ptr [rsp+78h+var_48+4], eax
0x1400153a4  mov     eax, [rsp+78h+var_20]
0x1400153a8  mov     dword ptr [rsp+78h+var_48], eax
0x1400153ac  mov     rax, [rsp+78h+var_48]
0x1400153b1  mov     cs:qword_14009D428, rax
0x1400153b8  mov     eax, edi
0x1400153ba  mov     rcx, [rsp+78h+var_18]
0x1400153bf  xor     rcx, rsp; StackCookie
0x1400153c2  call    __security_check_cookie
0x1400153c7  lea     r11, [rsp+78h+var_8]
0x1400153cc  mov     rbx, [r11+10h]
0x1400153d0  mov     rbp, [r11+18h]
0x1400153d4  mov     rsi, [r11+20h]
0x1400153d8  mov     rsp, r11
0x1400153db  pop     rdi
0x1400153dc  retn
```
