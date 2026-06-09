# CLstBxWinHost::RemoveString(long,long)

- ea: `0x18006b628`
- end: `0x18006b9e3`
- name: `?RemoveString@CLstBxWinHost@@QEAAHJJ@Z`
- size: `955`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180068ef0`

## callees

- `0x18004ef50`
- `0x1800630f0`
- `0x180063960`
- `0x18006832c`
- `0x1800683c8`
- `0x180068e40`
- `0x18006936c`
- `0x180069b58`
- `0x18006b628`
- `0x18006d0d4`
- `0x18006d7b4`
- `0x18006dd50`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!IntersectRect` at `0x18006b8f8`
- `USER32!IntersectRect` at `0x18006b8f8`
- `USER32!InvalidateRect` at `0x18006b91f`
- `USER32!InvalidateRect` at `0x18006b91f`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::RemoveString(CLstBxWinHost *this, int a2, int a3)
{
  int v3; // r15d
  int v7; // r13d
  int v8; // esi
  int IsSelected; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  unsigned int v12; // esi
  unsigned int v13; // r12d
  _DWORD *v14; // rbx
  _DWORD *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  unsigned int i; // esi
  _DWORD *v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  int v22; // eax
  bool v23; // zf
  int v24; // edx
  HWND v25; // rcx
  int v26; // eax
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // [rsp+30h] [rbp-40h] BYREF
  struct ITextRange *v31; // [rsp+38h] [rbp-38h] BYREF
  int v32; // [rsp+40h] [rbp-30h]
  struct tagRECT rcDst; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT v34; // [rsp+58h] [rbp-18h] BYREF

  v3 = a3;
  v32 = a3;
  CLstBxWinHost::Freeze(this);
  v31 = 0;
  if ( !(unsigned int)CLstBxWinHost::GetRange(this, a2, v3, &v31) )
  {
    CLstBxWinHost::Unfreeze(this);
    return 0;
  }
  v30 = 0;
  if ( a2 )
  {
    ((void (__fastcall *)(struct ITextRange *, __int64, __int64, int *))v31->lpVtbl->MoveStart)(
      v31,
      1,
      0xFFFFFFFFLL,
      &v30);
    ((void (__fastcall *)(struct ITextRange *, __int64, __int64, int *))v31->lpVtbl->MoveEnd)(
      v31,
      1,
      0xFFFFFFFFLL,
      &v30);
  }
  if ( ((unsigned int (__fastcall *)(struct ITextRange *, __int64, _QWORD, int *))v31->lpVtbl->Delete)(v31, 1, 0, &v30)
    && *((int *)this + 48) > 1 )
  {
    CLstBxWinHost::Unfreeze(this);
    ((void (__fastcall *)(struct ITextRange *))v31->lpVtbl->Release)(v31);
    return 0;
  }
  ((void (__fastcall *)(struct ITextRange *))v31->lpVtbl->Release)(v31);
  v7 = *((_DWORD *)this + 48);
  v8 = a2 - 1;
  *((_DWORD *)this + 48) = a2 + v7 - v3 - 1;
  if ( a2 - 1 <= 0 )
    v8 = 0;
  if ( (*((_BYTE *)this + 128) & 1) == 0 )
  {
    IsSelected = CLstBxWinHost::IsSelected(this, v8);
    if ( (unsigned int)CLstBxWinHost::IsSelected(this, v3) != IsSelected || !*((_DWORD *)this + 48) )
    {
      v10 = -9999997;
      v11 = -9999997;
      if ( (unsigned int)CLstBxWinHost::IsSelected(this, v8) && *((_DWORD *)this + 48) )
      {
        v10 = *((_DWORD *)this + 37);
        v11 = *((_DWORD *)this + 38);
      }
      CLstBxWinHost::SetColors(this, v10, v11, v8, v8);
    }
  }
  v12 = v3 + 1;
  v13 = a2;
  if ( v3 + 1 < v7 )
  {
    do
    {
      v14 = (_DWORD *)CDynamicArray<CLbData>::Get((char *)this + 224, v12);
      v15 = (_DWORD *)CDynamicArray<CLbData>::operator[]((char *)this + 224, v13);
      *v15 ^= (*v14 ^ *v15) & 1;
      LODWORD(v14) = *(_DWORD *)(CDynamicArray<CLbData>::Get((char *)this + 224, v12) + 4);
      v16 = CDynamicArray<CLbData>::operator[]((char *)this + 224, v13++);
      ++v12;
      *(_DWORD *)(v16 + 4) = (_DWORD)v14;
    }
    while ( (int)v12 < v7 );
    v3 = v32;
  }
  v17 = *((_DWORD *)this + 48);
  for ( i = v12 - 1; (int)i >= v17; v17 = *((_DWORD *)this + 48) )
  {
    v19 = (_DWORD *)CDynamicArray<CLbData>::operator[]((char *)this + 224, i);
    *v19 &= ~1u;
    v20 = CDynamicArray<CLbData>::operator[]((char *)this + 224, i--);
    *(_DWORD *)(v20 + 4) = 0;
  }
  if ( v17 <= 0 )
  {
    CLstBxWinHost::SetTopViewableItem(this, 0);
    *(_QWORD *)((char *)this + 196) = -1;
  }
  else
  {
    v21 = *((_DWORD *)this + 50);
    if ( a2 <= v21 )
      --v21;
    v22 = v17 - 1;
    if ( v21 >= v22 )
      v21 = v22;
    v23 = *((_DWORD *)this + 33) == 3;
    *((_DWORD *)this + 50) = v21;
    if ( v23 )
    {
      v24 = *((_DWORD *)this + 49);
      if ( v21 < 0 || v24 >= 0 && a2 <= v24 && v24 <= v3 )
      {
        *((_DWORD *)this + 49) = -1;
        if ( v24 < v22 )
          v22 = v24;
        *((_DWORD *)this + 51) = v22;
      }
    }
    if ( (*((_BYTE *)this + 128) & 1) != 0 )
    {
      rcDst = 0;
      v34 = 0;
      CLstBxWinHost::LbGetItemRect(this, a2, &rcDst);
      CLstBxWinHost::LbGetItemRect(this, v3, &v34);
      rcDst.bottom = v34.bottom;
      if ( IntersectRect(&rcDst, &rcDst, (const RECT *)((char *)this + 164)) )
      {
        v25 = (HWND)*((_QWORD *)this + 2);
        rcDst.bottom = *((_DWORD *)this + 44);
        InvalidateRect(v25, &rcDst, 1);
      }
    }
  }
  if ( *((_DWORD *)this + 46) < *((_DWORD *)this + 45) && (*((_BYTE *)this + 128) & 8) != 0 )
  {
    v26 = *((_DWORD *)this + 47);
    if ( *((_DWORD *)this + 48) <= v26 && v7 > v26 )
      (*(void (__fastcall **)(CLstBxWinHost *, __int64, __int64))(*(_QWORD *)this + 48LL))(this, 1, 3);
  }
  CLstBxWinHost::LbDeleteItemNotify(this, a2, v3);
  v27 = *((_DWORD *)this + 48);
  if ( v27 )
  {
    v28 = *((_DWORD *)this + 31);
    v29 = v27 - 1;
    if ( v28 >= v29 )
      v28 = v29;
    CLstBxWinHost::LbShowIndex(this, v28, 0);
  }
  CLstBxWinHost::Unfreeze(this);
  return 1;
}

