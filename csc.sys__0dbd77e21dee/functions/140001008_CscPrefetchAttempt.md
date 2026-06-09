# CscPrefetchAttempt

- ea: `0x140001008`
- end: `0x1400012e4`
- name: `CscPrefetchAttempt`
- size: `732`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002680`
- `0x1400043b4`

## callees

- `0x140001008`
- `0x1400012ec`
- `0x140018930`
- `0x14001a624`
- `0x14001a69c`
- `0x14001ac1c`
- `0x14002dfbc`

## import_xrefs

- `MUP!MupSurrogateGetFileName` at `0x1400010d0`
- `MUP!MupSurrogateGetFileName` at `0x1400010d0`

## pseudocode

```c
__int64 __fastcall CscPrefetchAttempt(__int64 a1, _QWORD *a2, int a3, int a4, char a5)
{
  __int64 v5; // r11
  __int64 v6; // r10
  char v10; // bp
  char v11; // r15
  int v12; // ebp
  char v13; // al
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // esi
  int FileName; // eax
  __int64 result; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // r9
  __int128 v24; // [rsp+30h] [rbp-38h] BYREF
  int v25; // [rsp+70h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 56);
  v6 = a2[1];
  v24 = 0;
  v25 = 0;
  _m_prefetchw((const void *)(v6 + 96));
  v10 = _InterlockedXor((volatile signed __int32 *)(v6 + 96), 0);
  if ( (*(_DWORD *)(*a2 + 4LL) & 0x200) != 0 )
    return 0;
  v11 = a5;
  v12 = v10 & 0x10;
  v13 = CscPrefetchTrigger(v5, a2[1], a3, a4, a5, (__int64)&v25);
  if ( !v13 && !v12 )
    return 0;
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL);
  if ( !v15 || !*(_QWORD *)(v15 + 40) )
    return 0;
  v16 = 0;
  if ( !v13 )
    goto LABEL_21;
  LOBYTE(v14) = 1;
  FileName = MupSurrogateGetFileName(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL), 3, v14, &v24);
  if ( FileName < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL),
        FileName);
    return 0;
  }
  _InterlockedIncrement((volatile signed __int32 *)(CscDevExtn + 1424));
  _InterlockedIncrement((volatile signed __int32 *)(a2[1] + 112LL));
  v16 = CscDclNotifyPrefetch(
          v25,
          (unsigned int)&v24,
          a4,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL) + 40LL) + 72LL),
          *(_QWORD *)(a2[1] + 56LL));
  if ( v16 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids, &v24);
LABEL_21:
    if ( (*(_DWORD *)(a1 + 536) & 1) == 0 && (*(_DWORD *)(a1 + 120) & 0x200) == 0 && (v25 & 8) != 0 )
    {
      v19 = *(_QWORD *)(a1 + 56);
      *(_DWORD *)(a1 + 408) = 400;
      v20 = *(_QWORD *)(v19 + 120);
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 32);
        if ( v21 )
        {
          v22 = *(_DWORD *)(v21 + 120);
          if ( !v12 )
            v22 *= 2;
          v23 = (unsigned int)(v22 + 400);
          *(_DWORD *)(a1 + 408) = v23;
          if ( (unsigned int)v23 > 0x3E8 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids, v23);
            }
            *(_DWORD *)(a1 + 408) = 1000;
          }
        }
      }
      v16 = -1069481983;
      _InterlockedOr((volatile signed __int32 *)(a2[1] + 96LL), 4u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids,
          *(unsigned int *)(a1 + 408));
    }
    goto LABEL_36;
  }
  if ( !v11 )
    _InterlockedAnd((volatile signed __int32 *)(a2[1] + 96LL), 0xFFFFFFFE);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_ZD(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      (unsigned int)WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids,
      (unsigned int)&v24,
      v16);
LABEL_36:
  result = 0;
  if ( v16 == -1069481983 )
    return 3225485313LL;
  return result;
}

