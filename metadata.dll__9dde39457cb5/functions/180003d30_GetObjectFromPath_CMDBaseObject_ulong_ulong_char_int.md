# GetObjectFromPath(CMDBaseObject * &,ulong,ulong,char * &,int)

- ea: `0x180003d30`
- end: `0x180004282`
- name: `?GetObjectFromPath@@YAJAEAPEAVCMDBaseObject@@KKAEAPEADH@Z`
- size: `1362`
- prototype: `__int64 __fastcall(struct CMDBaseObject **, unsigned int, char, const CHAR **, int)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x180005900`
- `0x1800166b8`
- `0x180016bb4`
- `0x180017a70`
- `0x1800181f0`
- `0x18001841c`
- `0x1800185bc`
- `0x18001870c`
- `0x18001919c`
- `0x180019c9c`
- `0x180019d8c`
- `0x18001c580`
- `0x180022ab8`
- `0x180022c20`

## callees

- `0x180003d30`
- `0x1800056d0`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `USER32!CharNextExA` at `0x1800040c4`
- `USER32!CharNextExA` at `0x1800040c4`
- `KERNEL32!LCMapStringW` at `0x180003ee0`
- `KERNEL32!LCMapStringW` at `0x180003ee0`
- `KERNEL32!MultiByteToWideChar` at `0x180004124`
- `KERNEL32!MultiByteToWideChar` at `0x180004124`
- `KERNEL32!GetLastError` at `0x180003eed`
- `KERNEL32!GetLastError` at `0x180004130`
- `KERNEL32!GetLastError` at `0x180003eed`
- `KERNEL32!GetLastError` at `0x180004130`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e9d`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003f55`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800040e8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004150`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e9d`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003f55`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800040e8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004150`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800040fa`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004143`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004174`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800040fa`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004143`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180004174`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003e46`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003e7f`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003e46`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003e7f`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003da7`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003f85`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003da7`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003f85`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f00`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f10`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f66`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f95`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800041d9`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f00`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f10`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f66`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003f95`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800041d9`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003eb3`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003f3a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004108`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004163`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003eb3`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003f3a`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004108`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180004163`

## pseudocode

```c
__int64 __fastcall GetObjectFromPath(struct CMDBaseObject **a1, unsigned int a2, char a3, const CHAR **a4, int a5)
{
  int Key; // eax
  __int16 v10; // ax
  LPSTR v11; // rdi
  CHAR v12; // al
  int v13; // esi
  const WCHAR *v14; // r15
  unsigned int v15; // ebx
  int cchDest; // ebx
  WCHAR *lpDestStr; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  struct CMDBaseObject *v23; // rbx
  struct CMDBaseObject *v24; // rcx
  const CHAR *v25; // r14
  struct CMDBaseObject *v26; // r12
  const CHAR *v27; // rax
  unsigned int v28; // ebx
  WCHAR *Ptr; // rax
  int v30; // ebx
  unsigned int Size; // eax
  const CHAR *i; // [rsp+30h] [rbp-D0h] BYREF
  struct CMDBaseObject **v33; // [rsp+38h] [rbp-C8h]
  char **v34; // [rsp+40h] [rbp-C0h]
  _BYTE v35[48]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int j; // [rsp+80h] [rbp-80h]
  struct CMDBaseObject *v37; // [rsp+88h] [rbp-78h]
  _BYTE v38[48]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v39[512]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v40[272]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v33 = a1;
  v34 = (char **)a4;
  if ( !g_pHandleTable )
    return 2147942406LL;
  i = 0;
  Key = CLKRHashTable::FindKey(g_pHandleTable, a2, &i);
  if ( Key == -99 )
    return 2147942406LL;
  switch ( Key )
  {
    case 0:
      v27 = i;
      if ( !i )
        return 2147942406LL;
      *a1 = 0;
      if ( ((a3 & 2) == 0 || (v27[12] & 2) != 0) && ((a3 & 1) == 0 || (v27[12] & 1) != 0) )
      {
        v26 = (struct CMDBaseObject *)*((_QWORD *)v27 + 3);
        if ( !v26 )
          return (unsigned int)-2147467259;
        v25 = *a4;
        if ( !*a4 )
        {
          *a1 = v26;
          return 0;
        }
        v24 = 0;
        if ( a5 )
        {
          if ( *(_WORD *)v25 == 47 || *(_WORD *)v25 == 92 )
            v25 += 2;
        }
        else if ( *v25 == 47 || *v25 == 92 )
        {
          goto LABEL_55;
        }
        while ( 1 )
        {
          while ( 1 )
          {
            if ( !v26 )
            {
              if ( v24 )
              {
                v21 = -2147024893;
                *v33 = v24;
                *v34 = (char *)v25;
              }
              else
              {
                return (unsigned int)-2147467259;
              }
              return v21;
            }
            if ( a5 )
            {
              if ( !*(_WORD *)v25 )
                goto LABEL_75;
              v10 = *(_WORD *)v25;
              v11 = (LPSTR)v25;
              for ( i = v25; v10 != 92; v11 += 2 )
              {
                if ( v10 == 47 )
                  break;
                if ( !v10 )
                  break;
                v10 = *((_WORD *)v11 + 1);
              }
            }
            else
            {
              v12 = *v25;
              if ( !*v25 )
              {
LABEL_75:
                v21 = 0;
                *v33 = v26;
                return v21;
              }
              v11 = (LPSTR)v25;
              if ( v12 != 92 )
              {
                do
                {
                  if ( v12 == 47 )
                    break;
                  if ( !v12 )
                    break;
                  v11 = CharNextExA(0, v11, 0);
                  v12 = *v11;
                }
                while ( *v11 != 92 );
              }
            }
            BUFFER::BUFFER((BUFFER *)v35, v40, 0x104u);
            j = 0;
            v37 = v26;
            v13 = (_DWORD)v11 - (_DWORD)v25;
            if ( (_DWORD)v11 == (_DWORD)v25 )
            {
              v21 = -2147024893;
              BUFFER::~BUFFER((BUFFER *)v35);
              return v21;
            }
            v14 = (const WCHAR *)v25;
            memset_0(v39, 0, sizeof(v39));
            BUFFER::BUFFER((BUFFER *)v38, v39, 0x200u);
            if ( !a5 )
            {
              if ( v13 > 0 && !BUFFER::Resize((BUFFER *)v38, 2 * v13 + 50) )
                goto LABEL_23;
              while ( 1 )
              {
                v28 = BUFFER::QuerySize((BUFFER *)v38) >> 1;
                Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v38);
                v30 = MultiByteToWideChar(0, 1u, v25, v13, Ptr, v28);
                if ( v30 )
                  break;
                if ( GetLastError() == 122 )
                {
                  Size = BUFFER::QuerySize((BUFFER *)v38);
                  if ( BUFFER::Resize((BUFFER *)v38, Size + 50) )
                    continue;
                }
                goto LABEL_23;
              }
              v14 = (const WCHAR *)BUFFER::QueryPtr((BUFFER *)v38);
              v13 = 2 * v30;
            }
            if ( v13 > 0 )
            {
              if ( BUFFER::Resize((BUFFER *)v35, v13) )
              {
                v15 = v13;
                j = v13;
                goto LABEL_19;
              }
LABEL_23:
              BUFFER::~BUFFER((BUFFER *)v38);
              v21 = -2147024882;
              BUFFER::~BUFFER((BUFFER *)v35);
              return v21;
            }
            v15 = BUFFER::QuerySize((BUFFER *)v35);
            for ( j = v15; ; v15 = j )
            {
LABEL_19:
              cchDest = v15 >> 1;
              lpDestStr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v35);
              v18 = v13;
              if ( v13 >= 0 )
                v18 = v13 / 2;
              v19 = LCMapStringW(0x800u, 0x200u, v14, v18, lpDestStr, cchDest);
              v20 = v19;
              if ( v19 )
                break;
              if ( GetLastError() != 122 || !(unsigned int)CMDKeyBuffer::Resize((CMDKeyBuffer *)v35, j + 50) )
                goto LABEL_23;
            }
            if ( !*((_WORD *)BUFFER::QueryPtr((BUFFER *)v35) + v19 - 1) )
              --v20;
            v22 = 2 * v20;
            if ( !BUFFER::Resize((BUFFER *)v35, v22) )
              goto LABEL_23;
            j = v22;
            BUFFER::~BUFFER((BUFFER *)v38);
            i = 0;
            CLKRHashTable::FindKey(g_phtChildren, v35, &i);
            v23 = (struct CMDBaseObject *)i;
            BUFFER::~BUFFER((BUFFER *)v35);
            v24 = v26;
            if ( v23 )
              break;
LABEL_32:
            v26 = v23;
          }
          v25 = v11;
          if ( a5 )
          {
            if ( *(_WORD *)v11 == 47 || *(_WORD *)v11 == 92 )
              v25 = v11 + 2;
            goto LABEL_32;
          }
          if ( *v11 == 47 || *v11 == 92 )
          {
            v26 = v23;
LABEL_55:
            ++v25;
          }
          else
          {
            v26 = v23;
          }
        }
      }
      return 2147942405LL;
    default:
      return 2147942406LL;
  }
}

