# ESIMPM::_ESIM_POLICY_CONFIG::_ESIM_POLICY_CONFIG(ESIMPM::_ESIM_POLICY_CONFIG const &)

- ea: `0x140026c28`
- end: `0x140026d7d`
- name: `??0_ESIM_POLICY_CONFIG@ESIMPM@@QEAA@AEBU01@@Z`
- size: `341`
- prototype: `ESIMPM::_ESIM_POLICY_CONFIG *__fastcall(ESIMPM::_ESIM_POLICY_CONFIG *this, const struct ESIMPM::_ESIM_POLICY_CONFIG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140029f20`

## callees

- `0x140002f84`
- `0x14000dce0`
- `0x140014700`
- `0x140026c28`
- `0x14002a7c4`

## pseudocode

```c
ESIMPM::_ESIM_POLICY_CONFIG *__fastcall ESIMPM::_ESIM_POLICY_CONFIG::_ESIM_POLICY_CONFIG(
        ESIMPM::_ESIM_POLICY_CONFIG *this,
        const struct ESIMPM::_ESIM_POLICY_CONFIG *a2)
{
  __int64 *v4; // rsi
  unsigned __int64 v5; // rax
  __int64 v6; // rax
  unsigned __int64 v7; // rbx
  char *v8; // rax
  size_t v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rbp
  __int64 i; // rdi
  _OWORD *v13; // rdx

  *(_DWORD *)this = *(_DWORD *)a2;
  *((_DWORD *)this + 1) = *((_DWORD *)a2 + 1);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 3) = *((_DWORD *)a2 + 3);
  *((_DWORD *)this + 4) = *((_DWORD *)a2 + 4);
  *((_DWORD *)this + 5) = *((_DWORD *)a2 + 5);
  v4 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v5 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a2 + 4) - *((_QWORD *)a2 + 3)) >> 3);
  if ( v5 )
  {
    if ( v5 > 0x666666666666666LL )
      std::vector<ESIMPM::_ESIM_POLICY>::_Xlength();
    v6 = (__int64)(*((_QWORD *)a2 + 4) - *((_QWORD *)a2 + 3)) >> 3;
    v7 = 8 * v6;
    if ( 8 * v6 )
    {
      v9 = 8 * v6;
      if ( v7 < 0x1000 )
        v8 = (char *)operator new(v9);
      else
        v8 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v9);
    }
    else
    {
      v8 = 0;
    }
    *v4 = (__int64)v8;
    v4[1] = (__int64)v8;
    v4[2] = (__int64)&v8[v7];
    v10 = *v4;
    v11 = *((_QWORD *)a2 + 4);
    for ( i = *((_QWORD *)a2 + 3); i != v11; i += 40 )
    {
      *(_OWORD *)v10 = 0;
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 0;
      if ( *(_QWORD *)(i + 24) <= 7u )
        v13 = (_OWORD *)i;
      else
        v13 = *(_OWORD **)i;
      std::wstring::_Construct<2,unsigned short const *>(v10, v13, *(_QWORD *)(i + 16));
      *(_DWORD *)(v10 + 32) = *(_DWORD *)(i + 32);
      v10 += 40;
    }
    v4[1] = v10;
  }
  return this;
}

```

## disassembly

