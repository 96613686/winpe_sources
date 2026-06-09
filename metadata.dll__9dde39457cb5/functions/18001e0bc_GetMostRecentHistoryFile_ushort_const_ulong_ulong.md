# GetMostRecentHistoryFile(ushort const *,ulong *,ulong *)

- ea: `0x18001e0bc`
- end: `0x18001e287`
- name: `?GetMostRecentHistoryFile@@YAJPEBGPEAK1@Z`
- size: `459`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019560`

## callees

- `0x18001e0bc`
- `0x180021218`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!FindClose` at `0x18001e262`
- `KERNEL32!FindClose` at `0x18001e262`
- `KERNEL32!FindNextFileW` at `0x18001e21d`
- `KERNEL32!FindNextFileW` at `0x18001e21d`
- `KERNEL32!FindFirstFileW` at `0x18001e129`
- `KERNEL32!FindFirstFileW` at `0x18001e129`
- `KERNEL32!CompareFileTime` at `0x18001e168`
- `KERNEL32!CompareFileTime` at `0x18001e168`
- `KERNEL32!GetLastError` at `0x18001e138`
- `KERNEL32!GetLastError` at `0x18001e138`

## pseudocode

```c
__int64 __fastcall GetMostRecentHistoryFile(LPCWSTR lpFileName, unsigned int *a2, unsigned int *a3)
{
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  int v8; // ebx
  char v9; // bl
  _OWORD *v10; // rax
  struct _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v12; // rdx
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  unsigned int v25; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v26[3]; // [rsp+24h] [rbp-DCh] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v28[20]; // [rsp+280h] [rbp+180h] BYREF
  FILETIME FileTime2; // [rsp+294h] [rbp+194h] BYREF
  unsigned __int16 v30[274]; // [rsp+2ACh] [rbp+1ACh] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v28, 0, 0x250u);
  v25 = 0;
  v26[0] = 0;
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v9 = 0;
    do
    {
      if ( (!v9 || CompareFileTime(&FindFileData.ftLastWriteTime, &FileTime2) > 0)
        && ParseVersionNumber(FindFileData.cFileName, v26, &v25) >= 0 )
      {
        v9 = 1;
        v10 = v28;
        p_FindFileData = &FindFileData;
        v12 = 2;
        do
        {
          v13 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v14 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
          *v10 = v13;
          v15 = *(_OWORD *)&p_FindFileData[-1].cFileName[226];
          v10[1] = v14;
          v16 = *(_OWORD *)&p_FindFileData[-1].cFileName[234];
          v10[2] = v15;
          v17 = *(_OWORD *)&p_FindFileData[-1].cFileName[242];
          v10[3] = v16;
          v18 = *(_OWORD *)&p_FindFileData[-1].cFileName[250];
          v10[4] = v17;
          v19 = *(_OWORD *)&p_FindFileData[-1].cFileName[258];
          v10[5] = v18;
          v20 = *(_OWORD *)&p_FindFileData[-1].cAlternateFileName[6];
          v10[6] = v19;
          v10[7] = v20;
          v10 += 8;
          --v12;
        }
        while ( v12 );
        v21 = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
        *v10 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
        v22 = *(_OWORD *)&p_FindFileData->nFileSizeLow;
        v10[1] = v21;
        v23 = *(_OWORD *)&p_FindFileData->cFileName[2];
        v10[2] = v22;
        v10[3] = v23;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( v9 )
    {
      v8 = ParseVersionNumber(v30, v26, &v25);
      if ( v8 >= 0 )
      {
        *a2 = v25;
        *a3 = v26[0];
      }
    }
    else
    {
      v8 = -2147024894;
    }
    FindClose(FirstFileW);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e0bc  push    rbp
0x18001e0be  push    rbx
0x18001e0bf  push    rsi
0x18001e0c0  push    rdi
0x18001e0c1  push    r14
0x18001e0c3  lea     rbp, [rsp-3E0h]
0x18001e0cb  sub     rsp, 4E0h
0x18001e0d2  mov     rax, cs:__security_cookie
0x18001e0d9  xor     rax, rsp
0x18001e0dc  mov     [rbp+400h+var_30], rax
0x18001e0e3  mov     r14, r8
0x18001e0e6  mov     rsi, rdx
0x18001e0e9  mov     rbx, rcx
0x18001e0ec  mov     edi, 250h
0x18001e0f1  mov     r8d, edi; Size
0x18001e0f4  lea     rcx, [rsp+500h+FindFileData]; void *
0x18001e0f9  xor     edx, edx; Val
0x18001e0fb  call    memset_0
0x18001e100  mov     r8d, edi; Size
0x18001e103  lea     rcx, [rbp+400h+var_280]; void *
0x18001e10a  xor     edx, edx; Val
0x18001e10c  call    memset_0
0x18001e111  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x18001e116  mov     [rsp+500h+var_4E0], 0
0x18001e11e  mov     rcx, rbx; lpFileName
0x18001e121  mov     [rsp+500h+var_4DC], 0
0x18001e129  call    cs:__imp_FindFirstFileW
0x18001e12f  mov     rdi, rax
0x18001e132  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e136  jnz     short loc_18001E156
0x18001e138  call    cs:__imp_GetLastError
0x18001e13e  mov     ebx, eax
0x18001e140  test    eax, eax
0x18001e142  jle     loc_18001E268
0x18001e148  movzx   ebx, ax
0x18001e14b  or      ebx, 80070000h
0x18001e151  jmp     loc_18001E268
0x18001e156  xor     bl, bl
0x18001e158  test    bl, bl
0x18001e15a  jz      short loc_18001E176
0x18001e15c  lea     rdx, [rbp+400h+FileTime2]; lpFileTime2
0x18001e163  lea     rcx, [rsp+500h+FindFileData.ftLastWriteTime]; lpFileTime1
0x18001e168  call    cs:__imp_CompareFileTime
0x18001e16e  test    eax, eax
0x18001e170  jle     loc_18001E215
0x18001e176  lea     r8, [rsp+500h+var_4E0]; unsigned int *
0x18001e17b  lea     rdx, [rsp+500h+var_4DC]; unsigned int *
0x18001e180  lea     rcx, [rsp+500h+FindFileData.cFileName]; unsigned __int16 *
0x18001e185  call    ?ParseVersionNumber@@YAJPEAGPEAK1@Z; ParseVersionNumber(ushort *,ulong *,ulong *)
0x18001e18a  test    eax, eax
0x18001e18c  js      loc_18001E215
0x18001e192  mov     bl, 1
0x18001e194  lea     rax, [rbp+400h+var_280]
0x18001e19b  lea     rcx, [rsp+500h+FindFileData]
0x18001e1a0  mov     edx, 2
0x18001e1a5  movups  xmm0, xmmword ptr [rcx]
0x18001e1a8  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e1ac  lea     rcx, [rcx+80h]
0x18001e1b3  movups  xmmword ptr [rax], xmm0
0x18001e1b6  movups  xmm0, xmmword ptr [rcx-60h]
0x18001e1ba  movups  xmmword ptr [rax+10h], xmm1
0x18001e1be  movups  xmm1, xmmword ptr [rcx-50h]
0x18001e1c2  movups  xmmword ptr [rax+20h], xmm0
0x18001e1c6  movups  xmm0, xmmword ptr [rcx-40h]
0x18001e1ca  movups  xmmword ptr [rax+30h], xmm1
0x18001e1ce  movups  xmm1, xmmword ptr [rcx-30h]
0x18001e1d2  movups  xmmword ptr [rax+40h], xmm0
0x18001e1d6  movups  xmm0, xmmword ptr [rcx-20h]
0x18001e1da  movups  xmmword ptr [rax+50h], xmm1
0x18001e1de  movups  xmm1, xmmword ptr [rcx-10h]
0x18001e1e2  movups  xmmword ptr [rax+60h], xmm0
0x18001e1e6  movups  xmmword ptr [rax+70h], xmm1
0x18001e1ea  lea     rax, [rax+80h]
0x18001e1f1  sub     rdx, 1
0x18001e1f5  jnz     short loc_18001E1A5
0x18001e1f7  movups  xmm0, xmmword ptr [rcx]
0x18001e1fa  movups  xmm1, xmmword ptr [rcx+10h]
0x18001e1fe  movups  xmmword ptr [rax], xmm0
0x18001e201  movups  xmm0, xmmword ptr [rcx+20h]
0x18001e205  movups  xmmword ptr [rax+10h], xmm1
0x18001e209  movups  xmm1, xmmword ptr [rcx+30h]
0x18001e20d  movups  xmmword ptr [rax+20h], xmm0
0x18001e211  movups  xmmword ptr [rax+30h], xmm1
0x18001e215  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x18001e21a  mov     rcx, rdi; hFindFile
0x18001e21d  call    cs:__imp_FindNextFileW
0x18001e223  test    eax, eax
0x18001e225  jnz     loc_18001E158
0x18001e22b  test    bl, bl
0x18001e22d  jnz     short loc_18001E236
0x18001e22f  mov     ebx, 80070002h
0x18001e234  jmp     short loc_18001E25F
0x18001e236  lea     r8, [rsp+500h+var_4E0]; unsigned int *
0x18001e23b  lea     rdx, [rsp+500h+var_4DC]; unsigned int *
0x18001e240  lea     rcx, [rbp+400h+var_254]; unsigned __int16 *
0x18001e247  call    ?ParseVersionNumber@@YAJPEAGPEAK1@Z; ParseVersionNumber(ushort *,ulong *,ulong *)
0x18001e24c  mov     ebx, eax
0x18001e24e  test    eax, eax
0x18001e250  js      short loc_18001E25F
0x18001e252  mov     ecx, [rsp+500h+var_4E0]
0x18001e256  mov     [rsi], ecx
0x18001e258  mov     ecx, [rsp+500h+var_4DC]
0x18001e25c  mov     [r14], ecx
0x18001e25f  mov     rcx, rdi; hFindFile
0x18001e262  call    cs:__imp_FindClose
0x18001e268  mov     eax, ebx
0x18001e26a  mov     rcx, [rbp+400h+var_30]
0x18001e271  xor     rcx, rsp; StackCookie
0x18001e274  call    __security_check_cookie
0x18001e279  add     rsp, 4E0h
0x18001e280  pop     r14
0x18001e282  pop     rdi
0x18001e283  pop     rsi
0x18001e284  pop     rbx
0x18001e285  pop     rbp
0x18001e286  retn
```
