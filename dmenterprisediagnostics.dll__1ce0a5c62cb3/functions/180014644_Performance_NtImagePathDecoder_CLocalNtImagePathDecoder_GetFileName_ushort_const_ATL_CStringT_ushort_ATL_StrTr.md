# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180014644`
- end: `0x180014684`
- name: `?GetFileName@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800121e8`
- `0x180015d78`

## callees

- `0x180014644`
- `0x18001468c`
- `0x180014f08`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(
        Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *a1,
        __int64 a2,
        __int64 a3)
{
  if ( !*((_BYTE *)a1 + 112) )
    Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(a1);
  return Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName((__int64)a1, a2, a3);
}

```

## disassembly

```asm
0x180014644  mov     [rsp+arg_0], rbx
0x180014649  mov     [rsp+arg_8], rsi
0x18001464e  push    rdi
0x18001464f  sub     rsp, 20h
0x180014653  cmp     byte ptr [rcx+70h], 0
0x180014657  mov     rdi, r8
0x18001465a  mov     rsi, rdx
0x18001465d  mov     rbx, rcx
0x180014660  jnz     short loc_180014667
0x180014662  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x180014667  mov     r8, rdi
0x18001466a  mov     rdx, rsi
0x18001466d  mov     rcx, rbx
0x180014670  mov     rbx, [rsp+28h+arg_0]
0x180014675  mov     rsi, [rsp+28h+arg_8]
0x18001467a  add     rsp, 20h
0x18001467e  pop     rdi
0x18001467f  jmp     ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
```