```

## disassembly

```asm
0x180003d30  push    rbp
0x180003d32  push    rbx
0x180003d33  push    rsi
0x180003d34  push    rdi
0x180003d35  push    r15
0x180003d37  lea     rbp, [rsp-2F0h]
0x180003d3f  sub     rsp, 3F0h
0x180003d46  mov     rax, cs:__security_cookie
0x180003d4d  xor     rax, rsp
0x180003d50  mov     [rbp+310h+var_40], rax
0x180003d57  mov     rdi, rcx
0x180003d5a  mov     [rsp+410h+var_3D8], rcx
0x180003d5f  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x180003d66  mov     rsi, r9
0x180003d69  mov     [rsp+410h+var_3D0], r9
0x180003d6e  mov     ebx, r8d
0x180003d71  test    rcx, rcx
0x180003d74  jnz     short loc_180003D98
0x180003d76  mov     eax, 80070006h; jumptable 0000000180003DD5 default case, cases -98--1,1-3
0x180003d7b  mov     rcx, [rbp+310h+var_40]
0x180003d82  xor     rcx, rsp; StackCookie
0x180003d85  call    __security_check_cookie
0x180003d8a  add     rsp, 3F0h
0x180003d91  pop     r15
0x180003d93  pop     rdi
0x180003d94  pop     rsi
0x180003d95  pop     rbx
0x180003d96  pop     rbp
0x180003d97  retn
0x180003d98  xor     r15d, r15d
0x180003d9b  mov     edx, edx
0x180003d9d  lea     r8, [rsp+410h+var_3E0]
0x180003da2  mov     [rsp+410h+var_3E0], r15
0x180003da7  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180003dad  cmp     eax, 0FFFFFF9Dh
0x180003db0  jz      short def_180003DD5; jumptable 0000000180003DD5 default case, cases -98--1,1-3
0x180003db2  add     eax, 62h ; 'b'; switch 102 cases
0x180003db5  cmp     eax, 65h
0x180003db8  ja      short def_180003DD5; jumptable 0000000180003DD5 default case, cases -98--1,1-3
0x180003dba  lea     rdx, cs:180000000h
0x180003dc1  cdqe
0x180003dc3  movzx   eax, ds:(byte_18000421C - 180000000h)[rdx+rax]
0x180003dcb  mov     ecx, ds:(jpt_180003DD5 - 180000000h)[rdx+rax*4]
0x180003dd2  add     rcx, rdx
0x180003dd5  jmp     rcx; switch jump
0x180003dd7  test    r13d, r13d
0x180003dda  jz      short loc_180003E1B
0x180003ddc  cmp     word ptr [r14], 0
0x180003de1  jz      loc_1800041E4
0x180003de7  movzx   eax, word ptr [r14]
0x180003deb  mov     rdi, r14
0x180003dee  mov     [rsp+410h+var_3E0], r14
0x180003df3  cmp     ax, 5Ch ; '\'
0x180003df7  jz      short loc_180003E32
0x180003df9  nop     dword ptr [rax+00000000h]
0x180003e00  cmp     ax, 2Fh ; '/'
0x180003e04  jz      short loc_180003E32
0x180003e06  test    ax, ax
0x180003e09  jz      short loc_180003E32
0x180003e0b  movzx   eax, word ptr [rdi+2]
0x180003e0f  add     rdi, 2
0x180003e13  cmp     ax, 5Ch ; '\'
0x180003e17  jnz     short loc_180003E00
0x180003e19  jmp     short loc_180003E32
0x180003e1b  movzx   eax, byte ptr [r14]
0x180003e1f  test    al, al
0x180003e21  jz      loc_1800041E4
0x180003e27  mov     rdi, r14
0x180003e2a  cmp     al, 5Ch ; '\'
0x180003e2c  jnz     loc_1800040AC
0x180003e32  mov     r8d, 104h
0x180003e38  lea     rdx, [rbp+310h+var_150]
0x180003e3f  lea     rcx, [rsp+410h+var_3C0]
0x180003e44  mov     esi, edi
0x180003e46  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180003e4c  mov     [rbp+310h+var_390], r15d
0x180003e50  mov     [rbp+310h+var_388], r12
0x180003e54  sub     esi, r14d
0x180003e57  jz      loc_1800041CF
0x180003e5d  xor     edx, edx; Val
0x180003e5f  lea     rcx, [rbp+310h+var_350]; void *
0x180003e63  mov     r8d, 200h; Size
0x180003e69  mov     r15, r14
0x180003e6c  call    memset_0
0x180003e71  mov     r8d, 200h
0x180003e77  lea     rdx, [rbp+310h+var_350]
0x180003e7b  lea     rcx, [rbp+310h+var_380]
0x180003e7f  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180003e85  test    r13d, r13d
0x180003e88  jz      loc_1800040D9
0x180003e8e  lea     rcx, [rsp+410h+var_3C0]
0x180003e93  test    esi, esi
0x180003e95  jle     loc_180004174
0x180003e9b  mov     edx, esi
0x180003e9d  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003ea3  test    al, al
0x180003ea5  jz      short loc_180003EFC
0x180003ea7  mov     ebx, esi
0x180003ea9  mov     [rbp+310h+var_390], ebx
0x180003eac  lea     rcx, [rsp+410h+var_3C0]
0x180003eb1  shr     ebx, 1
0x180003eb3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003eb9  mov     rcx, rax
0x180003ebc  mov     eax, esi
0x180003ebe  test    esi, esi
0x180003ec0  js      short loc_180003EC7
0x180003ec2  cdq
0x180003ec3  sub     eax, edx
0x180003ec5  sar     eax, 1
0x180003ec7  mov     [rsp+410h+cchDest], ebx; cchDest
0x180003ecb  mov     r9d, eax; cchSrc
0x180003ece  mov     [rsp+410h+lpDestStr], rcx; lpDestStr
0x180003ed3  mov     r8, r15; lpSrcStr
0x180003ed6  mov     ecx, 800h; Locale
0x180003edb  mov     edx, 200h; dwMapFlags
0x180003ee0  call    cs:__imp_LCMapStringW
0x180003ee6  movsxd  rbx, eax
0x180003ee9  test    eax, eax
0x180003eeb  jnz     short loc_180003F35
0x180003eed  call    cs:__imp_GetLastError
0x180003ef3  cmp     eax, 7Ah ; 'z'
0x180003ef6  jz      loc_180004184
0x180003efc  lea     rcx, [rbp+310h+var_380]
0x180003f00  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f06  lea     rcx, [rsp+410h+var_3C0]
0x180003f0b  mov     ebx, 8007000Eh
0x180003f10  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f16  mov     r13, [rsp+410h+var_28]
0x180003f1e  mov     r14, [rsp+410h+var_30]
0x180003f26  mov     r12, [rsp+410h+arg_10]
0x180003f2e  mov     eax, ebx
0x180003f30  jmp     loc_180003D7B
0x180003f35  lea     rcx, [rsp+410h+var_3C0]
0x180003f3a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003f40  cmp     word ptr [rax+rbx*2-2], 0
0x180003f46  jz      loc_1800041A4
0x180003f4c  add     ebx, ebx
0x180003f4e  lea     rcx, [rsp+410h+var_3C0]
0x180003f53  mov     edx, ebx
0x180003f55  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003f5b  test    al, al
0x180003f5d  jz      short loc_180003EFC
0x180003f5f  lea     rcx, [rbp+310h+var_380]
0x180003f63  mov     [rbp+310h+var_390], ebx
0x180003f66  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f6c  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180003f73  lea     r8, [rsp+410h+var_3E0]
0x180003f78  xor     r15d, r15d
0x180003f7b  lea     rdx, [rsp+410h+var_3C0]
0x180003f80  mov     [rsp+410h+var_3E0], r15
0x180003f85  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180003f8b  mov     rbx, [rsp+410h+var_3E0]
0x180003f90  lea     rcx, [rsp+410h+var_3C0]
0x180003f95  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f9b  mov     rcx, r12
0x180003f9e  test    rbx, rbx
0x180003fa1  jz      short loc_180003FC6
0x180003fa3  mov     r14, rdi
0x180003fa6  test    r13d, r13d
0x180003fa9  jz      loc_1800041B4
0x180003faf  movzx   eax, word ptr [rdi]
0x180003fb2  cmp     ax, 2Fh ; '/'
0x180003fb6  jz      loc_1800041AB
0x180003fbc  cmp     ax, 5Ch ; '\'
0x180003fc0  jz      loc_1800041AB
0x180003fc6  mov     r12, rbx
0x180003fc9  jmp     short loc_18000401F
0x180003fcb  mov     [rsp+410h+arg_10], r12
0x180003fd3  mov     r12, [rax+18h]
0x180003fd7  test    r12, r12
0x180003fda  jz      loc_180004078
0x180003fe0  mov     [rsp+410h+var_30], r14
0x180003fe8  mov     r14, [rsi]
0x180003feb  test    r14, r14
0x180003fee  jz      loc_180004082
0x180003ff4  mov     [rsp+410h+var_28], r13
0x180003ffc  mov     rcx, r15
0x180003fff  mov     r13d, [rbp+310h+arg_20]
0x180004006  test    r13d, r13d
0x180004009  jz      loc_180004093
0x18000400f  movzx   eax, word ptr [r14]
0x180004013  cmp     ax, 2Fh ; '/'
0x180004017  jz      short loc_18000408D
0x180004019  cmp     ax, 5Ch ; '\'
0x18000401d  jz      short loc_18000408D
0x18000401f  test    r12, r12
0x180004022  jnz     loc_180003DD7
0x180004028  test    rcx, rcx
0x18000402b  jnz     loc_1800041F4
0x180004031  mov     ebx, 80004005h
0x180004036  jmp     loc_180003F16
0x18000403b  mov     rax, [rsp+410h+var_3E0]; jumptable 0000000180003DD5 case 0
0x180004040  test    rax, rax
0x180004043  jz      def_180003DD5; jumptable 0000000180003DD5 default case, cases -98--1,1-3
0x180004049  mov     [rdi], r15
0x18000404c  test    bl, 2
0x18000404f  jnz     short loc_180004066
0x180004051  test    bl, 1
0x180004054  jz      loc_180003FCB
0x18000405a  test    byte ptr [rax+0Ch], 1
0x18000405e  jnz     loc_180003FCB
0x180004064  jmp     short loc_18000406C
0x180004066  test    byte ptr [rax+0Ch], 2
0x18000406a  jnz     short loc_180004051
0x18000406c  mov     ebx, 80070005h
0x180004071  mov     eax, ebx
0x180004073  jmp     loc_180003D7B
0x180004078  mov     ebx, 80004005h
0x18000407d  jmp     loc_180003F26
0x180004082  mov     [rdi], r12
0x180004085  mov     ebx, r15d
0x180004088  jmp     loc_180003F1E
0x18000408d  add     r14, 2
0x180004091  jmp     short loc_18000401F
0x180004093  movzx   eax, byte ptr [r14]
0x180004097  cmp     al, 2Fh ; '/'
0x180004099  jz      short loc_1800040A4
0x18000409b  cmp     al, 5Ch ; '\'
0x18000409d  jnz     short loc_18000401F
0x18000409f  jmp     short loc_1800040A4
0x1800040a1  mov     r12, rbx
0x1800040a4  inc     r14
0x1800040a7  jmp     loc_18000401F
0x1800040ac  cmp     al, 2Fh ; '/'
0x1800040ae  jz      loc_180003E32
0x1800040b4  test    al, al
0x1800040b6  jz      loc_180003E32
0x1800040bc  xor     ecx, ecx; CodePage
0x1800040be  xor     r8d, r8d; dwFlags
0x1800040c1  mov     rdx, rdi; lpCurrentChar
0x1800040c4  call    cs:__imp_CharNextExA
0x1800040ca  mov     rdi, rax
0x1800040cd  movzx   eax, byte ptr [rax]
0x1800040d0  cmp     al, 5Ch ; '\'
0x1800040d2  jnz     short loc_1800040AC
0x1800040d4  jmp     loc_180003E32
0x1800040d9  test    esi, esi
0x1800040db  jle     short loc_1800040F6
0x1800040dd  lea     edx, ds:32h[rsi*2]
0x1800040e4  lea     rcx, [rbp+310h+var_380]
0x1800040e8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800040ee  test    al, al
0x1800040f0  jz      loc_180003EFC
0x1800040f6  lea     rcx, [rbp+310h+var_380]
0x1800040fa  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180004100  mov     ebx, eax
0x180004102  lea     rcx, [rbp+310h+var_380]
0x180004106  shr     ebx, 1
0x180004108  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000410e  mov     r9d, esi; cbMultiByte
0x180004111  mov     [rsp+410h+cchDest], ebx; cchWideChar
0x180004115  mov     r8, r14; lpMultiByteStr
0x180004118  mov     [rsp+410h+lpDestStr], rax; lpWideCharStr
0x18000411d  mov     edx, 1; dwFlags
0x180004122  xor     ecx, ecx; CodePage
0x180004124  call    cs:__imp_MultiByteToWideChar
0x18000412a  mov     ebx, eax
0x18000412c  test    eax, eax
0x18000412e  jnz     short loc_18000415F
0x180004130  call    cs:__imp_GetLastError
0x180004136  cmp     eax, 7Ah ; 'z'
0x180004139  jnz     loc_180003EFC
0x18000413f  lea     rcx, [rbp+310h+var_380]
0x180004143  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180004149  lea     rcx, [rbp+310h+var_380]
0x18000414d  lea     edx, [rax+32h]
0x180004150  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180004156  test    al, al
0x180004158  jnz     short loc_1800040F6
0x18000415a  jmp     loc_180003EFC
0x18000415f  lea     rcx, [rbp+310h+var_380]
0x180004163  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180004169  mov     r15, rax
0x18000416c  lea     esi, [rbx+rbx]
0x18000416f  jmp     loc_180003E8E
0x180004174  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000417a  mov     ebx, eax
0x18000417c  mov     [rbp+310h+var_390], eax
0x18000417f  jmp     loc_180003EAC
0x180004184  mov     edx, [rbp+310h+var_390]
0x180004187  lea     rcx, [rsp+410h+var_3C0]; this
0x18000418c  add     edx, 32h ; '2'; unsigned int
0x18000418f  call    ?Resize@CMDKeyBuffer@@QEAAHI@Z; CMDKeyBuffer::Resize(uint)
0x180004194  test    eax, eax
0x180004196  jz      loc_180003EFC
0x18000419c  mov     ebx, [rbp+310h+var_390]
0x18000419f  jmp     loc_180003EAC
0x1800041a4  dec     ebx
0x1800041a6  jmp     loc_180003F4C
0x1800041ab  add     r14, 2
0x1800041af  jmp     loc_180003FC6
0x1800041b4  movzx   eax, byte ptr [rdi]
0x1800041b7  cmp     al, 2Fh ; '/'
0x1800041b9  jz      loc_1800040A1
0x1800041bf  cmp     al, 5Ch ; '\'
0x1800041c1  jz      loc_1800040A1
0x1800041c7  mov     r12, rbx
0x1800041ca  jmp     loc_18000401F
0x1800041cf  lea     rcx, [rsp+410h+var_3C0]
0x1800041d4  mov     ebx, 80070003h
  ... truncated ...
```
