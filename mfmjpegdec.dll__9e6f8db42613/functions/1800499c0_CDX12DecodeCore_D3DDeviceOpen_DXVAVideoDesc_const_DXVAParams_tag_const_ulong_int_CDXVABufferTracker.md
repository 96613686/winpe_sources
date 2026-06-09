# CDX12DecodeCore::D3DDeviceOpen(DXVAVideoDesc const &,DXVAParams_tag const *,ulong &,int,CDXVABufferTracker * *)

- ea: `0x1800499c0`
- end: `0x180049b90`
- name: `?D3DDeviceOpen@CDX12DecodeCore@@UEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@AEAKHPEAPEAVCDXVABufferTracker@@@Z`
- size: `464`
- prototype: `__int64 __usercall@<rax>(CDX12DecodeCore *__hidden this@<rcx>, const struct DXVAVideoDesc *@<rdx>, const struct DXVAParams_tag *@<r8>, unsigned int *@<r9>, int, struct CDXVABufferTracker **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800436f0`

## callees

- `0x180020598`
- `0x1800483f8`
- `0x18004862c`
- `0x180048ac4`
- `0x1800499c0`
- `0x18004aa94`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499f3`

## pseudocode

```c
__int64 __fastcall CDX12DecodeCore::D3DDeviceOpen(
        CDX12DecodeCore *this,
        const struct DXVAVideoDesc *a2,
        const struct DXVAParams_tag *a3,
        unsigned int *a4,
        int a5,
        struct CDXVABufferTracker **a6)
{
  HANDLE EventW; // rax
  __int64 v12; // rcx
  unsigned int Resources; // ebx
  _QWORD *v14; // r15
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, GUID *, char *); // rbx
  __int128 *v17; // rax
  __int64 v18; // rdx
  __int128 v19; // xmm2
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int64 v22; // r10
  _OWORD v23[4]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v24[136]; // [rsp+70h] [rbp-88h] BYREF

  if ( *((_QWORD *)this + 6) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 6) = EventW;
    if ( !EventW )
      return 2147942414LL;
  }
  v12 = *((_QWORD *)this + 174);
  *((_BYTE *)this + 1385) = 0;
  if ( v12 )
  {
    v14 = (_QWORD *)((char *)this + 1400);
    if ( *((_QWORD *)this + 175) )
    {
      Resources = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
      if ( Resources )
        goto LABEL_16;
      *v14 = 0;
    }
    Resources = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 174) + 48LL))(
                  *((_QWORD *)this + 174),
                  (char *)this + 1400);
    if ( !Resources )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
      v15 = *((_QWORD *)this + 174);
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, char *))(*(_QWORD *)v15 + 32LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
      Resources = v16(v15, *v14, &IID_ID3D12Device, (char *)this + 16);
      if ( !Resources )
      {
        Resources = CDX12DecodeCore::AllocateResources(this, a2, a3);
        if ( !Resources )
        {
          *a4 = *((_DWORD *)this + 28);
          if ( a6 )
          {
            v17 = (__int128 *)CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1_::_lambda_1_(v24, this, a2);
            v18 = *((unsigned int *)this + 28);
            v19 = *v17;
            v20 = v17[2];
            v23[1] = v17[1];
            v21 = v17[3];
            v23[0] = v19;
            v23[3] = v21;
            v23[2] = v20;
            Resources = AllocateDXVA2SampleArray__CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1___(a2, v18, v22, v23);
            if ( !Resources )
              Resources = (*(__int64 (__fastcall **)(CDX12DecodeCore *, const struct DXVAVideoDesc *))(*(_QWORD *)this + 176LL))(
                            this,
                            a2);
          }
          else
          {
            Resources = -2147024809;
          }
        }
      }
    }
    goto LABEL_16;
  }
  Resources = -2147217408;
LABEL_16:
  if ( g_wppLevels )
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
      Resources,
      this);
  return Resources;
}

