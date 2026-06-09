# MemoryCache::ParseCommands(void)

- ea: `0x180274878`
- end: `0x180274e84`
- name: `?ParseCommands@MemoryCache@@QEAAXXZ`
- size: `1548`
- prototype: `void __fastcall(MemoryCache *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801ed9c0`
- `0x1801f5c20`

## callees

- `0x1800727b8`
- `0x180072c8c`
- `0x18008dafc`
- `0x180240f9c`
- `0x1802746bc`
- `0x180274878`
- `0x180280968`
- `0x18028c3d0`
- `0x18028c404`
- `0x1804141fc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274906`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027493b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027496c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027499a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802749b8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802749d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a01`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a1f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a42`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a65`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a83`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274aa1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274acb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274afa`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274906`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027493b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027496c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18027499a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802749b8`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802749d7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a01`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a1f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a42`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a65`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274a83`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274aa1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274acb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180274afa`

## string_xrefs

- `0x180274bb3`: `Cached info for address %s for 4096 bytes was flushed\n`
- `0x180274c26`: `.cache [flushall | flushu | flush addr]\n`
- `0x180274c1a`: `.cache [{cachesize} | hold | unhold\n`
- `0x180274c50`: `.cache [forcedecodeptes | forcedecodeuser | noforcedecodeptes]\n`
- `0x180274c44`: `.cache [decodeptes | nodecodeptes]\n`
- `0x180274be8`: `*** Cache size %ld (%#lx KB) is too large - cache unchanged.\n`
- `0x180274c5c`: `.cache [decodeprotos | nodecodeprotos]\n`
- `0x180274cc4`: `Max cache size is       : %ld bytes (%#lx KB) %s\n`
- `0x180274cb4`: `(cache is off)`
- `0x180274cfc`: `Number of regions cached: %ld\n`
- `0x180274ce2`: `Total memory in cache   : %ld bytes (%#lx KB) \n`
- `0x180274d54`: `    counts: %d cached/%d uncached, %.2lf%% cached\n`
- `0x180274d0b`: `%d full reads broken into %d partial reads\n`
- `0x180274dc9`: `    bytes : %I64d cached/%I64d uncached, %.2lf%% cached\n`
- `0x180274e26`: `** %s addresses are translated to physical addresses before access\n`
- `0x180274e69`: `** Cache access is suspended, count %d\n`
- `0x180274e56`: `** Implicit cache flushing disabled **\n`

## pseudocode

