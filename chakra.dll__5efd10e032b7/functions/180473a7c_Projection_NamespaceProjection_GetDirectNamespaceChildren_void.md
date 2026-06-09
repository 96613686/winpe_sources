# Projection::NamespaceProjection::GetDirectNamespaceChildren(void)

- ea: `0x180473a7c`
- end: `0x180473cd1`
- name: `?GetDirectNamespaceChildren@NamespaceProjection@Projection@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(Projection::NamespaceProjection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180473ce0`

## callees

- `0x1800981b4`
- `0x1803f209c`
- `0x1803f25ac`
- `0x180473a7c`
- `0x1804743b8`
- `0x1805cd010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180473b64`
- `msvcrt!wcscpy_s` at `0x180473b64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473b8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180473c94`

## pseudocode

```c
__int64 __fastcall Projection::NamespaceProjection::GetDirectNamespaceChildren(Projection::NamespaceProjection *this)
{
  int v2; // edi
  unsigned int v3; // esi
  int v4; // ebx
  wchar_t *v5; // r15
  __int64 v6; // rax
  rsize_t v7; // r12
  wchar_t *v8; // r13
  unsigned int i; // ebx
  void *v10; // rcx
  char *v11; // r14
  unsigned int v12; // esi
  unsigned int j; // ebx
  __int64 v14; // rdx
  __int64 result; // rax
  void **v16; // rax
  void *v17; // rdx
  struct Js::RecyclableObject *v18; // rax
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-64h] BYREF
  LPVOID v21; // [rsp+48h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-58h] BYREF
  LPVOID v23[2]; // [rsp+58h] [rbp-50h] BYREF
  const Js::JavascriptException *v24; // [rsp+68h] [rbp-40h] BYREF
  char *(__fastcall *v25)(Memory::ArenaAllocator *__hidden, unsigned __int64); // [rsp+70h] [rbp-38h] BYREF
  int v26; // [rsp+78h] [rbp-30h]
  int v27; // [rsp+7Ch] [rbp-2Ch]

  v23[1] = (LPVOID)-2LL;
  try
  {
    RuntimeErrorWithScriptEnter = 0;
    v21 = 0;
    v20 = 0;
    pv = 0;
    v23[0] = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, LPVOID *, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 8) + 40LL) + 48LL))(
               *(_QWORD *)(*((_QWORD *)this + 8) + 40LL),
               *((_QWORD *)this + 3),
               &RuntimeErrorWithScriptEnter,
               &v21,
               &v20,
               &pv,
               v23);
  }
  catch ( Js::OutOfMemoryException )
  {
    return (unsigned int)-2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    return (unsigned int)-2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    return (unsigned int)-2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    return (unsigned int)-2147467260;
  }
  catch ( Js::AsmJsParseException )
  {
    return (unsigned int)-2146823140;
  }
  catch ( const Js::JavascriptException *v24 )
  {
    v16 = (void **)Js::JavascriptException::GetAndClear(v24);
    if ( !*v16 )
      return (unsigned int)-2147024882;
    if ( !Js::JavascriptError::Is(*v16) && !Js::JavascriptError::IsRemoteError(v17) )
      return (unsigned int)-2146823266;
    v18 = Js::RecyclableObject::FromVar(v17);
    RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v18, 0);
    return RuntimeErrorWithScriptEnter;
  }
  catch ( ... )
  {
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x1805C5BBBLL);
  }
  v2 = result;
  if ( (int)result >= 0 )
  {
    v3 = 0;
    v4 = v27;
    while ( v3 < v20 )
    {
      v5 = (wchar_t *)*((_QWORD *)pv + v3);
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      v7 = v6 + 1;
      v25 = Memory::ArenaAllocator::Alloc;
      v26 = 0;
      v27 = v4;
      v8 = (wchar_t *)Memory::AllocateArray<Memory::Recycler,unsigned short,0>(
                        *(_QWORD *)(*((_QWORD *)this + 8) + 24LL),
                        &v25,
                        v6 + 1);
      wcscpy_s(v8, v7, v5);
      *((_QWORD *)this + 4) = regex::ImmutableList<regex::ImmutableList<ProjectionModel::AbiMethodSignature const *> *>::Prepend(
                                *((_QWORD *)this + 4),
                                v8,
                                *(_QWORD *)(*((_QWORD *)this + 8) + 24LL));
      CoTaskMemFree(v5);
      *((_QWORD *)pv + v3++) = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= RuntimeErrorWithScriptEnter )
      {
        *((_QWORD *)this + 4) = regex::ImmutableList<unsigned short const *>::SortCurrentList(*((_QWORD *)this + 4));
        CoTaskMemFree(v21);
        v21 = 0;
        CoTaskMemFree(v23[0]);
        return (unsigned int)v2;
      }
      v2 = Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(
             this,
             *((struct IUnknown **)v21 + i),
             *((_DWORD *)v23[0] + i));
      if ( v2 < 0 )
        break;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 + i) + 16LL))(*((_QWORD *)v21 + i));
    }
    v10 = v21;
    v11 = (char *)v21 + 8 * i;
    v12 = RuntimeErrorWithScriptEnter - i;
    for ( j = 0; j < v12; ++j )
    {
      v14 = *(_QWORD *)&v11[8 * j];
      if ( v14 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 16LL))(*(_QWORD *)&v11[8 * j]);
        v10 = v21;
      }
    }
    CoTaskMemFree(v10);
    v21 = 0;
    CoTaskMemFree(v23[0]);
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180473a7c  mov     r11, rsp
0x180473a7f  mov     [r11+8], rcx
0x180473a83  push    rdi
0x180473a84  push    r12
0x180473a86  push    r13
0x180473a88  push    r14
0x180473a8a  push    r15
0x180473a8c  sub     rsp, 80h
0x180473a93  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180473a9b  mov     [r11+10h], rbx
0x180473a9f  mov     [r11+18h], rsi
0x180473aa3  xor     r13d, r13d
0x180473aa6  mov     [r11-68h], r13d
0x180473aaa  mov     [r11-60h], r13
0x180473aae  mov     [r11-64h], r13d
0x180473ab2  mov     [r11-58h], r13
0x180473ab6  mov     [r11-50h], r13
0x180473aba  mov     r14, rcx
0x180473abd  mov     rax, [rcx+40h]
0x180473ac1  mov     rcx, [rax+28h]
0x180473ac5  mov     rax, [rcx]
0x180473ac8  lea     rdx, [r11-50h]
0x180473acc  mov     [r11-78h], rdx
0x180473ad0  lea     rdx, [r11-58h]
0x180473ad4  mov     [r11-80h], rdx
0x180473ad8  lea     rdx, [r11-64h]
0x180473adc  mov     [rsp+0A8h+var_88], rdx
0x180473ae1  lea     r9, [r11-60h]
0x180473ae5  lea     r8, [r11-68h]
0x180473ae9  mov     rdx, [r14+18h]
0x180473aed  mov     rax, [rax+30h]
0x180473af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473af6  mov     edi, eax
0x180473af8  test    eax, eax
0x180473afa  js      loc_180473CB3
0x180473b00  mov     esi, r13d
0x180473b03  mov     ebx, [rsp+0A8h+var_2C]
0x180473b07  cmp     esi, [rsp+0A8h+var_64]
0x180473b0b  jnb     loc_180473BAC
0x180473b11  mov     ecx, esi
0x180473b13  mov     rax, [rsp+0A8h+pv]
0x180473b18  mov     r15, [rax+rcx*8]
0x180473b1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180473b20  inc     rax
0x180473b23  cmp     [r15+rax*2], r13w
0x180473b28  jnz     short loc_180473B20
0x180473b2a  lea     r12, [rax+1]
0x180473b2e  lea     rax, ?Alloc@ArenaAllocator@Memory@@QEAAPEAD_K@Z; Memory::ArenaAllocator::Alloc(unsigned __int64)
0x180473b35  mov     [rsp+0A8h+var_38], rax
0x180473b3a  mov     [rsp+0A8h+var_30], r13d
0x180473b3f  mov     [rsp+0A8h+var_2C], ebx
0x180473b43  mov     rcx, [r14+40h]
0x180473b47  mov     r8, r12
0x180473b4a  lea     rdx, [rsp+0A8h+var_38]
0x180473b4f  mov     rcx, [rcx+18h]
0x180473b53  call    ??$AllocateArray@VRecycler@Memory@@G$0A@@Memory@@YAPEAGPEAVRecycler@0@P810@EAAPEAD_K@Z1@Z; Memory::AllocateArray<Memory::Recycler,ushort,0>(Memory::Recycler *,char * (Memory::Recycler::*)(unsigned __int64),unsigned __int64)
0x180473b58  mov     r13, rax
0x180473b5b  mov     r8, r15; Source
0x180473b5e  mov     rdx, r12; SizeInWords
0x180473b61  mov     rcx, rax; Destination
0x180473b64  call    cs:__imp_wcscpy_s
0x180473b6b  nop     dword ptr [rax+rax+00h]
0x180473b70  mov     r8, [r14+40h]
0x180473b74  mov     r8, [r8+18h]
0x180473b78  mov     rdx, r13
0x180473b7b  mov     rcx, [r14+20h]
0x180473b7f  call    ?Prepend@?$ImmutableList@PEAV?$ImmutableList@PEBUAbiMethodSignature@ProjectionModel@@@regex@@@regex@@QEAAPEAV12@PEAV?$ImmutableList@PEBUAbiMethodSignature@ProjectionModel@@@2@PEAVArenaAllocator@Memory@@@Z; regex::ImmutableList<regex::ImmutableList<ProjectionModel::AbiMethodSignature const *> *>::Prepend(regex::ImmutableList<ProjectionModel::AbiMethodSignature const *> *,Memory::ArenaAllocator *)
0x180473b84  mov     [r14+20h], rax
0x180473b88  mov     rcx, r15; pv
0x180473b8b  call    cs:__imp_CoTaskMemFree
0x180473b92  nop     dword ptr [rax+rax+00h]
0x180473b97  mov     rax, [rsp+0A8h+pv]
0x180473b9c  mov     ecx, esi
0x180473b9e  xor     r13d, r13d
0x180473ba1  mov     [rax+rcx*8], r13
0x180473ba5  inc     esi
0x180473ba7  jmp     loc_180473B07
0x180473bac  mov     rcx, [rsp+0A8h+pv]; pv
0x180473bb1  call    cs:__imp_CoTaskMemFree
0x180473bb8  nop     dword ptr [rax+rax+00h]
0x180473bbd  mov     [rsp+0A8h+pv], r13
0x180473bc2  mov     ebx, r13d
0x180473bc5  cmp     ebx, [rsp+0A8h+var_68]
0x180473bc9  jnb     loc_180473C6C
0x180473bcf  mov     esi, ebx
0x180473bd1  mov     r8, [rsp+0A8h+var_50]
0x180473bd6  mov     r8d, [r8+rsi*4]; int
0x180473bda  mov     rdx, [rsp+0A8h+var_60]
0x180473bdf  mov     rdx, [rdx+rsi*8]; struct IUnknown *
0x180473be3  mov     rcx, r14; this
0x180473be6  call    ?AddDirectChildTypesFromMetadata@NamespaceProjection@Projection@@AEAAJPEAUIUnknown@@H@Z; Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(IUnknown *,int)
0x180473beb  mov     edi, eax
0x180473bed  test    eax, eax
0x180473bef  jns     short loc_180473C50
0x180473bf1  mov     rcx, [rsp+0A8h+var_60]; pv
0x180473bf6  lea     r14, [rcx+rsi*8]
0x180473bfa  mov     esi, [rsp+0A8h+var_68]
0x180473bfe  sub     esi, ebx
0x180473c00  mov     ebx, r13d
0x180473c03  cmp     ebx, esi
0x180473c05  jnb     short loc_180473C2A
0x180473c07  mov     eax, ebx
0x180473c09  mov     rdx, [r14+rax*8]
0x180473c0d  test    rdx, rdx
0x180473c10  jz      short loc_180473C26
0x180473c12  mov     rax, [rdx]
0x180473c15  mov     rcx, rdx
0x180473c18  mov     rax, [rax+10h]
0x180473c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473c21  mov     rcx, [rsp+0A8h+var_60]
0x180473c26  inc     ebx
0x180473c28  jmp     short loc_180473C03
0x180473c2a  call    cs:__imp_CoTaskMemFree
0x180473c31  nop     dword ptr [rax+rax+00h]
0x180473c36  mov     [rsp+0A8h+var_60], r13
0x180473c3b  mov     rcx, [rsp+0A8h+var_50]; pv
0x180473c40  call    cs:__imp_CoTaskMemFree
0x180473c47  nop     dword ptr [rax+rax+00h]
0x180473c4c  mov     eax, edi
0x180473c4e  jmp     short loc_180473CB3
0x180473c50  mov     rax, [rsp+0A8h+var_60]
0x180473c55  mov     rcx, [rax+rsi*8]
0x180473c59  mov     rax, [rcx]
0x180473c5c  mov     rax, [rax+10h]
0x180473c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473c65  inc     ebx
0x180473c67  jmp     loc_180473BC5
0x180473c6c  mov     rcx, [r14+20h]
0x180473c70  call    ?SortCurrentList@?$ImmutableList@PEBG@regex@@QEAAPEAV12@PEAU?$Comparer@PEAPEBG@2@@Z; regex::ImmutableList<ushort const *>::SortCurrentList(regex::Comparer<ushort const * *> *)
0x180473c75  mov     [r14+20h], rax
0x180473c79  mov     rcx, [rsp+0A8h+var_60]; pv
0x180473c7e  call    cs:__imp_CoTaskMemFree
0x180473c85  nop     dword ptr [rax+rax+00h]
0x180473c8a  mov     [rsp+0A8h+var_60], r13
0x180473c8f  mov     rcx, [rsp+0A8h+var_50]; pv
0x180473c94  call    cs:__imp_CoTaskMemFree
0x180473c9b  nop     dword ptr [rax+rax+00h]
0x180473ca0  nop
0x180473ca1  jmp     short loc_180473CB1
0x180473ca3  jmp     short loc_180473CAD
0x180473ca5  jmp     short loc_180473CAD
0x180473ca7  jmp     short loc_180473CAD
0x180473ca9  jmp     short loc_180473CAD
0x180473cab  jmp     short $+2
0x180473cad  mov     edi, [rsp+0A8h+var_68]
0x180473cb1  mov     eax, edi
0x180473cb3  lea     r11, [rsp+0A8h+var_28]
0x180473cbb  mov     rbx, [r11+38h]
0x180473cbf  mov     rsi, [r11+40h]
0x180473cc3  mov     rsp, r11
0x180473cc6  pop     r15
0x180473cc8  pop     r14
0x180473cca  pop     r13
0x180473ccc  pop     r12
0x180473cce  pop     rdi
0x180473ccf  retn
```
