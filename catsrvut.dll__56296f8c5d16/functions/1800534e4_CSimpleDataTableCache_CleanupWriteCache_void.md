# CSimpleDataTableCache::CleanupWriteCache(void)

- ea: `0x1800534e4`
- end: `0x18005357c`
- name: `?CleanupWriteCache@CSimpleDataTableCache@@IEAAXXZ`
- size: `152`
- prototype: `void __fastcall(CSimpleDataTableCache *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800533a0`
- `0x180053ae8`
- `0x180054270`
- `0x1800542b8`

## callees

- `0x1800534e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005350e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005353f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005350e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005353f`

## pseudocode

```c
void __fastcall CSimpleDataTableCache::CleanupWriteCache(CSimpleDataTableCache *this)
{
  int v1; // eax
  int *v2; // rdi
  int v4; // ecx
  void *v5; // rcx
  void *v6; // rcx

  v1 = *(_DWORD *)this;
  v2 = (int *)((char *)this + 40);
  if ( (*(_DWORD *)this & 0x40000) != 0 || (v4 = *v2, (*v2 & 0x20000) == 0) )
  {
    v5 = (void *)*((_QWORD *)this + 11);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      v1 = *(_DWORD *)this;
      *((_QWORD *)this + 11) = 0;
    }
    *v2 &= ~0x20000u;
    v4 = *v2;
  }
  if ( (v4 & 0x200000) == 0 || (v1 & 0x40000) != 0 )
  {
    v6 = (void *)*((_QWORD *)this + 13);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *((_QWORD *)this + 13) = 0;
    }
    *v2 &= ~0x200000u;
  }
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
}

```

## disassembly

```asm
0x1800534e4  mov     [rsp+arg_0], rbx
0x1800534e9  push    rdi
0x1800534ea  sub     rsp, 20h
0x1800534ee  mov     eax, [rcx]
0x1800534f0  lea     rdi, [rcx+28h]
0x1800534f4  mov     rbx, rcx
0x1800534f7  bt      eax, 12h
0x1800534fb  jb      short loc_180053505
0x1800534fd  mov     ecx, [rdi]
0x1800534ff  bt      ecx, 11h
0x180053503  jb      short loc_180053524
0x180053505  mov     rcx, [rbx+58h]; pv
0x180053509  test    rcx, rcx
0x18005350c  jz      short loc_18005351E
0x18005350e  call    cs:__imp_CoTaskMemFree
0x180053514  mov     eax, [rbx]
0x180053516  mov     qword ptr [rbx+58h], 0
0x18005351e  btr     dword ptr [rdi], 11h
0x180053522  mov     ecx, [rdi]
0x180053524  bt      ecx, 15h
0x180053528  setb    cl
0x18005352b  bt      eax, 12h
0x18005352f  setnb   al
0x180053532  test    al, cl
0x180053534  jnz     short loc_180053551
0x180053536  mov     rcx, [rbx+68h]; pv
0x18005353a  test    rcx, rcx
0x18005353d  jz      short loc_18005354D
0x18005353f  call    cs:__imp_CoTaskMemFree
0x180053545  mov     qword ptr [rbx+68h], 0
0x18005354d  btr     dword ptr [rdi], 15h
0x180053551  mov     qword ptr [rbx+50h], 0
0x180053559  mov     qword ptr [rbx+60h], 0
0x180053561  mov     qword ptr [rbx+58h], 0
0x180053569  mov     qword ptr [rbx+68h], 0
0x180053571  mov     rbx, [rsp+28h+arg_0]
0x180053576  add     rsp, 20h
0x18005357a  pop     rdi
0x18005357b  retn
```
