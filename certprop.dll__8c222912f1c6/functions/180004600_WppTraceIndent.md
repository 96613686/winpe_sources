# WppTraceIndent

- ea: `0x180004600`
- end: `0x1800048f9`
- name: `WppTraceIndent`
- size: `761`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `84`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001570`
- `0x1800019d8`
- `0x180001c98`
- `0x180001e90`
- `0x180002690`
- `0x180002aa0`
- `0x180002df0`
- `0x180002ee0`
- `0x180003070`
- `0x180003230`
- `0x180003370`
- `0x180003510`
- `0x180004900`
- `0x180004fa0`
- `0x180005830`
- `0x180005e10`
- `0x180006010`
- `0x1800061c0`
- `0x1800062e0`
- `0x180006750`
- `0x180006a40`
- `0x1800093c0`
- `0x180009c00`
- `0x18000a050`
- `0x18000aa00`
- `0x18000b09c`
- `0x18000bfe0`
- `0x18000c8f0`
- `0x18000ce50`
- `0x18000d350`
- `0x18000d588`
- `0x18000d7c0`
- `0x18000dd30`
- `0x18000e4ac`
- `0x18000e7b8`
- `0x18000e888`
- `0x18000ec48`
- `0x18000f240`
- `0x18000fe80`
- `0x1800103f0`
- `0x180010d90`
- `0x180011190`
- `0x1800115c0`
- `0x180011c10`
- `0x180012690`
- `0x180012d90`
- `0x180014210`
- `0x1800144d0`
- `0x180014a30`
- `0x180014ca0`

## callees

- `0x180004600`
- `0x18000af90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000460c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000460c`

## pseudocode

```c
int __fastcall WppTraceIndent(__int64 a1, int a2)
{
  DWORD CurrentThreadId; // eax
  char *v4; // rcx
  int v5; // r10d
  size_t v6; // rdx
  int v7; // r11d
  char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  char *v11; // rcx
  const char *v12; // r9
  __int64 v13; // rax
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  const char *v17; // r8
  int v18; // r9d
  bool v19; // zf
  int v20; // r8d
  int v21; // edi
  int v22; // r11d

  CurrentThreadId = GetCurrentThreadId();
  v5 = `WppTraceIndent'::`2'::idxCurrentThread;
  v6 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v5 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180031404[0] = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
    {
      v4 = 0;
      v18 = -1;
      while ( 1 )
      {
        v19 = (_DWORD)v4 == 32;
        if ( (unsigned int)v4 >= 0x20 )
          break;
        v20 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)v4);
        if ( v20 == CurrentThreadId )
        {
          v5 = (int)v4;
          `WppTraceIndent'::`2'::idxCurrentThread = (int)v4;
          v19 = (_DWORD)v4 == 32;
          break;
        }
        if ( v18 == -1 && !v20 )
          v18 = (int)v4;
        v4 = (char *)(unsigned int)((_DWORD)v4 + 1);
      }
      if ( v19 )
      {
        if ( v18 == -1 )
        {
          v5 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_5;
        }
        v5 = v18;
        `WppTraceIndent'::`2'::idxCurrentThread = v18;
        *(&`WppTraceIndent'::`2'::ThreadTable + v18) = CurrentThreadId;
      }
    }
    if ( v5 < 0 )
    {
LABEL_5:
      v7 = 0;
      goto LABEL_6;
    }
  }
  if ( !a2 )
    ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v5 + 1);
  v7 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v5 + 1);
