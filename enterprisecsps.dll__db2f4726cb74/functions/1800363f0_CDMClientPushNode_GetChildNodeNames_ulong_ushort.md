# CDMClientPushNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800363f0`
- end: `0x180036573`
- name: `?GetChildNodeNames@CDMClientPushNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `387`
- prototype: `__int64 __fastcall(CDMClientPushNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x1800363f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800364e3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800364e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180036521`
- `OLEAUT32!__imp_SysFreeString` at `0x180036521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003653e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003653e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036496`

## pseudocode

```c
__int64 __fastcall CDMClientPushNode::GetChildNodeNames(
        CDMClientPushNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  int v5; // ebx
  unsigned int v6; // esi
  __int64 v7; // rcx
  unsigned int v8; // eax
  size_t v9; // rbp
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // rdi
  __int64 v12; // rbp
  int i; // r12d
  const OLECHAR *v14; // rcx
  BSTR v15; // rax
  __int64 j; // rbp
  OLECHAR *v17; // rcx
  SIZE_T cb; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 11) != 16 )
  {
    if ( *((_DWORD *)this + 11) == 17 || (unsigned int)(*((_DWORD *)this + 11) - 18) <= 1 )
      return (unsigned int)-2046820335;
    return (unsigned int)-2147024809;
  }
  LODWORD(cb) = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = 0;
  *a2 = 0;
  v7 = 0;
  *a3 = 0;
  do
  {
    v8 = v6 + 1;
    if ( !(&c_rgPushNodes)[v7] )
      v8 = v6;
    ++v7;
    v6 = v8;
  }
  while ( v7 != 3 );
  v5 = ULongLongToULong(8LL * v8, (unsigned int *)&cb);
  if ( v5 >= 0 )
  {
    v9 = (unsigned int)cb;
    v10 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, v9);
      v12 = 0;
      for ( i = 0; i < 3; ++i )
      {
        if ( (unsigned int)v12 >= v6 )
          goto LABEL_23;
        v14 = (const OLECHAR *)(&c_rgPushNodes)[i];
        if ( v14 )
        {
          v15 = SysAllocString(v14);
          v11[v12] = v15;
          if ( !v15 )
          {
            v5 = -2147024882;
            goto LABEL_24;
          }
          v12 = (unsigned int)(v12 + 1);
        }
      }
      if ( (_DWORD)v12 == v6 )
      {
        *a2 = v12;
        *a3 = v11;
        return (unsigned int)v5;
      }
LABEL_23:
      v5 = -2147418113;
LABEL_24:
      for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
      {
        v17 = v11[j];
        if ( v17 )
        {
          SysFreeString(v17);
          v11[j] = 0;
        }
      }
      CoTaskMemFree(v11);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800363f0  mov     [rsp+arg_8], rbx
