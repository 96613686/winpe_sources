# CLogScript::OpenLogFile(ushort *,IOMode,ushort *,long,ushort *)

- ea: `0x180008720`
- end: `0x18000889f`
- name: `?OpenLogFile@CLogScript@@UEAAJPEAGW4IOMode@@0J0@Z`
- size: `383`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x180002114`
- `0x180008720`
- `0x18000eca0`
- `0x18000ed30`

## import_xrefs

- `msvcrt!fclose` at `0x180008765`
- `msvcrt!fclose` at `0x180008810`
- `msvcrt!fclose` at `0x180008765`
- `msvcrt!fclose` at `0x180008810`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800087c7`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180008876`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x1800087c7`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180008876`
- `KERNEL32!EnterCriticalSection` at `0x18000874b`
- `KERNEL32!EnterCriticalSection` at `0x18000874b`
- `KERNEL32!LeaveCriticalSection` at `0x180008880`
- `KERNEL32!LeaveCriticalSection` at `0x180008880`

## pseudocode

```c
__int64 __fastcall CLogScript::OpenLogFile(__int64 a1, const unsigned __int16 *a2, int a3)
{
  FILE *v6; // rcx
  const char *v7; // rax
  __int64 v8; // rax
  int v9; // r8d
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  void *v14; // rax
  FILE *v15; // rcx
  const char *v16; // rbx
  __int64 v17; // rax
  int v18; // r8d
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  char v24[48]; // [rsp+20h] [rbp+0h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( a3 == 1 )
  {
    v6 = *(FILE **)(a1 + 48);
    if ( v6 )
    {
      fclose(v6);
      *(_QWORD *)(a1 + 48) = 0;
    }
    if ( a2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = 2 * v8 + 2;
      v10 = v9 + 15LL;
      if ( v10 <= v9 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
      v12 = alloca(v11);
      v13 = alloca(v11);
      v7 = AtlW2AHelper(v24, a2, v9);
    }
    else
    {
      v7 = 0;
    }
    STR::Copy((STR *)(a1 + 56), v7);
    if ( !*(_QWORD *)(a1 + 1144) )
    {
      *(_DWORD *)(a1 + 1152) = 10241;
      v14 = operator new(0x2801u);
      *(_QWORD *)(a1 + 1144) = v14;
      if ( !v14 )
        *(_DWORD *)(a1 + 1152) = 0;
    }
  }
  else
  {
    v15 = *(FILE **)(a1 + 1080);
    v16 = 0;
    if ( v15 )
    {
      fclose(v15);
      *(_QWORD *)(a1 + 1080) = 0;
    }
    if ( a2 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
      v18 = 2 * v17 + 2;
      v19 = v18 + 15LL;
      if ( v19 <= v18 )
        v19 = 0xFFFFFFFFFFFFFF0LL;
      v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
      v21 = alloca(v20);
      v22 = alloca(v20);
      v16 = AtlW2AHelper(v24, a2, v18);
    }
    STR::Copy((STR *)(a1 + 1088), v16);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return 0;
}

```

## disassembly

```asm
0x180008720  push    rbp
0x180008722  push    rbx
0x180008723  push    rsi
0x180008724  push    rdi
0x180008725  push    r14
0x180008727  sub     rsp, 30h
0x18000872b  lea     rbp, [rsp+20h]
0x180008730  mov     rax, cs:__security_cookie
0x180008737  xor     rax, rbp
0x18000873a  mov     qword ptr [rbp+30h+var_30], rax
0x18000873e  mov     rdi, rcx
0x180008741  mov     ebx, r8d
0x180008744  add     rcx, 8; lpCriticalSection
0x180008748  mov     rsi, rdx
0x18000874b  call    cs:__imp_EnterCriticalSection
0x180008751  cmp     ebx, 1
0x180008754  jnz     loc_180008802
0x18000875a  mov     rcx, [rdi+30h]; Stream
0x18000875e  xor     ebx, ebx
0x180008760  test    rcx, rcx
0x180008763  jz      short loc_18000876F
0x180008765  call    cs:__imp_fclose
0x18000876b  mov     [rdi+30h], rbx
0x18000876f  test    rsi, rsi
0x180008772  jnz     short loc_180008779
0x180008774  mov     rax, rbx
0x180008777  jmp     short loc_1800087C0
0x180008779  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000877d  inc     rax
0x180008780  cmp     [rsi+rax*2], bx
0x180008784  jnz     short loc_18000877D
0x180008786  lea     r8d, ds:2[rax*2]
0x18000878e  movsxd  rax, r8d
0x180008791  lea     rcx, [rax+0Fh]
0x180008795  cmp     rcx, rax
0x180008798  ja      short loc_1800087A4
0x18000879a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800087a4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800087a8  mov     rax, rcx
0x1800087ab  call    _alloca_probe
0x1800087b0  sub     rsp, rcx
0x1800087b3  mov     rdx, rsi; unsigned __int16 *
0x1800087b6  lea     rcx, [rsp+50h+var_30]; char *
0x1800087bb  call    ?AtlW2AHelper@@YAPEADPEADPEBGH@Z; AtlW2AHelper(char *,ushort const *,int)
0x1800087c0  lea     rcx, [rdi+38h]
0x1800087c4  mov     rdx, rax
0x1800087c7  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x1800087cd  cmp     [rdi+478h], rbx
0x1800087d4  jnz     loc_18000887C
0x1800087da  mov     ecx, 2801h; Size
0x1800087df  mov     [rdi+480h], ecx
0x1800087e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800087ea  mov     [rdi+478h], rax
0x1800087f1  test    rax, rax
0x1800087f4  jnz     loc_18000887C
0x1800087fa  mov     [rdi+480h], ebx
0x180008800  jmp     short loc_18000887C
0x180008802  mov     rcx, [rdi+438h]; Stream
0x180008809  xor     ebx, ebx
0x18000880b  test    rcx, rcx
0x18000880e  jz      short loc_18000881D
0x180008810  call    cs:__imp_fclose
0x180008816  mov     [rdi+438h], rbx
0x18000881d  test    rsi, rsi
0x180008820  jz      short loc_18000886C
0x180008822  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008826  inc     rax
0x180008829  cmp     [rsi+rax*2], bx
0x18000882d  jnz     short loc_180008826
0x18000882f  lea     r8d, ds:2[rax*2]
0x180008837  movsxd  rax, r8d
0x18000883a  lea     rcx, [rax+0Fh]
0x18000883e  cmp     rcx, rax
0x180008841  ja      short loc_18000884D
0x180008843  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000884d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008851  mov     rax, rcx
0x180008854  call    _alloca_probe
0x180008859  sub     rsp, rcx
0x18000885c  mov     rdx, rsi; unsigned __int16 *
0x18000885f  lea     rcx, [rsp+50h+var_30]; char *
0x180008864  call    ?AtlW2AHelper@@YAPEADPEADPEBGH@Z; AtlW2AHelper(char *,ushort const *,int)
0x180008869  mov     rbx, rax
0x18000886c  lea     rcx, [rdi+440h]
0x180008873  mov     rdx, rbx
0x180008876  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000887c  lea     rcx, [rdi+8]; lpCriticalSection
0x180008880  call    cs:__imp_LeaveCriticalSection
0x180008886  xor     eax, eax
0x180008888  mov     rcx, qword ptr [rbp+30h+var_30]
0x18000888c  xor     rcx, rbp; StackCookie
0x18000888f  call    __security_check_cookie
0x180008894  lea     rsp, [rbp+10h]
0x180008898  pop     r14
0x18000889a  pop     rdi
0x18000889b  pop     rsi
0x18000889c  pop     rbx
0x18000889d  pop     rbp
0x18000889e  retn
```
