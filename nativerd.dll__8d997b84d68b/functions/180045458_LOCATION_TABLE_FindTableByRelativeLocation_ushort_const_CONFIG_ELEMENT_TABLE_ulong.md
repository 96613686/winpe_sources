# LOCATION_TABLE::FindTableByRelativeLocation(ushort const *,CONFIG_ELEMENT_TABLE * *,ulong *)

- ea: `0x180045458`
- end: `0x18004556f`
- name: `?FindTableByRelativeLocation@LOCATION_TABLE@@AEAAJPEBGPEAPEAVCONFIG_ELEMENT_TABLE@@PEAK@Z`
- size: `279`
- prototype: `__int64 __fastcall(LOCATION_TABLE *__hidden this, const unsigned __int16 *, struct CONFIG_ELEMENT_TABLE **, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180044fa0`
- `0x180045070`
- `0x1800456a0`
- `0x180045aa0`

## callees

- `0x1800156d0`
- `0x180045458`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180045547`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180045547`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045529`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180045529`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800454a8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800454a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045504`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180045504`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180045518`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180045518`

## pseudocode

```c
__int64 __fastcall LOCATION_TABLE::FindTableByRelativeLocation(
        LOCATION_TABLE *this,
        const unsigned __int16 *a2,
        struct CONFIG_ELEMENT_TABLE **a3,
        unsigned int *a4)
{
  int Table; // ebx
  int v9; // edx
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *Str; // rax
  _BYTE v14[64]; // [rsp+20h] [rbp-188h] BYREF
  unsigned __int16 v15[128]; // [rsp+60h] [rbp-148h] BYREF

  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v14, v15, 0x80u);
  if ( !a2 )
  {
    Table = -2147024809;
    goto LABEL_14;
  }
  if ( *a2 )
  {
    v9 = *a2 - 46;
    if ( *a2 == 46 )
      v9 = a2[1];
    if ( v9 )
    {
      v10 = (int)(*((_DWORD *)this + 5) << 27) >> 28;
      if ( v10 == 1 )
      {
        v11 = L"WEBROOT/APPHOST/";
        goto LABEL_11;
      }
      if ( v10 == 2 )
      {
        v11 = L"APPHOST/";
LABEL_11:
        Table = STRU::Copy((STRU *)v14, v11);
        if ( Table < 0 )
          goto LABEL_14;
      }
    }
  }
  Table = STRU::Append((STRU *)v14, a2);
  if ( Table >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v14);
    Table = LOCATION_TABLE::FindTable(this, Str, a3, a4);
  }
LABEL_14:
  STRU::~STRU((STRU *)v14);
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x180045458  push    rbx
0x18004545a  push    rbp
0x18004545b  push    rsi
0x18004545c  push    rdi
0x18004545d  push    r14
0x18004545f  push    r15
0x180045461  sub     rsp, 178h
0x180045468  mov     rax, cs:__security_cookie
0x18004546f  xor     rax, rsp
0x180045472  mov     [rsp+1A8h+var_48], rax
0x18004547a  mov     rbp, r8
0x18004547d  mov     rdi, rdx
0x180045480  mov     rsi, rcx
0x180045483  xor     edx, edx; Val
0x180045485  mov     r8d, 100h; Size
0x18004548b  lea     rcx, [rsp+1A8h+var_148]; void *
0x180045490  mov     r14, r9
0x180045493  call    memset_0
0x180045498  mov     r8d, 80h
0x18004549e  lea     rdx, [rsp+1A8h+var_148]
0x1800454a3  lea     rcx, [rsp+1A8h+var_188]
0x1800454a8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800454ae  xor     r15d, r15d
0x1800454b1  test    rdi, rdi
0x1800454b4  jnz     short loc_1800454C0
0x1800454b6  mov     ebx, 80070057h
0x1800454bb  jmp     loc_180045542
0x1800454c0  cmp     [rdi], r15w
0x1800454c4  jz      short loc_180045510
0x1800454c6  movzx   edx, word ptr [rdi]
0x1800454c9  sub     edx, 2Eh ; '.'
0x1800454cc  jnz     short loc_1800454D8
0x1800454ce  movzx   edx, word ptr [rdi+2]
0x1800454d2  movzx   ecx, r15w
0x1800454d6  sub     edx, ecx
0x1800454d8  test    edx, edx
0x1800454da  jz      short loc_180045510
0x1800454dc  mov     eax, [rsi+14h]
0x1800454df  shl     eax, 1Bh
0x1800454e2  sar     eax, 1Ch
0x1800454e5  cmp     eax, 1
0x1800454e8  jnz     short loc_1800454F3
0x1800454ea  lea     rdx, aWebrootApphost_0; "WEBROOT/APPHOST/"
0x1800454f1  jmp     short loc_1800454FF
0x1800454f3  cmp     eax, 2
0x1800454f6  jnz     short loc_180045510
0x1800454f8  lea     rdx, aApphost_0; "APPHOST/"
0x1800454ff  lea     rcx, [rsp+1A8h+var_188]
0x180045504  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004550a  mov     ebx, eax
0x18004550c  test    eax, eax
0x18004550e  js      short loc_180045542
0x180045510  mov     rdx, rdi
0x180045513  lea     rcx, [rsp+1A8h+var_188]
0x180045518  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18004551e  mov     ebx, eax
0x180045520  test    eax, eax
0x180045522  js      short loc_180045542
0x180045524  lea     rcx, [rsp+1A8h+var_188]
0x180045529  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004552f  mov     r9, r14; unsigned int *
0x180045532  mov     r8, rbp; struct CONFIG_ELEMENT_TABLE **
0x180045535  mov     rdx, rax; unsigned __int16 *
0x180045538  mov     rcx, rsi; this
0x18004553b  call    ?FindTable@LOCATION_TABLE@@QEAAJPEBGPEAPEAVCONFIG_ELEMENT_TABLE@@PEAK@Z; LOCATION_TABLE::FindTable(ushort const *,CONFIG_ELEMENT_TABLE * *,ulong *)
0x180045540  mov     ebx, eax
0x180045542  lea     rcx, [rsp+1A8h+var_188]
0x180045547  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004554d  mov     eax, ebx
0x18004554f  mov     rcx, [rsp+1A8h+var_48]
0x180045557  xor     rcx, rsp; StackCookie
0x18004555a  call    __security_check_cookie
0x18004555f  add     rsp, 178h
0x180045566  pop     r15
0x180045568  pop     r14
0x18004556a  pop     rdi
0x18004556b  pop     rsi
0x18004556c  pop     rbp
0x18004556d  pop     rbx
0x18004556e  retn
```
