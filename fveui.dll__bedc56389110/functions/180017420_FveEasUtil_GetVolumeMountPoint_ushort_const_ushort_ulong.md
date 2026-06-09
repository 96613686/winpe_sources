# FveEasUtil::GetVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x180017420`
- end: `0x18001771a`
- name: `?GetVolumeMountPoint@FveEasUtil@@SAJPEBGPEAGK@Z`
- size: `762`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x180023fe4`

## callees

- `0x180001bd4`
- `0x180002028`
- `0x180002774`
- `0x1800037a0`
- `0x18000b978`
- `0x18000b9bc`
- `0x1800103b8`
- `0x18001541c`
- `0x180017420`

## import_xrefs

- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180017487`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180017487`
- `KERNEL32!GetLastError` at `0x180017495`
- `KERNEL32!GetLastError` at `0x180017495`

## pseudocode

```c
__int64 __fastcall FveEasUtil::GetVolumeMountPoint(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  WCHAR *v4; // rbx
  DWORD v5; // esi
  unsigned int i; // edi
  unsigned __int64 v7; // rax
  WCHAR *v8; // rsi
  int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int KnownLastErrorHR; // eax
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rbp
  unsigned int v16; // r14d
  unsigned int v17; // eax
  PVOID *v18; // r11
  PVOID v19; // rcx
  unsigned __int64 v20; // rcx
  WCHAR *v22; // [rsp+20h] [rbp-48h] BYREF
  DWORD cchReturnLength; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp+20h] BYREF

  v24 = 0;
  cchReturnLength = 0;
  v4 = 0;
  v22 = 0;
  v5 = 0;
  memset_0(a2, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( i == 3 )
      {
        v12 = 2147549183LL;
        v9 = -2147418113;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_51;
        v11 = 114;
        goto LABEL_49;
      }
      goto LABEL_27;
    }
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v4, v5, &cchReturnLength) )
      break;
    if ( GetLastError() != 234 )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v9 = KnownLastErrorHR;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_51;
      v11 = 112;
LABEL_48:
      v12 = KnownLastErrorHR;
      goto LABEL_49;
    }
    if ( cchReturnLength <= 1 )
    {
      v9 = 0;
      goto LABEL_51;
    }
    v7 = 2LL * cchReturnLength;
    v8 = v4;
    if ( !is_mul_ok(cchReturnLength, 2u) )
      v7 = -1;
    v22 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v22;
    if ( v8 )
      operator delete(v8);
    if ( !v22 )
    {
      v9 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_51;
      v11 = 113;
      v12 = 2147942414LL;
LABEL_49:
      v19 = (PVOID)v10[2];
LABEL_50:
      WPP_SF_d(v19, v11, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v12);
      goto LABEL_51;
    }
    v5 = cchReturnLength;
  }
  if ( !v4 )
  {
    v12 = 2147549183LL;
    v9 = -2147418113;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_51;
    v11 = 111;
    goto LABEL_49;
  }
LABEL_27:
  v14 = 0;
  v15 = 0;
  v16 = 260;
  while ( v15 < v5 )
  {
    v17 = StringCchLengthW(&v4[v15], v5 - v15, &v24);
    v9 = v17;
    if ( v17 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
      {
        WPP_SF_d(v18[2], 115, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v17);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 < 0 )
        goto LABEL_51;
    }
    if ( !v24 )
      break;
    if ( v24 < v16 )
    {
      if ( v24 > 0xFFFFFFFF )
      {
        v9 = -2147024362;
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
        {
          v19 = v18[2];
          v11 = 116;
          v12 = 2147942934LL;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      v16 = v24;
      v14 = v15;
    }
    v15 += v24;
  }
  v20 = v14 + v16;
  if ( v4[v20 - 1] == 92 )
    v4[v20 - 1] = 0;
  KnownLastErrorHR = StringCchCopyW(a2, 0x104u, &v4[v14]);
  v9 = KnownLastErrorHR;
  if ( KnownLastErrorHR )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 117;
      goto LABEL_48;
    }
  }
