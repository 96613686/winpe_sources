# CRAInvitationHistoryManager::put_InvitationItem(CRAInvitationHistoryItem *)

- ea: `0x140043e00`
- end: `0x1400441f4`
- name: `?put_InvitationItem@CRAInvitationHistoryManager@@QEAAJPEAVCRAInvitationHistoryItem@@@Z`
- size: `1012`
- prototype: `int(CRAInvitationHistoryManager *__hidden this, struct CRAInvitationHistoryItem *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002f0d0`
- `0x140031e8c`

## callees

- `0x140001cc4`
- `0x140034ce4`
- `0x140041998`
- `0x140041a4c`
- `0x140043b64`
- `0x140043c34`
- `0x140043e00`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140043fca`
- `KERNEL32!CompareStringW` at `0x140043fca`
- `KERNEL32!HeapFree` at `0x140044171`
- `KERNEL32!HeapFree` at `0x140044171`
- `KERNEL32!GetProcessHeap` at `0x14004400a`
- `KERNEL32!GetProcessHeap` at `0x14004415d`
- `KERNEL32!GetProcessHeap` at `0x14004400a`
- `KERNEL32!GetProcessHeap` at `0x14004415d`
- `KERNEL32!HeapAlloc` at `0x14004401f`
- `KERNEL32!HeapAlloc` at `0x14004401f`
- `msvcrt!??3@YAXPEAX@Z` at `0x140044094`
- `msvcrt!??3@YAXPEAX@Z` at `0x140044149`
- `msvcrt!??3@YAXPEAX@Z` at `0x140044094`
- `msvcrt!??3@YAXPEAX@Z` at `0x140044149`
- `OLEAUT32!__imp_SysFreeString` at `0x140043fe7`
- `OLEAUT32!__imp_SysFreeString` at `0x140044185`
- `OLEAUT32!__imp_SysFreeString` at `0x140044199`
- `OLEAUT32!__imp_SysFreeString` at `0x140043fe7`
- `OLEAUT32!__imp_SysFreeString` at `0x140044185`
- `OLEAUT32!__imp_SysFreeString` at `0x140044199`
- `OLEAUT32!__imp_SysStringLen` at `0x140043efb`
- `OLEAUT32!__imp_SysStringLen` at `0x140043fa0`
- `OLEAUT32!__imp_SysStringLen` at `0x140043efb`
- `OLEAUT32!__imp_SysStringLen` at `0x140043fa0`

## pseudocode

```c
__int64 __fastcall CRAInvitationHistoryManager::put_InvitationItem(
        CRAInvitationHistoryManager *this,
        struct CRAInvitationHistoryItem *a2)
{
  WCHAR *lpString2; // rsi
  char *v5; // rax
  CRAInvitationHistoryManager *v6; // rcx
  CRAInvitationHistoryItem *v7; // rdi
  signed int v8; // eax
  unsigned int v9; // ebx
  signed int Address; // eax
  unsigned int v11; // r9d
  WCHAR *v12; // r12
  unsigned int v13; // r9d
  __int64 *v14; // r15
  __int64 *v15; // r13
  bool v16; // zf
  CRAInvitationHistoryItem *v17; // rcx
  signed int Name; // eax
  unsigned int v19; // r9d
  UINT cchCount2; // eax
  HANDLE ProcessHeap; // rax
  __int64 *v22; // rax
  __int64 *v23; // rcx
  __int64 *v24; // r14
  __int64 *v25; // rax
  __int64 v26; // rcx
  void *v27; // r13
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 *v30; // rdi
  __int64 *v31; // rax
  __int64 v32; // rcx
  void *v33; // r14
  HANDLE v34; // rax
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v37; // [rsp+38h] [rbp-8h]
  BSTR pbstr; // [rsp+90h] [rbp+50h] BYREF
  int cchCount1; // [rsp+98h] [rbp+58h]

