# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a8c8`
- end: `0x14000aa9d`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140006ab0`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x14000a8c8`
- `0x14000b2cc`
- `0x14000b344`
- `0x140017670`

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
0x14000a8c8  push    rbp
0x14000a8ca  push    rbx
0x14000a8cb  push    rsi
0x14000a8cc  push    rdi
0x14000a8cd  push    r12
0x14000a8cf  push    r14
0x14000a8d1  lea     rbp, [rsp-0F68h]
0x14000a8d9  mov     eax, 1068h
0x14000a8de  call    _alloca_probe
0x14000a8e3  sub     rsp, rax
0x14000a8e6  mov     rax, cs:__security_cookie
0x14000a8ed  xor     rax, rsp
0x14000a8f0  mov     [rbp+0F90h+var_40], rax
0x14000a8f7  mov     rax, [rcx+8]
0x14000a8fb  xor     ebx, ebx
0x14000a8fd  sub     rax, [rcx]
0x14000a900  xor     edi, edi
0x14000a902  mov     r14, rcx
0x14000a905  cmp     rax, 0Ch
0x14000a909  jb      loc_14000AA69
0x14000a90f  xor     esi, esi
0x14000a911  mov     r12, 0AAAAAAAAAAAAAAABh
0x14000a91b  xor     edx, edx; Val
0x14000a91d  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a922  mov     r8d, 1000h; Size
0x14000a928  call    memset_0
0x14000a92d  lea     rax, [rsp+1090h+var_1050]
0x14000a932  mov     [rsp+1090h+var_1050], 1000h
0x14000a93a  mov     [rsp+1090h+var_1068], rax
0x14000a93f  lea     r9, [rsp+1090h+var_104C]
0x14000a944  lea     rax, [rsp+1090h+var_1040]
0x14000a949  mov     [rsp+1090h+var_104C], 0
0x14000a951  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000a958  mov     [rsp+1090h+var_1070], rax
0x14000a95d  call    wil_details_NtQueryWnfStateData
0x14000a962  mov     ebx, eax
0x14000a964  test    eax, eax
0x14000a966  jnz     loc_14000AA52
0x14000a96c  mov     r9d, [rsp+1090h+var_1050]
0x14000a971  mov     rax, r12
0x14000a974  mul     r9
0x14000a977  shr     rdx, 3
0x14000a97b  lea     rcx, [rdx+rdx*2]
0x14000a97f  shl     rcx, 2
0x14000a983  cmp     r9, rcx
0x14000a986  jz      short loc_14000A990
0x14000a988  xor     r9d, r9d
0x14000a98b  mov     [rsp+1090h+var_1050], r9d
0x14000a990  mov     r8, [r14]
0x14000a993  mov     rax, r12
0x14000a996  mov     ecx, r9d
0x14000a999  mul     rcx
0x14000a99c  mov     rcx, [r14+8]
0x14000a9a0  mov     rax, r12
0x14000a9a3  mov     r10, rdx
0x14000a9a6  sub     rcx, r8
0x14000a9a9  mul     rcx
0x14000a9ac  shr     r10, 3
0x14000a9b0  shr     rdx, 3
0x14000a9b4  lea     rax, [rdx+rdx*2]
0x14000a9b8  lea     rdi, [r8+rax*4]
0x14000a9bc  jmp     short loc_14000AA27
0x14000a9be  mov     eax, r10d
0x14000a9c1  lea     rcx, [rax+rax*2]
0x14000a9c5  lea     rdx, [rdx+rcx*4]
0x14000a9c9  lea     rax, [rsp+1090h+var_1040]
0x14000a9ce  cmp     rax, rdx
0x14000a9d1  jz      short loc_14000A9F8
0x14000a9d3  mov     r11d, [r8]
0x14000a9d6  lea     rcx, [rsp+1090h+var_1040]
0x14000a9db  cmp     [rcx], r11d
0x14000a9de  jnz     short loc_14000A9EF
0x14000a9e0  movzx   eax, word ptr [r8+4]
0x14000a9e5  cmp     [rcx+4], ax
0x14000a9e9  jz      loc_14000AA8F
0x14000a9ef  add     rcx, 0Ch
0x14000a9f3  cmp     rcx, rdx
0x14000a9f6  jnz     short loc_14000A9DB
0x14000a9f8  mov     eax, r9d
0x14000a9fb  add     rax, 0Ch
0x14000a9ff  cmp     rax, 1000h
0x14000aa05  ja      short loc_14000AA23
0x14000aa07  movsd   xmm0, qword ptr [r8]
0x14000aa0c  add     r9d, 0Ch
0x14000aa10  movsd   qword ptr [rdx], xmm0
0x14000aa14  inc     r10d
0x14000aa17  mov     eax, [r8+8]
0x14000aa1b  mov     [rdx+8], eax
0x14000aa1e  mov     [rsp+1090h+var_1050], r9d
0x14000aa23  add     r8, 0Ch
0x14000aa27  lea     rdx, [rsp+1090h+var_1040]
0x14000aa2c  cmp     r8, rdi
0x14000aa2f  jnz     short loc_14000A9BE
0x14000aa31  mov     eax, [rsp+1090h+var_104C]
0x14000aa35  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000aa3c  mov     [rsp+1090h+var_1060], 1
0x14000aa44  mov     r8d, r9d
0x14000aa47  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000aa4b  call    wil_details_NtUpdateWnfStateData
0x14000aa50  mov     edi, eax
0x14000aa52  cmp     edi, 0C0000001h
0x14000aa58  jnz     short loc_14000AA69
0x14000aa5a  inc     esi
0x14000aa5c  cmp     esi, 64h ; 'd'
0x14000aa5f  jge     short loc_14000AA69
0x14000aa61  test    ebx, ebx
0x14000aa63  jz      loc_14000A91B
0x14000aa69  test    ebx, ebx
0x14000aa6b  cmovz   ebx, edi
0x14000aa6e  mov     eax, ebx
0x14000aa70  mov     rcx, [rbp+0F90h+var_40]
0x14000aa77  xor     rcx, rsp; StackCookie
0x14000aa7a  call    __security_check_cookie
0x14000aa7f  add     rsp, 1068h
0x14000aa86  pop     r14
0x14000aa88  pop     r12
0x14000aa8a  pop     rdi
0x14000aa8b  pop     rsi
0x14000aa8c  pop     rbx
0x14000aa8d  pop     rbp
0x14000aa8e  retn
0x14000aa8f  mov     eax, [r8+8]
0x14000aa93  add     [rcx+8], eax
0x14000aa96  mov     r9d, [rsp+1090h+var_1050]
0x14000aa9b  jmp     short loc_14000AA23
```
