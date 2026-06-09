# DwAddLinkageKeysIfNotPresent(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x18006a2cc`
- end: `0x18006a484`
- name: `?DwAddLinkageKeysIfNotPresent@@YAKPEAG000PEAHK@Z`
- size: `440`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180069c1c`
- `0x180069f74`
- `0x18006a780`
- `0x18006a97c`

## callees

- `0x180025e2c`
- `0x180025ef0`
- `0x18006a2cc`
- `0x18006b384`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006a46b`
- `KERNEL32!LocalFree` at `0x18006a46b`
- `ADVAPI32!RegSetValueExW` at `0x18006a44c`
- `ADVAPI32!RegSetValueExW` at `0x18006a44c`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a31c`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a31c`
- `ADVAPI32!RegCloseKey` at `0x18006a45d`
- `ADVAPI32!RegCloseKey` at `0x18006a45d`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        unsigned int a6)
{
  BYTE *v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned __int64 v12; // r11
  int v13; // r14d
  STRSAFE_LPWSTR v14; // rdi
  __int64 v15; // r9
  unsigned __int64 v16; // rax
  char *v17; // rcx
  unsigned __int16 *v18; // rax
  signed __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  unsigned __int64 v22; // r11
  BYTE *v23; // rax
  bool v24; // zf
  _WORD *v25; // rcx
  unsigned int v27; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v28 = 0;
  v8 = 0;
  *a5 = 0;
  pszDest = 0;
  v27 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hKey);
  if ( !v9 )
  {
    v11 = RegQueryValueWithAllocW(hKey, a3, v10, (unsigned __int8 **)&pszDest, &v27, &v28, a6);
    v8 = (BYTE *)pszDest;
    v9 = v11;
    if ( !v11 )
    {
      v12 = v27;
      v13 = 2;
      v14 = pszDest;
      if ( *pszDest )
      {
        while ( 1 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          v16 = -1;
          do
            ++v16;
          while ( a4[v16] );
          if ( (unsigned int)v15 >= v16 )
          {
            v17 = (char *)&v14[v16];
            if ( *(_WORD *)v17 == 123 )
            {
              v18 = a1;
              v19 = v17 - (char *)a1;
              do
              {
                v20 = *(unsigned __int16 *)((char *)v18 + v19);
                v21 = *v18 - v20;
                if ( v21 )
                  break;
                ++v18;
              }
              while ( v20 );
              if ( !v21 )
                break;
            }
          }
          v14 += (unsigned int)v15 + 1;
          v12 = (unsigned int)(-2 - 2 * v15 + v12);
          if ( !*v14 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        StringCchCopyW(v14, v12 >> 1, a4);
        StringCchCatW(v14, v22, a1);
        v23 = v8;
        while ( 1 )
        {
          v24 = *(_WORD *)v23 == 0;
          v25 = v23 + 2;
          v23 += 2;
          if ( v24 && !*v25 )
            break;
          ++v13;
        }
        v9 = RegSetValueExW(hKey, a3, 0, 7u, v8, 2 * v13);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18006a2cc  mov     [rsp-40h+arg_0], rcx
0x18006a2d1  push    rbp
0x18006a2d2  push    rbx
0x18006a2d3  push    rsi
0x18006a2d4  push    rdi
0x18006a2d5  push    r12
0x18006a2d7  push    r13
0x18006a2d9  push    r14
0x18006a2db  push    r15
0x18006a2dd  mov     rbp, rsp
0x18006a2e0  sub     rsp, 68h
0x18006a2e4  mov     r15, [rbp+arg_20]
0x18006a2e8  lea     rax, [rbp+hKey]
0x18006a2ec  xor     edi, edi
0x18006a2ee  mov     [rsp+68h+phkResult], rax; phkResult
0x18006a2f3  mov     r13, r9
0x18006a2f6  mov     [rbp+hKey], rdi
0x18006a2fa  mov     r12, r8
0x18006a2fd  mov     [rbp+var_24], edi
0x18006a300  mov     ebx, edi
0x18006a302  mov     [r15], edi
0x18006a305  mov     r9d, 0F003Fh; samDesired
0x18006a30b  mov     [rbp+pszDest], rbx
0x18006a30f  xor     r8d, r8d; ulOptions
0x18006a312  mov     [rbp+var_28], edi
0x18006a315  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a31c  call    cs:__imp_RegOpenKeyExW
0x18006a322  mov     esi, eax
0x18006a324  test    eax, eax
0x18006a326  jnz     loc_18006A454
0x18006a32c  mov     eax, [rbp+arg_28]
0x18006a32f  lea     r9, [rbp+pszDest]; unsigned __int8 **
0x18006a333  mov     rcx, [rbp+hKey]; hKey
0x18006a337  mov     rdx, r12; lpValueName
0x18006a33a  mov     [rsp+68h+var_38], eax; unsigned int
0x18006a33e  lea     rax, [rbp+var_24]
0x18006a342  mov     qword ptr [rsp+68h+cbData], rax; unsigned int *
0x18006a347  lea     rax, [rbp+var_28]
0x18006a34b  mov     [rsp+68h+phkResult], rax; unsigned int *
0x18006a350  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x18006a355  mov     rbx, [rbp+pszDest]
0x18006a359  mov     esi, eax
0x18006a35b  test    eax, eax
0x18006a35d  jnz     loc_18006A454
0x18006a363  mov     r11d, [rbp+var_28]
0x18006a367  lea     r14d, [rax+2]
0x18006a36b  xor     ecx, ecx
0x18006a36d  mov     rdi, rbx
0x18006a370  cmp     [rbx], cx
0x18006a373  jz      short loc_18006A3EF
0x18006a375  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006a379  inc     r9
0x18006a37c  cmp     [rdi+r9*2], cx
0x18006a381  jnz     short loc_18006A379
0x18006a383  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006a387  inc     rax
0x18006a38a  cmp     [r13+rax*2+0], cx
0x18006a390  jnz     short loc_18006A387
0x18006a392  mov     r10d, r9d
0x18006a395  cmp     r10, rax
0x18006a398  jb      short loc_18006A3CA
0x18006a39a  lea     rcx, [rdi+rax*2]
0x18006a39e  mov     eax, 7Bh ; '{'
0x18006a3a3  cmp     ax, [rcx]
0x18006a3a6  jnz     short loc_18006A3CA
0x18006a3a8  mov     rax, [rbp+arg_0]
0x18006a3ac  sub     rcx, rax
0x18006a3af  movzx   r8d, word ptr [rax]
0x18006a3b3  movzx   edx, word ptr [rax+rcx]
0x18006a3b7  sub     r8d, edx
0x18006a3ba  jnz     short loc_18006A3C3
0x18006a3bc  add     rax, r14
0x18006a3bf  test    edx, edx
0x18006a3c1  jnz     short loc_18006A3AF
0x18006a3c3  xor     ecx, ecx
0x18006a3c5  test    r8d, r8d
0x18006a3c8  jz      short loc_18006A3E8
0x18006a3ca  mov     ecx, 0FFFFFFFEh
0x18006a3cf  lea     rdi, [rdi+r10*2]
0x18006a3d3  lea     eax, [r9+r9]
0x18006a3d7  add     rdi, r14
0x18006a3da  sub     ecx, eax
0x18006a3dc  add     r11d, ecx
0x18006a3df  xor     ecx, ecx
0x18006a3e1  cmp     [rdi], cx
0x18006a3e4  jnz     short loc_18006A375
0x18006a3e6  jmp     short loc_18006A3EF
0x18006a3e8  mov     dword ptr [r15], 1
0x18006a3ef  cmp     [r15], ecx
0x18006a3f2  jnz     short loc_18006A454
0x18006a3f4  shr     r11, 1
0x18006a3f7  mov     r8, r13; pszSrc
0x18006a3fa  mov     rdx, r11; cchDest
0x18006a3fd  mov     rcx, rdi; pszDest
0x18006a400  call    StringCchCopyW
0x18006a405  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18006a409  mov     rdx, r11; unsigned __int64
0x18006a40c  mov     rcx, rdi; unsigned __int16 *
0x18006a40f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006a414  mov     rax, rbx
0x18006a417  xor     edi, edi
0x18006a419  cmp     [rax], di
0x18006a41c  lea     rcx, [rax+2]
0x18006a420  mov     rax, rcx
0x18006a423  jnz     short loc_18006A42A
0x18006a425  cmp     [rcx], di
0x18006a428  jz      short loc_18006A42F
0x18006a42a  inc     r14d
0x18006a42d  jmp     short loc_18006A419
0x18006a42f  mov     rcx, [rbp+hKey]; hKey
0x18006a433  lea     eax, [r14+r14]
0x18006a437  mov     [rsp+68h+cbData], eax; cbData
0x18006a43b  mov     r9d, 7; dwType
0x18006a441  xor     r8d, r8d; Reserved
0x18006a444  mov     [rsp+68h+phkResult], rbx; lpData
0x18006a449  mov     rdx, r12; lpValueName
0x18006a44c  call    cs:__imp_RegSetValueExW
0x18006a452  mov     esi, eax
0x18006a454  mov     rcx, [rbp+hKey]; hKey
0x18006a458  test    rcx, rcx
0x18006a45b  jz      short loc_18006A463
0x18006a45d  call    cs:__imp_RegCloseKey
0x18006a463  test    rbx, rbx
0x18006a466  jz      short loc_18006A471
0x18006a468  mov     rcx, rbx; hMem
0x18006a46b  call    cs:__imp_LocalFree
0x18006a471  mov     eax, esi
0x18006a473  add     rsp, 68h
0x18006a477  pop     r15
0x18006a479  pop     r14
0x18006a47b  pop     r13
0x18006a47d  pop     r12
0x18006a47f  pop     rdi
0x18006a480  pop     rsi
0x18006a481  pop     rbx
0x18006a482  pop     rbp
0x18006a483  retn
```
