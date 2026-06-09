# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d20c`
- end: `0x18000d3d6`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006880`

## callees

- `0x180001a70`
- `0x180002554`
- `0x18000d20c`
- `0x18000da84`
- `0x18000dafc`
- `0x1800116b0`

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
0x18000d20c  push    rbp
0x18000d20e  push    rbx
0x18000d20f  push    rsi
0x18000d210  push    rdi
0x18000d211  push    r12
0x18000d213  push    r14
0x18000d215  lea     rbp, [rsp-0F68h]
0x18000d21d  mov     eax, 1068h
0x18000d222  call    _alloca_probe
0x18000d227  sub     rsp, rax
0x18000d22a  mov     rax, cs:__security_cookie
0x18000d231  xor     rax, rsp
0x18000d234  mov     [rbp+0F90h+var_40], rax
0x18000d23b  mov     rax, [rcx+8]
0x18000d23f  xor     ebx, ebx
0x18000d241  sub     rax, [rcx]
0x18000d244  xor     edi, edi
0x18000d246  mov     r14, rcx
0x18000d249  cmp     rax, 0Ch
0x18000d24d  jb      loc_18000D3B0
0x18000d253  xor     esi, esi
0x18000d255  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000d25f  xor     edx, edx; Val
0x18000d261  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d266  mov     r8d, 1000h; Size
0x18000d26c  call    memset_0
0x18000d271  lea     rax, [rsp+1090h+var_1050]
0x18000d276  mov     [rsp+1090h+var_1050], 1000h
0x18000d27e  mov     [rsp+1090h+var_1068], rax
0x18000d283  lea     r9, [rsp+1090h+var_104C]
0x18000d288  lea     rax, [rsp+1090h+var_1040]
0x18000d28d  mov     [rsp+1090h+var_104C], 0
0x18000d295  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d29c  mov     [rsp+1090h+var_1070], rax
0x18000d2a1  call    wil_details_NtQueryWnfStateData
0x18000d2a6  mov     ebx, eax
0x18000d2a8  test    eax, eax
0x18000d2aa  jnz     loc_18000D399
0x18000d2b0  mov     r9d, [rsp+1090h+var_1050]
0x18000d2b5  mov     rax, r12
0x18000d2b8  mul     r9
0x18000d2bb  shr     rdx, 3
0x18000d2bf  lea     rcx, [rdx+rdx*2]
0x18000d2c3  shl     rcx, 2
0x18000d2c7  cmp     r9, rcx
0x18000d2ca  jz      short loc_18000D2D4
0x18000d2cc  xor     r9d, r9d
0x18000d2cf  mov     [rsp+1090h+var_1050], r9d
0x18000d2d4  mov     r8, [r14]
0x18000d2d7  mov     rax, r12
0x18000d2da  mov     ecx, r9d
0x18000d2dd  mul     rcx
0x18000d2e0  mov     rcx, [r14+8]
0x18000d2e4  mov     rax, r12
0x18000d2e7  mov     r11, rdx
0x18000d2ea  sub     rcx, r8
0x18000d2ed  mul     rcx
0x18000d2f0  shr     r11, 3
0x18000d2f4  shr     rdx, 3
0x18000d2f8  lea     rax, [rdx+rdx*2]
0x18000d2fc  lea     rdi, [r8+rax*4]
0x18000d300  jmp     short loc_18000D36E
0x18000d302  mov     eax, r11d
0x18000d305  lea     r10, [rsp+1090h+var_1040]
0x18000d30a  lea     rcx, [rax+rax*2]
0x18000d30e  lea     r10, [r10+rcx*4]
0x18000d312  cmp     rdx, r10
0x18000d315  jz      short loc_18000D33D
0x18000d317  mov     eax, [r8]
0x18000d31a  cmp     [rdx], eax
0x18000d31c  jnz     short loc_18000D329
0x18000d31e  movzx   eax, word ptr [r8+4]
0x18000d323  cmp     [rdx+4], ax
0x18000d327  jz      short loc_18000D32F
0x18000d329  add     rdx, 0Ch
0x18000d32d  jmp     short loc_18000D312
0x18000d32f  mov     eax, [r8+8]
0x18000d333  add     [rdx+8], eax
0x18000d336  mov     r9d, [rsp+1090h+var_1050]
0x18000d33b  jmp     short loc_18000D36A
0x18000d33d  mov     eax, r9d
0x18000d340  add     rax, 0Ch
0x18000d344  cmp     rax, 1000h
0x18000d34a  ja      short loc_18000D36A
0x18000d34c  movsd   xmm0, qword ptr [r8]
0x18000d351  add     r9d, 0Ch
0x18000d355  movsd   qword ptr [r10], xmm0
0x18000d35a  inc     r11d
0x18000d35d  mov     eax, [r8+8]
0x18000d361  mov     [r10+8], eax
0x18000d365  mov     [rsp+1090h+var_1050], r9d
0x18000d36a  add     r8, 0Ch
0x18000d36e  lea     rdx, [rsp+1090h+var_1040]
0x18000d373  cmp     r8, rdi
0x18000d376  jnz     short loc_18000D302
0x18000d378  mov     eax, [rsp+1090h+var_104C]
0x18000d37c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d383  mov     [rsp+1090h+var_1060], 1
0x18000d38b  mov     r8d, r9d
0x18000d38e  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d392  call    wil_details_NtUpdateWnfStateData
0x18000d397  mov     edi, eax
0x18000d399  cmp     edi, 0C0000001h
0x18000d39f  jnz     short loc_18000D3B0
0x18000d3a1  inc     esi
0x18000d3a3  cmp     esi, 64h ; 'd'
0x18000d3a6  jge     short loc_18000D3B0
0x18000d3a8  test    ebx, ebx
0x18000d3aa  jz      loc_18000D25F
0x18000d3b0  test    ebx, ebx
0x18000d3b2  cmovz   ebx, edi
0x18000d3b5  mov     eax, ebx
0x18000d3b7  mov     rcx, [rbp+0F90h+var_40]
0x18000d3be  xor     rcx, rsp; StackCookie
0x18000d3c1  call    __security_check_cookie
0x18000d3c6  add     rsp, 1068h
0x18000d3cd  pop     r14
0x18000d3cf  pop     r12
0x18000d3d1  pop     rdi
0x18000d3d2  pop     rsi
0x18000d3d3  pop     rbx
0x18000d3d4  pop     rbp
0x18000d3d5  retn
```
