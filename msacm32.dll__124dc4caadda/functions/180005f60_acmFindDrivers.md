# acmFindDrivers

- ea: `0x180005f60`
- end: `0x180006301`
- name: `acmFindDrivers`
- size: `929`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005e70`

## callees

- `0x180004b70`
- `0x180005f60`
- `0x1800066b0`
- `0x180009270`
- `0x180009afa`
- `0x1800120ec`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180005fe8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000623f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180005fe8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18000623f`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180006022`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180006022`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005fff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062c3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005fff`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800062c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006201`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006211`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005faa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005faa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000616f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000616f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180006158`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180006158`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18000618e`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18000618e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800061b6`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800061b6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800060f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006124`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006124`

## pseudocode

```c
__int64 __fastcall acmFindDrivers(__int64 a1)
{
  unsigned int i; // esi
  WCHAR *v3; // rax
  HWND v4; // rbx
  WCHAR *v5; // r14
  DWORD PrivateProfileStringW; // edx
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  size_t v11; // rdx
  const wchar_t *v12; // r8
  DWORD FileVersionInfoSizeW; // eax
  DWORD v14; // esi
  HLOCAL v15; // rax
  void *v16; // rdi
  __int64 v17; // rax
  unsigned int puLen; // [rsp+30h] [rbp-278h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-274h] BYREF
  WCHAR ReturnedString; // [rsp+38h] [rbp-270h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-268h] BYREF
  __int64 v24; // [rsp+48h] [rbp-260h] BYREF
  WCHAR *v25; // [rsp+50h] [rbp-258h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-248h] BYREF

  v24 = 0;
  for ( i = 512; ; i *= 2 )
  {
    v3 = (WCHAR *)GlobalAlloc(0, i);
    v4 = (HWND)v3;
    if ( !v3 )
      return 7;
    v25 = v3;
    *v3 = 0;
    v5 = v3;
    PrivateProfileStringW = GetPrivateProfileStringW(L"DRIVERS32", 0, &gszNull, v3, i >> 1, L"SYSTEM.INI");
    if ( PrivateProfileStringW < ((unsigned __int64)i >> 1) - 5 )
      break;
    GlobalFree(v4);
    if ( i >= 0x8000 )
      return 7;
  }
  if ( *(_WORD *)v4 )
  {
    CharLowerBuffW((LPWSTR)v4, PrivateProfileStringW);
    if ( *(_WORD *)v4 )
    {
      v7 = gszTagDrivers;
      while ( 2 )
      {
        v8 = *(_QWORD *)v4 - v7;
        if ( *(_QWORD *)v4 == v7 )
          v8 = *((unsigned int *)v4 + 2) - 3014765LL;
        if ( v8 )
          goto LABEL_38;
        v9 = -1;
        do
          ++v9;
        while ( *((_WORD *)v4 + v9) );
        if ( v9 > 0xD )
          LODWORD(v9) = 13;
        if ( CompareStringOrdinal((LPCWCH)v4, v9, L"msacm.voxacm1", -1, 1) != 2 )
        {
          if ( ((unsigned __int64)v4 & 0xFFFFFFFF00000000uLL) != 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( *((_WORD *)v4 + v10) );
            if ( v10 > 0xC )
              LODWORD(v10) = 12;
            if ( CompareStringOrdinal((LPCWCH)v4, v10, L"msacm.vorbis", -1, 1) == 2 )
            {
              memset_0(Buffer, 0, 0x208u);
              if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 && StringCchCatW(Buffer, v11, v12) >= 0 )
              {
                dwHandle = 0;
                FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, &dwHandle);
                v14 = FileVersionInfoSizeW;
                if ( FileVersionInfoSizeW )
                {
                  v15 = LocalAlloc(0x40u, FileVersionInfoSizeW);
                  v16 = v15;
                  if ( v15 )
                  {
                    if ( GetFileVersionInfoW(Buffer, 0, v14, v15) )
                    {
                      lpBuffer = 0;
                      puLen = 0;
                      if ( VerQueryValueW(v16, L"\\", &lpBuffer, &puLen) )
                      {
                        if ( puLen && !*((_DWORD *)lpBuffer + 2) && *((_DWORD *)lpBuffer + 3) == 196614 )
                        {
                          LocalFree(v16);
                          goto LABEL_37;
                        }
                      }
                    }
                    LocalFree(v16);
                  }
                }
              }
            }
          }
          GetPrivateProfileStringW(L"DRIVERS32", (LPCWSTR)v4, &gszNull, &ReturnedString, 2u, L"SYSTEM.INI");
          if ( ReturnedString != 42 && (unsigned int)DriverAllowedByPluginControlPolicy((LPCWCH)v4) )
            IDriverAdd(a1, &v24, 0, v4, 0, 9u);
        }
LABEL_37:
        v7 = gszTagDrivers;
LABEL_38:
        v17 = -1;
        while ( *((_WORD *)v4 + ++v17) != 0 )
          ;
        v4 = (HWND)((char *)v4 + 2 * v17 + 2);
        if ( !*(_WORD *)v4 )
        {
          v5 = v25;
          break;
        }
        continue;
      }
    }
  }
  GlobalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x180005f60  mov     [rsp+arg_18], rbx
