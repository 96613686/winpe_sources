# RegistryPath::Append(ushort const *)

- ea: `0x180006190`
- end: `0x18000644a`
- name: `?Append@RegistryPath@@QEAAKPEBG@Z`
- size: `698`
- prototype: `__int64 __fastcall(const wchar_t **this, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000554c`
- `0x180005994`
- `0x180005bbc`
- `0x180009f10`
- `0x180095dfc`
- `0x180096490`
- `0x180096ad4`
- `0x180096d08`

## callees

- `0x1800051d4`
- `0x180006190`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x180012cf0`
- `0x18003334c`
- `0x180044c94`
- `0x180044cf4`
- `0x180096670`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800061c9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000622a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800061c9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000622a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063c0`

## string_xrefs

- `0x1800061de`: `RegistryPath::Append`
- `0x180006334`: `RegistryPath::Append`
- `0x18000635d`: `RegistryPath::Append`
- `0x18000639c`: `RegistryPath::Append`
- `0x180006407`: `RegistryPath::Append`
- `0x1800061d7`: `%s: subPath is longer than %d characters`
- `0x18000634c`: `%s: Registry path is longer than %d characters`
- `0x18000633b`: `%s: subPath is empty. Nothing to do.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegistryPath::Append(const wchar_t **this, const unsigned __int16 *a2)
{
  size_t v2; // rsi
  const wchar_t *v3; // r12
  unsigned int v5; // ebp
  size_t v7; // rbx
  unsigned __int64 v8; // r15
  wchar_t *v9; // r14
  char v10; // r15
  int v11; // eax
  unsigned int v12; // esi
  const wchar_t *v13; // rcx
  unsigned __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // r13d
  wchar_t *v17; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *v19; // rax

  v2 = 0;
  v3 = a2;
  if ( a2 )
  {
    while ( a2[v2] == 92 )
    {
      if ( ++v2 >= 0x400 )
        goto LABEL_4;
    }
    v3 = &a2[v2];
    v2 = wcsnlen(v3, 0x400u);
LABEL_4:
    if ( v2 == 1024 )
    {
      Logger::TraceError(L"%s: subPath is longer than %d characters", L"RegistryPath::Append", 1023);
      return 87;
    }
  }
  v5 = 0;
  if ( !v2 )
  {
    Logger::TraceVerbose((wchar_t *)L"%s: subPath is empty. Nothing to do.", L"RegistryPath::Append");
    return v5;
  }
  v7 = 0;
  if ( *this && (v7 = wcsnlen(*this, 0x400u), v7 == 1024) || (v8 = v2 + v7 + 2, v8 > 0x400) )
  {
    Logger::TraceError(L"%s: Registry path is longer than %d characters", L"RegistryPath::Append", 1023);
    return 87;
  }
  if ( v8 > (unsigned __int64)this[1] )
  {
    v14 = v8 / 0x96 + 1;
    if ( 150 * v14 - v8 <= 1024 - v8 )
      v8 = 150 * v14;
    v9 = (wchar_t *)SafeAlloc(2 * v8);
    if ( !v9 )
    {
      v5 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Append");
      return v5;
    }
    v9[v7] = 0;
    if ( v7 )
    {
      v15 = o_wcsncpy_s_0(v9, v8, *this, v7);
      v16 = v15;
      if ( v15 )
      {
        v17 = wcserror(v15);
        Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v16, v17);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        return wcsncpy_s_error(v16);
      }
    }
    SafeFree((void *)*this);
    *this = v9;
    this[1] = (const wchar_t *)v8;
  }
  else
  {
    v9 = (wchar_t *)*this;
  }
  if ( v7 )
  {
    if ( v9[v7 - 1] == 92 && *v3 == 92 )
    {
      --v7;
      v10 = 0;
      v9[v7] = 0;
    }
    else
    {
      v10 = 0;
      if ( v9[v7 - 1] != 92 && *v3 != 92 )
      {
        v9[v7] = 92;
        v10 = 1;
        (*this)[++v7] = 0;
      }
    }
  }
  else
  {
    v10 = 0;
  }
  v11 = o_wcsncpy_s_0(&(*this)[v7], (char *)this[1] - v7, v3, v2 + 1);
  v12 = v11;
  if ( v11 )
  {
    v19 = wcserror(v11);
    Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v12, v19);
    v5 = wcsncpy_s_error(v12);
    if ( v10 )
      (*this)[--v7] = 0;
    if ( (unsigned __int64)this[3] > v7 )
      this[3] = (const wchar_t *)v7;
  }
  else
  {
    v13 = this[3];
    if ( (*this)[(_QWORD)v13] == 92 )
      this[3] = (const wchar_t *)((char *)v13 + 1);
    RegistryPath::CloseSubKey((RegistryPath *)this);
  }
  return v5;
}

```

