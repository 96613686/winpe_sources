# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140018b0c`
- end: `0x140018ce2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140015950`

## callees

- `0x140018b0c`
- `0x140018ce8`
- `0x140018d90`
- `0x1400195e2`
- `0x140019610`
- `0x1400196d0`

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
      v15 = 4096;
      v16[0] = 0;
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
          if ( v17 == v11 )
          {
LABEL_12:
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
            v12 = v17;
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_12;
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
0x140018b0c  push    rbp
0x140018b0e  push    rbx
0x140018b0f  push    rsi
0x140018b10  push    rdi
0x140018b11  push    r12
0x140018b13  push    r14
0x140018b15  lea     rbp, [rsp-0F68h]
0x140018b1d  mov     eax, 1068h
0x140018b22  call    _alloca_probe
0x140018b27  sub     rsp, rax
0x140018b2a  mov     rax, cs:__security_cookie
0x140018b31  xor     rax, rsp
0x140018b34  mov     [rbp+0F90h+var_40], rax
0x140018b3b  mov     rax, [rcx+8]
0x140018b3f  xor     ebx, ebx
0x140018b41  sub     rax, [rcx]
0x140018b44  xor     edi, edi
0x140018b46  mov     r14, rcx
0x140018b49  cmp     rax, 0Ch
0x140018b4d  jb      loc_140018CAD
0x140018b53  xor     esi, esi
0x140018b55  mov     r12, 0AAAAAAAAAAAAAAABh
0x140018b5f  xor     edx, edx; Val
0x140018b61  lea     rcx, [rsp+1090h+var_1040]; void *
0x140018b66  mov     r8d, 1000h; Size
0x140018b6c  call    memset_0
0x140018b71  lea     rax, [rsp+1090h+var_1050]
0x140018b76  mov     [rsp+1090h+var_1050], 1000h
0x140018b7e  mov     [rsp+1090h+var_1068], rax
0x140018b83  lea     r9, [rsp+1090h+var_104C]
0x140018b88  lea     rax, [rsp+1090h+var_1040]
0x140018b8d  mov     [rsp+1090h+var_104C], 0
0x140018b95  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140018b9c  mov     [rsp+1090h+var_1070], rax
0x140018ba1  call    wil_details_NtQueryWnfStateData
0x140018ba6  mov     ebx, eax
0x140018ba8  test    eax, eax
0x140018baa  jnz     loc_140018C96
0x140018bb0  mov     r9d, [rsp+1090h+var_1050]
0x140018bb5  mov     rax, r12
0x140018bb8  mul     r9
0x140018bbb  shr     rdx, 3
0x140018bbf  lea     rcx, [rdx+rdx*2]
0x140018bc3  shl     rcx, 2
0x140018bc7  cmp     r9, rcx
0x140018bca  jz      short loc_140018BD4
0x140018bcc  xor     r9d, r9d
0x140018bcf  mov     [rsp+1090h+var_1050], r9d
0x140018bd4  mov     r8, [r14]
0x140018bd7  mov     rax, r12
0x140018bda  mov     ecx, r9d
0x140018bdd  mul     rcx
0x140018be0  mov     rcx, [r14+8]
0x140018be4  mov     rax, r12
0x140018be7  mov     r10, rdx
0x140018bea  sub     rcx, r8
0x140018bed  mul     rcx
0x140018bf0  shr     r10, 3
0x140018bf4  shr     rdx, 3
0x140018bf8  lea     rax, [rdx+rdx*2]
0x140018bfc  lea     rdi, [r8+rax*4]
0x140018c00  jmp     short loc_140018C6B
0x140018c02  mov     eax, r10d
0x140018c05  lea     rcx, [rax+rax*2]
0x140018c09  lea     rdx, [rdx+rcx*4]
0x140018c0d  lea     rax, [rsp+1090h+var_1040]
0x140018c12  cmp     rax, rdx
0x140018c15  jz      short loc_140018C3C
0x140018c17  mov     r11d, [r8]
0x140018c1a  lea     rcx, [rsp+1090h+var_1040]
0x140018c1f  cmp     [rcx], r11d
0x140018c22  jnz     short loc_140018C33
0x140018c24  movzx   eax, word ptr [r8+4]
0x140018c29  cmp     [rcx+4], ax
0x140018c2d  jz      loc_140018CD4
0x140018c33  add     rcx, 0Ch
0x140018c37  cmp     rcx, rdx
0x140018c3a  jnz     short loc_140018C1F
0x140018c3c  mov     eax, r9d
0x140018c3f  add     rax, 0Ch
0x140018c43  cmp     rax, 1000h
0x140018c49  ja      short loc_140018C67
0x140018c4b  movsd   xmm0, qword ptr [r8]
0x140018c50  add     r9d, 0Ch
0x140018c54  movsd   qword ptr [rdx], xmm0
0x140018c58  inc     r10d
0x140018c5b  mov     eax, [r8+8]
0x140018c5f  mov     [rdx+8], eax
0x140018c62  mov     [rsp+1090h+var_1050], r9d
0x140018c67  add     r8, 0Ch
0x140018c6b  lea     rdx, [rsp+1090h+var_1040]
0x140018c70  cmp     r8, rdi
0x140018c73  jnz     short loc_140018C02
0x140018c75  mov     eax, [rsp+1090h+var_104C]
0x140018c79  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140018c80  mov     [rsp+1090h+var_1060], 1
0x140018c88  mov     r8d, r9d
0x140018c8b  mov     dword ptr [rsp+1090h+var_1068], eax
0x140018c8f  call    wil_details_NtUpdateWnfStateData
0x140018c94  mov     edi, eax
0x140018c96  cmp     edi, 0C0000001h
0x140018c9c  jnz     short loc_140018CAD
0x140018c9e  inc     esi
0x140018ca0  cmp     esi, 64h ; 'd'
0x140018ca3  jge     short loc_140018CAD
0x140018ca5  test    ebx, ebx
0x140018ca7  jz      loc_140018B5F
0x140018cad  test    ebx, ebx
0x140018caf  cmovz   ebx, edi
0x140018cb2  mov     eax, ebx
0x140018cb4  mov     rcx, [rbp+0F90h+var_40]
0x140018cbb  xor     rcx, rsp; StackCookie
0x140018cbe  call    __security_check_cookie
0x140018cc3  add     rsp, 1068h
0x140018cca  pop     r14
0x140018ccc  pop     r12
0x140018cce  pop     rdi
0x140018ccf  pop     rsi
0x140018cd0  pop     rbx
0x140018cd1  pop     rbp
0x140018cd2  retn
0x140018cd4  mov     eax, [r8+8]
0x140018cd8  add     [rcx+8], eax
0x140018cdb  mov     r9d, [rsp+1090h+var_1050]
0x140018ce0  jmp     short loc_140018C67
```
