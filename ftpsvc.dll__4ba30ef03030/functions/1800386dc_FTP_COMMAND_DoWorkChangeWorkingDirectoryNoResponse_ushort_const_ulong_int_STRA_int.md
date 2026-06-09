# FTP_COMMAND::DoWorkChangeWorkingDirectoryNoResponse(ushort const *,ulong,int,STRA *,int *)

- ea: `0x1800386dc`
- end: `0x1800388af`
- name: `?DoWorkChangeWorkingDirectoryNoResponse@FTP_COMMAND@@AEAAJPEBGKHPEAVSTRA@@PEAH@Z`
- size: `467`
- prototype: `__int64 __fastcall(FTP_COMMAND *this, const unsigned __int16 *, __int64, int, struct STRA *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003860c`
- `0x180039e28`

## callees

- `0x18002be4c`
- `0x180033c70`
- `0x1800386dc`
- `0x180049010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800387b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800387e4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800387b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800387e4`
- `iisutil!PuDbgPrintError` at `0x18003885b`
- `iisutil!PuDbgPrintError` at `0x18003885b`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180038870`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180038870`

## string_xrefs

- `0x180038837`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\ftp_command.cxx`
- `0x18003882b`: `FTP_COMMAND::DoWorkChangeWorkingDirectoryNoResponse`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_COMMAND::DoWorkChangeWorkingDirectoryNoResponse(
        FTP_COMMAND *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        struct STRA *a5,
        int *a6)
{
  bool v7; // zf
  __int64 v9; // rcx
  __int64 v10; // rsi
  int SanitizedFullVirtualPath; // edi
  const unsigned __int16 *v12; // rbp
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v7 = *a2 == 126;
  v9 = *((_QWORD *)this + 132);
  v10 = *(_QWORD *)(v9 + 1056);
  v17 = 0;
  if ( !v7 || a2[1] )
  {
    if ( !(_DWORD)a3 )
    {
      a3 = -1;
      do
        ++a3;
      while ( a2[a3] );
    }
  }
  else
  {
    a2 = *(const unsigned __int16 **)(v9 + 5160);
    LODWORD(a3) = *(_DWORD *)(v9 + 5176);
  }
  SanitizedFullVirtualPath = FTP_SESSION::GetSanitizedFullVirtualPath(
                               (FTP_SESSION *)v9,
                               a2,
                               a3,
                               (unsigned __int16 **)this + 78);
  if ( SanitizedFullVirtualPath >= 0 )
  {
    SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v10 + 88LL))(
                                 v10,
                                 *((_QWORD *)this + 82),
                                 0,
                                 0);
    if ( SanitizedFullVirtualPath >= 0 )
    {
      SanitizedFullVirtualPath = STRU::Copy(
                                   (STRU *)(*((_QWORD *)this + 132) + 4816LL),
                                   *((const unsigned __int16 **)this + 82));
      if ( SanitizedFullVirtualPath >= 0 && a4 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v10 + 112LL))(
                v10,
                *((_QWORD *)this + 82),
                &v17);
        if ( v14 >= 0 )
        {
          v15 = FormatFileSizeA(v17, a5);
        }
        else
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\ftp_command.cxx",
              1964,
              "FTP_COMMAND::DoWorkChangeWorkingDirectoryNoResponse",
              v14,
              "Failed to check available bytes at %S.\n",
              *((const wchar_t **)this + 82));
          v15 = STRA::Copy(a5, "?");
        }
        SanitizedFullVirtualPath = v15;
      }
    }
    else
    {
      v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 208LL))(v10);
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 200LL))(v10);
      if ( !*((_DWORD *)this + 274) )
      {
        *((_DWORD *)this + 274) = v13;
        STRU::Copy((FTP_COMMAND *)((char *)this + 1112), v12);
        *((_QWORD *)this + 138) = *((_QWORD *)this + 143);
      }
    }
  }
  *a6 = 1;
  return (unsigned int)SanitizedFullVirtualPath;
}

```

## disassembly

