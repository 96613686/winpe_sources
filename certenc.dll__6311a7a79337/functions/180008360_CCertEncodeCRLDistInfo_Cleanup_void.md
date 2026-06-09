# CCertEncodeCRLDistInfo::_Cleanup(void)

- ea: `0x180008360`
- end: `0x18000840c`
- name: `?_Cleanup@CCertEncodeCRLDistInfo@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(CCertEncodeCRLDistInfo *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a20`
- `0x180007a70`
- `0x1800080b0`

## callees

- `0x180008360`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083ea`

## pseudocode

```c
void __fastcall CCertEncodeCRLDistInfo::_Cleanup(CCertEncodeCRLDistInfo *this)
{
  unsigned __int64 v1; // rbx
  void *v3; // rcx
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r15
  void *v7; // rcx

  v1 = *((_QWORD *)this + 8);
  if ( v1 )
  {
    if ( *((_DWORD *)this + 22) )
    {
      v4 = v1 + ((__int64)*((int *)this + 18) << 6);
      while ( v1 < v4 )
      {
        v5 = *(_QWORD *)(v1 + 16);
        if ( v5 )
        {
          v6 = v5 + 24LL * *(unsigned int *)(v1 + 8);
          while ( v5 < v6 )
          {
            v7 = *(void **)(v5 + 8);
            if ( v7 )
              LocalFree(v7);
            v5 += 24LL;
          }
          LocalFree(*(HLOCAL *)(v1 + 16));
        }
        v1 += 64LL;
      }
      LocalFree(*((HLOCAL *)this + 8));
    }
    else
    {
      v3 = (void *)*((_QWORD *)this + 10);
      if ( v3 )
      {
        LocalFree(v3);
        *((_QWORD *)this + 10) = 0;
      }
    }
    *((_QWORD *)this + 8) = 0;
  }
  *((_DWORD *)this + 22) = 0;
}

```

## disassembly

```asm
0x180008360  push    rbx
0x180008362  push    rbp
0x180008363  push    rsi
0x180008364  push    rdi
0x180008365  push    r14
0x180008367  push    r15
0x180008369  sub     rsp, 28h
0x18000836d  mov     rbx, [rcx+40h]
0x180008371  mov     rdi, rcx
0x180008374  test    rbx, rbx
0x180008377  jz      short loc_1800083F8
0x180008379  cmp     dword ptr [rcx+58h], 0
0x18000837d  jnz     short loc_180008398
0x18000837f  mov     rcx, [rcx+50h]; hMem
0x180008383  test    rcx, rcx
0x180008386  jz      short loc_1800083F0
0x180008388  call    cs:__imp_LocalFree
0x18000838e  mov     qword ptr [rdi+50h], 0
0x180008396  jmp     short loc_1800083F0
0x180008398  movsxd  rbp, dword ptr [rcx+48h]
0x18000839c  shl     rbp, 6
0x1800083a0  add     rbp, rbx
0x1800083a3  jmp     short loc_1800083E1
0x1800083a5  mov     rsi, [rbx+10h]
0x1800083a9  test    rsi, rsi
0x1800083ac  jz      short loc_1800083DD
0x1800083ae  mov     eax, [rbx+8]
0x1800083b1  lea     rcx, [rax+rax*2]
0x1800083b5  lea     r15, [rsi+rcx*8]
0x1800083b9  jmp     short loc_1800083CE
0x1800083bb  mov     rcx, [rsi+8]; hMem
0x1800083bf  test    rcx, rcx
0x1800083c2  jz      short loc_1800083CA
0x1800083c4  call    cs:__imp_LocalFree
0x1800083ca  add     rsi, 18h
0x1800083ce  cmp     rsi, r15
0x1800083d1  jb      short loc_1800083BB
0x1800083d3  mov     rcx, [rbx+10h]; hMem
0x1800083d7  call    cs:__imp_LocalFree
0x1800083dd  add     rbx, 40h ; '@'
0x1800083e1  cmp     rbx, rbp
0x1800083e4  jb      short loc_1800083A5
0x1800083e6  mov     rcx, [rdi+40h]; hMem
0x1800083ea  call    cs:__imp_LocalFree
0x1800083f0  mov     qword ptr [rdi+40h], 0
0x1800083f8  mov     dword ptr [rdi+58h], 0
0x1800083ff  add     rsp, 28h
0x180008403  pop     r15
0x180008405  pop     r14
0x180008407  pop     rdi
0x180008408  pop     rsi
0x180008409  pop     rbp
0x18000840a  pop     rbx
0x18000840b  retn
```
