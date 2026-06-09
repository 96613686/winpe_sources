# MRxSmbQueryFileInformationFromPseudoOpen

- ea: `0x140047dc0`
- end: `0x140047fa0`
- name: `MRxSmbQueryFileInformationFromPseudoOpen`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003a5f0`
- `0x140047fb0`

## callees

- `0x140047dc0`
- `0x140048b30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140047de2`
- `ntoskrnl!ExAllocatePool2` at `0x140047de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047f0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047f0b`
- `rdbss!RxInitializeContext` at `0x140047e06`
- `rdbss!RxInitializeContext` at `0x140047e06`

## pseudocode

```c
__int64 __fastcall MRxSmbQueryFileInformationFromPseudoOpen(__int64 a1, __int64 a2, ULONG a3)
{
  struct _RX_CONTEXT *Pool2; // rax
  struct _RX_CONTEXT *v7; // rbx
  PVOID *p_EaBuffer; // rcx
  __int128 *v9; // rax
  __int64 v10; // rdx
  __int128 v11; // xmm0
  unsigned int FileInformation; // edi
  __int64 result; // rax
  RXVBO v14; // rax
  bool v15; // cl

  Pool2 = (struct _RX_CONTEXT *)ExAllocatePool2(64, 896, 2018667859);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  RxInitializeContext(0, *(PRDBSS_DEVICE_OBJECT *)(a2 + 80), 0, Pool2);
  v7->pFcb = *(PMRX_FCB *)(a2 + 56);
  v7->pFobx = *(PMRX_FOBX *)(a2 + 64);
  v7->CurrentIrp = *(PIRP *)(a2 + 40);
  v7->CurrentIrpSp = *(PIO_STACK_LOCATION *)(a2 + 48);
  LOBYTE(v7->RealDevice) = 0;
  v7->pRelevantSrvOpen = *(PMRX_SRV_OPEN *)(a2 + 72);
  LODWORD(v7->RdbssDbgExtension) = -2143289342;
  switch ( a3 )
  {
    case 4u:
      *((_DWORD *)&v7->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 40;
      v14 = a1 + 472;
LABEL_10:
      v7->LowIoContext.ParamsFor.ReadWrite.ByteOffset = v14;
      break;
    case 5u:
      *((_DWORD *)&v7->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 24;
      v14 = a1 + 512;
      goto LABEL_10;
    case 6u:
      *((_DWORD *)&v7->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = 8;
      v14 = a1 + 536;
      goto LABEL_10;
  }
  v7->LowIoContext.ParamsFor.Locks.Flags = a3;
  p_EaBuffer = &v7->Create.EaBuffer;
  v9 = (__int128 *)(a2 + 512);
  v10 = 2;
  do
  {
    p_EaBuffer += 16;
    v11 = *v9;
    v9 += 8;
    *((_OWORD *)p_EaBuffer - 8) = v11;
    *((_OWORD *)p_EaBuffer - 7) = *(v9 - 7);
    *((_OWORD *)p_EaBuffer - 6) = *(v9 - 6);
    *((_OWORD *)p_EaBuffer - 5) = *(v9 - 5);
    *((_OWORD *)p_EaBuffer - 4) = *(v9 - 4);
    *((_OWORD *)p_EaBuffer - 3) = *(v9 - 3);
    *((_OWORD *)p_EaBuffer - 2) = *(v9 - 2);
    *((_OWORD *)p_EaBuffer - 1) = *(v9 - 1);
    --v10;
  }
  while ( v10 );
  *(_OWORD *)p_EaBuffer = *v9;
  *((_OWORD *)p_EaBuffer + 1) = v9[1];
  *((_OWORD *)p_EaBuffer + 2) = v9[2];
  *((_OWORD *)p_EaBuffer + 3) = v9[3];
  *((_OWORD *)p_EaBuffer + 4) = v9[4];
  p_EaBuffer[10] = (PVOID)*((_QWORD *)v9 + 10);
  FileInformation = MRxSmbQueryFileInformation(v7);
  ExFreePoolWithTag(v7, 0);
  result = FileInformation;
  if ( !FileInformation && a3 == 4 )
  {
    v15 = (*(_DWORD *)(a1 + 504) & 0x10) != 0;
    *(_BYTE *)(a1 + 533) = v15;
    *(_DWORD *)(a1 + 552) = !v15 + 1;
  }
  return result;
}

```

## disassembly

```asm
0x140047dc0  push    rbx
0x140047dc2  push    rbp
0x140047dc3  push    rsi
0x140047dc4  push    rdi
0x140047dc5  sub     rsp, 28h
0x140047dc9  mov     esi, r8d
0x140047dcc  mov     rdi, rdx
0x140047dcf  mov     rbp, rcx
0x140047dd2  mov     edx, 380h
0x140047dd7  mov     ecx, 40h ; '@'
0x140047ddc  mov     r8d, 78526D53h
0x140047de2  call    cs:__imp_ExAllocatePool2
0x140047de9  nop     dword ptr [rax+rax+00h]
0x140047dee  mov     rbx, rax
0x140047df1  test    rax, rax
0x140047df4  jz      loc_140047F6B
0x140047dfa  mov     rdx, [rdi+50h]; RxDeviceObject
0x140047dfe  mov     r9, rax; RxContext
0x140047e01  xor     r8d, r8d; InitialContextFlags
0x140047e04  xor     ecx, ecx; Irp
0x140047e06  call    cs:__imp_RxInitializeContext
0x140047e0d  nop     dword ptr [rax+rax+00h]
0x140047e12  mov     rax, [rdi+38h]
0x140047e16  mov     ecx, esi
0x140047e18  mov     [rbx+38h], rax
0x140047e1c  mov     rax, [rdi+40h]
0x140047e20  mov     [rbx+40h], rax
0x140047e24  mov     rax, [rdi+28h]
0x140047e28  mov     [rbx+28h], rax
0x140047e2c  mov     rax, [rdi+30h]
0x140047e30  mov     [rbx+30h], rax
0x140047e34  mov     byte ptr [rbx+20h], 0
0x140047e38  mov     rax, [rdi+48h]
0x140047e3c  mov     [rbx+48h], rax
0x140047e40  mov     dword ptr [rbx+78h], 80400002h
0x140047e47  sub     ecx, 4
0x140047e4a  jz      loc_140047F27
0x140047e50  sub     ecx, 1
0x140047e53  jz      loc_140047F8D
0x140047e59  cmp     ecx, 1
0x140047e5c  jz      loc_140047F7A
0x140047e62  mov     [rbx+1C0h], esi
0x140047e68  lea     rcx, [rbx+200h]
0x140047e6f  lea     rax, [rdi+200h]
0x140047e76  mov     edx, 2
0x140047e7b  lea     rcx, [rcx+80h]
0x140047e82  movups  xmm0, xmmword ptr [rax]
0x140047e85  lea     rax, [rax+80h]
0x140047e8c  movups  xmmword ptr [rcx-80h], xmm0
0x140047e90  movups  xmm1, xmmword ptr [rax-70h]
0x140047e94  movups  xmmword ptr [rcx-70h], xmm1
0x140047e98  movups  xmm0, xmmword ptr [rax-60h]
0x140047e9c  movups  xmmword ptr [rcx-60h], xmm0
0x140047ea0  movups  xmm1, xmmword ptr [rax-50h]
0x140047ea4  movups  xmmword ptr [rcx-50h], xmm1
0x140047ea8  movups  xmm0, xmmword ptr [rax-40h]
0x140047eac  movups  xmmword ptr [rcx-40h], xmm0
0x140047eb0  movups  xmm1, xmmword ptr [rax-30h]
0x140047eb4  movups  xmmword ptr [rcx-30h], xmm1
0x140047eb8  movups  xmm0, xmmword ptr [rax-20h]
0x140047ebc  movups  xmmword ptr [rcx-20h], xmm0
0x140047ec0  movups  xmm1, xmmword ptr [rax-10h]
0x140047ec4  movups  xmmword ptr [rcx-10h], xmm1
0x140047ec8  sub     rdx, 1
0x140047ecc  jnz     short loc_140047E7B
0x140047ece  movups  xmm0, xmmword ptr [rax]
0x140047ed1  movups  xmmword ptr [rcx], xmm0
0x140047ed4  movups  xmm1, xmmword ptr [rax+10h]
0x140047ed8  movups  xmmword ptr [rcx+10h], xmm1
0x140047edc  movups  xmm0, xmmword ptr [rax+20h]
0x140047ee0  movups  xmmword ptr [rcx+20h], xmm0
0x140047ee4  movups  xmm1, xmmword ptr [rax+30h]
0x140047ee8  movups  xmmword ptr [rcx+30h], xmm1
0x140047eec  movups  xmm0, xmmword ptr [rax+40h]
0x140047ef0  movups  xmmword ptr [rcx+40h], xmm0
0x140047ef4  mov     rax, [rax+50h]
0x140047ef8  mov     [rcx+50h], rax
0x140047efc  mov     rcx, rbx
0x140047eff  call    MRxSmbQueryFileInformation
0x140047f04  xor     edx, edx; Tag
0x140047f06  mov     rcx, rbx; P
0x140047f09  mov     edi, eax
0x140047f0b  call    cs:__imp_ExFreePoolWithTag
0x140047f12  nop     dword ptr [rax+rax+00h]
0x140047f17  mov     eax, edi
0x140047f19  test    edi, edi
0x140047f1b  jz      short loc_140047F44
0x140047f1d  add     rsp, 28h
0x140047f21  pop     rdi
0x140047f22  pop     rsi
0x140047f23  pop     rbp
0x140047f24  pop     rbx
0x140047f25  retn
0x140047f27  mov     dword ptr [rbx+1D8h], 28h ; '('
0x140047f31  lea     rax, [rbp+1D8h]
0x140047f38  mov     [rbx+1C8h], rax
0x140047f3f  jmp     loc_140047E62
0x140047f44  cmp     esi, 4
0x140047f47  jnz     short loc_140047F1D
0x140047f49  mov     ecx, [rbp+1F8h]
0x140047f4f  shr     ecx, 4
0x140047f52  and     cl, 1
0x140047f55  movzx   edx, cl
0x140047f58  mov     [rbp+215h], dl
0x140047f5e  xor     edx, 1
0x140047f61  inc     edx
0x140047f63  mov     [rbp+228h], edx
0x140047f69  jmp     short loc_140047F1D
0x140047f6b  mov     eax, 0C000009Ah
0x140047f70  add     rsp, 28h
0x140047f74  pop     rdi
0x140047f75  pop     rsi
0x140047f76  pop     rbp
0x140047f77  pop     rbx
0x140047f78  retn
0x140047f7a  mov     dword ptr [rbx+1D8h], 8
0x140047f84  lea     rax, [rbp+218h]
0x140047f8b  jmp     short loc_140047F38
0x140047f8d  mov     dword ptr [rbx+1D8h], 18h
0x140047f97  lea     rax, [rbp+200h]
0x140047f9e  jmp     short loc_140047F38
```