```c
void __fastcall MemoryCache::ParseCommands(MemoryCache *this)
{
  wchar_t *v2; // rcx
  const wchar_t *v3; // rdi
  wchar_t v4; // ax
  wchar_t *v5; // rdx
  wchar_t v6; // si
  __int64 v7; // rax
  unsigned int v8; // edx
  bool v9; // r8
  bool v10; // dl
  int v11; // eax
  int v12; // eax
  int v13; // eax
  wchar_t v14; // ax
  unsigned __int64 Expression; // rdi
  struct MachineInfo *v16; // rcx
  unsigned __int16 *v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rax
  wchar_t *i; // rax
  __int64 v21; // rdx
  const wchar_t *v22; // r9
  int v23; // esi
  __int64 v24; // rdi
  double v25; // xmm6_8
  double v26; // xmm3_8
  __int64 v27; // rcx
  double v28; // xmm6_8
  __int64 v29; // rax
  double v30; // xmm6_8
  double v31; // xmm0_8
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // ecx
  const wchar_t *v35; // rdx
  __int64 v36; // rax

  GetNextChar((const unsigned __int16 **)&g_CurCmd);
  v2 = g_CurCmd;
  v3 = g_CurCmd;
  v4 = *g_CurCmd;
  if ( *g_CurCmd < 0x61u )
  {
    v6 = *g_CurCmd;
  }
  else
  {
    v5 = g_CurCmd;
    do
    {
      v6 = v4;
      if ( v4 > 0x7Au )
        break;
      v2 = v5 + 1;
      g_CurCmd = v2;
      ++v5;
      v4 = *v2;
      v6 = *v2;
    }
    while ( *v2 >= 0x61u );
  }
  *v2 = 0;
  v7 = *((_QWORD *)this + 11);
  if ( v7 && *(_DWORD *)(v7 + 4104) == 1 && *((_QWORD *)this + 12) )
  {
    if ( !_wcsicmp(v3, L"decodeptes") )
    {
      DbsSplayTreeCache::Flush(this);
      *(_DWORD *)(*((_QWORD *)this + 12) + 1496LL) = 1;
LABEL_65:
      *g_CurCmd = v6;
      goto LABEL_66;
    }
    if ( !_wcsicmp(v3, L"nodecodeptes") )
    {
      DbsSplayTreeCache::Flush(this);
      *(_DWORD *)(*((_QWORD *)this + 12) + 1496LL) = 0;
      goto LABEL_65;
    }
    if ( !_wcsicmp(v3, L"forcedecodeptes") )
    {
      v8 = 1;
LABEL_16:
      ProcessInfo::SetForceVaTrans(*((ProcessInfo **)this + 12), v8, 1);
      goto LABEL_65;
    }
    if ( !_wcsicmp(v3, L"noforcedecodeptes") )
    {
      v8 = 0;
      goto LABEL_16;
    }
    if ( !_wcsicmp(v3, L"forcedecodeuser") )
    {
      v8 = 2;
      goto LABEL_16;
    }
    if ( !_wcsicmp(v3, L"decodeprotos") )
    {
      v10 = 1;
LABEL_23:
      ProcessInfo::SetAllowProtoPteTrans(*((ProcessInfo **)this + 12), v10, v9);
      goto LABEL_65;
    }
    if ( !_wcsicmp(v3, L"nodecodeprotos") )
    {
      v10 = 0;
      goto LABEL_23;
    }
  }
  if ( !_wcsicmp(v3, L"hold") )
  {
    *((_BYTE *)this + 80) = 1;
    goto LABEL_65;
  }
  if ( !_wcsicmp(v3, L"unhold") )
  {
    *((_BYTE *)this + 80) = 0;
    goto LABEL_65;
  }
  if ( !_wcsicmp(v3, L"flushall") || !_wcsicmp(v3, L"flushu") )
  {
    DbsSplayTreeCache::Flush(this);
    goto LABEL_65;
  }
  if ( !_wcsicmp(v3, L"suspend") )
  {
    v11 = *((_DWORD *)this + 21);
    if ( v11 == -1 )
      goto LABEL_65;
    v12 = v11 + 1;
LABEL_38:
    *((_DWORD *)this + 21) = v12;
    goto LABEL_65;
  }
  if ( !_wcsicmp(v3, L"nosuspend") )
  {
    v13 = *((_DWORD *)this + 21);
    if ( !v13 )
      goto LABEL_65;
    v12 = v13 - 1;
    goto LABEL_38;
  }
  if ( !_wcsicmp(v3, L"dump") )
  {
    MemoryCache::Output(this, 0);
    *g_CurCmd = v6;
    return;
  }
  *g_CurCmd = v6;
  g_CurCmd = (wchar_t *)v3;
  v14 = *v3;
  if ( *v3 == 102 )
  {
    do
    {
      if ( v14 > 0x7Au )
        break;
      g_CurCmd = (wchar_t *)++v3;
      v14 = *v3;
    }
    while ( *v3 >= 0x61u );
    Expression = GetExpression(0);
    DbsSplayTreeCache::Remove(this, Expression, 0x1000u);
    if ( g_Target )
    {
      if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
        || (v16 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
      {
        v16 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
      }
    }
    else
    {
      v16 = 0;
    }
    v17 = FormatMachineAddr64(v16, Expression);
    dprintf(L"Cached info for address %s for 4096 bytes was flushed\n", v17);
    goto LABEL_66;
  }
  if ( !v14 )
  {
LABEL_66:
    dprintf(L"\n");
    v21 = *((unsigned int *)this + 16);
    v22 = &strIn;
    if ( !(_DWORD)v21 )
      v22 = L"(cache is off)";
    dprintf(L"Max cache size is       : %ld bytes (%#lx KB) %s\n", v21, (unsigned int)(v21 + 1023) >> 10, v22);
    dprintf(
      L"Total memory in cache   : %ld bytes (%#lx KB) \n",
      *((unsigned int *)this + 15),
      (unsigned int)(*((_DWORD *)this + 15) + 1023) >> 10);
    dprintf(L"Number of regions cached: %ld\n", *((unsigned int *)this + 19));
    v23 = *((_DWORD *)this + 8) + *((_DWORD *)this + 7);
    v24 = *((_QWORD *)this + 6) + *((_QWORD *)this + 5);
    dprintf(L"%d full reads broken into %d partial reads\n", *((unsigned int *)this + 6), (unsigned int)v23);
    v25 = 0.0;
    v26 = 0.0;
    if ( v23 )
      v26 = (double)*((int *)this + 7) * 100.0 / (double)v23;
    dprintf(
      L"    counts: %d cached/%d uncached, %.2lf%% cached\n",
      *((unsigned int *)this + 7),
      *((unsigned int *)this + 8),
      v26);
    if ( v24 )
    {
      v27 = *((_QWORD *)this + 5);
      if ( v27 < 0 )
      {
        v29 = *((_QWORD *)this + 5) & 1LL | (*((_QWORD *)this + 5) >> 1);
        v28 = (double)(int)v29 + (double)(int)v29;
      }
      else
      {
        v28 = (double)(int)v27;
      }
      v30 = v28 * 100.0;
      if ( v24 < 0 )
        v31 = (double)(int)(v24 & 1 | ((unsigned __int64)v24 >> 1))
            + (double)(int)(v24 & 1 | ((unsigned __int64)v24 >> 1));
      else
        v31 = (double)(int)v24;
      v25 = v30 / v31;
    }
    dprintf(
      L"    bytes : %I64d cached/%I64d uncached, %.2lf%% cached\n",
      *((_QWORD *)this + 5),
      *((_QWORD *)this + 6),
      v25);
    v32 = *((_QWORD *)this + 12);
    if ( v32 && *(_DWORD *)(v32 + 1496) )
      dprintf(L"** Transition PTEs are implicitly decoded\n");
    v33 = *((_QWORD *)this + 12);
    if ( v33 )
    {
      v34 = *(_DWORD *)(v33 + 1500);
      if ( v34 )
      {
        v35 = L"Virtual";
        if ( v34 != 1 )
          v35 = L"User virtual";
        dprintf(L"** %s addresses are translated to physical addresses before access\n", v35);
      }
    }
    v36 = *((_QWORD *)this + 12);
    if ( v36 && *(_BYTE *)(v36 + 1504) )
      dprintf(L"** Prototype PTEs are implicitly decoded\n");
    if ( *((_BYTE *)this + 80) )
      dprintf(L"** Implicit cache flushing disabled **\n");
    if ( *((_DWORD *)this + 21) )
      dprintf(L"** Cache access is suspended, count %d\n");
    return;
  }
  if ( (unsigned __int16)(v14 - 48) <= 9u )
  {
    v18 = (unsigned int)GetExpression(0) << 10;
    if ( (v18 & 0x80000000) == 0 )
    {
      *((_DWORD *)this + 26) = v18;
      *((_DWORD *)this + 16) = v18;
      if ( !v18 )
        DbsSplayTreeCache::Flush(this);
    }
    else
    {
      dprintf(L"*** Cache size %ld (%#lx KB) is too large - cache unchanged.\n", v18, v18 >> 10);
    }
    goto LABEL_66;
  }
  dprintf(L".cache [{cachesize} | hold | unhold\n");
  dprintf(L".cache [flushall | flushu | flush addr]\n");
  v19 = *((_QWORD *)this + 11);
  if ( v19 && *(_DWORD *)(v19 + 4104) == 1 )
  {
    dprintf(L".cache [decodeptes | nodecodeptes]\n");
    dprintf(L".cache [forcedecodeptes | forcedecodeuser | noforcedecodeptes]\n");
    dprintf(L".cache [decodeprotos | nodecodeprotos]\n");
  }
  for ( i = g_CurCmd; *i && *i != 59; g_CurCmd = i )
    ++i;
}

```

