# DecoderBuffersList::GetBitstreamBuffer(unsigned __int64,Microsoft::WRL::ComPtr<ID3D12Resource> &)

- ea: `0x180055284`
- end: `0x1800553bc`
- name: `?GetBitstreamBuffer@DecoderBuffersList@@QEAAJ_KAEAV?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049e90`

## callees

- `0x180020598`
- `0x180021fec`
- `0x180044d78`
- `0x180054cf4`
- `0x180055284`
- `0x1800554c0`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DecoderBuffersList::GetBitstreamBuffer(__int64 a1, unsigned __int64 a2, __int64 *a3)
{
  unsigned int BitstreamBuffer; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, GUID *, struct ID3D12Device **); // rbx
  DecoderBuffersList *v9; // rcx
  struct ID3D12Device *v11; // [rsp+60h] [rbp+8h] BYREF

  BitstreamBuffer = 0;
  if ( *(_QWORD *)(a1 + 72LL * *(unsigned int *)(a1 + 4) + 88) < a2 )
  {
    if ( g_wppLevels )
      WPP_SF_diiq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14);
    v11 = 0;
    v7 = *(_QWORD *)(a1 + 72LL * *(unsigned int *)(a1 + 4) + 24);
    v8 = *(__int64 (__fastcall **)(__int64, GUID *, struct ID3D12Device **))(*(_QWORD *)v7 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
    BitstreamBuffer = v8(v7, &GUID_189819f1_1db6_4b57_be54_1821339b85f7, &v11);
    if ( BitstreamBuffer
      || (v9 = (DecoderBuffersList *)(*(unsigned int *)(a1 + 4) + 8LL * *(unsigned int *)(a1 + 4) + 3),
          (BitstreamBuffer = DecoderBuffersList::AllocateBitstreamBuffer(
                               v9,
                               v11,
                               a2,
                               (struct _DecoderBuffers *)(a1 + 8LL * (_QWORD)v9))) != 0) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
      return BitstreamBuffer;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
  }
  Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(
    a3,
    (__int64 *)(a1 + 8 * (*(unsigned int *)(a1 + 4) + 8LL * *(unsigned int *)(a1 + 4) + 3)));
  if ( !*a3 )
  {
    if ( g_wppLevels )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids, a1);
    return (unsigned int)-2147467259;
  }
  return BitstreamBuffer;
}

```

## disassembly

```asm
0x180055284  mov     r11, rsp
0x180055287  mov     [r11+10h], rbx
0x18005528b  mov     [r11+18h], rbp
0x18005528f  push    rsi
0x180055290  push    rdi
0x180055291  push    r14
0x180055293  sub     rsp, 40h
0x180055297  mov     r14, r8
0x18005529a  mov     rbp, rdx
0x18005529d  mov     rsi, rcx
0x1800552a0  xor     ebx, ebx
0x1800552a2  mov     r9d, [rcx+4]
0x1800552a6  lea     rax, [r9+r9*8]
0x1800552aa  mov     rcx, [rcx+rax*8+58h]
0x1800552af  cmp     rcx, rdx
0x1800552b2  jnb     loc_18005535A
0x1800552b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800552bf  jb      short loc_1800552E0
0x1800552c1  lea     edx, [rbx+0Eh]
0x1800552c4  mov     [r11-28h], rsi
0x1800552c8  mov     [r11-30h], rbp
0x1800552cc  mov     [r11-38h], rcx
0x1800552d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552d7  mov     rcx, [rcx+10h]
0x1800552db  call    WPP_SF_diiq
0x1800552e0  mov     [rsp+58h+arg_0], rbx
0x1800552e5  mov     eax, [rsi+4]
0x1800552e8  lea     rcx, [rax+rax*8]
0x1800552ec  mov     rdi, [rsi+rcx*8+18h]
0x1800552f1  mov     rax, [rdi]
0x1800552f4  mov     rbx, [rax+38h]
0x1800552f8  lea     rcx, [rsp+58h+arg_0]
0x1800552fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180055302  lea     r8, [rsp+58h+arg_0]
0x180055307  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x18005530e  mov     rcx, rdi
0x180055311  mov     rax, rbx
0x180055314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055319  mov     ebx, eax
0x18005531b  test    eax, eax
0x18005531d  jz      short loc_18005532B
0x18005531f  lea     rcx, [rsp+58h+arg_0]
0x180055324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180055329  jmp     short loc_1800553A7
0x18005532b  mov     eax, [rsi+4]
0x18005532e  lea     rcx, ds:3[rax*8]
0x180055336  add     rcx, rax; this
0x180055339  lea     r9, [rsi+rcx*8]; struct _DecoderBuffers *
0x18005533d  mov     r8, rbp; unsigned __int64
0x180055340  mov     rdx, [rsp+58h+arg_0]; struct ID3D12Device *
0x180055345  call    ?AllocateBitstreamBuffer@DecoderBuffersList@@AEAAJQEAUID3D12Device@@_KAEAU_DecoderBuffers@@@Z; DecoderBuffersList::AllocateBitstreamBuffer(ID3D12Device * const,unsigned __int64,_DecoderBuffers &)
0x18005534a  mov     ebx, eax
0x18005534c  lea     rcx, [rsp+58h+arg_0]
0x180055351  test    eax, eax
0x180055353  jnz     short loc_180055324
0x180055355  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005535a  mov     eax, [rsi+4]
0x18005535d  lea     rcx, ds:3[rax*8]
0x180055365  add     rcx, rax
0x180055368  lea     rdx, [rsi+rcx*8]
0x18005536c  mov     rcx, r14
0x18005536f  call    ??4?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(Microsoft::WRL::ComPtr<ID3D12Resource> const &)
0x180055374  cmp     qword ptr [r14], 0
0x180055378  jnz     short loc_1800553A7
0x18005537a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055381  jb      short loc_1800553A2
0x180055383  mov     edx, 0Fh
0x180055388  mov     r9, rsi
0x18005538b  lea     r8, WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids
0x180055392  mov     rcx, cs:WPP_GLOBAL_Control
0x180055399  mov     rcx, [rcx+10h]
0x18005539d  call    WPP_SF_q
0x1800553a2  mov     ebx, 80004005h
0x1800553a7  mov     eax, ebx
0x1800553a9  mov     rbx, [rsp+58h+arg_8]
0x1800553ae  mov     rbp, [rsp+58h+arg_10]
0x1800553b3  add     rsp, 40h
0x1800553b7  pop     r14
0x1800553b9  pop     rdi
0x1800553ba  pop     rsi
0x1800553bb  retn
```
