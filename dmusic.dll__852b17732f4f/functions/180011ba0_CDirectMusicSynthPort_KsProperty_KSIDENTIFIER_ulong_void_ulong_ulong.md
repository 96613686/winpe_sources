# CDirectMusicSynthPort::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180011ba0`
- end: `0x180011cf9`
- name: `?KsProperty@CDirectMusicSynthPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `345`
- prototype: `__int64 __fastcall(CDirectMusicSynthPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800168a0`

## callees

- `0x180011ba0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort::KsProperty(
        CDirectMusicSynthPort *this,
        struct KSIDENTIFIER *a2,
        __int64 a3,
        int *a4,
        unsigned int a5,
        unsigned int *a6)
{
  int *v6; // rdi
  unsigned int v7; // r15d
  unsigned int v10; // esi
  ULONG v11; // edx
  unsigned int *v12; // r14
  __int64 result; // rax
  int v14; // eax
  int v15; // ecx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+90h] [rbp+18h] BYREF

  v18 = 0;
  v6 = a4;
  v7 = a3;
  if ( (_DWORD)a3 && !a2 )
    return 2147500035LL;
  v10 = a5;
  v11 = a2->Flags & 2;
  if ( v11 )
  {
    if ( a5 && !a4 )
      return 2147500035LL;
  }
  v12 = a6;
  if ( !a6 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 2) )
    return 2289570100LL;
  if ( a2->Alignment == *(_QWORD *)&GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
    && *(&a2->Alignment + 1) == *(_QWORD *)GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data4 )
  {
    if ( !a2->Id )
    {
      if ( a5 != 4 )
        return 2147942487LL;
      if ( v11 )
      {
        v14 = *a4;
        v15 = -20000;
        v18 = v14;
        if ( v14 < -20000 || (v15 = 2000, v14 > 2000) )
        {
          v18 = v15;
          v6 = &v18;
        }
      }
      goto LABEL_19;
    }
    return 2289570082LL;
  }
  if ( a2->Alignment == *(_QWORD *)&GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data1
    && *(&a2->Alignment + 1) == *(_QWORD *)GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data4 )
  {
    return 2289570082LL;
  }
LABEL_19:
  v16 = *((_QWORD *)this + 4);
  result = 2289570082LL;
  if ( !v16
    || (result = (*(__int64 (__fastcall **)(__int64, struct KSIDENTIFIER *, __int64, int *, unsigned int, unsigned int *))(*(_QWORD *)v16 + 24LL))(
                   v16,
                   a2,
                   a3,
                   v6,
                   a5,
                   a6),
        (_DWORD)result == -2005397214) )
  {
    v17 = *((_QWORD *)this + 5);
    if ( v17 )
      return (*(__int64 (__fastcall **)(__int64, struct KSIDENTIFIER *, _QWORD, int *, unsigned int, unsigned int *))(*(_QWORD *)v17 + 24LL))(
               v17,
               a2,
               v7,
               v6,
               v10,
               v12);
  }
  return result;
}

