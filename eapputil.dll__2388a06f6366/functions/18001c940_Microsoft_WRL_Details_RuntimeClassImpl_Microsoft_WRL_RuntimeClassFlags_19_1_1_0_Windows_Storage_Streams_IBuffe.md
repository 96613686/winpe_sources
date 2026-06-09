# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetWeakReference(IWeakReference * *)

- ea: `0x18001c940`
- end: `0x18001ca88`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025a0`
- `0x180003820`
- `0x18001c940`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetWeakReference(
        __int64 a1,
        __int64 *a2)
{
  signed __int64 v4; // rsi
  __int64 v5; // r8
  signed __int32 v6; // eax
  _DWORD *v8; // rax
  __int64 v9; // rbx
  unsigned __int64 v10; // rdx
  bool i; // zf
  signed __int64 v12; // rax
  signed __int64 v13; // rsi
  __int64 v14; // rdx
  signed __int32 v15; // eax

  v4 = *(_QWORD *)(a1 + 64);
  *a2 = 0;
  if ( v4 < 0 )
  {
    v5 = 2 * v4;
    do
      v6 = *(_DWORD *)(2 * v4 + 0xC);
    while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 12), v6 + 1, v6) );
    *a2 = v5;
    return 0;
  }
  v8 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v9 = (__int64)v8;
  if ( v8 )
  {
    v8[3] = 1;
    *(_QWORD *)v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_DWORD *)(v9 + 16) = 0x3FFFFFFF;
    *(_QWORD *)v9 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *(_QWORD *)(v9 + 24) = a1 - 8;
    *(_DWORD *)(v9 + 12) = 2;
    v10 = (v9 >> 1) | 0x8000000000000000uLL;
    *(_DWORD *)(v9 + 16) = v4;
    v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v10, v4);
    for ( i = v4 == v12; ; i = v12 == v13 )
    {
      v13 = v12;
      if ( i )
      {
        *a2 = v9;
        return 0;
      }
      if ( v12 < 0 )
        break;
      *(_DWORD *)(v9 + 16) = v12;
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v10, v12);
    }
    *(_QWORD *)v9 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *(_DWORD *)(v9 + 16) = -1073741823;
    *(_DWORD *)(v9 + 12) = -1073741823;
    operator delete((void *)v9);
    v14 = 2 * v13;
    do
      v15 = *(_DWORD *)(2 * v13 + 0xC);
    while ( v15 != 0x7FFFFFFF && v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 12), v15 + 1, v15) );
    *a2 = v14;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001c940  push    rbx
0x18001c942  push    rbp
0x18001c943  push    rsi
0x18001c944  push    rdi
0x18001c945  push    r14
0x18001c947  sub     rsp, 20h
0x18001c94b  mov     rdi, rdx
0x18001c94e  mov     rbp, rcx
0x18001c951  mov     rsi, [rcx+40h]
0x18001c955  mov     qword ptr [rdx], 0
0x18001c95c  test    rsi, rsi
0x18001c95f  jns     short loc_18001C98B
0x18001c961  lea     r8, [rsi+rsi]
0x18001c965  mov     r9d, 7FFFFFFFh
0x18001c96b  jmp     short loc_18001C978
0x18001c96d  lea     ecx, [rax+1]
0x18001c970  lock cmpxchg [r8+0Ch], ecx
0x18001c976  jz      short loc_18001C981
0x18001c978  mov     eax, [r8+0Ch]
0x18001c97c  cmp     eax, r9d
0x18001c97f  jnz     short loc_18001C96D
0x18001c981  mov     [rdx], r8
0x18001c984  xor     eax, eax
0x18001c986  jmp     loc_18001CA7D
0x18001c98b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c992  mov     ecx, 20h ; ' '; unsigned __int64
0x18001c997  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c99c  mov     rbx, rax
0x18001c99f  test    rax, rax
0x18001c9a2  jz      loc_18001CA78
0x18001c9a8  lea     r14, [rbp-8]
0x18001c9ac  mov     dword ptr [rax+0Ch], 1
0x18001c9b3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x18001c9ba  mov     [rbx], rax
0x18001c9bd  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001c9c4  test    rcx, rcx
0x18001c9c7  jz      short loc_18001C9D6
0x18001c9c9  mov     rax, [rcx]
0x18001c9cc  mov     rax, [rax+8]
0x18001c9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9d5  nop
0x18001c9d6  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x18001c9dd  lea     r8, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18001c9e4  mov     [rbx], r8
0x18001c9e7  mov     [rbx+18h], r14
0x18001c9eb  mov     dword ptr [rbx+0Ch], 2
0x18001c9f2  mov     rdx, rbx
0x18001c9f5  sar     rdx, 1
0x18001c9f8  mov     rax, 8000000000000000h
0x18001ca02  or      rdx, rax
0x18001ca05  mov     [rbx+10h], esi
0x18001ca08  mov     rax, rsi
0x18001ca0b  lock cmpxchg [rbp+40h], rdx
0x18001ca11  jmp     short loc_18001CA2A
0x18001ca13  test    rsi, rsi
0x18001ca16  js      short loc_18001CA37
0x18001ca18  mov     rcx, rsi
0x18001ca1b  mov     [rbx+10h], esi
0x18001ca1e  mov     rax, rsi
0x18001ca21  lock cmpxchg [rbp+40h], rdx
0x18001ca27  cmp     rax, rcx
0x18001ca2a  mov     rsi, rax
0x18001ca2d  jnz     short loc_18001CA13
0x18001ca2f  mov     [rdi], rbx
0x18001ca32  jmp     loc_18001C984
0x18001ca37  mov     [rbx], r8
0x18001ca3a  mov     eax, 0C0000001h
0x18001ca3f  mov     [rbx+10h], eax
0x18001ca42  mov     [rbx+0Ch], eax
0x18001ca45  mov     edx, 20h ; ' '; unsigned __int64
0x18001ca4a  mov     rcx, rbx; void *
0x18001ca4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca52  lea     rdx, [rsi+rsi]
0x18001ca56  mov     r9d, 7FFFFFFFh
0x18001ca5c  jmp     short loc_18001CA68
0x18001ca5e  lea     ecx, [rax+1]
0x18001ca61  lock cmpxchg [rdx+0Ch], ecx
0x18001ca66  jz      short loc_18001CA70
0x18001ca68  mov     eax, [rdx+0Ch]
0x18001ca6b  cmp     eax, r9d
0x18001ca6e  jnz     short loc_18001CA5E
0x18001ca70  mov     [rdi], rdx
0x18001ca73  jmp     loc_18001C984
0x18001ca78  mov     eax, 8007000Eh
0x18001ca7d  add     rsp, 20h
0x18001ca81  pop     r14
0x18001ca83  pop     rdi
0x18001ca84  pop     rsi
0x18001ca85  pop     rbp
0x18001ca86  pop     rbx
0x18001ca87  retn
```
