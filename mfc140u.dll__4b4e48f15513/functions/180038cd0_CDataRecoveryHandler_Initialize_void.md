# CDataRecoveryHandler::Initialize(void)

- ea: `0x180038cd0`
- end: `0x180038f89`
- name: `?Initialize@CDataRecoveryHandler@@UEAAHXZ`
- size: `697`
- prototype: `int __fastcall(CDataRecoveryHandler *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000ddc0`
- `0x180038cd0`
- `0x1802bbce0`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180038d30`
- `KERNEL32!GetProcAddress` at `0x180038d30`
- `KERNEL32!GetModuleHandleW` at `0x180038d17`
- `KERNEL32!GetModuleHandleW` at `0x180038d17`
- `KERNEL32!DecodePointer` at `0x180038d4b`
- `KERNEL32!DecodePointer` at `0x180038d4b`
- `KERNEL32!EncodePointer` at `0x180038d3c`
- `KERNEL32!EncodePointer` at `0x180038d3c`
- `VCRUNTIME140!memmove` at `0x180038e77`
- `VCRUNTIME140!memmove` at `0x180038e77`
- `VCRUNTIME140!memset` at `0x180038ea6`
- `VCRUNTIME140!memset` at `0x180038ea6`
- `VCRUNTIME140!memcpy` at `0x180038e9c`
- `VCRUNTIME140!memcpy` at `0x180038e9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180038eb8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180038eb8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180038e57`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180038eac`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180038e57`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180038eac`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180038df3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180038df3`
- `USER32!SetTimer` at `0x180038f51`
- `USER32!SetTimer` at `0x180038f51`
- `ole32!CoTaskMemFree` at `0x180038f1e`
- `ole32!CoTaskMemFree` at `0x180038f1e`

## string_xrefs

- `0x180038d10`: `shell32.dll`
- `0x180038d26`: `SHGetKnownFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataRecoveryHandler::Initialize(CDataRecoveryHandler *this)
{
  unsigned int v2; // r12d
  HMODULE ModuleHandleW; // rax
  PVOID ProcAddress; // rbx
  wchar_t *v5; // rdi
  HINSTANCE__ *StringResourceHandle; // rax
  int v7; // ebx
  wchar_t *m_pszData; // rax
  unsigned __int64 v9; // r13
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rsi
  wchar_t *v12; // rdx
  size_t v13; // r8
  wchar_t *v14; // rdx
  UINT v15; // eax
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > v17; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *pszAutosavePath; // [rsp+78h] [rbp+48h] BYREF
  void (__fastcall *SetAutosavePath)(CDataRecoveryHandler *, const ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *); // [rsp+80h] [rbp+50h]

  v2 = 1;
  if ( (this->m_dwRestartManagerSupportFlags & 0xC) != 0 )
  {
    pszAutosavePath = 0;
    if ( Ptr )
    {
      ProcAddress = DecodePointer(Ptr);
    }
    else
    {
      ModuleHandleW = GetModuleHandleW(L"shell32.dll");
      if ( !ModuleHandleW )
        return 0;
      ProcAddress = GetProcAddress(ModuleHandleW, "SHGetKnownFolderPath");
      Ptr = EncodePointer(ProcAddress);
    }
    if ( ProcAddress )
    {
      if ( !((unsigned int (__fastcall *)(_GUID *, _QWORD, _QWORD, wchar_t **))ProcAddress)(
              &FOLDERID_LocalAppData,
              0,
              0,
              &pszAutosavePath) )
      {
        v5 = pszAutosavePath;
        if ( pszAutosavePath )
        {
          SetAutosavePath = this->SetAutosavePath;
          v17.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
          if ( (unsigned __int64)v5 < 0x10000 )
          {
            StringResourceHandle = AfxFindStringResourceHandle((unsigned __int16)v5);
            if ( StringResourceHandle )
              ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
                &v17,
                StringResourceHandle,
                (unsigned __int16)v5);
            goto LABEL_32;
          }
          v7 = wcslen(v5);
          if ( !v7 )
          {
            ATL::CSimpleStringT<wchar_t,1>::Empty(&v17);
            goto LABEL_32;
          }
          m_pszData = v17.m_pszData;
          v9 = *((unsigned int *)v17.m_pszData - 4);
          v10 = v5 - v17.m_pszData;
          if ( v7 < 0 )
LABEL_39:
            ATL::AtlThrowImpl(-2147024809);
          if ( ((1 - *((_DWORD *)v17.m_pszData - 2)) | (*((_DWORD *)v17.m_pszData - 3) - v7)) < 0 )
          {
            ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&v17, v7);
            m_pszData = v17.m_pszData;
          }
          v11 = 2LL * v7;
          if ( v10 > v9 )
          {
            v13 = 2LL * *((int *)m_pszData - 3);
            if ( !v11 )
              goto LABEL_29;
            if ( v13 >= v11 )
            {
              memcpy(m_pszData, v5, 2LL * v7);
              goto LABEL_28;
            }
            memset(m_pszData, 0, v13);
          }
          else
          {
            v12 = &m_pszData[v10];
            if ( !v11 )
              goto LABEL_29;
            if ( !v12 )
            {
              *_errno() = 22;
LABEL_27:
              _invalid_parameter_noinfo();
              goto LABEL_28;
            }
            if ( 2LL * *((int *)m_pszData - 3) >= v11 )
            {
              memmove(m_pszData, v12, 2LL * v7);
LABEL_28:
              m_pszData = v17.m_pszData;
LABEL_29:
              if ( v7 <= *((_DWORD *)m_pszData - 3) )
              {
                *((_DWORD *)m_pszData - 4) = v7;
                v17.m_pszData[v11 / 2] = 0;
LABEL_32:
                SetAutosavePath(this, &v17);
                v14 = v17.m_pszData - 12;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17.m_pszData - 2, 0xFFFFFFFF) <= 1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
                CoTaskMemFree(pszAutosavePath);
                goto LABEL_35;
              }
              goto LABEL_39;
            }
          }
          *_errno() = 34;
          goto LABEL_27;
        }
      }
    }
    return 0;
  }
