# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180008ebc`
- end: `0x180009091`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e650`

## callees

- `0x180008ebc`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180009035`
- `ntdll!EtwEventWriteTransfer` at `0x180009035`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 **a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v13; // rcx
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rdx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rdx
  __int64 v21; // rax
  int v22; // eax
  __int64 *v23; // rdx
  int v24; // ecx
  unsigned int v26; // [rsp+30h] [rbp-99h]
  _DWORD v27[2]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v28; // [rsp+40h] [rbp-89h]
  _QWORD v29[5]; // [rsp+50h] [rbp-79h] BYREF
  int v30; // [rsp+78h] [rbp-51h]
  int v31; // [rsp+7Ch] [rbp-4Dh]
  __int64 *v32; // [rsp+80h] [rbp-49h]
  int v33; // [rsp+88h] [rbp-41h]
  int v34; // [rsp+8Ch] [rbp-3Dh]
  __int64 *v35; // [rsp+90h] [rbp-39h]
  int v36; // [rsp+98h] [rbp-31h]
  int v37; // [rsp+9Ch] [rbp-2Dh]
  __int64 *v38; // [rsp+A0h] [rbp-29h]
  int v39; // [rsp+A8h] [rbp-21h]
  int v40; // [rsp+ACh] [rbp-1Dh]
  __int64 v41; // [rsp+B0h] [rbp-19h]
  __int64 v42; // [rsp+B8h] [rbp-11h]
  __int64 v43; // [rsp+C0h] [rbp-9h]
  __int64 v44; // [rsp+C8h] [rbp-1h]

  v43 = a10;
  v41 = a9;
  v13 = -1;
  v44 = 4;
  v42 = 4;
  v14 = *a8;
  if ( *a8 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_180026E50;
    v16 = 2;
  }
  v39 = v16;
  v38 = v14;
  v40 = 0;
  v17 = *a7;
  if ( *a7 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v19 = 2 * v18 + 2;
  }
  else
  {
    v17 = &qword_180026E50;
    v19 = 2;
  }
  v36 = v19;
  v35 = v17;
  v37 = 0;
  v20 = *a6;
  if ( *a6 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    v22 = 2 * v21 + 2;
  }
  else
  {
    v20 = &qword_180026E50;
    v22 = 2;
  }
  v33 = v22;
  v32 = v20;
  v34 = 0;
  v23 = *a5;
  if ( *a5 )
  {
    do
      ++v13;
    while ( *((_WORD *)v23 + v13) );
    v24 = 2 * v13 + 2;
  }
  else
  {
    v23 = &qword_180026E50;
    v24 = 2;
  }
  v27[0] = *a2 << 24;
  v27[1] = *(unsigned __int16 *)(a2 + 1);
  v28 = *(_QWORD *)(a2 + 3);
  v29[0] = *(_QWORD *)(a1 + 8);
  v30 = v24;
  v29[4] = v23;
  v31 = 0;
  v29[1] = *(unsigned __int16 *)v29[0] | 0x200000000LL;
  v29[3] = *(unsigned __int16 *)(a2 + 11) | 0x100000000LL;
  v29[2] = a2 + 11;
  v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  return EtwEventWriteTransfer(*(_QWORD *)(a1 + 32), v27, a3, a4, 8, v29, v26);
}

