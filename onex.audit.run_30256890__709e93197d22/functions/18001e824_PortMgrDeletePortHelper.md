# PortMgrDeletePortHelper

- ea: `0x18001e824`
- end: `0x18001e928`
- name: `PortMgrDeletePortHelper`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180016e80`
- `0x180023770`

## callees

- `0x180005440`
- `0x18000f1d0`
- `0x180010ae0`
- `0x18001e824`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001e8ae`
- `MobileNetworking!ReleaseWriteLock` at `0x18001e8ae`
- `MobileNetworking!AcquireWriteLock` at `0x18001e889`
- `MobileNetworking!AcquireWriteLock` at `0x18001e889`

## string_xrefs

- `0x18001e879`: `PortMgrDeletePortHelper`
- `0x18001e896`: `PortMgrDeletePortHelper`

## pseudocode

```c
__int64 __fastcall PortMgrDeletePortHelper(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
  _InterlockedDecrement((volatile signed __int32 *)&qword_18003DD8C);
  AcquireWriteLock(a1, a1 + 2896, "PortMgrDeletePortHelper", 454);
  *(_DWORD *)(a1 + 24) &= 0x3FFFFFFFu;
  *(_DWORD *)(a1 + 24) |= 0x80000000;
  ReleaseWriteLock(a1, a1 + 2896, "PortMgrDeletePortHelper", 463);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      47,
      WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
      *(unsigned int *)(a1 + 20));
  result = PortMgrDereferencePort(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x18001e824  mov     [rsp+arg_0], rbx
0x18001e829  mov     [rsp+arg_8], rdi
0x18001e82e  push    r14
0x18001e830  sub     rsp, 20h
0x18001e834  mov     rdi, rcx
0x18001e837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e83e  lea     r14, WPP_GLOBAL_Control
0x18001e845  cmp     rcx, r14
0x18001e848  jz      short loc_18001E868
0x18001e84a  test    dword ptr [rcx+44h], 800h
0x18001e851  jz      short loc_18001E868
0x18001e853  mov     rcx, [rcx+38h]
0x18001e857  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001e85e  mov     edx, 2Eh ; '.'
0x18001e863  call    WPP_SF_
0x18001e868  lock dec dword ptr cs:qword_18003DD8C
0x18001e86f  lea     rbx, [rdi+0B50h]
0x18001e876  mov     rdx, rbx
0x18001e879  lea     r8, aPortmgrdeletep; "PortMgrDeletePortHelper"
0x18001e880  mov     r9d, 1C6h
0x18001e886  mov     rcx, rdi
0x18001e889  call    cs:__imp_AcquireWriteLock
0x18001e88f  and     dword ptr [rdi+18h], 3FFFFFFFh
0x18001e896  lea     r8, aPortmgrdeletep; "PortMgrDeletePortHelper"
0x18001e89d  bts     dword ptr [rdi+18h], 1Fh
0x18001e8a2  mov     r9d, 1CFh
0x18001e8a8  mov     rdx, rbx
0x18001e8ab  mov     rcx, rdi
0x18001e8ae  call    cs:__imp_ReleaseWriteLock
0x18001e8b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8bb  cmp     rcx, r14
0x18001e8be  jz      short loc_18001E8E2
0x18001e8c0  test    dword ptr [rcx+44h], 800h
0x18001e8c7  jz      short loc_18001E8E2
0x18001e8c9  mov     r9d, [rdi+14h]
0x18001e8cd  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001e8d4  mov     rcx, [rcx+38h]
0x18001e8d8  mov     edx, 2Fh ; '/'
0x18001e8dd  call    WPP_SF_d
0x18001e8e2  mov     rcx, rdi
0x18001e8e5  call    PortMgrDereferencePort
0x18001e8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8f1  cmp     rcx, r14
0x18001e8f4  jz      short loc_18001E917
0x18001e8f6  test    dword ptr [rcx+44h], 800h
0x18001e8fd  jz      short loc_18001E917
0x18001e8ff  mov     rcx, [rcx+38h]
0x18001e903  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001e90a  mov     edx, 30h ; '0'
0x18001e90f  xor     r9d, r9d
0x18001e912  call    WPP_SF_D
0x18001e917  mov     rbx, [rsp+28h+arg_0]
0x18001e91c  mov     rdi, [rsp+28h+arg_8]
0x18001e921  add     rsp, 20h
0x18001e925  pop     r14
0x18001e927  retn
```