  pbstr = 0;
  bstrString = 0;
  lpString2 = 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (CRAInvitationHistoryItem *)v5;
  if ( !v5 )
  {
    v13 = 943;
    goto LABEL_42;
  }
  *(_OWORD *)(v5 + 40) = 0;
  *((_DWORD *)v5 + 14) = 0;
  *(_QWORD *)v5 = 0;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v8 = CRAInvitationHistoryManager::CloneHistoryItem(v6, a2, (struct CRAInvitationHistoryItem *)v5);
  v9 = v8;
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      0x3B1u,
      L"CRAInvitationHistoryManager::put_InvitationItem",
      v8);
    return v9;
  }
  if ( *((_DWORD *)this + 1) == 3 )
  {
    Address = CRAInvitationHistoryItem::get_Address(v7, &pbstr);
    v9 = Address;
    if ( Address < 0 )
    {
      v11 = 947;
LABEL_7:
      CEventLogger::LogError(
        (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        v11,
        L"CRAInvitationHistoryManager::put_InvitationItem",
        Address);
      v12 = pbstr;
      goto LABEL_39;
    }
  }
  else
  {
    Address = CRAInvitationHistoryItem::get_Name(v7, &pbstr);
    v9 = Address;
    if ( Address < 0 )
    {
      v11 = 949;
      goto LABEL_7;
    }
  }
  v12 = pbstr;
  if ( !pbstr )
  {
    v13 = 951;
LABEL_42:
    v9 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
      &Recoverable_Error,
      (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
      v13,
      L"CRAInvitationHistoryManager::put_InvitationItem",
      0x8007000E);
    return v9;
  }
  v14 = (__int64 *)((char *)this + 488);
  cchCount1 = SysStringLen(pbstr);
  v15 = (__int64 *)*((_QWORD *)this + 61);
  LODWORD(pbstr) = 0;
  if ( *(int *)this <= 0 )
  {
LABEL_25:
    ProcessHeap = GetProcessHeap();
    v22 = (__int64 *)HeapAlloc(ProcessHeap, 0, 0x18u);
    v23 = v22;
    if ( v22 )
    {
      v22[2] = (__int64)v7;
      v29 = *v14;
      *v23 = *v14;
      v23[1] = (__int64)v14;
      *(_QWORD *)(v29 + 8) = v23;
      *v14 = (__int64)v23;
      if ( *(int *)this >= 60 )
      {
        v30 = (__int64 *)*((_QWORD *)this + 62);
        v31 = (__int64 *)v30[1];
        v32 = *v30;
        *v31 = *v30;
        *(_QWORD *)(v32 + 8) = v31;
        v33 = (void *)v30[2];
        if ( v33 )
        {
          CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v30[2]);
          operator delete(v33);
          v30[2] = 0;
        }
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v30);
      }
      else
      {
        ++*(_DWORD *)this;
      }
    }
    else
    {
      v9 = -2147467261;
      CEventLogger::LogError(
        (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x3FCu,
        L"CRAInvitationHistoryManager::put_InvitationItem",
        0x80004003);
    }
    goto LABEL_37;
  }
  while ( 1 )
  {
    if ( v15 == v14 )
      goto LABEL_25;
    v16 = *((_DWORD *)this + 1) == 3;
    v17 = (CRAInvitationHistoryItem *)v15[2];
    v37 = (__int64 *)*v15;
    if ( v16 )
    {
      Name = CRAInvitationHistoryItem::get_Address(v17, &bstrString);
      v9 = Name;
      if ( Name < 0 )
      {
        v19 = 973;
LABEL_17:
        CEventLogger::LogError(
          (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          v19,
          L"CRAInvitationHistoryManager::put_InvitationItem",
          Name);
        lpString2 = bstrString;
        goto LABEL_37;
      }
    }
    else
    {
      Name = CRAInvitationHistoryItem::get_Name(v17, &bstrString);
      v9 = Name;
      if ( Name < 0 )
      {
        v19 = 976;
        goto LABEL_17;
      }
    }
    lpString2 = bstrString;
    if ( !bstrString )
    {
      v9 = -2147024882;
      CEventLogger::LogError(
        (CEventLogger *)L"CRAInvitationHistoryManager::put_InvitationItem",
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x3D2u,
        L"CRAInvitationHistoryManager::put_InvitationItem",
        0x8007000E);
      goto LABEL_39;
    }
    v15 = v37;
    cchCount2 = SysStringLen(bstrString);
    if ( cchCount1 == cchCount2 && CompareStringW(0x7Fu, 1u, v12, cchCount1, lpString2, cchCount2) == 2 )
      break;
    if ( lpString2 )
    {
      SysFreeString(lpString2);
      lpString2 = 0;
      bstrString = 0;
    }
    LODWORD(pbstr) = (_DWORD)pbstr + 1;
    if ( (int)pbstr >= *(_DWORD *)this )
      goto LABEL_25;
  }
  v24 = (__int64 *)v15[1];
  v25 = (__int64 *)v24[1];
  v26 = *v24;
  *v25 = *v24;
  *(_QWORD *)(v26 + 8) = v25;
  v27 = (void *)v24[2];
  if ( v27 )
  {
    CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v24[2]);
    operator delete(v27);
  }
  v24[2] = (__int64)v7;
  v28 = *v14;
  *v24 = *v14;
  v24[1] = (__int64)v14;
  *(_QWORD *)(v28 + 8) = v24;
  *v14 = (__int64)v24;
