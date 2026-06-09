# CVsActivityLogFile::FOpenFile(bool)

- ea: `0x140064640`
- end: `0x14006495b`
- name: `?FOpenFile@CVsActivityLogFile@@QEAA_N_N@Z`
- size: `795`
- prototype: `bool __fastcall(CVsActivityLogFile *__hidden this, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140064d80`
- `0x140065360`

## callees

- `0x140001020`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x14001c380`
- `0x14001e7a0`
- `0x140033290`
- `0x140064370`
- `0x140064500`
- `0x140064640`
- `0x140064960`
- `0x140064a80`
- `0x140064b20`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1400646c0`
- `KERNEL32!SetFilePointer` at `0x1400646c0`
- `KERNEL32!DeleteFileW` at `0x1400646e9`
- `KERNEL32!DeleteFileW` at `0x140064788`
- `KERNEL32!DeleteFileW` at `0x1400646e9`
- `KERNEL32!DeleteFileW` at `0x140064788`
- `KERNEL32!CreateFileW` at `0x14006469a`
- `KERNEL32!CreateFileW` at `0x140064733`
- `KERNEL32!CreateFileW` at `0x140064816`
- `KERNEL32!CreateFileW` at `0x14006469a`
- `KERNEL32!CreateFileW` at `0x140064733`
- `KERNEL32!CreateFileW` at `0x140064816`

## string_xrefs

- `0x1400647be`: `*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
bool __fastcall CVsActivityLogFile::FOpenFile(CVsActivityLogFile *this, char a2)
{
  const WCHAR *v3; // rcx
  HANDLE FileW; // rax
  LONG v5; // edx
  const unsigned __int16 **LogFileFolder; // rax
  bool v8; // di
  HANDLE NewFileWithSamePrefix; // rsi
  LONG *v10; // rdx
  _QWORD *v11; // rdx
  volatile signed __int32 *v12; // r14
  LPCWSTR v13; // rdx
  LONG *v14; // [rsp+40h] [rbp-40h] BYREF
  LONG **p_lpFileName; // [rsp+48h] [rbp-38h]
  LONG **v16; // [rsp+50h] [rbp-30h]
  LONG DistanceToMoveHigh[2]; // [rsp+58h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-20h] BYREF
  LONG *v19; // [rsp+68h] [rbp-18h] BYREF

  if ( a2 && (v3 = (const WCHAR *)*((_QWORD *)this + 2), *((_DWORD *)v3 - 4)) )
  {
    FileW = CreateFileW(v3, 0x40000000u, 1u, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 4) = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      v5 = *((_DWORD *)this + 6);
      if ( v5 != -1 )
      {
        DistanceToMoveHigh[0] = 0;
        SetFilePointer(FileW, v5, DistanceToMoveHigh, 0);
      }
    }
    return *((_QWORD *)this + 4) != -1;
  }
  else
  {
    lpFileName = 0;
    CVsActivityLogFile::GetDefaultLogFilePath(this, &lpFileName);
    DeleteFileW(lpFileName);
    LogFileFolder = (const unsigned __int16 **)CVsActivityLogFile::GetLogFileFolder(this);
    if ( (unsigned int)util_EnsureDirectoryW(*LogFileFolder) )
    {
      NewFileWithSamePrefix = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 1u, 0x80u, 0);
      if ( NewFileWithSamePrefix != (HANDLE)-1LL )
        goto LABEL_18;
      v19 = DistanceToMoveHigh;
      v14 = DistanceToMoveHigh;
      *(_QWORD *)DistanceToMoveHigh = ATL::CSimpleStringT<unsigned short,0>::CloneData(lpFileName - 12) + 24;
      NewFileWithSamePrefix = (HANDLE)CVsActivityLogFile::CreateNewFileWithSamePrefix(this, DistanceToMoveHigh);
      if ( NewFileWithSamePrefix != (HANDLE)-1LL )
        goto LABEL_18;
      DeleteFileW(lpFileName);
      *(_QWORD *)DistanceToMoveHigh = 0;
      v14 = DistanceToMoveHigh;
      *(_QWORD *)DistanceToMoveHigh = ATL::CSimpleStringT<unsigned short,0>::CloneData(lpFileName - 12) + 24;
      ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveExtension(DistanceToMoveHigh);
      v19 = 0;
      ATL::operator+(&v19, DistanceToMoveHigh, L"*.xml");
      v16 = &v14;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v14,
        v19);
      CVsActivityLogFile::DeleteFiles(this, &v14);
      NewFileWithSamePrefix = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 1u, 0x80u, 0);
      if ( NewFileWithSamePrefix == (HANDLE)-1LL )
      {
        v16 = &v14;
        p_lpFileName = &v14;
        v14 = (LONG *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(lpFileName - 12) + 24);
        NewFileWithSamePrefix = (HANDLE)CVsActivityLogFile::CreateNewFileWithSamePrefix(this, &v14);
      }
      v10 = v19 - 6;
      if ( _InterlockedExchangeAdd(v19 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
      }
      p_lpFileName = (LONG **)DistanceToMoveHigh;
      v11 = (_QWORD *)(*(_QWORD *)DistanceToMoveHigh - 24LL);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)DistanceToMoveHigh - 24LL + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
      }
      if ( NewFileWithSamePrefix != (HANDLE)-1LL )
      {
LABEL_18:
        v12 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(lpFileName - 12);
        v19 = (LONG *)(v12 + 6);
        ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 16, &v19);
        if ( _InterlockedExchangeAdd(v12 + 4, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12, v12);
        }
      }
      *((_QWORD *)this + 4) = NewFileWithSamePrefix;
      CVsActivityLogFile::FWriteFile(this, &CVsActivityLogFile::ms_szUnicodeBOM);
      v8 = *((_QWORD *)this + 4) != -1;
    }
    else
    {
      v8 = 0;
    }
    p_lpFileName = (LONG **)&lpFileName;
    v13 = lpFileName - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpFileName - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
    }
    return v8;
  }
}

```

