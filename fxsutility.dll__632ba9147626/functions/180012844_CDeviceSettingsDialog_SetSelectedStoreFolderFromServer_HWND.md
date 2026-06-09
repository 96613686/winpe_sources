# CDeviceSettingsDialog::SetSelectedStoreFolderFromServer(HWND__ *)

- ea: `0x180012844`
- end: `0x180012970`
- name: `?SetSelectedStoreFolderFromServer@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z`
- size: `300`
- prototype: `unsigned int(CDeviceSettingsDialog *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180010bc8`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180006318`
- `0x180006594`
- `0x180012844`

## import_xrefs

- `FXSAPI!FaxGetExtensionDataW` at `0x1800128b8`
- `FXSAPI!FaxGetExtensionDataW` at `0x1800128b8`
- `FXSAPI!FaxFreeBuffer` at `0x18001295a`
- `FXSAPI!FaxFreeBuffer` at `0x18001295a`
- `KERNEL32!GetLastError` at `0x1800128c2`
- `KERNEL32!GetLastError` at `0x1800128c2`
- `USER32!SetDlgItemTextW` at `0x180012935`
- `USER32!SetDlgItemTextW` at `0x18001294a`
- `USER32!SetDlgItemTextW` at `0x180012935`
- `USER32!SetDlgItemTextW` at `0x18001294a`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsDialog::SetSelectedStoreFolderFromServer(CDeviceSettingsDialog *this, HWND a2)
{
  DWORD LastError; // eax
  DWORD v5; // ebx
  WCHAR *v7; // rcx
  __int64 v8; // rax
  const WCHAR *v9; // rax
  WCHAR *v10; // rbx
  int v11; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR lpString; // [rsp+60h] [rbp+18h] BYREF

  lpString = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  if ( (unsigned int)FaxGetExtensionDataW(
                       *((_QWORD *)this + 7),
                       *(unsigned int *)(*((_QWORD *)this + 6) + 4LL),
                       L"{92041a90-9af2-11d0-abf7-00c04fd91a4e}",
                       &lpString,
                       &v11) )
  {
    v7 = (WCHAR *)lpString;
    if ( lpString )
    {
      v8 = -1;
      do
        ++v8;
      while ( lpString[v8] );
      if ( v8 )
      {
        v9 = (const WCHAR *)ExpandEnvironmentString((unsigned __int16 *)lpString);
        v10 = (WCHAR *)v9;
        if ( v9 )
        {
          SetDlgItemTextW(a2, 4549, v9);
          pMemFree(v10);
        }
        else
        {
          SetDlgItemTextW(a2, 4549, lpString);
        }
        v7 = (WCHAR *)lpString;
      }
      if ( v7 )
        FaxFreeBuffer(v7);
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180012844  mov     [rsp+arg_8], rbx
0x180012849  push    rsi
0x18001284a  push    rdi
0x18001284b  push    r14
0x18001284d  sub     rsp, 30h
0x180012851  xor     esi, esi
0x180012853  mov     rdi, rdx
0x180012856  mov     [rsp+48h+lpString], rsi
0x18001285b  mov     rbx, rcx
0x18001285e  mov     [rsp+48h+arg_0], esi
0x180012862  mov     rcx, cs:WPP_GLOBAL_Control
0x180012869  lea     r14, WPP_GLOBAL_Control
0x180012870  cmp     rcx, r14
0x180012873  jz      short loc_180012897
0x180012875  test    dword ptr [rcx+1Ch], 100h
0x18001287c  jz      short loc_180012897
0x18001287e  cmp     byte ptr [rcx+19h], 5
0x180012882  jb      short loc_180012897
0x180012884  mov     rcx, [rcx+10h]
0x180012888  lea     edx, [rsi+2Ch]
0x18001288b  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012892  call    WPP_SF_
0x180012897  mov     rdx, [rbx+30h]
0x18001289b  lea     rax, [rsp+48h+arg_0]
0x1800128a0  mov     rcx, [rbx+38h]
0x1800128a4  lea     r9, [rsp+48h+lpString]
0x1800128a9  lea     r8, a92041a909af211; "{92041a90-9af2-11d0-abf7-00c04fd91a4e}"
0x1800128b0  mov     [rsp+48h+var_28], rax
0x1800128b5  mov     edx, [rdx+4]
0x1800128b8  call    cs:__imp_FaxGetExtensionDataW
0x1800128be  test    eax, eax
0x1800128c0  jnz     short loc_180012901
0x1800128c2  call    cs:__imp_GetLastError
0x1800128c8  mov     ebx, eax
0x1800128ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128d1  cmp     rcx, r14
0x1800128d4  jz      short loc_1800128FD
0x1800128d6  test    dword ptr [rcx+1Ch], 100h
0x1800128dd  jz      short loc_1800128FD
0x1800128df  cmp     byte ptr [rcx+19h], 3
0x1800128e3  jb      short loc_1800128FD
0x1800128e5  mov     rcx, [rcx+10h]
0x1800128e9  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800128f0  mov     edx, 2Dh ; '-'
0x1800128f5  mov     r9d, eax
0x1800128f8  call    WPP_SF_d
0x1800128fd  mov     eax, ebx
0x1800128ff  jmp     short loc_180012962
0x180012901  mov     rcx, [rsp+48h+lpString]; unsigned __int16 *
0x180012906  test    rcx, rcx
0x180012909  jz      short loc_180012960
0x18001290b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001290f  inc     rax
0x180012912  cmp     [rcx+rax*2], si
0x180012916  jnz     short loc_18001290F
0x180012918  test    rax, rax
0x18001291b  jz      short loc_180012955
0x18001291d  call    ExpandEnvironmentString
0x180012922  mov     rbx, rax
0x180012925  mov     edx, 11C5h; nIDDlgItem
0x18001292a  mov     rcx, rdi; hDlg
0x18001292d  test    rax, rax
0x180012930  jz      short loc_180012945
0x180012932  mov     r8, rax; lpString
0x180012935  call    cs:__imp_SetDlgItemTextW
0x18001293b  mov     rcx, rbx; lpMem
0x18001293e  call    pMemFree
0x180012943  jmp     short loc_180012950
0x180012945  mov     r8, [rsp+48h+lpString]; lpString
0x18001294a  call    cs:__imp_SetDlgItemTextW
0x180012950  mov     rcx, [rsp+48h+lpString]; Buffer
0x180012955  test    rcx, rcx
0x180012958  jz      short loc_180012960
0x18001295a  call    cs:__imp_FaxFreeBuffer
0x180012960  xor     eax, eax
0x180012962  mov     rbx, [rsp+48h+arg_8]
0x180012967  add     rsp, 30h
0x18001296b  pop     r14
0x18001296d  pop     rdi
0x18001296e  pop     rsi
0x18001296f  retn
```
