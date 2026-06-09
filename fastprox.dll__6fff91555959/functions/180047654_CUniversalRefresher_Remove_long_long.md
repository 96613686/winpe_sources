# CUniversalRefresher::Remove(long,long)

- ea: `0x180047654`
- end: `0x180047863`
- name: `?Remove@CUniversalRefresher@@IEAAJJJ@Z`
- size: `527`
- prototype: `int(CUniversalRefresher *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047870`

## callees

- `0x180037120`
- `0x180046cf0`
- `0x18004736c`
- `0x1800474d8`
- `0x180047654`
- `0x180089678`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047685`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800476c8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047724`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047739`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800477eb`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047685`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800476c8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047724`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180047739`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800477eb`
- `wbemcomn!GetMemLogObject` at `0x180047759`
- `wbemcomn!GetMemLogObject` at `0x1800477af`
- `wbemcomn!GetMemLogObject` at `0x180047811`
- `wbemcomn!GetMemLogObject` at `0x180047759`
- `wbemcomn!GetMemLogObject` at `0x1800477af`
- `wbemcomn!GetMemLogObject` at `0x180047811`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180047676`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800476b8`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800476f7`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180047711`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180047676`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800476b8`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800476f7`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180047711`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800477ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004781c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180047764`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800477ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004781c`

## pseudocode

```c
__int64 __fastcall CUniversalRefresher::Remove(CUniversalRefresher *this, int a2, int a3)
{
  CFlexArray *v4; // rbp
  int i; // edi
  CUniversalRefresher::CRemote *v8; // rax
  struct CUniversalRefresher *v9; // r9
  unsigned int v10; // ebx
  int j; // edi
  CUniversalRefresher::CDirect *v13; // rax
  struct CUniversalRefresher *v14; // r8
  int v15; // eax
  int k; // edi
  int m; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v19; // rcx
  __int64 v20; // rdx
  CMemoryLog *v21; // rax
  CUniversalRefresher::CNonHiPerf *v22; // rax
  struct CUniversalRefresher *v23; // r8
  int v24; // eax
  CMemoryLog *v25; // rax

  v4 = (CUniversalRefresher *)((char *)this + 224);
  for ( i = 0; i < CFlexArray::Size(v4); ++i )
  {
    v8 = (CUniversalRefresher::CRemote *)CFlexArray::GetAt(v4, i);
    v10 = CUniversalRefresher::CRemote::Remove(v8, a2, a3, v9);
    if ( !v10 )
      return 0;
    if ( (v10 & 0x80000000) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v10);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 92;
LABEL_22:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, v10);
      }
      return v10;
    }
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= CFlexArray::Size((CUniversalRefresher *)((char *)this + 32)) )
    {
      for ( k = 0; ; ++k )
      {
        if ( k >= CFlexArray::Size((CUniversalRefresher *)((char *)this + 128)) )
        {
          for ( m = 0; m < CFlexArray::Size((CUniversalRefresher *)((char *)this + 320)); ++m )
          {
            if ( *((_DWORD *)CFlexArray::GetAt((CUniversalRefresher *)((char *)this + 320), m) + 2) == a2 )
            {
              CFlexArray::GetAt((CUniversalRefresher *)((char *)this + 320), m);
              CPointerArray<CUniversalRefresher::CNestedRefresher,CUniqueManager<CUniversalRefresher::CNestedRefresher>,CFlexArray>::RemoveAt(
                (char *)this + 320,
                (unsigned int)m);
              return 0;
            }
          }
          return 1;
        }
        v22 = (CUniversalRefresher::CNonHiPerf *)CFlexArray::GetAt((CUniversalRefresher *)((char *)this + 128), k);
        v24 = CUniversalRefresher::CNonHiPerf::Remove(v22, a2, v23);
        v10 = v24;
        if ( !v24 )
          return 0;
        if ( v24 < 0 )
          break;
      }
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v10);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 94;
        goto LABEL_22;
      }
      return v10;
    }
    v13 = (CUniversalRefresher::CDirect *)CFlexArray::GetAt((CUniversalRefresher *)((char *)this + 32), j);
    v15 = CUniversalRefresher::CDirect::Remove(v13, a2, v14);
    v10 = v15;
    if ( !v15 )
      return 0;
    if ( v15 < 0 )
      break;
  }
  v21 = GetMemLogObject();
  CMemoryLog::Write(v21, v10);
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 93;
    goto LABEL_22;
  }
  return v10;
}

```

## disassembly