LABEL_51:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>((void **)&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017420  mov     rax, rsp
0x180017423  mov     [rax+8], rbx
0x180017427  mov     [rax+18h], r8d
0x18001742b  push    rbp
0x18001742c  push    rsi
0x18001742d  push    rdi
0x18001742e  push    r12
0x180017430  push    r13
0x180017432  push    r14
0x180017434  push    r15
0x180017436  sub     rsp, 30h
0x18001743a  mov     r13, rdx
0x18001743d  mov     qword ptr [rax+20h], 0
0x180017445  mov     rbp, rcx
0x180017448  mov     dword ptr [rax+18h], 0
0x18001744f  xor     ebx, ebx
0x180017451  mov     rcx, r13; void *
0x180017454  xor     edx, edx; Val
0x180017456  mov     [rax-48h], rbx
0x18001745a  mov     r8d, 208h; Size
0x180017460  xor     esi, esi
0x180017462  call    memset_0
0x180017467  xor     edi, edi
0x180017469  lea     r14d, [rbx+2]
0x18001746d  cmp     edi, 3
0x180017470  jnb     loc_1800175AC
0x180017476  lea     r9, [rsp+68h+cchReturnLength]; lpcchReturnLength
0x18001747e  mov     r8d, esi; cchBufferLength
0x180017481  mov     rdx, rbx; lpszVolumePathNames
0x180017484  mov     rcx, rbp; lpszVolumeName
0x180017487  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18001748d  test    eax, eax
0x18001748f  jnz     loc_180017575
0x180017495  call    cs:__imp_GetLastError
0x18001749b  cmp     eax, 0EAh
0x1800174a0  jnz     loc_180017543
0x1800174a6  cmp     [rsp+68h+cchReturnLength], 1
0x1800174ae  jbe     loc_18001753C
0x1800174b4  mov     ecx, [rsp+68h+cchReturnLength]
0x1800174bb  mov     rax, r14
0x1800174be  mul     rcx
0x1800174c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800174c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800174cf  mov     rsi, rbx
0x1800174d2  cmovb   rax, rcx
0x1800174d6  mov     rcx, rax; unsigned __int64
0x1800174d9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800174de  mov     [rsp+68h+var_48], rax
0x1800174e3  mov     rbx, rax
0x1800174e6  test    rsi, rsi
0x1800174e9  jz      short loc_1800174F6
0x1800174eb  mov     rdx, r14; unsigned __int64
0x1800174ee  mov     rcx, rsi; void *
0x1800174f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800174f6  test    rbx, rbx
0x1800174f9  jz      short loc_180017509
0x1800174fb  mov     esi, [rsp+68h+cchReturnLength]
0x180017502  inc     edi
0x180017504  jmp     loc_18001746D
0x180017509  mov     edi, 8007000Eh
0x18001750e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017515  lea     rsi, WPP_GLOBAL_Control
0x18001751c  cmp     rcx, rsi
0x18001751f  jz      loc_1800176F9
0x180017525  test    byte ptr [rcx+1Ch], 40h
0x180017529  jz      loc_1800176F9
0x18001752f  mov     edx, 71h ; 'q'
0x180017534  mov     r9d, edi
0x180017537  jmp     loc_1800176E9
0x18001753c  xor     edi, edi
0x18001753e  jmp     loc_1800176F9
0x180017543  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180017548  mov     edi, eax
0x18001754a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017551  lea     rsi, WPP_GLOBAL_Control
0x180017558  cmp     rcx, rsi
0x18001755b  jz      loc_1800176F9
0x180017561  test    byte ptr [rcx+1Ch], 40h
0x180017565  jz      loc_1800176F9
0x18001756b  mov     edx, 70h ; 'p'
0x180017570  jmp     loc_1800176E6
0x180017575  test    rbx, rbx
0x180017578  jnz     short loc_1800175E2
0x18001757a  mov     r9d, 8000FFFFh
0x180017580  mov     edi, r9d
0x180017583  mov     rcx, cs:WPP_GLOBAL_Control
0x18001758a  lea     rsi, WPP_GLOBAL_Control
0x180017591  cmp     rcx, rsi
0x180017594  jz      loc_1800176F9
0x18001759a  test    byte ptr [rcx+1Ch], 40h
0x18001759e  jz      loc_1800176F9
0x1800175a4  lea     edx, [rbx+6Fh]
0x1800175a7  jmp     loc_1800176E9
0x1800175ac  jnz     short loc_1800175E2
0x1800175ae  mov     r9d, 8000FFFFh
0x1800175b4  mov     edi, r9d
0x1800175b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175be  lea     rsi, WPP_GLOBAL_Control
0x1800175c5  cmp     rcx, rsi
0x1800175c8  jz      loc_1800176F9
0x1800175ce  test    byte ptr [rcx+1Ch], 40h
0x1800175d2  jz      loc_1800176F9
0x1800175d8  mov     edx, 72h ; 'r'
0x1800175dd  jmp     loc_1800176E9
0x1800175e2  mov     r11, cs:WPP_GLOBAL_Control
0x1800175e9  xor     r15d, r15d
0x1800175ec  mov     r12d, esi
0x1800175ef  xor     ebp, ebp
0x1800175f1  mov     r14d, 104h
0x1800175f7  lea     rsi, WPP_GLOBAL_Control
0x1800175fe  cmp     rbp, r12
0x180017601  jnb     loc_1800176A3
0x180017607  mov     rdx, r12
0x18001760a  lea     rcx, [rbx+rbp*2]; unsigned __int16 *
0x18001760e  sub     rdx, rbp; unsigned __int64
0x180017611  lea     r8, [rsp+68h+arg_18]; unsigned __int64 *
0x180017619  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001761e  mov     edi, eax
0x180017620  test    eax, eax
0x180017622  jz      short loc_180017657
0x180017624  cmp     r11, rsi
0x180017627  jz      short loc_18001764F
0x180017629  test    byte ptr [r11+1Ch], 40h
0x18001762e  jz      short loc_18001764F
0x180017630  mov     rcx, [r11+10h]
0x180017634  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001763b  mov     edx, 73h ; 's'
0x180017640  mov     r9d, eax
0x180017643  call    WPP_SF_d
0x180017648  mov     r11, cs:WPP_GLOBAL_Control
0x18001764f  test    edi, edi
0x180017651  js      loc_1800176F9
0x180017657  mov     rcx, [rsp+68h+arg_18]
0x18001765f  test    rcx, rcx
0x180017662  jz      short loc_1800176A3
0x180017664  mov     eax, r14d
0x180017667  cmp     rcx, rax
0x18001766a  jnb     short loc_18001767C
0x18001766c  mov     eax, 0FFFFFFFFh
0x180017671  cmp     rcx, rax
0x180017674  ja      short loc_180017684
0x180017676  mov     r14d, ecx
0x180017679  mov     r15, rbp
0x18001767c  add     rbp, rcx
0x18001767f  jmp     loc_1800175FE
0x180017684  mov     edi, 80070216h
0x180017689  cmp     r11, rsi
0x18001768c  jz      short loc_1800176F9
0x18001768e  test    byte ptr [r11+1Ch], 40h
0x180017693  jz      short loc_1800176F9
0x180017695  mov     rcx, [r11+10h]
0x180017699  mov     edx, 74h ; 't'
0x18001769e  mov     r9d, edi
0x1800176a1  jmp     short loc_1800176ED
0x1800176a3  mov     ecx, r14d
0x1800176a6  add     rcx, r15
0x1800176a9  cmp     word ptr [rbx+rcx*2-2], 5Ch ; '\'
0x1800176af  jnz     short loc_1800176B8
0x1800176b1  xor     eax, eax
0x1800176b3  mov     [rbx+rcx*2-2], ax
0x1800176b8  lea     r8, [rbx+r15*2]; unsigned __int16 *
0x1800176bc  mov     edx, 104h; unsigned __int64
0x1800176c1  mov     rcx, r13; unsigned __int16 *
0x1800176c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800176c9  mov     edi, eax
0x1800176cb  test    eax, eax
0x1800176cd  jz      short loc_1800176F9
0x1800176cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176d6  cmp     rcx, rsi
0x1800176d9  jz      short loc_1800176F9
0x1800176db  test    byte ptr [rcx+1Ch], 40h
0x1800176df  jz      short loc_1800176F9
0x1800176e1  mov     edx, 75h ; 'u'
0x1800176e6  mov     r9d, eax
0x1800176e9  mov     rcx, [rcx+10h]
0x1800176ed  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800176f4  call    WPP_SF_d
0x1800176f9  lea     rcx, [rsp+68h+var_48]
0x1800176fe  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180017703  mov     rbx, [rsp+68h+arg_0]
0x180017708  mov     eax, edi
0x18001770a  add     rsp, 30h
0x18001770e  pop     r15
0x180017710  pop     r14
0x180017712  pop     r13
0x180017714  pop     r12
0x180017716  pop     rdi
0x180017717  pop     rsi
0x180017718  pop     rbp
0x180017719  retn
```
