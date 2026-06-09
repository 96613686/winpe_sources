# CMapiStore::GetOnlineStatus(int *)

- ea: `0x18002cfe0`
- end: `0x18002d14e`
- name: `?GetOnlineStatus@CMapiStore@@AEAAJPEAH@Z`
- size: `366`
- prototype: `__int64 __fastcall(CMapiStore *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002b2e0`

## callees

- `0x180005210`
- `0x18002cfe0`
- `0x18002d154`
- `0x18002d33c`
- `0x18002d37c`
- `0x18002d514`
- `0x18003d010`

## string_xrefs

- `0x18002d0a0`: `Checking OST status with HrOpenOfflineObj: Offline`
- `0x18002d087`: `Checking OST status with HrOpenOfflineObj: Online`
- `0x18002d0c7`: `Checking OST status with HrOpenOfflineObj failed`
- `0x18002d0b4`: `Checking OST status with HrOpenOfflineObj: No result returned`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiStore::GetOnlineStatus(CMapiStore *this, int *a2)
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(_QWORD, _QWORD, GUID *, _QWORD, __int64 *); // rax
  int v6; // ebp
  int v7; // ebx
  int v8; // eax
  int RootFolderorIPMSubTree; // eax
  struct IMAPIFolder *v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  if ( *((_QWORD *)this + 6) && *((_DWORD *)this + 28) )
  {
    v4 = *((_QWORD *)this + 78);
    if ( !v4 )
      goto LABEL_17;
    v5 = *(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD, __int64 *))(v4 + 248);
    if ( v5 )
    {
      v6 = 0;
      v12 = 0;
      v7 = v5(0, *((_QWORD *)this + 83), &GUID_GlobalState, 0, &v12);
      if ( v7 < 0
        || (LODWORD(v11) = 0,
            v7 = (*(__int64 (__fastcall **)(__int64, struct IMAPIFolder **))(*(_QWORD *)v12 + 40LL))(v12, &v11),
            v7 < 0) )
      {
        CLogger::Info(v7, L"Checking OST status with HrOpenOfflineObj failed");
      }
      else
      {
        v8 = (unsigned __int8)v11 & 3;
        if ( v8 == 2 )
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: Online");
          *a2 = 1;
        }
        else if ( v8 == 1 )
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: Offline");
          *a2 = 0;
        }
        else
        {
          CLogger::Info(L"Checking OST status with HrOpenOfflineObj: No result returned");
          v6 = 1;
        }
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v12);
    }
    else
    {
      v7 = 0;
      v6 = 1;
    }
    if ( v7 >= 0 && v6 )
    {
LABEL_17:
      v11 = 0;
      RootFolderorIPMSubTree = CMapiStore::GetRootFolderorIPMSubTree(this, &v11, 0);
      v7 = RootFolderorIPMSubTree;
      if ( RootFolderorIPMSubTree < 0 )
        CLogger::Info(RootFolderorIPMSubTree, L"Checking OST status with ICS failed");
      else
        *a2 = CMapiStore::IsICSSupported(this, v11);
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v11);
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cfe0  mov     r11, rsp
0x18002cfe3  mov     [r11+18h], rbx
0x18002cfe7  push    rbp
0x18002cfe8  push    rsi
0x18002cfe9  push    rdi
0x18002cfea  sub     rsp, 30h
0x18002cfee  mov     rsi, rdx
0x18002cff1  mov     rdi, rcx
0x18002cff4  mov     dword ptr [rdx], 0
0x18002cffa  cmp     qword ptr [rcx+30h], 0
0x18002cfff  jz      loc_18002D13A
0x18002d005  cmp     dword ptr [rcx+70h], 0
0x18002d009  jz      loc_18002D13A
0x18002d00f  mov     rax, [rcx+270h]
0x18002d016  test    rax, rax
0x18002d019  jz      loc_18002D0EF
0x18002d01f  mov     rax, [rax+0F8h]
0x18002d026  test    rax, rax
0x18002d029  jz      loc_18002D0E2
0x18002d02f  xor     ebp, ebp
0x18002d031  mov     [r11+10h], rbp
0x18002d035  lea     rcx, [r11+10h]
0x18002d039  mov     [r11-28h], rcx
0x18002d03d  xor     r9d, r9d
0x18002d040  lea     r8, GUID_GlobalState
0x18002d047  mov     rdx, [rdi+298h]
0x18002d04e  xor     ecx, ecx
0x18002d050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d055  mov     ebx, eax
0x18002d057  test    eax, eax
0x18002d059  js      short loc_18002D0C7
0x18002d05b  mov     dword ptr [rsp+48h+arg_0], ebp
0x18002d05f  mov     rcx, [rsp+48h+arg_8]
0x18002d064  mov     rax, [rcx]
0x18002d067  lea     rdx, [rsp+48h+arg_0]
0x18002d06c  mov     rax, [rax+28h]
0x18002d070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d075  mov     ebx, eax
0x18002d077  test    eax, eax
0x18002d079  js      short loc_18002D0C7
0x18002d07b  mov     eax, dword ptr [rsp+48h+arg_0]
0x18002d07f  and     eax, 3
0x18002d082  cmp     eax, 2
0x18002d085  jnz     short loc_18002D09B
0x18002d087  lea     rcx, aCheckingOstSta; "Checking OST status with HrOpenOfflineO"...
0x18002d08e  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002d093  mov     dword ptr [rsi], 1
0x18002d099  jmp     short loc_18002D0D6
0x18002d09b  cmp     eax, 1
0x18002d09e  jnz     short loc_18002D0B4
0x18002d0a0  lea     rcx, aCheckingOstSta_2; "Checking OST status with HrOpenOfflineO"...
0x18002d0a7  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002d0ac  mov     dword ptr [rsi], 0
0x18002d0b2  jmp     short loc_18002D0D6
0x18002d0b4  lea     rcx, aCheckingOstSta_0; "Checking OST status with HrOpenOfflineO"...
0x18002d0bb  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002d0c0  mov     ebp, 1
0x18002d0c5  jmp     short loc_18002D0D6
0x18002d0c7  lea     rdx, aCheckingOstSta_1; "Checking OST status with HrOpenOfflineO"...
0x18002d0ce  mov     ecx, ebx; int
0x18002d0d0  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002d0d5  nop
0x18002d0d6  lea     rcx, [rsp+48h+arg_8]
0x18002d0db  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002d0e0  jmp     short loc_18002D0E7
0x18002d0e2  xor     ebx, ebx
0x18002d0e4  lea     ebp, [rbx+1]
0x18002d0e7  test    ebx, ebx
0x18002d0e9  js      short loc_18002D13F
0x18002d0eb  test    ebp, ebp
0x18002d0ed  jz      short loc_18002D13F
0x18002d0ef  mov     [rsp+48h+arg_0], 0
0x18002d0f8  xor     r8d, r8d; int
0x18002d0fb  lea     rdx, [rsp+48h+arg_0]; struct IMAPIFolder **
0x18002d100  mov     rcx, rdi; this
0x18002d103  call    ?GetRootFolderorIPMSubTree@CMapiStore@@QEAAJPEAPEAUIMAPIFolder@@H@Z; CMapiStore::GetRootFolderorIPMSubTree(IMAPIFolder * *,int)
0x18002d108  mov     ebx, eax
0x18002d10a  test    eax, eax
0x18002d10c  js      short loc_18002D11F
0x18002d10e  mov     rdx, [rsp+48h+arg_0]; struct IMAPIFolder *
0x18002d113  mov     rcx, rdi; this
0x18002d116  call    ?IsICSSupported@CMapiStore@@AEAAHPEAUIMAPIFolder@@@Z; CMapiStore::IsICSSupported(IMAPIFolder *)
0x18002d11b  mov     [rsi], eax
0x18002d11d  jmp     short loc_18002D12E
0x18002d11f  lea     rdx, aCheckingOstSta_3; "Checking OST status with ICS failed"
0x18002d126  mov     ecx, eax; int
0x18002d128  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002d12d  nop
0x18002d12e  lea     rcx, [rsp+48h+arg_0]
0x18002d133  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002d138  jmp     short loc_18002D13F
0x18002d13a  mov     ebx, 80004005h
0x18002d13f  mov     eax, ebx
0x18002d141  mov     rbx, [rsp+48h+arg_10]
0x18002d146  add     rsp, 30h
0x18002d14a  pop     rdi
0x18002d14b  pop     rsi
0x18002d14c  pop     rbp
0x18002d14d  retn
```
