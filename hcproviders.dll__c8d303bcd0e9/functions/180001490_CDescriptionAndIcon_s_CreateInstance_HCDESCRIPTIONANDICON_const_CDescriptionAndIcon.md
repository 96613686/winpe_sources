# CDescriptionAndIcon::s_CreateInstance(HCDESCRIPTIONANDICON const *,CDescriptionAndIcon * *)

- ea: `0x180001490`
- end: `0x1800015a5`
- name: `?s_CreateInstance@CDescriptionAndIcon@@SAJPEBUHCDESCRIPTIONANDICON@@PEAPEAV1@@Z`
- size: `277`
- prototype: `__int64 __fastcall(const struct HCDESCRIPTIONANDICON *, struct CDescriptionAndIcon **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009a10`

## callees

- `0x180001490`
- `0x180001ea0`
- `0x18000206c`
- `0x1800021b0`
- `0x180002eb0`
- `0x180004a4c`
- `0x180004fc8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001530`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001530`

## pseudocode

```c
__int64 __fastcall CDescriptionAndIcon::s_CreateInstance(char **a1, unsigned __int16 ***a2)
{
  CDescriptionAndIcon *v4; // rax
  CDescriptionAndIcon *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 **v8; // rbx
  char *v9; // r8
  _QWORD *v10; // rdi
  unsigned int v11; // edi
  __int64 result; // rax
  int StringW; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int Error; // eax
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-18h]
  char *Buffer; // [rsp+50h] [rbp+18h] BYREF

  v4 = (CDescriptionAndIcon *)operator new(0x20u);
  if ( !v4 )
    return 2147942414LL;
  v5 = CDescriptionAndIcon::CDescriptionAndIcon(v4);
  v8 = (unsigned __int16 **)v5;
  if ( !v5 )
    return 2147942414LL;
  v9 = *a1;
  v10 = (_QWORD *)((char *)v5 + 16);
  *((_QWORD *)v5 + 2) = 0;
  if ( v9 )
  {
    if ( (unsigned __int64)v9 >= 0x10000 )
    {
      Error = _AllocString<CTCoAllocPolicy>(v7, v6, v9, v10);
    }
    else
    {
      Buffer = 0;
      StringW = LoadStringW(g_hinst, (UINT)v9, (LPWSTR)&Buffer, 0);
      if ( StringW <= 0 )
        Error = ResultFromKnownLastError();
      else
        Error = _AllocStringWorker<CTCoAllocPolicy>(v15, v14, Buffer, StringW, v18, v10);
    }
    v11 = Error;
    if ( Error >= 0 )
    {
      LOBYTE(v17) = 1;
      result = LoadStringHelper(a1[1], v17, v8 + 3);
      v11 = result;
      if ( (int)result >= 0 )
      {
        *a2 = v8;
        return result;
      }
    }
  }
  else
  {
    v11 = -2147467259;
  }
  (*((void (__fastcall **)(unsigned __int16 **))*v8 + 2))(v8);
  return v11;
}

```

## disassembly

```asm
0x180001490  mov     [rsp+arg_8], rbx
0x180001495  mov     [rsp+arg_18], rsi
0x18000149a  push    r14
0x18000149c  sub     rsp, 30h
0x1800014a0  mov     rsi, rcx
0x1800014a3  mov     r14, rdx
0x1800014a6  mov     ecx, 20h ; ' '; Size
0x1800014ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800014b0  test    rax, rax
0x1800014b3  jz      loc_18000158E
0x1800014b9  mov     rcx, rax; this
0x1800014bc  call    ??0CDescriptionAndIcon@@AEAA@XZ; CDescriptionAndIcon::CDescriptionAndIcon(void)
0x1800014c1  mov     rbx, rax
0x1800014c4  test    rax, rax
0x1800014c7  jz      loc_18000158E
0x1800014cd  mov     r8, [rsi]
0x1800014d0  mov     [rsp+38h+arg_0], rdi
0x1800014d5  lea     rdi, [rax+10h]
0x1800014d9  xor     eax, eax
0x1800014db  mov     [rdi], rax
0x1800014de  test    r8, r8
0x1800014e1  jnz     short loc_180001510
0x1800014e3  mov     edi, 80004005h
0x1800014e8  mov     rax, [rbx]
0x1800014eb  mov     rcx, rbx
0x1800014ee  mov     rax, [rax+10h]
0x1800014f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f7  mov     eax, edi
0x1800014f9  mov     rdi, [rsp+38h+arg_0]
0x1800014fe  mov     rbx, [rsp+38h+arg_8]
0x180001503  mov     rsi, [rsp+38h+arg_18]
0x180001508  add     rsp, 30h
0x18000150c  pop     r14
0x18000150e  retn
0x180001510  cmp     r8, 10000h
0x180001517  jnb     short loc_18000155B
0x180001519  mov     rcx, cs:g_hinst; hInstance
0x180001520  mov     edx, r8d; uID
0x180001523  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x180001528  mov     [rsp+38h+Buffer], rax
0x18000152d  xor     r9d, r9d; cchBufferMax
0x180001530  call    cs:__imp_LoadStringW
0x180001537  nop     dword ptr [rax+rax+00h]
0x18000153c  test    eax, eax
0x18000153e  jle     short loc_180001554
0x180001540  mov     r8, [rsp+38h+Buffer]
0x180001545  movsxd  r9, eax
0x180001548  mov     [rsp+38h+var_10], rdi
0x18000154d  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180001552  jmp     short loc_180001563
0x180001554  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180001559  jmp     short loc_180001563
0x18000155b  mov     r9, rdi
0x18000155e  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180001563  mov     edi, eax
0x180001565  test    eax, eax
0x180001567  js      loc_1800014E8
0x18000156d  mov     rcx, [rsi+8]; uID
0x180001571  lea     r8, [rbx+18h]; unsigned __int16 **
0x180001575  mov     dl, 1; bool
0x180001577  call    ?LoadStringHelper@@YAJPEBG_NPEAPEAG@Z; LoadStringHelper(ushort const *,bool,ushort * *)
0x18000157c  mov     edi, eax
0x18000157e  test    eax, eax
0x180001580  js      loc_1800014E8
0x180001586  mov     [r14], rbx
0x180001589  jmp     loc_1800014F9
0x18000158e  mov     rbx, [rsp+38h+arg_8]
0x180001593  mov     eax, 8007000Eh
0x180001598  mov     rsi, [rsp+38h+arg_18]
0x18000159d  add     rsp, 30h
0x1800015a1  pop     r14
0x1800015a3  retn
```
