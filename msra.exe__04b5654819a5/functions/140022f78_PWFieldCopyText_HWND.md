# PWFieldCopyText(HWND__ *)

- ea: `0x140022f78`
- end: `0x1400231cf`
- name: `?PWFieldCopyText@@YAJPEAUHWND__@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(HWND hWndNewOwner)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400206b0`
- `0x140023830`

## callees

- `0x1400020f4`
- `0x140022f78`
- `0x140034ce4`
- `0x14004d010`

## import_xrefs

- `USER32!CloseClipboard` at `0x140023144`
- `USER32!CloseClipboard` at `0x140023144`
- `USER32!SetClipboardData` at `0x140023138`
- `USER32!SetClipboardData` at `0x140023138`
- `USER32!EmptyClipboard` at `0x1400230db`
- `USER32!EmptyClipboard` at `0x1400230db`
- `USER32!OpenClipboard` at `0x1400230c0`
- `USER32!OpenClipboard` at `0x1400230c0`
- `USER32!GetWindowTextW` at `0x140022ffb`
- `USER32!GetWindowTextW` at `0x140022ffb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400231b3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400231b3`
- `ole32!GetHGlobalFromStream` at `0x1400230f1`
- `ole32!GetHGlobalFromStream` at `0x1400230f1`
- `ole32!CreateStreamOnHGlobal` at `0x140022f9b`
- `ole32!CreateStreamOnHGlobal` at `0x140022f9b`

## string_xrefs

- `0x140023011`: `PWFieldCopyText`
- `0x14002310e`: `PWFieldCopyText`
- `0x140023171`: `PWFieldCopyText`

## pseudocode

```c
__int64 __fastcall PWFieldCopyText(HWND hWndNewOwner)
{
  HRESULT v2; // eax
  CEventLogger *v3; // rcx
  unsigned int v4; // ebx
  WCHAR *v5; // rdi
  WCHAR *v6; // rax
  CEventLogger *v7; // rcx
  CEventLogger *v8; // rcx
  unsigned int v9; // r9d
  WCHAR *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  CEventLogger *v13; // rcx
  unsigned __int64 v14; // r8
  signed int v15; // eax
  CEventLogger *v16; // rcx
  HRESULT HGlobalFromStream; // eax
  CEventLogger *v18; // rcx
  LPSTREAM pstm; // [rsp+58h] [rbp+10h] BYREF
  HGLOBAL phglobal; // [rsp+60h] [rbp+18h] BYREF

  phglobal = 0;
  pstm = 0;
  v2 = CreateStreamOnHGlobal(0, 0, &pstm);
  v4 = v2;
  if ( v2 < 0 )
  {
    v5 = 0;
    CEventLogger::LogError(
      v3,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x16B8u,
      L"PWFieldCopyText",
      v2);
    goto LABEL_23;
  }
  v6 = (WCHAR *)operator new[](0x800u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x16BEu,
      L"PWFieldCopyText",
      0x8007000E);
    goto LABEL_23;
  }
  if ( !GetWindowTextW(hWndNewOwner, v6, 1024) )
  {
    v9 = 5824;
LABEL_7:
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      v9,
      L"PWFieldCopyText",
      0);
    v4 = -2147467259;
    goto LABEL_23;
  }
  v10 = v5;
  v11 = 512;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v4 = v11 == 0 ? 0x80070057 : 0;
  if ( v11 )
  {
    v12 = 2 * (512 - v11);
    v13 = (CEventLogger *)-v11;
    v14 = v12 & -(__int64)(v13 != 0);
    if ( v14 > 0xFFFFFFFF )
    {
      v4 = -2147024362;
      CEventLogger::LogError(
        v13,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0x16C2u,
        L"PWFieldCopyText",
        0x80070216);
    }
    else
    {
      v15 = (*(__int64 (__fastcall **)(LPSTREAM, WCHAR *, _QWORD, _QWORD))(*(_QWORD *)pstm + 32LL))(
              pstm,
              v5,
              (unsigned int)(v14 + 2),
              0);
      v4 = v15;
      if ( v15 >= 0 )
      {
        if ( !OpenClipboard(hWndNewOwner) )
        {
          v9 = 5829;
          goto LABEL_7;
        }
        EmptyClipboard();
        HGlobalFromStream = GetHGlobalFromStream(pstm, &phglobal);
        v4 = HGlobalFromStream;
        if ( HGlobalFromStream >= 0 )
          SetClipboardData(0xDu, phglobal);
        else
          CEventLogger::LogError(
            v18,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
            0x16CDu,
            L"PWFieldCopyText",
            HGlobalFromStream);
        CloseClipboard();
      }
      else
      {
        CEventLogger::LogError(
          v16,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
          0x16C4u,
          L"PWFieldCopyText",
          v15);
      }
    }
  }
  else
  {
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x16C1u,
      L"PWFieldCopyText",
      v4);
  }
LABEL_23:
  if ( pstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)pstm + 16LL))(pstm);
    pstm = 0;
  }
  if ( v5 )
    operator delete[](v5);
  return v4;
}

```