## disassembly

```asm
0x180006190  push    rbx
0x180006192  push    rbp
0x180006193  push    rsi
0x180006194  push    rdi
0x180006195  push    r12
0x180006197  push    r13
0x180006199  push    r14
0x18000619b  push    r15
0x18000619d  sub     rsp, 28h
0x1800061a1  xor     esi, esi
0x1800061a3  mov     r12, rdx
0x1800061a6  mov     rdi, rcx
0x1800061a9  mov     r14d, 400h
0x1800061af  lea     r13d, [rsi+5Ch]
0x1800061b3  test    rdx, rdx
0x1800061b6  jz      short loc_180006212
0x1800061b8  cmp     [rdx+rsi*2], r13w
0x1800061bd  jz      short loc_180006208
0x1800061bf  lea     r12, [rdx+rsi*2]
0x1800061c3  mov     rdx, r14; MaxCount
0x1800061c6  mov     rcx, r12; Source
0x1800061c9  call    cs:__imp_wcsnlen
0x1800061cf  mov     rsi, rax
0x1800061d2  cmp     rsi, r14
0x1800061d5  jnz     short loc_180006212
0x1800061d7  lea     rcx, aSSubpathIsLong; "%s: subPath is longer than %d character"...
0x1800061de  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800061e5  mov     r8d, 3FFh
0x1800061eb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800061f0  mov     ebp, 57h ; 'W'
0x1800061f5  mov     eax, ebp
0x1800061f7  add     rsp, 28h
0x1800061fb  pop     r15
0x1800061fd  pop     r14
0x1800061ff  pop     r13
0x180006201  pop     r12
0x180006203  pop     rdi
0x180006204  pop     rsi
0x180006205  pop     rbp
0x180006206  pop     rbx
0x180006207  retn
0x180006208  inc     rsi
0x18000620b  cmp     rsi, r14
0x18000620e  jb      short loc_1800061B8
0x180006210  jmp     short loc_1800061D2
0x180006212  xor     ebp, ebp
0x180006214  test    rsi, rsi
0x180006217  jz      loc_180006334
0x18000621d  mov     rcx, [rdi]; Source
0x180006220  xor     ebx, ebx
0x180006222  test    rcx, rcx
0x180006225  jz      short loc_18000623C
0x180006227  mov     rdx, r14; MaxCount
0x18000622a  call    cs:__imp_wcsnlen
0x180006230  mov     rbx, rax
0x180006233  cmp     rax, r14
0x180006236  jz      loc_18000634C
0x18000623c  lea     r15, [rbx+2]
0x180006240  add     r15, rsi
0x180006243  cmp     r15, r14
0x180006246  ja      loc_18000634C
0x18000624c  cmp     r15, [rdi+8]
0x180006250  ja      loc_1800062DD
0x180006256  mov     r14, [rdi]
0x180006259  test    rbx, rbx
0x18000625c  jz      short loc_1800062CE
0x18000625e  cmp     [r14+rbx*2-2], r13w
0x180006264  setz    al
0x180006267  jz      loc_1800063E0
0x18000626d  xor     r15b, r15b
0x180006270  test    al, al
0x180006272  jnz     short loc_18000628F
0x180006274  cmp     [r12], r13w
0x180006279  jz      short loc_18000628F
0x18000627b  mov     [r14+rbx*2], r13w
0x180006280  mov     r15b, 1
0x180006283  mov     rcx, [rdi]
0x180006286  inc     rbx
0x180006289  xor     eax, eax
0x18000628b  mov     [rcx+rbx*2], ax
0x18000628f  mov     rax, [rdi]
0x180006292  lea     r9, [rsi+1]
0x180006296  mov     rdx, [rdi+8]
0x18000629a  mov     r8, r12
0x18000629d  sub     rdx, rbx
0x1800062a0  lea     rcx, [rax+rbx*2]
0x1800062a4  call    _o_wcsncpy_s_0
0x1800062a9  mov     esi, eax
0x1800062ab  test    eax, eax
0x1800062ad  jnz     loc_1800063FD
0x1800062b3  mov     rcx, [rdi+18h]
0x1800062b7  mov     rax, [rdi]
0x1800062ba  cmp     [rax+rcx*2], r13w
0x1800062bf  jz      short loc_1800062D3
0x1800062c1  mov     rcx, rdi; this
0x1800062c4  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x1800062c9  jmp     loc_1800061F5
0x1800062ce  xor     r15b, r15b
0x1800062d1  jmp     short loc_18000628F
0x1800062d3  lea     rax, [rcx+1]
0x1800062d7  mov     [rdi+18h], rax
0x1800062db  jmp     short loc_1800062C1
0x1800062dd  mov     rax, 6D3A06D3A06D3A07h
0x1800062e7  sub     r14, r15
0x1800062ea  mul     r15
0x1800062ed  shr     rdx, 6
0x1800062f1  inc     rdx
0x1800062f4  imul    rax, rdx, 96h
0x1800062fb  sub     rax, r15
0x1800062fe  cmp     rax, r14
0x180006301  jbe     short loc_180006358
0x180006303  lea     rcx, [r15+r15]; unsigned __int64
0x180006307  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18000630c  mov     r14, rax
0x18000630f  test    rax, rax
0x180006312  jz      short loc_18000635D
0x180006314  xor     eax, eax
0x180006316  mov     [r14+rbx*2], ax
0x18000631b  test    rbx, rbx
0x18000631e  jnz     short loc_18000637A
0x180006320  mov     rcx, [rdi]; lpMem
0x180006323  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180006328  mov     [rdi], r14
0x18000632b  mov     [rdi+8], r15
0x18000632f  jmp     loc_180006259
0x180006334  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000633b  lea     rcx, aSSubpathIsEmpt; "%s: subPath is empty. Nothing to do."
0x180006342  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006347  jmp     loc_1800061F5
0x18000634c  lea     rcx, aSRegistryPathI; "%s: Registry path is longer than %d cha"...
0x180006353  jmp     loc_1800061DE
0x180006358  add     r15, rax
0x18000635b  jmp     short loc_180006303
0x18000635d  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180006364  mov     ebp, 0Eh
0x180006369  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180006370  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180006375  jmp     loc_1800061F5
0x18000637a  mov     r8, [rdi]
0x18000637d  mov     r9, rbx
0x180006380  mov     rdx, r15
0x180006383  mov     rcx, r14
0x180006386  call    _o_wcsncpy_s_0
0x18000638b  mov     r13d, eax
0x18000638e  test    eax, eax
0x180006390  jz      short loc_1800063D5
0x180006392  mov     ecx, eax; ErrorNumber
0x180006394  call    _wcserror
0x180006399  mov     r9, rax
0x18000639c  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800063a3  mov     r8d, r13d
0x1800063a6  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x1800063ad  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800063b2  call    cs:__imp_GetProcessHeap
0x1800063b8  mov     r8, r14; lpMem
0x1800063bb  xor     edx, edx; dwFlags
0x1800063bd  mov     rcx, rax; hHeap
0x1800063c0  call    cs:__imp_HeapFree
0x1800063c6  mov     ecx, r13d; int
0x1800063c9  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x1800063ce  mov     ebp, eax
0x1800063d0  jmp     loc_1800061F5
0x1800063d5  mov     r13d, 5Ch ; '\'
0x1800063db  jmp     loc_180006320
0x1800063e0  cmp     [r12], r13w
0x1800063e5  jnz     loc_18000626D
0x1800063eb  dec     rbx
0x1800063ee  xor     r15b, r15b
0x1800063f1  xor     eax, eax
0x1800063f3  mov     [r14+rbx*2], ax
0x1800063f8  jmp     loc_18000628F
0x1800063fd  mov     ecx, esi; ErrorNumber
0x1800063ff  call    _wcserror
0x180006404  mov     r9, rax
0x180006407  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000640e  mov     r8d, esi
0x180006411  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x180006418  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000641d  mov     ecx, esi; int
0x18000641f  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x180006424  mov     ebp, eax
0x180006426  test    r15b, r15b
0x180006429  jz      short loc_180006437
0x18000642b  mov     rcx, [rdi]
0x18000642e  dec     rbx
0x180006431  xor     eax, eax
0x180006433  mov     [rcx+rbx*2], ax
0x180006437  cmp     [rdi+18h], rbx
0x18000643b  jbe     loc_1800061F5
0x180006441  mov     [rdi+18h], rbx
0x180006445  jmp     loc_1800061F5
```
