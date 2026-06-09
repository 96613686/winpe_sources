# Dfdll::CVariantBufferBase::CopyFrom(tagVARIANT const *,uint,uint)

- ea: `0x1800028c0`
- end: `0x180002986`
- name: `?CopyFrom@CVariantBufferBase@Dfdll@@MEAAJPEBUtagVARIANT@@II@Z`
- size: `198`
- prototype: `__int64 __fastcall(Dfdll::CVariantBufferBase *__hidden this, const struct tagVARIANT *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800028c0`
- `0x18001efd0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180002955`
- `OLEAUT32!__imp_VariantCopy` at `0x180002955`

## pseudocode

```c
HRESULT __fastcall Dfdll::CVariantBufferBase::CopyFrom(
        Dfdll::CVariantBufferBase *this,
        const struct tagVARIANT *a2,
        unsigned int a3,
        unsigned int a4)
{
  HRESULT result; // eax
  unsigned int v7; // eax
  __int64 v8; // rax
  __int64 v9; // r15
  __int64 v10; // rsi
  const struct tagVARIANT *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147024809;
  v7 = *((_DWORD *)this + 4);
  if ( a3 >= v7 || v7 - a3 < a4 )
    return -2147024809;
  v8 = *(_QWORD *)this;
  v13 = 0;
  result = (*(__int64 (__fastcall **)(Dfdll::CVariantBufferBase *, _QWORD, __int64 *))(v8 + 64))(this, a3, &v13);
  if ( result >= 0 )
  {
    v9 = v13;
    v10 = 0;
    if ( a4 )
    {
      v11 = a2;
      v12 = v13;
      do
      {
        if ( v11->vt != 8 || v11->llVal )
        {
          result = VariantCopy((VARIANTARG *)(v9 + 24 * v10), &a2[v10]);
          if ( result < 0 )
            return result;
        }
        else
        {
          *(_QWORD *)(v12 + 8) = 0;
          *(_WORD *)v12 = 8;
        }
        v10 = (unsigned int)(v10 + 1);
        ++v11;
        v12 += 24;
      }
      while ( (unsigned int)v10 < a4 );
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  mov     [rsp+arg_10], rbp
0x1800028ca  push    rsi
0x1800028cb  push    rdi
0x1800028cc  push    r13
0x1800028ce  push    r14
0x1800028d0  push    r15
0x1800028d2  sub     rsp, 20h
0x1800028d6  mov     ebp, r9d
0x1800028d9  mov     r10d, r8d
0x1800028dc  mov     r14, rdx
0x1800028df  test    rdx, rdx
0x1800028e2  jnz     short loc_1800028EE
0x1800028e4  mov     eax, 80070057h
0x1800028e9  jmp     loc_18000296F
0x1800028ee  mov     eax, [rcx+10h]
0x1800028f1  cmp     r10d, eax
0x1800028f4  jnb     short loc_1800028E4
0x1800028f6  sub     eax, r10d
0x1800028f9  cmp     eax, ebp
0x1800028fb  jb      short loc_1800028E4
0x1800028fd  mov     rax, [rcx]
0x180002900  lea     r8, [rsp+48h+arg_8]
0x180002905  and     [rsp+48h+arg_8], 0
0x18000290b  mov     edx, r10d
0x18000290e  mov     rax, [rax+40h]
0x180002912  call    cs:__guard_dispatch_icall_fptr
0x180002918  test    eax, eax
0x18000291a  js      short loc_18000296F
0x18000291c  mov     r15, [rsp+48h+arg_8]
0x180002921  xor     esi, esi
0x180002923  test    ebp, ebp
0x180002925  jz      short loc_18000296D
0x180002927  mov     rbx, r14
0x18000292a  lea     r13d, [rsi+8]
0x18000292e  mov     rdi, r15
0x180002931  cmp     [rbx], r13w
0x180002935  jnz     short loc_180002949
0x180002937  cmp     qword ptr [rbx+8], 0
0x18000293c  jnz     short loc_180002949
0x18000293e  and     qword ptr [rdi+8], 0
0x180002943  mov     [rdi], r13w
0x180002947  jmp     short loc_18000295F
0x180002949  lea     rcx, [rsi+rsi*2]
0x18000294d  lea     rdx, [r14+rcx*8]; pvargSrc
0x180002951  lea     rcx, [r15+rcx*8]; pvargDest
0x180002955  call    cs:__imp_VariantCopy
0x18000295b  test    eax, eax
0x18000295d  js      short loc_18000296F
0x18000295f  inc     esi
0x180002961  add     rbx, 18h
0x180002965  add     rdi, 18h
0x180002969  cmp     esi, ebp
0x18000296b  jb      short loc_180002931
0x18000296d  xor     eax, eax
0x18000296f  mov     rbx, [rsp+48h+arg_0]
0x180002974  mov     rbp, [rsp+48h+arg_10]
0x180002979  add     rsp, 20h
0x18000297d  pop     r15
0x18000297f  pop     r14
0x180002981  pop     r13
0x180002983  pop     rdi
0x180002984  pop     rsi
0x180002985  retn
```