```

## disassembly

```asm
0x1800499c0  push    rbx
0x1800499c2  push    rbp
0x1800499c3  push    rsi
0x1800499c4  push    rdi
0x1800499c5  push    r12
0x1800499c7  push    r13
0x1800499c9  push    r14
0x1800499cb  push    r15
0x1800499cd  sub     rsp, 0B8h
0x1800499d4  xor     edi, edi
0x1800499d6  mov     r12, r9
0x1800499d9  mov     r13, r8
0x1800499dc  mov     rbp, rdx
0x1800499df  mov     r14, rcx
0x1800499e2  cmp     [rcx+30h], rdi
0x1800499e6  jz      short loc_180049A0C
0x1800499e8  xor     r9d, r9d; lpName
0x1800499eb  lea     edx, [rdi+1]; bManualReset
0x1800499ee  xor     r8d, r8d; bInitialState
0x1800499f1  xor     ecx, ecx; lpEventAttributes
0x1800499f3  call    cs:__imp_CreateEventW
0x1800499f9  mov     [r14+30h], rax
0x1800499fd  test    rax, rax
0x180049a00  jnz     short loc_180049A0C
0x180049a02  mov     eax, 8007000Eh
0x180049a07  jmp     loc_180049B7C
0x180049a0c  mov     rcx, [r14+570h]
0x180049a13  mov     [r14+569h], dil
0x180049a1a  test    rcx, rcx
0x180049a1d  jnz     short loc_180049A29
0x180049a1f  mov     ebx, 80041000h
0x180049a24  jmp     loc_180049B4D
0x180049a29  lea     r15, [r14+578h]
0x180049a30  mov     rdx, [r15]
0x180049a33  test    rdx, rdx
0x180049a36  jz      short loc_180049A51
0x180049a38  mov     rax, [rcx]
0x180049a3b  mov     rax, [rax+18h]
0x180049a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a44  mov     ebx, eax
0x180049a46  test    eax, eax
0x180049a48  jnz     loc_180049B4D
0x180049a4e  mov     [r15], rdi
0x180049a51  mov     rcx, [r14+570h]
0x180049a58  mov     rdx, r15
0x180049a5b  mov     rax, [rcx]
0x180049a5e  mov     rax, [rax+30h]
0x180049a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a67  mov     ebx, eax
0x180049a69  test    eax, eax
0x180049a6b  jnz     loc_180049B4D
0x180049a71  lea     rdi, [r14+10h]
0x180049a75  mov     rcx, rdi
0x180049a78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049a7d  mov     rsi, [r14+570h]
0x180049a84  mov     rcx, rdi
0x180049a87  mov     rax, [rsi]
0x180049a8a  mov     rbx, [rax+20h]
0x180049a8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180049a93  mov     rdx, [r15]
0x180049a96  lea     r8, IID_ID3D12Device
0x180049a9d  mov     r9, rdi
0x180049aa0  mov     rcx, rsi
0x180049aa3  mov     rax, rbx
0x180049aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aab  mov     ebx, eax
0x180049aad  test    eax, eax
0x180049aaf  jnz     loc_180049B4D
0x180049ab5  mov     r8, r13; struct DXVAParams_tag *
0x180049ab8  mov     rdx, rbp; struct DXVAVideoDesc *
0x180049abb  mov     rcx, r14; this
0x180049abe  call    ?AllocateResources@CDX12DecodeCore@@IEAAJAEBUDXVAVideoDesc@@PEBUDXVAParams_tag@@@Z; CDX12DecodeCore::AllocateResources(DXVAVideoDesc const &,DXVAParams_tag const *)
0x180049ac3  mov     ebx, eax
0x180049ac5  test    eax, eax
0x180049ac7  jnz     loc_180049B4D
0x180049acd  mov     r10, [rsp+0F8h+arg_28]
0x180049ad5  mov     eax, [r14+70h]
0x180049ad9  mov     [r12], eax
0x180049add  test    r10, r10
0x180049ae0  jnz     short loc_180049AE9
0x180049ae2  mov     ebx, 80070057h
0x180049ae7  jmp     short loc_180049B4D
0x180049ae9  mov     r8, rbp
0x180049aec  lea     rcx, [rsp+0F8h+var_88]
0x180049af1  mov     rdx, r14
0x180049af4  call    _CDX12DecodeCore__D3DDeviceOpen____1____lambda_1____lambda_1_
0x180049af9  mov     edx, [r14+70h]
0x180049afd  lea     r9, [rsp+0F8h+var_C8]
0x180049b02  mov     r8, r10
0x180049b05  mov     rcx, rbp
0x180049b08  movups  xmm0, xmmword ptr [rax+10h]
0x180049b0c  movups  xmm2, xmmword ptr [rax]
0x180049b0f  movups  xmm1, xmmword ptr [rax+20h]
0x180049b13  movaps  [rsp+0F8h+var_B8], xmm0
0x180049b18  movups  xmm0, xmmword ptr [rax+30h]
0x180049b1c  movaps  [rsp+0F8h+var_C8], xmm2
0x180049b21  movaps  [rsp+0F8h+var_98], xmm0
0x180049b26  movaps  [rsp+0F8h+var_A8], xmm1
0x180049b2b  call    AllocateDXVA2SampleArray__CDX12DecodeCore__D3DDeviceOpen____1____lambda_1___
0x180049b30  mov     ebx, eax
0x180049b32  test    eax, eax
0x180049b34  jnz     short loc_180049B4D
0x180049b36  mov     rax, [r14]
0x180049b39  mov     rdx, rbp
0x180049b3c  mov     rcx, r14
0x180049b3f  mov     rax, [rax+0B0h]
0x180049b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b4b  mov     ebx, eax
0x180049b4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180049b54  jb      short loc_180049B7A
0x180049b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b5d  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x180049b64  mov     edx, 1Ah
0x180049b69  mov     [rsp+0F8h+var_D8], r14
0x180049b6e  mov     r9d, ebx
0x180049b71  mov     rcx, [rcx+10h]
0x180049b75  call    WPP_SF_dq
0x180049b7a  mov     eax, ebx
0x180049b7c  add     rsp, 0B8h
0x180049b83  pop     r15
0x180049b85  pop     r14
0x180049b87  pop     r13
0x180049b89  pop     r12
0x180049b8b  pop     rdi
0x180049b8c  pop     rsi
0x180049b8d  pop     rbp
0x180049b8e  pop     rbx
0x180049b8f  retn
```
