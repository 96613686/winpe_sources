# SC_DISK::SaveStorageProperty(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER *)

- ea: `0x140009ac0`
- end: `0x140009ba2`
- name: `?SaveStorageProperty@SC_DISK@@MEAAXW4_STORAGE_PROPERTY_ID@@PEAU_STORAGE_DESCRIPTOR_HEADER@@@Z`
- size: `226`
- prototype: `void __fastcall(SC_DISK *__hidden this, enum _STORAGE_PROPERTY_ID, struct _STORAGE_DESCRIPTOR_HEADER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140009ac0`
- `0x140010920`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b87`

## pseudocode

```c
void __fastcall SC_DISK::SaveStorageProperty(
        SC_DISK *this,
        enum _STORAGE_PROPERTY_ID a2,
        struct _STORAGE_DESCRIPTOR_HEADER *a3)
{
  __int64 v4; // rax
  PVOID *v5; // rbx

  if ( a2 > StorageDeviceResiliencyProperty )
  {
    switch ( a2 )
    {
      case '1':
        v4 = 392;
        break;
      case '9':
        v4 = 320;
        break;
      case ':':
        v4 = 344;
        break;
      case '<':
        v4 = 384;
        break;
      case 'A':
        ExFreePoolWithTag(a3, 0);
        return;
      default:
        goto LABEL_19;
    }
  }
  else
  {
    switch ( a2 )
    {
      case StorageDeviceResiliencyProperty:
        v4 = 352;
        break;
      case StorageDeviceWriteCacheProperty:
        v4 = 328;
        break;
      case StorageAccessAlignmentProperty:
        v4 = 312;
        break;
      case StorageDeviceSeekPenaltyProperty:
        v4 = 360;
        break;
      case StorageDeviceTrimProperty:
        v4 = 376;
        break;
      case StorageDeviceLBProvisioningProperty:
        v4 = 368;
        break;
      default:
LABEL_19:
        SC_DEVICE::SaveStorageProperty(this, a2, a3);
        return;
    }
  }
  v5 = (PVOID *)((char *)this + v4);
  if ( (SC_DISK *)((char *)this + v4) )
  {
    if ( *v5 )
      ExFreePoolWithTag(*v5, 0);
    *v5 = a3;
  }
}

```

## disassembly

```asm
0x140009ac0  mov     [rsp+arg_0], rbx
0x140009ac5  push    rdi
0x140009ac6  sub     rsp, 20h
0x140009aca  mov     rdi, r8
0x140009acd  mov     r10, rcx
0x140009ad0  cmp     edx, 0Eh
0x140009ad3  jg      short loc_140009B22
0x140009ad5  jz      short loc_140009B1B
0x140009ad7  mov     r9d, edx
0x140009ada  sub     r9d, 4
0x140009ade  jz      short loc_140009B14
0x140009ae0  sub     r9d, 2
0x140009ae4  jz      short loc_140009B0D
0x140009ae6  sub     r9d, 1
0x140009aea  jz      short loc_140009B06
0x140009aec  sub     r9d, 1
0x140009af0  jz      short loc_140009AFF
0x140009af2  cmp     r9d, 3
0x140009af6  jnz     short loc_140009B3D
0x140009af8  mov     eax, 170h
0x140009afd  jmp     short loc_140009B74
0x140009aff  mov     eax, 178h
0x140009b04  jmp     short loc_140009B74
0x140009b06  mov     eax, 168h
0x140009b0b  jmp     short loc_140009B74
0x140009b0d  mov     eax, 138h
0x140009b12  jmp     short loc_140009B74
0x140009b14  mov     eax, 148h
0x140009b19  jmp     short loc_140009B74
0x140009b1b  mov     eax, 160h
0x140009b20  jmp     short loc_140009B74
0x140009b22  mov     ecx, edx
0x140009b24  sub     ecx, 31h ; '1'
0x140009b27  jz      short loc_140009B6F
0x140009b29  sub     ecx, 8
0x140009b2c  jz      short loc_140009B68
0x140009b2e  sub     ecx, 1
0x140009b31  jz      short loc_140009B61
0x140009b33  sub     ecx, 2
0x140009b36  jz      short loc_140009B5A
0x140009b38  cmp     ecx, 5
0x140009b3b  jz      short loc_140009B47
0x140009b3d  mov     rcx, r10; this
0x140009b40  call    ?SaveStorageProperty@SC_DEVICE@@MEAAXW4_STORAGE_PROPERTY_ID@@PEAU_STORAGE_DESCRIPTOR_HEADER@@@Z; SC_DEVICE::SaveStorageProperty(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER *)
0x140009b45  jmp     short loc_140009B96
0x140009b47  xor     edx, edx; Tag
0x140009b49  mov     rcx, rdi; P
0x140009b4c  call    cs:__imp_ExFreePoolWithTag
0x140009b53  nop     dword ptr [rax+rax+00h]
0x140009b58  jmp     short loc_140009B96
0x140009b5a  mov     eax, 180h
0x140009b5f  jmp     short loc_140009B74
0x140009b61  mov     eax, 158h
0x140009b66  jmp     short loc_140009B74
0x140009b68  mov     eax, 140h
0x140009b6d  jmp     short loc_140009B74
0x140009b6f  mov     eax, 188h
0x140009b74  lea     rbx, [rax+r10]
0x140009b78  test    rbx, rbx
0x140009b7b  jz      short loc_140009B96
0x140009b7d  mov     rcx, [rbx]; P
0x140009b80  test    rcx, rcx
0x140009b83  jz      short loc_140009B93
0x140009b85  xor     edx, edx; Tag
0x140009b87  call    cs:__imp_ExFreePoolWithTag
0x140009b8e  nop     dword ptr [rax+rax+00h]
0x140009b93  mov     [rbx], rdi
0x140009b96  mov     rbx, [rsp+28h+arg_0]
0x140009b9b  add     rsp, 20h
0x140009b9f  pop     rdi
0x140009ba0  retn
```
