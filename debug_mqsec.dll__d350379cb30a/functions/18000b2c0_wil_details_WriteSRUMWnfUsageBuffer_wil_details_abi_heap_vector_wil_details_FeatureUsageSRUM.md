# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b2c0`
- end: `0x18000b495`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180004b90`

## callees

- `0x18000b2c0`
- `0x18000b550`
- `0x18000b5c8`
- `0x18002f0ba`
- `0x18002f0e0`
- `0x18002f1a0`

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
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
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
0x18000b2c0  push    rbp
0x18000b2c2  push    rbx
0x18000b2c3  push    rsi
0x18000b2c4  push    rdi
0x18000b2c5  push    r12
0x18000b2c7  push    r14
0x18000b2c9  lea     rbp, [rsp-0F68h]
0x18000b2d1  mov     eax, 1068h
0x18000b2d6  call    _alloca_probe
0x18000b2db  sub     rsp, rax
0x18000b2de  mov     rax, cs:__security_cookie
0x18000b2e5  xor     rax, rsp
0x18000b2e8  mov     [rbp+0F90h+var_40], rax
0x18000b2ef  mov     rax, [rcx+8]
0x18000b2f3  xor     ebx, ebx
0x18000b2f5  sub     rax, [rcx]
0x18000b2f8  xor     edi, edi
0x18000b2fa  mov     r14, rcx
0x18000b2fd  cmp     rax, 0Ch
0x18000b301  jb      loc_18000B461
0x18000b307  xor     esi, esi
0x18000b309  mov     r12, 0AAAAAAAAAAAAAAABh
0x18000b313  xor     edx, edx; Val
0x18000b315  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b31a  mov     r8d, 1000h; Size
0x18000b320  call    memset_0
0x18000b325  lea     rax, [rsp+1090h+var_1050]
0x18000b32a  mov     [rsp+1090h+var_1050], 1000h
0x18000b332  mov     [rsp+1090h+var_1068], rax
0x18000b337  lea     r9, [rsp+1090h+var_104C]
0x18000b33c  lea     rax, [rsp+1090h+var_1040]
0x18000b341  mov     [rsp+1090h+var_104C], 0
0x18000b349  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b350  mov     [rsp+1090h+var_1070], rax
0x18000b355  call    wil_details_NtQueryWnfStateData
0x18000b35a  mov     ebx, eax
0x18000b35c  test    eax, eax
0x18000b35e  jnz     loc_18000B44A
0x18000b364  mov     r9d, [rsp+1090h+var_1050]
0x18000b369  mov     rax, r12
0x18000b36c  mul     r9
0x18000b36f  shr     rdx, 3
0x18000b373  lea     rcx, [rdx+rdx*2]
0x18000b377  shl     rcx, 2
0x18000b37b  cmp     r9, rcx
0x18000b37e  jz      short loc_18000B388
0x18000b380  xor     r9d, r9d
0x18000b383  mov     [rsp+1090h+var_1050], r9d
0x18000b388  mov     r8, [r14]
0x18000b38b  mov     rax, r12
0x18000b38e  mov     ecx, r9d
0x18000b391  mul     rcx
0x18000b394  mov     rcx, [r14+8]
0x18000b398  mov     rax, r12
0x18000b39b  mov     r10, rdx
0x18000b39e  sub     rcx, r8
0x18000b3a1  mul     rcx
0x18000b3a4  shr     r10, 3
0x18000b3a8  shr     rdx, 3
0x18000b3ac  lea     rax, [rdx+rdx*2]
0x18000b3b0  lea     rdi, [r8+rax*4]
0x18000b3b4  jmp     short loc_18000B41F
0x18000b3b6  mov     eax, r10d
0x18000b3b9  lea     rcx, [rax+rax*2]
0x18000b3bd  lea     rdx, [rdx+rcx*4]
0x18000b3c1  lea     rax, [rsp+1090h+var_1040]
0x18000b3c6  cmp     rax, rdx
0x18000b3c9  jz      short loc_18000B3F0
0x18000b3cb  mov     r11d, [r8]
0x18000b3ce  lea     rcx, [rsp+1090h+var_1040]
0x18000b3d3  cmp     [rcx], r11d
0x18000b3d6  jnz     short loc_18000B3E7
0x18000b3d8  movzx   eax, word ptr [r8+4]
0x18000b3dd  cmp     [rcx+4], ax
0x18000b3e1  jz      loc_18000B487
0x18000b3e7  add     rcx, 0Ch
0x18000b3eb  cmp     rcx, rdx
0x18000b3ee  jnz     short loc_18000B3D3
0x18000b3f0  mov     eax, r9d
0x18000b3f3  add     rax, 0Ch
0x18000b3f7  cmp     rax, 1000h
0x18000b3fd  ja      short loc_18000B41B
0x18000b3ff  movsd   xmm0, qword ptr [r8]
0x18000b404  add     r9d, 0Ch
0x18000b408  movsd   qword ptr [rdx], xmm0
0x18000b40c  inc     r10d
0x18000b40f  mov     eax, [r8+8]
0x18000b413  mov     [rdx+8], eax
0x18000b416  mov     [rsp+1090h+var_1050], r9d
0x18000b41b  add     r8, 0Ch
0x18000b41f  lea     rdx, [rsp+1090h+var_1040]
0x18000b424  cmp     r8, rdi
0x18000b427  jnz     short loc_18000B3B6
0x18000b429  mov     eax, [rsp+1090h+var_104C]
0x18000b42d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b434  mov     [rsp+1090h+var_1060], 1
0x18000b43c  mov     r8d, r9d
0x18000b43f  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b443  call    wil_details_NtUpdateWnfStateData
0x18000b448  mov     edi, eax
0x18000b44a  cmp     edi, 0C0000001h
0x18000b450  jnz     short loc_18000B461
0x18000b452  inc     esi
0x18000b454  cmp     esi, 64h ; 'd'
0x18000b457  jge     short loc_18000B461
0x18000b459  test    ebx, ebx
0x18000b45b  jz      loc_18000B313
0x18000b461  test    ebx, ebx
0x18000b463  cmovz   ebx, edi
0x18000b466  mov     eax, ebx
0x18000b468  mov     rcx, [rbp+0F90h+var_40]
0x18000b46f  xor     rcx, rsp; StackCookie
0x18000b472  call    __security_check_cookie
0x18000b477  add     rsp, 1068h
0x18000b47e  pop     r14
0x18000b480  pop     r12
0x18000b482  pop     rdi
0x18000b483  pop     rsi
0x18000b484  pop     rbx
0x18000b485  pop     rbp
0x18000b486  retn
0x18000b487  mov     eax, [r8+8]
0x18000b48b  add     [rcx+8], eax
0x18000b48e  mov     r9d, [rsp+1090h+var_1050]
0x18000b493  jmp     short loc_18000B41B
```
