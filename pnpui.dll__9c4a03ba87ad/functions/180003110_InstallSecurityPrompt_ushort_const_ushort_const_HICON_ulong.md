# InstallSecurityPrompt(ushort const *,ushort const *,HICON__ *,ulong)

- ea: `0x180003110`
- end: `0x18000343e`
- name: `?InstallSecurityPrompt@@YAHPEBG0PEAUHICON__@@K@Z`
- size: `814`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HICON, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007630`

## callees

- `0x180001254`
- `0x180002a80`
- `0x180002f00`
- `0x180003110`
- `0x180003444`
- `0x180003550`
- `0x1800037c4`
- `0x18000ccde`
- `0x18000cd10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800031a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800031a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033c7`

## string_xrefs

- `0x18000319c`: `pnpui.dll`

## pseudocode

```c
__int64 __fastcall InstallSecurityPrompt(unsigned __int16 *a1, unsigned __int16 *a2, HICON a3, unsigned int a4)
{
  char *v6; // rax
  char *v7; // rbx
  unsigned __int64 v8; // r13
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r12
  __int64 v14; // rcx
  unsigned __int16 *v15; // rcx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rcx
  OLECHAR *v23; // r14
  OLECHAR *v24; // rax
  __int64 v25; // r8
  OLECHAR *v26; // rsi
  int v27; // r15d
  unsigned int v29; // [rsp+20h] [rbp-E0h] BYREF
  int v30; // [rsp+24h] [rbp-DCh] BYREF
  HINSTANCE ModuleHandleW; // [rsp+28h] [rbp-D8h]
  HICON v32; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v33[48]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v34[48]; // [rsp+A0h] [rbp-60h] BYREF

  v29 = a4;
  v32 = a3;
  v6 = (char *)operator new(0xD0u);
  v7 = v6;
  if ( v6 )
  {
    memset_0(v6 + 32, 0, 0xB0u);
    *((_QWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &AuthDlg::`vftable';
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 1) = 0;
  }
  else
  {
    v7 = 0;
  }
  v30 = 0;
  if ( !v7 )
    return 1000;
  ModuleHandleW = GetModuleHandleW(L"pnpui.dll");
  memset_0(v34, 0, 0x5Au);
  memset_0(v33, 0, 0x5Au);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = v34;
  v11 = 45;
  v12 = 45;
  v13 = 2147483646;
  if ( v9 <= 0x28 )
  {
    v16 = 2147483646;
    do
    {
      if ( !v16 )
        break;
      if ( !*a1 )
        break;
      *v10++ = *a1++;
      --v16;
      --v12;
    }
    while ( v12 );
    v17 = v10 - 1;
    if ( v12 )
      v17 = v10;
    *v17 = 0;
  }
  else
  {
    v14 = 40;
    do
    {
      if ( !v14 )
        break;
      if ( !*a1 )
        break;
      *v10++ = *a1++;
      --v14;
      --v12;
    }
    while ( v12 );
    v15 = v10 - 1;
    if ( v12 )
      v15 = v10;
    *v15 = 0;
    StringCchCatW(v34, 0x2Du, L"...");
  }
  do
    ++v8;
  while ( a2[v8] );
  v18 = v33;
  if ( v8 <= 0x28 )
  {
    do
    {
      if ( !v13 )
        break;
      if ( !*a2 )
        break;
      *v18++ = *a2++;
      --v13;
      --v11;
    }
    while ( v11 );
    v22 = v18 - 1;
    if ( v11 )
      v22 = v18;
    *v22 = 0;
  }
  else
  {
    v19 = 40;
    v20 = 45;
    do
    {
      if ( !v19 )
        break;
      if ( !*a2 )
        break;
      *v18++ = *a2++;
      --v19;
      --v20;
    }
    while ( v20 );
    v21 = v18 - 1;
    if ( v20 )
      v21 = v18;
    *v21 = 0;
    StringCchCatW(v33, 0x2Du, L"...");
  }
  if ( !ModuleHandleW || (int)AuthDlg::Initialize((AuthDlg *)v7, ModuleHandleW, v33, v29) < 0 )
    goto LABEL_50;
  v23 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0xD4, v34);
  v24 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0xD5, v33);
  v26 = v24;
  if ( (v29 == 20 || v29 == 40) && (int)AuthDlg::SetDUIContent((AuthDlg *)v7, v23, v24, v32) < 0 )
    goto LABEL_50;
  v29 = 0;
  *((_DWORD *)v7 + 13) = *((_DWORD *)v7 + 13);
  v27 = IsolationAwareTaskDialogIndirect(v7 + 32, &v30, v25, &v29);
  if ( v23 )
    LocalFree(v23);
  if ( v26 )
    LocalFree(v26);
  if ( v27 )
  {
LABEL_50:
    (**(void (__fastcall ***)(char *, __int64))v7)(v7, 1);
    return 1000;
  }
  (**(void (__fastcall ***)(char *, __int64))v7)(v7, 1);
  if ( v30 == 1 )
    return (unsigned int)(v29 != 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x180003110  mov     [rsp-8+arg_0], rbx
0x180003115  mov     [rsp-8+arg_8], rsi
0x18000311a  push    rbp
0x18000311b  push    r12
0x18000311d  push    r13
0x18000311f  push    r14
0x180003121  push    r15
0x180003123  lea     rbp, [rsp-10h]
0x180003128  sub     rsp, 110h
0x18000312f  mov     rax, cs:__security_cookie
0x180003136  xor     rax, rsp
0x180003139  mov     [rbp+30h+var_30], rax
0x18000313d  mov     r14, rcx
0x180003140  mov     [rsp+130h+var_110], r9d
0x180003145  mov     ecx, 0D0h; Size
0x18000314a  mov     [rsp+130h+var_100], r8
0x18000314f  mov     r15, rdx
0x180003152  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003157  xor     r12d, r12d
0x18000315a  mov     rbx, rax
0x18000315d  test    rax, rax
0x180003160  jz      short loc_18000318B
0x180003162  lea     rcx, [rax+20h]; void *
0x180003166  xor     edx, edx; Val
0x180003168  mov     r8d, 0B0h; Size
0x18000316e  call    memset_0
0x180003173  lea     rax, ??_7AuthDlg@@6B@; const AuthDlg::`vftable'
0x18000317a  mov     [rbx+10h], r12
0x18000317e  mov     [rbx], rax
0x180003181  mov     [rbx+18h], r12
0x180003185  mov     [rbx+8], r12
0x180003189  jmp     short loc_18000318E
0x18000318b  mov     rbx, r12
0x18000318e  mov     [rsp+130h+var_10C], r12d
0x180003193  test    rbx, rbx
0x180003196  jz      loc_180003410
0x18000319c  lea     rcx, ModuleName; "pnpui.dll"
0x1800031a3  call    cs:__imp_GetModuleHandleW
0x1800031a9  xor     edx, edx; Val
0x1800031ab  lea     rcx, [rbp+30h+var_90]; void *
0x1800031af  mov     [rsp+130h+var_108], rax
0x1800031b4  lea     r8d, [rdx+5Ah]; Size
0x1800031b8  call    memset_0
0x1800031bd  xor     edx, edx; Val
0x1800031bf  lea     rcx, [rsp+130h+var_F0]; void *
0x1800031c4  lea     r8d, [rdx+5Ah]; Size
0x1800031c8  call    memset_0
0x1800031cd  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800031d1  mov     rcx, r13
0x1800031d4  xor     r9d, r9d
0x1800031d7  inc     rcx
0x1800031da  cmp     [r14+rcx*2], r9w
0x1800031df  jnz     short loc_1800031D7
0x1800031e1  lea     rax, [rbp+30h+var_90]
0x1800031e5  mov     esi, 2Dh ; '-'
0x1800031ea  mov     edx, esi
0x1800031ec  mov     r12d, 7FFFFFFEh
0x1800031f2  cmp     rcx, 28h ; '('
0x1800031f6  jbe     short loc_180003246
0x1800031f8  lea     ecx, [rsi-5]
0x1800031fb  test    rcx, rcx
0x1800031fe  jz      short loc_18000321F
0x180003200  movzx   r8d, word ptr [r14]
0x180003204  test    r8w, r8w
0x180003208  jz      short loc_18000321F
0x18000320a  mov     [rax], r8w
0x18000320e  add     r14, 2
0x180003212  add     rax, 2
0x180003216  dec     rcx
0x180003219  sub     rdx, 1
0x18000321d  jnz     short loc_1800031FB
0x18000321f  test    rdx, rdx
0x180003222  lea     rcx, [rax-2]
0x180003226  lea     r8, asc_18000FC70; "..."
0x18000322d  mov     rdx, rsi; unsigned __int64
0x180003230  cmovnz  rcx, rax
0x180003234  mov     [rcx], r9w
0x180003238  lea     rcx, [rbp+30h+var_90]; unsigned __int16 *
0x18000323c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003241  xor     r9d, r9d
0x180003244  jmp     short loc_18000327C
0x180003246  mov     rcx, r12
0x180003249  test    rcx, rcx
0x18000324c  jz      short loc_18000326D
0x18000324e  movzx   r8d, word ptr [r14]
0x180003252  test    r8w, r8w
0x180003256  jz      short loc_18000326D
0x180003258  mov     [rax], r8w
0x18000325c  add     r14, 2
0x180003260  add     rax, 2
0x180003264  dec     rcx
0x180003267  sub     rdx, 1
0x18000326b  jnz     short loc_180003249
0x18000326d  test    rdx, rdx
0x180003270  lea     rcx, [rax-2]
0x180003274  cmovnz  rcx, rax
0x180003278  mov     [rcx], r9w
0x18000327c  inc     r13
0x18000327f  cmp     [r15+r13*2], r9w
0x180003284  jnz     short loc_18000327C
0x180003286  lea     rax, [rsp+130h+var_F0]
0x18000328b  cmp     r13, 28h ; '('
0x18000328f  jbe     short loc_1800032E2
0x180003291  mov     ecx, 28h ; '('
0x180003296  mov     rdx, rsi
0x180003299  test    rcx, rcx
0x18000329c  jz      short loc_1800032BD
0x18000329e  movzx   r8d, word ptr [r15]
0x1800032a2  test    r8w, r8w
0x1800032a6  jz      short loc_1800032BD
0x1800032a8  mov     [rax], r8w
0x1800032ac  add     r15, 2
0x1800032b0  add     rax, 2
0x1800032b4  dec     rcx
0x1800032b7  sub     rdx, 1
0x1800032bb  jnz     short loc_180003299
0x1800032bd  test    rdx, rdx
0x1800032c0  lea     rcx, [rax-2]
0x1800032c4  lea     r8, asc_18000FC70; "..."
0x1800032cb  mov     rdx, rsi; unsigned __int64
0x1800032ce  cmovnz  rcx, rax
0x1800032d2  mov     [rcx], r9w
0x1800032d6  lea     rcx, [rsp+130h+var_F0]; unsigned __int16 *
0x1800032db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800032e0  jmp     short loc_180003313
0x1800032e2  test    r12, r12
0x1800032e5  jz      short loc_180003304
0x1800032e7  movzx   ecx, word ptr [r15]
0x1800032eb  test    cx, cx
0x1800032ee  jz      short loc_180003304
0x1800032f0  mov     [rax], cx
0x1800032f3  add     r15, 2
0x1800032f7  add     rax, 2
0x1800032fb  dec     r12
0x1800032fe  sub     rsi, 1
0x180003302  jnz     short loc_1800032E2
0x180003304  test    rsi, rsi
0x180003307  lea     rcx, [rax-2]
0x18000330b  cmovnz  rcx, rax
0x18000330f  mov     [rcx], r9w
0x180003313  mov     rsi, [rsp+130h+var_108]
0x180003318  test    rsi, rsi
0x18000331b  jz      loc_1800033FD
0x180003321  mov     r15d, [rsp+130h+var_110]
0x180003326  lea     r8, [rsp+130h+var_F0]; unsigned __int16 *
0x18000332b  mov     r9d, r15d; unsigned int
0x18000332e  mov     rdx, rsi; HINSTANCE
0x180003331  mov     rcx, rbx; this
0x180003334  call    ?Initialize@AuthDlg@@QEAAJPEAUHINSTANCE__@@PEBGK@Z; AuthDlg::Initialize(HINSTANCE__ *,ushort const *,ulong)
0x180003339  xor     r12d, r12d
0x18000333c  test    eax, eax
0x18000333e  js      loc_1800033FD
0x180003344  lea     r8, [rbp+30h+var_90]
0x180003348  mov     edx, 0D4h; unsigned __int16 *
0x18000334d  mov     rcx, rsi; HINSTANCE
0x180003350  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x180003355  lea     r8, [rsp+130h+var_F0]
0x18000335a  mov     edx, 0D5h; unsigned __int16 *
0x18000335f  mov     rcx, rsi; HINSTANCE
0x180003362  mov     r14, rax
0x180003365  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000336a  mov     rsi, rax
0x18000336d  cmp     r15d, 14h
0x180003371  jz      short loc_180003379
0x180003373  cmp     r15d, 28h ; '('
0x180003377  jnz     short loc_180003390
0x180003379  mov     r9, [rsp+130h+var_100]; HICON
0x18000337e  mov     r8, rsi; OLECHAR *
0x180003381  mov     rdx, r14; psz
0x180003384  mov     rcx, rbx; this
0x180003387  call    ?SetDUIContent@AuthDlg@@QEAAJPEBG0PEAUHICON__@@@Z; AuthDlg::SetDUIContent(ushort const *,ushort const *,HICON__ *)
0x18000338c  test    eax, eax
0x18000338e  js      short loc_1800033FD
0x180003390  lea     rcx, [rbx+20h]
0x180003394  mov     [rsp+130h+var_110], r12d
0x180003399  mov     eax, [rcx+14h]
0x18000339c  lea     r9, [rsp+130h+var_110]
0x1800033a1  lea     rdx, [rsp+130h+var_10C]
0x1800033a6  mov     [rbx+34h], eax
0x1800033a9  call    IsolationAwareTaskDialogIndirect
0x1800033ae  mov     r15d, eax
0x1800033b1  test    r14, r14
0x1800033b4  jz      short loc_1800033BF
0x1800033b6  mov     rcx, r14; hMem
0x1800033b9  call    cs:__imp_LocalFree
0x1800033bf  test    rsi, rsi
0x1800033c2  jz      short loc_1800033CD
0x1800033c4  mov     rcx, rsi; hMem
0x1800033c7  call    cs:__imp_LocalFree
0x1800033cd  test    r15d, r15d
0x1800033d0  jnz     short loc_1800033FD
0x1800033d2  mov     rax, [rbx]
0x1800033d5  lea     edx, [r15+1]
0x1800033d9  mov     rcx, rbx
0x1800033dc  mov     rax, [rax]
0x1800033df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e4  cmp     [rsp+130h+var_10C], 1
0x1800033e9  jnz     short loc_1800033F9
0x1800033eb  mov     eax, [rsp+130h+var_110]
0x1800033ef  neg     eax
0x1800033f1  sbb     eax, eax
0x1800033f3  neg     eax
0x1800033f5  inc     eax
0x1800033f7  jmp     short loc_180003415
0x1800033f9  xor     eax, eax
0x1800033fb  jmp     short loc_180003415
0x1800033fd  mov     rax, [rbx]
0x180003400  mov     edx, 1
0x180003405  mov     rcx, rbx
0x180003408  mov     rax, [rax]
0x18000340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003410  mov     eax, 3E8h
0x180003415  mov     rcx, [rbp+30h+var_30]
0x180003419  xor     rcx, rsp; StackCookie
0x18000341c  call    __security_check_cookie
0x180003421  lea     r11, [rsp+130h+var_20]
0x180003429  mov     rbx, [r11+30h]
0x18000342d  mov     rsi, [r11+38h]
0x180003431  mov     rsp, r11
0x180003434  pop     r15
0x180003436  pop     r14
0x180003438  pop     r13
0x18000343a  pop     r12
0x18000343c  pop     rbp
0x18000343d  retn
```
