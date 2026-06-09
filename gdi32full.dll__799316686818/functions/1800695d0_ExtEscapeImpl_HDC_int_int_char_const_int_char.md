# ExtEscapeImpl(HDC__ *,int,int,char const *,int,char *)

- ea: `0x1800695d0`
- end: `0x180069b25`
- name: `?ExtEscapeImpl@@YAHPEAUHDC__@@HHPEBDHPEAD@Z`
- size: `1365`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, const char *@<r9>, int, char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021768`
- `0x180022f88`
- `0x180037224`
- `0x1800449c8`
- `0x180044b38`
- `0x180044d48`
- `0x1800695d0`
- `0x180079540`
- `0x18007ac50`
- `0x18007ba24`
- `0x18008dc94`
- `0x18009252c`
- `0x1800a3514`
- `0x1800a3520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069909`
- `GDI32!StartPage` at `0x18006976d`
- `GDI32!StartPage` at `0x18006976d`
- `GDI32!pldcGet` at `0x1800696f1`
- `GDI32!pldcGet` at `0x1800696f1`
- `GDI32!GdiSetLastError` at `0x180069b18`
- `GDI32!GdiSetLastError` at `0x180069b18`
- `ntdll!RtlAllocateHeap` at `0x180069984`
- `ntdll!RtlAllocateHeap` at `0x180069984`
- `USER32!GetAppCompatFlags2` at `0x18006968f`
- `USER32!GetAppCompatFlags2` at `0x1800698cb`
- `USER32!GetAppCompatFlags2` at `0x18006968f`
- `USER32!GetAppCompatFlags2` at `0x1800698cb`
- `win32u!NtGdiExtEscape` at `0x180069a89`
- `win32u!NtGdiExtEscape` at `0x180069a89`
- `win32u!NtGdiGetTransform` at `0x1800697cd`
- `win32u!NtGdiGetTransform` at `0x1800697cd`
- `win32u!NtGdiIsDcInXfer` at `0x1800696c9`
- `win32u!NtGdiIsDcInXfer` at `0x1800696c9`

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
    MF_ModifyWorldTransform(v9, qword_1800BF868, 4);
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
0x1800695d0  push    rbp
0x1800695d2  push    rbx
0x1800695d3  push    rsi
0x1800695d4  push    rdi
0x1800695d5  push    r12
0x1800695d7  push    r13
0x1800695d9  push    r14
0x1800695db  push    r15
0x1800695dd  lea     rbp, [rsp-1A8h]
0x1800695e5  sub     rsp, 2A8h
0x1800695ec  mov     rax, cs:__security_cookie
0x1800695f3  xor     rax, rsp
0x1800695f6  mov     [rbp+1E0h+var_50], rax
0x1800695fd  mov     r12, r9
0x180069600  mov     esi, r8d
0x180069603  mov     edi, edx
0x180069605  mov     r13, rcx
0x180069608  mov     [rsp+2E0h+var_288], rcx
0x18006960d  mov     r14, [rbp+1E0h+arg_28]
0x180069614  mov     [rsp+2E0h+var_2A0], r14
0x180069619  xorps   xmm0, xmm0
0x18006961c  xor     eax, eax
0x18006961e  movups  [rsp+2E0h+var_278], xmm0
0x180069623  mov     [rsp+2E0h+var_268], rax
0x180069628  xor     edx, edx; Val
0x18006962a  mov     r8d, 208h; Size
0x180069630  lea     rcx, [rbp+1E0h+Src]; void *
0x180069634  call    memset_0
0x180069639  cmp     edi, 100h
0x18006963f  jnz     short loc_18006967F
0x180069641  lea     rdx, [rbp+1E0h+Src]
0x180069645  mov     rcx, r13; hdc
0x180069648  call    GetETM
0x18006964d  test    eax, eax
0x18006964f  jz      loc_180069B1E
0x180069655  movsxd  rax, [rbp+1E0h+arg_20]
0x18006965c  mov     r8d, 34h ; '4'
0x180069662  cmp     rax, r8
0x180069665  cmovb   r8, rax; Size
0x180069669  lea     rdx, [rbp+1E0h+Src]; Src
0x18006966d  mov     rcx, r14; void *
0x180069670  call    memcpy_0
0x180069675  mov     eax, 1
0x18006967a  jmp     loc_180069A8F
0x18006967f  xor     ebx, ebx
0x180069681  cmp     edi, 19h
0x180069684  jnz     loc_1800698A8
0x18006968a  mov     ecx, 400h
0x18006968f  call    cs:__imp_GetAppCompatFlags2
0x180069695  test    al, 8
0x180069697  jnz     loc_180069B1E
0x18006969d  lea     eax, [rbx+14h]
0x1800696a0  test    esi, esi
0x1800696a2  cmovnz  eax, esi
0x1800696a5  mov     esi, eax
0x1800696a7  mov     eax, r13d
0x1800696aa  and     eax, 7F0000h
0x1800696af  mov     r14d, eax
0x1800696b2  mov     [rsp+2E0h+var_298], ebx
0x1800696b6  cmp     eax, 10000h
0x1800696bb  jz      loc_180069A4F
0x1800696c1  lea     rdx, [rsp+2E0h+var_298]
0x1800696c6  mov     rcx, r13
0x1800696c9  call    cs:__imp_NtGdiIsDcInXfer
0x1800696cf  test    eax, eax
0x1800696d1  js      loc_180069B1E
0x1800696d7  cmp     [rsp+2E0h+var_298], ebx
0x1800696db  jnz     loc_180069A4F
0x1800696e1  cmp     r14d, 660000h
0x1800696e8  jz      loc_180069B1E
0x1800696ee  mov     rcx, r13
0x1800696f1  call    cs:__imp_pldcGet
0x1800696f7  mov     r15, rax
0x1800696fa  test    rax, rax
0x1800696fd  jz      loc_180069B13
0x180069703  cmp     r14d, 660000h
0x18006970a  jz      loc_180069B13
0x180069710  mov     ecx, [rax+8]
0x180069713  test    ecx, 10020h
0x180069719  jz      short loc_180069736
0x18006971b  test    cl, 20h
0x18006971e  jz      short loc_180069728
0x180069720  mov     rcx, rax
0x180069723  call    vSAPCallback
0x180069728  mov     ecx, [r15+8]
0x18006972c  bt      ecx, 10h
0x180069730  jb      loc_180069B1E
0x180069736  lea     eax, [rdi-1000h]
0x18006973c  mov     r14d, 1
0x180069742  cmp     eax, 2
0x180069745  jbe     short loc_180069764
0x180069747  lea     eax, [rdi-201h]
0x18006974d  cmp     eax, r14d
0x180069750  jbe     short loc_180069764
0x180069752  cmp     edi, 25h ; '%'
0x180069755  jz      short loc_180069764
0x180069757  cmp     edi, 13h
0x18006975a  jz      short loc_180069764
0x18006975c  cmp     edi, 100Fh
0x180069762  jnz     short loc_180069773
0x180069764  bt      ecx, 8
0x180069768  jnb     short loc_180069773
0x18006976a  mov     rcx, r13; hdc
0x18006976d  call    cs:__imp_StartPage
0x180069773  cmp     dword ptr [r15+0Ch], 2
0x180069778  jnz     loc_180069916
0x18006977e  test    dword ptr [r15+8], 20000h
0x180069786  jz      loc_180069916
0x18006978c  lea     eax, [rdi-1015h]
0x180069792  cmp     eax, r14d
0x180069795  jbe     loc_180069904
0x18006979b  cmp     edi, 11h
0x18006979e  jz      loc_18006992E
0x1800697a4  cmp     edi, 8
0x1800697a7  jz      loc_18006992E
0x1800697ad  lea     eax, [rdi-1017h]
0x1800697b3  cmp     eax, r14d
0x1800697b6  jbe     loc_18006992E
0x1800697bc  mov     [rsp+2E0h+var_290], ebx
0x1800697c0  lea     r8, [rsp+2E0h+var_278]
0x1800697c5  mov     edx, 203h
0x1800697ca  mov     rcx, r13
0x1800697cd  call    cs:__imp_NtGdiGetTransform
0x1800697d3  test    eax, eax
0x1800697d5  jz      short loc_180069830
0x1800697d7  movss   xmm1, cs:__real@3f800000
0x1800697df  movss   xmm0, dword ptr [rsp+2E0h+var_278]
0x1800697e5  ucomiss xmm0, xmm1
0x1800697e8  jp      short loc_180069816
0x1800697ea  jnz     short loc_180069816
0x1800697ec  movss   xmm0, dword ptr [rsp+2E0h+var_278+0Ch]
0x1800697f2  ucomiss xmm0, xmm1
0x1800697f5  jp      short loc_180069816
0x1800697f7  jnz     short loc_180069816
0x1800697f9  xorps   xmm1, xmm1
0x1800697fc  movss   xmm0, dword ptr [rsp+2E0h+var_278+4]
0x180069802  ucomiss xmm0, xmm1
0x180069805  jp      short loc_180069816
0x180069807  jnz     short loc_180069816
0x180069809  movss   xmm0, dword ptr [rsp+2E0h+var_278+8]
0x18006980f  ucomiss xmm0, xmm1
0x180069812  jp      short loc_180069816
0x180069814  jz      short loc_180069830
0x180069816  mov     [rsp+2E0h+var_290], r14d
0x18006981b  mov     r8d, 4
0x180069821  lea     rdx, qword_1800BF868
0x180069828  mov     rcx, r13
0x18006982b  call    MF_ModifyWorldTransform
0x180069830  mov     [rsp+2E0h+var_2C0], 6Ah ; 'j'
0x180069838  mov     r9, r12
0x18006983b  mov     r8d, esi
0x18006983e  mov     edx, edi
0x180069840  mov     rcx, r13
0x180069843  call    MF_WriteEscape
0x180069848  cmp     [rsp+2E0h+var_290], ebx
0x18006984c  jz      short loc_180069861
0x18006984e  mov     r8d, 4
0x180069854  lea     rdx, [rsp+2E0h+var_278]
0x180069859  mov     rcx, r13
0x18006985c  call    MF_ModifyWorldTransform
0x180069861  cmp     [rsp+2E0h+var_2A0], rbx
0x180069866  jz      short loc_180069874
0x180069868  cmp     [rbp+1E0h+arg_20], ebx
0x18006986e  jnz     loc_180069916
0x180069874  cmp     edi, 13h
0x180069877  jz      short loc_180069886
0x180069879  cmp     edi, 1013h
0x18006987f  jz      short loc_180069886
0x180069881  cmp     edi, 25h ; '%'
0x180069884  jnz     short loc_180069899
0x180069886  cmp     esi, 2
0x180069889  jl      short loc_180069901
0x18006988b  movzx   eax, word ptr [r12]
0x180069890  lea     ecx, [rax+2]
0x180069893  cmp     esi, ecx
0x180069895  jl      short loc_180069901
0x180069897  mov     esi, eax
0x180069899  cmp     esi, r14d
0x18006989c  cmovg   r14d, esi
0x1800698a0  mov     eax, r14d
0x1800698a3  jmp     loc_180069A8F
0x1800698a8  cmp     edi, 8
0x1800698ab  jnz     short loc_1800698DF
0x1800698ad  cmp     dword ptr [r12], 102h
0x1800698b5  jz      loc_180069675
0x1800698bb  cmp     dword ptr [r12], 19h
0x1800698c0  jnz     loc_1800696A7
0x1800698c6  mov     ecx, 400h
0x1800698cb  call    cs:__imp_GetAppCompatFlags2
0x1800698d1  test    dil, al
0x1800698d4  jz      loc_1800696A7
0x1800698da  jmp     loc_180069B1E
0x1800698df  cmp     edi, 102h
0x1800698e5  jnz     loc_1800696A7
0x1800698eb  mov     r8, r14; struct _KERNPAIR *
0x1800698ee  mov     edx, [rbp+1E0h+arg_20]; unsigned int
0x1800698f4  mov     rcx, r13; hdc
0x1800698f7  call    ?GetPairKernTable@@YAKPEAUHDC__@@KPEAU_KERNPAIR@@@Z; GetPairKernTable(HDC__ *,ulong,_KERNPAIR *)
0x1800698fc  jmp     loc_180069A8F
0x180069901  or      ebx, 0FFFFFFFFh
0x180069904  mov     ecx, 57h ; 'W'; dwErrCode
0x180069909  call    cs:__imp_SetLastError
0x18006990f  mov     eax, ebx
0x180069911  jmp     loc_180069A8F
0x180069916  cmp     edi, 202h
0x18006991c  jz      loc_180069AB9
0x180069922  cmp     edi, 201h
0x180069928  jz      loc_1800699E4
0x18006992e  cmp     edi, 1016h
0x180069934  jz      short loc_180069942
0x180069936  cmp     edi, 1015h
0x18006993c  jnz     loc_1800699E4
0x180069942  test    byte ptr [r15+8], 40h
0x180069947  jnz     loc_1800699E4
0x18006994d  test    esi, esi
0x18006994f  js      loc_180069B1E
0x180069955  lea     eax, [rsi+1Fh]
0x180069958  cmp     eax, 1Fh
0x18006995b  jb      loc_180069B1E
0x180069961  lea     ecx, [rax+3]
0x180069964  cmp     ecx, eax
0x180069966  jb      loc_180069B1E
0x18006996c  and     ecx, 0FFFFFFFCh
0x18006996f  mov     r13d, ecx
0x180069972  mov     r8d, ecx; Size
0x180069975  mov     rcx, gs:60h
0x18006997e  xor     edx, edx; Flags
0x180069980  mov     rcx, [rcx+30h]; HeapHandle
0x180069984  call    cs:__imp_RtlAllocateHeap
0x18006998a  mov     r14, rax
0x18006998d  test    rax, rax
0x180069990  jz      loc_180069AB2
0x180069996  add     r13d, 0FFFFFFF0h
0x18006999a  mov     [rax+10h], r13d
0x18006999e  mov     [rax+14h], edi
0x1800699a1  mov     [rax+18h], esi
0x1800699a4  movsxd  r8, esi; Size
0x1800699a7  lea     rcx, [rax+1Ch]; void *
0x1800699ab  mov     rdx, r12; Src
0x1800699ae  call    memcpy_0
0x1800699b3  lea     rax, [r15+90h]
0x1800699ba  mov     rcx, [rax+8]
0x1800699be  cmp     [rcx], rax
0x1800699c1  jz      short loc_1800699CA
0x1800699c3  mov     ecx, 3
0x1800699c8  int     29h; Win8: RtlFailFast(ecx)
0x1800699ca  mov     [r14], rax
0x1800699cd  mov     [r14+8], rcx
0x1800699d1  mov     [rcx], r14
0x1800699d4  mov     [rax+8], r14
0x1800699d8  add     [r15+88h], r13d
0x1800699df  mov     r13, [rsp+2E0h+var_288]
0x1800699e4  mov     r14, [rsp+2E0h+var_2A0]
0x1800699e9  cmp     [r15+30h], rbx
0x1800699ed  jz      short loc_180069A4F
0x1800699ef  mov     dword ptr [rsp+2E0h+var_288], edi
0x1800699f3  mov     dword ptr [rsp+2E0h+var_288+4], esi
0x1800699f7  mov     [rsp+2E0h+var_280], r12
0x1800699fc  mov     rdx, r15
0x1800699ff  lea     rcx, [rsp+2E0h+var_290]
0x180069a04  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x180069a09  nop
0x180069a0a  mov     [rsp+2E0h+var_2A8], r14; void *
0x180069a0f  mov     eax, [rbp+1E0h+arg_20]
0x180069a15  mov     [rsp+2E0h+var_2B0], eax; unsigned int
0x180069a19  lea     rax, [rsp+2E0h+var_288]
0x180069a1e  mov     [rsp+2E0h+var_2B8], rax; void *
0x180069a23  mov     [rsp+2E0h+var_2C0], 10h; unsigned int
0x180069a2b  mov     r9d, 0Bh; int
0x180069a31  mov     r8, r13; HDC
0x180069a34  mov     rdx, [r15+30h]; void *
0x180069a38  lea     rcx, [rsp+2E0h+var_290]; this
0x180069a3d  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x180069a42  nop
0x180069a43  xor     edx, edx; struct _UMPD *
0x180069a45  lea     rcx, [rsp+2E0h+var_290]; this
0x180069a4a  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180069a4f  mov     r8, [rsp+2E0h+var_2A0]
0x180069a54  mov     rax, r8
0x180069a57  neg     rax
0x180069a5a  sbb     edx, edx
0x180069a5c  and     edx, [rbp+1E0h+arg_20]
0x180069a62  mov     rax, r12
0x180069a65  neg     rax
0x180069a68  sbb     ecx, ecx
0x180069a6a  and     ecx, esi
0x180069a6c  mov     [rsp+2E0h+var_2A8], r8
0x180069a71  mov     [rsp+2E0h+var_2B0], edx
0x180069a75  mov     [rsp+2E0h+var_2B8], r12
0x180069a7a  mov     [rsp+2E0h+var_2C0], ecx
0x180069a7e  mov     r9d, edi
0x180069a81  xor     r8d, r8d
0x180069a84  xor     edx, edx
0x180069a86  mov     rcx, r13
0x180069a89  call    cs:__imp_NtGdiExtEscape
0x180069a8f  mov     rcx, [rbp+1E0h+var_50]
0x180069a96  xor     rcx, rsp; StackCookie
0x180069a99  call    __security_check_cookie
0x180069a9e  add     rsp, 2A8h
0x180069aa5  pop     r15
  ... truncated ...
```
