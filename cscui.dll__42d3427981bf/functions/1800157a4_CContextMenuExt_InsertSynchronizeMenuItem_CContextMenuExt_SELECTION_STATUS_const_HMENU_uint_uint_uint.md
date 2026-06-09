# CContextMenuExt::_InsertSynchronizeMenuItem(CContextMenuExt::SELECTION_STATUS const &,HMENU__ *,uint *,uint *,uint)

- ea: `0x1800157a4`
- end: `0x180015b86`
- name: `?_InsertSynchronizeMenuItem@CContextMenuExt@@AEAAJAEBUSELECTION_STATUS@1@PEAUHMENU__@@PEAI2I@Z`
- size: `994`
- prototype: `__int64 __fastcall(CContextMenuExt *__hidden this, const struct CContextMenuExt::SELECTION_STATUS *, HMENU, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x180008a7c`
- `0x180010ff4`
- `0x18001101c`
- `0x18001569c`
- `0x1800157a4`
- `0x18004825c`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800159ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800159ca`
- `USER32!DestroyMenu` at `0x180015aec`
- `USER32!DestroyMenu` at `0x180015aec`
- `USER32!CreatePopupMenu` at `0x1800159e3`
- `USER32!CreatePopupMenu` at `0x1800159e3`
- `USER32!InsertMenuW` at `0x180015a4a`
- `USER32!InsertMenuW` at `0x180015a4a`

## pseudocode

```c
__int64 __fastcall CContextMenuExt::_InsertSynchronizeMenuItem(
        CContextMenuExt *this,
        const struct CContextMenuExt::SELECTION_STATUS *a2,
        HMENU a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6)
{
  int v6; // eax
  int Error; // ebp
  int v10; // r13d
  int v11; // r12d
  UstCommon::CImpersonator *v12; // rcx
  __int64 v13; // rdx
  UstCommon::CImpersonator *v14; // rcx
  HMENU PopupMenu; // rsi
  UINT v16; // r8d
  CContextMenuExt *v17; // rcx
  __int64 v18; // rcx
  unsigned int CountFromEnumExplorerCommand; // eax
  unsigned int v20; // ecx
  unsigned int v21; // edi
  WCHAR Buffer[264]; // [rsp+50h] [rbp-268h] BYREF

  v6 = *((_DWORD *)a2 + 5);
  Error = 0;
  if ( !v6 || (v10 = 1, v6 != *(_DWORD *)a2) )
    v10 = 0;
  if ( *((int *)a2 + 4) <= 0 && *((int *)a2 + 2) <= 0 && *((int *)a2 + 3) <= 0 || (v11 = 1, *((_DWORD *)a2 + 7)) )
    v11 = 0;
  if ( v10 && !*((_QWORD *)this + 6) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v13 = 33;
LABEL_62:
      WPP_SF_(*((_QWORD *)v12 + 2), v13, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
      return (unsigned int)Error;
    }
    return (unsigned int)Error;
  }
  if ( !v11 && !*((_QWORD *)this + 6) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v14 + 2), 37, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids, *((unsigned int *)a2 + 4));
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)v14 + 2),
              38,
              WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
              *((unsigned int *)a2 + 2));
            v14 = WPP_GLOBAL_Control;
          }
          if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)v14 + 2),
                39,
                WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
                *((unsigned int *)a2 + 3));
              v14 = WPP_GLOBAL_Control;
            }
            if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)v14 + 2),
                  40,
                  WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
                  *((unsigned int *)a2 + 7));
                v14 = WPP_GLOBAL_Control;
              }
              if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)v14 + 2),
                    41,
                    WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
                    *((unsigned int *)a2 + 8));
                  v14 = WPP_GLOBAL_Control;
                }
                if ( v14 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x40000) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)v14 + 2),
                    42,
                    WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
                    *((unsigned int *)a2 + 9));
              }
            }
          }
        }
      }
    }
    return (unsigned int)Error;
  }
  if ( *a5 + 1 > a6 )
  {
    Error = -2147024809;
LABEL_64:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
        (unsigned int)Error);
    }
    return (unsigned int)Error;
  }
  if ( !LoadStringW(g_hInstance, 0x27u, Buffer, 260) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_64;
  }
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_64;
  }
  if ( *((int *)this + 49) < 0 || !v11 || v10 )
  {
    v16 = 1026;
  }
  else
  {
    v16 = 1024;
    *((_DWORD *)this + 47) = 1;
  }
  if ( (InsertMenuW(PopupMenu, 0, v16, *a5 + 1, Buffer) || (Error = ResultFromKnownLastError(), Error >= 0))
    && (Error = CContextMenuExt::_InsertMenuItem(v17, a3, 0x29u, a4, a5, 1, 0, PopupMenu), Error >= 0) )
  {
    ++*a5;
    v18 = *((_QWORD *)this + 6);
    *((_DWORD *)this + 53) = 1;
    if ( v18 )
    {
      CountFromEnumExplorerCommand = GetCountFromEnumExplorerCommand();
      v20 = *a5;
      v21 = a6 - *a5;
      if ( CountFromEnumExplorerCommand < v21 )
        v21 = CountFromEnumExplorerCommand;
      if ( v21 )
      {
        *((_DWORD *)this + 51) = v20;
        *((_DWORD *)this + 52) = v21 + v20 - 1;
        *a5 += v21;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
        *((_QWORD *)this + 6) = 0;
      }
    }
  }
  else if ( PopupMenu )
  {
    DestroyMenu(PopupMenu);
  }
  if ( Error < 0 )
    goto LABEL_64;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    v13 = 34;
    goto LABEL_62;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800157a4  push    rbx
