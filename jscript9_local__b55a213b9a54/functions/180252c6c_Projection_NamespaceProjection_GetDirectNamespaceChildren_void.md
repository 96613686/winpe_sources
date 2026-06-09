# Projection::NamespaceProjection::GetDirectNamespaceChildren(void)

- ea: `0x180252c6c`
- end: `0x180252ec3`
- name: `?GetDirectNamespaceChildren@NamespaceProjection@Projection@@AEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(Projection::NamespaceProjection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180252ed0`

## callees

- `0x18001689c`
- `0x180248ba0`
- `0x180252560`
- `0x180252c6c`
- `0x180253974`
- `0x180364010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180252d54`
- `msvcrt!wcscpy_s` at `0x180252d54`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252d7b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252da1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e1a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e30`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e6e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e84`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252d7b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252da1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e1a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e30`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e6e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180252e84`

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
  struct Js::RecyclableObject *v16; // r8
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-64h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-58h] BYREF
  LPVOID v21[2]; // [rsp+58h] [rbp-50h] BYREF
  _QWORD *v22; // [rsp+68h] [rbp-40h] BYREF
  char *(__fastcall *v23)(ArenaAllocator *__hidden, unsigned __int64); // [rsp+70h] [rbp-38h] BYREF
  int v24; // [rsp+78h] [rbp-30h]
  int v25; // [rsp+7Ch] [rbp-2Ch]

  v21[1] = (LPVOID)-2LL;
  try
  {
    RuntimeErrorWithScriptEnter = 0;
    v19 = 0;
    v18 = 0;
    pv = 0;
    v21[0] = 0;
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, LPVOID *, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)(*((_QWORD *)this + 8) + 40LL) + 48LL))(
               *(_QWORD *)(*((_QWORD *)this + 8) + 40LL),
               *((_QWORD *)this + 3),
               &RuntimeErrorWithScriptEnter,
               &v19,
               &v18,
               &pv,
               v21);
  }
  catch ( Js::InternalErrorException )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::OutOfMemoryException )
  {
    RuntimeErrorWithScriptEnter = -2147024882;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::StackOverflowException )
  {
    RuntimeErrorWithScriptEnter = -2146828260;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::NotImplementedException )
  {
    RuntimeErrorWithScriptEnter = -2147467263;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::ScriptAbortException )
  {
    RuntimeErrorWithScriptEnter = -2147467260;
    return RuntimeErrorWithScriptEnter;
  }
  catch ( Js::JavascriptExceptionObject *v22 )
  {
    if ( *v22
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v22) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v16) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v16, 0);
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147024882;
    }
    return RuntimeErrorWithScriptEnter;
  }
  catch ( ... )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
    return RuntimeErrorWithScriptEnter;
  }
  v2 = result;
  if ( (int)result >= 0 )
  {
    v3 = 0;
    v4 = v25;
    while ( v3 < v18 )
    {
      v5 = (wchar_t *)*((_QWORD *)pv + v3);
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
      v7 = v6 + 1;
      v23 = ArenaAllocator::Alloc;
      v24 = 0;
      v25 = v4;
      v8 = (wchar_t *)AllocateArray<ArenaAllocator,unsigned short,0>(
                        *(_QWORD *)(*((_QWORD *)this + 8) + 24LL),
                        &v23,
                        v6 + 1);
      wcscpy_s(v8, v7, v5);
      *((_QWORD *)this + 4) = regex::ImmutableList<ProjectionModel::Property const *>::Prepend(
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
        CoTaskMemFree(v19);
        v19 = 0;
        CoTaskMemFree(v21[0]);
        return (unsigned int)v2;
      }
      v2 = Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(
             this,
             *((struct IUnknown **)v19 + i),
             *((_DWORD *)v21[0] + i));
      if ( v2 < 0 )
        break;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 + i) + 16LL))(*((_QWORD *)v19 + i));
    }
    v10 = v19;
    v11 = (char *)v19 + 8 * i;
    v12 = RuntimeErrorWithScriptEnter - i;
    for ( j = 0; j < v12; ++j )
    {
      v14 = *(_QWORD *)&v11[8 * j];
      if ( v14 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14 + 16LL))(*(_QWORD *)&v11[8 * j]);
        v10 = v19;
      }
    }
    CoTaskMemFree(v10);
    v19 = 0;
    CoTaskMemFree(v21[0]);
    return (unsigned int)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180252c6c  mov     r11, rsp
