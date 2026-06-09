# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::_Reset_map(void)

- ea: `0x180010808`
- end: `0x180010871`
- name: `?_Reset_map@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAXXZ`
- size: `105`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800108e8`

## callees

- `0x180003c34`
- `0x180010808`

## pseudocode

```c
void __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Reset_map(__int64 a1)
{
  __int64 v1; // rdi
  void **v2; // rbx
  void *v4; // rcx

  v1 = *(_QWORD *)(a1 + 16);
  v2 = (void **)(a1 + 8);
  while ( v1 > 0 )
  {
    --v1;
    v4 = (void *)*((_QWORD *)*v2 + v1);
    if ( v4 )
      std::_Deallocate<16>(v4, 0x10u);
  }
  std::_Deallocate<16>(*v2, 8LL * *(_QWORD *)(a1 + 16));
  *v2 = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180010808  mov     [rsp+arg_0], rbx
0x18001080d  mov     [rsp+arg_8], rsi
0x180010812  push    rdi
0x180010813  sub     rsp, 20h
0x180010817  mov     rdi, [rcx+10h]
0x18001081b  lea     rbx, [rcx+8]
0x18001081f  mov     rsi, rcx
0x180010822  jmp     short loc_18001083D
0x180010824  mov     rax, [rbx]
0x180010827  dec     rdi
0x18001082a  mov     rcx, [rax+rdi*8]
0x18001082e  test    rcx, rcx
0x180010831  jz      short loc_18001083D
0x180010833  mov     edx, 10h
0x180010838  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001083d  test    rdi, rdi
0x180010840  jg      short loc_180010824
0x180010842  mov     rdx, [rsi+10h]
0x180010846  mov     rcx, [rbx]
0x180010849  shl     rdx, 3
0x18001084d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010852  mov     qword ptr [rbx], 0
0x180010859  mov     rbx, [rsp+28h+arg_0]
0x18001085e  mov     qword ptr [rsi+10h], 0
0x180010866  mov     rsi, [rsp+28h+arg_8]
0x18001086b  add     rsp, 20h
0x18001086f  pop     rdi
0x180010870  retn
```
