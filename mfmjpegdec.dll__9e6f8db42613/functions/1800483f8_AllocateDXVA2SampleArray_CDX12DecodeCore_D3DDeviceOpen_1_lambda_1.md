# AllocateDXVA2SampleArray__CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1___

- ea: `0x1800483f8`
- end: `0x180048583`
- name: `AllocateDXVA2SampleArray__CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1___`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800499c0`

## callees

- `0x180020598`
- `0x180024bf4`
- `0x18003a54c`
- `0x18003a628`
- `0x1800483f8`
- `0x1800485dc`
- `0x18004892c`
- `0x18004897c`
- `0x180048a84`
- `0x18004a11c`
- `0x18004a9f0`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AllocateDXVA2SampleArray__CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1___(
        _DWORD *a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v8; // rbx
  unsigned __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  char *v13; // rdi
  unsigned int v14; // esi
  int v15; // eax
  int v16; // ebx
  unsigned int v18; // edx
  _QWORD *v19; // [rsp+30h] [rbp-28h] BYREF
  __int64 v20[4]; // [rsp+38h] [rbp-20h] BYREF

  v8 = a2;
  v20[0] = a2;
  v9 = (unsigned __int64)a2 << 6;
  if ( !is_mul_ok(a2, 0x40u) )
    v9 = -1;
  v10 = __CFADD__(v9, 8);
  v11 = v9 + 8;
  if ( v10 )
    v11 = -1;
  v12 = operator new[](v11);
  v19 = v12;
  if ( v12 )
  {
    *v12 = v8;
    v13 = (char *)(v12 + 1);
    `eh vector constructor iterator'(
      v12 + 1,
      0x40u,
      (unsigned int)v8,
      (void (*)(void *))CDXVABufferTracker::CDXVABufferTracker,
      (void (*)(void *))CDXVABufferTracker::~CDXVABufferTracker);
  }
  else
  {
    v13 = 0;
  }
  v20[1] = (__int64)v13;
  if ( !v13 )
    return 2147942414LL;
  memset_0(v13, 0, v8 << 6);
  v14 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v19 = 0;
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v19);
      v15 = CDX12DecodeCore::D3DDeviceOpen_::_1_::_lambda_1_::operator()(a4, v14, &v19);
      v16 = v15;
      if ( v15 < 0 )
        break;
      if ( v15 != 1 )
      {
        v20[0] = 0;
        v16 = Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(&v19, v20);
        if ( v16 < 0
          || (v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20[0] + 48LL))(
                      v20[0],
                      (unsigned int)(3 * *a1 * a1[1]) >> 1),
              v16 < 0) )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
          break;
        }
        CDXVABufferTracker::reset((CDXVABufferTracker *)&v13[64 * (unsigned __int64)v14]);
        Microsoft::WRL::ComPtr<IMFTrackedBuffer>::operator=(&v13[64 * (unsigned __int64)v14], &v19);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
      }
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v19);
      if ( ++v14 >= a2 )
        goto LABEL_16;
    }
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v19);
    CDXVABufferTracker::`vector deleting destructor'((CDXVABufferTracker *)v13, v18);
    return (unsigned int)v16;
  }
  else
  {
LABEL_16:
    *a3 = v13;
    return 0;
  }
}

```

## disassembly

