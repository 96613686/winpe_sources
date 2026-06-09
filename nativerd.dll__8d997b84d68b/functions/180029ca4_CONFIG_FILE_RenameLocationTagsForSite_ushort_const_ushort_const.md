# CONFIG_FILE::RenameLocationTagsForSite(ushort const *,ushort const *)

- ea: `0x180029ca4`
- end: `0x180029e58`
- name: `?RenameLocationTagsForSite@CONFIG_FILE@@AEAAJPEBG0@Z`
- size: `436`
- prototype: `int(CONFIG_FILE *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800273e8`

## callees

- `0x180029ca4`
- `0x180045790`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180029d93`
- `msvcrt!_wcsnicmp` at `0x180029d93`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e25`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180029e25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029df2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180029df2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180029cf8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180029cf8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180029dbe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180029dbe`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180029dda`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180029dda`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::RenameLocationTagsForSite(
        CONFIG_FILE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  int v7; // r15d
  __int64 v8; // rdi
  unsigned int v9; // esi
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // r14
  const unsigned __int16 *v14; // r14
  LOCATION_TABLE *v15; // rbx
  const unsigned __int16 *Str; // rax
  unsigned int v18; // [rsp+20h] [rbp-118h]
  unsigned int v19[2]; // [rsp+30h] [rbp-108h]
  _BYTE v20[56]; // [rsp+38h] [rbp-100h] BYREF
  unsigned __int16 v21[64]; // [rsp+70h] [rbp-C8h] BYREF

  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v20, v21, 0x40u);
  if ( a2 && a3 && (*((_DWORD *)this + 68) & 0x3C0) == 0xC0 )
  {
    v6 = 0;
    v7 = 0;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = 0;
    v10 = *(_DWORD *)(*((_QWORD *)this + 22) + 48LL);
    v18 = v10;
    while ( v9 < v10 )
    {
      *(_QWORD *)v19 = v9 - v7;
      v11 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 22) + 40LL) + 8LL * *(_QWORD *)v19);
      v12 = v11 + 96;
      if ( !v11 )
        v12 = 104;
      v13 = *(const wchar_t **)v12;
      if ( !_wcsnicmp(*(const wchar_t **)v12, a2, (unsigned int)v8) )
      {
        v14 = &v13[(unsigned int)v8];
        if ( *v14 == 47 || !*v14 )
        {
          v6 = STRU::Copy((STRU *)v20, a3);
          if ( v6 < 0 )
            break;
          if ( *v14 )
          {
            v6 = STRU::Append((STRU *)v20, v14);
            if ( v6 < 0 )
              break;
          }
          v15 = (LOCATION_TABLE *)*((_QWORD *)this + 22);
          Str = STRU::QueryStr((STRU *)v20);
          v6 = LOCATION_TABLE::RenameLocationInternal(v15, v19[0], Str);
          if ( v6 < 0 )
            break;
          ++v7;
        }
      }
      v10 = v18;
      ++v9;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  STRU::~STRU((STRU *)v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180029ca4  mov     [rsp+arg_18], rbx
0x180029ca9  push    rbp
0x180029caa  push    rsi
0x180029cab  push    rdi
0x180029cac  push    r12
0x180029cae  push    r13
0x180029cb0  push    r14
0x180029cb2  push    r15
0x180029cb4  sub     rsp, 100h
0x180029cbb  mov     rax, cs:__security_cookie
0x180029cc2  xor     rax, rsp
0x180029cc5  mov     [rsp+138h+var_48], rax
0x180029ccd  mov     r12, r8
0x180029cd0  mov     r13, rdx
0x180029cd3  mov     rbp, rcx
0x180029cd6  xor     edx, edx; Val
0x180029cd8  mov     r8d, 80h; Size
0x180029cde  lea     rcx, [rsp+138h+var_C8]; void *
0x180029ce3  call    memset_0
0x180029ce8  mov     r8d, 40h ; '@'
0x180029cee  lea     rdx, [rsp+138h+var_C8]
0x180029cf3  lea     rcx, [rsp+138h+var_100]
0x180029cf8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180029cfe  xor     r8d, r8d
0x180029d01  test    r13, r13
0x180029d04  jz      loc_180029E1B
0x180029d0a  test    r12, r12
0x180029d0d  jz      loc_180029E1B
0x180029d13  mov     eax, [rbp+110h]
0x180029d19  and     eax, 3C0h
0x180029d1e  cmp     eax, 0C0h
0x180029d23  jnz     loc_180029E1B
0x180029d29  mov     ebx, r8d
0x180029d2c  mov     r15d, r8d
0x180029d2f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029d33  inc     rdi
0x180029d36  cmp     [r13+rdi*2+0], r8w
0x180029d3c  jnz     short loc_180029D33
0x180029d3e  mov     rax, [rbp+0B0h]
0x180029d45  mov     esi, r8d
0x180029d48  mov     eax, [rax+30h]
0x180029d4b  mov     [rsp+138h+var_118], eax
0x180029d4f  cmp     esi, eax
0x180029d51  jnb     loc_180029E20
0x180029d57  mov     rax, [rbp+0B0h]
0x180029d5e  mov     edx, esi
0x180029d60  sub     edx, r15d
0x180029d63  mov     r8d, edi; MaxCount
0x180029d66  mov     qword ptr [rsp+138h+var_108], rdx
0x180029d6b  mov     rcx, [rax+28h]
0x180029d6f  mov     rax, [rcx+rdx*8]
0x180029d73  mov     edx, 68h ; 'h'
0x180029d78  test    rax, rax
0x180029d7b  lea     rcx, [rax+60h]
0x180029d7f  mov     eax, edi
0x180029d81  cmovz   rcx, rdx
0x180029d85  mov     [rsp+138h+var_110], rax
0x180029d8a  mov     rdx, r13; String2
0x180029d8d  mov     r14, [rcx]
0x180029d90  mov     rcx, r14; String1
0x180029d93  call    cs:__imp__wcsnicmp
0x180029d99  xor     r8d, r8d
0x180029d9c  test    eax, eax
0x180029d9e  jnz     short loc_180029E10
0x180029da0  mov     rax, [rsp+138h+var_110]
0x180029da5  lea     r14, [r14+rax*2]
0x180029da9  cmp     word ptr [r14], 2Fh ; '/'
0x180029dae  jz      short loc_180029DB6
0x180029db0  cmp     [r14], r8w
0x180029db4  jnz     short loc_180029E10
0x180029db6  mov     rdx, r12
0x180029db9  lea     rcx, [rsp+138h+var_100]
0x180029dbe  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180029dc4  mov     ebx, eax
0x180029dc6  xor     eax, eax
0x180029dc8  test    ebx, ebx
0x180029dca  js      short loc_180029E20
0x180029dcc  cmp     [r14], ax
0x180029dd0  jz      short loc_180029DE6
0x180029dd2  mov     rdx, r14
0x180029dd5  lea     rcx, [rsp+138h+var_100]
0x180029dda  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180029de0  mov     ebx, eax
0x180029de2  test    eax, eax
0x180029de4  js      short loc_180029E20
0x180029de6  mov     rbx, [rbp+0B0h]
0x180029ded  lea     rcx, [rsp+138h+var_100]
0x180029df2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180029df8  mov     edx, [rsp+138h+var_108]; unsigned int
0x180029dfc  mov     rcx, rbx; this
0x180029dff  mov     r8, rax; unsigned __int16 *
0x180029e02  call    ?RenameLocationInternal@LOCATION_TABLE@@QEAAJKPEBG@Z; LOCATION_TABLE::RenameLocationInternal(ulong,ushort const *)
0x180029e07  mov     ebx, eax
0x180029e09  test    eax, eax
0x180029e0b  js      short loc_180029E20
0x180029e0d  inc     r15d
0x180029e10  mov     eax, [rsp+138h+var_118]
0x180029e14  inc     esi
0x180029e16  jmp     loc_180029D4F
0x180029e1b  mov     ebx, 80070057h
0x180029e20  lea     rcx, [rsp+138h+var_100]
0x180029e25  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180029e2b  mov     eax, ebx
0x180029e2d  mov     rcx, [rsp+138h+var_48]
0x180029e35  xor     rcx, rsp; StackCookie
0x180029e38  call    __security_check_cookie
0x180029e3d  mov     rbx, [rsp+138h+arg_18]
0x180029e45  add     rsp, 100h
0x180029e4c  pop     r15
0x180029e4e  pop     r14
0x180029e50  pop     r13
0x180029e52  pop     r12
0x180029e54  pop     rdi
0x180029e55  pop     rsi
0x180029e56  pop     rbp
0x180029e57  retn
```
