# CKsQueue::FrameToFrameCopy(_KSPSTREAM_POINTER *,_KSPSTREAM_POINTER *)

- ea: `0x18000fca4`
- end: `0x18000fe23`
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
- `0x18000fca4`
- `0x180019c60`
- `0x180019cc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fd5a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fdb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fd5a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fdb9`

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
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids);
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
0x18000fca4  push    rbx
0x18000fca6  push    rbp
0x18000fca7  push    rsi
0x18000fca8  push    rdi
0x18000fca9  push    r14
0x18000fcab  push    r15
0x18000fcad  sub     rsp, 38h
0x18000fcb1  mov     rdi, r8
0x18000fcb4  mov     rbp, rdx
0x18000fcb7  mov     rbx, rcx
0x18000fcba  lea     rax, WPP_RECORDER_INITIALIZED
0x18000fcc1  xor     r15d, r15d
0x18000fcc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000fccb  jz      short loc_18000FCFA
0x18000fccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcd4  cmp     [rcx+48h], r15w
0x18000fcd9  jz      short loc_18000FCFA
0x18000fcdb  mov     rcx, [rcx+40h]
0x18000fcdf  lea     rax, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18000fce6  lea     r9d, [r15+3Dh]
0x18000fcea  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x18000fcef  lea     r8d, [r15+1]
0x18000fcf3  mov     dl, 5
0x18000fcf5  call    WPP_RECORDER_SF_
0x18000fcfa  mov     rcx, [rbp+48h]
0x18000fcfe  mov     rax, [rcx]
0x18000fd01  mov     rax, [rax+0D0h]
0x18000fd08  call    _guard_dispatch_icall
0x18000fd0d  test    al, al
0x18000fd0f  jnz     short loc_18000FD29
0x18000fd11  mov     esi, [rbp+98h]
0x18000fd17  sub     esi, [rbp+9Ch]
0x18000fd1d  mov     r14, [rbp+90h]
0x18000fd24  sub     r14, rsi
0x18000fd27  jmp     short loc_18000FD69
0x18000fd29  mov     rax, [rbp+70h]
0x18000fd2d  mov     esi, [rax+24h]
0x18000fd30  mov     rax, [rbp+50h]
0x18000fd34  mov     rcx, [rax+28h]; MemoryDescriptorList
0x18000fd38  test    byte ptr [rcx+0Ah], 5
0x18000fd3c  jz      short loc_18000FD44
0x18000fd3e  mov     r14, [rcx+18h]
0x18000fd42  jmp     short loc_18000FD69
0x18000fd44  xor     r9d, r9d; RequestedAddress
0x18000fd47  mov     [rsp+68h+Priority], 40000020h; Priority
0x18000fd4f  xor     edx, edx; AccessMode
0x18000fd51  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x18000fd56  lea     r8d, [r9+1]; CacheType
0x18000fd5a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fd61  nop     dword ptr [rax+rax+00h]
0x18000fd66  mov     r14, rax
0x18000fd69  mov     rcx, [rbx]
0x18000fd6c  mov     rax, [rcx+0D0h]
0x18000fd73  mov     rcx, rbx
0x18000fd76  call    _guard_dispatch_icall
0x18000fd7b  test    al, al
0x18000fd7d  jz      short loc_18000FDD5
0x18000fd7f  lea     rbx, [rdi+70h]
0x18000fd83  mov     rcx, [rbx]
0x18000fd86  cmp     [rcx+20h], esi
0x18000fd89  jb      loc_18000FE15
0x18000fd8f  mov     rax, [rdi+50h]
0x18000fd93  mov     rcx, [rax+28h]; MemoryDescriptorList
0x18000fd97  test    byte ptr [rcx+0Ah], 5
0x18000fd9b  jz      short loc_18000FDA3
0x18000fd9d  mov     rax, [rcx+18h]
0x18000fda1  jmp     short loc_18000FDC5
0x18000fda3  xor     r9d, r9d; RequestedAddress
0x18000fda6  mov     [rsp+68h+Priority], 40000020h; Priority
0x18000fdae  xor     edx, edx; AccessMode
0x18000fdb0  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x18000fdb5  lea     r8d, [r9+1]; CacheType
0x18000fdb9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fdc0  nop     dword ptr [rax+rax+00h]
0x18000fdc5  mov     r8d, esi; Size
0x18000fdc8  mov     rdx, r14; Src
0x18000fdcb  mov     rcx, rax; void *
0x18000fdce  call    memmove
0x18000fdd3  jmp     short loc_18000FE02
0x18000fdd5  cmp     [rdi+9Ch], esi
0x18000fddb  jb      short loc_18000FE15
0x18000fddd  mov     rcx, [rdi+90h]; void *
0x18000fde4  mov     rdx, r14; Src
0x18000fde7  mov     r8d, esi; Size
0x18000fdea  mov     ebx, esi
0x18000fdec  call    memmove
0x18000fdf1  sub     [rdi+9Ch], esi
0x18000fdf7  add     [rdi+90h], rbx
0x18000fdfe  lea     rbx, [rdi+70h]
0x18000fe02  mov     rax, [rbp+70h]
0x18000fe06  mov     rcx, [rbx]
0x18000fe09  mov     eax, [rax+30h]
0x18000fe0c  mov     [rcx+30h], eax
0x18000fe0f  mov     rax, [rbx]
0x18000fe12  mov     [rax+24h], esi
0x18000fe15  add     rsp, 38h
0x18000fe19  pop     r15
0x18000fe1b  pop     r14
0x18000fe1d  pop     rdi
0x18000fe1e  pop     rsi
0x18000fe1f  pop     rbp
0x18000fe20  pop     rbx
0x18000fe21  retn
```
