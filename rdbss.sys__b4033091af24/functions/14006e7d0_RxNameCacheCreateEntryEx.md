# RxNameCacheCreateEntryEx

- ea: `0x14006e7d0`
- end: `0x14006ecf2`
- name: `RxNameCacheCreateEntryEx`
- size: `1314`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140014e40`
- `0x140017280`
- `0x140025d00`
- `0x140025d80`
- `0x14006e7d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006e8b0`
- `ntoskrnl!ExAllocatePool2` at `0x14006ea6a`
- `ntoskrnl!ExAllocatePool2` at `0x14006e8b0`
- `ntoskrnl!ExAllocatePool2` at `0x14006ea6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ea3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ea3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e823`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006eaba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ebcf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006e823`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006eaba`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ebcf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e883`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e93f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006eaf5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006eb76`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ec00`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ece1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e883`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006e93f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006eaf5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006eb76`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ec00`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ece1`
- `ntoskrnl!RtlHashUnicodeString` at `0x14006e9a5`
- `ntoskrnl!RtlHashUnicodeString` at `0x14006e9a5`

## pseudocode

```c
_QWORD *__fastcall RxNameCacheCreateEntryEx(__int64 a1, const UNICODE_STRING *a2, __int64 *a3, char a4)
{
  char v4; // r12
  _QWORD *v8; // rax
  __int64 *v9; // rdi
  __int64 v10; // rcx
  _QWORD *v11; // rbx
  unsigned int v12; // r15d
  __int64 Pool2; // rax
  __int64 v14; // rax
  __int64 (__fastcall *v15)(_QWORD, _QWORD *); // rax
  void *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  PDEVICE_OBJECT v21; // rcx
  _QWORD *v22; // rax
  _QWORD *v23; // r15
  _QWORD *v24; // rcx
  __int64 v25; // r12
  __int64 v26; // rax
  _QWORD *v27; // rcx
  void (__fastcall *v28)(_QWORD, _QWORD *); // rax
  __int64 v29; // rcx
  __int64 v30; // rdx

  v4 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids, a2);
  }
  ExAcquirePushLockExclusiveEx(a1 + 48, 0);
  v8 = *(_QWORD **)(a1 + 72);
  v9 = (__int64 *)(a1 + 72);
  if ( v8 == (_QWORD *)(a1 + 72) )
    goto LABEL_7;
  if ( (__int64 *)v8[1] != v9 )
    goto LABEL_36;
  v10 = *v8;
  if ( *(_QWORD **)(*v8 + 8LL) != v8 )
    goto LABEL_36;
  *v9 = v10;
  v11 = v8 - 8;
  *(_QWORD *)(v10 + 8) = v9;
  v8[1] = v8;
  *v8 = v8;
  if ( v8 == (_QWORD *)64 )
  {
LABEL_7:
    if ( *(_DWORD *)(a1 + 88) >= (unsigned int)(8 * *(_DWORD *)(a1 + 92)) )
    {
      v22 = (_QWORD *)(a1 + 56);
      if ( (_QWORD *)*v22 == v22 )
      {
        ExReleasePushLockExclusiveEx(a1 + 48, 0);
        return 0;
      }
      v23 = *(_QWORD **)(a1 + 64);
      if ( (_QWORD *)*v23 != v22 )
        goto LABEL_36;
      v24 = (_QWORD *)v23[1];
      if ( (_QWORD *)*v24 != v23 )
        goto LABEL_36;
      *(_QWORD *)(a1 + 64) = v24;
      v11 = v23 - 8;
      v25 = (__int64)(v23 + 4);
      *v24 = v22;
      v26 = *(_QWORD *)v25;
      if ( *(_QWORD *)(*(_QWORD *)v25 + 8LL) != v25 )
        goto LABEL_36;
      v27 = (_QWORD *)v23[5];
      if ( *v27 != v25 )
        goto LABEL_36;
      *v27 = v26;
      *(_QWORD *)(v26 + 8) = v27;
      ExReleasePushLockExclusiveEx(a1 + 48, 0);
      v23[5] = v23 + 4;
      *(_QWORD *)v25 = v25;
      v23[1] = v23;
      *v23 = v23;
      v28 = *(void (__fastcall **)(_QWORD, _QWORD *))(a1 + 136);
      if ( v28 )
      {
        v28(*(_QWORD *)(a1 + 144), v23 - 8);
        v11[5] = 0;
      }
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 100));
      v4 = a4;
    }
    else
    {
      ExReleasePushLockExclusiveEx(a1 + 48, 0);
      v12 = ((*(_DWORD *)(a1 + 96) + 7) & 0xFFFFFFF8) + 136;
      Pool2 = ExAllocatePool2(256, v12, 1666086994);
      v11 = (_QWORD *)Pool2;
      if ( !Pool2 )
        return 0;
      *(_WORD *)Pool2 = -5247;
      *(_WORD *)(Pool2 + 2) = v12;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 88));
      _InterlockedIncrement(&dword_140038AD8);
      *(_QWORD *)(Pool2 + 88) = 0;
      *(_DWORD *)(Pool2 + 80) = 0;
      *(_QWORD *)(Pool2 + 104) = Pool2 + 96;
      *(_QWORD *)(Pool2 + 96) = Pool2 + 96;
      *(_QWORD *)(Pool2 + 72) = Pool2 + 64;
      *(_QWORD *)(Pool2 + 64) = Pool2 + 64;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids);
      }
    }
  }
  else
  {
    ExReleasePushLockExclusiveEx(a1 + 48, 0);
  }
  if ( a2->Length > *((_WORD *)v11 + 41) )
  {
    v17 = (void *)v11[11];
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      v11[11] = 0;
    }
    if ( a2->Length )
      v18 = ExAllocatePool2(258, a2->Length, 1666086994);
    else
      v18 = 0;
    v11[11] = v18;
    if ( a2->Length && !v18 )
    {
      *((_DWORD *)v11 + 20) = 0;
      ExAcquirePushLockExclusiveEx(a1 + 48, 0);
      v29 = *v9;
      if ( *(__int64 **)(*v9 + 8) != v9 )
        goto LABEL_36;
      v11[8] = v29;
      v11[9] = v9;
      *(_QWORD *)(v29 + 8) = v11 + 8;
      *v9 = (__int64)(v11 + 8);
      ExReleasePushLockExclusiveEx(a1 + 48, 0);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v30 = 12;
LABEL_64:
        WPP_SF_(v21->AttachedDevice, v30, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids);
      }
      return 0;
    }
    *((_WORD *)v11 + 41) = a2->Length;
  }
  *((_WORD *)v11 + 40) = a2->Length;
  *((_BYTE *)v11 + 128) = v4;
  *((_DWORD *)v11 + 28) = 0;
  if ( a3 )
    v14 = *a3;
  else
    v14 = 0;
  v11[15] = v14;
  if ( a2->Length )
  {
    memmove((void *)v11[11], a2->Buffer, a2->Length);
    RtlHashUnicodeString(a2, 1u, 0, (PULONG)v11 + 28);
  }
  v15 = *(__int64 (__fastcall **)(_QWORD, _QWORD *))(a1 + 128);
  if ( v15 )
  {
    v19 = v15(*(_QWORD *)(a1 + 144), v11);
    v11[5] = v19;
    if ( v19 )
      goto LABEL_23;
    ExAcquirePushLockExclusiveEx(a1 + 48, 0);
    v20 = *v9;
    if ( *(__int64 **)(*v9 + 8) != v9 )
LABEL_36:
      __fastfail(3u);
    v11[8] = v20;
    v11[9] = v9;
    *(_QWORD *)(v20 + 8) = v11 + 8;
    *v9 = (__int64)(v11 + 8);
    ExReleasePushLockExclusiveEx(a1 + 48, 0);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v30 = 13;
      goto LABEL_64;
    }
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 96) )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids);
    }
    return v11;
  }
  v11[5] = v11 + 17;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids);
    goto LABEL_23;
  }
  return v11;
}

```

