# KsGetBusEnumIdentifier

- ea: `0x180035790`
- end: `0x1800358b7`
- name: `KsGetBusEnumIdentifier`
- size: `295`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b168`
- `0x180035790`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x180035814`
- `ntoskrnl!ProbeForWrite` at `0x180035814`
- `ntoskrnl!ExAllocatePool2` at `0x18003582e`
- `ntoskrnl!ExAllocatePool2` at `0x18003582e`

## pseudocode

```c
NTSTATUS __stdcall KsGetBusEnumIdentifier(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v3; // rax
  const wchar_t *v5; // r15
  __int64 v6; // rax
  ULONG_PTR v7; // rsi
  unsigned int Length; // eax
  SIZE_T v9; // rbx
  struct _IRP *Pool2; // r14
  HRESULT v11; // eax
  size_t v12; // [rsp+20h] [rbp-48h]
  size_t pcchNewDestLength; // [rsp+70h] [rbp+8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = *(_QWORD *)CurrentStackLocation->DeviceObject->DeviceExtension;
  if ( !v3 )
    return -1073741811;
  if ( !*(_DWORD *)(v3 + 16) )
    v3 = *(_QWORD *)(v3 + 40);
  v5 = (const wchar_t *)(v3 + 760);
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = (unsigned int)(2 * v6 + 2);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length )
  {
    if ( Length < (unsigned int)v7 )
      return -1073741789;
    v9 = CurrentStackLocation->Parameters.Read.Length;
    ProbeForWrite(Irp->UserBuffer, v9, 1u);
    Pool2 = (struct _IRP *)ExAllocatePool2(99, v9, 1869174611);
    Irp->AssociatedIrp.MasterIrp = Pool2;
    Irp->Flags |= 0x70u;
    v11 = v7 >> 1 == 0 ? 0x80070057 : 0;
    if ( v7 >> 1 )
    {
      v11 = StringCopyWorkerW((STRSAFE_LPWSTR)Pool2, v7 >> 1, &pcchNewDestLength, v5, v12);
      if ( v11 >= 0 )
      {
LABEL_17:
        Irp->IoStatus.Information = v7;
        return 0;
      }
      if ( v7 )
      {
        if ( v7 >> 1 )
          Pool2->Type = 0;
      }
    }
    if ( v11 < 0 )
    {
      Irp->IoStatus.Information = 0;
      return -1073741670;
    }
    goto LABEL_17;
  }
  Irp->IoStatus.Information = (unsigned int)v7;
  return -2147483643;
}

```

## disassembly

```asm
0x180035790  push    rbx
0x180035792  push    rsi
0x180035793  push    rdi
0x180035794  push    r12
0x180035796  push    r14
0x180035798  push    r15
0x18003579a  sub     rsp, 38h
0x18003579e  mov     rdi, rcx
0x1800357a1  mov     rcx, [rcx+0B8h]
0x1800357a8  mov     rax, [rcx+28h]
0x1800357ac  mov     rdx, [rax+40h]
0x1800357b0  mov     rax, [rdx]
0x1800357b3  xor     r12d, r12d
0x1800357b6  test    rax, rax
0x1800357b9  jnz     short loc_1800357C5
0x1800357bb  mov     eax, 0C000000Dh
0x1800357c0  jmp     loc_1800358A8
0x1800357c5  cmp     [rax+10h], r12d
0x1800357c9  jnz     short loc_1800357CF
0x1800357cb  mov     rax, [rax+28h]
0x1800357cf  lea     r15, [rax+2F8h]
0x1800357d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800357da  inc     rax
0x1800357dd  cmp     [r15+rax*2], r12w
0x1800357e2  jnz     short loc_1800357DA
0x1800357e4  lea     esi, ds:2[rax*2]
0x1800357eb  mov     eax, [rcx+8]
0x1800357ee  test    eax, eax
0x1800357f0  jz      loc_18003589D
0x1800357f6  cmp     eax, esi
0x1800357f8  jnb     short loc_180035804
0x1800357fa  mov     eax, 0C0000023h
0x1800357ff  jmp     loc_1800358A8
0x180035804  mov     rbx, rax
0x180035807  mov     r8d, 1; Alignment
0x18003580d  mov     rdx, rax; Length
0x180035810  mov     rcx, [rdi+70h]; Address
0x180035814  call    cs:__imp_ProbeForWrite
0x18003581b  nop     dword ptr [rax+rax+00h]
0x180035820  mov     r8d, 6F695753h
0x180035826  mov     rdx, rbx
0x180035829  mov     ecx, 63h ; 'c'
0x18003582e  call    cs:__imp_ExAllocatePool2
0x180035835  nop     dword ptr [rax+rax+00h]
0x18003583a  mov     r14, rax
0x18003583d  mov     [rdi+18h], rax
0x180035841  or      dword ptr [rdi+10h], 70h
0x180035845  mov     rbx, rsi
0x180035848  shr     rbx, 1
0x18003584b  mov     rax, rbx
0x18003584e  neg     rax
0x180035851  sbb     eax, eax
0x180035853  not     eax
0x180035855  and     eax, 80070057h
0x18003585a  test    rbx, rbx
0x18003585d  jz      short loc_180035884
0x18003585f  mov     r9, r15; pszSrc
0x180035862  lea     r8, [rsp+68h+pcchNewDestLength]; pcchNewDestLength
0x180035867  mov     rdx, rbx; cchDest
0x18003586a  mov     rcx, r14; pszDest
0x18003586d  call    StringCopyWorkerW
0x180035872  test    eax, eax
0x180035874  jns     short loc_180035893
0x180035876  test    rsi, rsi
0x180035879  jz      short loc_180035884
0x18003587b  test    rbx, rbx
0x18003587e  jz      short loc_180035884
0x180035880  mov     [r14], r12w
0x180035884  test    eax, eax
0x180035886  jns     short loc_180035893
0x180035888  mov     [rdi+38h], r12
0x18003588c  mov     eax, 0C000009Ah
0x180035891  jmp     short loc_1800358A8
0x180035893  mov     [rdi+38h], rsi
0x180035897  xor     eax, eax
0x180035899  jmp     short loc_1800358A8
0x18003589b  jmp     short loc_1800358A8
0x18003589d  mov     eax, esi
0x18003589f  mov     [rdi+38h], rax
0x1800358a3  mov     eax, 80000005h
0x1800358a8  add     rsp, 38h
0x1800358ac  pop     r15
0x1800358ae  pop     r14
0x1800358b0  pop     r12
0x1800358b2  pop     rdi
0x1800358b3  pop     rsi
0x1800358b4  pop     rbx
0x1800358b5  retn
```
