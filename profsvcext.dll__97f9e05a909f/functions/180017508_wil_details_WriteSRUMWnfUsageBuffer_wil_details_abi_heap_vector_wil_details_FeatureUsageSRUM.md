# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180017508`
- end: `0x1800176dd`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010bd0`

## callees

- `0x18000a520`
- `0x18000aef8`
- `0x180017508`
- `0x180017c8c`
- `0x180017d04`
- `0x18001e520`

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
0x180017508  push    rbp
0x18001750a  push    rbx
0x18001750b  push    rsi
0x18001750c  push    rdi
0x18001750d  push    r12
0x18001750f  push    r14
0x180017511  lea     rbp, [rsp-0F68h]
0x180017519  mov     eax, 1068h
0x18001751e  call    _alloca_probe
0x180017523  sub     rsp, rax
0x180017526  mov     rax, cs:__security_cookie
0x18001752d  xor     rax, rsp
0x180017530  mov     [rbp+0F90h+var_40], rax
0x180017537  mov     rax, [rcx+8]
0x18001753b  xor     ebx, ebx
0x18001753d  sub     rax, [rcx]
0x180017540  xor     edi, edi
0x180017542  mov     r14, rcx
0x180017545  cmp     rax, 0Ch
0x180017549  jb      loc_1800176A9
0x18001754f  xor     esi, esi
0x180017551  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001755b  xor     edx, edx; Val
0x18001755d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180017562  mov     r8d, 1000h; Size
0x180017568  call    memset_0
0x18001756d  lea     rax, [rsp+1090h+var_1050]
0x180017572  mov     [rsp+1090h+var_1050], 1000h
0x18001757a  mov     [rsp+1090h+var_1068], rax
0x18001757f  lea     r9, [rsp+1090h+var_104C]
0x180017584  lea     rax, [rsp+1090h+var_1040]
0x180017589  mov     [rsp+1090h+var_104C], 0
0x180017591  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180017598  mov     [rsp+1090h+var_1070], rax
0x18001759d  call    wil_details_NtQueryWnfStateData
0x1800175a2  mov     ebx, eax
0x1800175a4  test    eax, eax
0x1800175a6  jnz     loc_180017692
0x1800175ac  mov     r9d, [rsp+1090h+var_1050]
0x1800175b1  mov     rax, r12
0x1800175b4  mul     r9
0x1800175b7  shr     rdx, 3
0x1800175bb  lea     rcx, [rdx+rdx*2]
0x1800175bf  shl     rcx, 2
0x1800175c3  cmp     r9, rcx
0x1800175c6  jz      short loc_1800175D0
0x1800175c8  xor     r9d, r9d
0x1800175cb  mov     [rsp+1090h+var_1050], r9d
0x1800175d0  mov     r8, [r14]
0x1800175d3  mov     rax, r12
0x1800175d6  mov     ecx, r9d
0x1800175d9  mul     rcx
0x1800175dc  mov     rcx, [r14+8]
0x1800175e0  mov     rax, r12
0x1800175e3  mov     r10, rdx
0x1800175e6  sub     rcx, r8
0x1800175e9  mul     rcx
0x1800175ec  shr     r10, 3
0x1800175f0  shr     rdx, 3
0x1800175f4  lea     rax, [rdx+rdx*2]
0x1800175f8  lea     rdi, [r8+rax*4]
0x1800175fc  jmp     short loc_180017667
0x1800175fe  mov     eax, r10d
0x180017601  lea     rcx, [rax+rax*2]
0x180017605  lea     rdx, [rdx+rcx*4]
0x180017609  lea     rax, [rsp+1090h+var_1040]
0x18001760e  cmp     rax, rdx
0x180017611  jz      short loc_180017638
0x180017613  mov     r11d, [r8]
0x180017616  lea     rcx, [rsp+1090h+var_1040]
0x18001761b  cmp     [rcx], r11d
0x18001761e  jnz     short loc_18001762F
0x180017620  movzx   eax, word ptr [r8+4]
0x180017625  cmp     [rcx+4], ax
0x180017629  jz      loc_1800176CF
0x18001762f  add     rcx, 0Ch
0x180017633  cmp     rcx, rdx
0x180017636  jnz     short loc_18001761B
0x180017638  mov     eax, r9d
0x18001763b  add     rax, 0Ch
0x18001763f  cmp     rax, 1000h
0x180017645  ja      short loc_180017663
0x180017647  movsd   xmm0, qword ptr [r8]
0x18001764c  add     r9d, 0Ch
0x180017650  movsd   qword ptr [rdx], xmm0
0x180017654  inc     r10d
0x180017657  mov     eax, [r8+8]
0x18001765b  mov     [rdx+8], eax
0x18001765e  mov     [rsp+1090h+var_1050], r9d
0x180017663  add     r8, 0Ch
0x180017667  lea     rdx, [rsp+1090h+var_1040]
0x18001766c  cmp     r8, rdi
0x18001766f  jnz     short loc_1800175FE
0x180017671  mov     eax, [rsp+1090h+var_104C]
0x180017675  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001767c  mov     [rsp+1090h+var_1060], 1
0x180017684  mov     r8d, r9d
0x180017687  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001768b  call    wil_details_NtUpdateWnfStateData
0x180017690  mov     edi, eax
0x180017692  cmp     edi, 0C0000001h
0x180017698  jnz     short loc_1800176A9
0x18001769a  inc     esi
0x18001769c  cmp     esi, 64h ; 'd'
0x18001769f  jge     short loc_1800176A9
0x1800176a1  test    ebx, ebx
0x1800176a3  jz      loc_18001755B
0x1800176a9  test    ebx, ebx
0x1800176ab  cmovz   ebx, edi
0x1800176ae  mov     eax, ebx
0x1800176b0  mov     rcx, [rbp+0F90h+var_40]
0x1800176b7  xor     rcx, rsp; StackCookie
0x1800176ba  call    __security_check_cookie
0x1800176bf  add     rsp, 1068h
0x1800176c6  pop     r14
0x1800176c8  pop     r12
0x1800176ca  pop     rdi
0x1800176cb  pop     rsi
0x1800176cc  pop     rbx
0x1800176cd  pop     rbp
0x1800176ce  retn
0x1800176cf  mov     eax, [r8+8]
0x1800176d3  add     [rcx+8], eax
0x1800176d6  mov     r9d, [rsp+1090h+var_1050]
0x1800176db  jmp     short loc_180017663
```
