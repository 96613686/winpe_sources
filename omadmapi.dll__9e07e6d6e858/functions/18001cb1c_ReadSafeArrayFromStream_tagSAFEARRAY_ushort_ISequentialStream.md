# ReadSafeArrayFromStream(tagSAFEARRAY * *,ushort,ISequentialStream *)

- ea: `0x18001cb1c`
- end: `0x18001cd48`
- name: `?ReadSafeArrayFromStream@@YAJPEAPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct tagSAFEARRAY **, unsigned __int16, struct ISequentialStream *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d1b0`

## callees

- `0x18001cb1c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cc56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cc56`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc48`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc48`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001cbb5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001cbb5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cc6a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001cc6a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cbd7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001cbd7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cc2b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001cc2b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001cccf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001cccf`

## pseudocode

```c
__int64 __fastcall ReadSafeArrayFromStream(struct tagSAFEARRAY **a1, VARTYPE a2, struct ISequentialStream *a3)
{
  SAFEARRAY *v3; // rsi
  OLECHAR *v4; // rdi
  HRESULT v8; // ebx
  SAFEARRAY *v9; // rax
  __int64 v11; // r15
  struct ISequentialStreamVtbl *lpVtbl; // rax
  BSTR v13; // rax
  UINT len; // [rsp+30h] [rbp-20h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-18h] BYREF
  void *ppvData; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+80h] [rbp+30h] BYREF
  ULONG v18; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v4 = 0;
  rgsabound = 0;
  ppvData = 0;
  len = 0;
  v18 = 0;
  v17 = 0;
  if ( !a1 || !a3 )
  {
    v8 = -2147467261;
    goto LABEL_16;
  }
  v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, __int64, int *))a3->lpVtbl->Read)(
         a3,
         &v18,
         4,
         &v17);
  if ( v8 >= 0 )
  {
    if ( v17 != 4 )
    {
LABEL_6:
      v8 = -2147467259;
      goto LABEL_16;
    }
    rgsabound.cElements = v18;
    rgsabound.lLbound = 0;
    v9 = SafeArrayCreate(a2, 1u, &rgsabound);
    v3 = v9;
    if ( !v9 )
    {
LABEL_8:
      v8 = -2147024882;
      goto LABEL_16;
    }
    v8 = SafeArrayAccessData(v9, &ppvData);
    if ( v8 >= 0 )
    {
      if ( a2 != 8 )
      {
        if ( a2 == 17 )
        {
          v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, void *, _QWORD, int *))a3->lpVtbl->Read)(
                 a3,
                 ppvData,
                 v18,
                 &v17);
          if ( v8 < 0 )
            goto LABEL_16;
          if ( v18 != v17 )
            goto LABEL_6;
        }
        goto LABEL_14;
      }
      v11 = 0;
      if ( !v18 )
      {
LABEL_14:
        v4 = 0;
        v8 = SafeArrayUnaccessData(v3);
        if ( v8 >= 0 )
        {
          *a1 = v3;
          v3 = 0;
        }
        goto LABEL_16;
      }
      while ( 1 )
      {
        lpVtbl = a3->lpVtbl;
        v17 = 0;
        v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, UINT *, __int64, int *))lpVtbl->Read)(
               a3,
               &len,
               4,
               &v17);
        if ( v8 < 0 )
          break;
        if ( v17 != 4 )
        {
          v8 = -2147467259;
          break;
        }
        v13 = SysAllocStringByteLen(0, len);
        v4 = v13;
        if ( !v13 )
          goto LABEL_8;
        v8 = ((__int64 (__fastcall *)(struct ISequentialStream *, BSTR, _QWORD, int *))a3->lpVtbl->Read)(
               a3,
               v13,
               len,
               &v17);
        if ( v8 < 0 )
          goto LABEL_16;
        if ( len != v17 )
          goto LABEL_6;
        v4[(unsigned __int64)len >> 1] = 0;
        *((_QWORD *)ppvData + v11) = v4;
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= v18 )
          goto LABEL_14;
      }
      v4 = 0;
    }
  }