## disassembly

```asm
0x140064640  mov     r11, rsp
0x140064643  mov     [r11+10h], rsi
0x140064647  mov     [r11+18h], rdi
0x14006464b  mov     [r11+20h], r14
0x14006464f  push    rbp
0x140064650  mov     rbp, rsp
0x140064653  sub     rsp, 80h
0x14006465a  mov     rax, cs:__security_cookie
0x140064661  xor     rax, rsp
0x140064664  mov     [rbp+var_10], rax
0x140064668  mov     rdi, rcx
0x14006466b  test    dl, dl
0x14006466d  jz      short loc_1400646D3
0x14006466f  mov     rcx, [rcx+10h]; lpFileName
0x140064673  cmp     dword ptr [rcx-10h], 0
0x140064677  jz      short loc_1400646D3
0x140064679  and     qword ptr [r11-58h], 0
0x14006467e  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140064686  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x14006468e  xor     r9d, r9d; lpSecurityAttributes
0x140064691  mov     edx, 40000000h; dwDesiredAccess
0x140064696  lea     r8d, [r9+1]; dwShareMode
0x14006469a  call    cs:__imp_CreateFileW
0x1400646a0  mov     [rdi+20h], rax
0x1400646a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400646a8  jz      short loc_1400646C6
0x1400646aa  mov     edx, [rdi+18h]; lDistanceToMove
0x1400646ad  cmp     edx, 0FFFFFFFFh
0x1400646b0  jz      short loc_1400646C6
0x1400646b2  and     [rbp+DistanceToMoveHigh], 0
0x1400646b6  xor     r9d, r9d; dwMoveMethod
0x1400646b9  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1400646bd  mov     rcx, rax; hFile
0x1400646c0  call    cs:__imp_SetFilePointer
0x1400646c6  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x1400646cb  setnz   al
0x1400646ce  jmp     loc_140064936
0x1400646d3  and     [rbp+lpFileName], 0
0x1400646d8  lea     rdx, [rbp+lpFileName]
0x1400646dc  mov     rcx, rdi
0x1400646df  call    ?GetDefaultLogFilePath@CVsActivityLogFile@@AEAA?AV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@XZ; CVsActivityLogFile::GetDefaultLogFilePath(void)
0x1400646e4  nop
0x1400646e5  mov     rcx, [rbp+lpFileName]; lpFileName
0x1400646e9  call    cs:__imp_DeleteFileW
0x1400646ef  mov     rcx, rdi
0x1400646f2  call    ?GetLogFileFolder@CVsActivityLogFile@@AEAAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CVsActivityLogFile::GetLogFileFolder(void)
0x1400646f7  mov     rcx, [rax]; unsigned __int16 *
0x1400646fa  call    ?util_EnsureDirectoryW@@YAHPEBG@Z; util_EnsureDirectoryW(ushort const *)
0x1400646ff  test    eax, eax
0x140064701  jnz     short loc_14006470B
0x140064703  xor     dil, dil
0x140064706  jmp     loc_140064909
0x14006470b  and     [rsp+80h+var_50], 0
0x140064711  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140064719  mov     r14d, 1
0x14006471f  mov     [rsp+80h+dwCreationDisposition], r14d; dwCreationDisposition
0x140064724  xor     r9d, r9d; lpSecurityAttributes
0x140064727  mov     r8d, r14d; dwShareMode
0x14006472a  mov     edx, 40000000h; dwDesiredAccess
0x14006472f  mov     rcx, [rbp+lpFileName]; lpFileName
0x140064733  call    cs:__imp_CreateFileW
0x140064739  mov     rsi, rax
0x14006473c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140064740  jnz     loc_1400648AA
0x140064746  lea     rax, [rbp+DistanceToMoveHigh]
0x14006474a  mov     [rbp+var_18], rax
0x14006474e  lea     rax, [rbp+DistanceToMoveHigh]
0x140064752  mov     [rbp+var_40], rax
0x140064756  mov     rcx, [rbp+lpFileName]
0x14006475a  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14006475e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140064763  add     rax, 18h
0x140064767  mov     qword ptr [rbp+DistanceToMoveHigh], rax
0x14006476b  lea     rdx, [rbp+DistanceToMoveHigh]
0x14006476f  mov     rcx, rdi
0x140064772  call    ?CreateNewFileWithSamePrefix@CVsActivityLogFile@@AEAAPEAXV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CVsActivityLogFile::CreateNewFileWithSamePrefix(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>)
0x140064777  mov     rsi, rax
0x14006477a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006477e  jnz     loc_1400648AA
0x140064784  mov     rcx, [rbp+lpFileName]; lpFileName
0x140064788  call    cs:__imp_DeleteFileW
0x14006478e  and     qword ptr [rbp+DistanceToMoveHigh], 0
0x140064793  lea     rax, [rbp+DistanceToMoveHigh]
0x140064797  mov     [rbp+var_40], rax
0x14006479b  mov     rcx, [rbp+lpFileName]
0x14006479f  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1400647a3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400647a8  add     rax, 18h
0x1400647ac  mov     qword ptr [rbp+DistanceToMoveHigh], rax
0x1400647b0  lea     rcx, [rbp+DistanceToMoveHigh]
0x1400647b4  call    ?RemoveExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveExtension(void)
0x1400647b9  and     [rbp+var_18], 0
0x1400647be  lea     r8, aXml; "*.xml"
0x1400647c5  lea     rdx, [rbp+DistanceToMoveHigh]
0x1400647c9  lea     rcx, [rbp+var_18]
0x1400647cd  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x1400647d2  nop
0x1400647d3  lea     rax, [rbp+var_40]
0x1400647d7  mov     [rbp+var_30], rax
0x1400647db  mov     rdx, [rbp+var_18]
0x1400647df  lea     rcx, [rbp+var_40]
0x1400647e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400647e8  lea     rdx, [rbp+var_40]
0x1400647ec  mov     rcx, rdi
0x1400647ef  call    ?DeleteFiles@CVsActivityLogFile@@AEAAXV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CVsActivityLogFile::DeleteFiles(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>)
0x1400647f4  and     [rsp+80h+var_50], 0
0x1400647fa  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140064802  mov     [rsp+80h+dwCreationDisposition], r14d; dwCreationDisposition
0x140064807  xor     r9d, r9d; lpSecurityAttributes
0x14006480a  mov     r8d, r14d; dwShareMode
0x14006480d  mov     edx, 40000000h; dwDesiredAccess
0x140064812  mov     rcx, [rbp+lpFileName]; lpFileName
0x140064816  call    cs:__imp_CreateFileW
0x14006481c  mov     rsi, rax
0x14006481f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140064823  jnz     short loc_140064859
0x140064825  lea     rax, [rbp+var_40]
0x140064829  mov     [rbp+var_30], rax
0x14006482d  lea     rax, [rbp+var_40]
0x140064831  mov     [rbp+var_38], rax
0x140064835  mov     rcx, [rbp+lpFileName]
0x140064839  add     rcx, 0FFFFFFFFFFFFFFE8h
0x14006483d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140064842  add     rax, 18h
0x140064846  mov     [rbp+var_40], rax
0x14006484a  lea     rdx, [rbp+var_40]
0x14006484e  mov     rcx, rdi
0x140064851  call    ?CreateNewFileWithSamePrefix@CVsActivityLogFile@@AEAAPEAXV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@@Z; CVsActivityLogFile::CreateNewFileWithSamePrefix(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>)
0x140064856  mov     rsi, rax
0x140064859  mov     rdx, [rbp+var_18]
0x14006485d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140064861  or      eax, 0FFFFFFFFh
0x140064864  lock xadd [rdx+10h], eax
0x140064869  sub     eax, 1
0x14006486c  jg      short loc_14006487B
0x14006486e  lfence
0x140064871  mov     rcx, [rdx]
0x140064874  mov     rax, [rcx]
0x140064877  call    qword ptr [rax+8]
0x14006487a  nop
0x14006487b  lea     rax, [rbp+DistanceToMoveHigh]
0x14006487f  mov     [rbp+var_38], rax
0x140064883  mov     rdx, qword ptr [rbp+DistanceToMoveHigh]
0x140064887  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14006488b  or      eax, 0FFFFFFFFh
0x14006488e  lock xadd [rdx+10h], eax
0x140064893  sub     eax, 1
0x140064896  jg      short loc_1400648A4
0x140064898  lfence
0x14006489b  mov     rcx, [rdx]
0x14006489e  mov     rax, [rcx]
0x1400648a1  call    qword ptr [rax+8]
0x1400648a4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400648a8  jz      short loc_1400648ED
0x1400648aa  mov     rcx, [rbp+lpFileName]
0x1400648ae  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1400648b2  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400648b7  mov     r14, rax
0x1400648ba  add     rax, 18h
0x1400648be  mov     [rbp+var_18], rax
0x1400648c2  lea     rcx, [rdi+10h]
0x1400648c6  lea     rdx, [rbp+var_18]
0x1400648ca  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400648cf  nop
0x1400648d0  or      eax, 0FFFFFFFFh
0x1400648d3  lock xadd [r14+10h], eax
0x1400648d9  sub     eax, 1
0x1400648dc  jg      short loc_1400648ED
0x1400648de  lfence
0x1400648e1  mov     rcx, [r14]
0x1400648e4  mov     rax, [rcx]
0x1400648e7  mov     rdx, r14
0x1400648ea  call    qword ptr [rax+8]
0x1400648ed  mov     [rdi+20h], rsi
0x1400648f1  lea     rdx, ?ms_szUnicodeBOM@CVsActivityLogFile@@0QBGB; unsigned __int16 *
0x1400648f8  mov     rcx, rdi; this
0x1400648fb  call    ?FWriteFile@CVsActivityLogFile@@QEAA_NPEBG@Z; CVsActivityLogFile::FWriteFile(ushort const *)
0x140064900  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x140064905  setnz   dil
0x140064909  lea     rax, [rbp+lpFileName]
0x14006490d  mov     [rbp+var_38], rax
0x140064911  mov     rdx, [rbp+lpFileName]
0x140064915  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140064919  or      ecx, 0FFFFFFFFh
0x14006491c  lock xadd [rdx+10h], ecx
0x140064921  sub     ecx, 1
0x140064924  jg      short loc_140064933
0x140064926  lfence
0x140064929  mov     rcx, [rdx]
0x14006492c  mov     r8, [rcx]
0x14006492f  call    qword ptr [r8+8]
0x140064933  mov     al, dil
0x140064936  mov     rcx, [rbp+var_10]
0x14006493a  xor     rcx, rsp; StackCookie
0x14006493d  call    __security_check_cookie
0x140064942  lea     r11, [rsp+80h+var_s0]
0x14006494a  mov     rsi, [r11+18h]
0x14006494e  mov     rdi, [r11+20h]
0x140064952  mov     r14, [r11+28h]
0x140064956  mov     rsp, r11
0x140064959  pop     rbp
0x14006495a  retn
```
