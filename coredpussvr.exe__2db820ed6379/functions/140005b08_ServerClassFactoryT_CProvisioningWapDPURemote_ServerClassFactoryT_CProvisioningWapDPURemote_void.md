# ServerClassFactoryT<CProvisioningWapDPURemote>::~ServerClassFactoryT<CProvisioningWapDPURemote>(void)

- ea: `0x140005b08`
- end: `0x140005b36`
- name: `??1?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@UEAA@XZ`
- size: `46`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005d10`
- `0x140005d80`

## callees

- `0x140005b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005b24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005b24`

## pseudocode

```c
void __fastcall ServerClassFactoryT<CProvisioningWapDPURemote>::~ServerClassFactoryT<CProvisioningWapDPURemote>(
        _QWORD *a1)
{
  _QWORD *v1; // rcx

  *a1 = &ServerClassFactoryT<CProvisioningWapDPURemote>::`vftable';
  v1 = a1 + 2;
  if ( *((_BYTE *)v1 + 40) )
  {
    *((_BYTE *)v1 + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x140005b08  sub     rsp, 28h
0x140005b0c  lea     rax, ??_7?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@6B@; const ServerClassFactoryT<CProvisioningWapDPURemote>::`vftable'
0x140005b13  mov     [rcx], rax
0x140005b16  add     rcx, 10h; lpCriticalSection
0x140005b1a  cmp     byte ptr [rcx+28h], 0
0x140005b1e  jz      short loc_140005B30
0x140005b20  mov     byte ptr [rcx+28h], 0
0x140005b24  call    cs:__imp_DeleteCriticalSection
0x140005b2b  nop     dword ptr [rax+rax+00h]
0x140005b30  add     rsp, 28h
0x140005b34  retn
```
