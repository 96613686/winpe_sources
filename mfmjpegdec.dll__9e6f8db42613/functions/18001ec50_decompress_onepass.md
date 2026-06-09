# decompress_onepass

- ea: `0x18001ec50`
- end: `0x18001ef15`
- name: `decompress_onepass`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001cab8`
- `0x18001ec50`
- `0x180025060`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall decompress_onepass(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  unsigned int v4; // eax
  int v5; // r14d
  unsigned int v6; // esi
  __int64 v7; // r12
  int v8; // r15d
  int v9; // r13d
  __int64 v10; // rbp
  int v11; // r9d
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int v14; // r15d
  void (__fastcall *v15)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // r10
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // r12d
  int v19; // esi
  int v20; // r14d
  __int64 result; // rax
  int i; // [rsp+30h] [rbp-78h]
  unsigned int v23; // [rsp+34h] [rbp-74h]
  unsigned int v24; // [rsp+38h] [rbp-70h]
  int v25; // [rsp+3Ch] [rbp-6Ch]
  int v26; // [rsp+44h] [rbp-64h]
  __int64 v27; // [rsp+48h] [rbp-60h]
  void (__fastcall *v28)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // [rsp+50h] [rbp-58h]
  __int64 v29; // [rsp+58h] [rbp-50h]
  int v30; // [rsp+B0h] [rbp+8h]
  int v32; // [rsp+C0h] [rbp+18h]
  int v33; // [rsp+C8h] [rbp+20h]

  v3 = *(_QWORD *)(a1 + 528);
  v4 = *(_DWORD *)(a1 + 440) - 1;
  v24 = v4;
  v30 = *(_DWORD *)(a1 + 388) - 1;
  v5 = *(_DWORD *)(v3 + 68);
LABEL_2:
  v25 = v5;
  if ( v5 >= *(_DWORD *)(v3 + 72) )
  {
    ++*(_DWORD *)(a1 + 160);
    ++*(_DWORD *)(a1 + 168);
    if ( *(_DWORD *)(a1 + 160) >= *(_DWORD *)(a1 + 388) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 544) + 24LL))(a1);
      return 4;
    }
    else
    {
      start_iMCU_row_0(a1);
      return 3;
    }
  }
  else
  {
    v6 = *(_DWORD *)(v3 + 64);
    v7 = a1 + 512;
    while ( 1 )
    {
      v23 = v6;
      if ( v6 > v4 )
      {
        *(_DWORD *)(v3 + 64) = 0;
        ++v5;
        goto LABEL_2;
      }
      v29 = v7;
      jzero_far(*(_QWORD *)(v3 + 80), (__int64)*(int *)(a1 + 448) << 7);
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 560) + 32LL) )
        *(_DWORD *)(*(_QWORD *)v7 + 112LL) = *(_DWORD *)(a1 + 160);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 560) + 8LL))(a1, v3 + 80) )
        break;
      if ( v6 >= *(_DWORD *)(*(_QWORD *)v7 + 20LL) && v6 <= *(_DWORD *)(*(_QWORD *)v7 + 24LL) )
      {
        v8 = 0;
        v9 = 0;
        for ( i = 0; v8 < *(_DWORD *)(a1 + 400); i = v8 )
        {
          v10 = *(_QWORD *)(a1 + 8LL * v8 + 408);
          if ( *(_BYTE *)(v10 + 48) )
          {
            if ( *(int *)(v10 + 56) > 0 )
            {
              v11 = *(_DWORD *)((-(__int64)(v6 < v24) & 0xFFFFFFFFFFFFFFF0uLL) + v10 + 68);
              v12 = *(int *)(v10 + 4);
              v13 = *(_DWORD *)(v10 + 36);
              v14 = v30;
              v32 = v11;
              v15 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)(a1 + 568) + 8 * v12 + 8);
              v28 = v15;
              v16 = *(_QWORD *)(a2 + 8 * v12) + 8LL * v5 * v13;
              v27 = v16;
              v17 = *(_DWORD *)(v10 + 64) * (v6 - *(_DWORD *)(*(_QWORD *)v7 + 20LL));
              v18 = 0;
              v33 = 0;
              v26 = v17;
              do
              {
                if ( *(_DWORD *)(a1 + 160) < v14 || v5 + v18 < *(_DWORD *)(v10 + 72) )
                {
                  v19 = v17;
                  if ( v11 > 0 )
                  {
                    v20 = 0;
                    do
                    {
                      v15(a1, v10, *(_QWORD *)(v3 + 8LL * (v20 + v9) + 80), v27, v19);
                      v13 = *(_DWORD *)(v10 + 36);
                      ++v20;
                      v15 = v28;
                      v19 += v13;
                    }
                    while ( v20 < v32 );
                    v5 = v25;
                    v18 = v33;
                    v14 = v30;
                    v16 = v27;
                    v17 = v26;
                    v11 = v32;
                  }
                }
                v9 += *(_DWORD *)(v10 + 52);
                v33 = ++v18;
                v16 += 8LL * v13;
                v27 = v16;
              }
              while ( v18 < *(_DWORD *)(v10 + 56) );
              v6 = v23;
              v8 = i;
              v7 = v29;
            }
          }
          else
          {
            v9 += *(_DWORD *)(v10 + 60);
          }
          ++v8;
        }
      }
      v4 = v24;
      ++v6;
    }
    *(_DWORD *)(v3 + 68) = v5;
    result = 0;
    *(_DWORD *)(v3 + 64) = v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001ec50  mov     [rsp+arg_8], rdx
0x18001ec55  push    rbx
0x18001ec56  push    rbp
0x18001ec57  push    rsi
0x18001ec58  push    rdi
0x18001ec59  push    r12
0x18001ec5b  push    r13
0x18001ec5d  push    r14
0x18001ec5f  push    r15
0x18001ec61  sub     rsp, 68h
0x18001ec65  mov     eax, [rcx+1B8h]
0x18001ec6b  mov     rbx, rcx
0x18001ec6e  mov     rdi, [rcx+210h]
0x18001ec75  dec     eax
0x18001ec77  mov     ecx, [rcx+184h]
0x18001ec7d  dec     ecx
0x18001ec7f  mov     [rsp+0A8h+var_70], eax
0x18001ec83  mov     [rsp+0A8h+arg_0], ecx
0x18001ec8a  mov     r14d, [rdi+44h]
0x18001ec8e  mov     [rsp+0A8h+var_6C], r14d
0x18001ec93  cmp     r14d, [rdi+48h]
0x18001ec97  jge     loc_18001EEC6
0x18001ec9d  mov     esi, [rdi+40h]
0x18001eca0  lea     r12, [rbx+200h]
0x18001eca7  mov     [rsp+0A8h+var_74], esi
0x18001ecab  cmp     esi, eax
0x18001ecad  ja      loc_18001EEAC
0x18001ecb3  movsxd  rdx, dword ptr [rbx+1C0h]
0x18001ecba  mov     rcx, [rdi+50h]
0x18001ecbe  shl     rdx, 7
0x18001ecc2  mov     [rsp+0A8h+var_50], r12
0x18001ecc7  call    jzero_far
0x18001eccc  mov     rax, [rbx+230h]
0x18001ecd3  cmp     byte ptr [rax+20h], 0
0x18001ecd7  jnz     short loc_18001ECE6
0x18001ecd9  mov     rcx, [r12]
0x18001ecdd  mov     eax, [rbx+0A0h]
0x18001ece3  mov     [rcx+70h], eax
0x18001ece6  mov     rax, [rbx+230h]
0x18001eced  lea     rdx, [rdi+50h]
0x18001ecf1  mov     rcx, rbx
0x18001ecf4  mov     rax, [rax+8]
0x18001ecf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecfd  test    al, al
0x18001ecff  jz      loc_18001EEBB
0x18001ed05  mov     rax, [r12]
0x18001ed09  cmp     esi, [rax+14h]
0x18001ed0c  jb      loc_18001EEA1
0x18001ed12  cmp     esi, [rax+18h]
0x18001ed15  ja      loc_18001EEA1
0x18001ed1b  xor     r15d, r15d
0x18001ed1e  xor     r13d, r13d
0x18001ed21  mov     [rsp+0A8h+var_78], r15d
0x18001ed26  cmp     [rbx+190h], r13d
0x18001ed2d  jle     loc_18001EEA1
0x18001ed33  movsxd  rax, r15d
0x18001ed36  mov     rbp, [rbx+rax*8+198h]
0x18001ed3e  cmp     byte ptr [rbp+30h], 0
0x18001ed42  jnz     short loc_18001ED4D
0x18001ed44  add     r13d, [rbp+3Ch]
0x18001ed48  jmp     loc_18001EE8C
0x18001ed4d  cmp     esi, [rsp+0A8h+var_70]
0x18001ed51  sbb     rcx, rcx
0x18001ed54  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001ed58  cmp     dword ptr [rbp+38h], 0
0x18001ed5c  jle     loc_18001EE8C
0x18001ed62  mov     r9d, [rcx+rbp+44h]
0x18001ed67  movsxd  rdx, dword ptr [rbp+4]
0x18001ed6b  mov     rax, [rbx+238h]
0x18001ed72  mov     r8d, [rbp+24h]
0x18001ed76  mov     r15d, [rsp+0A8h+arg_0]
0x18001ed7e  mov     [rsp+0A8h+arg_10], r9d
0x18001ed86  mov     r10, [rax+rdx*8+8]
0x18001ed8b  mov     eax, r8d
0x18001ed8e  imul    eax, r14d
0x18001ed92  mov     [rsp+0A8h+var_58], r10
0x18001ed97  movsxd  rcx, eax
0x18001ed9a  mov     rax, [rsp+0A8h+arg_8]
0x18001eda2  mov     rax, [rax+rdx*8]
0x18001eda6  lea     rdx, [rax+rcx*8]
0x18001edaa  mov     rax, [r12]
0x18001edae  mov     ecx, esi
0x18001edb0  mov     [rsp+0A8h+var_60], rdx
0x18001edb5  sub     ecx, [rax+14h]
0x18001edb8  imul    ecx, [rbp+40h]
0x18001edbc  xor     r12d, r12d
0x18001edbf  mov     [rsp+0A8h+arg_18], r12d
0x18001edc7  mov     [rsp+0A8h+var_64], ecx
0x18001edcb  cmp     [rbx+0A0h], r15d
0x18001edd2  jb      short loc_18001EDDD
0x18001edd4  lea     eax, [r14+r12]
0x18001edd8  cmp     eax, [rbp+48h]
0x18001eddb  jge     short loc_18001EE59
0x18001eddd  mov     [rsp+0A8h+var_68], 0
0x18001ede5  mov     esi, ecx
0x18001ede7  test    r9d, r9d
0x18001edea  jle     short loc_18001EE59
0x18001edec  mov     r14d, [rsp+0A8h+var_68]
0x18001edf1  mov     r15, [rsp+0A8h+var_60]
0x18001edf6  mov     r12d, [rsp+0A8h+arg_10]
0x18001edfe  lea     eax, [r14+r13]
0x18001ee02  mov     [rsp+0A8h+var_88], esi
0x18001ee06  movsxd  r8, eax
0x18001ee09  mov     r9, r15
0x18001ee0c  mov     rdx, rbp
0x18001ee0f  mov     rcx, rbx
0x18001ee12  mov     rax, r10
0x18001ee15  mov     r8, [rdi+r8*8+50h]
0x18001ee1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee1f  mov     r8d, [rbp+24h]
0x18001ee23  inc     r14d
0x18001ee26  mov     r10, [rsp+0A8h+var_58]
0x18001ee2b  add     esi, r8d
0x18001ee2e  cmp     r14d, r12d
0x18001ee31  jl      short loc_18001EDFE
0x18001ee33  mov     r14d, [rsp+0A8h+var_6C]
0x18001ee38  mov     r12d, [rsp+0A8h+arg_18]
0x18001ee40  mov     r15d, [rsp+0A8h+arg_0]
0x18001ee48  mov     rdx, [rsp+0A8h+var_60]
0x18001ee4d  mov     ecx, [rsp+0A8h+var_64]
0x18001ee51  mov     r9d, [rsp+0A8h+arg_10]
0x18001ee59  add     r13d, [rbp+34h]
0x18001ee5d  inc     r12d
0x18001ee60  movsxd  rax, r8d
0x18001ee63  mov     [rsp+0A8h+arg_18], r12d
0x18001ee6b  lea     rdx, [rdx+rax*8]
0x18001ee6f  mov     [rsp+0A8h+var_60], rdx
0x18001ee74  cmp     r12d, [rbp+38h]
0x18001ee78  jl      loc_18001EDCB
0x18001ee7e  mov     esi, [rsp+0A8h+var_74]
0x18001ee82  mov     r15d, [rsp+0A8h+var_78]
0x18001ee87  mov     r12, [rsp+0A8h+var_50]
0x18001ee8c  inc     r15d
0x18001ee8f  mov     [rsp+0A8h+var_78], r15d
0x18001ee94  cmp     r15d, [rbx+190h]
0x18001ee9b  jl      loc_18001ED33
0x18001eea1  mov     eax, [rsp+0A8h+var_70]
0x18001eea5  inc     esi
0x18001eea7  jmp     loc_18001ECA7
0x18001eeac  mov     dword ptr [rdi+40h], 0
0x18001eeb3  inc     r14d
0x18001eeb6  jmp     loc_18001EC8E
0x18001eebb  mov     [rdi+44h], r14d
0x18001eebf  xor     eax, eax
0x18001eec1  mov     [rdi+40h], esi
0x18001eec4  jmp     short loc_18001EF04
0x18001eec6  inc     dword ptr [rbx+0A0h]
0x18001eecc  mov     rcx, rbx
0x18001eecf  inc     dword ptr [rbx+0A8h]
0x18001eed5  mov     eax, [rbx+0A0h]
0x18001eedb  cmp     eax, [rbx+184h]
0x18001eee1  jnb     short loc_18001EEEF
0x18001eee3  call    start_iMCU_row_0
0x18001eee8  mov     eax, 3
0x18001eeed  jmp     short loc_18001EF04
0x18001eeef  mov     rax, [rbx+220h]
0x18001eef6  mov     rax, [rax+18h]
0x18001eefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeff  mov     eax, 4
0x18001ef04  add     rsp, 68h
0x18001ef08  pop     r15
0x18001ef0a  pop     r14
0x18001ef0c  pop     r13
0x18001ef0e  pop     r12
0x18001ef10  pop     rdi
0x18001ef11  pop     rsi
0x18001ef12  pop     rbp
0x18001ef13  pop     rbx
0x18001ef14  retn
```
