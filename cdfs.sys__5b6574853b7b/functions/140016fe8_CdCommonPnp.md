# CdCommonPnp

- ea: `0x140016fe8`
- end: `0x140017141`
- name: `CdCommonPnp`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001160`
- `0x1400021c4`
- `0x140016fe8`
- `0x140017148`
- `0x14001734c`
- `0x1400174c8`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140017097`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400170dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017116`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017097`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400170dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017116`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001700b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001700b`
- `ntoskrnl!IofCallDriver` at `0x1400170fa`
- `ntoskrnl!IofCallDriver` at `0x1400170fa`

## pseudocode

```c
__int64 __fastcall CdCommonPnp(_DWORD *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PDEVICE_OBJECT DeviceObject; // rsi
  struct _IRP **p_CurrentIrp; // rsi
  __int64 v8; // rcx
  struct _ERESOURCE *v9; // rcx
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  NTSTATUS v12; // r8d
  IRP *v13; // rdx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( DeviceObject->Size != 1168 || (p_CurrentIrp = &DeviceObject[1].CurrentIrp) == 0 || *(_WORD *)p_CurrentIrp != 770 )
  {
    ExReleaseResourceLite(&Resource);
    v10 = -1073741811;
    v13 = a2;
    v12 = -1073741811;
    goto LABEL_17;
  }
  a1[8] |= 4u;
  if ( !p_CurrentIrp[1] )
    goto LABEL_14;
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 1u:
      return (unsigned int)CdPnpQueryRemove(a1, a2, p_CurrentIrp);
    case 2u:
      return (unsigned int)CdPnpRemove(a1, a2, p_CurrentIrp);
    case 3u:
      CdAcquireResource(a1, p_CurrentIrp + 16, 0, 0);
      ExReleaseResourceLite(&Resource);
      CdUnlockVolumeInternal(v8, p_CurrentIrp, 0);
      v9 = (struct _ERESOURCE *)(p_CurrentIrp + 16);
LABEL_15:
      ExReleaseResourceLite(v9);
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
      v11 = IofCallDriver((PDEVICE_OBJECT)p_CurrentIrp[2], a2);
      v12 = 0;
      v10 = v11;
      v13 = 0;
LABEL_17:
      CdCompleteRequest(a1, v13, v12);
      return v10;
  }
  if ( CurrentStackLocation->MinorFunction != 23 )
  {
LABEL_14:
    v9 = &Resource;
    goto LABEL_15;
  }
  return (unsigned int)CdPnpSurpriseRemove(a1, a2, p_CurrentIrp);
}

```

## disassembly

```asm
0x140016fe8  push    rbx
0x140016fea  push    rbp
0x140016feb  push    rsi
0x140016fec  push    rdi
0x140016fed  sub     rsp, 28h
0x140016ff1  mov     rbx, [rdx+0B8h]
0x140016ff8  mov     rdi, rdx
0x140016ffb  mov     rbp, rcx
0x140016ffe  mov     dl, 1; Wait
0x140017000  lea     rcx, Resource; Resource
0x140017007  mov     rsi, [rbx+28h]
0x14001700b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140017012  nop     dword ptr [rax+rax+00h]
0x140017017  mov     eax, 490h
0x14001701c  cmp     [rsi+2], ax
0x140017020  jnz     loc_14001710F
0x140017026  add     rsi, 170h
0x14001702d  jz      loc_14001710F
0x140017033  mov     eax, 302h
0x140017038  cmp     [rsi], ax
0x14001703b  jnz     loc_14001710F
0x140017041  or      dword ptr [rbp+20h], 4
0x140017045  cmp     qword ptr [rsi+8], 0
0x14001704a  jz      loc_1400170D5
0x140017050  movzx   ecx, byte ptr [rbx+1]
0x140017054  sub     ecx, 1
0x140017057  jz      short loc_1400170C3
0x140017059  sub     ecx, 1
0x14001705c  jz      short loc_1400170B3
0x14001705e  sub     ecx, 1
0x140017061  jz      short loc_140017078
0x140017063  cmp     ecx, 14h
0x140017066  jnz     short loc_1400170D5
0x140017068  mov     r8, rsi
0x14001706b  mov     rdx, rdi
0x14001706e  mov     rcx, rbp
0x140017071  call    CdPnpSurpriseRemove
0x140017076  jmp     short loc_1400170D1
0x140017078  lea     rbx, [rsi+80h]
0x14001707f  xor     r9d, r9d
0x140017082  mov     rdx, rbx
0x140017085  xor     r8d, r8d
0x140017088  mov     rcx, rbp
0x14001708b  call    CdAcquireResource
0x140017090  lea     rcx, Resource; Resource
0x140017097  call    cs:__imp_ExReleaseResourceLite
0x14001709e  nop     dword ptr [rax+rax+00h]
0x1400170a3  xor     r8d, r8d
0x1400170a6  mov     rdx, rsi
0x1400170a9  call    CdUnlockVolumeInternal
0x1400170ae  mov     rcx, rbx
0x1400170b1  jmp     short loc_1400170DC
0x1400170b3  mov     r8, rsi
0x1400170b6  mov     rdx, rdi
0x1400170b9  mov     rcx, rbp
0x1400170bc  call    CdPnpRemove
0x1400170c1  jmp     short loc_1400170D1
0x1400170c3  mov     r8, rsi
0x1400170c6  mov     rdx, rdi
0x1400170c9  mov     rcx, rbp
0x1400170cc  call    CdPnpQueryRemove
0x1400170d1  mov     ebx, eax
0x1400170d3  jmp     short loc_140017135
0x1400170d5  lea     rcx, Resource; Resource
0x1400170dc  call    cs:__imp_ExReleaseResourceLite
0x1400170e3  nop     dword ptr [rax+rax+00h]
0x1400170e8  inc     byte ptr [rdi+43h]
0x1400170eb  mov     rdx, rdi; Irp
0x1400170ee  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400170f6  mov     rcx, [rsi+10h]; DeviceObject
0x1400170fa  call    cs:__imp_IofCallDriver
0x140017101  nop     dword ptr [rax+rax+00h]
0x140017106  xor     r8d, r8d
0x140017109  mov     ebx, eax
0x14001710b  xor     edx, edx
0x14001710d  jmp     short loc_14001712D
0x14001710f  lea     rcx, Resource; Resource
0x140017116  call    cs:__imp_ExReleaseResourceLite
0x14001711d  nop     dword ptr [rax+rax+00h]
0x140017122  mov     ebx, 0C000000Dh
0x140017127  mov     rdx, rdi
0x14001712a  mov     r8d, ebx
0x14001712d  mov     rcx, rbp
0x140017130  call    CdCompleteRequest
0x140017135  mov     eax, ebx
0x140017137  add     rsp, 28h
0x14001713b  pop     rdi
0x14001713c  pop     rsi
0x14001713d  pop     rbp
0x14001713e  pop     rbx
0x14001713f  retn
```
