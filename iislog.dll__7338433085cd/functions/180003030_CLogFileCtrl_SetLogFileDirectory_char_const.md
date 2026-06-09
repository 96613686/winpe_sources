# CLogFileCtrl::SetLogFileDirectory(char const *)

- ea: `0x180003030`
- end: `0x18000322b`
- name: `?SetLogFileDirectory@CLogFileCtrl@@AEAAXPEBD@Z`
- size: `507`
- prototype: `void(CLogFileCtrl *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800024d0`
- `0x180003000`

## callees

- `0x180003030`
- `0x18000ec62`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `msvcrt!strchr` at `0x18000313d`
- `msvcrt!strchr` at `0x18000313d`
- `msvcrt!isdigit` at `0x180003162`
- `msvcrt!isdigit` at `0x180003162`
- `msvcrt!atoi` at `0x18000317a`
- `msvcrt!atoi` at `0x18000317a`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180003067`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180003067`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800031ff`
- `IisRTL!??1STR@@QEAA@XZ` at `0x1800031ff`
- `IisRTL!PuDbgPrint` at `0x1800031c7`
- `IisRTL!PuDbgPrint` at `0x1800031c7`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030ce`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030e0`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030f2`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000310f`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030ce`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030e0`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x1800030f2`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x18000310f`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180003088`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800030a7`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180003088`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800030a7`
- `KERNEL32!FindFirstFileA` at `0x18000311e`
- `KERNEL32!FindFirstFileA` at `0x18000311e`
- `KERNEL32!FindNextFileA` at `0x1800031d4`
- `KERNEL32!FindNextFileA` at `0x1800031d4`
- `KERNEL32!FindClose` at `0x1800031e5`
- `KERNEL32!FindClose` at `0x1800031e5`
- `USER32!CharPrevA` at `0x1800030b7`
- `USER32!CharPrevA` at `0x1800030b7`

## string_xrefs

- `0x1800031b5`: `inetsrv\iis\svcs\infocomm\log\plugin\filectl.cpp`
- `0x1800031aa`: `CLogFileCtrl::SetLogFileDirectory`

## pseudocode

```c
void __fastcall CLogFileCtrl::SetLogFileDirectory(CLogFileCtrl *this, const char *a2)
{
  const char *v4; // rax
  HANDLE FirstFileA; // r15
  DWORD nFileSizeLow; // r14d
  char *v7; // rax
  unsigned int v8; // edi
  unsigned __int8 v9; // al
  CHAR *cFileName; // rsi
  bool v11; // zf
  _BYTE v12[32]; // [rsp+40h] [rbp-C0h] BYREF
  LPCSTR lpFileName; // [rsp+60h] [rbp-A0h]
  int v14; // [rsp+70h] [rbp-90h]
  _WIN32_FIND_DATAA FindFileData; // [rsp+80h] [rbp-80h] BYREF

  STR::STR((STR *)v12);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  STR::Copy((CLogFileCtrl *)((char *)this + 240), a2);
  if ( !*((_DWORD *)this + 27) )
  {
    *((_DWORD *)this + 18) = 1;
    STR::Copy((STR *)v12, a2);
    if ( *CharPrevA(a2, &a2[v14]) != 92 )
      STR::Append((STR *)v12, "\\");
    STR::Append((STR *)v12, *((const char **)this + 20));
    STR::Append((STR *)v12, "\\");
    v4 = (const char *)(*(__int64 (__fastcall **)(CLogFileCtrl *))(*(_QWORD *)this + 120LL))(this);
    STR::Append((STR *)v12, v4);
    FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
    if ( FirstFileA != (HANDLE)-1LL )
    {
      nFileSizeLow = 0;
      do
      {
        v7 = strchr(FindFileData.cFileName, 46);
        if ( v7 )
        {
          *v7 = 0;
          v8 = 1;
          v9 = FindFileData.cFileName[0];
          if ( FindFileData.cFileName[0] )
          {
            cFileName = FindFileData.cFileName;
            while ( !isdigit(v9) )
            {
              v9 = *++cFileName;
              if ( !*cFileName )
                goto LABEL_13;
            }
            v8 = atoi(cFileName);
          }
LABEL_13:
          if ( v8 > *((_DWORD *)this + 18) )
          {
            v11 = (g_dwDebugFlags & 3) == 0;
            nFileSizeLow = FindFileData.nFileSizeLow;
            *((_DWORD *)this + 18) = v8;
            if ( !v11 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\filectl.cpp",
                975,
                "CLogFileCtrl::SetLogFileDirectory",
                "Sequence start is %d[%d]\n",
                v8,
                nFileSizeLow);
          }
        }
      }
      while ( FindNextFileA(FirstFileA, &FindFileData) );
      FindClose(FirstFileA);
      if ( nFileSizeLow + 512 > *((_DWORD *)this + 26) )
        ++*((_DWORD *)this + 18);
    }
  }
  STR::~STR((STR *)v12);
}

