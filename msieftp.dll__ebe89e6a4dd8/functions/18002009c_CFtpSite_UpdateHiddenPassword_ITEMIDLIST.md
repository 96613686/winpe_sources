# CFtpSite::UpdateHiddenPassword(_ITEMIDLIST *)

- ea: `0x18002009c`
- end: `0x180020197`
- name: `?UpdateHiddenPassword@CFtpSite@@QEAAJPEFAU_ITEMIDLIST@@@Z`
- size: `251`
- prototype: `int(CFtpSite *__hidden this, struct _ITEMIDLIST *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800172a0`
- `0x1800182c4`

## callees

- `0x180002240`
- `0x18000c134`
- `0x18001cad0`
- `0x18001cc1c`
- `0x18001d240`
- `0x18001d36c`
- `0x18002009c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002013e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002013e`

## pseudocode

```c
__int64 __fastcall CFtpSite::UpdateHiddenPassword(CFtpSite *this, struct _ITEMIDLIST *a2)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  struct tagFTPSERVERIDLIST *DataThunk; // rbx
  const unsigned __int16 *v7; // rdi
  struct _FILETIME v8; // rcx
  CCookieList *CookieList; // rax
  unsigned __int16 v11[128]; // [rsp+20h] [rbp-228h] BYREF
  unsigned __int16 v12[128]; // [rsp+120h] [rbp-128h] BYREF

  v4 = 1;
  if ( *((_QWORD *)this + 11) )
  {
    if ( FtpPidl_GetUserName(a2, v11, 0x80u) >= 0 )
    {
      if ( v11[0] )
      {
        if ( FtpPidl_GetPassword(a2, v12, v5, 1) >= 0 && !v12[0] )
        {
          v4 = -2147024809;
          DataThunk = FtpServerID_GetDataThunk(a2);
          if ( DataThunk )
          {
            v7 = (const unsigned __int16 *)*((_QWORD *)this + 11);
            if ( g_SessionKey.dwHighDateTime == -1 )
              GetSystemTimeAsFileTime(&g_SessionKey);
            v8 = g_SessionKey;
            *(_DWORD *)DataThunk |= 0x2000u;
            *((struct _FILETIME *)DataThunk + 1) = v8;
            if ( GetCookieList() )
            {
              CookieList = GetCookieList();
              *((_DWORD *)DataThunk + 4) = CCookieList::GetCookie(CookieList, v7);
            }
            return 0;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002009c  mov     [rsp+arg_10], rbx
0x1800200a1  push    rbp
0x1800200a2  push    rsi
0x1800200a3  push    rdi
0x1800200a4  sub     rsp, 230h
0x1800200ab  mov     rax, cs:__security_cookie
0x1800200b2  xor     rax, rsp
0x1800200b5  mov     [rsp+248h+var_28], rax
0x1800200bd  xor     ebp, ebp
0x1800200bf  mov     rbx, rdx
0x1800200c2  mov     rsi, rcx
0x1800200c5  mov     edi, 1
0x1800200ca  cmp     [rcx+58h], rbp
0x1800200ce  jz      loc_180020172
0x1800200d4  lea     r8d, [rdi+7Fh]; unsigned int
0x1800200d8  mov     rcx, rbx; struct _ITEMIDLIST *
0x1800200db  lea     rdx, [rsp+248h+var_228]; unsigned __int16 *
0x1800200e0  call    ?FtpPidl_GetUserName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetUserName(_ITEMIDLIST const *,ushort *,ulong)
0x1800200e5  test    eax, eax
0x1800200e7  js      loc_180020172
0x1800200ed  cmp     [rsp+248h+var_228], bp
0x1800200f2  jz      short loc_180020172
0x1800200f4  mov     r9d, edi; int
0x1800200f7  lea     rdx, [rsp+248h+var_128]; unsigned __int16 *
0x1800200ff  mov     rcx, rbx; struct _ITEMIDLIST *
0x180020102  call    ?FtpPidl_GetPassword@@YAJPEFBU_ITEMIDLIST@@PEAGKH@Z; FtpPidl_GetPassword(_ITEMIDLIST const *,ushort *,ulong,int)
0x180020107  test    eax, eax
0x180020109  js      short loc_180020172
0x18002010b  cmp     [rsp+248h+var_128], bp
0x180020113  jnz     short loc_180020172
0x180020115  mov     rcx, rbx; struct _ITEMIDLIST *
0x180020118  mov     edi, 80070057h
0x18002011d  call    ?FtpServerID_GetDataThunk@@YAPEFAUtagFTPSERVERIDLIST@@PEFAU_ITEMIDLIST@@@Z; FtpServerID_GetDataThunk(_ITEMIDLIST *)
0x180020122  mov     rbx, rax
0x180020125  test    rax, rax
0x180020128  jz      short loc_180020172
0x18002012a  cmp     cs:?g_SessionKey@@3U_FILETIME@@A.dwHighDateTime, 0FFFFFFFFh; _FILETIME g_SessionKey ...
0x180020131  mov     rdi, [rsi+58h]
0x180020135  jnz     short loc_180020144
0x180020137  lea     rcx, ?g_SessionKey@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x18002013e  call    cs:__imp_GetSystemTimeAsFileTime
0x180020144  mov     rcx, qword ptr cs:?g_SessionKey@@3U_FILETIME@@A.dwLowDateTime; _FILETIME g_SessionKey ...
0x18002014b  bts     dword ptr [rbx], 0Dh
0x18002014f  mov     [rbx+8], rcx
0x180020153  call    ?GetCookieList@@YAPEAVCCookieList@@XZ; GetCookieList(void)
0x180020158  test    rax, rax
0x18002015b  jz      short loc_180020170
0x18002015d  call    ?GetCookieList@@YAPEAVCCookieList@@XZ; GetCookieList(void)
0x180020162  mov     rdx, rdi; unsigned __int16 *
0x180020165  mov     rcx, rax; this
0x180020168  call    ?GetCookie@CCookieList@@QEAAKPEBG@Z; CCookieList::GetCookie(ushort const *)
0x18002016d  mov     [rbx+10h], eax
0x180020170  mov     edi, ebp
0x180020172  mov     eax, edi
0x180020174  mov     rcx, [rsp+248h+var_28]
0x18002017c  xor     rcx, rsp; StackCookie
0x18002017f  call    __security_check_cookie
0x180020184  mov     rbx, [rsp+248h+arg_10]
0x18002018c  add     rsp, 230h
0x180020193  pop     rdi
0x180020194  pop     rsi
0x180020195  pop     rbp
0x180020196  retn
```
