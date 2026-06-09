# subtract_timestamp_interval

- ea: `0x180017650`
- end: `0x18001779c`
- name: `subtract_timestamp_interval`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017418`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x1800103c8`
- `0x180012820`
- `0x180017650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800176d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800176d5`

## string_xrefs

- `0x1800176c9`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall subtract_timestamp_interval(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  unsigned int *v6; // r9
  __int64 v7; // rdx
  HMODULE ModuleHandleA; // rax
  __int64 v9; // rcx
  __int64 v10; // xmm0_8
  int v11; // eax
  __int128 v13; // [rsp+30h] [rbp-18h] BYREF

  v5 = Timestamp_ToMicroseconds(*(_QWORD *)(a2 + 8) + 20LL);
  v6 = *(unsigned int **)(a3 + 8);
  v7 = v6[9] + 1000000 * (v6[8] + 60 * (v6[7] + 60 * (v6[6] + 24LL * v6[5])));
  if ( v5 == 0x46120BA57B2FFFFLL )
  {
    if ( v7 == 8639999999999000000LL )
    {
      v13 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v13 = Intlstr_GetString_LoadString(ModuleHandleA, 2051);
      BYTE8(v13) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      goto LABEL_8;
    }
    v7 = 0;
  }
  else if ( v7 == 8639999999999000000LL )
  {
    v7 = v5 + 0xA0EDC6DC1LL;
  }
  v9 = MintValue_CreateTimestampFromMicroseconds(&v13, v5 - v7);
  if ( *(_BYTE *)v9 != 0xFE )
  {
    v10 = *(_QWORD *)(v9 + 1);
    *(_BYTE *)a1 = *(_BYTE *)v9;
    v11 = *(_DWORD *)(v9 + 9);
    *(_QWORD *)(a1 + 1) = v10;
    *(_DWORD *)(a1 + 9) = v11;
    *(_WORD *)(a1 + 13) = *(_WORD *)(v9 + 13);
    *(_BYTE *)(a1 + 15) = *(_BYTE *)(v9 + 15);
    return a1;
  }
LABEL_8:
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x180017650  mov     [rsp+arg_0], rbx
0x180017655  push    rdi
0x180017656  sub     rsp, 40h
0x18001765a  mov     rdi, rcx
0x18001765d  mov     rbx, r8
0x180017660  mov     rcx, [rdx+8]
0x180017664  add     rcx, 14h
0x180017668  call    Timestamp_ToMicroseconds
0x18001766d  mov     r9, [rbx+8]
0x180017671  mov     r10, rax
0x180017674  mov     eax, [r9+14h]
0x180017678  mov     r8d, [r9+18h]
0x18001767c  lea     rdx, [rax+rax*2]
0x180017680  lea     rax, [r8+rdx*8]
0x180017684  imul    rdx, rax, 3Ch ; '<'
0x180017688  mov     eax, [r9+1Ch]
0x18001768c  add     rdx, rax
0x18001768f  mov     eax, [r9+20h]
0x180017693  imul    rcx, rdx, 3Ch ; '<'
0x180017697  add     rcx, rax
0x18001769a  mov     eax, [r9+24h]
0x18001769e  imul    rdx, rcx, 0F4240h
0x1800176a5  add     rdx, rax
0x1800176a8  mov     rax, 46120BA57B2FFFFh
0x1800176b2  cmp     r10, rax
0x1800176b5  mov     rax, 77E772392B50BDC0h
0x1800176bf  jnz     short loc_180017727
0x1800176c1  cmp     rdx, rax
0x1800176c4  jnz     short loc_180017723
0x1800176c6  xorps   xmm0, xmm0
0x1800176c9  lea     rcx, ModuleName; "mpunits.dll"
0x1800176d0  movups  [rsp+48h+var_18], xmm0
0x1800176d5  call    cs:__imp_GetModuleHandleA
0x1800176db  mov     rcx, rax
0x1800176de  mov     edx, 803h
0x1800176e3  call    _Intlstr_GetString_LoadString
0x1800176e8  xor     edx, edx
0x1800176ea  mov     qword ptr [rsp+48h+var_18], rax
0x1800176ef  mov     byte ptr [rsp+48h+var_18+8], dl
0x1800176f3  lea     r9, [rsp+48h+var_18]
0x1800176f8  movaps  xmm0, [rsp+48h+var_18]
0x1800176fd  mov     [rsp+48h+var_20], rdx; __int64
0x180017702  lea     r8d, [rdx+5]
0x180017706  mov     [rsp+48h+var_28], rdx; __int64
0x18001770b  lea     ecx, [r8-1]; int
0x18001770f  movdqa  [rsp+48h+var_18], xmm0
0x180017715  lea     rdx, aMi; "MI"
0x18001771c  call    MI_ReportErrorDetails_ForCustomError
0x180017721  jmp     short loc_180017752
0x180017723  xor     edx, edx
0x180017725  jmp     short loc_180017739
0x180017727  cmp     rdx, rax
0x18001772a  jnz     short loc_180017739
0x18001772c  mov     rdx, 0A0EDC6DC1h
0x180017736  add     rdx, r10
0x180017739  sub     r10, rdx
0x18001773c  lea     rcx, [rsp+48h+var_18]
0x180017741  mov     rdx, r10
0x180017744  call    MintValue_CreateTimestampFromMicroseconds
0x180017749  mov     rcx, rax
0x18001774c  mov     al, [rax]
0x18001774e  cmp     al, 0FEh
0x180017750  jnz     short loc_18001776E
0x180017752  xor     edx, edx
0x180017754  xor     ecx, ecx
0x180017756  mov     eax, 0FFh
0x18001775b  mov     [rdi+4], edx
0x18001775e  and     eax, 0FFFFFFFEh
0x180017761  mov     [rdi+8], rcx
0x180017765  or      eax, 0FEh
0x18001776a  mov     [rdi], eax
0x18001776c  jmp     short loc_18001778E
0x18001776e  movsd   xmm0, qword ptr [rcx+1]
0x180017773  mov     [rdi], al
0x180017775  mov     eax, [rcx+9]
0x180017778  movsd   qword ptr [rdi+1], xmm0
0x18001777d  mov     [rdi+9], eax
0x180017780  movzx   eax, word ptr [rcx+0Dh]
0x180017784  mov     [rdi+0Dh], ax
0x180017788  mov     al, [rcx+0Fh]
0x18001778b  mov     [rdi+0Fh], al
0x18001778e  mov     rbx, [rsp+48h+arg_0]
0x180017793  mov     rax, rdi
0x180017796  add     rsp, 40h
0x18001779a  pop     rdi
0x18001779b  retn
```