```

## disassembly

```asm
0x18006b628  mov     [rsp-38h+arg_18], rbx
0x18006b62d  push    rbp
0x18006b62e  push    rsi
0x18006b62f  push    rdi
0x18006b630  push    r12
0x18006b632  push    r13
0x18006b634  push    r14
0x18006b636  push    r15
0x18006b638  mov     rbp, rsp
0x18006b63b  sub     rsp, 70h
0x18006b63f  mov     rax, cs:__security_cookie
0x18006b646  xor     rax, rsp
0x18006b649  mov     [rbp+var_8], rax
0x18006b64d  mov     r15d, r8d
0x18006b650  mov     [rbp+var_30], r8d
0x18006b654  mov     r14d, edx
0x18006b657  mov     rdi, rcx
0x18006b65a  call    ?Freeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Freeze(void)
0x18006b65f  xor     r12d, r12d
0x18006b662  lea     r9, [rbp+var_38]; struct ITextRange **
0x18006b666  mov     r8d, r15d; int
0x18006b669  mov     [rbp+var_38], r12
0x18006b66d  mov     edx, r14d; int
0x18006b670  mov     rcx, rdi; this
0x18006b673  call    ?GetRange@CLstBxWinHost@@QEAAHJJPEAPEAUITextRange@@@Z; CLstBxWinHost::GetRange(long,long,ITextRange * *)
0x18006b678  test    eax, eax
0x18006b67a  jnz     short loc_18006B68B
0x18006b67c  mov     rcx, rdi; this
0x18006b67f  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x18006b684  xor     eax, eax
0x18006b686  jmp     loc_18006B9BE
0x18006b68b  or      ebx, 0FFFFFFFFh
0x18006b68e  mov     [rbp+var_40], r12d
0x18006b692  test    r14d, r14d
0x18006b695  jz      short loc_18006B6D1
0x18006b697  mov     rcx, [rbp+var_38]
0x18006b69b  lea     r9, [rbp+var_40]
0x18006b69f  mov     r8d, ebx
0x18006b6a2  lea     edx, [rbx+2]
0x18006b6a5  mov     rax, [rcx]
0x18006b6a8  mov     rax, [rax+120h]
0x18006b6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6b4  mov     rcx, [rbp+var_38]
0x18006b6b8  lea     r9, [rbp+var_40]
0x18006b6bc  mov     r8d, ebx
0x18006b6bf  lea     edx, [rbx+2]
0x18006b6c2  mov     rax, [rcx]
0x18006b6c5  mov     rax, [rax+128h]
0x18006b6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6d1  mov     rcx, [rbp+var_38]
0x18006b6d5  lea     r9, [rbp+var_40]
0x18006b6d9  xor     r8d, r8d
0x18006b6dc  mov     rax, [rcx]
0x18006b6df  lea     edx, [r8+1]
0x18006b6e3  mov     rax, [rax+178h]
0x18006b6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6ef  test    eax, eax
0x18006b6f1  jz      short loc_18006B719
0x18006b6f3  cmp     dword ptr [rdi+0C0h], 1
0x18006b6fa  jle     short loc_18006B719
0x18006b6fc  mov     rcx, rdi; this
0x18006b6ff  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x18006b704  mov     rcx, [rbp+var_38]
0x18006b708  mov     rax, [rcx]
0x18006b70b  mov     rax, [rax+10h]
0x18006b70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b714  jmp     loc_18006B684
0x18006b719  mov     rcx, [rbp+var_38]
0x18006b71d  mov     rax, [rcx]
0x18006b720  mov     rax, [rax+10h]
0x18006b724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b729  mov     r13d, [rdi+0C0h]
0x18006b730  lea     esi, [r14-1]
0x18006b734  mov     eax, r13d
0x18006b737  sub     eax, r15d
0x18006b73a  dec     eax
0x18006b73c  add     eax, r14d
0x18006b73f  test    esi, esi
0x18006b741  mov     [rdi+0C0h], eax
0x18006b747  cmovle  esi, r12d
0x18006b74b  test    byte ptr [rdi+80h], 1
0x18006b752  jnz     short loc_18006B7B8
0x18006b754  mov     edx, esi; int
0x18006b756  mov     rcx, rdi; this
0x18006b759  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x18006b75e  mov     edx, r15d; int
0x18006b761  mov     rcx, rdi; this
0x18006b764  mov     ebx, eax
0x18006b766  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x18006b76b  cmp     eax, ebx
0x18006b76d  jnz     short loc_18006B778
0x18006b76f  cmp     [rdi+0C0h], r12d
0x18006b776  jnz     short loc_18006B7B8
0x18006b778  mov     ebx, 0FF676983h
0x18006b77d  mov     edx, esi; int
0x18006b77f  mov     rcx, rdi; this
0x18006b782  mov     r12d, ebx
0x18006b785  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x18006b78a  test    eax, eax
0x18006b78c  jz      short loc_18006B7A4
0x18006b78e  cmp     dword ptr [rdi+0C0h], 0
0x18006b795  jz      short loc_18006B7A4
0x18006b797  mov     ebx, [rdi+94h]
0x18006b79d  mov     r12d, [rdi+98h]
0x18006b7a4  mov     r9d, esi; int
0x18006b7a7  mov     [rsp+70h+var_50], esi; int
0x18006b7ab  mov     r8d, r12d; unsigned int
0x18006b7ae  mov     edx, ebx; unsigned int
0x18006b7b0  mov     rcx, rdi; this
0x18006b7b3  call    ?SetColors@CLstBxWinHost@@IEAAHKKJJ@Z; CLstBxWinHost::SetColors(ulong,ulong,long,long)
0x18006b7b8  lea     esi, [r15+1]
0x18006b7bc  mov     r12d, r14d
0x18006b7bf  cmp     esi, r13d
0x18006b7c2  jge     short loc_18006B815
0x18006b7c4  lea     r15, [rdi+0E0h]
0x18006b7cb  mov     edx, esi
0x18006b7cd  mov     rcx, r15
0x18006b7d0  call    ?Get@?$CDynamicArray@VCLbData@@@@QEAAAEBVCLbData@@H@Z; CDynamicArray<CLbData>::Get(int)
0x18006b7d5  mov     edx, r12d
0x18006b7d8  mov     rcx, r15
0x18006b7db  mov     rbx, rax
0x18006b7de  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x18006b7e3  mov     edx, esi
0x18006b7e5  mov     ecx, [rax]
0x18006b7e7  xor     ecx, [rbx]
0x18006b7e9  and     ecx, 1
0x18006b7ec  xor     [rax], ecx
0x18006b7ee  mov     rcx, r15
0x18006b7f1  call    ?Get@?$CDynamicArray@VCLbData@@@@QEAAAEBVCLbData@@H@Z; CDynamicArray<CLbData>::Get(int)
0x18006b7f6  mov     edx, r12d
0x18006b7f9  mov     rcx, r15
0x18006b7fc  mov     ebx, [rax+4]
0x18006b7ff  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x18006b804  inc     r12d
0x18006b807  inc     esi
0x18006b809  mov     [rax+4], ebx
0x18006b80c  cmp     esi, r13d
0x18006b80f  jl      short loc_18006B7CB
0x18006b811  mov     r15d, [rbp+var_30]
0x18006b815  mov     eax, [rdi+0C0h]
0x18006b81b  dec     esi
0x18006b81d  cmp     esi, eax
0x18006b81f  jl      short loc_18006B852
0x18006b821  lea     rbx, [rdi+0E0h]
0x18006b828  mov     edx, esi
0x18006b82a  mov     rcx, rbx
0x18006b82d  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x18006b832  mov     edx, esi
0x18006b834  mov     rcx, rbx
0x18006b837  and     dword ptr [rax], 0FFFFFFFEh
0x18006b83a  call    ??A?$CDynamicArray@VCLbData@@@@QEAAAEAVCLbData@@H@Z; CDynamicArray<CLbData>::operator[](int)
0x18006b83f  dec     esi
0x18006b841  mov     dword ptr [rax+4], 0
0x18006b848  mov     eax, [rdi+0C0h]
0x18006b84e  cmp     esi, eax
0x18006b850  jge     short loc_18006B828
0x18006b852  test    eax, eax
0x18006b854  jle     loc_18006B92D
0x18006b85a  mov     ecx, [rdi+0C8h]
0x18006b860  cmp     r14d, ecx
0x18006b863  jg      short loc_18006B867
0x18006b865  dec     ecx
0x18006b867  dec     eax
0x18006b869  cmp     ecx, eax
0x18006b86b  cmovge  ecx, eax
0x18006b86e  cmp     dword ptr [rdi+84h], 3
0x18006b875  mov     [rdi+0C8h], ecx
0x18006b87b  jnz     short loc_18006B8AA
0x18006b87d  mov     edx, [rdi+0C4h]
0x18006b883  test    ecx, ecx
0x18006b885  js      short loc_18006B895
0x18006b887  test    edx, edx
0x18006b889  js      short loc_18006B8AA
0x18006b88b  cmp     r14d, edx
0x18006b88e  jg      short loc_18006B8AA
0x18006b890  cmp     edx, r15d
0x18006b893  jg      short loc_18006B8AA
0x18006b895  cmp     edx, eax
0x18006b897  mov     dword ptr [rdi+0C4h], 0FFFFFFFFh
0x18006b8a1  cmovl   eax, edx
0x18006b8a4  mov     [rdi+0CCh], eax
0x18006b8aa  test    byte ptr [rdi+80h], 1
0x18006b8b1  jz      loc_18006B942
0x18006b8b7  xorps   xmm0, xmm0
0x18006b8ba  lea     r8, [rbp+rcDst]; struct tagRECT *
0x18006b8be  xorps   xmm1, xmm1
0x18006b8c1  mov     edx, r14d; int
0x18006b8c4  mov     rcx, rdi; this
0x18006b8c7  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x18006b8cb  movups  xmmword ptr [rbp+var_18.left], xmm1
0x18006b8cf  call    ?LbGetItemRect@CLstBxWinHost@@QEAAHHPEAUtagRECT@@@Z; CLstBxWinHost::LbGetItemRect(int,tagRECT *)
0x18006b8d4  lea     r8, [rbp+var_18]; struct tagRECT *
0x18006b8d8  mov     edx, r15d; int
0x18006b8db  mov     rcx, rdi; this
0x18006b8de  call    ?LbGetItemRect@CLstBxWinHost@@QEAAHHPEAUtagRECT@@@Z; CLstBxWinHost::LbGetItemRect(int,tagRECT *)
0x18006b8e3  mov     eax, [rbp+var_18.bottom]
0x18006b8e6  lea     r8, [rdi+0A4h]; lprcSrc2
0x18006b8ed  lea     rdx, [rbp+rcDst]; lprcSrc1
0x18006b8f1  mov     [rbp+rcDst.bottom], eax
0x18006b8f4  lea     rcx, [rbp+rcDst]; lprcDst
0x18006b8f8  call    cs:__imp_IntersectRect
0x18006b8ff  nop     dword ptr [rax+rax+00h]
0x18006b904  test    eax, eax
0x18006b906  jz      short loc_18006B942
0x18006b908  mov     eax, [rdi+0B0h]
0x18006b90e  lea     rdx, [rbp+rcDst]; lpRect
0x18006b912  mov     rcx, [rdi+10h]; hWnd
0x18006b916  mov     r8d, 1; bErase
0x18006b91c  mov     [rbp+rcDst.bottom], eax
0x18006b91f  call    cs:__imp_InvalidateRect
0x18006b926  nop     dword ptr [rax+rax+00h]
0x18006b92b  jmp     short loc_18006B942
0x18006b92d  xor     edx, edx; int
0x18006b92f  mov     rcx, rdi; this
0x18006b932  call    ?SetTopViewableItem@CLstBxWinHost@@IEAAHJ@Z; CLstBxWinHost::SetTopViewableItem(long)
0x18006b937  mov     qword ptr [rdi+0C4h], 0FFFFFFFFFFFFFFFFh
0x18006b942  mov     eax, [rdi+0B4h]
0x18006b948  cmp     [rdi+0B8h], eax
0x18006b94e  jge     short loc_18006B984
0x18006b950  test    byte ptr [rdi+80h], 8
0x18006b957  jz      short loc_18006B984
0x18006b959  mov     eax, [rdi+0BCh]
0x18006b95f  cmp     [rdi+0C0h], eax
0x18006b965  jg      short loc_18006B984
0x18006b967  cmp     r13d, eax
0x18006b96a  jle     short loc_18006B984
0x18006b96c  mov     rax, [rdi]
0x18006b96f  mov     edx, 1
0x18006b974  mov     rcx, rdi
0x18006b977  mov     rax, [rax+30h]
0x18006b97b  lea     r8d, [rdx+2]
0x18006b97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b984  mov     r8d, r15d; int
0x18006b987  mov     edx, r14d; int
0x18006b98a  mov     rcx, rdi; this
0x18006b98d  call    ?LbDeleteItemNotify@CLstBxWinHost@@QEAAXHH@Z; CLstBxWinHost::LbDeleteItemNotify(int,int)
0x18006b992  mov     ecx, [rdi+0C0h]
0x18006b998  test    ecx, ecx
0x18006b99a  jz      short loc_18006B9B1
0x18006b99c  mov     edx, [rdi+7Ch]
0x18006b99f  dec     ecx
0x18006b9a1  cmp     edx, ecx
0x18006b9a3  cmovge  edx, ecx; int
0x18006b9a6  xor     r8d, r8d; int
0x18006b9a9  mov     rcx, rdi; this
0x18006b9ac  call    ?LbShowIndex@CLstBxWinHost@@QEAAHJH@Z; CLstBxWinHost::LbShowIndex(long,int)
0x18006b9b1  mov     rcx, rdi; this
0x18006b9b4  call    ?Unfreeze@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::Unfreeze(void)
0x18006b9b9  mov     eax, 1
0x18006b9be  mov     rcx, [rbp+var_8]
0x18006b9c2  xor     rcx, rsp; StackCookie
0x18006b9c5  call    __security_check_cookie
0x18006b9ca  mov     rbx, [rsp+70h+arg_18]
0x18006b9d2  add     rsp, 70h
0x18006b9d6  pop     r15
0x18006b9d8  pop     r14
0x18006b9da  pop     r13
0x18006b9dc  pop     r12
0x18006b9de  pop     rdi
0x18006b9df  pop     rsi
0x18006b9e0  pop     rbp
0x18006b9e1  retn
```
