# CNDFAPI::Show(HWND__ *,ushort const *,ushort const *,long)

- ea: `0x180015590`
- end: `0x180015701`
- name: `?Show@CNDFAPI@@UEAAJPEAUHWND__@@PEBG1J@Z`
- size: `369`
- prototype: `int(CNDFAPI *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180003d50`
- `0x180010320`
- `0x180010460`
- `0x180010664`
- `0x180015590`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800156a9`
- `KERNEL32!GetLastError` at `0x1800156a9`
- `USER32!LoadStringW` at `0x180015682`
- `USER32!LoadStringW` at `0x180015682`
- `SHELL32!__imp_IsNetDrive` at `0x1800155ed`
- `SHELL32!__imp_IsNetDrive` at `0x1800155ed`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800155e5`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800155e5`
- `MPR!WNetGetUniversalNameW` at `0x180015611`
- `MPR!WNetGetUniversalNameW` at `0x180015611`

## pseudocode

```c
int __fastcall CNDFAPI::Show(CNDFAPI *this, HWND a2, const unsigned __int16 *a3, const unsigned __int16 *a4, int a5)
{
  const WCHAR *v5; // rbx
  int result; // eax
  int DriveNumberW; // eax
  HINSTANCE v9; // rcx
  unsigned __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  HINSTANCE v13; // rdx
  bool v14; // sf
  const unsigned __int16 *v15; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v16; // [rsp+28h] [rbp-D8h]
  DWORD BufferSize[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD Buffer[66]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v19[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v20[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v21[264]; // [rsp+680h] [rbp+580h] BYREF

  v5 = a4;
  if ( !a4 )
    return -2147024809;
  memset_0(Buffer, 0, sizeof(Buffer));
  DriveNumberW = PathGetDriveNumberW(v5);
  if ( IsNetDrive(DriveNumberW) )
  {
    BufferSize[0] = 528;
    if ( !WNetGetUniversalNameW(v5, 1u, Buffer, BufferSize) )
      v5 = (const WCHAR *)Buffer[0];
  }
  if ( a5 == -2147024891 )
    return SMBAccessDeniedMessageBox(v9, a2, v5);
  result = FormatDiagnoseErrMessage(v9, a5, v21, v10);
  if ( result >= 0 )
  {
    v11 = 520;
    v12 = v19;
    do
    {
      *(_BYTE *)v12 = 0;
      v12 = (unsigned __int16 *)((char *)v12 + 1);
      --v11;
    }
    while ( v11 );
    if ( LoadStringW(g_hinstDll, 0x9C92u, v20, 260) )
    {
      result = StringCchPrintfW(v19, 0x103u, v20, v5);
    }
    else
    {
      result = GetLastError();
      v14 = result < 0;
      if ( result <= 0 )
        goto LABEL_16;
      result = (unsigned __int16)result | 0x80070000;
    }
    v14 = result < 0;
LABEL_16:
    if ( !v14 )
      return ShellDiagnoseMessageBox(v5, v13, a2, v19, v15, v16, v21);
  }
  return result;
}

```

## disassembly

```asm
0x180015590  mov     [rsp-8+arg_0], rbx
0x180015595  mov     [rsp-8+arg_10], rdi
0x18001559a  push    rbp
0x18001559b  lea     rbp, [rsp-7A0h]
0x1800155a3  sub     rsp, 8A0h
0x1800155aa  mov     rax, cs:__security_cookie
0x1800155b1  xor     rax, rsp
0x1800155b4  mov     [rbp+7A0h+var_10], rax
0x1800155bb  mov     rbx, r9
0x1800155be  mov     rdi, rdx
0x1800155c1  test    r9, r9
0x1800155c4  jnz     short loc_1800155D0
0x1800155c6  mov     eax, 80070057h
0x1800155cb  jmp     loc_1800156DD
0x1800155d0  xor     edx, edx; Val
0x1800155d2  lea     rcx, [rsp+8A0h+Buffer]; void *
0x1800155d7  mov     r8d, 210h; Size
0x1800155dd  call    memset_0
0x1800155e2  mov     rcx, rbx; pszPath
0x1800155e5  call    cs:__imp_PathGetDriveNumberW
0x1800155eb  mov     ecx, eax; iDrive
0x1800155ed  call    cs:__imp_IsNetDrive
0x1800155f3  test    eax, eax
0x1800155f5  jz      short loc_18001561F
0x1800155f7  lea     r9, [rsp+8A0h+BufferSize]; lpBufferSize
0x1800155fc  mov     [rsp+8A0h+BufferSize], 210h
0x180015604  lea     r8, [rsp+8A0h+Buffer]; lpBuffer
0x180015609  mov     edx, 1; dwInfoLevel
0x18001560e  mov     rcx, rbx; lpLocalPath
0x180015611  call    cs:__imp_WNetGetUniversalNameW
0x180015617  test    eax, eax
0x180015619  cmovz   rbx, [rsp+8A0h+Buffer]
0x18001561f  mov     edx, [rbp+7A0h+arg_20]; int
0x180015625  cmp     edx, 80070005h
0x18001562b  jnz     short loc_18001563D
0x18001562d  mov     r8, rbx; unsigned __int16 *
0x180015630  mov     rdx, rdi; HWND
0x180015633  call    ?SMBAccessDeniedMessageBox@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBG@Z; SMBAccessDeniedMessageBox(HINSTANCE__ *,HWND__ *,ushort const *)
0x180015638  jmp     loc_1800156DD
0x18001563d  lea     r8, [rbp+7A0h+var_220]; unsigned __int16 *
0x180015644  call    ?FormatDiagnoseErrMessage@@YAJPEAUHINSTANCE__@@JPEAG_K@Z; FormatDiagnoseErrMessage(HINSTANCE__ *,long,ushort *,unsigned __int64)
0x180015649  test    eax, eax
0x18001564b  js      loc_1800156DD
0x180015651  mov     ecx, 208h
0x180015656  lea     rax, [rbp+7A0h+var_640]
0x18001565d  mov     byte ptr [rax], 0
0x180015660  inc     rax
0x180015663  sub     rcx, 1
0x180015667  jnz     short loc_18001565D
0x180015669  mov     rcx, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180015670  lea     r8, [rbp+7A0h+var_430]; lpBuffer
0x180015677  mov     r9d, 104h; cchBufferMax
0x18001567d  mov     edx, 9C92h; uID
0x180015682  call    cs:__imp_LoadStringW
0x180015688  test    eax, eax
0x18001568a  jz      short loc_1800156A9
0x18001568c  mov     r9, rbx
0x18001568f  lea     r8, [rbp+7A0h+var_430]; unsigned __int16 *
0x180015696  mov     edx, 103h; unsigned __int64
0x18001569b  lea     rcx, [rbp+7A0h+var_640]; unsigned __int16 *
0x1800156a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800156a7  jmp     short loc_1800156BB
0x1800156a9  call    cs:__imp_GetLastError
0x1800156af  test    eax, eax
0x1800156b1  jle     short loc_1800156BD
0x1800156b3  movzx   eax, ax
0x1800156b6  or      eax, 80070000h
0x1800156bb  test    eax, eax
0x1800156bd  js      short loc_1800156DD
0x1800156bf  lea     rax, [rbp+7A0h+var_220]
0x1800156c6  mov     r8, rdi; HWND
0x1800156c9  lea     r9, [rbp+7A0h+var_640]; unsigned __int16 *
0x1800156d0  mov     [rsp+8A0h+var_870], rax; unsigned __int16 *
0x1800156d5  mov     rcx, rbx; UNCPath
0x1800156d8  call    ?ShellDiagnoseMessageBox@@YAJPEBGPEAUHINSTANCE__@@PEAUHWND__@@0000@Z; ShellDiagnoseMessageBox(ushort const *,HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800156dd  mov     rcx, [rbp+7A0h+var_10]
0x1800156e4  xor     rcx, rsp; StackCookie
0x1800156e7  call    __security_check_cookie
0x1800156ec  lea     r11, [rsp+8A0h+var_s0]
0x1800156f4  mov     rbx, [r11+10h]
0x1800156f8  mov     rdi, [r11+20h]
0x1800156fc  mov     rsp, r11
0x1800156ff  pop     rbp
0x180015700  retn
```
