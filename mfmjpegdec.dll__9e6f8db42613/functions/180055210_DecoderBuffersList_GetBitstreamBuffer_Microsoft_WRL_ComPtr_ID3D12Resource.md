# DecoderBuffersList::GetBitstreamBuffer(Microsoft::WRL::ComPtr<ID3D12Resource> &)

- ea: `0x180055210`
- end: `0x18005527c`
- name: `?GetBitstreamBuffer@DecoderBuffersList@@QEAAJAEAV?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@@Z`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004a148`
- `0x18004a550`

## callees

- `0x180021fec`
- `0x180044d78`
- `0x180055210`

## pseudocode

```c
__int64 __fastcall DecoderBuffersList::GetBitstreamBuffer(__int64 a1, __int64 *a2)
{
  Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(
    a2,
    (__int64 *)(a1 + 8 * (*(unsigned int *)(a1 + 4) + 8LL * *(unsigned int *)(a1 + 4) + 3)));
  if ( *a2 )
    return 0;
  if ( g_wppLevels )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids, a1);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180055210  mov     [rsp+arg_0], rbx
0x180055215  push    rdi
0x180055216  sub     rsp, 20h
0x18005521a  mov     eax, [rcx+4]
0x18005521d  mov     rbx, rdx
0x180055220  mov     rdi, rcx
0x180055223  lea     r8, ds:3[rax*8]
0x18005522b  add     r8, rax
0x18005522e  lea     rdx, [rcx+r8*8]
0x180055232  mov     rcx, rbx
0x180055235  call    ??4?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(Microsoft::WRL::ComPtr<ID3D12Resource> const &)
0x18005523a  cmp     qword ptr [rbx], 0
0x18005523e  jnz     short loc_18005526F
0x180055240  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055247  jb      short loc_180055268
0x180055249  mov     rcx, cs:WPP_GLOBAL_Control
0x180055250  lea     r8, WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids
0x180055257  mov     edx, 10h
0x18005525c  mov     r9, rdi
0x18005525f  mov     rcx, [rcx+10h]
0x180055263  call    WPP_SF_q
0x180055268  mov     eax, 80004005h
0x18005526d  jmp     short loc_180055271
0x18005526f  xor     eax, eax
0x180055271  mov     rbx, [rsp+28h+arg_0]
0x180055276  add     rsp, 20h
0x18005527a  pop     rdi
0x18005527b  retn
```
