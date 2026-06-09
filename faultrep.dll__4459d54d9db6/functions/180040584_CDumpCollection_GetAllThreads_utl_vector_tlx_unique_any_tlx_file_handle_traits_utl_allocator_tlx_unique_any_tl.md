# CDumpCollection::_GetAllThreads(utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>> &,ulong)

- ea: `0x180040584`
- end: `0x180040852`
- name: `?_GetAllThreads@CDumpCollection@@AEAAJAEAV?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@K@Z`
- size: `718`
- prototype: `__int64 __fastcall(DWORD **this, __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003f144`
- `0x18003f334`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x180040584`
- `0x180040b78`
- `0x180040cb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004075a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18004075a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800405be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800405be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040832`

## pseudocode

```c
__int64 __fastcall CDumpCollection::_GetAllThreads(DWORD **this, __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rbx
  __int64 v6; // rbx
  void *v7; // rcx
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD *v11; // rax
  DWORD *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // r15
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbp
  __int64 v17; // r14
  __int64 v18; // rbx
  void *v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  DWORD *v22; // rbx
  DWORD *v23; // rdi
  __int64 v24; // r14
  HANDLE v25; // rax
  void *v26; // rcx
  signed int LastError; // eax
  __int64 v28; // r14
  __int64 v29; // rdi
  __int64 v30; // rdi
  void *v31; // rcx

  v2 = *a2;
  v5 = a2[1] - *a2;
  a2[1] = *a2;
  v6 = v5 >> 3;
  while ( v6 )
  {
    --v6;
    v7 = *(void **)(v2 + 8 * v6);
    if ( (unsigned __int64)v7 + 1 > 1 )
      CloseHandle(v7);
  }
  v8 = CDumpCollection::_SnapAllThreads((CDumpCollection *)this);
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 73;
LABEL_13:
      WPP_SF_(v9[2], v10, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  v11 = this[300];
  v12 = this[301];
  if ( v11 == v12 )
  {
    v8 = -2147467259;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 74;
      goto LABEL_13;
    }
LABEL_47:
    v28 = *a2;
    v29 = a2[1] - *a2;
    a2[1] = *a2;
    v30 = v29 >> 3;
    while ( v30 )
    {
      --v30;
      v31 = *(void **)(v28 + 8 * v30);
      if ( (unsigned __int64)v31 + 1 > 1 )
        CloseHandle(v31);
    }
    return (unsigned int)v8;
  }
  v13 = a2[1];
  v14 = *a2;
  v15 = v12 - v11;
  v16 = (v13 - *a2) >> 3;
  if ( v15 > v16 )
  {
    if ( v15 > (a2[2] - v14) >> 3 )
    {
      v20 = 7 * ((unsigned __int64)((a2[2] - v14) >> 3) >> 2) + 8;
      if ( v20 < v15 )
        v20 = v15;
      if ( v20 > 0xFFFFFFFFFFFFFFFLL )
        v20 = 0xFFFFFFFFFFFFFFFLL;
      if ( v15 > v20
        || !(unsigned __int8)utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::_SetCapacity(a2) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
        v8 = -2147024882;
        goto LABEL_47;
      }
      v13 = a2[1];
    }
    v21 = 0;
    if ( v15 != v16 )
    {
      do
        *(_QWORD *)(v13 + 8 * v21++) = 0;
      while ( v21 != v15 - v16 );
    }
    v14 = *a2;
    v17 = *a2 + 8 * v15;
    a2[1] = v17;
  }
  else
  {
    v17 = v14 + 8 * v15;
    a2[1] = v17;
    v18 = (v13 - v17) >> 3;
    if ( v18 )
    {
      do
      {
        --v18;
        v19 = *(void **)(v17 + 8 * v18);
        if ( (unsigned __int64)v19 + 1 > 1 )
          CloseHandle(v19);
      }
      while ( v18 );
      v17 = a2[1];
      v14 = *a2;
    }
  }
  v22 = this[300];
  v23 = this[301];
  v24 = (v17 - v14) >> 3;
  while ( 1 )
  {
    if ( v22 == v23 )
      return 0;
    --v24;
    v25 = OpenThread(0x1FFFFFu, 0, *v22);
    v26 = *(void **)(v14 + 8 * v24);
    *(_QWORD *)(v14 + 8 * v24) = v25;
    if ( (unsigned __int64)v26 + 1 > 1 )
      CloseHandle(v26);
    v14 = *a2;
    if ( *(_QWORD *)(*a2 + 8 * v24) == -1 || *(_QWORD *)(*a2 + 8 * v24) == 0 )
      break;
    ++v22;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, (unsigned int)v8);
  if ( v8 < 0 )
    goto LABEL_47;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180040584  push    rbx
0x180040586  push    rbp
0x180040587  push    rsi
0x180040588  push    rdi
0x180040589  push    r13
0x18004058b  push    r14
0x18004058d  push    r15
0x18004058f  sub     rsp, 20h
0x180040593  mov     rdi, [rdx]
0x180040596  mov     rsi, rdx
0x180040599  mov     rbx, [rdx+8]
0x18004059d  mov     r13, rcx
0x1800405a0  sub     rbx, rdi
0x1800405a3  mov     [rdx+8], rdi
0x1800405a7  sar     rbx, 3
0x1800405ab  jmp     short loc_1800405C4
0x1800405ad  dec     rbx
0x1800405b0  mov     rcx, [rdi+rbx*8]; hObject
0x1800405b4  lea     rax, [rcx+1]
0x1800405b8  cmp     rax, 1
0x1800405bc  jbe     short loc_1800405C4
0x1800405be  call    cs:__imp_CloseHandle
0x1800405c4  test    rbx, rbx
0x1800405c7  jnz     short loc_1800405AD
0x1800405c9  mov     rcx, r13; this
0x1800405cc  call    ?_SnapAllThreads@CDumpCollection@@AEAAJXZ; CDumpCollection::_SnapAllThreads(void)
0x1800405d1  mov     ebx, eax
0x1800405d3  test    eax, eax
0x1800405d5  jns     short loc_1800405FF
0x1800405d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800405de  lea     rax, WPP_GLOBAL_Control
0x1800405e5  cmp     rcx, rax
0x1800405e8  jz      loc_18004080D
0x1800405ee  test    byte ptr [rcx+1Ch], 1
0x1800405f2  jz      loc_18004080D
0x1800405f8  mov     edx, 49h ; 'I'
0x1800405fd  jmp     short loc_18004063D
0x1800405ff  mov     rax, [r13+960h]
0x180040606  mov     rdi, [r13+968h]
0x18004060d  cmp     rax, rdi
0x180040610  jnz     short loc_180040652
0x180040612  mov     ebx, 80004005h
0x180040617  mov     rcx, cs:WPP_GLOBAL_Control
0x18004061e  lea     rax, WPP_GLOBAL_Control
0x180040625  cmp     rcx, rax
0x180040628  jz      loc_18004080D
0x18004062e  test    byte ptr [rcx+1Ch], 1
0x180040632  jz      loc_18004080D
0x180040638  mov     edx, 4Ah ; 'J'
0x18004063d  mov     rcx, [rcx+10h]
0x180040641  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x180040648  call    WPP_SF_
0x18004064d  jmp     loc_18004080D
0x180040652  mov     rbx, [rsi+8]
0x180040656  sub     rdi, rax
0x180040659  mov     r15, [rsi]
0x18004065c  mov     rbp, rbx
0x18004065f  sub     rbp, r15
0x180040662  sar     rdi, 2
0x180040666  sar     rbp, 3
0x18004066a  cmp     rdi, rbp
0x18004066d  ja      short loc_1800406AF
0x18004066f  lea     r14, [r15+rdi*8]
0x180040673  sub     rbx, r14
0x180040676  mov     [rsi+8], r14
0x18004067a  sar     rbx, 3
0x18004067e  test    rbx, rbx
0x180040681  jz      loc_18004072F
0x180040687  dec     rbx
0x18004068a  mov     rcx, [r14+rbx*8]; hObject
0x18004068e  lea     rax, [rcx+1]
0x180040692  cmp     rax, 1
0x180040696  jbe     short loc_18004069E
0x180040698  call    cs:__imp_CloseHandle
0x18004069e  test    rbx, rbx
0x1800406a1  jnz     short loc_180040687
0x1800406a3  mov     r14, [rsi+8]
0x1800406a7  mov     r15, [rsi]
0x1800406aa  jmp     loc_18004072F
0x1800406af  mov     rcx, [rsi+10h]
0x1800406b3  mov     rax, rcx
0x1800406b6  sub     rax, r15
0x1800406b9  sar     rax, 3
0x1800406bd  cmp     rdi, rax
0x1800406c0  jbe     short loc_18004070A
0x1800406c2  sub     rcx, r15
0x1800406c5  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800406cf  sar     rcx, 3
0x1800406d3  shr     rcx, 2
0x1800406d7  imul    rdx, rcx, 7
0x1800406db  add     rdx, 8
0x1800406df  cmp     rdx, rdi
0x1800406e2  cmovb   rdx, rdi
0x1800406e6  cmp     rdx, rax
0x1800406e9  cmova   rdx, rax
0x1800406ed  cmp     rdi, rdx
0x1800406f0  ja      loc_18004078E
0x1800406f6  mov     rcx, rsi
0x1800406f9  call    ?_SetCapacity@?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::_SetCapacity(unsigned __int64)
0x1800406fe  test    al, al
0x180040700  jz      loc_18004078E
0x180040706  mov     rbx, [rsi+8]
0x18004070a  xor     eax, eax
0x18004070c  mov     rcx, rdi
0x18004070f  sub     rcx, rbp
0x180040712  jz      short loc_180040724
0x180040714  mov     qword ptr [rbx+rax*8], 0
0x18004071c  inc     rax
0x18004071f  cmp     rax, rcx
0x180040722  jnz     short loc_180040714
0x180040724  mov     r15, [rsi]
0x180040727  lea     r14, [r15+rdi*8]
0x18004072b  mov     [rsi+8], r14
0x18004072f  mov     rbx, [r13+960h]
0x180040736  sub     r14, r15
0x180040739  mov     rdi, [r13+968h]
0x180040740  sar     r14, 3
0x180040744  cmp     rbx, rdi
0x180040747  jz      loc_18004083F
0x18004074d  mov     r8d, [rbx]; dwThreadId
0x180040750  xor     edx, edx; bInheritHandle
0x180040752  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180040757  dec     r14
0x18004075a  call    cs:__imp_OpenThread
0x180040760  mov     rcx, [r15+r14*8]; hObject
0x180040764  mov     [r15+r14*8], rax
0x180040768  lea     rax, [rcx+1]
0x18004076c  cmp     rax, 1
0x180040770  jbe     short loc_180040778
0x180040772  call    cs:__imp_CloseHandle
0x180040778  mov     r15, [rsi]
0x18004077b  mov     rax, [r15+r14*8]
0x18004077f  inc     rax
0x180040782  cmp     rax, 1
0x180040786  jbe     short loc_1800407C3
0x180040788  add     rbx, 4
0x18004078c  jmp     short loc_180040744
0x18004078e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040795  lea     rax, WPP_GLOBAL_Control
0x18004079c  cmp     rcx, rax
0x18004079f  jz      short loc_1800407BC
0x1800407a1  test    byte ptr [rcx+1Ch], 1
0x1800407a5  jz      short loc_1800407BC
0x1800407a7  mov     rcx, [rcx+10h]
0x1800407ab  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x1800407b2  mov     edx, 4Bh ; 'K'
0x1800407b7  call    WPP_SF_
0x1800407bc  mov     ebx, 8007000Eh
0x1800407c1  jmp     short loc_18004080D
0x1800407c3  call    cs:__imp_GetLastError
0x1800407c9  mov     ebx, eax
0x1800407cb  test    eax, eax
0x1800407cd  jle     short loc_1800407D8
0x1800407cf  movzx   ebx, ax
0x1800407d2  or      ebx, 80070000h
0x1800407d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407df  lea     rax, WPP_GLOBAL_Control
0x1800407e6  cmp     rcx, rax
0x1800407e9  jz      short loc_180040809
0x1800407eb  test    byte ptr [rcx+1Ch], 1
0x1800407ef  jz      short loc_180040809
0x1800407f1  mov     rcx, [rcx+10h]
0x1800407f5  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x1800407fc  mov     edx, 4Ch ; 'L'
0x180040801  mov     r9d, ebx
0x180040804  call    WPP_SF_d
0x180040809  test    ebx, ebx
0x18004080b  jns     short loc_180040841
0x18004080d  mov     r14, [rsi]
0x180040810  mov     rdi, [rsi+8]
0x180040814  sub     rdi, r14
0x180040817  mov     [rsi+8], r14
0x18004081b  sar     rdi, 3
0x18004081f  jmp     short loc_180040838
0x180040821  dec     rdi
0x180040824  mov     rcx, [r14+rdi*8]; hObject
0x180040828  lea     rax, [rcx+1]
0x18004082c  cmp     rax, 1
0x180040830  jbe     short loc_180040838
0x180040832  call    cs:__imp_CloseHandle
0x180040838  test    rdi, rdi
0x18004083b  jnz     short loc_180040821
0x18004083d  jmp     short loc_180040841
0x18004083f  xor     ebx, ebx
0x180040841  mov     eax, ebx
0x180040843  add     rsp, 20h
0x180040847  pop     r15
0x180040849  pop     r14
0x18004084b  pop     r13
0x18004084d  pop     rdi
0x18004084e  pop     rsi
0x18004084f  pop     rbp
0x180040850  pop     rbx
0x180040851  retn
```
