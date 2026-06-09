# winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::Complete(void)

- ea: `0x180014840`
- end: `0x180014892`
- name: `?Complete@?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@AEAAXXZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001430c`
- `0x180014c80`

## callees

- `0x180014840`
- `0x180015b40`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::Complete(
        __int64 a1)
{
  __int64 result; // rax
  __int64 (__fastcall **v2)(_QWORD); // rbx

  result = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 24LL);
  *(_BYTE *)(*(_QWORD *)(a1 + 16) + 24LL) = 0;
  if ( (_BYTE)result )
  {
    *(_QWORD *)(a1 + 24) = 0;
  }
  else
  {
    v2 = *(__int64 (__fastcall ***)(_QWORD))(a1 + 24);
    *(_QWORD *)(a1 + 24) = 0;
    result = winrt::impl::resume_apartment(a1, v2, *(_QWORD *)(a1 + 16) + 20LL);
    if ( !(_BYTE)result )
      return (*v2)(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180014840  push    rbx
0x180014842  sub     rsp, 20h
0x180014846  mov     rdx, [rcx+10h]
0x18001484a  xor     eax, eax
0x18001484c  xchg    al, [rdx+18h]
0x18001484f  test    al, al
0x180014851  jz      short loc_180014861
0x180014853  mov     qword ptr [rcx+18h], 0
0x18001485b  add     rsp, 20h
0x18001485f  pop     rbx
0x180014860  retn
0x180014861  mov     rbx, [rcx+18h]
0x180014865  mov     qword ptr [rcx+18h], 0
0x18001486d  mov     rdx, rbx
0x180014870  mov     r8, [rcx+10h]
0x180014874  add     r8, 14h
0x180014878  call    ?resume_apartment@impl@winrt@@YA@AEBUresume_apartment_context@12@U?$coroutine_handle@X@experimental@std@@PEAH@Z; winrt::impl::resume_apartment(winrt::impl::resume_apartment_context const &,std::experimental::coroutine_handle<void>,int *)
0x18001487d  test    al, al
0x18001487f  jnz     short loc_18001488C
0x180014881  mov     rax, [rbx]
0x180014884  mov     rcx, rbx
0x180014887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001488c  add     rsp, 20h
0x180014890  pop     rbx
0x180014891  retn
```
