# RtlSetThreadPreferredUILanguages

- ea: `0x18000ca60`
- end: `0x18000d034`
- name: `RtlSetThreadPreferredUILanguages`
- size: `1492`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180044bc0`

## callees

- `0x180007060`
- `0x180008040`
- `0x180009060`
- `0x1800094d0`
- `0x18000ca60`
- `0x18000d03c`
- `0x18000d3e0`
- `0x180010320`
- `0x18001b984`
- `0x180054eb0`

## string_xrefs

- `0x18000cb2e`: `RtlSetThreadPreferredUILanguages`

## pseudocode

```c
__int64 __fastcall RtlSetThreadPreferredUILanguages(int a1, __int16 *a2, int *a3)
{
  unsigned __int64 v3; // rsi
  int v5; // edi
  void *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebp
  __int64 v9; // rdx
  __int16 v10; // r9
  _WORD *v11; // rdx
  unsigned __int64 v12; // rcx
  _WORD *v13; // rax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  __int64 v16; // rbx
  __int64 Heap_0; // rax
  __int64 v18; // rcx
  int v19; // eax
  char v20; // bl
  _BYTE *MergedPrefLanguages; // rcx
  __int64 v22; // rax
  __int64 *UserPrefLanguages; // rcx
  __int64 v24; // rbx
  int v25; // eax
  _QWORD *v26; // rax
  _QWORD *v27; // rsi
  int v28; // ecx
  _QWORD *v29; // rax
  _QWORD *v30; // rsi
  _QWORD v31[9]; // [rsp+40h] [rbp-48h] BYREF
  int v32; // [rsp+90h] [rbp+8h] BYREF
  int *v33; // [rsp+A0h] [rbp+18h]
  int v34; // [rsp+A8h] [rbp+20h] BYREF

  v33 = a3;
  v3 = 0;
  v34 = 0;
  v5 = a1;
  v32 = 0;
  v6 = 0;
  v31[0] = 0;
  if ( (a1 & 0xFFFF7CF2) != 0 )
    return 3221225485LL;
  if ( (a1 & 8) != 0 )
  {
    if ( (a1 & 4) != 0 )
      return 3221225485LL;
  }
  else if ( (a1 & 4) == 0 )
  {
    v5 = a1 | 8;
  }
  if ( (v5 & 0x200) != 0 && (v5 & 0x100) != 0 || (v5 & 1) != 0 && ((v5 & 0x200) != 0 || (v5 & 0x100) != 0) )
    return 3221225485LL;
  result = RtlpCreateProcessRegistryInfo(v31);
  v8 = result;
  if ( (int)result >= 0 )
  {
    if ( (v5 & 0x200) == 0 && (v5 & 0x100) == 0 && (v5 & 1) == 0 )
    {
      if ( a2 )
      {
        v9 = 4;
        if ( (v5 & 4) == 0 )
          v9 = 85;
        if ( (int)RtlpCheckMuiMultiStringSafe(a2, v9) < 0 )
          DbgPrint(
            "*** ASSERT FAILED: Input parameter: %s, for function: %s is not a valid multi-string!\n",
            (const char *)a2,
            "RtlSetThreadPreferredUILanguages");
        v10 = *a2;
        v11 = a2 + 1;
        if ( *a2 )
          v11 = a2;
        LOBYTE(v3) = v10 == 0;
        while ( *v11 )
        {
          if ( v3 > 0x7FFFFFFF )
            return (unsigned int)-1073741811;
          v12 = 0x7FFFFFFF - v3;
          if ( v3 > 0x7FFFFFFF && v3 != 0 )
            return (unsigned int)-1073741811;
          v13 = v11;
          if ( !v12 )
            return (unsigned int)-1073741811;
          while ( *v13 )
          {
            ++v13;
            if ( !--v12 )
              return (unsigned int)-1073741811;
          }
          v14 = 0x7FFFFFFF - v3 - v12;
          v3 = 0x7FFFFFFF - v12 + 1;
          v11 += v14 + 1;
        }
        v15 = v3 + 1;
        if ( v15 < 2 || v10 || a2[1] )
        {
          v16 = v31[0];
          if ( !v31[0] )
            return (unsigned int)-1073741801;
          Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 94);
          v18 = Heap_0;
          if ( Heap_0 )
          {
            *(_DWORD *)Heap_0 = 94;
            *(_DWORD *)(Heap_0 + 4) = 327680;
            *(_BYTE *)(Heap_0 + 8) = 0;
            *(_QWORD *)(Heap_0 + 24) = Heap_0 + 64;
            *(_DWORD *)(Heap_0 + 40) = 0;
            *(_QWORD *)(Heap_0 + 16) = v16;
          }
          else
          {
            v18 = 0;
          }
          v31[0] = v18;
          if ( !v18 )
            return (unsigned int)-1073741801;
          v8 = RtlpMuiRegAddMultiSzToLangFallbackList(g_RegInfo, a2, v15, v5 | 2u, 26, 5, v31);
          if ( (v8 & 0x80000000) != 0 )
          {
            RtlpMuiRegFreeLanguageList(v31[0]);
            return v8;
          }
          v6 = (void *)v31[0];
          v19 = *(unsigned __int16 *)(v31[0] + 4LL);
          if ( !(_WORD)v19 )
          {
            RtlpMuiRegFreeLanguageList(v31[0]);
            return (unsigned int)-1073741823;
          }
          if ( v33 )
            *v33 = v19;
        }
      }
      v20 = 0;
      if ( NtCurrentTeb()->PreferredLanguages )
      {
        RtlpMuiRegFreeLanguageList(NtCurrentTeb()->PreferredLanguages);
        NtCurrentTeb()->PreferredLanguages = 0;
      }
      NtCurrentTeb()->PreferredLanguages = v6;
LABEL_40:
      if ( NtCurrentTeb()->MergedPrefLanguages )
      {
        MergedPrefLanguages = NtCurrentTeb()->MergedPrefLanguages;
        if ( (MergedPrefLanguages[40] & 0x40) != 0 )
        {
          v22 = ((__int64 (*)(void))RtlpMuiRegDupLanguageList)();
          MergedPrefLanguages = (_BYTE *)v22;
          if ( !v22 )
            return (unsigned int)-1073741823;
          *(_DWORD *)(v22 + 40) &= ~0x40u;
        }
        *((_DWORD *)MergedPrefLanguages + 10) |= 0x80u;
        NtCurrentTeb()->MergedPrefLanguages = MergedPrefLanguages;
      }
      if ( v8 || !v20 )
        return v8;
      if ( NtCurrentTeb()->UserPrefLanguages )
      {
        UserPrefLanguages = (__int64 *)NtCurrentTeb()->UserPrefLanguages;
        v24 = *UserPrefLanguages;
        if ( *UserPrefLanguages )
        {
          if ( (v5 & 1) != 0 )
          {
            *(_DWORD *)(v24 + 40) &= 0xFFFFFFF9;
          }
          else
          {
            v25 = *(_DWORD *)(v24 + 40) & 0x40;
            if ( (v5 & 0x100) != 0 )
            {
              if ( v25 )
              {
                v24 = RtlpMuiRegDupLanguageList(*UserPrefLanguages);
                if ( !v24 )
                  return 3221225473LL;
                if ( NtCurrentTeb()->UserPrefLanguages )
                {
                  v30 = NtCurrentTeb()->UserPrefLanguages;
                }
                else
                {
                  v29 = (_QWORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 16);
                  v30 = v29;
                  if ( !v29 )
                    return 3221225473LL;
                  *v29 = 0;
                  v29[1] = 0;
                  NtCurrentTeb()->UserPrefLanguages = v29;
                }
                if ( *v30 )
                {
                  *(_DWORD *)(v24 + 40) = *(_DWORD *)(*v30 + 40LL);
                  RtlpMuiRegFreeLanguageList(*v30);
                }
                *v30 = v24;
                *(_DWORD *)(v24 + 40) &= ~0x40u;
                v8 = 0;
              }
              *(_DWORD *)(v24 + 40) = *(_DWORD *)(v24 + 40) & 0xFFFFFFF9 | 2;
              if ( (v5 & 0x8000) == 0 )
                goto LABEL_61;
              if ( !v33 )
                goto LABEL_61;
              v28 = *v33;
              if ( !*v33 )
                goto LABEL_61;
            }
            else
            {
              if ( v25 )
              {
                v24 = RtlpMuiRegDupLanguageList(*UserPrefLanguages);
                if ( !v24 )
                  return 3221225473LL;
                if ( NtCurrentTeb()->UserPrefLanguages )
                {
                  v27 = NtCurrentTeb()->UserPrefLanguages;
                }
                else
                {
                  v26 = (_QWORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 16);
                  v27 = v26;
                  if ( !v26 )
                    return 3221225473LL;
                  *v26 = 0;
                  v26[1] = 0;
                  NtCurrentTeb()->UserPrefLanguages = v26;
                }
                if ( *v27 )
                {
                  *(_DWORD *)(v24 + 40) = *(_DWORD *)(*v27 + 40LL);
                  RtlpMuiRegFreeLanguageList(*v27);
                }
                *v27 = v24;
                *(_DWORD *)(v24 + 40) &= ~0x40u;
                v8 = 0;
              }
              *(_DWORD *)(v24 + 40) = *(_DWORD *)(v24 + 40) & 0xFFFFFFF9 | 4;
              if ( (v5 & 0x8000) == 0 )
                goto LABEL_61;
              if ( !v33 )
                goto LABEL_61;
              v28 = *v33;
              if ( !*v33 )
                goto LABEL_61;
            }
            *(_WORD *)(v24 + 42) = 0;
            *(_DWORD *)(v24 + 40) |= v28 << 16;
          }
        }
      }
LABEL_61:
      RtlGetThreadPreferredUILanguages(v5 | 0x30u, &v34, 0, &v32);
      return v8;
    }
    if ( !a2 )
    {
      v20 = 1;
      RtlpInitializeUserList(v31[0]);
      goto LABEL_40;
    }
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ca60  mov     rax, rsp
0x18000ca63  mov     [rax+10h], rbx
0x18000ca67  mov     [rax+18h], r8
0x18000ca6b  push    rbp
0x18000ca6c  push    rsi
0x18000ca6d  push    rdi
0x18000ca6e  push    r12
0x18000ca70  push    r13
0x18000ca72  push    r14
0x18000ca74  push    r15
0x18000ca76  sub     rsp, 50h
0x18000ca7a  xor     esi, esi
0x18000ca7c  mov     r14, rdx
0x18000ca7f  mov     [rax+20h], esi
0x18000ca82  mov     edi, ecx
0x18000ca84  mov     [rax+8], esi
0x18000ca87  mov     r13d, esi
0x18000ca8a  mov     [rax-48h], rsi
0x18000ca8e  test    ecx, 0FFFF7CF2h
0x18000ca94  jnz     loc_18000CE02
0x18000ca9a  mov     eax, ecx
0x18000ca9c  and     eax, 4
0x18000ca9f  test    dil, 8
0x18000caa3  jnz     loc_18000CDEF
0x18000caa9  test    eax, eax
0x18000caab  jnz     short loc_18000CAB0
0x18000caad  or      edi, 8
0x18000cab0  mov     r15d, edi
0x18000cab3  mov     ebx, edi
0x18000cab5  and     r15d, 100h
0x18000cabc  and     ebx, 200h
0x18000cac2  jz      short loc_18000CACD
0x18000cac4  test    r15d, r15d
0x18000cac7  jnz     loc_18000CE02
0x18000cacd  mov     r12d, edi
0x18000cad0  and     r12d, 1
0x18000cad4  jnz     loc_18000CE74
0x18000cada  lea     rcx, [rsp+88h+var_48]
0x18000cadf  call    RtlpCreateProcessRegistryInfo
0x18000cae4  mov     ebp, eax
0x18000cae6  test    eax, eax
0x18000cae8  js      loc_18000CE2E
0x18000caee  test    ebx, ebx
0x18000caf0  jnz     loc_18000CDF9
0x18000caf6  test    r15d, r15d
0x18000caf9  jnz     loc_18000CDF9
0x18000caff  test    r12d, r12d
0x18000cb02  jnz     loc_18000CDF9
0x18000cb08  test    r14, r14
0x18000cb0b  jz      loc_18000CC90
0x18000cb11  mov     eax, 55h ; 'U'
0x18000cb16  test    dil, 4
0x18000cb1a  mov     edx, 4
0x18000cb1f  mov     rcx, r14
0x18000cb22  cmovz   edx, eax
0x18000cb25  call    RtlpCheckMuiMultiStringSafe
0x18000cb2a  test    eax, eax
0x18000cb2c  jns     short loc_18000CB44
0x18000cb2e  lea     r8, aRtlsetthreadpr_1; "RtlSetThreadPreferredUILanguages"
0x18000cb35  mov     rdx, r14
0x18000cb38  lea     rcx, aAssertFailedIn; "*** ASSERT FAILED: Input parameter: %s,"...
0x18000cb3f  call    DbgPrint
0x18000cb44  movzx   r9d, word ptr [r14]
0x18000cb48  lea     rdx, [r14+2]
0x18000cb4c  test    r9w, r9w
0x18000cb50  cmovnz  rdx, r14
0x18000cb54  setz    sil
0x18000cb58  cmp     [rdx], r13w
0x18000cb5c  jz      short loc_18000CBBC
0x18000cb5e  cmp     rsi, 7FFFFFFFh
0x18000cb65  ja      loc_18000D023
0x18000cb6b  mov     ecx, 7FFFFFFFh
0x18000cb70  sub     rcx, rsi
0x18000cb73  cmp     rcx, 7FFFFFFFh
0x18000cb7a  ja      loc_18000D023
0x18000cb80  mov     rax, rdx
0x18000cb83  mov     r8, rcx
0x18000cb86  test    rcx, rcx
0x18000cb89  jz      loc_18000D023
0x18000cb8f  nop
0x18000cb90  cmp     [rax], r13w
0x18000cb94  jz      short loc_18000CBA9
0x18000cb96  add     rax, 2
0x18000cb9a  sub     rcx, 1
0x18000cb9e  jnz     short loc_18000CB90
0x18000cba0  test    rcx, rcx
0x18000cba3  jz      loc_18000D023
0x18000cba9  sub     r8, rcx
0x18000cbac  inc     rsi
0x18000cbaf  add     rsi, r8
0x18000cbb2  lea     rdx, [rdx+r8*2]
0x18000cbb6  add     rdx, 2
0x18000cbba  jmp     short loc_18000CB58
0x18000cbbc  inc     esi
0x18000cbbe  cmp     esi, 2
0x18000cbc1  jnb     loc_18000CE47
0x18000cbc7  mov     rbx, [rsp+88h+var_48]
0x18000cbcc  test    rbx, rbx
0x18000cbcf  jz      loc_18000CE6D
0x18000cbd5  mov     rcx, gs:60h
0x18000cbde  mov     edx, 8
0x18000cbe3  mov     r8d, 5Eh ; '^'
0x18000cbe9  mov     rcx, [rcx+30h]
0x18000cbed  call    RtlAllocateHeap_0
0x18000cbf2  xor     r8d, r8d
0x18000cbf5  mov     rcx, rax
0x18000cbf8  mov     edx, 5
0x18000cbfd  test    rax, rax
0x18000cc00  jz      loc_18000D01B
0x18000cc06  mov     dword ptr [rax], 5Eh ; '^'
0x18000cc0c  mov     dword ptr [rax+4], 50000h
0x18000cc13  mov     [rax+8], r8b
0x18000cc17  add     rax, 40h ; '@'
0x18000cc1b  mov     [rcx+18h], rax
0x18000cc1f  mov     [rcx+28h], r8d
0x18000cc23  mov     [rcx+10h], rbx
0x18000cc27  mov     [rsp+88h+var_48], rcx
0x18000cc2c  test    rcx, rcx
0x18000cc2f  jz      loc_18000CE6D
0x18000cc35  mov     rcx, cs:g_RegInfo
0x18000cc3c  lea     rax, [rsp+88h+var_48]
0x18000cc41  mov     [rsp+88h+var_58], rax
0x18000cc46  mov     r9d, edi
0x18000cc49  mov     [rsp+88h+var_60], edx
0x18000cc4d  or      r9d, 2
0x18000cc51  mov     rdx, r14
0x18000cc54  mov     [rsp+88h+var_68], 1Ah
0x18000cc5c  mov     r8d, esi
0x18000cc5f  call    RtlpMuiRegAddMultiSzToLangFallbackList
0x18000cc64  mov     ebp, eax
0x18000cc66  test    eax, eax
0x18000cc68  js      loc_18000CE61
0x18000cc6e  mov     r13, [rsp+88h+var_48]
0x18000cc73  movzx   eax, word ptr [r13+4]
0x18000cc78  test    ax, ax
0x18000cc7b  jz      loc_18000CFD5
0x18000cc81  mov     rsi, [rsp+88h+arg_10]
0x18000cc89  test    rsi, rsi
0x18000cc8c  jz      short loc_18000CC90
0x18000cc8e  mov     [rsi], eax
0x18000cc90  mov     rax, gs:30h
0x18000cc99  xor     bl, bl
0x18000cc9b  cmp     qword ptr [rax+17D0h], 0
0x18000cca3  jz      loc_18000D02D
0x18000cca9  mov     rcx, gs:30h
0x18000ccb2  mov     rcx, [rcx+17D0h]
0x18000ccb9  call    RtlpMuiRegFreeLanguageList
0x18000ccbe  mov     rax, gs:30h
0x18000ccc7  xor     esi, esi
0x18000ccc9  mov     [rax+17D0h], rsi
0x18000ccd0  mov     rax, gs:30h
0x18000ccd9  mov     [rax+17D0h], r13
0x18000cce0  mov     rax, gs:30h
0x18000cce9  cmp     qword ptr [rax+17E0h], 0
0x18000ccf1  jz      short loc_18000CD35
0x18000ccf3  mov     rax, gs:30h
0x18000ccfc  mov     rcx, [rax+17E0h]
0x18000cd03  test    byte ptr [rcx+28h], 40h
0x18000cd07  jz      short loc_18000CD1E
0x18000cd09  call    RtlpMuiRegDupLanguageList
0x18000cd0e  mov     rcx, rax
0x18000cd11  test    rax, rax
0x18000cd14  jz      loc_18000CFDD
0x18000cd1a  and     dword ptr [rax+28h], 0FFFFFFBFh
0x18000cd1e  or      dword ptr [rcx+28h], 80h
0x18000cd25  mov     rax, gs:30h
0x18000cd2e  mov     [rax+17E0h], rcx
0x18000cd35  test    ebp, ebp
0x18000cd37  jnz     loc_18000CE2C
0x18000cd3d  test    bl, bl
0x18000cd3f  jz      loc_18000CE2C
0x18000cd45  mov     rax, gs:30h
0x18000cd4e  cmp     qword ptr [rax+17D8h], 0
0x18000cd56  jz      loc_18000CE0F
0x18000cd5c  mov     rax, gs:30h
0x18000cd65  mov     rcx, [rax+17D8h]
0x18000cd6c  mov     rbx, [rcx]
0x18000cd6f  test    rbx, rbx
0x18000cd72  jz      loc_18000CE0F
0x18000cd78  mov     eax, [rbx+28h]
0x18000cd7b  test    r12d, r12d
0x18000cd7e  jnz     loc_18000CE09
0x18000cd84  and     eax, 40h
0x18000cd87  test    r15d, r15d
0x18000cd8a  jnz     loc_18000CEFE
0x18000cd90  test    eax, eax
0x18000cd92  jz      loc_18000CEB7
0x18000cd98  mov     rcx, rbx
0x18000cd9b  call    RtlpMuiRegDupLanguageList
0x18000cda0  mov     rbx, rax
0x18000cda3  test    rax, rax
0x18000cda6  jz      short loc_18000CDE8
0x18000cda8  mov     rax, gs:30h
0x18000cdb1  cmp     qword ptr [rax+17D8h], 0
0x18000cdb9  jnz     loc_18000CE86
0x18000cdbf  mov     rcx, gs:60h
0x18000cdc8  mov     edx, 8
0x18000cdcd  mov     r8d, 10h
0x18000cdd3  mov     rcx, [rcx+30h]
0x18000cdd7  call    RtlAllocateHeap_0
0x18000cddc  mov     rsi, rax
0x18000cddf  test    rax, rax
0x18000cde2  jnz     loc_18000CFE7
0x18000cde8  mov     eax, 0C0000001h
0x18000cded  jmp     short loc_18000CE2E
0x18000cdef  test    eax, eax
0x18000cdf1  jz      loc_18000CAB0
0x18000cdf7  jmp     short loc_18000CE02
0x18000cdf9  test    r14, r14
0x18000cdfc  jz      loc_18000CEED
0x18000ce02  mov     eax, 0C000000Dh
0x18000ce07  jmp     short loc_18000CE2E
0x18000ce09  and     eax, 0FFFFFFF9h
0x18000ce0c  mov     [rbx+28h], eax
0x18000ce0f  or      edi, 30h
0x18000ce12  lea     r9, [rsp+88h+arg_0]
0x18000ce1a  mov     ecx, edi
0x18000ce1c  lea     rdx, [rsp+88h+arg_18]
0x18000ce24  xor     r8d, r8d
0x18000ce27  call    RtlGetThreadPreferredUILanguages
0x18000ce2c  mov     eax, ebp
0x18000ce2e  mov     rbx, [rsp+88h+arg_8]
0x18000ce36  add     rsp, 50h
0x18000ce3a  pop     r15
0x18000ce3c  pop     r14
0x18000ce3e  pop     r13
0x18000ce40  pop     r12
0x18000ce42  pop     rdi
0x18000ce43  pop     rsi
0x18000ce44  pop     rbp
0x18000ce45  retn
0x18000ce47  test    r9w, r9w
0x18000ce4b  jnz     loc_18000CBC7
0x18000ce51  cmp     [r14+2], r13w
0x18000ce56  jnz     loc_18000CBC7
0x18000ce5c  jmp     loc_18000CC90
0x18000ce61  mov     rcx, [rsp+88h+var_48]
0x18000ce66  call    RtlpMuiRegFreeLanguageList
0x18000ce6b  jmp     short loc_18000CE2C
0x18000ce6d  mov     ebp, 0C0000017h
0x18000ce72  jmp     short loc_18000CE2C
0x18000ce74  test    ebx, ebx
0x18000ce76  jnz     short loc_18000CE02
0x18000ce78  test    r15d, r15d
0x18000ce7b  jz      loc_18000CADA
0x18000ce81  jmp     loc_18000CE02
0x18000ce86  mov     rax, gs:30h
0x18000ce8f  mov     rsi, [rax+17D8h]
0x18000ce96  mov     rax, [rsi]
0x18000ce99  test    rax, rax
0x18000ce9c  jz      short loc_18000CEAC
0x18000ce9e  mov     eax, [rax+28h]
0x18000cea1  mov     [rbx+28h], eax
0x18000cea4  mov     rcx, [rsi]
0x18000cea7  call    RtlpMuiRegFreeLanguageList
0x18000ceac  mov     [rsi], rbx
0x18000ceaf  xor     esi, esi
0x18000ceb1  and     dword ptr [rbx+28h], 0FFFFFFBFh
0x18000ceb5  mov     ebp, esi
0x18000ceb7  mov     eax, [rbx+28h]
0x18000ceba  and     eax, 0FFFFFFFDh
0x18000cebd  or      eax, 4
0x18000cec0  mov     [rbx+28h], eax
0x18000cec3  bt      edi, 0Fh
0x18000cec7  jnb     loc_18000CE0F
0x18000cecd  mov     rcx, [rsp+88h+arg_10]
0x18000ced5  test    rcx, rcx
0x18000ced8  jz      loc_18000CE0F
0x18000cede  mov     ecx, [rcx]
0x18000cee0  test    ecx, ecx
0x18000cee2  jz      loc_18000CE0F
0x18000cee8  jmp     loc_18000CFC6
0x18000ceed  mov     rcx, [rsp+88h+var_48]
0x18000cef2  mov     bl, 1
0x18000cef4  call    RtlpInitializeUserList
0x18000cef9  jmp     loc_18000CCE0
0x18000cefe  test    eax, eax
0x18000cf00  jz      loc_18000CF95
0x18000cf06  mov     rcx, rbx
0x18000cf09  call    RtlpMuiRegDupLanguageList
0x18000cf0e  mov     rbx, rax
0x18000cf11  test    rax, rax
0x18000cf14  jz      loc_18000CDE8
0x18000cf1a  mov     rcx, gs:30h
0x18000cf23  cmp     qword ptr [rcx+17D8h], 0
0x18000cf2b  jnz     loc_18000D006
0x18000cf31  mov     rcx, gs:60h
0x18000cf3a  mov     edx, 8
0x18000cf3f  mov     r8d, 10h
0x18000cf45  mov     rcx, [rcx+30h]
0x18000cf49  call    RtlAllocateHeap_0
0x18000cf4e  mov     rsi, rax
0x18000cf51  test    rax, rax
0x18000cf54  jz      loc_18000CDE8
0x18000cf5a  xor     r8d, r8d
0x18000cf5d  mov     [rax], r8
0x18000cf60  mov     [rax+8], r8
0x18000cf64  mov     rcx, gs:30h
0x18000cf6d  mov     [rcx+17D8h], rax
0x18000cf74  mov     rax, [rsi]
  ... truncated ...
```