## disassembly

```asm
0x140022f78  mov     rax, rsp
0x140022f7b  mov     [rax+8], rbx
0x140022f7f  push    rbp
0x140022f80  push    rsi
0x140022f81  push    rdi
0x140022f82  sub     rsp, 30h
0x140022f86  mov     rsi, rcx
0x140022f89  lea     r8, [rax+10h]; ppstm
0x140022f8d  xor     ebp, ebp
0x140022f8f  xor     ecx, ecx; hGlobal
0x140022f91  xor     edx, edx; fDeleteOnRelease
0x140022f93  mov     [rax+18h], rbp
0x140022f97  mov     [rax+10h], rbp
0x140022f9b  call    cs:__imp_CreateStreamOnHGlobal
0x140022fa2  nop     dword ptr [rax+rax+00h]
0x140022fa7  mov     ebx, eax
0x140022fa9  test    eax, eax
0x140022fab  jns     short loc_140022FBE
0x140022fad  mov     edi, ebp
0x140022faf  mov     [rsp+48h+var_20], eax
0x140022fb3  mov     r9d, 16B8h
0x140022fb9  jmp     loc_140023171
0x140022fbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140022fc5  mov     ecx, 800h; unsigned __int64
0x140022fca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140022fcf  mov     rdi, rax
0x140022fd2  test    rax, rax
0x140022fd5  jnz     short loc_140022FEF
0x140022fd7  mov     ebx, 8007000Eh
0x140022fdc  mov     [rsp+48h+var_20], 8007000Eh
0x140022fe4  mov     r9d, 16BEh
0x140022fea  jmp     loc_140023171
0x140022fef  mov     r8d, 400h; nMaxCount
0x140022ff5  mov     rdx, rdi; lpString
0x140022ff8  mov     rcx, rsi; hWnd
0x140022ffb  call    cs:__imp_GetWindowTextW
0x140023002  nop     dword ptr [rax+rax+00h]
0x140023007  test    eax, eax
0x140023009  jnz     short loc_14002303E
0x14002300b  mov     r9d, 16C0h; unsigned int
0x140023011  lea     rax, aPwfieldcopytex; "PWFieldCopyText"
0x140023018  mov     [rsp+48h+var_20], ebp; unsigned int
0x14002301c  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140023023  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x140023028  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002302f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140023034  mov     ebx, 80004005h
0x140023039  jmp     loc_140023190
0x14002303e  mov     edx, 200h
0x140023043  mov     rax, rdi
0x140023046  mov     ecx, edx
0x140023048  cmp     [rax], bp
0x14002304b  jz      short loc_140023057
0x14002304d  add     rax, 2
0x140023051  sub     rcx, 1; this
0x140023055  jnz     short loc_140023048
0x140023057  mov     rax, rcx
0x14002305a  neg     rax
0x14002305d  sbb     ebx, ebx
0x14002305f  not     ebx
0x140023061  and     ebx, 80070057h
0x140023067  test    rcx, rcx
0x14002306a  jz      loc_140023167
0x140023070  sub     rdx, rcx
0x140023073  mov     eax, 0FFFFFFFFh
0x140023078  add     rdx, rdx
0x14002307b  neg     rcx
0x14002307e  sbb     r8, r8
0x140023081  and     r8, rdx
0x140023084  cmp     r8, rax
0x140023087  ja      loc_140023152
0x14002308d  mov     rcx, [rsp+48h+pstm]
0x140023092  add     r8d, 2
0x140023096  xor     r9d, r9d
0x140023099  mov     rdx, rdi
0x14002309c  mov     rax, [rcx]
0x14002309f  mov     rax, [rax+20h]
0x1400230a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400230a8  mov     ebx, eax
0x1400230aa  test    eax, eax
0x1400230ac  jns     short loc_1400230BD
0x1400230ae  mov     [rsp+48h+var_20], eax
0x1400230b2  mov     r9d, 16C4h
0x1400230b8  jmp     loc_140023171
0x1400230bd  mov     rcx, rsi; hWndNewOwner
0x1400230c0  call    cs:__imp_OpenClipboard
0x1400230c7  nop     dword ptr [rax+rax+00h]
0x1400230cc  test    eax, eax
0x1400230ce  jnz     short loc_1400230DB
0x1400230d0  mov     r9d, 16C5h
0x1400230d6  jmp     loc_140023011
0x1400230db  call    cs:__imp_EmptyClipboard
0x1400230e2  nop     dword ptr [rax+rax+00h]
0x1400230e7  mov     rcx, [rsp+48h+pstm]; pstm
0x1400230ec  lea     rdx, [rsp+48h+phglobal]; phglobal
0x1400230f1  call    cs:__imp_GetHGlobalFromStream
0x1400230f8  nop     dword ptr [rax+rax+00h]
0x1400230fd  mov     ebx, eax
0x1400230ff  test    eax, eax
0x140023101  jns     short loc_14002312E
0x140023103  mov     [rsp+48h+var_20], eax; unsigned int
0x140023107  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14002310e  lea     rax, aPwfieldcopytex; "PWFieldCopyText"
0x140023115  mov     r9d, 16CDh; unsigned int
0x14002311b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140023122  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x140023127  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002312c  jmp     short loc_140023144
0x14002312e  mov     rdx, [rsp+48h+phglobal]; hMem
0x140023133  mov     ecx, 0Dh; uFormat
0x140023138  call    cs:__imp_SetClipboardData
0x14002313f  nop     dword ptr [rax+rax+00h]
0x140023144  call    cs:__imp_CloseClipboard
0x14002314b  nop     dword ptr [rax+rax+00h]
0x140023150  jmp     short loc_140023190
0x140023152  mov     ebx, 80070216h
0x140023157  mov     [rsp+48h+var_20], 80070216h
0x14002315f  mov     r9d, 16C2h
0x140023165  jmp     short loc_140023171
0x140023167  mov     [rsp+48h+var_20], ebx; unsigned int
0x14002316b  mov     r9d, 16C1h; unsigned int
0x140023171  lea     rax, aPwfieldcopytex; "PWFieldCopyText"
0x140023178  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14002317f  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x140023184  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002318b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140023190  mov     rcx, [rsp+48h+pstm]
0x140023195  test    rcx, rcx
0x140023198  jz      short loc_1400231AB
0x14002319a  mov     rax, [rcx]
0x14002319d  mov     rax, [rax+10h]
0x1400231a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400231a6  mov     [rsp+48h+pstm], rbp
0x1400231ab  test    rdi, rdi
0x1400231ae  jz      short loc_1400231BF
0x1400231b0  mov     rcx, rdi
0x1400231b3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400231ba  nop     dword ptr [rax+rax+00h]
0x1400231bf  mov     eax, ebx
0x1400231c1  mov     rbx, [rsp+48h+arg_0]
0x1400231c6  add     rsp, 30h
0x1400231ca  pop     rdi
0x1400231cb  pop     rsi
0x1400231cc  pop     rbp
0x1400231cd  retn
```
