# CKsQueue::FrameToFrameCopy(_KSPSTREAM_POINTER *,_KSPSTREAM_POINTER *)

- ea: `0x18000fcb8`
- end: `0x18000fe37`
- name: `?FrameToFrameCopy@CKsQueue@@AEAAXPEAU_KSPSTREAM_POINTER@@0@Z`
- size: `383`
- prototype: `void __fastcall(CKsQueue *__hidden this, struct _KSPSTREAM_POINTER *, struct _KSPSTREAM_POINTER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002960`
- `0x1800066b0`

## callees

- `0x18000b7bc`
- `0x18000fcb8`
- `0x180019cb0`
- `0x180019d00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fd6e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fdcd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fd6e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fdcd`

## pseudocode

```c
void __fastcall CKsQueue::FrameToFrameCopy(
        CKsQueue *this,
        struct _KSPSTREAM_POINTER *a2,
        struct _KSPSTREAM_POINTER *a3)
{
  struct _KSPSTREAM_POINTER *v4; // rbp
  __int64 v6; // rsi
  UCHAR *MappedSystemVa; // r14
  _MDL *Mdl; // rcx
  PKSSTREAM_HEADER *p_StreamHeader; // rbx
  _MDL *v10; // rcx
  PVOID v11; // rax

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      61,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids);
  }
  if ( v4->Queue->GeneratesMappings(v4->Queue) )
  {
    LODWORD(v6) = v4->Public.StreamHeader->DataUsed;
    Mdl = v4->FrameHeader->Mdl;
    if ( (Mdl->MdlFlags & 5) != 0 )
      MappedSystemVa = (UCHAR *)Mdl->MappedSystemVa;
    else
      MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000020u);
  }
  else
  {
    v6 = v4->Public.OffsetOut.Count - v4->Public.OffsetOut.Remaining;
    MappedSystemVa = &v4->Public.OffsetOut.Data[-v6];
  }
  if ( this->GeneratesMappings(this) )
  {
    p_StreamHeader = &a3->Public.StreamHeader;
    if ( a3->Public.StreamHeader->FrameExtent < (unsigned int)v6 )
      return;
    v10 = a3->FrameHeader->Mdl;
    if ( (v10->MdlFlags & 5) != 0 )
      v11 = v10->MappedSystemVa;
    else
      v11 = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000020u);
    memmove(v11, MappedSystemVa, (unsigned int)v6);
  }
  else
  {
    if ( a3->Public.OffsetOut.Remaining < (unsigned int)v6 )
      return;
    memmove(a3->Public.OffsetOut.Data, MappedSystemVa, (unsigned int)v6);
    a3->Public.OffsetOut.Remaining -= v6;
    a3->Public.OffsetOut.Data += (unsigned int)v6;
    p_StreamHeader = &a3->Public.StreamHeader;
  }
  (*p_StreamHeader)->OptionsFlags = v4->Public.StreamHeader->OptionsFlags;
  (*p_StreamHeader)->DataUsed = v6;
}

```

## disassembly

