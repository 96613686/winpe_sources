# ProcessToken::~ProcessToken(void)

- ea: `0x18003c3e8`
- end: `0x18003c4a2`
- name: `??1ProcessToken@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(ProcessToken *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180061630`

## callees

- `0x18003c3e8`
- `0x18005f8e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c43c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c402`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c496`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c496`

## pseudocode

```c
void __fastcall ProcessToken::~ProcessToken(ProcessToken *this)
{
  void *v2; // r8

  if ( *(_QWORD *)this )
  {
    HeapFree(g_hHeap, 0, *(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    WindowsDeleteString(*((HSTRING *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    HeapFree(g_hHeap, 0, v2);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_QWORD *)this + 3) )
  {
    WindowsDeleteString(*((HSTRING *)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_QWORD *)this + 4) )
  {
    WindowsDeleteString(*((HSTRING *)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    WindowsDeleteString((HSTRING)_InterlockedExchange64((volatile __int64 *)this + 6, 0));
}

```

## disassembly

```asm
0x18003c3e8  push    rbx
0x18003c3ea  sub     rsp, 20h
0x18003c3ee  mov     r8, [rcx]; lpMem
0x18003c3f1  mov     rbx, rcx
0x18003c3f4  test    r8, r8
0x18003c3f7  jz      short loc_18003C40F
0x18003c3f9  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003c400  xor     edx, edx; dwFlags
0x18003c402  call    cs:__imp_HeapFree
0x18003c408  mov     qword ptr [rbx], 0
0x18003c40f  mov     rax, [rbx+8]
0x18003c413  test    rax, rax
0x18003c416  jz      short loc_18003C42A
0x18003c418  mov     rcx, [rbx+8]; string
0x18003c41c  call    cs:__imp_WindowsDeleteString
0x18003c422  mov     qword ptr [rbx+8], 0
0x18003c42a  mov     r8, [rbx+10h]; lpMem
0x18003c42e  test    r8, r8
0x18003c431  jz      short loc_18003C44A
0x18003c433  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003c43a  xor     edx, edx; dwFlags
0x18003c43c  call    cs:__imp_HeapFree
0x18003c442  mov     qword ptr [rbx+10h], 0
0x18003c44a  mov     rax, [rbx+18h]
0x18003c44e  test    rax, rax
0x18003c451  jz      short loc_18003C465
0x18003c453  mov     rcx, [rbx+18h]; string
0x18003c457  call    cs:__imp_WindowsDeleteString
0x18003c45d  mov     qword ptr [rbx+18h], 0
0x18003c465  mov     rax, [rbx+20h]
0x18003c469  test    rax, rax
0x18003c46c  jz      short loc_18003C480
0x18003c46e  mov     rcx, [rbx+20h]; string
0x18003c472  call    cs:__imp_WindowsDeleteString
0x18003c478  mov     qword ptr [rbx+20h], 0
0x18003c480  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18003c487  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18003c48c  test    al, al
0x18003c48e  jz      short loc_18003C49C
0x18003c490  xor     ecx, ecx
0x18003c492  xchg    rcx, [rbx+30h]; string
0x18003c496  call    cs:__imp_WindowsDeleteString
0x18003c49c  add     rsp, 20h
0x18003c4a0  pop     rbx
0x18003c4a1  retn
```
