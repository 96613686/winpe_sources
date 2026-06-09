# sub_1400FCCB0

- ea: `0x1400fccb0`
- end: `0x1400fd058`
- name: `sub_1400FCCB0`
- size: `936`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003f4d0`
- `0x140056aa0`
- `0x140059f00`
- `0x140061b00`
- `0x140069060`
- `0x14006d4e0`
- `0x140079a10`
- `0x140081e60`
- `0x140086090`
- `0x140086c50`
- `0x1400fccb0`
- `0x14011cb20`
- `0x14011fa70`
- `0x140152ce0`
- `0x140292ff0`
- `0x14037b2f0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400fcd3d`
- `KERNEL32!GetModuleFileNameW` at `0x1400fce21`
- `KERNEL32!GetModuleFileNameW` at `0x1400fcd3d`
- `KERNEL32!GetModuleFileNameW` at `0x1400fce21`
- `KERNEL32!GetSystemDirectoryW` at `0x1400fcdf6`
- `KERNEL32!GetSystemDirectoryW` at `0x1400fcdf6`
- `KERNEL32!GetWindowsDirectoryW` at `0x140171f8a`
- `KERNEL32!GetWindowsDirectoryW` at `0x140171f8a`
- `SHELL32!SHGetFolderPathW` at `0x1400fce50`
- `SHELL32!SHGetFolderPathW` at `0x1400fce7f`
- `SHELL32!SHGetFolderPathW` at `0x1400fceae`
- `SHELL32!SHGetFolderPathW` at `0x1400fcedd`
- `SHELL32!SHGetFolderPathW` at `0x1401540b4`
- `SHELL32!SHGetFolderPathW` at `0x1401540e3`
- `SHELL32!SHGetFolderPathW` at `0x140154112`
- `SHELL32!SHGetFolderPathW` at `0x140171f67`
- `SHELL32!SHGetFolderPathW` at `0x140171fb1`
- `SHELL32!SHGetFolderPathW` at `0x140172051`
- `SHELL32!SHGetFolderPathW` at `0x140172080`
- `SHELL32!SHGetFolderPathW` at `0x1401720af`
- `SHELL32!SHGetFolderPathW` at `0x1401720de`
- `SHELL32!SHGetFolderPathW` at `0x1401722f1`
- `SHELL32!SHGetFolderPathW` at `0x1400fce50`
- `SHELL32!SHGetFolderPathW` at `0x1400fce7f`
- `SHELL32!SHGetFolderPathW` at `0x1400fceae`
- `SHELL32!SHGetFolderPathW` at `0x1400fcedd`
- `SHELL32!SHGetFolderPathW` at `0x1401540b4`
- `SHELL32!SHGetFolderPathW` at `0x1401540e3`
- `SHELL32!SHGetFolderPathW` at `0x140154112`
- `SHELL32!SHGetFolderPathW` at `0x140171f67`
- `SHELL32!SHGetFolderPathW` at `0x140171fb1`
- `SHELL32!SHGetFolderPathW` at `0x140172051`
- `SHELL32!SHGetFolderPathW` at `0x140172080`
- `SHELL32!SHGetFolderPathW` at `0x1401720af`
- `SHELL32!SHGetFolderPathW` at `0x1401720de`
- `SHELL32!SHGetFolderPathW` at `0x1401722f1`
- `ole32!CoTaskMemFree` at `0x140172248`
- `ole32!CoTaskMemFree` at `0x1401722d2`
- `ole32!CoTaskMemFree` at `0x140172248`
- `ole32!CoTaskMemFree` at `0x1401722d2`

## string_xrefs

- `0x14017210f`: `SystemTemp`

## pseudocode

```c
__int64 __fastcall sub_1400FCCB0(int a1, void *a2)
{
  PWSTR *p_Src; // rbx
  WCHAR *pszPath; // rdi
  unsigned __int64 v6; // rcx
  PWSTR *v7; // rcx
  PWSTR *v9; // rcx
  __int64 v10; // rax
  PWSTR *v11; // rdx
  _BYTE v12[32]; // [rsp+0h] [rbp-4A8h] BYREF
  _QWORD v13[4]; // [rsp+30h] [rbp-478h] BYREF
  PWSTR v14; // [rsp+50h] [rbp-458h] BYREF
  char v15; // [rsp+60h] [rbp-448h] BYREF
  const char *v16; // [rsp+70h] [rbp-438h]
  __int64 v17; // [rsp+78h] [rbp-430h]
  const char *v18; // [rsp+80h] [rbp-428h]
  __int64 v19; // [rsp+88h] [rbp-420h]
  const char *v20; // [rsp+90h] [rbp-418h]
  __int64 v21; // [rsp+98h] [rbp-410h]
  const char *v22; // [rsp+A0h] [rbp-408h]
  __int64 v23; // [rsp+A8h] [rbp-400h]
  const wchar_t *v24; // [rsp+B0h] [rbp-3F8h]
  __int64 v25; // [rsp+B8h] [rbp-3F0h]
  const wchar_t *v26; // [rsp+C0h] [rbp-3E8h]
  __int64 v27; // [rsp+C8h] [rbp-3E0h]
  const wchar_t *v28; // [rsp+D0h] [rbp-3D8h]
  __int64 v29; // [rsp+D8h] [rbp-3D0h]
  char v30; // [rsp+E0h] [rbp-3C8h] BYREF
  char v31; // [rsp+F0h] [rbp-3B8h] BYREF
  PWSTR v32; // [rsp+100h] [rbp-3A8h] BYREF
  _BYTE v33[24]; // [rsp+110h] [rbp-398h] BYREF
  PWSTR ppszPath[3]; // [rsp+128h] [rbp-380h] BYREF
  char v35; // [rsp+140h] [rbp-368h] BYREF
  char v36; // [rsp+150h] [rbp-358h] BYREF
  char v37; // [rsp+160h] [rbp-348h] BYREF
  char v38; // [rsp+170h] [rbp-338h] BYREF
  char v39; // [rsp+180h] [rbp-328h] BYREF
  char v40; // [rsp+190h] [rbp-318h] BYREF
  char v41; // [rsp+1A0h] [rbp-308h] BYREF
  char v42; // [rsp+1B0h] [rbp-2F8h] BYREF
  char v43; // [rsp+1C0h] [rbp-2E8h] BYREF
  char v44; // [rsp+1D0h] [rbp-2D8h] BYREF
  char v45; // [rsp+1E0h] [rbp-2C8h] BYREF
  char v46; // [rsp+1F0h] [rbp-2B8h] BYREF
  char v47; // [rsp+200h] [rbp-2A8h] BYREF
  char v48; // [rsp+210h] [rbp-298h] BYREF
  char v49; // [rsp+220h] [rbp-288h] BYREF
  __int128 v50; // [rsp+230h] [rbp-278h] BYREF
  __int64 v51; // [rsp+240h] [rbp-268h]
  __int128 Src; // [rsp+250h] [rbp-258h] BYREF
  __int64 v53; // [rsp+260h] [rbp-248h]
  WCHAR Filename[260]; // [rsp+270h] [rbp-238h] BYREF
  __int64 v55; // [rsp+478h] [rbp-30h]

  LODWORD(p_Src) = 0;
  pszPath = Filename;
  memset(Filename, 0, sizeof(Filename));
  Src = 0;
  v53 = 0;
  sub_14003F4D0(&Src);
  switch ( a1 )
  {
    case 1:
      LODWORD(p_Src) = 0;
      pszPath = Filename;
      if ( GetModuleFileNameW(0, Filename, 0x104u) )
      {
        p_Src = (PWSTR *)&v49;
        goto LABEL_4;
      }
      goto LABEL_8;
    case 2:
      pszPath = Filename;
      if ( GetModuleFileNameW(&_ImageBase, Filename, 0x104u) )
      {
        p_Src = (PWSTR *)&v48;
        goto LABEL_4;
      }
LABEL_66:
      LODWORD(p_Src) = 0;
      goto LABEL_8;
    case 3:
    case 4:
    case 5:
    case 6:
    case 7:
    case 9:
      goto LABEL_8;
    case 8:
      LODWORD(p_Src) = 0;
      if ( SHGetFolderPathW(0, 16, 0, 0, Filename) >= 0 )
      {
        p_Src = (PWSTR *)&v31;
        goto LABEL_4;
      }
      goto LABEL_8;
    case 10:
      pszPath = (WCHAR *)&v50;
      v50 = 0;
      v51 = 0;
      sub_14003F4D0(&v50);
      sub_140081E60(3, &v50);
      p_Src = (PWSTR *)v33;
      sub_140069060(&v50);
      sub_140069060(v33);
      sub_14006D4E0(&Src, ppszPath);
      sub_140086C50(ppszPath);
      v9 = (PWSTR *)v33;
LABEL_27:
      sub_140086C50(v9);
      goto LABEL_5;
    default:
      switch ( a1 )
      {
        case 'e':
          GetWindowsDirectoryW(Filename, 0x104u);
          p_Src = (PWSTR *)&v47;
          goto LABEL_4;
        case 'f':
          GetSystemDirectoryW(Filename, 0x104u);
          p_Src = (PWSTR *)&v46;
          goto LABEL_4;
        case 'g':
          goto LABEL_50;
        case 'h':
          goto LABEL_37;
        case 'i':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 38, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v43;
          goto LABEL_4;
        case 'j':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 32, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v42;
          goto LABEL_4;
        case 'k':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 23, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v41;
          goto LABEL_4;
        case 'l':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 2, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v40;
          goto LABEL_4;
        case 'm':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 24, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v39;
          goto LABEL_4;
        case 'n':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 7, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v38;
          goto LABEL_4;
        case 'o':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 26, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v37;
          goto LABEL_4;
        case 'p':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 28, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v35;
          goto LABEL_4;
        case 'q':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 35, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v36;
          goto LABEL_4;
        case 'r':
          ppszPath[0] = 0;
          if ( SHGetKnownFolderPath(&stru_140397020, 0, 0, ppszPath) < 0 )
            goto LABEL_64;
          v32 = ppszPath[0];
          if ( !ppszPath[0] )
            goto LABEL_74;
          v10 = ((__int64 (*)(void))sub_14011CB20)();
          v11 = &v32;
          goto LABEL_70;
        case 's':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 25, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v30;
          goto LABEL_4;
        case 't':
          if ( !(unsigned __int8)sub_140081E60(111, &Src) )
            goto LABEL_66;
          v28 = L"Microsoft";
          v29 = 9;
          p_Src = (PWSTR *)&Src;
          pszPath = (WCHAR *)v33;
          sub_140061B00(&Src);
          v26 = L"Internet Explorer";
          v27 = 17;
          sub_140061B00(v33);
          v24 = L"Quick Launch";
          v25 = 12;
          sub_140061B00(ppszPath);
          sub_14006D4E0(&Src, &v50);
          sub_140086C50(&v50);
          v9 = ppszPath;
          goto LABEL_27;
        case 'u':
          if ( !(unsigned __int8)sub_140081E60(116, &Src) )
            goto LABEL_66;
          v22 = "U";
          v23 = 11;
          pszPath = (WCHAR *)&Src;
          p_Src = ppszPath;
          sub_140061B00(&Src);
          v20 = "T";
          v21 = 7;
          goto LABEL_24;
        case 'v':
          if ( !(unsigned __int8)sub_140081E60(116, &Src) )
            goto LABEL_66;
          v18 = "U";
          v19 = 11;
          pszPath = (WCHAR *)&Src;
          p_Src = ppszPath;
          sub_140061B00(&Src);
          v16 = "I";
          v17 = 20;
LABEL_24:
          sub_140061B00(ppszPath);
          sub_14006D4E0(&Src, &v50);
          sub_140086C50(&v50);
          v7 = ppszPath;
          goto LABEL_6;
        case 'w':
          LODWORD(p_Src) = 0;
          if ( SHGetFolderPathW(0, 20, 0, 0, Filename) < 0 )
            goto LABEL_8;
          p_Src = (PWSTR *)&v15;
          goto LABEL_4;
        case 'x':
          if ( (int)sub_140086090() < 3 )
            goto LABEL_66;
          ppszPath[0] = 0;
          if ( SHGetKnownFolderPath(&rfid, 0, 0, ppszPath) < 0 )
          {
LABEL_64:
            if ( ppszPath[0] )
              CoTaskMemFree(ppszPath[0]);
            goto LABEL_66;
          }
          v14 = ppszPath[0];
          if ( !ppszPath[0] )
LABEL_74:
            BUG();
          v10 = ((__int64 (*)(void))sub_14011CB20)();
          v11 = &v14;
LABEL_70:
          v11[1] = (PWSTR)v10;
          pszPath = (WCHAR *)&v50;
          sub_140056AA0(&v50);
          sub_14006D4E0(&Src, &v50);
          sub_140086C50(&v50);
          if ( ppszPath[0] )
            CoTaskMemFree(ppszPath[0]);
          break;
        case 'y':
          if ( !(unsigned __int8)sub_140081E60(101, &Src)
            || (v13[2] = L"SystemTemp",
                v13[3] = 10,
                pszPath = (WCHAR *)&Src,
                p_Src = (PWSTR *)&v50,
                sub_140061B00(&Src),
                sub_14006D4E0(&Src, &v50),
                sub_140086C50(&v50),
                !(unsigned __int8)sub_140292FF0((LPCWSTR)&Src)) )
          {
            if ( !(unsigned __int8)sub_140081E60(103, &Src) || !(unsigned __int8)sub_140292FF0((LPCWSTR)&Src) )
              goto LABEL_66;
          }
          goto LABEL_7;
        case 'z':
          ppszPath[0] = 0;
          if ( SHGetKnownFolderPath(&stru_140397010, 0, 0, ppszPath) < 0 )
            goto LABEL_64;
          v13[0] = ppszPath[0];
          if ( !ppszPath[0] )
            goto LABEL_74;
          v10 = ((__int64 (*)(void))sub_14011CB20)();
          v11 = (PWSTR *)v13;
          goto LABEL_70;
        default:
          goto LABEL_8;
      }
      break;
  }
LABEL_7:
  sub_140059F00(a2);
  LOBYTE(p_Src) = 1;
LABEL_8:
  while ( 1 )
  {
    sub_140086C50(&Src);
    if ( _security_cookie == ((unsigned __int64)v12 ^ v55) )
      return (unsigned int)p_Src;
    v6 = (unsigned __int64)v12 ^ v55;
LABEL_37:
    if ( (unsigned int)sub_140079A10(v6) )
    {
      LODWORD(p_Src) = 0;
      if ( SHGetFolderPathW(0, 42, 0, 0, pszPath) >= 0 )
      {
        p_Src = (PWSTR *)&v45;
        goto LABEL_4;
      }
    }
    else
    {
LABEL_50:
      LODWORD(p_Src) = 0;
      if ( SHGetFolderPathW(0, 38, 0, 0, pszPath) >= 0 )
      {
        p_Src = (PWSTR *)&v44;
LABEL_4:
        *p_Src = pszPath;
        p_Src[1] = (PWSTR)sub_14011CB20(pszPath);
        pszPath = (WCHAR *)&v50;
        sub_140056AA0(&v50);
        sub_14006D4E0(&Src, &v50);
LABEL_5:
        v7 = (PWSTR *)pszPath;
LABEL_6:
        sub_140086C50(v7);
        goto LABEL_7;
      }
    }
  }
}

