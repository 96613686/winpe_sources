# MountMgrDeletePointsDbOnly

- ea: `0x14000c528`
- end: `0x14000c71e`
- name: `MountMgrDeletePointsDbOnly`
- size: `502`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000adf0`
- `0x14000c528`
- `0x1400168b0`
- `0x140019ca0`
- `0x140019e30`

## import_xrefs

- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000c696`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000c696`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5c0`
- `ntoskrnl!ExAllocatePool2` at `0x14000c62e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5c0`
- `ntoskrnl!ExAllocatePool2` at `0x14000c62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c66a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c66a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c6a9`

## string_xrefs

- `0x14000c68b`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrDeletePointsDbOnly(__int64 a1, __int64 a2)
{
  int Points; // ebx
  __int64 v5; // r8
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v9; // rdi
  unsigned int i; // esi
  WCHAR *Pool2; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  _WORD *v14; // rax
  void *v15; // r14
  unsigned int v16; // ecx
  UNICODE_STRING ValueName; // [rsp+20h] [rbp-48h] BYREF

  ValueName = 0;
  Points = MountMgrQueryPoints(a1, a2);
  if ( Points >= 0 )
  {
    v9 = *(_QWORD *)(a2 + 24);
    for ( i = 0; i < *(_DWORD *)(v9 + 4); ++i )
    {
      ValueName.Length = *(_WORD *)(v9 + 24LL * i + 12);
      ValueName.MaximumLength = ValueName.Length + 2;
      Pool2 = (WCHAR *)ExAllocatePool2(258, (unsigned __int16)(ValueName.Length + 2), 1098149453);
      ValueName.Buffer = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 230);
        return 3221225626LL;
      }
      memmove(Pool2, (const void *)(v9 + *(unsigned int *)(v9 + 24LL * i + 8)), ValueName.Length);
      ValueName.Buffer[(unsigned __int64)ValueName.Length >> 1] = 0;
      if ( *(_DWORD *)(v9 + 4) == 1 )
      {
        if ( (unsigned __int8)IsDriveLetter(&ValueName) )
        {
          v13 = *(unsigned __int16 *)(v9 + 24LL * i + 20);
          if ( (_WORD)v13 )
          {
            v14 = (_WORD *)ExAllocatePool2(258, v13 + 4, 1098149453);
            v15 = v14;
            if ( v14 )
            {
              v16 = *(unsigned __int16 *)(v9 + 24LL * i + 20);
              *v14 = v16;
              memmove(v14 + 1, (const void *)(v9 + *(unsigned int *)(v9 + 24LL * i + 16)), v16);
              CreateNoDriveLetterEntry(v15);
              ExFreePoolWithTag(v15, 0);
            }
          }
        }
      }
      LOBYTE(v12) = 1;
      Points = DeleteSymbolicLinkNameFromMemory(a1, &ValueName, v12);
      RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", ValueName.Buffer);
      ExFreePoolWithTag(ValueName.Buffer, 0);
      if ( Points < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v7 = 231;
          goto LABEL_5;
        }
        return (unsigned int)Points;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v7 = 229;
LABEL_5:
      WPP_SF_L(v6->AttachedDevice, v7, v5, (unsigned int)Points);
    }
  }
  return (unsigned int)Points;
}

