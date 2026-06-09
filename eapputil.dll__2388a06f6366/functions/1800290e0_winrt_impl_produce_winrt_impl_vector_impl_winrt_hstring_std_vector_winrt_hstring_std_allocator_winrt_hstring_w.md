# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::ReplaceAll(uint,void * *)

- ea: `0x1800290e0`
- end: `0x18002927a`
- name: `?ReplaceAll@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x180017fb8`
- `0x180025954`
- `0x180025fc8`
- `0x1800290e0`
- `0x18002aa0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029272`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029272`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        struct winrt::impl::shared_hstring_header **a3)
{
  __int64 v4; // r9
  __int64 v5; // r14
  struct winrt::impl::shared_hstring_header ***v6; // rbx
  struct winrt::impl::shared_hstring_header **v7; // rsi
  struct winrt::impl::shared_hstring_header **v8; // r8
  unsigned __int64 v9; // r15
  struct winrt::impl::shared_hstring_header **v10; // r14
  __int64 result; // rax
  __int64 v12; // r12
  __int64 i; // r15
  volatile signed __int32 **v14; // r15
  volatile signed __int32 **v15; // rdi
  volatile signed __int32 *v16; // rsi
  int v17; // eax
  HANDLE ProcessHeap; // rax
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-48h]
  int v21; // [rsp+88h] [rbp+10h] BYREF

  v4 = (a1 - 16) & -(__int64)(a1 != 0);
  v19 = 0;
  v20 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 40));
  if ( &v19 != (__int128 *)((v4 & -(__int64)(v4 != -40)) + 48) )
  {
    *(_QWORD *)&v19 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30) = 0;
    *((_QWORD *)&v19 + 1) = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38) = 0;
    v20 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40);
    *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40) = 0;
  }
  try
  {
    v5 = a2;
    v6 = (struct winrt::impl::shared_hstring_header ***)((v4 & -(__int64)(v4 != -40)) + 48);
    v7 = *(struct winrt::impl::shared_hstring_header ***)((v4 & -(__int64)(v4 != -40)) + 0x30);
    if ( a2 <= (unsigned __int64)((__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40) - (_QWORD)v7) >> 3) )
    {
      v9 = (__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x38) - (_QWORD)v7) >> 3;
      if ( a2 <= v9 )
      {
        v12 = *(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x30);
        for ( i = a2; i; --i )
        {
          winrt::hstring::operator=(v12, a3);
          v12 += 8;
          ++a3;
        }
        v10 = &v7[v5];
        v14 = (volatile signed __int32 **)v6[1];
        v15 = (volatile signed __int32 **)v10;
        if ( v10 != (struct winrt::impl::shared_hstring_header **)v14 )
        {
          do
          {
            v16 = *v15;
            if ( *v15 )
            {
              v17 = _InterlockedDecrement(v16 + 6);
              if ( v17 )
              {
                if ( v17 < 0 )
                  abort();
              }
              else
              {
                ProcessHeap = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v16);
              }
              *v15 = 0;
            }
            ++v15;
          }
          while ( v15 != v14 );
        }
        goto LABEL_10;
      }
      while ( 1 )
      {
        v8 = v6[1];
        if ( v7 == v8 )
          break;
        winrt::hstring::operator=(v7++, a3++);
      }
      v5 -= v9;
    }
    else
    {
      std::vector<winrt::hstring>::_Clear_and_reserve_geometric((v4 & -(__int64)(v4 != -40)) + 48, a2, -(v4 + 40));
      v8 = *v6;
    }
    v10 = std::_Uninitialized_copy_n<winrt::hstring const *>(a3, v5, v8, (__int64)v6);
LABEL_10:
    v6[1] = v10;
    std::vector<winrt::hstring>::~vector<winrt::hstring>(&v19);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v21);
  }
  return result;
}

```

## disassembly