0x1800363f5  mov     [rsp+arg_10], rbp
0x1800363fa  push    rsi
0x1800363fb  push    rdi
0x1800363fc  push    r12
0x1800363fe  push    r14
0x180036400  push    r15
0x180036402  sub     rsp, 20h
0x180036406  mov     r9d, [rcx+2Ch]
0x18003640a  mov     r14, r8
0x18003640d  mov     r15, rdx
0x180036410  sub     r9d, 10h
0x180036414  jz      short loc_180036436
0x180036416  sub     r9d, 1
0x18003641a  jz      short loc_18003642C
0x18003641c  sub     r9d, 1
0x180036420  jz      short loc_18003642C
0x180036422  cmp     r9d, 1
0x180036426  jnz     loc_180036554
0x18003642c  mov     ebx, 86000011h
0x180036431  jmp     loc_180036559
0x180036436  mov     dword ptr [rsp+48h+cb], 0
0x18003643e  test    r15, r15
0x180036441  jz      loc_180036554
0x180036447  test    r14, r14
0x18003644a  jz      loc_180036554
0x180036450  xor     esi, esi
0x180036452  mov     [rdx], esi
0x180036454  xor     ecx, ecx
0x180036456  mov     [r8], rsi
0x180036459  lea     rdx, ?c_rgPushNodes@@3PAPEBGA; ushort const * near * c_rgPushNodes
0x180036460  cmp     qword ptr [rdx+rcx*8], 0
0x180036465  lea     eax, [rsi+1]
0x180036468  cmovz   eax, esi
0x18003646b  inc     rcx
0x18003646e  mov     esi, eax
0x180036470  cmp     rcx, 3
0x180036474  jnz     short loc_180036460
0x180036476  mov     ecx, esi
0x180036478  lea     rdx, [rsp+48h+cb]; unsigned int *
0x18003647d  shl     rcx, 3; unsigned __int64
0x180036481  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180036486  mov     ebx, eax
0x180036488  test    eax, eax
0x18003648a  js      loc_180036559
0x180036490  mov     ebp, dword ptr [rsp+48h+cb]
0x180036494  mov     ecx, ebp; cb
0x180036496  call    cs:__imp_CoTaskMemAlloc
0x18003649d  nop     dword ptr [rax+rax+00h]
0x1800364a2  mov     rdi, rax
0x1800364a5  test    rax, rax
0x1800364a8  jnz     short loc_1800364B4
0x1800364aa  mov     ebx, 8007000Eh
0x1800364af  jmp     loc_180036559
0x1800364b4  mov     r8, rbp; Size
0x1800364b7  xor     edx, edx; Val
0x1800364b9  mov     rcx, rdi; void *
0x1800364bc  call    memset_0
0x1800364c1  xor     ebp, ebp
0x1800364c3  xor     r12d, r12d
0x1800364c6  cmp     r12d, 3
0x1800364ca  jge     short loc_180036506
0x1800364cc  cmp     ebp, esi
0x1800364ce  jnb     short loc_18003650A
0x1800364d0  movsxd  rax, r12d
0x1800364d3  lea     rcx, ?c_rgPushNodes@@3PAPEBGA; ushort const * near * c_rgPushNodes
0x1800364da  mov     rcx, [rcx+rax*8]; psz
0x1800364de  test    rcx, rcx
0x1800364e1  jz      short loc_1800364FA
0x1800364e3  call    cs:__imp_SysAllocString
0x1800364ea  nop     dword ptr [rax+rax+00h]
0x1800364ef  mov     [rdi+rbp*8], rax
0x1800364f3  test    rax, rax
0x1800364f6  jz      short loc_1800364FF
0x1800364f8  inc     ebp
0x1800364fa  inc     r12d
0x1800364fd  jmp     short loc_1800364C6
0x1800364ff  mov     ebx, 8007000Eh
0x180036504  jmp     short loc_18003650F
0x180036506  cmp     ebp, esi
0x180036508  jz      short loc_18003654C
0x18003650a  mov     ebx, 8000FFFFh
0x18003650f  xor     ebp, ebp
0x180036511  mov     r14, rdi
0x180036514  test    esi, esi
0x180036516  jz      short loc_18003653B
0x180036518  mov     rcx, [r14+rbp*8]; bstrString
0x18003651c  test    rcx, rcx
0x18003651f  jz      short loc_180036535
0x180036521  call    cs:__imp_SysFreeString
0x180036528  nop     dword ptr [rax+rax+00h]
0x18003652d  mov     qword ptr [r14+rbp*8], 0
0x180036535  inc     ebp
0x180036537  cmp     ebp, esi
0x180036539  jb      short loc_180036518
0x18003653b  mov     rcx, rdi; pv
0x18003653e  call    cs:__imp_CoTaskMemFree
0x180036545  nop     dword ptr [rax+rax+00h]
0x18003654a  jmp     short loc_180036559
0x18003654c  mov     [r15], ebp
0x18003654f  mov     [r14], rdi
0x180036552  jmp     short loc_180036559
0x180036554  mov     ebx, 80070057h
0x180036559  mov     rbp, [rsp+48h+arg_10]
0x18003655e  mov     eax, ebx
0x180036560  mov     rbx, [rsp+48h+arg_8]
0x180036565  add     rsp, 20h
0x180036569  pop     r15
0x18003656b  pop     r14
0x18003656d  pop     r12
0x18003656f  pop     rdi
0x180036570  pop     rsi
0x180036571  retn
```