```

## disassembly

```asm
0x180011ba0  mov     rax, rsp
0x180011ba3  push    rbx
0x180011ba4  push    rbp
0x180011ba5  push    rsi
0x180011ba6  push    rdi
0x180011ba7  push    r14
0x180011ba9  push    r15
0x180011bab  sub     rsp, 48h
0x180011baf  mov     dword ptr [rax+18h], 0
0x180011bb6  mov     rdi, r9
0x180011bb9  mov     r15d, r8d
0x180011bbc  mov     rbx, rdx
0x180011bbf  mov     rbp, rcx
0x180011bc2  test    r8d, r8d
0x180011bc5  jz      short loc_180011BCC
0x180011bc7  test    rdx, rdx
0x180011bca  jz      short loc_180011BF1
0x180011bcc  mov     edx, [rdx+14h]
0x180011bcf  mov     esi, [rsp+78h+arg_20]
0x180011bd6  and     edx, 2
0x180011bd9  jz      short loc_180011BE4
0x180011bdb  test    esi, esi
0x180011bdd  jz      short loc_180011BE4
0x180011bdf  test    r9, r9
0x180011be2  jz      short loc_180011BF1
0x180011be4  mov     r14, [rsp+78h+arg_28]
0x180011bec  test    r14, r14
0x180011bef  jnz     short loc_180011BFB
0x180011bf1  mov     eax, 80004003h
0x180011bf6  jmp     loc_180011CCC
0x180011bfb  cmp     qword ptr [rcx+10h], 0
0x180011c00  jnz     short loc_180011C0C
0x180011c02  mov     eax, 88781134h
0x180011c07  jmp     loc_180011CCC
0x180011c0c  mov     rax, [rbx]
0x180011c0f  cmp     rax, qword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
0x180011c16  jnz     loc_180011CD9
0x180011c1c  mov     rax, [rbx+8]
0x180011c20  cmp     rax, qword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data4
0x180011c27  jnz     loc_180011CD9
0x180011c2d  cmp     dword ptr [rbx+10h], 0
0x180011c31  jnz     loc_180011CF2
0x180011c37  cmp     esi, 4
0x180011c3a  jz      short loc_180011C46
0x180011c3c  mov     eax, 80070057h
0x180011c41  jmp     loc_180011CCC
0x180011c46  test    edx, edx
0x180011c48  jz      short loc_180011C75
0x180011c4a  mov     eax, [r9]
0x180011c4d  mov     ecx, 0FFFFB1E0h
0x180011c52  mov     [rsp+78h+arg_10], eax
0x180011c59  cmp     eax, ecx
0x180011c5b  jl      short loc_180011C66
0x180011c5d  mov     ecx, 7D0h
0x180011c62  cmp     eax, ecx
0x180011c64  jle     short loc_180011C75
0x180011c66  mov     [rsp+78h+arg_10], ecx
0x180011c6d  lea     rdi, [rsp+78h+arg_10]
0x180011c75  mov     rcx, [rbp+20h]
0x180011c79  mov     eax, 88781122h
0x180011c7e  test    rcx, rcx
0x180011c81  jz      short loc_180011CA5
0x180011c83  mov     rax, [rcx]
0x180011c86  mov     r9, rdi
0x180011c89  mov     [rsp+78h+var_50], r14
0x180011c8e  mov     rdx, rbx
0x180011c91  mov     [rsp+78h+var_58], esi
0x180011c95  mov     rax, [rax+18h]
0x180011c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c9e  cmp     eax, 88781122h
0x180011ca3  jnz     short loc_180011CCC
0x180011ca5  mov     rcx, [rbp+28h]
0x180011ca9  test    rcx, rcx
0x180011cac  jz      short loc_180011CCC
0x180011cae  mov     rax, [rcx]
0x180011cb1  mov     r9, rdi
0x180011cb4  mov     [rsp+78h+var_50], r14
0x180011cb9  mov     r8d, r15d
0x180011cbc  mov     rdx, rbx
0x180011cbf  mov     [rsp+78h+var_58], esi
0x180011cc3  mov     rax, [rax+18h]
0x180011cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ccc  add     rsp, 48h
0x180011cd0  pop     r15
0x180011cd2  pop     r14
0x180011cd4  pop     rdi
0x180011cd5  pop     rsi
0x180011cd6  pop     rbp
0x180011cd7  pop     rbx
0x180011cd8  retn
0x180011cd9  mov     rax, [rbx]
0x180011cdc  cmp     rax, qword ptr cs:_GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data1
0x180011ce3  jnz     short loc_180011C75
0x180011ce5  mov     rax, [rbx+8]
0x180011ce9  cmp     rax, qword ptr cs:_GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data4
0x180011cf0  jnz     short loc_180011C75
0x180011cf2  mov     eax, 88781122h
0x180011cf7  jmp     short loc_180011CCC
```
