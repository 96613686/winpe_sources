# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a87c`
- end: `0x14000aa52`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140002c40`

## callees

- `0x14000271f`
- `0x14000a87c`
- `0x14000b5a0`
- `0x14000b648`
- `0x140015690`
- `0x140015750`

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
0x14000a87c  push    rbp
0x14000a87e  push    rbx
0x14000a87f  push    rsi
0x14000a880  push    rdi
0x14000a881  push    r12
0x14000a883  push    r14
0x14000a885  lea     rbp, [rsp-0F68h]
0x14000a88d  mov     eax, 1068h
0x14000a892  call    _alloca_probe
0x14000a897  sub     rsp, rax
0x14000a89a  mov     rax, cs:__security_cookie
0x14000a8a1  xor     rax, rsp
0x14000a8a4  mov     [rbp+0F90h+var_40], rax
0x14000a8ab  mov     rax, [rcx+8]
0x14000a8af  xor     ebx, ebx
0x14000a8b1  sub     rax, [rcx]
0x14000a8b4  xor     edi, edi
0x14000a8b6  mov     r14, rcx
0x14000a8b9  cmp     rax, 0Ch
0x14000a8bd  jb      loc_14000AA1D
0x14000a8c3  xor     esi, esi
0x14000a8c5  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000a8cf  xor     edx, edx; Val
0x14000a8d1  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a8d6  mov     r8d, 1000h; Size
0x14000a8dc  call    memset_0
0x14000a8e1  lea     rax, [rsp+1090h+var_1050]
0x14000a8e6  mov     [rsp+1090h+var_1050], 1000h
0x14000a8ee  mov     [rsp+1090h+var_1068], rax
0x14000a8f3  lea     r9, [rsp+1090h+var_104C]
0x14000a8f8  lea     rax, [rsp+1090h+var_1040]
0x14000a8fd  mov     [rsp+1090h+var_104C], 0
0x14000a905  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a90c  mov     [rsp+1090h+var_1070], rax
0x14000a911  call    wil_details_NtQueryWnfStateData
0x14000a916  mov     ebx, eax
0x14000a918  test    eax, eax
0x14000a91a  jnz     loc_14000AA06
0x14000a920  mov     r9d, [rsp+1090h+var_1050]
0x14000a925  mov     rax, r12
0x14000a928  mul     r9
0x14000a92b  shr     rdx, 3
0x14000a92f  lea     rcx, [rdx+rdx*2]
0x14000a933  shl     rcx, 2
0x14000a937  cmp     r9, rcx
0x14000a93a  jz      short loc_14000A944
0x14000a93c  xor     r9d, r9d
0x14000a93f  mov     [rsp+1090h+var_1050], r9d
0x14000a944  mov     r8, [r14]
0x14000a947  mov     rax, r12
0x14000a94a  mov     ecx, r9d
0x14000a94d  mul     rcx
0x14000a950  mov     rcx, [r14+8]
0x14000a954  mov     rax, r12
0x14000a957  mov     r10, rdx
0x14000a95a  sub     rcx, r8
0x14000a95d  mul     rcx
0x14000a960  shr     r10, 3
0x14000a964  shr     rdx, 3
0x14000a968  lea     rax, [rdx+rdx*2]
0x14000a96c  lea     rdi, [r8+rax*4]
0x14000a970  jmp     short loc_14000A9DB
0x14000a972  mov     eax, r10d
0x14000a975  lea     rcx, [rax+rax*2]
0x14000a979  lea     rdx, [rdx+rcx*4]
0x14000a97d  lea     rax, [rsp+1090h+var_1040]
0x14000a982  cmp     rax, rdx
0x14000a985  jz      short loc_14000A9AC
0x14000a987  mov     r11d, [r8]
0x14000a98a  lea     rcx, [rsp+1090h+var_1040]
0x14000a98f  cmp     [rcx], r11d
0x14000a992  jnz     short loc_14000A9A3
0x14000a994  movzx   eax, word ptr [r8+4]
0x14000a999  cmp     [rcx+4], ax
0x14000a99d  jz      loc_14000AA44
0x14000a9a3  add     rcx, 0Ch
0x14000a9a7  cmp     rcx, rdx
0x14000a9aa  jnz     short loc_14000A98F
0x14000a9ac  mov     eax, r9d
0x14000a9af  add     rax, 0Ch
0x14000a9b3  cmp     rax, 1000h
0x14000a9b9  ja      short loc_14000A9D7
0x14000a9bb  movsd   xmm0, qword ptr [r8]
0x14000a9c0  add     r9d, 0Ch
0x14000a9c4  movsd   qword ptr [rdx], xmm0
0x14000a9c8  inc     r10d
0x14000a9cb  mov     eax, [r8+8]
0x14000a9cf  mov     [rdx+8], eax
0x14000a9d2  mov     [rsp+1090h+var_1050], r9d
0x14000a9d7  add     r8, 0Ch
0x14000a9db  lea     rdx, [rsp+1090h+var_1040]
0x14000a9e0  cmp     r8, rdi
0x14000a9e3  jnz     short loc_14000A972
0x14000a9e5  mov     eax, [rsp+1090h+var_104C]
0x14000a9e9  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a9f0  mov     [rsp+1090h+var_1060], 1
0x14000a9f8  mov     r8d, r9d
0x14000a9fb  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000a9ff  call    wil_details_NtUpdateWnfStateData
0x14000aa04  mov     edi, eax
0x14000aa06  cmp     edi, 0C0000001h
0x14000aa0c  jnz     short loc_14000AA1D
0x14000aa0e  inc     esi
0x14000aa10  cmp     esi, 64h ; 'd'
0x14000aa13  jge     short loc_14000AA1D
0x14000aa15  test    ebx, ebx
0x14000aa17  jz      loc_14000A8CF
0x14000aa1d  test    ebx, ebx
0x14000aa1f  cmovz   ebx, edi
0x14000aa22  mov     eax, ebx
0x14000aa24  mov     rcx, [rbp+0F90h+var_40]
0x14000aa2b  xor     rcx, rsp; StackCookie
0x14000aa2e  call    __security_check_cookie
0x14000aa33  add     rsp, 1068h
0x14000aa3a  pop     r14
0x14000aa3c  pop     r12
0x14000aa3e  pop     rdi
0x14000aa3f  pop     rsi
0x14000aa40  pop     rbx
0x14000aa41  pop     rbp
0x14000aa42  retn
0x14000aa44  mov     eax, [r8+8]
0x14000aa48  add     [rcx+8], eax
0x14000aa4b  mov     r9d, [rsp+1090h+var_1050]
0x14000aa50  jmp     short loc_14000A9D7
```
