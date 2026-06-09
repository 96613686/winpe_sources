# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180024640`
- end: `0x18002480a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800202a0`

## callees

- `0x180024640`
- `0x180024870`
- `0x1800248e8`
- `0x18002656a`
- `0x1800265b0`
- `0x180026640`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  unsigned int v7; // r9d
  __int64 v8; // r8
  unsigned int v9; // r11d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // r10
  _DWORD *v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v15 = 4096;
      v16 = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (unsigned int)&v16,
                       (__int64)v17,
                       (__int64)&v15);
      if ( !WnfStateData )
      {
        v7 = v15;
        if ( v15 != 12 * (v15 / 0xCuLL) )
        {
          v7 = 0;
          v15 = 0;
        }
        v8 = *a1;
        v9 = v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( 1 )
        {
          v12 = v17;
          if ( v8 == v10 )
            break;
          v11 = &v17[3 * v9];
          while ( v12 != v11 )
          {
            if ( *v12 == *(_DWORD *)v8 && *((_WORD *)v12 + 2) == *(_WORD *)(v8 + 4) )
            {
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v15;
              goto LABEL_15;
            }
            v12 += 3;
          }
          if ( (unsigned __int64)v7 + 12 <= 0x1000 )
          {
            v7 += 12;
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (unsigned int)v17,
                    v7,
                    v7,
                    v14,
                    v16,
                    1);
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x180024640  push    rbp
0x180024642  push    rbx
0x180024643  push    rsi
0x180024644  push    rdi
0x180024645  push    r12
0x180024647  push    r14
0x180024649  lea     rbp, [rsp-0F68h]
0x180024651  mov     eax, 1068h
0x180024656  call    _alloca_probe
0x18002465b  sub     rsp, rax
0x18002465e  mov     rax, cs:__security_cookie
0x180024665  xor     rax, rsp
0x180024668  mov     [rbp+0F90h+var_40], rax
0x18002466f  mov     rax, [rcx+8]
0x180024673  xor     ebx, ebx
0x180024675  sub     rax, [rcx]
0x180024678  xor     edi, edi
0x18002467a  mov     r14, rcx
0x18002467d  cmp     rax, 0Ch
0x180024681  jb      loc_1800247E4
0x180024687  xor     esi, esi
0x180024689  mov     r12, 0AAAAAAAAAAAAAAABh
0x180024693  xor     edx, edx; Val
0x180024695  lea     rcx, [rsp+1090h+var_1040]; void *
0x18002469a  mov     r8d, 1000h; Size
0x1800246a0  call    memset_0
0x1800246a5  lea     rax, [rsp+1090h+var_1050]
0x1800246aa  mov     [rsp+1090h+var_1050], 1000h
0x1800246b2  mov     [rsp+1090h+var_1068], rax
0x1800246b7  lea     r9, [rsp+1090h+var_104C]
0x1800246bc  lea     rax, [rsp+1090h+var_1040]
0x1800246c1  mov     [rsp+1090h+var_104C], 0
0x1800246c9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800246d0  mov     [rsp+1090h+var_1070], rax
0x1800246d5  call    wil_details_NtQueryWnfStateData
0x1800246da  mov     ebx, eax
0x1800246dc  test    eax, eax
0x1800246de  jnz     loc_1800247CD
0x1800246e4  mov     r9d, [rsp+1090h+var_1050]
0x1800246e9  mov     rax, r12
0x1800246ec  mul     r9
0x1800246ef  shr     rdx, 3
0x1800246f3  lea     rcx, [rdx+rdx*2]
0x1800246f7  shl     rcx, 2
0x1800246fb  cmp     r9, rcx
0x1800246fe  jz      short loc_180024708
0x180024700  xor     r9d, r9d
0x180024703  mov     [rsp+1090h+var_1050], r9d
0x180024708  mov     r8, [r14]
0x18002470b  mov     rax, r12
0x18002470e  mov     ecx, r9d
0x180024711  mul     rcx
0x180024714  mov     rcx, [r14+8]
0x180024718  mov     rax, r12
0x18002471b  mov     r11, rdx
0x18002471e  sub     rcx, r8
0x180024721  mul     rcx
0x180024724  shr     r11, 3
0x180024728  shr     rdx, 3
0x18002472c  lea     rax, [rdx+rdx*2]
0x180024730  lea     rdi, [r8+rax*4]
0x180024734  jmp     short loc_1800247A2
0x180024736  mov     eax, r11d
0x180024739  lea     r10, [rsp+1090h+var_1040]
0x18002473e  lea     rcx, [rax+rax*2]
0x180024742  lea     r10, [r10+rcx*4]
0x180024746  cmp     rdx, r10
0x180024749  jz      short loc_180024771
0x18002474b  mov     eax, [r8]
0x18002474e  cmp     [rdx], eax
0x180024750  jnz     short loc_18002475D
0x180024752  movzx   eax, word ptr [r8+4]
0x180024757  cmp     [rdx+4], ax
0x18002475b  jz      short loc_180024763
0x18002475d  add     rdx, 0Ch
0x180024761  jmp     short loc_180024746
0x180024763  mov     eax, [r8+8]
0x180024767  add     [rdx+8], eax
0x18002476a  mov     r9d, [rsp+1090h+var_1050]
0x18002476f  jmp     short loc_18002479E
0x180024771  mov     eax, r9d
0x180024774  add     rax, 0Ch
0x180024778  cmp     rax, 1000h
0x18002477e  ja      short loc_18002479E
0x180024780  movsd   xmm0, qword ptr [r8]
0x180024785  add     r9d, 0Ch
0x180024789  movsd   qword ptr [r10], xmm0
0x18002478e  inc     r11d
0x180024791  mov     eax, [r8+8]
0x180024795  mov     [r10+8], eax
0x180024799  mov     [rsp+1090h+var_1050], r9d
0x18002479e  add     r8, 0Ch
0x1800247a2  lea     rdx, [rsp+1090h+var_1040]
0x1800247a7  cmp     r8, rdi
0x1800247aa  jnz     short loc_180024736
0x1800247ac  mov     eax, [rsp+1090h+var_104C]
0x1800247b0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800247b7  mov     [rsp+1090h+var_1060], 1
0x1800247bf  mov     r8d, r9d
0x1800247c2  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800247c6  call    wil_details_NtUpdateWnfStateData
0x1800247cb  mov     edi, eax
0x1800247cd  cmp     edi, 0C0000001h
0x1800247d3  jnz     short loc_1800247E4
0x1800247d5  inc     esi
0x1800247d7  cmp     esi, 64h ; 'd'
0x1800247da  jge     short loc_1800247E4
0x1800247dc  test    ebx, ebx
0x1800247de  jz      loc_180024693
0x1800247e4  test    ebx, ebx
0x1800247e6  cmovz   ebx, edi
0x1800247e9  mov     eax, ebx
0x1800247eb  mov     rcx, [rbp+0F90h+var_40]
0x1800247f2  xor     rcx, rsp; StackCookie
0x1800247f5  call    __security_check_cookie
0x1800247fa  add     rsp, 1068h
0x180024801  pop     r14
0x180024803  pop     r12
0x180024805  pop     rdi
0x180024806  pop     rsi
0x180024807  pop     rbx
0x180024808  pop     rbp
0x180024809  retn
```