```asm
0x1800386dc  mov     [rsp+arg_8], rbx
0x1800386e1  mov     [rsp+arg_10], rbp
0x1800386e6  push    rsi
0x1800386e7  push    rdi
0x1800386e8  push    r14
0x1800386ea  sub     rsp, 40h
0x1800386ee  xor     r14d, r14d
0x1800386f1  mov     rbx, rcx
0x1800386f4  cmp     word ptr [rdx], 7Eh ; '~'
0x1800386f8  mov     ebp, r9d
0x1800386fb  mov     rcx, [rcx+420h]; this
0x180038702  mov     rsi, [rcx+420h]
0x180038709  mov     [rsp+58h+arg_0], r14
0x18003870e  jnz     short loc_180038727
0x180038710  cmp     [rdx+2], r14w
0x180038715  jnz     short loc_180038727
0x180038717  mov     rdx, [rcx+1428h]; unsigned __int16 *
0x18003871e  mov     r8d, [rcx+1438h]
0x180038725  jmp     short loc_18003873A
0x180038727  test    r8d, r8d
0x18003872a  jnz     short loc_18003873A
0x18003872c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038730  inc     r8; unsigned int
0x180038733  cmp     [rdx+r8*2], r14w
0x180038738  jnz     short loc_180038730
0x18003873a  lea     r9, [rbx+270h]; struct STRU *
0x180038741  call    ?GetSanitizedFullVirtualPath@FTP_SESSION@@QEAAJPEBGKPEAVSTRU@@@Z; FTP_SESSION::GetSanitizedFullVirtualPath(ushort const *,ulong,STRU *)
0x180038746  mov     edi, eax
0x180038748  test    eax, eax
0x18003874a  js      loc_18003888C
0x180038750  mov     rax, [rsi]
0x180038753  xor     r9d, r9d
0x180038756  mov     rdx, [rbx+290h]
0x18003875d  xor     r8d, r8d
0x180038760  mov     rcx, rsi
0x180038763  mov     rax, [rax+58h]
0x180038767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003876c  mov     edi, eax
0x18003876e  test    eax, eax
0x180038770  jns     short loc_1800387CF
0x180038772  mov     rax, [rsi]
0x180038775  mov     rcx, rsi
0x180038778  mov     rax, [rax+0D0h]
0x18003877f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038784  mov     rdx, [rsi]
0x180038787  mov     rbp, rax
0x18003878a  mov     rcx, rsi
0x18003878d  mov     rax, [rdx+0C8h]
0x180038794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038799  cmp     [rbx+448h], r14d
0x1800387a0  jnz     loc_18003888C
0x1800387a6  lea     rcx, [rbx+458h]
0x1800387ad  mov     [rbx+448h], eax
0x1800387b3  mov     rdx, rbp
0x1800387b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800387bc  mov     rax, [rbx+478h]
0x1800387c3  mov     [rbx+450h], rax
0x1800387ca  jmp     loc_18003888C
0x1800387cf  mov     rcx, [rbx+420h]
0x1800387d6  mov     rdx, [rbx+290h]
0x1800387dd  add     rcx, 12D0h
0x1800387e4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800387ea  mov     edi, eax
0x1800387ec  test    eax, eax
0x1800387ee  js      loc_18003888C
0x1800387f4  test    ebp, ebp
0x1800387f6  jz      loc_18003888C
0x1800387fc  mov     rax, [rsi]
0x1800387ff  lea     r8, [rsp+58h+arg_0]
0x180038804  mov     rdx, [rbx+290h]
0x18003880b  mov     rcx, rsi
0x18003880e  mov     rax, [rax+70h]
0x180038812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038817  test    eax, eax
0x180038819  jns     short loc_180038878
0x18003881b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180038822  jz      short loc_180038861
0x180038824  mov     rcx, [rbx+290h]
0x18003882b  lea     r9, aFtpCommandDowo; "FTP_COMMAND::DoWorkChangeWorkingDirecto"...
0x180038832  mov     [rsp+58h+var_28], rcx
0x180038837  lea     rdx, aInetsrvIisIisr_8; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18003883e  lea     rcx, aFailedToCheckA; "Failed to check available bytes at %S."...
0x180038845  mov     r8d, 7ACh
0x18003884b  mov     [rsp+58h+var_30], rcx
0x180038850  mov     rcx, cs:g_pDebug
0x180038857  mov     [rsp+58h+var_38], eax
0x18003885b  call    cs:__imp_PuDbgPrintError
0x180038861  mov     rcx, [rsp+58h+arg_20]
0x180038869  lea     rdx, asc_18005482C; "?"
0x180038870  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180038876  jmp     short loc_18003888A
0x180038878  mov     rdx, [rsp+58h+arg_20]; struct STRA *
0x180038880  mov     rcx, [rsp+58h+arg_0]; unsigned __int64
0x180038885  call    ?FormatFileSizeA@@YAJ_KPEAVSTRA@@@Z; FormatFileSizeA(unsigned __int64,STRA *)
0x18003888a  mov     edi, eax
0x18003888c  mov     rax, [rsp+58h+arg_28]
0x180038894  mov     rbx, [rsp+58h+arg_8]
0x180038899  mov     rbp, [rsp+58h+arg_10]
0x18003889e  mov     dword ptr [rax], 1
0x1800388a4  mov     eax, edi
0x1800388a6  add     rsp, 40h
0x1800388aa  pop     r14
0x1800388ac  pop     rdi
0x1800388ad  pop     rsi
0x1800388ae  retn
```
