# DifNtCreateResourceManagerWrapper

- ea: `0x140659980`
- end: `0x140659b29`
- name: `DifNtCreateResourceManagerWrapper`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x140659980`
- `0x1406eb0e0`
- `0x1406f7380`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateResourceManager` at `0x140659a9a`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateResourceManager` at `0x140659a9a`

## pseudocode

```c
__int64 __fastcall DifNtCreateResourceManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        GUID *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes,
        ULONG CreateOptions,
        UNICODE_STRING *Description)
{
  __int64 APIThunkContextById; // rax
  __int64 v11; // r14
  int v12; // ecx
  __int64 ReturnAddressForWrappers; // rax
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  BOOLEAN v16; // di
  _QWORD *j; // rbx
  _QWORD v19[2]; // [rsp+40h] [rbp-51h] BYREF
  ULONG v20; // [rsp+50h] [rbp-41h]
  OBJECT_ATTRIBUTES *v21; // [rsp+58h] [rbp-39h]
  GUID *v22; // [rsp+60h] [rbp-31h]
  void *v23; // [rsp+68h] [rbp-29h]
  ACCESS_MASK v24; // [rsp+70h] [rbp-21h]
  HANDLE *v25; // [rsp+78h] [rbp-19h]
  unsigned int ResourceManager; // [rsp+80h] [rbp-11h]
  __int64 retaddr; // [rsp+D8h] [rbp+47h]

  memset_0(v19, 0, 0x48u);
  APIThunkContextById = DifGetAPIThunkContextById(552);
  v11 = APIThunkContextById;
  if ( !APIThunkContextById )
    goto LABEL_17;
  v12 = *(_DWORD *)(APIThunkContextById + 12);
  if ( (v12 & 0x18) != 0 )
  {
    ReturnAddressForWrappers = retaddr;
  }
  else
  {
    if ( (v12 & 4) == 0 )
      goto LABEL_7;
    ReturnAddressForWrappers = DifGetReturnAddressForWrappers();
  }
  v19[0] = ReturnAddressForWrappers;
LABEL_7:
  v25 = a1;
  v21 = ObjectAttributes;
  v20 = CreateOptions;
  v19[1] = Description;
  v24 = a2;
  v23 = a3;
  v22 = a4;
  if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
    || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
  {
    for ( i = *(_QWORD **)(v11 + 32); i != (_QWORD *)(v11 + 32); i = (_QWORD *)*i )
    {
      if ( i != (_QWORD *)16 )
        guard_dispatch_icall_no_overrides(v19);
    }
    if ( v14 )
      ExReleaseRundownProtection_0(&DifRebootlessRundown);
  }
LABEL_17:
  ResourceManager = NtCreateResourceManager(a1, a2, a3, a4, ObjectAttributes, CreateOptions, Description);
  if ( v11 )
  {
    if ( !VfDifRunningWithoutReboot && (v16 = 0, (VfOptionFlags & 0x800) == 0)
      || (v16 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v11 + 48); j != (_QWORD *)(v11 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(v19);
      }
      if ( v16 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return ResourceManager;
}

```

## disassembly

```asm
0x140659980  mov     [rsp-8+ResourceManagerHandle], rcx
0x140659985  push    rbp
0x140659986  push    rbx
0x140659987  push    rsi
0x140659988  push    rdi
0x140659989  push    r12
0x14065998b  push    r13
0x14065998d  push    r14
0x14065998f  push    r15
0x140659991  lea     rbp, [rsp-7]
0x140659996  sub     rsp, 98h
0x14065999d  mov     r13d, edx
0x1406599a0  lea     rcx, [rbp+3Fh+var_90]; void *
0x1406599a4  xor     edx, edx; Val
0x1406599a6  mov     r12, r8
0x1406599a9  mov     r15, r9
0x1406599ac  lea     r8d, [rdx+48h]; Size
0x1406599b0  call    memset_0
0x1406599b5  mov     ecx, 228h
0x1406599ba  call    DifGetAPIThunkContextById
0x1406599bf  mov     r14, rax
0x1406599c2  test    rax, rax
0x1406599c5  jz      loc_140659A74
0x1406599cb  mov     ecx, [rax+0Ch]
0x1406599ce  test    cl, 18h
0x1406599d1  jz      short loc_1406599D9
0x1406599d3  mov     rax, [rbp+47h]
0x1406599d7  jmp     short loc_1406599E3
0x1406599d9  test    cl, 4
0x1406599dc  jz      short loc_1406599E7
0x1406599de  call    DifGetReturnAddressForWrappers
0x1406599e3  mov     [rbp+3Fh+var_90], rax
0x1406599e7  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406599ee  mov     rax, [rbp+3Fh+ResourceManagerHandle]
0x1406599f2  mov     [rbp+3Fh+var_58], rax
0x1406599f6  mov     rax, [rbp+3Fh+arg_20]
0x1406599fa  mov     [rbp+3Fh+var_78], rax
0x1406599fe  mov     eax, [rbp+3Fh+arg_28]
0x140659a01  mov     [rbp+3Fh+var_80], eax
0x140659a04  mov     rax, [rbp+3Fh+arg_30]
0x140659a08  mov     [rbp+3Fh+var_88], rax
0x140659a0c  mov     [rbp+3Fh+var_60], r13d
0x140659a10  mov     [rbp+3Fh+var_68], r12
0x140659a14  mov     [rbp+3Fh+var_70], r15
0x140659a18  jnz     short loc_140659A29
0x140659a1a  xor     sil, sil
0x140659a1d  test    cs:VfOptionFlags, 800h
0x140659a27  jz      short loc_140659A3C
0x140659a29  lea     rcx, DifRebootlessRundown; RunRef
0x140659a30  call    ExAcquireRundownProtection_0
0x140659a35  mov     sil, al
0x140659a38  test    al, al
0x140659a3a  jz      short loc_140659A74
0x140659a3c  lea     rdi, [r14+20h]
0x140659a40  mov     rbx, [rdi]
0x140659a43  jmp     short loc_140659A5E
0x140659a45  lea     rax, [rbx-10h]
0x140659a49  test    rax, rax
0x140659a4c  jz      short loc_140659A5B
0x140659a4e  mov     rax, [rax+8]
0x140659a52  lea     rcx, [rbp+3Fh+var_90]
0x140659a56  call    _guard_dispatch_icall_no_overrides
0x140659a5b  mov     rbx, [rbx]
0x140659a5e  cmp     rbx, rdi
0x140659a61  jnz     short loc_140659A45
0x140659a63  test    sil, sil
0x140659a66  jz      short loc_140659A74
0x140659a68  lea     rcx, DifRebootlessRundown; RunRef
0x140659a6f  call    ExReleaseRundownProtection_0
0x140659a74  mov     rax, [rbp+3Fh+arg_30]
0x140659a78  mov     r9, r15; RmGuid
0x140659a7b  mov     rcx, [rbp+3Fh+ResourceManagerHandle]; ResourceManagerHandle
0x140659a7f  mov     r8, r12; TmHandle
0x140659a82  mov     [rsp+0D0h+Description], rax; Description
0x140659a87  mov     edx, r13d; DesiredAccess
0x140659a8a  mov     eax, [rbp+3Fh+arg_28]
0x140659a8d  mov     [rsp+0D0h+CreateOptions], eax; CreateOptions
0x140659a91  mov     rax, [rbp+3Fh+arg_20]
0x140659a95  mov     [rsp+0D0h+ObjectAttributes], rax; ObjectAttributes
0x140659a9a  call    cs:__imp_NtCreateResourceManager
0x140659aa1  nop     dword ptr [rax+rax+00h]
0x140659aa6  mov     [rbp+3Fh+var_50], eax
0x140659aa9  test    r14, r14
0x140659aac  jz      short loc_140659B11
0x140659aae  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659ab5  jnz     short loc_140659AC6
0x140659ab7  xor     dil, dil
0x140659aba  test    cs:VfOptionFlags, 800h
0x140659ac4  jz      short loc_140659AD9
0x140659ac6  lea     rcx, DifRebootlessRundown; RunRef
0x140659acd  call    ExAcquireRundownProtection_0
0x140659ad2  mov     dil, al
0x140659ad5  test    al, al
0x140659ad7  jz      short loc_140659B11
0x140659ad9  lea     rsi, [r14+30h]
0x140659add  mov     rbx, [rsi]
0x140659ae0  jmp     short loc_140659AFB
0x140659ae2  lea     rax, [rbx-10h]
0x140659ae6  test    rax, rax
0x140659ae9  jz      short loc_140659AF8
0x140659aeb  mov     rax, [rax+8]
0x140659aef  lea     rcx, [rbp+3Fh+var_90]
0x140659af3  call    _guard_dispatch_icall_no_overrides
0x140659af8  mov     rbx, [rbx]
0x140659afb  cmp     rbx, rsi
0x140659afe  jnz     short loc_140659AE2
0x140659b00  test    dil, dil
0x140659b03  jz      short loc_140659B11
0x140659b05  lea     rcx, DifRebootlessRundown; RunRef
0x140659b0c  call    ExReleaseRundownProtection_0
0x140659b11  mov     eax, [rbp+3Fh+var_50]
0x140659b14  add     rsp, 98h
0x140659b1b  pop     r15
0x140659b1d  pop     r14
0x140659b1f  pop     r13
0x140659b21  pop     r12
0x140659b23  pop     rdi
0x140659b24  pop     rsi
0x140659b25  pop     rbx
0x140659b26  pop     rbp
0x140659b27  retn
```
