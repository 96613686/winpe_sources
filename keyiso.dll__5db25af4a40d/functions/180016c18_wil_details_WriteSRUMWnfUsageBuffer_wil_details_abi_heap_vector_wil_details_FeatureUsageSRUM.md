# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180016c18`
- end: `0x180016de2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800118d0`

## callees

- `0x18000d0ac`
- `0x180016c18`
- `0x180016f0c`
- `0x180016f84`
- `0x1800188b0`
- `0x180018950`

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
0x180016c18  push    rbp
0x180016c1a  push    rbx
0x180016c1b  push    rsi
0x180016c1c  push    rdi
0x180016c1d  push    r12
0x180016c1f  push    r14
0x180016c21  lea     rbp, [rsp-0F68h]
0x180016c29  mov     eax, 1068h
0x180016c2e  call    _alloca_probe
0x180016c33  sub     rsp, rax
0x180016c36  mov     rax, cs:__security_cookie
0x180016c3d  xor     rax, rsp
0x180016c40  mov     [rbp+0F90h+var_40], rax
0x180016c47  mov     rax, [rcx+8]
0x180016c4b  xor     ebx, ebx
0x180016c4d  sub     rax, [rcx]
0x180016c50  xor     edi, edi
0x180016c52  mov     r14, rcx
0x180016c55  cmp     rax, 0Ch
0x180016c59  jb      loc_180016DBC
0x180016c5f  xor     esi, esi
0x180016c61  mov     r12, 0AAAAAAAAAAAAAAABh
0x180016c6b  xor     edx, edx; Val
0x180016c6d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180016c72  mov     r8d, 1000h; Size
0x180016c78  call    memset_0
0x180016c7d  lea     rax, [rsp+1090h+var_1050]
0x180016c82  mov     [rsp+1090h+var_1050], 1000h
0x180016c8a  mov     [rsp+1090h+var_1068], rax
0x180016c8f  lea     r9, [rsp+1090h+var_104C]
0x180016c94  lea     rax, [rsp+1090h+var_1040]
0x180016c99  mov     [rsp+1090h+var_104C], 0
0x180016ca1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016ca8  mov     [rsp+1090h+var_1070], rax
0x180016cad  call    wil_details_NtQueryWnfStateData
0x180016cb2  mov     ebx, eax
0x180016cb4  test    eax, eax
0x180016cb6  jnz     loc_180016DA5
0x180016cbc  mov     r9d, [rsp+1090h+var_1050]
0x180016cc1  mov     rax, r12
0x180016cc4  mul     r9
0x180016cc7  shr     rdx, 3
0x180016ccb  lea     rcx, [rdx+rdx*2]
0x180016ccf  shl     rcx, 2
0x180016cd3  cmp     r9, rcx
0x180016cd6  jz      short loc_180016CE0
0x180016cd8  xor     r9d, r9d
0x180016cdb  mov     [rsp+1090h+var_1050], r9d
0x180016ce0  mov     r8, [r14]
0x180016ce3  mov     rax, r12
0x180016ce6  mov     ecx, r9d
0x180016ce9  mul     rcx
0x180016cec  mov     rcx, [r14+8]
0x180016cf0  mov     rax, r12
0x180016cf3  mov     r11, rdx
0x180016cf6  sub     rcx, r8
0x180016cf9  mul     rcx
0x180016cfc  shr     r11, 3
0x180016d00  shr     rdx, 3
0x180016d04  lea     rax, [rdx+rdx*2]
0x180016d08  lea     rdi, [r8+rax*4]
0x180016d0c  jmp     short loc_180016D7A
0x180016d0e  mov     eax, r11d
0x180016d11  lea     r10, [rsp+1090h+var_1040]
0x180016d16  lea     rcx, [rax+rax*2]
0x180016d1a  lea     r10, [r10+rcx*4]
0x180016d1e  cmp     rdx, r10
0x180016d21  jz      short loc_180016D49
0x180016d23  mov     eax, [r8]
0x180016d26  cmp     [rdx], eax
0x180016d28  jnz     short loc_180016D35
0x180016d2a  movzx   eax, word ptr [r8+4]
0x180016d2f  cmp     [rdx+4], ax
0x180016d33  jz      short loc_180016D3B
0x180016d35  add     rdx, 0Ch
0x180016d39  jmp     short loc_180016D1E
0x180016d3b  mov     eax, [r8+8]
0x180016d3f  add     [rdx+8], eax
0x180016d42  mov     r9d, [rsp+1090h+var_1050]
0x180016d47  jmp     short loc_180016D76
0x180016d49  mov     eax, r9d
0x180016d4c  add     rax, 0Ch
0x180016d50  cmp     rax, 1000h
0x180016d56  ja      short loc_180016D76
0x180016d58  movsd   xmm0, qword ptr [r8]
0x180016d5d  add     r9d, 0Ch
0x180016d61  movsd   qword ptr [r10], xmm0
0x180016d66  inc     r11d
0x180016d69  mov     eax, [r8+8]
0x180016d6d  mov     [r10+8], eax
0x180016d71  mov     [rsp+1090h+var_1050], r9d
0x180016d76  add     r8, 0Ch
0x180016d7a  lea     rdx, [rsp+1090h+var_1040]
0x180016d7f  cmp     r8, rdi
0x180016d82  jnz     short loc_180016D0E
0x180016d84  mov     eax, [rsp+1090h+var_104C]
0x180016d88  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016d8f  mov     [rsp+1090h+var_1060], 1
0x180016d97  mov     r8d, r9d
0x180016d9a  mov     dword ptr [rsp+1090h+var_1068], eax
0x180016d9e  call    wil_details_NtUpdateWnfStateData
0x180016da3  mov     edi, eax
0x180016da5  cmp     edi, 0C0000001h
0x180016dab  jnz     short loc_180016DBC
0x180016dad  inc     esi
0x180016daf  cmp     esi, 64h ; 'd'
0x180016db2  jge     short loc_180016DBC
0x180016db4  test    ebx, ebx
0x180016db6  jz      loc_180016C6B
0x180016dbc  test    ebx, ebx
0x180016dbe  cmovz   ebx, edi
0x180016dc1  mov     eax, ebx
0x180016dc3  mov     rcx, [rbp+0F90h+var_40]
0x180016dca  xor     rcx, rsp; StackCookie
0x180016dcd  call    __security_check_cookie
0x180016dd2  add     rsp, 1068h
0x180016dd9  pop     r14
0x180016ddb  pop     r12
0x180016ddd  pop     rdi
0x180016dde  pop     rsi
0x180016ddf  pop     rbx
0x180016de0  pop     rbp
0x180016de1  retn
```
