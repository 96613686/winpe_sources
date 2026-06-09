# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180020b50`
- end: `0x180020c2e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020c40`

## callees

- `0x180020b50`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 == -871399154
      && a2[1] == *(_DWORD *)&GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data2
      && a2[2] == *(_DWORD *)GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data4
      && a2[3] == *(_DWORD *)&GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data4[4] )
    {
      *a3 = a1;
LABEL_22:
      a1 = *a3;
      goto LABEL_6;
    }
LABEL_12:
    v4 = a1 + 8;
    if ( *a2 == -1796592748 )
    {
      if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
        || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
    }
    else
    {
      if ( *a2 != 3
        || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
        || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
      {
        return (unsigned int)-2147467262;
      }
      v5 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
    }
    if ( a2[3] == v5 )
    {
      *a3 = v4;
      goto LABEL_22;
    }
    return (unsigned int)-2147467262;
  }
  if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_12;
  }
  *a3 = a1;
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180020b50  push    rbx
0x180020b52  sub     rsp, 20h
0x180020b56  xor     ebx, ebx
0x180020b58  mov     [r8], rbx
0x180020b5b  cmp     [rdx], ebx
0x180020b5d  jnz     short loc_180020B94
0x180020b5f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180020b65  cmp     [rdx+4], eax
0x180020b68  jnz     short loc_180020BC2
0x180020b6a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180020b70  cmp     [rdx+8], eax
0x180020b73  jnz     short loc_180020BC2
0x180020b75  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180020b7b  cmp     [rdx+0Ch], eax
0x180020b7e  jnz     short loc_180020BC2
0x180020b80  mov     [r8], rcx
0x180020b83  mov     rax, [rcx]
0x180020b86  mov     rax, [rax+8]
0x180020b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b8f  jmp     loc_180020C25
0x180020b94  cmp     dword ptr [rdx], 0CC0F810Eh
0x180020b9a  jnz     short loc_180020BC2
0x180020b9c  mov     eax, dword ptr cs:_GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data2
0x180020ba2  cmp     [rdx+4], eax
0x180020ba5  jnz     short loc_180020BC2
0x180020ba7  mov     eax, dword ptr cs:_GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data4
0x180020bad  cmp     [rdx+8], eax
0x180020bb0  jnz     short loc_180020BC2
0x180020bb2  mov     eax, dword ptr cs:_GUID_cc0f810e_2b3e_537f_ba50_d5f55668c637.Data4+4
0x180020bb8  cmp     [rdx+0Ch], eax
0x180020bbb  jnz     short loc_180020BC2
0x180020bbd  mov     [r8], rcx
0x180020bc0  jmp     short loc_180020C18
0x180020bc2  add     rcx, 8
0x180020bc6  cmp     dword ptr [rdx], 94EA2B94h
0x180020bcc  jnz     short loc_180020BEC
0x180020bce  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x180020bd4  cmp     [rdx+4], eax
0x180020bd7  jnz     short loc_180020C20
0x180020bd9  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x180020bdf  cmp     [rdx+8], eax
0x180020be2  jnz     short loc_180020C20
0x180020be4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x180020bea  jmp     short loc_180020C0D
0x180020bec  cmp     dword ptr [rdx], 3
0x180020bef  jnz     short loc_180020C20
0x180020bf1  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x180020bf7  cmp     [rdx+4], eax
0x180020bfa  jnz     short loc_180020C20
0x180020bfc  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x180020c02  cmp     [rdx+8], eax
0x180020c05  jnz     short loc_180020C20
0x180020c07  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x180020c0d  cmp     [rdx+0Ch], eax
0x180020c10  jnz     short loc_180020C20
0x180020c12  mov     rax, r8
0x180020c15  mov     [rax], rcx
0x180020c18  mov     rcx, [r8]
0x180020c1b  jmp     loc_180020B83
0x180020c20  mov     ebx, 80004002h
0x180020c25  mov     eax, ebx
0x180020c27  add     rsp, 20h
0x180020c2b  pop     rbx
0x180020c2c  retn
```
