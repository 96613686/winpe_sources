# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000d838`
- end: `0x14000da02`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140003300`

## callees

- `0x140002de3`
- `0x14000d838`
- `0x14000e88c`
- `0x14000e904`
- `0x140025d70`
- `0x140025e30`

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
0x14000d838  push    rbp
0x14000d83a  push    rbx
0x14000d83b  push    rsi
0x14000d83c  push    rdi
0x14000d83d  push    r12
0x14000d83f  push    r14
0x14000d841  lea     rbp, [rsp-0F68h]
0x14000d849  mov     eax, 1068h
0x14000d84e  call    _alloca_probe
0x14000d853  sub     rsp, rax
0x14000d856  mov     rax, cs:__security_cookie
0x14000d85d  xor     rax, rsp
0x14000d860  mov     [rbp+0F90h+var_40], rax
0x14000d867  mov     rax, [rcx+8]
0x14000d86b  xor     ebx, ebx
0x14000d86d  sub     rax, [rcx]
0x14000d870  xor     edi, edi
0x14000d872  mov     r14, rcx
0x14000d875  cmp     rax, 0Ch
0x14000d879  jb      loc_14000D9DC
0x14000d87f  xor     esi, esi
0x14000d881  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000d88b  xor     edx, edx; Val
0x14000d88d  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000d892  mov     r8d, 1000h; Size
0x14000d898  call    memset_0
0x14000d89d  lea     rax, [rsp+1090h+var_1050]
0x14000d8a2  mov     [rsp+1090h+var_1050], 1000h
0x14000d8aa  mov     [rsp+1090h+var_1068], rax
0x14000d8af  lea     r9, [rsp+1090h+var_104C]
0x14000d8b4  lea     rax, [rsp+1090h+var_1040]
0x14000d8b9  mov     [rsp+1090h+var_104C], 0
0x14000d8c1  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d8c8  mov     [rsp+1090h+var_1070], rax
0x14000d8cd  call    wil_details_NtQueryWnfStateData
0x14000d8d2  mov     ebx, eax
0x14000d8d4  test    eax, eax
0x14000d8d6  jnz     loc_14000D9C5
0x14000d8dc  mov     r9d, [rsp+1090h+var_1050]
0x14000d8e1  mov     rax, r12
0x14000d8e4  mul     r9
0x14000d8e7  shr     rdx, 3
0x14000d8eb  lea     rcx, [rdx+rdx*2]
0x14000d8ef  shl     rcx, 2
0x14000d8f3  cmp     r9, rcx
0x14000d8f6  jz      short loc_14000D900
0x14000d8f8  xor     r9d, r9d
0x14000d8fb  mov     [rsp+1090h+var_1050], r9d
0x14000d900  mov     r8, [r14]
0x14000d903  mov     rax, r12
0x14000d906  mov     ecx, r9d
0x14000d909  mul     rcx
0x14000d90c  mov     rcx, [r14+8]
0x14000d910  mov     rax, r12
0x14000d913  mov     r11, rdx
0x14000d916  sub     rcx, r8
0x14000d919  mul     rcx
0x14000d91c  shr     r11, 3
0x14000d920  shr     rdx, 3
0x14000d924  lea     rax, [rdx+rdx*2]
0x14000d928  lea     rdi, [r8+rax*4]
0x14000d92c  jmp     short loc_14000D99A
0x14000d92e  mov     eax, r11d
0x14000d931  lea     r10, [rsp+1090h+var_1040]
0x14000d936  lea     rcx, [rax+rax*2]
0x14000d93a  lea     r10, [r10+rcx*4]
0x14000d93e  cmp     rdx, r10
0x14000d941  jz      short loc_14000D969
0x14000d943  mov     eax, [r8]
0x14000d946  cmp     [rdx], eax
0x14000d948  jnz     short loc_14000D955
0x14000d94a  movzx   eax, word ptr [r8+4]
0x14000d94f  cmp     [rdx+4], ax
0x14000d953  jz      short loc_14000D95B
0x14000d955  add     rdx, 0Ch
0x14000d959  jmp     short loc_14000D93E
0x14000d95b  mov     eax, [r8+8]
0x14000d95f  add     [rdx+8], eax
0x14000d962  mov     r9d, [rsp+1090h+var_1050]
0x14000d967  jmp     short loc_14000D996
0x14000d969  mov     eax, r9d
0x14000d96c  add     rax, 0Ch
0x14000d970  cmp     rax, 1000h
0x14000d976  ja      short loc_14000D996
0x14000d978  movsd   xmm0, qword ptr [r8]
0x14000d97d  add     r9d, 0Ch
0x14000d981  movsd   qword ptr [r10], xmm0
0x14000d986  inc     r11d
0x14000d989  mov     eax, [r8+8]
0x14000d98d  mov     [r10+8], eax
0x14000d991  mov     [rsp+1090h+var_1050], r9d
0x14000d996  add     r8, 0Ch
0x14000d99a  lea     rdx, [rsp+1090h+var_1040]
0x14000d99f  cmp     r8, rdi
0x14000d9a2  jnz     short loc_14000D92E
0x14000d9a4  mov     eax, [rsp+1090h+var_104C]
0x14000d9a8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d9af  mov     [rsp+1090h+var_1060], 1
0x14000d9b7  mov     r8d, r9d
0x14000d9ba  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000d9be  call    wil_details_NtUpdateWnfStateData
0x14000d9c3  mov     edi, eax
0x14000d9c5  cmp     edi, 0C0000001h
0x14000d9cb  jnz     short loc_14000D9DC
0x14000d9cd  inc     esi
0x14000d9cf  cmp     esi, 64h ; 'd'
0x14000d9d2  jge     short loc_14000D9DC
0x14000d9d4  test    ebx, ebx
0x14000d9d6  jz      loc_14000D88B
0x14000d9dc  test    ebx, ebx
0x14000d9de  cmovz   ebx, edi
0x14000d9e1  mov     eax, ebx
0x14000d9e3  mov     rcx, [rbp+0F90h+var_40]
0x14000d9ea  xor     rcx, rsp; StackCookie
0x14000d9ed  call    __security_check_cookie
0x14000d9f2  add     rsp, 1068h
0x14000d9f9  pop     r14
0x14000d9fb  pop     r12
0x14000d9fd  pop     rdi
0x14000d9fe  pop     rsi
0x14000d9ff  pop     rbx
0x14000da00  pop     rbp
0x14000da01  retn
```
