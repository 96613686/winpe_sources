# CModule::GetCoreExports(std::shared_lock<std::shared_mutex> &)

- ea: `0x180006110`
- end: `0x1800061d0`
- name: `?GetCoreExports@CModule@@QEAAAEBUDllExports2@D3D12Core@@AEAV?$shared_lock@Vshared_mutex@std@@@std@@@Z`
- size: `192`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180005d70`
- `0x180006060`
- `0x18000ac30`
- `0x18000e980`
- `0x18000f120`
- `0x18000f190`
- `0x18000f200`
- `0x18000f280`
- `0x18000f320`
- `0x18000f3c0`

## callees

- `0x180006110`
- `0x1800061d8`
- `0x18000afcc`
- `0x18000afdc`
- `0x18000afec`
- `0x18000affc`
- `0x180010590`

## pseudocode

```c
__int64 (__fastcall **__fastcall CModule::GetCoreExports(CModule *this, __int64 a2))()
{
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned int v7; // edi

  LOBYTE(v4) = 0;
  v5 = *((_QWORD *)this + 16);
  if ( !v5 )
  {
    do
    {
      if ( (_BYTE)v4 )
        return off_180016280;
      if ( !*(_QWORD *)a2
        || !*(_BYTE *)(a2 + 8)
        || (Smtx_unlock_shared(*(_Smtx_t **)a2),
            *(_BYTE *)(a2 + 8) = 0,
            Smtx_lock_exclusive(&qword_18001E7F8),
            v7 = CModule::EnsureRedistDllLoaded(this),
            Smtx_unlock_exclusive(&qword_18001E7F8),
            !*(_QWORD *)a2) )
      {
        std::_Throw_system_error(1);
      }
      if ( *(_BYTE *)(a2 + 8) )
        std::_Throw_system_error(36);
      v4 = v7 >> 31;
      Smtx_lock_shared(*(_Smtx_t **)a2);
      *(_BYTE *)(a2 + 8) = 1;
      v5 = *((_QWORD *)this + 16);
    }
    while ( !v5 );
    if ( (_BYTE)v4 )
      return off_180016280;
  }
  return (__int64 (__fastcall **)())(v5 + 32);
}

```

## disassembly

```asm
0x180006110  mov     [rsp+arg_0], rbx
0x180006115  mov     [rsp+arg_8], rsi
0x18000611a  push    rdi
0x18000611b  sub     rsp, 20h
0x18000611f  mov     rbx, rdx
0x180006122  mov     rsi, rcx
0x180006125  xor     dil, dil
0x180006128  mov     rax, [rcx+80h]
0x18000612f  test    rax, rax
0x180006132  jnz     short loc_1800061A6
0x180006134  test    dil, dil
0x180006137  jz      short loc_180006142
0x180006139  lea     rax, off_180016280
0x180006140  jmp     short loc_1800061AA
0x180006142  mov     rcx, [rbx]; _Smtx_t *
0x180006145  test    rcx, rcx
0x180006148  jz      short loc_1800061C5
0x18000614a  cmp     byte ptr [rbx+8], 0
0x18000614e  jz      short loc_1800061C5
0x180006150  call    _Smtx_unlock_shared
0x180006155  mov     byte ptr [rbx+8], 0
0x180006159  lea     rcx, qword_18001E7F8; _Smtx_t *
0x180006160  call    _Smtx_lock_exclusive
0x180006165  mov     rcx, rsi; this
0x180006168  call    ?EnsureRedistDllLoaded@CModule@@AEAAJXZ; CModule::EnsureRedistDllLoaded(void)
0x18000616d  mov     edi, eax
0x18000616f  lea     rcx, qword_18001E7F8; _Smtx_t *
0x180006176  call    _Smtx_unlock_exclusive
0x18000617b  mov     rcx, [rbx]; _Smtx_t *
0x18000617e  test    rcx, rcx
0x180006181  jz      short loc_1800061C5
0x180006183  cmp     byte ptr [rbx+8], 0
0x180006187  jnz     short loc_1800061BA
0x180006189  shr     edi, 1Fh
0x18000618c  call    _Smtx_lock_shared
0x180006191  mov     byte ptr [rbx+8], 1
0x180006195  mov     rax, [rsi+80h]
0x18000619c  test    rax, rax
0x18000619f  jz      short loc_180006134
0x1800061a1  test    dil, dil
0x1800061a4  jnz     short loc_180006139
0x1800061a6  add     rax, 20h ; ' '
0x1800061aa  mov     rbx, [rsp+28h+arg_0]
0x1800061af  mov     rsi, [rsp+28h+arg_8]
0x1800061b4  add     rsp, 20h
0x1800061b8  pop     rdi
0x1800061b9  retn
0x1800061ba  mov     ecx, 24h ; '$'
0x1800061bf  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800061c5  mov     ecx, 1
0x1800061ca  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
