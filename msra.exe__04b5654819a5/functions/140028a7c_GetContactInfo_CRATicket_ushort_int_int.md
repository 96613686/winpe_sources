# GetContactInfo(CRATicket *,ushort *,int,int)

- ea: `0x140028a7c`
- end: `0x140028ed4`
- name: `?GetContactInfo@@YAJPEAVCRATicket@@PEAGHH@Z`
- size: `1112`
- prototype: `int(struct CRATicket *, unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140012794`
- `0x140026750`

## callees

- `0x140028a7c`
- `0x140029334`
- `0x14002c0a4`
- `0x140034ce4`
- `0x14003fdbc`
- `0x14003fe58`
- `0x14003ff50`
- `0x140040070`
- `0x140040220`
- `0x140041998`
- `0x140041a4c`
- `0x140041cc8`
- `0x140043b64`
- `0x140043bcc`
- `0x140043c34`
- `0x140043c9c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140028be0`
- `KERNEL32!CompareStringW` at `0x140028be0`
- `OLEAUT32!__imp_SysFreeString` at `0x140028bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x140028c35`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e74`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e88`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e9c`
- `OLEAUT32!__imp_SysFreeString` at `0x140028bfc`
- `OLEAUT32!__imp_SysFreeString` at `0x140028c35`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e74`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e88`
- `OLEAUT32!__imp_SysFreeString` at `0x140028e9c`
- `OLEAUT32!__imp_SysStringLen` at `0x140028b4c`
- `OLEAUT32!__imp_SysStringLen` at `0x140028bb1`
- `OLEAUT32!__imp_SysStringLen` at `0x140028b4c`
- `OLEAUT32!__imp_SysStringLen` at `0x140028bb1`

## string_xrefs

- `0x140028b30`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140028d37`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140028d7b`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140028dba`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetContactInfo(struct CRATicket *a1, unsigned __int16 *a2, int a3, int a4)
{
  int v4; // r13d
  OLECHAR *v5; // r12
  WCHAR *lpString2; // rdi
  unsigned __int16 *v7; // r14
  signed int InvitationManagerLoaded; // eax
  CEventLogger *v9; // rcx
  signed int v10; // ebx
  int v11; // r15d
  CRAInvitationHistoryManager *v12; // rcx
  __int64 **v13; // r15
  int v14; // r12d
  __int64 *v15; // r13
  signed int Address; // eax
  CEventLogger *v17; // rcx
  UINT v18; // eax
  signed int v19; // eax
  signed int PublicKey; // eax
  CEventLogger *v21; // rcx
  unsigned __int16 *v22; // r15
  signed int Name; // eax
  CEventLogger *v24; // rcx
  unsigned __int16 *v25; // rdi
  signed int ComputerName; // eax
  CEventLogger *v27; // rcx
  CRATicket *v28; // rcx
  BSTR pbstr; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 *v31; // [rsp+48h] [rbp-C0h] BYREF
  int cchCount1[2]; // [rsp+50h] [rbp-B8h]
  BSTR v33; // [rsp+58h] [rbp-B0h] BYREF
  BSTR bstrString[9]; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v35[122]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v36[11]; // [rsp+290h] [rbp+188h] BYREF

  v4 = a4;
  v5 = a2;
  lpString2 = 0;
  v35[0] = 0;
  v35[1] = 1;
  v36[1] = v36;
  v36[0] = v36;
  v33 = 0;
  memset(bstrString, 0, 68);
  v7 = 0;
  v31 = 0;
  InvitationManagerLoaded = GetInvitationManagerLoaded((struct CRAInvitationHistoryManager *)v35, 3);
  v10 = InvitationManagerLoaded;
  if ( InvitationManagerLoaded < 0 )
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x17A8u,
      L"GetContactInfo",
      InvitationManagerLoaded);
    goto LABEL_43;
  }
  v11 = 0;
  cchCount1[0] = SysStringLen(v5);
  pbstr = 0;
  if ( v35[0] <= 0 )
  {
    v10 = 0;
  }
  else
  {
    v13 = (__int64 **)v36[0];
    v14 = 0;
    v10 = 0;
    while ( 1 )
    {
      if ( v13 == v36 )
        goto LABEL_13;
      v15 = *v13;
      Address = CRAInvitationHistoryItem::get_Address((CRAInvitationHistoryItem *)v13[2], &pbstr);
      v10 = Address;
      if ( Address < 0 )
      {
        CEventLogger::LogError(
          v17,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x452u,
          L"CRAInvitationHistoryManager::get_InvitationItemByMatch",
          Address);
        lpString2 = pbstr;
        goto LABEL_13;
      }
      lpString2 = pbstr;
      v18 = SysStringLen(pbstr);
      v12 = (CRAInvitationHistoryManager *)(unsigned int)cchCount1[0];
      if ( cchCount1[0] == v18 && CompareStringW(0x7Fu, 1u, a2, cchCount1[0], lpString2, v18) == 2 )
        break;
      v13 = (__int64 **)v15;
      if ( lpString2 )
      {
        SysFreeString(lpString2);
        lpString2 = 0;
        pbstr = 0;
      }
      if ( ++v14 >= v35[0] )
        goto LABEL_13;
    }
    v19 = CRAInvitationHistoryManager::CloneHistoryItem(
            v12,
            (struct CRAInvitationHistoryItem *)v13[2],
            (struct CRAInvitationHistoryItem *)&bstrString[1]);
    v10 = v19;
    if ( v19 < 0 )
    {
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x468u,
        L"CRAInvitationHistoryManager::get_InvitationItemByMatch",
        v19);
LABEL_13:
      v11 = 0;
      goto LABEL_14;
    }
    v11 = 1;
