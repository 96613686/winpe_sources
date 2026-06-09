# CMapiNamedProp::GetNamedPropId(IMAPIProp *,wchar_t const *,ulong,ulong *,int)

- ea: `0x180034094`
- end: `0x18003416f`
- name: `?GetNamedPropId@CMapiNamedProp@@AEAAJPEAUIMAPIProp@@PEB_WKPEAKH@Z`
- size: `219`
- prototype: `int(CMapiNamedProp *__hidden this, struct IMAPIProp *, const wchar_t *, unsigned int, unsigned int *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800239c8`

## callees

- `0x180006270`
- `0x180034020`
- `0x180034094`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800340e0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800340e0`

## pseudocode

```c
__int64 __fastcall CMapiNamedProp::GetNamedPropId(
        CMapiNamedProp *this,
        struct IMAPIProp *a2,
        const wchar_t *a3,
        int a4,
        unsigned int *a5)
{
  struct IMAPIPropVtbl *lpVtbl; // rax
  int v8; // ebx
  unsigned int v9; // edx
  __int128 *v11; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+38h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-40h] BYREF
  __int128 v14; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+58h] [rbp-28h]
  GUID pclsid; // [rsp+60h] [rbp-20h] BYREF

  v15 = 0;
  v12 = 0;
  *a5 = 0;
  v14 = 0;
  pclsid = 0;
  CLSIDFromString(a3, &pclsid);
  DWORD2(v14) = 0;
  *(_QWORD *)&v14 = &pclsid;
  v11 = &v14;
  lpVtbl = a2->lpVtbl;
  LODWORD(v15) = a4;
  v8 = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, __int128 **))lpVtbl->GetIDsFromNames)(a2, 1, &v11);
  if ( v8 >= 0 )
  {
    v13 = v12;
    v9 = *(_DWORD *)(v12 + 4);
    if ( v9 == 10 )
      v8 = -2147467259;
    else
      *a5 = HIWORD(v9);
    CMapiBuffer::~CMapiBuffer((CMapiBuffer *)&v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180034094  mov     [rsp-18h+arg_0], rbx
0x180034099  push    rbp
0x18003409a  push    rsi
0x18003409b  push    rdi
0x18003409c  mov     rbp, rsp
0x18003409f  sub     rsp, 80h
0x1800340a6  mov     rax, cs:__security_cookie
0x1800340ad  xor     rax, rsp
0x1800340b0  mov     [rbp+var_10], rax
0x1800340b4  mov     rsi, [rbp+arg_20]
0x1800340b8  xor     eax, eax
0x1800340ba  xorps   xmm0, xmm0
0x1800340bd  mov     [rbp+var_28], rax
0x1800340c1  mov     rdi, rdx
0x1800340c4  mov     [rbp+var_50], rax
0x1800340c8  lea     rdx, [rbp+pclsid]; pclsid
0x1800340cc  mov     [rbp+var_48], rax
0x1800340d0  mov     rcx, r8; lpsz
0x1800340d3  mov     [rsi], eax
0x1800340d5  mov     ebx, r9d
0x1800340d8  movups  [rbp+var_38], xmm0
0x1800340dc  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800340e0  call    cs:__imp_CLSIDFromString
0x1800340e6  lea     rax, [rbp+pclsid]
0x1800340ea  mov     dword ptr [rbp+var_38+8], 0
0x1800340f1  mov     qword ptr [rbp+var_38], rax
0x1800340f5  lea     rcx, [rbp+var_48]
0x1800340f9  lea     rax, [rbp+var_38]
0x1800340fd  mov     [rsp+80h+var_60], rcx
0x180034102  mov     [rbp+var_50], rax
0x180034106  lea     r8, [rbp+var_50]
0x18003410a  mov     rax, [rdi]
0x18003410d  xor     r9d, r9d
0x180034110  mov     rcx, rdi
0x180034113  mov     dword ptr [rbp+var_28], ebx
0x180034116  mov     rax, [rax+68h]
0x18003411a  lea     edx, [r9+1]
0x18003411e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034123  mov     ebx, eax
0x180034125  test    eax, eax
0x180034127  js      short loc_18003414E
0x180034129  mov     rcx, [rbp+var_48]
0x18003412d  mov     [rbp+var_40], rcx
0x180034131  mov     edx, [rcx+4]
0x180034134  cmp     edx, 0Ah
0x180034137  jz      short loc_180034140
0x180034139  shr     edx, 10h
0x18003413c  mov     [rsi], edx
0x18003413e  jmp     short loc_180034145
0x180034140  mov     ebx, 80004005h
0x180034145  lea     rcx, [rbp+var_40]; this
0x180034149  call    ??1CMapiBuffer@@QEAA@XZ; CMapiBuffer::~CMapiBuffer(void)
0x18003414e  mov     eax, ebx
0x180034150  mov     rcx, [rbp+var_10]
0x180034154  xor     rcx, rsp; StackCookie
0x180034157  call    __security_check_cookie
0x18003415c  mov     rbx, [rsp+80h+arg_0]
0x180034164  add     rsp, 80h
0x18003416b  pop     rdi
0x18003416c  pop     rsi
0x18003416d  pop     rbp
0x18003416e  retn
```
