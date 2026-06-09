# AslEnvExpandStrings

- ea: `0x1800212e0`
- end: `0x18002174e`
- name: `AslEnvExpandStrings`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001d6a4`

## callees

- `0x1800212e0`
- `0x18003b28c`
- `0x1800510ec`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021640`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021640`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021612`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021612`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002162a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002162a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002152e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002153a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002152e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002153a`

## string_xrefs

- `0x180021600`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AslEnvExpandStrings(
        WCHAR *a1,
        _WORD *a2,
        unsigned __int64 a3,
        _WORD *a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  unsigned int v6; // r14d
  WCHAR *v7; // rbx
  _WORD *v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r13
  __int64 v11; // r8
  int v12; // edx
  WCHAR *v13; // rcx
  unsigned __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 result; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rbp
  _WORD *v19; // r15
  const wchar_t *v20; // r9
  WCHAR *v21; // r13
  WCHAR *v22; // r12
  WCHAR *v23; // r14
  WCHAR v24; // di
  WCHAR v25; // si
  WCHAR v26; // ax
  __int64 v27; // rsi
  const void *v28; // rdx
  HMODULE Library; // rax
  HMODULE v30; // rbx
  __int64 (*ProcAddress)(void); // rax
  int v32; // [rsp+20h] [rbp-78h]
  __int64 v33; // [rsp+28h] [rbp-70h]
  const wchar_t *v34; // [rsp+30h] [rbp-68h]
  unsigned __int64 v35; // [rsp+38h] [rbp-60h]
  unsigned __int64 v36; // [rsp+40h] [rbp-58h]
  _WORD *v38; // [rsp+A8h] [rbp+10h]
  unsigned __int64 v39; // [rsp+B0h] [rbp+18h]
  _WORD *v40; // [rsp+B8h] [rbp+20h]

  v40 = a4;
  v39 = a3;
  v38 = a2;
  v6 = 0;
  v7 = a1;
  v8 = a4;
  v9 = a3;
  v10 = a5;
  v11 = 0;
  v32 = 0;
  v33 = 0;
  if ( !v9 )
    goto LABEL_2;
  v35 = a5;
  do
  {
    if ( *a2 != 37 )
      goto LABEL_19;
    v17 = v9 - 1;
    v18 = 0;
    v36 = v9 - 1;
    v19 = a2 + 1;
    v34 = a2 + 1;
    v20 = a2 + 1;
    if ( v9 == 1 )
      goto LABEL_19;
    do
    {
      if ( *v19 == 37 )
        break;
      ++v19;
      ++v18;
    }
    while ( v18 < v17 );
    if ( v18 && v18 < v17 )
    {
      if ( v18 < 0xA )
        goto LABEL_28;
      if ( wcsnicmp(v20, L"systemroot", 0xAu) )
      {
        a2 = v38;
        v17 = v9 - 1;
        v20 = v34;
        v11 = v33;
LABEL_28:
        if ( !v7 )
        {
LABEL_67:
          ++v11;
          v39 = v17;
          v9 = v17;
          v19 = a2;
          goto LABEL_11;
        }
        v21 = (WCHAR *)&v20[v18];
        while ( 2 )
        {
          if ( !*v7 )
          {
            a2 = v38;
            v17 = v36;
            v8 = v40;
            v6 = v32;
            v10 = v35;
            v11 = v33;
            goto LABEL_67;
          }
          v22 = v7;
          v23 = (WCHAR *)v20;
          if ( v20 >= v21 )
          {
LABEL_36:
            if ( v23 != v21 || *v7 != 61 )
              goto LABEL_37;
            v12 = 1;
LABEL_4:
            v13 = v7;
            do
            {
              if ( (__int64)(((char *)v7 - (char *)v13) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
                break;
              ++v7;
            }
            while ( *v7 );
            if ( v12 )
            {
              v10 = v35;
              v8 = v40;
              v14 = v7 - (v13 + 1);
              if ( v14 < v35 )
              {
                v15 = v14;
                memcpy_0(v40, v13 + 1, 2 * v14);
                v6 = v32;
                goto LABEL_10;
              }
              if ( v40 && v35 )
                *v40 = 0;
              v9 = v39;
LABEL_65:
              v11 = v14 + v33;
              v9 += -2LL - v18;
              v6 = -1073741789;
              v39 = v9;
              v32 = -1073741789;
              goto LABEL_11;
            }
          }
          else
          {
            while ( *v7 )
            {
              v24 = *v7;
              v25 = RtlUpcaseUnicodeChar(*v23);
              if ( RtlUpcaseUnicodeChar(v24) == v25 )
              {
                ++v7;
                if ( ++v23 < v21 )
                  continue;
              }
              v20 = v34;
              goto LABEL_36;
            }
            v20 = v34;
LABEL_37:
            v26 = *v7;
            if ( *v7 )
            {
              while ( v26 != 61 || v7 == v22 )
              {
                v26 = v7[1];
                ++v7;
                if ( !v26 )
                  goto LABEL_40;
              }
              if ( *v7 )
              {
                v12 = 0;
                goto LABEL_4;
              }
            }
          }
LABEL_40:
          ++v7;
          continue;
        }
      }
      v27 = (__int64)Src;
      if ( !Src )
      {
        v27 = 2147352624;
        Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
        v30 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
          if ( ProcAddress )
            v27 = ProcAddress();
          FreeLibrary(v30);
        }
        Src = (void *)v27;
      }
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v27 + 2 * v14) );
      if ( v14 >= v10 )
      {
        v8 = v40;
        if ( v40 && v10 )
          *v40 = 0;
        goto LABEL_65;
      }
      v28 = (const void *)v27;
      v15 = v14;
      v8 = v40;
      memcpy_0(v40, v28, 2 * v14);
LABEL_10:
      v8[v15] = 0;
      v11 = v14 + v33;
      v8 += v14;
      v40 = v8;
      v9 = -2LL - v18 + v39;
      v10 -= v14;
      v39 = v9;
      v35 = v10;
LABEL_11:
      v7 = a1;
    }
    else
    {
LABEL_19:
      if ( v6 != -1073741789 )
      {
        if ( v10 <= 1 )
        {
          v6 = -1073741789;
          v32 = -1073741789;
        }
        else
        {
          --v10;
          *v8++ = *a2;
          v35 = v10;
          v40 = v8;
        }
      }
      ++v11;
      v19 = a2;
      v39 = --v9;
    }
    v33 = v11;
    a2 = v19 + 1;
    v38 = v19 + 1;
  }
  while ( v9 );
  if ( v6 != -1073741789 )
  {
LABEL_2:
    if ( v10 )
      *v8 = 0;
    else
      v6 = -1073741789;
  }
  result = v6;
  if ( a6 )
    *a6 = v11 + 1;
  return result;
}

