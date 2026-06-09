# CCertEncodeAltName::_Cleanup(void)

- ea: `0x1800035e0`
- end: `0x1800036c3`
- name: `?_Cleanup@CCertEncodeAltName@@AEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CCertEncodeAltName *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002acc`
- `0x180002b10`
- `0x180003240`

## callees

- `0x1800035e0`
- `0x1800036cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000366f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000368e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003610`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000366f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000368e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036a1`

## pseudocode

```c
void __fastcall CCertEncodeAltName::_Cleanup(CCertEncodeAltName *this)
{
  unsigned int *v1; // rbx
  void *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int *v6; // rbp
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 *v10; // rsi
  __int64 v11; // r15

  v1 = (unsigned int *)*((_QWORD *)this + 8);
  if ( !v1 )
    goto LABEL_24;
  if ( *((_DWORD *)this + 23) )
  {
    v4 = *((int *)this + 18);
    v5 = 3 * v4;
    v6 = &v1[6 * v4];
    while ( 1 )
    {
      if ( v1 >= v6 )
      {
        LocalFree(*((HLOCAL *)this + 8));
        goto LABEL_23;
      }
      v7 = CCertEncodeAltName::_NameType(v5, *v1) - 1;
      if ( v7 && (v8 = v7 - 1) != 0 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 != 1 )
            goto LABEL_20;
          v10 = (__int64 *)(v1 + 2);
          v11 = *((_QWORD *)v1 + 1);
          if ( v11 )
          {
            if ( *(_QWORD *)v11 )
              LocalFree(*(HLOCAL *)v11);
            v5 = *(_QWORD *)(v11 + 16);
            if ( v5 )
              LocalFree((HLOCAL)v5);
          }
        }
        else
        {
          v10 = (__int64 *)(v1 + 4);
        }
      }
      else
      {
        v10 = (__int64 *)(v1 + 2);
      }
      if ( v10 )
      {
        v5 = *v10;
        if ( *v10 )
          LocalFree((HLOCAL)v5);
      }
LABEL_20:
      v1 += 6;
    }
  }
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 10) = 0;
  }
LABEL_23:
  *((_QWORD *)this + 8) = 0;
LABEL_24:
  *((_DWORD *)this + 23) = 0;
}

```

## disassembly

```asm
0x1800035e0  push    rbx
0x1800035e2  push    rbp
0x1800035e3  push    rsi
0x1800035e4  push    rdi
0x1800035e5  push    r14
0x1800035e7  push    r15
0x1800035e9  sub     rsp, 28h
0x1800035ed  mov     rbx, [rcx+40h]
0x1800035f1  mov     rdi, rcx
0x1800035f4  test    rbx, rbx
0x1800035f7  jz      loc_1800036AF
0x1800035fd  cmp     dword ptr [rcx+5Ch], 0
0x180003601  jnz     short loc_180003623
0x180003603  mov     rcx, [rcx+50h]; hMem
0x180003607  test    rcx, rcx
0x18000360a  jz      loc_1800036A7
0x180003610  call    cs:__imp_LocalFree
0x180003616  mov     qword ptr [rdi+50h], 0
0x18000361e  jmp     loc_1800036A7
0x180003623  movsxd  rax, dword ptr [rcx+48h]
0x180003627  lea     rcx, [rax+rax*2]
0x18000362b  lea     rbp, [rbx+rcx*8]
0x18000362f  jmp     short loc_180003698
0x180003631  mov     edx, [rbx]
0x180003633  call    ?_NameType@CCertEncodeAltName@@AEAA?AW4_enumNameType@1@K@Z; CCertEncodeAltName::_NameType(ulong)
0x180003638  sub     eax, 1
0x18000363b  jz      short loc_18000367D
0x18000363d  sub     eax, 1
0x180003640  jz      short loc_18000367D
0x180003642  sub     eax, 1
0x180003645  jz      short loc_180003677
0x180003647  cmp     eax, 1
0x18000364a  jnz     short loc_180003694
0x18000364c  lea     rsi, [rbx+8]
0x180003650  mov     r15, [rsi]
0x180003653  test    r15, r15
0x180003656  jz      short loc_180003681
0x180003658  mov     rcx, [r15]; hMem
0x18000365b  test    rcx, rcx
0x18000365e  jz      short loc_180003666
0x180003660  call    cs:__imp_LocalFree
0x180003666  mov     rcx, [r15+10h]; hMem
0x18000366a  test    rcx, rcx
0x18000366d  jz      short loc_180003681
0x18000366f  call    cs:__imp_LocalFree
0x180003675  jmp     short loc_180003681
0x180003677  lea     rsi, [rbx+10h]
0x18000367b  jmp     short loc_180003681
0x18000367d  lea     rsi, [rbx+8]
0x180003681  test    rsi, rsi
0x180003684  jz      short loc_180003694
0x180003686  mov     rcx, [rsi]; hMem
0x180003689  test    rcx, rcx
0x18000368c  jz      short loc_180003694
0x18000368e  call    cs:__imp_LocalFree
0x180003694  add     rbx, 18h
0x180003698  cmp     rbx, rbp
0x18000369b  jb      short loc_180003631
0x18000369d  mov     rcx, [rdi+40h]; hMem
0x1800036a1  call    cs:__imp_LocalFree
0x1800036a7  mov     qword ptr [rdi+40h], 0
0x1800036af  mov     dword ptr [rdi+5Ch], 0
0x1800036b6  add     rsp, 28h
0x1800036ba  pop     r15
0x1800036bc  pop     r14
0x1800036be  pop     rdi
0x1800036bf  pop     rsi
0x1800036c0  pop     rbp
0x1800036c1  pop     rbx
0x1800036c2  retn
```
