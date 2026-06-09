# AllocateBStrArray(ushort const * *,int,ulong *,ushort * * *)

- ea: `0x180015d58`
- end: `0x180015e89`
- name: `?AllocateBStrArray@@YAJPEAPEBGHPEAKPEAPEAPEAG@Z`
- size: `305`
- prototype: `__int64 __fastcall(const unsigned __int16 **, int, unsigned int *, unsigned __int16 ***)`
- caller_count: `50`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016b38`
- `0x180016d74`
- `0x180016fb0`
- `0x1800171ec`
- `0x180021460`
- `0x180021800`
- `0x180022340`
- `0x180045210`
- `0x18004a5b0`
- `0x18004c800`
- `0x180050780`
- `0x180051860`
- `0x1800531a0`
- `0x180053260`
- `0x180054b80`
- `0x180061c10`
- `0x1800623e0`
- `0x180069060`
- `0x18006cd70`
- `0x18006cfa0`
- `0x18006df40`
- `0x18006f558`
- `0x18006f794`
- `0x18006f9d0`
- `0x18006fc0c`
- `0x18006fe48`
- `0x180070084`
- `0x1800702c0`
- `0x1800704fc`
- `0x180070738`
- `0x180070974`
- `0x18007d9b0`
- `0x18007fea0`
- `0x180086000`
- `0x1800868b0`
- `0x1800928b0`
- `0x180093020`
- `0x180093b90`
- `0x1800946d0`
- `0x180094bb0`
- `0x1800957d0`
- `0x1800a2420`
- `0x1800a3170`
- `0x1800a3b50`
- `0x1800a4390`
- `0x1800a4a90`
- `0x1800a52e0`
- `0x1800bc6d0`
- `0x1800bdbf0`
- `0x1800be380`

## callees

- `0x180009cc4`
- `0x180015d58`
- `0x180015e90`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015dfd`
- `OLEAUT32!__imp_SysAllocString` at `0x180015dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015dbc`

## pseudocode

