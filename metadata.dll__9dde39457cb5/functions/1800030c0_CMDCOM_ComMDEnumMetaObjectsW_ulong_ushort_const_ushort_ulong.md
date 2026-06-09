# CMDCOM::ComMDEnumMetaObjectsW(ulong,ushort const *,ushort *,ulong)

- ea: `0x1800030c0`
- end: `0x1800034d2`
- name: `?ComMDEnumMetaObjectsW@CMDCOM@@UEAAJKPEBGPEAGK@Z`
- size: `1042`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030c0`
- `0x1800034e0`
- `0x1800056d0`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800031fe`
- `msvcrt!wcscpy_s` at `0x1800031fe`
- `KERNEL32!LCMapStringW` at `0x1800032df`
- `KERNEL32!LCMapStringW` at `0x1800032df`
- `KERNEL32!GetLastError` at `0x1800032ec`
- `KERNEL32!GetLastError` at `0x1800032ec`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800031c4`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800031c4`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003293`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000336f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003293`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000336f`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000345c`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000345c`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003158`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003158`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003119`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180003119`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003247`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000327e`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180003247`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000327e`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003137`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000339d`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003137`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000339d`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003302`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003312`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003381`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800033ad`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800034ab`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003302`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003312`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003381`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800033ad`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800034ab`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800032ac`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003352`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800032ac`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003352`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDEnumMetaObjectsW(
        CMDCOM *this,
        unsigned int a2,
        WCHAR *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int Key; // eax
  unsigned int v9; // ebx
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // r8d
  const wchar_t *Str; // r8
  unsigned __int64 v15; // rax
  WCHAR v16; // ax
  const unsigned __int16 *v17; // r15
  signed int v18; // esi
  unsigned int Size; // r14d
  int cchDest; // r14d
  WCHAR *lpDestStr; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // r14d
  _QWORD *v25; // rdi
  int v26; // esi
  unsigned int v27; // esi
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rdi
  _QWORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[48]; // [rsp+40h] [rbp-C0h] BYREF
  int i; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  _BYTE v35[48]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v36[512]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 v37[272]; // [rsp+2B0h] [rbp+1B0h] BYREF

  if ( g_dwInitialized )
  {
    if ( a4 )
    {
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
      if ( g_pHandleTable
        && (v31[0] = 0,
            Key = CLKRHashTable::FindKey(g_pHandleTable, a2, v31),
            (int)CHandleTable::_HRESULT_FROM_LK_RETCODE(Key) >= 0)
        && v31[0] )
      {
        if ( (*(_BYTE *)(v31[0] + 12LL) & 1) != 0 )
        {
          v30 = *(_QWORD *)(v31[0] + 24LL);
          if ( v30 )
          {
            if ( a3 )
            {
              v29 = 0;
              if ( *a3 == 47 || *a3 == 92 )
                ++a3;
              while ( v30 )
              {
                v16 = *a3;
                if ( !*a3 )
                  goto LABEL_35;
                v17 = a3;
                while ( v16 != 92 && v16 != 47 && v16 )
                  v16 = *++v17;
                BUFFER::BUFFER((BUFFER *)v32, v37, 0x104u);
                i = 0;
                v34 = v30;
                v18 = (_DWORD)v17 - (_DWORD)a3;
                if ( (_DWORD)v17 == (_DWORD)a3 )
                {
                  BUFFER::~BUFFER((BUFFER *)v32);
                  v9 = -2147024893;
                  goto LABEL_6;
                }
                memset_0(v36, 0, sizeof(v36));
                BUFFER::BUFFER((BUFFER *)v35, v36, 0x200u);
                if ( v18 > 0 )
                {
                  if ( BUFFER::Resize((BUFFER *)v32, v18) )
                  {
                    Size = (_DWORD)v17 - (_DWORD)a3;
                    i = (_DWORD)v17 - (_DWORD)a3;
                    goto LABEL_30;
                  }
LABEL_34:
                  BUFFER::~BUFFER((BUFFER *)v35);
                  v9 = -2147024882;
                  BUFFER::~BUFFER((BUFFER *)v32);
                  goto LABEL_6;
                }
                Size = BUFFER::QuerySize((BUFFER *)v32);
                for ( i = Size; ; Size = i )
                {
LABEL_30:
                  cchDest = Size >> 1;
                  lpDestStr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v32);
                  v22 = (_DWORD)v17 - (_DWORD)a3;
                  if ( v18 >= 0 )
                    v22 = v18 / 2;
                  v23 = LCMapStringW(0x800u, 0x200u, a3, v22, lpDestStr, cchDest);
                  v24 = v23;
                  if ( v23 )
                    break;
                  if ( GetLastError() != 122 || !(unsigned int)CMDKeyBuffer::Resize((CMDKeyBuffer *)v32, i + 50) )
                    goto LABEL_34;
                }
                v26 = v23 - 1;
                if ( *((_WORD *)BUFFER::QueryPtr((BUFFER *)v32) + v23 - 1) )
                  v26 = v24;
                v27 = 2 * v26;
                if ( !BUFFER::Resize((BUFFER *)v32, v27) )
                  goto LABEL_34;
                i = v27;
                BUFFER::~BUFFER((BUFFER *)v35);
                v31[0] = 0;
                CLKRHashTable::FindKey(g_phtChildren, v32, v31);
                v28 = v31[0];
                BUFFER::~BUFFER((BUFFER *)v32);
                v29 = v30;
                if ( v28 )
                {
                  a3 = (WCHAR *)v17;
                  if ( *v17 == 47 || *v17 == 92 )
                    a3 = (WCHAR *)(v17 + 1);
                  v30 = v28;
                }
                else
                {
                  v30 = 0;
                }
              }
              if ( !v29 )
                goto LABEL_51;
              v9 = -2147024893;
            }
            else
            {
LABEL_35:
              v13 = a5;
              v25 = (_QWORD *)(v30 + 232);
              v12 = *v25 - 248LL;
              if ( (_QWORD *)*v25 == v25 )
                v12 = 0;
              while ( 1 )
              {
                if ( !v12 )
                {
                  v9 = -2147024637;
                  goto LABEL_6;
                }
                if ( !v13 )
                  break;
                v11 = *(_QWORD **)(v12 + 248);
                v12 = (__int64)(v11 - 31);
                if ( v11 == v25 )
                  v12 = 0;
                --v13;
              }
              Str = (const wchar_t *)STRAU::QueryStr((STRAU *)(v12 + 8), 1);
              if ( Str )
              {
                v15 = -1;
                do
                  ++v15;
                while ( Str[v15] );
                if ( v15 < 0x100 )
                {
                  v9 = 0;
                  wcscpy_s(a4, 0x100u, Str);
                }
                else
                {
                  v9 = -2147024774;
                }
              }
              else
              {
                v9 = -2147024882;
              }
            }
          }
          else
          {
LABEL_51:
            v9 = -2147467259;
          }
        }
        else
        {
          v9 = -2147024891;
        }
      }
      else
      {
        v9 = -2147024890;
      }
LABEL_6:
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2146646016;
  }
  return v9;
}

```

