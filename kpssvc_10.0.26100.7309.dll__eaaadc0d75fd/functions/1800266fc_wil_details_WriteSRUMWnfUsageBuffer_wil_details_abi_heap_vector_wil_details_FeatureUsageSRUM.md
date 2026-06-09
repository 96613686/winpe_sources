# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800266fc`
- end: `0x1800268e9`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001b3b0`

## callees

- `0x1800266fc`
- `0x1800273cc`
- `0x180027474`
- `0x18003100e`
- `0x180031040`
- `0x180031100`

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
      v16[0] = 0;
      v15 = 4096;
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
          v12 = v17;
          if ( v17 == v11 )
          {
LABEL_11:
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
            while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
            {
              v12 += 3;
              if ( v12 == v11 )
                goto LABEL_11;
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
      ++v4;
    }
    while ( updated == -1073741823 && v4 < 100 && !WnfStateData );
  }
  if ( !WnfStateData )
    return updated;
  return WnfStateData;
}

```

## disassembly

```asm
0x1800266fc  mov     rax, rsp
0x1800266ff  mov     [rax+8], rbx
0x180026703  mov     [rax+10h], rsi
0x180026707  mov     [rax+18h], rdi
0x18002670b  push    rbp
0x18002670c  push    r12
0x18002670e  push    r14
0x180026710  lea     rbp, [rax-0F78h]
0x180026717  mov     eax, 1060h
0x18002671c  call    _alloca_probe
0x180026721  sub     rsp, rax
0x180026724  mov     rax, cs:__security_cookie
0x18002672b  xor     rax, rsp
0x18002672e  mov     [rbp+0F70h+var_20], rax
0x180026735  mov     rax, [rcx+8]
0x180026739  xor     ebx, ebx
0x18002673b  sub     rax, [rcx]
0x18002673e  xor     edi, edi
0x180026740  mov     r14, rcx
0x180026743  cmp     rax, 0Ch
0x180026747  jb      loc_1800268A4
0x18002674d  xor     esi, esi
0x18002674f  mov     r12, 0AAAAAAAAAAAAAAABh
0x180026759  xor     edx, edx; Val
0x18002675b  lea     rcx, [rsp+1070h+var_1020]; void *
0x180026760  mov     r8d, 1000h; Size
0x180026766  call    memset_0
0x18002676b  and     [rsp+1070h+var_102C], 0
0x180026770  lea     rax, [rsp+1070h+var_1030]
0x180026775  mov     qword ptr [rsp+1070h+var_1048], rax
0x18002677a  lea     r9, [rsp+1070h+var_102C]
0x18002677f  lea     rax, [rsp+1070h+var_1020]
0x180026784  mov     [rsp+1070h+var_1030], 1000h
0x18002678c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180026793  mov     [rsp+1070h+var_1050], rax
0x180026798  call    wil_details_NtQueryWnfStateData
0x18002679d  mov     ebx, eax
0x18002679f  test    eax, eax
0x1800267a1  jnz     loc_18002688D
0x1800267a7  mov     r9d, [rsp+1070h+var_1030]
0x1800267ac  mov     rax, r12
0x1800267af  mul     r9
0x1800267b2  shr     rdx, 3
0x1800267b6  lea     rcx, [rdx+rdx*2]
0x1800267ba  shl     rcx, 2
0x1800267be  cmp     r9, rcx
0x1800267c1  jz      short loc_1800267CB
0x1800267c3  xor     r9d, r9d
0x1800267c6  mov     [rsp+1070h+var_1030], r9d
0x1800267cb  mov     r8, [r14]
0x1800267ce  mov     rax, r12
0x1800267d1  mov     ecx, r9d
0x1800267d4  mul     rcx
0x1800267d7  mov     rcx, [r14+8]
0x1800267db  mov     rax, r12
0x1800267de  mov     r10, rdx
0x1800267e1  sub     rcx, r8
0x1800267e4  mul     rcx
0x1800267e7  shr     r10, 3
0x1800267eb  shr     rdx, 3
0x1800267ef  lea     rax, [rdx+rdx*2]
0x1800267f3  lea     rdi, [r8+rax*4]
0x1800267f7  jmp     short loc_180026862
0x1800267f9  mov     eax, r10d
0x1800267fc  lea     rcx, [rax+rax*2]
0x180026800  lea     rdx, [rdx+rcx*4]
0x180026804  lea     rax, [rsp+1070h+var_1020]
0x180026809  lea     rcx, [rsp+1070h+var_1020]
0x18002680e  cmp     rax, rdx
0x180026811  jz      short loc_180026833
0x180026813  mov     r11d, [r8]
0x180026816  cmp     [rcx], r11d
0x180026819  jnz     short loc_18002682A
0x18002681b  movzx   eax, word ptr [r8+4]
0x180026820  cmp     [rcx+4], ax
0x180026824  jz      loc_1800268D8
0x18002682a  add     rcx, 0Ch
0x18002682e  cmp     rcx, rdx
0x180026831  jnz     short loc_180026816
0x180026833  mov     eax, r9d
0x180026836  add     rax, 0Ch
0x18002683a  cmp     rax, 1000h
0x180026840  ja      short loc_18002685E
0x180026842  movsd   xmm0, qword ptr [r8]
0x180026847  add     r9d, 0Ch
0x18002684b  movsd   qword ptr [rdx], xmm0
0x18002684f  inc     r10d
0x180026852  mov     eax, [r8+8]
0x180026856  mov     [rdx+8], eax
0x180026859  mov     [rsp+1070h+var_1030], r9d
0x18002685e  add     r8, 0Ch
0x180026862  lea     rdx, [rsp+1070h+var_1020]
0x180026867  cmp     r8, rdi
0x18002686a  jnz     short loc_1800267F9
0x18002686c  mov     eax, [rsp+1070h+var_102C]
0x180026870  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180026877  mov     [rsp+1070h+var_1040], 1
0x18002687f  mov     r8d, r9d
0x180026882  mov     [rsp+1070h+var_1048], eax
0x180026886  call    wil_details_NtUpdateWnfStateData
0x18002688b  mov     edi, eax
0x18002688d  inc     esi
0x18002688f  cmp     edi, 0C0000001h
0x180026895  jnz     short loc_1800268A4
0x180026897  cmp     esi, 64h ; 'd'
0x18002689a  jge     short loc_1800268A4
0x18002689c  test    ebx, ebx
0x18002689e  jz      loc_180026759
0x1800268a4  test    ebx, ebx
0x1800268a6  cmovz   ebx, edi
0x1800268a9  mov     eax, ebx
0x1800268ab  mov     rcx, [rbp+0F70h+var_20]
0x1800268b2  xor     rcx, rsp; StackCookie
0x1800268b5  call    __security_check_cookie
0x1800268ba  lea     r11, [rsp+1070h+var_10]
0x1800268c2  mov     rbx, [r11+20h]
0x1800268c6  mov     rsi, [r11+28h]
0x1800268ca  mov     rdi, [r11+30h]
0x1800268ce  mov     rsp, r11
0x1800268d1  pop     r14
0x1800268d3  pop     r12
0x1800268d5  pop     rbp
0x1800268d6  retn
0x1800268d8  mov     eax, [r8+8]
0x1800268dc  add     [rcx+8], eax
0x1800268df  mov     r9d, [rsp+1070h+var_1030]
0x1800268e4  jmp     loc_18002685E
```