0x1800157a6  push    rbp
0x1800157a7  push    rsi
0x1800157a8  push    rdi
0x1800157a9  push    r12
0x1800157ab  push    r13
0x1800157ad  push    r14
0x1800157af  push    r15
0x1800157b1  sub     rsp, 278h
0x1800157b8  mov     rax, cs:__security_cookie
0x1800157bf  xor     rax, rsp
0x1800157c2  mov     [rsp+2B8h+var_58], rax
0x1800157ca  mov     eax, [rdx+14h]
0x1800157cd  xor     esi, esi
0x1800157cf  mov     r15, [rsp+2B8h+arg_20]
0x1800157d7  mov     rbx, rcx
0x1800157da  mov     [rsp+2B8h+var_278], r9
0x1800157df  mov     r14, rdx
0x1800157e2  mov     [rsp+2B8h+var_270], r8
0x1800157e7  mov     ebp, esi
0x1800157e9  lea     ecx, [rsi+1]
0x1800157ec  test    eax, eax
0x1800157ee  jz      short loc_1800157F7
0x1800157f0  mov     r13d, ecx
0x1800157f3  cmp     eax, [rdx]
0x1800157f5  jz      short loc_1800157FA
0x1800157f7  mov     r13d, esi
0x1800157fa  cmp     [rdx+10h], esi
0x1800157fd  jg      short loc_180015809
0x1800157ff  cmp     [rdx+8], esi
0x180015802  jg      short loc_180015809
0x180015804  cmp     [rdx+0Ch], esi
0x180015807  jle     short loc_180015811
0x180015809  mov     r12d, ecx
0x18001580c  cmp     [rdx+1Ch], esi
0x18001580f  jz      short loc_180015814
0x180015811  mov     r12d, esi
0x180015814  test    r13d, r13d
0x180015817  jz      short loc_18001584E
0x180015819  cmp     [rbx+30h], rsi
0x18001581d  jnz     short loc_18001584E
0x18001581f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015826  lea     rbx, WPP_GLOBAL_Control
0x18001582d  cmp     rcx, rbx
0x180015830  jz      loc_180015B60
0x180015836  mov     edi, 40000h
0x18001583b  test    [rcx+1Ch], edi
0x18001583e  jz      loc_180015B60
0x180015844  mov     edx, 21h ; '!'
0x180015849  jmp     loc_180015B18
0x18001584e  test    r12d, r12d
0x180015851  jnz     loc_18001599F
0x180015857  cmp     [rbx+30h], rsi
0x18001585b  jnz     loc_18001599F
0x180015861  mov     rcx, cs:WPP_GLOBAL_Control
0x180015868  lea     rbx, WPP_GLOBAL_Control
0x18001586f  cmp     rcx, rbx
0x180015872  jz      loc_180015B60
0x180015878  mov     edi, 40000h
0x18001587d  lea     rsi, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180015884  test    [rcx+1Ch], edi
0x180015887  jz      short loc_1800158A1
0x180015889  mov     rcx, [rcx+10h]
0x18001588d  lea     edx, [r12+24h]
0x180015892  mov     r8, rsi
0x180015895  call    WPP_SF_
0x18001589a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158a1  cmp     rcx, rbx
0x1800158a4  jz      loc_180015B60
0x1800158aa  test    [rcx+1Ch], edi
0x1800158ad  jz      short loc_1800158CB
0x1800158af  mov     r9d, [r14+10h]
0x1800158b3  mov     edx, 25h ; '%'
0x1800158b8  mov     rcx, [rcx+10h]
0x1800158bc  mov     r8, rsi
0x1800158bf  call    WPP_SF_d
0x1800158c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158cb  cmp     rcx, rbx
0x1800158ce  jz      loc_180015B60
0x1800158d4  test    [rcx+1Ch], edi
0x1800158d7  jz      short loc_1800158F5
0x1800158d9  mov     r9d, [r14+8]
0x1800158dd  mov     edx, 26h ; '&'
0x1800158e2  mov     rcx, [rcx+10h]
0x1800158e6  mov     r8, rsi
0x1800158e9  call    WPP_SF_d
0x1800158ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158f5  cmp     rcx, rbx
0x1800158f8  jz      loc_180015B60
0x1800158fe  test    [rcx+1Ch], edi
0x180015901  jz      short loc_18001591F
0x180015903  mov     r9d, [r14+0Ch]
0x180015907  mov     edx, 27h ; '''
0x18001590c  mov     rcx, [rcx+10h]
0x180015910  mov     r8, rsi
0x180015913  call    WPP_SF_d
0x180015918  mov     rcx, cs:WPP_GLOBAL_Control
0x18001591f  cmp     rcx, rbx
0x180015922  jz      loc_180015B60
0x180015928  test    [rcx+1Ch], edi
0x18001592b  jz      short loc_180015949
0x18001592d  mov     r9d, [r14+1Ch]
0x180015931  mov     edx, 28h ; '('
0x180015936  mov     rcx, [rcx+10h]
0x18001593a  mov     r8, rsi
0x18001593d  call    WPP_SF_d
0x180015942  mov     rcx, cs:WPP_GLOBAL_Control
0x180015949  cmp     rcx, rbx
0x18001594c  jz      loc_180015B60
0x180015952  test    [rcx+1Ch], edi
0x180015955  jz      short loc_180015973
0x180015957  mov     r9d, [r14+20h]
0x18001595b  mov     edx, 29h ; ')'
0x180015960  mov     rcx, [rcx+10h]
0x180015964  mov     r8, rsi
0x180015967  call    WPP_SF_d
0x18001596c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015973  cmp     rcx, rbx
0x180015976  jz      loc_180015B60
0x18001597c  test    [rcx+1Ch], edi
0x18001597f  jz      loc_180015B60
0x180015985  mov     r9d, [r14+24h]
0x180015989  mov     edx, 2Ah ; '*'
0x18001598e  mov     rcx, [rcx+10h]
0x180015992  mov     r8, rsi
0x180015995  call    WPP_SF_d
0x18001599a  jmp     loc_180015B60
0x18001599f  mov     eax, [r15]
0x1800159a2  mov     edi, [rsp+2B8h+arg_28]
0x1800159a9  add     eax, ecx
0x1800159ab  cmp     eax, edi
0x1800159ad  ja      loc_180015B2A
0x1800159b3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800159ba  lea     r8, [rsp+2B8h+Buffer]; lpBuffer
0x1800159bf  mov     r9d, 104h; cchBufferMax
0x1800159c5  mov     edx, 27h ; '''; uID
0x1800159ca  call    cs:__imp_LoadStringW
0x1800159d0  test    eax, eax
0x1800159d2  jnz     short loc_1800159E3
0x1800159d4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800159d9  mov     ebp, eax
0x1800159db  test    eax, eax
0x1800159dd  js      loc_180015B2F
0x1800159e3  call    cs:__imp_CreatePopupMenu
0x1800159e9  xor     r14d, r14d
0x1800159ec  mov     rsi, rax
0x1800159ef  test    rax, rax
0x1800159f2  jnz     short loc_180015A03
0x1800159f4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800159f9  mov     ebp, eax
0x1800159fb  test    eax, eax
0x1800159fd  js      loc_180015B2F
0x180015a03  cmp     [rbx+0C4h], r14d
0x180015a0a  jl      short loc_180015A29
0x180015a0c  test    r12d, r12d
0x180015a0f  jz      short loc_180015A29
0x180015a11  test    r13d, r13d
0x180015a14  jnz     short loc_180015A29
0x180015a16  lea     r12d, [r13+1]
0x180015a1a  mov     r8d, 400h
0x180015a20  mov     [rbx+0BCh], r12d
0x180015a27  jmp     short loc_180015A35
0x180015a29  mov     r8d, 402h; uFlags
0x180015a2f  mov     r12d, 1
0x180015a35  mov     r9d, [r15]
0x180015a38  lea     rax, [rsp+2B8h+Buffer]
0x180015a3d  add     r9d, r12d; uIDNewItem
0x180015a40  mov     [rsp+2B8h+lpNewItem], rax; lpNewItem
0x180015a45  xor     edx, edx; uPosition
0x180015a47  mov     rcx, rsi; hMenu
0x180015a4a  call    cs:__imp_InsertMenuW
0x180015a50  test    eax, eax
0x180015a52  jnz     short loc_180015A63
0x180015a54  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015a59  mov     ebp, eax
0x180015a5b  test    eax, eax
0x180015a5d  js      loc_180015AE4
0x180015a63  mov     r9, [rsp+2B8h+var_278]; unsigned int *
0x180015a68  mov     r8d, 29h ; ')'; unsigned int
0x180015a6e  mov     rdx, [rsp+2B8h+var_270]; HMENU
0x180015a73  mov     [rsp+2B8h+var_280], rsi; HMENU
0x180015a78  mov     [rsp+2B8h+var_288], r14d; int
0x180015a7d  mov     [rsp+2B8h+var_290], r12d; int
0x180015a82  mov     [rsp+2B8h+lpNewItem], r15; unsigned int *
0x180015a87  call    ?_InsertMenuItem@CContextMenuExt@@AEAAJPEAUHMENU__@@IPEAI1HH0@Z; CContextMenuExt::_InsertMenuItem(HMENU__ *,uint,uint *,uint *,int,int,HMENU__ *)
0x180015a8c  mov     ebp, eax
0x180015a8e  test    eax, eax
0x180015a90  js      short loc_180015AE4
0x180015a92  add     [r15], r12d
0x180015a95  mov     rcx, [rbx+30h]
0x180015a99  mov     [rbx+0D4h], r12d
0x180015aa0  test    rcx, rcx
0x180015aa3  jz      short loc_180015AF2
0x180015aa5  call    GetCountFromEnumExplorerCommand
0x180015aaa  mov     ecx, [r15]
0x180015aad  sub     edi, ecx
0x180015aaf  cmp     eax, edi
0x180015ab1  cmovb   edi, eax
0x180015ab4  test    edi, edi
0x180015ab6  jz      short loc_180015ACE
0x180015ab8  lea     eax, [rcx-1]
0x180015abb  mov     [rbx+0CCh], ecx
0x180015ac1  add     eax, edi
0x180015ac3  mov     [rbx+0D0h], eax
0x180015ac9  add     [r15], edi
0x180015acc  jmp     short loc_180015AF2
0x180015ace  mov     rcx, [rbx+30h]
0x180015ad2  mov     rax, [rcx]
0x180015ad5  mov     rax, [rax+10h]
0x180015ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ade  mov     [rbx+30h], r14
0x180015ae2  jmp     short loc_180015AF2
0x180015ae4  test    rsi, rsi
0x180015ae7  jz      short loc_180015AF2
0x180015ae9  mov     rcx, rsi; hMenu
0x180015aec  call    cs:__imp_DestroyMenu
0x180015af2  test    ebp, ebp
0x180015af4  js      short loc_180015B2F
0x180015af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015afd  lea     rbx, WPP_GLOBAL_Control
0x180015b04  cmp     rcx, rbx
0x180015b07  jz      short loc_180015B60
0x180015b09  mov     edi, 40000h
0x180015b0e  test    [rcx+1Ch], edi
0x180015b11  jz      short loc_180015B60
0x180015b13  mov     edx, 22h ; '"'
0x180015b18  mov     rcx, [rcx+10h]
0x180015b1c  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180015b23  call    WPP_SF_
0x180015b28  jmp     short loc_180015B60
0x180015b2a  mov     ebp, 80070057h
0x180015b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b36  lea     rbx, WPP_GLOBAL_Control
0x180015b3d  cmp     rcx, rbx
0x180015b40  jz      short loc_180015B60
0x180015b42  test    byte ptr [rcx+1Ch], 2
0x180015b46  jz      short loc_180015B60
0x180015b48  mov     rcx, [rcx+10h]
0x180015b4c  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180015b53  mov     edx, 23h ; '#'
0x180015b58  mov     r9d, ebp
0x180015b5b  call    WPP_SF_d
0x180015b60  mov     eax, ebp
0x180015b62  mov     rcx, [rsp+2B8h+var_58]
0x180015b6a  xor     rcx, rsp; StackCookie
0x180015b6d  call    __security_check_cookie
0x180015b72  add     rsp, 278h
0x180015b79  pop     r15
0x180015b7b  pop     r14
0x180015b7d  pop     r13
0x180015b7f  pop     r12
0x180015b81  pop     rdi
0x180015b82  pop     rsi
0x180015b83  pop     rbp
0x180015b84  pop     rbx
0x180015b85  retn
```
