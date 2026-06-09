# CLogSet::MergeLogInfos(HWND__ *)

- ea: `0x180016084`
- end: `0x1800164cf`
- name: `?MergeLogInfos@CLogSet@@QEAAJPEAUHWND__@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(CLogSet *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008958`

## callees

- `0x180001910`
- `0x180002928`
- `0x180005f64`
- `0x180006f94`
- `0x180015e48`
- `0x180016084`
- `0x1800165b0`
- `0x180017630`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001adf4`
- `0x18001ae60`
- `0x18001af3c`
- `0x18001eef4`
- `0x18001ef94`
- `0x18001f278`
- `0x18001f4ec`
- `0x18001f9cc`
- `0x180020580`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180016345`
- `msvcrt!wcsncpy_s` at `0x180016403`
- `msvcrt!wcsncpy_s` at `0x18001641e`
- `msvcrt!wcsncpy_s` at `0x180016345`
- `msvcrt!wcsncpy_s` at `0x180016403`
- `msvcrt!wcsncpy_s` at `0x18001641e`
- `KERNEL32!lstrcmpiW` at `0x1800162fe`
- `KERNEL32!lstrcmpiW` at `0x1800162fe`
- `KERNEL32!LocalFree` at `0x18001645a`
- `KERNEL32!LocalFree` at `0x18001645a`

## string_xrefs