```asm
0x18000fcb8  push    rbx
0x18000fcba  push    rbp
0x18000fcbb  push    rsi
0x18000fcbc  push    rdi
0x18000fcbd  push    r14
0x18000fcbf  push    r15
0x18000fcc1  sub     rsp, 38h
0x18000fcc5  mov     rdi, r8
0x18000fcc8  mov     rbp, rdx
0x18000fccb  mov     rbx, rcx
0x18000fcce  lea     rax, WPP_RECORDER_INITIALIZED
0x18000fcd5  xor     r15d, r15d
0x18000fcd8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000fcdf  jz      short loc_18000FD0E
0x18000fce1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fce8  cmp     [rcx+48h], r15w
0x18000fced  jz      short loc_18000FD0E
0x18000fcef  mov     rcx, [rcx+40h]
0x18000fcf3  lea     rax, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x18000fcfa  lea     r9d, [r15+3Dh]
0x18000fcfe  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x18000fd03  lea     r8d, [r15+1]
0x18000fd07  mov     dl, 5
0x18000fd09  call    WPP_RECORDER_SF_
0x18000fd0e  mov     rcx, [rbp+48h]
0x18000fd12  mov     rax, [rcx]
0x18000fd15  mov     rax, [rax+0D0h]
0x18000fd1c  call    _guard_dispatch_icall
0x18000fd21  test    al, al
0x18000fd23  jnz     short loc_18000FD3D
0x18000fd25  mov     esi, [rbp+98h]
0x18000fd2b  sub     esi, [rbp+9Ch]
0x18000fd31  mov     r14, [rbp+90h]
0x18000fd38  sub     r14, rsi
0x18000fd3b  jmp     short loc_18000FD7D
0x18000fd3d  mov     rax, [rbp+70h]
0x18000fd41  mov     esi, [rax+24h]
0x18000fd44  mov     rax, [rbp+50h]
0x18000fd48  mov     rcx, [rax+28h]; MemoryDescriptorList
0x18000fd4c  test    byte ptr [rcx+0Ah], 5
0x18000fd50  jz      short loc_18000FD58
0x18000fd52  mov     r14, [rcx+18h]
0x18000fd56  jmp     short loc_18000FD7D
0x18000fd58  xor     r9d, r9d; RequestedAddress
0x18000fd5b  mov     [rsp+68h+Priority], 40000020h; Priority
0x18000fd63  xor     edx, edx; AccessMode
0x18000fd65  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x18000fd6a  lea     r8d, [r9+1]; CacheType
0x18000fd6e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fd75  nop     dword ptr [rax+rax+00h]
0x18000fd7a  mov     r14, rax
0x18000fd7d  mov     rcx, [rbx]
0x18000fd80  mov     rax, [rcx+0D0h]
0x18000fd87  mov     rcx, rbx
0x18000fd8a  call    _guard_dispatch_icall
0x18000fd8f  test    al, al
0x18000fd91  jz      short loc_18000FDE9
0x18000fd93  lea     rbx, [rdi+70h]
0x18000fd97  mov     rcx, [rbx]
0x18000fd9a  cmp     [rcx+20h], esi
0x18000fd9d  jb      loc_18000FE29
0x18000fda3  mov     rax, [rdi+50h]
0x18000fda7  mov     rcx, [rax+28h]; MemoryDescriptorList
0x18000fdab  test    byte ptr [rcx+0Ah], 5
0x18000fdaf  jz      short loc_18000FDB7
0x18000fdb1  mov     rax, [rcx+18h]
0x18000fdb5  jmp     short loc_18000FDD9
0x18000fdb7  xor     r9d, r9d; RequestedAddress
0x18000fdba  mov     [rsp+68h+Priority], 40000020h; Priority
0x18000fdc2  xor     edx, edx; AccessMode
0x18000fdc4  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x18000fdc9  lea     r8d, [r9+1]; CacheType
0x18000fdcd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fdd4  nop     dword ptr [rax+rax+00h]
0x18000fdd9  mov     r8d, esi; Size
0x18000fddc  mov     rdx, r14; Src
0x18000fddf  mov     rcx, rax; void *
0x18000fde2  call    memmove
0x18000fde7  jmp     short loc_18000FE16
0x18000fde9  cmp     [rdi+9Ch], esi
0x18000fdef  jb      short loc_18000FE29
0x18000fdf1  mov     rcx, [rdi+90h]; void *
0x18000fdf8  mov     rdx, r14; Src
0x18000fdfb  mov     r8d, esi; Size
0x18000fdfe  mov     ebx, esi
0x18000fe00  call    memmove
0x18000fe05  sub     [rdi+9Ch], esi
0x18000fe0b  add     [rdi+90h], rbx
0x18000fe12  lea     rbx, [rdi+70h]
0x18000fe16  mov     rax, [rbp+70h]
0x18000fe1a  mov     rcx, [rbx]
0x18000fe1d  mov     eax, [rax+30h]
0x18000fe20  mov     [rcx+30h], eax
0x18000fe23  mov     rax, [rbx]
0x18000fe26  mov     [rax+24h], esi
0x18000fe29  add     rsp, 38h
0x18000fe2d  pop     r15
0x18000fe2f  pop     r14
0x18000fe31  pop     rdi
0x18000fe32  pop     rsi
0x18000fe33  pop     rbp
0x18000fe34  pop     rbx
0x18000fe35  retn
```
