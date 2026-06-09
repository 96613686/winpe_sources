# CClfsBaseFile::ValidateOffsets(_CLFS_BASE_RECORD_HEADER * const)

- ea: `0x140060154`
- end: `0x140060533`
- name: `?ValidateOffsets@CClfsBaseFile@@IEAAJQEAU_CLFS_BASE_RECORD_HEADER@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(CClfsBaseFile *__hidden this, struct _CLFS_BASE_RECORD_HEADER *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005ed70`

## callees

- `0x140011f04`
- `0x140060154`
- `0x14006053c`
- `0x14006059c`
- `0x140060a70`
- `0x140060c54`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400601cf`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400601cf`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400602b7`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x1400602b7`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140060221`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400602cb`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400602df`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140060221`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400602cb`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400602df`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006043a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140060512`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006043a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140060512`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006023b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006023b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140060181`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140060181`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::ValidateOffsets(CClfsBaseFile *this, struct _CLFS_BASE_RECORD_HEADER *const a2)
{
  unsigned __int64 v4; // rbx
  struct _RTL_AVL_TABLE *TableContext; // rax
  struct _CLFS_VALIDATE_OFFSET_TABLE *v6; // rdi
  char v8; // r13
  __int64 v9; // r8
  char *v10; // rdx
  signed int v11; // ebx
  BOOLEAN k; // dl
  PVOID v13; // rax
  _BYTE *i; // r12
  _DWORD *v15; // rax
  _BYTE *v16; // r15
  unsigned int v17; // r11d
  __int64 v18; // rbx
  __int16 v19; // r14
  __int64 v20; // rdx
  unsigned int v21; // r8d
  unsigned int *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v27; // r9
  unsigned int v28; // eax
  __int64 v29; // rcx
  _WORD *v30; // rdx
  unsigned __int64 j; // rcx

  v4 = *(_QWORD *)(*((_QWORD *)this + 6) + 48LL);
  TableContext = (struct _RTL_AVL_TABLE *)ExAllocatePoolWithTag(PagedPool, 0x68u, 0x73666C43u);
  v6 = (struct _CLFS_VALIDATE_OFFSET_TABLE *)TableContext;
  if ( !TableContext )
    return 3221225626LL;
  v8 = 0;
  RtlInitializeGenericTableAvl(
    TableContext,
    CClfsBaseFile::CompareGenericoffsets,
    CClfsBaseFile::AllocOffsetNode,
    CClfsLogFcbPhysical::ReleaseLsnMap,
    TableContext);
  v9 = *(unsigned int *)(v4 + 104);
  if ( (unsigned int)v9 > *(unsigned __int16 *)(v4 + 4) << 9
    || (v10 = (char *)a2 + *((unsigned int *)a2 + 1226) + 4920, v10 < (char *)a2 + 4920)
    || v4 + v9 < v4
    || (unsigned __int64)v10 > v4 + v9 )
  {
LABEL_5:
    v11 = -1072037875;
  }
  else
  {
    v11 = CClfsBaseFile::ValidateContainerContextOffsets(this, v6, a2);
    if ( v11 >= 0 )
    {
      v11 = CClfsBaseFile::ValidateClientContextOffsets(this, (PRTL_AVL_TABLE)v6, a2);
      if ( v11 >= 0 )
      {
        v11 = CClfsBaseFile::ValidateContainerSymTblOffsets(this, v6, a2);
        if ( v11 >= 0 )
        {
          v11 = CClfsBaseFile::ValidateClientSymTblOffsets(this, v6, a2);
          if ( v11 >= 0 )
          {
            v8 = RtlNumberGenericTableElementsAvl((PRTL_AVL_TABLE)v6);
            for ( i = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)v6, 1u); ; i = v16 )
            {
              v15 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)v6, 0);
              v16 = v15;
              if ( !i )
              {
LABEL_55:
                if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
                {
                  WPP_SF_sdLD(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    28,
                    v9,
                    (unsigned int)"CClfsBaseFile::ValidateOffsets",
                    64,
                    v8,
                    v11);
                }
                goto LABEL_9;
              }
              v17 = v15 ? *v15 : *((_DWORD *)a2 + 1226) + 4920;
              v18 = *((_QWORD *)this + 6);
              v19 = *((_WORD *)this + 20);
              v20 = *(_QWORD *)(v18 + 48);
              if ( !v19 )
                break;
              if ( !v20 )
                goto LABEL_5;
              v21 = *(_DWORD *)(v18 + 56);
              v22 = (unsigned int *)(v20 + 40);
              v23 = *(unsigned int *)(v20 + 40);
              if ( (unsigned int)v23 >= v21 || (unsigned int)v23 < 0x70 || v21 - (unsigned int)v23 < 0x1338 )
                goto LABEL_28;
              v24 = v20 + v23;
LABEL_29:
              v25 = *(unsigned int *)i;
              v9 = *v22;
              if ( (int)v9 + (int)v25 < (unsigned int)v25 )
                goto LABEL_5;
              if ( !v24 )
                goto LABEL_5;
              if ( (int)v9 + (int)v25 >= (unsigned int)(*(unsigned __int16 *)(v20 + 4) << 9) )
                goto LABEL_5;
              v26 = v24 + v25;
              if ( !v26 )
                goto LABEL_5;
              v27 = *(unsigned int *)(v26 + 32);
              if ( (unsigned int)v27 > v17 || !i[4] )
                goto LABEL_5;
              if ( v19
                && (v28 = *(_DWORD *)(v18 + 56), (unsigned int)v9 < v28)
                && (unsigned int)v9 >= 0x70
                && v28 - (unsigned int)v9 >= 0x1338 )
              {
                v29 = v20 + v9;
              }
              else
              {
                v29 = 0;
              }
              if ( (int)v9 + (int)v27 < (unsigned int)v27
                || !v29
                || (int)v9 + (int)v27 >= (unsigned int)(*(unsigned __int16 *)(v20 + 4) << 9)
                || (v30 = (_WORD *)(v29 + v27)) == 0 )
              {
                v11 = -1073741811;
                goto LABEL_6;
              }
              for ( j = (unsigned __int64)(v17 - (unsigned int)v27) >> 1; j; --j )
              {
                if ( !*v30 )
                  break;
                ++v30;
              }
              v11 = j == 0 ? 0xC000000D : 0;
              if ( !j )
                goto LABEL_6;
              if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)v6, i) )
                goto LABEL_5;
              if ( !v16 )
                goto LABEL_55;
            }
            if ( !v20 )
              goto LABEL_5;
            v22 = (unsigned int *)(v20 + 40);
