# HrGetValFromBLOB(tagPROPVARIANT *,tagPROPVARIANT const *,ushort)

- ea: `0x180052050`
- end: `0x18005213c`
- name: `?HrGetValFromBLOB@@YAJPEAUtagPROPVARIANT@@PEBU1@G@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051b64`

## callees

- `0x180052050`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800520f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800520f6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800520b3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800520b3`

## pseudocode

```c
__int64 __fastcall HrGetValFromBLOB(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2, __int16 a3)
{
  unsigned int v5; // ebx
  unsigned int ulVal; // ebp
  BYTE *pData; // r14
  SAFEARRAY *v8; // rax
  LARGE_INTEGER v9; // rsi
  PVOID pvData; // rcx
  void *v11; // rax
  __int128 v13; // [rsp+20h] [rbp-28h]
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp+20h] BYREF

  DWORD1(v13) = 0;
  if ( a3 == 65 || a3 == 70 )
  {
    v5 = 0;
    if ( !a2->lVal )
    {
      a1->bstrblobVal.pData = 0;
      a1->lVal = 0;
      return v5;
    }
    LODWORD(v13) = a2->lVal;
    v11 = CoTaskMemAlloc((unsigned int)v13);
    *((_QWORD *)&v13 + 1) = v11;
    if ( v11 )
    {
      memcpy_0(v11, a2->bstrblobVal.pData, a2->ulVal);
      *(_OWORD *)&a1->decVal.Lo32 = v13;
      return v5;
    }
    return (unsigned int)-2147024882;
  }
  if ( a3 != 8209 )
    return (unsigned int)-2147352571;
  ulVal = a2->ulVal;
  pData = a2->bstrblobVal.pData;
  rgsabound.lLbound = 0;
  rgsabound.cElements = ulVal;
  v8 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v9.QuadPart = (LONGLONG)v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  pvData = v8->pvData;
  v5 = 0;
  if ( pvData )
    memcpy_0(pvData, pData, ulVal);
  a1->hVal = v9;
  return v5;
}

```

## disassembly

```asm
0x180052050  mov     [rsp+arg_0], rbx
0x180052055  mov     [rsp+arg_8], rbp
0x18005205a  push    rsi
0x18005205b  push    rdi
0x18005205c  push    r14
0x18005205e  sub     rsp, 30h
0x180052062  mov     dword ptr [rsp+48h+var_28+4], 0
0x18005206a  mov     rsi, rdx
0x18005206d  mov     rdi, rcx
0x180052070  cmp     r8w, 41h ; 'A'
0x180052075  jz      short loc_1800520DD
0x180052077  cmp     r8w, 46h ; 'F'
0x18005207c  jz      short loc_1800520DD
0x18005207e  mov     eax, 2011h
0x180052083  cmp     r8w, ax
0x180052087  jz      short loc_180052093
0x180052089  mov     ebx, 80020005h
0x18005208e  jmp     loc_180052127
0x180052093  mov     ebp, [rdx+8]
0x180052096  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x18005209b  mov     r14, [rdx+10h]
0x18005209f  mov     ecx, 11h; vt
0x1800520a4  mov     [rsp+48h+rgsabound.lLbound], 0
0x1800520ac  mov     [rsp+48h+rgsabound.cElements], ebp
0x1800520b0  lea     edx, [rcx-10h]; cDims
0x1800520b3  call    cs:__imp_SafeArrayCreate
0x1800520b9  mov     rsi, rax
0x1800520bc  test    rax, rax
0x1800520bf  jz      short loc_180052106
0x1800520c1  mov     rcx, [rax+10h]; void *
0x1800520c5  xor     ebx, ebx
0x1800520c7  test    rcx, rcx
0x1800520ca  jz      short loc_1800520D7
0x1800520cc  mov     r8d, ebp; Size
0x1800520cf  mov     rdx, r14; Src
0x1800520d2  call    memcpy_0
0x1800520d7  mov     [rdi+8], rsi
0x1800520db  jmp     short loc_180052127
0x1800520dd  mov     eax, [rdx+8]
0x1800520e0  xor     ebx, ebx
0x1800520e2  test    eax, eax
0x1800520e4  jnz     short loc_1800520EF
0x1800520e6  mov     [rcx+10h], rbx
0x1800520ea  mov     [rcx+8], ebx
0x1800520ed  jmp     short loc_180052127
0x1800520ef  mov     rcx, rax; cb
0x1800520f2  mov     dword ptr [rsp+48h+var_28], eax
0x1800520f6  call    cs:__imp_CoTaskMemAlloc
0x1800520fc  mov     qword ptr [rsp+48h+var_28+8], rax
0x180052101  test    rax, rax
0x180052104  jnz     short loc_18005210D
0x180052106  mov     ebx, 8007000Eh
0x18005210b  jmp     short loc_180052127
0x18005210d  mov     r8d, [rsi+8]; Size
0x180052111  mov     rcx, rax; void *
0x180052114  mov     rdx, [rsi+10h]; Src
0x180052118  call    memcpy_0
0x18005211d  movups  xmm0, [rsp+48h+var_28]
0x180052122  movdqu  xmmword ptr [rdi+8], xmm0
0x180052127  mov     rbp, [rsp+48h+arg_8]
0x18005212c  mov     eax, ebx
0x18005212e  mov     rbx, [rsp+48h+arg_0]
0x180052133  add     rsp, 30h
0x180052137  pop     r14
0x180052139  pop     rdi
0x18005213a  pop     rsi
0x18005213b  retn
```
