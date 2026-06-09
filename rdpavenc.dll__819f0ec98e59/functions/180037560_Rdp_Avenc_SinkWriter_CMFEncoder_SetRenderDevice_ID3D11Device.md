# Rdp::Avenc::SinkWriter::CMFEncoder::SetRenderDevice(ID3D11Device *)

- ea: `0x180037560`
- end: `0x18003765b`
- name: `?SetRenderDevice@CMFEncoder@SinkWriter@Avenc@Rdp@@QEAAXPEAUID3D11Device@@@Z`
- size: `251`
- prototype: `void __fastcall(Rdp::Avenc::SinkWriter::CMFEncoder *__hidden this, struct ID3D11Device *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180037670`

## callees

- `0x18000e848`
- `0x18002ace4`
- `0x180037560`
- `0x180089010`

## import_xrefs

- `MFPlat!MFCreateDXGIDeviceManager` at `0x1800375b7`
- `MFPlat!MFCreateDXGIDeviceManager` at `0x1800375b7`

## string_xrefs

- `0x1800375c2`: `Failed to create DXGI device manager`
- `0x1800375d1`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\SinkWriterProcessor/SinkWriterFrameProcessor.h`
- `0x18003760b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\SinkWriterProcessor/SinkWriterFrameProcessor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Rdp::Avenc::SinkWriter::CMFEncoder::SetRenderDevice(
        Rdp::Avenc::SinkWriter::CMFEncoder *this,
        struct ID3D11Device *a2)
{
  bool v4; // al
  IMFDXGIDeviceManager **v5; // rdi
  UINT *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // eax
  const char *v9; // [rsp+28h] [rbp-30h]
  _BYTE v10[8]; // [rsp+30h] [rbp-28h] BYREF
  char v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-18h]
  __int64 v13; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Rdp::Utils::Graphics::CRenderDevice::CRenderDevice((Rdp::Utils::Graphics::CRenderDevice *)v10, a2);
  v4 = v11 == 0;
  *((_BYTE *)this + 152) = v11 == 0;
  if ( v4 )
  {
    v5 = (IMFDXGIDeviceManager **)((char *)this + 104);
    if ( *((_QWORD *)this + 13) )
    {
      v6 = (UINT *)((char *)this + 128);
    }
    else
    {
      *v5 = 0;
      v6 = (UINT *)((char *)this + 128);
      v7 = MFCreateDXGIDeviceManager(v6, v5);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\SinkWriterProcessor/SinkWriterFrameProcessor.h",
        (const char *)v7,
        (int)"Failed to create DXGI device manager",
        v9);
    }
    v8 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, struct ID3D11Device *, _QWORD))(*v5)->lpVtbl->ResetDevice)(
           *v5,
           a2,
           *v6);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\SinkWriterProcessor/SinkWriterFrameProcessor.h",
      (const char *)v8,
      (int)"Failed to reset D3D device",
      v9);
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
}

```

## disassembly

```asm
0x180037560  mov     [rsp+arg_0], rbx
0x180037565  mov     [rsp+arg_8], rsi
0x18003756a  push    rdi
0x18003756b  sub     rsp, 50h
0x18003756f  mov     rsi, rdx
0x180037572  mov     rbx, rcx
0x180037575  lea     rcx, [rsp+58h+var_28]; this
0x18003757a  call    ??0CRenderDevice@Graphics@Utils@Rdp@@QEAA@PEAUID3D11Device@@@Z; Rdp::Utils::Graphics::CRenderDevice::CRenderDevice(ID3D11Device *)
0x18003757f  nop
0x180037580  cmp     [rsp+58h+var_20], 0
0x180037585  setz    al
0x180037588  mov     [rbx+98h], al
0x18003758e  test    al, al
0x180037590  jz      loc_18003761D
0x180037596  lea     rdi, [rbx+68h]
0x18003759a  cmp     qword ptr [rdi], 0
0x18003759e  jz      short loc_1800375A6
0x1800375a0  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800375a4  jmp     short loc_1800375E2
0x1800375a6  mov     qword ptr [rdi], 0
0x1800375ad  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800375b1  mov     rdx, rdi; ppDeviceManager
0x1800375b4  mov     rcx, rbx; resetToken
0x1800375b7  call    cs:__imp_MFCreateDXGIDeviceManager
0x1800375bd  mov     rcx, [rsp+58h]; this
0x1800375c2  lea     rdx, aFailedToCreate_1; "Failed to create DXGI device manager"
0x1800375c9  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800375ce  mov     r9d, eax; char *
0x1800375d1  lea     r8, aOnecoreuapTerm_39; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800375d8  mov     edx, 116h; void *
0x1800375dd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800375e2  mov     rcx, [rdi]
0x1800375e5  mov     rax, [rcx]
0x1800375e8  mov     r8d, [rbx]
0x1800375eb  mov     rdx, rsi
0x1800375ee  mov     rax, [rax+38h]
0x1800375f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375f7  mov     rcx, [rsp+58h]; this
0x1800375fc  lea     rdx, aFailedToResetD; "Failed to reset D3D device"
0x180037603  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180037608  mov     r9d, eax; char *
0x18003760b  lea     r8, aOnecoreuapTerm_39; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180037612  mov     edx, 11Ah; void *
0x180037617  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003761c  nop
0x18003761d  mov     rcx, [rsp+58h+var_10]
0x180037622  test    rcx, rcx
0x180037625  jz      short loc_180037634
0x180037627  mov     rax, [rcx]
0x18003762a  mov     rax, [rax+10h]
0x18003762e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037633  nop
0x180037634  mov     rcx, [rsp+58h+var_18]
0x180037639  test    rcx, rcx
0x18003763c  jz      short loc_18003764B
0x18003763e  mov     rax, [rcx]
0x180037641  mov     rax, [rax+10h]
0x180037645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003764a  nop
0x18003764b  mov     rbx, [rsp+58h+arg_0]
0x180037650  mov     rsi, [rsp+58h+arg_8]
0x180037655  add     rsp, 50h
0x180037659  pop     rdi
0x18003765a  retn
```
