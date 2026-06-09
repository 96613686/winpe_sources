# ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x18000fee0`
- end: `0x18000ffcc`
- name: `?GetIDsOfNames@?$IDispatchImpl@UIIasComponent@@$1?_GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B$1?_GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `236`
- prototype: `int __fastcall(ATL::CComTypeInfoHolder *, __int64, const void **, unsigned int, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fee0`
- `0x180010020`
- `0x180018196`
- `0x180019010`

## pseudocode

```c
int __fastcall ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        ATL::CComTypeInfoHolder *a1,
        __int64 a2,
        const void **a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6)
{
  struct ITypeInfo *v6; // r14
  __int64 v9; // rbx
  int result; // eax
  _WORD *v11; // r15
  __int64 v12; // rsi
  unsigned int v13; // ebp

  v6 = qword_1800242B8;
  if ( !qword_1800242B8 || (v9 = qword_1800242C8, result = 0, !qword_1800242C8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(a1, a5);
    v9 = qword_1800242C8;
    v6 = qword_1800242B8;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_1800242D0;
      while ( (--v13 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v9 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v13), v11, 2LL * *(int *)(v9 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, const void **, _QWORD, _DWORD *))v6->lpVtbl->GetIDsOfNames)(
             v6,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x18000fee0  push    rbx
0x18000fee2  push    rbp
0x18000fee3  push    rsi
0x18000fee4  push    rdi
0x18000fee5  push    r12
0x18000fee7  push    r13
0x18000fee9  push    r14
0x18000feeb  push    r15
0x18000feed  sub     rsp, 38h
0x18000fef1  mov     r14, cs:qword_1800242B8
0x18000fef8  xor     edx, edx
0x18000fefa  mov     r12d, r9d
0x18000fefd  mov     r13, r8
0x18000ff00  test    r14, r14
0x18000ff03  jz      short loc_18000FF13
0x18000ff05  mov     rbx, cs:qword_1800242C8
0x18000ff0c  mov     eax, edx
0x18000ff0e  test    rbx, rbx
0x18000ff11  jnz     short loc_18000FF2F
0x18000ff13  mov     edx, [rsp+78h+arg_20]; unsigned int
0x18000ff1a  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000ff1f  mov     rbx, cs:qword_1800242C8
0x18000ff26  xor     edx, edx
0x18000ff28  mov     r14, cs:qword_1800242B8
0x18000ff2f  test    r14, r14
0x18000ff32  jz      short loc_18000FFA9
0x18000ff34  test    rbx, rbx
0x18000ff37  jz      short loc_18000FF8C
0x18000ff39  cmp     r12d, 1
0x18000ff3d  jnz     short loc_18000FF8C
0x18000ff3f  mov     r15, [r13+0]
0x18000ff43  test    r15, r15
0x18000ff46  jnz     short loc_18000FF4C
0x18000ff48  mov     esi, edx
0x18000ff4a  jmp     short loc_18000FF5A
0x18000ff4c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ff50  inc     rsi
0x18000ff53  cmp     [r15+rsi*2], dx
0x18000ff58  jnz     short loc_18000FF50
0x18000ff5a  mov     ebp, cs:dword_1800242D0
0x18000ff60  jmp     short loc_18000FF87
0x18000ff62  mov     edi, ebp
0x18000ff64  add     rdi, rdi
0x18000ff67  cmp     esi, [rbx+rdi*8+8]
0x18000ff6b  jnz     short loc_18000FF87
0x18000ff6d  movsxd  r8, dword ptr [rbx+rdi*8+8]
0x18000ff72  mov     rdx, r15; Buf2
0x18000ff75  mov     rcx, [rbx+rdi*8]; Buf1
0x18000ff79  add     r8, r8; Size
0x18000ff7c  call    memcmp_0
0x18000ff81  xor     edx, edx
0x18000ff83  test    eax, eax
0x18000ff85  jz      short loc_18000FFBA
0x18000ff87  sub     ebp, 1
0x18000ff8a  jns     short loc_18000FF62
0x18000ff8c  mov     rax, [r14]
0x18000ff8f  mov     r8d, r12d
0x18000ff92  mov     r9, [rsp+78h+arg_28]
0x18000ff9a  mov     rdx, r13
0x18000ff9d  mov     rcx, r14
0x18000ffa0  mov     rax, [rax+50h]
0x18000ffa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa9  add     rsp, 38h
0x18000ffad  pop     r15
0x18000ffaf  pop     r14
0x18000ffb1  pop     r13
0x18000ffb3  pop     r12
0x18000ffb5  pop     rdi
0x18000ffb6  pop     rsi
0x18000ffb7  pop     rbp
0x18000ffb8  pop     rbx
0x18000ffb9  retn
0x18000ffba  mov     rax, [rsp+78h+arg_28]
0x18000ffc2  mov     ecx, [rbx+rdi*8+0Ch]
0x18000ffc6  mov     [rax], ecx
0x18000ffc8  mov     eax, edx
0x18000ffca  jmp     short loc_18000FFA9
```
