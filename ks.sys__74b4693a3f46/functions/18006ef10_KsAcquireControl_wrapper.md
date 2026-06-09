# KsAcquireControl_wrapper

- ea: `0x18006ef10`
- end: `0x18006f22e`
- name: `KsAcquireControl_wrapper`
- size: `798`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180019c60`
- `0x180057c70`
- `0x18005a5b0`
- `0x18006ef10`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006ef45`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006ef45`

## string_xrefs

- `0x18006eff2`: `The driver attempts to acquire the filter mutex while holding a processing mutex.`
- `0x18006f0bc`: `The driver attempts to acquire the filter mutex while holding it. This operation will cause a deadlock.`

## pseudocode

```c
__int64 __fastcall KsAcquireControl_wrapper(PVOID Object)
{
  __int64 v2; // rdi
  __int64 v3; // r9
  const _KSDEVICE_DESCRIPTOR *Descriptor; // r14
  __int64 v5; // rdx
  PVOID v6; // r8
  __int64 v7; // r9
  PVOID v8; // r8
  PVOID v9; // r8
  __int64 result; // rax
  __int64 v11; // [rsp+20h] [rbp-20h]
  __int64 i; // [rsp+68h] [rbp+28h] BYREF

  i = 0;
  v2 = 0;
  Descriptor = KsGetDevice(Object)[1].Descriptor;
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsAcquireControl should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v2 = (*(__int64 (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 8))(Descriptor);
    (*(void (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 72))(Descriptor);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v2 )
  {
    for ( i = *(_QWORD *)(v2 + 160);
          i;
          (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(KsVerifierUtilTable + 56))(
            *(_QWORD *)(v2 + 160),
            v5,
            136,
            &i) )
    {
      v5 = i;
      if ( *(struct _KTHREAD **)(i + 112) == KeGetCurrentThread() && *(_BYTE *)(i + 128) )
      {
        (*(void (__fastcall **)(const char *, __int64, __int64, __int64, __int64, int))(KsVerifierUtilTable + 88))(
          "The driver attempts to acquire the filter mutex while holding a processing mutex.",
          528395,
          v2,
          i,
          v2 + 160,
          136);
        v5 = i;
      }
    }
    if ( *((_DWORD *)Object - 20) == 3 )
      v6 = (PVOID)((*((_QWORD *)Object - 11) + 128LL) & -(__int64)(*((_QWORD *)Object - 11) != 0));
    else
      v6 = Object;
    LOBYTE(v3) = 1;
    LOBYTE(v11) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PVOID, __int64, _DWORD, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v2 + 152),
      136,
      v6,
      v3,
      v11,
      &i);
    if ( i && *(struct _KTHREAD **)(i + 112) == KeGetCurrentThread() && *(_BYTE *)(i + 128) )
    {
      v11 = v2 + 152;
      (*(void (__fastcall **)(const char *, __int64, __int64))(KsVerifierUtilTable + 88))(
        "The driver attempts to acquire the filter mutex while holding it. This operation will cause a deadlock.",
        528394,
        v2);
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 80))(Descriptor);
  KsAcquireControl(Object);
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 72))(Descriptor);
  if ( (KsXdvExtLevel & 8) != 0 && v2 )
  {
    if ( *((_DWORD *)Object - 20) == 3 )
      v8 = (PVOID)((*((_QWORD *)Object - 11) + 128LL) & -(__int64)(*((_QWORD *)Object - 11) != 0));
    else
      v8 = Object;
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(__int64, __int64, PVOID, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v2 + 152,
      136,
      v8,
      v7,
      &i);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v2 )
  {
    v9 = *((_DWORD *)Object - 20) == 3
       ? (PVOID)((*((_QWORD *)Object - 11) + 128LL) & -(__int64)(*((_QWORD *)Object - 11) != 0))
       : Object;
    LOBYTE(v7) = 1;
    LOBYTE(v11) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PVOID, __int64, __int64, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v2 + 152),
      136,
      v9,
      v7,
      v11,
      &i);
    if ( i )
    {
      *(_QWORD *)(i + 120) = Object;
      *(_BYTE *)(i + 128) = 2;
      *(_QWORD *)(i + 112) = KeGetCurrentThread();
    }
  }
  result = (unsigned int)KsXdvExtLevel;
  if ( (KsXdvExtLevel & 0x18) != 0 )
    return (*(__int64 (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 80))(Descriptor);
  return result;
}

