# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::Append(void *)

- ea: `0x1800266d0`
- end: `0x18002678a`
- name: `?Append@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAX@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007eac`
- `0x180008274`
- `0x1800253d0`
- `0x1800266d0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::Append(
        __int64 a1,
        __int64 a2)
{
  struct winrt::impl::shared_hstring_header *v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdi
  struct winrt::impl::shared_hstring_header **v6; // r14
  unsigned int v7; // esi
  const void *v8; // r15
  int v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = a2;
  v2 = (struct winrt::impl::shared_hstring_header *)a2;
  v3 = (a1 - 16) & -(__int64)(a1 != 0);
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 40));
  v4 = v3 & -(__int64)(v3 != -40);
  v5 = v4 + 48;
  v6 = *(struct winrt::impl::shared_hstring_header ***)(v4 + 0x38);
  if ( v6 == *(struct winrt::impl::shared_hstring_header ***)(v4 + 0x40) )
  {
    std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(
      v4 + 48,
      *(_QWORD *)((v3 & -(__int64)(v3 != -40)) + 0x38),
      &v11);
    return 0;
  }
  if ( !a2 )
    goto LABEL_3;
  if ( (*(_BYTE *)a2 & 1) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 24));
    goto LABEL_8;
  }
  v7 = *(_DWORD *)(a2 + 4);
  if ( !v7 )
  {
LABEL_3:
    v2 = 0;
LABEL_8:
    *v6 = v2;
    *(_QWORD *)(v5 + 8) += 8LL;
    return 0;
  }
  try
  {
    v8 = *(const void **)(a2 + 16);
    v2 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v7, a2);
    memcpy_s((char *)v2 + 28, 2LL * v7, v8, 2LL * v7);
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v10);
  }
  goto LABEL_8;
}

```

## disassembly

```asm
0x1800266d0  mov     [rsp+arg_10], rbx
0x1800266d5  mov     [rsp+arg_18], rsi
0x1800266da  mov     [rsp+arg_8], rdx
0x1800266df  push    rdi
0x1800266e0  push    r14
0x1800266e2  push    r15
0x1800266e4  sub     rsp, 20h
0x1800266e8  mov     rbx, rdx
0x1800266eb  lea     rax, [rcx-10h]
0x1800266ef  neg     rcx
0x1800266f2  sbb     rcx, rcx
0x1800266f5  and     rcx, rax
0x1800266f8  lea     rax, [rcx+28h]
0x1800266fc  lock inc dword ptr [rax]
0x1800266ff  neg     rax
0x180026702  sbb     rax, rax
0x180026705  and     rax, rcx
0x180026708  lea     rdi, [rax+30h]
0x18002670c  mov     r14, [rdi+8]
0x180026710  cmp     r14, [rdi+10h]
0x180026714  jz      short loc_18002675D
0x180026716  test    rdx, rdx
0x180026719  jnz     short loc_18002671F
0x18002671b  xor     ebx, ebx
0x18002671d  jmp     short loc_180026753
0x18002671f  test    byte ptr [rdx], 1
0x180026722  jnz     short loc_18002672A
0x180026724  lock inc dword ptr [rdx+18h]
0x180026728  jmp     short loc_180026753
0x18002672a  mov     esi, [rdx+4]
0x18002672d  test    esi, esi
0x18002672f  jz      short loc_18002671B
0x180026731  mov     r15, [rdx+10h]
0x180026735  mov     ecx, esi; this
0x180026737  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002673c  mov     rbx, rax
0x18002673f  mov     edx, esi
0x180026741  add     rdx, rdx; DestinationSize
0x180026744  lea     rcx, [rax+1Ch]; Destination
0x180026748  mov     r9, rdx; SourceSize
0x18002674b  mov     r8, r15; Source
0x18002674e  call    memcpy_s
0x180026753  mov     [r14], rbx
0x180026756  add     qword ptr [rdi+8], 8
0x18002675b  jmp     short loc_18002676D
0x18002675d  lea     r8, [rsp+38h+arg_8]
0x180026762  mov     rdx, r14
0x180026765  mov     rcx, rdi
0x180026768  call    ??$_Emplace_reallocate@AEBUhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@AEBU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring const &>(winrt::hstring * const,winrt::hstring const &)
0x18002676d  xor     eax, eax
0x18002676f  jmp     short loc_180026775
0x180026771  mov     eax, [rsp+38h+arg_0]
0x180026775  mov     rbx, [rsp+38h+arg_10]
0x18002677a  mov     rsi, [rsp+38h+arg_18]
0x18002677f  add     rsp, 20h
0x180026783  pop     r15
0x180026785  pop     r14
0x180026787  pop     rdi
0x180026788  retn
```