```

## disassembly

```asm
0x180008ebc  push    rbp
0x180008ebe  push    rbx
0x180008ebf  push    rsi
0x180008ec0  lea     rbp, [rsp-17h]
0x180008ec5  sub     rsp, 0E0h
0x180008ecc  mov     rax, cs:__security_cookie
0x180008ed3  xor     rax, rsp
0x180008ed6  mov     [rbp+27h+var_20], rax
0x180008eda  mov     rax, [rbp+27h+arg_48]
0x180008ede  xor     ebx, ebx
0x180008ee0  mov     [rbp+27h+var_30], rax
0x180008ee4  mov     r11, r8
0x180008ee7  mov     rax, [rbp+27h+arg_40]
0x180008eeb  mov     r8, rdx
0x180008eee  mov     [rbp+27h+var_40], rax
0x180008ef2  mov     r10, rcx
0x180008ef5  mov     rax, [rbp+27h+arg_38]
0x180008ef9  lea     esi, [rbx+2]
0x180008efc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008f00  mov     [rbp+27h+var_28], 4
0x180008f08  mov     [rbp+27h+var_38], 4
0x180008f10  mov     rdx, [rax]
0x180008f13  test    rdx, rdx
0x180008f16  jz      loc_180009059
0x180008f1c  mov     rax, rcx
0x180008f1f  inc     rax
0x180008f22  cmp     [rdx+rax*2], bx
0x180008f26  jnz     short loc_180008F1F
0x180008f28  lea     eax, ds:2[rax*2]
0x180008f2f  mov     [rbp+27h+var_48], eax
0x180008f32  mov     rax, [rbp+27h+arg_30]
0x180008f36  mov     [rbp+27h+var_50], rdx
0x180008f3a  mov     [rbp+27h+var_44], ebx
0x180008f3d  mov     rdx, [rax]
0x180008f40  test    rdx, rdx
0x180008f43  jz      loc_180009067
0x180008f49  mov     rax, rcx
0x180008f4c  inc     rax
0x180008f4f  cmp     [rdx+rax*2], bx
0x180008f53  jnz     short loc_180008F4C
0x180008f55  lea     eax, ds:2[rax*2]
0x180008f5c  mov     [rbp+27h+var_58], eax
0x180008f5f  mov     rax, [rbp+27h+arg_28]
0x180008f63  mov     [rbp+27h+var_60], rdx
0x180008f67  mov     [rbp+27h+var_54], ebx
0x180008f6a  mov     rdx, [rax]
0x180008f6d  test    rdx, rdx
0x180008f70  jz      loc_180009075
0x180008f76  mov     rax, rcx
0x180008f79  inc     rax
0x180008f7c  cmp     [rdx+rax*2], bx
0x180008f80  jnz     short loc_180008F79
0x180008f82  lea     eax, ds:2[rax*2]
0x180008f89  mov     [rbp+27h+var_68], eax
0x180008f8c  mov     rax, [rbp+27h+arg_20]
0x180008f90  mov     [rbp+27h+var_70], rdx
0x180008f94  mov     [rbp+27h+var_64], ebx
0x180008f97  mov     rdx, [rax]
0x180008f9a  test    rdx, rdx
0x180008f9d  jz      loc_180009083
0x180008fa3  inc     rcx
0x180008fa6  cmp     [rdx+rcx*2], bx
0x180008faa  jnz     short loc_180008FA3
0x180008fac  lea     ecx, ds:2[rcx*2]
0x180008fb3  movzx   eax, byte ptr [r8]
0x180008fb7  shl     eax, 18h
0x180008fba  mov     [rsp+0F0h+var_B8], eax
0x180008fbe  movzx   eax, word ptr [r8+1]
0x180008fc3  mov     [rsp+0F0h+var_B4], eax
0x180008fc7  mov     rax, [r8+3]
0x180008fcb  mov     [rsp+0F0h+var_B0], rax
0x180008fd0  mov     rax, [r10+8]
0x180008fd4  mov     [rbp+27h+var_A0], rax
0x180008fd8  mov     [rbp+27h+var_78], ecx
0x180008fdb  lea     rcx, [r8+0Bh]
0x180008fdf  mov     [rbp+27h+var_80], rdx
0x180008fe3  mov     r8, r11
0x180008fe6  mov     [rbp+27h+var_74], ebx
0x180008fe9  lea     rdx, [rsp+0F0h+var_B8]
0x180008fee  movzx   eax, word ptr [rax]
0x180008ff1  mov     dword ptr [rbp+27h+var_98], eax
0x180008ff4  movzx   eax, word ptr [rcx]
0x180008ff7  mov     dword ptr [rbp+27h+var_88], eax
0x180008ffa  lea     rax, _TraceLoggingMetadataEnd
0x180009001  mov     [rbp+27h+var_90], rcx
0x180009005  lea     rcx, _TraceLoggingMetadata
0x18000900c  sub     eax, ecx
0x18000900e  mov     dword ptr [rbp+27h+var_98+4], esi
0x180009011  mov     dword ptr [rbp+27h+var_88+4], 1
0x180009018  mov     [rsp+0F0h+var_C0], eax
0x18000901c  mov     eax, [rsp+0F0h+var_C0]
0x180009020  mov     rcx, [r10+20h]
0x180009024  lea     rax, [rbp+27h+var_A0]
0x180009028  mov     [rsp+0F0h+var_C8], rax
0x18000902d  mov     [rsp+0F0h+var_D0], 8
0x180009035  call    cs:__imp_EtwEventWriteTransfer
0x18000903c  nop     dword ptr [rax+rax+00h]
0x180009041  mov     rcx, [rbp+27h+var_20]
0x180009045  xor     rcx, rsp; StackCookie
0x180009048  call    __security_check_cookie
0x18000904d  add     rsp, 0E0h
0x180009054  pop     rsi
0x180009055  pop     rbx
0x180009056  pop     rbp
0x180009057  retn
0x180009059  lea     rdx, qword_180026E50
0x180009060  mov     eax, esi
0x180009062  jmp     loc_180008F2F
0x180009067  lea     rdx, qword_180026E50
0x18000906e  mov     eax, esi
0x180009070  jmp     loc_180008F5C
0x180009075  lea     rdx, qword_180026E50
0x18000907c  mov     eax, esi
0x18000907e  jmp     loc_180008F89
0x180009083  lea     rdx, qword_180026E50
0x18000908a  mov     ecx, esi
0x18000908c  jmp     loc_180008FB3
```
