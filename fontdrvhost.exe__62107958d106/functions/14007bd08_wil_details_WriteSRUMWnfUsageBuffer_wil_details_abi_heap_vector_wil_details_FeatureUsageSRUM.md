# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14007bd08`
- end: `0x14007bed2`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140076f80`

## callees

- `0x140075de0`
- `0x14007680c`
- `0x14007bd08`
- `0x14007bf68`
- `0x14007bfe0`
- `0x140096170`

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
0x14007bd08  push    rbp
0x14007bd0a  push    rbx
0x14007bd0b  push    rsi
0x14007bd0c  push    rdi
0x14007bd0d  push    r12
0x14007bd0f  push    r14
0x14007bd11  lea     rbp, [rsp-0F68h]
0x14007bd19  mov     eax, 1068h
0x14007bd1e  call    _alloca_probe
0x14007bd23  sub     rsp, rax
0x14007bd26  mov     rax, cs:__security_cookie
0x14007bd2d  xor     rax, rsp
0x14007bd30  mov     [rbp+0F90h+var_40], rax
0x14007bd37  mov     rax, [rcx+8]
0x14007bd3b  xor     ebx, ebx
0x14007bd3d  sub     rax, [rcx]
0x14007bd40  xor     edi, edi
0x14007bd42  mov     r14, rcx
0x14007bd45  cmp     rax, 0Ch
0x14007bd49  jb      loc_14007BEAC
0x14007bd4f  xor     esi, esi
0x14007bd51  mov     r12, 0AAAAAAAAAAAAAAABh
0x14007bd5b  xor     edx, edx; Val
0x14007bd5d  lea     rcx, [rsp+1090h+var_1040]; void *
0x14007bd62  mov     r8d, 1000h; Size
0x14007bd68  call    memset_0
0x14007bd6d  lea     rax, [rsp+1090h+var_1050]
0x14007bd72  mov     [rsp+1090h+var_1050], 1000h
0x14007bd7a  mov     [rsp+1090h+var_1068], rax
0x14007bd7f  lea     r9, [rsp+1090h+var_104C]
0x14007bd84  lea     rax, [rsp+1090h+var_1040]
0x14007bd89  mov     [rsp+1090h+var_104C], 0
0x14007bd91  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14007bd98  mov     [rsp+1090h+var_1070], rax
0x14007bd9d  call    wil_details_NtQueryWnfStateData
0x14007bda2  mov     ebx, eax
0x14007bda4  test    eax, eax
0x14007bda6  jnz     loc_14007BE95
0x14007bdac  mov     r9d, [rsp+1090h+var_1050]
0x14007bdb1  mov     rax, r12
0x14007bdb4  mul     r9
0x14007bdb7  shr     rdx, 3
0x14007bdbb  lea     rcx, [rdx+rdx*2]
0x14007bdbf  shl     rcx, 2
0x14007bdc3  cmp     r9, rcx
0x14007bdc6  jz      short loc_14007BDD0
0x14007bdc8  xor     r9d, r9d
0x14007bdcb  mov     [rsp+1090h+var_1050], r9d
0x14007bdd0  mov     r8, [r14]
0x14007bdd3  mov     rax, r12
0x14007bdd6  mov     ecx, r9d
0x14007bdd9  mul     rcx
0x14007bddc  mov     rcx, [r14+8]
0x14007bde0  mov     rax, r12
0x14007bde3  mov     r11, rdx
0x14007bde6  sub     rcx, r8
0x14007bde9  mul     rcx
0x14007bdec  shr     r11, 3
0x14007bdf0  shr     rdx, 3
0x14007bdf4  lea     rax, [rdx+rdx*2]
0x14007bdf8  lea     rdi, [r8+rax*4]
0x14007bdfc  jmp     short loc_14007BE6A
0x14007bdfe  mov     eax, r11d
0x14007be01  lea     r10, [rsp+1090h+var_1040]
0x14007be06  lea     rcx, [rax+rax*2]
0x14007be0a  lea     r10, [r10+rcx*4]
0x14007be0e  cmp     rdx, r10
0x14007be11  jz      short loc_14007BE39
0x14007be13  mov     eax, [r8]
0x14007be16  cmp     [rdx], eax
0x14007be18  jnz     short loc_14007BE25
0x14007be1a  movzx   eax, word ptr [r8+4]
0x14007be1f  cmp     [rdx+4], ax
0x14007be23  jz      short loc_14007BE2B
0x14007be25  add     rdx, 0Ch
0x14007be29  jmp     short loc_14007BE0E
0x14007be2b  mov     eax, [r8+8]
0x14007be2f  add     [rdx+8], eax
0x14007be32  mov     r9d, [rsp+1090h+var_1050]
0x14007be37  jmp     short loc_14007BE66
0x14007be39  mov     eax, r9d
0x14007be3c  add     rax, 0Ch
0x14007be40  cmp     rax, 1000h
0x14007be46  ja      short loc_14007BE66
0x14007be48  movsd   xmm0, qword ptr [r8]
0x14007be4d  add     r9d, 0Ch
0x14007be51  movsd   qword ptr [r10], xmm0
0x14007be56  inc     r11d
0x14007be59  mov     eax, [r8+8]
0x14007be5d  mov     [r10+8], eax
0x14007be61  mov     [rsp+1090h+var_1050], r9d
0x14007be66  add     r8, 0Ch
0x14007be6a  lea     rdx, [rsp+1090h+var_1040]
0x14007be6f  cmp     r8, rdi
0x14007be72  jnz     short loc_14007BDFE
0x14007be74  mov     eax, [rsp+1090h+var_104C]
0x14007be78  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14007be7f  mov     [rsp+1090h+var_1060], 1
0x14007be87  mov     r8d, r9d
0x14007be8a  mov     dword ptr [rsp+1090h+var_1068], eax
0x14007be8e  call    wil_details_NtUpdateWnfStateData
0x14007be93  mov     edi, eax
0x14007be95  cmp     edi, 0C0000001h
0x14007be9b  jnz     short loc_14007BEAC
0x14007be9d  inc     esi
0x14007be9f  cmp     esi, 64h ; 'd'
0x14007bea2  jge     short loc_14007BEAC
0x14007bea4  test    ebx, ebx
0x14007bea6  jz      loc_14007BD5B
0x14007beac  test    ebx, ebx
0x14007beae  cmovz   ebx, edi
0x14007beb1  mov     eax, ebx
0x14007beb3  mov     rcx, [rbp+0F90h+var_40]
0x14007beba  xor     rcx, rsp; StackCookie
0x14007bebd  call    __security_check_cookie
0x14007bec2  add     rsp, 1068h
0x14007bec9  pop     r14
0x14007becb  pop     r12
0x14007becd  pop     rdi
0x14007bece  pop     rsi
0x14007becf  pop     rbx
0x14007bed0  pop     rbp
0x14007bed1  retn
```