LABEL_37:
  if ( lpString2 )
    SysFreeString(lpString2);
LABEL_39:
  if ( v12 )
    SysFreeString(v12);
  return v9;
}

```

## disassembly

```asm
0x140043e00  mov     [rsp-38h+arg_0], rbx
0x140043e05  push    rbp
0x140043e06  push    rsi
0x140043e07  push    rdi
0x140043e08  push    r12
0x140043e0a  push    r13
0x140043e0c  push    r14
0x140043e0e  push    r15
0x140043e10  mov     rbp, rsp
0x140043e13  sub     rsp, 40h
0x140043e17  xor     r12d, r12d
0x140043e1a  mov     rbx, rdx
0x140043e1d  mov     r14, rcx
0x140043e20  mov     [rbp+pbstr], r12
0x140043e24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140043e2b  mov     [rbp+bstrString], r12
0x140043e2f  mov     esi, r12d
0x140043e32  lea     ecx, [r12+40h]; unsigned __int64
0x140043e37  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140043e3c  mov     rdi, rax
0x140043e3f  test    rax, rax
0x140043e42  jz      loc_1400441A7
0x140043e48  xorps   xmm0, xmm0
0x140043e4b  mov     r8, rax; struct CRAInvitationHistoryItem *
0x140043e4e  movups  xmmword ptr [rax+28h], xmm0
0x140043e52  mov     rdx, rbx; struct CRAInvitationHistoryItem *
0x140043e55  mov     [rax+38h], r12d
0x140043e59  mov     [rax], r12
0x140043e5c  mov     [rax+8], r12
0x140043e60  mov     [rax+10h], r12
0x140043e64  mov     [rax+18h], r12
0x140043e68  mov     [rax+20h], r12
0x140043e6c  call    ?CloneHistoryItem@CRAInvitationHistoryManager@@AEAAJPEAVCRAInvitationHistoryItem@@0@Z; CRAInvitationHistoryManager::CloneHistoryItem(CRAInvitationHistoryItem *,CRAInvitationHistoryItem *)
0x140043e71  mov     ebx, eax
0x140043e73  test    eax, eax
0x140043e75  jns     short loc_140043E86
0x140043e77  mov     [rsp+40h+cchCount2], eax
0x140043e7b  mov     r9d, 3B1h
0x140043e81  jmp     loc_1400441BA
0x140043e86  cmp     dword ptr [r14+4], 3
0x140043e8b  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x140043e8f  mov     rcx, rdi; this
0x140043e92  jnz     short loc_140043ED1
0x140043e94  call    ?get_Address@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Address(ushort * *)
0x140043e99  mov     ebx, eax
0x140043e9b  test    eax, eax
0x140043e9d  jns     short loc_140043EE4
0x140043e9f  mov     r9d, 3B3h; unsigned int
0x140043ea5  lea     rcx, aCrainvitationh; "CRAInvitationHistoryManager::put_Invita"...
0x140043eac  mov     [rsp+40h+cchCount2], eax; unsigned int
0x140043eb0  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140043eb7  mov     [rsp+40h+lpString2], rcx; unsigned __int16 *
0x140043ebc  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140043ec3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140043ec8  mov     r12, [rbp+pbstr]
0x140043ecc  jmp     loc_140044191
0x140043ed1  call    ?get_Name@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Name(ushort * *)
0x140043ed6  mov     ebx, eax
0x140043ed8  test    eax, eax
0x140043eda  jns     short loc_140043EE4
0x140043edc  mov     r9d, 3B5h
0x140043ee2  jmp     short loc_140043EA5
0x140043ee4  mov     r12, [rbp+pbstr]
0x140043ee8  test    r12, r12
0x140043eeb  jnz     short loc_140043EF8
0x140043eed  mov     r9d, 3B7h
0x140043ef3  jmp     loc_1400441AD
0x140043ef8  mov     rcx, r12; pbstr
0x140043efb  call    cs:__imp_SysStringLen
0x140043f02  nop     dword ptr [rax+rax+00h]
0x140043f07  lea     r15, [r14+1E8h]
0x140043f0e  mov     [rbp+cchCount1], eax
0x140043f11  mov     r13, [r15]
0x140043f14  mov     dword ptr [rbp+pbstr], esi
0x140043f17  cmp     [r14], esi
0x140043f1a  jle     loc_14004400A
0x140043f20  cmp     r13, r15
0x140043f23  jz      loc_14004400A
0x140043f29  cmp     dword ptr [r14+4], 3
0x140043f2e  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140043f32  mov     rax, [r13+0]
0x140043f36  mov     rcx, [r13+10h]; this
0x140043f3a  mov     [rbp+var_8], rax
0x140043f3e  jnz     short loc_140043F7D
0x140043f40  call    ?get_Address@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Address(ushort * *)
0x140043f45  mov     ebx, eax
0x140043f47  test    eax, eax
0x140043f49  jns     short loc_140043F8C
0x140043f4b  mov     r9d, 3CDh; unsigned int
0x140043f51  lea     rcx, aCrainvitationh; "CRAInvitationHistoryManager::put_Invita"...
0x140043f58  mov     [rsp+40h+cchCount2], eax; unsigned int
0x140043f5c  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140043f63  mov     [rsp+40h+lpString2], rcx; unsigned __int16 *
0x140043f68  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140043f6f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140043f74  mov     rsi, [rbp+bstrString]
0x140043f78  jmp     loc_14004417D
0x140043f7d  call    ?get_Name@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Name(ushort * *)
0x140043f82  mov     ebx, eax
0x140043f84  test    eax, eax
0x140043f86  js      loc_1400440F1
0x140043f8c  mov     rsi, [rbp+bstrString]
0x140043f90  test    rsi, rsi
0x140043f93  jz      loc_1400440BA
0x140043f99  mov     r13, [rbp+var_8]
0x140043f9d  mov     rcx, rsi; pbstr
0x140043fa0  call    cs:__imp_SysStringLen
0x140043fa7  nop     dword ptr [rax+rax+00h]
0x140043fac  mov     ecx, [rbp+cchCount1]
0x140043faf  cmp     ecx, eax
0x140043fb1  jnz     short loc_140043FDF
0x140043fb3  mov     edx, 1; dwCmpFlags
0x140043fb8  mov     [rsp+40h+cchCount2], eax; cchCount2
0x140043fbc  mov     r9d, ecx; cchCount1
0x140043fbf  mov     [rsp+40h+lpString2], rsi; lpString2
0x140043fc4  mov     r8, r12; lpString1
0x140043fc7  lea     ecx, [rdx+7Eh]; Locale
0x140043fca  call    cs:__imp_CompareStringW
0x140043fd1  nop     dword ptr [rax+rax+00h]
0x140043fd6  cmp     eax, 2
0x140043fd9  jz      loc_14004406E
0x140043fdf  test    rsi, rsi
0x140043fe2  jz      short loc_140043FF9
0x140043fe4  mov     rcx, rsi; bstrString
0x140043fe7  call    cs:__imp_SysFreeString
0x140043fee  nop     dword ptr [rax+rax+00h]
0x140043ff3  xor     esi, esi
0x140043ff5  mov     [rbp+bstrString], rsi
0x140043ff9  mov     eax, dword ptr [rbp+pbstr]
0x140043ffc  inc     eax
0x140043ffe  mov     dword ptr [rbp+pbstr], eax
0x140044001  cmp     eax, [r14]
0x140044004  jl      loc_140043F20
0x14004400a  call    cs:__imp_GetProcessHeap
0x140044011  nop     dword ptr [rax+rax+00h]
0x140044016  xor     edx, edx; dwFlags
0x140044018  mov     rcx, rax; hHeap
0x14004401b  lea     r8d, [rdx+18h]; dwBytes
0x14004401f  call    cs:__imp_HeapAlloc
0x140044026  nop     dword ptr [rax+rax+00h]
0x14004402b  mov     rcx, rax
0x14004402e  test    rax, rax
0x140044031  jnz     loc_1400440FC
0x140044037  lea     rcx, aCrainvitationh; "CRAInvitationHistoryManager::put_Invita"...
0x14004403e  mov     [rsp+40h+cchCount2], 80004003h; unsigned int
0x140044046  mov     r9d, 3FCh; unsigned int
0x14004404c  mov     [rsp+40h+lpString2], rcx; unsigned __int16 *
0x140044051  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140044058  mov     ebx, 80004003h
0x14004405d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140044064  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140044069  jmp     loc_14004417D
0x14004406e  mov     r14, [r13+8]
0x140044072  mov     rax, [r14+8]
0x140044076  mov     rcx, [r14]
0x140044079  mov     [rax], rcx
0x14004407c  mov     [rcx+8], rax
0x140044080  mov     r13, [r14+10h]
0x140044084  test    r13, r13
0x140044087  jz      short loc_1400440A0
0x140044089  mov     rcx, r13; this
0x14004408c  call    ??1CRAInvitationHistoryItem@@QEAA@XZ; CRAInvitationHistoryItem::~CRAInvitationHistoryItem(void)
0x140044091  mov     rcx, r13
0x140044094  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14004409b  nop     dword ptr [rax+rax+00h]
0x1400440a0  mov     [r14+10h], rdi
0x1400440a4  mov     rax, [r15]
0x1400440a7  mov     [r14], rax
0x1400440aa  mov     [r14+8], r15
0x1400440ae  mov     [rax+8], r14
0x1400440b2  mov     [r15], r14
0x1400440b5  jmp     loc_14004417D
0x1400440ba  lea     rcx, aCrainvitationh; "CRAInvitationHistoryManager::put_Invita"...
0x1400440c1  mov     [rsp+40h+cchCount2], 8007000Eh; unsigned int
0x1400440c9  mov     r9d, 3D2h; unsigned int
0x1400440cf  mov     [rsp+40h+lpString2], rcx; unsigned __int16 *
0x1400440d4  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x1400440db  mov     ebx, 8007000Eh
0x1400440e0  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400440e7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400440ec  jmp     loc_140044191
0x1400440f1  mov     r9d, 3D0h
0x1400440f7  jmp     loc_140043F51
0x1400440fc  mov     [rax+10h], rdi
0x140044100  mov     rax, [r15]
0x140044103  mov     [rcx], rax
0x140044106  mov     [rcx+8], r15
0x14004410a  mov     [rax+8], rcx
0x14004410e  mov     [r15], rcx
0x140044111  mov     eax, [r14]
0x140044114  cmp     eax, 3Ch ; '<'
0x140044117  jge     short loc_140044120
0x140044119  inc     eax
0x14004411b  mov     [r14], eax
0x14004411e  jmp     short loc_14004417D
0x140044120  mov     rdi, [r14+1F0h]
0x140044127  mov     rax, [rdi+8]
0x14004412b  mov     rcx, [rdi]
0x14004412e  mov     [rax], rcx
0x140044131  mov     [rcx+8], rax
0x140044135  mov     r14, [rdi+10h]
0x140044139  test    r14, r14
0x14004413c  jz      short loc_14004415D
0x14004413e  mov     rcx, r14; this
0x140044141  call    ??1CRAInvitationHistoryItem@@QEAA@XZ; CRAInvitationHistoryItem::~CRAInvitationHistoryItem(void)
0x140044146  mov     rcx, r14
0x140044149  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140044150  nop     dword ptr [rax+rax+00h]
0x140044155  mov     qword ptr [rdi+10h], 0
0x14004415d  call    cs:__imp_GetProcessHeap
0x140044164  nop     dword ptr [rax+rax+00h]
0x140044169  mov     r8, rdi; lpMem
0x14004416c  xor     edx, edx; dwFlags
0x14004416e  mov     rcx, rax; hHeap
0x140044171  call    cs:__imp_HeapFree
0x140044178  nop     dword ptr [rax+rax+00h]
0x14004417d  test    rsi, rsi
0x140044180  jz      short loc_140044191
0x140044182  mov     rcx, rsi; bstrString
0x140044185  call    cs:__imp_SysFreeString
0x14004418c  nop     dword ptr [rax+rax+00h]
0x140044191  test    r12, r12
0x140044194  jz      short loc_1400441D9
0x140044196  mov     rcx, r12; bstrString
0x140044199  call    cs:__imp_SysFreeString
0x1400441a0  nop     dword ptr [rax+rax+00h]
0x1400441a5  jmp     short loc_1400441D9
0x1400441a7  mov     r9d, 3AFh; unsigned int
0x1400441ad  mov     [rsp+40h+cchCount2], 8007000Eh; unsigned int
0x1400441b5  mov     ebx, 8007000Eh
0x1400441ba  lea     rcx, aCrainvitationh; "CRAInvitationHistoryManager::put_Invita"...
0x1400441c1  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x1400441c8  mov     [rsp+40h+lpString2], rcx; unsigned __int16 *
0x1400441cd  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400441d4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400441d9  mov     eax, ebx
0x1400441db  mov     rbx, [rsp+40h+arg_0]
0x1400441e3  add     rsp, 40h
0x1400441e7  pop     r15
0x1400441e9  pop     r14
0x1400441eb  pop     r13
0x1400441ed  pop     r12
0x1400441ef  pop     rdi
0x1400441f0  pop     rsi
0x1400441f1  pop     rbp
0x1400441f2  retn
```
