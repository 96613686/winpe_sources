# DetailsView::CreateToolBar(void)

- ea: `0x180009b34`
- end: `0x18000a073`
- name: `?CreateToolBar@DetailsView@@AEAAJXZ`
- size: `1343`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e918`

## callees

- `0x1800022b4`
- `0x180006eb4`
- `0x180006ec0`
- `0x180006fa0`
- `0x180007700`
- `0x180007b58`
- `0x1800092f4`
- `0x180009b34`
- `0x18000a8a8`
- `0x18001003c`
- `0x180019d74`
- `0x180019ee0`
- `0x180019f38`
- `0x18001b878`
- `0x18001b8bc`
- `0x18001b9dc`
- `0x18001ba34`
- `0x18001ba9c`
- `0x18001c0c4`
- `0x18001c134`
- `0x18001ca18`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ec9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009e2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009ec9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009d5d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009d5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f50`
- `KERNEL32!DeactivateActCtx` at `0x180009bc4`
- `KERNEL32!DeactivateActCtx` at `0x180009bc4`
- `KERNEL32!lstrlenW` at `0x180009f2c`
- `KERNEL32!lstrlenW` at `0x180009f2c`
- `USER32!CheckMenuItem` at `0x180009fe7`
- `USER32!CheckMenuItem` at `0x180009fe7`
- `USER32!GetMenu` at `0x180009fd6`
- `USER32!GetMenu` at `0x180009fd6`
- `USER32!SendMessageW` at `0x180009c05`
- `USER32!SendMessageW` at `0x180009c1e`
- `USER32!SendMessageW` at `0x180009c34`
- `USER32!SendMessageW` at `0x180009c4d`
- `USER32!SendMessageW` at `0x180009c62`
- `USER32!SendMessageW` at `0x180009ce7`
- `USER32!SendMessageW` at `0x180009cfd`
- `USER32!SendMessageW` at `0x180009f88`
- `USER32!SendMessageW` at `0x180009c05`
- `USER32!SendMessageW` at `0x180009c1e`
- `USER32!SendMessageW` at `0x180009c34`
- `USER32!SendMessageW` at `0x180009c4d`
- `USER32!SendMessageW` at `0x180009c62`
- `USER32!SendMessageW` at `0x180009ce7`
- `USER32!SendMessageW` at `0x180009cfd`
- `USER32!SendMessageW` at `0x180009f88`
- `USER32!ShowWindow` at `0x180009c6f`
- `USER32!ShowWindow` at `0x180009fbf`
- `USER32!ShowWindow` at `0x180009c6f`
- `USER32!ShowWindow` at `0x180009fbf`

## string_xrefs