## disassembly

```asm
0x14006e7d0  mov     [rsp+arg_10], rbp
0x14006e7d5  mov     [rsp+arg_18], r9b
0x14006e7da  push    rsi
0x14006e7db  push    rdi
0x14006e7dc  push    r12
0x14006e7de  push    r13
0x14006e7e0  push    r14
0x14006e7e2  sub     rsp, 20h
0x14006e7e6  movzx   r12d, r9b
0x14006e7ea  mov     r13, r8
0x14006e7ed  mov     r14, rdx
0x14006e7f0  mov     rsi, rcx
0x14006e7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e7fa  lea     rax, WPP_GLOBAL_Control
0x14006e801  cmp     rcx, rax
0x14006e804  jz      short loc_14006E813
0x14006e806  test    dword ptr [rcx+2Ch], 800h
0x14006e80d  jnz     loc_14006EC44
0x14006e813  mov     [rsp+48h+arg_0], rbx
0x14006e818  lea     rcx, [rsi+30h]
0x14006e81c  xor     edx, edx
0x14006e81e  mov     [rsp+48h+arg_8], r15
0x14006e823  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006e82a  nop     dword ptr [rax+rax+00h]
0x14006e82f  mov     rax, [rsi+48h]
0x14006e833  lea     rdi, [rsi+48h]
0x14006e837  cmp     rax, rdi
0x14006e83a  jz      short loc_14006E86E
0x14006e83c  cmp     [rax+8], rdi
0x14006e840  jnz     loc_14006EACF
0x14006e846  mov     rcx, [rax]
0x14006e849  cmp     [rcx+8], rax
0x14006e84d  jnz     loc_14006EACF
0x14006e853  mov     [rdi], rcx
0x14006e856  lea     rbx, [rax-40h]
0x14006e85a  mov     [rcx+8], rdi
0x14006e85e  mov     [rax+8], rax
0x14006e862  mov     [rax], rax
0x14006e865  test    rbx, rbx
0x14006e868  jnz     loc_14006E939
0x14006e86e  mov     eax, [rsi+5Ch]
0x14006e871  shl     eax, 3
0x14006e874  cmp     [rsi+58h], eax
0x14006e877  jnb     loc_14006EB1F
0x14006e87d  xor     edx, edx
0x14006e87f  lea     rcx, [rsi+30h]
0x14006e883  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006e88a  nop     dword ptr [rax+rax+00h]
0x14006e88f  mov     r15d, [rsi+60h]
0x14006e893  mov     ecx, 100h
0x14006e898  add     r15d, 7
0x14006e89c  mov     r8d, 634E7852h
0x14006e8a2  and     r15d, 0FFFFFFF8h
0x14006e8a6  add     r15d, 88h
0x14006e8ad  mov     edx, r15d
0x14006e8b0  call    cs:__imp_ExAllocatePool2
0x14006e8b7  nop     dword ptr [rax+rax+00h]
0x14006e8bc  mov     rbx, rax
0x14006e8bf  test    rax, rax
0x14006e8c2  jz      loc_14006EB18
0x14006e8c8  mov     word ptr [rax], 0EB81h
0x14006e8cd  mov     [rax+2], r15w
0x14006e8d2  lock inc dword ptr [rsi+58h]
0x14006e8d6  lock inc cs:dword_140038AD8
0x14006e8dd  mov     qword ptr [rax+58h], 0
0x14006e8e5  xor     eax, eax
0x14006e8e7  mov     [rbx+50h], eax
0x14006e8ea  lea     rax, [rbx+60h]
0x14006e8ee  mov     [rax+8], rax
0x14006e8f2  mov     [rax], rax
0x14006e8f5  lea     rax, [rbx+40h]
0x14006e8f9  mov     [rax+8], rax
0x14006e8fd  mov     [rax], rax
0x14006e900  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e907  lea     rax, WPP_GLOBAL_Control
0x14006e90e  cmp     rcx, rax
0x14006e911  jz      short loc_14006E94B
0x14006e913  test    dword ptr [rcx+2Ch], 800h
0x14006e91a  jz      short loc_14006E94B
0x14006e91c  cmp     byte ptr [rcx+29h], 4
0x14006e920  jb      short loc_14006E94B
0x14006e922  mov     rcx, [rcx+18h]
0x14006e926  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006e92d  mov     edx, 0Bh
0x14006e932  call    WPP_SF_
0x14006e937  jmp     short loc_14006E94B
0x14006e939  xor     edx, edx
0x14006e93b  lea     rcx, [rsi+30h]
0x14006e93f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006e946  nop     dword ptr [rax+rax+00h]
0x14006e94b  movzx   eax, word ptr [rbx+52h]
0x14006e94f  cmp     [r14], ax
0x14006e953  ja      loc_14006EA31
0x14006e959  movzx   eax, word ptr [r14]
0x14006e95d  mov     [rbx+50h], ax
0x14006e961  mov     [rbx+80h], r12b
0x14006e968  mov     dword ptr [rbx+70h], 0
0x14006e96f  test    r13, r13
0x14006e972  jz      loc_14006EAD6
0x14006e978  mov     rax, [r13+0]
0x14006e97c  mov     [rbx+78h], rax
0x14006e980  movzx   eax, word ptr [r14]
0x14006e984  test    ax, ax
0x14006e987  jz      short loc_14006E9B1
0x14006e989  mov     rdx, [r14+8]; Src
0x14006e98d  mov     r8d, eax; Size
0x14006e990  mov     rcx, [rbx+58h]; void *
0x14006e994  call    memmove
0x14006e999  lea     r9, [rbx+70h]; HashValue
0x14006e99d  xor     r8d, r8d; HashAlgorithm
0x14006e9a0  mov     dl, 1; CaseInSensitive
0x14006e9a2  mov     rcx, r14; String
0x14006e9a5  call    cs:__imp_RtlHashUnicodeString
0x14006e9ac  nop     dword ptr [rax+rax+00h]
0x14006e9b1  mov     rax, [rsi+80h]
0x14006e9b8  test    rax, rax
0x14006e9bb  jnz     loc_14006EA98
0x14006e9c1  cmp     [rsi+60h], eax
0x14006e9c4  jbe     short loc_14006E9F1
0x14006e9c6  lea     rax, [rbx+88h]
0x14006e9cd  mov     [rbx+28h], rax
0x14006e9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9d8  lea     rax, WPP_GLOBAL_Control
0x14006e9df  cmp     rcx, rax
0x14006e9e2  jz      short loc_14006EA11
0x14006e9e4  test    dword ptr [rcx+2Ch], 800h
0x14006e9eb  jnz     loc_14006EC93
0x14006e9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9f8  lea     rax, WPP_GLOBAL_Control
0x14006e9ff  cmp     rcx, rax
0x14006ea02  jz      short loc_14006EA11
0x14006ea04  test    dword ptr [rcx+2Ch], 800h
0x14006ea0b  jnz     loc_14006ECB7
0x14006ea11  mov     rax, rbx
0x14006ea14  mov     r15, [rsp+48h+arg_8]
0x14006ea19  mov     rbx, [rsp+48h+arg_0]
0x14006ea1e  mov     rbp, [rsp+48h+arg_10]
0x14006ea23  add     rsp, 20h
0x14006ea27  pop     r14
0x14006ea29  pop     r13
0x14006ea2b  pop     r12
0x14006ea2d  pop     rdi
0x14006ea2e  pop     rsi
0x14006ea2f  retn
0x14006ea31  mov     rcx, [rbx+58h]; P
0x14006ea35  test    rcx, rcx
0x14006ea38  jz      short loc_14006EA50
0x14006ea3a  xor     edx, edx; Tag
0x14006ea3c  call    cs:__imp_ExFreePoolWithTag
0x14006ea43  nop     dword ptr [rax+rax+00h]
0x14006ea48  mov     qword ptr [rbx+58h], 0
0x14006ea50  movzx   eax, word ptr [r14]
0x14006ea54  test    ax, ax
0x14006ea57  jz      loc_14006EC6B
0x14006ea5d  mov     edx, eax
0x14006ea5f  mov     ecx, 102h
0x14006ea64  mov     r8d, 634E7852h
0x14006ea6a  call    cs:__imp_ExAllocatePool2
0x14006ea71  nop     dword ptr [rax+rax+00h]
0x14006ea76  mov     rcx, rax
0x14006ea79  mov     [rbx+58h], rcx
0x14006ea7d  movzx   eax, word ptr [r14]
0x14006ea81  test    ax, ax
0x14006ea84  jz      short loc_14006EA8F
0x14006ea86  test    rcx, rcx
0x14006ea89  jz      loc_14006EBC4
0x14006ea8f  mov     [rbx+52h], ax
0x14006ea93  jmp     loc_14006E959
0x14006ea98  mov     rcx, [rsi+90h]
0x14006ea9f  mov     rdx, rbx
0x14006eaa2  call    _guard_dispatch_icall
0x14006eaa7  mov     [rbx+28h], rax
0x14006eaab  test    rax, rax
0x14006eaae  jnz     loc_14006E9F1
0x14006eab4  xor     edx, edx
0x14006eab6  lea     rcx, [rsi+30h]
0x14006eaba  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006eac1  nop     dword ptr [rax+rax+00h]
0x14006eac6  mov     rcx, [rdi]
0x14006eac9  cmp     [rcx+8], rdi
0x14006eacd  jz      short loc_14006EADD
0x14006eacf  mov     ecx, 3
0x14006ead4  int     29h; Win8: RtlFailFast(ecx)
0x14006ead6  xor     eax, eax
0x14006ead8  jmp     loc_14006E97C
0x14006eadd  lea     rax, [rbx+40h]
0x14006eae1  xor     edx, edx
0x14006eae3  mov     [rax], rcx
0x14006eae6  mov     [rax+8], rdi
0x14006eaea  mov     [rcx+8], rax
0x14006eaee  lea     rcx, [rsi+30h]
0x14006eaf2  mov     [rdi], rax
0x14006eaf5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006eafc  nop     dword ptr [rax+rax+00h]
0x14006eb01  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eb08  lea     rax, WPP_GLOBAL_Control
0x14006eb0f  cmp     rcx, rax
0x14006eb12  jnz     loc_14006EC72
0x14006eb18  xor     eax, eax
0x14006eb1a  jmp     loc_14006EA14
0x14006eb1f  lea     rax, [rsi+38h]
0x14006eb23  cmp     [rax], rax
0x14006eb26  jz      loc_14006ECDB
0x14006eb2c  mov     r15, [rax+8]
0x14006eb30  cmp     [r15], rax
0x14006eb33  jnz     short loc_14006EACF
0x14006eb35  mov     rcx, [r15+8]
0x14006eb39  cmp     [rcx], r15
0x14006eb3c  jnz     short loc_14006EACF
0x14006eb3e  mov     [rax+8], rcx
0x14006eb42  lea     rbx, [r15-40h]
0x14006eb46  lea     r12, [rbx+60h]
0x14006eb4a  mov     [rcx], rax
0x14006eb4d  mov     rax, [r12]
0x14006eb51  cmp     [rax+8], r12
0x14006eb55  jnz     loc_14006EACF
0x14006eb5b  mov     rcx, [r12+8]
0x14006eb60  cmp     [rcx], r12
0x14006eb63  jnz     loc_14006EACF
0x14006eb69  mov     [rcx], rax
0x14006eb6c  xor     edx, edx
0x14006eb6e  mov     [rax+8], rcx
0x14006eb72  lea     rcx, [rsi+30h]
0x14006eb76  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006eb7d  nop     dword ptr [rax+rax+00h]
0x14006eb82  mov     [r12+8], r12
0x14006eb87  mov     [r12], r12
0x14006eb8b  mov     [r15+8], r15
0x14006eb8f  mov     [r15], r15
0x14006eb92  mov     rax, [rsi+88h]
0x14006eb99  test    rax, rax
0x14006eb9c  jz      short loc_14006EBB5
0x14006eb9e  mov     rcx, [rsi+90h]
0x14006eba5  mov     rdx, rbx
0x14006eba8  call    _guard_dispatch_icall
0x14006ebad  mov     qword ptr [rbx+28h], 0
0x14006ebb5  lock dec dword ptr [rsi+64h]
0x14006ebb9  movzx   r12d, [rsp+48h+arg_18]
0x14006ebbf  jmp     loc_14006E94B
0x14006ebc4  xor     eax, eax
0x14006ebc6  lea     rcx, [rsi+30h]
0x14006ebca  xor     edx, edx
0x14006ebcc  mov     [rbx+50h], eax
0x14006ebcf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006ebd6  nop     dword ptr [rax+rax+00h]
0x14006ebdb  mov     rcx, [rdi]
0x14006ebde  cmp     [rcx+8], rdi
0x14006ebe2  jnz     loc_14006EACF
0x14006ebe8  lea     rax, [rbx+40h]
0x14006ebec  xor     edx, edx
0x14006ebee  mov     [rax], rcx
0x14006ebf1  mov     [rax+8], rdi
0x14006ebf5  mov     [rcx+8], rax
0x14006ebf9  lea     rcx, [rsi+30h]
0x14006ebfd  mov     [rdi], rax
0x14006ec00  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006ec07  nop     dword ptr [rax+rax+00h]
0x14006ec0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ec13  lea     rax, WPP_GLOBAL_Control
0x14006ec1a  cmp     rcx, rax
0x14006ec1d  jz      loc_14006EB18
0x14006ec23  test    dword ptr [rcx+2Ch], 800h
0x14006ec2a  jz      loc_14006EB18
0x14006ec30  cmp     byte ptr [rcx+29h], 4
0x14006ec34  jb      loc_14006EB18
0x14006ec3a  mov     edx, 0Ch
0x14006ec3f  jmp     loc_14007F1CC
0x14006ec44  cmp     byte ptr [rcx+29h], 4
0x14006ec48  jb      loc_14006E813
0x14006ec4e  mov     rcx, [rcx+18h]
0x14006ec52  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006ec59  mov     edx, 0Ah
0x14006ec5e  mov     r9, r14
0x14006ec61  call    WPP_SF_Z
0x14006ec66  jmp     loc_14006E813
0x14006ec6b  xor     ecx, ecx
0x14006ec6d  jmp     loc_14006EA79
0x14006ec72  test    dword ptr [rcx+2Ch], 800h
0x14006ec79  jz      loc_14006EB18
0x14006ec7f  cmp     byte ptr [rcx+29h], 4
0x14006ec83  jb      loc_14006EB18
0x14006ec89  mov     edx, 0Dh
0x14006ec8e  jmp     loc_14007F1CC
0x14006ec93  cmp     byte ptr [rcx+29h], 4
0x14006ec97  jb      loc_14006E9F1
0x14006ec9d  mov     rcx, [rcx+18h]
0x14006eca1  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006eca8  mov     edx, 0Eh
0x14006ecad  call    WPP_SF_
0x14006ecb2  jmp     loc_14006E9F1
0x14006ecb7  cmp     byte ptr [rcx+29h], 4
0x14006ecbb  jb      loc_14006EA11
0x14006ecc1  mov     rcx, [rcx+18h]
0x14006ecc5  lea     r8, WPP_1519d73bff3037ddba3ff7d0fa361a6d_Traceguids
0x14006eccc  mov     edx, 0Fh
0x14006ecd1  call    WPP_SF_
0x14006ecd6  jmp     loc_14006EA11
0x14006ecdb  xor     edx, edx
0x14006ecdd  lea     rcx, [rsi+30h]
0x14006ece1  call    cs:__imp_ExReleasePushLockExclusiveEx
  ... truncated ...
```
