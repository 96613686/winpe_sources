# UserPropSheet::UpdateSpaceUsed(HWND__ *,__int64,__int64,int)

- ea: `0x180018384`
- end: `0x1800184b8`
- name: `?UpdateSpaceUsed@UserPropSheet@@AEAAXPEAUHWND__@@_J1H@Z`
- size: `308`
- prototype: `void(UserPropSheet *__hidden this, HWND, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800170dc`
- `0x1800177fc`

## callees

- `0x180001510`
- `0x180018384`
- `0x180019d74`
- `0x180019ee0`
- `0x180019fb0`
- `0x18001a468`
- `0x18001a5f0`
- `0x18001a73c`
- `0x18001af90`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x180018417`
- `USER32!SetDlgItemTextW` at `0x180018488`
- `USER32!SetDlgItemTextW` at `0x180018417`
- `USER32!SetDlgItemTextW` at `0x180018488`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserPropSheet::UpdateSpaceUsed(UserPropSheet *this, HWND a2, __int64 a3, __int64 a4, int a5)
{
  unsigned __int16 *Buffer; // rdx
  __int64 v9; // rcx
  _BYTE v10[8]; // [rsp+30h] [rbp-81h] BYREF
  LPCWSTR *v11; // [rsp+38h] [rbp-79h]
  unsigned __int16 v12[80]; // [rsp+40h] [rbp-71h] BYREF

  XBytes::FormatByteCountForDisplay(a3, v12, 0x50u);
  CString::CString((CString *)v10, v12);
  if ( a5 == 1 && (unsigned __int64)(a4 + 1) > 1 )
    CString::Format((CString *)v10, g_hInstDll, 0x9E62u, v12, 100 * a3 / a4);
  SetDlgItemTextW(a2, 1023, *v11);
  CString::operator=(v10, v12);
  if ( a4 == -1 )
  {
    CString::Format((CString *)v10, g_hInstDll, 0x9E72u);
  }
  else
  {
    Buffer = CString::GetBuffer((CString *)v10, 80);
    v9 = a4 - a3;
    if ( a3 > a4 )
      v9 = 0;
    XBytes::FormatByteCountForDisplay(v9, Buffer, 0x50u);
    CString::ReleaseBuffer((CString *)v10);
  }
  SetDlgItemTextW(a2, 1025, *v11);
  CString::~CString((CString *)v10);
}

```

## disassembly

```asm
0x180018384  mov     [rsp-8+arg_0], rbx
0x180018389  push    rbp
0x18001838a  push    rsi
0x18001838b  push    rdi
0x18001838c  lea     rbp, [rsp-3Fh]
0x180018391  sub     rsp, 0F0h
0x180018398  mov     rax, cs:__security_cookie
0x18001839f  xor     rax, rsp
0x1800183a2  mov     [rbp+4Fh+var_20], rax
0x1800183a6  mov     rbx, r9
0x1800183a9  mov     rsi, r8
0x1800183ac  mov     rdi, rdx
0x1800183af  mov     r8d, 50h ; 'P'; unsigned int
0x1800183b5  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x1800183b9  mov     rcx, rsi; __int64
0x1800183bc  call    ?FormatByteCountForDisplay@XBytes@@SAX_JPEAGI@Z; XBytes::FormatByteCountForDisplay(__int64,ushort *,uint)
0x1800183c1  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int16 *
0x1800183c5  lea     rcx, [rsp+100h+var_D0]; this
0x1800183ca  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800183cf  nop
0x1800183d0  cmp     [rbp+4Fh+arg_20], 1
0x1800183d4  jnz     short loc_180018408
0x1800183d6  lea     rax, [rbx+1]
0x1800183da  cmp     rax, 1
0x1800183de  jbe     short loc_180018408
0x1800183e0  imul    rax, rsi, 64h ; 'd'
0x1800183e4  cqo
0x1800183e6  idiv    rbx
0x1800183e9  mov     [rsp+100h+var_E0], eax
0x1800183ed  lea     r9, [rbp+4Fh+var_C0]
0x1800183f1  mov     r8d, 9E62h; unsigned int
0x1800183f7  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800183fe  lea     rcx, [rsp+100h+var_D0]; this
0x180018403  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180018408  mov     r8, [rbp+4Fh+var_C8]
0x18001840c  mov     r8, [r8]; lpString
0x18001840f  mov     edx, 3FFh; nIDDlgItem
0x180018414  mov     rcx, rdi; hDlg
0x180018417  call    cs:__imp_SetDlgItemTextW
0x18001841d  lea     rdx, [rbp+4Fh+var_C0]
0x180018421  lea     rcx, [rsp+100h+var_D0]
0x180018426  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x18001842b  lea     rcx, [rsp+100h+var_D0]; this
0x180018430  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180018434  jz      short loc_180018467
0x180018436  mov     edx, 50h ; 'P'; int
0x18001843b  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x180018440  mov     rdx, rax; unsigned __int16 *
0x180018443  mov     rcx, rbx
0x180018446  sub     rcx, rsi
0x180018449  xor     eax, eax
0x18001844b  cmp     rsi, rbx
0x18001844e  cmovg   rcx, rax; __int64
0x180018452  lea     r8d, [rax+50h]; unsigned int
0x180018456  call    ?FormatByteCountForDisplay@XBytes@@SAX_JPEAGI@Z; XBytes::FormatByteCountForDisplay(__int64,ushort *,uint)
0x18001845b  lea     rcx, [rsp+100h+var_D0]; this
0x180018460  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x180018465  jmp     short loc_180018479
0x180018467  mov     r8d, 9E72h; unsigned int
0x18001846d  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180018474  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180018479  mov     r8, [rbp+4Fh+var_C8]
0x18001847d  mov     r8, [r8]; lpString
0x180018480  mov     edx, 401h; nIDDlgItem
0x180018485  mov     rcx, rdi; hDlg
0x180018488  call    cs:__imp_SetDlgItemTextW
0x18001848e  nop
0x18001848f  lea     rcx, [rsp+100h+var_D0]; this
0x180018494  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180018499  mov     rcx, [rbp+4Fh+var_20]
0x18001849d  xor     rcx, rsp; StackCookie
0x1800184a0  call    __security_check_cookie
0x1800184a5  mov     rbx, [rsp+100h+arg_0]
0x1800184ad  add     rsp, 0F0h
0x1800184b4  pop     rdi
0x1800184b5  pop     rsi
0x1800184b6  pop     rbp
0x1800184b7  retn
```
