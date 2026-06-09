# RxTdiOpenAddress

- ea: `0x1400578e8`
- end: `0x140057b9f`
- name: `RxTdiOpenAddress`
- size: `695`
- prototype: `__int64 __fastcall(__int64, struct _TRANSPORT_ADDRESS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14008b2a0`

## callees

- `0x140028ed4`
- `0x140038068`
- `0x14003838c`
- `0x1400383d0`
- `0x1400578e8`
- `0x140058240`
- `0x14005845c`
- `0x14008b230`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140057a90`
- `ntoskrnl!ObfDereferenceObject` at `0x140057a90`
- `ntoskrnl!ZwCreateFile` at `0x1400579db`
- `ntoskrnl!ZwCreateFile` at `0x1400579db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057a55`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057a55`
- `ntoskrnl!ZwClose` at `0x140057aae`
- `ntoskrnl!ZwClose` at `0x140057b8e`
- `ntoskrnl!ZwClose` at `0x140057aae`
- `ntoskrnl!ZwClose` at `0x140057b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057af1`

## pseudocode

```c
__int64 __fastcall RxTdiOpenAddress(__int64 a1, struct _TRANSPORT_ADDRESS *a2)
{
  unsigned int v4; // eax
  int v5; // eax
  PVOID v6; // r14
  NTSTATUS v7; // edi
  POOL_TYPE v8; // r8d
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  PVOID P; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  ULONG EaLength; // [rsp+F0h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  EaLength = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v4 = ComputeTransportAddressLength(a2);
  v5 = BuildEaBuffer(16, "TransportAddress", v4, a2, (__int64 *)&P, &EaLength);
  v6 = P;
  v7 = v5;
  if ( v5 < 0
    || (ObjectAttributes.RootDirectory = *(HANDLE *)(a1 + 80),
        ObjectAttributes.Length = 48,
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&RelativeName,
        ObjectAttributes.Attributes = 512,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        v7 = ZwCreateFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 3u, 0, P, EaLength),
        v7 < 0) )
  {
LABEL_11:
    v9 = *(void **)(a1 + 120);
    if ( v9 )
    {
      ObfDereferenceObject(v9);
      *(_QWORD *)(a1 + 120) = 0;
    }
    v10 = *(void **)(a1 + 112);
    if ( v10 != (void *)-1LL )
    {
      ZwClose(v10);
      *(_QWORD *)(a1 + 112) = -1;
    }
    v11 = *(void **)(a1 + 104);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0x74437852u);
      *(_QWORD *)(a1 + 104) = 0;
    }
    goto LABEL_17;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 112), (signed __int64)FileHandle, -1) == -1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        &WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids,
        *(_QWORD *)(a1 + 112));
    }
    v7 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 112), 0, 0, 0, (PVOID *)(a1 + 120), 0);
    if ( v7 < 0 )
      goto LABEL_11;
    v7 = RxTdiSetEventHandlers(a1);
    if ( v7 < 0 )
      goto LABEL_11;
    v7 = DuplicateTransportAddress((PTRANSPORT_ADDRESS *)(a1 + 104), a2, v8);
    if ( v7 < 0 )
      goto LABEL_11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids,
        *(_QWORD *)(a1 + 112),
        FileHandle);
    }
    ZwClose(FileHandle);
  }
LABEL_17:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x64437852u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400578e8  mov     [rsp-8+arg_0], rbx
0x1400578ed  push    rbp
0x1400578ee  push    rsi
0x1400578ef  push    rdi
0x1400578f0  push    r14
0x1400578f2  push    r15
0x1400578f4  lea     rbp, [rsp-37h]
0x1400578f9  sub     rsp, 0B0h
0x140057900  xorps   xmm0, xmm0
0x140057903  xor     eax, eax
0x140057905  mov     rbx, rcx
0x140057908  mov     [rbp+57h+FileHandle], rax
0x14005790c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140057910  mov     rcx, rdx
0x140057913  mov     [rbp+57h+arg_10], eax
0x140057916  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14005791a  mov     r15, rdx
0x14005791d  mov     [rbp+57h+P], rax
0x140057921  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140057925  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140057929  call    ComputeTransportAddressLength
0x14005792e  lea     rcx, [rbp+57h+arg_10]
0x140057932  mov     r9, r15
0x140057935  mov     qword ptr [rsp+0D0h+FileAttributes], rcx
0x14005793a  lea     rdx, aTransportaddre; "TransportAddress"
0x140057941  lea     rcx, [rbp+57h+P]
0x140057945  mov     r8d, eax
0x140057948  mov     [rsp+0D0h+AllocationSize], rcx
0x14005794d  mov     ecx, 10h
0x140057952  call    BuildEaBuffer
0x140057957  mov     r14, [rbp+57h+P]
0x14005795b  mov     edi, eax
0x14005795d  lea     rsi, WPP_GLOBAL_Control
0x140057964  test    eax, eax
0x140057966  js      loc_140057A87
0x14005796c  mov     rax, [rbx+50h]
0x140057970  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140057974  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140057978  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005797c  lea     rax, RelativeName
0x140057983  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005798a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005798e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140057992  mov     eax, [rbp+57h+arg_10]
0x140057995  xorps   xmm0, xmm0
0x140057998  mov     [rsp+0D0h+EaLength], eax; EaLength
0x14005799c  mov     edx, 0C0100000h; DesiredAccess
0x1400579a1  mov     [rsp+0D0h+EaBuffer], r14; EaBuffer
0x1400579a6  mov     [rsp+0D0h+CreateOptions], 0; CreateOptions
0x1400579ae  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x1400579b6  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x1400579be  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x1400579c6  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x1400579cf  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400579d6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400579db  call    cs:__imp_ZwCreateFile
0x1400579e2  nop     dword ptr [rax+rax+00h]
0x1400579e7  mov     edi, eax
0x1400579e9  test    eax, eax
0x1400579eb  js      loc_140057A87
0x1400579f1  mov     rcx, [rbp+57h+FileHandle]
0x1400579f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400579f9  lock cmpxchg [rbx+70h], rcx
0x1400579ff  jnz     loc_140057B48
0x140057a05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057a0c  cmp     rcx, rsi
0x140057a0f  jz      short loc_140057A37
0x140057a11  mov     eax, [rcx+2Ch]
0x140057a14  test    al, 4
0x140057a16  jz      short loc_140057A37
0x140057a18  cmp     byte ptr [rcx+29h], 2
0x140057a1c  jb      short loc_140057A37
0x140057a1e  mov     r9, [rbx+70h]
0x140057a22  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057a29  mov     rcx, [rcx+18h]
0x140057a2d  mov     edx, 0Bh
0x140057a32  call    WPP_SF_q
0x140057a37  mov     rcx, [rbx+70h]; Handle
0x140057a3b  lea     rax, [rbx+78h]
0x140057a3f  mov     qword ptr [rsp+0D0h+FileAttributes], 0; HandleInformation
0x140057a48  xor     r9d, r9d; AccessMode
0x140057a4b  xor     r8d, r8d; ObjectType
0x140057a4e  mov     [rsp+0D0h+AllocationSize], rax; Object
0x140057a53  xor     edx, edx; DesiredAccess
0x140057a55  call    cs:__imp_ObReferenceObjectByHandle
0x140057a5c  nop     dword ptr [rax+rax+00h]
0x140057a61  mov     edi, eax
0x140057a63  test    eax, eax
0x140057a65  js      short loc_140057A87
0x140057a67  mov     rcx, rbx
0x140057a6a  call    RxTdiSetEventHandlers
0x140057a6f  mov     edi, eax
0x140057a71  test    eax, eax
0x140057a73  js      short loc_140057A87
0x140057a75  lea     rcx, [rbx+68h]; Copy
0x140057a79  mov     rdx, r15; Original
0x140057a7c  call    DuplicateTransportAddress
0x140057a81  mov     edi, eax
0x140057a83  test    eax, eax
0x140057a85  jns     short loc_140057AE4
0x140057a87  mov     rcx, [rbx+78h]; Object
0x140057a8b  test    rcx, rcx
0x140057a8e  jz      short loc_140057AA4
0x140057a90  call    cs:__imp_ObfDereferenceObject
0x140057a97  nop     dword ptr [rax+rax+00h]
0x140057a9c  mov     qword ptr [rbx+78h], 0
0x140057aa4  mov     rcx, [rbx+70h]; Handle
0x140057aa8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140057aac  jz      short loc_140057AC2
0x140057aae  call    cs:__imp_ZwClose
0x140057ab5  nop     dword ptr [rax+rax+00h]
0x140057aba  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x140057ac2  mov     rcx, [rbx+68h]; P
0x140057ac6  test    rcx, rcx
0x140057ac9  jz      short loc_140057AE4
0x140057acb  mov     edx, 74437852h; Tag
0x140057ad0  call    cs:__imp_ExFreePoolWithTag
0x140057ad7  nop     dword ptr [rax+rax+00h]
0x140057adc  mov     qword ptr [rbx+68h], 0
0x140057ae4  test    r14, r14
0x140057ae7  jz      short loc_140057AFD
0x140057ae9  mov     edx, 64437852h; Tag
0x140057aee  mov     rcx, r14; P
0x140057af1  call    cs:__imp_ExFreePoolWithTag
0x140057af8  nop     dword ptr [rax+rax+00h]
0x140057afd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057b04  cmp     rcx, rsi
0x140057b07  jz      short loc_140057B2E
0x140057b09  mov     eax, [rcx+2Ch]
0x140057b0c  test    al, 4
0x140057b0e  jz      short loc_140057B2E
0x140057b10  cmp     byte ptr [rcx+29h], 1
0x140057b14  jb      short loc_140057B2E
0x140057b16  mov     rcx, [rcx+18h]
0x140057b1a  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057b21  mov     edx, 0Dh
0x140057b26  mov     r9d, edi
0x140057b29  call    WPP_SF_d
0x140057b2e  mov     rbx, [rsp+0D0h+arg_0]
0x140057b36  mov     eax, edi
0x140057b38  add     rsp, 0B0h
0x140057b3f  pop     r15
0x140057b41  pop     r14
0x140057b43  pop     rdi
0x140057b44  pop     rsi
0x140057b45  pop     rbp
0x140057b46  retn
0x140057b48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140057b4f  lea     rsi, WPP_GLOBAL_Control
0x140057b56  cmp     rcx, rsi
0x140057b59  jz      short loc_140057B8A
0x140057b5b  mov     eax, [rcx+2Ch]
0x140057b5e  test    al, 4
0x140057b60  jz      short loc_140057B8A
0x140057b62  cmp     byte ptr [rcx+29h], 2
0x140057b66  jb      short loc_140057B8A
0x140057b68  mov     rax, [rbp+57h+FileHandle]
0x140057b6c  lea     r8, WPP_8c435767c9f635b7c8f3875fbe9f0814_Traceguids
0x140057b73  mov     r9, [rbx+70h]
0x140057b77  mov     edx, 0Ch
0x140057b7c  mov     rcx, [rcx+18h]
0x140057b80  mov     [rsp+0D0h+AllocationSize], rax
0x140057b85  call    WPP_SF_qq
0x140057b8a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140057b8e  call    cs:__imp_ZwClose
0x140057b95  nop     dword ptr [rax+rax+00h]
0x140057b9a  jmp     loc_140057AE4
```