```asm
0x1800483f8  push    rbp
0x1800483fa  push    rbx
0x1800483fb  push    rsi
0x1800483fc  push    rdi
0x1800483fd  push    r12
0x1800483ff  push    r13
0x180048401  push    r14
0x180048403  push    r15
0x180048405  mov     rbp, rsp
0x180048408  sub     rsp, 58h
0x18004840c  mov     r12, r9
0x18004840f  mov     r15, r8
0x180048412  mov     r14d, edx
0x180048415  mov     r13, rcx
0x180048418  mov     ebx, edx
0x18004841a  mov     [rbp+var_20], rbx
0x18004841e  mov     esi, 40h ; '@'
0x180048423  mov     eax, esi
0x180048425  mul     r14
0x180048428  lea     rcx, [rsi-41h]
0x18004842c  cmovb   rax, rcx
0x180048430  add     rax, 8
0x180048434  cmovb   rax, rcx
0x180048438  mov     rcx, rax; unsigned __int64
0x18004843b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048440  mov     [rbp+var_28], rax
0x180048444  test    rax, rax
0x180048447  jz      short loc_180048472
0x180048449  mov     [rax], rbx
0x18004844c  lea     rdi, [rax+8]
0x180048450  lea     rax, ??1CDXVABufferTracker@@QEAA@XZ; CDXVABufferTracker::~CDXVABufferTracker(void)
0x180048457  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x18004845c  lea     r9, ??0CDXVABufferTracker@@QEAA@XZ; void (*)(void *)
0x180048463  mov     r8d, ebx; unsigned __int64
0x180048466  mov     edx, esi; unsigned __int64
0x180048468  mov     rcx, rdi; void *
0x18004846b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180048470  jmp     short loc_180048474
0x180048472  xor     edi, edi
0x180048474  mov     [rbp+var_18], rdi
0x180048478  test    rdi, rdi
0x18004847b  jz      loc_18004856D
0x180048481  shl     rbx, 6
0x180048485  mov     r8, rbx; Size
0x180048488  xor     edx, edx; Val
0x18004848a  mov     rcx, rdi; void *
0x18004848d  call    memset_0
0x180048492  xor     esi, esi
0x180048494  test    r14d, r14d
0x180048497  jz      loc_180048546
0x18004849d  mov     [rbp+var_28], 0
0x1800484a5  lea     rcx, [rbp+var_28]
0x1800484a9  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800484ae  lea     r8, [rbp+var_28]
0x1800484b2  mov     edx, esi
0x1800484b4  mov     rcx, r12
0x1800484b7  call    _CDX12DecodeCore__D3DDeviceOpen____1____lambda_1___operator__
0x1800484bc  mov     ebx, eax
0x1800484be  test    eax, eax
0x1800484c0  js      loc_180048557
0x1800484c6  cmp     eax, 1
0x1800484c9  jz      short loc_180048532
0x1800484cb  mov     [rbp+var_20], 0
0x1800484d3  lea     rdx, [rbp+var_20]
0x1800484d7  lea     rcx, [rbp+var_28]
0x1800484db  call    ??$As@UIMFMediaBuffer@@@?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFMediaBuffer>>)
0x1800484e0  mov     ebx, eax
0x1800484e2  test    eax, eax
0x1800484e4  js      short loc_18004854D
0x1800484e6  mov     rcx, [rbp+var_20]
0x1800484ea  mov     r8, [rcx]
0x1800484ed  mov     eax, [r13+4]
0x1800484f1  imul    eax, [r13+0]
0x1800484f6  lea     edx, [rax+rax*2]
0x1800484f9  shr     edx, 1
0x1800484fb  mov     rax, [r8+30h]
0x1800484ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048504  mov     ebx, eax
0x180048506  test    eax, eax
0x180048508  js      short loc_18004854D
0x18004850a  mov     ebx, esi
0x18004850c  shl     rbx, 6
0x180048510  add     rbx, rdi
0x180048513  mov     rcx, rbx; this
0x180048516  call    ?reset@CDXVABufferTracker@@QEAAXXZ; CDXVABufferTracker::reset(void)
0x18004851b  lea     rdx, [rbp+var_28]
0x18004851f  mov     rcx, rbx
0x180048522  call    ??4?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMFTrackedBuffer>::operator=(Microsoft::WRL::ComPtr<IMFTrackedBuffer> const &)
0x180048527  nop
0x180048528  lea     rcx, [rbp+var_20]
0x18004852c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048531  nop
0x180048532  lea     rcx, [rbp+var_28]
0x180048536  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18004853b  inc     esi
0x18004853d  cmp     esi, r14d
0x180048540  jb      loc_18004849D
0x180048546  mov     [r15], rdi
0x180048549  xor     eax, eax
0x18004854b  jmp     short loc_180048572
0x18004854d  lea     rcx, [rbp+var_20]
0x180048551  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048556  nop
0x180048557  lea     rcx, [rbp+var_28]
0x18004855b  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180048560  nop
0x180048561  mov     rcx, rdi; this
0x180048564  call    ??_ECDXVABufferTracker@@QEAAPEAXI@Z; CDXVABufferTracker::`vector deleting destructor'(uint)
0x180048569  mov     eax, ebx
0x18004856b  jmp     short loc_180048572
0x18004856d  mov     eax, 8007000Eh
0x180048572  add     rsp, 58h
0x180048576  pop     r15
0x180048578  pop     r14
0x18004857a  pop     r13
0x18004857c  pop     r12
0x18004857e  pop     rdi
0x18004857f  pop     rsi
0x180048580  pop     rbx
0x180048581  pop     rbp
0x180048582  retn
```
