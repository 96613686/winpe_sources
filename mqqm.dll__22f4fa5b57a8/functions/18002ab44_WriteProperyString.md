# WriteProperyString

- ea: `0x18002ab44`
- end: `0x18002af88`
- name: `WriteProperyString`
- size: `1092`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180029950`

## callees

- `0x18000bb04`
- `0x18000cb80`
- `0x18002ab44`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x18002abb1`
- `msvcrt!free` at `0x18002ac2a`
- `msvcrt!free` at `0x18002acce`
- `msvcrt!free` at `0x18002ad0b`
- `msvcrt!free` at `0x18002adb0`
- `msvcrt!free` at `0x18002ae0e`
- `msvcrt!free` at `0x18002ae55`
- `msvcrt!free` at `0x18002ae9c`
- `msvcrt!free` at `0x18002aedf`
- `msvcrt!free` at `0x18002af45`
- `msvcrt!free` at `0x18002af54`
- `msvcrt!free` at `0x18002abb1`
- `msvcrt!free` at `0x18002ac2a`
- `msvcrt!free` at `0x18002acce`
- `msvcrt!free` at `0x18002ad0b`
- `msvcrt!free` at `0x18002adb0`
- `msvcrt!free` at `0x18002ae0e`
- `msvcrt!free` at `0x18002ae55`
- `msvcrt!free` at `0x18002ae9c`
- `msvcrt!free` at `0x18002aedf`
- `msvcrt!free` at `0x18002af45`
- `msvcrt!free` at `0x18002af54`
- `KERNEL32!GetLastError` at `0x18002af0a`
- `KERNEL32!GetLastError` at `0x18002af0a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002af00`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002af00`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteProperyString(LPCWSTR lpFileName, const WCHAR *a2, __int16 a3, unsigned __int8 *a4)
{
  unsigned int v6; // r12d
  WCHAR *v7; // rbx
  unsigned int v8; // ebx
  WCHAR *v10; // r15
  int v11; // eax
  unsigned int v12; // edi
  int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // eax
  wchar_t *v16; // rbp
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  DWORD LastError; // eax
  const WCHAR *lpKeyName; // [rsp+78h] [rbp-D0h]
  WCHAR String[64]; // [rsp+80h] [rbp-C8h] BYREF

  lpKeyName = a2;
  v6 = 0;
  v7 = 0;
  if ( !a4 && a3 && a3 != 31 )
  {
    v8 = -1072824296;
    LogMsgHR(-1072824296, (wchar_t *)L"lqs", 0x280u);
    free(0);
    return v8;
  }
  v10 = String;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 2:
        v23 = StringCchPrintfW(String, 0x40u, L"%d", (unsigned int)*(__int16 *)a4);
        v12 = v23;
        if ( v23 < 0 )
        {
          LogMsgHR(v23, (wchar_t *)L"lqs", 0x13CEu);
          free(0);
          return v12;
        }
        break;
      case 3:
        v22 = StringCchPrintfW(String, 0x40u, L"%d", *(unsigned int *)a4);
        v12 = v22;
        if ( v22 < 0 )
        {
          LogMsgHR(v22, (wchar_t *)L"lqs", 0x13D8u);
          free(0);
          return v12;
        }
        break;
      case 17:
        v21 = StringCchPrintfW(String, 0x40u, L"%02x", *a4);
        v12 = v21;
        if ( v21 < 0 )
        {
          LogMsgHR(v21, (wchar_t *)L"lqs", 0x14F0u);
          free(0);
          return v12;
        }
        break;
      case 19:
        v20 = StringCchPrintfW(String, 0x40u, L"%u", *(unsigned int *)a4);
        v12 = v20;
        if ( v20 < 0 )
        {
          LogMsgHR(v20, (wchar_t *)L"lqs", 0x13E2u);
          free(0);
          return v12;
        }
        break;
      case 31:
        v10 = (WCHAR *)a4;
        break;
      case 65:
        v13 = 64;
        v14 = 2 * *(_DWORD *)a4;
        if ( v14 >= 0x40 )
        {
          v15 = v14 + 1;
          if ( v15 > 0x10000 )
          {
            v8 = -1072824296;
            LogMsgHR(-1072824296, (wchar_t *)L"lqs", 0x46u);
            free(0);
            return v8;
          }
          v7 = (WCHAR *)MmAllocate(saturated_mul(v15, 2u));
          v10 = v7;
          v13 = 2 * *(_DWORD *)a4 + 1;
        }
        v16 = v10;
        *v10 = 0;
        while ( v6 < *(_DWORD *)a4 )
        {
          v17 = *(unsigned __int8 *)(*((_QWORD *)a4 + 1) + v6);
          v18 = mqwcslen(v10);
          v19 = StringCchPrintfW(v16, v13 - v18, L"%02x", v17);
          v12 = v19;
          if ( v19 < 0 )
          {
            LogMsgHR(v19, (wchar_t *)L"lqs", 0x1522u);
            free(v7);
            return v12;
          }
          v16 += mqwcslen(v16);
          ++v6;
        }
        *v16 = 0;
        break;
      case 72:
        v11 = StringCchPrintfW(
                String,
                0x40u,
                L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
                *(unsigned int *)a4,
                *((unsigned __int16 *)a4 + 2),
                *((unsigned __int16 *)a4 + 3),
                a4[8],
                a4[9],
                a4[10],
                a4[11],
                a4[12],
                a4[13],
                a4[14],
                a4[15],
                0,
                a2);
        v12 = v11;
        if ( v11 < 0 )
        {
          LogMsgHR(v11, (wchar_t *)L"lqs", 0x13F6u);
          free(0);
          return v12;
        }
        break;
      default:
        v8 = -1072824295;
        LogMsgHR(-1072824295, (wchar_t *)L"lqs", 0x2B7u);
        free(0);
        return v8;
    }
  }
  else
  {
    v10 = 0;
  }
  if ( !WritePrivateProfileStringW(L"Properties", lpKeyName, v10, lpFileName) )
  {
    LastError = GetLastError();
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"lqs", 0x50u);
    v12 = -1072824281;
    LogMsgHR(-1072824281, (wchar_t *)L"lqs", 0x4A8u);
    free(v7);
    return v12;
  }
  free(v7);
  return 0;
}

```

