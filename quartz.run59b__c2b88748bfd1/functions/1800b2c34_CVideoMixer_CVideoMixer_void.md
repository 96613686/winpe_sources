# CVideoMixer::~CVideoMixer(void)

- ea: `0x1800b2c34`
- end: `0x1800b2db5`
- name: `??1CVideoMixer@@UEAA@XZ`
- size: `385`
- prototype: `void __fastcall(CVideoMixer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b2dc0`

## callees

- `0x18002d864`
- `0x180038498`
- `0x1800b2bec`
- `0x1800b2c34`
- `0x1800b2dfc`
- `0x1800b61cc`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800b2cf3`
- `KERNEL32!Sleep` at `0x1800b2cf3`
- `KERNEL32!WaitForSingleObject` at `0x1800b2d10`
- `KERNEL32!WaitForSingleObject` at `0x1800b2d10`
- `KERNEL32!DeleteCriticalSection` at `0x1800b2d96`
- `KERNEL32!DeleteCriticalSection` at `0x1800b2d96`
- `KERNEL32!CloseHandle` at `0x1800b2d23`
- `KERNEL32!CloseHandle` at `0x1800b2d3b`
- `KERNEL32!CloseHandle` at `0x1800b2d23`
- `KERNEL32!CloseHandle` at `0x1800b2d3b`
- `GDI32!DeleteObject` at `0x1800b2c78`
- `GDI32!DeleteObject` at `0x1800b2c78`
- `USER32!PostThreadMessageW` at `0x1800b2ce1`
- `USER32!PostThreadMessageW` at `0x1800b2ce1`

## pseudocode

```c
void __fastcall CVideoMixer::~CVideoMixer(CVideoMixer *this)
{
  void *v2; // rcx
  unsigned int v3; // edx
  int i; // edi
  void *v5; // rcx
  __int64 j; // rdi
  CVideoMixerStream *v7; // rcx

  *(_QWORD *)this = &CVideoMixer::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CVideoMixer::`vftable'{for `IVMRMixerControlInternal'};
  *((_QWORD *)this + 4) = &CVideoMixer::`vftable'{for `IVMRMixerStream'};
  *((_QWORD *)this + 5) = &CVideoMixer::`vftable'{for `IVMRMixerBitmap'};
  v2 = (void *)*((_QWORD *)this + 278);
  if ( v2 )
    DeleteObject(v2);
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 2248);
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 2192);
  CVideoMixer::FreeSurface(this, 0);
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 584);
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 96);
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 104);
  if ( *((_QWORD *)this + 21) )
  {
    for ( i = 0; i < 100; ++i )
    {
      if ( PostThreadMessageW(*((_DWORD *)this + 44), 0x400u, 0, 0) )
        break;
      Sleep(0);
    }
    WaitForSingleObject(*((HANDLE *)this + 21), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 21));
  }
  v5 = (void *)*((_QWORD *)this + 20);
  if ( v5 )
    CloseHandle(v5);
  if ( *((_QWORD *)this + 19) )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 36); j = (unsigned int)(j + 1) )
    {
      v7 = *(CVideoMixerStream **)(*((_QWORD *)this + 19) + 8 * j);
      if ( v7 )
        CVideoMixerStream::`scalar deleting destructor'(v7, v3);
    }
  }
  operator delete(*((void **)this + 19));
  CVideoMixer::CIIVMRImageCompositor::~CIIVMRImageCompositor((CVideoMixer *)((char *)this + 592));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
}

```

## disassembly

```asm
0x1800b2c34  mov     [rsp+arg_0], rbx
0x1800b2c39  push    rdi
0x1800b2c3a  sub     rsp, 20h
0x1800b2c3e  lea     rax, ??_7CVideoMixer@@6BCUnknown@@@; const CVideoMixer::`vftable'{for `CUnknown'}
0x1800b2c45  mov     rbx, rcx
0x1800b2c48  mov     [rcx], rax
0x1800b2c4b  lea     rax, ??_7CVideoMixer@@6BIVMRMixerControlInternal@@@; const CVideoMixer::`vftable'{for `IVMRMixerControlInternal'}
0x1800b2c52  mov     [rcx+18h], rax
0x1800b2c56  lea     rax, ??_7CVideoMixer@@6BIVMRMixerStream@@@; const CVideoMixer::`vftable'{for `IVMRMixerStream'}
0x1800b2c5d  mov     [rcx+20h], rax
0x1800b2c61  lea     rax, ??_7CVideoMixer@@6BIVMRMixerBitmap@@@; const CVideoMixer::`vftable'{for `IVMRMixerBitmap'}
0x1800b2c68  mov     [rcx+28h], rax
0x1800b2c6c  mov     rcx, [rcx+8B0h]; ho
0x1800b2c73  test    rcx, rcx
0x1800b2c76  jz      short loc_1800B2C84
0x1800b2c78  call    cs:__imp_DeleteObject
0x1800b2c7f  nop     dword ptr [rax+rax+00h]
0x1800b2c84  lea     rcx, [rbx+8C8h]
0x1800b2c8b  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2c90  lea     rcx, [rbx+890h]
0x1800b2c97  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2c9c  xor     edx, edx; int
0x1800b2c9e  mov     rcx, rbx; this
0x1800b2ca1  call    ?FreeSurface@CVideoMixer@@AEAAXH@Z; CVideoMixer::FreeSurface(int)
0x1800b2ca6  lea     rcx, [rbx+248h]
0x1800b2cad  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2cb2  lea     rcx, [rbx+60h]
0x1800b2cb6  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2cbb  lea     rcx, [rbx+68h]
0x1800b2cbf  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800b2cc4  cmp     qword ptr [rbx+0A8h], 0
0x1800b2ccc  jz      short loc_1800B2D2F
0x1800b2cce  xor     edi, edi
0x1800b2cd0  mov     ecx, [rbx+0B0h]; idThread
0x1800b2cd6  xor     r9d, r9d; lParam
0x1800b2cd9  xor     r8d, r8d; wParam
0x1800b2cdc  mov     edx, 400h; Msg
0x1800b2ce1  call    cs:__imp_PostThreadMessageW
0x1800b2ce8  nop     dword ptr [rax+rax+00h]
0x1800b2ced  test    eax, eax
0x1800b2cef  jnz     short loc_1800B2D06
0x1800b2cf1  xor     ecx, ecx; dwMilliseconds
0x1800b2cf3  call    cs:__imp_Sleep
0x1800b2cfa  nop     dword ptr [rax+rax+00h]
0x1800b2cff  inc     edi
0x1800b2d01  cmp     edi, 64h ; 'd'
0x1800b2d04  jl      short loc_1800B2CD0
0x1800b2d06  mov     rcx, [rbx+0A8h]; hHandle
0x1800b2d0d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2d10  call    cs:__imp_WaitForSingleObject
0x1800b2d17  nop     dword ptr [rax+rax+00h]
0x1800b2d1c  mov     rcx, [rbx+0A8h]; hObject
0x1800b2d23  call    cs:__imp_CloseHandle
0x1800b2d2a  nop     dword ptr [rax+rax+00h]
0x1800b2d2f  mov     rcx, [rbx+0A0h]; hObject
0x1800b2d36  test    rcx, rcx
0x1800b2d39  jz      short loc_1800B2D47
0x1800b2d3b  call    cs:__imp_CloseHandle
0x1800b2d42  nop     dword ptr [rax+rax+00h]
0x1800b2d47  cmp     qword ptr [rbx+98h], 0
0x1800b2d4f  jz      short loc_1800B2D7A
0x1800b2d51  xor     edi, edi
0x1800b2d53  cmp     [rbx+90h], edi
0x1800b2d59  jbe     short loc_1800B2D7A
0x1800b2d5b  mov     rax, [rbx+98h]
0x1800b2d62  mov     rcx, [rax+rdi*8]; this
0x1800b2d66  test    rcx, rcx
0x1800b2d69  jz      short loc_1800B2D70
0x1800b2d6b  call    ??_GCVideoMixerStream@@QEAAPEAXI@Z; CVideoMixerStream::`scalar deleting destructor'(uint)
0x1800b2d70  inc     edi
0x1800b2d72  cmp     edi, [rbx+90h]
0x1800b2d78  jb      short loc_1800B2D5B
0x1800b2d7a  mov     rcx, [rbx+98h]; Block
0x1800b2d81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b2d86  lea     rcx, [rbx+250h]; this
0x1800b2d8d  call    ??1CIIVMRImageCompositor@CVideoMixer@@QEAA@XZ; CVideoMixer::CIIVMRImageCompositor::~CIIVMRImageCompositor(void)
0x1800b2d92  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800b2d96  call    cs:__imp_DeleteCriticalSection
0x1800b2d9d  nop     dword ptr [rax+rax+00h]
0x1800b2da2  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800b2da9  mov     rbx, [rsp+28h+arg_0]
0x1800b2dae  add     rsp, 20h
0x1800b2db2  pop     rdi
0x1800b2db3  retn
```
