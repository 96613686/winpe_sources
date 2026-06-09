# MakeTypeInfo(int,int,ushort * *,ITypeInfo * *)

- ea: `0x180086ff0`
- end: `0x1800872a6`
- name: `?MakeTypeInfo@@YAJHHPEAPEAGPEAPEAUITypeInfo@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(int, int, unsigned __int16 **, struct ITypeInfo **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180086a00`
- `0x180086b88`
- `0x1800902fc`

## callees

- `0x180085f00`
- `0x180086ff0`
- `0x1800966aa`
- `0x1800966e0`
- `0x180096770`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x180087070`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x180087070`

## pseudocode

```c
__int64 __fastcall MakeTypeInfo(int a1, int a2, unsigned __int16 **a3, struct ITypeInfo **a4)
{
  unsigned __int64 v4; // rdi
  HRESULT v8; // ebx
  size_t v9; // r8
  __int64 v10; // rax
  void *v11; // rsp
  struct ITypeInfo *v12; // rcx
  __int64 result; // rax
  int i; // ecx
  __int64 v15; // rax
  __int64 v16; // [rsp+30h] [rbp+0h] BYREF
  struct ITypeInfo *v17; // [rsp+38h] [rbp+8h] BYREF
  ICreateTypeLib2 *ppctlib; // [rsp+40h] [rbp+10h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp+20h] BYREF
  __int64 *v20; // [rsp+60h] [rbp+30h]
  int v21; // [rsp+68h] [rbp+38h]
  int v22; // [rsp+6Ch] [rbp+3Ch]
  int v23; // [rsp+70h] [rbp+40h]
  __int16 v24; // [rsp+74h] [rbp+44h]
  __int16 v25; // [rsp+7Ah] [rbp+4Ah]
  __int128 v26; // [rsp+80h] [rbp+50h]
  __int128 v27; // [rsp+90h] [rbp+60h]
  _BYTE v28[32]; // [rsp+B0h] [rbp+80h] BYREF
  __int16 v29; // [rsp+D0h] [rbp+A0h]
  int v30; // [rsp+ECh] [rbp+BCh]

  v4 = a2;
  memset_0(v28, 0, 0x40u);
  memset_0(v19, 0, 0x58u);
  v17 = 0;
  ppctlib = 0;
  v16 = 0;
  v8 = CreateTypeLib2(SYS_WIN32, L"JSSig.tlb", &ppctlib);
  if ( v8 < 0 )
    goto LABEL_10;
  v8 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, _QWORD, __int64, __int64 *))ppctlib->lpVtbl->CreateTypeInfo)(
         ppctlib,
         *a3,
         4,
         &v16);
  if ( v8 < 0 )
    goto LABEL_10;
  if ( a1 == 1 )
  {
    if ( (v4 & 0x80000000) != 0LL || v4 > 0x3FFFFFF )
      goto LABEL_9;
    v9 = 32 * v4;
    v10 = 32 * v4 + 15;
    if ( v9 + 15 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( !&v16 )
    {
LABEL_9:
      v8 = -2147024882;
LABEL_10:
      v12 = v17;
      goto LABEL_11;
    }
    memset_0(&v16, 0, v9);
    for ( i = 0; i < (int)v4; *((_WORD *)&v16 + 16 * v15 + 4) = 12 )
      v15 = (unsigned int)i++;
    memset_0(v19, 0, 0x58u);
    v20 = &v16;
    v21 = 4;
    v23 = 4;
    v22 = 1;
    v24 = v4 - 1;
    v26 = 0;
    v25 = -1;
    v27 = 0;
    WORD4(v26) = 12;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 72LL))(v16, 0, v19);
    if ( v8 < 0 )
      goto LABEL_10;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)v16 + 120LL))(
           v16,
           0,
           a3,
           (unsigned int)v4);
    if ( v8 < 0 )
      goto LABEL_10;
  }
  else
  {
    memset_0(v28, 0, 0x40u);
    v30 = 3;
    v29 = 12;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 112LL))(v16, 0, v28);
    if ( (int)result < 0 )
      return result;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 128LL))(v16, 0, *a3);
    if ( (int)result < 0 )
      return result;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ITypeInfo **))v16)(v16, &IID_ITypeInfo, &v17);
  if ( v8 < 0 )
    goto LABEL_10;
  v12 = v17;
  v8 = 0;
  *a4 = v17;
LABEL_11:
  if ( v12 && v8 < 0 )
    ((void (__fastcall *)(struct ITypeInfo *))v12->lpVtbl->Release)(v12);
  if ( ppctlib )
    ((void (__fastcall *)(ICreateTypeLib2 *))ppctlib->lpVtbl->Release)(ppctlib);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  FreeNames(a3, (unsigned int)v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180086ff0  push    rbp
0x180086ff2  push    rbx
0x180086ff3  push    rsi
0x180086ff4  push    rdi
0x180086ff5  push    r13
0x180086ff7  push    r14
0x180086ff9  push    r15
0x180086ffb  sub     rsp, 100h
0x180087002  lea     rbp, [rsp+30h]
0x180087007  mov     rax, cs:__security_cookie
0x18008700e  xor     rax, rbp
0x180087011  mov     [rbp+100h+var_40], rax
0x180087018  movsxd  rdi, edx
0x18008701b  mov     r14, r8
0x18008701e  xor     edx, edx; Val
0x180087020  mov     esi, ecx
0x180087022  lea     rcx, [rbp+100h+var_80]; void *
0x180087029  mov     r15, r9
0x18008702c  lea     r8d, [rdx+40h]; Size
0x180087030  call    memset_0
0x180087035  xor     edx, edx; Val
0x180087037  lea     rcx, [rbp+100h+var_E0]; void *
0x18008703b  lea     r8d, [rdx+58h]; Size
0x18008703f  call    memset_0
0x180087044  mov     r13d, 1
0x18008704a  mov     [rbp+100h+var_F8], 0
0x180087052  mov     ecx, r13d; syskind
0x180087055  mov     [rbp+100h+ppctlib], 0
0x18008705d  lea     r8, [rbp+100h+ppctlib]; ppctlib
0x180087061  mov     [rbp+100h+var_100], 0
0x180087069  lea     rdx, szFile; "JSSig.tlb"
0x180087070  call    cs:__imp_CreateTypeLib2
0x180087077  nop     dword ptr [rax+rax+00h]
0x18008707c  mov     ebx, eax
0x18008707e  test    eax, eax
0x180087080  js      short loc_1800870EE
0x180087082  mov     rcx, [rbp+100h+ppctlib]
0x180087086  lea     r9, [rbp+100h+var_100]
0x18008708a  mov     rdx, [r14]
0x18008708d  lea     r8d, [r13+3]
0x180087091  mov     rax, [rcx]
0x180087094  mov     rax, [rax+18h]
0x180087098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008709d  mov     ebx, eax
0x18008709f  test    eax, eax
0x1800870a1  js      short loc_1800870EE
0x1800870a3  cmp     esi, r13d
0x1800870a6  jnz     loc_18008720B
0x1800870ac  test    edi, edi
0x1800870ae  js      short loc_1800870E9
0x1800870b0  mov     r8, rdi
0x1800870b3  cmp     rdi, 3FFFFFFh
0x1800870ba  ja      short loc_1800870E9
0x1800870bc  shl     r8, 5
0x1800870c0  lea     rax, [r8+0Fh]
0x1800870c4  cmp     rax, r8
0x1800870c7  ja      short loc_1800870D3
0x1800870c9  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800870d3  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800870d7  call    _alloca_probe
0x1800870dc  sub     rsp, rax
0x1800870df  lea     rbx, [rsp+130h+var_100]
0x1800870e4  test    rbx, rbx
0x1800870e7  jnz     short loc_18008715F
0x1800870e9  mov     ebx, 8007000Eh
0x1800870ee  mov     rcx, [rbp+100h+var_F8]
0x1800870f2  test    rcx, rcx
0x1800870f5  jz      short loc_180087107
0x1800870f7  test    ebx, ebx
0x1800870f9  jns     short loc_180087107
0x1800870fb  mov     rax, [rcx]
0x1800870fe  mov     rax, [rax+10h]
0x180087102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087107  mov     rcx, [rbp+100h+ppctlib]
0x18008710b  test    rcx, rcx
0x18008710e  jz      short loc_18008711C
0x180087110  mov     rax, [rcx]
0x180087113  mov     rax, [rax+10h]
0x180087117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008711c  mov     rcx, [rbp+100h+var_100]
0x180087120  test    rcx, rcx
0x180087123  jz      short loc_180087131
0x180087125  mov     rax, [rcx]
0x180087128  mov     rax, [rax+10h]
0x18008712c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087131  mov     edx, edi
0x180087133  mov     rcx, r14
0x180087136  call    FreeNames
0x18008713b  mov     eax, ebx
0x18008713d  mov     rcx, [rbp+100h+var_40]
0x180087144  xor     rcx, rbp; StackCookie
0x180087147  call    __security_check_cookie
0x18008714c  lea     rsp, [rbp+0D0h]
0x180087153  pop     r15
0x180087155  pop     r14
0x180087157  pop     r13
0x180087159  pop     rdi
0x18008715a  pop     rsi
0x18008715b  pop     rbx
0x18008715c  pop     rbp
0x18008715d  retn
0x18008715f  xor     edx, edx; Val
0x180087161  mov     rcx, rbx; void *
0x180087164  call    memset_0
0x180087169  xor     ecx, ecx
0x18008716b  lea     esi, [rcx+0Ch]
0x18008716e  test    edi, edi
0x180087170  jle     short loc_180087184
0x180087172  mov     eax, ecx
0x180087174  add     ecx, r13d
0x180087177  shl     rax, 5
0x18008717b  mov     [rax+rbx+8], si
0x180087180  cmp     ecx, edi
0x180087182  jl      short loc_180087172
0x180087184  xor     edx, edx; Val
0x180087186  lea     rcx, [rbp+100h+var_E0]; void *
0x18008718a  lea     r8d, [rdx+58h]; Size
0x18008718e  call    memset_0
0x180087193  mov     rcx, [rbp+100h+var_100]
0x180087197  lea     r8, [rbp+100h+var_E0]
0x18008719b  mov     eax, 4
0x1800871a0  mov     [rbp+100h+var_D0], rbx
0x1800871a4  mov     [rbp+100h+var_C8], eax
0x1800871a7  xorps   xmm0, xmm0
0x1800871aa  mov     [rbp+100h+var_C0], eax
0x1800871ad  xor     edx, edx
0x1800871af  movzx   eax, di
0x1800871b2  mov     [rbp+100h+var_C4], r13d
0x1800871b6  sub     ax, r13w
0x1800871ba  mov     [rbp+100h+var_BC], ax
0x1800871be  or      eax, 0FFFFFFFFh
0x1800871c1  movups  [rbp+100h+var_B0], xmm0
0x1800871c5  mov     [rbp+100h+var_B6], ax
0x1800871c9  movups  [rbp+100h+var_A0], xmm0
0x1800871cd  mov     word ptr [rbp+100h+var_B0+8], si
0x1800871d1  mov     rax, [rcx]
0x1800871d4  mov     rax, [rax+48h]
0x1800871d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871dd  mov     ebx, eax
0x1800871df  test    eax, eax
0x1800871e1  js      loc_1800870EE
0x1800871e7  mov     rcx, [rbp+100h+var_100]
0x1800871eb  mov     r9d, edi
0x1800871ee  mov     r8, r14
0x1800871f1  xor     edx, edx
0x1800871f3  mov     rax, [rcx]
0x1800871f6  mov     rax, [rax+78h]
0x1800871fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871ff  mov     ebx, eax
0x180087201  test    eax, eax
0x180087203  js      loc_1800870EE
0x180087209  jmp     short loc_180087274
0x18008720b  xor     edx, edx; Val
0x18008720d  lea     rcx, [rbp+100h+var_80]; void *
0x180087214  lea     r8d, [rdx+40h]; Size
0x180087218  call    memset_0
0x18008721d  mov     rcx, [rbp+100h+var_100]
0x180087221  lea     r8, [rbp+100h+var_80]
0x180087228  mov     [rbp+100h+var_44], 3
0x180087232  mov     esi, 0Ch
0x180087237  mov     [rbp+100h+var_60], si
0x18008723e  xor     edx, edx
0x180087240  mov     rax, [rcx]
0x180087243  mov     rax, [rax+70h]
0x180087247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008724c  test    eax, eax
0x18008724e  js      loc_18008713D
0x180087254  mov     rcx, [rbp+100h+var_100]
0x180087258  xor     edx, edx
0x18008725a  mov     r8, [r14]
0x18008725d  mov     rax, [rcx]
0x180087260  mov     rax, [rax+80h]
0x180087267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008726c  test    eax, eax
0x18008726e  js      loc_18008713D
0x180087274  mov     rcx, [rbp+100h+var_100]
0x180087278  lea     r8, [rbp+100h+var_F8]
0x18008727c  lea     rdx, IID_ITypeInfo
0x180087283  mov     rax, [rcx]
0x180087286  mov     rax, [rax]
0x180087289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008728e  mov     ebx, eax
0x180087290  test    eax, eax
0x180087292  js      loc_1800870EE
0x180087298  mov     rcx, [rbp+100h+var_F8]
0x18008729c  xor     ebx, ebx
0x18008729e  mov     [r15], rcx
0x1800872a1  jmp     loc_1800870F2
```
