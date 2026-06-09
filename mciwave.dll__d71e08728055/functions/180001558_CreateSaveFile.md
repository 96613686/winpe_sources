# CreateSaveFile

- ea: `0x180001558`
- end: `0x180001760`
- name: `CreateSaveFile`
- size: `520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002320`

## callees

- `0x180001558`
- `0x1800031c4`
- `0x180005c29`
- `0x180005c60`

## import_xrefs

- `WINMM!mmioAscend` at `0x180001673`
- `WINMM!mmioAscend` at `0x180001673`
- `WINMM!mmioCreateChunk` at `0x180001612`
- `WINMM!mmioCreateChunk` at `0x18000163a`
- `WINMM!mmioCreateChunk` at `0x180001698`
- `WINMM!mmioCreateChunk` at `0x180001612`
- `WINMM!mmioCreateChunk` at `0x18000163a`
- `WINMM!mmioCreateChunk` at `0x180001698`
- `WINMM!mmioClose` at `0x180001728`
- `WINMM!mmioClose` at `0x180001728`
- `WINMM!mmioOpenW` at `0x1800015c9`
- `WINMM!mmioOpenW` at `0x1800016fe`
- `WINMM!mmioOpenW` at `0x1800015c9`
- `WINMM!mmioOpenW` at `0x1800016fe`
- `WINMM!mmioWrite` at `0x18000165b`
- `WINMM!mmioWrite` at `0x18000165b`

## pseudocode

```c
HMMIO __fastcall CreateSaveFile(__int64 a1, WCHAR *a2)
{
  HMMIO v4; // rsi
  int v5; // edx
  int v6; // eax
  DWORD v7; // eax
  LONG v8; // ebx
  __int64 v10; // rcx
  WCHAR *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  _MMCKINFO pmmcki; // [rsp+20h] [rbp-59h] BYREF
  _MMIOINFO pmmioinfo; // [rsp+40h] [rbp-39h] BYREF

  memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
  InitMMIOOpen(a1, &pmmioinfo);
  if ( *(_QWORD *)(a1 + 152) )
  {
    *a2 = 0;
    a2 = *(WCHAR **)(a1 + 152);
  }
  else
  {
    v10 = 2147483646;
    v11 = (WCHAR *)(a1 + 256);
    v12 = 260;
    v13 = a2;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v10;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( !mmioOpenW(a2, &pmmioinfo, 0x20000u) )
    {
      *(_DWORD *)(a1 + 140) = 349;
      return 0;
    }
  }
  v4 = mmioOpenW(a2, &pmmioinfo, 0x1022u);
  if ( v4 )
  {
    v5 = *(_DWORD *)(a1 + 160);
    v6 = *(_DWORD *)(a1 + 76) + 20;
    pmmcki.ckid = 0;
    v7 = v5 + v6;
    *(_QWORD *)&pmmcki.dwDataOffset = 0;
    pmmcki.cksize = v7;
    if ( (v5 & 1) != 0 )
      pmmcki.cksize = v7 + 1;
    pmmcki.fccType = 1163280727;
    if ( !mmioCreateChunk(v4, &pmmcki, 0x20u) )
    {
      pmmcki.cksize = *(_DWORD *)(a1 + 160);
      pmmcki.ckid = 544501094;
      if ( !mmioCreateChunk(v4, &pmmcki, 0) )
      {
        v8 = *(_DWORD *)(a1 + 160);
        if ( mmioWrite(v4, *(const char **)(a1 + 168), v8) == v8 && !mmioAscend(v4, &pmmcki, 0) )
        {
          pmmcki.cksize = *(_DWORD *)(a1 + 76);
          pmmcki.ckid = 1635017060;
          if ( !mmioCreateChunk(v4, &pmmcki, 0) )
            return v4;
        }
      }
    }
    *(_DWORD *)(a1 + 140) = 349;
    mmioClose(v4, 0);
  }
  else
  {
    *(_DWORD *)(a1 + 140) = 286;
  }
  return 0;
}

```

## disassembly

