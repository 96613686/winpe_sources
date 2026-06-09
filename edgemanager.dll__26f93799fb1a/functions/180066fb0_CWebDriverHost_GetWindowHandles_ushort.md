# CWebDriverHost::_GetWindowHandles(ushort * *)

- ea: `0x180066fb0`
- end: `0x180067095`
- name: `?_GetWindowHandles@CWebDriverHost@@AEAAJPEAPEAG@Z`
- size: `229`
- prototype: `__int64 __fastcall(CWebDriverHost *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180065cd0`

## callees

- `0x18002b560`
- `0x18002ba84`
- `0x180038c34`
- `0x180066a44`
- `0x180066fb0`
- `0x1800794dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006707a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006707a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066fd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006705a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006705a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWebDriverHost::_GetWindowHandles(CWebDriverHost *this, unsigned __int16 **a2)
{
  CWebDriverHost *v4; // rcx
  const unsigned __int16 **v5; // rdi
  __int64 v6; // rbp
  __int64 v7; // rdx
  __int64 i; // rsi
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+48h] [rbp+10h]

  *a2 = 0;
  EnterCriticalSection(&stru_1800B6EB0);
  v11 = &stru_1800B6EB0;
  v5 = (const unsigned __int16 **)operator new[](saturated_mul((unsigned int)(*((_DWORD *)this + 26) - 1), 8u));
  v6 = 0;
  v7 = **((_QWORD **)this + 11);
  v10 = v7;
  while ( v7 != *((_QWORD *)this + 11) )
  {
    v5[v6] = CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(v4, *(_DWORD *)(v7 + 28));
    v6 = (unsigned int)(v6 + 1);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned long>>>,std::_Iterator_base0>::operator++(&v10);
    v7 = v10;
  }
  GenerateStringArrayResponse(*((const unsigned __int16 **)this + 22), v6, v5, a2);
  for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
  {
    CoTaskMemFree((LPVOID)v5[i]);
    v5[i] = 0;
  }
  operator delete(v5);
  LeaveCriticalSection(&stru_1800B6EB0);
  return 0;
}

```

## disassembly

```asm
0x180066fb0  mov     [rsp+arg_10], rbx
0x180066fb5  mov     [rsp+arg_18], rbp
0x180066fba  push    rsi
0x180066fbb  push    rdi
0x180066fbc  push    r14
0x180066fbe  sub     rsp, 20h
0x180066fc2  mov     rsi, rdx
0x180066fc5  mov     rbx, rcx
0x180066fc8  mov     qword ptr [rdx], 0
0x180066fcf  lea     r14, stru_1800B6EB0
0x180066fd6  mov     rcx, r14; lpCriticalSection
0x180066fd9  call    cs:__imp_EnterCriticalSection
0x180066fdf  mov     [rsp+38h+arg_8], r14
0x180066fe4  mov     r8d, [rbx+68h]
0x180066fe8  dec     r8d
0x180066feb  mov     eax, 8
0x180066ff0  mul     r8
0x180066ff3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180066ffa  cmovb   rax, rcx
0x180066ffe  mov     rcx, rax; unsigned __int64
0x180067001  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180067006  mov     rdi, rax
0x180067009  xor     ebp, ebp
0x18006700b  mov     rdx, [rbx+58h]
0x18006700f  mov     rdx, [rdx]
0x180067012  mov     [rsp+38h+arg_0], rdx
0x180067017  cmp     rdx, [rbx+58h]
0x18006701b  jz      short loc_18006703C
0x18006701d  mov     edx, [rdx+1Ch]; unsigned int
0x180067020  call    ?_ConvertCoreWebViewPrivateIdToWindowHandle@CWebDriverHost@@AEAAPEAGK@Z; CWebDriverHost::_ConvertCoreWebViewPrivateIdToWindowHandle(ulong)
0x180067025  mov     [rdi+rbp*8], rax
0x180067029  inc     ebp
0x18006702b  lea     rcx, [rsp+38h+arg_0]
0x180067030  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>,std::_Iterator_base0>::operator++(void)
0x180067035  mov     rdx, [rsp+38h+arg_0]
0x18006703a  jmp     short loc_180067017
0x18006703c  mov     r9, rsi; unsigned __int16 **
0x18006703f  mov     r8, rdi; unsigned __int16 **
0x180067042  mov     edx, ebp; int
0x180067044  mov     rcx, [rbx+0B0h]; unsigned __int16 *
0x18006704b  call    ?GenerateStringArrayResponse@@YAXPEBGHPEAPEBGPEAPEAG@Z; GenerateStringArrayResponse(ushort const *,int,ushort const * *,ushort * *)
0x180067050  xor     esi, esi
0x180067052  test    ebp, ebp
0x180067054  jz      short loc_18006706E
0x180067056  mov     rcx, [rdi+rsi*8]; pv
0x18006705a  call    cs:__imp_CoTaskMemFree
0x180067060  mov     qword ptr [rdi+rsi*8], 0
0x180067068  inc     esi
0x18006706a  cmp     esi, ebp
0x18006706c  jb      short loc_180067056
0x18006706e  mov     rcx, rdi; Block
0x180067071  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180067076  nop
0x180067077  mov     rcx, r14; lpCriticalSection
0x18006707a  call    cs:__imp_LeaveCriticalSection
0x180067080  xor     eax, eax
0x180067082  mov     rbx, [rsp+38h+arg_10]
0x180067087  mov     rbp, [rsp+38h+arg_18]
0x18006708c  add     rsp, 20h
0x180067090  pop     r14
0x180067092  pop     rdi
0x180067093  pop     rsi
0x180067094  retn
```
