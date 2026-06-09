# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b940`
- end: `0x18000b9b4`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEmptyVolumeCache@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b940`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != -1882303961
      || a2[1] != *(_DWORD *)&GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data2
      || a2[2] != *(_DWORD *)GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x18000b940  push    rbx
0x18000b942  sub     rsp, 20h
0x18000b946  xor     ebx, ebx
0x18000b948  mov     [r8], rbx
0x18000b94b  cmp     [rdx], ebx
0x18000b94d  jnz     short loc_18000B981
0x18000b94f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000b955  cmp     [rdx+4], eax
0x18000b958  jnz     short loc_18000B9A7
0x18000b95a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000b960  cmp     [rdx+8], eax
0x18000b963  jnz     short loc_18000B9A7
0x18000b965  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000b96b  cmp     [rdx+0Ch], eax
0x18000b96e  jnz     short loc_18000B9A7
0x18000b970  mov     [r8], rcx
0x18000b973  mov     rax, [rcx]
0x18000b976  mov     rax, [rax+8]
0x18000b97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97f  jmp     short loc_18000B9AC
0x18000b981  cmp     dword ptr [rdx], 8FCE5227h
0x18000b987  jnz     short loc_18000B9A7
0x18000b989  mov     eax, dword ptr cs:_GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data2
0x18000b98f  cmp     [rdx+4], eax
0x18000b992  jnz     short loc_18000B9A7
0x18000b994  mov     eax, dword ptr cs:_GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data4
0x18000b99a  cmp     [rdx+8], eax
0x18000b99d  jnz     short loc_18000B9A7
0x18000b99f  mov     eax, dword ptr cs:_GUID_8fce5227_04da_11d1_a004_00805f8abe06.Data4+4
0x18000b9a5  jmp     short loc_18000B96B
0x18000b9a7  mov     ebx, 80004002h
0x18000b9ac  mov     eax, ebx
0x18000b9ae  add     rsp, 20h
0x18000b9b2  pop     rbx
0x18000b9b3  retn
```
