# DMClient::GetAllMultipleSessionChildNodeNames(ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x180027a98`
- end: `0x180027bfa`
- name: `?GetAllMultipleSessionChildNodeNames@DMClient@@YAJPEBG0PEAKPEAPEAPEAG@Z`
- size: `354`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036200`

## callees

- `0x180027a98`
- `0x180029694`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027b73`
- `OLEAUT32!__imp_SysAllocString` at `0x180027b73`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ba5`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ba5`
- `OLEAUT32!__imp_VariantInit` at `0x180027ac9`
- `OLEAUT32!__imp_VariantInit` at `0x180027ac9`
- `OLEAUT32!__imp_VariantClear` at `0x180027b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180027bda`
- `OLEAUT32!__imp_VariantClear` at `0x180027b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180027bda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027afe`

## pseudocode

```c
__int64 __fastcall DMClient::GetAllMultipleSessionChildNodeNames(
        DMClient *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  _QWORD *v8; // rdi
  unsigned int *v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rsi
  int i; // ebp
  int MultipleSessionValue; // eax
  BSTR v14; // rax
  __int64 j; // rbp
  OLECHAR *v16; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-68h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !this || !a3 || !a4 || !a2 )
  {
    v10 = -2147024809;
    goto LABEL_23;
  }
  v8 = CoTaskMemAlloc(0x20u);
  if ( !v8 )
  {
    v10 = -2147024882;
    goto LABEL_23;
  }
  v11 = 0;
  v10 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      *(_DWORD *)a3 = v11;
      *(_QWORD *)a4 = v8;
      goto LABEL_23;
    }
    MultipleSessionValue = DMClient::GetMultipleSessionValue(
                             this,
                             (LPCWSTR)(&c_rgMultipleSessionValues)[i],
                             &pvarg.uiVal,
                             v9);
    v10 = MultipleSessionValue;
    if ( MultipleSessionValue == -2147024894 )
    {
      v10 = 0;
      continue;
    }
    if ( MultipleSessionValue < 0 )
      goto LABEL_16;
    VariantClear(&pvarg);
    v14 = SysAllocString((const OLECHAR *)(&c_rgMultipleSessionValues)[i]);
    v8[v11] = v14;
    if ( !v14 )
      break;
    v11 = (unsigned int)(v11 + 1);
  }
  v10 = -2147024882;
LABEL_16:
  for ( j = 0; (unsigned int)j < (unsigned int)v11; j = (unsigned int)(j + 1) )
  {
    v16 = (OLECHAR *)v8[j];
    if ( v16 )
      SysFreeString(v16);
  }
  CoTaskMemFree(v8);
LABEL_23:
  VariantClear(&pvarg);
  return v10;
}

```

## disassembly

