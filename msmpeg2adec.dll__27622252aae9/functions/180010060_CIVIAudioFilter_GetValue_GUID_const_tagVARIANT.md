# CIVIAudioFilter::GetValue(_GUID const *,tagVARIANT *)

- ea: `0x180010060`
- end: `0x180010453`
- name: `?GetValue@CIVIAudioFilter@@UEAAJPEBU_GUID@@PEAUtagVARIANT@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, const struct _GUID *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b900`
- `0x180010060`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001010f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001010f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800100f9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800100f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010124`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010124`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetValue(CIVIAudioFilter *this, const struct _GUID *a2, struct tagVARIANT *a3)
{
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  GUID *v8; // rcx
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  LPOLESTR v11; // rcx
  __int64 result; // rax
  __int64 v13; // rax
  LPOLESTR lpsz; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data4 )
  {
    v4 = *((_DWORD *)this - 2226);
    lpsz = 0;
    if ( !v4 )
    {
      v8 = &GUID_696e1d30_548f_4036_825f_7026c60011bd;
      goto LABEL_15;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      v8 = &GUID_696e1d31_548f_4036_825f_7026c60011bd;
      goto LABEL_15;
    }
    v6 = v5 - 2;
    if ( !v6 )
    {
      v8 = &GUID_696e1d33_548f_4036_825f_7026c60011bd;
      goto LABEL_15;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      v8 = &GUID_696e1d34_548f_4036_825f_7026c60011bd;
      goto LABEL_15;
    }
    if ( v7 == 1 )
    {
      v8 = &GUID_696e1d35_548f_4036_825f_7026c60011bd;
LABEL_15:
      StringFromCLSID(v8, &lpsz);
      v9 = lpsz;
      a3->vt = 8;
      v10 = SysAllocString(v9);
      v11 = lpsz;
      a3->llVal = (LONGLONG)v10;
      CoTaskMemFree(v11);
      return 0;
    }
    return 2147500037LL;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_b887974e_bb98_46db_942f_6dc0310c243d.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_b887974e_bb98_46db_942f_6dc0310c243d.Data4 )
  {
    v13 = *((_QWORD *)this - 1896);
    if ( v13 && *(_QWORD *)(v13 + 48) )
      return AssembleCurrentConfigBlob(*((_DWORD *)this - 2226) == 3, a3);
    return 2147500037LL;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2221);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2224);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2222);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2223);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2216);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2220);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2218) != 0;
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4 )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2179);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4 )
  {
    a3->vt = 3;
    a3->lVal = *((_DWORD *)this - 2215);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == 0x4DC5CFC22B50583DLL && *(_QWORD *)a2->Data4 == 0x693FDCA3C027B2B7LL )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2219);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == 0x416E4FBFFFFFFFFFLL && *(_QWORD *)a2->Data4 == 0x16661DE94415FF93LL )
  {
    a3->vt = 19;
    a3->lVal = *((_DWORD *)this - 2237);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 != 0x316B3EBAFFFFFFFFLL || *(_QWORD *)a2->Data4 != 0xD5742DC85426EF23uLL )
    return 2147942487LL;
  a3->vt = 11;
  result = 0;
  a3->iVal = -(*((_BYTE *)this - 14808) != 0);
  return result;
}

