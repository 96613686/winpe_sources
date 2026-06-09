# ExtEscapeImpl(HDC__ *,int,int,char const *,int,char *)

- ea: `0x18006d900`
- end: `0x18006de92`
- name: `?ExtEscapeImpl@@YAHPEAUHDC__@@HHPEBDHPEAD@Z`
- size: `1426`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, const char *@<r9>, int, char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002a4fc`
- `0x18002bea8`
- `0x18003e758`
- `0x18003e8e0`
- `0x18003eb04`
- `0x180042d6c`
- `0x18006d900`
- `0x18007e0f0`
- `0x18007f800`
- `0x180080604`
- `0x180093590`
- `0x180098144`
- `0x1800a68d4`
- `0x1800a68e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006dc5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006dc5d`
- `GDI32!StartPage` at `0x18006daaf`
- `GDI32!StartPage` at `0x18006daaf`
- `GDI32!pldcGet` at `0x18006da2d`
- `GDI32!pldcGet` at `0x18006da2d`
- `GDI32!GdiSetLastError` at `0x18006de7f`
- `GDI32!GdiSetLastError` at `0x18006de7f`
- `ntdll!RtlAllocateHeap` at `0x18006dcde`
- `ntdll!RtlAllocateHeap` at `0x18006dcde`
- `USER32!GetAppCompatFlags2` at `0x18006d9bf`
- `USER32!GetAppCompatFlags2` at `0x18006dc19`
- `USER32!GetAppCompatFlags2` at `0x18006d9bf`
- `USER32!GetAppCompatFlags2` at `0x18006dc19`
- `win32u!NtGdiExtEscape` at `0x18006dde9`
- `win32u!NtGdiExtEscape` at `0x18006dde9`
- `win32u!NtGdiGetTransform` at `0x18006db15`
- `win32u!NtGdiGetTransform` at `0x18006db15`
- `win32u!NtGdiIsDcInXfer` at `0x18006d9ff`
- `win32u!NtGdiIsDcInXfer` at `0x18006d9ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall ExtEscapeImpl(
        HDC a1,
        unsigned int a2,
        int a3,
        const char *p_Src,
        unsigned int a5,
        struct _KERNPAIR *a6)
{
  HDC v9; // r13
  size_t v10; // r8
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r15
  int v16; // ecx
  int v17; // r14d
  int v18; // ecx
  unsigned int v19; // r13d
  _DWORD *Heap; // rax
  _QWORD *v21; // r14
  unsigned int v22; // r13d
  _QWORD *v23; // rcx
  char *v24; // r14
  __int64 v25; // rcx
  const void *v26; // rdx
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int16 Src; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[526]; // [rsp+82h] [rbp-7Eh] BYREF

