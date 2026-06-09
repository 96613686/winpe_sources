# CUtlProps2::CopyUPropVal(ulong,tagUPROPVAL *,CColumnIds *,unsigned __int64)

- ea: `0x18013b824`
- end: `0x18013ba8a`
- name: `?CopyUPropVal@CUtlProps2@@QEBAJKPEAUtagUPROPVAL@@PEAVCColumnIds@@_K@Z`
- size: `614`
- prototype: `int(CUtlProps2 *__hidden this, unsigned int, struct tagUPROPVAL *, struct CColumnIds *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18013bca0`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1801355e0`
- `0x180136c2c`
- `0x18013737c`
- `0x18013b824`
- `0x1801a65e1`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18013b9cf`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18013b9cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18013b9db`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18013b9db`
- `OLEAUT32!__imp_VariantClear` at `0x18013ba5e`
- `OLEAUT32!__imp_VariantClear` at `0x18013ba5e`
- `OLEAUT32!__imp_VariantCopy` at `0x18013b9ab`
- `OLEAUT32!__imp_VariantCopy` at `0x18013b9ab`

## pseudocode

```c
__int64 __fastcall CUtlProps2::CopyUPropVal(
        CUtlProps2 *this,
        unsigned int a2,
        struct tagUPROPVAL *a3,
        struct CColumnIds *a4,
        unsigned __int64 a5)
{
  __int64 v6; // rbx
  HRESULT v8; // esi
  __int64 v10; // rcx
  __int64 v11; // r14
  unsigned int v12; // r15d
  __int64 v14; // rdi
  __int64 v15; // rbx
  CEXAutoBackupFile *v16; // rcx
  CEXAutoBackupFile *v17; // rax
  int v18; // r14d
  int NextValue; // eax
  int v20; // ecx
  __int64 v21; // rax
  VARIANTARG *v22; // rcx
  char *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v27; // [rsp+20h] [rbp-B8h]
  __int64 v28; // [rsp+28h] [rbp-B0h]
  struct tagDBPROP v29; // [rsp+30h] [rbp-A8h] BYREF

  v6 = a2;
  v8 = 0;
  memset_0(&v29, 0, sizeof(v29));
  v10 = *((_QWORD *)this + 6);
  v11 = 3 * v6;
  v28 = 3 * v6;
  v27 = v10;
  v12 = 0;
  if ( !*(_DWORD *)(v10 + 24 * v6) )
    goto LABEL_39;
  while ( 1 )
  {
    v14 = *(_QWORD *)(v10 + 8 * v11 + 16);
    v15 = 56LL * v12;
    *(_DWORD *)((char *)a3 + v15) = *(_DWORD *)(v15 + v14);
    *(_DWORD *)((char *)a3 + v15 + 12) = *(_DWORD *)(v15 + v14 + 12);
    *(_DWORD *)((char *)a3 + v15 + 16) = *(_DWORD *)(v15 + v14 + 16);
    *(_DWORD *)((char *)a3 + v15 + 4) = *(_DWORD *)(v15 + v14 + 4);
    *(_DWORD *)((char *)a3 + v15 + 8) = *(_DWORD *)(v15 + v14 + 8);
    if ( *(_QWORD *)(v15 + v14 + 24) )
      break;
    *(_QWORD *)((char *)a3 + v15 + 24) = 0;
LABEL_16:
    v21 = v15 + v14;
    if ( *(_WORD *)(v15 + v14 + 32) )
    {
      switch ( *(_WORD *)(v21 + 32) )
      {
        case 3:
          goto LABEL_24;
        case 8:
          if ( !*(_QWORD *)(v15 + v14 + 40) )
            goto LABEL_24;
LABEL_21:
          v22 = (VARIANTARG *)((char *)a3 + v15 + 32);
          v22->vt = 0;
          v8 = VariantCopy(v22, (const VARIANTARG *)(v21 + 32));
          if ( v8 < 0 )
            goto LABEL_39;
          break;
        case 0xB:
        case 0x14:
LABEL_24:
          v23 = (char *)a3 + v15 + 32;
          if ( v23 )
          {
            *(_OWORD *)v23 = *(_OWORD *)(v21 + 32);
            *((_QWORD *)v23 + 2) = *(_QWORD *)(v21 + 48);
          }
          else
          {
            *_errno() = 22;
            _invalid_parameter_noinfo();
          }
          break;
        default:
          goto LABEL_21;
      }
      v10 = v27;
      goto LABEL_30;
    }
    if ( *(_WORD *)((char *)a3 + v15 + 32) )
      goto LABEL_24;
LABEL_30:
    if ( ++v12 >= *(_DWORD *)(v10 + 8 * v11) )
      goto LABEL_39;
  }
  v16 = a4;
  *((_DWORD *)a4 + 5) = 1;
  a4 = (struct CColumnIds *)((char *)a4 + 24);
  if ( v16 )
    v17 = CEXAutoBackupFile::CEXAutoBackupFile(v16);
  else
    v17 = 0;
  *(_QWORD *)((char *)a3 + v15 + 24) = v17;
  if ( v17 )
  {
    v18 = 1;
    *(_QWORD *)(*(_QWORD *)(v15 + v14 + 24) + 8LL) = **(_QWORD **)(v15 + v14 + 24);
    while ( a5 )
    {
      NextValue = CColumnIds::GetNextValue(*(CColumnIds **)(v15 + v14 + 24), &v29.dwOptions, &v29.colid, &v29.vValue);
      v8 = NextValue;
      if ( NextValue < 0 )
        goto LABEL_39;
      v20 = 0;
      if ( NextValue != 1 )
        v20 = v18;
      v18 = v20;
      v8 = CColumnIds::AddColumnId(*(CColumnIds **)((char *)a3 + v15 + 24), &v29);
      if ( v8 < 0 )
        goto LABEL_39;
      --a5;
      if ( !v18 )
      {
        v11 = v28;
        v10 = v27;
        goto LABEL_16;
      }
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v24 = 809993;
      v25 = 2147549183LL;
      goto LABEL_37;
    }
    v8 = -2147418113;
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    v24 = 834569;
    v25 = 2147942414LL;
LABEL_37:
    v8 = bidTraceHR(off_180260758[0], v24, v25);
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_39:
  VariantClear(&v29.vValue);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18013b824  push    rbx
0x18013b826  push    rbp
0x18013b827  push    rsi
0x18013b828  push    rdi
0x18013b829  push    r12
0x18013b82b  push    r13
0x18013b82d  push    r14
0x18013b82f  push    r15
0x18013b831  sub     rsp, 98h
0x18013b838  mov     rax, cs:__security_cookie
0x18013b83f  xor     rax, rsp
0x18013b842  mov     [rsp+0D8h+var_58], rax
0x18013b84a  mov     rbp, r8
0x18013b84d  mov     ebx, edx
0x18013b84f  mov     rdi, rcx
0x18013b852  xor     esi, esi
0x18013b854  xor     edx, edx; Val
0x18013b856  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18013b85b  mov     r13, r9
0x18013b85e  lea     r8d, [rsi+48h]; Size
0x18013b862  call    memset_0
0x18013b867  mov     rcx, [rdi+30h]
0x18013b86b  lea     r14, [rbx+rbx*2]
0x18013b86f  xor     edx, edx
0x18013b871  mov     [rsp+0D8h+var_B0], r14
0x18013b876  mov     [rsp+0D8h+var_B8], rcx
0x18013b87b  mov     r15d, edx
0x18013b87e  cmp     [rcx+r14*8], edx
0x18013b882  jbe     loc_18013BA59
0x18013b888  mov     r12, [rsp+0D8h+arg_20]
0x18013b890  mov     rdi, [rcx+r14*8+10h]
0x18013b895  mov     eax, r15d
0x18013b898  imul    rbx, rax, 38h ; '8'
0x18013b89c  mov     eax, [rbx+rdi]
0x18013b89f  mov     [rbx+rbp], eax
0x18013b8a2  mov     eax, [rbx+rdi+0Ch]
0x18013b8a6  mov     [rbx+rbp+0Ch], eax
0x18013b8aa  mov     eax, [rbx+rdi+10h]
0x18013b8ae  mov     [rbx+rbp+10h], eax
0x18013b8b2  mov     eax, [rbx+rdi+4]
0x18013b8b6  mov     [rbx+rbp+4], eax
0x18013b8ba  mov     eax, [rbx+rdi+8]
0x18013b8be  mov     [rbx+rbp+8], eax
0x18013b8c2  cmp     [rbx+rdi+18h], rdx
0x18013b8c7  jz      loc_18013B972
0x18013b8cd  mov     rcx, r13; this
0x18013b8d0  mov     dword ptr [r13+14h], 1
0x18013b8d8  add     r13, 18h
0x18013b8dc  test    rcx, rcx
0x18013b8df  jz      short loc_18013B8E8
0x18013b8e1  call    ??0CEXAutoBackupFile@@QEAA@XZ; CEXAutoBackupFile::CEXAutoBackupFile(void)
0x18013b8e6  jmp     short loc_18013B8EB
0x18013b8e8  mov     rax, rdx
0x18013b8eb  mov     [rbx+rbp+18h], rax
0x18013b8f0  test    rax, rax
0x18013b8f3  jz      loc_18013BA30
0x18013b8f9  mov     rcx, [rbx+rdi+18h]
0x18013b8fe  mov     r14d, 1
0x18013b904  mov     rax, [rcx]
0x18013b907  mov     [rcx+8], rax
0x18013b90b  test    r12, r12
0x18013b90e  jz      loc_18013BA13
0x18013b914  mov     rcx, [rbx+rdi+18h]; this
0x18013b919  lea     r9, [rsp+0D8h+var_A8.vValue]; struct tagVARIANT *
0x18013b91e  lea     r8, [rsp+0D8h+var_A8.colid]; struct tagDBID *
0x18013b923  lea     rdx, [rsp+0D8h+var_A8.dwOptions]; unsigned int *
0x18013b928  call    ?GetNextValue@CColumnIds@@QEAAJPEAKPEAUtagDBID@@PEAUtagVARIANT@@@Z; CColumnIds::GetNextValue(ulong *,tagDBID *,tagVARIANT *)
0x18013b92d  mov     esi, eax
0x18013b92f  test    eax, eax
0x18013b931  js      loc_18013BA59
0x18013b937  xor     ecx, ecx
0x18013b939  lea     rdx, [rsp+0D8h+var_A8]; struct tagDBPROP *
0x18013b93e  cmp     eax, 1
0x18013b941  cmovnz  ecx, r14d
0x18013b945  mov     r14d, ecx
0x18013b948  mov     rcx, [rbx+rbp+18h]; this
0x18013b94d  call    ?AddColumnId@CColumnIds@@QEAAJPEAUtagDBPROP@@@Z; CColumnIds::AddColumnId(tagDBPROP *)
0x18013b952  xor     edx, edx
0x18013b954  mov     esi, eax
0x18013b956  test    eax, eax
0x18013b958  js      loc_18013BA59
0x18013b95e  dec     r12
0x18013b961  test    r14d, r14d
0x18013b964  jnz     short loc_18013B90B
0x18013b966  mov     r14, [rsp+0D8h+var_B0]
0x18013b96b  mov     rcx, [rsp+0D8h+var_B8]
0x18013b970  jmp     short loc_18013B977
0x18013b972  mov     [rbx+rbp+18h], rdx
0x18013b977  lea     rax, [rbx+rdi]
0x18013b97b  cmp     [rax+20h], dx
0x18013b97f  jz      short loc_18013B9E5
0x18013b981  cmp     word ptr [rax+20h], 3
0x18013b986  jz      short loc_18013B9C6
0x18013b988  cmp     word ptr [rax+20h], 8
0x18013b98d  jz      short loc_18013B9BF
0x18013b98f  cmp     word ptr [rax+20h], 0Bh
0x18013b994  jz      short loc_18013B9C6
0x18013b996  cmp     word ptr [rax+20h], 14h
0x18013b99b  jz      short loc_18013B9C6
0x18013b99d  lea     rcx, [rbp+20h]
0x18013b9a1  add     rcx, rbx; pvargDest
0x18013b9a4  mov     [rcx], dx
0x18013b9a7  lea     rdx, [rax+20h]; pvargSrc
0x18013b9ab  call    cs:__imp_VariantCopy
0x18013b9b1  xor     edx, edx
0x18013b9b3  mov     esi, eax
0x18013b9b5  test    eax, eax
0x18013b9b7  js      loc_18013BA59
0x18013b9bd  jmp     short loc_18013B9FF
0x18013b9bf  cmp     [rbx+rdi+28h], rdx
0x18013b9c4  jnz     short loc_18013B99D
0x18013b9c6  lea     rcx, [rbp+20h]
0x18013b9ca  add     rcx, rbx
0x18013b9cd  jnz     short loc_18013B9EE
0x18013b9cf  call    cs:__imp__errno
0x18013b9d5  mov     dword ptr [rax], 16h
0x18013b9db  call    cs:__imp__invalid_parameter_noinfo
0x18013b9e1  xor     edx, edx
0x18013b9e3  jmp     short loc_18013B9FF
0x18013b9e5  cmp     [rbx+rbp+20h], dx
0x18013b9ea  jz      short loc_18013BA04
0x18013b9ec  jmp     short loc_18013B9C6
0x18013b9ee  movups  xmm0, xmmword ptr [rax+20h]
0x18013b9f2  movups  xmmword ptr [rcx], xmm0
0x18013b9f5  movsd   xmm1, qword ptr [rax+30h]
0x18013b9fa  movsd   qword ptr [rcx+10h], xmm1
0x18013b9ff  mov     rcx, [rsp+0D8h+var_B8]
0x18013ba04  inc     r15d
0x18013ba07  cmp     r15d, [rcx+r14*8]
0x18013ba0b  jb      loc_18013B890
0x18013ba11  jmp     short loc_18013BA59
0x18013ba13  test    byte ptr cs:_bidGblFlags, 2
0x18013ba1a  jz      short loc_18013BA29
0x18013ba1c  mov     edx, 0C5C09h
0x18013ba21  mov     r8d, 8000FFFFh
0x18013ba27  jmp     short loc_18013BA44
0x18013ba29  mov     esi, 8000FFFFh
0x18013ba2e  jmp     short loc_18013BA59
0x18013ba30  test    byte ptr cs:_bidGblFlags, 2
0x18013ba37  jz      short loc_18013BA54
0x18013ba39  mov     edx, 0CBC09h
0x18013ba3e  mov     r8d, 8007000Eh
0x18013ba44  mov     rcx, cs:off_180260758; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ms"...
0x18013ba4b  call    _bidTraceHR
0x18013ba50  mov     esi, eax
0x18013ba52  jmp     short loc_18013BA59
0x18013ba54  mov     esi, 8007000Eh
0x18013ba59  lea     rcx, [rsp+0D8h+var_A8.vValue]; pvarg
0x18013ba5e  call    cs:__imp_VariantClear
0x18013ba64  mov     eax, esi
0x18013ba66  mov     rcx, [rsp+0D8h+var_58]
0x18013ba6e  xor     rcx, rsp; StackCookie
0x18013ba71  call    __security_check_cookie
0x18013ba76  add     rsp, 98h
0x18013ba7d  pop     r15
0x18013ba7f  pop     r14
0x18013ba81  pop     r13
0x18013ba83  pop     r12
0x18013ba85  pop     rdi
0x18013ba86  pop     rsi
0x18013ba87  pop     rbp
0x18013ba88  pop     rbx
0x18013ba89  retn
```