- `0x180009cbc`: `COMBOBOX`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DetailsView::CreateToolBar(DetailsView *this)
{
  HIMAGELIST v2; // rax
  HWND Window; // rax
  LRESULT v4; // rax
  HKEY v5; // rdx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  int ValueBufferSize; // eax
  int v9; // r14d
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // r15
  const unsigned __int16 *v12; // rsi
  int Value; // r13d
  CString *v14; // rbx
  int v15; // ecx
  int v16; // r14d
  int v17; // r14d
  int v18; // esi
  unsigned int i; // ebx
  __int64 v20; // rax
  unsigned int v21; // esi
  UINT v22; // ebx
  HMENU Menu; // rax
  void **v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B8h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *p_CriticalSection; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+C8h] [rbp-38h]
  _BYTE v34[16]; // [rsp+D0h] [rbp-30h] BYREF
  void **v35; // [rsp+E0h] [rbp-20h]
  BOOL v36; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v37; // [rsp+F0h] [rbp-10h]
  _BYTE v38[88]; // [rsp+F8h] [rbp-8h] BYREF
  CString *pExceptionObject; // [rsp+160h] [rbp+60h] BYREF
  ULONG_PTR ulCookie; // [rsp+168h] [rbp+68h] BYREF

  ulCookie = 0;
  if ( (unsigned int)SHActivateContext(&ulCookie) )
  {
    *((_QWORD *)this + 15) = SHFusionCreateWindowEx(
                               0,
                               L"ToolbarWindow32",
                               0,
                               0x50810900u,
                               0,
                               0,
                               0,
                               0,
                               *((HWND *)this + 12),
                               (HMENU)0x1F4,
                               g_hInstDll,
                               0);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  if ( *((_QWORD *)this + 15) )
  {
    v2 = ImageList_Create(16, 16, 0x11u, 5, 0);
    *((_QWORD *)this + 19) = v2;
    SendMessageW(*((HWND *)this + 15), 0x430u, 0, (LPARAM)v2);
    SendMessageW(*((HWND *)this + 15), 0x432u, 0, -1);
    SendMessageW(*((HWND *)this + 15), 0x41Eu, 0x20u, 0);
    SendMessageW(*((HWND *)this + 15), 0x444u, 5u, (LPARAM)&lParam);
    SendMessageW(*((HWND *)this + 15), 0x421u, 0, 0);
    ShowWindow(*((HWND *)this + 15), 1);
    Window = SHFusionCreateWindowEx(
               0,
               L"COMBOBOX",
               &WindowName,
               0x40810242u,
               0,
               0,
               200,
               200,
               *((HWND *)this + 15),
               (HMENU)0x1F6,
               g_hInstDll,
               0);
    *((_QWORD *)this + 16) = Window;
    if ( Window )
    {
      v4 = SendMessageW(*((HWND *)this + 13), 0x31u, 0, 0);
      SendMessageW(*((HWND *)this + 16), 0x30u, v4, 0);
      DetailsView::Finder::ConnectToolbarCombo(*((_QWORD *)this + 23), *((HWND *)this + 16));
      RegKey::RegKey((RegKey *)v38, v5, v6);
      if ( RegKey::Open((RegKey *)v38, 0x20019u, 0) >= 0 )
      {
        v25 = &CArray<CString>::`vftable';
        v26 = 0;
        v27 = 8;
        v28 = 0;
        if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0) )
        {
          CSyncException::CSyncException(&pExceptionObject);
          throw (CSyncException *)&pExceptionObject;
        }
        ValueBufferSize = RegKey::GetValueBufferSize((RegKey *)v38, v7);
        v9 = ValueBufferSize;
        if ( ValueBufferSize > 0 )
        {
          v10 = (unsigned __int64)ValueBufferSize >> 1;
          v11 = (unsigned __int16 *)operator new(saturated_mul(v10 + 1, 2u));
          v36 = v11 != 0;
          v37 = v11;
          v35 = &array_autoptr<char>::`vftable';
          v12 = v11;
          memset_0(v11, 0, 2 * v10 + 2);
          Value = RegKey::GetValue((RegKey *)v38, L"FindMRU", 7u, (unsigned __int8 *)v11, v9);
          if ( Value >= 0 && v11 )
          {
            do
            {
              if ( !*v12 )
                break;
              v14 = CString::CString((CString *)v34, v12);
              pExceptionObject = v14;
              p_CriticalSection = &CriticalSection;
              EnterCriticalSection(&CriticalSection);
              v33 = 1;
              v15 = HIDWORD(v26);
              v16 = HIDWORD(v26) - 1;
              if ( HIDWORD(v26) && (v16 < 0 || v16 >= SHIDWORD(v26)) )
              {
                CMemoryException::CMemoryException(&pExceptionObject, 2);
                throw (CMemoryException *)&pExceptionObject;
              }
              v17 = HIDWORD(v26);
              if ( SHIDWORD(v26) >= (int)v26 )
              {
                CArray<CString>::SetSize(&v25, (unsigned int)(v27 + v26), HIDWORD(v26));
                v15 = HIDWORD(v26);
              }
              HIDWORD(v26) = v15 + 1;
              v30 = &CriticalSection;
              EnterCriticalSection(&CriticalSection);
              v31 = 1;
              if ( v17 < 0 || v17 >= (int)v26 )
              {
                CMemoryException::CMemoryException(&pExceptionObject, 2);
                throw (CMemoryException *)&pExceptionObject;
              }
              CString::operator=(v28 + 16LL * v17, v14);
              v31 = 0;
              LeaveCriticalSection(&CriticalSection);
              v33 = 0;
              LeaveCriticalSection(&CriticalSection);
              CString::~CString((CString *)v34);
              v12 += lstrlenW(v12) + 1;
            }
            while ( v12 );
          }
          if ( v11 )
            LocalFree(v11);
          if ( Value >= 0 )
          {
            v18 = HIDWORD(v26);
            for ( i = 0; (int)i < v18; ++i )
            {
              v20 = CArray<CString>::operator[](&v25, i);
              SendMessageW(*((HWND *)this + 16), 0x143u, 0, **(_QWORD **)(v20 + 8));
            }
          }
        }
        CArray<COwnerListFile>::~CArray<COwnerListFile>((__int64)&v25);
      }
      RegKey::~RegKey((RegKey *)v38);
    }
    v21 = 0;
    if ( (*((_BYTE *)this + 588) & 1) == 0 )
      ShowWindow(*((HWND *)this + 15), 0);
    v22 = 8 * (*((_WORD *)this + 294) & 1);
    Menu = GetMenu(*((HWND *)this + 12));
    CheckMenuItem(Menu, 0x9C43u, v22);
    DetailsView::EnableMenuItem_Undo(this, 0);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v21;
}

