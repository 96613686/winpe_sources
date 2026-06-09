# CContainer::ReadReference(IStream *,IRIFFStream *,_MMCKINFO,_DMUS_OBJECTDESC *)

- ea: `0x18000f330`
- end: `0x18000f632`
- name: `?ReadReference@CContainer@@AEAAJPEAUIStream@@PEAUIRIFFStream@@U_MMCKINFO@@PEAU_DMUS_OBJECTDESC@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CContainer *__hidden this, struct IStream *, struct IRIFFStream *, struct _MMCKINFO *, struct _DMUS_OBJECTDESC *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e9e4`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x18000f330`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CContainer::ReadReference(
        CContainer *this,
        struct IStream *a2,
        struct IRIFFStream *a3,
        struct _MMCKINFO *a4,
        struct _DMUS_OBJECTDESC *a5)
{
  int v8; // edi
  struct IStreamVtbl *v9; // rax
  unsigned int v10; // eax
  struct IStreamVtbl *lpVtbl; // rax
  __int128 v12; // xmm0
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  int v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  int v20; // [rsp+48h] [rbp-38h]
  __int64 v21; // [rsp+4Ch] [rbp-34h]
  __int128 v22; // [rsp+58h] [rbp-28h] BYREF
  int v23; // [rsp+68h] [rbp-18h]

  if ( !a2 || !a3 || !a5 )
    return 2147942487LL;
  memset_0((char *)a5 + 4, 0, 0x354u);
  v8 = 0;
  *(_DWORD *)a5 = 856;
  v17 = 0;
  v19 = 0;
  v21 = 0;
LABEL_5:
  v20 = 0;
  while ( !(*(unsigned int (__fastcall **)(struct IRIFFStream *, __int64 *, struct _MMCKINFO *, _QWORD))(*(_QWORD *)a3 + 24LL))(
             a3,
             &v19,
             a4,
             0) )
  {
    switch ( (_DWORD)v19 )
    {
      case 0x64697567:
        v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
               a2,
               (char *)a5 + 8,
               16,
               &v17);
        if ( v8 >= 0 )
        {
          *((_DWORD *)a5 + 1) |= 1u;
          goto LABEL_36;
        }
        break;
      case 0x656C6966:
        v15 = HIDWORD(v19);
        if ( HIDWORD(v19) > 0x208 )
          v15 = 520;
        v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
               a2,
               (char *)a5 + 312,
               v15,
               &v17);
        if ( v8 >= 0 )
        {
          *((_WORD *)a5 + 415) = 0;
          *((_DWORD *)a5 + 1) |= 0x10u;
          goto LABEL_36;
        }
        break;
      case 0x656D616E:
        v14 = HIDWORD(v19);
        if ( HIDWORD(v19) > 0x80 )
          v14 = 128;
        v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
               a2,
               (char *)a5 + 56,
               v14,
               &v17);
        if ( v8 >= 0 )
        {
          *((_WORD *)a5 + 91) = 0;
          *((_DWORD *)a5 + 1) |= 4u;
          goto LABEL_36;
        }
        break;
      case 0x65746164:
        v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
               a2,
               (char *)a5 + 40,
               8,
               &v17);
        if ( v8 >= 0 )
        {
          *((_DWORD *)a5 + 1) |= 0x100u;
          goto LABEL_36;
        }
        break;
      case 0x67746163:
        v13 = HIDWORD(v19);
        if ( HIDWORD(v19) > 0x80 )
          v13 = 128;
        v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
               a2,
               (char *)a5 + 184,
               v13,
               &v17);
        if ( v8 >= 0 )
        {
          *((_WORD *)a5 + 155) = 0;
          *((_DWORD *)a5 + 1) |= 8u;
          goto LABEL_36;
        }
        break;
      case 0x68666572:
        v23 = 0;
        lpVtbl = a2->lpVtbl;
        v22 = 0;
        v8 = ((__int64 (__fastcall *)(struct IStream *, __int128 *, __int64, int *))lpVtbl->Read)(a2, &v22, 20, &v17);
        if ( v8 >= 0 )
        {
          v12 = v22;
          *((_DWORD *)a5 + 1) |= v23 | 2;
          *(_OWORD *)((char *)a5 + 24) = v12;
          goto LABEL_36;
        }
        break;
      case 0x73726576:
        v9 = a2->lpVtbl;
        v18 = 0;
        v8 = ((__int64 (__fastcall *)(struct IStream *, __int64 *, __int64, int *))v9->Read)(a2, &v18, 8, &v17);
        if ( v8 >= 0 )
        {
          v10 = v18;
          *((_DWORD *)a5 + 1) |= 0x80u;
          *((_QWORD *)a5 + 6) = __PAIR64__(HIDWORD(v18), v10);
          goto LABEL_36;
        }
        break;
      default:
        if ( v8 >= 0 )
        {
LABEL_36:
          if ( !(*(unsigned int (__fastcall **)(struct IRIFFStream *, __int64 *, _QWORD))(*(_QWORD *)a3 + 32LL))(
                  a3,
                  &v19,
                  0) )
          {
            LODWORD(v19) = 0;
            goto LABEL_5;
          }
          v8 = -2005397197;
        }
        break;
    }
  }
  if ( (*((_BYTE *)a5 + 4) & 0x15) == 0 )
    return (unsigned int)-2005396945;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f330  push    rbp
0x18000f332  push    rbx
0x18000f333  push    rsi
0x18000f334  push    rdi
0x18000f335  push    r13
0x18000f337  push    r14
0x18000f339  push    r15
0x18000f33b  mov     rbp, rsp
0x18000f33e  sub     rsp, 80h
0x18000f345  mov     rax, cs:__security_cookie
0x18000f34c  xor     rax, rsp
0x18000f34f  mov     [rbp+var_10], rax
0x18000f353  mov     rbx, [rbp+arg_20]
0x18000f357  mov     r15, r9
0x18000f35a  mov     r14, r8
0x18000f35d  mov     rsi, rdx
0x18000f360  test    rdx, rdx
0x18000f363  jz      loc_18000F60F
0x18000f369  test    r8, r8
0x18000f36c  jz      loc_18000F60F
0x18000f372  test    rbx, rbx
0x18000f375  jz      loc_18000F60F
0x18000f37b  lea     rcx, [rbx+4]; void *
0x18000f37f  xor     edx, edx; Val
0x18000f381  mov     r8d, 354h; Size
0x18000f387  call    memset_0
0x18000f38c  xor     edi, edi
0x18000f38e  mov     dword ptr [rbx], 358h
0x18000f394  mov     [rbp+var_50], 0
0x18000f39b  mov     r13d, 80h
0x18000f3a1  mov     [rbp+var_40], 0
0x18000f3a9  mov     [rbp+var_34], 0
0x18000f3b1  mov     [rbp+var_38], 0
0x18000f3b8  mov     rax, [r14]
0x18000f3bb  lea     rdx, [rbp+var_40]
0x18000f3bf  xor     r9d, r9d
0x18000f3c2  mov     r8, r15
0x18000f3c5  mov     rcx, r14
0x18000f3c8  mov     rax, [rax+18h]
0x18000f3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d1  test    eax, eax
0x18000f3d3  jnz     loc_18000F5FF
0x18000f3d9  mov     eax, dword ptr [rbp+var_40]
0x18000f3dc  cmp     eax, 64697567h
0x18000f3e1  jz      loc_18000F5A8
0x18000f3e7  cmp     eax, 656C6966h
0x18000f3ec  jz      loc_18000F565
0x18000f3f2  cmp     eax, 656D616Eh
0x18000f3f7  jz      loc_18000F52A
0x18000f3fd  cmp     eax, 65746164h
0x18000f402  jz      loc_18000F4F9
0x18000f408  cmp     eax, 67746163h
0x18000f40d  jz      loc_18000F4B8
0x18000f413  cmp     eax, 68666572h
0x18000f418  jz      short loc_18000F46E
0x18000f41a  cmp     eax, 73726576h
0x18000f41f  jz      short loc_18000F42A
0x18000f421  test    edi, edi
0x18000f423  js      short loc_18000F3B8
0x18000f425  jmp     loc_18000F5D3
0x18000f42a  mov     rax, [rsi]
0x18000f42d  lea     r9, [rbp+var_50]
0x18000f431  mov     r8d, 8
0x18000f437  mov     [rbp+var_48], 0
0x18000f43f  lea     rdx, [rbp+var_48]
0x18000f443  mov     rcx, rsi
0x18000f446  mov     rax, [rax+18h]
0x18000f44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f44f  mov     edi, eax
0x18000f451  test    eax, eax
0x18000f453  js      loc_18000F3B8
0x18000f459  mov     eax, dword ptr [rbp+var_48]
0x18000f45c  or      [rbx+4], r13d
0x18000f460  mov     [rbx+30h], eax
0x18000f463  mov     eax, dword ptr [rbp+var_48+4]
0x18000f466  mov     [rbx+34h], eax
0x18000f469  jmp     loc_18000F5D3
0x18000f46e  xor     eax, eax
0x18000f470  lea     r9, [rbp+var_50]
0x18000f474  mov     [rbp+var_18], eax
0x18000f477  lea     rdx, [rbp+var_28]
0x18000f47b  mov     rax, [rsi]
0x18000f47e  xorps   xmm0, xmm0
0x18000f481  mov     r8d, 14h
0x18000f487  mov     rcx, rsi
0x18000f48a  movups  [rbp+var_28], xmm0
0x18000f48e  mov     rax, [rax+18h]
0x18000f492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f497  mov     edi, eax
0x18000f499  test    eax, eax
0x18000f49b  js      loc_18000F3B8
0x18000f4a1  movups  xmm0, [rbp+var_28]
0x18000f4a5  mov     eax, [rbp+var_18]
0x18000f4a8  or      eax, 2
0x18000f4ab  or      [rbx+4], eax
0x18000f4ae  movdqu  xmmword ptr [rbx+18h], xmm0
0x18000f4b3  jmp     loc_18000F5D3
0x18000f4b8  mov     r8d, dword ptr [rbp+var_40+4]
0x18000f4bc  lea     rdx, [rbx+0B8h]
0x18000f4c3  mov     rax, [rsi]
0x18000f4c6  lea     r9, [rbp+var_50]
0x18000f4ca  cmp     r8d, r13d
0x18000f4cd  mov     rcx, rsi
0x18000f4d0  cmova   r8d, r13d
0x18000f4d4  mov     rax, [rax+18h]
0x18000f4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4dd  mov     edi, eax
0x18000f4df  test    eax, eax
0x18000f4e1  js      loc_18000F3B8
0x18000f4e7  xor     eax, eax
0x18000f4e9  mov     [rbx+136h], ax
0x18000f4f0  or      dword ptr [rbx+4], 8
0x18000f4f4  jmp     loc_18000F5D3
0x18000f4f9  mov     rax, [rsi]
0x18000f4fc  lea     rdx, [rbx+28h]
0x18000f500  lea     r9, [rbp+var_50]
0x18000f504  mov     r8d, 8
0x18000f50a  mov     rcx, rsi
0x18000f50d  mov     rax, [rax+18h]
0x18000f511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f516  mov     edi, eax
0x18000f518  test    eax, eax
0x18000f51a  js      loc_18000F3B8
0x18000f520  bts     dword ptr [rbx+4], 8
0x18000f525  jmp     loc_18000F5D3
0x18000f52a  mov     r8d, dword ptr [rbp+var_40+4]
0x18000f52e  lea     rdx, [rbx+38h]
0x18000f532  mov     rax, [rsi]
0x18000f535  lea     r9, [rbp+var_50]
0x18000f539  cmp     r8d, r13d
0x18000f53c  mov     rcx, rsi
0x18000f53f  cmova   r8d, r13d
0x18000f543  mov     rax, [rax+18h]
0x18000f547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54c  mov     edi, eax
0x18000f54e  test    eax, eax
0x18000f550  js      loc_18000F3B8
0x18000f556  xor     eax, eax
0x18000f558  mov     [rbx+0B6h], ax
0x18000f55f  or      dword ptr [rbx+4], 4
0x18000f563  jmp     short loc_18000F5D3
0x18000f565  mov     r8d, dword ptr [rbp+var_40+4]
0x18000f569  lea     rdx, [rbx+138h]
0x18000f570  mov     eax, 208h
0x18000f575  lea     r9, [rbp+var_50]
0x18000f579  cmp     r8d, eax
0x18000f57c  mov     rcx, rsi
0x18000f57f  cmova   r8d, eax
0x18000f583  mov     rax, [rsi]
0x18000f586  mov     rax, [rax+18h]
0x18000f58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f58f  mov     edi, eax
0x18000f591  test    eax, eax
0x18000f593  js      loc_18000F3B8
0x18000f599  xor     eax, eax
0x18000f59b  mov     [rbx+33Eh], ax
0x18000f5a2  or      dword ptr [rbx+4], 10h
0x18000f5a6  jmp     short loc_18000F5D3
0x18000f5a8  mov     rax, [rsi]
0x18000f5ab  lea     rdx, [rbx+8]
0x18000f5af  lea     r9, [rbp+var_50]
0x18000f5b3  mov     r8d, 10h
0x18000f5b9  mov     rcx, rsi
0x18000f5bc  mov     rax, [rax+18h]
0x18000f5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c5  mov     edi, eax
0x18000f5c7  test    eax, eax
0x18000f5c9  js      loc_18000F3B8
0x18000f5cf  or      dword ptr [rbx+4], 1
0x18000f5d3  mov     rax, [r14]
0x18000f5d6  lea     rdx, [rbp+var_40]
0x18000f5da  xor     r8d, r8d
0x18000f5dd  mov     rcx, r14
0x18000f5e0  mov     rax, [rax+20h]
0x18000f5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e9  test    eax, eax
0x18000f5eb  jnz     short loc_18000F5F5
0x18000f5ed  mov     dword ptr [rbp+var_40], eax
0x18000f5f0  jmp     loc_18000F3B1
0x18000f5f5  mov     edi, 88781133h
0x18000f5fa  jmp     loc_18000F3B8
0x18000f5ff  test    byte ptr [rbx+4], 15h
0x18000f603  mov     eax, 8878122Fh
0x18000f608  cmovz   edi, eax
0x18000f60b  mov     eax, edi
0x18000f60d  jmp     short loc_18000F614
0x18000f60f  mov     eax, 80070057h
0x18000f614  mov     rcx, [rbp+var_10]
0x18000f618  xor     rcx, rsp; StackCookie
0x18000f61b  call    __security_check_cookie
0x18000f620  add     rsp, 80h
0x18000f627  pop     r15
0x18000f629  pop     r14
0x18000f62b  pop     r13
0x18000f62d  pop     rdi
0x18000f62e  pop     rsi
0x18000f62f  pop     rbx
0x18000f630  pop     rbp
0x18000f631  retn
```