```

## disassembly

```asm
0x18006ef10  mov     [rsp-18h+arg_0], rbx
0x18006ef15  mov     [rsp-18h+arg_10], rsi
0x18006ef1a  push    rbp
0x18006ef1b  push    rdi
0x18006ef1c  push    r14
0x18006ef1e  mov     rbp, rsp
0x18006ef21  sub     rsp, 40h
0x18006ef25  mov     rbx, rcx
0x18006ef28  mov     [rbp+arg_8], 0
0x18006ef30  xor     edi, edi
0x18006ef32  call    KsGetDevice
0x18006ef37  mov     r14, [rax+40h]
0x18006ef3b  mov     eax, cs:KsXdvExtLevel
0x18006ef41  test    al, 8
0x18006ef43  jz      short loc_18006EF71
0x18006ef45  call    cs:__imp_KeGetCurrentIrql
0x18006ef4c  nop     dword ptr [rax+rax+00h]
0x18006ef51  test    al, al
0x18006ef53  jz      short loc_18006EF71
0x18006ef55  mov     rax, cs:KsVerifierUtilTable
0x18006ef5c  lea     rcx, aKsacquirecontr; "KsAcquireControl should only be called "...
0x18006ef63  mov     edx, 81009h
0x18006ef68  mov     rax, [rax+60h]
0x18006ef6c  call    _guard_dispatch_icall
0x18006ef71  mov     eax, cs:KsXdvExtLevel
0x18006ef77  test    al, 18h
0x18006ef79  jz      short loc_18006EFA4
0x18006ef7b  mov     rax, cs:KsVerifierUtilTable
0x18006ef82  mov     rcx, r14
0x18006ef85  mov     rax, [rax+8]
0x18006ef89  call    _guard_dispatch_icall
0x18006ef8e  mov     rcx, cs:KsVerifierUtilTable
0x18006ef95  mov     rdi, rax
0x18006ef98  mov     rax, [rcx+48h]
0x18006ef9c  mov     rcx, r14
0x18006ef9f  call    _guard_dispatch_icall
0x18006efa4  mov     ecx, cs:KsXdvExtLevel
0x18006efaa  test    cl, 8
0x18006efad  jz      loc_18006F0E1
0x18006efb3  test    rdi, rdi
0x18006efb6  jz      loc_18006F0E1
0x18006efbc  lea     rsi, [rdi+0A0h]
0x18006efc3  mov     rax, [rsi]
0x18006efc6  mov     [rbp+arg_8], rax
0x18006efca  test    rax, rax
0x18006efcd  jz      short loc_18006F042
0x18006efcf  mov     rax, gs:188h
0x18006efd8  mov     rdx, [rbp+arg_8]
0x18006efdc  cmp     [rdx+70h], rax
0x18006efe0  jnz     short loc_18006F01E
0x18006efe2  cmp     byte ptr [rdx+80h], 0
0x18006efe9  jz      short loc_18006F01E
0x18006efeb  mov     rax, cs:KsVerifierUtilTable
0x18006eff2  lea     rcx, aTheDriverAttem_0; "The driver attempts to acquire the filt"...
0x18006eff9  mov     r9, rdx
0x18006effc  mov     dword ptr [rsp+40h+var_18], 88h
0x18006f004  mov     r8, rdi
0x18006f007  mov     [rsp+40h+var_20], rsi
0x18006f00c  mov     edx, 8100Bh
0x18006f011  mov     rax, [rax+58h]
0x18006f015  call    _guard_dispatch_icall
0x18006f01a  mov     rdx, [rbp+arg_8]
0x18006f01e  mov     rax, cs:KsVerifierUtilTable
0x18006f025  lea     r9, [rbp+arg_8]
0x18006f029  mov     rcx, [rsi]
0x18006f02c  mov     r8d, 88h
0x18006f032  mov     rax, [rax+38h]
0x18006f036  call    _guard_dispatch_icall
0x18006f03b  cmp     [rbp+arg_8], 0
0x18006f040  jnz     short loc_18006EFCF
0x18006f042  cmp     dword ptr [rbx-50h], 3
0x18006f046  jnz     short loc_18006F05E
0x18006f048  mov     rax, [rbx-58h]
0x18006f04c  lea     rcx, [rax+80h]
0x18006f053  neg     rax
0x18006f056  sbb     r8, r8
0x18006f059  and     r8, rcx
0x18006f05c  jmp     short loc_18006F061
0x18006f05e  mov     r8, rbx
0x18006f061  mov     rax, cs:KsVerifierUtilTable
0x18006f068  lea     rcx, [rbp+arg_8]
0x18006f06c  mov     [rsp+40h+var_18], rcx
0x18006f071  lea     rsi, [rdi+98h]
0x18006f078  mov     rcx, [rsi]
0x18006f07b  mov     r9b, 1
0x18006f07e  mov     edx, 88h
0x18006f083  mov     byte ptr [rsp+40h+var_20], 1
0x18006f088  mov     rax, [rax+20h]
0x18006f08c  call    _guard_dispatch_icall
0x18006f091  cmp     [rbp+arg_8], 0
0x18006f096  jz      short loc_18006F0E1
0x18006f098  mov     rax, gs:188h
0x18006f0a1  mov     r9, [rbp+arg_8]
0x18006f0a5  cmp     [r9+70h], rax
0x18006f0a9  jnz     short loc_18006F0E1
0x18006f0ab  cmp     byte ptr [r9+80h], 0
0x18006f0b3  jz      short loc_18006F0E1
0x18006f0b5  mov     rax, cs:KsVerifierUtilTable
0x18006f0bc  lea     rcx, aTheDriverAttem_3; "The driver attempts to acquire the filt"...
0x18006f0c3  mov     dword ptr [rsp+40h+var_18], 88h
0x18006f0cb  mov     r8, rdi
0x18006f0ce  mov     edx, 8100Ah
0x18006f0d3  mov     [rsp+40h+var_20], rsi
0x18006f0d8  mov     rax, [rax+58h]
0x18006f0dc  call    _guard_dispatch_icall
0x18006f0e1  mov     eax, cs:KsXdvExtLevel
0x18006f0e7  test    al, 18h
0x18006f0e9  jz      short loc_18006F0FE
0x18006f0eb  mov     rax, cs:KsVerifierUtilTable
0x18006f0f2  mov     rcx, r14
0x18006f0f5  mov     rax, [rax+50h]
0x18006f0f9  call    _guard_dispatch_icall
0x18006f0fe  mov     rcx, rbx; Object
0x18006f101  call    KsAcquireControl
0x18006f106  mov     eax, cs:KsXdvExtLevel
0x18006f10c  test    al, 18h
0x18006f10e  jz      short loc_18006F123
0x18006f110  mov     rax, cs:KsVerifierUtilTable
0x18006f117  mov     rcx, r14
0x18006f11a  mov     rax, [rax+48h]
0x18006f11e  call    _guard_dispatch_icall
0x18006f123  mov     eax, cs:KsXdvExtLevel
0x18006f129  test    al, 8
0x18006f12b  jz      short loc_18006F179
0x18006f12d  test    rdi, rdi
0x18006f130  jz      short loc_18006F179
0x18006f132  cmp     dword ptr [rbx-50h], 3
0x18006f136  jnz     short loc_18006F14E
0x18006f138  mov     rax, [rbx-58h]
0x18006f13c  lea     rcx, [rax+80h]
0x18006f143  neg     rax
0x18006f146  sbb     r8, r8
0x18006f149  and     r8, rcx
0x18006f14c  jmp     short loc_18006F151
0x18006f14e  mov     r8, rbx
0x18006f151  mov     rax, cs:KsVerifierUtilTable
0x18006f158  lea     rdx, [rbp+arg_8]
0x18006f15c  mov     [rsp+40h+var_20], rdx
0x18006f161  lea     rcx, [rdi+98h]
0x18006f168  mov     r9b, 1
0x18006f16b  mov     edx, 88h
0x18006f170  mov     rax, [rax+28h]
0x18006f174  call    _guard_dispatch_icall
0x18006f179  mov     eax, cs:KsXdvExtLevel
0x18006f17f  test    al, 8
0x18006f181  jz      short loc_18006F1FD
0x18006f183  test    rdi, rdi
0x18006f186  jz      short loc_18006F1FD
0x18006f188  cmp     dword ptr [rbx-50h], 3
0x18006f18c  jnz     short loc_18006F1A4
0x18006f18e  mov     rax, [rbx-58h]
0x18006f192  lea     rcx, [rax+80h]
0x18006f199  neg     rax
0x18006f19c  sbb     r8, r8
0x18006f19f  and     r8, rcx
0x18006f1a2  jmp     short loc_18006F1A7
0x18006f1a4  mov     r8, rbx
0x18006f1a7  mov     rax, cs:KsVerifierUtilTable
0x18006f1ae  lea     rcx, [rbp+arg_8]
0x18006f1b2  mov     [rsp+40h+var_18], rcx
0x18006f1b7  mov     r9b, 1
0x18006f1ba  mov     rcx, [rdi+98h]
0x18006f1c1  mov     edx, 88h
0x18006f1c6  mov     byte ptr [rsp+40h+var_20], 1
0x18006f1cb  mov     rax, [rax+20h]
0x18006f1cf  call    _guard_dispatch_icall
0x18006f1d4  mov     rax, [rbp+arg_8]
0x18006f1d8  test    rax, rax
0x18006f1db  jz      short loc_18006F1FD
0x18006f1dd  mov     [rax+78h], rbx
0x18006f1e1  mov     rax, [rbp+arg_8]
0x18006f1e5  mov     byte ptr [rax+80h], 2
0x18006f1ec  mov     rdx, gs:188h
0x18006f1f5  mov     rax, [rbp+arg_8]
0x18006f1f9  mov     [rax+70h], rdx
0x18006f1fd  mov     eax, cs:KsXdvExtLevel
0x18006f203  test    al, 18h
0x18006f205  jz      short loc_18006F21A
0x18006f207  mov     rax, cs:KsVerifierUtilTable
0x18006f20e  mov     rcx, r14
0x18006f211  mov     rax, [rax+50h]
0x18006f215  call    _guard_dispatch_icall
0x18006f21a  mov     rbx, [rsp+40h+arg_0]
0x18006f21f  mov     rsi, [rsp+40h+arg_10]
0x18006f224  add     rsp, 40h
0x18006f228  pop     r14
0x18006f22a  pop     rdi
0x18006f22b  pop     rbp
0x18006f22c  retn
```