```asm
0x1800290e0  mov     r11, rsp
0x1800290e3  push    rbx
0x1800290e4  push    rsi
0x1800290e5  push    rdi
0x1800290e6  push    r12
0x1800290e8  push    r14
0x1800290ea  push    r15
0x1800290ec  sub     rsp, 48h
0x1800290f0  mov     rdi, r8
0x1800290f3  lea     rax, [rcx-10h]
0x1800290f7  neg     rcx
0x1800290fa  sbb     r9, r9
0x1800290fd  and     r9, rax
0x180029100  lea     r8, [r9+28h]
0x180029104  xorps   xmm0, xmm0
0x180029107  movdqu  [rsp+78h+var_58], xmm0
0x18002910d  mov     qword ptr [r11-48h], 0
0x180029115  lock inc dword ptr [r8]
0x180029119  mov     rax, r8
0x18002911c  neg     rax
0x18002911f  sbb     rcx, rcx
0x180029122  and     rcx, r9
0x180029125  add     rcx, 30h ; '0'
0x180029129  lea     rax, [r11-58h]
0x18002912d  cmp     rax, rcx
0x180029130  jz      short loc_180029160
0x180029132  mov     rax, [rcx]
0x180029135  mov     [r11-58h], rax
0x180029139  mov     qword ptr [rcx], 0
0x180029140  mov     rax, [rcx+8]
0x180029144  mov     [r11-50h], rax
0x180029148  mov     qword ptr [rcx+8], 0
0x180029150  mov     rax, [rcx+10h]
0x180029154  mov     [r11-48h], rax
0x180029158  mov     qword ptr [rcx+10h], 0
0x180029160  mov     r14d, edx
0x180029163  neg     r8
0x180029166  sbb     rax, rax
0x180029169  and     rax, r9
0x18002916c  lea     rbx, [rax+30h]
0x180029170  mov     rsi, [rbx]
0x180029173  mov     rax, [rbx+10h]
0x180029177  sub     rax, rsi
0x18002917a  sar     rax, 3
0x18002917e  cmp     r14, rax
0x180029181  jbe     short loc_180029193
0x180029183  mov     edx, r14d
0x180029186  mov     rcx, rbx
0x180029189  call    ?_Clear_and_reserve_geometric@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAX_K@Z; std::vector<winrt::hstring>::_Clear_and_reserve_geometric(unsigned __int64)
0x18002918e  mov     r8, [rbx]
0x180029191  jmp     short loc_1800291C4
0x180029193  mov     r15, [rbx+8]
0x180029197  sub     r15, rsi
0x18002919a  sar     r15, 3
0x18002919e  cmp     r14, r15
0x1800291a1  jbe     short loc_1800291FC
0x1800291a3  mov     r8, [rbx+8]
0x1800291a7  cmp     rsi, r8
0x1800291aa  jz      short loc_1800291C1
0x1800291ac  mov     rdx, rdi
0x1800291af  mov     rcx, rsi
0x1800291b2  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x1800291b7  add     rsi, 8
0x1800291bb  add     rdi, 8
0x1800291bf  jmp     short loc_1800291A3
0x1800291c1  sub     r14, r15
0x1800291c4  mov     r9, rbx
0x1800291c7  mov     rdx, r14
0x1800291ca  mov     rcx, rdi
0x1800291cd  call    ??$_Uninitialized_copy_n@PEBUhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@YAPEAUhstring@winrt@@PEBU12@_KPEAU12@AEAV?$allocator@Uhstring@winrt@@@0@@Z; std::_Uninitialized_copy_n<winrt::hstring const *>(winrt::hstring const *,unsigned __int64,winrt::hstring *,std::allocator<winrt::hstring> &)
0x1800291d2  mov     r14, rax
0x1800291d5  mov     [rbx+8], r14
0x1800291d9  lea     rcx, [rsp+78h+var_58]
0x1800291de  call    ??1?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::hstring>::~vector<winrt::hstring>(void)
0x1800291e3  xor     eax, eax
0x1800291e5  jmp     short loc_1800291EE
0x1800291e7  mov     eax, [rsp+78h+arg_8]
0x1800291ee  add     rsp, 48h
0x1800291f2  pop     r15
0x1800291f4  pop     r14
0x1800291f6  pop     r12
0x1800291f8  pop     rdi
0x1800291f9  pop     rsi
0x1800291fa  pop     rbx
0x1800291fb  retn
0x1800291fc  mov     r12, rsi
0x1800291ff  mov     r15, r14
0x180029202  test    r15, r15
0x180029205  jz      short loc_18002921F
0x180029207  mov     rdx, rdi
0x18002920a  mov     rcx, r12
0x18002920d  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x180029212  add     r12, 8
0x180029216  add     rdi, 8
0x18002921a  dec     r15
0x18002921d  jmp     short loc_180029202
0x18002921f  lea     r14, [rsi+r14*8]
0x180029223  mov     r15, [rbx+8]
0x180029227  mov     rdi, r14
0x18002922a  cmp     r14, r15
0x18002922d  jz      short loc_1800291D5
0x18002922f  mov     rsi, [rdi]
0x180029232  test    rsi, rsi
0x180029235  jz      short loc_180029264
0x180029237  or      eax, 0FFFFFFFFh
0x18002923a  lock xadd [rsi+18h], eax
0x18002923f  sub     eax, 1
0x180029242  jnz     short loc_180029259
0x180029244  nop
0x180029245  call    WINRT_IMPL_GetProcessHeap
0x18002924a  mov     rcx, rax; hHeap
0x18002924d  mov     r8, rsi; lpMem
0x180029250  xor     edx, edx; dwFlags
0x180029252  call    WINRT_IMPL_HeapFree
0x180029257  jmp     short loc_18002925D
0x180029259  test    eax, eax
0x18002925b  js      short loc_180029272
0x18002925d  mov     qword ptr [rdi], 0
0x180029264  add     rdi, 8
0x180029268  cmp     rdi, r15
0x18002926b  jnz     short loc_18002922F
0x18002926d  jmp     loc_1800291D5
0x180029272  call    cs:__imp_abort
```