## disassembly

```asm
0x1800030c0  mov     [rsp-8+arg_0], rbx
0x1800030c5  push    rbp
0x1800030c6  push    rsi
0x1800030c7  push    rdi
0x1800030c8  push    r12
0x1800030ca  push    r13
0x1800030cc  push    r14
0x1800030ce  push    r15
0x1800030d0  lea     rbp, [rsp-2D0h]
0x1800030d8  sub     rsp, 3D0h
0x1800030df  mov     rax, cs:__security_cookie
0x1800030e6  xor     rax, rsp
0x1800030e9  mov     [rbp+300h+var_40], rax
0x1800030f0  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800030f6  xor     r13d, r13d
0x1800030f9  mov     edi, edx
0x1800030fb  mov     r12, r9
0x1800030fe  mov     rbx, r8
0x180003101  test    eax, eax
0x180003103  jz      loc_180003442
0x180003109  test    r9, r9
0x18000310c  jz      loc_18000344C
0x180003112  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180003119  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000311f  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x180003126  test    rcx, rcx
0x180003129  jz      short loc_18000314C
0x18000312b  mov     edx, edi
0x18000312d  mov     [rsp+400h+var_3D0], r13
0x180003132  lea     r8, [rsp+400h+var_3D0]
0x180003137  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000313d  mov     ecx, eax
0x18000313f  call    ?_HRESULT_FROM_LK_RETCODE@CHandleTable@@CAJW4LK_RETCODE@@@Z; CHandleTable::_HRESULT_FROM_LK_RETCODE(LK_RETCODE)
0x180003144  test    eax, eax
0x180003146  jns     loc_180003424
0x18000314c  mov     ebx, 80070006h
0x180003151  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180003158  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000315e  mov     eax, ebx
0x180003160  mov     rcx, [rbp+300h+var_40]
0x180003167  xor     rcx, rsp; StackCookie
0x18000316a  call    __security_check_cookie
0x18000316f  mov     rbx, [rsp+400h+arg_0]
0x180003177  add     rsp, 3D0h
0x18000317e  pop     r15
0x180003180  pop     r14
0x180003182  pop     r13
0x180003184  pop     r12
0x180003186  pop     rdi
0x180003187  pop     rsi
0x180003188  pop     rbp
0x180003189  retn
0x18000318a  test    r8d, r8d
0x18000318d  jz      short loc_1800031BB
0x18000318f  mov     rdx, r9
0x180003192  test    rcx, rcx
0x180003195  jz      short loc_18000319E
0x180003197  mov     rdx, [rcx+0F8h]
0x18000319e  cmp     rdx, rdi
0x1800031a1  lea     rcx, [rdx-0F8h]
0x1800031a8  cmovz   rcx, r13
0x1800031ac  dec     r8d
0x1800031af  test    rcx, rcx
0x1800031b2  jnz     short loc_18000318A
0x1800031b4  mov     ebx, 80070103h
0x1800031b9  jmp     short loc_180003151
0x1800031bb  add     rcx, 8
0x1800031bf  mov     edx, 1
0x1800031c4  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x1800031ca  mov     r8, rax; Source
0x1800031cd  test    rax, rax
0x1800031d0  jz      loc_1800034C8
0x1800031d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800031da  inc     rax
0x1800031dd  cmp     [r8+rax*2], r13w
0x1800031e2  jnz     short loc_1800031DA
0x1800031e4  mov     edx, 100h; SizeInWords
0x1800031e9  cmp     rax, rdx
0x1800031ec  jb      short loc_1800031F8
0x1800031ee  mov     ebx, 8007007Ah
0x1800031f3  jmp     loc_180003151
0x1800031f8  mov     rcx, r12; Destination
0x1800031fb  mov     ebx, r13d
0x1800031fe  call    cs:__imp_wcscpy_s
0x180003204  jmp     loc_180003151
0x180003209  movzx   eax, word ptr [rbx]
0x18000320c  test    ax, ax
0x18000320f  jz      loc_180003329
0x180003215  mov     r15, rbx
0x180003218  cmp     ax, 5Ch ; '\'
0x18000321c  jz      short loc_180003232
0x18000321e  cmp     ax, 2Fh ; '/'
0x180003222  jz      short loc_180003232
0x180003224  test    ax, ax
0x180003227  jz      short loc_180003232
0x180003229  add     r15, rcx
0x18000322c  movzx   eax, word ptr [r15]
0x180003230  jmp     short loc_180003218
0x180003232  mov     r8d, 104h
0x180003238  lea     rdx, [rbp+300h+var_150]
0x18000323f  lea     rcx, [rsp+400h+var_3C0]
0x180003244  mov     esi, r15d
0x180003247  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000324d  mov     [rsp+400h+var_390], r13d
0x180003252  mov     [rsp+400h+var_388], rdi
0x180003257  sub     esi, ebx
0x180003259  jz      loc_1800034A6
0x18000325f  xor     edx, edx; Val
0x180003261  lea     rcx, [rbp+300h+var_350]; void *
0x180003265  mov     r8d, 200h; Size
0x18000326b  call    memset_0
0x180003270  mov     r8d, 200h
0x180003276  lea     rdx, [rbp+300h+var_350]
0x18000327a  lea     rcx, [rbp+300h+var_380]
0x18000327e  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180003284  lea     rcx, [rsp+400h+var_3C0]
0x180003289  test    esi, esi
0x18000328b  jle     loc_18000345C
0x180003291  mov     edx, esi
0x180003293  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003299  test    al, al
0x18000329b  jz      short loc_1800032FB
0x18000329d  mov     r14d, esi
0x1800032a0  mov     [rsp+400h+var_390], esi
0x1800032a4  lea     rcx, [rsp+400h+var_3C0]
0x1800032a9  shr     r14d, 1
0x1800032ac  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800032b2  mov     rcx, rax
0x1800032b5  mov     eax, esi
0x1800032b7  test    esi, esi
0x1800032b9  js      short loc_1800032C5
0x1800032bb  cdq
0x1800032bc  mov     r8d, 2
0x1800032c2  idiv    r8d
0x1800032c5  mov     [rsp+400h+cchDest], r14d; cchDest
0x1800032ca  mov     r9d, eax; cchSrc
0x1800032cd  mov     [rsp+400h+lpDestStr], rcx; lpDestStr
0x1800032d2  mov     r8, rbx; lpSrcStr
0x1800032d5  mov     ecx, 800h; Locale
0x1800032da  mov     edx, 200h; dwMapFlags
0x1800032df  call    cs:__imp_LCMapStringW
0x1800032e5  movsxd  r14, eax
0x1800032e8  test    eax, eax
0x1800032ea  jnz     short loc_18000334D
0x1800032ec  call    cs:__imp_GetLastError
0x1800032f2  cmp     eax, 7Ah ; 'z'
0x1800032f5  jz      loc_18000346E
0x1800032fb  lea     rcx, [rbp+300h+var_380]
0x1800032ff  mov     rdi, r13
0x180003302  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003308  lea     rcx, [rsp+400h+var_3C0]
0x18000330d  mov     ebx, 8007000Eh
0x180003312  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003318  test    ebx, ebx
0x18000331a  js      loc_180003151
0x180003320  test    rdi, rdi
0x180003323  jz      loc_18000341A
0x180003329  mov     r8d, [rbp+300h+arg_20]
0x180003330  add     rdi, 0E8h
0x180003337  mov     r9, [rdi]
0x18000333a  cmp     r9, rdi
0x18000333d  lea     rcx, [r9-0F8h]
0x180003344  cmovz   rcx, r13
0x180003348  jmp     loc_1800031AF
0x18000334d  lea     rcx, [rsp+400h+var_3C0]
0x180003352  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003358  lea     esi, [r14-1]
0x18000335c  lea     rcx, [rsp+400h+var_3C0]
0x180003361  cmp     [rax+r14*2-2], r13w
0x180003367  cmovnz  esi, r14d
0x18000336b  add     esi, esi
0x18000336d  mov     edx, esi
0x18000336f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003375  test    al, al
0x180003377  jz      short loc_1800032FB
0x180003379  lea     rcx, [rbp+300h+var_380]
0x18000337d  mov     [rsp+400h+var_390], esi
0x180003381  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003387  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x18000338e  lea     r8, [rsp+400h+var_3D0]
0x180003393  lea     rdx, [rsp+400h+var_3C0]
0x180003398  mov     [rsp+400h+var_3D0], r13
0x18000339d  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800033a3  mov     rsi, [rsp+400h+var_3D0]
0x1800033a8  lea     rcx, [rsp+400h+var_3C0]
0x1800033ad  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800033b3  mov     rax, rdi
0x1800033b6  test    rsi, rsi
0x1800033b9  jz      loc_18000349E
0x1800033bf  cmp     word ptr [r15], 2Fh ; '/'
0x1800033c4  mov     rbx, r15
0x1800033c7  jz      loc_180003491
0x1800033cd  cmp     word ptr [r15], 5Ch ; '\'
0x1800033d2  jz      loc_180003491
0x1800033d8  mov     ecx, 2
0x1800033dd  mov     rdi, rsi
0x1800033e0  jmp     short loc_180003408
0x1800033e2  mov     rdi, [rdi+18h]
0x1800033e6  test    rdi, rdi
0x1800033e9  jz      short loc_18000341A
0x1800033eb  test    rbx, rbx
0x1800033ee  jz      loc_180003329
0x1800033f4  cmp     word ptr [rbx], 2Fh ; '/'
0x1800033f8  mov     rax, r13
0x1800033fb  jz      short loc_180003456
0x1800033fd  cmp     word ptr [rbx], 5Ch ; '\'
0x180003401  jz      short loc_180003456
0x180003403  mov     ecx, 2
0x180003408  test    rdi, rdi
0x18000340b  jnz     loc_180003209
0x180003411  test    rax, rax
0x180003414  jnz     loc_1800034BB
0x18000341a  mov     ebx, 80004005h
0x18000341f  jmp     loc_180003151
0x180003424  mov     rdi, [rsp+400h+var_3D0]
0x180003429  test    rdi, rdi
0x18000342c  jz      loc_18000314C
0x180003432  test    byte ptr [rdi+0Ch], 1
0x180003436  jnz     short loc_1800033E2
0x180003438  mov     ebx, 80070005h
0x18000343d  jmp     loc_180003151
0x180003442  mov     ebx, 800CC800h
0x180003447  jmp     loc_18000315E
0x18000344c  mov     ebx, 80070057h
0x180003451  jmp     loc_18000315E
0x180003456  add     rbx, 2
0x18000345a  jmp     short loc_180003403
0x18000345c  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180003462  mov     r14d, eax
0x180003465  mov     [rsp+400h+var_390], eax
0x180003469  jmp     loc_1800032A4
0x18000346e  mov     edx, [rsp+400h+var_390]
0x180003472  lea     rcx, [rsp+400h+var_3C0]; this
0x180003477  add     edx, 32h ; '2'; unsigned int
0x18000347a  call    ?Resize@CMDKeyBuffer@@QEAAHI@Z; CMDKeyBuffer::Resize(uint)
0x18000347f  test    eax, eax
0x180003481  jz      loc_1800032FB
0x180003487  mov     r14d, [rsp+400h+var_390]
0x18000348c  jmp     loc_1800032A4
0x180003491  mov     ecx, 2
0x180003496  add     rbx, rcx
0x180003499  jmp     loc_1800033DD
0x18000349e  mov     rdi, rsi
0x1800034a1  jmp     loc_180003403
0x1800034a6  lea     rcx, [rsp+400h+var_3C0]
0x1800034ab  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800034b1  mov     ebx, 80070003h
0x1800034b6  jmp     loc_180003151
0x1800034bb  mov     rdi, rax
0x1800034be  mov     ebx, 80070003h
0x1800034c3  jmp     loc_180003318
0x1800034c8  mov     ebx, 8007000Eh
0x1800034cd  jmp     loc_180003151
```
