# CONFIG_EXCEPTION::Create(PARSE_ERROR_INFO *)

- ea: `0x180058ba0`
- end: `0x180058c70`
- name: `?Create@CONFIG_EXCEPTION@@QEAAJPEAVPARSE_ERROR_INFO@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(CONFIG_EXCEPTION *__hidden this, struct PARSE_ERROR_INFO *)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180021ad0`
- `0x1800265d0`
- `0x1800271d0`
- `0x18003a11c`
- `0x1800439e8`
- `0x180043f5c`
- `0x18004d0b8`

## callees

- `0x180058ba0`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058bdc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058bfa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c1e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c3c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c5a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058bdc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058bfa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c1e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c3c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058c5a`

## pseudocode

```c
int __fastcall CONFIG_EXCEPTION::Create(CONFIG_EXCEPTION *this, struct PARSE_ERROR_INFO *a2)
{
  int result; // eax
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rdx

  if ( !a2 )
    return -2147024809;
  v5 = &szDomain;
  v6 = &szDomain;
  if ( *((_QWORD *)a2 + 4) )
    v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  result = STRU::Copy((CONFIG_EXCEPTION *)((char *)this + 40), v6);
  if ( result >= 0 )
  {
    v7 = &szDomain;
    if ( *((_QWORD *)a2 + 3) )
      v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
    result = STRU::Copy((CONFIG_EXCEPTION *)((char *)this + 152), v7);
    if ( result >= 0 )
    {
      *((_DWORD *)this + 9) = *((_DWORD *)a2 + 3);
      v8 = &szDomain;
      if ( *((_QWORD *)a2 + 5) )
        v8 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
      result = STRU::Copy((CONFIG_EXCEPTION *)((char *)this + 208), v8);
      if ( result >= 0 )
      {
        v9 = &szDomain;
        if ( *((_QWORD *)a2 + 6) )
          v9 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        result = STRU::Copy((CONFIG_EXCEPTION *)((char *)this + 264), v9);
        if ( result >= 0 )
        {
          if ( *((_QWORD *)a2 + 7) )
            v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
          return STRU::Copy((CONFIG_EXCEPTION *)((char *)this + 320), v5);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180058ba0  mov     [rsp+arg_0], rbx
0x180058ba5  mov     [rsp+arg_8], rsi
0x180058baa  push    rdi
0x180058bab  sub     rsp, 20h
0x180058baf  mov     rbx, rdx
0x180058bb2  mov     rdi, rcx
0x180058bb5  test    rdx, rdx
0x180058bb8  jnz     short loc_180058BC4
0x180058bba  mov     eax, 80070057h
0x180058bbf  jmp     loc_180058C60
0x180058bc4  cmp     qword ptr [rbx+20h], 0
0x180058bc9  lea     rsi, szDomain
0x180058bd0  mov     rdx, rsi
0x180058bd3  cmovnz  rdx, [rbx+20h]
0x180058bd8  add     rcx, 28h ; '('
0x180058bdc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058be2  test    eax, eax
0x180058be4  js      short loc_180058C60
0x180058be6  cmp     qword ptr [rbx+18h], 0
0x180058beb  lea     rcx, [rdi+98h]
0x180058bf2  mov     rdx, rsi
0x180058bf5  cmovnz  rdx, [rbx+18h]
0x180058bfa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058c00  test    eax, eax
0x180058c02  js      short loc_180058C60
0x180058c04  mov     eax, [rbx+0Ch]
0x180058c07  lea     rcx, [rdi+0D0h]
0x180058c0e  mov     [rdi+24h], eax
0x180058c11  mov     rdx, rsi
0x180058c14  cmp     qword ptr [rbx+28h], 0
0x180058c19  cmovnz  rdx, [rbx+28h]
0x180058c1e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058c24  test    eax, eax
0x180058c26  js      short loc_180058C60
0x180058c28  cmp     qword ptr [rbx+30h], 0
0x180058c2d  lea     rcx, [rdi+108h]
0x180058c34  mov     rdx, rsi
0x180058c37  cmovnz  rdx, [rbx+30h]
0x180058c3c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058c42  test    eax, eax
0x180058c44  js      short loc_180058C60
0x180058c46  cmp     qword ptr [rbx+38h], 0
0x180058c4b  lea     rcx, [rdi+140h]
0x180058c52  cmovnz  rsi, [rbx+38h]
0x180058c57  mov     rdx, rsi
0x180058c5a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058c60  mov     rbx, [rsp+28h+arg_0]
0x180058c65  mov     rsi, [rsp+28h+arg_8]
0x180058c6a  add     rsp, 20h
0x180058c6e  pop     rdi
0x180058c6f  retn
```