## disassembly

```asm
0x18002ab44  mov     [rsp+arg_10], rbx
0x18002ab49  push    rbp
0x18002ab4a  push    rsi
0x18002ab4b  push    rdi
0x18002ab4c  push    r12
0x18002ab4e  push    r13
0x18002ab50  push    r14
0x18002ab52  push    r15
0x18002ab54  sub     rsp, 110h
0x18002ab5b  mov     rax, cs:__security_cookie
0x18002ab62  xor     rax, rsp
0x18002ab65  mov     [rsp+148h+var_48], rax
0x18002ab6d  mov     r14, r9
0x18002ab70  mov     [rsp+148h+lpKeyName], rdx
0x18002ab75  mov     r13, rcx
0x18002ab78  xor     r12d, r12d
0x18002ab7b  mov     ebx, r12d
0x18002ab7e  mov     [rsp+148h+var_D8], rbx
0x18002ab83  test    r9, r9
0x18002ab86  jnz     short loc_18002ABBF
0x18002ab88  test    r8w, r8w
0x18002ab8c  jz      short loc_18002ABBF
0x18002ab8e  cmp     r8w, 1Fh
0x18002ab93  jz      short loc_18002ABBF
0x18002ab95  mov     r8d, 280h; unsigned __int16
0x18002ab9b  lea     rdx, aLqs_0; "lqs"
0x18002aba2  mov     ebx, 0C00E0018h
0x18002aba7  mov     ecx, ebx; int
0x18002aba9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002abae  nop
0x18002abaf  xor     ecx, ecx; Block
0x18002abb1  call    cs:__imp_free
0x18002abb7  nop
0x18002abb8  mov     eax, ebx
0x18002abba  jmp     loc_18002AF5D
0x18002abbf  lea     r15, [rsp+148h+String]
0x18002abc7  movzx   ecx, r8w
0x18002abcb  test    ecx, ecx
0x18002abcd  jz      loc_18002AEEB
0x18002abd3  sub     ecx, 2
0x18002abd6  jz      loc_18002AEA5
0x18002abdc  sub     ecx, 1
0x18002abdf  jz      loc_18002AE63
0x18002abe5  sub     ecx, 0Eh
0x18002abe8  jz      loc_18002AE17
0x18002abee  sub     ecx, 2
0x18002abf1  jz      loc_18002ADD1
0x18002abf7  sub     ecx, 0Ch
0x18002abfa  jz      loc_18002ADC9
0x18002ac00  sub     ecx, 22h ; '"'
0x18002ac03  jz      loc_18002ACDA
0x18002ac09  cmp     ecx, 7
0x18002ac0c  jz      short loc_18002AC33
0x18002ac0e  mov     r8d, 2B7h; unsigned __int16
0x18002ac14  lea     rdx, aLqs_0; "lqs"
0x18002ac1b  mov     ebx, 0C00E0019h
0x18002ac20  mov     ecx, ebx; int
0x18002ac22  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ac27  nop
0x18002ac28  xor     ecx, ecx; Block
0x18002ac2a  call    cs:__imp_free
0x18002ac30  nop
0x18002ac31  jmp     short loc_18002ABB8
0x18002ac33  movzx   eax, byte ptr [r9+0Fh]
0x18002ac38  movzx   ecx, byte ptr [r9+0Eh]
0x18002ac3d  movzx   edx, byte ptr [r9+0Dh]
0x18002ac42  movzx   r8d, byte ptr [r9+0Ch]
0x18002ac47  movzx   r9d, byte ptr [r9+0Bh]
0x18002ac4c  movzx   r10d, byte ptr [r14+0Ah]
0x18002ac51  movzx   r11d, byte ptr [r14+9]
0x18002ac56  movzx   edi, byte ptr [r14+8]
0x18002ac5b  movzx   esi, word ptr [r14+6]
0x18002ac60  movzx   ebp, word ptr [r14+4]
0x18002ac65  mov     [rsp+148h+var_E0], eax
0x18002ac69  mov     [rsp+148h+var_E8], ecx
0x18002ac6d  mov     [rsp+148h+var_F0], edx
0x18002ac71  mov     [rsp+148h+var_F8], r8d
0x18002ac76  mov     [rsp+148h+var_100], r9d
0x18002ac7b  mov     [rsp+148h+var_108], r10d
0x18002ac80  mov     [rsp+148h+var_110], r11d
0x18002ac85  mov     [rsp+148h+var_118], edi
0x18002ac89  mov     [rsp+148h+var_120], esi
0x18002ac8d  mov     [rsp+148h+var_128], ebp
0x18002ac91  mov     r9d, [r14]
0x18002ac94  lea     r8, a08x04x04x02x02_0; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x18002ac9b  mov     edx, 40h ; '@'; unsigned __int64
0x18002aca0  lea     rcx, [rsp+148h+String]; wchar_t *
0x18002aca8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002acad  mov     edi, eax
0x18002acaf  test    eax, eax
0x18002acb1  jns     loc_18002AEEE
0x18002acb7  mov     r8d, 13F6h; unsigned __int16
0x18002acbd  lea     rdx, aLqs_0; "lqs"
0x18002acc4  mov     ecx, eax; int
0x18002acc6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002accb  nop
0x18002accc  xor     ecx, ecx; Block
0x18002acce  call    cs:__imp_free
0x18002acd4  nop
0x18002acd5  jmp     loc_18002AE5C
0x18002acda  mov     esi, 40h ; '@'
0x18002acdf  mov     eax, [r9]
0x18002ace2  add     eax, eax
0x18002ace4  cmp     eax, esi
0x18002ace6  jb      short loc_18002AD49
0x18002ace8  inc     eax
0x18002acea  cmp     eax, 10000h
0x18002acef  jbe     short loc_18002AD17
0x18002acf1  lea     r8d, [rsi+6]; unsigned __int16
0x18002acf5  lea     rdx, aLqs_0; "lqs"
0x18002acfc  mov     ebx, 0C00E0018h
0x18002ad01  mov     ecx, ebx; int
0x18002ad03  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ad08  nop
0x18002ad09  xor     ecx, ecx; Block
0x18002ad0b  call    cs:__imp_free
0x18002ad11  nop
0x18002ad12  jmp     loc_18002ABB8
0x18002ad17  mov     ecx, eax
0x18002ad19  mov     eax, 2
0x18002ad1e  mul     rcx
0x18002ad21  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ad28  cmovb   rax, rcx
0x18002ad2c  mov     rcx, rax; unsigned __int64
0x18002ad2f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002ad34  mov     rbx, rax
0x18002ad37  mov     [rsp+148h+var_D8], rax
0x18002ad3c  mov     r15, rax
0x18002ad3f  mov     ecx, [r14]
0x18002ad42  lea     esi, ds:1[rcx*2]
0x18002ad49  mov     rbp, r15
0x18002ad4c  mov     [r15], r12w
0x18002ad50  cmp     r12d, [r14]
0x18002ad53  jnb     short loc_18002ADBC
0x18002ad55  mov     ecx, r12d
0x18002ad58  mov     rax, [r14+8]
0x18002ad5c  movzx   edi, byte ptr [rax+rcx]
0x18002ad60  mov     rcx, r15; wchar_t *
0x18002ad63  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002ad68  mov     edx, esi
0x18002ad6a  sub     edx, eax; unsigned __int64
0x18002ad6c  mov     r9d, edi
0x18002ad6f  lea     r8, a02x; "%02x"
0x18002ad76  mov     rcx, rbp; wchar_t *
0x18002ad79  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002ad7e  mov     edi, eax
0x18002ad80  test    eax, eax
0x18002ad82  js      short loc_18002AD98
0x18002ad84  mov     rcx, rbp; wchar_t *
0x18002ad87  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002ad8c  mov     eax, eax
0x18002ad8e  lea     rbp, [rbp+rax*2+0]
0x18002ad93  inc     r12d
0x18002ad96  jmp     short loc_18002AD50
0x18002ad98  mov     r8d, 1522h; unsigned __int16
0x18002ad9e  lea     rdx, aLqs_0; "lqs"
0x18002ada5  mov     ecx, edi; int
0x18002ada7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002adac  nop
0x18002adad  mov     rcx, rbx; Block
0x18002adb0  call    cs:__imp_free
0x18002adb6  nop
0x18002adb7  jmp     loc_18002AE5C
0x18002adbc  xor     r12d, r12d
0x18002adbf  mov     [rbp+0], r12w
0x18002adc4  jmp     loc_18002AEEE
0x18002adc9  mov     r15, r14
0x18002adcc  jmp     loc_18002AEEE
0x18002add1  mov     r9d, [r9]
0x18002add4  lea     r8, aU; "%u"
0x18002addb  mov     edx, 40h ; '@'; unsigned __int64
0x18002ade0  lea     rcx, [rsp+148h+String]; wchar_t *
0x18002ade8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002aded  mov     edi, eax
0x18002adef  test    eax, eax
0x18002adf1  jns     loc_18002AEEE
0x18002adf7  mov     r8d, 13E2h; unsigned __int16
0x18002adfd  lea     rdx, aLqs_0; "lqs"
0x18002ae04  mov     ecx, eax; int
0x18002ae06  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ae0b  nop
0x18002ae0c  xor     ecx, ecx; Block
0x18002ae0e  call    cs:__imp_free
0x18002ae14  nop
0x18002ae15  jmp     short loc_18002AE5C
0x18002ae17  movzx   r9d, byte ptr [r9]
0x18002ae1b  lea     r8, a02x; "%02x"
0x18002ae22  mov     edx, 40h ; '@'; unsigned __int64
0x18002ae27  lea     rcx, [rsp+148h+String]; wchar_t *
0x18002ae2f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002ae34  mov     edi, eax
0x18002ae36  test    eax, eax
0x18002ae38  jns     loc_18002AEEE
0x18002ae3e  mov     r8d, 14F0h; unsigned __int16
0x18002ae44  lea     rdx, aLqs_0; "lqs"
0x18002ae4b  mov     ecx, eax; int
0x18002ae4d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ae52  nop
0x18002ae53  xor     ecx, ecx; Block
0x18002ae55  call    cs:__imp_free
0x18002ae5b  nop
0x18002ae5c  mov     eax, edi
0x18002ae5e  jmp     loc_18002AF5D
0x18002ae63  mov     r9d, [r9]
0x18002ae66  lea     r8, aD; "%d"
0x18002ae6d  mov     edx, 40h ; '@'; unsigned __int64
0x18002ae72  lea     rcx, [rsp+148h+String]; wchar_t *
0x18002ae7a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002ae7f  mov     edi, eax
0x18002ae81  test    eax, eax
0x18002ae83  jns     short loc_18002AEEE
0x18002ae85  mov     r8d, 13D8h; unsigned __int16
0x18002ae8b  lea     rdx, aLqs_0; "lqs"
0x18002ae92  mov     ecx, eax; int
0x18002ae94  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002ae99  nop
0x18002ae9a  xor     ecx, ecx; Block
0x18002ae9c  call    cs:__imp_free
0x18002aea2  nop
0x18002aea3  jmp     short loc_18002AE5C
0x18002aea5  movsx   r9d, word ptr [r9]
0x18002aea9  lea     r8, aD; "%d"
0x18002aeb0  mov     edx, 40h ; '@'; unsigned __int64
0x18002aeb5  lea     rcx, [rsp+148h+String]; wchar_t *
0x18002aebd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002aec2  mov     edi, eax
0x18002aec4  test    eax, eax
0x18002aec6  jns     short loc_18002AEEE
0x18002aec8  mov     r8d, 13CEh; unsigned __int16
0x18002aece  lea     rdx, aLqs_0; "lqs"
0x18002aed5  mov     ecx, eax; int
0x18002aed7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002aedc  nop
0x18002aedd  xor     ecx, ecx; Block
0x18002aedf  call    cs:__imp_free
0x18002aee5  nop
0x18002aee6  jmp     loc_18002AE5C
0x18002aeeb  mov     r15, r12
0x18002aeee  mov     r9, r13; lpFileName
0x18002aef1  mov     r8, r15; lpString
0x18002aef4  mov     rdx, [rsp+148h+lpKeyName]; lpKeyName
0x18002aef9  lea     rcx, AppName; "Properties"
0x18002af00  call    cs:__imp_WritePrivateProfileStringW
0x18002af06  test    eax, eax
0x18002af08  jnz     short loc_18002AF51
0x18002af0a  call    cs:__imp_GetLastError
0x18002af10  test    eax, eax
0x18002af12  jz      short loc_18002AF28
0x18002af14  mov     r8d, 50h ; 'P'; unsigned __int16
0x18002af1a  lea     rdx, aLqs_0; "lqs"
0x18002af21  mov     ecx, eax; int
0x18002af23  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18002af28  mov     r8d, 4A8h; unsigned __int16
0x18002af2e  lea     rdx, aLqs_0; "lqs"
0x18002af35  mov     edi, 0C00E0027h
0x18002af3a  mov     ecx, edi; int
0x18002af3c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002af41  nop
0x18002af42  mov     rcx, rbx; Block
0x18002af45  call    cs:__imp_free
0x18002af4b  nop
0x18002af4c  jmp     loc_18002AE5C
0x18002af51  mov     rcx, rbx; Block
0x18002af54  call    cs:__imp_free
0x18002af5a  nop
0x18002af5b  xor     eax, eax
0x18002af5d  mov     rcx, [rsp+148h+var_48]
0x18002af65  xor     rcx, rsp; StackCookie
0x18002af68  call    __security_check_cookie
0x18002af6d  mov     rbx, [rsp+148h+arg_10]
0x18002af75  add     rsp, 110h
0x18002af7c  pop     r15
0x18002af7e  pop     r14
0x18002af80  pop     r13
0x18002af82  pop     r12
0x18002af84  pop     rdi
0x18002af85  pop     rsi
0x18002af86  pop     rbp
0x18002af87  retn
```
