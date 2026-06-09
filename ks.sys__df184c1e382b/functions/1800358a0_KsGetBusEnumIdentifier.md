# KsGetBusEnumIdentifier

- ea: `0x1800358a0`
- end: `0x1800359c7`
- name: `KsGetBusEnumIdentifier`
- size: `295`
- prototype: `NTSTATUS __stdcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b168`
- `0x1800358a0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x180035924`
- `ntoskrnl!ProbeForWrite` at `0x180035924`
- `ntoskrnl!ExAllocatePool2` at `0x18003593e`
- `ntoskrnl!ExAllocatePool2` at `0x18003593e`

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
0x1800358a0  push    rbx
0x1800358a2  push    rsi
0x1800358a3  push    rdi
0x1800358a4  push    r12
0x1800358a6  push    r14
0x1800358a8  push    r15
0x1800358aa  sub     rsp, 38h
0x1800358ae  mov     rdi, rcx
0x1800358b1  mov     rcx, [rcx+0B8h]
0x1800358b8  mov     rax, [rcx+28h]
0x1800358bc  mov     rdx, [rax+40h]
0x1800358c0  mov     rax, [rdx]
0x1800358c3  xor     r12d, r12d
0x1800358c6  test    rax, rax
0x1800358c9  jnz     short loc_1800358D5
0x1800358cb  mov     eax, 0C000000Dh
0x1800358d0  jmp     loc_1800359B8
0x1800358d5  cmp     [rax+10h], r12d
0x1800358d9  jnz     short loc_1800358DF
0x1800358db  mov     rax, [rax+28h]
0x1800358df  lea     r15, [rax+2F8h]
0x1800358e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800358ea  inc     rax
0x1800358ed  cmp     [r15+rax*2], r12w
0x1800358f2  jnz     short loc_1800358EA
0x1800358f4  lea     esi, ds:2[rax*2]
0x1800358fb  mov     eax, [rcx+8]
0x1800358fe  test    eax, eax
0x180035900  jz      loc_1800359AD
0x180035906  cmp     eax, esi
0x180035908  jnb     short loc_180035914
0x18003590a  mov     eax, 0C0000023h
0x18003590f  jmp     loc_1800359B8
0x180035914  mov     rbx, rax
0x180035917  mov     r8d, 1; Alignment
0x18003591d  mov     rdx, rax; Length
0x180035920  mov     rcx, [rdi+70h]; Address
0x180035924  call    cs:__imp_ProbeForWrite
0x18003592b  nop     dword ptr [rax+rax+00h]
0x180035930  mov     r8d, 6F695753h
0x180035936  mov     rdx, rbx
0x180035939  mov     ecx, 63h ; 'c'
0x18003593e  call    cs:__imp_ExAllocatePool2
0x180035945  nop     dword ptr [rax+rax+00h]
0x18003594a  mov     r14, rax
0x18003594d  mov     [rdi+18h], rax
0x180035951  or      dword ptr [rdi+10h], 70h
0x180035955  mov     rbx, rsi
0x180035958  shr     rbx, 1
0x18003595b  mov     rax, rbx
0x18003595e  neg     rax
0x180035961  sbb     eax, eax
0x180035963  not     eax
0x180035965  and     eax, 80070057h
0x18003596a  test    rbx, rbx
0x18003596d  jz      short loc_180035994
0x18003596f  mov     r9, r15; pszSrc
0x180035972  lea     r8, [rsp+68h+pcchNewDestLength]; pcchNewDestLength
0x180035977  mov     rdx, rbx; cchDest
0x18003597a  mov     rcx, r14; pszDest
0x18003597d  call    StringCopyWorkerW
0x180035982  test    eax, eax
0x180035984  jns     short loc_1800359A3
0x180035986  test    rsi, rsi
0x180035989  jz      short loc_180035994
0x18003598b  test    rbx, rbx
0x18003598e  jz      short loc_180035994
0x180035990  mov     [r14], r12w
0x180035994  test    eax, eax
0x180035996  jns     short loc_1800359A3
0x180035998  mov     [rdi+38h], r12
0x18003599c  mov     eax, 0C000009Ah
0x1800359a1  jmp     short loc_1800359B8
0x1800359a3  mov     [rdi+38h], rsi
0x1800359a7  xor     eax, eax
0x1800359a9  jmp     short loc_1800359B8
0x1800359ab  jmp     short loc_1800359B8
0x1800359ad  mov     eax, esi
0x1800359af  mov     [rdi+38h], rax
0x1800359b3  mov     eax, 80000005h
0x1800359b8  add     rsp, 38h
0x1800359bc  pop     r15
0x1800359be  pop     r14
0x1800359c0  pop     r12
0x1800359c2  pop     rdi
0x1800359c3  pop     rsi
0x1800359c4  pop     rbx
0x1800359c5  retn
```