```

## disassembly

```asm
0x180003030  mov     [rsp-8+arg_10], rbx
0x180003035  push    rbp
0x180003036  push    rsi
0x180003037  push    rdi
0x180003038  push    r14
0x18000303a  push    r15
0x18000303c  lea     rbp, [rsp-0D0h]
0x180003044  sub     rsp, 1D0h
0x18000304b  mov     rax, cs:__security_cookie
0x180003052  xor     rax, rsp
0x180003055  mov     [rbp+0F0h+var_30], rax
0x18000305c  mov     rbx, rcx
0x18000305f  mov     rdi, rdx
0x180003062  lea     rcx, [rsp+1F0h+var_1B0]
0x180003067  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x18000306d  xor     edx, edx; Val
0x18000306f  lea     rcx, [rbp+0F0h+FindFileData]; void *
0x180003073  mov     r8d, 140h; Size
0x180003079  call    memset_0
0x18000307e  lea     rcx, [rbx+0F0h]
0x180003085  mov     rdx, rdi
0x180003088  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000308e  cmp     dword ptr [rbx+6Ch], 0
0x180003092  jnz     loc_1800031FA
0x180003098  mov     rdx, rdi
0x18000309b  mov     dword ptr [rbx+48h], 1
0x1800030a2  lea     rcx, [rsp+1F0h+var_1B0]
0x1800030a7  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x1800030ad  mov     edx, [rsp+1F0h+var_180]
0x1800030b1  mov     rcx, rdi; lpszStart
0x1800030b4  add     rdx, rdi; lpszCurrent
0x1800030b7  call    cs:__imp_CharPrevA
0x1800030bd  cmp     byte ptr [rax], 5Ch ; '\'
0x1800030c0  jz      short loc_1800030D4
0x1800030c2  lea     rdx, asc_1800130D0; "\\"
0x1800030c9  lea     rcx, [rsp+1F0h+var_1B0]
0x1800030ce  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x1800030d4  mov     rdx, [rbx+0A0h]
0x1800030db  lea     rcx, [rsp+1F0h+var_1B0]
0x1800030e0  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x1800030e6  lea     rdx, asc_1800130D0; "\\"
0x1800030ed  lea     rcx, [rsp+1F0h+var_1B0]
0x1800030f2  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x1800030f8  mov     rax, [rbx]
0x1800030fb  mov     rcx, rbx
0x1800030fe  mov     rax, [rax+78h]
0x180003102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003107  mov     rdx, rax
0x18000310a  lea     rcx, [rsp+1F0h+var_1B0]
0x18000310f  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180003115  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x18000311a  lea     rdx, [rbp+0F0h+FindFileData]; lpFindFileData
0x18000311e  call    cs:__imp_FindFirstFileA
0x180003124  mov     r15, rax
0x180003127  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000312b  jz      loc_1800031FA
0x180003131  xor     r14d, r14d
0x180003134  mov     edx, 2Eh ; '.'; Val
0x180003139  lea     rcx, [rbp+0F0h+FindFileData.cFileName]; Str
0x18000313d  call    cs:__imp_strchr
0x180003143  test    rax, rax
0x180003146  jz      loc_1800031CD
0x18000314c  mov     byte ptr [rax], 0
0x18000314f  mov     edi, 1
0x180003154  mov     al, [rbp+0F0h+FindFileData.cFileName]
0x180003157  test    al, al
0x180003159  jz      short loc_180003182
0x18000315b  lea     rsi, [rbp+0F0h+FindFileData.cFileName]
0x18000315f  movzx   ecx, al; C
0x180003162  call    cs:__imp_isdigit
0x180003168  test    eax, eax
0x18000316a  jnz     short loc_180003177
0x18000316c  inc     rsi
0x18000316f  mov     al, [rsi]
0x180003171  test    al, al
0x180003173  jnz     short loc_18000315F
0x180003175  jmp     short loc_180003182
0x180003177  mov     rcx, rsi; String
0x18000317a  call    cs:__imp_atoi
0x180003180  mov     edi, eax
0x180003182  cmp     edi, [rbx+48h]
0x180003185  jbe     short loc_1800031CD
0x180003187  test    byte ptr cs:g_dwDebugFlags, 3
0x18000318e  mov     r14d, [rbp+0F0h+FindFileData.nFileSizeLow]
0x180003192  mov     [rbx+48h], edi
0x180003195  jz      short loc_1800031CD
0x180003197  mov     rcx, cs:g_pDebug
0x18000319e  lea     rax, aSequenceStartI; "Sequence start is %d[%d]\n"
0x1800031a5  mov     [rsp+1F0h+var_1C0], r14d
0x1800031aa  lea     r9, aClogfilectrlSe; "CLogFileCtrl::SetLogFileDirectory"
0x1800031b1  mov     [rsp+1F0h+var_1C8], edi
0x1800031b5  lea     rdx, aInetsrvIisSvcs_0; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x1800031bc  mov     r8d, 3CFh
0x1800031c2  mov     [rsp+1F0h+var_1D0], rax
0x1800031c7  call    cs:__imp_PuDbgPrint
0x1800031cd  lea     rdx, [rbp+0F0h+FindFileData]; lpFindFileData
0x1800031d1  mov     rcx, r15; hFindFile
0x1800031d4  call    cs:__imp_FindNextFileA
0x1800031da  test    eax, eax
0x1800031dc  jnz     loc_180003134
0x1800031e2  mov     rcx, r15; hFindFile
0x1800031e5  call    cs:__imp_FindClose
0x1800031eb  lea     eax, [r14+200h]
0x1800031f2  cmp     eax, [rbx+68h]
0x1800031f5  jbe     short loc_1800031FA
0x1800031f7  inc     dword ptr [rbx+48h]
0x1800031fa  lea     rcx, [rsp+1F0h+var_1B0]
0x1800031ff  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180003205  mov     rcx, [rbp+0F0h+var_30]
0x18000320c  xor     rcx, rsp; StackCookie
0x18000320f  call    __security_check_cookie
0x180003214  mov     rbx, [rsp+1F0h+arg_10]
0x18000321c  add     rsp, 1D0h
0x180003223  pop     r15
0x180003225  pop     r14
0x180003227  pop     rdi
0x180003228  pop     rsi
0x180003229  pop     rbp
0x18000322a  retn
```
