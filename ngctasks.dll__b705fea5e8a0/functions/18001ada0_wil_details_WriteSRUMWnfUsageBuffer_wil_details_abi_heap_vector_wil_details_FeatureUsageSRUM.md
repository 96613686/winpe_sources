# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001ada0`
- end: `0x18001af6a`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180016ed0`

## callees

- `0x180006330`
- `0x180006e9c`
- `0x18001ada0`
- `0x18001b54c`
- `0x18001b5c4`
- `0x18001e940`

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
0x18001ada0  push    rbp
0x18001ada2  push    rbx
0x18001ada3  push    rsi
0x18001ada4  push    rdi
0x18001ada5  push    r12
0x18001ada7  push    r14
0x18001ada9  lea     rbp, [rsp-0F68h]
0x18001adb1  mov     eax, 1068h
0x18001adb6  call    _alloca_probe
0x18001adbb  sub     rsp, rax
0x18001adbe  mov     rax, cs:__security_cookie
0x18001adc5  xor     rax, rsp
0x18001adc8  mov     [rbp+0F90h+var_40], rax
0x18001adcf  mov     rax, [rcx+8]
0x18001add3  xor     ebx, ebx
0x18001add5  sub     rax, [rcx]
0x18001add8  xor     edi, edi
0x18001adda  mov     r14, rcx
0x18001addd  cmp     rax, 0Ch
0x18001ade1  jb      loc_18001AF44
0x18001ade7  xor     esi, esi
0x18001ade9  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001adf3  xor     edx, edx; Val
0x18001adf5  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001adfa  mov     r8d, 1000h; Size
0x18001ae00  call    memset_0
0x18001ae05  lea     rax, [rsp+1090h+var_1050]
0x18001ae0a  mov     [rsp+1090h+var_1050], 1000h
0x18001ae12  mov     [rsp+1090h+var_1068], rax
0x18001ae17  lea     r9, [rsp+1090h+var_104C]
0x18001ae1c  lea     rax, [rsp+1090h+var_1040]
0x18001ae21  mov     [rsp+1090h+var_104C], 0
0x18001ae29  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001ae30  mov     [rsp+1090h+var_1070], rax
0x18001ae35  call    wil_details_NtQueryWnfStateData
0x18001ae3a  mov     ebx, eax
0x18001ae3c  test    eax, eax
0x18001ae3e  jnz     loc_18001AF2D
0x18001ae44  mov     r9d, [rsp+1090h+var_1050]
0x18001ae49  mov     rax, r12
0x18001ae4c  mul     r9
0x18001ae4f  shr     rdx, 3
0x18001ae53  lea     rcx, [rdx+rdx*2]
0x18001ae57  shl     rcx, 2
0x18001ae5b  cmp     r9, rcx
0x18001ae5e  jz      short loc_18001AE68
0x18001ae60  xor     r9d, r9d
0x18001ae63  mov     [rsp+1090h+var_1050], r9d
0x18001ae68  mov     r8, [r14]
0x18001ae6b  mov     rax, r12
0x18001ae6e  mov     ecx, r9d
0x18001ae71  mul     rcx
0x18001ae74  mov     rcx, [r14+8]
0x18001ae78  mov     rax, r12
0x18001ae7b  mov     r11, rdx
0x18001ae7e  sub     rcx, r8
0x18001ae81  mul     rcx
0x18001ae84  shr     r11, 3
0x18001ae88  shr     rdx, 3
0x18001ae8c  lea     rax, [rdx+rdx*2]
0x18001ae90  lea     rdi, [r8+rax*4]
0x18001ae94  jmp     short loc_18001AF02
0x18001ae96  mov     eax, r11d
0x18001ae99  lea     r10, [rsp+1090h+var_1040]
0x18001ae9e  lea     rcx, [rax+rax*2]
0x18001aea2  lea     r10, [r10+rcx*4]
0x18001aea6  cmp     rdx, r10
0x18001aea9  jz      short loc_18001AED1
0x18001aeab  mov     eax, [r8]
0x18001aeae  cmp     [rdx], eax
0x18001aeb0  jnz     short loc_18001AEBD
0x18001aeb2  movzx   eax, word ptr [r8+4]
0x18001aeb7  cmp     [rdx+4], ax
0x18001aebb  jz      short loc_18001AEC3
0x18001aebd  add     rdx, 0Ch
0x18001aec1  jmp     short loc_18001AEA6
0x18001aec3  mov     eax, [r8+8]
0x18001aec7  add     [rdx+8], eax
0x18001aeca  mov     r9d, [rsp+1090h+var_1050]
0x18001aecf  jmp     short loc_18001AEFE
0x18001aed1  mov     eax, r9d
0x18001aed4  add     rax, 0Ch
0x18001aed8  cmp     rax, 1000h
0x18001aede  ja      short loc_18001AEFE
0x18001aee0  movsd   xmm0, qword ptr [r8]
0x18001aee5  add     r9d, 0Ch
0x18001aee9  movsd   qword ptr [r10], xmm0
0x18001aeee  inc     r11d
0x18001aef1  mov     eax, [r8+8]
0x18001aef5  mov     [r10+8], eax
0x18001aef9  mov     [rsp+1090h+var_1050], r9d
0x18001aefe  add     r8, 0Ch
0x18001af02  lea     rdx, [rsp+1090h+var_1040]
0x18001af07  cmp     r8, rdi
0x18001af0a  jnz     short loc_18001AE96
0x18001af0c  mov     eax, [rsp+1090h+var_104C]
0x18001af10  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001af17  mov     [rsp+1090h+var_1060], 1
0x18001af1f  mov     r8d, r9d
0x18001af22  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001af26  call    wil_details_NtUpdateWnfStateData
0x18001af2b  mov     edi, eax
0x18001af2d  cmp     edi, 0C0000001h
0x18001af33  jnz     short loc_18001AF44
0x18001af35  inc     esi
0x18001af37  cmp     esi, 64h ; 'd'
0x18001af3a  jge     short loc_18001AF44
0x18001af3c  test    ebx, ebx
0x18001af3e  jz      loc_18001ADF3
0x18001af44  test    ebx, ebx
0x18001af46  cmovz   ebx, edi
0x18001af49  mov     eax, ebx
0x18001af4b  mov     rcx, [rbp+0F90h+var_40]
0x18001af52  xor     rcx, rsp; StackCookie
0x18001af55  call    __security_check_cookie
0x18001af5a  add     rsp, 1068h
0x18001af61  pop     r14
0x18001af63  pop     r12
0x18001af65  pop     rdi
0x18001af66  pop     rsi
0x18001af67  pop     rbx
0x18001af68  pop     rbp
0x18001af69  retn
```
