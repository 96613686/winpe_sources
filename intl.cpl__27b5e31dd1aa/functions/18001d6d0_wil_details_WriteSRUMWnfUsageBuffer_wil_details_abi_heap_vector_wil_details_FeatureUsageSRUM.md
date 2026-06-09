# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001d6d0`
- end: `0x18001d89a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180018cc0`

## callees

- `0x18001d6d0`
- `0x18001de7c`
- `0x18001def4`
- `0x18002a112`
- `0x18002a150`
- `0x18002a210`

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
0x18001d6d0  push    rbp
0x18001d6d2  push    rbx
0x18001d6d3  push    rsi
0x18001d6d4  push    rdi
0x18001d6d5  push    r12
0x18001d6d7  push    r14
0x18001d6d9  lea     rbp, [rsp-0F68h]
0x18001d6e1  mov     eax, 1068h
0x18001d6e6  call    _alloca_probe
0x18001d6eb  sub     rsp, rax
0x18001d6ee  mov     rax, cs:__security_cookie
0x18001d6f5  xor     rax, rsp
0x18001d6f8  mov     [rbp+0F90h+var_40], rax
0x18001d6ff  mov     rax, [rcx+8]
0x18001d703  xor     ebx, ebx
0x18001d705  sub     rax, [rcx]
0x18001d708  xor     edi, edi
0x18001d70a  mov     r14, rcx
0x18001d70d  cmp     rax, 0Ch
0x18001d711  jb      loc_18001D874
0x18001d717  xor     esi, esi
0x18001d719  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001d723  xor     edx, edx; Val
0x18001d725  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001d72a  mov     r8d, 1000h; Size
0x18001d730  call    memset_0
0x18001d735  lea     rax, [rsp+1090h+var_1050]
0x18001d73a  mov     [rsp+1090h+var_1050], 1000h
0x18001d742  mov     [rsp+1090h+var_1068], rax
0x18001d747  lea     r9, [rsp+1090h+var_104C]
0x18001d74c  lea     rax, [rsp+1090h+var_1040]
0x18001d751  mov     [rsp+1090h+var_104C], 0
0x18001d759  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001d760  mov     [rsp+1090h+var_1070], rax
0x18001d765  call    wil_details_NtQueryWnfStateData
0x18001d76a  mov     ebx, eax
0x18001d76c  test    eax, eax
0x18001d76e  jnz     loc_18001D85D
0x18001d774  mov     r9d, [rsp+1090h+var_1050]
0x18001d779  mov     rax, r12
0x18001d77c  mul     r9
0x18001d77f  shr     rdx, 3
0x18001d783  lea     rcx, [rdx+rdx*2]
0x18001d787  shl     rcx, 2
0x18001d78b  cmp     r9, rcx
0x18001d78e  jz      short loc_18001D798
0x18001d790  xor     r9d, r9d
0x18001d793  mov     [rsp+1090h+var_1050], r9d
0x18001d798  mov     r8, [r14]
0x18001d79b  mov     rax, r12
0x18001d79e  mov     ecx, r9d
0x18001d7a1  mul     rcx
0x18001d7a4  mov     rcx, [r14+8]
0x18001d7a8  mov     rax, r12
0x18001d7ab  mov     r11, rdx
0x18001d7ae  sub     rcx, r8
0x18001d7b1  mul     rcx
0x18001d7b4  shr     r11, 3
0x18001d7b8  shr     rdx, 3
0x18001d7bc  lea     rax, [rdx+rdx*2]
0x18001d7c0  lea     rdi, [r8+rax*4]
0x18001d7c4  jmp     short loc_18001D832
0x18001d7c6  mov     eax, r11d
0x18001d7c9  lea     r10, [rsp+1090h+var_1040]
0x18001d7ce  lea     rcx, [rax+rax*2]
0x18001d7d2  lea     r10, [r10+rcx*4]
0x18001d7d6  cmp     rdx, r10
0x18001d7d9  jz      short loc_18001D801
0x18001d7db  mov     eax, [r8]
0x18001d7de  cmp     [rdx], eax
0x18001d7e0  jnz     short loc_18001D7ED
0x18001d7e2  movzx   eax, word ptr [r8+4]
0x18001d7e7  cmp     [rdx+4], ax
0x18001d7eb  jz      short loc_18001D7F3
0x18001d7ed  add     rdx, 0Ch
0x18001d7f1  jmp     short loc_18001D7D6
0x18001d7f3  mov     eax, [r8+8]
0x18001d7f7  add     [rdx+8], eax
0x18001d7fa  mov     r9d, [rsp+1090h+var_1050]
0x18001d7ff  jmp     short loc_18001D82E
0x18001d801  mov     eax, r9d
0x18001d804  add     rax, 0Ch
0x18001d808  cmp     rax, 1000h
0x18001d80e  ja      short loc_18001D82E
0x18001d810  movsd   xmm0, qword ptr [r8]
0x18001d815  add     r9d, 0Ch
0x18001d819  movsd   qword ptr [r10], xmm0
0x18001d81e  inc     r11d
0x18001d821  mov     eax, [r8+8]
0x18001d825  mov     [r10+8], eax
0x18001d829  mov     [rsp+1090h+var_1050], r9d
0x18001d82e  add     r8, 0Ch
0x18001d832  lea     rdx, [rsp+1090h+var_1040]
0x18001d837  cmp     r8, rdi
0x18001d83a  jnz     short loc_18001D7C6
0x18001d83c  mov     eax, [rsp+1090h+var_104C]
0x18001d840  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001d847  mov     [rsp+1090h+var_1060], 1
0x18001d84f  mov     r8d, r9d
0x18001d852  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001d856  call    wil_details_NtUpdateWnfStateData
0x18001d85b  mov     edi, eax
0x18001d85d  cmp     edi, 0C0000001h
0x18001d863  jnz     short loc_18001D874
0x18001d865  inc     esi
0x18001d867  cmp     esi, 64h ; 'd'
0x18001d86a  jge     short loc_18001D874
0x18001d86c  test    ebx, ebx
0x18001d86e  jz      loc_18001D723
0x18001d874  test    ebx, ebx
0x18001d876  cmovz   ebx, edi
0x18001d879  mov     eax, ebx
0x18001d87b  mov     rcx, [rbp+0F90h+var_40]
0x18001d882  xor     rcx, rsp; StackCookie
0x18001d885  call    __security_check_cookie
0x18001d88a  add     rsp, 1068h
0x18001d891  pop     r14
0x18001d893  pop     r12
0x18001d895  pop     rdi
0x18001d896  pop     rsi
0x18001d897  pop     rbx
0x18001d898  pop     rbp
0x18001d899  retn
```