```

## disassembly

```asm
0x140001008  mov     rax, rsp
0x14000100b  mov     [rax+10h], rbx
0x14000100f  mov     [rax+18h], rbp
0x140001013  push    rsi
0x140001014  push    rdi
0x140001015  push    r12
0x140001017  push    r14
0x140001019  push    r15
0x14000101b  sub     rsp, 40h
0x14000101f  mov     r11, [rcx+38h]
0x140001023  xorps   xmm0, xmm0
0x140001026  mov     r10, [rdx+8]
0x14000102a  mov     r12d, r9d
0x14000102d  movups  xmmword ptr [rax-38h], xmm0
0x140001031  mov     r14, rdx
0x140001034  mov     dword ptr [rax+8], 0
0x14000103b  mov     rbx, rcx
0x14000103e  prefetchw byte ptr [r10+60h]
0x140001043  mov     eax, [r10+60h]
0x140001047  mov     ecx, eax
0x140001049  xor     ecx, 0
0x14000104c  lock cmpxchg [r10+60h], ecx
0x140001052  jnz     short loc_140001047
0x140001054  mov     rcx, [rdx]
0x140001057  mov     ebp, eax
0x140001059  test    dword ptr [rcx+4], 200h
0x140001060  jnz     loc_14000111A
0x140001066  mov     r15b, [rsp+68h+arg_20]
0x14000106e  lea     rax, [rsp+68h+arg_0]
0x140001073  mov     rdx, [rdx+8]
0x140001077  mov     rcx, r11
0x14000107a  mov     [rsp+68h+var_40], rax
0x14000107f  and     ebp, 10h
0x140001082  mov     byte ptr [rsp+68h+var_48], r15b
0x140001087  call    CscPrefetchTrigger
0x14000108c  test    al, al
0x14000108e  jnz     short loc_140001098
0x140001090  test    ebp, ebp
0x140001092  jz      loc_14000111A
0x140001098  mov     rcx, [rbx+40h]
0x14000109c  mov     rdx, [rcx+20h]
0x1400010a0  test    rdx, rdx
0x1400010a3  jz      short loc_14000111A
0x1400010a5  cmp     qword ptr [rdx+28h], 0
0x1400010aa  jz      short loc_14000111A
0x1400010ac  xor     esi, esi
0x1400010ae  lea     rdi, WPP_GLOBAL_Control
0x1400010b5  test    al, al
0x1400010b7  jz      loc_140001200
0x1400010bd  mov     rcx, [rbx+30h]
0x1400010c1  lea     r9, [rsp+68h+var_38]
0x1400010c6  mov     r8b, 1
0x1400010c9  lea     edx, [rsi+3]
0x1400010cc  mov     rcx, [rcx+30h]
0x1400010d0  call    cs:__imp_MupSurrogateGetFileName
0x1400010d7  nop     dword ptr [rax+rax+00h]
0x1400010dc  test    eax, eax
0x1400010de  jns     short loc_140001136
0x1400010e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400010e7  lea     rdi, WPP_GLOBAL_Control
0x1400010ee  cmp     rcx, rdi
0x1400010f1  jz      short loc_14000111A
0x1400010f3  mov     edx, [rcx+2Ch]
0x1400010f6  test    dl, 20h
0x1400010f9  jz      short loc_14000111A
0x1400010fb  mov     r9, [rbx+30h]
0x1400010ff  lea     edx, [rsi+16h]
0x140001102  mov     rcx, [rcx+18h]
0x140001106  lea     r8, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids
0x14000110d  mov     dword ptr [rsp+68h+var_48], eax
0x140001111  mov     r9, [r9+30h]
0x140001115  call    WPP_SF_qD
0x14000111a  xor     eax, eax
0x14000111c  lea     r11, [rsp+68h+var_28]
0x140001121  mov     rbx, [r11+38h]
0x140001125  mov     rbp, [r11+40h]
0x140001129  mov     rsp, r11
0x14000112c  pop     r15
0x14000112e  pop     r14
0x140001130  pop     r12
0x140001132  pop     rdi
0x140001133  pop     rsi
0x140001134  retn
0x140001136  mov     rax, cs:CscDevExtn
0x14000113d  lock inc dword ptr [rax+590h]
0x140001144  mov     rax, [r14+8]
0x140001148  lock inc dword ptr [rax+70h]
0x14000114c  mov     rax, [rbx+40h]
0x140001150  mov     r8d, r12d
0x140001153  mov     rdx, [r14+8]
0x140001157  mov     rcx, [rax+20h]
0x14000115b  mov     rax, [rdx+38h]
0x14000115f  lea     rdx, [rsp+68h+var_38]
0x140001164  mov     [rsp+68h+var_48], rax
0x140001169  mov     r9, [rcx+28h]
0x14000116d  mov     ecx, [rsp+68h+arg_0]
0x140001171  mov     r9, [r9+48h]
0x140001175  call    CscDclNotifyPrefetch
0x14000117a  mov     esi, eax
0x14000117c  test    eax, eax
0x14000117e  jns     short loc_1400011D3
0x140001180  test    r15b, r15b
0x140001183  jnz     short loc_14000118E
0x140001185  mov     rcx, [r14+8]
0x140001189  lock and dword ptr [rcx+60h], 0FFFFFFFEh
0x14000118e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001195  lea     rdi, WPP_GLOBAL_Control
0x14000119c  cmp     rcx, rdi
0x14000119f  jz      loc_1400012D4
0x1400011a5  mov     eax, [rcx+2Ch]
0x1400011a8  test    al, 40h
0x1400011aa  jz      loc_1400012D4
0x1400011b0  mov     rcx, [rcx+18h]
0x1400011b4  lea     r9, [rsp+68h+var_38]
0x1400011b9  mov     edx, 17h
0x1400011be  mov     dword ptr [rsp+68h+var_48], esi
0x1400011c2  lea     r8, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids
0x1400011c9  call    WPP_SF_ZD
0x1400011ce  jmp     loc_1400012D4
0x1400011d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011da  cmp     rcx, rdi
0x1400011dd  jz      short loc_140001200
0x1400011df  mov     eax, [rcx+2Ch]
0x1400011e2  test    al, 40h
0x1400011e4  jz      short loc_140001200
0x1400011e6  mov     rcx, [rcx+18h]
0x1400011ea  lea     r9, [rsp+68h+var_38]
0x1400011ef  mov     edx, 18h
0x1400011f4  lea     r8, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids
0x1400011fb  call    WPP_SF_Z
0x140001200  mov     eax, [rbx+218h]
0x140001206  test    al, 1
0x140001208  jnz     loc_1400012D4
0x14000120e  test    dword ptr [rbx+78h], 200h
0x140001215  jnz     loc_1400012D4
0x14000121b  test    byte ptr [rsp+68h+arg_0], 8
0x140001220  jz      loc_1400012D4
0x140001226  mov     rax, [rbx+38h]
0x14000122a  mov     dword ptr [rbx+198h], 190h
0x140001234  mov     rcx, [rax+78h]
0x140001238  test    rcx, rcx
0x14000123b  jz      short loc_140001297
0x14000123d  mov     rcx, [rcx+20h]
0x140001241  test    rcx, rcx
0x140001244  jz      short loc_140001297
0x140001246  mov     ecx, [rcx+78h]
0x140001249  test    ebp, ebp
0x14000124b  mov     esi, 3E8h
0x140001250  lea     eax, [rcx+rcx]
0x140001253  cmovz   ecx, eax
0x140001256  lea     r9d, [rcx+190h]
0x14000125d  mov     [rbx+198h], r9d
0x140001264  cmp     r9d, esi
0x140001267  jbe     short loc_140001297
0x140001269  mov     rcx, cs:WPP_GLOBAL_Control
0x140001270  cmp     rcx, rdi
0x140001273  jz      short loc_140001291
0x140001275  mov     eax, [rcx+2Ch]
0x140001278  test    al, 40h
0x14000127a  jz      short loc_140001291
0x14000127c  mov     rcx, [rcx+18h]
0x140001280  lea     r8, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids
0x140001287  mov     edx, 19h
0x14000128c  call    WPP_SF_d
0x140001291  mov     [rbx+198h], esi
0x140001297  mov     rax, [r14+8]
0x14000129b  mov     esi, 0C0410001h
0x1400012a0  lock or dword ptr [rax+60h], 4
0x1400012a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012ac  cmp     rcx, rdi
0x1400012af  jz      short loc_1400012D4
0x1400012b1  mov     eax, [rcx+2Ch]
0x1400012b4  test    al, 40h
0x1400012b6  jz      short loc_1400012D4
0x1400012b8  mov     r9d, [rbx+198h]
0x1400012bf  lea     r8, WPP_9cc5bd3a539839aefe9c070b99a7dfde_Traceguids
0x1400012c6  mov     rcx, [rcx+18h]
0x1400012ca  mov     edx, 1Ah
0x1400012cf  call    WPP_SF_d
0x1400012d4  xor     eax, eax
0x1400012d6  cmp     esi, 0C0410001h
0x1400012dc  cmovz   eax, esi
0x1400012df  jmp     loc_14000111C
```