## disassembly

```asm
0x180274878  push    rbx
0x18027487a  push    rbp
0x18027487b  push    rsi
0x18027487c  push    rdi
0x18027487d  sub     rsp, 38h
0x180274881  mov     rbx, rcx
0x180274884  movaps  [rsp+58h+var_38], xmm6
0x180274889  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x180274890  call    ?GetNextChar@@YAGPEAPEBG@Z; GetNextChar(ushort const * *)
0x180274895  mov     rcx, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x18027489c  mov     rdi, rcx
0x18027489f  movzx   eax, word ptr [rcx]
0x1802748a2  cmp     ax, 61h ; 'a'
0x1802748a6  jb      short loc_1802748D0
0x1802748a8  mov     rdx, rcx
0x1802748ab  movzx   esi, ax
0x1802748ae  cmp     ax, 7Ah ; 'z'
0x1802748b2  ja      short loc_1802748D3
0x1802748b4  lea     rcx, [rdx+2]
0x1802748b8  mov     cs:?g_CurCmd@@3PEAGEA, rcx; ushort * g_CurCmd
0x1802748bf  mov     rdx, rcx
0x1802748c2  movzx   eax, word ptr [rcx]
0x1802748c5  movzx   esi, ax
0x1802748c8  cmp     ax, 61h ; 'a'
0x1802748cc  jnb     short loc_1802748AB
0x1802748ce  jmp     short loc_1802748D3
0x1802748d0  movzx   esi, ax
0x1802748d3  xor     ebp, ebp
0x1802748d5  mov     [rcx], bp
0x1802748d8  mov     rax, [rbx+58h]
0x1802748dc  test    rax, rax
0x1802748df  jz      loc_180274A15
0x1802748e5  cmp     dword ptr [rax+1008h], 1
0x1802748ec  jnz     loc_180274A15
0x1802748f2  cmp     [rbx+60h], rbp
0x1802748f6  jz      loc_180274A15
0x1802748fc  lea     rdx, aDecodeptes; "decodeptes"
0x180274903  mov     rcx, rdi; String1
0x180274906  call    cs:__imp__wcsicmp
0x18027490d  nop     dword ptr [rax+rax+00h]
0x180274912  test    eax, eax
0x180274914  jnz     short loc_180274931
0x180274916  mov     rcx, rbx; this
0x180274919  call    ?Flush@DbsSplayTreeCache@@QEAAXXZ; DbsSplayTreeCache::Flush(void)
0x18027491e  mov     rax, [rbx+60h]
0x180274922  mov     dword ptr [rax+5D8h], 1
0x18027492c  jmp     loc_180274C9B
0x180274931  lea     rdx, aNodecodeptes; "nodecodeptes"
0x180274938  mov     rcx, rdi; String1
0x18027493b  call    cs:__imp__wcsicmp
0x180274942  nop     dword ptr [rax+rax+00h]
0x180274947  test    eax, eax
0x180274949  jnz     short loc_180274962
0x18027494b  mov     rcx, rbx; this
0x18027494e  call    ?Flush@DbsSplayTreeCache@@QEAAXXZ; DbsSplayTreeCache::Flush(void)
0x180274953  mov     rax, [rbx+60h]
0x180274957  mov     [rax+5D8h], ebp
0x18027495d  jmp     loc_180274C9B
0x180274962  lea     rdx, aForcedecodepte; "forcedecodeptes"
0x180274969  mov     rcx, rdi; String1
0x18027496c  call    cs:__imp__wcsicmp
0x180274973  nop     dword ptr [rax+rax+00h]
0x180274978  test    eax, eax
0x18027497a  jnz     short loc_180274990
0x18027497c  lea     edx, [rax+1]; unsigned int
0x18027497f  mov     rcx, [rbx+60h]; this
0x180274983  mov     r8b, 1; bool
0x180274986  call    ?SetForceVaTrans@ProcessInfo@@QEAAXK_N@Z; ProcessInfo::SetForceVaTrans(ulong,bool)
0x18027498b  jmp     loc_180274C9B
0x180274990  lea     rdx, aNoforcedecodep; "noforcedecodeptes"
0x180274997  mov     rcx, rdi; String1
0x18027499a  call    cs:__imp__wcsicmp
0x1802749a1  nop     dword ptr [rax+rax+00h]
0x1802749a6  test    eax, eax
0x1802749a8  jnz     short loc_1802749AE
0x1802749aa  xor     edx, edx
0x1802749ac  jmp     short loc_18027497F
0x1802749ae  lea     rdx, aForcedecodeuse; "forcedecodeuser"
0x1802749b5  mov     rcx, rdi; String1
0x1802749b8  call    cs:__imp__wcsicmp
0x1802749bf  nop     dword ptr [rax+rax+00h]
0x1802749c4  test    eax, eax
0x1802749c6  jnz     short loc_1802749CD
0x1802749c8  lea     edx, [rax+2]
0x1802749cb  jmp     short loc_18027497F
0x1802749cd  lea     rdx, aDecodeprotos; "decodeprotos"
0x1802749d4  mov     rcx, rdi; String1
0x1802749d7  call    cs:__imp__wcsicmp
0x1802749de  nop     dword ptr [rax+rax+00h]
0x1802749e3  test    eax, eax
0x1802749e5  jnz     short loc_1802749F7
0x1802749e7  mov     dl, 1; bool
0x1802749e9  mov     rcx, [rbx+60h]; this
0x1802749ed  call    ?SetAllowProtoPteTrans@ProcessInfo@@QEAAX_N0@Z; ProcessInfo::SetAllowProtoPteTrans(bool,bool)
0x1802749f2  jmp     loc_180274C9B
0x1802749f7  lea     rdx, aNodecodeprotos; "nodecodeprotos"
0x1802749fe  mov     rcx, rdi; String1
0x180274a01  call    cs:__imp__wcsicmp
0x180274a08  nop     dword ptr [rax+rax+00h]
0x180274a0d  test    eax, eax
0x180274a0f  jnz     short loc_180274A15
0x180274a11  xor     edx, edx
0x180274a13  jmp     short loc_1802749E9
0x180274a15  lea     rdx, aHold; "hold"
0x180274a1c  mov     rcx, rdi; String1
0x180274a1f  call    cs:__imp__wcsicmp
0x180274a26  nop     dword ptr [rax+rax+00h]
0x180274a2b  test    eax, eax
0x180274a2d  jnz     short loc_180274A38
0x180274a2f  mov     byte ptr [rbx+50h], 1
0x180274a33  jmp     loc_180274C9B
0x180274a38  lea     rdx, aUnhold; "unhold"
0x180274a3f  mov     rcx, rdi; String1
0x180274a42  call    cs:__imp__wcsicmp
0x180274a49  nop     dword ptr [rax+rax+00h]
0x180274a4e  test    eax, eax
0x180274a50  jnz     short loc_180274A5B
0x180274a52  mov     [rbx+50h], bpl
0x180274a56  jmp     loc_180274C9B
0x180274a5b  lea     rdx, aFlushall; "flushall"
0x180274a62  mov     rcx, rdi; String1
0x180274a65  call    cs:__imp__wcsicmp
0x180274a6c  nop     dword ptr [rax+rax+00h]
0x180274a71  test    eax, eax
0x180274a73  jz      loc_180274C93
0x180274a79  lea     rdx, aFlushu; "flushu"
0x180274a80  mov     rcx, rdi; String1
0x180274a83  call    cs:__imp__wcsicmp
0x180274a8a  nop     dword ptr [rax+rax+00h]
0x180274a8f  test    eax, eax
0x180274a91  jz      loc_180274C93
0x180274a97  lea     rdx, aSuspend; "suspend"
0x180274a9e  mov     rcx, rdi; String1
0x180274aa1  call    cs:__imp__wcsicmp
0x180274aa8  nop     dword ptr [rax+rax+00h]
0x180274aad  test    eax, eax
0x180274aaf  jnz     short loc_180274AC1
0x180274ab1  mov     eax, [rbx+54h]
0x180274ab4  cmp     eax, 0FFFFFFFFh
0x180274ab7  jnb     loc_180274C9B
0x180274abd  inc     eax
0x180274abf  jmp     short loc_180274AE8
0x180274ac1  lea     rdx, aNosuspend; "nosuspend"
0x180274ac8  mov     rcx, rdi; String1
0x180274acb  call    cs:__imp__wcsicmp
0x180274ad2  nop     dword ptr [rax+rax+00h]
0x180274ad7  test    eax, eax
0x180274ad9  jnz     short loc_180274AF0
0x180274adb  mov     eax, [rbx+54h]
0x180274ade  test    eax, eax
0x180274ae0  jz      loc_180274C9B
0x180274ae6  dec     eax
0x180274ae8  mov     [rbx+54h], eax
0x180274aeb  jmp     loc_180274C9B
0x180274af0  lea     rdx, aDump_0; "dump"
0x180274af7  mov     rcx, rdi; String1
0x180274afa  call    cs:__imp__wcsicmp
0x180274b01  nop     dword ptr [rax+rax+00h]
0x180274b06  test    eax, eax
0x180274b08  jnz     short loc_180274B23
0x180274b0a  xor     edx, edx; unsigned int
0x180274b0c  mov     rcx, rbx; this
0x180274b0f  call    ?Output@MemoryCache@@QEAAXK@Z; MemoryCache::Output(ulong)
0x180274b14  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x180274b1b  mov     [rax], si
0x180274b1e  jmp     loc_180274E75
0x180274b23  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x180274b2a  mov     [rax], si
0x180274b2d  mov     cs:?g_CurCmd@@3PEAGEA, rdi; ushort * g_CurCmd
0x180274b34  movzx   eax, word ptr [rdi]
0x180274b37  cmp     ax, 66h ; 'f'
0x180274b3b  jnz     loc_180274BC4
0x180274b41  cmp     ax, 7Ah ; 'z'
0x180274b45  ja      short loc_180274B5B
0x180274b47  add     rdi, 2
0x180274b4b  mov     cs:?g_CurCmd@@3PEAGEA, rdi; ushort * g_CurCmd
0x180274b52  movzx   eax, word ptr [rdi]
0x180274b55  cmp     ax, 61h ; 'a'
0x180274b59  jnb     short loc_180274B41
0x180274b5b  xor     ecx, ecx; unsigned __int16 *
0x180274b5d  call    ?GetExpression@@YA_KPEBG@Z; GetExpression(ushort const *)
0x180274b62  mov     r8d, 1000h; unsigned int
0x180274b68  mov     rdx, rax; unsigned __int64
0x180274b6b  mov     rcx, rbx; this
0x180274b6e  mov     rdi, rax
0x180274b71  call    ?Remove@DbsSplayTreeCache@@QEAAX_KK@Z; DbsSplayTreeCache::Remove(unsigned __int64,ulong)
0x180274b76  mov     rdx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x180274b7d  test    rdx, rdx
0x180274b80  jz      short loc_180274BA5
0x180274b82  mov     ecx, [rdx+1008h]
0x180274b88  sub     ecx, 2
0x180274b8b  cmp     ecx, 1
0x180274b8e  ja      short loc_180274B9C
0x180274b90  mov     rcx, [rdx+2A8h]
0x180274b97  test    rcx, rcx
0x180274b9a  jnz     short loc_180274BA8
0x180274b9c  mov     rcx, [rdx+298h]
0x180274ba3  jmp     short loc_180274BA8
0x180274ba5  mov     rcx, rbp; struct MachineInfo *
0x180274ba8  mov     rdx, rdi; unsigned __int64
0x180274bab  call    ?FormatMachineAddr64@@YAPEAGPEAVMachineInfo@@_K@Z; FormatMachineAddr64(MachineInfo *,unsigned __int64)
0x180274bb0  mov     rdx, rax
0x180274bb3  lea     rcx, aCachedInfoForA; "Cached info for address %s for 4096 byt"...
0x180274bba  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274bbf  jmp     loc_180274CA5
0x180274bc4  test    ax, ax
0x180274bc7  jz      loc_180274CA5
0x180274bcd  sub     ax, 30h ; '0'
0x180274bd1  cmp     ax, 9
0x180274bd5  ja      short loc_180274C1A
0x180274bd7  xor     ecx, ecx; unsigned __int16 *
0x180274bd9  call    ?GetExpression@@YA_KPEBG@Z; GetExpression(ushort const *)
0x180274bde  shl     eax, 0Ah
0x180274be1  test    eax, eax
0x180274be3  jns     short loc_180274BFF
0x180274be5  mov     r8d, eax
0x180274be8  lea     rcx, aCacheSizeLdLxK; "*** Cache size %ld (%#lx KB) is too lar"...
0x180274bef  shr     r8d, 0Ah
0x180274bf3  mov     edx, eax
0x180274bf5  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274bfa  jmp     loc_180274CA5
0x180274bff  mov     [rbx+68h], eax
0x180274c02  mov     [rbx+40h], eax
0x180274c05  test    eax, eax
0x180274c07  jnz     loc_180274CA5
0x180274c0d  mov     rcx, rbx; this
0x180274c10  call    ?Flush@DbsSplayTreeCache@@QEAAXXZ; DbsSplayTreeCache::Flush(void)
0x180274c15  jmp     loc_180274CA5
0x180274c1a  lea     rcx, aCacheCachesize; ".cache [{cachesize} | hold | unhold\n"
0x180274c21  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274c26  lea     rcx, aCacheFlushallF; ".cache [flushall | flushu | flush addr]"...
0x180274c2d  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274c32  mov     rax, [rbx+58h]
0x180274c36  test    rax, rax
0x180274c39  jz      short loc_180274C68
0x180274c3b  cmp     dword ptr [rax+1008h], 1
0x180274c42  jnz     short loc_180274C68
0x180274c44  lea     rcx, aCacheDecodepte; ".cache [decodeptes | nodecodeptes]\n"
0x180274c4b  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274c50  lea     rcx, aCacheForcedeco; ".cache [forcedecodeptes | forcedecodeus"...
0x180274c57  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274c5c  lea     rcx, aCacheDecodepro; ".cache [decodeprotos | nodecodeprotos]"...
0x180274c63  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274c68  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x180274c6f  jmp     short loc_180274C86
0x180274c71  cmp     cx, 3Bh ; ';'
0x180274c75  jz      loc_180274E75
0x180274c7b  add     rax, 2
0x180274c7f  mov     cs:?g_CurCmd@@3PEAGEA, rax; ushort * g_CurCmd
0x180274c86  movzx   ecx, word ptr [rax]
0x180274c89  test    cx, cx
0x180274c8c  jnz     short loc_180274C71
0x180274c8e  jmp     loc_180274E75
0x180274c93  mov     rcx, rbx; this
0x180274c96  call    ?Flush@DbsSplayTreeCache@@QEAAXXZ; DbsSplayTreeCache::Flush(void)
0x180274c9b  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x180274ca2  mov     [rax], si
0x180274ca5  lea     rcx, asc_1805BAA38; "\n"
0x180274cac  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274cb1  mov     edx, [rbx+40h]
0x180274cb4  lea     rax, aCacheIsOff; "(cache is off)"
0x180274cbb  test    edx, edx
0x180274cbd  lea     r9, strIn
0x180274cc4  lea     rcx, aMaxCacheSizeIs; "Max cache size is       : %ld bytes (%#"...
0x180274ccb  cmovz   r9, rax
0x180274ccf  lea     r8d, [rdx+3FFh]
0x180274cd6  shr     r8d, 0Ah
0x180274cda  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274cdf  mov     edx, [rbx+3Ch]
0x180274ce2  lea     rcx, aTotalMemoryInC; "Total memory in cache   : %ld bytes (%#"...
0x180274ce9  lea     r8d, [rdx+3FFh]
0x180274cf0  shr     r8d, 0Ah
0x180274cf4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274cf9  mov     edx, [rbx+4Ch]
0x180274cfc  lea     rcx, aNumberOfRegion; "Number of regions cached: %ld\n"
0x180274d03  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274d08  mov     esi, [rbx+1Ch]
0x180274d0b  lea     rcx, aDFullReadsBrok; "%d full reads broken into %d partial re"...
0x180274d12  add     esi, [rbx+20h]
0x180274d15  mov     rdi, [rbx+28h]
0x180274d19  mov     r8d, esi
0x180274d1c  mov     edx, [rbx+18h]
0x180274d1f  add     rdi, [rbx+30h]
0x180274d23  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x180274d28  xorps   xmm6, xmm6
0x180274d2b  xorps   xmm3, xmm3
0x180274d2e  test    esi, esi
0x180274d30  jz      short loc_180274D50
0x180274d32  mov     eax, [rbx+1Ch]
0x180274d35  xorps   xmm0, xmm0
0x180274d38  cvtsi2sd xmm3, rax
0x180274d3d  mov     eax, esi
0x180274d3f  cvtsi2sd xmm0, rax
0x180274d44  mulsd   xmm3, cs:__real@4059000000000000
0x180274d4c  divsd   xmm3, xmm0
0x180274d50  mov     r8d, [rbx+20h]
0x180274d54  lea     rcx, aCountsDCachedD; "    counts: %d cached/%d uncached, %.2l"...
0x180274d5b  mov     edx, [rbx+1Ch]
0x180274d5e  movq    r9, xmm3
0x180274d63  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
  ... truncated ...
```
