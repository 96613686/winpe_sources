# CIVIAudioFilter::GetParameterValues(_GUID const *,tagVARIANT * *,ulong *)

- ea: `0x18000f480`
- end: `0x18000f6ff`
- name: `?GetParameterValues@CIVIAudioFilter@@UEAAJPEBU_GUID@@PEAPEAUtagVARIANT@@PEAK@Z`
- size: `639`
- prototype: `int(CIVIAudioFilter *__hidden this, const struct _GUID *, struct tagVARIANT **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f480`
- `0x18000f710`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f69c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f69c`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetParameterValues(
        CIVIAudioFilter *this,
        const struct _GUID *a2,
        struct tagVARIANT **a3,
        unsigned int *a4)
{
  __int64 result; // rax
  struct tagVARIANT *v7; // rax
  struct tagVARIANT *v8; // rax
  struct tagVARIANT *v9; // rcx

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4
    || *(_QWORD *)&a2->Data1 == 0x4DC5CFC22B50583DLL && *(_QWORD *)a2->Data4 == 0x693FDCA3C027B2B7LL )
  {
    return 2147746576LL;
  }
  *a3 = 0;
  *a4 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc )
    return CIVIAudioFilter::GetParameterValues_AVDecCommonOutputFormat(this, a3, a4);
  if ( *(_QWORD *)&a2->Data1 == 0x416E4FBFFFFFFFFFLL && *(_QWORD *)a2->Data4 == 0x16661DE94415FF93LL )
  {
    v7 = (struct tagVARIANT *)CoTaskMemAlloc(0x48u);
    if ( !v7 )
      return 2147942414LL;
    v7->lVal = 0;
    v7->vt = 19;
    v7[1].vt = 19;
    v7[2].vt = 19;
    v7[1].lVal = 2;
    v7[2].lVal = 6;
    *a4 = 3;
    *a3 = v7;
    return 0;
  }
  else if ( *(_QWORD *)&a2->Data1 == 0x316B3EBAFFFFFFFFLL && *(_QWORD *)a2->Data4 == 0xD5742DC85426EF23uLL )
  {
    v8 = (struct tagVARIANT *)CoTaskMemAlloc(0x30u);
    v9 = v8;
    if ( !v8 )
      return 2147942414LL;
    v8->iVal = -1;
    v8->vt = 11;
    v8[1].vt = 11;
    result = 0;
    v9[1].iVal = 0;
    *a4 = 2;
    *a3 = v9;
  }
  else
  {
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000f480  mov     [rsp+arg_0], rbx
0x18000f485  push    rdi
0x18000f486  sub     rsp, 20h
0x18000f48a  mov     rbx, r9
0x18000f48d  mov     rdi, r8
0x18000f490  test    rdx, rdx
0x18000f493  jz      loc_18000F6EE
0x18000f499  test    r8, r8
0x18000f49c  jz      loc_18000F6EE
0x18000f4a2  test    rbx, rbx
0x18000f4a5  jz      loc_18000F6EE
0x18000f4ab  mov     rax, [rdx]
0x18000f4ae  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
0x18000f4b5  jnz     short loc_18000F4C8
0x18000f4b7  mov     rax, [rdx+8]
0x18000f4bb  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4
0x18000f4c2  jz      loc_18000F5B5
0x18000f4c8  mov     rax, [rdx]
0x18000f4cb  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
0x18000f4d2  jnz     short loc_18000F4E5
0x18000f4d4  mov     rax, [rdx+8]
0x18000f4d8  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4
0x18000f4df  jz      loc_18000F5B5
0x18000f4e5  mov     rax, [rdx]
0x18000f4e8  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
0x18000f4ef  jnz     short loc_18000F502
0x18000f4f1  mov     rax, [rdx+8]
0x18000f4f5  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4
0x18000f4fc  jz      loc_18000F5B5
0x18000f502  mov     rax, [rdx]
0x18000f505  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
0x18000f50c  jnz     short loc_18000F51F
0x18000f50e  mov     rax, [rdx+8]
0x18000f512  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4
0x18000f519  jz      loc_18000F5B5
0x18000f51f  mov     rax, [rdx]
0x18000f522  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
0x18000f529  jnz     short loc_18000F538
0x18000f52b  mov     rax, [rdx+8]
0x18000f52f  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4
0x18000f536  jz      short loc_18000F5B5
0x18000f538  mov     rax, [rdx]
0x18000f53b  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
0x18000f542  jnz     short loc_18000F551
0x18000f544  mov     rax, [rdx+8]
0x18000f548  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4
0x18000f54f  jz      short loc_18000F5B5
0x18000f551  mov     rax, [rdx]
0x18000f554  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
0x18000f55b  jnz     short loc_18000F56A
0x18000f55d  mov     rax, [rdx+8]
0x18000f561  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4
0x18000f568  jz      short loc_18000F5B5
0x18000f56a  mov     rax, [rdx]
0x18000f56d  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
0x18000f574  jnz     short loc_18000F583
0x18000f576  mov     rax, [rdx+8]
0x18000f57a  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4
0x18000f581  jz      short loc_18000F5B5
0x18000f583  mov     rax, [rdx]
0x18000f586  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
0x18000f58d  jnz     short loc_18000F59C
0x18000f58f  mov     rax, [rdx+8]
0x18000f593  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4
0x18000f59a  jz      short loc_18000F5B5
0x18000f59c  mov     rax, [rdx]
0x18000f59f  cmp     rax, qword ptr cs:stru_18008DAC8.Data1
0x18000f5a6  jnz     short loc_18000F5C6
0x18000f5a8  mov     rax, [rdx+8]
0x18000f5ac  cmp     rax, qword ptr cs:stru_18008DAC8.Data4
0x18000f5b3  jnz     short loc_18000F5C6
0x18000f5b5  mov     eax, 80040310h
0x18000f5ba  mov     rbx, [rsp+28h+arg_0]
0x18000f5bf  add     rsp, 20h
0x18000f5c3  pop     rdi
0x18000f5c4  retn
0x18000f5c6  mov     qword ptr [r8], 0
0x18000f5cd  mov     dword ptr [r9], 0
0x18000f5d4  mov     rax, [rdx]
0x18000f5d7  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data1
0x18000f5de  jnz     short loc_18000F602
0x18000f5e0  mov     rax, [rdx+8]
0x18000f5e4  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data4
0x18000f5eb  jnz     short loc_18000F602
0x18000f5ed  mov     r8, rbx; unsigned int *
0x18000f5f0  mov     rdx, rdi; struct tagVARIANT **
0x18000f5f3  mov     rbx, [rsp+28h+arg_0]
0x18000f5f8  add     rsp, 20h
0x18000f5fc  pop     rdi
0x18000f5fd  jmp     ?GetParameterValues_AVDecCommonOutputFormat@CIVIAudioFilter@@AEAAJPEAPEAUtagVARIANT@@PEAK@Z; CIVIAudioFilter::GetParameterValues_AVDecCommonOutputFormat(tagVARIANT * *,ulong *)
0x18000f602  mov     rax, [rdx]
0x18000f605  cmp     rax, cs:qword_18008DC90
0x18000f60c  jnz     short loc_18000F67E
0x18000f60e  mov     rax, [rdx+8]
0x18000f612  cmp     rax, cs:qword_18008DC98
0x18000f619  jnz     short loc_18000F67E
0x18000f61b  mov     ecx, 48h ; 'H'; cb
0x18000f620  call    cs:__imp_CoTaskMemAlloc
0x18000f627  nop     dword ptr [rax+rax+00h]
0x18000f62c  test    rax, rax
0x18000f62f  jnz     short loc_18000F642
0x18000f631  mov     eax, 8007000Eh
0x18000f636  mov     rbx, [rsp+28h+arg_0]
0x18000f63b  add     rsp, 20h
0x18000f63f  pop     rdi
0x18000f640  retn
0x18000f642  mov     ecx, 13h
0x18000f647  mov     dword ptr [rax+8], 0
0x18000f64e  mov     [rax], cx
0x18000f651  mov     [rax+18h], cx
0x18000f655  mov     [rax+30h], cx
0x18000f659  mov     dword ptr [rax+20h], 2
0x18000f660  mov     dword ptr [rax+38h], 6
0x18000f667  mov     dword ptr [rbx], 3
0x18000f66d  mov     [rdi], rax
0x18000f670  xor     eax, eax
0x18000f672  mov     rbx, [rsp+28h+arg_0]
0x18000f677  add     rsp, 20h
0x18000f67b  pop     rdi
0x18000f67c  retn
0x18000f67e  mov     rax, [rdx]
0x18000f681  cmp     rax, cs:qword_18008DBE0
0x18000f688  jnz     short loc_18000F6DD
0x18000f68a  mov     rax, [rdx+8]
0x18000f68e  cmp     rax, cs:qword_18008DBE8
0x18000f695  jnz     short loc_18000F6DD
0x18000f697  mov     ecx, 30h ; '0'; cb
0x18000f69c  call    cs:__imp_CoTaskMemAlloc
0x18000f6a3  nop     dword ptr [rax+rax+00h]
0x18000f6a8  mov     rcx, rax
0x18000f6ab  test    rax, rax
0x18000f6ae  jz      short loc_18000F631
0x18000f6b0  mov     word ptr [rax+8], 0FFFFh
0x18000f6b6  mov     edx, 0Bh
0x18000f6bb  mov     [rax], dx
0x18000f6be  mov     [rax+18h], dx
0x18000f6c2  xor     eax, eax
0x18000f6c4  mov     [rcx+20h], ax
0x18000f6c8  mov     dword ptr [rbx], 2
0x18000f6ce  mov     [rdi], rcx
0x18000f6d1  mov     rbx, [rsp+28h+arg_0]
0x18000f6d6  add     rsp, 20h
0x18000f6da  pop     rdi
0x18000f6db  retn
0x18000f6dd  mov     eax, 1
0x18000f6e2  mov     rbx, [rsp+28h+arg_0]
0x18000f6e7  add     rsp, 20h
0x18000f6eb  pop     rdi
0x18000f6ec  retn
0x18000f6ee  mov     rbx, [rsp+28h+arg_0]
0x18000f6f3  mov     eax, 80070057h
0x18000f6f8  add     rsp, 20h
0x18000f6fc  pop     rdi
0x18000f6fd  retn
```
