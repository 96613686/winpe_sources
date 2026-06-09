# DecoderBuffersList::GetCommandAllocator(Microsoft::WRL::ComPtr<ID3D12CommandAllocator> &)

- ea: `0x1800553c4`
- end: `0x18005545b`
- name: `?GetCommandAllocator@DecoderBuffersList@@QEAAJAEAV?$ComPtr@UID3D12CommandAllocator@@@WRL@Microsoft@@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180048ac4`
- `0x18004a550`

## callees

- `0x180020598`
- `0x180044d78`
- `0x1800553c4`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DecoderBuffersList::GetCommandAllocator(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v4 = *(unsigned int *)(a1 + 4);
  v5 = *(_QWORD *)(a1 + 72 * v4 + 32);
  if ( *a2 != v5 )
  {
    if ( v5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*(_QWORD *)(a1 + 72 * v4 + 32));
    v7 = *a2;
    *a2 = v5;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  if ( *a2 )
    return 0;
  if ( g_wppLevels )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids, a1);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800553c4  mov     [rsp+arg_8], rbx
0x1800553c9  mov     [rsp+arg_10], rsi
0x1800553ce  push    rdi
0x1800553cf  sub     rsp, 20h
0x1800553d3  mov     rdi, rdx
0x1800553d6  mov     rsi, rcx
0x1800553d9  mov     eax, [rcx+4]
0x1800553dc  lea     r8, [rax+rax*8]
0x1800553e0  mov     rbx, [rcx+r8*8+20h]
0x1800553e5  cmp     [rdx], rbx
0x1800553e8  jz      short loc_180055414
0x1800553ea  test    rbx, rbx
0x1800553ed  jz      short loc_1800553FF
0x1800553ef  mov     rax, [rbx]
0x1800553f2  mov     rcx, rbx
0x1800553f5  mov     rax, [rax+8]
0x1800553f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553fe  nop
0x1800553ff  mov     rax, [rdi]
0x180055402  mov     [rsp+28h+arg_0], rax
0x180055407  mov     [rdi], rbx
0x18005540a  lea     rcx, [rsp+28h+arg_0]
0x18005540f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180055414  cmp     qword ptr [rdi], 0
0x180055418  jnz     short loc_180055449
0x18005541a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055421  jb      short loc_180055442
0x180055423  mov     edx, 11h
0x180055428  mov     r9, rsi
0x18005542b  lea     r8, WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids
0x180055432  mov     rcx, cs:WPP_GLOBAL_Control
0x180055439  mov     rcx, [rcx+10h]
0x18005543d  call    WPP_SF_q
0x180055442  mov     eax, 80004005h
0x180055447  jmp     short loc_18005544B
0x180055449  xor     eax, eax
0x18005544b  mov     rbx, [rsp+28h+arg_8]
0x180055450  mov     rsi, [rsp+28h+arg_10]
0x180055455  add     rsp, 20h
0x180055459  pop     rdi
0x18005545a  retn
```