  v9 = a1;
  v29[0] = a1;
  v30 = 0;
  v31 = 0;
  memset_0(&Src, 0, 0x208u);
  if ( a2 == 256 )
  {
    if ( (unsigned int)GetETM(v9) )
    {
      v10 = 52;
      if ( (unsigned __int64)(int)a5 < 0x34 )
        v10 = (int)a5;
      memcpy_0(a6, &Src, v10);
      return 1;
    }
    return 0;
  }
  v12 = 0;
  switch ( a2 )
  {
    case 0x19u:
      if ( (GetAppCompatFlags2(1024) & 8) != 0 )
        return 0;
      v13 = 20;
      if ( a3 )
        v13 = a3;
      a3 = v13;
      break;
    case 8u:
      if ( *(_DWORD *)p_Src == 258 )
        return 1;
      if ( *(_DWORD *)p_Src == 25 && (GetAppCompatFlags2(1024) & 8) != 0 )
        return 0;
      break;
    case 0x102u:
      return GetPairKernTable(v9, a5, a6);
  }
  v27 = 0;
  if ( ((unsigned int)v9 & 0x7F0000) == 0x10000 )
    return NtGdiExtEscape(v9, 0, 0, a2, a3 & (unsigned int)-(p_Src != 0), p_Src, a6 != 0 ? a5 : 0, a6);
  if ( (int)NtGdiIsDcInXfer(v9, &v27) < 0 )
    return 0;
  if ( v27 )
    return NtGdiExtEscape(v9, 0, 0, a2, a3 & (unsigned int)-(p_Src != 0), p_Src, a6 != 0 ? a5 : 0, a6);
  if ( ((unsigned int)v9 & 0x7F0000) == 0x660000 )
    return 0;
  v14 = pldcGet(v9);
  v15 = v14;
  if ( !v14 )
  {
    v25 = 6;
LABEL_87:
    GdiSetLastError(v25);
    return 0;
  }
  v16 = *(_DWORD *)(v14 + 8);
  if ( (v16 & 0x10020) != 0 )
  {
    if ( (v16 & 0x20) != 0 )
      vSAPCallback(v14);
    v16 = *(_DWORD *)(v15 + 8);
    if ( (v16 & 0x10000) != 0 )
      return 0;
  }
  v17 = 1;
  if ( (a2 - 4096 <= 2 || a2 - 513 <= 1 || a2 == 37 || a2 == 19 || a2 == 4111) && (v16 & 0x100) != 0 )
    StartPage(v9);
  if ( *(_DWORD *)(v15 + 12) != 2 || (*(_DWORD *)(v15 + 8) & 0x20000) == 0 )
    goto LABEL_62;
  if ( a2 - 4117 <= 1 )
  {
LABEL_61:
    SetLastError(0x57u);
    return v12;
  }
  if ( a2 == 17 || a2 == 8 || a2 - 4119 <= 1 )
  {
LABEL_64:
    if ( (a2 == 4118 || a2 == 4117) && (*(_BYTE *)(v15 + 8) & 0x40) == 0 )
    {
      if ( a3 < 0 )
        return 0;
      v18 = a3 + 34;
      if ( a3 + 34 < (unsigned int)(a3 + 31) )
        return 0;
      v19 = v18 & 0xFFFFFFFC;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18 & 0xFFFFFFFC);
      v21 = Heap;
      if ( Heap )
      {
        v22 = v19 - 16;
        Heap[4] = v22;
        Heap[5] = a2;
        Heap[6] = a3;
        memcpy_0(Heap + 7, p_Src, a3);
        v23 = *(_QWORD **)(v15 + 152);
        if ( *v23 != v15 + 144 )
          __fastfail(3u);
        *v21 = v15 + 144;
        v21[1] = v23;
        *v23 = v21;
        *(_QWORD *)(v15 + 152) = v21;
        *(_DWORD *)(v15 + 136) += v22;
        v9 = (HDC)v29[0];
        goto LABEL_73;
      }
      v25 = 8;
      goto LABEL_87;
    }
LABEL_73:
    v24 = (char *)a6;
    goto LABEL_74;
  }
  v28 = 0;
  if ( (unsigned int)NtGdiGetTransform(v9, 515, &v30)
    && (*(float *)&v30 != 1.0
     || *((float *)&v30 + 3) != 1.0
     || *((float *)&v30 + 1) != 0.0
     || *((float *)&v30 + 2) != 0.0) )
  {
    v28 = 1;
    MF_ModifyWorldTransform(v9, qword_1800C2888, 4);
  }
  MF_WriteEscape(v9, a2, (unsigned int)a3, p_Src, 106);
  if ( v28 )
    MF_ModifyWorldTransform(v9, &v30, 4);
  if ( a6 && a5 )
  {
LABEL_62:
    if ( a2 != 514 )
    {
      if ( a2 == 513 )
        goto LABEL_73;
      goto LABEL_64;
    }
    v26 = gpwcANSICharSet;
    if ( gpwcANSICharSet )
    {
LABEL_81:
      memmove_0(v33, v26, 0x200u);
      v24 = (char *)a6;
      if ( a6 && a5 >= 2 )
        Src = *(_WORD *)a6;
      else
        Src = 0;
      a3 = 514;
      p_Src = (const char *)&Src;
LABEL_74:
      if ( *(_QWORD *)(v15 + 48) )
      {
        v29[0] = __PAIR64__(a3, a2);
        v29[1] = p_Src;
        LdcGetUmpd(&v28, v15);
        DocumentEventEx((struct UmpdPtr *)&v28, *(void **)(v15 + 48), v9, 11, 0x10u, v29, a5, v24);
        UmpdPtr::reset((UmpdPtr *)&v28, 0);
      }
      return NtGdiExtEscape(v9, 0, 0, a2, a3 & (unsigned int)-(p_Src != 0), p_Src, a6 != 0 ? a5 : 0, a6);
    }
    if ( (unsigned int)bGetANSISetMap() )
    {
      v26 = gpwcANSICharSet;
      goto LABEL_81;
    }
    return 0;
  }
  if ( a2 != 19 && a2 != 4115 && a2 != 37 )
    goto LABEL_50;
  if ( a3 < 2 || a3 < *(unsigned __int16 *)p_Src + 2 )
  {
    v12 = -1;
    goto LABEL_61;
  }
  a3 = *(unsigned __int16 *)p_Src;
