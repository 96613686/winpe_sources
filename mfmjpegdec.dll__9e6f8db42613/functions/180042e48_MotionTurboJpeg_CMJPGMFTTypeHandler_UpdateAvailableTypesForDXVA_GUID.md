# MotionTurboJpeg::CMJPGMFTTypeHandler::UpdateAvailableTypesForDXVA(_GUID)

- ea: `0x180042e48`
- end: `0x180042f00`
- name: `?UpdateAvailableTypesForDXVA@CMJPGMFTTypeHandler@MotionTurboJpeg@@QEAAJU_GUID@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(MotionTurboJpeg::CMJPGMFTTypeHandler *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ff0c`

## callees

- `0x18001eb58`
- `0x180020598`
- `0x180042e48`
- `0x18004570c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall MotionTurboJpeg::CMJPGMFTTypeHandler::UpdateAvailableTypesForDXVA(
        MotionTurboJpeg::CMJPGMFTTypeHandler *this,
        struct _GUID *a2)
{
  struct IMFMediaType **v2; // rax
  struct IMFMediaType *v3; // rbx
  struct IMFMediaType *v4; // r14
  struct IMFMediaType *v7; // rdi
  unsigned int inited; // edi
  struct IMFMediaType *v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11[4]; // [rsp+28h] [rbp-20h] BYREF

  v2 = (struct IMFMediaType **)*((_QWORD *)this + 5);
  v3 = 0;
  v4 = 0;
  v10 = 0;
  v7 = *v2;
  if ( *v2 )
  {
    ((void (__fastcall *)(struct IMFMediaType *))v7->lpVtbl->AddRef)(*v2);
    v11[0] = 0;
    v3 = v7;
    v10 = v7;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
    v4 = v7;
  }
  inited = CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(this, 1u);
  if ( !inited )
  {
    inited = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v4->lpVtbl->SetGUID)(
               v4,
               &MF_MT_SUBTYPE,
               a2);
    if ( !inited )
      CMFTSimpleTypeHandler::SetAvailableOutputType(this, 0, v3);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return inited;
}

```

## disassembly

```asm
0x180042e48  mov     [rsp+arg_10], rbx
0x180042e4d  mov     [rsp+arg_18], rbp
0x180042e52  push    rsi
0x180042e53  push    rdi
0x180042e54  push    r14
0x180042e56  sub     rsp, 30h
0x180042e5a  mov     rax, [rcx+28h]
0x180042e5e  xor     ebx, ebx
0x180042e60  xor     r14d, r14d
0x180042e63  mov     [rsp+48h+var_28], rbx
0x180042e68  mov     rbp, rdx
0x180042e6b  mov     rsi, rcx
0x180042e6e  mov     rdi, [rax]
0x180042e71  test    rdi, rdi
0x180042e74  jz      short loc_180042E9F
0x180042e76  mov     rax, [rdi]
0x180042e79  mov     rcx, rdi
0x180042e7c  mov     rax, [rax+8]
0x180042e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e85  mov     [rsp+48h+var_20], rbx
0x180042e8a  lea     rcx, [rsp+48h+var_20]
0x180042e8f  mov     rbx, rdi
0x180042e92  mov     [rsp+48h+var_28], rbx
0x180042e97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042e9c  mov     r14, rdi
0x180042e9f  mov     edx, 1; unsigned int
0x180042ea4  mov     rcx, rsi; this
0x180042ea7  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x180042eac  mov     edi, eax
0x180042eae  test    eax, eax
0x180042eb0  jnz     short loc_180042EE1
0x180042eb2  mov     rax, [r14]
0x180042eb5  lea     rdx, MF_MT_SUBTYPE
0x180042ebc  mov     r8, rbp
0x180042ebf  mov     rcx, r14
0x180042ec2  mov     rax, [rax+0C0h]
0x180042ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ece  mov     edi, eax
0x180042ed0  test    eax, eax
0x180042ed2  jnz     short loc_180042EE1
0x180042ed4  mov     r8, rbx; struct IMFMediaType *
0x180042ed7  xor     edx, edx; unsigned int
0x180042ed9  mov     rcx, rsi; this
0x180042edc  call    ?SetAvailableOutputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *)
0x180042ee1  lea     rcx, [rsp+48h+var_28]
0x180042ee6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042eeb  mov     rbx, [rsp+48h+arg_10]
0x180042ef0  mov     eax, edi
0x180042ef2  mov     rbp, [rsp+48h+arg_18]
0x180042ef7  add     rsp, 30h
0x180042efb  pop     r14
0x180042efd  pop     rdi
0x180042efe  pop     rsi
0x180042eff  retn
```
