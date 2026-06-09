# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180010b20`
- end: `0x180010d03`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000e0b0`

## callees

- `0x18000d0a0`
- `0x18000ddc4`
- `0x18000e3f8`
- `0x180010b20`
- `0x180010efc`
- `0x180010f74`
- `0x180016700`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(_QWORD *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  unsigned int v8; // r11d
  __int64 i; // r10
  __int64 v10; // r8
  __int64 v11; // r10
  __int64 j; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[512]; // [rsp+70h] [rbp-90h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( a1[1] - *a1 >= 0xCu )
  {
    v4 = 0;
    do
    {
      memset_0(v20, 0, sizeof(v20));
      v16 = 4096;
      v17 = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (unsigned int)&v17,
                       (__int64)v20,
                       (__int64)&v16);
      if ( !WnfStateData )
      {
        if ( v16 != 12 * (v16 / 0xCuLL) )
          v16 = 0;
        wil::make_range<wil_details_FeatureUsageSRUM *>(v18, *a1, (a1[1] - *a1) / 0xCuLL);
        for ( i = v18[0]; i != v18[1]; i = v11 + 12 )
        {
          wil::make_range<wil_details_FeatureUsageSRUM *>(v19, v20, v8);
          for ( j = v19[0]; j != v19[1]; j += 12 )
          {
            if ( *(_DWORD *)j == *(_DWORD *)v11 && *(_WORD *)(j + 4) == *(_WORD *)(v11 + 4) )
            {
              *(_DWORD *)(j + 8) += *(_DWORD *)(v11 + 8);
              v7 = v16;
              goto LABEL_15;
            }
          }
          if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
          {
            v13 = 3 * v10;
            *(_QWORD *)((char *)v20 + 4 * v13) = *(_QWORD *)v11;
            v7 = (unsigned int)(v7 + 12);
            ++v8;
            *((_DWORD *)&v20[1] + v13) = *(_DWORD *)(v11 + 8);
            v16 = v7;
          }
LABEL_15:
          ;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v20,
                    v7,
                    v7,
                    v15,
                    v17,
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
0x180010b20  push    rbp
0x180010b22  push    rbx
0x180010b23  push    rsi
0x180010b24  push    rdi
0x180010b25  push    r12
0x180010b27  push    r14
0x180010b29  lea     rbp, [rsp-0F88h]
0x180010b31  mov     eax, 1088h
0x180010b36  call    _alloca_probe
0x180010b3b  sub     rsp, rax
0x180010b3e  mov     rax, cs:__security_cookie
0x180010b45  xor     rax, rsp
0x180010b48  mov     [rbp+0FB0h+var_40], rax
0x180010b4f  mov     rax, [rcx+8]
0x180010b53  xor     ebx, ebx
0x180010b55  sub     rax, [rcx]
0x180010b58  xor     edi, edi
0x180010b5a  mov     r14, rcx
0x180010b5d  cmp     rax, 0Ch
0x180010b61  jb      loc_180010CDD
0x180010b67  xor     esi, esi
0x180010b69  mov     r12, 0AAAAAAAAAAAAAAABh
0x180010b73  xor     edx, edx; Val
0x180010b75  lea     rcx, [rsp+10B0h+var_1040]; void *
0x180010b7a  mov     r8d, 1000h; Size
0x180010b80  call    memset_0
0x180010b85  lea     rax, [rsp+10B0h+var_1070]
0x180010b8a  mov     [rsp+10B0h+var_1070], 1000h
0x180010b92  mov     [rsp+10B0h+var_1088], rax
0x180010b97  lea     r9, [rsp+10B0h+var_106C]
0x180010b9c  lea     rax, [rsp+10B0h+var_1040]
0x180010ba1  mov     [rsp+10B0h+var_106C], 0
0x180010ba9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010bb0  mov     [rsp+10B0h+var_1090], rax
0x180010bb5  call    wil_details_NtQueryWnfStateData
0x180010bba  mov     ebx, eax
0x180010bbc  test    eax, eax
0x180010bbe  jnz     loc_180010CC6
0x180010bc4  mov     r9d, [rsp+10B0h+var_1070]
0x180010bc9  mov     rax, r12
0x180010bcc  mul     r9
0x180010bcf  shr     rdx, 3
0x180010bd3  lea     rcx, [rdx+rdx*2]
0x180010bd7  shl     rcx, 2
0x180010bdb  cmp     r9, rcx
0x180010bde  jz      short loc_180010BE8
0x180010be0  xor     r9d, r9d
0x180010be3  mov     [rsp+10B0h+var_1070], r9d
0x180010be8  mov     ecx, r9d
0x180010beb  mov     rax, r12
0x180010bee  mul     rcx
0x180010bf1  mov     rcx, [r14+8]
0x180010bf5  mov     rax, r12
0x180010bf8  sub     rcx, [r14]
0x180010bfb  mov     r11, rdx
0x180010bfe  mul     rcx
0x180010c01  shr     r11, 3
0x180010c05  lea     rcx, [rsp+10B0h+var_1068]
0x180010c0a  shr     rdx, 3
0x180010c0e  mov     r8, rdx
0x180010c11  mov     rdx, [r14]
0x180010c14  call    ??$make_range@PEAUwil_details_FeatureUsageSRUM@@@wil@@YA?AV?$pointer_range@PEAUwil_details_FeatureUsageSRUM@@@details@0@PEAUwil_details_FeatureUsageSRUM@@_K@Z; wil::make_range<wil_details_FeatureUsageSRUM *>(wil_details_FeatureUsageSRUM *,unsigned __int64)
0x180010c19  mov     r10, [rsp+10B0h+var_1068]
0x180010c1e  jmp     short loc_180010C95
0x180010c20  mov     r8d, r11d
0x180010c23  lea     rcx, [rsp+10B0h+var_1058]
0x180010c28  call    ??$make_range@PEAUwil_details_FeatureUsageSRUM@@@wil@@YA?AV?$pointer_range@PEAUwil_details_FeatureUsageSRUM@@@details@0@PEAUwil_details_FeatureUsageSRUM@@_K@Z; wil::make_range<wil_details_FeatureUsageSRUM *>(wil_details_FeatureUsageSRUM *,unsigned __int64)
0x180010c2d  mov     rcx, [rsp+10B0h+var_1058]
0x180010c32  cmp     rcx, [rsp+10B0h+var_1050]
0x180010c37  jz      short loc_180010C5F
0x180010c39  mov     eax, [r10]
0x180010c3c  cmp     [rcx], eax
0x180010c3e  jnz     short loc_180010C4B
0x180010c40  movzx   eax, word ptr [r10+4]
0x180010c45  cmp     [rcx+4], ax
0x180010c49  jz      short loc_180010C51
0x180010c4b  add     rcx, 0Ch
0x180010c4f  jmp     short loc_180010C32
0x180010c51  mov     eax, [r10+8]
0x180010c55  add     [rcx+8], eax
0x180010c58  mov     r9d, [rsp+10B0h+var_1070]
0x180010c5d  jmp     short loc_180010C91
0x180010c5f  mov     eax, r9d
0x180010c62  add     rax, 0Ch
0x180010c66  cmp     rax, 1000h
0x180010c6c  ja      short loc_180010C91
0x180010c6e  movsd   xmm0, qword ptr [r10]
0x180010c73  lea     rcx, [r8+r8*2]
0x180010c77  movsd   [rsp+rcx*4+10B0h+var_1040], xmm0
0x180010c7d  add     r9d, 0Ch
0x180010c81  mov     eax, [r10+8]
0x180010c85  inc     r11d
0x180010c88  mov     [rsp+rcx*4+10B0h+var_1038], eax
0x180010c8c  mov     [rsp+10B0h+var_1070], r9d
0x180010c91  add     r10, 0Ch
0x180010c95  lea     rdx, [rsp+10B0h+var_1040]
0x180010c9a  cmp     r10, [rsp+10B0h+var_1060]
0x180010c9f  jnz     loc_180010C20
0x180010ca5  mov     eax, [rsp+10B0h+var_106C]
0x180010ca9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010cb0  mov     [rsp+10B0h+var_1080], 1
0x180010cb8  mov     r8d, r9d
0x180010cbb  mov     dword ptr [rsp+10B0h+var_1088], eax
0x180010cbf  call    wil_details_NtUpdateWnfStateData
0x180010cc4  mov     edi, eax
0x180010cc6  cmp     edi, 0C0000001h
0x180010ccc  jnz     short loc_180010CDD
0x180010cce  inc     esi
0x180010cd0  cmp     esi, 64h ; 'd'
0x180010cd3  jge     short loc_180010CDD
0x180010cd5  test    ebx, ebx
0x180010cd7  jz      loc_180010B73
0x180010cdd  test    ebx, ebx
0x180010cdf  cmovz   ebx, edi
0x180010ce2  mov     eax, ebx
0x180010ce4  mov     rcx, [rbp+0FB0h+var_40]
0x180010ceb  xor     rcx, rsp; StackCookie
0x180010cee  call    __security_check_cookie
0x180010cf3  add     rsp, 1088h
0x180010cfa  pop     r14
0x180010cfc  pop     r12
0x180010cfe  pop     rdi
0x180010cff  pop     rsi
0x180010d00  pop     rbx
0x180010d01  pop     rbp
0x180010d02  retn
```