LABEL_28:
            v24 = 0;
            goto LABEL_29;
          }
        }
      }
    }
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
  {
    WPP_SF_sdLD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      29,
      v9,
      (unsigned int)"CClfsBaseFile::ValidateOffsets",
      77,
      v8,
      v11);
  }
  for ( k = 1; ; k = 0 )
  {
    v13 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)v6, k);
    if ( !v13 )
      break;
    if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)v6, v13) )
    {
      v11 = -1072037875;
      break;
    }
  }
LABEL_9:
  ExFreePoolWithTag(v6, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140060154  push    rbx
0x140060156  push    rbp
0x140060157  push    rsi
0x140060158  push    rdi
0x140060159  push    r12
0x14006015b  push    r13
0x14006015d  push    r14
0x14006015f  push    r15
0x140060161  sub     rsp, 48h
0x140060165  mov     rax, [rcx+30h]
0x140060169  mov     rsi, rdx
0x14006016c  mov     edx, 68h ; 'h'; NumberOfBytes
0x140060171  mov     rbp, rcx
0x140060174  mov     r8d, 73666C43h; Tag
0x14006017a  mov     rbx, [rax+30h]
0x14006017e  lea     ecx, [rdx-67h]; PoolType
0x140060181  call    cs:__imp_ExAllocatePoolWithTag
0x140060188  nop     dword ptr [rax+rax+00h]
0x14006018d  xor     r14d, r14d
0x140060190  mov     rdi, rax
0x140060193  test    rax, rax
0x140060196  jnz     short loc_1400601AF
0x140060198  mov     eax, 0C000009Ah
0x14006019d  add     rsp, 48h
0x1400601a1  pop     r15
0x1400601a3  pop     r14
0x1400601a5  pop     r13
0x1400601a7  pop     r12
0x1400601a9  pop     rdi
0x1400601aa  pop     rsi
0x1400601ab  pop     rbp
0x1400601ac  pop     rbx
0x1400601ad  retn
0x1400601af  lea     r9, ?ReleaseLsnMap@CClfsLogFcbPhysical@@UEAAXPEAU_CLFS_LSN_MAP@@@Z; FreeRoutine
0x1400601b6  mov     [rsp+88h+TableContext], rdi; TableContext
0x1400601bb  lea     r8, ?AllocOffsetNode@CClfsBaseFile@@KAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1400601c2  mov     rcx, rdi; Table
0x1400601c5  lea     rdx, ?CompareGenericoffsets@CClfsBaseFile@@KA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1400601cc  mov     r13d, r14d
0x1400601cf  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400601d6  nop     dword ptr [rax+rax+00h]
0x1400601db  movzx   eax, word ptr [rbx+4]
0x1400601df  mov     r8d, [rbx+68h]
0x1400601e3  shl     eax, 9
0x1400601e6  cmp     r8d, eax
0x1400601e9  ja      short loc_140060200
0x1400601eb  mov     edx, [rsi+1328h]
0x1400601f1  lea     rcx, [rsi+1338h]
0x1400601f8  add     rdx, rcx
0x1400601fb  cmp     rdx, rcx
0x1400601fe  jnb     short loc_14006024E
0x140060200  mov     ebx, 0C01A000Dh
0x140060205  mov     rcx, cs:WPP_GLOBAL_Control
0x14006020c  lea     rax, WPP_GLOBAL_Control
0x140060213  cmp     rcx, rax
0x140060216  jnz     loc_1400604D4
0x14006021c  mov     dl, 1; Restart
0x14006021e  mov     rcx, rdi; Table
0x140060221  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140060228  nop     dword ptr [rax+rax+00h]
0x14006022d  test    rax, rax
0x140060230  jnz     loc_14006050C
0x140060236  xor     edx, edx; Tag
0x140060238  mov     rcx, rdi; P
0x14006023b  call    cs:__imp_ExFreePoolWithTag
0x140060242  nop     dword ptr [rax+rax+00h]
0x140060247  mov     eax, ebx
0x140060249  jmp     loc_14006019D
0x14006024e  lea     rcx, [rbx+r8]
0x140060252  cmp     rcx, rbx
0x140060255  jb      short loc_140060200
0x140060257  cmp     rdx, rcx
0x14006025a  ja      short loc_140060200
0x14006025c  mov     r8, rsi; struct _CLFS_BASE_RECORD_HEADER *
0x14006025f  mov     rdx, rdi; struct _CLFS_VALIDATE_OFFSET_TABLE *
0x140060262  mov     rcx, rbp; this
0x140060265  call    ?ValidateContainerContextOffsets@CClfsBaseFile@@IEAAJPEAU_CLFS_VALIDATE_OFFSET_TABLE@@QEAU_CLFS_BASE_RECORD_HEADER@@@Z; CClfsBaseFile::ValidateContainerContextOffsets(_CLFS_VALIDATE_OFFSET_TABLE *,_CLFS_BASE_RECORD_HEADER * const)
0x14006026a  mov     ebx, eax
0x14006026c  test    eax, eax
0x14006026e  js      short loc_140060205
0x140060270  mov     r8, rsi; struct _CLFS_BASE_RECORD_HEADER *
0x140060273  mov     rdx, rdi; Table
0x140060276  mov     rcx, rbp; this
0x140060279  call    ?ValidateClientContextOffsets@CClfsBaseFile@@IEAAJPEAU_CLFS_VALIDATE_OFFSET_TABLE@@QEAU_CLFS_BASE_RECORD_HEADER@@@Z; CClfsBaseFile::ValidateClientContextOffsets(_CLFS_VALIDATE_OFFSET_TABLE *,_CLFS_BASE_RECORD_HEADER * const)
0x14006027e  mov     ebx, eax
0x140060280  test    eax, eax
0x140060282  js      short loc_140060205
0x140060284  mov     r8, rsi; struct _CLFS_BASE_RECORD_HEADER *
0x140060287  mov     rdx, rdi; struct _CLFS_VALIDATE_OFFSET_TABLE *
0x14006028a  mov     rcx, rbp; this
0x14006028d  call    ?ValidateContainerSymTblOffsets@CClfsBaseFile@@IEAAJPEAU_CLFS_VALIDATE_OFFSET_TABLE@@QEAU_CLFS_BASE_RECORD_HEADER@@@Z; CClfsBaseFile::ValidateContainerSymTblOffsets(_CLFS_VALIDATE_OFFSET_TABLE *,_CLFS_BASE_RECORD_HEADER * const)
0x140060292  mov     ebx, eax
0x140060294  test    eax, eax
0x140060296  js      loc_140060205
0x14006029c  mov     r8, rsi; struct _CLFS_BASE_RECORD_HEADER *
0x14006029f  mov     rdx, rdi; struct _CLFS_VALIDATE_OFFSET_TABLE *
0x1400602a2  mov     rcx, rbp; this
0x1400602a5  call    ?ValidateClientSymTblOffsets@CClfsBaseFile@@IEAAJPEAU_CLFS_VALIDATE_OFFSET_TABLE@@QEAU_CLFS_BASE_RECORD_HEADER@@@Z; CClfsBaseFile::ValidateClientSymTblOffsets(_CLFS_VALIDATE_OFFSET_TABLE *,_CLFS_BASE_RECORD_HEADER * const)
0x1400602aa  mov     ebx, eax
0x1400602ac  test    eax, eax
0x1400602ae  js      loc_140060205
0x1400602b4  mov     rcx, rdi; Table
0x1400602b7  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1400602be  nop     dword ptr [rax+rax+00h]
0x1400602c3  mov     dl, 1; Restart
0x1400602c5  mov     rcx, rdi; Table
0x1400602c8  mov     r13d, eax
0x1400602cb  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400602d2  nop     dword ptr [rax+rax+00h]
0x1400602d7  mov     r12, rax
0x1400602da  xor     edx, edx; Restart
0x1400602dc  mov     rcx, rdi; Table
0x1400602df  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400602e6  nop     dword ptr [rax+rax+00h]
0x1400602eb  mov     r15, rax
0x1400602ee  test    r12, r12
0x1400602f1  jz      loc_140060485
0x1400602f7  test    rax, rax
0x1400602fa  jz      loc_1400603E5
0x140060300  mov     r11d, [rax]
0x140060303  mov     rbx, [rbp+30h]
0x140060307  xor     eax, eax
0x140060309  movzx   r14d, word ptr [rbp+28h]
0x14006030e  mov     rdx, [rbx+30h]
0x140060312  cmp     ax, r14w
0x140060316  jz      short loc_140060346
0x140060318  test    rdx, rdx
0x14006031b  jz      loc_140060200
0x140060321  mov     r8d, [rbx+38h]
0x140060325  lea     rax, [rdx+28h]
0x140060329  mov     ecx, [rax]
0x14006032b  cmp     ecx, r8d
0x14006032e  jnb     short loc_140060353
0x140060330  cmp     ecx, 70h ; 'p'
0x140060333  jb      short loc_140060353
0x140060335  sub     r8d, ecx
0x140060338  cmp     r8d, 1338h
0x14006033f  jb      short loc_140060353
0x140060341  add     rcx, rdx
0x140060344  jmp     short loc_140060355
0x140060346  test    rdx, rdx
0x140060349  jz      loc_140060200
0x14006034f  lea     rax, [rdx+28h]
0x140060353  xor     ecx, ecx
0x140060355  mov     r9d, [r12]
0x140060359  mov     r8d, [rax]
0x14006035c  lea     r10d, [r8+r9]
0x140060360  cmp     r10d, r9d
0x140060363  jb      loc_140060200
0x140060369  test    rcx, rcx
0x14006036c  jz      loc_140060200
0x140060372  movzx   eax, word ptr [rdx+4]
0x140060376  shl     eax, 9
0x140060379  cmp     r10d, eax
0x14006037c  jnb     loc_140060200
0x140060382  add     r9, rcx
0x140060385  jz      loc_140060200
0x14006038b  mov     r9d, [r9+20h]
0x14006038f  cmp     r9d, r11d
0x140060392  ja      loc_140060200
0x140060398  cmp     byte ptr [r12+4], 0
0x14006039e  jz      loc_140060200
0x1400603a4  xor     eax, eax
0x1400603a6  cmp     ax, r14w
0x1400603aa  jz      short loc_1400603C8
0x1400603ac  mov     eax, [rbx+38h]
0x1400603af  cmp     r8d, eax
0x1400603b2  jnb     short loc_1400603C8
0x1400603b4  cmp     r8d, 70h ; 'p'
0x1400603b8  jb      short loc_1400603C8
0x1400603ba  sub     eax, r8d
0x1400603bd  cmp     eax, 1338h
0x1400603c2  jnb     loc_14006045B
0x1400603c8  xor     r14d, r14d
0x1400603cb  mov     ecx, r14d
0x1400603ce  lea     r10d, [r8+r9]
0x1400603d2  cmp     r10d, r9d
0x1400603d5  jnb     loc_140060467
0x1400603db  mov     ebx, 0C000000Dh
0x1400603e0  jmp     loc_140060205
0x1400603e5  mov     r11d, [rsi+1328h]
0x1400603ec  add     r11d, 1338h
0x1400603f3  jmp     loc_140060303
0x1400603f8  mov     rdx, r9
0x1400603fb  add     rdx, rcx
0x1400603fe  jz      short loc_1400603DB
0x140060400  sub     r11d, r9d
0x140060403  mov     ecx, r11d
0x140060406  shr     rcx, 1
0x140060409  jz      short loc_14006041B
0x14006040b  cmp     [rdx], r14w
0x14006040f  jz      short loc_14006041B
0x140060411  add     rdx, 2
0x140060415  sub     rcx, 1
0x140060419  jnz     short loc_14006040B
0x14006041b  mov     rax, rcx
0x14006041e  neg     rax
0x140060421  sbb     ebx, ebx
0x140060423  not     ebx
0x140060425  and     ebx, 0C000000Dh
0x14006042b  test    rcx, rcx
0x14006042e  jz      loc_140060205
0x140060434  mov     rdx, r12; Buffer
0x140060437  mov     rcx, rdi; Table
0x14006043a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140060441  nop     dword ptr [rax+rax+00h]
0x140060446  test    al, al
0x140060448  jz      loc_140060200
0x14006044e  test    r15, r15
0x140060451  jz      short loc_140060485
0x140060453  mov     r12, r15
0x140060456  jmp     loc_1400602DA
0x14006045b  lea     rcx, [rdx+r8]
0x14006045f  xor     r14d, r14d
0x140060462  jmp     loc_1400603CE
0x140060467  test    rcx, rcx
0x14006046a  jz      loc_1400603DB
0x140060470  movzx   eax, word ptr [rdx+4]
0x140060474  shl     eax, 9
0x140060477  cmp     r10d, eax
0x14006047a  jnb     loc_1400603DB
0x140060480  jmp     loc_1400603F8
0x140060485  mov     rcx, cs:WPP_GLOBAL_Control
0x14006048c  lea     rax, WPP_GLOBAL_Control
0x140060493  cmp     rcx, rax
0x140060496  jz      loc_140060236
0x14006049c  test    dword ptr [rcx+2Ch], 4000000h
0x1400604a3  jz      loc_140060236
0x1400604a9  mov     rcx, [rcx+18h]
0x1400604ad  lea     r9, aCclfsbasefileV_2; "CClfsBaseFile::ValidateOffsets"
0x1400604b4  mov     [rsp+88h+var_58], ebx
0x1400604b8  mov     edx, 1Ch
0x1400604bd  mov     [rsp+88h+var_60], r13d
0x1400604c2  mov     dword ptr [rsp+88h+TableContext], 1640h
0x1400604ca  call    WPP_SF_sdLD
0x1400604cf  jmp     loc_140060236
0x1400604d4  test    dword ptr [rcx+2Ch], 8000000h
0x1400604db  jz      loc_14006021C
0x1400604e1  mov     rcx, [rcx+18h]
0x1400604e5  lea     r9, aCclfsbasefileV_2; "CClfsBaseFile::ValidateOffsets"
0x1400604ec  mov     [rsp+88h+var_58], ebx
0x1400604f0  mov     edx, 1Dh
0x1400604f5  mov     [rsp+88h+var_60], r13d
0x1400604fa  mov     dword ptr [rsp+88h+TableContext], 164Dh
0x140060502  call    WPP_SF_sdLD
0x140060507  jmp     loc_14006021C
0x14006050c  mov     rdx, rax; Buffer
0x14006050f  mov     rcx, rdi; Table
0x140060512  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140060519  nop     dword ptr [rax+rax+00h]
0x14006051e  test    al, al
0x140060520  jz      short loc_140060529
0x140060522  xor     edx, edx
0x140060524  jmp     loc_14006021E
0x140060529  mov     ebx, 0C01A000Dh
0x14006052e  jmp     loc_140060236
```