LABEL_16:
  SysFreeString(v4);
  LocalFree(0);
  if ( v3 )
    SafeArrayDestroy(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001cb1c  mov     [rsp-28h+arg_8], rbx
0x18001cb21  mov     [rsp-28h+arg_10], rsi
0x18001cb26  push    rbp
0x18001cb27  push    rdi
0x18001cb28  push    r12
0x18001cb2a  push    r14
0x18001cb2c  push    r15
0x18001cb2e  mov     rbp, rsp
0x18001cb31  sub     rsp, 50h
0x18001cb35  xor     esi, esi
0x18001cb37  xor     edi, edi
0x18001cb39  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x18001cb3d  mov     r14, r8
0x18001cb40  mov     [rbp+ppvData], rsi
0x18001cb44  movzx   r15d, dx
0x18001cb48  mov     [rbp+len], esi
0x18001cb4b  mov     r12, rcx
0x18001cb4e  mov     [rbp+arg_18], esi
0x18001cb51  mov     [rbp+arg_0], esi
0x18001cb54  test    rcx, rcx
0x18001cb57  jnz     short loc_18001CB63
0x18001cb59  mov     ebx, 80004003h
0x18001cb5e  jmp     loc_18001CC45
0x18001cb63  test    r14, r14
0x18001cb66  jz      short loc_18001CB59
0x18001cb68  mov     rax, [r8]
0x18001cb6b  lea     r9, [rbp+arg_0]
0x18001cb6f  mov     r8d, 4
0x18001cb75  lea     rdx, [rbp+arg_18]
0x18001cb79  mov     rcx, r14
0x18001cb7c  mov     rax, [rax+18h]
0x18001cb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb85  mov     ebx, eax
0x18001cb87  test    eax, eax
0x18001cb89  js      loc_18001CC45
0x18001cb8f  cmp     [rbp+arg_0], 4
0x18001cb93  jz      short loc_18001CB9F
0x18001cb95  mov     ebx, 80004005h
0x18001cb9a  jmp     loc_18001CC45
0x18001cb9f  mov     eax, [rbp+arg_18]
0x18001cba2  lea     r8, [rbp+rgsabound]; rgsabound
0x18001cba6  mov     edx, 1; cDims
0x18001cbab  mov     [rbp+rgsabound.cElements], eax
0x18001cbae  movzx   ecx, r15w; vt
0x18001cbb2  mov     [rbp+rgsabound.lLbound], esi
0x18001cbb5  call    cs:__imp_SafeArrayCreate
0x18001cbbc  nop     dword ptr [rax+rax+00h]
0x18001cbc1  mov     rsi, rax
0x18001cbc4  test    rax, rax
0x18001cbc7  jnz     short loc_18001CBD0
0x18001cbc9  mov     ebx, 8007000Eh
0x18001cbce  jmp     short loc_18001CC45
0x18001cbd0  lea     rdx, [rbp+ppvData]; ppvData
0x18001cbd4  mov     rcx, rsi; psa
0x18001cbd7  call    cs:__imp_SafeArrayAccessData
0x18001cbde  nop     dword ptr [rax+rax+00h]
0x18001cbe3  mov     ebx, eax
0x18001cbe5  test    eax, eax
0x18001cbe7  js      short loc_18001CC45
0x18001cbe9  cmp     r15w, 8
0x18001cbee  jz      loc_18001CC92
0x18001cbf4  cmp     r15w, 11h
0x18001cbf9  jnz     short loc_18001CC28
0x18001cbfb  mov     rax, [r14]
0x18001cbfe  lea     r9, [rbp+arg_0]
0x18001cc02  mov     r8d, [rbp+arg_18]
0x18001cc06  mov     rcx, r14
0x18001cc09  mov     rdx, [rbp+ppvData]
0x18001cc0d  mov     rax, [rax+18h]
0x18001cc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc16  mov     ebx, eax
0x18001cc18  test    eax, eax
0x18001cc1a  js      short loc_18001CC45
0x18001cc1c  mov     eax, [rbp+arg_0]
0x18001cc1f  cmp     [rbp+arg_18], eax
0x18001cc22  jnz     loc_18001CB95
0x18001cc28  mov     rcx, rsi; psa
0x18001cc2b  call    cs:__imp_SafeArrayUnaccessData
0x18001cc32  nop     dword ptr [rax+rax+00h]
0x18001cc37  xor     edi, edi
0x18001cc39  mov     ebx, eax
0x18001cc3b  test    eax, eax
0x18001cc3d  js      short loc_18001CC45
0x18001cc3f  mov     [r12], rsi
0x18001cc43  xor     esi, esi
0x18001cc45  mov     rcx, rdi; bstrString
0x18001cc48  call    cs:__imp_SysFreeString
0x18001cc4f  nop     dword ptr [rax+rax+00h]
0x18001cc54  xor     ecx, ecx; hMem
0x18001cc56  call    cs:__imp_LocalFree
0x18001cc5d  nop     dword ptr [rax+rax+00h]
0x18001cc62  test    rsi, rsi
0x18001cc65  jz      short loc_18001CC76
0x18001cc67  mov     rcx, rsi; psa
0x18001cc6a  call    cs:__imp_SafeArrayDestroy
0x18001cc71  nop     dword ptr [rax+rax+00h]
0x18001cc76  lea     r11, [rsp+50h+var_s0]
0x18001cc7b  mov     eax, ebx
0x18001cc7d  mov     rbx, [r11+38h]
0x18001cc81  mov     rsi, [r11+40h]
0x18001cc85  mov     rsp, r11
0x18001cc88  pop     r15
0x18001cc8a  pop     r14
0x18001cc8c  pop     r12
0x18001cc8e  pop     rdi
0x18001cc8f  pop     rbp
0x18001cc90  retn
0x18001cc92  xor     r15d, r15d
0x18001cc95  cmp     [rbp+arg_18], edi
0x18001cc98  jbe     short loc_18001CC28
0x18001cc9a  mov     rax, [r14]
0x18001cc9d  lea     r9, [rbp+arg_0]
0x18001cca1  mov     r8d, 4
0x18001cca7  mov     [rbp+arg_0], 0
0x18001ccae  lea     rdx, [rbp+len]
0x18001ccb2  mov     rcx, r14
0x18001ccb5  mov     rax, [rax+18h]
0x18001ccb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccbe  mov     ebx, eax
0x18001ccc0  test    eax, eax
0x18001ccc2  js      short loc_18001CD41
0x18001ccc4  cmp     [rbp+arg_0], 4
0x18001ccc8  jnz     short loc_18001CD3C
0x18001ccca  mov     edx, [rbp+len]; len
0x18001cccd  xor     ecx, ecx; psz
0x18001cccf  call    cs:__imp_SysAllocStringByteLen
0x18001ccd6  nop     dword ptr [rax+rax+00h]
0x18001ccdb  mov     rdi, rax
0x18001ccde  test    rax, rax
0x18001cce1  jz      loc_18001CBC9
0x18001cce7  mov     rcx, [r14]
0x18001ccea  lea     r9, [rbp+arg_0]
0x18001ccee  mov     r8d, [rbp+len]
0x18001ccf2  mov     rdx, rdi
0x18001ccf5  mov     rax, [rcx+18h]
0x18001ccf9  mov     rcx, r14
0x18001ccfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd01  mov     ebx, eax
0x18001cd03  test    eax, eax
0x18001cd05  js      loc_18001CC45
0x18001cd0b  mov     eax, [rbp+len]
0x18001cd0e  cmp     eax, [rbp+arg_0]
0x18001cd11  jnz     loc_18001CB95
0x18001cd17  mov     ecx, eax
0x18001cd19  xor     eax, eax
0x18001cd1b  shr     rcx, 1
0x18001cd1e  mov     [rdi+rcx*2], ax
0x18001cd22  mov     rax, [rbp+ppvData]
0x18001cd26  mov     [rax+r15*8], rdi
0x18001cd2a  inc     r15d
0x18001cd2d  cmp     r15d, [rbp+arg_18]
0x18001cd31  jb      loc_18001CC9A
0x18001cd37  jmp     loc_18001CC28
0x18001cd3c  mov     ebx, 80004005h
0x18001cd41  xor     edi, edi
0x18001cd43  jmp     loc_18001CC45
```
