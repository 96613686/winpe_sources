# GetCompiledName(char const *,CStr *)

- ea: `0x180066cc0`
- end: `0x180066e3c`
- name: `?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z`
- size: `380`
- prototype: `const char *__fastcall(PCSTR pszFirst, struct CStr *)`
- caller_count: `16`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c484`
- `0x180013c00`
- `0x18001dd04`
- `0x1800269d0`
- `0x18002b334`
- `0x18002d2dc`
- `0x180030704`
- `0x180037e70`
- `0x180038028`
- `0x180038640`
- `0x180038d40`
- `0x180038e7c`
- `0x180048910`
- `0x180062d70`
- `0x180063bd8`
- `0x18006a610`

## callees

- `0x180004224`
- `0x180057e60`
- `0x180066cc0`

## import_xrefs

- `SHLWAPI!StrStrA` at `0x180066dfa`
- `SHLWAPI!StrStrA` at `0x180066e23`
- `SHLWAPI!StrStrA` at `0x180066dfa`
- `SHLWAPI!StrStrA` at `0x180066e23`

## string_xrefs

- `0x180066cdc`: `mk:@MSITStore:`

## pseudocode

```c
const char *__fastcall GetCompiledName(PCSTR pszFirst, PCSTR *a2)
{
  const CHAR *v3; // rbx
  PCSTR v4; // r9
  const char *v5; // r10
  int i; // r8d
  int v7; // edx
  int v8; // ecx
  int v9; // r11d
  int v10; // edx
  const CHAR *v11; // r8
  const char *v12; // r9
  int j; // edx
  int v14; // ecx
  int v15; // r11d
  int v16; // ecx
  int v17; // r10d
  const CHAR *v18; // r8
  const char *v19; // r9
  int k; // edx
  int v21; // ecx
  int v22; // r11d
  int v23; // ecx
  int v24; // r10d
  PSTR v25; // rax
  unsigned __int64 v26; // r9

  v3 = pszFirst;
  if ( !pszFirst )
    return 0;
  v4 = pszFirst;
  v5 = "mk:@MSITStore:";
  for ( i = 14; ; --i )
  {
    if ( !i )
      goto LABEL_34;
    v7 = *(unsigned __int8 *)v4;
    v8 = *(unsigned __int8 *)v5;
    v9 = v7 + 32;
    if ( (unsigned int)(v7 - 65) > 0x19 )
      v9 = *(unsigned __int8 *)v4;
    v10 = v8 + 32;
    if ( (unsigned int)(v8 - 65) > 0x19 )
      v10 = *(unsigned __int8 *)v5;
    if ( v9 != v10 )
      goto LABEL_12;
    if ( !v9 )
      break;
    ++v4;
    ++v5;
  }
  if ( !v10 )
  {
LABEL_34:
    v3 += 14;
    goto LABEL_35;
  }
LABEL_12:
  v11 = v3;
  v12 = "ms-its:";
  for ( j = 7; ; --j )
  {
    if ( !j )
      goto LABEL_33;
    v14 = *(unsigned __int8 *)v11;
    v15 = v14 + 32;
    if ( (unsigned int)(v14 - 65) > 0x19 )
      v15 = *(unsigned __int8 *)v11;
    v16 = *(unsigned __int8 *)v12;
    v17 = v16 + 32;
    if ( (unsigned int)(v16 - 65) > 0x19 )
      v17 = *(unsigned __int8 *)v12;
    if ( v15 != v17 )
      goto LABEL_22;
    if ( !v15 )
      break;
    ++v11;
    ++v12;
  }
  if ( !v17 )
  {
LABEL_33:
    v3 += 7;
    goto LABEL_35;
  }
LABEL_22:
  v18 = v3;
  v19 = "its:";
  for ( k = 4; k; --k )
  {
    v21 = *(unsigned __int8 *)v18;
    v22 = v21 + 32;
    if ( (unsigned int)(v21 - 65) > 0x19 )
      v22 = *(unsigned __int8 *)v18;
    v23 = *(unsigned __int8 *)v19;
    v24 = v23 + 32;
    if ( (unsigned int)(v23 - 65) > 0x19 )
      v24 = *(unsigned __int8 *)v19;
    if ( v22 != v24 )
      goto LABEL_35;
    if ( !v22 )
    {
      if ( v24 )
        goto LABEL_35;
      break;
    }
    ++v18;
    ++v19;
  }
  v3 += 4;
LABEL_35:
  CStr::operator=(a2);
  v25 = StrStrA(*a2, "::");
  if ( !v25 )
    return 0;
  *v25 = 0;
  ReplaceEscapes(*a2, (char *)*a2, 2, v26);
  return StrStrA(v3, "::") + 2;
}

