# ValidateDataKey

- ea: `0x180001980`
- end: `0x180001a46`
- name: `ValidateDataKey`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`
- `0x180002c90`

## callees

- `0x180001980`

## pseudocode

```c
char __fastcall ValidateDataKey(__int64 a1, _BYTE *a2)
{
  unsigned int v2; // eax
  _BYTE *v4; // r9
  unsigned int v5; // edx
  __int64 v6; // rcx
  unsigned int v7; // edx
  __int64 v8; // rcx
  unsigned int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // rcx
  unsigned int v13; // edx
  __int64 v14; // rcx

  v2 = *(_DWORD *)a1;
  if ( !*(_DWORD *)a1 )
    return 0;
  v4 = *(_BYTE **)(a1 + 8);
  if ( !v4 )
    return 0;
  if ( v2 < 7 )
  {
    *a2 = *v4;
    *(_QWORD *)(a1 + 8) = a2;
    *(_QWORD *)(a1 + 16) = a2;
    *(_DWORD *)a1 = 7;
    *(_DWORD *)(a1 + 4) = 7;
    a2[1] = v4[v2 > 1];
    v5 = (v2 > 1) + 1;
    v6 = 0;
    if ( v5 < v2 )
      v6 = v5;
    v7 = v6 + 1;
    a2[2] = v4[v6];
    v8 = 0;
    if ( v7 < v2 )
      v8 = v7;
    v9 = v8 + 1;
    a2[3] = v4[v8];
    v10 = 0;
    if ( v9 < v2 )
      v10 = v9;
    v11 = v10 + 1;
    a2[4] = v4[v10];
    v12 = 0;
    if ( v11 < v2 )
      v12 = v11;
    v13 = v12 + 1;
    a2[5] = v4[v12];
    v14 = 0;
    if ( v13 < v2 )
      v14 = v13;
    a2[6] = v4[v14];
  }
  return 1;
}

```

## disassembly

```asm
0x180001980  mov     eax, [rcx]
0x180001982  mov     r10, rdx
0x180001985  mov     r8, rcx
0x180001988  test    eax, eax
0x18000198a  jz      loc_180001A43
0x180001990  mov     r9, [rcx+8]
0x180001994  test    r9, r9
0x180001997  jz      loc_180001A43
0x18000199d  cmp     eax, 7
0x1800019a0  jnb     loc_180001A3F
0x1800019a6  movzx   edx, byte ptr [r9]
0x1800019aa  xor     ecx, ecx
0x1800019ac  mov     [r10], dl
0x1800019af  cmp     eax, 1
0x1800019b2  mov     [r8+8], r10
0x1800019b6  setnbe  cl
0x1800019b9  mov     [r8+10h], r10
0x1800019bd  xor     edx, edx
0x1800019bf  mov     dword ptr [r8], 7
0x1800019c6  cmp     eax, 1
0x1800019c9  mov     dword ptr [r8+4], 7
0x1800019d1  movzx   ecx, byte ptr [rcx+r9]
0x1800019d6  setnbe  dl
0x1800019d9  mov     [r10+1], cl
0x1800019dd  inc     edx
0x1800019df  xor     ecx, ecx
0x1800019e1  cmp     edx, eax
0x1800019e3  cmovb   ecx, edx
0x1800019e6  mov     edx, ecx
0x1800019e8  inc     edx
0x1800019ea  movzx   ecx, byte ptr [rcx+r9]
0x1800019ef  mov     [r10+2], cl
0x1800019f3  xor     ecx, ecx
0x1800019f5  cmp     edx, eax
0x1800019f7  cmovb   ecx, edx
0x1800019fa  mov     edx, ecx
0x1800019fc  inc     edx
0x1800019fe  movzx   ecx, byte ptr [rcx+r9]
0x180001a03  mov     [r10+3], cl
0x180001a07  xor     ecx, ecx
0x180001a09  cmp     edx, eax
0x180001a0b  cmovb   ecx, edx
0x180001a0e  mov     edx, ecx
0x180001a10  inc     edx
0x180001a12  movzx   ecx, byte ptr [rcx+r9]
0x180001a17  mov     [r10+4], cl
0x180001a1b  xor     ecx, ecx
0x180001a1d  cmp     edx, eax
0x180001a1f  cmovb   ecx, edx
0x180001a22  mov     edx, ecx
0x180001a24  inc     edx
0x180001a26  movzx   ecx, byte ptr [rcx+r9]
0x180001a2b  mov     [r10+5], cl
0x180001a2f  xor     ecx, ecx
0x180001a31  cmp     edx, eax
0x180001a33  cmovb   ecx, edx
0x180001a36  movzx   ecx, byte ptr [rcx+r9]
0x180001a3b  mov     [r10+6], cl
0x180001a3f  mov     al, 1
0x180001a41  retn
0x180001a43  xor     al, al
0x180001a45  retn
```
