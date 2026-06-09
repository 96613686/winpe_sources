# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_Compare(IMFAttributes *,_MF_ATTRIBUTES_MATCH_TYPE,_GUID const *,uint,int *)

- ea: `0x18002f254`
- end: `0x18002f502`
- name: `?_Compare@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@QEAAJPEAUIMFAttributes@@W4_MF_ATTRIBUTES_MATCH_TYPE@@PEBU_GUID@@IPEAH@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002ab60`

## callees

- `0x180001e80`
- `0x18002f254`
- `0x18002f58c`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f29e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f29e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_Compare(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        int a5,
        _DWORD *a6)
{
  int v9; // ebx
  unsigned int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int i; // r15d
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int j; // r15d
  __int64 v18; // rax
  __int64 Item; // r8
  __int64 v20; // rax
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+34h] [rbp-1Ch] BYREF
  __int128 v24; // [rsp+38h] [rbp-18h] BYREF

  v9 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 224))(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v10 = 0;
  if ( v9 >= 0 )
  {
    if ( a3 == 4 )
    {
      v11 = *a2;
      v22 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v11 + 240))(a2, &v22);
      if ( v9 < 0 )
        goto LABEL_35;
      if ( v22 >= *(_DWORD *)(a1 + 60) )
      {
        a3 = 0;
        goto LABEL_6;
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_6;
      if ( a3 != 1 )
      {
        if ( a3 == 2 )
        {
LABEL_6:
          while ( v10 < *(_DWORD *)(a1 + 60) )
          {
            v23 = 0;
            v12 = *(_QWORD *)(a1 + 48) + 40LL * v10;
            v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, int *))(*a2 + 40))(a2, v12, v12 + 16, &v23);
            if ( v9 < 0 )
              goto LABEL_35;
            if ( !v23 )
              goto LABEL_30;
            ++v10;
          }
          if ( a3 != 2 )
            goto LABEL_34;
          v20 = *a2;
          v23 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(v20 + 240))(a2, &v23);
          if ( v9 >= 0 )
          {
            if ( v23 != *(_DWORD *)(a1 + 60) )
            {
LABEL_30:
              *a6 = 0;
              goto LABEL_35;
            }
            goto LABEL_34;
          }
        }
        else
        {
          if ( a3 == 3 )
          {
            for ( i = 0; i < *(_DWORD *)(a1 + 60); ++i )
            {
              v14 = *a2;
              v22 = 0;
              if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD))(v14 + 24))(
                     a2,
                     *(_QWORD *)(a1 + 48) + 40LL * i,
                     0) >= 0 )
              {
                v15 = *(_QWORD *)(a1 + 48) + 40LL * i;
                v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int *))(*a2 + 40))(
                       a2,
                       v15,
                       v15 + 16,
                       &v22);
                if ( v9 < 0 )
                  goto LABEL_35;
                if ( !v22 )
                {
LABEL_20:
                  *a6 = 0;
                  goto LABEL_35;
                }
              }
            }
            goto LABEL_34;
          }
          v9 = -2147024809;
        }
LABEL_35:
        (*(void (__fastcall **)(__int64 *))(*a2 + 232))(a2);
        goto LABEL_36;
      }
    }
    v16 = *a2;
    v22 = 0;
    v24 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v16 + 240))(a2, &v22);
    if ( v9 >= 0 )
    {
      for ( j = 0; j < v22; ++j )
      {
        v18 = *a2;
        v23 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *, _QWORD))(v18 + 248))(a2, j, &v24, 0);
        if ( v9 < 0 )
          goto LABEL_35;
        Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, &v24);
        if ( !Item )
          goto LABEL_20;
        v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, int *))(*a2 + 40))(a2, &v24, Item, &v23);
        if ( v9 < 0 )
          goto LABEL_35;
        if ( !v23 )
          goto LABEL_20;
      }
LABEL_34:
      *a6 = 1;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