- `0x180016134`: `SYSTEM\CurrentControlSet\Services\EventLog`
- `0x1800161e0`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogSet::MergeLogInfos(CLogSet *this, HWND hWnd)
{
  unsigned __int16 *v4; // r14
  struct IConsole *v5; // r15
  WCHAR *CurrentFocus; // rsi
  HCURSOR v7; // r8
  __int64 i; // rdx
  __int16 v9; // cx
  int v10; // ebx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  const unsigned __int16 *v14; // r14
  unsigned int v15; // r15d
  HKEY v16; // rbx
  unsigned int v17; // edi
  int v18; // r12d
  __int64 v19; // rdi
  int v20; // r14d
  __int16 v21; // ax
  int v22; // edi
  void *v23; // rax
  CLogInfo *v24; // rax
  wchar_t *v25; // rdi
  const unsigned __int16 *LogDisplayName; // rax
  unsigned __int16 *v27; // r14
  HKEY v28; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v29; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v31; // [rsp+48h] [rbp-B8h]
  void *v32; // [rsp+50h] [rbp-B0h]
  _QWORD v33[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-90h]
  WCHAR String2[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Source[264]; // [rsp+290h] [rbp+190h] BYREF

  v4 = (unsigned __int16 *)*((_QWORD *)this + 4);
  v5 = (struct IConsole *)*((_QWORD *)v4 + 144);
  CurrentFocus = (WCHAR *)CComponentData::GetCurrentFocus((CComponentData *)v4);
  for ( i = *((_QWORD *)this + 17); i; i = *(_QWORD *)(i + 8) )
  {
    if ( (*(_BYTE *)(i + 24) & 1) != 0 )
      v9 = *(_WORD *)(i + 24) | 0x500;
    else
      v9 = *(_WORD *)(i + 24) | 0x700;
    *(_WORD *)(i + 24) = v9;
  }
  phkResult = 0;
  v28 = 0;
  if ( CurrentFocus )
  {
    v10 = CSafeReg::Connect(&phkResult, CurrentFocus, v7);
    if ( v10 < 0
      || (v10 = CSafeReg::Open((CSafeReg *)&v28, phkResult, L"SYSTEM\\CurrentControlSet\\Services\\EventLog", 8u),
          v10 < 0) )
    {
      ComposeErrorMessgeFromHRESULT(v33, (unsigned int)v10);
      v11 = v33;
      if ( hWnd )
      {
        if ( v34 >= 8 )
          v11 = (_QWORD *)v33[0];
        MsgBox(hWnd, 0x12Au, 0x10u, CurrentFocus, v11);
      }
      else
      {
        if ( v34 >= 8 )
          v11 = (_QWORD *)v33[0];
        ConsoleMsgBox(v5, 0x12Au, 0x10u, CurrentFocus, v11);
      }
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(v33, v12, 0);
      goto LABEL_18;
    }
  }
  else
  {
    v10 = CSafeReg::Open((CSafeReg *)&v28, HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\EventLog", 8u);
    if ( v10 < 0 )
    {
LABEL_18:
      CSafeReg::Close((CSafeReg *)&v28);
      CSafeReg::Close((CSafeReg *)&phkResult);
      return (unsigned int)v10;
    }
  }
  v14 = v4 + 306;
  v31 = v14;
  v15 = 0;
  v16 = v28;
  while ( 1 )
  {
    v17 = CSafeReg::Enum((CSafeReg *)&v28, v15, String2, 0x105u);
    if ( v17 )
      break;
    v29 = 0;
    if ( (int)CSafeReg::Open((CSafeReg *)&v29, v16, String2, 1u) < 0
      || (int)CSafeReg::QueryPath(&v29, L"File", (BYTE *)Source, 0x105u, CurrentFocus == 0) >= 0
      && CurrentFocus
      && (int)ExpandSystemRootAndConvertToUnc(Source, 0x105u, CurrentFocus, v14) < 0 )
    {
      Source[0] = 0;
    }
    CSafeReg::Close((CSafeReg *)&v29);
    v18 = CSafeReg::Open((CSafeReg *)&v29, v16, String2, 2u);
    CSafeReg::Close((CSafeReg *)&v29);
    v19 = *((_QWORD *)this + 17);
    if ( !v19 )
      goto LABEL_40;
    v20 = 0;
    do
    {
      if ( (*(_BYTE *)(v19 + 24) & 1) == 0 && !lstrcmpiW((LPCWSTR)(v19 + 554), String2) )
      {
        v20 = 1;
        v21 = (*(_BYTE *)(v19 + 24) & 8) != 0 ? *(_WORD *)(v19 + 24) & 0xFCFF | 0x100 : *(_WORD *)(v19 + 24) & 0xFCFF;
        *(_WORD *)(v19 + 24) = v21;
        wcsncpy_s((wchar_t *)(v19 + 1076), 0x105u, Source, 0x104u);
        CLogInfo::SetLogServerName((CLogInfo *)v19, CurrentFocus);
        if ( v18 >= 0 )
          *(_WORD *)(v19 + 24) &= ~0x400u;
      }
      v19 = *(_QWORD *)(v19 + 8);
    }
    while ( v19 );
    if ( !v20 && (*((_BYTE *)this + 24) & 0x20) == 0 )
    {
      v14 = v31;
LABEL_40:
      v22 = DetermineLogType(String2);
      v23 = operator new(0x1318u);
      v32 = v23;
      if ( v23 )
      {
        v24 = (CLogInfo *)CLogInfo::CLogInfo(
                            (__int64)v23,
                            *((_QWORD *)this + 4),
                            (__int64)this,
                            v22,
                            0,
                            CurrentFocus == 0);
        v25 = (wchar_t *)v24;
        if ( v24 )
        {
          if ( CurrentFocus )
            CLogInfo::SetLogServerName(v24, CurrentFocus);
          wcsncpy_s(v25 + 538, 0x105u, Source, 0x104u);
          wcsncpy_s(v25 + 277, 0x105u, String2, 0x104u);
          if ( v18 < 0 )
            v25[12] |= 0x400u;
          LogDisplayName = GetLogDisplayName(v16, CurrentFocus, v14, String2);
          v27 = (unsigned __int16 *)LogDisplayName;
          if ( LogDisplayName )
          {
            CLogInfo::SetDisplayName((CLogInfo *)v25, LogDisplayName);
            LocalFree(v27);
          }
          else
          {
            CLogInfo::SetDisplayName((CLogInfo *)v25, String2);
          }
          CLogSet::AddLogInfoToList(this, (struct CLogInfo *)v25);
        }
      }
    }
    CSafeReg::Close((CSafeReg *)&v29);
    ++v15;
    v14 = v31;
  }
  CSafeReg::Close((CSafeReg *)&v28);
  CSafeReg::Close((CSafeReg *)&phkResult);
  return v17;
}

```

## disassembly

```asm
0x180016084  mov     [rsp-8+arg_10], rbx
0x180016089  push    rbp
0x18001608a  push    rsi
0x18001608b  push    rdi
0x18001608c  push    r12
0x18001608e  push    r13
0x180016090  push    r14
0x180016092  push    r15
0x180016094  lea     rbp, [rsp-3B0h]
0x18001609c  sub     rsp, 4B0h
0x1800160a3  mov     rax, cs:__security_cookie
0x1800160aa  xor     rax, rsp
0x1800160ad  mov     [rbp+3E0h+var_40], rax
0x1800160b4  mov     rdi, rdx
0x1800160b7  mov     r13, rcx
0x1800160ba  mov     r14, [rcx+20h]
0x1800160be  mov     r15, [r14+480h]
0x1800160c5  mov     rcx, r14; this
0x1800160c8  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x1800160cd  mov     rsi, rax
0x1800160d0  mov     rdx, [r13+88h]
0x1800160d7  mov     eax, 400h
0x1800160dc  jmp     short loc_180016103
0x1800160de  mov     ecx, 500h
0x1800160e3  or      cx, [rdx+18h]
0x1800160e7  test    cl, 1
0x1800160ea  jz      short loc_1800160F1
0x1800160ec  or      cx, ax
0x1800160ef  jmp     short loc_1800160FB
0x1800160f1  or      cx, 200h
0x1800160f6  mov     eax, 400h
0x1800160fb  mov     [rdx+18h], cx
0x1800160ff  mov     rdx, [rdx+8]
0x180016103  test    rdx, rdx
0x180016106  jnz     short loc_1800160DE
0x180016108  mov     [rsp+4E0h+phkResult], rdx
0x18001610d  mov     [rsp+4E0h+var_4B0], rdx
0x180016112  test    rsi, rsi
0x180016115  jz      loc_1800161DA
0x18001611b  mov     rdx, rsi; lpMachineName
0x18001611e  lea     rcx, [rsp+4E0h+phkResult]; phkResult
0x180016123  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180016128  mov     ebx, eax
0x18001612a  test    eax, eax
0x18001612c  js      short loc_180016154
0x18001612e  mov     r9d, 8; unsigned int
0x180016134  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18001613b  mov     rdx, [rsp+4E0h+phkResult]; HKEY
0x180016140  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180016145  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18001614a  mov     ebx, eax
0x18001614c  test    eax, eax
0x18001614e  jns     loc_1800161FE
0x180016154  mov     edx, ebx
0x180016156  lea     rcx, [rsp+4E0h+var_488]
0x18001615b  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x180016160  nop
0x180016161  lea     rax, [rsp+4E0h+var_488]
0x180016166  mov     r9, rsi
0x180016169  mov     edx, 12Ah; unsigned int
0x18001616e  mov     r8d, 10h; unsigned int
0x180016174  test    rdi, rdi
0x180016177  jz      short loc_180016194
0x180016179  cmp     [rsp+4E0h+var_470], 8
0x18001617f  cmovnb  rax, [rsp+4E0h+var_488]
0x180016185  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x18001618a  mov     rcx, rdi; hWnd
0x18001618d  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x180016192  jmp     short loc_1800161AE
0x180016194  cmp     [rsp+4E0h+var_470], 8
0x18001619a  cmovnb  rax, [rsp+4E0h+var_488]
0x1800161a0  mov     qword ptr [rsp+4E0h+var_4C0], rax
0x1800161a5  mov     rcx, r15; struct IConsole *
0x1800161a8  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x1800161ad  nop
0x1800161ae  xor     r8d, r8d
0x1800161b1  mov     dl, 1
0x1800161b3  lea     rcx, [rsp+4E0h+var_488]
0x1800161b8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800161bd  nop
0x1800161be  lea     rcx, [rsp+4E0h+var_4B0]; this
0x1800161c3  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800161c8  nop
0x1800161c9  lea     rcx, [rsp+4E0h+phkResult]; this
0x1800161ce  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800161d3  mov     eax, ebx
0x1800161d5  jmp     loc_1800164A5
0x1800161da  mov     r9d, 8; unsigned int
0x1800161e0  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800161e7  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800161ee  lea     rcx, [rsp+4E0h+var_4B0]; this
0x1800161f3  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800161f8  mov     ebx, eax
0x1800161fa  test    eax, eax
0x1800161fc  js      short loc_1800161BE
0x1800161fe  add     r14, 264h
0x180016205  mov     [rsp+4E0h+var_498], r14
0x18001620a  xor     r15d, r15d
0x18001620d  mov     rbx, [rsp+4E0h+var_4B0]
0x180016212  mov     r9d, 105h; unsigned int
0x180016218  lea     r8, [rbp+3E0h+String2]; unsigned __int16 *
0x18001621c  mov     edx, r15d; unsigned int
0x18001621f  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180016224  call    ?Enum@CSafeReg@@QEBAJKPEAGK@Z; CSafeReg::Enum(ulong,ushort *,ulong)
0x180016229  mov     edi, eax
0x18001622b  test    eax, eax
0x18001622d  jnz     loc_18001648E
0x180016233  mov     [rsp+4E0h+var_4A8], 0
0x18001623c  lea     r9d, [rax+1]; unsigned int
0x180016240  lea     r8, [rbp+3E0h+String2]; unsigned __int16 *
0x180016244  mov     rdx, rbx; HKEY
0x180016247  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001624c  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180016251  test    eax, eax
0x180016253  js      short loc_1800162A3
0x180016255  xor     eax, eax
0x180016257  test    rsi, rsi
0x18001625a  setz    al
0x18001625d  mov     [rsp+4E0h+var_4C0], eax; int
0x180016261  mov     r9d, 105h; unsigned int
0x180016267  lea     r8, [rbp+3E0h+Source]; unsigned __int16 *
0x18001626e  lea     rdx, aFile; "File"
0x180016275  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001627a  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18001627f  test    eax, eax
0x180016281  js      short loc_1800162AC
0x180016283  test    rsi, rsi
0x180016286  jz      short loc_1800162AC
0x180016288  mov     r9, r14; Src
0x18001628b  mov     r8, rsi; Source
0x18001628e  mov     edx, 105h; SizeInWords
0x180016293  lea     rcx, [rbp+3E0h+Source]; Destination
0x18001629a  call    ?ExpandSystemRootAndConvertToUnc@@YAJPEAGKPEBG1@Z; ExpandSystemRootAndConvertToUnc(ushort *,ulong,ushort const *,ushort const *)
0x18001629f  test    eax, eax
0x1800162a1  jns     short loc_1800162AC
0x1800162a3  xor     eax, eax
0x1800162a5  mov     [rbp+3E0h+Source], ax
0x1800162ac  lea     rcx, [rsp+4E0h+var_4A8]; this
0x1800162b1  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800162b6  mov     r9d, 2; unsigned int
0x1800162bc  lea     r8, [rbp+3E0h+String2]; unsigned __int16 *
0x1800162c0  mov     rdx, rbx; HKEY
0x1800162c3  lea     rcx, [rsp+4E0h+var_4A8]; this
0x1800162c8  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800162cd  mov     r12d, eax
0x1800162d0  lea     rcx, [rsp+4E0h+var_4A8]; this
0x1800162d5  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800162da  mov     rdi, [r13+88h]
0x1800162e1  test    rdi, rdi
0x1800162e4  jz      loc_180016386
0x1800162ea  xor     r14d, r14d
0x1800162ed  test    byte ptr [rdi+18h], 1
0x1800162f1  jnz     short loc_180016364
0x1800162f3  lea     rcx, [rdi+22Ah]; lpString1
0x1800162fa  lea     rdx, [rbp+3E0h+String2]; lpString2
0x1800162fe  call    cs:__imp_lstrcmpiW
0x180016304  test    eax, eax
0x180016306  jnz     short loc_180016364
0x180016308  mov     eax, 0FDFFh
0x18001630d  mov     r14d, 1
0x180016313  and     ax, [rdi+18h]
0x180016317  test    al, 8
0x180016319  jz      short loc_180016321
0x18001631b  or      ax, 100h
0x18001631f  jmp     short loc_180016329
0x180016321  mov     ecx, 0FEFFh
0x180016326  and     ax, cx
0x180016329  mov     [rdi+18h], ax
0x18001632d  lea     rcx, [rdi+434h]; Destination
0x180016334  mov     r9d, 104h; MaxCount
0x18001633a  lea     r8, [rbp+3E0h+Source]; Source
0x180016341  lea     edx, [r9+1]; SizeInWords
0x180016345  call    cs:__imp_wcsncpy_s
0x18001634b  mov     rdx, rsi; unsigned __int16 *
0x18001634e  mov     rcx, rdi; this
0x180016351  call    ?SetLogServerName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetLogServerName(ushort const *)
0x180016356  test    r12d, r12d
0x180016359  js      short loc_180016364
0x18001635b  mov     eax, 0FBFFh
0x180016360  and     [rdi+18h], ax
0x180016364  mov     rdi, [rdi+8]
0x180016368  test    rdi, rdi
0x18001636b  jnz     short loc_1800162ED
0x18001636d  test    r14d, r14d
0x180016370  jnz     loc_180016477
0x180016376  test    byte ptr [r13+18h], 20h
0x18001637b  jnz     loc_180016477
0x180016381  mov     r14, [rsp+4E0h+var_498]
0x180016386  lea     rcx, [rbp+3E0h+String2]
0x18001638a  call    ?DetermineLogType@@YA?AW4EVENTLOGTYPE@@PEBG@Z; DetermineLogType(ushort const *)
0x18001638f  mov     edi, eax
0x180016391  mov     ecx, 1318h; Size
0x180016396  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001639b  mov     [rsp+4E0h+var_490], rax
0x1800163a0  test    rax, rax
0x1800163a3  jz      loc_180016477
0x1800163a9  xor     ecx, ecx
0x1800163ab  test    rsi, rsi
0x1800163ae  setz    cl
0x1800163b1  mov     [rsp+4E0h+var_4B8], ecx
0x1800163b5  mov     [rsp+4E0h+var_4C0], 0
0x1800163bd  mov     r9d, edi
0x1800163c0  mov     r8, r13
0x1800163c3  mov     rdx, [r13+20h]
0x1800163c7  mov     rcx, rax
0x1800163ca  call    ??0CLogInfo@@QEAA@PEAVCComponentData@@PEAVCLogSet@@W4EVENTLOGTYPE@@HH@Z; CLogInfo::CLogInfo(CComponentData *,CLogSet *,EVENTLOGTYPE,int,int)
0x1800163cf  mov     rdi, rax
0x1800163d2  test    rax, rax
0x1800163d5  jz      loc_180016477
0x1800163db  test    rsi, rsi
0x1800163de  jz      short loc_1800163EB
0x1800163e0  mov     rdx, rsi; unsigned __int16 *
0x1800163e3  mov     rcx, rax; this
0x1800163e6  call    ?SetLogServerName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetLogServerName(ushort const *)
0x1800163eb  lea     rcx, [rdi+434h]; Destination
0x1800163f2  mov     r9d, 104h; MaxCount
0x1800163f8  lea     r8, [rbp+3E0h+Source]; Source
0x1800163ff  lea     edx, [r9+1]; SizeInWords
0x180016403  call    cs:__imp_wcsncpy_s
0x180016409  lea     rcx, [rdi+22Ah]; Destination
0x180016410  mov     r9d, 104h; MaxCount
0x180016416  lea     r8, [rbp+3E0h+String2]; Source
0x18001641a  lea     edx, [r9+1]; SizeInWords
0x18001641e  call    cs:__imp_wcsncpy_s
0x180016424  test    r12d, r12d
0x180016427  jns     short loc_180016432
0x180016429  mov     eax, 400h
0x18001642e  or      [rdi+18h], ax
0x180016432  lea     r9, [rbp+3E0h+String2]; unsigned __int16 *
0x180016436  mov     r8, r14; Src
0x180016439  mov     rdx, rsi; Source
0x18001643c  mov     rcx, rbx; HKEY
0x18001643f  call    ?GetLogDisplayName@@YAPEAGPEAUHKEY__@@PEBG11@Z; GetLogDisplayName(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180016444  mov     r14, rax
0x180016447  mov     rcx, rdi; this
0x18001644a  test    rax, rax
0x18001644d  jz      short loc_180016462
0x18001644f  mov     rdx, rax; unsigned __int16 *
0x180016452  call    ?SetDisplayName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetDisplayName(ushort const *)
0x180016457  mov     rcx, r14; hMem
0x18001645a  call    cs:__imp_LocalFree
0x180016460  jmp     short loc_18001646B
0x180016462  lea     rdx, [rbp+3E0h+String2]; unsigned __int16 *
0x180016466  call    ?SetDisplayName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetDisplayName(ushort const *)
0x18001646b  mov     rdx, rdi; struct CLogInfo *
0x18001646e  mov     rcx, r13; this
0x180016471  call    ?AddLogInfoToList@CLogSet@@QEAAXPEAVCLogInfo@@@Z; CLogSet::AddLogInfoToList(CLogInfo *)
0x180016476  nop
0x180016477  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001647c  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180016481  inc     r15d
0x180016484  mov     r14, [rsp+4E0h+var_498]
0x180016489  jmp     loc_180016212
0x18001648e  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180016493  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180016498  nop
0x180016499  lea     rcx, [rsp+4E0h+phkResult]; this
0x18001649e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800164a3  mov     eax, edi
0x1800164a5  mov     rcx, [rbp+3E0h+var_40]
0x1800164ac  xor     rcx, rsp; StackCookie
0x1800164af  call    __security_check_cookie
0x1800164b4  mov     rbx, [rsp+4E0h+arg_10]
0x1800164bc  add     rsp, 4B0h
0x1800164c3  pop     r15
0x1800164c5  pop     r14
0x1800164c7  pop     r13
0x1800164c9  pop     r12
0x1800164cb  pop     rdi
0x1800164cc  pop     rsi
0x1800164cd  pop     rbp
0x1800164ce  retn
```
