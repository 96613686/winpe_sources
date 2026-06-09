# winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::ReplaceAll(uint,void * *)

- ea: `0x1800127e0`
- end: `0x1800129ce`
- name: `?ReplaceAll@?$produce@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UIBuffer@Streams@Storage@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800083ec`
- `0x18001156c`
- `0x1800127e0`
- `0x180012b00`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Storage::Streams::IBuffer>>::ReplaceAll(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v4; // r9
  __int64 v5; // r14
  __int64 v6; // r8
  __int64 v7; // r15
  __int64 *v8; // rbx
  __int64 *k; // rdi
  __int64 v10; // rcx
  unsigned __int64 v11; // r12
  __int64 v12; // rcx
  __int64 *v13; // rsi
  __int64 *j; // rbx
  __int64 result; // rax
  __int64 v16; // rcx
  __int64 i; // r14
  __int64 v18; // rcx
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
    v5 = (unsigned int)a2;
    v6 = -(v4 + 40);
    v7 = (v4 & -(__int64)(v4 != -40)) + 48;
    v8 = *(__int64 **)((v4 & -(__int64)(v4 != -40)) + 0x30);
    if ( (unsigned int)a2 <= (unsigned __int64)((__int64)(*(_QWORD *)((v4 & -(__int64)(v4 != -40)) + 0x40) - (_QWORD)v8) >> 3) )
    {
      k = *(__int64 **)((v4 & -(__int64)(v4 != -40)) + 0x38);
      v11 = k - v8;
      if ( (unsigned int)a2 > v11 )
      {
        while ( v8 != k )
        {
          if ( v8 != a3 )
          {
            if ( *v8 )
              winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v8);
            v16 = *a3;
            *v8 = *a3;
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
          }
          ++v8;
          ++a3;
          k = *(__int64 **)(v7 + 8);
        }
        for ( i = v5 - v11; i; --i )
        {
          v18 = *a3;
          *k = *a3;
          if ( v18 )
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, a2, v6);
          ++k;
          ++a3;
        }
      }
      else
      {
        k = &v8[(unsigned int)a2];
        if ( (_DWORD)a2 )
        {
          do
          {
            if ( v8 != a3 )
            {
              if ( *v8 )
                winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v8);
              v12 = *a3;
              *v8 = *a3;
              if ( v12 )
                (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, a2, v6);
            }
            ++v8;
            ++a3;
            --v5;
          }
          while ( v5 );
        }
        v13 = *(__int64 **)(v7 + 8);
        for ( j = k; j != v13; ++j )
        {
          if ( *j )
            winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(j);
        }
      }
    }
    else
    {
      std::vector<winrt::Windows::Storage::Streams::IBuffer>::_Clear_and_reserve_geometric(
        (v4 & -(__int64)(v4 != -40)) + 48,
        (unsigned int)a2,
        v6);
      for ( k = *(__int64 **)v7; v5; --v5 )
      {
        v10 = *a3;
        *k = *a3;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        ++k;
        ++a3;
      }
    }
    *(_QWORD *)(v7 + 8) = k;
    std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::~vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>((__int64)&v19);
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
0x1800127e0  mov     r11, rsp
0x1800127e3  push    rbx
0x1800127e4  push    rsi
0x1800127e5  push    rdi
0x1800127e6  push    r12
0x1800127e8  push    r14
0x1800127ea  push    r15
0x1800127ec  sub     rsp, 48h
0x1800127f0  mov     rsi, r8
0x1800127f3  lea     rax, [rcx-10h]
0x1800127f7  neg     rcx
0x1800127fa  sbb     r9, r9
0x1800127fd  and     r9, rax
0x180012800  lea     r8, [r9+28h]
0x180012804  xorps   xmm0, xmm0
0x180012807  movdqu  [rsp+78h+var_58], xmm0
0x18001280d  mov     qword ptr [r11-48h], 0
0x180012815  lock inc dword ptr [r8]
0x180012819  mov     rax, r8
0x18001281c  neg     rax
0x18001281f  sbb     rcx, rcx
0x180012822  and     rcx, r9
0x180012825  add     rcx, 30h ; '0'
0x180012829  lea     rax, [r11-58h]
0x18001282d  cmp     rax, rcx
0x180012830  jz      short loc_180012860
0x180012832  mov     rax, [rcx]
0x180012835  mov     [r11-58h], rax
0x180012839  mov     qword ptr [rcx], 0
0x180012840  mov     rax, [rcx+8]
0x180012844  mov     [r11-50h], rax
0x180012848  mov     qword ptr [rcx+8], 0
0x180012850  mov     rax, [rcx+10h]
0x180012854  mov     [r11-48h], rax
0x180012858  mov     qword ptr [rcx+10h], 0
0x180012860  mov     r14d, edx
0x180012863  neg     r8
0x180012866  sbb     rax, rax
0x180012869  and     rax, r9
0x18001286c  lea     r15, [rax+30h]
0x180012870  mov     rbx, [r15]
0x180012873  mov     rax, [r15+10h]
0x180012877  sub     rax, rbx
0x18001287a  sar     rax, 3
0x18001287e  cmp     r14, rax
0x180012881  jbe     short loc_1800128C1
0x180012883  mov     edx, r14d
0x180012886  mov     rcx, r15
0x180012889  call    ?_Clear_and_reserve_geometric@?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@AEAAX_K@Z; std::vector<winrt::Windows::Storage::Streams::IBuffer>::_Clear_and_reserve_geometric(unsigned __int64)
0x18001288e  mov     rdi, [r15]
0x180012891  test    r14, r14
0x180012894  jz      loc_18001293B
0x18001289a  mov     rcx, [rsi]
0x18001289d  mov     [rdi], rcx
0x1800128a0  test    rcx, rcx
0x1800128a3  jz      short loc_1800128B1
0x1800128a5  mov     rax, [rcx]
0x1800128a8  mov     rax, [rax+8]
0x1800128ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b1  add     rdi, 8
0x1800128b5  add     rsi, 8
0x1800128b9  sub     r14, 1
0x1800128bd  jnz     short loc_18001289A
0x1800128bf  jmp     short loc_18001293B
0x1800128c1  mov     rdi, [r15+8]
0x1800128c5  mov     r12, rdi
0x1800128c8  sub     r12, rbx
0x1800128cb  sar     r12, 3
0x1800128cf  cmp     r14, r12
0x1800128d2  ja      loc_180012998
0x1800128d8  lea     rdi, [rbx+r14*8]
0x1800128dc  test    edx, edx
0x1800128de  jz      short loc_180012918
0x1800128e0  cmp     rbx, rsi
0x1800128e3  jz      short loc_18001290A
0x1800128e5  cmp     qword ptr [rbx], 0
0x1800128e9  jz      short loc_1800128F3
0x1800128eb  mov     rcx, rbx
0x1800128ee  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800128f3  mov     rcx, [rsi]
0x1800128f6  mov     [rbx], rcx
0x1800128f9  test    rcx, rcx
0x1800128fc  jz      short loc_18001290A
0x1800128fe  mov     rax, [rcx]
0x180012901  mov     rax, [rax+8]
0x180012905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001290a  add     rbx, 8
0x18001290e  add     rsi, 8
0x180012912  sub     r14, 1
0x180012916  jnz     short loc_1800128E0
0x180012918  mov     rsi, [r15+8]
0x18001291c  mov     rbx, rdi
0x18001291f  cmp     rdi, rsi
0x180012922  jz      short loc_18001293B
0x180012924  cmp     qword ptr [rbx], 0
0x180012928  jz      short loc_180012932
0x18001292a  mov     rcx, rbx
0x18001292d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012932  add     rbx, 8
0x180012936  cmp     rbx, rsi
0x180012939  jnz     short loc_180012924
0x18001293b  mov     [r15+8], rdi
0x18001293f  lea     rcx, [rsp+78h+var_58]
0x180012944  call    ??1?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>::~vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>(void)
0x180012949  xor     eax, eax
0x18001294b  jmp     short loc_180012954
0x18001294d  mov     eax, [rsp+78h+arg_8]
0x180012954  add     rsp, 48h
0x180012958  pop     r15
0x18001295a  pop     r14
0x18001295c  pop     r12
0x18001295e  pop     rdi
0x18001295f  pop     rsi
0x180012960  pop     rbx
0x180012961  retn
0x180012962  cmp     rbx, rsi
0x180012965  jz      short loc_18001298C
0x180012967  cmp     qword ptr [rbx], 0
0x18001296b  jz      short loc_180012975
0x18001296d  mov     rcx, rbx
0x180012970  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180012975  mov     rcx, [rsi]
0x180012978  mov     [rbx], rcx
0x18001297b  test    rcx, rcx
0x18001297e  jz      short loc_18001298C
0x180012980  mov     rax, [rcx]
0x180012983  mov     rax, [rax+8]
0x180012987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001298c  add     rbx, 8
0x180012990  add     rsi, 8
0x180012994  mov     rdi, [r15+8]
0x180012998  cmp     rbx, rdi
0x18001299b  jnz     short loc_180012962
0x18001299d  sub     r14, r12
0x1800129a0  jz      short loc_18001293B
0x1800129a2  mov     rcx, [rsi]
0x1800129a5  mov     [rdi], rcx
0x1800129a8  test    rcx, rcx
0x1800129ab  jz      short loc_1800129B9
0x1800129ad  mov     rax, [rcx]
0x1800129b0  mov     rax, [rax+8]
0x1800129b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b9  add     rdi, 8
0x1800129bd  add     rsi, 8
0x1800129c1  sub     r14, 1
0x1800129c5  jnz     short loc_1800129A2
0x1800129c7  jmp     loc_18001293B
```