LABEL_14:
    v5 = a2;
    v4 = a4;
  }
  if ( lpString2 )
    SysFreeString(lpString2);
  if ( !v11 )
  {
    v10 = -2147467259;
LABEL_25:
    if ( v4 == 1 )
      ShowErrorMessage(0x251u, 0x24Eu, 0, 0, (unsigned __int16 *)0xFFFE, 0);
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x17BAu,
      L"GetContactInfo",
      v10);
    goto LABEL_43;
  }
  if ( v10 < 0 )
    goto LABEL_25;
  PublicKey = CRAInvitationHistoryItem::get_PublicKey((CRAInvitationHistoryItem *)&bstrString[1], &v33);
  v10 = PublicKey;
  v22 = v33;
  if ( PublicKey >= 0 )
  {
    Name = CRAInvitationHistoryItem::get_Name((CRAInvitationHistoryItem *)&bstrString[1], bstrString);
    v10 = Name;
    v25 = bstrString[0];
    if ( Name >= 0 )
    {
      ComputerName = CRAInvitationHistoryItem::get_ComputerName((CRAInvitationHistoryItem *)&bstrString[1], &v31);
      v10 = ComputerName;
      if ( ComputerName >= 0 )
      {
        *((_DWORD *)a1 + 34) = 8;
        v28 = (CRATicket *)*((_QWORD *)_AtlModule + 104);
        if ( a3 )
        {
          CRATicket::put_ExpertName(v28, v25);
          v7 = v31;
          CRATicket::put_ComputerName(*((CRATicket **)_AtlModule + 104), v31);
          CRATicket::put_PNRPAddress(*((CRATicket **)_AtlModule + 104), v22);
        }
        else
        {
          CRATicket::put_NoviceName(v28, v25);
          v7 = v31;
          CRATicket::put_ComputerName(*((CRATicket **)_AtlModule + 104), v31);
          CRATicket::put_UserPassword(*((CRATicket **)_AtlModule + 104), v5);
        }
      }
      else
      {
        CEventLogger::LogError(
          v27,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x17C0u,
          L"GetContactInfo",
          ComputerName);
        v7 = v31;
      }
    }
    else
    {
      CEventLogger::LogError(
        v24,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x17BFu,
        L"GetContactInfo",
        Name);
    }
    if ( v25 )
      SysFreeString(v25);
  }
  else
  {
    CEventLogger::LogError(
      v21,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x17BEu,
      L"GetContactInfo",
      PublicKey);
  }
  if ( v22 )
    SysFreeString(v22);
  if ( v7 )
    SysFreeString(v7);
