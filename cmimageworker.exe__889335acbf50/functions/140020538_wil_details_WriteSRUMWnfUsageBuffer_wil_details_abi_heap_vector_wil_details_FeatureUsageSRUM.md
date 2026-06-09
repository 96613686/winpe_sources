# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140020538`
- end: `0x14002070e`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000fba0`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x140020538`
- `0x140020714`
- `0x1400207bc`
- `0x14002e860`

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
0x140020538  push    rbp
0x14002053a  push    rbx
0x14002053b  push    rsi
0x14002053c  push    rdi
0x14002053d  push    r12
0x14002053f  push    r14
0x140020541  lea     rbp, [rsp-0F68h]
0x140020549  mov     eax, 1068h
0x14002054e  call    _alloca_probe
0x140020553  sub     rsp, rax
0x140020556  mov     rax, cs:__security_cookie
0x14002055d  xor     rax, rsp
0x140020560  mov     [rbp+0F90h+var_40], rax
0x140020567  mov     rax, [rcx+8]
0x14002056b  xor     ebx, ebx
0x14002056d  sub     rax, [rcx]
0x140020570  xor     edi, edi
0x140020572  mov     r14, rcx
0x140020575  cmp     rax, 0Ch
0x140020579  jb      loc_1400206D9
0x14002057f  xor     esi, esi
0x140020581  mov     r12, 0AAAAAAAAAAAAAAABh
0x14002058b  xor     edx, edx; Val
0x14002058d  lea     rcx, [rsp+1090h+var_1040]; void *
0x140020592  mov     r8d, 1000h; Size
0x140020598  call    memset_0
0x14002059d  lea     rax, [rsp+1090h+var_1050]
0x1400205a2  mov     [rsp+1090h+var_1050], 1000h
0x1400205aa  mov     [rsp+1090h+var_1068], rax
0x1400205af  lea     r9, [rsp+1090h+var_104C]
0x1400205b4  lea     rax, [rsp+1090h+var_1040]
0x1400205b9  mov     [rsp+1090h+var_104C], 0
0x1400205c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400205c8  mov     [rsp+1090h+var_1070], rax
0x1400205cd  call    wil_details_NtQueryWnfStateData
0x1400205d2  mov     ebx, eax
0x1400205d4  test    eax, eax
0x1400205d6  jnz     loc_1400206C2
0x1400205dc  mov     r9d, [rsp+1090h+var_1050]
0x1400205e1  mov     rax, r12
0x1400205e4  mul     r9
0x1400205e7  shr     rdx, 3
0x1400205eb  lea     rcx, [rdx+rdx*2]
0x1400205ef  shl     rcx, 2
0x1400205f3  cmp     r9, rcx
0x1400205f6  jz      short loc_140020600
0x1400205f8  xor     r9d, r9d
0x1400205fb  mov     [rsp+1090h+var_1050], r9d
0x140020600  mov     r8, [r14]
0x140020603  mov     rax, r12
0x140020606  mov     ecx, r9d
0x140020609  mul     rcx
0x14002060c  mov     rcx, [r14+8]
0x140020610  mov     rax, r12
0x140020613  mov     r10, rdx
0x140020616  sub     rcx, r8
0x140020619  mul     rcx
0x14002061c  shr     r10, 3
0x140020620  shr     rdx, 3
0x140020624  lea     rax, [rdx+rdx*2]
0x140020628  lea     rdi, [r8+rax*4]
0x14002062c  jmp     short loc_140020697
0x14002062e  mov     eax, r10d
0x140020631  lea     rcx, [rax+rax*2]
0x140020635  lea     rdx, [rdx+rcx*4]
0x140020639  lea     rax, [rsp+1090h+var_1040]
0x14002063e  cmp     rax, rdx
0x140020641  jz      short loc_140020668
0x140020643  mov     r11d, [r8]
0x140020646  lea     rcx, [rsp+1090h+var_1040]
0x14002064b  cmp     [rcx], r11d
0x14002064e  jnz     short loc_14002065F
0x140020650  movzx   eax, word ptr [r8+4]
0x140020655  cmp     [rcx+4], ax
0x140020659  jz      loc_140020700
0x14002065f  add     rcx, 0Ch
0x140020663  cmp     rcx, rdx
0x140020666  jnz     short loc_14002064B
0x140020668  mov     eax, r9d
0x14002066b  add     rax, 0Ch
0x14002066f  cmp     rax, 1000h
0x140020675  ja      short loc_140020693
0x140020677  movsd   xmm0, qword ptr [r8]
0x14002067c  add     r9d, 0Ch
0x140020680  movsd   qword ptr [rdx], xmm0
0x140020684  inc     r10d
0x140020687  mov     eax, [r8+8]
0x14002068b  mov     [rdx+8], eax
0x14002068e  mov     [rsp+1090h+var_1050], r9d
0x140020693  add     r8, 0Ch
0x140020697  lea     rdx, [rsp+1090h+var_1040]
0x14002069c  cmp     r8, rdi
0x14002069f  jnz     short loc_14002062E
0x1400206a1  mov     eax, [rsp+1090h+var_104C]
0x1400206a5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1400206ac  mov     [rsp+1090h+var_1060], 1
0x1400206b4  mov     r8d, r9d
0x1400206b7  mov     dword ptr [rsp+1090h+var_1068], eax
0x1400206bb  call    wil_details_NtUpdateWnfStateData
0x1400206c0  mov     edi, eax
0x1400206c2  cmp     edi, 0C0000001h
0x1400206c8  jnz     short loc_1400206D9
0x1400206ca  inc     esi
0x1400206cc  cmp     esi, 64h ; 'd'
0x1400206cf  jge     short loc_1400206D9
0x1400206d1  test    ebx, ebx
0x1400206d3  jz      loc_14002058B
0x1400206d9  test    ebx, ebx
0x1400206db  cmovz   ebx, edi
0x1400206de  mov     eax, ebx
0x1400206e0  mov     rcx, [rbp+0F90h+var_40]
0x1400206e7  xor     rcx, rsp; StackCookie
0x1400206ea  call    __security_check_cookie
0x1400206ef  add     rsp, 1068h
0x1400206f6  pop     r14
0x1400206f8  pop     r12
0x1400206fa  pop     rdi
0x1400206fb  pop     rsi
0x1400206fc  pop     rbx
0x1400206fd  pop     rbp
0x1400206fe  retn
0x140020700  mov     eax, [r8+8]
0x140020704  add     [rcx+8], eax
0x140020707  mov     r9d, [rsp+1090h+var_1050]
0x14002070c  jmp     short loc_140020693
```
