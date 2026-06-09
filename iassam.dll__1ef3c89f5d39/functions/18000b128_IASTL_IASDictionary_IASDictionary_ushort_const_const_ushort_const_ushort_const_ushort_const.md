# IASTL::IASDictionary::IASDictionary(ushort const * const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000b128`
- end: `0x18000b244`
- name: `??0IASDictionary@IASTL@@QEAA@PEBQEBGPEBG11@Z`
- size: `284`
- prototype: `__int64 __fastcall(IASTL::IASDictionary *__hidden this, const unsigned __int16 *const *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bcf8`

## callees

- `0x18000b128`
- `0x18000b81c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b1ea`
- `msvcrt!_wcsicmp` at `0x18000b1ea`
- `iassvcs!IASGetLocalDictionary` at `0x18000b16a`
- `iassvcs!IASGetLocalDictionary` at `0x18000b16a`
- `KERNEL32!GetLastError` at `0x18000b178`
- `KERNEL32!GetLastError` at `0x18000b178`
- `OLEAUT32!__imp_VariantInit` at `0x18000b163`
- `OLEAUT32!__imp_VariantInit` at `0x18000b163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b1a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b1a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b219`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
VARIANTARG *__fastcall IASTL::IASDictionary::IASDictionary(
        VARIANTARG *this,
        const unsigned __int16 *const *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rax
  DWORD LastError; // eax
  int v8; // edx
  const unsigned __int16 *const *i; // rax
  IRecordInfo *v10; // rax
  int v11; // edx
  __int64 j; // rsi
  const unsigned __int16 *v13; // r14
  wchar_t v14; // bp
  __int64 v15; // rdi
  __int64 k; // rcx
  int v17; // edx

  this->lVal = 0;
  *(_DWORD *)&this[1].vt = 0;
  this[1].llVal = 0;
  VariantInit(this + 3);
  v6 = IASGetLocalDictionary();
  *(_QWORD *)&this->vt = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    IASTL::issue_error((IASTL *)LastError, v8);
  }
  for ( i = a2; *i; ++i )
    ++this->lVal;
  v10 = (IRecordInfo *)CoTaskMemAlloc(4LL * this->cyVal.Lo);
  this->pRecInfo = v10;
  if ( !v10 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v11);
  for ( j = 0; (unsigned int)j < this->lVal; j = (unsigned int)(j + 1) )
  {
    v13 = a2[j];
    v14 = *v13;
    if ( *v13 == 45 )
      ++v13;
    v15 = 0;
    for ( k = *(_QWORD *)&this->vt; (unsigned int)v15 < **(_DWORD **)&this->vt; k = *(_QWORD *)&this->vt )
    {
      if ( !_wcsicmp(v13, *(const wchar_t **)(*(_QWORD *)(k + 8) + 8 * v15)) )
        break;
      v15 = (unsigned int)(v15 + 1);
    }
    if ( (_DWORD)v15 == **(_DWORD **)&this->vt && v14 != 45 )
    {
      CoTaskMemFree(this->pRecInfo);
      IASTL::issue_error((IASTL *)0x80070057LL, v17);
    }
    *((_DWORD *)&this->pRecInfo->lpVtbl + j) = v15;
  }
  return this;
}

```

## disassembly

```asm
0x18000b128  mov     [rsp+arg_8], rbx
0x18000b12d  mov     [rsp+arg_10], rbp
0x18000b132  mov     [rsp+arg_0], rcx
0x18000b137  push    rsi
0x18000b138  push    rdi
0x18000b139  push    r12
0x18000b13b  push    r14
0x18000b13d  push    r15
0x18000b13f  sub     rsp, 20h
0x18000b143  mov     r15, rdx
0x18000b146  mov     rbx, rcx
0x18000b149  mov     dword ptr [rcx+8], 0
0x18000b150  mov     dword ptr [rcx+18h], 0
0x18000b157  mov     qword ptr [rcx+20h], 0
0x18000b15f  add     rcx, 48h ; 'H'; pvarg
0x18000b163  call    cs:__imp_VariantInit
0x18000b169  nop
0x18000b16a  call    cs:__imp_IASGetLocalDictionary
0x18000b170  mov     [rbx], rax
0x18000b173  test    rax, rax
0x18000b176  jnz     short loc_18000B186
0x18000b178  call    cs:__imp_GetLastError
0x18000b17e  mov     ecx, eax; this
0x18000b180  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000b186  mov     rax, r15
0x18000b189  cmp     qword ptr [r15], 0
0x18000b18d  jz      short loc_18000B19C
0x18000b18f  inc     dword ptr [rbx+8]
0x18000b192  lea     rax, [rax+8]
0x18000b196  cmp     qword ptr [rax], 0
0x18000b19a  jnz     short loc_18000B18F
0x18000b19c  mov     ecx, [rbx+8]
0x18000b19f  shl     rcx, 2; cb
0x18000b1a3  call    cs:__imp_CoTaskMemAlloc
0x18000b1a9  mov     [rbx+10h], rax
0x18000b1ad  test    rax, rax
0x18000b1b0  jnz     short loc_18000B1BD
0x18000b1b2  mov     ecx, 8007000Eh; this
0x18000b1b7  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000b1bd  xor     esi, esi
0x18000b1bf  cmp     esi, [rbx+8]
0x18000b1c2  jnb     short loc_18000B22A
0x18000b1c4  mov     r14, [r15+rsi*8]
0x18000b1c8  movzx   ebp, word ptr [r14]
0x18000b1cc  cmp     bp, 2Dh ; '-'
0x18000b1d0  jnz     short loc_18000B1D6
0x18000b1d2  add     r14, 2
0x18000b1d6  xor     edi, edi
0x18000b1d8  mov     rcx, [rbx]
0x18000b1db  cmp     [rcx], edi
0x18000b1dd  jbe     short loc_18000B1FD
0x18000b1df  mov     rdx, [rcx+8]
0x18000b1e3  mov     rdx, [rdx+rdi*8]; String2
0x18000b1e7  mov     rcx, r14; String1
0x18000b1ea  call    cs:__imp__wcsicmp
0x18000b1f0  test    eax, eax
0x18000b1f2  jz      short loc_18000B1FD
0x18000b1f4  inc     edi
0x18000b1f6  mov     rcx, [rbx]
0x18000b1f9  cmp     edi, [rcx]
0x18000b1fb  jb      short loc_18000B1DF
0x18000b1fd  mov     rax, [rbx]
0x18000b200  cmp     edi, [rax]
0x18000b202  jnz     short loc_18000B20A
0x18000b204  cmp     bp, 2Dh ; '-'
0x18000b208  jnz     short loc_18000B215
0x18000b20a  mov     rax, [rbx+10h]
0x18000b20e  mov     [rax+rsi*4], edi
0x18000b211  inc     esi
0x18000b213  jmp     short loc_18000B1BF
0x18000b215  mov     rcx, [rbx+10h]; pv
0x18000b219  call    cs:__imp_CoTaskMemFree
0x18000b21f  mov     ecx, 80070057h; this
0x18000b224  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000b22a  mov     rax, rbx
0x18000b22d  mov     rbx, [rsp+48h+arg_8]
0x18000b232  mov     rbp, [rsp+48h+arg_10]
0x18000b237  add     rsp, 20h
0x18000b23b  pop     r15
0x18000b23d  pop     r14
0x18000b23f  pop     r12
0x18000b241  pop     rdi
0x18000b242  pop     rsi
0x18000b243  retn
```