```

## disassembly

```asm
0x1800212e0  mov     rax, rsp
0x1800212e3  mov     [rax+20h], r9
0x1800212e7  mov     [rax+18h], r8
0x1800212eb  mov     [rax+10h], rdx
0x1800212ef  mov     [rax+8], rcx
0x1800212f3  push    r14
0x1800212f5  sub     rsp, 90h
0x1800212fc  mov     [rax-10h], rbx
0x180021300  xor     r14d, r14d
0x180021303  mov     [rax-20h], rsi
0x180021307  mov     rbx, rcx
0x18002130a  mov     [rax-28h], rdi
0x18002130e  mov     rsi, r9
0x180021311  mov     rdi, r8
0x180021314  mov     [rax-38h], r13
0x180021318  mov     r13, [rsp+98h+arg_20]
0x180021320  xor     r8d, r8d
0x180021323  mov     [rsp+98h+var_78], r14d
0x180021328  mov     [rsp+98h+var_70], r8
0x18002132d  cmp     rdi, 1
0x180021331  jnb     loc_1800215E2
0x180021337  test    r13, r13
0x18002133a  jz      loc_180021737
0x180021340  xor     eax, eax
0x180021342  mov     [rsi], ax
0x180021345  jmp     loc_180021425
0x18002134a  xor     edx, edx
0x18002134c  mov     rcx, rbx
0x18002134f  nop
0x180021350  mov     rax, rbx
0x180021353  sub     rax, rcx
0x180021356  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002135a  cmp     rax, 0FFFEh
0x180021360  jge     short loc_18002136C
0x180021362  add     rbx, 2
0x180021366  cmp     word ptr [rbx], 0
0x18002136a  jnz     short loc_180021350
0x18002136c  test    edx, edx
0x18002136e  jz      loc_18002157B
0x180021374  mov     r13, [rsp+98h+var_60]
0x180021379  lea     rdx, [rcx+2]; Src
0x18002137d  mov     rsi, [rsp+98h+arg_18]
0x180021385  sub     rbx, rdx
0x180021388  sar     rbx, 1
0x18002138b  cmp     rbx, r13
0x18002138e  jnb     loc_180021680
0x180021394  lea     rdi, [rbx+rbx]
0x180021398  mov     rcx, rsi; void *
0x18002139b  mov     r8, rdi; Size
0x18002139e  call    memcpy_0
0x1800213a3  mov     r14d, [rsp+98h+var_78]
0x1800213a8  mov     r8, [rsp+98h+var_70]
0x1800213ad  xor     eax, eax
0x1800213af  mov     [rdi+rsi], ax
0x1800213b3  add     r8, rbx
0x1800213b6  mov     rdi, [rsp+98h+arg_10]
0x1800213be  lea     rsi, [rsi+rbx*2]
0x1800213c2  mov     rax, 0FFFFFFFFFFFFFFFEh
0x1800213c9  mov     [rsp+98h+arg_18], rsi
0x1800213d1  sub     rax, rbp
0x1800213d4  add     rdi, rax
0x1800213d7  sub     r13, rbx
0x1800213da  mov     [rsp+98h+arg_10], rdi
0x1800213e2  mov     [rsp+98h+var_60], r13
0x1800213e7  mov     rbx, [rsp+98h+arg_0]
0x1800213ef  mov     [rsp+98h+var_70], r8
0x1800213f4  lea     rdx, [r15+2]
0x1800213f8  mov     [rsp+98h+arg_8], rdx
0x180021400  cmp     rdi, 1
0x180021404  jnb     short loc_180021460
0x180021406  mov     r15, [rsp+98h+var_40]
0x18002140b  mov     r12, [rsp+98h+var_30]
0x180021410  mov     rbp, [rsp+98h+var_18]
0x180021418  cmp     r14d, 0C0000023h
0x18002141f  jnz     loc_180021337
0x180021425  mov     rdx, [rsp+98h+arg_28]
0x18002142d  mov     eax, r14d
0x180021430  mov     r13, [rsp+98h+var_38]
0x180021435  mov     rdi, [rsp+98h+var_28]
0x18002143a  mov     rsi, [rsp+98h+var_20]
0x18002143f  mov     rbx, [rsp+98h+var_10]
0x180021447  test    rdx, rdx
0x18002144a  jnz     loc_180021742
0x180021450  add     rsp, 90h
0x180021457  pop     r14
0x180021459  retn
0x180021460  movzx   eax, word ptr [rdx]
0x180021463  cmp     ax, 25h ; '%'
0x180021467  jnz     short loc_180021485
0x180021469  lea     rcx, [rdi-1]
0x18002146d  xor     ebp, ebp
0x18002146f  mov     [rsp+98h+var_58], rcx
0x180021474  lea     r15, [rdx+2]
0x180021478  mov     [rsp+98h+var_68], r15
0x18002147d  mov     r9, r15
0x180021480  test    rcx, rcx
0x180021483  jnz     short loc_1800214A8
0x180021485  cmp     r14d, 0C0000023h
0x18002148c  jnz     loc_180021705
0x180021492  inc     r8
0x180021495  mov     r15, rdx
0x180021498  dec     rdi
0x18002149b  mov     [rsp+98h+arg_10], rdi
0x1800214a3  jmp     loc_1800213EF
0x1800214a8  cmp     word ptr [r15], 25h ; '%'
0x1800214ad  jz      short loc_1800214BB
0x1800214af  add     r15, 2
0x1800214b3  inc     rbp
0x1800214b6  cmp     rbp, rcx
0x1800214b9  jb      short loc_1800214A8
0x1800214bb  test    rbp, rbp
0x1800214be  jz      short loc_180021485
0x1800214c0  cmp     rbp, rcx
0x1800214c3  jnb     short loc_180021485
0x1800214c5  cmp     rbp, 0Ah
0x1800214c9  jb      short loc_1800214FF
0x1800214cb  mov     r8d, 0Ah; MaxCount
0x1800214d1  lea     rdx, aSystemroot_1; "systemroot"
0x1800214d8  mov     rcx, r9; String1
0x1800214db  call    _wcsnicmp
0x1800214e0  test    eax, eax
0x1800214e2  jz      loc_180021598
0x1800214e8  mov     rdx, [rsp+98h+arg_8]
0x1800214f0  mov     rcx, [rsp+98h+var_58]
0x1800214f5  mov     r9, [rsp+98h+var_68]
0x1800214fa  mov     r8, [rsp+98h+var_70]
0x1800214ff  test    rbx, rbx
0x180021502  jz      loc_1800216EF
0x180021508  lea     r13, [r9+rbp*2]
0x18002150c  cmp     word ptr [rbx], 0
0x180021510  jz      loc_1800216CB
0x180021516  mov     r12, rbx
0x180021519  mov     r14, r9
0x18002151c  cmp     r9, r13
0x18002151f  jnb     short loc_180021557
0x180021521  cmp     word ptr [rbx], 0
0x180021525  jz      short loc_180021581
0x180021527  movzx   ecx, word ptr [r14]; Source
0x18002152b  movzx   edi, word ptr [rbx]
0x18002152e  call    cs:__imp_RtlUpcaseUnicodeChar
0x180021534  movzx   ecx, di; Source
0x180021537  movzx   esi, ax
0x18002153a  call    cs:__imp_RtlUpcaseUnicodeChar
0x180021540  cmp     ax, si
0x180021543  jnz     short loc_180021552
0x180021545  add     rbx, 2
0x180021549  add     r14, 2
0x18002154d  cmp     r14, r13
0x180021550  jb      short loc_180021521
0x180021552  mov     r9, [rsp+98h+var_68]
0x180021557  cmp     r14, r13
0x18002155a  jz      loc_18002166C
0x180021560  movzx   eax, word ptr [rbx]
0x180021563  test    ax, ax
0x180021566  jz      short loc_18002157B
0x180021568  cmp     ax, 3Dh ; '='
0x18002156c  jz      short loc_180021588
0x18002156e  movzx   eax, word ptr [rbx+2]
0x180021572  add     rbx, 2
0x180021576  test    ax, ax
0x180021579  jnz     short loc_180021568
0x18002157b  add     rbx, 2
0x18002157f  jmp     short loc_18002150C
0x180021581  mov     r9, [rsp+98h+var_68]
0x180021586  jmp     short loc_180021560
0x180021588  cmp     rbx, r12
0x18002158b  jz      short loc_18002156E
0x18002158d  cmp     word ptr [rbx], 0
0x180021591  jz      short loc_18002157B
0x180021593  jmp     loc_18002134A
0x180021598  mov     rsi, cs:Src
0x18002159f  test    rsi, rsi
0x1800215a2  jz      short loc_1800215FE
0x1800215a4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800215ab  nop     dword ptr [rax+rax+00h]
0x1800215b0  inc     rbx
0x1800215b3  cmp     word ptr [rsi+rbx*2], 0
0x1800215b8  jnz     short loc_1800215B0
0x1800215ba  cmp     rbx, r13
0x1800215bd  jnb     loc_180021652
0x1800215c3  mov     rdx, rsi; Src
0x1800215c6  lea     rdi, [rbx+rbx]
0x1800215ca  mov     rsi, [rsp+98h+arg_18]
0x1800215d2  mov     r8, rdi; Size
0x1800215d5  mov     rcx, rsi; void *
0x1800215d8  call    memcpy_0
0x1800215dd  jmp     loc_1800213A8
0x1800215e2  mov     [rsp+98h+var_18], rbp
0x1800215ea  mov     [rsp+98h+var_30], r12
0x1800215ef  mov     [rsp+98h+var_40], r15
0x1800215f4  mov     [rsp+98h+var_60], r13
0x1800215f9  jmp     loc_180021460
0x1800215fe  xor     edx, edx; hFile
0x180021600  lea     rcx, LibFileName; "ntdll.dll"
0x180021607  mov     r8d, 800h; dwFlags
0x18002160d  mov     esi, 7FFE0030h
0x180021612  call    cs:__imp_LoadLibraryExW
0x180021618  mov     rbx, rax
0x18002161b  test    rax, rax
0x18002161e  jz      short loc_180021646
0x180021620  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180021627  mov     rcx, rax; hModule
0x18002162a  call    cs:__imp_GetProcAddress
0x180021630  test    rax, rax
0x180021633  jz      short loc_18002163D
0x180021635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002163a  mov     rsi, rax
0x18002163d  mov     rcx, rbx; hLibModule
0x180021640  call    cs:__imp_FreeLibrary
0x180021646  mov     cs:Src, rsi
0x18002164d  jmp     loc_1800215A4
0x180021652  mov     rsi, [rsp+98h+arg_18]
0x18002165a  test    rsi, rsi
0x18002165d  jz      short loc_180021698
0x18002165f  cmp     r13, 1
0x180021663  jb      short loc_180021698
0x180021665  xor     eax, eax
0x180021667  mov     [rsi], ax
0x18002166a  jmp     short loc_180021698
0x18002166c  cmp     word ptr [rbx], 3Dh ; '='
0x180021670  jnz     loc_180021560
0x180021676  mov     edx, 1
0x18002167b  jmp     loc_18002134C
0x180021680  test    rsi, rsi
0x180021683  jz      short loc_180021690
0x180021685  cmp     r13, 1
0x180021689  jb      short loc_180021690
0x18002168b  xor     eax, eax
0x18002168d  mov     [rsi], ax
0x180021690  mov     rdi, [rsp+98h+arg_10]
0x180021698  mov     r8, [rsp+98h+var_70]
0x18002169d  inc     rbx
0x1800216a0  dec     r8
0x1800216a3  mov     rax, 0FFFFFFFFFFFFFFFEh
0x1800216aa  add     r8, rbx
0x1800216ad  sub     rax, rbp
0x1800216b0  add     rdi, rax
0x1800216b3  mov     r14d, 0C0000023h
0x1800216b9  mov     [rsp+98h+arg_10], rdi
0x1800216c1  mov     [rsp+98h+var_78], r14d
0x1800216c6  jmp     loc_1800213E7
0x1800216cb  mov     rdx, [rsp+98h+arg_8]
0x1800216d3  mov     rcx, [rsp+98h+var_58]
0x1800216d8  mov     rsi, [rsp+98h+arg_18]
0x1800216e0  mov     r14d, [rsp+98h+var_78]
0x1800216e5  mov     r13, [rsp+98h+var_60]
0x1800216ea  mov     r8, [rsp+98h+var_70]
0x1800216ef  inc     r8
0x1800216f2  mov     [rsp+98h+arg_10], rcx
0x1800216fa  mov     rdi, rcx
0x1800216fd  mov     r15, rdx
0x180021700  jmp     loc_1800213E7
0x180021705  cmp     r13, 1
0x180021709  jbe     short loc_180021727
0x18002170b  dec     r13
0x18002170e  mov     [rsi], ax
0x180021711  add     rsi, 2
0x180021715  mov     [rsp+98h+var_60], r13
0x18002171a  mov     [rsp+98h+arg_18], rsi
0x180021722  jmp     loc_180021492
0x180021727  mov     r14d, 0C0000023h
0x18002172d  mov     [rsp+98h+var_78], r14d
0x180021732  jmp     loc_180021492
0x180021737  mov     r14d, 0C0000023h
0x18002173d  jmp     loc_180021425
0x180021742  lea     rcx, [r8+1]
0x180021746  mov     [rdx], rcx
0x180021749  jmp     loc_180021450
```
