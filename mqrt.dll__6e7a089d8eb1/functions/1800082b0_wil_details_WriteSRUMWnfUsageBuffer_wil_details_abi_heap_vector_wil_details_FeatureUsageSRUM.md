# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800082b0`
- end: `0x18000847a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002870`

## callees

- `0x1800082b0`
- `0x1800088f0`
- `0x180008968`
- `0x180023c5a`
- `0x180023ca0`
- `0x180023d60`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
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
        v9 = (unsigned int)v7 / 0xC;
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
          if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
          {
            v7 = (unsigned int)(v7 + 12);
            *(_QWORD *)v11 = *(_QWORD *)v8;
            ++v9;
            v11[2] = *(_DWORD *)(v8 + 8);
            v15 = v7;
          }
LABEL_15:
          v8 += 12;
        }
        updated = wil_details_NtUpdateWnfStateData(
                    (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                    (__int64)v17,
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
0x1800082b0  push    rbp
0x1800082b2  push    rbx
0x1800082b3  push    rsi
0x1800082b4  push    rdi
0x1800082b5  push    r12
0x1800082b7  push    r14
0x1800082b9  lea     rbp, [rsp-0F68h]
0x1800082c1  mov     eax, 1068h
0x1800082c6  call    _alloca_probe
0x1800082cb  sub     rsp, rax
0x1800082ce  mov     rax, cs:__security_cookie
0x1800082d5  xor     rax, rsp
0x1800082d8  mov     [rbp+0F90h+var_40], rax
0x1800082df  mov     rax, [rcx+8]
0x1800082e3  xor     ebx, ebx
0x1800082e5  sub     rax, [rcx]
0x1800082e8  xor     edi, edi
0x1800082ea  mov     r14, rcx
0x1800082ed  cmp     rax, 0Ch
0x1800082f1  jb      loc_180008454
0x1800082f7  xor     esi, esi
0x1800082f9  mov     r12, 0AAAAAAAAAAAAAAABh
0x180008303  xor     edx, edx; Val
0x180008305  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000830a  mov     r8d, 1000h; Size
0x180008310  call    memset_0
0x180008315  lea     rax, [rsp+1090h+var_1050]
0x18000831a  mov     [rsp+1090h+var_1050], 1000h
0x180008322  mov     [rsp+1090h+var_1068], rax
0x180008327  lea     r9, [rsp+1090h+var_104C]
0x18000832c  lea     rax, [rsp+1090h+var_1040]
0x180008331  mov     [rsp+1090h+var_104C], 0
0x180008339  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008340  mov     [rsp+1090h+var_1070], rax
0x180008345  call    wil_details_NtQueryWnfStateData
0x18000834a  mov     ebx, eax
0x18000834c  test    eax, eax
0x18000834e  jnz     loc_18000843D
0x180008354  mov     r9d, [rsp+1090h+var_1050]
0x180008359  mov     rax, r12
0x18000835c  mul     r9
0x18000835f  shr     rdx, 3
0x180008363  lea     rcx, [rdx+rdx*2]
0x180008367  shl     rcx, 2
0x18000836b  cmp     r9, rcx
0x18000836e  jz      short loc_180008378
0x180008370  xor     r9d, r9d
0x180008373  mov     [rsp+1090h+var_1050], r9d
0x180008378  mov     r8, [r14]
0x18000837b  mov     rax, r12
0x18000837e  mov     ecx, r9d
0x180008381  mul     rcx
0x180008384  mov     rcx, [r14+8]
0x180008388  mov     rax, r12
0x18000838b  mov     r11, rdx
0x18000838e  sub     rcx, r8
0x180008391  mul     rcx
0x180008394  shr     r11, 3
0x180008398  shr     rdx, 3
0x18000839c  lea     rax, [rdx+rdx*2]
0x1800083a0  lea     rdi, [r8+rax*4]
0x1800083a4  jmp     short loc_180008412
0x1800083a6  mov     eax, r11d
0x1800083a9  lea     r10, [rsp+1090h+var_1040]
0x1800083ae  lea     rcx, [rax+rax*2]
0x1800083b2  lea     r10, [r10+rcx*4]
0x1800083b6  cmp     rdx, r10
0x1800083b9  jz      short loc_1800083E1
0x1800083bb  mov     eax, [r8]
0x1800083be  cmp     [rdx], eax
0x1800083c0  jnz     short loc_1800083CD
0x1800083c2  movzx   eax, word ptr [r8+4]
0x1800083c7  cmp     [rdx+4], ax
0x1800083cb  jz      short loc_1800083D3
0x1800083cd  add     rdx, 0Ch
0x1800083d1  jmp     short loc_1800083B6
0x1800083d3  mov     eax, [r8+8]
0x1800083d7  add     [rdx+8], eax
0x1800083da  mov     r9d, [rsp+1090h+var_1050]
0x1800083df  jmp     short loc_18000840E
0x1800083e1  mov     eax, r9d
0x1800083e4  add     rax, 0Ch
0x1800083e8  cmp     rax, 1000h
0x1800083ee  ja      short loc_18000840E
0x1800083f0  movsd   xmm0, qword ptr [r8]
0x1800083f5  add     r9d, 0Ch
0x1800083f9  movsd   qword ptr [r10], xmm0
0x1800083fe  inc     r11d
0x180008401  mov     eax, [r8+8]
0x180008405  mov     [r10+8], eax
0x180008409  mov     [rsp+1090h+var_1050], r9d
0x18000840e  add     r8, 0Ch
0x180008412  lea     rdx, [rsp+1090h+var_1040]
0x180008417  cmp     r8, rdi
0x18000841a  jnz     short loc_1800083A6
0x18000841c  mov     eax, [rsp+1090h+var_104C]
0x180008420  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008427  mov     [rsp+1090h+var_1060], 1
0x18000842f  mov     r8d, r9d
0x180008432  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008436  call    wil_details_NtUpdateWnfStateData
0x18000843b  mov     edi, eax
0x18000843d  cmp     edi, 0C0000001h
0x180008443  jnz     short loc_180008454
0x180008445  inc     esi
0x180008447  cmp     esi, 64h ; 'd'
0x18000844a  jge     short loc_180008454
0x18000844c  test    ebx, ebx
0x18000844e  jz      loc_180008303
0x180008454  test    ebx, ebx
0x180008456  cmovz   ebx, edi
0x180008459  mov     eax, ebx
0x18000845b  mov     rcx, [rbp+0F90h+var_40]
0x180008462  xor     rcx, rsp; StackCookie
0x180008465  call    __security_check_cookie
0x18000846a  add     rsp, 1068h
0x180008471  pop     r14
0x180008473  pop     r12
0x180008475  pop     rdi
0x180008476  pop     rsi
0x180008477  pop     rbx
0x180008478  pop     rbp
0x180008479  retn
```