```asm
0x180047654  push    rbx
0x180047656  push    rbp
0x180047657  push    rsi
0x180047658  push    rdi
0x180047659  push    r14
0x18004765b  push    r15
0x18004765d  sub     rsp, 28h
0x180047661  mov     r15d, r8d
0x180047664  lea     rbp, [rcx+0E0h]
0x18004766b  mov     r14d, edx
0x18004766e  mov     rsi, rcx
0x180047671  xor     edi, edi
0x180047673  mov     rcx, rbp
0x180047676  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004767c  cmp     edi, eax
0x18004767e  jge     short loc_1800476B2
0x180047680  mov     edx, edi
0x180047682  mov     rcx, rbp
0x180047685  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004768b  mov     r8d, r15d; int
0x18004768e  mov     edx, r14d; int
0x180047691  mov     rcx, rax; this
0x180047694  call    ?Remove@CRemote@CUniversalRefresher@@QEAAJJJPEAV2@@Z; CUniversalRefresher::CRemote::Remove(long,long,CUniversalRefresher *)
0x180047699  mov     ebx, eax
0x18004769b  test    eax, eax
0x18004769d  jnz     loc_18004774E
0x1800476a3  xor     eax, eax
0x1800476a5  add     rsp, 28h
0x1800476a9  pop     r15
0x1800476ab  pop     r14
0x1800476ad  pop     rdi
0x1800476ae  pop     rsi
0x1800476af  pop     rbp
0x1800476b0  pop     rbx
0x1800476b1  retn
0x1800476b2  xor     edi, edi
0x1800476b4  lea     rcx, [rsi+20h]
0x1800476b8  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800476be  cmp     edi, eax
0x1800476c0  jge     short loc_1800476EB
0x1800476c2  mov     edx, edi
0x1800476c4  lea     rcx, [rsi+20h]
0x1800476c8  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800476ce  mov     rcx, rax; this
0x1800476d1  mov     edx, r14d; int
0x1800476d4  call    ?Remove@CDirect@CUniversalRefresher@@QEAAJJPEAV2@@Z; CUniversalRefresher::CDirect::Remove(long,CUniversalRefresher *)
0x1800476d9  mov     ebx, eax
0x1800476db  test    eax, eax
0x1800476dd  jz      short loc_1800476A3
0x1800476df  test    eax, eax
0x1800476e1  js      loc_1800477AF
0x1800476e7  inc     edi
0x1800476e9  jmp     short loc_1800476B4
0x1800476eb  xor     edi, edi
0x1800476ed  lea     rbp, [rsi+80h]
0x1800476f4  mov     rcx, rbp
0x1800476f7  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800476fd  cmp     edi, eax
0x1800476ff  jl      loc_1800477E6
0x180047705  xor     ebx, ebx
0x180047707  lea     rdi, [rsi+140h]
0x18004770e  mov     rcx, rdi
0x180047711  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180047717  cmp     ebx, eax
0x180047719  jge     loc_180047859
0x18004771f  mov     edx, ebx
0x180047721  mov     rcx, rdi
0x180047724  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004772a  cmp     [rax+8], r14d
0x18004772e  jnz     loc_180047852
0x180047734  mov     edx, ebx
0x180047736  mov     rcx, rdi
0x180047739  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004773f  mov     edx, ebx
0x180047741  mov     rcx, rdi
0x180047744  call    ?RemoveAt@?$CPointerArray@VCNestedRefresher@CUniversalRefresher@@V?$CUniqueManager@VCNestedRefresher@CUniversalRefresher@@@@VCFlexArray@@@@QEAA_NHPEAPEAVCNestedRefresher@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CNestedRefresher,CUniqueManager<CUniversalRefresher::CNestedRefresher>,CFlexArray>::RemoveAt(int,CUniversalRefresher::CNestedRefresher * *)
0x180047749  jmp     loc_1800476A3
0x18004774e  test    ebx, ebx
0x180047750  js      short loc_180047759
0x180047752  inc     edi
0x180047754  jmp     loc_180047673
0x180047759  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004775f  mov     rcx, rax
0x180047762  mov     edx, ebx
0x180047764  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004776a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047771  lea     rax, WPP_GLOBAL_Control
0x180047778  cmp     rcx, rax
0x18004777b  jz      short loc_1800477A8
0x18004777d  test    byte ptr [rcx+1Ch], 1
0x180047781  jz      short loc_1800477A8
0x180047783  cmp     byte ptr [rcx+19h], 2
0x180047787  jb      short loc_1800477A8
0x180047789  mov     edx, 5Ch ; '\'
0x18004778e  jmp     short loc_180047795
0x180047790  mov     edx, 5Eh ; '^'
0x180047795  mov     rcx, [rcx+10h]
0x180047799  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800477a0  mov     r9d, ebx
0x1800477a3  call    WPP_SF_d
0x1800477a8  mov     eax, ebx
0x1800477aa  jmp     loc_1800476A5
0x1800477af  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800477b5  mov     rcx, rax
0x1800477b8  mov     edx, ebx
0x1800477ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800477c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800477c7  lea     rax, WPP_GLOBAL_Control
0x1800477ce  cmp     rcx, rax
0x1800477d1  jz      short loc_1800477A8
0x1800477d3  test    byte ptr [rcx+1Ch], 1
0x1800477d7  jz      short loc_1800477A8
0x1800477d9  cmp     byte ptr [rcx+19h], 2
0x1800477dd  jb      short loc_1800477A8
0x1800477df  mov     edx, 5Dh ; ']'
0x1800477e4  jmp     short loc_180047795
0x1800477e6  mov     edx, edi
0x1800477e8  mov     rcx, rbp
0x1800477eb  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800477f1  mov     rcx, rax; this
0x1800477f4  mov     edx, r14d; int
0x1800477f7  call    ?Remove@CNonHiPerf@CUniversalRefresher@@QEAAJJPEAV2@@Z; CUniversalRefresher::CNonHiPerf::Remove(long,CUniversalRefresher *)
0x1800477fc  mov     ebx, eax
0x1800477fe  test    eax, eax
0x180047800  jz      loc_1800476A3
0x180047806  test    eax, eax
0x180047808  js      short loc_180047811
0x18004780a  inc     edi
0x18004780c  jmp     loc_1800476F4
0x180047811  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180047817  mov     rcx, rax
0x18004781a  mov     edx, ebx
0x18004781c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180047822  mov     rcx, cs:WPP_GLOBAL_Control
0x180047829  lea     rax, WPP_GLOBAL_Control
0x180047830  cmp     rcx, rax
0x180047833  jz      loc_1800477A8
0x180047839  test    byte ptr [rcx+1Ch], 1
0x18004783d  jz      loc_1800477A8
0x180047843  cmp     byte ptr [rcx+19h], 2
0x180047847  jb      loc_1800477A8
0x18004784d  jmp     loc_180047790
0x180047852  inc     ebx
0x180047854  jmp     loc_18004770E
0x180047859  mov     eax, 1
0x18004785e  jmp     loc_1800476A5
```
