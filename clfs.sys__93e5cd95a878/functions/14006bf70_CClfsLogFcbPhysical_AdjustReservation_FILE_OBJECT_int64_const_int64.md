# CClfsLogFcbPhysical::AdjustReservation(_FILE_OBJECT *,__int64 const &,__int64 *)

- ea: `0x14006bf70`
- end: `0x14006c200`
- name: `?AdjustReservation@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@AEB_JPEA_J@Z`
- size: `656`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, const __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140015360`

## callees

- `0x1400035a8`
- `0x1400092d8`
- `0x140017f20`
- `0x14006bf70`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006bfb8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006bfb8`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006c1ac`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007b6f3`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006c1ac`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007b6f3`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::AdjustReservation(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned __int64 *a3,
        __int64 *a4)
{
  int v7; // edi
  char v8; // r14
  BOOLEAN v9; // r12
  __int64 v10; // r9
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r8
  int v14; // edx
  __int64 v15; // r10
  __int64 v16; // r11
  unsigned __int64 v17; // r9
  int v18; // r15d
  __int64 v19; // r10
  __int64 v20; // r11
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r10
  unsigned __int64 v23; // r9
  __int16 v25; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+28h] [rbp-50h]
  unsigned __int64 v27; // [rsp+30h] [rbp-48h]

  v7 = 0;
  v8 = 0;
  v9 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v25 = v9;
  v10 = *((_QWORD *)this + 59);
  v26 = v10;
  v11 = *((_QWORD *)this + 58);
  v12 = *a3;
  if ( (*a3 & 0x8000000000000000uLL) == 0LL )
  {
    v13 = *(unsigned int *)(*((_QWORD *)this + 89) + 144LL);
    if ( (_DWORD)v13 )
    {
      v19 = (unsigned int)(v13 - 1);
      v27 = ~v19 & (v19 + v12);
    }
    else
    {
      v27 = 0;
      LODWORD(v19) = -1;
    }
    v20 = (unsigned int)v19;
    v21 = ~(unsigned __int64)(unsigned int)v19;
    if ( (_DWORD)v13 )
      v22 = v21 & ((unsigned int)v19 + v11 + v10);
    else
      v22 = 0;
    if ( v27 > v22 )
    {
      v7 = -1072037859;
      goto LABEL_34;
    }
    if ( (_DWORD)v13 )
      v23 = v21 & (v20 + v10);
    else
      v23 = 0;
    if ( (_DWORD)v13 )
      v12 = v21 & (v20 + v12);
    else
      v12 = 0;
    v17 = v11 - v12 + v23;
    *((_QWORD *)this + 58) = v17;
    *((_QWORD *)this + 59) = *a3;
  }
  else
  {
    v13 = v12 + v10;
    if ( (__int64)(v12 + v10) < 0 )
    {
      v7 = -1073741811;
      goto LABEL_34;
    }
    v14 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
    if ( v14 )
    {
      v15 = (unsigned int)(v14 - 1);
      v16 = ~v15 & (v15 + v13);
    }
    else
    {
      v16 = 0;
      LODWORD(v15) = -1;
    }
    if ( v14 )
      v12 = ~(unsigned __int64)(unsigned int)v15 & ((unsigned int)v15 + v10);
    else
      v12 = 0;
    *((_QWORD *)this + 59) = v13;
    v17 = v11 - v16 + v12;
    *((_QWORD *)this + 58) = v17;
  }
  v18 = *((_DWORD *)this + 1380);
  if ( v18 <= 0 || v17 < *((_QWORD *)this + 87) )
  {
    if ( v17 > v11 )
    {
      v13 = *((_QWORD *)this + 87);
      v12 = v17 % v13;
      if ( v17 / v13 > v11 / v13 )
        CClfsLogFcbPhysical::ObservationContainerAvailable(this);
    }
  }
  else
  {
    CClfsLogFcbPhysical::WrapContainers(this, a2);
    if ( v18 != *((_DWORD *)this + 1380) )
    {
      v8 = 1;
      HIBYTE(v25) = 1;
    }
  }
  v10 = v26;
