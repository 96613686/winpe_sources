# HandleDiscovery(ulong,uchar *)

- ea: `0x1800474a0`
- end: `0x18004797c`
- name: `?HandleDiscovery@@YAKKPEAE@Z`
- size: `1244`
- prototype: `__int64 __fastcall(size_t Size, unsigned __int8 *Src)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002d26`
- `0x180005665`
- `0x18001ad48`
- `0x18001aea4`
- `0x18001b128`
- `0x1800474a0`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180047710`
- `msvcrt!wcsstr` at `0x18004772f`
- `msvcrt!wcsstr` at `0x180047710`
- `msvcrt!wcsstr` at `0x18004772f`
- `msvcrt!wcschr` at `0x18004754d`
- `msvcrt!wcschr` at `0x1800475cb`
- `msvcrt!wcschr` at `0x180047603`
- `msvcrt!wcschr` at `0x18004764a`
- `msvcrt!wcschr` at `0x18004774a`
- `msvcrt!wcschr` at `0x180047765`
- `msvcrt!wcschr` at `0x180047780`
- `msvcrt!wcschr` at `0x18004779b`
- `msvcrt!wcschr` at `0x18004754d`
- `msvcrt!wcschr` at `0x1800475cb`
- `msvcrt!wcschr` at `0x180047603`
- `msvcrt!wcschr` at `0x18004764a`
- `msvcrt!wcschr` at `0x18004774a`
- `msvcrt!wcschr` at `0x180047765`
- `msvcrt!wcschr` at `0x180047780`
- `msvcrt!wcschr` at `0x18004779b`
- `msvcrt!swprintf_s` at `0x1800477c9`
- `msvcrt!swprintf_s` at `0x1800477c9`
- `ADVAPI32!RevertToSelf` at `0x180047840`
- `ADVAPI32!RevertToSelf` at `0x1800478fd`
- `ADVAPI32!RevertToSelf` at `0x180047919`
- `ADVAPI32!RevertToSelf` at `0x180047957`
- `ADVAPI32!RevertToSelf` at `0x180047840`
- `ADVAPI32!RevertToSelf` at `0x1800478fd`
- `ADVAPI32!RevertToSelf` at `0x180047919`
- `ADVAPI32!RevertToSelf` at `0x180047957`
- `ADVAPI32!ImpersonateAnonymousToken` at `0x1800477e4`
- `ADVAPI32!ImpersonateAnonymousToken` at `0x1800477e4`
- `KERNEL32!WriteFile` at `0x1800478cd`
- `KERNEL32!WriteFile` at `0x1800478cd`
- `KERNEL32!GetFileType` at `0x18004788c`
- `KERNEL32!GetFileType` at `0x18004788c`
- `KERNEL32!CreateFileW` at `0x18004781e`
- `KERNEL32!CreateFileW` at `0x18004781e`
- `KERNEL32!GetComputerNameW` at `0x18004751f`
- `KERNEL32!GetComputerNameW` at `0x18004751f`
- `KERNEL32!GetCurrentThread` at `0x1800477d5`
- `KERNEL32!GetCurrentThread` at `0x1800477d5`
- `KERNEL32!GetLastError` at `0x18004752f`
- `KERNEL32!GetLastError` at `0x180047832`
- `KERNEL32!GetLastError` at `0x18004790b`
- `KERNEL32!GetLastError` at `0x18004752f`
- `KERNEL32!GetLastError` at `0x180047832`
- `KERNEL32!GetLastError` at `0x18004790b`
- `KERNEL32!CloseHandle` at `0x18004796b`
- `KERNEL32!CloseHandle` at `0x18004796b`

## pseudocode

```c
__int64 __fastcall HandleDiscovery(size_t Size, unsigned __int8 *Src)
{
  DWORD LastError; // ebx
  size_t v3; // rdi
  wchar_t *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const wchar_t *v9; // rsi
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  const wchar_t *v12; // r14
  wchar_t *v13; // rax
  int v14; // ecx
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rax
  HANDLE CurrentThread; // rax
  HANDLE FileW; // rax
  void *v20; // rsi
  __int64 v21; // r8
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR Buffer[20]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t FileName[376]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Str[360]; // [rsp+360h] [rbp+260h] BYREF

  LastError = 0;
  v3 = (unsigned int)Size;
  nSize = 16;
  NumberOfBytesWritten = 0;
  if ( (unsigned int)Size >= 0x2C6 )
    return 87;
  memset_0(Str, 0, 0x2C8u);
  memcpy_0(Str, Src, v3);
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    v6 = wcschr(Str, 0x3Cu);
    if ( v6 )
    {
      v9 = v6 + 1;
      v10 = wcschr(v6 + 1, 0x3Eu);
      if ( v10 )
      {
        *v10 = 0;
        v11 = wcschr(v10 + 1, 0x3Cu);
        if ( v11 )
        {
          v12 = v11 + 1;
          v13 = wcschr(v11 + 1, 0x3Eu);
          if ( v13 )
          {
            *v13 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids,
                (_DWORD)v9,
                (__int64)v12);
            v14 = *v9 - 42;
            if ( *v9 == 42 )
              v14 = v9[1];
            if ( v14 )
            {
              v15 = -1;
              v16 = -1;
              do
                ++v16;
              while ( v12[v16] );
              v17 = -1;
              do
                ++v17;
              while ( v9[v17] );
              if ( (unsigned __int64)(v16 + v17 + 13) <= 0x177
                && !wcsstr(v9, L"..")
                && !wcsstr(v12, L"..")
                && !wcschr(v9, 0x5Cu)
                && !wcschr(v12, 0x5Cu)
                && !wcschr(v9, 0x2Fu)
                && !wcschr(v12, 0x2Fu) )
              {
                swprintf_s(FileName, 0x177u, L"\\\\%s\\mailslot\\%s", v9, v12);
                CurrentThread = GetCurrentThread();
                if ( ImpersonateAnonymousToken(CurrentThread) )
                {
                  FileW = CreateFileW(FileName, 0x40000000u, 2u, 0, 3u, 0x80u, 0);
                  v20 = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    LastError = GetLastError();
                    RevertToSelf();
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_SD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        (unsigned int)WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids,
                        (unsigned int)FileName,
                        LastError);
                  }
                  else
                  {
                    if ( GetFileType(FileW) < 4 )
                    {
                      RevertToSelf();
                      LastError = 87;
                    }
                    else
                    {
                      v21 = -1;
                      do
                        ++v21;
                      while ( Buffer[v21] );
                      if ( !WriteFile(v20, Buffer, 2 * v21 + 2, &NumberOfBytesWritten, 0) )
                        goto LABEL_53;
                      do
                        ++v15;
                      while ( Buffer[v15] );
                      if ( NumberOfBytesWritten == 2 * v15 + 2 )
                      {
                        RevertToSelf();
                      }
                      else
                      {
LABEL_53:
                        LastError = GetLastError();
                        RevertToSelf();
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                        {
                          WPP_SF_SD(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            16,
                            (unsigned int)WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids,
                            (unsigned int)FileName,
                            LastError);
                        }
                      }
                    }
                    CloseHandle(v20);
                  }
                  return LastError;
                }
                return GetLastError();
              }
            }
            return 87;
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            return 87;
          v8 = 13;
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            return 87;
          v8 = 12;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          return 87;
        v8 = 11;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        return 87;
      v8 = 10;
    }
    WPP_SF_(v7[2], v8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids);
    return 87;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x1800474a0  mov     [rsp-8+arg_10], rbx
0x1800474a5  push    rbp
0x1800474a6  push    rsi
0x1800474a7  push    rdi
0x1800474a8  push    r14
0x1800474aa  push    r15
0x1800474ac  lea     rbp, [rsp-540h]
0x1800474b4  sub     rsp, 640h
0x1800474bb  mov     rax, cs:__security_cookie
0x1800474c2  xor     rax, rsp
0x1800474c5  mov     [rbp+560h+var_30], rax
0x1800474cc  xor     ebx, ebx
0x1800474ce  mov     edi, ecx
0x1800474d0  mov     [rsp+660h+nSize], 10h
0x1800474d8  mov     rsi, rdx
0x1800474db  mov     [rsp+660h+NumberOfBytesWritten], ebx
0x1800474df  cmp     ecx, 2C6h
0x1800474e5  jb      short loc_1800474EF
0x1800474e7  lea     eax, [rbx+57h]
0x1800474ea  jmp     loc_180047594
0x1800474ef  xor     edx, edx; Val
0x1800474f1  lea     rcx, [rbp+560h+Str]; void *
0x1800474f8  mov     r8d, 2C8h; Size
0x1800474fe  call    memset_0
0x180047503  mov     r8, rdi; Size
0x180047506  lea     rcx, [rbp+560h+Str]; void *
0x18004750d  mov     rdx, rsi; Src
0x180047510  call    memcpy_0
0x180047515  lea     rdx, [rsp+660h+nSize]; nSize
0x18004751a  lea     rcx, [rsp+660h+Buffer]; lpBuffer
0x18004751f  call    cs:__imp_GetComputerNameW
0x180047526  nop     dword ptr [rax+rax+00h]
0x18004752b  test    eax, eax
0x18004752d  jnz     short loc_18004753F
0x18004752f  call    cs:__imp_GetLastError
0x180047536  nop     dword ptr [rax+rax+00h]
0x18004753b  mov     ebx, eax
0x18004753d  jmp     short loc_180047592
0x18004753f  mov     edi, 3Ch ; '<'
0x180047544  lea     rcx, [rbp+560h+Str]; Str
0x18004754b  mov     edx, edi; Ch
0x18004754d  call    cs:__imp_wcschr
0x180047554  nop     dword ptr [rax+rax+00h]
0x180047559  mov     rsi, rax
0x18004755c  test    rax, rax
0x18004755f  jnz     short loc_1800475BB
0x180047561  mov     rcx, cs:WPP_GLOBAL_Control
0x180047568  lea     rdi, WPP_GLOBAL_Control
0x18004756f  cmp     rcx, rdi
0x180047572  jz      short loc_18004758D
0x180047574  test    byte ptr [rcx+1Ch], 40h
0x180047578  jz      short loc_18004758D
0x18004757a  lea     edx, [rax+0Ah]
0x18004757d  mov     rcx, [rcx+10h]
0x180047581  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x180047588  call    WPP_SF_
0x18004758d  mov     ebx, 57h ; 'W'
0x180047592  mov     eax, ebx
0x180047594  mov     rcx, [rbp+560h+var_30]
0x18004759b  xor     rcx, rsp; StackCookie
0x18004759e  call    __security_check_cookie
0x1800475a3  mov     rbx, [rsp+660h+arg_10]
0x1800475ab  add     rsp, 640h
0x1800475b2  pop     r15
0x1800475b4  pop     r14
0x1800475b6  pop     rdi
0x1800475b7  pop     rsi
0x1800475b8  pop     rbp
0x1800475b9  retn
0x1800475bb  add     rsi, 2
0x1800475bf  mov     r15d, 3Eh ; '>'
0x1800475c5  mov     edx, r15d; Ch
0x1800475c8  mov     rcx, rsi; Str
0x1800475cb  call    cs:__imp_wcschr
0x1800475d2  nop     dword ptr [rax+rax+00h]
0x1800475d7  test    rax, rax
0x1800475da  jnz     short loc_1800475FA
0x1800475dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475e3  lea     rdi, WPP_GLOBAL_Control
0x1800475ea  cmp     rcx, rdi
0x1800475ed  jz      short loc_18004758D
0x1800475ef  test    byte ptr [rcx+1Ch], 40h
0x1800475f3  jz      short loc_18004758D
0x1800475f5  lea     edx, [rax+0Bh]
0x1800475f8  jmp     short loc_18004757D
0x1800475fa  mov     edx, edi; Ch
0x1800475fc  mov     [rax], bx
0x1800475ff  lea     rcx, [rax+2]; Str
0x180047603  call    cs:__imp_wcschr
0x18004760a  nop     dword ptr [rax+rax+00h]
0x18004760f  mov     r14, rax
0x180047612  test    rax, rax
0x180047615  jnz     short loc_180047640
0x180047617  mov     rcx, cs:WPP_GLOBAL_Control
0x18004761e  lea     rdi, WPP_GLOBAL_Control
0x180047625  cmp     rcx, rdi
0x180047628  jz      loc_18004758D
0x18004762e  test    byte ptr [rcx+1Ch], 40h
0x180047632  jz      loc_18004758D
0x180047638  lea     edx, [rax+0Ch]
0x18004763b  jmp     loc_18004757D
0x180047640  add     r14, 2
0x180047644  mov     edx, r15d; Ch
0x180047647  mov     rcx, r14; Str
0x18004764a  call    cs:__imp_wcschr
0x180047651  nop     dword ptr [rax+rax+00h]
0x180047656  test    rax, rax
0x180047659  jnz     short loc_180047684
0x18004765b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047662  lea     rdi, WPP_GLOBAL_Control
0x180047669  cmp     rcx, rdi
0x18004766c  jz      loc_18004758D
0x180047672  test    byte ptr [rcx+1Ch], 40h
0x180047676  jz      loc_18004758D
0x18004767c  lea     edx, [rax+0Dh]
0x18004767f  jmp     loc_18004757D
0x180047684  mov     [rax], bx
0x180047687  mov     rcx, cs:WPP_GLOBAL_Control
0x18004768e  lea     rdi, WPP_GLOBAL_Control
0x180047695  cmp     rcx, rdi
0x180047698  jz      short loc_1800476BD
0x18004769a  test    byte ptr [rcx+1Ch], 40h
0x18004769e  jz      short loc_1800476BD
0x1800476a0  mov     rcx, [rcx+10h]
0x1800476a4  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x1800476ab  mov     edx, 0Eh
0x1800476b0  mov     qword ptr [rsp+660h+dwCreationDisposition], r14
0x1800476b5  mov     r9, rsi
0x1800476b8  call    WPP_SF_SS
0x1800476bd  movzx   ecx, word ptr [rsi]
0x1800476c0  sub     ecx, 2Ah ; '*'
0x1800476c3  jnz     short loc_1800476CE
0x1800476c5  movzx   ecx, word ptr [rsi+2]
0x1800476c9  movzx   eax, bx
0x1800476cc  sub     ecx, eax
0x1800476ce  test    ecx, ecx
0x1800476d0  jz      loc_18004758D
0x1800476d6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800476da  mov     rcx, r15
0x1800476dd  inc     rcx
0x1800476e0  cmp     [r14+rcx*2], bx
0x1800476e5  jnz     short loc_1800476DD
0x1800476e7  mov     rax, r15
0x1800476ea  inc     rax
0x1800476ed  cmp     [rsi+rax*2], bx
0x1800476f1  jnz     short loc_1800476EA
0x1800476f3  add     rax, 0Dh
0x1800476f7  add     rax, rcx
0x1800476fa  cmp     rax, 177h
0x180047700  ja      loc_18004758D
0x180047706  lea     rdx, SubStr; ".."
0x18004770d  mov     rcx, rsi; Str
0x180047710  call    cs:__imp_wcsstr
0x180047717  nop     dword ptr [rax+rax+00h]
0x18004771c  test    rax, rax
0x18004771f  jnz     loc_18004758D
0x180047725  lea     rdx, SubStr; ".."
0x18004772c  mov     rcx, r14; Str
0x18004772f  call    cs:__imp_wcsstr
0x180047736  nop     dword ptr [rax+rax+00h]
0x18004773b  test    rax, rax
0x18004773e  jnz     loc_18004758D
0x180047744  lea     edx, [rax+5Ch]; Ch
0x180047747  mov     rcx, rsi; Str
0x18004774a  call    cs:__imp_wcschr
0x180047751  nop     dword ptr [rax+rax+00h]
0x180047756  test    rax, rax
0x180047759  jnz     loc_18004758D
0x18004775f  lea     edx, [rax+5Ch]; Ch
0x180047762  mov     rcx, r14; Str
0x180047765  call    cs:__imp_wcschr
0x18004776c  nop     dword ptr [rax+rax+00h]
0x180047771  test    rax, rax
0x180047774  jnz     loc_18004758D
0x18004777a  lea     edx, [rax+2Fh]; Ch
0x18004777d  mov     rcx, rsi; Str
0x180047780  call    cs:__imp_wcschr
0x180047787  nop     dword ptr [rax+rax+00h]
0x18004778c  test    rax, rax
0x18004778f  jnz     loc_18004758D
0x180047795  lea     edx, [rax+2Fh]; Ch
0x180047798  mov     rcx, r14; Str
0x18004779b  call    cs:__imp_wcschr
0x1800477a2  nop     dword ptr [rax+rax+00h]
0x1800477a7  test    rax, rax
0x1800477aa  jnz     loc_18004758D
0x1800477b0  mov     r9, rsi
0x1800477b3  mov     qword ptr [rsp+660h+dwCreationDisposition], r14
0x1800477b8  lea     r8, aSMailslotS; "\\\\%s\\mailslot\\%s"
0x1800477bf  mov     edx, 177h; BufferCount
0x1800477c4  lea     rcx, [rsp+660h+FileName]; Buffer
0x1800477c9  call    cs:__imp_swprintf_s
0x1800477d0  nop     dword ptr [rax+rax+00h]
0x1800477d5  call    cs:__imp_GetCurrentThread
0x1800477dc  nop     dword ptr [rax+rax+00h]
0x1800477e1  mov     rcx, rax; ThreadHandle
0x1800477e4  call    cs:__imp_ImpersonateAnonymousToken
0x1800477eb  nop     dword ptr [rax+rax+00h]
0x1800477f0  test    eax, eax
0x1800477f2  jz      loc_18004752F
0x1800477f8  xor     r9d, r9d; lpSecurityAttributes
0x1800477fb  mov     [rsp+660h+hTemplateFile], rbx; hTemplateFile
0x180047800  mov     [rsp+660h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180047808  lea     rcx, [rsp+660h+FileName]; lpFileName
0x18004780d  mov     edx, 40000000h; dwDesiredAccess
0x180047812  mov     [rsp+660h+dwCreationDisposition], 3; dwCreationDisposition
0x18004781a  lea     r8d, [r9+2]; dwShareMode
0x18004781e  call    cs:__imp_CreateFileW
0x180047825  nop     dword ptr [rax+rax+00h]
0x18004782a  mov     rsi, rax
0x18004782d  cmp     rax, r15
0x180047830  jnz     short loc_180047889
0x180047832  call    cs:__imp_GetLastError
0x180047839  nop     dword ptr [rax+rax+00h]
0x18004783e  mov     ebx, eax
0x180047840  call    cs:__imp_RevertToSelf
0x180047847  nop     dword ptr [rax+rax+00h]
0x18004784c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047853  cmp     rcx, rdi
0x180047856  jz      loc_180047592
0x18004785c  test    byte ptr [rcx+1Ch], 40h
0x180047860  jz      loc_180047592
0x180047866  mov     rcx, [rcx+10h]
0x18004786a  lea     r9, [rsp+660h+FileName]
0x18004786f  mov     edx, 0Fh
0x180047874  mov     [rsp+660h+dwCreationDisposition], ebx
0x180047878  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x18004787f  call    WPP_SF_SD
0x180047884  jmp     loc_180047592
0x180047889  mov     rcx, rsi; hFile
0x18004788c  call    cs:__imp_GetFileType
0x180047893  nop     dword ptr [rax+rax+00h]
0x180047898  cmp     eax, 4
0x18004789b  jb      loc_180047957
0x1800478a1  lea     rax, [rsp+660h+Buffer]
0x1800478a6  mov     r8, r15
0x1800478a9  inc     r8
0x1800478ac  cmp     [rax+r8*2], bx
0x1800478b1  jnz     short loc_1800478A9
0x1800478b3  lea     r8d, ds:2[r8*2]; nNumberOfBytesToWrite
0x1800478bb  mov     qword ptr [rsp+660h+dwCreationDisposition], rbx; lpOverlapped
0x1800478c0  lea     r9, [rsp+660h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800478c5  mov     rcx, rsi; hFile
0x1800478c8  lea     rdx, [rsp+660h+Buffer]; lpBuffer
0x1800478cd  call    cs:__imp_WriteFile
0x1800478d4  nop     dword ptr [rax+rax+00h]
0x1800478d9  test    eax, eax
0x1800478db  jz      short loc_18004790B
0x1800478dd  lea     rax, [rsp+660h+Buffer]
0x1800478e2  inc     r15
0x1800478e5  cmp     [rax+r15*2], bx
0x1800478ea  jnz     short loc_1800478E2
0x1800478ec  mov     eax, [rsp+660h+NumberOfBytesWritten]
0x1800478f0  lea     rcx, ds:2[r15*2]
0x1800478f8  cmp     rax, rcx
0x1800478fb  jnz     short loc_18004790B
0x1800478fd  call    cs:__imp_RevertToSelf
0x180047904  nop     dword ptr [rax+rax+00h]
0x180047909  jmp     short loc_180047968
0x18004790b  call    cs:__imp_GetLastError
0x180047912  nop     dword ptr [rax+rax+00h]
0x180047917  mov     ebx, eax
0x180047919  call    cs:__imp_RevertToSelf
0x180047920  nop     dword ptr [rax+rax+00h]
0x180047925  mov     rcx, cs:WPP_GLOBAL_Control
0x18004792c  cmp     rcx, rdi
0x18004792f  jz      short loc_180047968
0x180047931  test    byte ptr [rcx+1Ch], 40h
0x180047935  jz      short loc_180047968
0x180047937  mov     rcx, [rcx+10h]
0x18004793b  lea     r9, [rsp+660h+FileName]
0x180047940  mov     edx, 10h
0x180047945  mov     [rsp+660h+dwCreationDisposition], ebx
0x180047949  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x180047950  call    WPP_SF_SD
0x180047955  jmp     short loc_180047968
0x180047957  call    cs:__imp_RevertToSelf
0x18004795e  nop     dword ptr [rax+rax+00h]
0x180047963  mov     ebx, 57h ; 'W'
0x180047968  mov     rcx, rsi; hObject
0x18004796b  call    cs:__imp_CloseHandle
0x180047972  nop     dword ptr [rax+rax+00h]
0x180047977  jmp     loc_180047592
```
