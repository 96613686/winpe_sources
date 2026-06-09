# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800126d0`
- end: `0x1800128a5`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000fd20`

## callees

- `0x1800126d0`
- `0x18001290c`
- `0x180012984`
- `0x180018a52`
- `0x180018a80`
- `0x180018b10`

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
0x1800126d0  push    rbp
0x1800126d2  push    rbx
0x1800126d3  push    rsi
0x1800126d4  push    rdi
0x1800126d5  push    r12
0x1800126d7  push    r14
0x1800126d9  lea     rbp, [rsp-0F68h]
0x1800126e1  mov     eax, 1068h
0x1800126e6  call    _alloca_probe
0x1800126eb  sub     rsp, rax
0x1800126ee  mov     rax, cs:__security_cookie
0x1800126f5  xor     rax, rsp
0x1800126f8  mov     [rbp+0F90h+var_40], rax
0x1800126ff  mov     rax, [rcx+8]
0x180012703  xor     ebx, ebx
0x180012705  sub     rax, [rcx]
0x180012708  xor     edi, edi
0x18001270a  mov     r14, rcx
0x18001270d  cmp     rax, 0Ch
0x180012711  jb      loc_180012871
0x180012717  xor     esi, esi
0x180012719  mov     r12, 0AAAAAAAAAAAAAAABh
0x180012723  xor     edx, edx; Val
0x180012725  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001272a  mov     r8d, 1000h; Size
0x180012730  call    memset_0
0x180012735  lea     rax, [rsp+1090h+var_1050]
0x18001273a  mov     [rsp+1090h+var_1050], 1000h
0x180012742  mov     [rsp+1090h+var_1068], rax
0x180012747  lea     r9, [rsp+1090h+var_104C]
0x18001274c  lea     rax, [rsp+1090h+var_1040]
0x180012751  mov     [rsp+1090h+var_104C], 0
0x180012759  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012760  mov     [rsp+1090h+var_1070], rax
0x180012765  call    wil_details_NtQueryWnfStateData
0x18001276a  mov     ebx, eax
0x18001276c  test    eax, eax
0x18001276e  jnz     loc_18001285A
0x180012774  mov     r9d, [rsp+1090h+var_1050]
0x180012779  mov     rax, r12
0x18001277c  mul     r9
0x18001277f  shr     rdx, 3
0x180012783  lea     rcx, [rdx+rdx*2]
0x180012787  shl     rcx, 2
0x18001278b  cmp     r9, rcx
0x18001278e  jz      short loc_180012798
0x180012790  xor     r9d, r9d
0x180012793  mov     [rsp+1090h+var_1050], r9d
0x180012798  mov     r8, [r14]
0x18001279b  mov     rax, r12
0x18001279e  mov     ecx, r9d
0x1800127a1  mul     rcx
0x1800127a4  mov     rcx, [r14+8]
0x1800127a8  mov     rax, r12
0x1800127ab  mov     r10, rdx
0x1800127ae  sub     rcx, r8
0x1800127b1  mul     rcx
0x1800127b4  shr     r10, 3
0x1800127b8  shr     rdx, 3
0x1800127bc  lea     rax, [rdx+rdx*2]
0x1800127c0  lea     rdi, [r8+rax*4]
0x1800127c4  jmp     short loc_18001282F
0x1800127c6  mov     eax, r10d
0x1800127c9  lea     rcx, [rax+rax*2]
0x1800127cd  lea     rdx, [rdx+rcx*4]
0x1800127d1  lea     rax, [rsp+1090h+var_1040]
0x1800127d6  cmp     rax, rdx
0x1800127d9  jz      short loc_180012800
0x1800127db  mov     r11d, [r8]
0x1800127de  lea     rcx, [rsp+1090h+var_1040]
0x1800127e3  cmp     [rcx], r11d
0x1800127e6  jnz     short loc_1800127F7
0x1800127e8  movzx   eax, word ptr [r8+4]
0x1800127ed  cmp     [rcx+4], ax
0x1800127f1  jz      loc_180012897
0x1800127f7  add     rcx, 0Ch
0x1800127fb  cmp     rcx, rdx
0x1800127fe  jnz     short loc_1800127E3
0x180012800  mov     eax, r9d
0x180012803  add     rax, 0Ch
0x180012807  cmp     rax, 1000h
0x18001280d  ja      short loc_18001282B
0x18001280f  movsd   xmm0, qword ptr [r8]
0x180012814  add     r9d, 0Ch
0x180012818  movsd   qword ptr [rdx], xmm0
0x18001281c  inc     r10d
0x18001281f  mov     eax, [r8+8]
0x180012823  mov     [rdx+8], eax
0x180012826  mov     [rsp+1090h+var_1050], r9d
0x18001282b  add     r8, 0Ch
0x18001282f  lea     rdx, [rsp+1090h+var_1040]
0x180012834  cmp     r8, rdi
0x180012837  jnz     short loc_1800127C6
0x180012839  mov     eax, [rsp+1090h+var_104C]
0x18001283d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012844  mov     [rsp+1090h+var_1060], 1
0x18001284c  mov     r8d, r9d
0x18001284f  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012853  call    wil_details_NtUpdateWnfStateData
0x180012858  mov     edi, eax
0x18001285a  cmp     edi, 0C0000001h
0x180012860  jnz     short loc_180012871
0x180012862  inc     esi
0x180012864  cmp     esi, 64h ; 'd'
0x180012867  jge     short loc_180012871
0x180012869  test    ebx, ebx
0x18001286b  jz      loc_180012723
0x180012871  test    ebx, ebx
0x180012873  cmovz   ebx, edi
0x180012876  mov     eax, ebx
0x180012878  mov     rcx, [rbp+0F90h+var_40]
0x18001287f  xor     rcx, rsp; StackCookie
0x180012882  call    __security_check_cookie
0x180012887  add     rsp, 1068h
0x18001288e  pop     r14
0x180012890  pop     r12
0x180012892  pop     rdi
0x180012893  pop     rsi
0x180012894  pop     rbx
0x180012895  pop     rbp
0x180012896  retn
0x180012897  mov     eax, [r8+8]
0x18001289b  add     [rcx+8], eax
0x18001289e  mov     r9d, [rsp+1090h+var_1050]
0x1800128a3  jmp     short loc_18001282B
```