```

## disassembly

```asm
0x180066cc0  mov     [rsp+arg_0], rbx
0x180066cc5  push    rdi
0x180066cc6  sub     rsp, 20h
0x180066cca  mov     rdi, rdx
0x180066ccd  mov     rbx, rcx
0x180066cd0  test    rcx, rcx
0x180066cd3  jz      loc_180066E2F
0x180066cd9  mov     r9, rcx
0x180066cdc  lea     r10, ?txtMkStore@@3QBDB; "mk:@MSITStore:"
0x180066ce3  mov     r8d, 0Eh
0x180066ce9  test    r8d, r8d
0x180066cec  jz      loc_180066DE1
0x180066cf2  movzx   edx, byte ptr [r9]
0x180066cf6  movzx   ecx, byte ptr [r10]
0x180066cfa  lea     eax, [rdx-41h]
0x180066cfd  cmp     eax, 19h
0x180066d00  lea     r11d, [rdx+20h]
0x180066d04  lea     eax, [rcx-41h]
0x180066d07  cmova   r11d, edx
0x180066d0b  cmp     eax, 19h
0x180066d0e  lea     edx, [rcx+20h]
0x180066d11  cmova   edx, ecx
0x180066d14  cmp     r11d, edx
0x180066d17  jnz     short loc_180066D31
0x180066d19  test    r11d, r11d
0x180066d1c  jz      short loc_180066D29
0x180066d1e  dec     r8d
0x180066d21  inc     r9
0x180066d24  inc     r10
0x180066d27  jmp     short loc_180066CE9
0x180066d29  test    edx, edx
0x180066d2b  jz      loc_180066DE1
0x180066d31  mov     r8, rbx
0x180066d34  lea     r9, ?txtMsItsMoniker@@3QBDB; "ms-its:"
0x180066d3b  mov     edx, 7
0x180066d40  test    edx, edx
0x180066d42  jz      loc_180066DDB
0x180066d48  movzx   ecx, byte ptr [r8]
0x180066d4c  lea     eax, [rcx-41h]
0x180066d4f  cmp     eax, 19h
0x180066d52  lea     r11d, [rcx+20h]
0x180066d56  cmova   r11d, ecx
0x180066d5a  movzx   ecx, byte ptr [r9]
0x180066d5e  lea     eax, [rcx-41h]
0x180066d61  cmp     eax, 19h
0x180066d64  lea     r10d, [rcx+20h]
0x180066d68  cmova   r10d, ecx
0x180066d6c  cmp     r11d, r10d
0x180066d6f  jnz     short loc_180066D85
0x180066d71  test    r11d, r11d
0x180066d74  jz      short loc_180066D80
0x180066d76  dec     edx
0x180066d78  inc     r8
0x180066d7b  inc     r9
0x180066d7e  jmp     short loc_180066D40
0x180066d80  test    r10d, r10d
0x180066d83  jz      short loc_180066DDB
0x180066d85  mov     r8, rbx
0x180066d88  lea     r9, ?txtItsMoniker@@3QBDB; "its:"
0x180066d8f  mov     edx, 4
0x180066d94  test    edx, edx
0x180066d96  jz      short loc_180066DD5
0x180066d98  movzx   ecx, byte ptr [r8]
0x180066d9c  lea     eax, [rcx-41h]
0x180066d9f  cmp     eax, 19h
0x180066da2  lea     r11d, [rcx+20h]
0x180066da6  cmova   r11d, ecx
0x180066daa  movzx   ecx, byte ptr [r9]
0x180066dae  lea     eax, [rcx-41h]
0x180066db1  cmp     eax, 19h
0x180066db4  lea     r10d, [rcx+20h]
0x180066db8  cmova   r10d, ecx
0x180066dbc  cmp     r11d, r10d
0x180066dbf  jnz     short loc_180066DE5
0x180066dc1  test    r11d, r11d
0x180066dc4  jz      short loc_180066DD0
0x180066dc6  dec     edx
0x180066dc8  inc     r8
0x180066dcb  inc     r9
0x180066dce  jmp     short loc_180066D94
0x180066dd0  test    r10d, r10d
0x180066dd3  jnz     short loc_180066DE5
0x180066dd5  add     rbx, 4
0x180066dd9  jmp     short loc_180066DE5
0x180066ddb  add     rbx, 7
0x180066ddf  jmp     short loc_180066DE5
0x180066de1  add     rbx, 0Eh
0x180066de5  mov     rdx, rbx
0x180066de8  mov     rcx, rdi
0x180066deb  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180066df0  mov     rcx, [rdi]; pszFirst
0x180066df3  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x180066dfa  call    cs:__imp_StrStrA
0x180066e00  test    rax, rax
0x180066e03  jz      short loc_180066E2F
0x180066e05  mov     byte ptr [rax], 0
0x180066e08  mov     r8d, 2; int
0x180066e0e  mov     rcx, [rdi]; char *
0x180066e11  mov     rdx, rcx; char *
0x180066e14  call    ?ReplaceEscapes@@YAHPEBDPEADH_K@Z; ReplaceEscapes(char const *,char *,int,unsigned __int64)
0x180066e19  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x180066e20  mov     rcx, rbx; pszFirst
0x180066e23  call    cs:__imp_StrStrA
0x180066e29  add     rax, 2
0x180066e2d  jmp     short loc_180066E31
0x180066e2f  xor     eax, eax
0x180066e31  mov     rbx, [rsp+28h+arg_0]
0x180066e36  add     rsp, 20h
0x180066e3a  pop     rdi
0x180066e3b  retn
```
