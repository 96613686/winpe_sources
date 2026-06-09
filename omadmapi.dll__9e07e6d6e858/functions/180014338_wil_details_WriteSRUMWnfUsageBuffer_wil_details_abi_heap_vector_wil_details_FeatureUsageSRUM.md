# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180014338`
- end: `0x18001450e`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180008b50`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x180014338`
- `0x18001c890`
- `0x18001c938`
- `0x1800229a0`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int WnfStateData; // ebx
  unsigned int updated; // edi
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned int v9; // r10d
  unsigned __int64 v10; // rdi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16[3]; // [rsp+44h] [rbp-BCh] BYREF
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
      v16[0] = 0;
      WnfStateData = wil_details_NtQueryWnfStateData(
                       (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                       v5,
                       v6,
                       (__int64)v16,
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
                    v16[0],
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
0x180014338  push    rbp
0x18001433a  push    rbx
0x18001433b  push    rsi
0x18001433c  push    rdi
0x18001433d  push    r12
0x18001433f  push    r14
0x180014341  lea     rbp, [rsp-0F68h]
0x180014349  mov     eax, 1068h
0x18001434e  call    _alloca_probe
0x180014353  sub     rsp, rax
0x180014356  mov     rax, cs:__security_cookie
0x18001435d  xor     rax, rsp
0x180014360  mov     [rbp+0F90h+var_40], rax
0x180014367  mov     rax, [rcx+8]
0x18001436b  xor     ebx, ebx
0x18001436d  sub     rax, [rcx]
0x180014370  xor     edi, edi
0x180014372  mov     r14, rcx
0x180014375  cmp     rax, 0Ch
0x180014379  jb      loc_1800144D9
0x18001437f  xor     esi, esi
0x180014381  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001438b  xor     edx, edx; Val
0x18001438d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180014392  mov     r8d, 1000h; Size
0x180014398  call    memset_0
0x18001439d  lea     rax, [rsp+1090h+var_1050]
0x1800143a2  mov     [rsp+1090h+var_1050], 1000h
0x1800143aa  mov     [rsp+1090h+var_1068], rax
0x1800143af  lea     r9, [rsp+1090h+var_104C]
0x1800143b4  lea     rax, [rsp+1090h+var_1040]
0x1800143b9  mov     [rsp+1090h+var_104C], 0
0x1800143c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800143c8  mov     [rsp+1090h+var_1070], rax
0x1800143cd  call    wil_details_NtQueryWnfStateData
0x1800143d2  mov     ebx, eax
0x1800143d4  test    eax, eax
0x1800143d6  jnz     loc_1800144C2
0x1800143dc  mov     r9d, [rsp+1090h+var_1050]
0x1800143e1  mov     rax, r12
0x1800143e4  mul     r9
0x1800143e7  shr     rdx, 3
0x1800143eb  lea     rcx, [rdx+rdx*2]
0x1800143ef  shl     rcx, 2
0x1800143f3  cmp     r9, rcx
0x1800143f6  jz      short loc_180014400
0x1800143f8  xor     r9d, r9d
0x1800143fb  mov     [rsp+1090h+var_1050], r9d
0x180014400  mov     r8, [r14]
0x180014403  mov     rax, r12
0x180014406  mov     ecx, r9d
0x180014409  mul     rcx
0x18001440c  mov     rcx, [r14+8]
0x180014410  mov     rax, r12
0x180014413  mov     r10, rdx
0x180014416  sub     rcx, r8
0x180014419  mul     rcx
0x18001441c  shr     r10, 3
0x180014420  shr     rdx, 3
0x180014424  lea     rax, [rdx+rdx*2]
0x180014428  lea     rdi, [r8+rax*4]
0x18001442c  jmp     short loc_180014497
0x18001442e  mov     eax, r10d
0x180014431  lea     rcx, [rax+rax*2]
0x180014435  lea     rdx, [rdx+rcx*4]
0x180014439  lea     rax, [rsp+1090h+var_1040]
0x18001443e  cmp     rax, rdx
0x180014441  jz      short loc_180014468
0x180014443  mov     r11d, [r8]
0x180014446  lea     rcx, [rsp+1090h+var_1040]
0x18001444b  cmp     [rcx], r11d
0x18001444e  jnz     short loc_18001445F
0x180014450  movzx   eax, word ptr [r8+4]
0x180014455  cmp     [rcx+4], ax
0x180014459  jz      loc_180014500
0x18001445f  add     rcx, 0Ch
0x180014463  cmp     rcx, rdx
0x180014466  jnz     short loc_18001444B
0x180014468  mov     eax, r9d
0x18001446b  add     rax, 0Ch
0x18001446f  cmp     rax, 1000h
0x180014475  ja      short loc_180014493
0x180014477  movsd   xmm0, qword ptr [r8]
0x18001447c  add     r9d, 0Ch
0x180014480  movsd   qword ptr [rdx], xmm0
0x180014484  inc     r10d
0x180014487  mov     eax, [r8+8]
0x18001448b  mov     [rdx+8], eax
0x18001448e  mov     [rsp+1090h+var_1050], r9d
0x180014493  add     r8, 0Ch
0x180014497  lea     rdx, [rsp+1090h+var_1040]
0x18001449c  cmp     r8, rdi
0x18001449f  jnz     short loc_18001442E
0x1800144a1  mov     eax, [rsp+1090h+var_104C]
0x1800144a5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800144ac  mov     [rsp+1090h+var_1060], 1
0x1800144b4  mov     r8d, r9d
0x1800144b7  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800144bb  call    wil_details_NtUpdateWnfStateData
0x1800144c0  mov     edi, eax
0x1800144c2  cmp     edi, 0C0000001h
0x1800144c8  jnz     short loc_1800144D9
0x1800144ca  inc     esi
0x1800144cc  cmp     esi, 64h ; 'd'
0x1800144cf  jge     short loc_1800144D9
0x1800144d1  test    ebx, ebx
0x1800144d3  jz      loc_18001438B
0x1800144d9  test    ebx, ebx
0x1800144db  cmovz   ebx, edi
0x1800144de  mov     eax, ebx
0x1800144e0  mov     rcx, [rbp+0F90h+var_40]
0x1800144e7  xor     rcx, rsp; StackCookie
0x1800144ea  call    __security_check_cookie
0x1800144ef  add     rsp, 1068h
0x1800144f6  pop     r14
0x1800144f8  pop     r12
0x1800144fa  pop     rdi
0x1800144fb  pop     rsi
0x1800144fc  pop     rbx
0x1800144fd  pop     rbp
0x1800144fe  retn
0x180014500  mov     eax, [r8+8]
0x180014504  add     [rcx+8], eax
0x180014507  mov     r9d, [rsp+1090h+var_1050]
0x18001450c  jmp     short loc_180014493
```
