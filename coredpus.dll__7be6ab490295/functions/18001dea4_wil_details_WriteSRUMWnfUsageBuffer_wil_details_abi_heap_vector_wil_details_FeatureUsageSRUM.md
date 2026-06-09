# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001dea4`
- end: `0x18001e06f`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180016830`

## callees

- `0x180014330`
- `0x180015174`
- `0x18001dea4`
- `0x18001e224`
- `0x18001e29c`
- `0x18002e480`

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
0x18001dea4  push    rbp
0x18001dea6  push    rbx
0x18001dea7  push    rsi
0x18001dea8  push    rdi
0x18001dea9  push    r12
0x18001deab  push    r14
0x18001dead  lea     rbp, [rsp-0F68h]
0x18001deb5  mov     eax, 1068h
0x18001deba  call    _alloca_probe
0x18001debf  sub     rsp, rax
0x18001dec2  mov     rax, cs:__security_cookie
0x18001dec9  xor     rax, rsp
0x18001decc  mov     [rbp+0F90h+var_40], rax
0x18001ded3  mov     rax, [rcx+8]
0x18001ded7  xor     ebx, ebx
0x18001ded9  sub     rax, [rcx]
0x18001dedc  xor     edi, edi
0x18001dede  mov     r14, rcx
0x18001dee1  cmp     rax, 0Ch
0x18001dee5  jb      loc_18001E048
0x18001deeb  xor     esi, esi
0x18001deed  mov     r12, 0AAAAAAAAAAAAAAABh
0x18001def7  xor     edx, edx; Val
0x18001def9  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001defe  mov     r8d, 1000h; Size
0x18001df04  call    memset_0
0x18001df09  lea     rax, [rsp+1090h+var_1050]
0x18001df0e  mov     [rsp+1090h+var_1050], 1000h
0x18001df16  mov     [rsp+1090h+var_1068], rax
0x18001df1b  lea     r9, [rsp+1090h+var_104C]
0x18001df20  lea     rax, [rsp+1090h+var_1040]
0x18001df25  mov     [rsp+1090h+var_104C], 0
0x18001df2d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001df34  mov     [rsp+1090h+var_1070], rax
0x18001df39  call    wil_details_NtQueryWnfStateData
0x18001df3e  mov     ebx, eax
0x18001df40  test    eax, eax
0x18001df42  jnz     loc_18001E031
0x18001df48  mov     r9d, [rsp+1090h+var_1050]
0x18001df4d  mov     rax, r12
0x18001df50  mul     r9
0x18001df53  shr     rdx, 3
0x18001df57  lea     rcx, [rdx+rdx*2]
0x18001df5b  shl     rcx, 2
0x18001df5f  cmp     r9, rcx
0x18001df62  jz      short loc_18001DF6C
0x18001df64  xor     r9d, r9d
0x18001df67  mov     [rsp+1090h+var_1050], r9d
0x18001df6c  mov     r8, [r14]
0x18001df6f  mov     rax, r12
0x18001df72  mov     ecx, r9d
0x18001df75  mul     rcx
0x18001df78  mov     rcx, [r14+8]
0x18001df7c  mov     rax, r12
0x18001df7f  mov     r11, rdx
0x18001df82  sub     rcx, r8
0x18001df85  mul     rcx
0x18001df88  shr     r11, 3
0x18001df8c  shr     rdx, 3
0x18001df90  lea     rax, [rdx+rdx*2]
0x18001df94  lea     rdi, [r8+rax*4]
0x18001df98  jmp     short loc_18001E006
0x18001df9a  mov     eax, r11d
0x18001df9d  lea     r10, [rsp+1090h+var_1040]
0x18001dfa2  lea     rcx, [rax+rax*2]
0x18001dfa6  lea     r10, [r10+rcx*4]
0x18001dfaa  cmp     rdx, r10
0x18001dfad  jz      short loc_18001DFD5
0x18001dfaf  mov     eax, [r8]
0x18001dfb2  cmp     [rdx], eax
0x18001dfb4  jnz     short loc_18001DFC1
0x18001dfb6  movzx   eax, word ptr [r8+4]
0x18001dfbb  cmp     [rdx+4], ax
0x18001dfbf  jz      short loc_18001DFC7
0x18001dfc1  add     rdx, 0Ch
0x18001dfc5  jmp     short loc_18001DFAA
0x18001dfc7  mov     eax, [r8+8]
0x18001dfcb  add     [rdx+8], eax
0x18001dfce  mov     r9d, [rsp+1090h+var_1050]
0x18001dfd3  jmp     short loc_18001E002
0x18001dfd5  mov     eax, r9d
0x18001dfd8  add     rax, 0Ch
0x18001dfdc  cmp     rax, 1000h
0x18001dfe2  ja      short loc_18001E002
0x18001dfe4  movsd   xmm0, qword ptr [r8]
0x18001dfe9  add     r9d, 0Ch
0x18001dfed  movsd   qword ptr [r10], xmm0
0x18001dff2  inc     r11d
0x18001dff5  mov     eax, [r8+8]
0x18001dff9  mov     [r10+8], eax
0x18001dffd  mov     [rsp+1090h+var_1050], r9d
0x18001e002  add     r8, 0Ch
0x18001e006  lea     rdx, [rsp+1090h+var_1040]
0x18001e00b  cmp     r8, rdi
0x18001e00e  jnz     short loc_18001DF9A
0x18001e010  mov     eax, [rsp+1090h+var_104C]
0x18001e014  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001e01b  mov     [rsp+1090h+var_1060], 1
0x18001e023  mov     r8d, r9d
0x18001e026  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001e02a  call    wil_details_NtUpdateWnfStateData
0x18001e02f  mov     edi, eax
0x18001e031  cmp     edi, 0C0000001h
0x18001e037  jnz     short loc_18001E048
0x18001e039  inc     esi
0x18001e03b  cmp     esi, 64h ; 'd'
0x18001e03e  jge     short loc_18001E048
0x18001e040  test    ebx, ebx
0x18001e042  jz      loc_18001DEF7
0x18001e048  test    ebx, ebx
0x18001e04a  cmovz   ebx, edi
0x18001e04d  mov     eax, ebx
0x18001e04f  mov     rcx, [rbp+0F90h+var_40]
0x18001e056  xor     rcx, rsp; StackCookie
0x18001e059  call    __security_check_cookie
0x18001e05e  add     rsp, 1068h
0x18001e065  pop     r14
0x18001e067  pop     r12
0x18001e069  pop     rdi
0x18001e06a  pop     rsi
0x18001e06b  pop     rbx
0x18001e06c  pop     rbp
0x18001e06d  retn
```