LABEL_6:
  LODWORD(v8) = (_DWORD)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (WPP_GLOBAL_Control[28] & 2) != 0 && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    v21 = 1;
    if ( v7 >= 1 )
    {
      do
      {
        LODWORD(v8) = StringCbCatA(v4, v6, "..");
        if ( (_DWORD)v8 )
          break;
        ++v21;
      }
      while ( v21 <= v22 );
    }
  }
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v9 = 256;
      v8 = &`WppTraceIndent'::`2'::szIndentPrefix;
      while ( *v8 )
      {
        ++v8;
        if ( !--v9 )
          goto LABEL_30;
      }
      v16 = 2147483646;
      v11 = (char *)HotPatchSpareGlobals - v9;
      v17 = "<";
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v11++ = *v17++;
        --v16;
        --v9;
      }
      while ( v9 );
    }
    else
    {
      if ( a2 != 2 )
        goto LABEL_30;
      v9 = 256;
      v8 = &`WppTraceIndent'::`2'::szIndentPrefix;
      while ( *v8 )
      {
        ++v8;
        if ( !--v9 )
          goto LABEL_30;
      }
      v10 = 2147483646;
      v11 = (char *)HotPatchSpareGlobals - v9;
      v12 = " ";
      do
      {
        if ( !v10 )
          break;
        if ( !*v12 )
          break;
        *v11++ = *v12++;
        --v10;
        --v9;
      }
      while ( v9 );
    }
  }
  else
  {
    v9 = 256;
    v8 = &`WppTraceIndent'::`2'::szIndentPrefix;
    while ( *v8 )
    {
      ++v8;
      if ( !--v9 )
        goto LABEL_30;
    }
    v13 = 2147483646;
    v11 = (char *)HotPatchSpareGlobals - v9;
    v14 = ">";
    do
    {
      if ( !v13 )
        break;
      if ( !*v14 )
        break;
      *v11++ = *v14++;
      --v13;
      --v9;
    }
    while ( v9 );
  }
  v8 = v11 - 1;
  if ( v9 )
    v8 = v11;
  *v8 = 0;