```

## disassembly

```asm
0x180010060  mov     [rsp+arg_0], rbx
0x180010065  push    rdi
0x180010066  sub     rsp, 20h
0x18001006a  mov     rbx, r8
0x18001006d  test    rdx, rdx
0x180010070  jz      loc_180010440
0x180010076  test    rbx, rbx
0x180010079  jz      loc_180010440
0x18001007f  mov     rax, [rdx]
0x180010082  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data1
0x180010089  jnz     loc_18001013E
0x18001008f  mov     rax, [rdx+8]
0x180010093  cmp     rax, qword ptr cs:_GUID_3c790028_c0ce_4256_b1a2_1b0fc8b1dcdc.Data4
0x18001009a  jnz     loc_18001013E
0x1800100a0  mov     ecx, [rcx-22C8h]
0x1800100a6  xor     edi, edi
0x1800100a8  mov     [rsp+28h+lpsz], rdi
0x1800100ad  test    ecx, ecx
0x1800100af  jz      short loc_1800100ED
0x1800100b1  sub     ecx, 1
0x1800100b4  jz      short loc_1800100E4
0x1800100b6  sub     ecx, 2
0x1800100b9  jz      short loc_1800100DB
0x1800100bb  sub     ecx, 1
0x1800100be  jz      short loc_1800100D2
0x1800100c0  cmp     ecx, 1
0x1800100c3  jnz     loc_18001018B
0x1800100c9  lea     rcx, _GUID_696e1d35_548f_4036_825f_7026c60011bd
0x1800100d0  jmp     short loc_1800100F4
0x1800100d2  lea     rcx, _GUID_696e1d34_548f_4036_825f_7026c60011bd
0x1800100d9  jmp     short loc_1800100F4
0x1800100db  lea     rcx, _GUID_696e1d33_548f_4036_825f_7026c60011bd
0x1800100e2  jmp     short loc_1800100F4
0x1800100e4  lea     rcx, _GUID_696e1d31_548f_4036_825f_7026c60011bd
0x1800100eb  jmp     short loc_1800100F4
0x1800100ed  lea     rcx, _GUID_696e1d30_548f_4036_825f_7026c60011bd; rclsid
0x1800100f4  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x1800100f9  call    cs:__imp_StringFromCLSID
0x180010100  nop     dword ptr [rax+rax+00h]
0x180010105  mov     rcx, [rsp+28h+lpsz]; psz
0x18001010a  mov     word ptr [rbx], 8
0x18001010f  call    cs:__imp_SysAllocString
0x180010116  nop     dword ptr [rax+rax+00h]
0x18001011b  mov     rcx, [rsp+28h+lpsz]; pv
0x180010120  mov     [rbx+8], rax
0x180010124  call    cs:__imp_CoTaskMemFree
0x18001012b  nop     dword ptr [rax+rax+00h]
0x180010130  mov     eax, edi
0x180010132  mov     rbx, [rsp+28h+arg_0]
0x180010137  add     rsp, 20h
0x18001013b  pop     rdi
0x18001013c  retn
0x18001013e  mov     rax, [rdx]
0x180010141  cmp     rax, qword ptr cs:_GUID_b887974e_bb98_46db_942f_6dc0310c243d.Data1
0x180010148  jnz     short loc_18001019E
0x18001014a  mov     rax, [rdx+8]
0x18001014e  cmp     rax, qword ptr cs:_GUID_b887974e_bb98_46db_942f_6dc0310c243d.Data4
0x180010155  jnz     short loc_18001019E
0x180010157  mov     rax, [rcx-3B40h]
0x18001015e  test    rax, rax
0x180010161  jz      short loc_18001018B
0x180010163  cmp     qword ptr [rax+30h], 0
0x180010168  jz      short loc_18001018B
0x18001016a  xor     edi, edi
0x18001016c  mov     rdx, rbx
0x18001016f  cmp     dword ptr [rcx-22C8h], 3
0x180010176  setz    dil
0x18001017a  mov     ecx, edi
0x18001017c  mov     rbx, [rsp+28h+arg_0]
0x180010181  add     rsp, 20h
0x180010185  pop     rdi
0x180010186  jmp     ?AssembleCurrentConfigBlob@@YAJU_DTV_Audio_Playback_Modes@@PEAUtagVARIANT@@@Z; AssembleCurrentConfigBlob(_DTV_Audio_Playback_Modes,tagVARIANT *)
0x18001018b  mov     edi, 80004005h
0x180010190  mov     eax, edi
0x180010192  mov     rbx, [rsp+28h+arg_0]
0x180010197  add     rsp, 20h
0x18001019b  pop     rdi
0x18001019c  retn
0x18001019e  mov     rax, [rdx]
0x1800101a1  xor     edi, edi
0x1800101a3  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data1
0x1800101aa  jnz     short loc_1800101D7
0x1800101ac  mov     rax, [rdx+8]
0x1800101b0  cmp     rax, qword ptr cs:_GUID_a5106186_cc94_4bc9_8cd9_aa2f61f6807e.Data4
0x1800101b7  jnz     short loc_1800101D7
0x1800101b9  mov     word ptr [r8], 13h
0x1800101bf  mov     eax, [rcx-22B4h]
0x1800101c5  mov     [r8+8], eax
0x1800101c9  mov     eax, edi
0x1800101cb  mov     rbx, [rsp+28h+arg_0]
0x1800101d0  add     rsp, 20h
0x1800101d4  pop     rdi
0x1800101d5  retn
0x1800101d7  mov     rax, [rdx]
0x1800101da  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data1
0x1800101e1  jnz     short loc_18001020E
0x1800101e3  mov     rax, [rdx+8]
0x1800101e7  cmp     rax, qword ptr cs:_GUID_d6d6c6d1_064e_4fdd_a40e_3ecbfcb7ebd0.Data4
0x1800101ee  jnz     short loc_18001020E
0x1800101f0  mov     word ptr [r8], 13h
0x1800101f6  mov     eax, [rcx-22C0h]
0x1800101fc  mov     [r8+8], eax
0x180010200  mov     eax, edi
0x180010202  mov     rbx, [rsp+28h+arg_0]
0x180010207  add     rsp, 20h
0x18001020b  pop     rdi
0x18001020c  retn
0x18001020e  mov     rax, [rdx]
0x180010211  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data1
0x180010218  jnz     short loc_180010245
0x18001021a  mov     rax, [rdx+8]
0x18001021e  cmp     rax, qword ptr cs:_GUID_50196c21_1f33_4af5_b296_11426d6c8789.Data4
0x180010225  jnz     short loc_180010245
0x180010227  mov     word ptr [r8], 13h
0x18001022d  mov     eax, [rcx-22B8h]
0x180010233  mov     [r8+8], eax
0x180010237  mov     eax, edi
0x180010239  mov     rbx, [rsp+28h+arg_0]
0x18001023e  add     rsp, 20h
0x180010242  pop     rdi
0x180010243  retn
0x180010245  mov     rax, [rdx]
0x180010248  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data1
0x18001024f  jnz     short loc_18001027C
0x180010251  mov     rax, [rdx+8]
0x180010255  cmp     rax, qword ptr cs:_GUID_044e62e4_11a5_42d5_a3b2_3bb2c7c2d7cf.Data4
0x18001025c  jnz     short loc_18001027C
0x18001025e  mov     word ptr [r8], 13h
0x180010264  mov     eax, [rcx-22BCh]
0x18001026a  mov     [r8+8], eax
0x18001026e  mov     eax, edi
0x180010270  mov     rbx, [rsp+28h+arg_0]
0x180010275  add     rsp, 20h
0x180010279  pop     rdi
0x18001027a  retn
0x18001027c  mov     rax, [rdx]
0x18001027f  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data1
0x180010286  jnz     short loc_1800102B3
0x180010288  mov     rax, [rdx+8]
0x18001028c  cmp     rax, qword ptr cs:_GUID_287c8abe_69a4_4d39_8080_d3d9712178a0.Data4
0x180010293  jnz     short loc_1800102B3
0x180010295  mov     word ptr [r8], 13h
0x18001029b  mov     eax, [rcx-22A0h]
0x1800102a1  mov     [r8+8], eax
0x1800102a5  mov     eax, edi
0x1800102a7  mov     rbx, [rsp+28h+arg_0]
0x1800102ac  add     rsp, 20h
0x1800102b0  pop     rdi
0x1800102b1  retn
0x1800102b3  mov     rax, [rdx]
0x1800102b6  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data1
0x1800102bd  jnz     short loc_1800102EA
0x1800102bf  mov     rax, [rdx+8]
0x1800102c3  cmp     rax, qword ptr cs:_GUID_8afd1a15_1812_4cbf_9319_433a5b2a3b27.Data4
0x1800102ca  jnz     short loc_1800102EA
0x1800102cc  mov     word ptr [r8], 13h
0x1800102d2  mov     eax, [rcx-22B0h]
0x1800102d8  mov     [r8+8], eax
0x1800102dc  mov     eax, edi
0x1800102de  mov     rbx, [rsp+28h+arg_0]
0x1800102e3  add     rsp, 20h
0x1800102e7  pop     rdi
0x1800102e8  retn
0x1800102ea  mov     rax, [rdx]
0x1800102ed  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data1
0x1800102f4  jnz     short loc_180010326
0x1800102f6  mov     rax, [rdx+8]
0x1800102fa  cmp     rax, qword ptr cs:_GUID_5612bca1_56da_4582_8da1_ca8090f92768.Data4
0x180010301  jnz     short loc_180010326
0x180010303  mov     eax, edi
0x180010305  mov     word ptr [r8], 13h
0x18001030b  cmp     [rcx-22A8h], eax
0x180010311  setnz   al
0x180010314  mov     [r8+8], eax
0x180010318  mov     eax, edi
0x18001031a  mov     rbx, [rsp+28h+arg_0]
0x18001031f  add     rsp, 20h
0x180010323  pop     rdi
0x180010324  retn
0x180010326  mov     rax, [rdx]
0x180010329  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data1
0x180010330  jnz     short loc_18001035D
0x180010332  mov     rax, [rdx+8]
0x180010336  cmp     rax, qword ptr cs:_GUID_01274475_f6bb_4017_b084_81a763c942d4.Data4
0x18001033d  jnz     short loc_18001035D
0x18001033f  mov     word ptr [r8], 13h
0x180010345  mov     eax, [rcx-220Ch]
0x18001034b  mov     [r8+8], eax
0x18001034f  mov     eax, edi
0x180010351  mov     rbx, [rsp+28h+arg_0]
0x180010356  add     rsp, 20h
0x18001035a  pop     rdi
0x18001035b  retn
0x18001035d  mov     rax, [rdx]
0x180010360  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data1
0x180010367  jnz     short loc_180010394
0x180010369  mov     rax, [rdx+8]
0x18001036d  cmp     rax, qword ptr cs:_GUID_4c437134_f9c2_4713_b2c2_6f3f456158e3.Data4
0x180010374  jnz     short loc_180010394
0x180010376  mov     word ptr [r8], 3
0x18001037c  mov     eax, [rcx-229Ch]
0x180010382  mov     [r8+8], eax
0x180010386  mov     eax, edi
0x180010388  mov     rbx, [rsp+28h+arg_0]
0x18001038d  add     rsp, 20h
0x180010391  pop     rdi
0x180010392  retn
0x180010394  mov     rax, [rdx]
0x180010397  cmp     rax, qword ptr cs:stru_18008DAC8.Data1
0x18001039e  jnz     short loc_1800103CB
0x1800103a0  mov     rax, [rdx+8]
0x1800103a4  cmp     rax, qword ptr cs:stru_18008DAC8.Data4
0x1800103ab  jnz     short loc_1800103CB
0x1800103ad  mov     word ptr [r8], 13h
0x1800103b3  mov     eax, [rcx-22ACh]
0x1800103b9  mov     [r8+8], eax
0x1800103bd  mov     eax, edi
0x1800103bf  mov     rbx, [rsp+28h+arg_0]
0x1800103c4  add     rsp, 20h
0x1800103c8  pop     rdi
0x1800103c9  retn
0x1800103cb  mov     rax, [rdx]
0x1800103ce  cmp     rax, cs:qword_18008DC90
0x1800103d5  jnz     short loc_180010402
0x1800103d7  mov     rax, [rdx+8]
0x1800103db  cmp     rax, cs:qword_18008DC98
0x1800103e2  jnz     short loc_180010402
0x1800103e4  mov     word ptr [r8], 13h
0x1800103ea  mov     eax, [rcx-22F4h]
0x1800103f0  mov     [r8+8], eax
0x1800103f4  mov     eax, edi
0x1800103f6  mov     rbx, [rsp+28h+arg_0]
0x1800103fb  add     rsp, 20h
0x1800103ff  pop     rdi
0x180010400  retn
0x180010402  mov     rax, [rdx]
0x180010405  cmp     rax, cs:qword_18008DBE0
0x18001040c  jnz     short loc_180010440
0x18001040e  mov     rax, [rdx+8]
0x180010412  cmp     rax, cs:qword_18008DBE8
0x180010419  jnz     short loc_180010440
0x18001041b  mov     word ptr [r8], 0Bh
0x180010421  movzx   eax, byte ptr [rcx-39D8h]
0x180010428  neg     al
0x18001042a  mov     eax, edi
0x18001042c  sbb     cx, cx
0x18001042f  mov     [r8+8], cx
0x180010434  mov     rbx, [rsp+28h+arg_0]
0x180010439  add     rsp, 20h
0x18001043d  pop     rdi
0x18001043e  retn
0x180010440  mov     rbx, [rsp+28h+arg_0]
0x180010445  mov     edi, 80070057h
0x18001044a  mov     eax, edi
0x18001044c  add     rsp, 20h
0x180010450  pop     rdi
0x180010451  retn
```
