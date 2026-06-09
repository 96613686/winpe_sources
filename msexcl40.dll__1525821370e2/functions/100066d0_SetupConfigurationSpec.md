# SetupConfigurationSpec

- ea: `0x100066d0`
- end: `0x10006835`
- name: `SetupConfigurationSpec`
- size: `357`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x10006840`
- `0x100068a0`
- `0x10006bd0`

## callees

- `0x100066d0`
- `0x1002580a`

## string_xrefs

- `0x10006808`: `DisabledExtensions`

## pseudocode

```c
int __thiscall SetupConfigurationSpec(void *this)
{
  int v2; // eax
  int v3; // edi
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax

  v2 = MemAllocate(8);
  v3 = v2;
  if ( !v2 )
    return 0;
  *(_DWORD *)v2 = 0;
  *(_BYTE *)(v2 + 4) = 1;
  v4 = MemAllocate(32);
  if ( v4 )
  {
    *(_BYTE *)(v4 + 4) = 1;
    *(_BYTE *)(v4 + 5) = (*(_BYTE *)(v3 + 4))++;
    *(_DWORD *)(v4 + 8) = L"TypeGuessRows";
    *(_DWORD *)(v4 + 12) = &ISAMDefaults;
    *(_DWORD *)(v4 + 16) = 8;
    *(_DWORD *)v4 = *(_DWORD *)v3;
    *(_DWORD *)v3 = v4;
  }
  v5 = MemAllocate(32);
  if ( v5 )
  {
    *(_BYTE *)(v5 + 4) = 1;
    *(_BYTE *)(v5 + 5) = (*(_BYTE *)(v3 + 4))++;
    *(_DWORD *)(v5 + 8) = L"AppendBlankRows";
    *(_DWORD *)(v5 + 12) = &dword_1003C2D8;
    *(_DWORD *)(v5 + 16) = 1;
    *(_DWORD *)v5 = *(_DWORD *)v3;
    *(_DWORD *)v3 = v5;
  }
  v6 = MemAllocate(32);
  if ( v6 )
  {
    *(_BYTE *)(v6 + 4) = 2;
    *(_BYTE *)(v6 + 5) = (*(_BYTE *)(v3 + 4))++;
    *(_DWORD *)(v6 + 8) = L"FirstRowHasNames";
    *(_DWORD *)(v6 + 12) = &dword_1003C2D4;
    *(_DWORD *)(v6 + 16) = 1;
    *(_DWORD *)v6 = *(_DWORD *)v3;
    *(_DWORD *)v3 = v6;
  }
  v7 = MemAllocate(32);
  if ( v7 )
  {
    *(_BYTE *)(v7 + 4) = 3;
    *(_BYTE *)(v7 + 5) = (*(_BYTE *)(v3 + 4))++;
    *(_DWORD *)(v7 + 8) = L"ImportMixedTypes";
    *(_DWORD *)(v7 + 12) = &dword_1003C2DC;
    *(_DWORD *)(v7 + 16) = 1;
    *(_DWORD *)(v7 + 20) = L"Majority Type";
    *(_DWORD *)(v7 + 24) = L"Text";
    *(_DWORD *)(v7 + 28) = 0;
    *(_DWORD *)v7 = *(_DWORD *)v3;
    *(_DWORD *)v3 = v7;
  }
  if ( !this )
  {
    v8 = MemAllocate(32);
    if ( v8 )
    {
      *(_BYTE *)(v8 + 4) = 0;
      *(_BYTE *)(v8 + 5) = (*(_BYTE *)(v3 + 4))++;
      *(_DWORD *)(v8 + 8) = L"DisabledExtensions";
      *(_DWORD *)(v8 + 16) = 1026;
      *(_DWORD *)(v8 + 12) = &DefaultSecureExtensions;
      *(_DWORD *)(v8 + 20) = L"!xls";
      *(_DWORD *)v8 = *(_DWORD *)v3;
      *(_DWORD *)v3 = v8;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x100066d0  mov     edi, edi
0x100066d2  push    ebx
0x100066d3  mov     ebx, ecx
0x100066d5  mov     ecx, 8
0x100066da  push    edi
0x100066db  call    _MemAllocate@4; MemAllocate(x)
0x100066e0  mov     edi, eax
0x100066e2  test    edi, edi
0x100066e4  jz      loc_10006830
0x100066ea  push    esi
0x100066eb  mov     ecx, 20h ; ' '
0x100066f0  mov     dword ptr [edi], 0
0x100066f6  mov     byte ptr [edi+4], 1
0x100066fa  call    _MemAllocate@4; MemAllocate(x)
0x100066ff  mov     edx, eax
0x10006701  test    edx, edx
0x10006703  jz      short loc_1000672D
0x10006705  mov     byte ptr [edx+4], 1
0x10006709  mov     cl, [edi+4]
0x1000670c  mov     [edx+5], cl
0x1000670f  inc     byte ptr [edi+4]
0x10006712  mov     dword ptr [edx+8], offset aTypeguessrows; "TypeGuessRows"
0x10006719  mov     dword ptr [edx+0Ch], offset _ISAMDefaults
0x10006720  mov     dword ptr [edx+10h], 8
0x10006727  mov     eax, [edi]
0x10006729  mov     [edx], eax
0x1000672b  mov     [edi], edx
0x1000672d  mov     ecx, 20h ; ' '
0x10006732  call    _MemAllocate@4; MemAllocate(x)
0x10006737  mov     edx, eax
0x10006739  test    edx, edx
0x1000673b  jz      short loc_10006765
0x1000673d  mov     byte ptr [edx+4], 1
0x10006741  mov     cl, [edi+4]
0x10006744  mov     [edx+5], cl
0x10006747  inc     byte ptr [edi+4]
0x1000674a  mov     dword ptr [edx+8], offset aAppendblankrow; "AppendBlankRows"
0x10006751  mov     dword ptr [edx+0Ch], offset dword_1003C2D8
0x10006758  mov     dword ptr [edx+10h], 1
0x1000675f  mov     eax, [edi]
0x10006761  mov     [edx], eax
0x10006763  mov     [edi], edx
0x10006765  mov     ecx, 20h ; ' '
0x1000676a  call    _MemAllocate@4; MemAllocate(x)
0x1000676f  mov     edx, eax
0x10006771  test    edx, edx
0x10006773  jz      short loc_1000679D
0x10006775  mov     byte ptr [edx+4], 2
0x10006779  mov     cl, [edi+4]
0x1000677c  mov     [edx+5], cl
0x1000677f  inc     byte ptr [edi+4]
0x10006782  mov     dword ptr [edx+8], offset aFirstrowhasnam; "FirstRowHasNames"
0x10006789  mov     dword ptr [edx+0Ch], offset dword_1003C2D4
0x10006790  mov     dword ptr [edx+10h], 1
0x10006797  mov     eax, [edi]
0x10006799  mov     [edx], eax
0x1000679b  mov     [edi], edx
0x1000679d  mov     ecx, 20h ; ' '
0x100067a2  call    _MemAllocate@4; MemAllocate(x)
0x100067a7  mov     edx, eax
0x100067a9  test    edx, edx
0x100067ab  jz      short loc_100067EA
0x100067ad  mov     byte ptr [edx+4], 3
0x100067b1  mov     cl, [edi+4]
0x100067b4  mov     [edx+5], cl
0x100067b7  inc     byte ptr [edi+4]
0x100067ba  mov     dword ptr [edx+8], offset aImportmixedtyp; "ImportMixedTypes"
0x100067c1  mov     dword ptr [edx+0Ch], offset dword_1003C2DC
0x100067c8  mov     dword ptr [edx+10h], 1
0x100067cf  mov     dword ptr [edx+14h], offset aMajorityType; "Majority Type"
0x100067d6  mov     dword ptr [edx+18h], offset aText; "Text"
0x100067dd  mov     dword ptr [edx+1Ch], 0
0x100067e4  mov     eax, [edi]
0x100067e6  mov     [edx], eax
0x100067e8  mov     [edi], edx
0x100067ea  test    ebx, ebx
0x100067ec  jnz     short loc_1000682A
0x100067ee  lea     ecx, [ebx+20h]
0x100067f1  call    _MemAllocate@4; MemAllocate(x)
0x100067f6  mov     edx, eax
0x100067f8  test    edx, edx
0x100067fa  jz      short loc_1000682A
0x100067fc  mov     [edx+4], bl
0x100067ff  mov     cl, [edi+4]
0x10006802  mov     [edx+5], cl
0x10006805  inc     byte ptr [edi+4]
0x10006808  mov     dword ptr [edx+8], offset aDisabledextens; "DisabledExtensions"
0x1000680f  mov     dword ptr [edx+10h], 402h
0x10006816  mov     dword ptr [edx+0Ch], offset _DefaultSecureExtensions
0x1000681d  mov     dword ptr [edx+14h], offset aXls_0; "!xls"
0x10006824  mov     eax, [edi]
0x10006826  mov     [edx], eax
0x10006828  mov     [edi], edx
0x1000682a  pop     esi
0x1000682b  mov     eax, edi
0x1000682d  pop     edi
0x1000682e  pop     ebx
0x1000682f  retn
0x10006830  pop     edi
0x10006831  xor     eax, eax
0x10006833  pop     ebx
0x10006834  retn
```
