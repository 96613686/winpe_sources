# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001d430`
- end: `0x18001d4bf`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d360`
- `0x18001d4d0`
- `0x18001d4e0`
- `0x18001d4f0`
- `0x18001d500`

## callees

- `0x180018c00`
- `0x18001d430`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  int v3; // eax
  int CanCastTo; // ebx
  _QWORD *v5; // r8

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != -1350114592
      || a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v3 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
LABEL_11:
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::CanCastTo(
                a1,
                a2,
                a3);
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x18001d430  push    rbx
0x18001d432  sub     rsp, 20h
0x18001d436  mov     qword ptr [r8], 0
0x18001d43d  cmp     dword ptr [rdx], 0
0x18001d440  jnz     short loc_18001D460
0x18001d442  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18001d448  cmp     [rdx+4], eax
0x18001d44b  jnz     short loc_18001D49C
0x18001d44d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18001d453  cmp     [rdx+8], eax
0x18001d456  jnz     short loc_18001D49C
0x18001d458  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001d45e  jmp     short loc_18001D484
0x18001d460  cmp     dword ptr [rdx], 0AF86E2E0h
0x18001d466  jnz     short loc_18001D49C
0x18001d468  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18001d46e  cmp     [rdx+4], eax
0x18001d471  jnz     short loc_18001D49C
0x18001d473  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18001d479  cmp     [rdx+8], eax
0x18001d47c  jnz     short loc_18001D49C
0x18001d47e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18001d484  cmp     [rdx+0Ch], eax
0x18001d487  jnz     short loc_18001D49C
0x18001d489  mov     [r8], rcx
0x18001d48c  mov     rax, [rcx]
0x18001d48f  mov     rax, [rax+8]
0x18001d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d498  xor     ebx, ebx
0x18001d49a  jmp     short loc_18001D4B7
0x18001d49c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x18001d4a1  mov     ebx, eax
0x18001d4a3  test    eax, eax
0x18001d4a5  js      short loc_18001D4B7
0x18001d4a7  mov     rcx, [r8]
0x18001d4aa  mov     rdx, [rcx]
0x18001d4ad  mov     rax, [rdx+8]
0x18001d4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b6  nop
0x18001d4b7  mov     eax, ebx
0x18001d4b9  add     rsp, 20h
0x18001d4bd  pop     rbx
0x18001d4be  retn
```
