# NativeMsh::PwrshCommon::OpenEngineRegKeyWithVersion(HKEY__ * *,ushort * *,ushort const *,int)

- ea: `0x1800086b8`
- end: `0x18000888a`
- name: `?OpenEngineRegKeyWithVersion@PwrshCommon@NativeMsh@@IEAAIPEAPEAUHKEY__@@PEAPEAGPEBGH@Z`
- size: `466`
- prototype: `__int64 __fastcall(NativeMsh::PwrshCommon *this, HKEY *, unsigned __int16 **, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007c2c`

## callees

- `0x1800079f4`
- `0x1800086b8`
- `0x180008d34`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000873b`
- `msvcrt!_itow_s` at `0x18000873b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800087fb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800087fb`
- `ADVAPI32!RegCloseKey` at `0x18000880a`
- `ADVAPI32!RegCloseKey` at `0x18000880a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800087b2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800087b2`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::OpenEngineRegKeyWithVersion(
        NativeMsh::PwrshCommon *this,
        HKEY *a2,
        unsigned __int16 **a3,
        const unsigned __int16 *a4,
        int a5)
{
  HKEY *v7; // r13
  int v9; // ecx
  WCHAR *v10; // rsi
  bool v11; // al
  LSTATUS v12; // r13d
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rsi
  unsigned int v16; // [rsp+30h] [rbp-41h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-39h] BYREF
  HKEY *v18; // [rsp+40h] [rbp-31h]
  HKEY hKey; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-21h] BYREF
  wchar_t Buffer[12]; // [rsp+58h] [rbp-19h] BYREF

  v18 = a2;
  v20 = 0;
  v7 = a2;
  if ( a2 && a3 && a4 && *a4 )
  {
    v9 = a5;
    if ( (unsigned int)(a5 - 4) <= 1 )
      v9 = 3;
    _itow_s(v9, Buffer, 0xBu, 10);
    v10 = 0;
    lpSubKey = 0;
    hKey = 0;
    if ( *a4
      && Buffer[0]
      && (v11 = NativeMsh::PwrshCommon::FormatStringWithErrorReporting(
                  this,
                  L"SOFTWARE\\Microsoft\\PowerShell\\%1!ls!",
                  (unsigned __int16 **)&lpSubKey,
                  &v16,
                  23,
                  Buffer),
          v10 = (WCHAR *)lpSubKey,
          v11) )
    {
      v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
      if ( v12 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *))(**((_QWORD **)this + 1) + 8LL))(
          *((_QWORD *)this + 1),
          0,
          25,
          a4);
        v13 = -393216;
        if ( v12 != 2 )
          v13 = -327680;
      }
      else
      {
        v13 = 0;
      }
      v7 = v18;
    }
    else
    {
      v13 = -327680;
    }
    if ( v10 )
      operator delete[](v10);
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v13 )
    {
      if ( NativeMsh::PwrshCommon::FormatStringWithErrorReporting(
             this,
             L"SOFTWARE\\Microsoft\\PowerShell\\%1!ls!\\PowerShellEngine",
             &v20,
             &v16,
             23,
             Buffer)
        && (v14 = v20, NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(this, v20, a4, v7)) )
      {
        *a3 = v14;
      }
      else
      {
        return (unsigned int)-327680;
      }
    }
  }
  else
  {
    return (unsigned int)-327680;
  }
  return v13;
}

```

## disassembly