LABEL_34:
  if ( a4 )
  {
    if ( v7 >= 0 )
      *a4 = *((_QWORD *)this + 59) - v10;
    else
      *a4 = 0;
  }
  if ( v9 )
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v8 )
    (*(void (__fastcall **)(CClfsLogFcbPhysical *, unsigned __int64, unsigned __int64, __int64, __int16))(*(_QWORD *)this + 232LL))(
      this,
      v12,
      v13,
      v10,
      v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14006bf70  mov     rax, rsp
0x14006bf73  mov     [rax+20h], r9
0x14006bf77  mov     [rax+10h], rdx
0x14006bf7b  mov     [rax+8], rcx
0x14006bf7f  push    rbx
0x14006bf80  push    rsi
0x14006bf81  push    rdi
0x14006bf82  push    r12
0x14006bf84  push    r13
0x14006bf86  push    r14
0x14006bf88  push    r15
0x14006bf8a  sub     rsp, 40h
0x14006bf8e  mov     rsi, r9
0x14006bf91  mov     r15, r8
0x14006bf94  mov     rbx, rcx
0x14006bf97  mov     qword ptr [rax-40h], 0
0x14006bf9f  xor     edi, edi
0x14006bfa1  mov     [rax-54h], edi
0x14006bfa4  mov     [rax-58h], dil
0x14006bfa8  xor     r14b, r14b
0x14006bfab  mov     [rax-57h], r14b
0x14006bfaf  mov     dl, 1; Wait
0x14006bfb1  add     rcx, 0C8h; Resource
0x14006bfb8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006bfbf  nop     dword ptr [rax+rax+00h]
0x14006bfc4  movzx   r12d, al
0x14006bfc8  mov     [rsp+78h+var_58], al
0x14006bfcc  mov     r9, [rbx+1D8h]
0x14006bfd3  mov     [rsp+78h+var_50], r9
0x14006bfd8  mov     [rsp+78h+var_40], r9
0x14006bfdd  mov     rcx, [rbx+1D0h]
0x14006bfe4  mov     rdx, [r15]
0x14006bfe7  test    rdx, rdx
0x14006bfea  jns     loc_14006C0B4
0x14006bff0  lea     r8, [rdx+r9]
0x14006bff4  test    r8, r8
0x14006bff7  js      short loc_14006C06B
0x14006bff9  mov     rax, [rbx+2C8h]
0x14006c000  mov     edx, [rax+90h]
0x14006c006  test    edx, edx
0x14006c008  jz      loc_14006C0A2
0x14006c00e  lea     r10d, [rdx-1]
0x14006c012  mov     eax, r10d
0x14006c015  lea     r11, [r10+r8]
0x14006c019  not     rax
0x14006c01c  and     r11, rax
0x14006c01f  test    edx, edx
0x14006c021  jz      loc_14006C0B0
0x14006c027  mov     eax, r10d
0x14006c02a  lea     rdx, [rax+r9]
0x14006c02e  not     rax
0x14006c031  and     rdx, rax
0x14006c034  mov     [rbx+1D8h], r8
0x14006c03b  mov     rax, rcx
0x14006c03e  sub     rax, r11
0x14006c041  lea     r9, [rax+rdx]
0x14006c045  mov     [rbx+1D0h], r9
0x14006c04c  mov     r15d, [rbx+1590h]
0x14006c053  test    r15d, r15d
0x14006c056  jg      loc_14006C15B
0x14006c05c  cmp     r9, rcx
0x14006c05f  ja      short loc_14006C079
0x14006c061  mov     r9, [rsp+78h+var_50]
0x14006c066  jmp     loc_14006C192
0x14006c06b  mov     edi, 0C000000Dh
0x14006c070  mov     [rsp+78h+var_54], edi
0x14006c074  jmp     loc_14006C192
0x14006c079  mov     r8, [rbx+2B8h]
0x14006c080  xor     edx, edx
0x14006c082  mov     rax, rcx
0x14006c085  div     r8
0x14006c088  mov     rcx, rax
0x14006c08b  xor     edx, edx
0x14006c08d  mov     rax, r9
0x14006c090  div     r8
0x14006c093  cmp     rax, rcx
0x14006c096  jbe     short loc_14006C061
0x14006c098  mov     rcx, rbx; this
0x14006c09b  call    ?ObservationContainerAvailable@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::ObservationContainerAvailable(void)
0x14006c0a0  jmp     short loc_14006C061
0x14006c0a2  xor     r11d, r11d
0x14006c0a5  mov     r10d, 0FFFFFFFFh
0x14006c0ab  jmp     loc_14006C01F
0x14006c0b0  xor     edx, edx
0x14006c0b2  jmp     short loc_14006C034
0x14006c0b4  mov     rax, [rbx+2C8h]
0x14006c0bb  mov     r8d, [rax+90h]
0x14006c0c2  test    r8d, r8d
0x14006c0c5  jz      short loc_14006C131
0x14006c0c7  lea     r10d, [r8-1]
0x14006c0cb  mov     eax, r10d
0x14006c0ce  lea     r11, [r10+rdx]
0x14006c0d2  not     rax
0x14006c0d5  and     r11, rax
0x14006c0d8  mov     [rsp+78h+var_48], r11
0x14006c0dd  mov     r11d, r10d
0x14006c0e0  mov     eax, r10d
0x14006c0e3  not     rax
0x14006c0e6  test    r8d, r8d
0x14006c0e9  jz      short loc_14006C142
0x14006c0eb  lea     r10, [rcx+r9]
0x14006c0ef  add     r10, r11
0x14006c0f2  and     r10, rax
0x14006c0f5  cmp     [rsp+78h+var_48], r10
0x14006c0fa  ja      short loc_14006C150
0x14006c0fc  test    r8d, r8d
0x14006c0ff  jz      short loc_14006C147
0x14006c101  add     r9, r11
0x14006c104  and     r9, rax
0x14006c107  test    r8d, r8d
0x14006c10a  jz      short loc_14006C14C
0x14006c10c  add     rdx, r11
0x14006c10f  and     rdx, rax
0x14006c112  mov     rax, rcx
0x14006c115  sub     rax, rdx
0x14006c118  add     r9, rax
0x14006c11b  mov     [rbx+1D0h], r9
0x14006c122  mov     rax, [r15]
0x14006c125  mov     [rbx+1D8h], rax
0x14006c12c  jmp     loc_14006C04C
0x14006c131  mov     [rsp+78h+var_48], 0
0x14006c13a  mov     r10d, 0FFFFFFFFh
0x14006c140  jmp     short loc_14006C0DD
0x14006c142  xor     r10d, r10d
0x14006c145  jmp     short loc_14006C0F5
0x14006c147  xor     r9d, r9d
0x14006c14a  jmp     short loc_14006C107
0x14006c14c  xor     edx, edx
0x14006c14e  jmp     short loc_14006C112
0x14006c150  mov     edi, 0C01A001Dh
0x14006c155  mov     [rsp+78h+var_54], edi
0x14006c159  jmp     short loc_14006C192
0x14006c15b  cmp     r9, [rbx+2B8h]
0x14006c162  jb      loc_14006C05C
0x14006c168  mov     rdx, [rsp+78h+arg_8]; struct _FILE_OBJECT *
0x14006c170  mov     rcx, rbx; this
0x14006c173  call    ?WrapContainers@CClfsLogFcbPhysical@@AEAAXPEAU_FILE_OBJECT@@@Z; CClfsLogFcbPhysical::WrapContainers(_FILE_OBJECT *)
0x14006c178  cmp     r15d, [rbx+1590h]
0x14006c17f  jz      loc_14006C061
0x14006c185  mov     r14b, 1
0x14006c188  mov     [rsp+78h+var_57], r14b
0x14006c18d  jmp     loc_14006C061
0x14006c192  test    rsi, rsi
0x14006c195  jnz     short loc_14006C1D0
0x14006c197  test    r12b, r12b
0x14006c19a  jz      short loc_14006C1B8
0x14006c19c  mov     rdx, gs:188h; ResourceThreadId
0x14006c1a5  lea     rcx, [rbx+0C8h]; Resource
0x14006c1ac  call    cs:__imp_ExReleaseResourceForThreadLite
0x14006c1b3  nop     dword ptr [rax+rax+00h]
0x14006c1b8  test    r14b, r14b
0x14006c1bb  jnz     short loc_14006C1EC
0x14006c1bd  mov     eax, edi
0x14006c1bf  add     rsp, 40h
0x14006c1c3  pop     r15
0x14006c1c5  pop     r14
0x14006c1c7  pop     r13
0x14006c1c9  pop     r12
0x14006c1cb  pop     rdi
0x14006c1cc  pop     rsi
0x14006c1cd  pop     rbx
0x14006c1ce  retn
0x14006c1d0  test    edi, edi
0x14006c1d2  jns     short loc_14006C1DD
0x14006c1d4  mov     qword ptr [rsi], 0
0x14006c1db  jmp     short loc_14006C197
0x14006c1dd  mov     rax, [rbx+1D8h]
0x14006c1e4  sub     rax, r9
0x14006c1e7  mov     [rsi], rax
0x14006c1ea  jmp     short loc_14006C197
0x14006c1ec  mov     rcx, [rbx]
0x14006c1ef  mov     rax, [rcx+0E8h]
0x14006c1f6  mov     rcx, rbx
0x14006c1f9  call    _guard_dispatch_icall
0x14006c1fe  jmp     short loc_14006C1BD
0x14007b690  push    rbx
0x14007b692  push    rbp
0x14007b693  sub     rsp, 28h
0x14007b697  mov     rbp, rdx
0x14007b69a  cmp     dword ptr [rbp+24h], 0
0x14007b69e  jl      short loc_14007B6C3
0x14007b6a0  mov     rcx, [rbp+98h]
0x14007b6a7  test    rcx, rcx
0x14007b6aa  jz      short loc_14007B6D6
0x14007b6ac  mov     rbx, [rbp+80h]
0x14007b6b3  mov     rax, [rbx+1D8h]
0x14007b6ba  sub     rax, [rbp+38h]
0x14007b6be  mov     [rcx], rax
0x14007b6c1  jmp     short loc_14007B6DD
0x14007b6c3  mov     rax, [rbp+98h]
0x14007b6ca  test    rax, rax
0x14007b6cd  jz      short loc_14007B6D6
0x14007b6cf  mov     qword ptr [rax], 0
0x14007b6d6  mov     rbx, [rbp+80h]
0x14007b6dd  cmp     byte ptr [rbp+20h], 0
0x14007b6e1  jz      short loc_14007B703
0x14007b6e3  mov     rdx, gs:188h; ResourceThreadId
0x14007b6ec  lea     rcx, [rbx+0C8h]; Resource
0x14007b6f3  call    cs:__imp_ExReleaseResourceForThreadLite
0x14007b6fa  nop     dword ptr [rax+rax+00h]
0x14007b6ff  mov     byte ptr [rbp+20h], 0
0x14007b703  cmp     byte ptr [rbp+21h], 0
0x14007b707  jz      short loc_14007B71C
0x14007b709  mov     rax, [rbx]
0x14007b70c  mov     rax, [rax+0E8h]
0x14007b713  mov     rcx, rbx
0x14007b716  call    _guard_dispatch_icall
0x14007b71b  nop
0x14007b71c  add     rsp, 28h
0x14007b720  pop     rbp
0x14007b721  pop     rbx
0x14007b722  retn
```
