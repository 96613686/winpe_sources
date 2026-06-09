# FtpServerID_Create(ushort const *,ushort const *,ushort const *,ulong,ushort,_ITEMIDLIST * *,IMalloc *,int)

- ea: `0x18001d028`
- end: `0x18001d23a`
- name: `?FtpServerID_Create@@YAJPEBG00KGPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@H@Z`
- size: `530`
- prototype: `__int64 __usercall@<rax>(PCWSTR pwszSrc@<rcx>, PCWSTR@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16, struct _ITEMIDLIST **cchBuf, struct IMalloc *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001b91c`
- `0x180021600`

## callees

- `0x180002b60`
- `0x18000c134`
- `0x18001d028`
- `0x18001d36c`
- `0x18002725c`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d15c`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d17b`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d1ca`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d15c`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d17b`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001d1ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d0e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d20c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d20c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d12a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d12a`
- `KERNEL32!lstrlenW` at `0x18001d045`
- `KERNEL32!lstrlenW` at `0x18001d050`
- `KERNEL32!lstrlenW` at `0x18001d05b`
- `KERNEL32!lstrlenW` at `0x18001d045`
- `KERNEL32!lstrlenW` at `0x18001d050`
- `KERNEL32!lstrlenW` at `0x18001d05b`

## pseudocode