```c
__int64 __fastcall AllocateBStrArray(const unsigned __int16 **a1, int a2, unsigned int *a3, unsigned __int16 ***a4)
{
  unsigned int v4; // edi
  __int64 v5; // r10
  unsigned int v9; // ecx
  int v10; // ebx
  size_t v11; // rbp
  unsigned __int16 **v12; // rax
  unsigned __int16 **v13; // rsi
  __int64 v14; // rbp
  int i; // r14d
  const OLECHAR *v16; // rcx
  BSTR v17; // rax
  __int64 j; // rbp
  OLECHAR *v19; // rcx
  SIZE_T cb; // [rsp+68h] [rbp+10h] BYREF
  unsigned int *v22; // [rsp+70h] [rbp+18h]

  v22 = a3;
  v4 = 0;
  v5 = 0;
  for ( LODWORD(cb) = 0; (int)v5 < a2; v4 = v9 )
  {
    v9 = v4 + 1;
    if ( !a1[v5] )
      v9 = v4;
    v5 = (unsigned int)(v5 + 1);
  }
  v10 = ULongLongToULong(8LL * v4, (unsigned int *)&cb);
  if ( v10 >= 0 )
  {
    v11 = (unsigned int)cb;
    v12 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, v11);
      v14 = 0;
      for ( i = 0; i < a2; ++i )
      {
        v16 = a1[i];
        if ( v16 )
        {
          v17 = SysAllocString(v16);
          v13[v14] = v17;
          if ( !v17 )
          {
            v10 = -2147024882;
            goto LABEL_17;
          }
          v14 = (unsigned int)(v14 + 1);
        }
      }
      if ( (_DWORD)v14 == v4 )
      {
        *v22 = v14;
        *a4 = v13;
        return (unsigned int)v10;
      }
      v10 = -2147418113;
LABEL_17:
      for ( j = 0; (unsigned int)j < v4; j = (unsigned int)(j + 1) )
      {
        v19 = v13[j];
        if ( v19 )
        {
          SysFreeString(v19);
          v13[j] = 0;
        }
      }
      CoTaskMemFree(v13);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180015d58  mov     [rsp+arg_0], rbx
0x180015d5d  mov     [rsp+arg_10], r8
0x180015d62  push    rbp
0x180015d63  push    rsi
0x180015d64  push    rdi
0x180015d65  push    r12
0x180015d67  push    r13
0x180015d69  push    r14
0x180015d6b  push    r15
0x180015d6d  sub     rsp, 20h
0x180015d71  xor     edi, edi
0x180015d73  xor     r10d, r10d
0x180015d76  mov     dword ptr [rsp+58h+cb], edi
0x180015d7a  mov     r13, r9
0x180015d7d  mov     r15d, edx
0x180015d80  mov     r12, rcx
0x180015d83  test    edx, edx
0x180015d85  jle     short loc_180015D9C
0x180015d87  cmp     qword ptr [r12+r10*8], 0
0x180015d8c  lea     ecx, [rdi+1]
0x180015d8f  cmovz   ecx, edi
0x180015d92  inc     r10d
0x180015d95  mov     edi, ecx
0x180015d97  cmp     r10d, r15d
0x180015d9a  jl      short loc_180015D87
0x180015d9c  mov     ecx, edi
0x180015d9e  lea     rdx, [rsp+58h+cb]; unsigned int *
0x180015da3  shl     rcx, 3; unsigned __int64
0x180015da7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180015dac  mov     ebx, eax
0x180015dae  test    eax, eax
0x180015db0  js      loc_180015E71
0x180015db6  mov     ebp, dword ptr [rsp+58h+cb]
0x180015dba  mov     ecx, ebp; cb
0x180015dbc  call    cs:__imp_CoTaskMemAlloc
0x180015dc3  nop     dword ptr [rax+rax+00h]
0x180015dc8  mov     rsi, rax
0x180015dcb  test    rax, rax
0x180015dce  jnz     short loc_180015DDA
0x180015dd0  mov     ebx, 8007000Eh
0x180015dd5  jmp     loc_180015E71
0x180015dda  mov     r8, rbp; Size
0x180015ddd  xor     edx, edx; Val
0x180015ddf  mov     rcx, rsi; void *
0x180015de2  call    memset_0
0x180015de7  xor     ebp, ebp
0x180015de9  xor     r14d, r14d
0x180015dec  cmp     r14d, r15d
0x180015def  jge     short loc_180015E20
0x180015df1  movsxd  rax, r14d
0x180015df4  mov     rcx, [r12+rax*8]; psz
0x180015df8  test    rcx, rcx
0x180015dfb  jz      short loc_180015E14
0x180015dfd  call    cs:__imp_SysAllocString
0x180015e04  nop     dword ptr [rax+rax+00h]
0x180015e09  mov     [rsi+rbp*8], rax
0x180015e0d  test    rax, rax
0x180015e10  jz      short loc_180015E19
0x180015e12  inc     ebp
0x180015e14  inc     r14d
0x180015e17  jmp     short loc_180015DEC
0x180015e19  mov     ebx, 8007000Eh
0x180015e1e  jmp     short loc_180015E29
0x180015e20  cmp     ebp, edi
0x180015e22  jz      short loc_180015E66
0x180015e24  mov     ebx, 8000FFFFh
0x180015e29  xor     ebp, ebp
0x180015e2b  mov     r14, rsi
0x180015e2e  test    edi, edi
0x180015e30  jz      short loc_180015E55
0x180015e32  mov     rcx, [r14+rbp*8]; bstrString
0x180015e36  test    rcx, rcx
0x180015e39  jz      short loc_180015E4F
0x180015e3b  call    cs:__imp_SysFreeString
0x180015e42  nop     dword ptr [rax+rax+00h]
0x180015e47  mov     qword ptr [r14+rbp*8], 0
0x180015e4f  inc     ebp
0x180015e51  cmp     ebp, edi
0x180015e53  jb      short loc_180015E32
0x180015e55  mov     rcx, rsi; pv
0x180015e58  call    cs:__imp_CoTaskMemFree
0x180015e5f  nop     dword ptr [rax+rax+00h]
0x180015e64  jmp     short loc_180015E71
0x180015e66  mov     rax, [rsp+58h+arg_10]
0x180015e6b  mov     [rax], ebp
0x180015e6d  mov     [r13+0], rsi
0x180015e71  mov     eax, ebx
0x180015e73  mov     rbx, [rsp+58h+arg_0]
0x180015e78  add     rsp, 20h
0x180015e7c  pop     r15
0x180015e7e  pop     r14
0x180015e80  pop     r13
0x180015e82  pop     r12
0x180015e84  pop     rdi
0x180015e85  pop     rsi
0x180015e86  pop     rbp
0x180015e87  retn
```
