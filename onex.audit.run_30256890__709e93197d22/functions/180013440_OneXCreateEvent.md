# OneXCreateEvent

- ea: `0x180013440`
- end: `0x18001354b`
- name: `OneXCreateEvent`
- size: `267`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x180002020`
- `0x18000ee70`
- `0x180019080`
- `0x180023b6c`
- `0x180023f94`
- `0x1800240fc`
- `0x180024238`
- `0x1800243a4`
- `0x18002b6d0`
- `0x18002bbf8`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180013440`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x18001348e`
- `MobileNetworking!AllocateMemory` at `0x18001348e`

## string_xrefs

- `0x180013484`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXCreateEvent(__int64 a1, int a2, int a3, __int64 a4)
{
  unsigned int v4; // r15d
  __int64 v9; // rcx
  __int64 result; // rax
  unsigned int v11; // esi
  _QWORD *v12; // rcx

  v4 = *(_DWORD *)(a4 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  if ( a3 )
    v9 = (unsigned int)(16 * a3 + 40);
  else
    v9 = 56;
  result = AllocateMemory(v9, a1, "OneXCreateEvent", 67);
  v11 = result;
  if ( !(_DWORD)result )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 16LL) = a2;
    *(_DWORD *)(*(_QWORD *)a1 + 32LL) = a3;
    *(_QWORD *)(*(_QWORD *)a1 + 24LL) = a4;
LABEL_6:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, result);
    goto LABEL_6;
  }
LABEL_7:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_D(v12[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180013440  push    rbx
0x180013442  push    rbp
0x180013443  push    rsi
0x180013444  push    rdi
0x180013445  push    r12
0x180013447  push    r14
0x180013449  push    r15
0x18001344b  sub     rsp, 30h
0x18001344f  mov     r15d, [r9+14h]
0x180013453  mov     rbp, r9
0x180013456  mov     edi, r8d
0x180013459  mov     r14d, edx
0x18001345c  mov     rbx, rcx
0x18001345f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013466  lea     r12, WPP_GLOBAL_Control
0x18001346d  cmp     rcx, r12
0x180013470  jnz     short loc_1800134DB
0x180013472  test    edi, edi
0x180013474  jz      short loc_1800134D4
0x180013476  mov     ecx, edi
0x180013478  shl     ecx, 4
0x18001347b  add     ecx, 28h ; '('
0x18001347e  mov     r9d, 43h ; 'C'
0x180013484  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x18001348b  mov     rdx, rbx
0x18001348e  call    cs:__imp_AllocateMemory
0x180013494  mov     esi, eax
0x180013496  test    eax, eax
0x180013498  jnz     short loc_1800134FE
0x18001349a  mov     rax, [rbx]
0x18001349d  mov     [rax+10h], r14d
0x1800134a1  mov     rax, [rbx]
0x1800134a4  mov     [rax+20h], edi
0x1800134a7  mov     rax, [rbx]
0x1800134aa  mov     [rax+18h], rbp
0x1800134ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134b5  cmp     rcx, r12
0x1800134b8  jz      short loc_1800134C3
0x1800134ba  test    dword ptr [rcx+44h], 800h
0x1800134c1  jnz     short loc_18001352E
0x1800134c3  mov     eax, esi
0x1800134c5  add     rsp, 30h
0x1800134c9  pop     r15
0x1800134cb  pop     r14
0x1800134cd  pop     r12
0x1800134cf  pop     rdi
0x1800134d0  pop     rsi
0x1800134d1  pop     rbp
0x1800134d2  pop     rbx
0x1800134d3  retn
0x1800134d4  mov     ecx, 38h ; '8'
0x1800134d9  jmp     short loc_18001347E
0x1800134db  test    dword ptr [rcx+44h], 800h
0x1800134e2  jz      short loc_180013472
0x1800134e4  mov     rcx, [rcx+38h]
0x1800134e8  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x1800134ef  mov     edx, 0Ah
0x1800134f4  call    WPP_SF_
0x1800134f9  jmp     loc_180013472
0x1800134fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180013505  cmp     rcx, r12
0x180013508  jz      short loc_1800134C5
0x18001350a  test    byte ptr [rcx+44h], 1
0x18001350e  jz      short loc_1800134B5
0x180013510  mov     rcx, [rcx+38h]
0x180013514  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18001351b  mov     edx, 0Bh
0x180013520  mov     [rsp+68h+var_48], esi
0x180013524  mov     r9d, r15d
0x180013527  call    WPP_SF_dd
0x18001352c  jmp     short loc_1800134AE
0x18001352e  mov     rcx, [rcx+38h]
0x180013532  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180013539  mov     edx, 0Ch
0x18001353e  mov     r9d, esi
0x180013541  call    WPP_SF_D
0x180013546  jmp     loc_1800134C3
```
