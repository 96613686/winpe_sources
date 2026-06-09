# RegistryPath::Append(ushort const *)

- ea: `0x18000db54`
- end: `0x18000ddd1`
- name: `?Append@RegistryPath@@QEAAKPEBG@Z`
- size: `637`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000d770`
- `0x18000e5d4`
- `0x180044c94`

## callees

- `0x1800073c0`
- `0x18000c160`
- `0x18000ced0`
- `0x18000db54`
- `0x18001a340`
- `0x180027448`
- `0x18002bc58`
- `0x18002e7e4`
- `0x18002e82c`
- `0x180046b50`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000db99`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000dbf6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000db99`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000dbf6`

## string_xrefs

- `0x18000dbae`: `RegistryPath::Append`
- `0x18000dbd1`: `RegistryPath::Append`
- `0x18000dc5d`: `RegistryPath::Append`
- `0x18000dca5`: `RegistryPath::Append`
- `0x18000dd5a`: `RegistryPath::Append`
- `0x18000dbd8`: `%s: subPath is empty. Nothing to do.`
- `0x18000dc04`: `%s: Registry path is longer than %d characters`
- `0x18000dba7`: `%s: subPath is longer than %d characters`

## pseudocode

```c
__int64 __fastcall RegistryPath::Append(const wchar_t **this, const unsigned __int16 *a2)
{
  wchar_t *v2; // rsi
  size_t v3; // r14
  const wchar_t *v4; // r13
  unsigned int v6; // ebp
  size_t v7; // rbx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // r12d
  wchar_t *v12; // rax
  char v13; // r15
  int v14; // eax
  unsigned int v15; // esi
  wchar_t *v16; // rax
  const wchar_t *v17; // rcx

  v2 = 0;
  v3 = 0;
  v4 = a2;
  if ( a2 )
  {
    while ( a2[v3] == 92 )
    {
      if ( ++v3 >= 0x400 )
        goto LABEL_6;
    }
    v4 = &a2[v3];
    v3 = wcsnlen(v4, 0x400u);
LABEL_6:
    if ( v3 == 1024 )
    {
      Logger::TraceError(L"%s: subPath is longer than %d characters", L"RegistryPath::Append", 1023);
LABEL_8:
      v6 = 87;
      goto LABEL_42;
    }
  }
  v6 = 0;
  if ( !v3 )
  {
    Logger::TraceVerbose(L"%s: subPath is empty. Nothing to do.", L"RegistryPath::Append");
    goto LABEL_42;
  }
  v7 = 0;
  if ( *this && (v7 = wcsnlen(*this, 0x400u), v7 == 1024) || (v8 = v3 + v7 + 2, v8 > 0x400) )
  {
    Logger::TraceError(L"%s: Registry path is longer than %d characters", L"RegistryPath::Append", 1023);
    goto LABEL_8;
  }
  if ( v8 <= (unsigned __int64)this[1] )
  {
    v2 = (wchar_t *)*this;
  }
  else
  {
    v9 = v8 / 0x96 + 1;
    if ( 150 * v9 - v8 <= 1024 - v8 )
      v8 = 150 * v9;
    v2 = (wchar_t *)MIDL_user_allocate(2 * v8);
    if ( !v2 )
    {
      v6 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Append");
      goto LABEL_42;
    }
    v2[v7] = 0;
    if ( v7 )
    {
      v10 = o_wcsncpy_s_0(v2, v8, *this, v7);
      v11 = v10;
      if ( v10 )
      {
        v12 = wcserror(v10);
        Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v11, v12);
        v6 = wcsncpy_s_error(v11);
        goto LABEL_42;
      }
    }
    SafeFree((void *)*this);
    *this = v2;
    this[1] = (const wchar_t *)v8;
  }
  if ( v7 )
  {
    if ( v2[v7 - 1] == 92 && *v4 == 92 )
    {
      --v7;
      v13 = 0;
      v2[v7] = 0;
    }
    else
    {
      v13 = 0;
      if ( v2[v7 - 1] != 92 && *v4 != 92 )
      {
        v2[v7] = 92;
        v13 = 1;
        (*this)[++v7] = 0;
      }
    }
  }
  else
  {
    v13 = 0;
  }
  v14 = o_wcsncpy_s_0(&(*this)[v7], (char *)this[1] - v7, v4, v3 + 1);
  v15 = v14;
  if ( v14 )
  {
    v16 = wcserror(v14);
    Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v15, v16);
    v6 = wcsncpy_s_error(v15);
    if ( v13 )
      (*this)[--v7] = 0;
    if ( (unsigned __int64)this[3] > v7 )
      this[3] = (const wchar_t *)v7;
  }
  else
  {
    v17 = this[3];
    if ( (*this)[(_QWORD)v17] == 92 )
      this[3] = (const wchar_t *)((char *)v17 + 1);
    RegistryPath::CloseSubKey((RegistryPath *)this);
  }
  v2 = 0;
LABEL_42:
  SafeFree(v2);
  return v6;
}

```

