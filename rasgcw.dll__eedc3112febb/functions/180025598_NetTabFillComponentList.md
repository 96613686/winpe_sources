# NetTabFillComponentList

- ea: `0x180025598`
- end: `0x180025728`
- name: `NetTabFillComponentList`
- size: `400`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180025a5c`

## callees

- `0x180025598`
- `0x180029348`
- `0x18002938c`
- `0x1800293c4`
- `0x18002d574`
- `0x18002d78c`
- `0x18002f382`

## import_xrefs

- `USER32!SendMessageW` at `0x18002568d`
- `USER32!SendMessageW` at `0x1800256f3`
- `USER32!SendMessageW` at `0x18002568d`
- `USER32!SendMessageW` at `0x1800256f3`

## pseudocode

```c
__int64 __fastcall NetTabFillComponentList(HWND hWnd, __int64 a2)
{
  unsigned int v4; // r14d
  int v5; // r12d
  int v6; // esi
  unsigned int i; // ebx
  int *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rax
  int lParam; // [rsp+20h] [rbp-99h] BYREF
  unsigned int lParam_4; // [rsp+24h] [rbp-95h] BYREF
  __int64 v15; // [rsp+38h] [rbp-81h]
  int v16; // [rsp+40h] [rbp-79h]
  int v17; // [rsp+44h] [rbp-75h]
  LPARAM v18; // [rsp+80h] [rbp-39h] BYREF
  int v19; // [rsp+8Ch] [rbp-2Dh]
  int v20; // [rsp+90h] [rbp-29h]
  int v21; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v22; // [rsp+130h] [rbp+77h] BYREF

  v22 = 0;
  v21 = 0;
  if ( !a2 )
    return 87;
  v4 = *(_DWORD *)(a2 + 16);
  v5 = 0;
  v6 = 0;
  memset_0(&lParam_4, 0, 0x54u);
  lParam = 3;
  for ( i = 0; i < v4; ++i )
  {
    if ( i < *(_DWORD *)(a2 + 16) )
    {
      v8 = *(int **)(*(_QWORD *)(a2 + 24) + 8LL * i);
      v5 = *v8;
      if ( !v8[8] || (v6 = 1, v8[12]) )
        v6 = 0;
    }
    netDbGetEnable(a2, i, &v21);
    netDbGetName(a2, v9, &v22);
    if ( v5 == 1 )
    {
      v10 = 1;
    }
    else if ( v5 == 2 )
    {
      v10 = 2;
    }
    else
    {
      v10 = 0;
    }
    v17 = v10;
    v11 = -1;
    v15 = v22;
    lParam_4 = i;
    do
      ++v11;
    while ( *(_WORD *)(v22 + 2 * v11) );
    v16 = v11 + 1;
    SendMessageW(hWnd, 0x104Du, 0, (LPARAM)&lParam);
    ListView_SetCheck(hWnd);
    if ( !v6 || (unsigned int)netDbIsReadOnly(a2) )
    {
      memset_0(&v18, 0, 0x58u);
      v20 = 61440;
      v19 = (unsigned int)ListView_GetCheck(hWnd, i) != 0 ? 0x4000 : 12288;
      SendMessageW(hWnd, 0x102Bu, (int)i, (LPARAM)&v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025598  mov     [rsp-8+arg_0], rbx
0x18002559d  push    rbp
0x18002559e  push    rsi
0x18002559f  push    rdi
0x1800255a0  push    r12
0x1800255a2  push    r13
0x1800255a4  push    r14
0x1800255a6  push    r15
0x1800255a8  lea     rbp, [rsp-27h]
0x1800255ad  sub     rsp, 0E0h
0x1800255b4  xor     r13d, r13d
0x1800255b7  mov     rdi, rdx
0x1800255ba  mov     [rbp+57h+arg_10], r13
0x1800255be  mov     r15, rcx
0x1800255c1  mov     [rbp+57h+arg_8], r13d
0x1800255c5  test    rdx, rdx
0x1800255c8  jz      loc_180025708
0x1800255ce  mov     r14d, [rdx+10h]
0x1800255d2  lea     r8d, [r13+54h]; Size
0x1800255d6  xor     edx, edx; Val
0x1800255d8  lea     rcx, [rsp+110h+lParam+4]; void *
0x1800255dd  mov     r12d, r13d
0x1800255e0  mov     esi, r13d
0x1800255e3  call    memset_0
0x1800255e8  mov     [rsp+110h+lParam], 3
0x1800255f0  mov     ebx, r13d
0x1800255f3  test    r14d, r14d
0x1800255f6  jz      loc_180025704
0x1800255fc  cmp     ebx, [rdi+10h]
0x1800255ff  jnb     short loc_180025622
0x180025601  mov     rax, [rdi+18h]
0x180025605  mov     edx, ebx
0x180025607  mov     rcx, [rax+rdx*8]
0x18002560b  mov     r12d, [rcx]
0x18002560e  cmp     [rcx+20h], r13d
0x180025612  jz      short loc_18002561F
0x180025614  mov     esi, 1
0x180025619  cmp     [rcx+30h], r13d
0x18002561d  jz      short loc_180025622
0x18002561f  mov     esi, r13d
0x180025622  lea     r8, [rbp+57h+arg_8]
0x180025626  mov     edx, ebx
0x180025628  mov     rcx, rdi
0x18002562b  call    netDbGetEnable
0x180025630  mov     rcx, rdi
0x180025633  lea     r8, [rbp+57h+arg_10]
0x180025637  call    netDbGetName
0x18002563c  mov     edx, r12d
0x18002563f  sub     edx, 1
0x180025642  jz      short loc_180025655
0x180025644  sub     edx, 1
0x180025647  jz      short loc_18002564E
0x180025649  mov     eax, r13d
0x18002564c  jmp     short loc_18002565A
0x18002564e  mov     eax, 2
0x180025653  jmp     short loc_18002565A
0x180025655  mov     eax, 1
0x18002565a  mov     rcx, [rbp+57h+arg_10]
0x18002565e  mov     [rbp+57h+var_CC], eax
0x180025661  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025665  mov     [rsp+110h+var_D8], rcx
0x18002566a  mov     [rsp+110h+lParam+4], ebx
0x18002566e  inc     rax
0x180025671  cmp     [rcx+rax*2], r13w
0x180025676  jnz     short loc_18002566E
0x180025678  inc     eax
0x18002567a  lea     r9, [rsp+110h+lParam]; lParam
0x18002567f  xor     r8d, r8d; wParam
0x180025682  mov     [rbp+57h+var_D0], eax
0x180025685  mov     edx, 104Dh; Msg
0x18002568a  mov     rcx, r15; hWnd
0x18002568d  call    cs:__imp_SendMessageW
0x180025693  mov     r8d, [rbp+57h+arg_8]
0x180025697  mov     edx, ebx
0x180025699  mov     rcx, r15; hWnd
0x18002569c  call    ListView_SetCheck
0x1800256a1  test    esi, esi
0x1800256a3  jz      short loc_1800256B1
0x1800256a5  mov     rcx, rdi
0x1800256a8  call    netDbIsReadOnly
0x1800256ad  test    eax, eax
0x1800256af  jz      short loc_1800256F9
0x1800256b1  xor     edx, edx; Val
0x1800256b3  lea     rcx, [rbp+57h+var_90]; void *
0x1800256b7  lea     r8d, [rdx+58h]; Size
0x1800256bb  call    memset_0
0x1800256c0  mov     edx, ebx
0x1800256c2  mov     [rbp+57h+var_80], 0F000h
0x1800256c9  mov     rcx, r15
0x1800256cc  call    ListView_GetCheck
0x1800256d1  neg     eax
0x1800256d3  movsxd  r8, ebx; wParam
0x1800256d6  lea     r9, [rbp+57h+var_90]; lParam
0x1800256da  mov     edx, 102Bh; Msg
0x1800256df  sbb     ecx, ecx
0x1800256e1  and     ecx, 1000h
0x1800256e7  add     ecx, 3000h
0x1800256ed  mov     [rbp+57h+var_84], ecx
0x1800256f0  mov     rcx, r15; hWnd
0x1800256f3  call    cs:__imp_SendMessageW
0x1800256f9  inc     ebx
0x1800256fb  cmp     ebx, r14d
0x1800256fe  jb      loc_1800255FC
0x180025704  xor     eax, eax
0x180025706  jmp     short loc_18002570D
0x180025708  mov     eax, 57h ; 'W'
0x18002570d  mov     rbx, [rsp+110h+arg_0]
0x180025715  add     rsp, 0E0h
0x18002571c  pop     r15
0x18002571e  pop     r14
0x180025720  pop     r13
0x180025722  pop     r12
0x180025724  pop     rdi
0x180025725  pop     rsi
0x180025726  pop     rbp
0x180025727  retn
```
