# CDirectMusicEmulatePort::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18001b690`
- end: `0x18001b7ff`
- name: `?KsProperty@CDirectMusicEmulatePort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `367`
- prototype: `int(CDirectMusicEmulatePort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18001b690`
- `0x1800217bc`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulatePort::KsProperty(
        CDirectMusicEmulatePort *this,
        struct KSIDENTIFIER *a2,
        int a3,
        _DWORD *a4,
        size_t Size,
        unsigned int *a6)
{
  unsigned int *v7; // rdi
  __int64 Id; // rdx
  struct GENERICPROPERTY near **v10; // r10
  unsigned int v11; // eax
  __int64 v12; // rdx
  struct GENERICPROPERTY near *v13; // rax
  unsigned int v14; // ebx

  if ( a3 && !a2 )
    return 2147500035LL;
  v7 = a6;
  if ( !a6 )
    return 2147500035LL;
  Id = a2->Id;
  v10 = &CDirectMusicEmulatePort::m_aProperty;
  while ( *(_QWORD *)*v10 != a2->Alignment
       || *((_QWORD *)*v10 + 1) != *(&a2->Alignment + 1)
       || *((_DWORD *)v10 + 2) != (_DWORD)Id )
  {
    v10 += 8;
    if ( v10 == (struct GENERICPROPERTY near **)&wil::details::g_featureStateManager )
      return 2289570082LL;
  }
  if ( (a2->Flags & 0x203) != 1 )
  {
    if ( (a2->Flags & 0x203) == 2 )
    {
      if ( (*((_BYTE *)v10 + 12) & 2) == 0 )
        return 2289570083LL;
      if ( ((_BYTE)v10[2] & 1) != 0 )
        return ((__int64 (__fastcall *)(char *, __int64, __int64, _DWORD *, size_t *))v10[5])(
                 (char *)this + *((int *)v10 + 12) - 24,
                 Id,
                 2,
                 a4,
                 &Size);
      v11 = Size;
      if ( (unsigned int)Size > *((_DWORD *)v10 + 8) )
        v11 = *((_DWORD *)v10 + 8);
      memcpy_0(v10[3], a4, v11);
    }
    else
    {
      if ( (a2->Flags & 0x203) != 0x200 || (unsigned int)Size < 4 )
        return 2147942487LL;
      *a4 = *((_DWORD *)v10 + 3);
      *v7 = 4;
    }
    return 0;
  }
  if ( (*((_BYTE *)v10 + 12) & 1) == 0 )
    return 2289570084LL;
  if ( ((_BYTE)v10[2] & 1) == 0 )
  {
    v14 = Size;
    if ( (unsigned int)Size > *((_DWORD *)v10 + 8) )
    {
      v14 = *((_DWORD *)v10 + 8);
      LODWORD(Size) = v14;
    }
    memcpy_0(a4, v10[3], v14);
    *v7 = v14;
    return 0;
  }
  v12 = *((int *)v10 + 12);
  v13 = v10[5];
  *a6 = Size;
  return ((__int64 (__fastcall *)(char *, _QWORD, __int64, _DWORD *, unsigned int *))v13)(
           (char *)this + v12 - 24,
           a2->Id,
           1,
           a4,
           v7);
}

```

## disassembly

```asm
0x18001b690  mov     [rsp+arg_0], rbx
0x18001b695  push    rdi
0x18001b696  sub     rsp, 30h
0x18001b69a  mov     r11, rdx
0x18001b69d  mov     rbx, rcx
0x18001b6a0  test    r8d, r8d
0x18001b6a3  jz      short loc_18001B6AA
0x18001b6a5  test    rdx, rdx
0x18001b6a8  jz      short loc_18001B6B4
0x18001b6aa  mov     rdi, [rsp+38h+arg_28]
0x18001b6af  test    rdi, rdi
0x18001b6b2  jnz     short loc_18001B6BB
0x18001b6b4  mov     eax, 80004003h
0x18001b6b9  jmp     short loc_18001B6F5
0x18001b6bb  mov     edx, [rdx+10h]
0x18001b6be  lea     r10, ?m_aProperty@CDirectMusicEmulatePort@@0PAUGENERICPROPERTY@@A; GENERICPROPERTY near * CDirectMusicEmulatePort::m_aProperty
0x18001b6c5  mov     rcx, [r10]
0x18001b6c8  mov     rax, [rcx]
0x18001b6cb  cmp     rax, [r11]
0x18001b6ce  jnz     short loc_18001B6E0
0x18001b6d0  mov     rax, [rcx+8]
0x18001b6d4  cmp     rax, [r11+8]
0x18001b6d8  jnz     short loc_18001B6E0
0x18001b6da  cmp     [r10+8], edx
0x18001b6de  jz      short loc_18001B700
0x18001b6e0  add     r10, 40h ; '@'
0x18001b6e4  lea     rax, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001b6eb  cmp     r10, rax
0x18001b6ee  jnz     short loc_18001B6C5
0x18001b6f0  mov     eax, 88781122h
0x18001b6f5  mov     rbx, [rsp+38h+arg_0]
0x18001b6fa  add     rsp, 30h
0x18001b6fe  pop     rdi
0x18001b6ff  retn
0x18001b700  mov     eax, [r11+14h]
0x18001b704  and     eax, 203h
0x18001b709  sub     eax, 1
0x18001b70c  jz      loc_18001B794
0x18001b712  sub     eax, 1
0x18001b715  jz      short loc_18001B73B
0x18001b717  cmp     eax, 1FEh
0x18001b71c  jnz     short loc_18001B725
0x18001b71e  cmp     dword ptr [rsp+38h+Size], 4
0x18001b723  jnb     short loc_18001B72C
0x18001b725  mov     eax, 80070057h
0x18001b72a  jmp     short loc_18001B6F5
0x18001b72c  mov     eax, [r10+0Ch]
0x18001b730  mov     [r9], eax
0x18001b733  mov     dword ptr [rdi], 4
0x18001b739  jmp     short loc_18001B78D
0x18001b73b  mov     r8d, 2
0x18001b741  test    [r10+0Ch], r8b
0x18001b745  jnz     short loc_18001B74E
0x18001b747  mov     eax, 88781123h
0x18001b74c  jmp     short loc_18001B6F5
0x18001b74e  test    byte ptr [r10+10h], 1
0x18001b753  jz      short loc_18001B770
0x18001b755  movsxd  rcx, dword ptr [r10+30h]
0x18001b759  lea     rax, [rsp+38h+Size]
0x18001b75e  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18001b762  mov     [rsp+38h+var_18], rax
0x18001b767  mov     rax, [r10+28h]
0x18001b76b  add     rcx, rbx
0x18001b76e  jmp     short loc_18001B7D0
0x18001b770  mov     eax, dword ptr [rsp+38h+Size]
0x18001b774  cmp     eax, [r10+20h]
0x18001b778  jbe     short loc_18001B77E
0x18001b77a  mov     eax, [r10+20h]
0x18001b77e  mov     rcx, [r10+18h]; void *
0x18001b782  mov     rdx, r9; Src
0x18001b785  mov     r8d, eax; Size
0x18001b788  call    memcpy_0
0x18001b78d  xor     eax, eax
0x18001b78f  jmp     loc_18001B6F5
0x18001b794  test    byte ptr [r10+0Ch], 1
0x18001b799  jnz     short loc_18001B7A5
0x18001b79b  mov     eax, 88781124h
0x18001b7a0  jmp     loc_18001B6F5
0x18001b7a5  test    byte ptr [r10+10h], 1
0x18001b7aa  jz      short loc_18001B7DA
0x18001b7ac  movsxd  rdx, dword ptr [r10+30h]
0x18001b7b0  mov     r8d, 1
0x18001b7b6  mov     ecx, dword ptr [rsp+38h+Size]
0x18001b7ba  mov     rax, [r10+28h]
0x18001b7be  mov     [rdi], ecx
0x18001b7c0  lea     rcx, [rbx-18h]
0x18001b7c4  add     rcx, rdx
0x18001b7c7  mov     [rsp+38h+var_18], rdi
0x18001b7cc  mov     edx, [r11+10h]
0x18001b7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7d5  jmp     loc_18001B6F5
0x18001b7da  mov     ebx, dword ptr [rsp+38h+Size]
0x18001b7de  cmp     ebx, [r10+20h]
0x18001b7e2  jbe     short loc_18001B7EC
0x18001b7e4  mov     ebx, [r10+20h]
0x18001b7e8  mov     dword ptr [rsp+38h+Size], ebx
0x18001b7ec  mov     rdx, [r10+18h]; Src
0x18001b7f0  mov     rcx, r9; void *
0x18001b7f3  mov     r8d, ebx; Size
0x18001b7f6  call    memcpy_0
0x18001b7fb  mov     [rdi], ebx
0x18001b7fd  jmp     short loc_18001B78D
```
