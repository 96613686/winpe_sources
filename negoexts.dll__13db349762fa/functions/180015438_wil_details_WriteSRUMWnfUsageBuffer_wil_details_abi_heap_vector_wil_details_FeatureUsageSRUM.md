# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180015438`
- end: `0x180015602`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010060`

## callees

- `0x180015438`
- `0x1800165d4`
- `0x18001664c`
- `0x18001ecee`
- `0x18001ed20`
- `0x18001edb0`

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
0x180015438  push    rbp
0x18001543a  push    rbx
0x18001543b  push    rsi
0x18001543c  push    rdi
0x18001543d  push    r12
0x18001543f  push    r14
0x180015441  lea     rbp, [rsp-0F68h]
0x180015449  mov     eax, 1068h
0x18001544e  call    _alloca_probe
0x180015453  sub     rsp, rax
0x180015456  mov     rax, cs:__security_cookie
0x18001545d  xor     rax, rsp
0x180015460  mov     [rbp+0F90h+var_40], rax
0x180015467  mov     rax, [rcx+8]
0x18001546b  xor     ebx, ebx
0x18001546d  sub     rax, [rcx]
0x180015470  xor     edi, edi
0x180015472  mov     r14, rcx
0x180015475  cmp     rax, 0Ch
0x180015479  jb      loc_1800155DC
0x18001547f  xor     esi, esi
0x180015481  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001548b  xor     edx, edx; Val
0x18001548d  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015492  mov     r8d, 1000h; Size
0x180015498  call    memset_0
0x18001549d  lea     rax, [rsp+1090h+var_1050]
0x1800154a2  mov     [rsp+1090h+var_1050], 1000h
0x1800154aa  mov     [rsp+1090h+var_1068], rax
0x1800154af  lea     r9, [rsp+1090h+var_104C]
0x1800154b4  lea     rax, [rsp+1090h+var_1040]
0x1800154b9  mov     [rsp+1090h+var_104C], 0
0x1800154c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800154c8  mov     [rsp+1090h+var_1070], rax
0x1800154cd  call    wil_details_NtQueryWnfStateData
0x1800154d2  mov     ebx, eax
0x1800154d4  test    eax, eax
0x1800154d6  jnz     loc_1800155C5
0x1800154dc  mov     r9d, [rsp+1090h+var_1050]
0x1800154e1  mov     rax, r12
0x1800154e4  mul     r9
0x1800154e7  shr     rdx, 3
0x1800154eb  lea     rcx, [rdx+rdx*2]
0x1800154ef  shl     rcx, 2
0x1800154f3  cmp     r9, rcx
0x1800154f6  jz      short loc_180015500
0x1800154f8  xor     r9d, r9d
0x1800154fb  mov     [rsp+1090h+var_1050], r9d
0x180015500  mov     r8, [r14]
0x180015503  mov     rax, r12
0x180015506  mov     ecx, r9d
0x180015509  mul     rcx
0x18001550c  mov     rcx, [r14+8]
0x180015510  mov     rax, r12
0x180015513  mov     r11, rdx
0x180015516  sub     rcx, r8
0x180015519  mul     rcx
0x18001551c  shr     r11, 3
0x180015520  shr     rdx, 3
0x180015524  lea     rax, [rdx+rdx*2]
0x180015528  lea     rdi, [r8+rax*4]
0x18001552c  jmp     short loc_18001559A
0x18001552e  mov     eax, r11d
0x180015531  lea     r10, [rsp+1090h+var_1040]
0x180015536  lea     rcx, [rax+rax*2]
0x18001553a  lea     r10, [r10+rcx*4]
0x18001553e  cmp     rdx, r10
0x180015541  jz      short loc_180015569
0x180015543  mov     eax, [r8]
0x180015546  cmp     [rdx], eax
0x180015548  jnz     short loc_180015555
0x18001554a  movzx   eax, word ptr [r8+4]
0x18001554f  cmp     [rdx+4], ax
0x180015553  jz      short loc_18001555B
0x180015555  add     rdx, 0Ch
0x180015559  jmp     short loc_18001553E
0x18001555b  mov     eax, [r8+8]
0x18001555f  add     [rdx+8], eax
0x180015562  mov     r9d, [rsp+1090h+var_1050]
0x180015567  jmp     short loc_180015596
0x180015569  mov     eax, r9d
0x18001556c  add     rax, 0Ch
0x180015570  cmp     rax, 1000h
0x180015576  ja      short loc_180015596
0x180015578  movsd   xmm0, qword ptr [r8]
0x18001557d  add     r9d, 0Ch
0x180015581  movsd   qword ptr [r10], xmm0
0x180015586  inc     r11d
0x180015589  mov     eax, [r8+8]
0x18001558d  mov     [r10+8], eax
0x180015591  mov     [rsp+1090h+var_1050], r9d
0x180015596  add     r8, 0Ch
0x18001559a  lea     rdx, [rsp+1090h+var_1040]
0x18001559f  cmp     r8, rdi
0x1800155a2  jnz     short loc_18001552E
0x1800155a4  mov     eax, [rsp+1090h+var_104C]
0x1800155a8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800155af  mov     [rsp+1090h+var_1060], 1
0x1800155b7  mov     r8d, r9d
0x1800155ba  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800155be  call    wil_details_NtUpdateWnfStateData
0x1800155c3  mov     edi, eax
0x1800155c5  cmp     edi, 0C0000001h
0x1800155cb  jnz     short loc_1800155DC
0x1800155cd  inc     esi
0x1800155cf  cmp     esi, 64h ; 'd'
0x1800155d2  jge     short loc_1800155DC
0x1800155d4  test    ebx, ebx
0x1800155d6  jz      loc_18001548B
0x1800155dc  test    ebx, ebx
0x1800155de  cmovz   ebx, edi
0x1800155e1  mov     eax, ebx
0x1800155e3  mov     rcx, [rbp+0F90h+var_40]
0x1800155ea  xor     rcx, rsp; StackCookie
0x1800155ed  call    __security_check_cookie
0x1800155f2  add     rsp, 1068h
0x1800155f9  pop     r14
0x1800155fb  pop     r12
0x1800155fd  pop     rdi
0x1800155fe  pop     rsi
0x1800155ff  pop     rbx
0x180015600  pop     rbp
0x180015601  retn
```