```asm
0x180001558  mov     [rsp-8+arg_10], rbx
0x18000155d  mov     [rsp-8+arg_18], rsi
0x180001562  push    rbp
0x180001563  push    rdi
0x180001564  push    r14
0x180001566  lea     rbp, [rsp-47h]
0x18000156b  sub     rsp, 0C0h
0x180001572  mov     rax, cs:__security_cookie
0x180001579  xor     rax, rsp
0x18000157c  mov     [rbp+57h+var_20], rax
0x180001580  mov     rbx, rdx
0x180001583  mov     rdi, rcx
0x180001586  xor     edx, edx; Val
0x180001588  lea     rcx, [rbp+57h+pmmioinfo]; void *
0x18000158c  lea     r8d, [rdx+64h]; Size
0x180001590  call    memset_0
0x180001595  lea     rdx, [rbp+57h+pmmioinfo]
0x180001599  mov     rcx, rdi
0x18000159c  call    InitMMIOOpen
0x1800015a1  xor     r14d, r14d
0x1800015a4  cmp     [rdi+98h], r14
0x1800015ab  jz      loc_1800016AA
0x1800015b1  mov     [rbx], r14w
0x1800015b5  mov     rbx, [rdi+98h]
0x1800015bc  mov     r8d, 1022h; fdwOpen
0x1800015c2  lea     rdx, [rbp+57h+pmmioinfo]; pmmioinfo
0x1800015c6  mov     rcx, rbx; pszFileName
0x1800015c9  call    cs:__imp_mmioOpenW
0x1800015cf  mov     rsi, rax
0x1800015d2  test    rax, rax
0x1800015d5  jz      loc_180001730
0x1800015db  mov     edx, [rdi+0A0h]
0x1800015e1  mov     eax, [rdi+4Ch]
0x1800015e4  add     eax, 14h
0x1800015e7  mov     [rbp+57h+pmmcki.ckid], r14d
0x1800015eb  add     eax, edx
0x1800015ed  mov     qword ptr [rbp+57h+pmmcki.dwDataOffset], r14
0x1800015f1  mov     [rbp+57h+pmmcki.cksize], eax
0x1800015f4  test    dl, 1
0x1800015f7  jz      short loc_1800015FE
0x1800015f9  inc     eax
0x1800015fb  mov     [rbp+57h+pmmcki.cksize], eax
0x1800015fe  mov     r8d, 20h ; ' '; fuCreate
0x180001604  mov     [rbp+57h+pmmcki.fccType], 45564157h
0x18000160b  lea     rdx, [rbp+57h+pmmcki]; pmmcki
0x18000160f  mov     rcx, rsi; hmmio
0x180001612  call    cs:__imp_mmioCreateChunk
0x180001618  test    eax, eax
0x18000161a  jnz     loc_180001719
0x180001620  mov     eax, [rdi+0A0h]
0x180001626  lea     rdx, [rbp+57h+pmmcki]; pmmcki
0x18000162a  xor     r8d, r8d; fuCreate
0x18000162d  mov     [rbp+57h+pmmcki.cksize], eax
0x180001630  mov     rcx, rsi; hmmio
0x180001633  mov     [rbp+57h+pmmcki.ckid], 20746D66h
0x18000163a  call    cs:__imp_mmioCreateChunk
0x180001640  test    eax, eax
0x180001642  jnz     loc_180001719
0x180001648  mov     ebx, [rdi+0A0h]
0x18000164e  mov     rcx, rsi; hmmio
0x180001651  mov     rdx, [rdi+0A8h]; pch
0x180001658  mov     r8d, ebx; cch
0x18000165b  call    cs:__imp_mmioWrite
0x180001661  cmp     eax, ebx
0x180001663  jnz     loc_180001719
0x180001669  xor     r8d, r8d; fuAscend
0x18000166c  lea     rdx, [rbp+57h+pmmcki]; pmmcki
0x180001670  mov     rcx, rsi; hmmio
0x180001673  call    cs:__imp_mmioAscend
0x180001679  test    eax, eax
0x18000167b  jnz     loc_180001719
0x180001681  mov     eax, [rdi+4Ch]
0x180001684  lea     rdx, [rbp+57h+pmmcki]; pmmcki
0x180001688  xor     r8d, r8d; fuCreate
0x18000168b  mov     [rbp+57h+pmmcki.cksize], eax
0x18000168e  mov     rcx, rsi; hmmio
0x180001691  mov     [rbp+57h+pmmcki.ckid], 61746164h
0x180001698  call    cs:__imp_mmioCreateChunk
0x18000169e  test    eax, eax
0x1800016a0  jnz     short loc_180001719
0x1800016a2  mov     rax, rsi
0x1800016a5  jmp     loc_18000173C
0x1800016aa  mov     ecx, 7FFFFFFEh
0x1800016af  lea     r8, [rdi+100h]
0x1800016b6  mov     edx, 104h
0x1800016bb  mov     rax, rbx
0x1800016be  test    rcx, rcx
0x1800016c1  jz      short loc_1800016E2
0x1800016c3  movzx   r9d, word ptr [r8]
0x1800016c7  test    r9w, r9w
0x1800016cb  jz      short loc_1800016E2
0x1800016cd  mov     [rax], r9w
0x1800016d1  add     r8, 2
0x1800016d5  add     rax, 2
0x1800016d9  dec     rcx
0x1800016dc  sub     rdx, 1
0x1800016e0  jnz     short loc_1800016BE
0x1800016e2  test    rdx, rdx
0x1800016e5  lea     rcx, [rax-2]
0x1800016e9  mov     r8d, 20000h; fdwOpen
0x1800016ef  lea     rdx, [rbp+57h+pmmioinfo]; pmmioinfo
0x1800016f3  cmovnz  rcx, rax
0x1800016f7  mov     [rcx], r14w
0x1800016fb  mov     rcx, rbx; pszFileName
0x1800016fe  call    cs:__imp_mmioOpenW
0x180001704  test    rax, rax
0x180001707  jnz     loc_1800015BC
0x18000170d  mov     dword ptr [rdi+8Ch], 15Dh
0x180001717  jmp     short loc_18000173A
0x180001719  xor     edx, edx; fuClose
0x18000171b  mov     dword ptr [rdi+8Ch], 15Dh
0x180001725  mov     rcx, rsi; hmmio
0x180001728  call    cs:__imp_mmioClose
0x18000172e  jmp     short loc_18000173A
0x180001730  mov     dword ptr [rdi+8Ch], 11Eh
0x18000173a  xor     eax, eax
0x18000173c  mov     rcx, [rbp+57h+var_20]
0x180001740  xor     rcx, rsp; StackCookie
0x180001743  call    __security_check_cookie
0x180001748  lea     r11, [rsp+0D0h+var_10]
0x180001750  mov     rbx, [r11+30h]
0x180001754  mov     rsi, [r11+38h]
0x180001758  mov     rsp, r11
0x18000175b  pop     r14
0x18000175d  pop     rdi
0x18000175e  pop     rbp
0x18000175f  retn
```