```asm
0x180027a98  push    rbx
0x180027a9a  push    rbp
0x180027a9b  push    rsi
0x180027a9c  push    rdi
0x180027a9d  push    r12
0x180027a9f  push    r13
0x180027aa1  push    r14
0x180027aa3  push    r15
0x180027aa5  sub     rsp, 48h
0x180027aa9  mov     r13, rcx
0x180027aac  xorps   xmm0, xmm0
0x180027aaf  xor     eax, eax
0x180027ab1  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180027ab6  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180027abb  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x180027ac0  mov     r14, r9
0x180027ac3  mov     r15, r8
0x180027ac6  mov     rbx, rdx
0x180027ac9  call    cs:__imp_VariantInit
0x180027ad0  nop     dword ptr [rax+rax+00h]
0x180027ad5  test    r13, r13
0x180027ad8  jz      loc_180027BD0
0x180027ade  test    r15, r15
0x180027ae1  jz      loc_180027BD0
0x180027ae7  test    r14, r14
0x180027aea  jz      loc_180027BD0
0x180027af0  test    rbx, rbx
0x180027af3  jz      loc_180027BD0
0x180027af9  mov     ecx, 20h ; ' '; cb
0x180027afe  call    cs:__imp_CoTaskMemAlloc
0x180027b05  nop     dword ptr [rax+rax+00h]
0x180027b0a  mov     rdi, rax
0x180027b0d  test    rax, rax
0x180027b10  jnz     short loc_180027B1C
0x180027b12  mov     ebx, 8007000Eh
0x180027b17  jmp     loc_180027BD5
0x180027b1c  xor     esi, esi
0x180027b1e  xor     ebx, ebx
0x180027b20  xor     ebp, ebp
0x180027b22  cmp     ebp, 4
0x180027b25  jge     loc_180027BC8
0x180027b2b  lea     rax, ?c_rgMultipleSessionValues@@3PAPEBGA; ushort const * near * c_rgMultipleSessionValues
0x180027b32  movsxd  r12, ebp
0x180027b35  lea     r8, [rsp+88h+pvarg+8]; unsigned __int16 *
0x180027b3a  mov     rcx, r13; this
0x180027b3d  mov     rdx, [rax+r12*8]; lpValue
0x180027b41  call    ?GetMultipleSessionValue@DMClient@@YAJPEBG0PEAK@Z; DMClient::GetMultipleSessionValue(ushort const *,ushort const *,ulong *)
0x180027b46  mov     ebx, eax
0x180027b48  cmp     eax, 80070002h
0x180027b4d  jnz     short loc_180027B53
0x180027b4f  xor     ebx, ebx
0x180027b51  jmp     short loc_180027B8A
0x180027b53  test    eax, eax
0x180027b55  js      short loc_180027B93
0x180027b57  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180027b5c  call    cs:__imp_VariantClear
0x180027b63  nop     dword ptr [rax+rax+00h]
0x180027b68  lea     rcx, ?c_rgMultipleSessionValues@@3PAPEBGA; ushort const * near * c_rgMultipleSessionValues
0x180027b6f  mov     rcx, [rcx+r12*8]; psz
0x180027b73  call    cs:__imp_SysAllocString
0x180027b7a  nop     dword ptr [rax+rax+00h]
0x180027b7f  mov     [rdi+rsi*8], rax
0x180027b83  test    rax, rax
0x180027b86  jz      short loc_180027B8E
0x180027b88  inc     esi
0x180027b8a  inc     ebp
0x180027b8c  jmp     short loc_180027B22
0x180027b8e  mov     ebx, 8007000Eh
0x180027b93  xor     ebp, ebp
0x180027b95  mov     r14, rdi
0x180027b98  test    esi, esi
0x180027b9a  jz      short loc_180027BB7
0x180027b9c  mov     rcx, [r14+rbp*8]; bstrString
0x180027ba0  test    rcx, rcx
0x180027ba3  jz      short loc_180027BB1
0x180027ba5  call    cs:__imp_SysFreeString
0x180027bac  nop     dword ptr [rax+rax+00h]
0x180027bb1  inc     ebp
0x180027bb3  cmp     ebp, esi
0x180027bb5  jb      short loc_180027B9C
0x180027bb7  mov     rcx, rdi; pv
0x180027bba  call    cs:__imp_CoTaskMemFree
0x180027bc1  nop     dword ptr [rax+rax+00h]
0x180027bc6  jmp     short loc_180027BD5
0x180027bc8  mov     [r15], esi
0x180027bcb  mov     [r14], rdi
0x180027bce  jmp     short loc_180027BD5
0x180027bd0  mov     ebx, 80070057h
0x180027bd5  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180027bda  call    cs:__imp_VariantClear
0x180027be1  nop     dword ptr [rax+rax+00h]
0x180027be6  mov     eax, ebx
0x180027be8  add     rsp, 48h
0x180027bec  pop     r15
0x180027bee  pop     r14
0x180027bf0  pop     r13
0x180027bf2  pop     r12
0x180027bf4  pop     rdi
0x180027bf5  pop     rsi
0x180027bf6  pop     rbp
0x180027bf7  pop     rbx
0x180027bf8  retn
```
