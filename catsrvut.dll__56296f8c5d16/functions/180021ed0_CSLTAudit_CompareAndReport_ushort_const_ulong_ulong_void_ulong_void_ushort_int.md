# CSLTAudit::CompareAndReport(ushort const *,ulong,ulong,void *,ulong,void *,ushort * *,int)

- ea: `0x180021ed0`
- end: `0x1800220ad`
- name: `?CompareAndReport@CSLTAudit@@EEAAJPEBGKKPEAXK1PEAPEAGH@Z`
- size: `477`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int, void *, unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000717c`
- `0x180021ed0`
- `0x18002318c`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022009`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::CompareAndReport(
        CSLTAudit *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        void *a7,
        unsigned __int16 **a8,
        int a9)
{
  unsigned __int16 *v12; // rbx
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // rdi
  unsigned __int16 *v18; // rax
  LPVOID pv; // [rsp+40h] [rbp-58h] BYREF
  LPVOID v21[10]; // [rsp+48h] [rbp-50h] BYREF

  v12 = 0;
  *a8 = 0;
  v13 = 0;
  pv = 0;
  v21[0] = 0;
  if ( CSLTAudit::MatchValues(this, (unsigned int)a2, a3, a4, a6, a5, a7) == 1 )
  {
    v13 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, void *, LPVOID *, int, _QWORD))(*(_QWORD *)this + 112LL))(
            this,
            a3,
            a4,
            a5,
            &pv,
            a9,
            0);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, _QWORD, void *, LPVOID *, int, _QWORD))(*(_QWORD *)this
                                                                                                  + 112LL))(
              this,
              a3,
              a6,
              a7,
              v21,
              a9,
              0);
      if ( v13 >= 0 )
      {
        v14 = -1;
        do
          ++v14;
        while ( a2[v14] );
        v15 = -1;
        do
          ++v15;
        while ( *((_WORD *)pv + v15) );
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v21[0] + v16) );
        v17 = v16 + 18 + v15 + v14;
        v18 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v17, 2u));
        v12 = v18;
        if ( v18 )
        {
          memset_0(v18, 0, 2 * v17);
          v13 = StringCchPrintfW(v12, v17, L"%s = '%s' -> '%s'", a2, pv, v21[0]);
          if ( v13 >= 0 )
          {
            *a8 = v12;
            v12 = 0;
          }
        }
        else
        {
          v13 = -2147024882;
        }
      }
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v21[0] )
      CoTaskMemFree(v21[0]);
    if ( v12 )
      CoTaskMemFree(v12);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180021ed0  mov     r11, rsp