```asm
0x1800086b8  push    rbp
0x1800086ba  push    rbx
0x1800086bb  push    rsi
0x1800086bc  push    rdi
0x1800086bd  push    r12
0x1800086bf  push    r13
0x1800086c1  push    r14
0x1800086c3  push    r15
0x1800086c5  lea     rbp, [rsp-17h]
0x1800086ca  sub     rsp, 88h
0x1800086d1  mov     rax, cs:__security_cookie
0x1800086d8  xor     rax, rsp
0x1800086db  mov     [rbp+4Fh+var_50], rax
0x1800086df  mov     [rbp+4Fh+var_80], rdx
0x1800086e3  mov     r14, r9
0x1800086e6  mov     [rbp+4Fh+var_70], 0
0x1800086ee  mov     r12, r8
0x1800086f1  mov     r13, rdx
0x1800086f4  mov     r15, rcx
0x1800086f7  test    rdx, rdx
0x1800086fa  jz      loc_180008863
0x180008700  test    r8, r8
0x180008703  jz      loc_180008863
0x180008709  test    r9, r9
0x18000870c  jz      loc_180008863
0x180008712  xor     eax, eax
0x180008714  cmp     ax, [r9]
0x180008718  jz      loc_180008863
0x18000871e  mov     ecx, [rbp+4Fh+arg_20]
0x180008721  mov     edx, 3
0x180008726  lea     eax, [rcx-4]
0x180008729  cmp     eax, 1
0x18000872c  lea     r9d, [rdx+7]; Radix
0x180008730  lea     r8d, [rdx+8]; BufferCount
0x180008734  cmovbe  ecx, edx; Value
0x180008737  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18000873b  call    cs:__imp__itow_s
0x180008741  xor     esi, esi
0x180008743  xor     eax, eax
0x180008745  mov     edi, 0FFFB0000h
0x18000874a  mov     [rbp+4Fh+lpSubKey], rsi
0x18000874e  mov     [rbp+4Fh+hKey], rsi
0x180008752  cmp     ax, [r14]
0x180008756  jz      loc_1800087F1
0x18000875c  cmp     ax, [rbp+4Fh+Buffer]
0x180008760  jz      loc_1800087F1
0x180008766  lea     rax, [rbp+4Fh+Buffer]
0x18000876a  mov     rcx, r15; this
0x18000876d  mov     [rsp+0C0h+var_98], rax
0x180008772  lea     r9, [rbp+4Fh+var_90]; unsigned int *
0x180008776  lea     r8, [rbp+4Fh+lpSubKey]; unsigned __int16 **
0x18000877a  mov     dword ptr [rsp+0C0h+phkResult], 17h; int
0x180008782  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\PowerShell\\%1!ls!"
0x180008789  call    ?FormatStringWithErrorReporting@PwrshCommon@NativeMsh@@IEAA_NPEBGPEAPEAGPEAKHZZ; NativeMsh::PwrshCommon::FormatStringWithErrorReporting(ushort const *,ushort * *,ulong *,int,...)
0x18000878e  mov     rsi, [rbp+4Fh+lpSubKey]
0x180008792  test    al, al
0x180008794  jz      short loc_1800087F1
0x180008796  lea     rax, [rbp+4Fh+hKey]
0x18000879a  mov     r9d, 20019h; samDesired
0x1800087a0  xor     r8d, r8d; ulOptions
0x1800087a3  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800087a8  mov     rdx, rsi; lpSubKey
0x1800087ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800087b2  call    cs:__imp_RegOpenKeyExW
0x1800087b8  mov     r13d, eax
0x1800087bb  test    eax, eax
0x1800087bd  jz      short loc_1800087ED
0x1800087bf  mov     r10, [r15+8]
0x1800087c3  xor     edx, edx
0x1800087c5  mov     r9, r14
0x1800087c8  mov     rcx, [r10]
0x1800087cb  lea     r8d, [rdx+19h]
0x1800087cf  mov     rax, [rcx+8]
0x1800087d3  mov     rcx, r10
0x1800087d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087db  cmp     r13d, 2
0x1800087df  mov     ebx, 0FFFA0000h
0x1800087e4  cmovnz  ebx, edi
0x1800087e7  mov     r13, [rbp+4Fh+var_80]
0x1800087eb  jmp     short loc_1800087F3
0x1800087ed  xor     ebx, ebx
0x1800087ef  jmp     short loc_1800087E7
0x1800087f1  mov     ebx, edi
0x1800087f3  test    rsi, rsi
0x1800087f6  jz      short loc_180008801
0x1800087f8  mov     rcx, rsi
0x1800087fb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008801  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180008805  test    rcx, rcx
0x180008808  jz      short loc_180008810
0x18000880a  call    cs:__imp_RegCloseKey
0x180008810  test    ebx, ebx
0x180008812  jnz     short loc_180008868
0x180008814  lea     rax, [rbp+4Fh+Buffer]
0x180008818  mov     rcx, r15; this
0x18000881b  mov     [rsp+0C0h+var_98], rax
0x180008820  lea     r9, [rbp+4Fh+var_90]; unsigned int *
0x180008824  lea     r8, [rbp+4Fh+var_70]; unsigned __int16 **
0x180008828  mov     dword ptr [rsp+0C0h+phkResult], 17h; int
0x180008830  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\PowerShell\\%1!ls!"...
0x180008837  call    ?FormatStringWithErrorReporting@PwrshCommon@NativeMsh@@IEAA_NPEBGPEAPEAGPEAKHZZ; NativeMsh::PwrshCommon::FormatStringWithErrorReporting(ushort const *,ushort * *,ulong *,int,...)
0x18000883c  test    al, al
0x18000883e  jnz     short loc_180008844
0x180008840  mov     ebx, edi
0x180008842  jmp     short loc_180008868
0x180008844  mov     rsi, [rbp+4Fh+var_70]
0x180008848  mov     r9, r13; HKEY *
0x18000884b  mov     rdx, rsi; unsigned __int16 *
0x18000884e  mov     r8, r14; unsigned __int16 *
0x180008851  mov     rcx, r15; this
0x180008854  call    ?RegOpenKeyWithErrorReport@PwrshCommon@NativeMsh@@IEAA_NPEBG0PEAPEAUHKEY__@@@Z; NativeMsh::PwrshCommon::RegOpenKeyWithErrorReport(ushort const *,ushort const *,HKEY__ * *)
0x180008859  test    al, al
0x18000885b  jz      short loc_180008840
0x18000885d  mov     [r12], rsi
0x180008861  jmp     short loc_180008868
0x180008863  mov     ebx, 0FFFB0000h
0x180008868  mov     eax, ebx
0x18000886a  mov     rcx, [rbp+4Fh+var_50]
0x18000886e  xor     rcx, rsp; StackCookie
0x180008871  call    __security_check_cookie
0x180008876  add     rsp, 88h
0x18000887d  pop     r15
0x18000887f  pop     r14
0x180008881  pop     r13
0x180008883  pop     r12
0x180008885  pop     rdi
0x180008886  pop     rsi
0x180008887  pop     rbx
0x180008888  pop     rbp
0x180008889  retn
```