0x180252c6f  mov     [r11+8], rcx
0x180252c73  push    rdi
0x180252c74  push    r12
0x180252c76  push    r13
0x180252c78  push    r14
0x180252c7a  push    r15
0x180252c7c  sub     rsp, 80h
0x180252c83  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180252c8b  mov     [r11+10h], rbx
0x180252c8f  mov     [r11+18h], rsi
0x180252c93  xor     r13d, r13d
0x180252c96  mov     [r11-68h], r13d
0x180252c9a  mov     [r11-60h], r13
0x180252c9e  mov     [r11-64h], r13d
0x180252ca2  mov     [r11-58h], r13
0x180252ca6  mov     [r11-50h], r13
0x180252caa  mov     r14, rcx
0x180252cad  mov     rax, [rcx+40h]
0x180252cb1  mov     rcx, [rax+28h]
0x180252cb5  mov     rax, [rcx]
0x180252cb8  lea     rdx, [r11-50h]
0x180252cbc  mov     [r11-78h], rdx
0x180252cc0  lea     rdx, [r11-58h]
0x180252cc4  mov     [r11-80h], rdx
0x180252cc8  lea     rdx, [r11-64h]
0x180252ccc  mov     [rsp+0A8h+var_88], rdx
0x180252cd1  lea     r9, [r11-60h]
0x180252cd5  lea     r8, [r11-68h]
0x180252cd9  mov     rdx, [r14+18h]
0x180252cdd  mov     rax, [rax+30h]
0x180252ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180252ce6  mov     edi, eax
0x180252ce8  test    eax, eax
0x180252cea  js      loc_180252EA5
0x180252cf0  mov     esi, r13d
0x180252cf3  mov     ebx, [rsp+0A8h+var_2C]
0x180252cf7  cmp     esi, [rsp+0A8h+var_64]
0x180252cfb  jnb     loc_180252D9C
0x180252d01  mov     ecx, esi
0x180252d03  mov     rax, [rsp+0A8h+pv]
0x180252d08  mov     r15, [rax+rcx*8]
0x180252d0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180252d10  inc     rax
0x180252d13  cmp     [r15+rax*2], r13w
0x180252d18  jnz     short loc_180252D10
0x180252d1a  lea     r12, [rax+1]
0x180252d1e  lea     rax, ?Alloc@ArenaAllocator@@QEAAPEAD_K@Z; ArenaAllocator::Alloc(unsigned __int64)
0x180252d25  mov     [rsp+0A8h+var_38], rax
0x180252d2a  mov     [rsp+0A8h+var_30], r13d
0x180252d2f  mov     [rsp+0A8h+var_2C], ebx
0x180252d33  mov     rcx, [r14+40h]
0x180252d37  mov     r8, r12
0x180252d3a  lea     rdx, [rsp+0A8h+var_38]
0x180252d3f  mov     rcx, [rcx+18h]
0x180252d43  call    ??$AllocateArray@VArenaAllocator@@G$0A@@@YAPEAGPEAVArenaAllocator@@P80@EAAPEAD_K@Z1@Z; AllocateArray<ArenaAllocator,ushort,0>(ArenaAllocator *,char * (ArenaAllocator::*)(unsigned __int64),unsigned __int64)
0x180252d48  mov     r13, rax
0x180252d4b  mov     r8, r15; Source
0x180252d4e  mov     rdx, r12; SizeInWords
0x180252d51  mov     rcx, rax; Destination
0x180252d54  call    cs:__imp_wcscpy_s
0x180252d5b  nop     dword ptr [rax+rax+00h]
0x180252d60  mov     r8, [r14+40h]
0x180252d64  mov     r8, [r8+18h]
0x180252d68  mov     rdx, r13
0x180252d6b  mov     rcx, [r14+20h]
0x180252d6f  call    ?Prepend@?$ImmutableList@PEBUProperty@ProjectionModel@@@regex@@QEAAPEAV12@PEBUProperty@ProjectionModel@@PEAVArenaAllocator@@@Z; regex::ImmutableList<ProjectionModel::Property const *>::Prepend(ProjectionModel::Property const *,ArenaAllocator *)
0x180252d74  mov     [r14+20h], rax
0x180252d78  mov     rcx, r15; pv
0x180252d7b  call    cs:__imp_CoTaskMemFree
0x180252d82  nop     dword ptr [rax+rax+00h]
0x180252d87  mov     rax, [rsp+0A8h+pv]
0x180252d8c  mov     ecx, esi
0x180252d8e  xor     r13d, r13d
0x180252d91  mov     [rax+rcx*8], r13
0x180252d95  inc     esi
0x180252d97  jmp     loc_180252CF7
0x180252d9c  mov     rcx, [rsp+0A8h+pv]; pv
0x180252da1  call    cs:__imp_CoTaskMemFree
0x180252da8  nop     dword ptr [rax+rax+00h]
0x180252dad  mov     [rsp+0A8h+pv], r13
0x180252db2  mov     ebx, r13d
0x180252db5  cmp     ebx, [rsp+0A8h+var_68]
0x180252db9  jnb     loc_180252E5C
0x180252dbf  mov     esi, ebx
0x180252dc1  mov     r8, [rsp+0A8h+var_50]
0x180252dc6  mov     r8d, [r8+rsi*4]; int
0x180252dca  mov     rdx, [rsp+0A8h+var_60]
0x180252dcf  mov     rdx, [rdx+rsi*8]; struct IUnknown *
0x180252dd3  mov     rcx, r14; this
0x180252dd6  call    ?AddDirectChildTypesFromMetadata@NamespaceProjection@Projection@@AEAAJPEAUIUnknown@@H@Z; Projection::NamespaceProjection::AddDirectChildTypesFromMetadata(IUnknown *,int)
0x180252ddb  mov     edi, eax
0x180252ddd  test    eax, eax
0x180252ddf  jns     short loc_180252E40
0x180252de1  mov     rcx, [rsp+0A8h+var_60]; pv
0x180252de6  lea     r14, [rcx+rsi*8]
0x180252dea  mov     esi, [rsp+0A8h+var_68]
0x180252dee  sub     esi, ebx
0x180252df0  mov     ebx, r13d
0x180252df3  cmp     ebx, esi
0x180252df5  jnb     short loc_180252E1A
0x180252df7  mov     eax, ebx
0x180252df9  mov     rdx, [r14+rax*8]
0x180252dfd  test    rdx, rdx
0x180252e00  jz      short loc_180252E16
0x180252e02  mov     rax, [rdx]
0x180252e05  mov     rcx, rdx
0x180252e08  mov     rax, [rax+10h]
0x180252e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180252e11  mov     rcx, [rsp+0A8h+var_60]
0x180252e16  inc     ebx
0x180252e18  jmp     short loc_180252DF3
0x180252e1a  call    cs:__imp_CoTaskMemFree
0x180252e21  nop     dword ptr [rax+rax+00h]
0x180252e26  mov     [rsp+0A8h+var_60], r13
0x180252e2b  mov     rcx, [rsp+0A8h+var_50]; pv
0x180252e30  call    cs:__imp_CoTaskMemFree
0x180252e37  nop     dword ptr [rax+rax+00h]
0x180252e3c  mov     eax, edi
0x180252e3e  jmp     short loc_180252EA5
0x180252e40  mov     rax, [rsp+0A8h+var_60]
0x180252e45  mov     rcx, [rax+rsi*8]
0x180252e49  mov     rax, [rcx]
0x180252e4c  mov     rax, [rax+10h]
0x180252e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180252e55  inc     ebx
0x180252e57  jmp     loc_180252DB5
0x180252e5c  mov     rcx, [r14+20h]
0x180252e60  call    ?SortCurrentList@?$ImmutableList@PEBG@regex@@QEAAPEAV12@PEAU?$Comparer@PEAPEBG@2@@Z; regex::ImmutableList<ushort const *>::SortCurrentList(regex::Comparer<ushort const * *> *)
0x180252e65  mov     [r14+20h], rax
0x180252e69  mov     rcx, [rsp+0A8h+var_60]; pv
0x180252e6e  call    cs:__imp_CoTaskMemFree
0x180252e75  nop     dword ptr [rax+rax+00h]
0x180252e7a  mov     [rsp+0A8h+var_60], r13
0x180252e7f  mov     rcx, [rsp+0A8h+var_50]; pv
0x180252e84  call    cs:__imp_CoTaskMemFree
0x180252e8b  nop     dword ptr [rax+rax+00h]
0x180252e90  nop
0x180252e91  jmp     short loc_180252EA3
0x180252e93  jmp     short loc_180252E9F
0x180252e95  jmp     short loc_180252E9F
0x180252e97  jmp     short loc_180252E9F
0x180252e99  jmp     short loc_180252E9F
0x180252e9b  jmp     short loc_180252E9F
0x180252e9d  jmp     short $+2
0x180252e9f  mov     edi, [rsp+0A8h+var_68]
0x180252ea3  mov     eax, edi
0x180252ea5  lea     r11, [rsp+0A8h+var_28]
0x180252ead  mov     rbx, [r11+38h]
0x180252eb1  mov     rsi, [r11+40h]
0x180252eb5  mov     rsp, r11
0x180252eb8  pop     r15
0x180252eba  pop     r14
0x180252ebc  pop     r13
0x180252ebe  pop     r12
0x180252ec0  pop     rdi
0x180252ec1  retn
```