```c
__int64 __fastcall FtpServerID_Create(
        PCWSTR pwszSrc,
        PCWSTR a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 a5,
        struct _ITEMIDLIST **cchBuf,
        struct IMalloc *a7,
        int a8)
{
  int v12; // edi
  int v13; // ebp
  int v14; // eax
  unsigned int v16; // edx
  struct _ITEMIDLIST *v17; // rdi
  unsigned int v18; // r8d
  unsigned int v19; // ecx
  int v20; // eax
  int v21; // ebp
  SIZE_T v22; // r15
  CHAR *v23; // rax
  struct _FILETIME *v24; // rbx
  CHAR *v25; // rdi
  struct _FILETIME v26; // rax
  CHAR *v27; // rdi
  CCookieList *CookieList; // rax
  struct _ITEMIDLIST *v29; // rax
  unsigned int v31; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+24h] [rbp-54h]
  unsigned int cchBufa; // [rsp+A8h] [rbp+30h]

  v12 = lstrlenW(pwszSrc);
  v13 = lstrlenW(a2);
  v14 = lstrlenW(a3);
  if ( !cchBuf || !*pwszSrc )
    return 2147500037LL;
  v16 = (v12 + 4) & 0xFFFFFFFC;
  v17 = 0;
  cchBufa = v16;
  v18 = 4 * (((unsigned __int64)(unsigned int)(v13 + 1) + 3) >> 2);
  v31 = v18;
  v19 = (v14 + 4) & 0xFFFFFFFC;
  v20 = a4 | 0x200;
  v32 = v19;
  if ( !*a2 )
    v20 = a4;
  v21 = v20 | 0x400;
  if ( !*a3 )
    v21 = v20;
  v22 = v19 + v18 + v16 + 48;
  v23 = (CHAR *)LocalAlloc(0x40u, v22);
  v24 = (struct _FILETIME *)v23;
  if ( v23 )
  {
    v25 = v23 + 40;
    memset_0(v23, 0, (unsigned int)v22);
    v24->dwHighDateTime = 4;
    v24->dwLowDateTime = v21 | 0x103;
    if ( g_SessionKey.dwHighDateTime == -1 )
      GetSystemTimeAsFileTime(&g_SessionKey);
    v26 = g_SessionKey;
    v24[2].dwLowDateTime = -1;
    v24[1] = v26;
    v24[4].dwLowDateTime = a5;
    v24[4].dwHighDateTime = cchBufa;
    SHUnicodeToAnsi(pwszSrc, v25, cchBufa);
    *(_DWORD *)&v25[cchBufa] = v31;
    v27 = &v25[cchBufa + 4];
    SHUnicodeToAnsi(a2, v27, v31);
    if ( a8 )
    {
      v24->dwLowDateTime |= 0x2000u;
      if ( GetCookieList() )
      {
        CookieList = GetCookieList();
        v24[2].dwLowDateTime = CCookieList::GetCookie(CookieList, a3);
      }
      a3 = &lParam;
    }
    *(_DWORD *)&v27[v31] = v32;
    SHUnicodeToAnsi(a3, &v27[v31 + 4], v32);
    v29 = (struct _ITEMIDLIST *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))a7->lpVtbl->Alloc)(a7, v22);
    v17 = v29;
    if ( v29 && v29->mkid.cb && v29 != (struct _ITEMIDLIST *)-6LL )
      memcpy_0(&v29[2], v24, v22);
    LocalFree(v24);
  }
  *cchBuf = v17;
  return v17 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001d028  push    rbx
0x18001d02a  push    rbp
0x18001d02b  push    rsi
0x18001d02c  push    rdi
0x18001d02d  push    r12
0x18001d02f  push    r13
0x18001d031  push    r14
0x18001d033  push    r15
0x18001d035  sub     rsp, 38h
0x18001d039  mov     ebx, r9d
0x18001d03c  mov     rsi, r8
0x18001d03f  mov     r12, rdx
0x18001d042  mov     r14, rcx
0x18001d045  call    cs:__imp_lstrlenW
0x18001d04b  mov     rcx, r12; lpString
0x18001d04e  mov     edi, eax
0x18001d050  call    cs:__imp_lstrlenW
0x18001d056  mov     rcx, rsi; lpString
0x18001d059  mov     ebp, eax
0x18001d05b  call    cs:__imp_lstrlenW
0x18001d061  mov     r13, [rsp+78h+cchBuf]
0x18001d069  xor     r10d, r10d
0x18001d06c  test    r13, r13
0x18001d06f  jz      loc_18001D224
0x18001d075  cmp     [r14], r10w
0x18001d079  jz      loc_18001D224
0x18001d07f  lea     ecx, [rbp+1]
0x18001d082  add     rcx, 3
0x18001d086  lea     edx, [rdi+1]
0x18001d089  shr     rcx, 2
0x18001d08d  add     rdx, 3
0x18001d091  and     edx, 0FFFFFFFCh
0x18001d094  mov     edi, r10d
0x18001d097  mov     dword ptr [rsp+78h+cchBuf], edx
0x18001d09e  lea     r8d, ds:0[rcx*4]
0x18001d0a6  lea     ecx, [rax+1]
0x18001d0a9  mov     [rsp+78h+var_58], r8d
0x18001d0ae  add     rcx, 3
0x18001d0b2  mov     eax, ebx
0x18001d0b4  and     ecx, 0FFFFFFFCh
0x18001d0b7  bts     eax, 9
0x18001d0bb  cmp     [r12], r10w
0x18001d0c0  mov     [rsp+78h+var_54], ecx
0x18001d0c4  cmovz   eax, ebx
0x18001d0c7  mov     ebp, eax
0x18001d0c9  bts     ebp, 0Ah
0x18001d0cd  cmp     [rsi], r10w
0x18001d0d1  cmovz   ebp, eax
0x18001d0d4  lea     eax, [rcx+r8]
0x18001d0d8  lea     ecx, [rdx+30h]
0x18001d0db  add     ecx, eax
0x18001d0dd  mov     r15d, ecx
0x18001d0e0  mov     edx, ecx; uBytes
0x18001d0e2  lea     ecx, [r10+40h]; uFlags
0x18001d0e6  call    cs:__imp_LocalAlloc
0x18001d0ec  mov     rbx, rax
0x18001d0ef  test    rax, rax
0x18001d0f2  jz      loc_18001D212
0x18001d0f8  mov     r8d, r15d; Size
0x18001d0fb  lea     rdi, [rax+28h]
0x18001d0ff  xor     edx, edx; Val
0x18001d101  mov     rcx, rax; void *
0x18001d104  call    memset_0
0x18001d109  or      ebp, 103h
0x18001d10f  mov     dword ptr [rbx+4], 4
0x18001d116  mov     [rbx], ebp
0x18001d118  or      ebp, 0FFFFFFFFh
0x18001d11b  cmp     cs:?g_SessionKey@@3U_FILETIME@@A.dwHighDateTime, ebp; _FILETIME g_SessionKey ...
0x18001d121  jnz     short loc_18001D130
0x18001d123  lea     rcx, ?g_SessionKey@@3U_FILETIME@@A; lpSystemTimeAsFileTime
0x18001d12a  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d130  mov     rax, qword ptr cs:?g_SessionKey@@3U_FILETIME@@A.dwLowDateTime; _FILETIME g_SessionKey ...
0x18001d137  mov     rdx, rdi; pszDst
0x18001d13a  mov     [rbx+10h], ebp
0x18001d13d  mov     rcx, r14; pwszSrc
0x18001d140  mov     ebp, dword ptr [rsp+78h+cchBuf]
0x18001d147  mov     [rbx+8], rax
0x18001d14b  mov     r8d, ebp; cchBuf
0x18001d14e  movzx   eax, [rsp+78h+arg_20]
0x18001d156  mov     [rbx+20h], eax
0x18001d159  mov     [rbx+24h], ebp
0x18001d15c  call    cs:__imp_SHUnicodeToAnsi
0x18001d162  mov     eax, ebp
0x18001d164  mov     rcx, r12; pwszSrc
0x18001d167  mov     ebp, [rsp+78h+var_58]
0x18001d16b  mov     r8d, ebp; cchBuf
0x18001d16e  mov     [rax+rdi], ebp
0x18001d171  add     rax, 4
0x18001d175  add     rdi, rax
0x18001d178  mov     rdx, rdi; pszDst
0x18001d17b  call    cs:__imp_SHUnicodeToAnsi
0x18001d181  xor     r14d, r14d
0x18001d184  cmp     [rsp+78h+arg_38], r14d
0x18001d18c  jz      short loc_18001D1B6
0x18001d18e  bts     dword ptr [rbx], 0Dh
0x18001d192  call    ?GetCookieList@@YAPEAVCCookieList@@XZ; GetCookieList(void)
0x18001d197  test    rax, rax
0x18001d19a  jz      short loc_18001D1AF
0x18001d19c  call    ?GetCookieList@@YAPEAVCCookieList@@XZ; GetCookieList(void)
0x18001d1a1  mov     rdx, rsi; unsigned __int16 *
0x18001d1a4  mov     rcx, rax; this
0x18001d1a7  call    ?GetCookie@CCookieList@@QEAAKPEBG@Z; CCookieList::GetCookie(ushort const *)
0x18001d1ac  mov     [rbx+10h], eax
0x18001d1af  lea     rsi, lParam
0x18001d1b6  mov     r8d, [rsp+78h+var_54]; cchBuf
0x18001d1bb  lea     rdx, [rbp+4]
0x18001d1bf  add     rdx, rdi; pszDst
0x18001d1c2  mov     [rbp+rdi+0], r8d
0x18001d1c7  mov     rcx, rsi; pwszSrc
0x18001d1ca  call    cs:__imp_SHUnicodeToAnsi
0x18001d1d0  mov     rcx, [rsp+78h+arg_30]
0x18001d1d8  mov     rdx, r15
0x18001d1db  mov     rax, [rcx]
0x18001d1de  mov     rax, [rax+18h]
0x18001d1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1e7  mov     rdi, rax
0x18001d1ea  test    rax, rax
0x18001d1ed  jz      short loc_18001D209
0x18001d1ef  cmp     [rax], r14w
0x18001d1f3  jz      short loc_18001D209
0x18001d1f5  lea     rcx, [rax+6]; void *
0x18001d1f9  test    rcx, rcx
0x18001d1fc  jz      short loc_18001D209
0x18001d1fe  mov     r8, r15; Size
0x18001d201  mov     rdx, rbx; Src
0x18001d204  call    memcpy_0
0x18001d209  mov     rcx, rbx; hMem
0x18001d20c  call    cs:__imp_LocalFree
0x18001d212  mov     [r13+0], rdi
0x18001d216  neg     rdi
0x18001d219  sbb     eax, eax
0x18001d21b  not     eax
0x18001d21d  and     eax, 8007000Eh
0x18001d222  jmp     short loc_18001D229
0x18001d224  mov     eax, 80004005h
0x18001d229  add     rsp, 38h
0x18001d22d  pop     r15
0x18001d22f  pop     r14
0x18001d231  pop     r13
0x18001d233  pop     r12
0x18001d235  pop     rdi
0x18001d236  pop     rsi
0x18001d237  pop     rbp
0x18001d238  pop     rbx
0x18001d239  retn
```