LABEL_43:
  CRAInvitationHistoryManager::EmptyList((CRAInvitationHistoryManager *)v35);
  CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)&bstrString[1]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140028a7c  mov     rax, rsp
0x140028a7f  mov     [rax+20h], r9d
0x140028a83  mov     [rax+18h], r8d
0x140028a87  mov     [rax+10h], rdx
0x140028a8b  mov     [rax+8], rcx
0x140028a8f  push    rbp
0x140028a90  push    rbx
0x140028a91  push    rsi
0x140028a92  push    rdi
0x140028a93  push    r12
0x140028a95  push    r13
0x140028a97  push    r14
0x140028a99  push    r15
0x140028a9b  lea     rbp, [rax-1E8h]
0x140028aa2  sub     rsp, 2A8h
0x140028aa9  mov     r13d, r9d
0x140028aac  mov     r12, rdx
0x140028aaf  xorps   xmm0, xmm0
0x140028ab2  movups  [rbp+1E0h+var_258], xmm0
0x140028ab6  xor     edi, edi
0x140028ab8  mov     [rbp+1E0h+var_248], edi
0x140028abb  movdqa  xmmword ptr [rsp+2E0h+bstrString+8], xmm0
0x140028ac1  xorps   xmm1, xmm1
0x140028ac4  movdqa  [rsp+2E0h+var_278+8], xmm1
0x140028aca  mov     [rbp+1E0h+var_260], rdi
0x140028ace  mov     [rbp+1E0h+var_240], edi
0x140028ad1  mov     [rbp+1E0h+var_23C], 1
0x140028ad8  lea     rax, [rbp+1E0h+var_58]
0x140028adf  mov     [rbp+1E0h+var_50], rax
0x140028ae6  lea     rax, [rbp+1E0h+var_58]
0x140028aed  mov     [rbp+1E0h+var_58], rax
0x140028af4  mov     [rsp+2E0h+var_290], rdi
0x140028af9  mov     [rsp+2E0h+bstrString], rdi
0x140028afe  mov     r14d, edi
0x140028b01  mov     [rsp+2E0h+var_2A0], rdi
0x140028b06  lea     edx, [rdi+3]; int
0x140028b09  lea     rcx, [rbp+1E0h+var_240]; this
0x140028b0d  call    ?GetInvitationManagerLoaded@@YAJPEAVCRAInvitationHistoryManager@@H@Z; GetInvitationManagerLoaded(CRAInvitationHistoryManager *,int)
0x140028b12  mov     ebx, eax
0x140028b14  test    eax, eax
0x140028b16  jns     short loc_140028B46
0x140028b18  mov     [rsp+28h], eax; unsigned int
0x140028b1c  mov     r9d, 17A8h; unsigned int
0x140028b22  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140028b29  lea     rax, aGetcontactinfo; "GetContactInfo"
0x140028b30  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028b37  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028b3c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028b41  jmp     loc_140028EA9
0x140028b46  mov     r15d, edi
0x140028b49  mov     rcx, r12; pbstr
0x140028b4c  call    cs:__imp_SysStringLen
0x140028b53  nop     dword ptr [rax+rax+00h]
0x140028b58  mov     [rsp+2E0h+cchCount1], eax
0x140028b5c  mov     [rsp+2E0h+pbstr], rdi
0x140028b61  lea     rsi, Recoverable_Error
0x140028b68  cmp     [rbp+1E0h+var_240], r14d
0x140028b6c  jle     loc_140028CC3
0x140028b72  mov     r15, [rbp+1E0h+var_58]
0x140028b79  xor     r12d, r12d
0x140028b7c  xor     ebx, ebx
0x140028b7e  lea     rax, [rbp+1E0h+var_58]
0x140028b85  cmp     r15, rax
0x140028b88  jz      loc_140028C1C
0x140028b8e  mov     r13, [r15]
0x140028b91  lea     rdx, [rsp+2E0h+pbstr]; unsigned __int16 **
0x140028b96  mov     rcx, [r15+10h]; this
0x140028b9a  call    ?get_Address@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Address(ushort * *)
0x140028b9f  mov     ebx, eax
0x140028ba1  test    eax, eax
0x140028ba3  js      loc_140028C94
0x140028ba9  mov     rdi, [rsp+2E0h+pbstr]
0x140028bae  mov     rcx, rdi; pbstr
0x140028bb1  call    cs:__imp_SysStringLen
0x140028bb8  nop     dword ptr [rax+rax+00h]
0x140028bbd  mov     ecx, [rsp+2E0h+cchCount1]
0x140028bc1  cmp     ecx, eax
0x140028bc3  jnz     short loc_140028BF1
0x140028bc5  mov     [rsp+28h], eax; cchCount2
0x140028bc9  mov     [rsp+2E0h+lpString2], rdi; lpString2
0x140028bce  mov     r9d, ecx; cchCount1
0x140028bd1  mov     r8, [rbp+1E0h+lpString1]; lpString1
0x140028bd8  mov     edx, 1; dwCmpFlags
0x140028bdd  lea     ecx, [rdx+7Eh]; Locale
0x140028be0  call    cs:__imp_CompareStringW
0x140028be7  nop     dword ptr [rax+rax+00h]
0x140028bec  cmp     eax, 2
0x140028bef  jz      short loc_140028C51
0x140028bf1  mov     r15, r13
0x140028bf4  test    rdi, rdi
0x140028bf7  jz      short loc_140028C0F
0x140028bf9  mov     rcx, rdi; bstrString
0x140028bfc  call    cs:__imp_SysFreeString
0x140028c03  nop     dword ptr [rax+rax+00h]
0x140028c08  xor     edi, edi
0x140028c0a  mov     [rsp+2E0h+pbstr], rdi
0x140028c0f  inc     r12d
0x140028c12  cmp     r12d, [rbp+1E0h+var_240]
0x140028c16  jl      loc_140028B7E
0x140028c1c  mov     r15d, r14d
0x140028c1f  mov     r12, [rbp+1E0h+lpString1]
0x140028c26  mov     r13d, [rbp+1E0h+arg_18]
0x140028c2d  test    rdi, rdi
0x140028c30  jz      short loc_140028C41
0x140028c32  mov     rcx, rdi; bstrString
0x140028c35  call    cs:__imp_SysFreeString
0x140028c3c  nop     dword ptr [rax+rax+00h]
0x140028c41  test    r15d, r15d
0x140028c44  jnz     loc_140028CCA
0x140028c4a  mov     ebx, 80004005h
0x140028c4f  jmp     short loc_140028CCE
0x140028c51  lea     r8, [rsp+2E0h+bstrString+8]; struct CRAInvitationHistoryItem *
0x140028c56  mov     rdx, [r15+10h]; struct CRAInvitationHistoryItem *
0x140028c5a  call    ?CloneHistoryItem@CRAInvitationHistoryManager@@AEAAJPEAVCRAInvitationHistoryItem@@0@Z; CRAInvitationHistoryManager::CloneHistoryItem(CRAInvitationHistoryItem *,CRAInvitationHistoryItem *)
0x140028c5f  mov     ebx, eax
0x140028c61  test    eax, eax
0x140028c63  jns     short loc_140028C8C
0x140028c65  mov     [rsp+28h], eax; unsigned int
0x140028c69  lea     rax, aCrainvitationh_4; "CRAInvitationHistoryManager::get_Invita"...
0x140028c70  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028c75  mov     r9d, 468h; unsigned int
0x140028c7b  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140028c82  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140028c85  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028c8a  jmp     short loc_140028C1C
0x140028c8c  mov     r15d, 1
0x140028c92  jmp     short loc_140028C1F
0x140028c94  mov     [rsp+28h], eax; unsigned int
0x140028c98  lea     rax, aCrainvitationh_4; "CRAInvitationHistoryManager::get_Invita"...
0x140028c9f  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028ca4  mov     r9d, 452h; unsigned int
0x140028caa  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x140028cb1  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140028cb4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028cb9  mov     rdi, [rsp+2E0h+pbstr]
0x140028cbe  jmp     loc_140028C1C
0x140028cc3  xor     ebx, ebx
0x140028cc5  jmp     loc_140028C2D
0x140028cca  test    ebx, ebx
0x140028ccc  jns     short loc_140028D07
0x140028cce  cmp     r13d, 1
0x140028cd2  jnz     short loc_140028CF5
0x140028cd4  mov     [rsp+28h], r14d; int
0x140028cd9  mov     [rsp+2E0h+lpString2], 0FFFEh; unsigned __int16 *
0x140028ce2  xor     r9d, r9d; int
0x140028ce5  xor     r8d, r8d; HWND
0x140028ce8  mov     edx, 24Eh; int
0x140028ced  lea     ecx, [rdx+3]; int
0x140028cf0  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x140028cf5  mov     [rsp+28h], ebx
0x140028cf9  mov     r9d, 17BAh
0x140028cff  mov     rdx, rsi
0x140028d02  jmp     loc_140028B29
0x140028d07  lea     rdx, [rsp+2E0h+var_290]; unsigned __int16 **
0x140028d0c  lea     rcx, [rsp+2E0h+bstrString+8]; this
0x140028d11  call    ?get_PublicKey@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_PublicKey(ushort * *)
0x140028d16  mov     ebx, eax
0x140028d18  mov     r15, [rsp+2E0h+var_290]
0x140028d1d  test    eax, eax
0x140028d1f  jns     short loc_140028D4B
0x140028d21  mov     [rsp+28h], eax; unsigned int
0x140028d25  lea     rax, aGetcontactinfo; "GetContactInfo"
0x140028d2c  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028d31  mov     r9d, 17BEh; unsigned int
0x140028d37  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028d3e  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140028d41  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028d46  jmp     loc_140028E80
0x140028d4b  lea     rdx, [rsp+2E0h+bstrString]; unsigned __int16 **
0x140028d50  lea     rcx, [rsp+2E0h+bstrString+8]; this
0x140028d55  call    ?get_Name@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Name(ushort * *)
0x140028d5a  mov     ebx, eax
0x140028d5c  mov     rdi, [rsp+2E0h+bstrString]
0x140028d61  test    eax, eax
0x140028d63  jns     short loc_140028D8F
0x140028d65  mov     [rsp+28h], eax; unsigned int
0x140028d69  lea     rax, aGetcontactinfo; "GetContactInfo"
0x140028d70  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028d75  mov     r9d, 17BFh; unsigned int
0x140028d7b  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028d82  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140028d85  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028d8a  jmp     loc_140028E6C
0x140028d8f  lea     rdx, [rsp+2E0h+var_2A0]; unsigned __int16 **
0x140028d94  lea     rcx, [rsp+2E0h+bstrString+8]; this
0x140028d99  call    ?get_ComputerName@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_ComputerName(ushort * *)
0x140028d9e  mov     ebx, eax
0x140028da0  test    eax, eax
0x140028da2  jns     short loc_140028DD3
0x140028da4  mov     [rsp+28h], eax; unsigned int
0x140028da8  lea     rax, aGetcontactinfo; "GetContactInfo"
0x140028daf  mov     [rsp+2E0h+lpString2], rax; unsigned __int16 *
0x140028db4  mov     r9d, 17C0h; unsigned int
0x140028dba  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028dc1  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140028dc4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028dc9  mov     r14, [rsp+2E0h+var_2A0]
0x140028dce  jmp     loc_140028E6C
0x140028dd3  mov     rax, [rbp+1E0h+arg_0]
0x140028dda  mov     dword ptr [rax+88h], 8
0x140028de4  mov     rdx, rdi; unsigned __int16 *
0x140028de7  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140028dee  mov     rcx, [rcx+340h]; this
0x140028df5  cmp     [rbp+1E0h+arg_10], r14d
0x140028dfc  jz      short loc_140028E36
0x140028dfe  call    ?put_ExpertName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ExpertName(ushort *)
0x140028e03  mov     r14, [rsp+2E0h+var_2A0]
0x140028e08  mov     rdx, r14; unsigned __int16 *
0x140028e0b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140028e12  mov     rcx, [rcx+340h]; this
0x140028e19  call    ?put_ComputerName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ComputerName(ushort *)
0x140028e1e  mov     rdx, r15; unsigned __int16 *
0x140028e21  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140028e28  mov     rcx, [rcx+340h]; this
0x140028e2f  call    ?put_PNRPAddress@CRATicket@@QEAAJPEAG@Z; CRATicket::put_PNRPAddress(ushort *)
0x140028e34  jmp     short loc_140028E6C
0x140028e36  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x140028e3b  mov     r14, [rsp+2E0h+var_2A0]
0x140028e40  mov     rdx, r14; unsigned __int16 *
0x140028e43  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140028e4a  mov     rcx, [rcx+340h]; this
0x140028e51  call    ?put_ComputerName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ComputerName(ushort *)
0x140028e56  mov     rdx, r12; unsigned __int16 *
0x140028e59  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140028e60  mov     rcx, [rcx+340h]; this
0x140028e67  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x140028e6c  test    rdi, rdi
0x140028e6f  jz      short loc_140028E80
0x140028e71  mov     rcx, rdi; bstrString
0x140028e74  call    cs:__imp_SysFreeString
0x140028e7b  nop     dword ptr [rax+rax+00h]
0x140028e80  test    r15, r15
0x140028e83  jz      short loc_140028E94
0x140028e85  mov     rcx, r15; bstrString
0x140028e88  call    cs:__imp_SysFreeString
0x140028e8f  nop     dword ptr [rax+rax+00h]
0x140028e94  test    r14, r14
0x140028e97  jz      short loc_140028EA9
0x140028e99  mov     rcx, r14; bstrString
0x140028e9c  call    cs:__imp_SysFreeString
0x140028ea3  nop     dword ptr [rax+rax+00h]
0x140028ea8  nop
0x140028ea9  lea     rcx, [rbp+1E0h+var_240]; this
0x140028ead  call    ?EmptyList@CRAInvitationHistoryManager@@AEAAXXZ; CRAInvitationHistoryManager::EmptyList(void)
0x140028eb2  nop
0x140028eb3  lea     rcx, [rsp+2E0h+bstrString+8]; this
0x140028eb8  call    ??1CRAInvitationHistoryItem@@QEAA@XZ; CRAInvitationHistoryItem::~CRAInvitationHistoryItem(void)
0x140028ebd  mov     eax, ebx
0x140028ebf  add     rsp, 2A8h
0x140028ec6  pop     r15
0x140028ec8  pop     r14
0x140028eca  pop     r13
0x140028ecc  pop     r12
0x140028ece  pop     rdi
0x140028ecf  pop     rsi
0x140028ed0  pop     rbx
0x140028ed1  pop     rbp
0x140028ed2  retn
```
