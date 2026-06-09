# CRecvFromPipe::SplitAndAdd(IAttributesRaw *,_IASATTRIBUTE *,IASTYPEENUM,ulong,ulong)

- ea: `0x1800181e8`
- end: `0x1800186b0`
- name: `?SplitAndAdd@CRecvFromPipe@@AEAAJPEAUIAttributesRaw@@PEAU_IASATTRIBUTE@@W4IASTYPEENUM@@KK@Z`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800186b8`

## callees

- `0x180002106`
- `0x1800094e4`
- `0x1800181e8`
- `0x18001d31c`
- `0x18002ada0`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001868a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001868a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ef5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001824e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001824e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184fc`

## pseudocode

```c
__int64 __fastcall CRecvFromPipe::SplitAndAdd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned int cb)
{
  __int64 v7; // r14
  LPVOID *v8; // rsi
  unsigned int v9; // edi
  _QWORD *v10; // r12
  __int64 v11; // rdx
  signed int v12; // ebx
  LPVOID *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 i; // r15
  void *v17; // rcx
  SIZE_T v18; // rcx
  __int64 j; // rbx
  LPVOID *v20; // r15
  void *v21; // rcx
  char *Src; // [rsp+38h] [rbp-70h]
  char *v24; // [rsp+40h] [rbp-68h]
  LPVOID *v25; // [rsp+48h] [rbp-60h]
  size_t v26; // [rsp+50h] [rbp-58h]
  unsigned int Size; // [rsp+B0h] [rbp+8h]
  unsigned int Sizea; // [rsp+B0h] [rbp+8h]

  v7 = 0;
  v8 = 0;
  v9 = a5 / cb;
  if ( a5 % cb )
    ++v9;
  v10 = CoTaskMemAlloc(16LL * v9);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_9;
    }
    WppDbgPrint("Unable to allocate memory for attribute position array while split and add of attributese in out-bound packet");
    v11 = 54;
LABEL_8:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
LABEL_9:
    v12 = -2147024882;
    goto LABEL_49;
  }
  v13 = (LPVOID *)CoTaskMemAlloc(8LL * v9);
  v8 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_9;
    }
    WppDbgPrint("Unable to allocate memorywhile split and add of out-bound attribues");
    v11 = 55;
    goto LABEL_8;
  }
  v14 = IASAttributeAlloc(v9, v13);
  v7 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate attributes while splitting out-boundattributes");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    if ( (int)v7 > 0 )
      v12 = (unsigned __int16)v7 | 0x80070000;
    else
      v12 = v7;
  }
  else
  {
    if ( a4 == 5 )
    {
      Src = *(char **)(a3 + 24);
      v15 = cb;
      Size = cb;
      for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
      {
        v25 = &v8[i];
        *((_QWORD *)*v25 + 4) = 0;
        *((_QWORD *)*v25 + 3) = CoTaskMemAlloc(v15 + 1);
        v17 = (void *)*((_QWORD *)*v25 + 3);
        if ( !v17 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to allocate memory for new attribute valueswhile split and add of out-bound attribues");
            v11 = 57;
            goto LABEL_8;
          }
          goto LABEL_9;
        }
        memcpy_0(v17, Src, Size);
        *(_BYTE *)(Size + *((_QWORD *)*v25 + 3)) = 0;
        *((_DWORD *)*v25 + 4) = 5;
        *((_DWORD *)*v25 + 2) = *(_DWORD *)(a3 + 8);
        *((_DWORD *)*v25 + 1) = *(_DWORD *)(a3 + 4);
        Src += Size;
        a5 -= Size;
        v15 = a5;
        if ( a5 > cb )
          v15 = cb;
        Size = v15;
        v10[2 * (unsigned int)i + 1] = *v25;
      }
    }
    else
    {
      v24 = *(char **)(a3 + 32);
      v18 = cb;
      Sizea = cb;
      for ( j = 0; (unsigned int)j < v9; j = (unsigned int)(j + 1) )
      {
        v26 = (unsigned int)v18;
        v20 = &v8[j];
        *((_QWORD *)*v20 + 4) = CoTaskMemAlloc(v18);
        v21 = (void *)*((_QWORD *)*v20 + 4);
        if ( !v21 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Unable to allocate memory for new attribute valueswhile split and add of out-bound attribues");
            v11 = 58;
            goto LABEL_8;
          }
          goto LABEL_9;
        }
        memcpy_0(v21, v24, v26);
        *((_DWORD *)*v20 + 6) = Sizea;
        *((_DWORD *)*v20 + 4) = a4;
        *((_DWORD *)*v20 + 2) = *(_DWORD *)(a3 + 8);
        *((_DWORD *)*v20 + 1) = *(_DWORD *)(a3 + 4);
        v24 += Sizea;
        a5 -= Sizea;
        v18 = a5;
        if ( a5 > cb )
          v18 = cb;
        Sizea = v18;
        v10[2 * (unsigned int)j + 1] = *v20;
      }
    }
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)a2 + 24LL))(a2, v9, v10);
    if ( v12 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Failed to add attributes to the collectionon split and add out-bound attributes");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
  }
LABEL_49:
  if ( v8 )
  {
    if ( !(_DWORD)v7 && v9 )
    {
      do
      {
        IASAttributeRelease(v8[v7]);
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < v9 );
    }
    CoTaskMemFree(v8);
  }
  if ( v10 )
    CoTaskMemFree(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800181e8  mov     rax, rsp
0x1800181eb  mov     [rax+20h], r9d
0x1800181ef  mov     [rax+18h], r8
0x1800181f3  mov     [rax+10h], rdx
0x1800181f7  mov     [rax+8], rcx
0x1800181fb  push    rbx
0x1800181fc  push    rsi
0x1800181fd  push    rdi
0x1800181fe  push    r12
0x180018200  push    r13
0x180018202  push    r14
0x180018204  push    r15
0x180018206  sub     rsp, 70h
0x18001820a  mov     r15, r8
0x18001820d  mov     r13d, dword ptr [rsp+0A8h+cb]
0x180018215  mov     [rsp+0A8h+var_84], 0
0x18001821d  xor     r14d, r14d
0x180018220  mov     [rax-80h], r14d
0x180018224  xor     esi, esi
0x180018226  mov     [rax-50h], rsi
0x18001822a  mov     [rax-48h], rsi
0x18001822e  xor     edx, edx
0x180018230  mov     eax, [rax+28h]
0x180018233  div     r13d
0x180018236  mov     edi, eax
0x180018238  mov     [rsp+0A8h+var_84], eax
0x18001823c  test    edx, edx
0x18001823e  jz      short loc_180018246
0x180018240  inc     edi
0x180018242  mov     [rsp+0A8h+var_84], edi
0x180018246  mov     ebx, edi
0x180018248  mov     ecx, edi
0x18001824a  shl     rcx, 4; cb
0x18001824e  call    cs:__imp_CoTaskMemAlloc
0x180018254  mov     r12, rax
0x180018257  mov     [rsp+0A8h+var_48], rax
0x18001825c  test    rax, rax
0x18001825f  jnz     short loc_1800182C0
0x180018261  lea     rax, WPP_GLOBAL_Control
0x180018268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001826f  cmp     rcx, rax
0x180018272  jz      short loc_1800182B2
0x180018274  cmp     byte ptr [rcx+19h], 2
0x180018278  jb      short loc_1800182B2
0x18001827a  test    dword ptr [rcx+1Ch], 100h
0x180018281  jz      short loc_1800182B2
0x180018283  lea     rcx, aUnableToAlloca_15; "Unable to allocate memory for attribute"...
0x18001828a  call    WppDbgPrint
0x18001828f  lea     edx, [r12+36h]
0x180018294  lea     r9, aNpsrad; "NPSRAD"
0x18001829b  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x1800182a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182a9  mov     rcx, [rcx+10h]
0x1800182ad  call    WPP_SF_s
0x1800182b2  mov     ebx, 8007000Eh
0x1800182b7  mov     [rsp+0A8h+var_88], ebx
0x1800182bb  jmp     loc_180018663
0x1800182c0  lea     rcx, ds:0[rbx*8]; cb
0x1800182c8  call    cs:__imp_CoTaskMemAlloc
0x1800182ce  mov     rsi, rax
0x1800182d1  mov     [rsp+0A8h+var_50], rax
0x1800182d6  test    rax, rax
0x1800182d9  jnz     short loc_18001830E
0x1800182db  lea     rax, WPP_GLOBAL_Control
0x1800182e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182e9  cmp     rcx, rax
0x1800182ec  jz      short loc_1800182B2
0x1800182ee  cmp     byte ptr [rcx+19h], 2
0x1800182f2  jb      short loc_1800182B2
0x1800182f4  test    dword ptr [rcx+1Ch], 100h
0x1800182fb  jz      short loc_1800182B2
0x1800182fd  lea     rcx, aUnableToAlloca_17; "Unable to allocate memorywhile split an"...
0x180018304  call    WppDbgPrint
0x180018309  lea     edx, [rsi+37h]
0x18001830c  jmp     short loc_180018294
0x18001830e  mov     rdx, rsi
0x180018311  mov     ecx, edi
0x180018313  call    IASAttributeAlloc
0x180018318  mov     r14d, eax
0x18001831b  mov     [rsp+0A8h+var_80], eax
0x18001831f  test    eax, eax
0x180018321  jz      short loc_180018390
0x180018323  lea     rax, WPP_GLOBAL_Control
0x18001832a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018331  cmp     rcx, rax
0x180018334  jz      short loc_180018374
0x180018336  cmp     byte ptr [rcx+19h], 2
0x18001833a  jb      short loc_180018374
0x18001833c  test    dword ptr [rcx+1Ch], 100h
0x180018343  jz      short loc_180018374
0x180018345  lea     rcx, aUnableToAlloca_1; "Unable to allocate attributes while spl"...
0x18001834c  call    WppDbgPrint
0x180018351  mov     edx, 38h ; '8'
0x180018356  lea     r9, aNpsrad; "NPSRAD"
0x18001835d  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001836b  mov     rcx, [rcx+10h]
0x18001836f  call    WPP_SF_s
0x180018374  test    r14d, r14d
0x180018377  jg      short loc_180018381
0x180018379  mov     ebx, r14d
0x18001837c  jmp     loc_1800182B7
0x180018381  movzx   ebx, r14w
0x180018385  or      ebx, 80070000h
0x18001838b  jmp     loc_1800182B7
0x180018390  cmp     [rsp+0A8h+arg_18], 5
0x180018398  jnz     loc_1800184D4
0x18001839e  mov     rax, [r15+18h]
0x1800183a2  mov     [rsp+0A8h+Src], rax
0x1800183a7  mov     ecx, r13d
0x1800183aa  mov     dword ptr [rsp+0A8h+Size], ecx
0x1800183b1  xor     r15d, r15d
0x1800183b4  mov     [rsp+0A8h+var_7C], r15d
0x1800183b9  cmp     r15d, edi
0x1800183bc  jnb     loc_1800185EE
0x1800183c2  mov     eax, r15d
0x1800183c5  mov     [rsp+0A8h+var_58], rax
0x1800183ca  lea     rbx, [rsi+r15*8]
0x1800183ce  mov     [rsp+0A8h+var_60], rbx
0x1800183d3  mov     rax, [rbx]
0x1800183d6  mov     qword ptr [rax+20h], 0
0x1800183de  inc     ecx; cb
0x1800183e0  call    cs:__imp_CoTaskMemAlloc
0x1800183e6  mov     rcx, [rbx]
0x1800183e9  mov     [rcx+18h], rax
0x1800183ed  mov     rax, [rbx]
0x1800183f0  mov     rcx, [rax+18h]; void *
0x1800183f4  test    rcx, rcx
0x1800183f7  jnz     short loc_18001843D
0x1800183f9  lea     rax, WPP_GLOBAL_Control
0x180018400  mov     rcx, cs:WPP_GLOBAL_Control
0x180018407  cmp     rcx, rax
0x18001840a  jz      loc_1800182B2
0x180018410  cmp     byte ptr [rcx+19h], 2
0x180018414  jb      loc_1800182B2
0x18001841a  test    dword ptr [rcx+1Ch], 100h
0x180018421  jz      loc_1800182B2
0x180018427  lea     rcx, aUnableToAlloca_11; "Unable to allocate memory for new attri"...
0x18001842e  call    WppDbgPrint
0x180018433  mov     edx, 39h ; '9'
0x180018438  jmp     loc_180018294
0x18001843d  mov     ebx, dword ptr [rsp+0A8h+Size]
0x180018444  mov     r8d, ebx; Size
0x180018447  mov     rdx, [rsp+0A8h+Src]; Src
0x18001844c  call    memcpy_0
0x180018451  mov     rdx, [rsp+0A8h+var_60]
0x180018456  mov     rax, [rdx]
0x180018459  mov     rcx, [rax+18h]
0x18001845d  mov     byte ptr [rbx+rcx], 0
0x180018461  mov     rax, [rdx]
0x180018464  mov     ecx, [rsp+0A8h+arg_18]
0x18001846b  mov     [rax+10h], ecx
0x18001846e  mov     rcx, [rdx]
0x180018471  mov     r8, [rsp+0A8h+arg_10]
0x180018479  mov     eax, [r8+8]
0x18001847d  mov     [rcx+8], eax
0x180018480  mov     rcx, [rdx]
0x180018483  mov     eax, [r8+4]
0x180018487  mov     [rcx+4], eax
0x18001848a  mov     rcx, [rsp+0A8h+Src]
0x18001848f  add     rcx, rbx
0x180018492  mov     [rsp+0A8h+Src], rcx
0x180018497  mov     eax, [rsp+0A8h+arg_20]
0x18001849e  sub     eax, dword ptr [rsp+0A8h+Size]
0x1800184a5  mov     [rsp+0A8h+arg_20], eax
0x1800184ac  mov     ecx, eax
0x1800184ae  cmp     eax, r13d
0x1800184b1  cmova   ecx, r13d
0x1800184b5  mov     dword ptr [rsp+0A8h+Size], ecx
0x1800184bc  mov     r8, [rsp+0A8h+var_58]
0x1800184c1  add     r8, r8
0x1800184c4  mov     rax, [rdx]
0x1800184c7  mov     [r12+r8*8+8], rax
0x1800184cc  inc     r15d
0x1800184cf  jmp     loc_1800183B4
0x1800184d4  mov     rax, [r15+20h]
0x1800184d8  mov     [rsp+0A8h+var_68], rax
0x1800184dd  mov     rcx, r13; cb
0x1800184e0  mov     dword ptr [rsp+0A8h+Size], ecx
0x1800184e7  xor     ebx, ebx
0x1800184e9  mov     [rsp+0A8h+var_78], ebx
0x1800184ed  cmp     ebx, edi
0x1800184ef  jnb     loc_1800185EE
0x1800184f5  mov     eax, ecx
0x1800184f7  mov     [rsp+0A8h+var_58], rax
0x1800184fc  call    cs:__imp_CoTaskMemAlloc
0x180018502  mov     ecx, ebx
0x180018504  mov     [rsp+0A8h+var_60], rcx
0x180018509  lea     r15, [rsi+rbx*8]
0x18001850d  mov     rcx, [r15]
0x180018510  mov     [rcx+20h], rax
0x180018514  mov     rax, [r15]
0x180018517  mov     rcx, [rax+20h]; void *
0x18001851b  test    rcx, rcx
0x18001851e  jnz     short loc_180018564
0x180018520  lea     rax, WPP_GLOBAL_Control
0x180018527  mov     rcx, cs:WPP_GLOBAL_Control
0x18001852e  cmp     rcx, rax
0x180018531  jz      loc_1800182B2
0x180018537  cmp     byte ptr [rcx+19h], 2
0x18001853b  jb      loc_1800182B2
0x180018541  test    dword ptr [rcx+1Ch], 100h
0x180018548  jz      loc_1800182B2
0x18001854e  lea     rcx, aUnableToAlloca_11; "Unable to allocate memory for new attri"...
0x180018555  call    WppDbgPrint
0x18001855a  mov     edx, 3Ah ; ':'
0x18001855f  jmp     loc_180018294
0x180018564  mov     r8, [rsp+0A8h+var_58]; Size
0x180018569  mov     rdx, [rsp+0A8h+var_68]; Src
0x18001856e  call    memcpy_0
0x180018573  mov     rax, [r15]
0x180018576  mov     r8d, dword ptr [rsp+0A8h+Size]
0x18001857e  mov     [rax+18h], r8d
0x180018582  mov     rax, [r15]
0x180018585  mov     ecx, [rsp+0A8h+arg_18]
0x18001858c  mov     [rax+10h], ecx
0x18001858f  mov     rcx, [r15]
0x180018592  mov     rdx, [rsp+0A8h+arg_10]
0x18001859a  mov     eax, [rdx+8]
0x18001859d  mov     [rcx+8], eax
0x1800185a0  mov     rcx, [r15]
0x1800185a3  mov     eax, [rdx+4]
0x1800185a6  mov     [rcx+4], eax
0x1800185a9  mov     rcx, [rsp+0A8h+var_68]
0x1800185ae  add     rcx, r8
0x1800185b1  mov     [rsp+0A8h+var_68], rcx
0x1800185b6  mov     eax, [rsp+0A8h+arg_20]
0x1800185bd  sub     eax, r8d
0x1800185c0  mov     [rsp+0A8h+arg_20], eax
0x1800185c7  mov     ecx, eax
0x1800185c9  cmp     eax, r13d
0x1800185cc  cmova   ecx, r13d
0x1800185d0  mov     dword ptr [rsp+0A8h+Size], ecx
0x1800185d7  mov     rdx, [rsp+0A8h+var_60]
0x1800185dc  add     rdx, rdx
0x1800185df  mov     rax, [r15]
0x1800185e2  mov     [r12+rdx*8+8], rax
0x1800185e7  inc     ebx
0x1800185e9  jmp     loc_1800184E9
0x1800185ee  mov     rcx, [rsp+0A8h+arg_8]
0x1800185f6  mov     rax, [rcx]
0x1800185f9  mov     r8, r12
0x1800185fc  mov     edx, edi
0x1800185fe  mov     rax, [rax+18h]
0x180018602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018607  mov     ebx, eax
0x180018609  mov     [rsp+0A8h+var_88], eax
0x18001860d  test    eax, eax
0x18001860f  jns     short loc_180018663
0x180018611  lea     rax, WPP_GLOBAL_Control
0x180018618  mov     rcx, cs:WPP_GLOBAL_Control
0x18001861f  cmp     rcx, rax
0x180018622  jz      short loc_180018663
0x180018624  cmp     byte ptr [rcx+19h], 2
0x180018628  jb      short loc_180018663
0x18001862a  test    dword ptr [rcx+1Ch], 100h
0x180018631  jz      short loc_180018663
0x180018633  lea     rcx, aFailedToAddAtt; "Failed to add attributes to the collect"...
0x18001863a  call    WppDbgPrint
0x18001863f  mov     edx, 3Bh ; ';'
0x180018644  lea     r9, aNpsrad; "NPSRAD"
0x18001864b  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180018652  mov     rcx, cs:WPP_GLOBAL_Control
0x180018659  mov     rcx, [rcx+10h]
0x18001865d  call    WPP_SF_s
0x180018662  nop
0x180018663  test    rsi, rsi
0x180018666  jz      short loc_180018690
0x180018668  test    r14d, r14d
0x18001866b  jnz     short loc_180018682
0x18001866d  test    edi, edi
0x18001866f  jz      short loc_180018682
0x180018671  mov     rcx, [rsi+r14*8]; pv
0x180018675  call    IASAttributeRelease
0x18001867a  inc     r14d
0x18001867d  cmp     r14d, edi
0x180018680  jb      short loc_180018671
0x180018682  test    rsi, rsi
0x180018685  jz      short loc_180018690
0x180018687  mov     rcx, rsi; pv
0x18001868a  call    cs:__imp_CoTaskMemFree
0x180018690  test    r12, r12
0x180018693  jz      short loc_18001869E
0x180018695  mov     rcx, r12; pv
0x180018698  call    cs:__imp_CoTaskMemFree
0x18001869e  mov     eax, ebx
0x1800186a0  add     rsp, 70h
0x1800186a4  pop     r15
0x1800186a6  pop     r14
0x1800186a8  pop     r13
0x1800186aa  pop     r12
0x1800186ac  pop     rdi
0x1800186ad  pop     rsi
0x1800186ae  pop     rbx
0x1800186af  retn
0x18002ef0f  push    rbx
0x18002ef11  push    rbp
0x18002ef12  push    rsi
0x18002ef13  push    rdi
0x18002ef14  sub     rsp, 28h
  ... truncated ...
```
