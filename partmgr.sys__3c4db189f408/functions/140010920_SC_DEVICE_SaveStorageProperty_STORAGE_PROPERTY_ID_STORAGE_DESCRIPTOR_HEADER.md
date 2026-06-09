# SC_DEVICE::SaveStorageProperty(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER *)

- ea: `0x140010920`
- end: `0x140010a29`
- name: `?SaveStorageProperty@SC_DEVICE@@MEAAXW4_STORAGE_PROPERTY_ID@@PEAU_STORAGE_DESCRIPTOR_HEADER@@@Z`
- size: `265`
- prototype: `void(SC_DEVICE *__hidden this, enum _STORAGE_PROPERTY_ID, struct _STORAGE_DESCRIPTOR_HEADER *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009ac0`

## callees

- `0x140009ba8`
- `0x140010920`
- `0x140011140`
- `0x140011440`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010964`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400109a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010964`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400109a8`

## pseudocode

```c
void __fastcall SC_DEVICE::SaveStorageProperty(
        SC_DEVICE *this,
        enum _STORAGE_PROPERTY_ID a2,
        struct _STORAGE_DESCRIPTOR_HEADER *a3)
{
  __int64 v6; // rdi
  void *v7; // rcx
  __int64 v8; // r9
  unsigned int v9; // eax

  if ( a2 )
  {
    switch ( a2 )
    {
      case StorageAdapterProperty:
        v6 = 152;
        break;
      case StorageDeviceIdProperty:
        v6 = 184;
        break;
      case StorageMiniportProperty:
        v6 = 192;
        break;
      case StorageDeviceFaultDomainProperty:
        v6 = 176;
        break;
      case StorageDeviceUnsafeShutdownCount|StorageDeviceIdProperty:
        v6 = 168;
        break;
      default:
        if ( a3 )
          ExFreePoolWithTag(a3, 0);
        return;
    }
  }
  else
  {
    v6 = 160;
  }
  v7 = *(void **)((char *)this + v6);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  *(_QWORD *)((char *)this + v6) = a3;
  if ( a2 )
  {
    if ( a2 == StorageDeviceFaultDomainProperty )
    {
      memset((char *)this + 88, 0, 0x40u);
      v8 = *((_QWORD *)this + 22);
      if ( v8 )
      {
        v9 = 4;
        if ( *(_DWORD *)(v8 + 8) < 4u )
          v9 = *(_DWORD *)(v8 + 8);
        memmove((char *)this + 88, (const void *)(v8 + 12), 16LL * v9);
      }
    }
  }
  else
  {
    ScExtractDeviceStrings(
      *((struct _STORAGE_DEVICE_DESCRIPTOR **)this + 20),
      (struct _UNICODE_STRING *)((char *)this + 24),
      (struct _UNICODE_STRING *)((char *)this + 40),
      (struct _UNICODE_STRING *)((char *)this + 56),
      (struct _UNICODE_STRING *)((char *)this + 72));
  }
}

```

## disassembly

```asm
0x140010920  push    rbx
0x140010922  push    rbp
0x140010923  push    rsi
0x140010924  push    rdi
0x140010925  sub     rsp, 38h
0x140010929  mov     rbp, r8
0x14001092c  mov     esi, edx
0x14001092e  mov     rbx, rcx
0x140010931  mov     r9d, edx
0x140010934  test    edx, edx
0x140010936  jz      short loc_140010998
0x140010938  sub     r9d, 1
0x14001093c  jz      short loc_140010991
0x14001093e  sub     r9d, 1
0x140010942  jz      short loc_14001098A
0x140010944  sub     r9d, 3
0x140010948  jz      short loc_140010983
0x14001094a  sub     r9d, 0Eh
0x14001094e  jz      short loc_14001097C
0x140010950  cmp     r9d, 2Ch ; ','
0x140010954  jz      short loc_140010975
0x140010956  test    r8, r8
0x140010959  jz      loc_140010A1F
0x14001095f  xor     edx, edx; Tag
0x140010961  mov     rcx, r8; P
0x140010964  call    cs:__imp_ExFreePoolWithTag
0x14001096b  nop     dword ptr [rax+rax+00h]
0x140010970  jmp     loc_140010A1F
0x140010975  mov     edi, 0A8h
0x14001097a  jmp     short loc_14001099D
0x14001097c  mov     edi, 0B0h
0x140010981  jmp     short loc_14001099D
0x140010983  mov     edi, 0C0h
0x140010988  jmp     short loc_14001099D
0x14001098a  mov     edi, 0B8h
0x14001098f  jmp     short loc_14001099D
0x140010991  mov     edi, 98h
0x140010996  jmp     short loc_14001099D
0x140010998  mov     edi, 0A0h
0x14001099d  mov     rcx, [rdi+rcx]; P
0x1400109a1  test    rcx, rcx
0x1400109a4  jz      short loc_1400109B4
0x1400109a6  xor     edx, edx; Tag
0x1400109a8  call    cs:__imp_ExFreePoolWithTag
0x1400109af  nop     dword ptr [rax+rax+00h]
0x1400109b4  mov     [rdi+rbx], rbp
0x1400109b8  test    esi, esi
0x1400109ba  jz      short loc_1400109FE
0x1400109bc  cmp     esi, 13h
0x1400109bf  jnz     short loc_140010A1F
0x1400109c1  xor     edx, edx; Val
0x1400109c3  lea     r8d, [rsi+2Dh]; Size
0x1400109c7  lea     rcx, [rbx+58h]; void *
0x1400109cb  call    memset
0x1400109d0  mov     r9, [rbx+0B0h]
0x1400109d7  test    r9, r9
0x1400109da  jz      short loc_140010A1F
0x1400109dc  mov     edx, [r9+8]
0x1400109e0  lea     eax, [rsi-0Fh]
0x1400109e3  cmp     edx, eax
0x1400109e5  lea     rcx, [rbx+58h]; void *
0x1400109e9  cmovb   eax, edx
0x1400109ec  lea     rdx, [r9+0Ch]; Src
0x1400109f0  mov     r8d, eax
0x1400109f3  shl     r8, 4; Size
0x1400109f7  call    memmove
0x1400109fc  jmp     short loc_140010A1F
0x1400109fe  mov     rcx, [rbx+0A0h]; struct _STORAGE_DEVICE_DESCRIPTOR *
0x140010a05  lea     rax, [rbx+48h]
0x140010a09  lea     r9, [rbx+38h]; struct _UNICODE_STRING *
0x140010a0d  mov     [rsp+58h+var_38], rax; struct _UNICODE_STRING *
0x140010a12  lea     r8, [rbx+28h]; struct _UNICODE_STRING *
0x140010a16  lea     rdx, [rbx+18h]; struct _UNICODE_STRING *
0x140010a1a  call    ?ScExtractDeviceStrings@@YAJPEAU_STORAGE_DEVICE_DESCRIPTOR@@PEAU_UNICODE_STRING@@111@Z; ScExtractDeviceStrings(_STORAGE_DEVICE_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140010a1f  add     rsp, 38h
0x140010a23  pop     rdi
0x140010a24  pop     rsi
0x140010a25  pop     rbp
0x140010a26  pop     rbx
0x140010a27  retn
```
