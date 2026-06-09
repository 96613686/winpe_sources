# ReadDirectoryDateTime(x)

- ea: `0x10029f76`
- end: `0x10029ff6`
- name: `_ReadDirectoryDateTime@4`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1002a000`
- `0x1002b527`

## callees

- `0x10024809`
- `0x10029f76`

## pseudocode

```c
__int64 __userpurge ReadDirectoryDateTime@<xmm0>(_DWORD *this@<ecx>)
{
  __int64 result; // xmm0_8
  int v2; // eax
  _DWORD *v3; // eax
  int v4; // esi
  int v5; // edi
  int v6; // ebx

  *(double *)&result = 0.0;
  v2 = *(_DWORD *)(this[3] + 8);
  if ( v2 )
  {
    v3 = *(_DWORD **)(v2 + 20);
    v4 = v3[13];
    v5 = v3[14];
    v6 = v3[15];
    MakeDate1900(v3[11], v3[10]);
    *(double *)&result = ((double)v4 * 3600.0 + (double)v5 * 60.0 + (double)v6) / 86400.0 + (double)0;
  }
  return result;
}

```

## disassembly

```asm
0x10029f76  mov     edi, edi
0x10029f78  push    ebp
0x10029f79  mov     ebp, esp
0x10029f7b  push    ecx
0x10029f7c  mov     eax, [ecx+0Ch]
0x10029f7f  xorps   xmm0, xmm0
0x10029f82  push    ebx
0x10029f83  push    esi
0x10029f84  push    edi
0x10029f85  mov     eax, [eax+8]
0x10029f88  mov     [ebp+var_4], 0
0x10029f8f  test    eax, eax
0x10029f91  jz      short loc_10029FF1
0x10029f93  mov     eax, [eax+14h]
0x10029f96  lea     ecx, [ebp+var_4]
0x10029f99  push    dword ptr [eax+28h]
0x10029f9c  mov     edx, [eax+30h]
0x10029f9f  push    dword ptr [eax+2Ch]
0x10029fa2  mov     esi, [eax+34h]
0x10029fa5  mov     edi, [eax+38h]
0x10029fa8  mov     ebx, [eax+3Ch]
0x10029fab  call    _MakeDate1900@16; MakeDate1900(x,x,x,x)
0x10029fb0  xorps   xmm0, xmm0
0x10029fb3  xorps   xmm1, xmm1
0x10029fb6  cvtsi2sd xmm0, esi
0x10029fba  cvtsi2sd xmm1, edi
0x10029fbe  mulsd   xmm0, ds:__real@40ac200000000000
0x10029fc6  mulsd   xmm1, ds:__real@404e000000000000
0x10029fce  addsd   xmm0, xmm1
0x10029fd2  xorps   xmm1, xmm1
0x10029fd5  cvtsi2sd xmm1, ebx
0x10029fd9  addsd   xmm0, xmm1
0x10029fdd  xorps   xmm1, xmm1
0x10029fe0  cvtsi2sd xmm1, [ebp+var_4]
0x10029fe5  divsd   xmm0, ds:__real@40f5180000000000
0x10029fed  addsd   xmm0, xmm1
0x10029ff1  pop     edi
0x10029ff2  pop     esi
0x10029ff3  pop     ebx
0x10029ff4  leave
0x10029ff5  retn
```