0x180005f65  push    rbp
0x180005f66  push    rsi
0x180005f67  push    rdi
0x180005f68  push    r12
0x180005f6a  push    r15
0x180005f6c  sub     rsp, 280h
0x180005f73  mov     rax, cs:__security_cookie
0x180005f7a  xor     rax, rsp
0x180005f7d  mov     [rsp+2A8h+var_38], rax
0x180005f85  xor     r15d, r15d
0x180005f88  mov     [rsp+2A8h+arg_10], r14
0x180005f90  mov     [rsp+2A8h+var_260], r15
0x180005f95  lea     r12, gszIniSystem; "SYSTEM.INI"
0x180005f9c  mov     rbp, rcx
0x180005f9f  mov     esi, 200h
0x180005fa4  mov     edx, esi; dwBytes
0x180005fa6  xor     ecx, ecx; uFlags
0x180005fa8  mov     edi, esi
0x180005faa  call    cs:__imp_GlobalAlloc
0x180005fb0  mov     rbx, rax
0x180005fb3  test    rax, rax
0x180005fb6  jz      loc_1800062CD
0x180005fbc  mov     ecx, esi
0x180005fbe  mov     [rsp+2A8h+lpFileName], r12; lpFileName
0x180005fc3  shr     ecx, 1
0x180005fc5  lea     r8, gszNull; lpDefault
0x180005fcc  mov     [rsp+2A8h+nSize], ecx; nSize
0x180005fd0  mov     r9, rax; lpReturnedString
0x180005fd3  lea     rcx, gszSecDrivers; "DRIVERS32"
0x180005fda  mov     [rsp+2A8h+var_258], rax
0x180005fdf  xor     edx, edx; lpKeyName
0x180005fe1  mov     [rax], r15w
0x180005fe5  mov     r14, rax
0x180005fe8  call    cs:__imp_GetPrivateProfileStringW
0x180005fee  shr     rdi, 1
0x180005ff1  mov     edx, eax; cchLength
0x180005ff3  sub     rdi, 5
0x180005ff7  cmp     rdx, rdi
0x180005ffa  jb      short loc_180006015
0x180005ffc  mov     rcx, rbx; hMem
0x180005fff  call    cs:__imp_GlobalFree
0x180006005  cmp     esi, 8000h
0x18000600b  jnb     loc_1800062CD
0x180006011  add     esi, esi
0x180006013  jmp     short loc_180005FA4
0x180006015  cmp     r15w, [rbx]
0x180006019  jz      loc_1800062C0
0x18000601f  mov     rcx, rbx; lpsz
0x180006022  call    cs:__imp_CharLowerBuffW
0x180006028  cmp     r15w, [rbx]
0x18000602c  jz      loc_1800062C0
0x180006032  mov     edx, cs:dword_180014A98
0x180006038  mov     eax, 0Dh
0x18000603d  mov     r8, cs:gszTagDrivers
0x180006044  mov     edi, 0Ch
0x180006049  mov     [rsp+2A8h+arg_8], r13
0x180006051  mov     r14d, 2Ah ; '*'
0x180006057  mov     r13, 0FFFFFFFF00000000h
0x180006061  mov     rcx, [rbx]
0x180006064  sub     rcx, r8
0x180006067  jnz     short loc_180006076
0x180006069  mov     ecx, [rbx+8]
0x18000606c  mov     eax, edx
0x18000606e  sub     rcx, rax
0x180006071  mov     eax, 0Dh
0x180006076  test    rcx, rcx
0x180006079  jnz     loc_180006286
0x18000607f  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006086  inc     rdx
0x180006089  cmp     [rbx+rdx*2], r15w
0x18000608e  jnz     short loc_180006086
0x180006090  cmp     rdx, 0Dh
0x180006094  mov     [rsp+2A8h+nSize], 1; bIgnoreCase
0x18000609c  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800060a2  lea     r8, gszVox; "msacm.voxacm1"
0x1800060a9  cmova   rdx, rax; cchCount1
0x1800060ad  mov     rcx, rbx; lpString1
0x1800060b0  call    cs:__imp_CompareStringOrdinal
0x1800060b6  cmp     eax, 2
0x1800060b9  jz      loc_180006279
0x1800060bf  test    r13, rbx
0x1800060c2  jz      loc_18000621C
0x1800060c8  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800060cf  inc     rdx
0x1800060d2  cmp     [rbx+rdx*2], r15w
0x1800060d7  jnz     short loc_1800060CF
0x1800060d9  cmp     rdx, 0Ch
0x1800060dd  mov     [rsp+2A8h+nSize], 1; bIgnoreCase
0x1800060e5  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800060eb  lea     r8, gszVorbis; "msacm.vorbis"
0x1800060f2  cmova   rdx, rdi; cchCount1
0x1800060f6  mov     rcx, rbx; lpString1
0x1800060f9  call    cs:__imp_CompareStringOrdinal
0x1800060ff  cmp     eax, 2
0x180006102  jnz     loc_18000621C
0x180006108  xor     edx, edx; Val
0x18000610a  lea     rcx, [rsp+2A8h+Buffer]; void *
0x18000610f  mov     r8d, 208h; Size
0x180006115  call    memset_0
0x18000611a  mov     edx, 104h; uSize
0x18000611f  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x180006124  call    cs:__imp_GetSystemDirectoryW
0x18000612a  dec     eax
0x18000612c  cmp     eax, 102h
0x180006131  ja      loc_18000621C
0x180006137  lea     rcx, [rsp+2A8h+Buffer]; pszDest
0x18000613c  call    StringCchCatW
0x180006141  test    eax, eax
0x180006143  js      loc_18000621C
0x180006149  lea     rdx, [rsp+2A8h+dwHandle]; lpdwHandle
0x18000614e  mov     [rsp+2A8h+dwHandle], r15d
0x180006153  lea     rcx, [rsp+2A8h+Buffer]; lptstrFilename
0x180006158  call    cs:__imp_GetFileVersionInfoSizeW
0x18000615e  mov     esi, eax
0x180006160  test    eax, eax
0x180006162  jz      loc_18000621C
0x180006168  mov     edx, esi; uBytes
0x18000616a  mov     ecx, 40h ; '@'; uFlags
0x18000616f  call    cs:__imp_LocalAlloc
0x180006175  mov     rdi, rax
0x180006178  test    rax, rax
0x18000617b  jz      loc_180006217
0x180006181  mov     r9, rax; lpData
0x180006184  lea     rcx, [rsp+2A8h+Buffer]; lptstrFilename
0x180006189  mov     r8d, esi; dwLen
0x18000618c  xor     edx, edx; dwHandle
0x18000618e  call    cs:__imp_GetFileVersionInfoW
0x180006194  test    eax, eax
0x180006196  jz      short loc_18000620E
0x180006198  lea     r9, [rsp+2A8h+puLen]; puLen
0x18000619d  mov     [rsp+2A8h+lpBuffer], r15
0x1800061a2  lea     r8, [rsp+2A8h+lpBuffer]; lplpBuffer
0x1800061a7  mov     [rsp+2A8h+puLen], r15d
0x1800061ac  lea     rdx, SubBlock; "\\"
0x1800061b3  mov     rcx, rdi; pBlock
0x1800061b6  call    cs:__imp_VerQueryValueW
0x1800061bc  test    eax, eax
0x1800061be  jz      short loc_18000620E
0x1800061c0  cmp     [rsp+2A8h+puLen], r15d
0x1800061c5  jz      short loc_18000620E
0x1800061c7  mov     r8, [rsp+2A8h+lpBuffer]
0x1800061cc  mov     edx, [r8+8]
0x1800061d0  mov     ecx, edx
0x1800061d2  shr     ecx, 10h
0x1800061d5  cmp     r15w, cx
0x1800061d9  jnz     short loc_18000620E
0x1800061db  cmp     r15w, dx
0x1800061df  jnz     short loc_18000620E
0x1800061e1  mov     ecx, [r8+0Ch]
0x1800061e5  mov     edx, 3
0x1800061ea  mov     eax, ecx
0x1800061ec  shr     eax, 10h
0x1800061ef  cmp     dx, ax
0x1800061f2  jnz     short loc_18000620E
0x1800061f4  mov     eax, 6
0x1800061f9  cmp     ax, cx
0x1800061fc  jnz     short loc_18000620E
0x1800061fe  mov     rcx, rdi; hMem
0x180006201  call    cs:__imp_LocalFree
0x180006207  mov     edi, 0Ch
0x18000620c  jmp     short loc_180006279
0x18000620e  mov     rcx, rdi; hMem
0x180006211  call    cs:__imp_LocalFree
0x180006217  mov     edi, 0Ch
0x18000621c  mov     [rsp+2A8h+lpFileName], r12; lpFileName
0x180006221  lea     r9, [rsp+2A8h+ReturnedString]; lpReturnedString
0x180006226  lea     r8, gszNull; lpDefault
0x18000622d  mov     [rsp+2A8h+nSize], 2; nSize
0x180006235  mov     rdx, rbx; lpKeyName
0x180006238  lea     rcx, gszSecDrivers; "DRIVERS32"
0x18000623f  call    cs:__imp_GetPrivateProfileStringW
0x180006245  cmp     r14w, [rsp+2A8h+ReturnedString]
0x18000624b  jz      short loc_180006279
0x18000624d  mov     rcx, rbx; lpString1
0x180006250  call    DriverAllowedByPluginControlPolicy
0x180006255  test    eax, eax
0x180006257  jz      short loc_180006279
0x180006259  mov     dword ptr [rsp+2A8h+lpFileName], 9
0x180006261  lea     rdx, [rsp+2A8h+var_260]
0x180006266  mov     r9, rbx
0x180006269  mov     [rsp+2A8h+nSize], r15d
0x18000626e  xor     r8d, r8d
0x180006271  mov     rcx, rbp
0x180006274  call    IDriverAdd
0x180006279  mov     edx, cs:dword_180014A98
0x18000627f  mov     r8, cs:gszTagDrivers
0x180006286  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000628d  nop     dword ptr [rax]
0x180006290  cmp     [rbx+rax*2+2], r15w
0x180006296  lea     rax, [rax+1]
0x18000629a  jnz     short loc_180006290
0x18000629c  lea     rbx, [rbx+rax*2]
0x1800062a0  mov     eax, 0Dh
0x1800062a5  add     rbx, 2
0x1800062a9  cmp     r15w, [rbx]
0x1800062ad  jnz     loc_180006061
0x1800062b3  mov     r13, [rsp+2A8h+arg_8]
0x1800062bb  mov     r14, [rsp+2A8h+var_258]
0x1800062c0  mov     rcx, r14; hMem
0x1800062c3  call    cs:__imp_GlobalFree
0x1800062c9  xor     eax, eax
0x1800062cb  jmp     short loc_1800062D2
0x1800062cd  mov     eax, 7
0x1800062d2  mov     r14, [rsp+2A8h+arg_10]
0x1800062da  mov     rcx, [rsp+2A8h+var_38]
0x1800062e2  xor     rcx, rsp; StackCookie
0x1800062e5  call    __security_check_cookie
0x1800062ea  mov     rbx, [rsp+2A8h+arg_18]
0x1800062f2  add     rsp, 280h
0x1800062f9  pop     r15
0x1800062fb  pop     r12
0x1800062fd  pop     rdi
0x1800062fe  pop     rsi
0x1800062ff  pop     rbp
0x180006300  retn
```