LABEL_35:
  if ( (this->m_dwRestartManagerSupportFlags & 8) != 0 )
  {
    v15 = this->GetAutosaveInterval(this);
    this->m_nTimerID = SetTimer(0, this->m_nTimerID, v15, AfxAutosaveTimerProc);
  }
  return v2;
}

```

## disassembly

```asm
0x180038cd0  mov     [rsp-38h+arg_18], rbx
0x180038cd5  push    rbp
0x180038cd6  push    rsi
0x180038cd7  push    rdi
0x180038cd8  push    r12
0x180038cda  push    r13
0x180038cdc  push    r14
0x180038cde  push    r15
0x180038ce0  mov     rbp, rsp
0x180038ce3  sub     rsp, 30h
0x180038ce7  mov     r15, this
0x180038cea  mov     r12d, 1
0x180038cf0  test    byte ptr [this+168h], 0Ch
0x180038cf7  jz      loc_180038F24
0x180038cfd  xor     r14d, r14d
0x180038d00  mov     [rbp+pszAutosavePath], r14
0x180038d04  mov     this, cs:Ptr; Ptr
0x180038d0b  test    this, this
0x180038d0e  jnz     short loc_180038D4B
0x180038d10  lea     this, aShell32Dll; "shell32.dll"
0x180038d17  call    cs:__imp_GetModuleHandleW
0x180038d1d  test    rax, rax
0x180038d20  jz      loc_180038F79
0x180038d26  lea     rdx, ProcName; "SHGetKnownFolderPath"
0x180038d2d  mov     this, rax; hModule
0x180038d30  call    cs:__imp_GetProcAddress
0x180038d36  mov     rbx, rax
0x180038d39  mov     this, rax; Ptr
0x180038d3c  call    cs:__imp_EncodePointer
0x180038d42  mov     cs:Ptr, rax
0x180038d49  jmp     short loc_180038D54
0x180038d4b  call    cs:__imp_DecodePointer
0x180038d51  mov     rbx, rax
0x180038d54  test    rbx, rbx
0x180038d57  jz      loc_180038F79
0x180038d5d  lea     r9, [rbp+pszAutosavePath]
0x180038d61  xor     r8d, r8d
0x180038d64  xor     edx, edx
0x180038d66  lea     this, FOLDERID_LocalAppData
0x180038d6d  mov     rax, rbx
0x180038d70  call    cs:__guard_dispatch_icall_fptr
0x180038d76  test    eax, eax
0x180038d78  jnz     loc_180038F79
0x180038d7e  mov     rdi, [rbp+pszAutosavePath]
0x180038d82  test    rdi, rdi
0x180038d85  jz      loc_180038F79
0x180038d8b  mov     rax, [r15]
0x180038d8e  mov     rax, [rax+48h]
0x180038d92  mov     [rbp+arg_10], rax
0x180038d96  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x180038d9d  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180038da4  mov     rax, [rax+18h]
0x180038da8  call    cs:__guard_dispatch_icall_fptr
0x180038dae  add     rax, 18h
0x180038db2  mov     [rbp+arg_0.m_pszData], rax
0x180038db6  test    rdi, rdi
0x180038db9  jz      loc_180038ED9
0x180038dbf  cmp     rdi, 10000h
0x180038dc6  jnb     short loc_180038DF0
0x180038dc8  movzx   ebx, di
0x180038dcb  mov     ecx, ebx; nID
0x180038dcd  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x180038dd2  nop
0x180038dd3  test    rax, rax
0x180038dd6  jz      loc_180038EE3
0x180038ddc  mov     r8d, ebx; nID
0x180038ddf  mov     rdx, rax; hInstance
0x180038de2  lea     this, [rbp+arg_0]; this
0x180038de6  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x180038deb  jmp     loc_180038EE3
0x180038df0  mov     this, rdi; String
0x180038df3  call    cs:__imp_wcslen
0x180038df9  mov     rbx, rax
0x180038dfc  test    eax, eax
0x180038dfe  jz      loc_180038ED9
0x180038e04  mov     rax, [rbp+arg_0.m_pszData]
0x180038e08  mov     r13d, [rax-10h]
0x180038e0c  mov     r14, rdi
0x180038e0f  sub     r14, rax
0x180038e12  sar     r14, 1
0x180038e15  test    ebx, ebx
0x180038e17  js      loc_180038F7E
0x180038e1d  mov     edx, r12d
0x180038e20  sub     edx, [rax-8]
0x180038e23  mov     ecx, [rax-0Ch]
0x180038e26  sub     ecx, ebx
0x180038e28  or      ecx, edx
0x180038e2a  jge     short loc_180038E3B
0x180038e2c  mov     edx, ebx; nLength
0x180038e2e  lea     this, [rbp+arg_0]; this
0x180038e32  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x180038e37  mov     rax, [rbp+arg_0.m_pszData]
0x180038e3b  movsxd  rsi, ebx
0x180038e3e  add     rsi, rsi
0x180038e41  cmp     r14, r13
0x180038e44  ja      short loc_180038E7F
0x180038e46  lea     rdx, [rax+r14*2]; Src
0x180038e4a  xor     r14d, r14d
0x180038e4d  test    rsi, rsi
0x180038e50  jz      short loc_180038EC2
0x180038e52  test    rdx, rdx
0x180038e55  jnz     short loc_180038E65
0x180038e57  call    cs:__imp__errno
0x180038e5d  mov     dword ptr [rax], 16h
0x180038e63  jmp     short loc_180038EB8
0x180038e65  movsxd  this, dword ptr [rax-0Ch]
0x180038e69  add     this, this
0x180038e6c  cmp     this, rsi
0x180038e6f  jb      short loc_180038EAC
0x180038e71  mov     r8, rsi; Size
0x180038e74  mov     this, rax; void *
0x180038e77  call    cs:__imp_memmove
0x180038e7d  jmp     short loc_180038EBE
0x180038e7f  movsxd  r8, dword ptr [rax-0Ch]
0x180038e83  add     r8, r8; Size
0x180038e86  xor     r14d, r14d
0x180038e89  test    rsi, rsi
0x180038e8c  jz      short loc_180038EC2
0x180038e8e  mov     this, rax; void *
0x180038e91  cmp     r8, rsi
0x180038e94  jb      short loc_180038EA4
0x180038e96  mov     r8, rsi; Size
0x180038e99  mov     rdx, rdi; Src
0x180038e9c  call    cs:__imp_memcpy
0x180038ea2  jmp     short loc_180038EBE
0x180038ea4  xor     edx, edx; Val
0x180038ea6  call    cs:__imp_memset
0x180038eac  call    cs:__imp__errno
0x180038eb2  mov     dword ptr [rax], 22h ; '"'
0x180038eb8  call    cs:__imp__invalid_parameter_noinfo
0x180038ebe  mov     rax, [rbp+arg_0.m_pszData]
0x180038ec2  cmp     ebx, [rax-0Ch]
0x180038ec5  jg      loc_180038F7E
0x180038ecb  mov     [rax-10h], ebx
0x180038ece  mov     rax, [rbp+arg_0.m_pszData]
0x180038ed2  mov     [rsi+rax], r14w
0x180038ed7  jmp     short loc_180038EE3
0x180038ed9  lea     this, [rbp+arg_0]; this
0x180038edd  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180038ee2  nop
0x180038ee3  lea     rdx, [rbp+arg_0]
0x180038ee7  mov     this, r15
0x180038eea  mov     rax, [rbp+arg_10]
0x180038eee  call    cs:__guard_dispatch_icall_fptr
0x180038ef4  nop
0x180038ef5  mov     rdx, [rbp+arg_0.m_pszData]
0x180038ef9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180038efd  or      eax, 0FFFFFFFFh
0x180038f00  lock xadd [rdx+10h], eax
0x180038f05  sub     eax, 1
0x180038f08  jg      short loc_180038F1A
0x180038f0a  mov     this, [rdx]
0x180038f0d  mov     rax, [this]
0x180038f10  mov     rax, [rax+8]
0x180038f14  call    cs:__guard_dispatch_icall_fptr
0x180038f1a  mov     this, [rbp+pszAutosavePath]; pv
0x180038f1e  call    cs:__imp_CoTaskMemFree
0x180038f24  test    byte ptr [r15+168h], 8
0x180038f2c  jz      short loc_180038F5E
0x180038f2e  mov     rax, [r15]
0x180038f31  mov     this, r15
0x180038f34  mov     rax, [rax+30h]
0x180038f38  call    cs:__guard_dispatch_icall_fptr
0x180038f3e  lea     r9, ?AfxAutosaveTimerProc@@YAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x180038f45  mov     r8d, eax; uElapse
0x180038f48  mov     rdx, [r15+180h]; nIDEvent
0x180038f4f  xor     ecx, ecx; hWnd
0x180038f51  call    cs:__imp_SetTimer
0x180038f57  mov     [r15+180h], rax
0x180038f5e  mov     eax, r12d
0x180038f61  mov     rbx, [rsp+30h+arg_18]
0x180038f69  add     rsp, 30h
0x180038f6d  pop     r15
0x180038f6f  pop     r14
0x180038f71  pop     r13
0x180038f73  pop     r12
0x180038f75  pop     rdi
0x180038f76  pop     rsi
0x180038f77  pop     rbp
0x180038f78  retn
0x180038f79  mov     r12d, r14d
0x180038f7c  jmp     short loc_180038F5E
0x180038f7e  mov     ecx, 80070057h; hr
0x180038f83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