```

## disassembly

```asm
0x14000c528  push    rbx
0x14000c52a  push    rbp
0x14000c52b  push    rsi
0x14000c52c  push    rdi
0x14000c52d  push    r14
0x14000c52f  push    r15
0x14000c531  sub     rsp, 38h
0x14000c535  xorps   xmm0, xmm0
0x14000c538  mov     rdi, rdx
0x14000c53b  movups  xmmword ptr [rsp+68h+ValueName.Length], xmm0
0x14000c540  mov     rbp, rcx
0x14000c543  call    MountMgrQueryPoints
0x14000c548  xor     r15d, r15d
0x14000c54b  mov     ebx, eax
0x14000c54d  test    eax, eax
0x14000c54f  jns     short loc_14000C58D
0x14000c551  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c558  lea     rax, WPP_GLOBAL_Control
0x14000c55f  cmp     rcx, rax
0x14000c562  jz      short loc_14000C57D
0x14000c564  mov     edx, [rcx+2Ch]
0x14000c567  test    dl, 1
0x14000c56a  jz      short loc_14000C57D
0x14000c56c  mov     edx, 0E5h
0x14000c571  mov     rcx, [rcx+18h]
0x14000c575  mov     r9d, ebx
0x14000c578  call    WPP_SF_L
0x14000c57d  mov     eax, ebx
0x14000c57f  add     rsp, 38h
0x14000c583  pop     r15
0x14000c585  pop     r14
0x14000c587  pop     rdi
0x14000c588  pop     rsi
0x14000c589  pop     rbp
0x14000c58a  pop     rbx
0x14000c58b  retn
0x14000c58d  mov     rdi, [rdi+18h]
0x14000c591  mov     esi, r15d
0x14000c594  cmp     esi, [rdi+4]
0x14000c597  jnb     short loc_14000C57D
0x14000c599  mov     eax, esi
0x14000c59b  mov     ecx, 102h
0x14000c5a0  mov     r8d, 41746E4Dh
0x14000c5a6  lea     rbx, [rax+rax*2]
0x14000c5aa  movzx   eax, word ptr [rdi+rbx*8+0Ch]
0x14000c5af  mov     [rsp+68h+ValueName.Length], ax
0x14000c5b4  add     ax, 2
0x14000c5b8  movzx   edx, ax
0x14000c5bb  mov     [rsp+68h+ValueName.MaximumLength], dx
0x14000c5c0  call    cs:__imp_ExAllocatePool2
0x14000c5c7  nop     dword ptr [rax+rax+00h]
0x14000c5cc  mov     [rsp+68h+ValueName.Buffer], rax
0x14000c5d1  test    rax, rax
0x14000c5d4  jz      loc_14000C6EC
0x14000c5da  mov     edx, [rdi+rbx*8+8]
0x14000c5de  mov     rcx, rax; void *
0x14000c5e1  movzx   r8d, [rsp+68h+ValueName.Length]; Size
0x14000c5e7  add     rdx, rdi; Src
0x14000c5ea  call    memmove
0x14000c5ef  movzx   edx, [rsp+68h+ValueName.Length]
0x14000c5f4  mov     rax, [rsp+68h+ValueName.Buffer]
0x14000c5f9  shr     rdx, 1
0x14000c5fc  mov     [rax+rdx*2], r15w
0x14000c601  cmp     dword ptr [rdi+4], 1
0x14000c605  jnz     short loc_14000C676
0x14000c607  lea     rcx, [rsp+68h+ValueName]; String2
0x14000c60c  call    IsDriveLetter
0x14000c611  test    al, al
0x14000c613  jz      short loc_14000C676
0x14000c615  movzx   eax, word ptr [rdi+rbx*8+14h]
0x14000c61a  test    ax, ax
0x14000c61d  jz      short loc_14000C676
0x14000c61f  lea     rdx, [rax+4]
0x14000c623  mov     ecx, 102h
0x14000c628  mov     r8d, 41746E4Dh
0x14000c62e  call    cs:__imp_ExAllocatePool2
0x14000c635  nop     dword ptr [rax+rax+00h]
0x14000c63a  mov     r14, rax
0x14000c63d  test    rax, rax
0x14000c640  jz      short loc_14000C676
0x14000c642  movzx   ecx, word ptr [rdi+rbx*8+14h]
0x14000c647  mov     [rax], cx
0x14000c64a  mov     r8d, ecx; Size
0x14000c64d  mov     edx, [rdi+rbx*8+10h]
0x14000c651  lea     rcx, [rax+2]; void *
0x14000c655  add     rdx, rdi; Src
0x14000c658  call    memmove
0x14000c65d  mov     rcx, r14
0x14000c660  call    CreateNoDriveLetterEntry
0x14000c665  xor     edx, edx; Tag
0x14000c667  mov     rcx, r14; P
0x14000c66a  call    cs:__imp_ExFreePoolWithTag
0x14000c671  nop     dword ptr [rax+rax+00h]
0x14000c676  mov     r8b, 1
0x14000c679  lea     rdx, [rsp+68h+ValueName]
0x14000c67e  mov     rcx, rbp
0x14000c681  call    DeleteSymbolicLinkNameFromMemory
0x14000c686  mov     r8, [rsp+68h+ValueName.Buffer]; ValueName
0x14000c68b  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000c692  xor     ecx, ecx; RelativeTo
0x14000c694  mov     ebx, eax
0x14000c696  call    cs:__imp_RtlDeleteRegistryValue
0x14000c69d  nop     dword ptr [rax+rax+00h]
0x14000c6a2  mov     rcx, [rsp+68h+ValueName.Buffer]; P
0x14000c6a7  xor     edx, edx; Tag
0x14000c6a9  call    cs:__imp_ExFreePoolWithTag
0x14000c6b0  nop     dword ptr [rax+rax+00h]
0x14000c6b5  test    ebx, ebx
0x14000c6b7  js      short loc_14000C6C0
0x14000c6b9  inc     esi
0x14000c6bb  jmp     loc_14000C594
0x14000c6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6c7  lea     rax, WPP_GLOBAL_Control
0x14000c6ce  cmp     rcx, rax
0x14000c6d1  jz      loc_14000C57D
0x14000c6d7  mov     eax, [rcx+2Ch]
0x14000c6da  test    al, 1
0x14000c6dc  jz      loc_14000C57D
0x14000c6e2  mov     edx, 0E7h
0x14000c6e7  jmp     loc_14000C571
0x14000c6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6f3  lea     rax, WPP_GLOBAL_Control
0x14000c6fa  cmp     rcx, rax
0x14000c6fd  jz      short loc_14000C714
0x14000c6ff  mov     eax, [rcx+2Ch]
0x14000c702  test    al, 4
0x14000c704  jz      short loc_14000C714
0x14000c706  mov     rcx, [rcx+18h]
0x14000c70a  mov     edx, 0E6h
0x14000c70f  call    WPP_SF_
0x14000c714  mov     eax, 0C000009Ah
0x14000c719  jmp     loc_14000C57F
```