```

## disassembly

```asm
0x1400fccb0  push    r15
0x1400fccb2  push    r14
0x1400fccb4  push    rsi
0x1400fccb5  push    rdi
0x1400fccb6  push    rbx
0x1400fccb7  sub     rsp, 480h
0x1400fccbe  mov     rsi, rdx
0x1400fccc1  mov     r14d, ecx
0x1400fccc4  mov     rax, cs:__security_cookie
0x1400fcccb  xor     rax, rsp
0x1400fccce  mov     [rsp+4A8h+var_30], rax
0x1400fccd6  xor     ebx, ebx
0x1400fccd8  lea     rdi, [rsp+4A8h+Filename]
0x1400fcce0  mov     r8d, 208h; Size
0x1400fcce6  mov     rcx, rdi; Dst
0x1400fcce9  xor     edx, edx; Val
0x1400fcceb  call    memset
0x1400fccf0  xorps   xmm0, xmm0
0x1400fccf3  lea     rcx, [rsp+4A8h+Src]
0x1400fccfb  movaps  xmmword ptr [rcx], xmm0
0x1400fccfe  mov     qword ptr [rcx+10h], 0
0x1400fcd06  call    sub_14003F4D0
0x1400fcd0b  lea     eax, [r14-1]; switch 10 cases
0x1400fcd0f  cmp     eax, 9
0x1400fcd12  ja      def_1400FCD26; jumptable 00000001400FCD26 default case
0x1400fcd18  lea     rcx, jpt_1400FCD26
0x1400fcd1f  movsxd  rax, ds:(jpt_1400FCD26 - 1403CAA2Ch)[rcx+rax*4]
0x1400fcd23  add     rax, rcx
0x1400fcd26  jmp     rax; switch jump
0x1400fcd28  xor     ebx, ebx; jumptable 00000001400FCD26 case 1
0x1400fcd2a  lea     rdi, [rsp+4A8h+Filename]
0x1400fcd32  xor     ecx, ecx; hModule
0x1400fcd34  mov     rdx, rdi; lpFilename
0x1400fcd37  mov     r8d, 104h; nSize
0x1400fcd3d  call    cs:GetModuleFileNameW
0x1400fcd43  test    eax, eax
0x1400fcd45  jz      short def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fcd47  lea     rbx, [rsp+4A8h+var_288]
0x1400fcd4f  mov     [rbx], rdi
0x1400fcd52  mov     rcx, rdi
0x1400fcd55  call    sub_14011CB20
0x1400fcd5a  mov     [rbx+8], rax
0x1400fcd5e  lea     rdi, [rsp+4A8h+var_278]
0x1400fcd66  mov     rcx, rdi
0x1400fcd69  mov     rdx, rbx
0x1400fcd6c  call    sub_140056AA0
0x1400fcd71  lea     rcx, [rsp+4A8h+Src]
0x1400fcd79  mov     rdx, rdi
0x1400fcd7c  call    sub_14006D4E0
0x1400fcd81  mov     rcx, rdi
0x1400fcd84  call    sub_140086C50
0x1400fcd89  lea     rdx, [rsp+4A8h+Src]
0x1400fcd91  mov     rcx, rsi; Src
0x1400fcd94  call    sub_140059F00
0x1400fcd99  mov     bl, 1
0x1400fcd9b  lea     rcx, [rsp+4A8h+Src]; jumptable 00000001400FCD26 cases 3-7,9
0x1400fcda3  call    sub_140086C50
0x1400fcda8  mov     rax, [rsp+4A8h+var_30]
0x1400fcdb0  xor     rax, rsp
0x1400fcdb3  mov     rcx, cs:__security_cookie
0x1400fcdba  cmp     rcx, rax
0x1400fcdbd  jnz     loc_140171F36
0x1400fcdc3  mov     eax, ebx
0x1400fcdc5  add     rsp, 480h
0x1400fcdcc  pop     rbx
0x1400fcdcd  pop     rdi
0x1400fcdce  pop     rsi
0x1400fcdcf  pop     r14
0x1400fcdd1  pop     r15
0x1400fcdd3  retn
0x1400fcdd4  add     r14d, 0FFFFFF9Bh; jumptable 00000001400FCD26 default case
0x1400fcdd8  cmp     r14d, 15h
0x1400fcddc  ja      short def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fcdde  lea     rax, jpt_1400FCDEC
0x1400fcde5  movsxd  rcx, ds:(jpt_1400FCDEC - 1403CAA54h)[rax+r14*4]
0x1400fcde9  add     rcx, rax
0x1400fcdec  jmp     rcx; switch jump
0x1400fcdee  mov     rcx, rdi; jumptable 00000001400FCDEC case 102
0x1400fcdf1  mov     edx, 104h; uSize
0x1400fcdf6  call    cs:GetSystemDirectoryW
0x1400fcdfc  lea     rbx, [rsp+4A8h+var_2B8]
0x1400fce04  jmp     loc_1400FCD4F
0x1400fce09  lea     rcx, __ImageBase; jumptable 00000001400FCD26 case 2
0x1400fce10  lea     rdi, [rsp+4A8h+Filename]
0x1400fce18  mov     rdx, rdi; lpFilename
0x1400fce1b  mov     r8d, 104h; nSize
0x1400fce21  call    cs:GetModuleFileNameW
0x1400fce27  test    eax, eax
0x1400fce29  jz      loc_14017224E
0x1400fce2f  lea     rbx, [rsp+4A8h+var_298]
0x1400fce37  jmp     loc_1400FCD4F
0x1400fce3c  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCD26 case 8
0x1400fce41  xor     ebx, ebx
0x1400fce43  xor     ecx, ecx; hwnd
0x1400fce45  mov     edx, 10h; csidl
0x1400fce4a  xor     r8d, r8d; hToken
0x1400fce4d  xor     r9d, r9d; dwFlags
0x1400fce50  call    cs:SHGetFolderPathW
0x1400fce56  test    eax, eax
0x1400fce58  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fce5e  lea     rbx, [rsp+4A8h+var_3B8]
0x1400fce66  jmp     loc_1400FCD4F
0x1400fce6b  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 112
0x1400fce70  xor     ebx, ebx
0x1400fce72  xor     ecx, ecx; hwnd
0x1400fce74  mov     edx, 1Ch; csidl
0x1400fce79  xor     r8d, r8d; hToken
0x1400fce7c  xor     r9d, r9d; dwFlags
0x1400fce7f  call    cs:SHGetFolderPathW
0x1400fce85  test    eax, eax
0x1400fce87  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fce8d  lea     rbx, [rsp+4A8h+var_368]
0x1400fce95  jmp     loc_1400FCD4F
0x1400fce9a  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 111
0x1400fce9f  xor     ebx, ebx
0x1400fcea1  xor     ecx, ecx; hwnd
0x1400fcea3  mov     edx, 1Ah; csidl
0x1400fcea8  xor     r8d, r8d; hToken
0x1400fceab  xor     r9d, r9d; dwFlags
0x1400fceae  call    cs:SHGetFolderPathW
0x1400fceb4  test    eax, eax
0x1400fceb6  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fcebc  lea     rbx, [rsp+4A8h+var_348]
0x1400fcec4  jmp     loc_1400FCD4F
0x1400fcec9  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 113
0x1400fcece  xor     ebx, ebx
0x1400fced0  xor     ecx, ecx; hwnd
0x1400fced2  mov     edx, 23h ; '#'; csidl
0x1400fced7  xor     r8d, r8d; hToken
0x1400fceda  xor     r9d, r9d; dwFlags
0x1400fcedd  call    cs:SHGetFolderPathW
0x1400fcee3  test    eax, eax
0x1400fcee5  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1400fceeb  lea     rbx, [rsp+4A8h+var_358]
0x1400fcef3  jmp     loc_1400FCD4F
0x1400fcef8  lea     rdx, [rsp+4A8h+Src]; jumptable 00000001400FCDEC case 117
0x1400fcf00  mov     ecx, 74h ; 't'
0x1400fcf05  call    sub_140081E60
0x1400fcf0a  test    al, al
0x1400fcf0c  jz      loc_14017224E
0x1400fcf12  lea     rax, aU; "U"
0x1400fcf19  lea     r8, [rsp+4A8h+var_408]
0x1400fcf21  mov     [r8], rax
0x1400fcf24  mov     qword ptr [r8+8], 0Bh
0x1400fcf2c  lea     rdi, [rsp+4A8h+Src]
0x1400fcf34  lea     rbx, [rsp+4A8h+ppszPath]
0x1400fcf3c  mov     rcx, rdi; Src
0x1400fcf3f  mov     rdx, rbx
0x1400fcf42  call    sub_140061B00
0x1400fcf47  lea     rax, aT_1; "T"
0x1400fcf4e  lea     r8, [rsp+4A8h+var_418]
0x1400fcf56  mov     [r8], rax
0x1400fcf59  mov     qword ptr [r8+8], 7
0x1400fcf61  lea     r14, [rsp+4A8h+var_278]
0x1400fcf69  mov     rcx, rbx; Src
0x1400fcf6c  mov     rdx, r14
0x1400fcf6f  call    sub_140061B00
0x1400fcf74  mov     rcx, rdi
0x1400fcf77  mov     rdx, r14
0x1400fcf7a  call    sub_14006D4E0
0x1400fcf7f  mov     rcx, r14
0x1400fcf82  call    sub_140086C50
0x1400fcf87  mov     rcx, rbx
0x1400fcf8a  jmp     loc_1400FCD84
0x1400fcf8f  lea     rdx, [rsp+4A8h+Src]; jumptable 00000001400FCDEC case 116
0x1400fcf97  mov     ecx, 6Fh ; 'o'
0x1400fcf9c  call    sub_140081E60
0x1400fcfa1  test    al, al
0x1400fcfa3  jz      loc_14017224E
0x1400fcfa9  lea     rax, aMicrosoft; "Microsoft"
0x1400fcfb0  lea     r8, [rsp+4A8h+var_3D8]
0x1400fcfb8  mov     [r8], rax
0x1400fcfbb  mov     qword ptr [r8+8], 9
0x1400fcfc3  lea     rbx, [rsp+4A8h+Src]
0x1400fcfcb  lea     rdi, [rsp+4A8h+var_398]
0x1400fcfd3  mov     rcx, rbx; Src
0x1400fcfd6  mov     rdx, rdi
0x1400fcfd9  call    sub_140061B00
0x1400fcfde  lea     rax, aInternetExplor; "Internet Explorer"
0x1400fcfe5  lea     r8, [rsp+4A8h+var_3E8]
0x1400fcfed  mov     [r8], rax
0x1400fcff0  mov     qword ptr [r8+8], 11h
0x1400fcff8  lea     r14, [rsp+4A8h+ppszPath]
0x1400fd000  mov     rcx, rdi; Src
0x1400fd003  mov     rdx, r14
0x1400fd006  call    sub_140061B00
0x1400fd00b  lea     rax, aQuickLaunch; "Quick Launch"
0x1400fd012  lea     r8, [rsp+4A8h+var_3F8]
0x1400fd01a  mov     [r8], rax
0x1400fd01d  mov     qword ptr [r8+8], 0Ch
0x1400fd025  lea     r15, [rsp+4A8h+var_278]
0x1400fd02d  mov     rcx, r14; Src
0x1400fd030  mov     rdx, r15
0x1400fd033  call    sub_140061B00
0x1400fd038  mov     rcx, rbx
0x1400fd03b  mov     rdx, r15
0x1400fd03e  call    sub_14006D4E0
0x1400fd043  mov     rcx, r15
0x1400fd046  call    sub_140086C50
0x1400fd04b  mov     rcx, r14
0x1400fd04e  call    sub_140086C50
0x1400fd053  jmp     loc_1400FCD81
0x140154035  lea     rdx, [rsp+4A8h+Src]; jumptable 00000001400FCDEC case 118
0x14015403d  mov     ecx, 74h ; 't'
0x140154042  call    sub_140081E60
0x140154047  test    al, al
0x140154049  jz      loc_14017224E
0x14015404f  lea     rax, aU; "U"
0x140154056  lea     r8, [rsp+4A8h+var_428]
0x14015405e  mov     [r8], rax
0x140154061  mov     qword ptr [r8+8], 0Bh
0x140154069  lea     rdi, [rsp+4A8h+Src]
0x140154071  lea     rbx, [rsp+4A8h+ppszPath]
0x140154079  mov     rcx, rdi; Src
0x14015407c  mov     rdx, rbx
0x14015407f  call    sub_140061B00
0x140154084  lea     rax, aI_2; "I"
0x14015408b  lea     r8, [rsp+4A8h+var_438]
0x140154090  mov     [r8], rax
0x140154093  mov     qword ptr [r8+8], 14h
0x14015409b  jmp     loc_1400FCF61
0x1401540a0  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 107
0x1401540a5  xor     ebx, ebx
0x1401540a7  xor     ecx, ecx; hwnd
0x1401540a9  mov     edx, 17h; csidl
0x1401540ae  xor     r8d, r8d; hToken
0x1401540b1  xor     r9d, r9d; dwFlags
0x1401540b4  call    cs:SHGetFolderPathW
0x1401540ba  test    eax, eax
0x1401540bc  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1401540c2  lea     rbx, [rsp+4A8h+var_308]
0x1401540ca  jmp     loc_1400FCD4F
0x1401540cf  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 115
0x1401540d4  xor     ebx, ebx
0x1401540d6  xor     ecx, ecx; hwnd
0x1401540d8  mov     edx, 19h; csidl
0x1401540dd  xor     r8d, r8d; hToken
0x1401540e0  xor     r9d, r9d; dwFlags
0x1401540e3  call    cs:SHGetFolderPathW
0x1401540e9  test    eax, eax
0x1401540eb  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x1401540f1  lea     rbx, [rsp+4A8h+var_3C8]
0x1401540f9  jmp     loc_1400FCD4F
0x1401540fe  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 108
0x140154103  xor     ebx, ebx
0x140154105  xor     ecx, ecx; hwnd
0x140154107  mov     edx, 2; csidl
0x14015410c  xor     r8d, r8d; hToken
0x14015410f  xor     r9d, r9d; dwFlags
0x140154112  call    cs:SHGetFolderPathW
0x140154118  test    eax, eax
0x14015411a  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x140154120  lea     rbx, [rsp+4A8h+var_318]
0x140154128  jmp     loc_1400FCD4F
0x140171f36  mov     rcx, [rsp+4A8h+var_30]
0x140171f3e  xor     rcx, rsp; StackCookie
0x140171f41  call    __security_check_cookie
0x140171f46  call    sub_140079A10; jumptable 00000001400FCDEC case 104
0x140171f4b  test    eax, eax
0x140171f4d  jz      loc_1401720CA; jumptable 00000001400FCDEC case 103
0x140171f53  mov     [rsp+4A8h+pszPath], rdi; pszPath
0x140171f58  xor     ebx, ebx
0x140171f5a  xor     ecx, ecx; hwnd
0x140171f5c  mov     edx, 2Ah ; '*'; csidl
0x140171f61  xor     r8d, r8d; hToken
0x140171f64  xor     r9d, r9d; dwFlags
0x140171f67  call    cs:SHGetFolderPathW
0x140171f6d  test    eax, eax
0x140171f6f  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x140171f75  lea     rbx, [rsp+4A8h+var_2C8]
0x140171f7d  jmp     loc_1400FCD4F
0x140171f82  mov     rcx, rdi; jumptable 00000001400FCDEC case 101
0x140171f85  mov     edx, 104h; uSize
0x140171f8a  call    cs:GetWindowsDirectoryW
0x140171f90  lea     rbx, [rsp+4A8h+var_2A8]
0x140171f98  jmp     loc_1400FCD4F
0x140171f9d  mov     [rsp+4A8h+pszPath], rdi; jumptable 00000001400FCDEC case 105
0x140171fa2  xor     ebx, ebx
0x140171fa4  xor     ecx, ecx; hwnd
0x140171fa6  mov     edx, 26h ; '&'; csidl
0x140171fab  xor     r8d, r8d; hToken
0x140171fae  xor     r9d, r9d; dwFlags
0x140171fb1  call    cs:SHGetFolderPathW
0x140171fb7  test    eax, eax
0x140171fb9  js      def_1400FCDEC; jumptable 00000001400FCD26 cases 3-7,9
0x140171fbf  lea     rbx, [rsp+4A8h+var_2E8]
0x140171fc7  jmp     loc_1400FCD4F
0x140171fcc  xorps   xmm0, xmm0; jumptable 00000001400FCD26 case 10
0x140171fcf  lea     rdi, [rsp+4A8h+var_278]
0x140171fd7  movaps  xmmword ptr [rdi], xmm0
0x140171fda  mov     qword ptr [rdi+10h], 0
0x140171fe2  mov     rcx, rdi
0x140171fe5  call    sub_14003F4D0
0x140171fea  mov     ecx, 3
0x140171fef  mov     rdx, rdi
0x140171ff2  call    sub_140081E60
0x140171ff7  lea     rbx, [rsp+4A8h+var_398]
0x140171fff  mov     rcx, rdi; Src
0x140172002  mov     rdx, rbx
0x140172005  call    sub_140069060
  ... truncated ...
```
