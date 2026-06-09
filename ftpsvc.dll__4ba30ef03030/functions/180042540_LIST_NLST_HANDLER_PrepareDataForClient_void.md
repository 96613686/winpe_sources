# LIST_NLST_HANDLER::PrepareDataForClient(void)

- ea: `0x180042540`
- end: `0x18004274d`
- name: `?PrepareDataForClient@LIST_NLST_HANDLER@@MEAAJXZ`
- size: `525`
- prototype: `__int64 __fastcall(LIST_NLST_HANDLER *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x180033c70`
- `0x180042540`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004265d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800426f0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004271c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004265d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800426f0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004271c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180042589`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180042589`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180042729`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180042729`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LIST_NLST_HANDLER::PrepareDataForClient(LIST_NLST_HANDLER *this)
{
  __int64 v2; // rax
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // r8d
  int SanitizedFullVirtualPath; // edi
  __int64 v6; // rsi
  __int64 v7; // rax
  const unsigned __int16 *v8; // rbp
  int v9; // eax
  const unsigned __int16 *v10; // rax
  unsigned __int16 *v12[4]; // [rsp+40h] [rbp-288h] BYREF
  const unsigned __int16 *v13; // [rsp+60h] [rbp-268h]
  unsigned __int16 v14[264]; // [rsp+80h] [rbp-248h] BYREF

  memset_0(v14, 0, 0x208u);
  STRU::STRU((STRU *)v12, v14, 0x104u);
  v2 = *((_QWORD *)this + 1);
  v3 = *(const unsigned __int16 **)(v2 + 344);
  v4 = *(_DWORD *)(v2 + 360);
  if ( v3 && *v3 == 45 )
  {
    ++v3;
    if ( --v4 )
    {
      while ( 1 )
      {
        switch ( *v3 )
        {
          case ' ':
            goto LABEL_17;
          case '1':
LABEL_14:
            *((_DWORD *)this + 7420) &= ~1u;
            *((_DWORD *)this + 7420) |= 2u;
            goto LABEL_15;
          case 'A':
            goto LABEL_13;
          case 'C':
            goto LABEL_14;
        }
        if ( *v3 != 70 )
          break;
        *((_DWORD *)this + 7422) = 1;
LABEL_15:
        ++v3;
        if ( !--v4 )
          goto LABEL_16;
      }
      if ( *v3 != 97 )
      {
        if ( *v3 == 108 )
          *((_DWORD *)this + 7420) = *((_DWORD *)this + 7420) & 0xFFFFFFFC | 1;
        goto LABEL_15;
      }
LABEL_13:
      *((_DWORD *)this + 7421) = 1;
      goto LABEL_15;
    }
LABEL_16:
    if ( *v3 == 32 )
    {
LABEL_17:
      ++v3;
      --v4;
    }
  }
  SanitizedFullVirtualPath = FTP_SESSION::GetSanitizedFullVirtualPath(*((FTP_SESSION **)this + 2), v3, v4, v12);
  if ( SanitizedFullVirtualPath >= 0 )
  {
    SanitizedFullVirtualPath = STRU::Copy((STRU *)(*((_QWORD *)this + 1) + 624LL), v13);
    if ( SanitizedFullVirtualPath >= 0 )
    {
      *((_DWORD *)this + 7419) = 50;
      SanitizedFullVirtualPath = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64, char *, char *, _QWORD))(**((_QWORD **)this + 4) + 96LL))(
                                   *((_QWORD *)this + 4),
                                   v13,
                                   1,
                                   (char *)this + 72,
                                   (char *)this + 29676,
                                   0);
      v6 = *((_QWORD *)this + 1);
      v7 = **((_QWORD **)this + 4);
      if ( SanitizedFullVirtualPath >= 0 )
      {
        v10 = (const unsigned __int16 *)(*(__int64 (**)(void))(v7 + 224))();
        SanitizedFullVirtualPath = STRU::Copy((STRU *)(v6 + 1184), v10);
      }
      else
      {
        v8 = (const unsigned __int16 *)(*(__int64 (**)(void))(v7 + 208))();
        v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 200LL))(*((_QWORD *)this + 4));
        if ( !*(_DWORD *)(v6 + 1096) )
        {
          *(_DWORD *)(v6 + 1096) = v9;
          STRU::Copy((STRU *)(v6 + 1112), v8);
          *(_QWORD *)(v6 + 1104) = *(_QWORD *)(v6 + 1144);
        }
      }
    }
  }
  STRU::~STRU(v12);
  return (unsigned int)SanitizedFullVirtualPath;
}