LABEL_36:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002f254  mov     [rsp-38h+arg_10], rbx
0x18002f259  push    rbp
0x18002f25a  push    rsi
0x18002f25b  push    rdi
0x18002f25c  push    r12
0x18002f25e  push    r13
0x18002f260  push    r14
0x18002f262  push    r15
0x18002f264  mov     rbp, rsp
0x18002f267  sub     rsp, 50h
0x18002f26b  mov     rax, cs:__security_cookie
0x18002f272  xor     rax, rsp
0x18002f275  mov     [rbp+var_8], rax
0x18002f279  mov     rax, [rdx]
0x18002f27c  mov     r14, rcx
0x18002f27f  mov     rsi, [rbp+arg_28]
0x18002f283  mov     rcx, rdx
0x18002f286  mov     r15d, r8d
0x18002f289  mov     rdi, rdx
0x18002f28c  mov     rax, [rax+0E0h]
0x18002f293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f298  lea     rcx, [r14+8]; lpCriticalSection
0x18002f29c  mov     ebx, eax
0x18002f29e  call    cs:__imp_EnterCriticalSection
0x18002f2a4  xor     r12d, r12d
0x18002f2a7  test    ebx, ebx
0x18002f2a9  js      loc_18002F4D2
0x18002f2af  cmp     r15d, 4
0x18002f2b3  jnz     loc_18002F33D
0x18002f2b9  mov     rax, [rdi]
0x18002f2bc  lea     rdx, [rbp+var_20]
0x18002f2c0  mov     rcx, rdi
0x18002f2c3  mov     [rbp+var_20], r12d
0x18002f2c7  mov     rax, [rax+0F0h]
0x18002f2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2d3  mov     ebx, eax
0x18002f2d5  test    eax, eax
0x18002f2d7  js      loc_18002F4C0
0x18002f2dd  mov     eax, [r14+3Ch]
0x18002f2e1  cmp     [rbp+var_20], eax
0x18002f2e4  jb      loc_18002F3DA
0x18002f2ea  mov     r15d, r12d
0x18002f2ed  cmp     r12d, [r14+3Ch]
0x18002f2f1  jnb     loc_18002F488
0x18002f2f7  mov     eax, r12d
0x18002f2fa  lea     r9, [rbp+var_1C]
0x18002f2fe  mov     [rbp+var_1C], 0
0x18002f305  lea     rcx, [rax+rax*4]
0x18002f309  mov     rax, [r14+30h]
0x18002f30d  lea     rdx, [rax+rcx*8]
0x18002f311  mov     rax, [rdi]
0x18002f314  lea     r8, [rdx+10h]
0x18002f318  mov     rcx, rdi
0x18002f31b  mov     rax, [rax+28h]
0x18002f31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f324  mov     ebx, eax
0x18002f326  test    eax, eax
0x18002f328  js      loc_18002F4C0
0x18002f32e  cmp     [rbp+var_1C], 0
0x18002f332  jz      loc_18002F480
0x18002f338  inc     r12d
0x18002f33b  jmp     short loc_18002F2ED
0x18002f33d  mov     ecx, r15d
0x18002f340  test    r15d, r15d
0x18002f343  jz      short loc_18002F2ED
0x18002f345  sub     ecx, 1
0x18002f348  jz      loc_18002F3DA
0x18002f34e  sub     ecx, 1
0x18002f351  jz      short loc_18002F2ED
0x18002f353  cmp     ecx, 1
0x18002f356  jz      short loc_18002F362
0x18002f358  mov     ebx, 80070057h
0x18002f35d  jmp     loc_18002F4C0
0x18002f362  mov     r15d, r12d
0x18002f365  cmp     r15d, [r14+3Ch]
0x18002f369  jnb     loc_18002F4BA
0x18002f36f  mov     rcx, [rdi]
0x18002f372  xor     r8d, r8d
0x18002f375  mov     eax, r15d
0x18002f378  mov     [rbp+var_20], r12d
0x18002f37c  lea     r12, [rax+rax*4]
0x18002f380  mov     rax, [r14+30h]
0x18002f384  lea     rdx, [rax+r12*8]
0x18002f388  mov     rax, [rcx+18h]
0x18002f38c  mov     rcx, rdi
0x18002f38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f394  test    eax, eax
0x18002f396  js      short loc_18002F3D2
0x18002f398  mov     rax, [r14+30h]
0x18002f39c  lea     r9, [rbp+var_20]
0x18002f3a0  mov     rcx, rdi
0x18002f3a3  lea     rdx, [rax+r12*8]
0x18002f3a7  mov     rax, [rdi]
0x18002f3aa  lea     r8, [rdx+10h]
0x18002f3ae  mov     rax, [rax+28h]
0x18002f3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3b7  xor     r12d, r12d
0x18002f3ba  mov     ebx, eax
0x18002f3bc  test    eax, eax
0x18002f3be  js      loc_18002F4C0
0x18002f3c4  cmp     [rbp+var_20], r12d
0x18002f3c8  jnz     short loc_18002F3D5
0x18002f3ca  mov     [rsi], r12d
0x18002f3cd  jmp     loc_18002F4C0
0x18002f3d2  xor     r12d, r12d
0x18002f3d5  inc     r15d
0x18002f3d8  jmp     short loc_18002F365
0x18002f3da  mov     rax, [rdi]
0x18002f3dd  lea     rdx, [rbp+var_20]
0x18002f3e1  xorps   xmm0, xmm0
0x18002f3e4  mov     [rbp+var_20], r12d
0x18002f3e8  mov     rcx, rdi
0x18002f3eb  movups  [rbp+var_18], xmm0
0x18002f3ef  mov     rax, [rax+0F0h]
0x18002f3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3fb  mov     ebx, eax
0x18002f3fd  test    eax, eax
0x18002f3ff  js      loc_18002F4C0
0x18002f405  mov     r15d, r12d
0x18002f408  cmp     r15d, [rbp+var_20]
0x18002f40c  jnb     loc_18002F4BA
0x18002f412  mov     rax, [rdi]
0x18002f415  lea     r8, [rbp+var_18]
0x18002f419  xor     r9d, r9d
0x18002f41c  mov     [rbp+var_1C], r12d
0x18002f420  mov     edx, r15d
0x18002f423  mov     rcx, rdi
0x18002f426  mov     rax, [rax+0F8h]
0x18002f42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f432  mov     ebx, eax
0x18002f434  test    eax, eax
0x18002f436  js      loc_18002F4C0
0x18002f43c  lea     rdx, [rbp+var_18]
0x18002f440  mov     rcx, r14
0x18002f443  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18002f448  mov     r8, rax
0x18002f44b  test    rax, rax
0x18002f44e  jz      loc_18002F3CA
0x18002f454  mov     rcx, [rdi]
0x18002f457  lea     r9, [rbp+var_1C]
0x18002f45b  lea     rdx, [rbp+var_18]
0x18002f45f  mov     rax, [rcx+28h]
0x18002f463  mov     rcx, rdi
0x18002f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f46b  mov     ebx, eax
0x18002f46d  test    eax, eax
0x18002f46f  js      short loc_18002F4C0
0x18002f471  cmp     [rbp+var_1C], r12d
0x18002f475  jz      loc_18002F3CA
0x18002f47b  inc     r15d
0x18002f47e  jmp     short loc_18002F408
0x18002f480  mov     dword ptr [rsi], 0
0x18002f486  jmp     short loc_18002F4C0
0x18002f488  cmp     r15d, 2
0x18002f48c  jnz     short loc_18002F4BA
0x18002f48e  mov     rax, [rdi]
0x18002f491  lea     rdx, [rbp+var_1C]
0x18002f495  mov     rcx, rdi
0x18002f498  mov     [rbp+var_1C], 0
0x18002f49f  mov     rax, [rax+0F0h]
0x18002f4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4ab  mov     ebx, eax
0x18002f4ad  test    eax, eax
0x18002f4af  js      short loc_18002F4C0
0x18002f4b1  mov     eax, [r14+3Ch]
0x18002f4b5  cmp     [rbp+var_1C], eax
0x18002f4b8  jnz     short loc_18002F480
0x18002f4ba  mov     dword ptr [rsi], 1
0x18002f4c0  mov     rax, [rdi]
0x18002f4c3  mov     rcx, rdi
0x18002f4c6  mov     rax, [rax+0E8h]
0x18002f4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4d2  lea     rcx, [r14+8]; lpCriticalSection
0x18002f4d6  call    cs:__imp_LeaveCriticalSection
0x18002f4dc  mov     eax, ebx
0x18002f4de  mov     rcx, [rbp+var_8]
0x18002f4e2  xor     rcx, rsp; StackCookie
0x18002f4e5  call    __security_check_cookie
0x18002f4ea  mov     rbx, [rsp+50h+arg_10]
0x18002f4f2  add     rsp, 50h
0x18002f4f6  pop     r15
0x18002f4f8  pop     r14
0x18002f4fa  pop     r13
0x18002f4fc  pop     r12
0x18002f4fe  pop     rdi
0x18002f4ff  pop     rsi
0x18002f500  pop     rbp
0x18002f501  retn
```