```asm
0x140026c28  mov     [rsp+arg_8], rbx
0x140026c2d  mov     [rsp+arg_10], rbp
0x140026c32  mov     [rsp+arg_0], rcx
0x140026c37  push    rsi
0x140026c38  push    rdi
0x140026c39  push    r14
0x140026c3b  sub     rsp, 40h
0x140026c3f  mov     rdi, rdx
0x140026c42  mov     r14, rcx
0x140026c45  mov     eax, [rdx]
0x140026c47  mov     [rcx], eax
0x140026c49  mov     eax, [rdx+4]
0x140026c4c  mov     [rcx+4], eax
0x140026c4f  mov     eax, [rdx+8]
0x140026c52  mov     [rcx+8], eax
0x140026c55  mov     eax, [rdx+0Ch]
0x140026c58  mov     [rcx+0Ch], eax
0x140026c5b  mov     eax, [rdx+10h]
0x140026c5e  mov     [rcx+10h], eax
0x140026c61  mov     eax, [rdx+14h]
0x140026c64  mov     [rcx+14h], eax
0x140026c67  lea     rsi, [rcx+18h]
0x140026c6b  mov     qword ptr [rsi], 0
0x140026c72  mov     qword ptr [rsi+8], 0
0x140026c7a  mov     qword ptr [rsi+10h], 0
0x140026c82  mov     rax, [rdx+20h]
0x140026c86  sub     rax, [rdx+18h]
0x140026c8a  sar     rax, 3
0x140026c8e  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x140026c98  imul    rax, rcx
0x140026c9c  test    rax, rax
0x140026c9f  jz      loc_140026D61
0x140026ca5  mov     rcx, 666666666666666h
0x140026caf  cmp     rax, rcx
0x140026cb2  ja      loc_140026D77
0x140026cb8  lea     rax, [rax+rax*4]
0x140026cbc  lea     rbx, ds:0[rax*8]
0x140026cc4  test    rbx, rbx
0x140026cc7  jnz     short loc_140026CCD
0x140026cc9  xor     eax, eax
0x140026ccb  jmp     short loc_140026CE5
0x140026ccd  mov     rcx, rbx; Size
0x140026cd0  cmp     rbx, 1000h
0x140026cd7  jb      short loc_140026CE0
0x140026cd9  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x140026cde  jmp     short loc_140026CE5
0x140026ce0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140026ce5  mov     [rsi], rax
0x140026ce8  mov     [rsi+8], rax
0x140026cec  add     rax, rbx
0x140026cef  mov     [rsi+10h], rax
0x140026cf3  mov     [rsp+58h+arg_0], rsi
0x140026cf8  mov     rbx, [rsi]
0x140026cfb  mov     rbp, [rdi+20h]
0x140026cff  mov     rdi, [rdi+18h]
0x140026d03  mov     [rsp+58h+var_38], rbx
0x140026d08  mov     [rsp+58h+var_30], rbx
0x140026d0d  mov     [rsp+58h+var_28], rsi
0x140026d12  jmp     short loc_140026D58
0x140026d14  xorps   xmm0, xmm0
0x140026d17  movups  xmmword ptr [rbx], xmm0
0x140026d1a  mov     qword ptr [rbx+10h], 0
0x140026d22  mov     qword ptr [rbx+18h], 0
0x140026d2a  cmp     qword ptr [rdi+18h], 7
0x140026d2f  jbe     short loc_140026D36
0x140026d31  mov     rdx, [rdi]
0x140026d34  jmp     short loc_140026D39
0x140026d36  mov     rdx, rdi
0x140026d39  mov     r8, [rdi+10h]
0x140026d3d  mov     rcx, rbx
0x140026d40  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140026d45  mov     eax, [rdi+20h]
0x140026d48  mov     [rbx+20h], eax
0x140026d4b  add     rbx, 28h ; '('
0x140026d4f  mov     [rsp+58h+var_30], rbx
0x140026d54  add     rdi, 28h ; '('
0x140026d58  cmp     rdi, rbp
0x140026d5b  jnz     short loc_140026D14
0x140026d5d  mov     [rsi+8], rbx
0x140026d61  mov     rax, r14
0x140026d64  mov     rbx, [rsp+58h+arg_8]
0x140026d69  mov     rbp, [rsp+58h+arg_10]
0x140026d6e  add     rsp, 40h
0x140026d72  pop     r14
0x140026d74  pop     rdi
0x140026d75  pop     rsi
0x140026d76  retn
0x140026d77  call    ?_Xlength@?$vector@U_ESIM_POLICY@ESIMPM@@V?$allocator@U_ESIM_POLICY@ESIMPM@@@std@@@std@@CAXXZ; std::vector<ESIMPM::_ESIM_POLICY>::_Xlength(void)
```