```

## disassembly

```asm
0x180042540  push    rbx
0x180042542  push    rbp
0x180042543  push    rsi
0x180042544  push    rdi
0x180042545  sub     rsp, 2A8h
0x18004254c  mov     rax, cs:__security_cookie
0x180042553  xor     rax, rsp
0x180042556  mov     [rsp+2C8h+var_38], rax
0x18004255e  mov     rbx, rcx
0x180042561  xor     edx, edx; Val
0x180042563  mov     r8d, 208h; Size
0x180042569  lea     rcx, [rsp+2C8h+var_248]; void *
0x180042571  call    memset_0
0x180042576  mov     r8d, 104h
0x18004257c  lea     rdx, [rsp+2C8h+var_248]
0x180042584  lea     rcx, [rsp+2C8h+var_288]
0x180042589  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004258f  nop
0x180042590  mov     rax, [rbx+8]
0x180042594  mov     rdx, [rax+158h]
0x18004259b  mov     r8d, [rax+168h]
0x1800425a2  mov     esi, 1
0x1800425a7  test    rdx, rdx
0x1800425aa  jz      loc_180042635
0x1800425b0  cmp     word ptr [rdx], 2Dh ; '-'
0x1800425b4  jnz     short loc_180042635
0x1800425b6  add     rdx, 2
0x1800425ba  sub     r8d, esi
0x1800425bd  mov     ecx, 0FFFFFFFFh
0x1800425c2  jz      short loc_180042628
0x1800425c4  cmp     word ptr [rdx], 20h ; ' '
0x1800425c8  jz      short loc_18004262E
0x1800425ca  cmp     word ptr [rdx], 31h ; '1'
0x1800425ce  jz      short loc_180042611
0x1800425d0  cmp     word ptr [rdx], 41h ; 'A'
0x1800425d4  jz      short loc_180042609
0x1800425d6  cmp     word ptr [rdx], 43h ; 'C'
0x1800425da  jz      short loc_180042611
0x1800425dc  cmp     word ptr [rdx], 46h ; 'F'
0x1800425e0  jz      short loc_180042601
0x1800425e2  cmp     word ptr [rdx], 61h ; 'a'
0x1800425e6  jz      short loc_180042609
0x1800425e8  cmp     word ptr [rdx], 6Ch ; 'l'
0x1800425ec  jnz     short loc_18004261F
0x1800425ee  mov     eax, [rbx+73F0h]
0x1800425f4  and     eax, 0FFFFFFFDh
0x1800425f7  or      eax, esi
0x1800425f9  mov     [rbx+73F0h], eax
0x1800425ff  jmp     short loc_18004261F
0x180042601  mov     [rbx+73F8h], esi
0x180042607  jmp     short loc_18004261F
0x180042609  mov     [rbx+73F4h], esi
0x18004260f  jmp     short loc_18004261F
0x180042611  and     dword ptr [rbx+73F0h], 0FFFFFFFEh
0x180042618  or      dword ptr [rbx+73F0h], 2
0x18004261f  add     rdx, 2
0x180042623  add     r8d, ecx
0x180042626  jnz     short loc_1800425C4
0x180042628  cmp     word ptr [rdx], 20h ; ' '
0x18004262c  jnz     short loc_180042635
0x18004262e  add     rdx, 2; unsigned __int16 *
0x180042632  add     r8d, ecx; unsigned int
0x180042635  lea     r9, [rsp+2C8h+var_288]; struct STRU *
0x18004263a  mov     rcx, [rbx+10h]; this
0x18004263e  call    ?GetSanitizedFullVirtualPath@FTP_SESSION@@QEAAJPEBGKPEAVSTRU@@@Z; FTP_SESSION::GetSanitizedFullVirtualPath(ushort const *,ulong,STRU *)
0x180042643  mov     edi, eax
0x180042645  test    eax, eax
0x180042647  js      loc_180042724
0x18004264d  mov     rcx, [rbx+8]
0x180042651  add     rcx, 270h
0x180042658  mov     rdx, [rsp+2C8h+var_268]
0x18004265d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180042663  mov     edi, eax
0x180042665  test    eax, eax
0x180042667  js      loc_180042724
0x18004266d  lea     rdx, [rbx+73ECh]
0x180042674  mov     dword ptr [rdx], 32h ; '2'
0x18004267a  mov     rcx, [rbx+20h]
0x18004267e  mov     rax, [rcx]
0x180042681  lea     r9, [rbx+48h]
0x180042685  mov     [rsp+2C8h+var_2A0], 0
0x18004268e  mov     [rsp+2C8h+var_2A8], rdx
0x180042693  mov     r8d, esi
0x180042696  mov     rdx, [rsp+2C8h+var_268]
0x18004269b  mov     rax, [rax+60h]
0x18004269f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426a4  mov     edi, eax
0x1800426a6  mov     rsi, [rbx+8]
0x1800426aa  mov     rcx, [rbx+20h]
0x1800426ae  mov     rax, [rcx]
0x1800426b1  test    edi, edi
0x1800426b3  jns     short loc_180042706
0x1800426b5  mov     rax, [rax+0D0h]
0x1800426bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426c1  mov     rbp, rax
0x1800426c4  mov     rcx, [rbx+20h]
0x1800426c8  mov     rdx, [rcx]
0x1800426cb  mov     rax, [rdx+0C8h]
0x1800426d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426d7  cmp     dword ptr [rsi+448h], 0
0x1800426de  jnz     short loc_180042724
0x1800426e0  mov     [rsi+448h], eax
0x1800426e6  lea     rcx, [rsi+458h]
0x1800426ed  mov     rdx, rbp
0x1800426f0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800426f6  mov     rax, [rsi+478h]
0x1800426fd  mov     [rsi+450h], rax
0x180042704  jmp     short loc_180042724
0x180042706  mov     rax, [rax+0E0h]
0x18004270d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042712  lea     rcx, [rsi+4A0h]
0x180042719  mov     rdx, rax
0x18004271c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180042722  mov     edi, eax
0x180042724  lea     rcx, [rsp+2C8h+var_288]
0x180042729  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004272f  mov     eax, edi
0x180042731  mov     rcx, [rsp+2C8h+var_38]
0x180042739  xor     rcx, rsp; StackCookie
0x18004273c  call    __security_check_cookie
0x180042741  add     rsp, 2A8h
0x180042748  pop     rdi
0x180042749  pop     rsi
0x18004274a  pop     rbp
0x18004274b  pop     rbx
0x18004274c  retn
```
