# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180015b8c`
- end: `0x180015d56`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180012580`

## callees

- `0x18000fa10`
- `0x18001039c`
- `0x180015b8c`
- `0x180015ffc`
- `0x180016074`
- `0x180017040`

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
0x180015b8c  push    rbp
0x180015b8e  push    rbx
0x180015b8f  push    rsi
0x180015b90  push    rdi
0x180015b91  push    r12
0x180015b93  push    r14
0x180015b95  lea     rbp, [rsp-0F68h]
0x180015b9d  mov     eax, 1068h
0x180015ba2  call    _alloca_probe
0x180015ba7  sub     rsp, rax
0x180015baa  mov     rax, cs:__security_cookie
0x180015bb1  xor     rax, rsp
0x180015bb4  mov     [rbp+0F90h+var_40], rax
0x180015bbb  mov     rax, [rcx+8]
0x180015bbf  xor     ebx, ebx
0x180015bc1  sub     rax, [rcx]
0x180015bc4  xor     edi, edi
0x180015bc6  mov     r14, rcx
0x180015bc9  cmp     rax, 0Ch
0x180015bcd  jb      loc_180015D30
0x180015bd3  xor     esi, esi
0x180015bd5  mov     r12, 0AAAAAAAAAAAAAAABh
0x180015bdf  xor     edx, edx; Val
0x180015be1  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015be6  mov     r8d, 1000h; Size
0x180015bec  call    memset_0
0x180015bf1  lea     rax, [rsp+1090h+var_1050]
0x180015bf6  mov     [rsp+1090h+var_1050], 1000h
0x180015bfe  mov     [rsp+1090h+var_1068], rax
0x180015c03  lea     r9, [rsp+1090h+var_104C]
0x180015c08  lea     rax, [rsp+1090h+var_1040]
0x180015c0d  mov     [rsp+1090h+var_104C], 0
0x180015c15  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015c1c  mov     [rsp+1090h+var_1070], rax
0x180015c21  call    wil_details_NtQueryWnfStateData
0x180015c26  mov     ebx, eax
0x180015c28  test    eax, eax
0x180015c2a  jnz     loc_180015D19
0x180015c30  mov     r9d, [rsp+1090h+var_1050]
0x180015c35  mov     rax, r12
0x180015c38  mul     r9
0x180015c3b  shr     rdx, 3
0x180015c3f  lea     rcx, [rdx+rdx*2]
0x180015c43  shl     rcx, 2
0x180015c47  cmp     r9, rcx
0x180015c4a  jz      short loc_180015C54
0x180015c4c  xor     r9d, r9d
0x180015c4f  mov     [rsp+1090h+var_1050], r9d
0x180015c54  mov     r8, [r14]
0x180015c57  mov     rax, r12
0x180015c5a  mov     ecx, r9d
0x180015c5d  mul     rcx
0x180015c60  mov     rcx, [r14+8]
0x180015c64  mov     rax, r12
0x180015c67  mov     r11, rdx
0x180015c6a  sub     rcx, r8
0x180015c6d  mul     rcx
0x180015c70  shr     r11, 3
0x180015c74  shr     rdx, 3
0x180015c78  lea     rax, [rdx+rdx*2]
0x180015c7c  lea     rdi, [r8+rax*4]
0x180015c80  jmp     short loc_180015CEE
0x180015c82  mov     eax, r11d
0x180015c85  lea     r10, [rsp+1090h+var_1040]
0x180015c8a  lea     rcx, [rax+rax*2]
0x180015c8e  lea     r10, [r10+rcx*4]
0x180015c92  cmp     rdx, r10
0x180015c95  jz      short loc_180015CBD
0x180015c97  mov     eax, [r8]
0x180015c9a  cmp     [rdx], eax
0x180015c9c  jnz     short loc_180015CA9
0x180015c9e  movzx   eax, word ptr [r8+4]
0x180015ca3  cmp     [rdx+4], ax
0x180015ca7  jz      short loc_180015CAF
0x180015ca9  add     rdx, 0Ch
0x180015cad  jmp     short loc_180015C92
0x180015caf  mov     eax, [r8+8]
0x180015cb3  add     [rdx+8], eax
0x180015cb6  mov     r9d, [rsp+1090h+var_1050]
0x180015cbb  jmp     short loc_180015CEA
0x180015cbd  mov     eax, r9d
0x180015cc0  add     rax, 0Ch
0x180015cc4  cmp     rax, 1000h
0x180015cca  ja      short loc_180015CEA
0x180015ccc  movsd   xmm0, qword ptr [r8]
0x180015cd1  add     r9d, 0Ch
0x180015cd5  movsd   qword ptr [r10], xmm0
0x180015cda  inc     r11d
0x180015cdd  mov     eax, [r8+8]
0x180015ce1  mov     [r10+8], eax
0x180015ce5  mov     [rsp+1090h+var_1050], r9d
0x180015cea  add     r8, 0Ch
0x180015cee  lea     rdx, [rsp+1090h+var_1040]
0x180015cf3  cmp     r8, rdi
0x180015cf6  jnz     short loc_180015C82
0x180015cf8  mov     eax, [rsp+1090h+var_104C]
0x180015cfc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015d03  mov     [rsp+1090h+var_1060], 1
0x180015d0b  mov     r8d, r9d
0x180015d0e  mov     dword ptr [rsp+1090h+var_1068], eax
0x180015d12  call    wil_details_NtUpdateWnfStateData
0x180015d17  mov     edi, eax
0x180015d19  cmp     edi, 0C0000001h
0x180015d1f  jnz     short loc_180015D30
0x180015d21  inc     esi
0x180015d23  cmp     esi, 64h ; 'd'
0x180015d26  jge     short loc_180015D30
0x180015d28  test    ebx, ebx
0x180015d2a  jz      loc_180015BDF
0x180015d30  test    ebx, ebx
0x180015d32  cmovz   ebx, edi
0x180015d35  mov     eax, ebx
0x180015d37  mov     rcx, [rbp+0F90h+var_40]
0x180015d3e  xor     rcx, rsp; StackCookie
0x180015d41  call    __security_check_cookie
0x180015d46  add     rsp, 1068h
0x180015d4d  pop     r14
0x180015d4f  pop     r12
0x180015d51  pop     rdi
0x180015d52  pop     rsi
0x180015d53  pop     rbx
0x180015d54  pop     rbp
0x180015d55  retn
```