LABEL_30:
  if ( v5 >= 0 && a2 == 1 )
  {
    LODWORD(v8) = v5;
    WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
    v15 = 8LL * v5;
    v19 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v15 + 4))-- == 1;
    if ( v19 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v15) = 0;
  }
  else
  {
    WPP_pszIndent = (__int64)&`WppTraceIndent'::`2'::szIndentPrefix;
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180004600  mov     [rsp+arg_10], rbx
0x180004605  push    rsi
0x180004606  sub     rsp, 20h
0x18000460a  mov     ebx, edx
0x18000460c  call    cs:__imp_GetCurrentThreadId
0x180004612  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::idxCurrentThread
0x180004619  lea     rsi, ?ThreadTable@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::ThreadTable
0x180004620  mov     edx, eax; cbDest
0x180004622  cmp     r10d, 0FFFFFFFFh
0x180004626  jz      loc_1800046E1
0x18000462c  cmp     r10d, 0FFFFFFFEh
0x180004630  jz      loc_180004814
0x180004636  cmp     [rsi+r10*8], eax
0x18000463a  jnz     loc_180004814
0x180004640  test    r10d, r10d
0x180004643  jns     loc_1800046F8
0x180004649  xor     r11d, r11d
0x18000464c  mov     rax, cs:WPP_GLOBAL_Control
0x180004653  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@9@9, 0; `WppTraceIndent'::`2'::szIndentPrefix
0x18000465a  test    byte ptr [rax+1Ch], 2
0x18000465e  jnz     loc_1800048BF
0x180004664  lea     r11, ?szIndentPrefix@?1??WppTraceIndent@@9@9; `WppTraceIndent'::`2'::szIndentPrefix
0x18000466b  mov     ecx, ebx
0x18000466d  test    ebx, ebx
0x18000466f  jz      loc_180004711
0x180004675  sub     ecx, 1
0x180004678  jz      loc_1800047B1
0x18000467e  cmp     ecx, 1
0x180004681  jnz     loc_18000476B
0x180004687  mov     edx, 100h
0x18000468c  mov     rax, r11
0x18000468f  cmp     byte ptr [rax], 0
0x180004692  jnz     loc_1800048AD
0x180004698  lea     rcx, HotPatchSpareGlobals
0x18000469f  mov     eax, 7FFFFFFEh
0x1800046a4  sub     rcx, rdx
0x1800046a7  lea     r9, asc_180027F18; " "
0x1800046ae  test    rdx, rdx
0x1800046b1  jz      loc_18000475D
0x1800046b7  test    rax, rax
0x1800046ba  jz      loc_18000475D
0x1800046c0  movzx   r8d, byte ptr [r9]
0x1800046c4  test    r8b, r8b
0x1800046c7  jz      loc_18000475D
0x1800046cd  mov     [rcx], r8b
0x1800046d0  inc     r9
0x1800046d3  inc     rcx
0x1800046d6  dec     rax
0x1800046d9  sub     rdx, 1
0x1800046dd  jnz     short loc_1800046B7
0x1800046df  jmp     short loc_18000475D
0x1800046e1  xor     r10d, r10d
0x1800046e4  mov     cs:?ThreadTable@?1??WppTraceIndent@@9@9, edx; `WppTraceIndent'::`2'::ThreadTable
0x1800046ea  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x1800046f1  mov     cs:dword_180031404, r10d
0x1800046f8  movsxd  rax, r10d
0x1800046fb  test    ebx, ebx
0x1800046fd  jnz     loc_18000480A
0x180004703  inc     dword ptr [rsi+rax*8+4]
0x180004707  mov     r11d, [rsi+rax*8+4]
0x18000470c  jmp     loc_18000464C
0x180004711  mov     edx, 100h
0x180004716  mov     rax, r11
0x180004719  cmp     byte ptr [rax], 0
0x18000471c  jnz     loc_180004889
0x180004722  lea     rcx, HotPatchSpareGlobals
0x180004729  mov     eax, 7FFFFFFEh
0x18000472e  sub     rcx, rdx
0x180004731  lea     r9, asc_180027E34; ">"
0x180004738  test    rdx, rdx
0x18000473b  jz      short loc_18000475D
0x18000473d  test    rax, rax
0x180004740  jz      short loc_18000475D
0x180004742  movzx   r8d, byte ptr [r9]
0x180004746  test    r8b, r8b
0x180004749  jz      short loc_18000475D
0x18000474b  mov     [rcx], r8b
0x18000474e  inc     r9
0x180004751  inc     rcx
0x180004754  dec     rax
0x180004757  sub     rdx, 1
0x18000475b  jnz     short loc_18000473D
0x18000475d  test    rdx, rdx
0x180004760  lea     rax, [rcx-1]
0x180004764  cmovnz  rax, rcx
0x180004768  mov     byte ptr [rax], 0
0x18000476b  test    r10d, r10d
0x18000476e  jns     short loc_180004782
0x180004770  mov     cs:WPP_pszIndent, r11
0x180004777  mov     rbx, [rsp+28h+arg_10]
0x18000477c  add     rsp, 20h
0x180004780  pop     rsi
0x180004781  retn
0x180004782  cmp     ebx, 1
0x180004785  jnz     short loc_180004770
0x180004787  movsxd  rax, r10d
0x18000478a  mov     cs:WPP_pszIndent, r11
0x180004791  lea     rcx, ds:0[rax*8]
0x180004799  sub     [rcx+rsi+4], ebx
0x18000479d  jnz     short loc_180004777
0x18000479f  mov     rbx, [rsp+28h+arg_10]
0x1800047a4  mov     dword ptr [rcx+rsi], 0
0x1800047ab  add     rsp, 20h
0x1800047af  pop     rsi
0x1800047b0  retn
0x1800047b1  mov     edx, 100h
0x1800047b6  mov     rax, r11
0x1800047b9  cmp     byte ptr [rax], 0
0x1800047bc  jnz     loc_18000489B
0x1800047c2  lea     rcx, HotPatchSpareGlobals
0x1800047c9  mov     eax, 7FFFFFFEh
0x1800047ce  sub     rcx, rdx
0x1800047d1  lea     r8, asc_180027E38; "<"
0x1800047d8  test    rdx, rdx
0x1800047db  jz      short loc_18000475D
0x1800047dd  test    rax, rax
0x1800047e0  jz      loc_18000475D
0x1800047e6  movzx   r9d, byte ptr [r8]
0x1800047ea  test    r9b, r9b
0x1800047ed  jz      loc_18000475D
0x1800047f3  mov     [rcx], r9b
0x1800047f6  inc     r8
0x1800047f9  inc     rcx
0x1800047fc  dec     rax
0x1800047ff  sub     rdx, 1
0x180004803  jnz     short loc_1800047DD
0x180004805  jmp     loc_18000475D
0x18000480a  mov     r11d, [rsi+rax*8+4]
0x18000480f  jmp     loc_18000464C
0x180004814  xor     ecx, ecx
0x180004816  mov     r9d, 0FFFFFFFFh
0x18000481c  nop     dword ptr [rax+00h]
0x180004820  cmp     ecx, 20h ; ' '
0x180004823  jnb     short loc_18000484E
0x180004825  movsxd  rax, ecx
0x180004828  mov     r8d, [rsi+rax*8]
0x18000482c  cmp     r8d, edx
0x18000482f  jz      short loc_180004842
0x180004831  cmp     r9d, 0FFFFFFFFh
0x180004835  jnz     short loc_18000483E
0x180004837  test    r8d, r8d
0x18000483a  cmovz   r9d, ecx
0x18000483e  inc     ecx
0x180004840  jmp     short loc_180004820
0x180004842  mov     r10d, ecx
0x180004845  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, ecx; `WppTraceIndent'::`2'::idxCurrentThread
0x18000484b  cmp     ecx, 20h ; ' '
0x18000484e  jnz     loc_180004640
0x180004854  cmp     r9d, 0FFFFFFFFh
0x180004858  jnz     short loc_18000486C
0x18000485a  mov     r10d, 0FFFFFFFEh
0x180004860  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r10d; `WppTraceIndent'::`2'::idxCurrentThread
0x180004867  jmp     loc_180004649
0x18000486c  movsxd  rax, r9d
0x18000486f  mov     r10d, r9d
0x180004872  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@9@9, r9d; `WppTraceIndent'::`2'::idxCurrentThread
0x180004879  mov     [rsi+rax*8], edx
0x18000487c  mov     dword ptr [rsi+rax*8+4], 0
0x180004884  jmp     loc_180004640
0x180004889  inc     rax
0x18000488c  sub     rdx, 1
0x180004890  jnz     loc_180004719
0x180004896  jmp     loc_18000476B
0x18000489b  inc     rax
0x18000489e  sub     rdx, 1
0x1800048a2  jnz     loc_1800047B9
0x1800048a8  jmp     loc_18000476B
0x1800048ad  inc     rax
0x1800048b0  sub     rdx, 1
0x1800048b4  jnz     loc_18000468F
0x1800048ba  jmp     loc_18000476B
0x1800048bf  cmp     byte ptr [rax+19h], 5
0x1800048c3  jb      loc_180004664
0x1800048c9  mov     [rsp+28h+arg_8], rdi
0x1800048ce  mov     edi, 1
0x1800048d3  cmp     r11d, edi
0x1800048d6  jl      short loc_1800048EF
0x1800048d8  lea     r8, pszSrc; ".."
0x1800048df  call    StringCbCatA
0x1800048e4  test    eax, eax
0x1800048e6  jnz     short loc_1800048EF
0x1800048e8  inc     edi
0x1800048ea  cmp     edi, r11d
0x1800048ed  jle     short loc_1800048D8
0x1800048ef  mov     rdi, [rsp+28h+arg_8]
0x1800048f4  jmp     loc_180004664
```