LABEL_50:
  if ( a3 > 1 )
    return a3;
  return v17;
}

```

## disassembly

```asm
0x18006d900  push    rbp
0x18006d902  push    rbx
0x18006d903  push    rsi
0x18006d904  push    rdi
0x18006d905  push    r12
0x18006d907  push    r13
0x18006d909  push    r14
0x18006d90b  push    r15
0x18006d90d  lea     rbp, [rsp-1A8h]
0x18006d915  sub     rsp, 2A8h
0x18006d91c  mov     rax, cs:__security_cookie
0x18006d923  xor     rax, rsp
0x18006d926  mov     [rbp+1E0h+var_50], rax
0x18006d92d  mov     r12, r9
0x18006d930  mov     esi, r8d
0x18006d933  mov     edi, edx
0x18006d935  mov     r13, rcx
0x18006d938  mov     [rsp+2E0h+var_288], rcx
0x18006d93d  mov     r14, [rbp+1E0h+arg_28]
0x18006d944  mov     [rsp+2E0h+var_2A0], r14
0x18006d949  xorps   xmm0, xmm0
0x18006d94c  xor     eax, eax
0x18006d94e  movups  [rsp+2E0h+var_278], xmm0
0x18006d953  mov     [rsp+2E0h+var_268], rax
0x18006d958  xor     edx, edx; Val
0x18006d95a  mov     r8d, 208h; Size
0x18006d960  lea     rcx, [rbp+1E0h+Src]; void *
0x18006d964  call    memset_0
0x18006d969  cmp     edi, 100h
0x18006d96f  jnz     short loc_18006D9AF
0x18006d971  lea     rdx, [rbp+1E0h+Src]
0x18006d975  mov     rcx, r13; hdc
0x18006d978  call    GetETM
0x18006d97d  test    eax, eax
0x18006d97f  jz      loc_18006DE8B
0x18006d985  movsxd  rax, [rbp+1E0h+arg_20]
0x18006d98c  mov     r8d, 34h ; '4'
0x18006d992  cmp     rax, r8
0x18006d995  cmovb   r8, rax; Size
0x18006d999  lea     rdx, [rbp+1E0h+Src]; Src
0x18006d99d  mov     rcx, r14; void *
0x18006d9a0  call    memcpy_0
0x18006d9a5  mov     eax, 1
0x18006d9aa  jmp     loc_18006DDF5
0x18006d9af  xor     ebx, ebx
0x18006d9b1  cmp     edi, 19h
0x18006d9b4  jnz     loc_18006DBF6
0x18006d9ba  mov     ecx, 400h
0x18006d9bf  call    cs:__imp_GetAppCompatFlags2
0x18006d9c6  nop     dword ptr [rax+rax+00h]
0x18006d9cb  test    al, 8
0x18006d9cd  jnz     loc_18006DE8B
0x18006d9d3  lea     eax, [rbx+14h]
0x18006d9d6  test    esi, esi
0x18006d9d8  cmovnz  eax, esi
0x18006d9db  mov     esi, eax
0x18006d9dd  mov     eax, r13d
0x18006d9e0  and     eax, 7F0000h
0x18006d9e5  mov     r14d, eax
0x18006d9e8  mov     [rsp+2E0h+var_298], ebx
0x18006d9ec  cmp     eax, 10000h
0x18006d9f1  jz      loc_18006DDAF
0x18006d9f7  lea     rdx, [rsp+2E0h+var_298]
0x18006d9fc  mov     rcx, r13
0x18006d9ff  call    cs:__imp_NtGdiIsDcInXfer
0x18006da06  nop     dword ptr [rax+rax+00h]
0x18006da0b  test    eax, eax
0x18006da0d  js      loc_18006DE8B
0x18006da13  cmp     [rsp+2E0h+var_298], ebx
0x18006da17  jnz     loc_18006DDAF
0x18006da1d  cmp     r14d, 660000h
0x18006da24  jz      loc_18006DE8B
0x18006da2a  mov     rcx, r13
0x18006da2d  call    cs:__imp_pldcGet
0x18006da34  nop     dword ptr [rax+rax+00h]
0x18006da39  mov     r15, rax
0x18006da3c  test    rax, rax
0x18006da3f  jz      loc_18006DE7A
0x18006da45  cmp     r14d, 660000h
0x18006da4c  jz      loc_18006DE7A
0x18006da52  mov     ecx, [rax+8]
0x18006da55  test    ecx, 10020h
0x18006da5b  jz      short loc_18006DA78
0x18006da5d  test    cl, 20h
0x18006da60  jz      short loc_18006DA6A
0x18006da62  mov     rcx, rax
0x18006da65  call    vSAPCallback
0x18006da6a  mov     ecx, [r15+8]
0x18006da6e  bt      ecx, 10h
0x18006da72  jb      loc_18006DE8B
0x18006da78  lea     eax, [rdi-1000h]
0x18006da7e  mov     r14d, 1
0x18006da84  cmp     eax, 2
0x18006da87  jbe     short loc_18006DAA6
0x18006da89  lea     eax, [rdi-201h]
0x18006da8f  cmp     eax, r14d
0x18006da92  jbe     short loc_18006DAA6
0x18006da94  cmp     edi, 25h ; '%'
0x18006da97  jz      short loc_18006DAA6
0x18006da99  cmp     edi, 13h
0x18006da9c  jz      short loc_18006DAA6
0x18006da9e  cmp     edi, 100Fh
0x18006daa4  jnz     short loc_18006DABB
0x18006daa6  bt      ecx, 8
0x18006daaa  jnb     short loc_18006DABB
0x18006daac  mov     rcx, r13; hdc
0x18006daaf  call    cs:__imp_StartPage
0x18006dab6  nop     dword ptr [rax+rax+00h]
0x18006dabb  cmp     dword ptr [r15+0Ch], 2
0x18006dac0  jnz     loc_18006DC70
0x18006dac6  test    dword ptr [r15+8], 20000h
0x18006dace  jz      loc_18006DC70
0x18006dad4  lea     eax, [rdi-1015h]
0x18006dada  cmp     eax, r14d
0x18006dadd  jbe     loc_18006DC58
0x18006dae3  cmp     edi, 11h
0x18006dae6  jz      loc_18006DC88
0x18006daec  cmp     edi, 8
0x18006daef  jz      loc_18006DC88
0x18006daf5  lea     eax, [rdi-1017h]
0x18006dafb  cmp     eax, r14d
0x18006dafe  jbe     loc_18006DC88
0x18006db04  mov     [rsp+2E0h+var_290], ebx
0x18006db08  lea     r8, [rsp+2E0h+var_278]
0x18006db0d  mov     edx, 203h
0x18006db12  mov     rcx, r13
0x18006db15  call    cs:__imp_NtGdiGetTransform
0x18006db1c  nop     dword ptr [rax+rax+00h]
0x18006db21  test    eax, eax
0x18006db23  jz      short loc_18006DB7E
0x18006db25  movss   xmm1, cs:__real@3f800000
0x18006db2d  movss   xmm0, dword ptr [rsp+2E0h+var_278]
0x18006db33  ucomiss xmm0, xmm1
0x18006db36  jp      short loc_18006DB64
0x18006db38  jnz     short loc_18006DB64
0x18006db3a  movss   xmm0, dword ptr [rsp+2E0h+var_278+0Ch]
0x18006db40  ucomiss xmm0, xmm1
0x18006db43  jp      short loc_18006DB64
0x18006db45  jnz     short loc_18006DB64
0x18006db47  xorps   xmm1, xmm1
0x18006db4a  movss   xmm0, dword ptr [rsp+2E0h+var_278+4]
0x18006db50  ucomiss xmm0, xmm1
0x18006db53  jp      short loc_18006DB64
0x18006db55  jnz     short loc_18006DB64
0x18006db57  movss   xmm0, dword ptr [rsp+2E0h+var_278+8]
0x18006db5d  ucomiss xmm0, xmm1
0x18006db60  jp      short loc_18006DB64
0x18006db62  jz      short loc_18006DB7E
0x18006db64  mov     [rsp+2E0h+var_290], r14d
0x18006db69  mov     r8d, 4
0x18006db6f  lea     rdx, qword_1800C2888
0x18006db76  mov     rcx, r13
0x18006db79  call    MF_ModifyWorldTransform
0x18006db7e  mov     [rsp+2E0h+var_2C0], 6Ah ; 'j'
0x18006db86  mov     r9, r12
0x18006db89  mov     r8d, esi
0x18006db8c  mov     edx, edi
0x18006db8e  mov     rcx, r13
0x18006db91  call    MF_WriteEscape
0x18006db96  cmp     [rsp+2E0h+var_290], ebx
0x18006db9a  jz      short loc_18006DBAF
0x18006db9c  mov     r8d, 4
0x18006dba2  lea     rdx, [rsp+2E0h+var_278]
0x18006dba7  mov     rcx, r13
0x18006dbaa  call    MF_ModifyWorldTransform
0x18006dbaf  cmp     [rsp+2E0h+var_2A0], rbx
0x18006dbb4  jz      short loc_18006DBC2
0x18006dbb6  cmp     [rbp+1E0h+arg_20], ebx
0x18006dbbc  jnz     loc_18006DC70
0x18006dbc2  cmp     edi, 13h
0x18006dbc5  jz      short loc_18006DBD4
0x18006dbc7  cmp     edi, 1013h
0x18006dbcd  jz      short loc_18006DBD4
0x18006dbcf  cmp     edi, 25h ; '%'
0x18006dbd2  jnz     short loc_18006DBE7
0x18006dbd4  cmp     esi, 2
0x18006dbd7  jl      short loc_18006DC55
0x18006dbd9  movzx   eax, word ptr [r12]
0x18006dbde  lea     ecx, [rax+2]
0x18006dbe1  cmp     esi, ecx
0x18006dbe3  jl      short loc_18006DC55
0x18006dbe5  mov     esi, eax
0x18006dbe7  cmp     esi, r14d
0x18006dbea  cmovg   r14d, esi
0x18006dbee  mov     eax, r14d
0x18006dbf1  jmp     loc_18006DDF5
0x18006dbf6  cmp     edi, 8
0x18006dbf9  jnz     short loc_18006DC33
0x18006dbfb  cmp     dword ptr [r12], 102h
0x18006dc03  jz      loc_18006D9A5
0x18006dc09  cmp     dword ptr [r12], 19h
0x18006dc0e  jnz     loc_18006D9DD
0x18006dc14  mov     ecx, 400h
0x18006dc19  call    cs:__imp_GetAppCompatFlags2
0x18006dc20  nop     dword ptr [rax+rax+00h]
0x18006dc25  test    dil, al
0x18006dc28  jz      loc_18006D9DD
0x18006dc2e  jmp     loc_18006DE8B
0x18006dc33  cmp     edi, 102h
0x18006dc39  jnz     loc_18006D9DD
0x18006dc3f  mov     r8, r14; struct _KERNPAIR *
0x18006dc42  mov     edx, [rbp+1E0h+arg_20]; unsigned int
0x18006dc48  mov     rcx, r13; hdc
0x18006dc4b  call    ?GetPairKernTable@@YAKPEAUHDC__@@KPEAU_KERNPAIR@@@Z; GetPairKernTable(HDC__ *,ulong,_KERNPAIR *)
0x18006dc50  jmp     loc_18006DDF5
0x18006dc55  or      ebx, 0FFFFFFFFh
0x18006dc58  mov     ecx, 57h ; 'W'; dwErrCode
0x18006dc5d  call    cs:__imp_SetLastError
0x18006dc64  nop     dword ptr [rax+rax+00h]
0x18006dc69  mov     eax, ebx
0x18006dc6b  jmp     loc_18006DDF5
0x18006dc70  cmp     edi, 202h
0x18006dc76  jz      loc_18006DE20
0x18006dc7c  cmp     edi, 201h
0x18006dc82  jz      loc_18006DD44
0x18006dc88  cmp     edi, 1016h
0x18006dc8e  jz      short loc_18006DC9C
0x18006dc90  cmp     edi, 1015h
0x18006dc96  jnz     loc_18006DD44
0x18006dc9c  test    byte ptr [r15+8], 40h
0x18006dca1  jnz     loc_18006DD44
0x18006dca7  test    esi, esi
0x18006dca9  js      loc_18006DE8B
0x18006dcaf  lea     eax, [rsi+1Fh]
0x18006dcb2  cmp     eax, 1Fh
0x18006dcb5  jb      loc_18006DE8B
0x18006dcbb  lea     ecx, [rax+3]
0x18006dcbe  cmp     ecx, eax
0x18006dcc0  jb      loc_18006DE8B
0x18006dcc6  and     ecx, 0FFFFFFFCh
0x18006dcc9  mov     r13d, ecx
0x18006dccc  mov     r8d, ecx; Size
0x18006dccf  mov     rcx, gs:60h
0x18006dcd8  xor     edx, edx; Flags
0x18006dcda  mov     rcx, [rcx+30h]; HeapHandle
0x18006dcde  call    cs:__imp_RtlAllocateHeap
0x18006dce5  nop     dword ptr [rax+rax+00h]
0x18006dcea  mov     r14, rax
0x18006dced  test    rax, rax
0x18006dcf0  jz      loc_18006DE19
0x18006dcf6  add     r13d, 0FFFFFFF0h
0x18006dcfa  mov     [rax+10h], r13d
0x18006dcfe  mov     [rax+14h], edi
0x18006dd01  mov     [rax+18h], esi
0x18006dd04  movsxd  r8, esi; Size
0x18006dd07  lea     rcx, [rax+1Ch]; void *
0x18006dd0b  mov     rdx, r12; Src
0x18006dd0e  call    memcpy_0
0x18006dd13  lea     rax, [r15+90h]
0x18006dd1a  mov     rcx, [rax+8]
0x18006dd1e  cmp     [rcx], rax
0x18006dd21  jz      short loc_18006DD2A
0x18006dd23  mov     ecx, 3
0x18006dd28  int     29h; Win8: RtlFailFast(ecx)
0x18006dd2a  mov     [r14], rax
0x18006dd2d  mov     [r14+8], rcx
0x18006dd31  mov     [rcx], r14
0x18006dd34  mov     [rax+8], r14
0x18006dd38  add     [r15+88h], r13d
0x18006dd3f  mov     r13, [rsp+2E0h+var_288]
0x18006dd44  mov     r14, [rsp+2E0h+var_2A0]
0x18006dd49  cmp     [r15+30h], rbx
0x18006dd4d  jz      short loc_18006DDAF
0x18006dd4f  mov     dword ptr [rsp+2E0h+var_288], edi
0x18006dd53  mov     dword ptr [rsp+2E0h+var_288+4], esi
0x18006dd57  mov     [rsp+2E0h+var_280], r12
0x18006dd5c  mov     rdx, r15
0x18006dd5f  lea     rcx, [rsp+2E0h+var_290]
0x18006dd64  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x18006dd69  nop
0x18006dd6a  mov     [rsp+2E0h+var_2A8], r14; void *
0x18006dd6f  mov     eax, [rbp+1E0h+arg_20]
0x18006dd75  mov     [rsp+2E0h+var_2B0], eax; unsigned int
0x18006dd79  lea     rax, [rsp+2E0h+var_288]
0x18006dd7e  mov     [rsp+2E0h+var_2B8], rax; void *
0x18006dd83  mov     [rsp+2E0h+var_2C0], 10h; unsigned int
0x18006dd8b  mov     r9d, 0Bh; int
0x18006dd91  mov     r8, r13; HDC
0x18006dd94  mov     rdx, [r15+30h]; void *
0x18006dd98  lea     rcx, [rsp+2E0h+var_290]; this
0x18006dd9d  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x18006dda2  nop
0x18006dda3  xor     edx, edx; struct _UMPD *
0x18006dda5  lea     rcx, [rsp+2E0h+var_290]; this
0x18006ddaa  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18006ddaf  mov     r8, [rsp+2E0h+var_2A0]
0x18006ddb4  mov     rax, r8
0x18006ddb7  neg     rax
0x18006ddba  sbb     edx, edx
0x18006ddbc  and     edx, [rbp+1E0h+arg_20]
0x18006ddc2  mov     rax, r12
0x18006ddc5  neg     rax
0x18006ddc8  sbb     ecx, ecx
0x18006ddca  and     ecx, esi
0x18006ddcc  mov     [rsp+2E0h+var_2A8], r8
0x18006ddd1  mov     [rsp+2E0h+var_2B0], edx
0x18006ddd5  mov     [rsp+2E0h+var_2B8], r12
0x18006ddda  mov     [rsp+2E0h+var_2C0], ecx
0x18006ddde  mov     r9d, edi
0x18006dde1  xor     r8d, r8d
  ... truncated ...
```
