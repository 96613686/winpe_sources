# WBISAMBeginSession(x)

- ea: `0x10006960`
- end: `0x10006a4e`
- name: `_WBISAMBeginSession@4`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x10006960`
- `0x1002580a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006969`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100069ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006969`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x100069ec`
- `msjet40!__imp__JetGetSystemParameter@24` at `0x10006a2e`
- `msjet40!__imp__JetGetSystemParameter@24` at `0x10006a2e`

## pseudocode

```c
int __stdcall WBISAMBeginSession(int *a1)
{
  DWORD CurrentProcessId; // eax
  _DWORD *v2; // esi
  _DWORD *v4; // eax
  _DWORD *v5; // edi
  int v6; // eax
  int v7; // eax
  DWORD v8; // eax
  _DWORD *v9; // ecx
  int v10; // [esp+4h] [ebp-8h] BYREF
  int v11; // [esp+8h] [ebp-4h]

  CurrentProcessId = GetCurrentProcessId();
  v2 = (_DWORD *)dword_1003AE68;
  if ( !dword_1003AE68 )
    return -1029;
  while ( v2[4] != CurrentProcessId )
  {
    v2 = (_DWORD *)*v2;
    if ( !v2 )
      return -1029;
  }
  if ( !v2 )
    return -1029;
  v11 = *a1;
  v4 = (_DWORD *)MemAllocate(24);
  v5 = v4;
  if ( !v4 )
    return -1011;
  v4[1] = v2;
  *v4 = v2[1];
  v6 = dword_1003A660;
  v2[1] = v5;
  v5[3] = v6;
  dword_1003A660 = v6 + 1;
  v5[4] = v11;
  v7 = *a1;
  v5[3] = *a1;
  dword_1003AE5C = v7;
  v8 = GetCurrentProcessId();
  v9 = (_DWORD *)dword_1003AE68;
  if ( dword_1003AE68 )
  {
    while ( v9[4] != v8 )
    {
      v9 = (_DWORD *)*v9;
      if ( !v9 )
      {
        *a1 = v5[3];
        return 0;
      }
    }
    if ( v9 )
    {
      if ( !JetGetSystemParameter(v9[8], *a1, 64, &v10, 0, 0) )
        v5[5] = v10;
    }
  }
  *a1 = v5[3];
  return 0;
}

```

## disassembly

```asm
0x10006960  mov     edi, edi
0x10006962  push    ebp
0x10006963  mov     ebp, esp
0x10006965  sub     esp, 8
0x10006968  push    esi
0x10006969  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1000696f  mov     esi, dword_1003AE68
0x10006975  test    esi, esi
0x10006977  jz      short loc_1000698B
0x10006979  nop     dword ptr [eax+00000000h]
0x10006980  cmp     [esi+10h], eax
0x10006983  jz      short loc_10006997
0x10006985  mov     esi, [esi]
0x10006987  test    esi, esi
0x10006989  jnz     short loc_10006980
0x1000698b  mov     eax, 0FFFFFBFBh
0x10006990  pop     esi
0x10006991  mov     esp, ebp
0x10006993  pop     ebp
0x10006994  retn    4
0x10006997  test    esi, esi
0x10006999  jz      short loc_1000698B
0x1000699b  push    ebx
0x1000699c  mov     ebx, [ebp+arg_0]
0x1000699f  mov     ecx, 18h
0x100069a4  push    edi
0x100069a5  mov     eax, [ebx]
0x100069a7  mov     [ebp+var_4], eax
0x100069aa  call    _MemAllocate@4; MemAllocate(x)
0x100069af  mov     edi, eax
0x100069b1  test    edi, edi
0x100069b3  jnz     short loc_100069C3
0x100069b5  pop     edi
0x100069b6  pop     ebx
0x100069b7  mov     eax, 0FFFFFC0Dh
0x100069bc  pop     esi
0x100069bd  mov     esp, ebp
0x100069bf  pop     ebp
0x100069c0  retn    4
0x100069c3  mov     [edi+4], esi
0x100069c6  mov     eax, [esi+4]
0x100069c9  mov     [edi], eax
0x100069cb  mov     eax, dword_1003A660
0x100069d0  mov     [esi+4], edi
0x100069d3  mov     [edi+0Ch], eax
0x100069d6  inc     eax
0x100069d7  mov     dword_1003A660, eax
0x100069dc  mov     eax, [ebp+var_4]
0x100069df  mov     [edi+10h], eax
0x100069e2  mov     eax, [ebx]
0x100069e4  mov     [edi+0Ch], eax
0x100069e7  mov     dword_1003AE5C, eax
0x100069ec  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x100069f2  mov     ecx, dword_1003AE68
0x100069f8  test    ecx, ecx
0x100069fa  jz      short loc_10006A3E
0x100069fc  nop     dword ptr [eax+00h]
0x10006a00  cmp     [ecx+10h], eax
0x10006a03  jz      short loc_10006A1B
0x10006a05  mov     ecx, [ecx]
0x10006a07  test    ecx, ecx
0x10006a09  jnz     short loc_10006A00
0x10006a0b  mov     eax, [edi+0Ch]
0x10006a0e  pop     edi
0x10006a0f  mov     [ebx], eax
0x10006a11  xor     eax, eax
0x10006a13  pop     ebx
0x10006a14  pop     esi
0x10006a15  mov     esp, ebp
0x10006a17  pop     ebp
0x10006a18  retn    4
0x10006a1b  test    ecx, ecx
0x10006a1d  jz      short loc_10006A3E
0x10006a1f  push    0
0x10006a21  push    0
0x10006a23  lea     eax, [ebp+var_8]
0x10006a26  push    eax
0x10006a27  push    40h ; '@'
0x10006a29  push    dword ptr [ebx]
0x10006a2b  push    dword ptr [ecx+20h]
0x10006a2e  call    ds:__imp__JetGetSystemParameter@24; JetGetSystemParameter(x,x,x,x,x,x)
0x10006a34  test    eax, eax
0x10006a36  jnz     short loc_10006A3E
0x10006a38  mov     eax, [ebp+var_8]
0x10006a3b  mov     [edi+14h], eax
0x10006a3e  mov     eax, [edi+0Ch]
0x10006a41  pop     edi
0x10006a42  mov     [ebx], eax
0x10006a44  xor     eax, eax
0x10006a46  pop     ebx
0x10006a47  pop     esi
0x10006a48  mov     esp, ebp
0x10006a4a  pop     ebp
0x10006a4b  retn    4
```