```

## disassembly

```asm
0x180009b34  mov     [rsp-8+arg_10], rbx
0x180009b39  push    rbp
0x180009b3a  push    rsi
0x180009b3b  push    rdi
0x180009b3c  push    r12
0x180009b3e  push    r13
0x180009b40  push    r14
0x180009b42  push    r15
0x180009b44  lea     rbp, [rsp-20h]
0x180009b49  sub     rsp, 120h
0x180009b50  mov     rdi, rcx
0x180009b53  xor     r14d, r14d
0x180009b56  mov     [rbp+50h+ulCookie], r14
0x180009b5a  lea     rcx, [rbp+50h+ulCookie]
0x180009b5e  call    SHActivateContext
0x180009b63  test    eax, eax
0x180009b65  jz      short loc_180009BCA
0x180009b67  mov     [rsp+150h+var_F8], r14; LPVOID
0x180009b6c  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x180009b73  mov     [rsp+150h+var_100], rax; HINSTANCE
0x180009b78  mov     [rsp+150h+var_108], 1F4h; HMENU
0x180009b81  mov     rax, [rdi+60h]
0x180009b85  mov     [rsp+150h+var_110], rax; HWND
0x180009b8a  mov     [rsp+150h+var_118], r14d; int
0x180009b8f  mov     [rsp+150h+var_120], r14d; int
0x180009b94  mov     [rsp+150h+var_128], r14d; int
0x180009b99  mov     [rsp+150h+cGrow], r14d; int
0x180009b9e  mov     r9d, 50810900h; dwStyle
0x180009ba4  xor     r8d, r8d; lpWindowName
0x180009ba7  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x180009bae  xor     ecx, ecx; dwExStyle
0x180009bb0  call    SHFusionCreateWindowEx
0x180009bb5  mov     [rdi+78h], rax
0x180009bb9  mov     rdx, [rbp+50h+ulCookie]; ulCookie
0x180009bbd  test    rdx, rdx
0x180009bc0  jz      short loc_180009BCA
0x180009bc2  xor     ecx, ecx; dwFlags
0x180009bc4  call    cs:__imp_DeactivateActCtx
0x180009bca  cmp     [rdi+78h], r14
0x180009bce  jz      loc_180009FF9
0x180009bd4  mov     [rsp+150h+cGrow], r14d; cGrow
0x180009bd9  mov     ebx, 5
0x180009bde  mov     r9d, ebx; cInitial
0x180009be1  lea     ecx, [rbx+0Bh]; cx
0x180009be4  lea     r8d, [rbx+0Ch]; flags
0x180009be8  mov     edx, ecx; cy
0x180009bea  call    ImageList_Create
0x180009bef  mov     [rdi+98h], rax
0x180009bf6  mov     r9, rax; lParam
0x180009bf9  xor     r8d, r8d; wParam
0x180009bfc  mov     edx, 430h; Msg
0x180009c01  mov     rcx, [rdi+78h]; hWnd
0x180009c05  call    cs:__imp_SendMessageW
0x180009c0b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009c0f  mov     r9, rsi; lParam
0x180009c12  xor     r8d, r8d; wParam
0x180009c15  mov     edx, 432h; Msg
0x180009c1a  mov     rcx, [rdi+78h]; hWnd
0x180009c1e  call    cs:__imp_SendMessageW
0x180009c24  xor     r9d, r9d; lParam
0x180009c27  mov     edx, 41Eh; Msg
0x180009c2c  lea     r8d, [rbx+1Bh]; wParam
0x180009c30  mov     rcx, [rdi+78h]; hWnd
0x180009c34  call    cs:__imp_SendMessageW
0x180009c3a  lea     r9, lParam; lParam
0x180009c41  mov     r8d, ebx; wParam
0x180009c44  mov     edx, 444h; Msg
0x180009c49  mov     rcx, [rdi+78h]; hWnd
0x180009c4d  call    cs:__imp_SendMessageW
0x180009c53  xor     r9d, r9d; lParam
0x180009c56  xor     r8d, r8d; wParam
0x180009c59  mov     edx, 421h; Msg
0x180009c5e  mov     rcx, [rdi+78h]; hWnd
0x180009c62  call    cs:__imp_SendMessageW
0x180009c68  lea     edx, [rbx-4]; nCmdShow
0x180009c6b  mov     rcx, [rdi+78h]; hWnd
0x180009c6f  call    cs:__imp_ShowWindow
0x180009c75  mov     [rsp+150h+var_F8], r14; LPVOID
0x180009c7a  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x180009c81  mov     [rsp+150h+var_100], rax; HINSTANCE
0x180009c86  mov     [rsp+150h+var_108], 1F6h; HMENU
0x180009c8f  mov     rax, [rdi+78h]
0x180009c93  mov     [rsp+150h+var_110], rax; HWND
0x180009c98  mov     eax, 0C8h
0x180009c9d  mov     [rsp+150h+var_118], eax; int
0x180009ca1  mov     [rsp+150h+var_120], eax; int
0x180009ca5  mov     [rsp+150h+var_128], r14d; int
0x180009caa  mov     [rsp+150h+cGrow], r14d; int
0x180009caf  mov     r9d, 40810242h; dwStyle
0x180009cb5  lea     r8, WindowName; lpWindowName
0x180009cbc  lea     rdx, aCombobox; "COMBOBOX"
0x180009cc3  xor     ecx, ecx; dwExStyle
0x180009cc5  call    SHFusionCreateWindowEx
0x180009cca  mov     [rdi+80h], rax
0x180009cd1  test    rax, rax
0x180009cd4  jz      loc_180009FAD
0x180009cda  xor     r9d, r9d; lParam
0x180009cdd  xor     r8d, r8d; wParam
0x180009ce0  lea     edx, [rbx+2Ch]; Msg
0x180009ce3  mov     rcx, [rdi+68h]; hWnd
0x180009ce7  call    cs:__imp_SendMessageW
0x180009ced  xor     r9d, r9d; lParam
0x180009cf0  mov     r8, rax; wParam
0x180009cf3  lea     edx, [rbx+2Bh]; Msg
0x180009cf6  mov     rcx, [rdi+80h]; hWnd
0x180009cfd  call    cs:__imp_SendMessageW
0x180009d03  mov     rdx, [rdi+80h]; hWnd
0x180009d0a  mov     rcx, [rdi+0B8h]; dwNewLong
0x180009d11  call    ?ConnectToolbarCombo@Finder@DetailsView@@QEAAXPEAUHWND__@@@Z; DetailsView::Finder::ConnectToolbarCombo(HWND__ *)
0x180009d16  lea     rcx, [rbp+50h+var_58]; this
0x180009d1a  call    ??0RegKey@@QEAA@PEAUHKEY__@@PEBG@Z; RegKey::RegKey(HKEY__ *,ushort const *)
0x180009d1f  nop
0x180009d20  xor     r8d, r8d; bool
0x180009d23  mov     edx, 20019h; unsigned int
0x180009d28  lea     rcx, [rbp+50h+var_58]; this
0x180009d2c  call    ?Open@RegKey@@QEBAJK_N@Z; RegKey::Open(ulong,bool)
0x180009d31  test    eax, eax
0x180009d33  js      loc_180009FA4
0x180009d39  lea     rax, ??_7?$CArray@VCString@@@@6B@; const CArray<CString>::`vftable'
0x180009d40  mov     [rsp+150h+var_F0], rax
0x180009d45  mov     [rsp+150h+var_E8], r14
0x180009d4a  mov     [rsp+150h+var_E0], 8
0x180009d52  mov     [rsp+150h+var_D8], r14
0x180009d57  xor     edx, edx; dwSpinCount
0x180009d59  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180009d5d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180009d63  test    eax, eax
0x180009d65  jz      loc_18000A059
0x180009d6b  lea     rcx, [rbp+50h+var_58]; this
0x180009d6f  call    ?GetValueBufferSize@RegKey@@QEBAHPEBG@Z; RegKey::GetValueBufferSize(ushort const *)
0x180009d74  movsxd  r14, eax
0x180009d77  test    eax, eax
0x180009d79  jle     loc_180009F96
0x180009d7f  mov     rbx, r14
0x180009d82  shr     rbx, 1
0x180009d85  lea     rcx, [rbx+1]
0x180009d89  lea     eax, [rsi+3]
0x180009d8c  mul     rcx
0x180009d8f  cmovb   rax, rsi
0x180009d93  mov     rcx, rax; uBytes
0x180009d96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d9b  mov     r15, rax
0x180009d9e  xor     r12d, r12d
0x180009da1  test    rax, rax
0x180009da4  setnz   r12b
0x180009da8  mov     [rbp+50h+var_68], r12d
0x180009dac  mov     [rbp+50h+var_60], rax
0x180009db0  lea     rax, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x180009db7  mov     [rbp+50h+var_70], rax
0x180009dbb  mov     rsi, r15
0x180009dbe  lea     r8, ds:2[rbx*2]; Size
0x180009dc6  xor     edx, edx; Val
0x180009dc8  mov     rcx, r15; void *
0x180009dcb  call    memset_0
0x180009dd0  mov     [rsp+150h+cGrow], r14d; int
0x180009dd5  mov     r9, r15; unsigned __int8 *
0x180009dd8  mov     r8d, 7; unsigned int
0x180009dde  lea     rdx, aFindmru; "FindMRU"
0x180009de5  lea     rcx, [rbp+50h+var_58]; this
0x180009de9  call    ?GetValue@RegKey@@AEBAJPEBGKPEAEH@Z; RegKey::GetValue(ushort const *,ulong,uchar *,int)
0x180009dee  mov     r13d, eax
0x180009df1  xor     r14d, r14d
0x180009df4  test    eax, eax
0x180009df6  js      loc_180009F43
0x180009dfc  test    r15, r15
0x180009dff  jz      loc_180009F43
0x180009e05  cmp     r14w, [rsi]
0x180009e09  jz      loc_180009F43
0x180009e0f  mov     rdx, rsi; unsigned __int16 *
0x180009e12  lea     rcx, [rbp+50h+var_80]; this
0x180009e16  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180009e1b  mov     rbx, rax
0x180009e1e  mov     [rbp+50h+pExceptionObject], rax
0x180009e22  lea     rax, [rbp+50h+CriticalSection]
0x180009e26  mov     [rbp+50h+var_90], rax
0x180009e2a  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180009e2e  call    cs:__imp_EnterCriticalSection
0x180009e34  mov     [rbp+50h+var_88], 1
0x180009e3b  mov     ecx, dword ptr [rsp+150h+var_E8+4]
0x180009e3f  lea     r14d, [rcx-1]
0x180009e43  test    ecx, ecx
0x180009e45  jnz     short loc_180009E53
0x180009e47  cmp     r14d, 0FFFFFFFFh
0x180009e4b  jnz     loc_18000A03A
0x180009e51  jmp     short loc_180009E65
0x180009e53  test    r14d, r14d
0x180009e56  js      loc_18000A03A
0x180009e5c  cmp     r14d, ecx
0x180009e5f  jge     loc_18000A03A
0x180009e65  mov     edx, dword ptr [rsp+150h+var_E8]
0x180009e69  inc     r14d
0x180009e6c  cmp     ecx, edx
0x180009e6e  jl      short loc_180009E83
0x180009e70  add     edx, [rsp+150h+var_E0]
0x180009e74  mov     r8d, r14d
0x180009e77  lea     rcx, [rsp+150h+var_F0]
0x180009e7c  call    ?SetSize@?$CArray@VCString@@@@QEAAXHH@Z; CArray<CString>::SetSize(int,int)
0x180009e81  jmp     short loc_180009EB3
0x180009e83  cmp     ecx, r14d
0x180009e86  jle     short loc_180009EB7
0x180009e88  lea     ebx, [rcx-1]
0x180009e8b  movsxd  rdx, ebx
0x180009e8e  shl     rdx, 4
0x180009e92  add     rdx, [rsp+150h+var_D8]
0x180009e97  movsxd  rcx, ecx
0x180009e9a  shl     rcx, 4
0x180009e9e  add     rcx, [rsp+150h+var_D8]
0x180009ea3  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180009ea8  mov     ecx, ebx
0x180009eaa  cmp     ebx, r14d
0x180009ead  jg      short loc_180009E88
0x180009eaf  mov     rbx, [rbp+50h+pExceptionObject]
0x180009eb3  mov     ecx, dword ptr [rsp+150h+var_E8+4]
0x180009eb7  inc     ecx
0x180009eb9  mov     dword ptr [rsp+150h+var_E8+4], ecx
0x180009ebd  lea     rax, [rbp+50h+CriticalSection]
0x180009ec1  mov     [rbp+50h+var_A0], rax
0x180009ec5  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180009ec9  call    cs:__imp_EnterCriticalSection
0x180009ecf  mov     [rbp+50h+var_98], 1
0x180009ed6  test    r14d, r14d
0x180009ed9  js      loc_18000A01B
0x180009edf  cmp     r14d, dword ptr [rsp+150h+var_E8]
0x180009ee4  jge     loc_18000A01B
0x180009eea  movsxd  rcx, r14d
0x180009eed  shl     rcx, 4
0x180009ef1  add     rcx, [rsp+150h+var_D8]
0x180009ef6  mov     rdx, rbx
0x180009ef9  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180009efe  nop
0x180009eff  xor     r14d, r14d
0x180009f02  mov     [rbp+50h+var_98], r14d
0x180009f06  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180009f0a  call    cs:__imp_LeaveCriticalSection
0x180009f10  nop
0x180009f11  mov     [rbp+50h+var_88], r14d
0x180009f15  lea     rcx, [rbp+50h+CriticalSection]; lpCriticalSection
0x180009f19  call    cs:__imp_LeaveCriticalSection
0x180009f1f  nop
0x180009f20  lea     rcx, [rbp+50h+var_80]; this
0x180009f24  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180009f29  mov     rcx, rsi; lpString
0x180009f2c  call    cs:__imp_lstrlenW
0x180009f32  inc     eax
0x180009f34  cdqe
0x180009f36  lea     rsi, [rsi+rax*2]
0x180009f3a  test    rsi, rsi
0x180009f3d  jnz     loc_180009E05
0x180009f43  test    r12d, r12d
0x180009f46  jz      short loc_180009F56
0x180009f48  test    r15, r15
0x180009f4b  jz      short loc_180009F56
0x180009f4d  mov     rcx, r15; hMem
0x180009f50  call    cs:__imp_LocalFree
0x180009f56  test    r13d, r13d
0x180009f59  js      short loc_180009F99
0x180009f5b  mov     esi, dword ptr [rsp+150h+var_E8+4]
0x180009f5f  mov     ebx, r14d
0x180009f62  test    esi, esi
0x180009f64  jle     short loc_180009F99
0x180009f66  mov     edx, ebx
0x180009f68  lea     rcx, [rsp+150h+var_F0]
0x180009f6d  call    ??A?$CArray@VCString@@@@QEAAAEAVCString@@H@Z; CArray<CString>::operator[](int)
0x180009f72  mov     r9, [rax+8]
0x180009f76  mov     r9, [r9]; lParam
0x180009f79  xor     r8d, r8d; wParam
0x180009f7c  mov     edx, 143h; Msg
0x180009f81  mov     rcx, [rdi+80h]; hWnd
0x180009f88  call    cs:__imp_SendMessageW
0x180009f8e  inc     ebx
0x180009f90  cmp     ebx, esi
0x180009f92  jl      short loc_180009F66
0x180009f94  jmp     short loc_180009F99
0x180009f96  xor     r14d, r14d
0x180009f99  lea     rcx, [rsp+150h+var_F0]
0x180009f9e  call    ??1?$CArray@VCOwnerListFile@@@@UEAA@XZ; CArray<COwnerListFile>::~CArray<COwnerListFile>(void)
0x180009fa3  nop
0x180009fa4  lea     rcx, [rbp+50h+var_58]; this
0x180009fa8  call    ??1RegKey@@UEAA@XZ; RegKey::~RegKey(void)
0x180009fad  mov     esi, r14d
0x180009fb0  test    byte ptr [rdi+24Ch], 1
0x180009fb7  jnz     short loc_180009FC5
0x180009fb9  xor     edx, edx; nCmdShow
0x180009fbb  mov     rcx, [rdi+78h]; hWnd
0x180009fbf  call    cs:__imp_ShowWindow
0x180009fc5  movzx   ebx, word ptr [rdi+24Ch]
0x180009fcc  and     ebx, 1
0x180009fcf  shl     ebx, 3
0x180009fd2  mov     rcx, [rdi+60h]; hWnd
0x180009fd6  call    cs:__imp_GetMenu
0x180009fdc  mov     r8d, ebx; uCheck
0x180009fdf  mov     edx, 9C43h; uIDCheckItem
0x180009fe4  mov     rcx, rax; hMenu
0x180009fe7  call    cs:__imp_CheckMenuItem
0x180009fed  xor     edx, edx; int
0x180009fef  mov     rcx, rdi; this
0x180009ff2  call    ?EnableMenuItem_Undo@DetailsView@@AEAAXH@Z; DetailsView::EnableMenuItem_Undo(int)
0x180009ff7  jmp     short loc_180009FFE
0x180009ff9  mov     esi, 80004005h
0x180009ffe  mov     eax, esi
  ... truncated ...
```
