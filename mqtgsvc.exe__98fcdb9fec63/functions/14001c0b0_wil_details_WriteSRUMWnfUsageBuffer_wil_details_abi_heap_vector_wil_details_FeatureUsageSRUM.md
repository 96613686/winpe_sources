# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14001c0b0`
- end: `0x14001c27a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400163f0`

## callees

- `0x14001c0b0`
- `0x14001c434`
- `0x14001c4ac`
- `0x14001ceda`
- `0x14001cf00`
- `0x14001cfc0`

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
0x14001c0b0  push    rbp
0x14001c0b2  push    rbx
0x14001c0b3  push    rsi
0x14001c0b4  push    rdi
0x14001c0b5  push    r12
0x14001c0b7  push    r14
0x14001c0b9  lea     rbp, [rsp-0F68h]
0x14001c0c1  mov     eax, 1068h
0x14001c0c6  call    _alloca_probe
0x14001c0cb  sub     rsp, rax
0x14001c0ce  mov     rax, cs:__security_cookie
0x14001c0d5  xor     rax, rsp
0x14001c0d8  mov     [rbp+0F90h+var_40], rax
0x14001c0df  mov     rax, [rcx+8]
0x14001c0e3  xor     ebx, ebx
0x14001c0e5  sub     rax, [rcx]
0x14001c0e8  xor     edi, edi
0x14001c0ea  mov     r14, rcx
0x14001c0ed  cmp     rax, 0Ch
0x14001c0f1  jb      loc_14001C254
0x14001c0f7  xor     esi, esi
0x14001c0f9  mov     r12, 0AAAAAAAAAAAAAAABh
0x14001c103  xor     edx, edx; Val
0x14001c105  lea     rcx, [rsp+1090h+var_1040]; void *
0x14001c10a  mov     r8d, 1000h; Size
0x14001c110  call    memset_0
0x14001c115  lea     rax, [rsp+1090h+var_1050]
0x14001c11a  mov     [rsp+1090h+var_1050], 1000h
0x14001c122  mov     [rsp+1090h+var_1068], rax
0x14001c127  lea     r9, [rsp+1090h+var_104C]
0x14001c12c  lea     rax, [rsp+1090h+var_1040]
0x14001c131  mov     [rsp+1090h+var_104C], 0
0x14001c139  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001c140  mov     [rsp+1090h+var_1070], rax
0x14001c145  call    wil_details_NtQueryWnfStateData
0x14001c14a  mov     ebx, eax
0x14001c14c  test    eax, eax
0x14001c14e  jnz     loc_14001C23D
0x14001c154  mov     r9d, [rsp+1090h+var_1050]
0x14001c159  mov     rax, r12
0x14001c15c  mul     r9
0x14001c15f  shr     rdx, 3
0x14001c163  lea     rcx, [rdx+rdx*2]
0x14001c167  shl     rcx, 2
0x14001c16b  cmp     r9, rcx
0x14001c16e  jz      short loc_14001C178
0x14001c170  xor     r9d, r9d
0x14001c173  mov     [rsp+1090h+var_1050], r9d
0x14001c178  mov     r8, [r14]
0x14001c17b  mov     rax, r12
0x14001c17e  mov     ecx, r9d
0x14001c181  mul     rcx
0x14001c184  mov     rcx, [r14+8]
0x14001c188  mov     rax, r12
0x14001c18b  mov     r11, rdx
0x14001c18e  sub     rcx, r8
0x14001c191  mul     rcx
0x14001c194  shr     r11, 3
0x14001c198  shr     rdx, 3
0x14001c19c  lea     rax, [rdx+rdx*2]
0x14001c1a0  lea     rdi, [r8+rax*4]
0x14001c1a4  jmp     short loc_14001C212
0x14001c1a6  mov     eax, r11d
0x14001c1a9  lea     r10, [rsp+1090h+var_1040]
0x14001c1ae  lea     rcx, [rax+rax*2]
0x14001c1b2  lea     r10, [r10+rcx*4]
0x14001c1b6  cmp     rdx, r10
0x14001c1b9  jz      short loc_14001C1E1
0x14001c1bb  mov     eax, [r8]
0x14001c1be  cmp     [rdx], eax
0x14001c1c0  jnz     short loc_14001C1CD
0x14001c1c2  movzx   eax, word ptr [r8+4]
0x14001c1c7  cmp     [rdx+4], ax
0x14001c1cb  jz      short loc_14001C1D3
0x14001c1cd  add     rdx, 0Ch
0x14001c1d1  jmp     short loc_14001C1B6
0x14001c1d3  mov     eax, [r8+8]
0x14001c1d7  add     [rdx+8], eax
0x14001c1da  mov     r9d, [rsp+1090h+var_1050]
0x14001c1df  jmp     short loc_14001C20E
0x14001c1e1  mov     eax, r9d
0x14001c1e4  add     rax, 0Ch
0x14001c1e8  cmp     rax, 1000h
0x14001c1ee  ja      short loc_14001C20E
0x14001c1f0  movsd   xmm0, qword ptr [r8]
0x14001c1f5  add     r9d, 0Ch
0x14001c1f9  movsd   qword ptr [r10], xmm0
0x14001c1fe  inc     r11d
0x14001c201  mov     eax, [r8+8]
0x14001c205  mov     [r10+8], eax
0x14001c209  mov     [rsp+1090h+var_1050], r9d
0x14001c20e  add     r8, 0Ch
0x14001c212  lea     rdx, [rsp+1090h+var_1040]
0x14001c217  cmp     r8, rdi
0x14001c21a  jnz     short loc_14001C1A6
0x14001c21c  mov     eax, [rsp+1090h+var_104C]
0x14001c220  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001c227  mov     [rsp+1090h+var_1060], 1
0x14001c22f  mov     r8d, r9d
0x14001c232  mov     dword ptr [rsp+1090h+var_1068], eax
0x14001c236  call    wil_details_NtUpdateWnfStateData
0x14001c23b  mov     edi, eax
0x14001c23d  cmp     edi, 0C0000001h
0x14001c243  jnz     short loc_14001C254
0x14001c245  inc     esi
0x14001c247  cmp     esi, 64h ; 'd'
0x14001c24a  jge     short loc_14001C254
0x14001c24c  test    ebx, ebx
0x14001c24e  jz      loc_14001C103
0x14001c254  test    ebx, ebx
0x14001c256  cmovz   ebx, edi
0x14001c259  mov     eax, ebx
0x14001c25b  mov     rcx, [rbp+0F90h+var_40]
0x14001c262  xor     rcx, rsp; StackCookie
0x14001c265  call    __security_check_cookie
0x14001c26a  add     rsp, 1068h
0x14001c271  pop     r14
0x14001c273  pop     r12
0x14001c275  pop     rdi
0x14001c276  pop     rsi
0x14001c277  pop     rbx
0x14001c278  pop     rbp
0x14001c279  retn
```
