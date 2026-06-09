# FTP_LOGGING::Initialize(FTP_LOG_FILE_CONFIG_ELEMENT *,int,int,ulong)

- ea: `0x180027010`
- end: `0x180027473`
- name: `?Initialize@FTP_LOGGING@@QEAAJPEAVFTP_LOG_FILE_CONFIG_ELEMENT@@HHK@Z`
- size: `1123`
- prototype: `__int64 __fastcall(FTP_LOGGING *__hidden this, struct FTP_LOG_FILE_CONFIG_ELEMENT *, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009d2c`
- `0x18000ac28`
- `0x180026bac`

## callees

- `0x180001210`
- `0x180027010`
- `0x18002b84c`
- `0x180047050`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180027166`
- `msvcrt!swprintf_s` at `0x180027166`
- `KERNEL32!GetLastError` at `0x1800273f4`
- `KERNEL32!GetLastError` at `0x1800273f4`
- `KERNEL32!GetComputerNameExW` at `0x1800273d0`
- `KERNEL32!GetComputerNameExW` at `0x1800273ea`
- `KERNEL32!GetComputerNameExW` at `0x1800273d0`
- `KERNEL32!GetComputerNameExW` at `0x1800273ea`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027068`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180027068`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027429`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027429`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800270e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027102`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027202`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800270e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027102`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180027202`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002711e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002713a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027175`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027191`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002711e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002713a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027175`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180027191`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027051`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002705d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002708e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027099`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027051`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002705d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18002708e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180027099`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027435`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027441`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027435`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027441`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FTP_LOGGING::Initialize(
        FTP_LOGGING *this,
        const unsigned __int16 **a2,
        int a3,
        int a4,
        unsigned int a5)
{
  char *v9; // rbx
  int v10; // r14d
  int v11; // ebx
  __int64 v12; // rbx
  const unsigned __int16 *v13; // r10
  int v14; // r11d
  int v15; // r9d
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  unsigned int v31; // edx
  unsigned int v32; // eax
  unsigned int v33; // ecx
  unsigned int v34; // eax
  unsigned int v35; // ecx
  unsigned int v36; // eax
  unsigned int v37; // r8d
  unsigned int v38; // edx
  signed int LastError; // eax
  DWORD nSize[2]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v42[32]; // [rsp+28h] [rbp-D8h] BYREF
  const unsigned __int16 *v43; // [rsp+48h] [rbp-B8h]
  _BYTE v44[56]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[12]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR WideCharStr[264]; // [rsp+B0h] [rbp-50h] BYREF

  STRU::STRU(v42);
  STRU::STRU(v44);
  CReaderWriterLock3::WriteLock((FTP_LOGGING *)((char *)this + 92));
  v9 = (char *)operator new(0xA8u);
  *(_QWORD *)nSize = v9;
  v10 = 1;
  if ( v9 )
  {
    STRU::STRU(v9);
    STRU::STRU(v9 + 56);
    *((_QWORD *)v9 + 14) = 0;
    *((_QWORD *)v9 + 15) = 1;
    *((_DWORD *)v9 + 32) = 0;
    *(_QWORD *)(v9 + 148) = 0;
    *(_QWORD *)(v9 + 156) = 1;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 1) = v9;
  if ( v9 )
  {
    v11 = STRU::Copy((STRU *)v44, L"FTPSVC");
    if ( v11 >= 0 )
    {
      v11 = STRU::Copy((STRU *)v42, a2[1]);
      if ( v11 >= 0 )
      {
        v11 = STRU::Append((STRU *)v42, L"\\");
        if ( v11 >= 0 )
        {
          v11 = STRU::Append((STRU *)v42, L"FTPSVC");
          if ( v11 >= 0 )
          {
            if ( !a4
              || (swprintf_s(Buffer, 0xBu, L"%lu", a5, *(_QWORD *)nSize),
                  v11 = STRU::Append((STRU *)v44, Buffer),
                  v11 >= 0)
              && (v11 = STRU::Append((STRU *)v42, Buffer), v11 >= 0) )
            {
              v12 = *((_QWORD *)this + 1);
              v13 = a2[3];
              v14 = *((_DWORD *)a2 + 8);
              v15 = *((_DWORD *)a2 + 4);
              v16 = v43;
              **(_WORD **)(v12 + 32) = 0;
              *(_DWORD *)(v12 + 48) = 0;
              **(_WORD **)(v12 + 88) = 0;
              *(_DWORD *)(v12 + 104) = 0;
              *(_QWORD *)(v12 + 112) = v13;
              *(_DWORD *)(v12 + 120) = v15;
              *(_DWORD *)(v12 + 124) = v14;
              *(_QWORD *)(v12 + 148) = 0;
              *(_DWORD *)(v12 + 128) = 0;
              *(_DWORD *)(v12 + 156) = a3;
              *(_DWORD *)(v12 + 160) = 0;
              v11 = STRU::Copy((STRU *)v12, v16);
              if ( v11 >= 0 )
              {
                if ( !*((_DWORD *)a2 + 9) || !*(_DWORD *)a2 )
                  v10 = 0;
                *((_DWORD *)this + 20) = v10;
                v17 = *(_DWORD *)a2 ^ (*((_DWORD *)this + 21) ^ *(_DWORD *)a2) & 0xFFFFFFFE;
                *((_DWORD *)this + 21) = v17;
                v18 = v17 & 0xFFFFFFFD | *(_DWORD *)a2 & 2;
                *((_DWORD *)this + 21) = v18;
                v19 = v18 & 0xFFFFFFFB | *(_DWORD *)a2 & 4;
                *((_DWORD *)this + 21) = v19;
                v20 = v19 & 0xFFFFFFF7 | (*(_DWORD *)a2 >> 22) & 8;
                *((_DWORD *)this + 21) = v20;
                v21 = v20 & 0xFFFFFFEF | (2 * (*(_DWORD *)a2 & 8));
                *((_DWORD *)this + 21) = v21;
                v22 = v21 & 0xFFFFFFDF | (2 * (*(_DWORD *)a2 & 0x10));
                *((_DWORD *)this + 21) = v22;
                v23 = v22 & 0xFFFFFFBF | (2 * (*(_DWORD *)a2 & 0x20));
                *((_DWORD *)this + 21) = v23;
                v24 = v23 & 0xFFFFDFFF | (*(_DWORD *)a2 >> 7) & 0x2000;
                *((_DWORD *)this + 21) = v24;
                v25 = v24 & 0xFFFFFF7F | (2 * (*(_DWORD *)a2 & 0x40));
                *((_DWORD *)this + 21) = v25;
                v26 = v25 & 0xFFFFFEFF | (*(_DWORD *)a2 >> 7) & 0x100;
                *((_DWORD *)this + 21) = v26;
                v27 = v26 & 0xFFFFFDFF | (4 * (*(_DWORD *)a2 & 0x80));
                *((_DWORD *)this + 21) = v27;
                v28 = v27 & 0xFFFFFBFF | (4 * (*(_DWORD *)a2 & 0x100));
                *((_DWORD *)this + 21) = v28;
                v29 = v28 & 0xFFFFF7FF | (2 * (*(_DWORD *)a2 & 0x400));
                *((_DWORD *)this + 21) = v29;
                v30 = v29 & 0xFFFFEFFF | (2 * (*(_DWORD *)a2 & 0x800));
                *((_DWORD *)this + 21) = v30;
                v31 = v30 & 0xFFFFBFFF | (*(_DWORD *)a2 >> 7) & 0x4000;
                *((_DWORD *)this + 21) = v31;
                v32 = v31 & 0xFFFF7FFF | (8 * (*(_DWORD *)a2 & 0x1000));
                *((_DWORD *)this + 21) = v32;
                v33 = v32 & 0xFFFEFFFF | (8 * (*(_DWORD *)a2 & 0x2000));
                *((_DWORD *)this + 21) = v33;
                v34 = v33 & 0xFFFDFFFF | (8 * (*(_DWORD *)a2 & 0x4000));
                *((_DWORD *)this + 21) = v34;
                v35 = v34 & 0xFFFBFFFF | (*(_DWORD *)a2 >> 4) & 0x40000;
                *((_DWORD *)this + 21) = v35;
                v36 = v35 & 0xFFF7FFFF | (*(_DWORD *)a2 >> 4) & 0x80000;
                *((_DWORD *)this + 21) = v36;
                v37 = v36 & 0xFFEFFFFF | (*(_DWORD *)a2 >> 6) & 0x100000;
                *((_DWORD *)this + 21) = v37;
                v38 = v37 & 0xFFDFFFFF | (*(_DWORD *)a2 >> 3) & 0x200000;
                *((_DWORD *)this + 21) = v38;
                *((_DWORD *)this + 22) = *((_DWORD *)a2 + 5);
                if ( (v38 & 0x40) != 0 )
                {
                  nSize[0] = 260;
                  if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, WideCharStr, nSize)
                    || (nSize[0] = 260, GetComputerNameExW(ComputerNamePhysicalDnsHostname, WideCharStr, nSize)) )
                  {
                    v11 = ConvertFromUnicode(WideCharStr, a3 != 0 ? 0xFDE9 : 0, (FTP_LOGGING *)((char *)this + 24));
                  }
                  else
                  {
                    LastError = GetLastError();
                    v11 = LastError;
                    if ( LastError > 0 )
                      v11 = (unsigned __int16)LastError | 0x80070000;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v11 = -2147024882;
  }
  CReaderWriterLock3::WriteUnlock((FTP_LOGGING *)((char *)this + 92));
  STRU::~STRU(v44);
  STRU::~STRU(v42);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180027010  mov     [rsp-8+arg_10], rbx
0x180027015  push    rbp
0x180027016  push    rsi
0x180027017  push    rdi
0x180027018  push    r12
0x18002701a  push    r13
0x18002701c  push    r14
0x18002701e  push    r15
0x180027020  lea     rbp, [rsp-1D0h]
0x180027028  sub     rsp, 2D0h
0x18002702f  mov     rax, cs:__security_cookie
0x180027036  xor     rax, rsp
0x180027039  mov     [rbp+200h+var_40], rax
0x180027040  mov     r13d, r9d
0x180027043  mov     r15d, r8d
0x180027046  mov     rdi, rdx
0x180027049  mov     rsi, rcx
0x18002704c  lea     rcx, [rsp+300h+var_2D8]
0x180027051  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027057  nop
0x180027058  lea     rcx, [rsp+300h+var_2A0]
0x18002705d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027063  nop
0x180027064  lea     rcx, [rsi+5Ch]
0x180027068  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18002706e  mov     ecx, 0A8h; Size
0x180027073  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027078  mov     rbx, rax
0x18002707b  mov     qword ptr [rsp+300h+nSize], rax
0x180027080  xor     eax, eax
0x180027082  lea     r14d, [rax+1]
0x180027086  test    rbx, rbx
0x180027089  jz      short loc_1800270C7
0x18002708b  mov     rcx, rbx
0x18002708e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180027094  nop
0x180027095  lea     rcx, [rbx+38h]
0x180027099  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18002709f  xor     eax, eax
0x1800270a1  mov     [rbx+70h], rax
0x1800270a5  mov     qword ptr [rbx+78h], 1
0x1800270ad  mov     [rbx+80h], eax
0x1800270b3  mov     [rbx+94h], rax
0x1800270ba  mov     qword ptr [rbx+9Ch], 1
0x1800270c5  jmp     short loc_1800270CA
0x1800270c7  mov     rbx, rax
0x1800270ca  mov     [rsi+8], rbx
0x1800270ce  test    rbx, rbx
0x1800270d1  jnz     short loc_1800270DD
0x1800270d3  mov     ebx, 8007000Eh
0x1800270d8  jmp     loc_180027425
0x1800270dd  lea     rdx, aFtpsvc; "FTPSVC"
0x1800270e4  lea     rcx, [rsp+300h+var_2A0]
0x1800270e9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800270ef  mov     ebx, eax
0x1800270f1  test    eax, eax
0x1800270f3  js      loc_180027425
0x1800270f9  mov     rdx, [rdi+8]
0x1800270fd  lea     rcx, [rsp+300h+var_2D8]
0x180027102  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180027108  mov     ebx, eax
0x18002710a  test    eax, eax
0x18002710c  js      loc_180027425
0x180027112  lea     rdx, asc_18004BD10; "\\"
0x180027119  lea     rcx, [rsp+300h+var_2D8]
0x18002711e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180027124  mov     ebx, eax
0x180027126  test    eax, eax
0x180027128  js      loc_180027425
0x18002712e  lea     rdx, aFtpsvc; "FTPSVC"
0x180027135  lea     rcx, [rsp+300h+var_2D8]
0x18002713a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180027140  mov     ebx, eax
0x180027142  test    eax, eax
0x180027144  js      loc_180027425
0x18002714a  test    r13d, r13d
0x18002714d  jz      short loc_1800271A3
0x18002714f  mov     r9d, [rbp+200h+arg_20]
0x180027156  lea     r8, aLu; "%lu"
0x18002715d  mov     edx, 0Bh; BufferCount
0x180027162  lea     rcx, [rbp+200h+Buffer]; Buffer
0x180027166  call    cs:__imp_swprintf_s
0x18002716c  lea     rdx, [rbp+200h+Buffer]
0x180027170  lea     rcx, [rsp+300h+var_2A0]
0x180027175  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002717b  mov     ebx, eax
0x18002717d  xor     r13d, r13d
0x180027180  test    eax, eax
0x180027182  js      loc_180027425
0x180027188  lea     rdx, [rbp+200h+Buffer]
0x18002718c  lea     rcx, [rsp+300h+var_2D8]
0x180027191  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180027197  mov     ebx, eax
0x180027199  test    eax, eax
0x18002719b  js      loc_180027425
0x1800271a1  jmp     short loc_1800271A6
0x1800271a3  xor     r13d, r13d
0x1800271a6  mov     rbx, [rsi+8]
0x1800271aa  mov     r10, [rdi+18h]
0x1800271ae  mov     r11d, [rdi+20h]
0x1800271b2  mov     r9d, [rdi+10h]
0x1800271b6  mov     rdx, [rsp+300h+var_2B8]
0x1800271bb  mov     rcx, [rbx+20h]
0x1800271bf  mov     [rcx], r13w
0x1800271c3  mov     [rbx+30h], r13d
0x1800271c7  mov     r8, [rbx+58h]
0x1800271cb  mov     [r8], r13w
0x1800271cf  mov     [rbx+68h], r13d
0x1800271d3  mov     [rbx+70h], r10
0x1800271d7  mov     [rbx+78h], r9d
0x1800271db  mov     [rbx+7Ch], r11d
0x1800271df  mov     qword ptr [rbx+94h], 0
0x1800271ea  mov     [rbx+80h], r13d
0x1800271f1  mov     [rbx+9Ch], r15d
0x1800271f8  mov     [rbx+0A0h], r13d
0x1800271ff  mov     rcx, rbx
0x180027202  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180027208  mov     ebx, eax
0x18002720a  test    eax, eax
0x18002720c  js      loc_180027425
0x180027212  cmp     [rdi+24h], r13d
0x180027216  jz      short loc_18002721D
0x180027218  cmp     [rdi], r13d
0x18002721b  jnz     short loc_180027220
0x18002721d  mov     r14d, r13d
0x180027220  mov     [rsi+50h], r14d
0x180027224  mov     eax, [rdi]
0x180027226  xor     eax, [rsi+54h]
0x180027229  and     eax, 0FFFFFFFEh
0x18002722c  xor     eax, [rdi]
0x18002722e  mov     [rsi+54h], eax
0x180027231  mov     ecx, [rdi]
0x180027233  and     ecx, 2
0x180027236  and     eax, 0FFFFFFFDh
0x180027239  or      ecx, eax
0x18002723b  mov     [rsi+54h], ecx
0x18002723e  mov     eax, [rdi]
0x180027240  and     eax, 4
0x180027243  and     ecx, 0FFFFFFFBh
0x180027246  or      eax, ecx
0x180027248  mov     [rsi+54h], eax
0x18002724b  mov     ecx, [rdi]
0x18002724d  shr     ecx, 16h
0x180027250  and     ecx, 8
0x180027253  and     eax, 0FFFFFFF7h
0x180027256  or      ecx, eax
0x180027258  mov     [rsi+54h], ecx
0x18002725b  mov     eax, [rdi]
0x18002725d  and     eax, 8
0x180027260  add     eax, eax
0x180027262  and     ecx, 0FFFFFFEFh
0x180027265  or      eax, ecx
0x180027267  mov     [rsi+54h], eax
0x18002726a  mov     ecx, [rdi]
0x18002726c  and     ecx, 10h
0x18002726f  add     ecx, ecx
0x180027271  and     eax, 0FFFFFFDFh
0x180027274  or      ecx, eax
0x180027276  mov     [rsi+54h], ecx
0x180027279  mov     eax, [rdi]
0x18002727b  and     eax, 20h
0x18002727e  add     eax, eax
0x180027280  and     ecx, 0FFFFFFBFh
0x180027283  or      eax, ecx
0x180027285  mov     [rsi+54h], eax
0x180027288  mov     ecx, [rdi]
0x18002728a  shr     ecx, 7
0x18002728d  mov     r9d, 2000h
0x180027293  and     ecx, r9d
0x180027296  btr     eax, 0Dh
0x18002729a  or      ecx, eax
0x18002729c  mov     [rsi+54h], ecx
0x18002729f  mov     eax, [rdi]
0x1800272a1  and     eax, 40h
0x1800272a4  add     eax, eax
0x1800272a6  btr     ecx, 7
0x1800272aa  or      eax, ecx
0x1800272ac  mov     [rsi+54h], eax
0x1800272af  mov     ecx, [rdi]
0x1800272b1  shr     ecx, 7
0x1800272b4  mov     edx, 100h
0x1800272b9  and     ecx, edx
0x1800272bb  btr     eax, 8
0x1800272bf  or      ecx, eax
0x1800272c1  mov     [rsi+54h], ecx
0x1800272c4  mov     eax, [rdi]
0x1800272c6  and     eax, 80h
0x1800272cb  shl     eax, 2
0x1800272ce  btr     ecx, 9
0x1800272d2  or      eax, ecx
0x1800272d4  mov     [rsi+54h], eax
0x1800272d7  mov     ecx, [rdi]
0x1800272d9  and     ecx, edx
0x1800272db  shl     ecx, 2
0x1800272de  btr     eax, 0Ah
0x1800272e2  or      ecx, eax
0x1800272e4  mov     [rsi+54h], ecx
0x1800272e7  mov     eax, [rdi]
0x1800272e9  and     eax, 400h
0x1800272ee  add     eax, eax
0x1800272f0  btr     ecx, 0Bh
0x1800272f4  or      eax, ecx
0x1800272f6  mov     [rsi+54h], eax
0x1800272f9  mov     ecx, [rdi]
0x1800272fb  and     ecx, 800h
0x180027301  add     ecx, ecx
0x180027303  btr     eax, 0Ch
0x180027307  or      ecx, eax
0x180027309  mov     [rsi+54h], ecx
0x18002730c  mov     edx, [rdi]
0x18002730e  shr     edx, 7
0x180027311  mov     r8d, 4000h
0x180027317  and     edx, r8d
0x18002731a  btr     ecx, 0Eh
0x18002731e  or      edx, ecx
0x180027320  mov     [rsi+54h], edx
0x180027323  mov     eax, [rdi]
0x180027325  and     eax, 1000h
0x18002732a  shl     eax, 3
0x18002732d  btr     edx, 0Fh
0x180027331  or      eax, edx
0x180027333  mov     [rsi+54h], eax
0x180027336  mov     ecx, [rdi]
0x180027338  and     ecx, r9d
0x18002733b  shl     ecx, 3
0x18002733e  btr     eax, 10h
0x180027342  or      ecx, eax
0x180027344  mov     [rsi+54h], ecx
0x180027347  mov     eax, [rdi]
0x180027349  and     eax, r8d
0x18002734c  shl     eax, 3
0x18002734f  btr     ecx, 11h
0x180027353  or      eax, ecx
0x180027355  mov     [rsi+54h], eax
0x180027358  mov     ecx, [rdi]
0x18002735a  shr     ecx, 4
0x18002735d  and     ecx, 40000h
0x180027363  btr     eax, 12h
0x180027367  or      ecx, eax
0x180027369  mov     [rsi+54h], ecx
0x18002736c  mov     eax, [rdi]
0x18002736e  shr     eax, 4
0x180027371  and     eax, 80000h
0x180027376  btr     ecx, 13h
0x18002737a  or      eax, ecx
0x18002737c  mov     [rsi+54h], eax
0x18002737f  mov     r8d, [rdi]
0x180027382  shr     r8d, 6
0x180027386  and     r8d, 100000h
0x18002738d  btr     eax, 14h
0x180027391  or      r8d, eax
0x180027394  mov     [rsi+54h], r8d
0x180027398  mov     edx, [rdi]
0x18002739a  shr     edx, 3
0x18002739d  and     edx, 200000h
0x1800273a3  btr     r8d, 15h
0x1800273a8  or      edx, r8d
0x1800273ab  mov     [rsi+54h], edx
0x1800273ae  mov     eax, [rdi+14h]
0x1800273b1  mov     [rsi+58h], eax
0x1800273b4  test    dl, 40h
0x1800273b7  jz      short loc_180027425
0x1800273b9  mov     ebx, 104h
0x1800273be  mov     [rsp+300h+nSize], ebx
0x1800273c2  lea     r8, [rsp+300h+nSize]; nSize
0x1800273c7  lea     rdx, [rbp+200h+WideCharStr]; lpBuffer
0x1800273cb  mov     ecx, 4; NameType
0x1800273d0  call    cs:__imp_GetComputerNameExW
0x1800273d6  test    eax, eax
0x1800273d8  jnz     short loc_18002740B
0x1800273da  mov     [rsp+300h+nSize], ebx
0x1800273de  lea     r8, [rsp+300h+nSize]; nSize
0x1800273e3  lea     rdx, [rbp+200h+WideCharStr]; lpBuffer
0x1800273e7  lea     ecx, [rax+5]; NameType
0x1800273ea  call    cs:__imp_GetComputerNameExW
0x1800273f0  test    eax, eax
0x1800273f2  jnz     short loc_18002740B
0x1800273f4  call    cs:__imp_GetLastError
0x1800273fa  mov     ebx, eax
0x1800273fc  test    eax, eax
0x1800273fe  jle     short loc_180027425
0x180027400  movzx   ebx, ax
0x180027403  or      ebx, 80070000h
0x180027409  jmp     short loc_180027425
0x18002740b  lea     r8, [rsi+18h]; struct STRA *
0x18002740f  neg     r15d
0x180027412  sbb     edx, edx
0x180027414  and     edx, 0FDE9h; CodePage
0x18002741a  lea     rcx, [rbp+200h+WideCharStr]; lpWideCharStr
0x18002741e  call    ?ConvertFromUnicode@@YAJPEBGKPEAVSTRA@@@Z; ConvertFromUnicode(ushort const *,ulong,STRA *)
0x180027423  mov     ebx, eax
0x180027425  lea     rcx, [rsi+5Ch]
0x180027429  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002742f  nop
0x180027430  lea     rcx, [rsp+300h+var_2A0]
0x180027435  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002743b  nop
0x18002743c  lea     rcx, [rsp+300h+var_2D8]
0x180027441  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180027447  mov     eax, ebx
  ... truncated ...
```
