# CTitleDatabase::CheckWordWheels(void)

- ea: `0x180073134`
- end: `0x1800733e4`
- name: `?CheckWordWheels@CTitleDatabase@@QEAAHXZ`
- size: `688`
- prototype: `__int64 __fastcall(CTitleDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800756e0`

## callees

- `0x180001728`
- `0x18000b3f0`
- `0x18004f538`
- `0x180072978`
- `0x180073134`
- `0x1800737c8`
- `0x180073870`
- `0x180074284`
- `0x1800743d4`
- `0x180074538`
- `0x180075850`
- `0x1800759a4`
- `0x180075a18`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180073252`
- `KERNEL32!CloseHandle` at `0x180073252`
- `KERNEL32!lstrcmpiA` at `0x18007333c`
- `KERNEL32!lstrcmpiA` at `0x18007333c`
- `KERNEL32!CreateFileA` at `0x180073243`
- `KERNEL32!CreateFileA` at `0x180073243`
- `KERNEL32!CompareFileTime` at `0x18007334e`
- `KERNEL32!CompareFileTime` at `0x18007334e`
- `KERNEL32!Sleep` at `0x180073207`
- `KERNEL32!Sleep` at `0x180073207`

## pseudocode

```c
__int64 __fastcall CTitleDatabase::CheckWordWheels(CTitleDatabase *this)
{
  signed int v2; // r13d
  _QWORD *v3; // rax
  signed int v4; // r14d
  signed int v5; // edi
  __int64 i; // rbx
  struct CTitleMapEntry *v7; // rax
  unsigned int v8; // ebx
  const CHAR *v9; // rcx
  HANDLE v10; // rax
  unsigned int v11; // edx
  void *v12; // rdi
  unsigned int v13; // edx
  int v14; // r15d
  signed int v15; // r12d
  CTitleMapEntry *v16; // rbx
  CTitleMapEntry *v17; // rax
  CTitleMapEntry *v18; // rbx
  int (*v19)(const void *, const void *); // rdx
  CTitleMap *v21; // rcx
  const CHAR *lpString2; // [rsp+40h] [rbp-38h]
  FILETIME FileTime2; // [rsp+48h] [rbp-30h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-20h] BYREF
  unsigned int Language; // [rsp+C0h] [rbp+48h]
  unsigned int v27; // [rsp+C8h] [rbp+50h]
  int v28; // [rsp+D0h] [rbp+58h]
  const CHAR *lpString1; // [rsp+D8h] [rbp+60h]

  v2 = *(_DWORD *)(*((_QWORD *)this + 36) + 1000LL);
  v3 = operator new(0x20u);
  v4 = 0;
  if ( v3 )
  {
    v3[1] = 0;
    *((_DWORD *)v3 + 4) = -1;
    v3[3] = 0;
    *(_DWORD *)v3 = 1;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 40) = v3;
  if ( v3 )
  {
    CTitleMap::SetCount((CTitleMap *)v3, v2);
    v5 = 0;
    for ( i = *(_QWORD *)(*((_QWORD *)this + 36) + 1080LL); v5 < v2; ++v5 )
    {
      v7 = CTitleMap::GetAt(*((CTitleMap **)this + 40), v5);
      if ( v7 )
      {
        *((_QWORD *)v7 + 1) = i;
        if ( i )
          i = *(_QWORD *)(i + 104);
      }
    }
    if ( !(unsigned int)IsFile(*((const char **)this + 2)) )
      return 1;
    while ( 1 )
    {
      v9 = (const CHAR *)*((_QWORD *)this + 2);
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = 0;
      v10 = CreateFileA(v9, 0x80000000, 1u, &SecurityAttributes, 3u, 0x80u, 0);
      if ( v10 != (HANDLE)-1LL )
        break;
      Sleep(0x64u);
      NextAnimation();
    }
    CloseHandle(v10);
    v12 = operator new(0x20u);
    if ( v12 )
    {
      *((_QWORD *)v12 + 1) = *((_QWORD *)this + 2);
      *(_DWORD *)v12 = 0;
      *((_DWORD *)v12 + 4) = -1;
      *((_QWORD *)v12 + 3) = 0;
      CTitleMap::Init((CTitleMap *)v12);
      v14 = *((_DWORD *)v12 + 4);
      if ( v14 == v2 )
      {
        v15 = 0;
        if ( v14 <= 0 )
        {
          v8 = 0;
        }
        else
        {
          while ( 2 )
          {
            v16 = CTitleMap::GetAt((CTitleMap *)v12, v15);
            lpString1 = CTitleMapEntry::GetShortName(v16);
            CTitleMapEntry::GetFileTime(v16);
            Language = CTitleMapEntry::GetLanguage(v16);
            v28 = *(_DWORD *)v16;
            while ( 1 )
            {
              if ( v4 >= v2 )
              {
                v8 = 1;
                goto LABEL_32;
              }
              v17 = CTitleMap::GetAt(*((CTitleMap **)this + 40), v4);
              v18 = v17;
              if ( v17 )
              {
                lpString2 = CTitleMapEntry::GetShortName(v17);
                CTitleMapEntry::GetFileTime(v18);
                v27 = CTitleMapEntry::GetLanguage(v18);
                if ( lpString1 )
                {
                  if ( !lstrcmpiA(lpString1, lpString2)
                    && !CompareFileTime(&FileTime1, &FileTime2)
                    && Language == v27
                    && !*(_DWORD *)v18 )
                  {
                    break;
                  }
                }
              }
              ++v4;
            }
            *(_DWORD *)v18 = v28;
            CTitleMapEntry::SetShortName(v18, lpString1);
            v4 = 0;
            ++v15;
            v8 = 0;
            if ( v15 < v14 )
              continue;
            break;
          }
        }
      }
      else
      {
        v8 = 1;
      }
LABEL_32:
      CTitleMap::`scalar deleting destructor'((CTitleMap *)v12, v13);
      if ( !v8 )
        CTitleMap::Sort(*((CTitleMap **)this + 40), v19);
      return v8;
    }
    v21 = (CTitleMap *)*((_QWORD *)this + 40);
    if ( v21 )
      CTitleMap::`scalar deleting destructor'(v21, v11);
    *((_QWORD *)this + 40) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180073134  push    rbp
0x180073136  push    rbx
0x180073137  push    rsi
0x180073138  push    rdi
0x180073139  push    r12
0x18007313b  push    r13
0x18007313d  push    r14
0x18007313f  push    r15
0x180073141  mov     rbp, rsp
0x180073144  sub     rsp, 78h
0x180073148  mov     rax, [rcx+120h]
0x18007314f  mov     rsi, rcx
0x180073152  mov     ecx, 20h ; ' '; Size
0x180073157  mov     r13d, [rax+3E8h]
0x18007315e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073163  or      r15d, 0FFFFFFFFh
0x180073167  mov     [rbp+arg_0], rax
0x18007316b  xor     r14d, r14d
0x18007316e  mov     r12d, 1
0x180073174  test    rax, rax
0x180073177  jz      short loc_18007318A
0x180073179  mov     [rax+8], r14
0x18007317d  mov     [rax+10h], r15d
0x180073181  mov     [rax+18h], r14
0x180073185  mov     [rax], r12d
0x180073188  jmp     short loc_18007318D
0x18007318a  mov     rax, r14
0x18007318d  mov     [rsi+140h], rax
0x180073194  test    rax, rax
0x180073197  jz      loc_1800733D0
0x18007319d  mov     edx, r13d; unsigned int
0x1800731a0  mov     rcx, rax; this
0x1800731a3  call    ?SetCount@CTitleMap@@QEAAKK@Z; CTitleMap::SetCount(ulong)
0x1800731a8  mov     rax, [rsi+120h]
0x1800731af  mov     edi, r14d
0x1800731b2  mov     rbx, [rax+438h]
0x1800731b9  test    r13d, r13d
0x1800731bc  jle     short loc_1800731E6
0x1800731be  mov     rcx, [rsi+140h]; this
0x1800731c5  mov     edx, edi; unsigned int
0x1800731c7  call    ?GetAt@CTitleMap@@QEAAPEAVCTitleMapEntry@@K@Z; CTitleMap::GetAt(ulong)
0x1800731cc  test    rax, rax
0x1800731cf  jz      short loc_1800731DE
0x1800731d1  mov     [rax+8], rbx
0x1800731d5  test    rbx, rbx
0x1800731d8  jz      short loc_1800731DE
0x1800731da  mov     rbx, [rbx+68h]
0x1800731de  add     edi, r12d
0x1800731e1  cmp     edi, r13d
0x1800731e4  jl      short loc_1800731BE
0x1800731e6  mov     rcx, [rsi+10h]; char *
0x1800731ea  call    ?IsFile@@YAHPEBD@Z; IsFile(char const *)
0x1800731ef  test    eax, eax
0x1800731f1  jnz     short loc_1800731FB
0x1800731f3  mov     ebx, r12d
0x1800731f6  jmp     loc_1800733B4
0x1800731fb  mov     edi, 80h
0x180073200  jmp     short loc_180073212
0x180073202  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180073207  call    cs:__imp_Sleep
0x18007320d  call    ?NextAnimation@@YAXXZ; NextAnimation(void)
0x180073212  mov     rcx, [rsi+10h]; lpFileName
0x180073216  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18007321a  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x18007321f  mov     r8d, r12d; dwShareMode
0x180073222  mov     [rsp+78h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180073226  mov     edx, 80000000h; dwDesiredAccess
0x18007322b  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180073233  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18007323b  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], r14
0x18007323f  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], r14
0x180073243  call    cs:__imp_CreateFileA
0x180073249  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007324d  jz      short loc_180073202
0x18007324f  mov     rcx, rax; hObject
0x180073252  call    cs:__imp_CloseHandle
0x180073258  mov     ecx, 20h ; ' '; Size
0x18007325d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073262  mov     [rbp+arg_0], rax
0x180073266  mov     rdi, rax
0x180073269  test    rax, rax
0x18007326c  jz      loc_1800733B8
0x180073272  mov     rax, [rsi+10h]
0x180073276  mov     [rdi+8], rax
0x18007327a  mov     [rdi], r14d
0x18007327d  mov     [rdi+10h], r15d
0x180073281  mov     [rdi+18h], r14
0x180073285  test    rdi, rdi
0x180073288  jz      loc_1800733B8
0x18007328e  mov     rcx, rdi; this
0x180073291  call    ?Init@CTitleMap@@AEAAHXZ; CTitleMap::Init(void)
0x180073296  mov     r15d, [rdi+10h]
0x18007329a  cmp     r15d, r13d
0x18007329d  jz      short loc_1800732A7
0x18007329f  mov     ebx, r12d
0x1800732a2  jmp     loc_18007339C
0x1800732a7  mov     r12d, r14d
0x1800732aa  test    r15d, r15d
0x1800732ad  jle     loc_180073399
0x1800732b3  mov     edx, r12d; unsigned int
0x1800732b6  mov     rcx, rdi; this
0x1800732b9  call    ?GetAt@CTitleMap@@QEAAPEAVCTitleMapEntry@@K@Z; CTitleMap::GetAt(ulong)
0x1800732be  mov     rcx, rax; this
0x1800732c1  mov     rbx, rax
0x1800732c4  call    ?GetShortName@CTitleMapEntry@@QEAAPEBDXZ; CTitleMapEntry::GetShortName(void)
0x1800732c9  lea     rdx, [rbp+FileTime1]
0x1800732cd  mov     [rbp+lpString1], rax
0x1800732d1  mov     rcx, rbx; this
0x1800732d4  call    ?GetFileTime@CTitleMapEntry@@QEAA?AU_FILETIME@@XZ; CTitleMapEntry::GetFileTime(void)
0x1800732d9  mov     rcx, rbx; this
0x1800732dc  call    ?GetLanguage@CTitleMapEntry@@QEAAKXZ; CTitleMapEntry::GetLanguage(void)
0x1800732e1  mov     dword ptr [rbp+arg_0], eax
0x1800732e4  mov     eax, [rbx]
0x1800732e6  mov     [rbp+arg_10], eax
0x1800732e9  cmp     r14d, r13d
0x1800732ec  jge     loc_180073392
0x1800732f2  mov     rcx, [rsi+140h]; this
0x1800732f9  mov     edx, r14d; unsigned int
0x1800732fc  call    ?GetAt@CTitleMap@@QEAAPEAVCTitleMapEntry@@K@Z; CTitleMap::GetAt(ulong)
0x180073301  mov     rbx, rax
0x180073304  test    rax, rax
0x180073307  jz      short loc_180073365
0x180073309  mov     rcx, rax; this
0x18007330c  call    ?GetShortName@CTitleMapEntry@@QEAAPEBDXZ; CTitleMapEntry::GetShortName(void)
0x180073311  lea     rdx, [rbp+FileTime2]
0x180073315  mov     [rbp+lpString2], rax
0x180073319  mov     rcx, rbx; this
0x18007331c  call    ?GetFileTime@CTitleMapEntry@@QEAA?AU_FILETIME@@XZ; CTitleMapEntry::GetFileTime(void)
0x180073321  mov     rcx, rbx; this
0x180073324  call    ?GetLanguage@CTitleMapEntry@@QEAAKXZ; CTitleMapEntry::GetLanguage(void)
0x180073329  mov     [rbp+arg_8], eax
0x18007332c  mov     rax, [rbp+lpString1]
0x180073330  test    rax, rax
0x180073333  jz      short loc_180073365
0x180073335  mov     rdx, [rbp+lpString2]; lpString2
0x180073339  mov     rcx, rax; lpString1
0x18007333c  call    cs:__imp_lstrcmpiA
0x180073342  test    eax, eax
0x180073344  jnz     short loc_180073365
0x180073346  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18007334a  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18007334e  call    cs:__imp_CompareFileTime
0x180073354  test    eax, eax
0x180073356  jnz     short loc_180073365
0x180073358  mov     eax, dword ptr [rbp+arg_0]
0x18007335b  cmp     eax, [rbp+arg_8]
0x18007335e  jnz     short loc_180073365
0x180073360  cmp     dword ptr [rbx], 0
0x180073363  jz      short loc_18007336D
0x180073365  inc     r14d
0x180073368  jmp     loc_1800732E9
0x18007336d  mov     eax, [rbp+arg_10]
0x180073370  mov     rcx, rbx; this
0x180073373  mov     rdx, [rbp+lpString1]; char *
0x180073377  mov     [rbx], eax
0x180073379  call    ?SetShortName@CTitleMapEntry@@QEAAPEBDPEBD@Z; CTitleMapEntry::SetShortName(char const *)
0x18007337e  xor     r14d, r14d
0x180073381  inc     r12d
0x180073384  mov     ebx, r14d
0x180073387  cmp     r12d, r15d
0x18007338a  jl      loc_1800732B3
0x180073390  jmp     short loc_18007339C
0x180073392  mov     ebx, 1
0x180073397  jmp     short loc_18007339C
0x180073399  mov     ebx, r14d
0x18007339c  mov     rcx, rdi; this
0x18007339f  call    ??_GCTitleMap@@QEAAPEAXI@Z; CTitleMap::`scalar deleting destructor'(uint)
0x1800733a4  test    ebx, ebx
0x1800733a6  jnz     short loc_1800733B4
0x1800733a8  mov     rcx, [rsi+140h]; this
0x1800733af  call    ?Sort@CTitleMap@@QEAAXP6AHPEBX0@Z@Z; CTitleMap::Sort(int (*)(void const *,void const *))
0x1800733b4  mov     eax, ebx
0x1800733b6  jmp     short loc_1800733D3
0x1800733b8  mov     rcx, [rsi+140h]; this
0x1800733bf  test    rcx, rcx
0x1800733c2  jz      short loc_1800733C9
0x1800733c4  call    ??_GCTitleMap@@QEAAPEAXI@Z; CTitleMap::`scalar deleting destructor'(uint)
0x1800733c9  mov     [rsi+140h], r14
0x1800733d0  mov     eax, r12d
0x1800733d3  add     rsp, 78h
0x1800733d7  pop     r15
0x1800733d9  pop     r14
0x1800733db  pop     r13
0x1800733dd  pop     r12
0x1800733df  pop     rdi
0x1800733e0  pop     rsi
0x1800733e1  pop     rbx
0x1800733e2  pop     rbp
0x1800733e3  retn
```
