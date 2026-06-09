# std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(HardwareAddress const &)

- ea: `0x18001a18c`
- end: `0x18001a246`
- name: `?lower_bound@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@AEBVHardwareAddress@@@Z`
- size: `186`
- prototype: `__int64 **__fastcall(_QWORD *, __int64 **, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018540`
- `0x1800195cc`

## callees

- `0x18001a18c`

## pseudocode

```c
__int64 **__fastcall std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(
        _QWORD *a1,
        __int64 **a2,
        int *a3)
{
  int v5; // ecx
  int v7; // edx
  unsigned __int64 v8; // r8
  int v9; // ecx
  int v10; // eax
  unsigned __int64 v11; // rdx
  __int64 v12; // r11
  __int64 v13; // rdx
  __int64 *v14; // r8
  __int64 *i; // rax
  __int64 *v16; // rcx
  int v17; // edx
  __int64 **result; // rax

  v5 = 16807 * *a3;
  v7 = (unsigned __int64)(2202930015LL * *a3) >> 32;
  v8 = a1[8];
  v9 = v5 - 0x7FFFFFFF * (((unsigned int)v7 >> 31) + (v7 >> 16));
  v10 = v9 + 0x7FFFFFFF;
  if ( v9 >= 0 )
    v10 = v9;
  v11 = v8 & v10;
  if ( a1[9] <= v11 )
    v11 = v11 - (v8 >> 1) - 1;
  v12 = a1[4];
  v13 = 2 * v11;
  v14 = (__int64 *)a1[1];
  for ( i = *(__int64 **)(v12 + 8 * v13); ; i = (__int64 *)*i )
  {
    v16 = *(__int64 **)(v12 + 8 * v13) == v14 ? (__int64 *)a1[1] : **(__int64 ***)(v12 + 8 * v13 + 8);
    if ( i == v16 )
      break;
    if ( *((_DWORD *)i + 6) == a3[2] && *((_WORD *)i + 14) == *((_WORD *)a3 + 6) )
    {
      v17 = a3[2] - *((_DWORD *)i + 6);
      if ( !v17 )
        v17 = *((unsigned __int16 *)a3 + 6) - *((unsigned __int16 *)i + 14);
      if ( !v17 )
        v14 = i;
      break;
    }
  }
  result = a2;
  *a2 = v14;
  return result;
}

```

## disassembly

```asm
0x18001a18c  mov     [rsp+arg_0], rbx
0x18001a191  mov     r9, rdx
0x18001a194  mov     rbx, rcx
0x18001a197  imul    ecx, [r8], 41A7h
0x18001a19e  mov     eax, 834E0B5Fh
0x18001a1a3  imul    dword ptr [r8]
0x18001a1a6  mov     r10, r8
0x18001a1a9  add     edx, [r8]
0x18001a1ac  mov     r8, [rbx+40h]
0x18001a1b0  sar     edx, 10h
0x18001a1b3  mov     eax, edx
0x18001a1b5  shr     eax, 1Fh
0x18001a1b8  add     edx, eax
0x18001a1ba  imul    eax, edx, 7FFFFFFFh
0x18001a1c0  sub     ecx, eax
0x18001a1c2  lea     eax, [rcx+7FFFFFFFh]
0x18001a1c8  cmovns  eax, ecx
0x18001a1cb  movsxd  rdx, eax
0x18001a1ce  and     rdx, r8
0x18001a1d1  cmp     [rbx+48h], rdx
0x18001a1d5  ja      short loc_18001A1E0
0x18001a1d7  shr     r8, 1
0x18001a1da  sub     rdx, r8
0x18001a1dd  dec     rdx
0x18001a1e0  mov     r11, [rbx+20h]
0x18001a1e4  add     rdx, rdx
0x18001a1e7  mov     r8, [rbx+8]
0x18001a1eb  mov     rax, [r11+rdx*8]
0x18001a1ef  cmp     [r11+rdx*8], r8
0x18001a1f3  jnz     short loc_18001A1FA
0x18001a1f5  mov     rcx, r8
0x18001a1f8  jmp     short loc_18001A202
0x18001a1fa  mov     rcx, [r11+rdx*8+8]
0x18001a1ff  mov     rcx, [rcx]
0x18001a202  cmp     rax, rcx
0x18001a205  jz      short loc_18001A23A
0x18001a207  mov     ecx, [rax+18h]
0x18001a20a  cmp     ecx, [r10+8]
0x18001a20e  jnz     short loc_18001A21B
0x18001a210  movzx   ecx, word ptr [rax+1Ch]
0x18001a214  cmp     cx, [r10+0Ch]
0x18001a219  jz      short loc_18001A220
0x18001a21b  mov     rax, [rax]
0x18001a21e  jmp     short loc_18001A1EF
0x18001a220  mov     edx, [r10+8]
0x18001a224  sub     edx, [rax+18h]
0x18001a227  jnz     short loc_18001A234
0x18001a229  movzx   edx, word ptr [r10+0Ch]
0x18001a22e  movzx   ecx, word ptr [rax+1Ch]
0x18001a232  sub     edx, ecx
0x18001a234  test    edx, edx
0x18001a236  cmovz   r8, rax
0x18001a23a  mov     rbx, [rsp+arg_0]
0x18001a23f  mov     rax, r9
0x18001a242  mov     [r9], r8
0x18001a245  retn
```