0x180021ed3  mov     [r11+10h], rdx
0x180021ed7  push    rbx
0x180021ed8  push    rbp
0x180021ed9  push    rsi
0x180021eda  push    rdi
0x180021edb  push    r12
0x180021edd  push    r13
0x180021edf  push    r14
0x180021ee1  push    r15
0x180021ee3  sub     rsp, 58h
0x180021ee7  mov     r14d, r9d
0x180021eea  mov     ebp, r8d
0x180021eed  mov     rsi, rcx
0x180021ef0  xor     ebx, ebx
0x180021ef2  mov     rax, [rsp+98h+arg_38]
0x180021efa  mov     [rax], rbx
0x180021efd  mov     edi, ebx
0x180021eff  mov     [r11-58h], rbx
0x180021f03  mov     [r11-50h], rbx
0x180021f07  mov     r12, [rsp+98h+arg_30]
0x180021f0f  mov     [r11-68h], r12
0x180021f13  mov     r15, [rsp+98h+arg_20]
0x180021f1b  mov     [r11-70h], r15
0x180021f1f  mov     r13d, [rsp+98h+arg_28]
0x180021f27  mov     [r11-78h], r13d
0x180021f2b  call    ?MatchValues@CSLTAudit@@AEAAHKKKKPEBX0@Z; CSLTAudit::MatchValues(ulong,ulong,ulong,ulong,void const *,void const *)
0x180021f30  cmp     eax, 1
0x180021f33  jnz     loc_18002209A
0x180021f39  mov     rax, [rsi]
0x180021f3c  mov     [rsp+98h+var_68], rbx
0x180021f41  mov     ecx, [rsp+98h+arg_40]
0x180021f48  mov     dword ptr [rsp+98h+var_70], ecx
0x180021f4c  lea     rcx, [rsp+98h+pv]
0x180021f51  mov     [rsp+98h+var_78], rcx
0x180021f56  mov     r9, r15
0x180021f59  mov     r8d, r14d
0x180021f5c  mov     edx, ebp
0x180021f5e  mov     rcx, rsi
0x180021f61  mov     rax, [rax+70h]
0x180021f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f6a  mov     edi, eax
0x180021f6c  xor     r14d, r14d
0x180021f6f  test    eax, eax
0x180021f71  js      loc_180022069
0x180021f77  mov     rax, [rsi]
0x180021f7a  mov     [rsp+98h+var_68], r14
0x180021f7f  mov     ecx, [rsp+98h+arg_40]
0x180021f86  mov     dword ptr [rsp+98h+var_70], ecx
0x180021f8a  lea     rcx, [rsp+98h+var_50]
0x180021f8f  mov     [rsp+98h+var_78], rcx
0x180021f94  mov     r9, r12
0x180021f97  mov     r8d, r13d
0x180021f9a  mov     edx, ebp
0x180021f9c  mov     rcx, rsi
0x180021f9f  mov     rax, [rax+70h]
0x180021fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa8  mov     edi, eax
0x180021faa  test    eax, eax
0x180021fac  js      loc_180022069
0x180021fb2  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021fb6  mov     rax, r9
0x180021fb9  mov     rsi, [rsp+98h+arg_8]
0x180021fc1  inc     rax
0x180021fc4  cmp     [rsi+rax*2], r14w
0x180021fc9  jnz     short loc_180021FC1
0x180021fcb  mov     rcx, [rsp+98h+pv]
0x180021fd0  mov     rdx, r9
0x180021fd3  inc     rdx
0x180021fd6  cmp     [rcx+rdx*2], r14w
0x180021fdb  jnz     short loc_180021FD3
0x180021fdd  mov     r8, [rsp+98h+var_50]
0x180021fe2  mov     rcx, r9
0x180021fe5  inc     rcx
0x180021fe8  cmp     [r8+rcx*2], r14w
0x180021fed  jnz     short loc_180021FE5
0x180021fef  lea     rdi, [rdx+rax]
0x180021ff3  add     rcx, 12h
0x180021ff7  add     rdi, rcx
0x180021ffa  mov     eax, 2
0x180021fff  mul     rdi
0x180022002  cmovb   rax, r9
0x180022006  mov     rcx, rax; cb
0x180022009  call    cs:__imp_CoTaskMemAlloc
0x18002200f  mov     rbx, rax
0x180022012  test    rax, rax
0x180022015  jnz     short loc_18002201E
0x180022017  mov     edi, 8007000Eh
0x18002201c  jmp     short loc_180022069
0x18002201e  lea     r8, [rdi+rdi]; Size
0x180022022  xor     edx, edx; Val
0x180022024  mov     rcx, rbx; void *
0x180022027  call    memset_0
0x18002202c  mov     rax, [rsp+98h+var_50]
0x180022031  mov     [rsp+98h+var_70], rax
0x180022036  mov     rax, [rsp+98h+pv]
0x18002203b  mov     [rsp+98h+var_78], rax
0x180022040  mov     r9, rsi
0x180022043  lea     r8, aSSS; "%s = '%s' -> '%s'"
0x18002204a  mov     rdx, rdi; unsigned __int64
0x18002204d  mov     rcx, rbx; unsigned __int16 *
0x180022050  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022055  mov     edi, eax
0x180022057  test    eax, eax
0x180022059  js      short loc_180022069
0x18002205b  mov     rax, [rsp+98h+arg_38]
0x180022063  mov     [rax], rbx
0x180022066  mov     rbx, r14
0x180022069  mov     rcx, [rsp+98h+pv]; pv
0x18002206e  test    rcx, rcx
0x180022071  jz      short loc_18002207A
0x180022073  call    cs:__imp_CoTaskMemFree
0x180022079  nop
0x18002207a  mov     rcx, [rsp+98h+var_50]; pv
0x18002207f  test    rcx, rcx
0x180022082  jz      short loc_18002208B
0x180022084  call    cs:__imp_CoTaskMemFree
0x18002208a  nop
0x18002208b  test    rbx, rbx
0x18002208e  jz      short loc_18002209A
0x180022090  mov     rcx, rbx; pv
0x180022093  call    cs:__imp_CoTaskMemFree
0x180022099  nop
0x18002209a  mov     eax, edi
0x18002209c  add     rsp, 58h
0x1800220a0  pop     r15
0x1800220a2  pop     r14
0x1800220a4  pop     r13
0x1800220a6  pop     r12
0x1800220a8  pop     rdi
0x1800220a9  pop     rsi
0x1800220aa  pop     rbp
0x1800220ab  pop     rbx
0x1800220ac  retn
```
