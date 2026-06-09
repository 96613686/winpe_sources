# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180019f6c`
- end: `0x18001a159`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003630`

## callees

- `0x1800026b0`
- `0x180003374`
- `0x180019f6c`
- `0x18001acf0`
- `0x18001ad98`
- `0x180021f90`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v17[1024]; // [rsp+50h] [rbp-B0h] BYREF

  WnfStateData = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v17, 0, sizeof(v17));
      v16[0] = 0;
      v15 = 4096;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
        v9 = (unsigned int)v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          v12 = v17;
          if ( v17 == v11 )
          {
LABEL_11:
            if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
            {
              v7 = (unsigned int)(v7 + 12);
              *(_QWORD *)v11 = *(_QWORD *)v8;
              ++v9;
              v11[2] = *(_DWORD *)(v8 + 8);
              v15 = v7;
            }
          }
          else
          {
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_11;
            }
            v12[2] += *(_DWORD *)(v8 + 8);
            v7 = v15;
          }
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
                    v7,
                    v7,
                    v14,
                    v16[0],
                    1);
      }
      ++v4;
    }
    while ( updated == -1073741823 && v4 < 100 && !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x180019f6c  mov     rax, rsp
0x180019f6f  mov     [rax+8], rbx
0x180019f73  mov     [rax+10h], rsi
0x180019f77  mov     [rax+18h], rdi
0x180019f7b  push    rbp
0x180019f7c  push    r12
0x180019f7e  push    r14
0x180019f80  lea     rbp, [rax-0F78h]
0x180019f87  mov     eax, 1060h
0x180019f8c  call    _alloca_probe
0x180019f91  sub     rsp, rax
0x180019f94  mov     rax, cs:__security_cookie
0x180019f9b  xor     rax, rsp
0x180019f9e  mov     [rbp+0F70h+var_20], rax
0x180019fa5  mov     rax, [rcx+8]
0x180019fa9  xor     ebx, ebx
0x180019fab  sub     rax, [rcx]
0x180019fae  xor     edi, edi
0x180019fb0  mov     r14, rcx
0x180019fb3  cmp     rax, 0Ch
0x180019fb7  jb      loc_18001A114
0x180019fbd  xor     esi, esi
0x180019fbf  mov     r12, 0AAAAAAAAAAAAAAABh
0x180019fc9  xor     edx, edx; Val
0x180019fcb  lea     rcx, [rsp+1070h+var_1020]; void *
0x180019fd0  mov     r8d, 1000h; Size
0x180019fd6  call    memset_0
0x180019fdb  and     [rsp+1070h+var_102C], 0
0x180019fe0  lea     rax, [rsp+1070h+var_1030]
0x180019fe5  mov     qword ptr [rsp+1070h+var_1048], rax
0x180019fea  lea     r9, [rsp+1070h+var_102C]
0x180019fef  lea     rax, [rsp+1070h+var_1020]
0x180019ff4  mov     [rsp+1070h+var_1030], 1000h
0x180019ffc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001a003  mov     [rsp+1070h+var_1050], rax
0x18001a008  call    wil_details_NtQueryWnfStateData
0x18001a00d  mov     ebx, eax
0x18001a00f  test    eax, eax
0x18001a011  jnz     loc_18001A0FD
0x18001a017  mov     r9d, [rsp+1070h+var_1030]
0x18001a01c  mov     rax, r12
0x18001a01f  mul     r9
0x18001a022  shr     rdx, 3
0x18001a026  lea     rcx, [rdx+rdx*2]
0x18001a02a  shl     rcx, 2
0x18001a02e  cmp     r9, rcx
0x18001a031  jz      short loc_18001A03B
0x18001a033  xor     r9d, r9d
0x18001a036  mov     [rsp+1070h+var_1030], r9d
0x18001a03b  mov     r8, [r14]
0x18001a03e  mov     rax, r12
0x18001a041  mov     ecx, r9d
0x18001a044  mul     rcx
0x18001a047  mov     rcx, [r14+8]
0x18001a04b  mov     rax, r12
0x18001a04e  mov     r10, rdx
0x18001a051  sub     rcx, r8
0x18001a054  mul     rcx
0x18001a057  shr     r10, 3
0x18001a05b  shr     rdx, 3
0x18001a05f  lea     rax, [rdx+rdx*2]
0x18001a063  lea     rdi, [r8+rax*4]
0x18001a067  jmp     short loc_18001A0D2
0x18001a069  mov     eax, r10d
0x18001a06c  lea     rcx, [rax+rax*2]
0x18001a070  lea     rdx, [rdx+rcx*4]
0x18001a074  lea     rax, [rsp+1070h+var_1020]
0x18001a079  lea     rcx, [rsp+1070h+var_1020]
0x18001a07e  cmp     rax, rdx
0x18001a081  jz      short loc_18001A0A3
0x18001a083  mov     r11d, [r8]
0x18001a086  cmp     [rcx], r11d
0x18001a089  jnz     short loc_18001A09A
0x18001a08b  movzx   eax, word ptr [r8+4]
0x18001a090  cmp     [rcx+4], ax
0x18001a094  jz      loc_18001A148
0x18001a09a  add     rcx, 0Ch
0x18001a09e  cmp     rcx, rdx
0x18001a0a1  jnz     short loc_18001A086
0x18001a0a3  mov     eax, r9d
0x18001a0a6  add     rax, 0Ch
0x18001a0aa  cmp     rax, 1000h
0x18001a0b0  ja      short loc_18001A0CE
0x18001a0b2  movsd   xmm0, qword ptr [r8]
0x18001a0b7  add     r9d, 0Ch
0x18001a0bb  movsd   qword ptr [rdx], xmm0
0x18001a0bf  inc     r10d
0x18001a0c2  mov     eax, [r8+8]
0x18001a0c6  mov     [rdx+8], eax
0x18001a0c9  mov     [rsp+1070h+var_1030], r9d
0x18001a0ce  add     r8, 0Ch
0x18001a0d2  lea     rdx, [rsp+1070h+var_1020]
0x18001a0d7  cmp     r8, rdi
0x18001a0da  jnz     short loc_18001A069
0x18001a0dc  mov     eax, [rsp+1070h+var_102C]
0x18001a0e0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001a0e7  mov     [rsp+1070h+var_1040], 1
0x18001a0ef  mov     r8d, r9d
0x18001a0f2  mov     [rsp+1070h+var_1048], eax
0x18001a0f6  call    wil_details_NtUpdateWnfStateData
0x18001a0fb  mov     edi, eax
0x18001a0fd  inc     esi
0x18001a0ff  cmp     edi, 0C0000001h
0x18001a105  jnz     short loc_18001A114
0x18001a107  cmp     esi, 64h ; 'd'
0x18001a10a  jge     short loc_18001A114
0x18001a10c  test    ebx, ebx
0x18001a10e  jz      loc_180019FC9
0x18001a114  test    ebx, ebx
0x18001a116  cmovz   ebx, edi
0x18001a119  mov     eax, ebx
0x18001a11b  mov     rcx, [rbp+0F70h+var_20]
0x18001a122  xor     rcx, rsp; StackCookie
0x18001a125  call    __security_check_cookie
0x18001a12a  lea     r11, [rsp+1070h+var_10]
0x18001a132  mov     rbx, [r11+20h]
0x18001a136  mov     rsi, [r11+28h]
0x18001a13a  mov     rdi, [r11+30h]
0x18001a13e  mov     rsp, r11
0x18001a141  pop     r14
0x18001a143  pop     r12
0x18001a145  pop     rbp
0x18001a146  retn
0x18001a148  mov     eax, [r8+8]
0x18001a14c  add     [rcx+8], eax
0x18001a14f  mov     r9d, [rsp+1070h+var_1030]
0x18001a154  jmp     loc_18001A0CE
```
