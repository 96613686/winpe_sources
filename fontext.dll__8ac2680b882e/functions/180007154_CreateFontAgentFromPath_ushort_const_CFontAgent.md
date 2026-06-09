# CreateFontAgentFromPath(ushort const *,CFontAgent * *)

- ea: `0x180007154`
- end: `0x1800073c9`
- name: `?CreateFontAgentFromPath@@YAJPEBGPEAPEAVCFontAgent@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CFontAgent **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007f30`

## callees

- `0x180006624`
- `0x180006e44`
- `0x180006e98`
- `0x180007154`
- `0x18001c0d0`
- `0x1800223e8`
- `0x180022564`
- `0x18002265c`
- `0x1800230fc`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000733b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000733b`

## pseudocode

```c
__int64 __fastcall CreateFontAgentFromPath(const unsigned __int16 *a1, struct CFontAgent **a2)
{
  signed int v4; // eax
  unsigned __int64 v5; // rdx
  int v6; // edi
  CFontAgent_Type1 *v7; // rbx
  struct _ITEMIDLIST *v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned __int64 v12; // rdx
  CFontAgent_General *v13; // rax
  unsigned __int64 v14; // rdx
  CFontAgent_Type1 *v15; // rax
  unsigned __int64 v16; // rdx
  CFontAgent_General *v17; // rax
  unsigned __int16 *v18; // rax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v21[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v22[384]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v23[384]; // [rsp+540h] [rbp+440h] BYREF

  *a2 = 0;
  pv = 0;
  v4 = FID_CreateFromPath(a1, (struct _ITEMIDLIST **)&pv);
  v6 = v4;
  if ( v4 >= 0 )
  {
    v7 = 0;
    memset_0(v21, 0, 0x208u);
    memset_0(v22, 0, 0x208u);
    v8 = (struct _ITEMIDLIST *)pv;
    v6 = FID_FileName((const struct _ITEMIDLIST *)pv, 0, v21);
    if ( v6 < 0 )
      goto LABEL_19;
    v9 = FID_Type(v8) - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 && v11 - 1 >= 2 )
        {
          v6 = -2147467259;
          goto LABEL_19;
        }
        v6 = FID_Description(v8, v22, 0x180u);
        if ( v6 >= 0 )
        {
          v13 = (CFontAgent_General *)DirectUI::HAllocAndZero((DirectUI *)0x758, v12);
          v7 = v13;
          if ( v13 )
          {
            CFontAgent_General::CFontAgent_General(v13, v22, v21);
            *(_QWORD *)v7 = &CFontAgent_TrueType::`vftable';
            *((_WORD *)v7 + 680) = 0;
            goto LABEL_19;
          }
LABEL_18:
          v7 = 0;
        }
      }
      else
      {
        v6 = FID_FileName(v8, 1u, v22);
        if ( v6 >= 0 )
        {
          v6 = FID_Description(v8, v23, 0x180u);
          if ( v6 >= 0 )
          {
            v15 = (CFontAgent_Type1 *)DirectUI::HAllocAndZero((DirectUI *)0x758, v14);
            if ( v15 )
              v7 = CFontAgent_Type1::CFontAgent_Type1(v15, v23, v21, v22);
          }
        }
      }
LABEL_19:
      CoTaskMemFree(v8);
      if ( v6 < 0 )
        return (unsigned int)v6;
      goto LABEL_26;
    }
    v6 = FID_Description(v8, v23, 0x180u);
    if ( v6 < 0 )
      goto LABEL_19;
    v17 = (CFontAgent_General *)DirectUI::HAllocAndZero((DirectUI *)0x550, v16);
    v7 = v17;
    if ( v17 )
    {
      CFontAgent_General::CFontAgent_General(v17, v23, v21);
      *(_QWORD *)v7 = &CFontAgent_Raster::`vftable';
      goto LABEL_19;
    }
    goto LABEL_18;
  }
  if ( v4 != -2147023266 )
    return (unsigned int)v6;
  v18 = (unsigned __int16 *)DirectUI::HAllocAndZero((DirectUI *)0x550, v5);
  v7 = (CFontAgent_Type1 *)v18;
  if ( v18 )
  {
    v18[4] = 0;
    v18[388] = 0;
    *(_QWORD *)v18 = &CFontAgent_Invalid::`vftable';
    StringCchCopyW(v18 + 420, 0x104u, a1);
  }
  else
  {
    v7 = 0;
  }
  v6 = 0;
LABEL_26:
  if ( v7 )
    *a2 = v7;
  else
    return (unsigned int)-2147024882;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007154  mov     [rsp-8+arg_10], rbx
0x180007159  mov     [rsp-8+arg_18], rsi
0x18000715e  push    rbp
0x18000715f  push    rdi
0x180007160  push    r14
0x180007162  lea     rbp, [rsp-750h]
0x18000716a  sub     rsp, 850h
0x180007171  mov     rax, cs:__security_cookie
0x180007178  xor     rax, rsp
0x18000717b  mov     [rbp+760h+var_20], rax
0x180007182  mov     r14, rdx
0x180007185  mov     qword ptr [rdx], 0
0x18000718c  lea     rdx, [rsp+860h+pv]; struct _ITEMIDLIST **
0x180007191  mov     [rsp+860h+pv], 0
0x18000719a  mov     rsi, rcx
0x18000719d  call    ?FID_CreateFromPath@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; FID_CreateFromPath(ushort const *,_ITEMIDLIST * *)
0x1800071a2  mov     edi, eax
0x1800071a4  test    eax, eax
0x1800071a6  js      loc_180007347
0x1800071ac  mov     edi, 208h
0x1800071b1  lea     rcx, [rsp+860h+var_830]; void *
0x1800071b6  mov     r8d, edi; Size
0x1800071b9  xor     edx, edx; Val
0x1800071bb  xor     ebx, ebx
0x1800071bd  call    memset_0
0x1800071c2  mov     r8d, edi; Size
0x1800071c5  lea     rcx, [rbp+760h+var_620]; void *
0x1800071cc  xor     edx, edx; Val
0x1800071ce  call    memset_0
0x1800071d3  mov     rsi, [rsp+860h+pv]
0x1800071d8  lea     r8, [rsp+860h+var_830]; unsigned __int16 *
0x1800071dd  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800071e0  xor     edx, edx; unsigned int
0x1800071e2  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x1800071e7  mov     edi, eax
0x1800071e9  test    eax, eax
0x1800071eb  js      loc_180007338
0x1800071f1  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800071f4  call    ?FID_Type@@YAKPEFBU_ITEMIDLIST@@@Z; FID_Type(_ITEMIDLIST const *)
0x1800071f9  sub     eax, 1
0x1800071fc  jz      loc_1800072E9
0x180007202  sub     eax, 1
0x180007205  jz      short loc_180007281
0x180007207  sub     eax, 1
0x18000720a  jz      short loc_180007220
0x18000720c  sub     eax, 1
0x18000720f  jz      short loc_180007220
0x180007211  cmp     eax, 1
0x180007214  jz      short loc_180007220
0x180007216  mov     edi, 80004005h
0x18000721b  jmp     loc_180007338
0x180007220  mov     r8d, 180h; unsigned __int64
0x180007226  lea     rdx, [rbp+760h+var_620]; unsigned __int16 *
0x18000722d  mov     rcx, rsi; struct _ITEMIDLIST *
0x180007230  call    ?FID_Description@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_Description(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x180007235  mov     edi, eax
0x180007237  test    eax, eax
0x180007239  js      loc_180007338
0x18000723f  mov     ecx, 758h; this
0x180007244  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180007249  mov     rbx, rax
0x18000724c  test    rax, rax
0x18000724f  jz      loc_180007336
0x180007255  lea     r8, [rsp+860h+var_830]; unsigned __int16 *
0x18000725a  mov     rcx, rax; this
0x18000725d  lea     rdx, [rbp+760h+var_620]; unsigned __int16 *
0x180007264  call    ??0CFontAgent_General@@QEAA@PEBG0@Z; CFontAgent_General::CFontAgent_General(ushort const *,ushort const *)
0x180007269  lea     rax, ??_7CFontAgent_TrueType@@6B@; const CFontAgent_TrueType::`vftable'
0x180007270  mov     [rbx], rax
0x180007273  xor     eax, eax
0x180007275  mov     [rbx+550h], ax
0x18000727c  jmp     loc_180007338
0x180007281  lea     r8, [rbp+760h+var_620]; unsigned __int16 *
0x180007288  mov     edx, 1; unsigned int
0x18000728d  mov     rcx, rsi; struct _ITEMIDLIST *
0x180007290  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x180007295  mov     edi, eax
0x180007297  test    eax, eax
0x180007299  js      loc_180007338
0x18000729f  mov     r8d, 180h; unsigned __int64
0x1800072a5  lea     rdx, [rbp+760h+var_320]; unsigned __int16 *
0x1800072ac  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800072af  call    ?FID_Description@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_Description(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x1800072b4  mov     edi, eax
0x1800072b6  test    eax, eax
0x1800072b8  js      short loc_180007338
0x1800072ba  mov     ecx, 758h; this
0x1800072bf  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800072c4  test    rax, rax
0x1800072c7  jz      short loc_180007338
0x1800072c9  lea     r9, [rbp+760h+var_620]; unsigned __int16 *
0x1800072d0  mov     rcx, rax; this
0x1800072d3  lea     r8, [rsp+860h+var_830]; unsigned __int16 *
0x1800072d8  lea     rdx, [rbp+760h+var_320]; unsigned __int16 *
0x1800072df  call    ??0CFontAgent_Type1@@QEAA@PEBG00@Z; CFontAgent_Type1::CFontAgent_Type1(ushort const *,ushort const *,ushort const *)
0x1800072e4  mov     rbx, rax
0x1800072e7  jmp     short loc_180007338
0x1800072e9  mov     r8d, 180h; unsigned __int64
0x1800072ef  lea     rdx, [rbp+760h+var_320]; unsigned __int16 *
0x1800072f6  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800072f9  call    ?FID_Description@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_Description(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x1800072fe  mov     edi, eax
0x180007300  test    eax, eax
0x180007302  js      short loc_180007338
0x180007304  mov     ecx, 550h; this
0x180007309  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000730e  mov     rbx, rax
0x180007311  test    rax, rax
0x180007314  jz      short loc_180007336
0x180007316  lea     r8, [rsp+860h+var_830]; unsigned __int16 *
0x18000731b  mov     rcx, rax; this
0x18000731e  lea     rdx, [rbp+760h+var_320]; unsigned __int16 *
0x180007325  call    ??0CFontAgent_General@@QEAA@PEBG0@Z; CFontAgent_General::CFontAgent_General(ushort const *,ushort const *)
0x18000732a  lea     rax, ??_7CFontAgent_Raster@@6B@; const CFontAgent_Raster::`vftable'
0x180007331  mov     [rbx], rax
0x180007334  jmp     short loc_180007338
0x180007336  xor     ebx, ebx
0x180007338  mov     rcx, rsi; pv
0x18000733b  call    cs:__imp_CoTaskMemFree
0x180007341  test    edi, edi
0x180007343  js      short loc_1800073A0
0x180007345  jmp     short loc_180007391
0x180007347  cmp     eax, 8007065Eh
0x18000734c  jnz     short loc_1800073A0
0x18000734e  mov     ecx, 550h; this
0x180007353  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180007358  mov     rbx, rax
0x18000735b  test    rax, rax
0x18000735e  jz      short loc_18000738D
0x180007360  xor     eax, eax
0x180007362  lea     rcx, [rbx+348h]; unsigned __int16 *
0x180007369  mov     [rbx+8], ax
0x18000736d  mov     r8, rsi; unsigned __int16 *
0x180007370  mov     [rbx+308h], ax
0x180007377  mov     edx, 104h; unsigned __int64
0x18000737c  lea     rax, ??_7CFontAgent_Invalid@@6B@; const CFontAgent_Invalid::`vftable'
0x180007383  mov     [rbx], rax
0x180007386  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000738b  jmp     short loc_18000738F
0x18000738d  xor     ebx, ebx
0x18000738f  xor     edi, edi
0x180007391  test    rbx, rbx
0x180007394  jz      short loc_18000739B
0x180007396  mov     [r14], rbx
0x180007399  jmp     short loc_1800073A0
0x18000739b  mov     edi, 8007000Eh
0x1800073a0  mov     eax, edi
0x1800073a2  mov     rcx, [rbp+760h+var_20]
0x1800073a9  xor     rcx, rsp; StackCookie
0x1800073ac  call    __security_check_cookie
0x1800073b1  lea     r11, [rsp+860h+var_10]
0x1800073b9  mov     rbx, [r11+30h]
0x1800073bd  mov     rsi, [r11+38h]
0x1800073c1  mov     rsp, r11
0x1800073c4  pop     r14
0x1800073c6  pop     rdi
0x1800073c7  pop     rbp
0x1800073c8  retn
```
