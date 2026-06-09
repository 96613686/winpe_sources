# CompareInfRank

- ea: `0x1800057e4`
- end: `0x180005897`
- name: `CompareInfRank`
- size: `179`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800058a0`

## callees

- `0x1800057e4`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180005838`
- `KERNEL32!CompareFileTime` at `0x18000584f`
- `KERNEL32!CompareFileTime` at `0x180005838`
- `KERNEL32!CompareFileTime` at `0x18000584f`

## pseudocode

```c
__int64 __fastcall CompareInfRank(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v3; // eax
  __int64 result; // rax
  unsigned __int64 v8; // rax

  v3 = *(_DWORD *)(a1 + 24);
  if ( v3 < *(_DWORD *)(a2 + 24) )
  {
    result = 0xFFFFFFFFLL;
LABEL_5:
    *a3 = 2;
    return result;
  }
  if ( v3 > *(_DWORD *)(a2 + 24) )
  {
    result = 1;
    goto LABEL_5;
  }
  if ( *(_DWORD *)a1 < *(_DWORD *)a2 )
  {
    result = 0xFFFFFFFFLL;
LABEL_10:
    *a3 = 3;
    return result;
  }
  if ( *(_DWORD *)a1 > *(_DWORD *)a2 )
  {
    result = 1;
    goto LABEL_10;
  }
  if ( CompareFileTime((const FILETIME *)(a1 + 4), (const FILETIME *)(a2 + 4)) > 0 )
  {
    result = 0xFFFFFFFFLL;
LABEL_15:
    *a3 = 4;
    return result;
  }
  if ( CompareFileTime((const FILETIME *)(a1 + 4), (const FILETIME *)(a2 + 4)) < 0 )
  {
    result = 1;
    goto LABEL_15;
  }
  v8 = *(_QWORD *)(a1 + 16);
  if ( v8 > *(_QWORD *)(a2 + 16) )
  {
    result = 0xFFFFFFFFLL;
LABEL_20:
    *a3 = 5;
    return result;
  }
  if ( v8 < *(_QWORD *)(a2 + 16) )
  {
    result = 1;
    goto LABEL_20;
  }
  result = 0;
  *a3 = 6;
  return result;
}

```

## disassembly

```asm
0x1800057e4  push    rbx
0x1800057e6  push    rbp
0x1800057e7  push    rsi
0x1800057e8  push    rdi
0x1800057e9  push    r14
0x1800057eb  sub     rsp, 20h
0x1800057ef  mov     eax, [rcx+18h]
0x1800057f2  mov     rbx, r8
0x1800057f5  mov     rdi, rdx
0x1800057f8  mov     rsi, rcx
0x1800057fb  cmp     eax, [rdx+18h]
0x1800057fe  jnb     short loc_180005805
0x180005800  or      eax, 0FFFFFFFFh
0x180005803  jmp     short loc_18000580C
0x180005805  jbe     short loc_180005815
0x180005807  mov     eax, 1
0x18000580c  mov     dword ptr [r8], 2
0x180005813  jmp     short loc_18000588C
0x180005815  mov     eax, [rcx]
0x180005817  cmp     eax, [rdx]
0x180005819  jnb     short loc_180005820
0x18000581b  or      eax, 0FFFFFFFFh
0x18000581e  jmp     short loc_180005827
0x180005820  jbe     short loc_180005830
0x180005822  mov     eax, 1
0x180005827  mov     dword ptr [r8], 3
0x18000582e  jmp     short loc_18000588C
0x180005830  add     rdx, 4; lpFileTime2
0x180005834  add     rcx, 4; lpFileTime1
0x180005838  call    cs:__imp_CompareFileTime
0x18000583e  test    eax, eax
0x180005840  jle     short loc_180005847
0x180005842  or      eax, 0FFFFFFFFh
0x180005845  jmp     short loc_18000585E
0x180005847  lea     rdx, [rdi+4]; lpFileTime2
0x18000584b  lea     rcx, [rsi+4]; lpFileTime1
0x18000584f  call    cs:__imp_CompareFileTime
0x180005855  test    eax, eax
0x180005857  jns     short loc_180005866
0x180005859  mov     eax, 1
0x18000585e  mov     dword ptr [rbx], 4
0x180005864  jmp     short loc_18000588C
0x180005866  mov     rax, [rsi+10h]
0x18000586a  cmp     rax, [rdi+10h]
0x18000586e  jbe     short loc_180005875
0x180005870  or      eax, 0FFFFFFFFh
0x180005873  jmp     short loc_18000587C
0x180005875  jnb     short loc_180005884
0x180005877  mov     eax, 1
0x18000587c  mov     dword ptr [rbx], 5
0x180005882  jmp     short loc_18000588C
0x180005884  xor     eax, eax
0x180005886  mov     dword ptr [rbx], 6
0x18000588c  add     rsp, 20h
0x180005890  pop     r14
0x180005892  pop     rdi
0x180005893  pop     rsi
0x180005894  pop     rbp
0x180005895  pop     rbx
0x180005896  retn
```