## disassembly

```asm
0x18000db54  push    rbx
0x18000db56  push    rbp
0x18000db57  push    rsi
0x18000db58  push    rdi
0x18000db59  push    r12
0x18000db5b  push    r13
0x18000db5d  push    r14
0x18000db5f  push    r15
0x18000db61  sub     rsp, 28h
0x18000db65  xor     esi, esi
0x18000db67  xor     r14d, r14d
0x18000db6a  mov     r13, rdx
0x18000db6d  mov     rdi, rcx
0x18000db70  mov     r12d, 400h
0x18000db76  lea     eax, [rsi+5Ch]
0x18000db79  test    rdx, rdx
0x18000db7c  jz      short loc_18000DBCA
0x18000db7e  cmp     [rdx+r14*2], ax
0x18000db83  jnz     short loc_18000DB8F
0x18000db85  inc     r14
0x18000db88  cmp     r14, r12
0x18000db8b  jb      short loc_18000DB7E
0x18000db8d  jmp     short loc_18000DBA2
0x18000db8f  lea     r13, [rdx+r14*2]
0x18000db93  mov     rdx, r12; MaxCount
0x18000db96  mov     rcx, r13; Source
0x18000db99  call    cs:__imp_wcsnlen
0x18000db9f  mov     r14, rax
0x18000dba2  cmp     r14, r12
0x18000dba5  jnz     short loc_18000DBCA
0x18000dba7  lea     rcx, aSSubpathIsLong; "%s: subPath is longer than %d character"...
0x18000dbae  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000dbb5  mov     r8d, 3FFh
0x18000dbbb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dbc0  mov     ebp, 57h ; 'W'
0x18000dbc5  jmp     loc_18000DDB6
0x18000dbca  xor     ebp, ebp
0x18000dbcc  test    r14, r14
0x18000dbcf  jnz     short loc_18000DBE9
0x18000dbd1  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000dbd8  lea     rcx, aSSubpathIsEmpt; "%s: subPath is empty. Nothing to do."
0x18000dbdf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000dbe4  jmp     loc_18000DDB6
0x18000dbe9  mov     rcx, [rdi]; Source
0x18000dbec  xor     ebx, ebx
0x18000dbee  test    rcx, rcx
0x18000dbf1  jz      short loc_18000DC0D
0x18000dbf3  mov     rdx, r12; MaxCount
0x18000dbf6  call    cs:__imp_wcsnlen
0x18000dbfc  mov     rbx, rax
0x18000dbff  cmp     rax, r12
0x18000dc02  jnz     short loc_18000DC0D
0x18000dc04  lea     rcx, aSRegistryPathI; "%s: Registry path is longer than %d cha"...
0x18000dc0b  jmp     short loc_18000DBAE
0x18000dc0d  lea     r15, [rbx+2]
0x18000dc11  add     r15, r14
0x18000dc14  cmp     r15, r12
0x18000dc17  ja      short loc_18000DC04
0x18000dc19  cmp     r15, [rdi+8]
0x18000dc1d  jbe     loc_18000DCDB
0x18000dc23  mov     rax, 6D3A06D3A06D3A07h
0x18000dc2d  sub     r12, r15
0x18000dc30  mul     r15
0x18000dc33  shr     rdx, 6
0x18000dc37  inc     rdx
0x18000dc3a  imul    rax, rdx, 96h
0x18000dc41  sub     rax, r15
0x18000dc44  cmp     rax, r12
0x18000dc47  ja      short loc_18000DC4C
0x18000dc49  add     r15, rax
0x18000dc4c  lea     rcx, [r15+r15]; size
0x18000dc50  call    MIDL_user_allocate
0x18000dc55  mov     rsi, rax
0x18000dc58  test    rax, rax
0x18000dc5b  jnz     short loc_18000DC78
0x18000dc5d  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000dc64  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000dc6b  lea     ebp, [rax+0Eh]
0x18000dc6e  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000dc73  jmp     loc_18000DDB6
0x18000dc78  xor     eax, eax
0x18000dc7a  mov     [rsi+rbx*2], ax
0x18000dc7e  test    rbx, rbx
0x18000dc81  jz      short loc_18000DCCA
0x18000dc83  mov     r8, [rdi]
0x18000dc86  mov     r9, rbx
0x18000dc89  mov     rdx, r15
0x18000dc8c  mov     rcx, rsi
0x18000dc8f  call    _o_wcsncpy_s_0
0x18000dc94  mov     r12d, eax
0x18000dc97  test    eax, eax
0x18000dc99  jz      short loc_18000DCCA
0x18000dc9b  mov     ecx, eax; ErrorNumber
0x18000dc9d  call    _wcserror
0x18000dca2  mov     r9, rax
0x18000dca5  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000dcac  mov     r8d, r12d
0x18000dcaf  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x18000dcb6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dcbb  mov     ecx, r12d; int
0x18000dcbe  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18000dcc3  mov     ebp, eax
0x18000dcc5  jmp     loc_18000DDB6
0x18000dcca  mov     rcx, [rdi]; lpMem
0x18000dccd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000dcd2  mov     [rdi], rsi
0x18000dcd5  mov     [rdi+8], r15
0x18000dcd9  jmp     short loc_18000DCDE
0x18000dcdb  mov     rsi, [rdi]
0x18000dcde  mov     r12d, 5Ch ; '\'
0x18000dce4  test    rbx, rbx
0x18000dce7  jz      short loc_18000DD2D
0x18000dce9  cmp     [rsi+rbx*2-2], r12w
0x18000dcef  setz    al
0x18000dcf2  jnz     short loc_18000DD09
0x18000dcf4  cmp     [r13+0], r12w
0x18000dcf9  jnz     short loc_18000DD09
0x18000dcfb  dec     rbx
0x18000dcfe  xor     r15b, r15b
0x18000dd01  xor     eax, eax
0x18000dd03  mov     [rsi+rbx*2], ax
0x18000dd07  jmp     short loc_18000DD30
0x18000dd09  xor     r15b, r15b
0x18000dd0c  test    al, al
0x18000dd0e  jnz     short loc_18000DD30
0x18000dd10  cmp     [r13+0], r12w
0x18000dd15  jz      short loc_18000DD30
0x18000dd17  mov     [rsi+rbx*2], r12w
0x18000dd1c  mov     r15b, 1
0x18000dd1f  mov     rcx, [rdi]
0x18000dd22  inc     rbx
0x18000dd25  xor     eax, eax
0x18000dd27  mov     [rcx+rbx*2], ax
0x18000dd2b  jmp     short loc_18000DD30
0x18000dd2d  xor     r15b, r15b
0x18000dd30  mov     rax, [rdi]
0x18000dd33  lea     r9, [r14+1]
0x18000dd37  mov     rdx, [rdi+8]
0x18000dd3b  mov     r8, r13
0x18000dd3e  sub     rdx, rbx
0x18000dd41  lea     rcx, [rax+rbx*2]
0x18000dd45  call    _o_wcsncpy_s_0
0x18000dd4a  mov     esi, eax
0x18000dd4c  test    eax, eax
0x18000dd4e  jz      short loc_18000DD96
0x18000dd50  mov     ecx, eax; ErrorNumber
0x18000dd52  call    _wcserror
0x18000dd57  mov     r9, rax
0x18000dd5a  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18000dd61  mov     r8d, esi
0x18000dd64  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x18000dd6b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dd70  mov     ecx, esi; int
0x18000dd72  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18000dd77  mov     ebp, eax
0x18000dd79  test    r15b, r15b
0x18000dd7c  jz      short loc_18000DD8A
0x18000dd7e  mov     rcx, [rdi]
0x18000dd81  dec     rbx
0x18000dd84  xor     eax, eax
0x18000dd86  mov     [rcx+rbx*2], ax
0x18000dd8a  cmp     [rdi+18h], rbx
0x18000dd8e  jbe     short loc_18000DDB4
0x18000dd90  mov     [rdi+18h], rbx
0x18000dd94  jmp     short loc_18000DDB4
0x18000dd96  mov     rcx, [rdi+18h]
0x18000dd9a  mov     rax, [rdi]
0x18000dd9d  cmp     [rax+rcx*2], r12w
0x18000dda2  jnz     short loc_18000DDAC
0x18000dda4  lea     rax, [rcx+1]
0x18000dda8  mov     [rdi+18h], rax
0x18000ddac  mov     rcx, rdi; this
0x18000ddaf  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x18000ddb4  xor     esi, esi
0x18000ddb6  mov     rcx, rsi; lpMem
0x18000ddb9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ddbe  mov     eax, ebp
0x18000ddc0  add     rsp, 28h
0x18000ddc4  pop     r15
0x18000ddc6  pop     r14
0x18000ddc8  pop     r13
0x18000ddca  pop     r12
0x18000ddcc  pop     rdi
0x18000ddcd  pop     rsi
0x18000ddce  pop     rbp
0x18000ddcf  pop     rbx
0x18000ddd0  retn
```
