# CSLTAudit::GenerateValueString(ushort const *,ulong,ulong,void *,ushort * *,int)

- ea: `0x180022d20`
- end: `0x180022e57`
- name: `?GenerateValueString@CSLTAudit@@EEAAJPEBGKKPEAXPEAPEAGH@Z`
- size: `311`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000717c`
- `0x180022d20`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022de8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::GenerateValueString(
        CSLTAudit *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        unsigned __int16 **a6,
        int a7)
{
  unsigned __int16 **v8; // rsi
  __int64 v9; // rbx
  __int64 result; // rax
  unsigned __int16 *v11; // rdi
  int v12; // ebx
  __int64 v13; // rax
  unsigned __int64 v14; // rbx
  LPVOID pv; // [rsp+80h] [rbp+8h] BYREF

  pv = 0;
  v8 = a6;
  *a6 = 0;
  LODWORD(a6) = 0;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  result = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, void *, LPVOID *, int, unsigned __int16 ***))(*(_QWORD *)this + 112LL))(
             this,
             a3,
             a4,
             a5,
             &pv,
             a7,
             &a6);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)a6 )
    {
      v11 = 0;
      v12 = 0;
    }
    else
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      v14 = v13 + 8 + v9;
      v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v14, 2u));
      if ( v11 )
        v12 = StringCchPrintfW(v11, v14, L"%s = %s", a2, pv);
      else
        v12 = -2147024882;
    }
    CoTaskMemFree(pv);
    if ( v12 < 0 && v11 )
      CoTaskMemFree(v11);
    else
      *v8 = v11;
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x180022d20  mov     rax, rsp
0x180022d23  push    rbx
0x180022d24  push    rbp
0x180022d25  push    rsi
0x180022d26  push    rdi
0x180022d27  push    r14
0x180022d29  push    r15
0x180022d2b  sub     rsp, 48h
0x180022d2f  mov     r11d, r9d
0x180022d32  mov     edi, r8d
0x180022d35  mov     rbp, rdx
0x180022d38  mov     r10, rcx
0x180022d3b  xor     r14d, r14d
0x180022d3e  mov     [rax+8], r14
0x180022d42  mov     rsi, [rsp+78h+arg_28]
0x180022d4a  mov     [rsi], r14
0x180022d4d  mov     [rax+30h], r14d
0x180022d51  or      r15, 0FFFFFFFFFFFFFFFFh
0x180022d55  mov     rbx, r15
0x180022d58  inc     rbx
0x180022d5b  cmp     [rdx+rbx*2], r14w
0x180022d60  jnz     short loc_180022D58
0x180022d62  mov     rax, [rcx]
0x180022d65  lea     rcx, [rsp+78h+arg_28]
0x180022d6d  mov     [rsp+78h+var_48], rcx
0x180022d72  mov     ecx, [rsp+78h+arg_30]
0x180022d79  mov     [rsp+78h+var_50], ecx
0x180022d7d  lea     rcx, [rsp+78h+pv]
0x180022d85  mov     [rsp+78h+var_58], rcx
0x180022d8a  mov     r9, [rsp+78h+arg_20]
0x180022d92  mov     r8d, r11d
0x180022d95  mov     edx, edi
0x180022d97  mov     rcx, r10
0x180022d9a  mov     rax, [rax+70h]
0x180022d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022da3  test    eax, eax
0x180022da5  js      loc_180022E4A
0x180022dab  cmp     dword ptr [rsp+78h+arg_28], r14d
0x180022db3  jz      short loc_180022DBD
0x180022db5  mov     rdi, r14
0x180022db8  mov     ebx, r14d
0x180022dbb  jmp     short loc_180022E21
0x180022dbd  mov     rcx, [rsp+78h+pv]
0x180022dc5  mov     rax, r15
0x180022dc8  inc     rax
0x180022dcb  cmp     [rcx+rax*2], r14w
0x180022dd0  jnz     short loc_180022DC8
0x180022dd2  add     rax, 8
0x180022dd6  add     rbx, rax
0x180022dd9  mov     eax, 2
0x180022dde  mul     rbx
0x180022de1  cmovb   rax, r15
0x180022de5  mov     rcx, rax; cb
0x180022de8  call    cs:__imp_CoTaskMemAlloc
0x180022dee  mov     rdi, rax
0x180022df1  test    rax, rax
0x180022df4  jnz     short loc_180022DFD
0x180022df6  mov     ebx, 8007000Eh
0x180022dfb  jmp     short loc_180022E21
0x180022dfd  mov     rax, [rsp+78h+pv]
0x180022e05  mov     [rsp+78h+var_58], rax
0x180022e0a  mov     r9, rbp
0x180022e0d  lea     r8, aSS; "%s = %s"
0x180022e14  mov     rdx, rbx; unsigned __int64
0x180022e17  mov     rcx, rdi; unsigned __int16 *
0x180022e1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022e1f  mov     ebx, eax
0x180022e21  mov     rcx, [rsp+78h+pv]; pv
0x180022e29  call    cs:__imp_CoTaskMemFree
0x180022e2f  nop
0x180022e30  test    ebx, ebx
0x180022e32  jns     short loc_180022E45
0x180022e34  test    rdi, rdi
0x180022e37  jz      short loc_180022E45
0x180022e39  mov     rcx, rdi; pv
0x180022e3c  call    cs:__imp_CoTaskMemFree
0x180022e42  nop
0x180022e43  jmp     short loc_180022E48
0x180022e45  mov     [rsi], rdi
0x180022e48  mov     eax, ebx
0x180022e4a  add     rsp, 48h
0x180022e4e  pop     r15
0x180022e50  pop     r14
0x180022e52  pop     rdi
0x180022e53  pop     rsi
0x180022e54  pop     rbp
0x180022e55  pop     rbx
0x180022e56  retn
```
