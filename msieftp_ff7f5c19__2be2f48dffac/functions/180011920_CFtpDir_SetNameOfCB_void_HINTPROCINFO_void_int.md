# CFtpDir::_SetNameOfCB(void *,HINTPROCINFO *,void *,int *)

- ea: `0x180011920`
- end: `0x1800119dc`
- name: `?_SetNameOfCB@CFtpDir@@SAJPEAXPEAUHINTPROCINFO@@0PEAH@Z`
- size: `188`
- prototype: `__int64 __fastcall(HINTERNET hConnect, struct HINTPROCINFO *, void *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002240`
- `0x180011920`
- `0x18001c9b8`
- `0x18001ca1c`
- `0x180023340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a3`
- `WININET!FtpRenameFileA` at `0x180011999`
- `WININET!FtpRenameFileA` at `0x180011999`

## pseudocode

```c
__int64 __fastcall CFtpDir::_SetNameOfCB(HINTERNET hConnect, HWND **a2, const struct _ITEMIDLIST **a3, int *a4)
{
  const struct _ITEMIDLIST *v7; // rbx
  const CHAR *LastItemWireName; // rdi
  const CHAR *v9; // rax
  unsigned int v10; // ebx
  signed int LastError; // eax
  unsigned __int16 v13[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( a2[2] )
  {
    FtpPidl_GetLastItemDisplayName(*a3, v13, (unsigned int)a3);
    CStatusBar::SetStatusMessage(a2[2], 0x45u, v13);
  }
  v7 = *a3;
  LastItemWireName = FtpPidl_GetLastItemWireName(a3[1]);
  v9 = FtpPidl_GetLastItemWireName(v7);
  if ( v9 && LastItemWireName )
  {
    v10 = 0;
    if ( !FtpRenameFileA(hConnect, v9, LastItemWireName) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v10;
}

```

## disassembly

```asm
0x180011920  push    rbx
0x180011922  push    rsi
0x180011923  push    rdi
0x180011924  sub     rsp, 240h
0x18001192b  mov     rax, cs:__security_cookie
0x180011932  xor     rax, rsp
0x180011935  mov     [rsp+258h+var_28], rax
0x18001193d  cmp     qword ptr [rdx+10h], 0
0x180011942  mov     rdi, r8
0x180011945  mov     rbx, rdx
0x180011948  mov     rsi, rcx
0x18001194b  jz      short loc_18001196D
0x18001194d  mov     rcx, [r8]; struct _ITEMIDLIST *
0x180011950  lea     rdx, [rsp+258h+var_238]; unsigned __int16 *
0x180011955  call    ?FtpPidl_GetLastItemDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetLastItemDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18001195a  mov     rcx, [rbx+10h]; this
0x18001195e  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180011963  mov     edx, 45h ; 'E'; unsigned int
0x180011968  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x18001196d  mov     rcx, [rdi+8]; struct _ITEMIDLIST *
0x180011971  mov     rbx, [rdi]
0x180011974  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x180011979  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001197c  mov     rdi, rax
0x18001197f  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x180011984  test    rax, rax
0x180011987  jz      short loc_1800119BA
0x180011989  test    rdi, rdi
0x18001198c  jz      short loc_1800119BA
0x18001198e  mov     r8, rdi; lpszNew
0x180011991  mov     rdx, rax; lpszExisting
0x180011994  mov     rcx, rsi; hConnect
0x180011997  xor     ebx, ebx
0x180011999  call    cs:__imp_FtpRenameFileA
0x18001199f  test    eax, eax
0x1800119a1  jnz     short loc_1800119BF
0x1800119a3  call    cs:__imp_GetLastError
0x1800119a9  mov     ebx, eax
0x1800119ab  test    eax, eax
0x1800119ad  jle     short loc_1800119BF
0x1800119af  movzx   ebx, ax
0x1800119b2  or      ebx, 80070000h
0x1800119b8  jmp     short loc_1800119BF
0x1800119ba  mov     ebx, 80004005h
0x1800119bf  mov     eax, ebx
0x1800119c1  mov     rcx, [rsp+258h+var_28]
0x1800119c9  xor     rcx, rsp; StackCookie
0x1800119cc  call    __security_check_cookie
0x1800119d1  add     rsp, 240h
0x1800119d8  pop     rdi
0x1800119d9  pop     rsi
0x1800119da  pop     rbx
0x1800119db  retn
```
