# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008f68`
- end: `0x18000913d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003d30`

## callees

- `0x180008f68`
- `0x18000932c`
- `0x1800093a4`
- `0x180009922`
- `0x180009950`
- `0x1800099e0`

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
        v9 = v7 / 0xC;
        v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
        while ( v8 != v10 )
        {
          v11 = &v17[3 * v9];
          if ( v17 == v11 )
          {
LABEL_12:
            if ( (unsigned __int64)v7 + 12 <= 0x1000 )
            {
              v7 += 12;
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
0x180008f68  push    rbp
0x180008f6a  push    rbx
0x180008f6b  push    rsi
0x180008f6c  push    rdi
0x180008f6d  push    r12
0x180008f6f  push    r14
0x180008f71  lea     rbp, [rsp-0F68h]
0x180008f79  mov     eax, 1068h
0x180008f7e  call    _alloca_probe
0x180008f83  sub     rsp, rax
0x180008f86  mov     rax, cs:__security_cookie
0x180008f8d  xor     rax, rsp
0x180008f90  mov     [rbp+0F90h+var_40], rax
0x180008f97  mov     rax, [rcx+8]
0x180008f9b  xor     ebx, ebx
0x180008f9d  sub     rax, [rcx]
0x180008fa0  xor     edi, edi
0x180008fa2  mov     r14, rcx
0x180008fa5  cmp     rax, 0Ch
0x180008fa9  jb      loc_180009109
0x180008faf  xor     esi, esi
0x180008fb1  mov     r12, 0AAAAAAAAAAAAAAABh
0x180008fbb  xor     edx, edx; Val
0x180008fbd  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008fc2  mov     r8d, 1000h; Size
0x180008fc8  call    memset_0
0x180008fcd  lea     rax, [rsp+1090h+var_1050]
0x180008fd2  mov     [rsp+1090h+var_1050], 1000h
0x180008fda  mov     [rsp+1090h+var_1068], rax
0x180008fdf  lea     r9, [rsp+1090h+var_104C]
0x180008fe4  lea     rax, [rsp+1090h+var_1040]
0x180008fe9  mov     [rsp+1090h+var_104C], 0
0x180008ff1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008ff8  mov     [rsp+1090h+var_1070], rax
0x180008ffd  call    wil_details_NtQueryWnfStateData
0x180009002  mov     ebx, eax
0x180009004  test    eax, eax
0x180009006  jnz     loc_1800090F2
0x18000900c  mov     r9d, [rsp+1090h+var_1050]
0x180009011  mov     rax, r12
0x180009014  mul     r9
0x180009017  shr     rdx, 3
0x18000901b  lea     rcx, [rdx+rdx*2]
0x18000901f  shl     rcx, 2
0x180009023  cmp     r9, rcx
0x180009026  jz      short loc_180009030
0x180009028  xor     r9d, r9d
0x18000902b  mov     [rsp+1090h+var_1050], r9d
0x180009030  mov     r8, [r14]
0x180009033  mov     rax, r12
0x180009036  mov     ecx, r9d
0x180009039  mul     rcx
0x18000903c  mov     rcx, [r14+8]
0x180009040  mov     rax, r12
0x180009043  mov     r10, rdx
0x180009046  sub     rcx, r8
0x180009049  mul     rcx
0x18000904c  shr     r10, 3
0x180009050  shr     rdx, 3
0x180009054  lea     rax, [rdx+rdx*2]
0x180009058  lea     rdi, [r8+rax*4]
0x18000905c  jmp     short loc_1800090C7
0x18000905e  mov     eax, r10d
0x180009061  lea     rcx, [rax+rax*2]
0x180009065  lea     rdx, [rdx+rcx*4]
0x180009069  lea     rax, [rsp+1090h+var_1040]
0x18000906e  cmp     rax, rdx
0x180009071  jz      short loc_180009098
0x180009073  mov     r11d, [r8]
0x180009076  lea     rcx, [rsp+1090h+var_1040]
0x18000907b  cmp     [rcx], r11d
0x18000907e  jnz     short loc_18000908F
0x180009080  movzx   eax, word ptr [r8+4]
0x180009085  cmp     [rcx+4], ax
0x180009089  jz      loc_18000912F
0x18000908f  add     rcx, 0Ch
0x180009093  cmp     rcx, rdx
0x180009096  jnz     short loc_18000907B
0x180009098  mov     eax, r9d
0x18000909b  add     rax, 0Ch
0x18000909f  cmp     rax, 1000h
0x1800090a5  ja      short loc_1800090C3
0x1800090a7  movsd   xmm0, qword ptr [r8]
0x1800090ac  add     r9d, 0Ch
0x1800090b0  movsd   qword ptr [rdx], xmm0
0x1800090b4  inc     r10d
0x1800090b7  mov     eax, [r8+8]
0x1800090bb  mov     [rdx+8], eax
0x1800090be  mov     [rsp+1090h+var_1050], r9d
0x1800090c3  add     r8, 0Ch
0x1800090c7  lea     rdx, [rsp+1090h+var_1040]
0x1800090cc  cmp     r8, rdi
0x1800090cf  jnz     short loc_18000905E
0x1800090d1  mov     eax, [rsp+1090h+var_104C]
0x1800090d5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800090dc  mov     [rsp+1090h+var_1060], 1
0x1800090e4  mov     r8d, r9d
0x1800090e7  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800090eb  call    wil_details_NtUpdateWnfStateData
0x1800090f0  mov     edi, eax
0x1800090f2  cmp     edi, 0C0000001h
0x1800090f8  jnz     short loc_180009109
0x1800090fa  inc     esi
0x1800090fc  cmp     esi, 64h ; 'd'
0x1800090ff  jge     short loc_180009109
0x180009101  test    ebx, ebx
0x180009103  jz      loc_180008FBB
0x180009109  test    ebx, ebx
0x18000910b  cmovz   ebx, edi
0x18000910e  mov     eax, ebx
0x180009110  mov     rcx, [rbp+0F90h+var_40]
0x180009117  xor     rcx, rsp; StackCookie
0x18000911a  call    __security_check_cookie
0x18000911f  add     rsp, 1068h
0x180009126  pop     r14
0x180009128  pop     r12
0x18000912a  pop     rdi
0x18000912b  pop     rsi
0x18000912c  pop     rbx
0x18000912d  pop     rbp
0x18000912e  retn
0x18000912f  mov     eax, [r8+8]
0x180009133  add     [rcx+8], eax
0x180009136  mov     r9d, [rsp+1090h+var_1050]
0x18000913b  jmp     short loc_1800090C3
```
