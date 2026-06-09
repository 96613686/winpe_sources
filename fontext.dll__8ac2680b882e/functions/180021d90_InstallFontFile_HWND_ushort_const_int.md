# InstallFontFile(HWND__ *,ushort const *,int)

- ea: `0x180021d90`
- end: `0x180021f8d`
- name: `?InstallFontFile@@YAJPEAUHWND__@@PEBGH@Z`
- size: `509`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x180006624`
- `0x180012768`
- `0x18001c0d0`
- `0x18001cc60`
- `0x18001cfe8`
- `0x18001d074`
- `0x180021d4c`
- `0x180021d90`
- `0x1800237a0`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180021e42`
- `SHLWAPI!PathFindFileNameW` at `0x180021e42`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180021e0a`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180021e0a`
- `USER32!GetDesktopWindow` at `0x180021ddb`
- `USER32!GetDesktopWindow` at `0x180021ddb`

## pseudocode

```c
__int64 __fastcall InstallFontFile(HWND a1, const unsigned __int16 *a2, int a3)
{
  HWND DesktopWindow; // rsi
  int v7; // edi
  const unsigned __int16 *FileNameW; // rax
  unsigned __int64 v9; // rdx
  struct IEnumFontNames *v10; // rax
  struct IEnumFontNames *v11; // rbx
  CPathEnum_FileList *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-B8h]
  void **v16; // [rsp+58h] [rbp-A8h] BYREF
  __m128i v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  __int64 v19; // [rsp+78h] [rbp-88h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+88h] [rbp-78h]
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF

  DesktopWindow = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( !a1 )
    DesktopWindow = GetDesktopWindow();
  memset_0(pszPath, 0, 0x208u);
  StringCchCopyW(pszPath, 0x104u, a2);
  PathRemoveFileSpecW(pszPath);
  v14 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v7 = CDblNulStr::AddString((CDblNulStr *)&v14, pszPath);
  if ( v7 >= 0 )
  {
    FileNameW = PathFindFileNameW(a2);
    v7 = CDblNulStr::AddString((CDblNulStr *)&v14, FileNameW);
    if ( v7 >= 0 )
    {
      v10 = (struct IEnumFontNames *)DirectUI::HAllocAndZero((DirectUI *)0x240, v9);
      v11 = v10;
      if ( v10 )
      {
        *((_DWORD *)v10 + 2) = 1;
        *(_QWORD *)v10 = &CPathEnum_FileList::`vftable';
        v12 = v10;
        *((_QWORD *)v10 + 67) = 0;
        *((_QWORD *)v10 + 69) = &v14;
        v13 = v14;
        *((_QWORD *)v11 + 70) = v14;
        *((_QWORD *)v11 + 71) = v13;
        CPathEnum_FileList::Reset(v12);
      }
      else
      {
        v11 = 0;
      }
      if ( v11 )
      {
        v16 = &CFontManager::`vftable';
        v17 = _mm_load_si128((const __m128i *)&_xmm);
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        _InterlockedIncrement(&g_cRefCount);
        v7 = CFontManager::Initialize((CFontManager *)&v16);
        if ( v7 >= 0 )
          v7 = CFontManager::InstallFontsInternal((CFontManager *)&v16, DesktopWindow, v11, a3, 0, 0, 0);
        (*(void (__fastcall **)(struct IEnumFontNames *))(*(_QWORD *)v11 + 16LL))(v11);
        CFontManager::~CFontManager((CFontManager *)&v16);
      }
    }
  }
  CDblNulStr::~CDblNulStr((CDblNulStr *)&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021d90  mov     [rsp-8+arg_10], rbx
0x180021d95  mov     [rsp-8+arg_18], rsi
0x180021d9a  push    rbp
0x180021d9b  push    rdi
0x180021d9c  push    r14
0x180021d9e  lea     rbp, [rsp-1B0h]
0x180021da6  sub     rsp, 2B0h
0x180021dad  mov     rax, cs:__security_cookie
0x180021db4  xor     rax, rsp
0x180021db7  mov     [rbp+1C0h+var_20], rax
0x180021dbe  mov     r14d, r8d
0x180021dc1  mov     rbx, rdx
0x180021dc4  mov     rsi, rcx
0x180021dc7  test    rdx, rdx
0x180021dca  jnz     short loc_180021DD6
0x180021dcc  mov     eax, 80070057h
0x180021dd1  jmp     loc_180021F66
0x180021dd6  test    rcx, rcx
0x180021dd9  jnz     short loc_180021DE4
0x180021ddb  call    cs:__imp_GetDesktopWindow
0x180021de1  mov     rsi, rax
0x180021de4  xor     edx, edx; Val
0x180021de6  lea     rcx, [rbp+1C0h+pszPath]; void *
0x180021dea  mov     r8d, 208h; Size
0x180021df0  call    memset_0
0x180021df5  mov     r8, rbx; unsigned __int16 *
0x180021df8  lea     rcx, [rbp+1C0h+pszPath]; unsigned __int16 *
0x180021dfc  mov     edx, 104h; unsigned __int64
0x180021e01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021e06  lea     rcx, [rbp+1C0h+pszPath]; pszPath
0x180021e0a  call    cs:__imp_PathRemoveFileSpecW
0x180021e10  movdqa  xmm0, cs:__xmm@00000000000001040000000000000000
0x180021e18  lea     rdx, [rbp+1C0h+pszPath]; unsigned __int16 *
0x180021e1c  lea     rcx, [rsp+2C0h+var_280]; this
0x180021e21  mov     [rsp+2C0h+var_280], 0
0x180021e2a  movdqu  [rsp+2C0h+var_278], xmm0
0x180021e30  call    ?AddString@CDblNulStr@@QEAAJPEBG@Z; CDblNulStr::AddString(ushort const *)
0x180021e35  mov     edi, eax
0x180021e37  test    eax, eax
0x180021e39  js      loc_180021F5A
0x180021e3f  mov     rcx, rbx; pszPath
0x180021e42  call    cs:__imp_PathFindFileNameW
0x180021e48  mov     rdx, rax; unsigned __int16 *
0x180021e4b  lea     rcx, [rsp+2C0h+var_280]; this
0x180021e50  call    ?AddString@CDblNulStr@@QEAAJPEBG@Z; CDblNulStr::AddString(ushort const *)
0x180021e55  mov     edi, eax
0x180021e57  test    eax, eax
0x180021e59  js      loc_180021F5A
0x180021e5f  mov     ecx, 240h; this
0x180021e64  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180021e69  mov     rbx, rax
0x180021e6c  test    rax, rax
0x180021e6f  jz      short loc_180021EB6
0x180021e71  mov     dword ptr [rbx+8], 1
0x180021e78  lea     rax, ??_7CPathEnum_FileList@@6B@; const CPathEnum_FileList::`vftable'
0x180021e7f  mov     [rbx], rax
0x180021e82  mov     rcx, rbx; this
0x180021e85  mov     qword ptr [rbx+218h], 0
0x180021e90  lea     rax, [rsp+2C0h+var_280]
0x180021e95  mov     [rbx+228h], rax
0x180021e9c  mov     rax, [rsp+2C0h+var_280]
0x180021ea1  mov     [rbx+230h], rax
0x180021ea8  mov     [rbx+238h], rax
0x180021eaf  call    ?Reset@CPathEnum_FileList@@UEAAJXZ; CPathEnum_FileList::Reset(void)
0x180021eb4  jmp     short loc_180021EB8
0x180021eb6  xor     ebx, ebx
0x180021eb8  test    rbx, rbx
0x180021ebb  jz      loc_180021F5A
0x180021ec1  movdqa  xmm0, cs:__xmm@00000000000000000000000000000001
0x180021ec9  lea     rax, ??_7CFontManager@@6B@; const CFontManager::`vftable'
0x180021ed0  mov     [rsp+2C0h+var_268], rax
0x180021ed5  movdqu  [rsp+2C0h+var_260], xmm0
0x180021edb  mov     [rsp+2C0h+var_250], 0
0x180021ee4  mov     [rsp+2C0h+var_248], 0
0x180021eed  mov     [rbp+1C0h+var_240], 0
0x180021ef5  mov     [rbp+1C0h+var_238], 0
0x180021efc  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x180021f03  lea     rcx, [rsp+2C0h+var_268]; this
0x180021f08  call    ?Initialize@CFontManager@@QEAAJXZ; CFontManager::Initialize(void)
0x180021f0d  mov     edi, eax
0x180021f0f  test    eax, eax
0x180021f11  js      short loc_180021F41
0x180021f13  mov     [rsp+2C0h+var_290], 0; struct IFontManagerEvents *
0x180021f1c  lea     rcx, [rsp+2C0h+var_268]; this
0x180021f21  mov     [rsp+2C0h+var_298], 0; int
0x180021f29  mov     r9d, r14d; int
0x180021f2c  mov     r8, rbx; struct IEnumFontNames *
0x180021f2f  mov     [rsp+2C0h+var_2A0], 0; int
0x180021f37  mov     rdx, rsi; HWND
0x180021f3a  call    ?InstallFontsInternal@CFontManager@@QEAAJPEAUHWND__@@PEAUIEnumFontNames@@HHHPEAUIFontManagerEvents@@@Z; CFontManager::InstallFontsInternal(HWND__ *,IEnumFontNames *,int,int,int,IFontManagerEvents *)
0x180021f3f  mov     edi, eax
0x180021f41  mov     rax, [rbx]
0x180021f44  mov     rcx, rbx
0x180021f47  mov     rax, [rax+10h]
0x180021f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f50  lea     rcx, [rsp+2C0h+var_268]; this
0x180021f55  call    ??1CFontManager@@UEAA@XZ; CFontManager::~CFontManager(void)
0x180021f5a  lea     rcx, [rsp+2C0h+var_280]; this
0x180021f5f  call    ??1CDblNulStr@@QEAA@XZ; CDblNulStr::~CDblNulStr(void)
0x180021f64  mov     eax, edi
0x180021f66  mov     rcx, [rbp+1C0h+var_20]
0x180021f6d  xor     rcx, rsp; StackCookie
0x180021f70  call    __security_check_cookie
0x180021f75  lea     r11, [rsp+2C0h+var_10]
0x180021f7d  mov     rbx, [r11+30h]
0x180021f81  mov     rsi, [r11+38h]
0x180021f85  mov     rsp, r11
0x180021f88  pop     r14
0x180021f8a  pop     rdi
0x180021f8b  pop     rbp
0x180021f8c  retn
```
