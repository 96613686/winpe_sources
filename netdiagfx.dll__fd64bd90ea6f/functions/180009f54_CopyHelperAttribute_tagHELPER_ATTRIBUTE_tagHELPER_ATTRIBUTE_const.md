# CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)

- ea: `0x180009f54`
- end: `0x18000a11e`
- name: `?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a124`
- `0x18000acf0`
- `0x180011810`
- `0x1800184d4`
- `0x18001a5b4`
- `0x18001a668`
- `0x180027ce0`
- `0x180028254`

## callees

- `0x1800020d6`
- `0x1800040b4`
- `0x1800070d4`
- `0x180008ca8`
- `0x180009f54`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a03d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a03d`

## pseudocode

```c
__int64 __fastcall CopyHelperAttribute(struct tagHELPER_ATTRIBUTE *a1, const struct tagHELPER_ATTRIBUTE *a2)
{
  const unsigned __int16 *pwszName; // r9
  unsigned int v5; // edx
  const unsigned __int16 *v6; // r8
  unsigned int v7; // edx
  int v8; // esi
  const unsigned __int16 *v9; // r8
  ATTRIBUTE_TYPE type; // eax
  unsigned __int16 *v11; // r14
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  unsigned __int16 *v20; // rax
  const unsigned __int16 *PWStr; // r9
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  unsigned __int8 v31; // [rsp+20h] [rbp-69h]
  unsigned __int8 v32; // [rsp+20h] [rbp-69h]
  unsigned int v33; // [rsp+28h] [rbp-61h]
  unsigned int v34; // [rsp+28h] [rbp-61h]
  __int128 *v35; // [rsp+30h] [rbp-59h] BYREF
  __int64 v36; // [rsp+38h] [rbp-51h]
  __int128 v37; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 *v38[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v39; // [rsp+60h] [rbp-29h]
  __int128 v40; // [rsp+70h] [rbp-19h]
  __int128 v41; // [rsp+80h] [rbp-9h]
  __int128 v42; // [rsp+90h] [rbp+7h]
  __int128 v43; // [rsp+A0h] [rbp+17h]
  __int128 v44; // [rsp+B0h] [rbp+27h]
  __int128 v45; // [rsp+C0h] [rbp+37h]
  unsigned __int16 *v46; // [rsp+F0h] [rbp+67h] BYREF

  if ( a1 && a2 )
  {
    memset_0(&v37, 0, 0x90u);
    pwszName = a2->pwszName;
    v35 = &v37;
    v36 = 1;
    v46 = 0;
    v8 = UtilAssembleStringsWithAlloc(&v46, v5, v6, pwszName, v31, v33);
    if ( v8 < 0 )
    {
LABEL_16:
      TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>(&v35);
      return (unsigned int)v8;
    }
    type = a2->type;
    v11 = v46;
    DWORD2(v37) = type;
    if ( type == AT_STRING )
    {
      PWStr = a2->PWStr;
      if ( PWStr )
      {
        v8 = UtilAssembleStringsWithAlloc(v38, v7, v9, PWStr, v32, v34);
        if ( v8 < 0 )
          goto LABEL_15;
      }
    }
    else if ( type == AT_OCTET_STRING )
    {
      if ( a2->OctetString.lpValue && a2->Boolean )
      {
        v20 = (unsigned __int16 *)CoTaskMemAlloc(a2->DWord);
        v38[1] = v20;
        if ( !v20 )
        {
          v8 = -2147024882;
LABEL_15:
          TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v46);
          goto LABEL_16;
        }
        memcpy_0(v20, a2->OctetString.lpValue, a2->DWord);
        LODWORD(v38[0]) = a2->Boolean;
      }
    }
    else
    {
      v12 = *(_OWORD *)&a2->Boolean;
      v37 = *(_OWORD *)&a2->pwszName;
      v13 = *((_OWORD *)&a2->OctetString + 1);
      *(_OWORD *)v38 = v12;
      v14 = *((_OWORD *)&a2->OctetString + 2);
      v39 = v13;
      v15 = *((_OWORD *)&a2->OctetString + 3);
      v40 = v14;
      v16 = *((_OWORD *)&a2->OctetString + 4);
      v41 = v15;
      v17 = *((_OWORD *)&a2->OctetString + 5);
      v42 = v16;
      v18 = *((_OWORD *)&a2->OctetString + 6);
      v43 = v17;
      v19 = *((_OWORD *)&a2->OctetString + 7);
      v44 = v18;
      v45 = v19;
    }
    v22 = *(_OWORD *)v38;
    *(_QWORD *)&v37 = v11;
    *(_OWORD *)&a1->pwszName = v37;
    v46 = 0;
    v23 = v39;
    *(_OWORD *)&a1->Boolean = v22;
    v35 = 0;
    v24 = v40;
    *((_OWORD *)&a1->OctetString + 1) = v23;
    LODWORD(v36) = 0;
    v25 = v41;
    *((_OWORD *)&a1->OctetString + 2) = v24;
    v26 = v42;
    *((_OWORD *)&a1->OctetString + 3) = v25;
    v27 = v43;
    *((_OWORD *)&a1->OctetString + 4) = v26;
    v28 = v44;
    *((_OWORD *)&a1->OctetString + 5) = v27;
    v29 = v45;
    *((_OWORD *)&a1->OctetString + 6) = v28;
    *((_OWORD *)&a1->OctetString + 7) = v29;
    goto LABEL_15;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009f54  mov     [rsp-8+arg_8], rbx
0x180009f59  mov     [rsp-8+arg_10], rsi
0x180009f5e  push    rbp
0x180009f5f  push    rdi
0x180009f60  push    r14
0x180009f62  lea     rbp, [rsp-47h]
0x180009f67  sub     rsp, 0D0h
0x180009f6e  mov     rbx, rdx
0x180009f71  mov     rdi, rcx
0x180009f74  test    rcx, rcx
0x180009f77  jz      loc_18000A101
0x180009f7d  test    rdx, rdx
0x180009f80  jz      loc_18000A101
0x180009f86  xor     edx, edx; Val
0x180009f88  lea     rcx, [rbp+57h+var_A0]; void *
0x180009f8c  mov     r8d, 90h; Size
0x180009f92  call    memset_0
0x180009f97  mov     r9, [rbx]; unsigned __int16 *
0x180009f9a  lea     rax, [rbp+57h+var_A0]
0x180009f9e  lea     rcx, [rbp+57h+arg_0]; unsigned __int16 **
0x180009fa2  mov     [rbp+57h+var_B0], rax
0x180009fa6  mov     [rbp+57h+var_A8], 1
0x180009fae  mov     [rbp+57h+arg_0], 0
0x180009fb6  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x180009fbb  mov     esi, eax
0x180009fbd  test    eax, eax
0x180009fbf  js      loc_18000A0F4
0x180009fc5  mov     eax, [rbx+8]
0x180009fc8  mov     r14, [rbp+57h+arg_0]
0x180009fcc  mov     [rbp+57h+arg_0], r14
0x180009fd0  mov     dword ptr [rbp+57h+var_A0+8], eax
0x180009fd3  cmp     eax, 0Ah
0x180009fd6  jz      loc_18000A06E
0x180009fdc  cmp     eax, 0Eh
0x180009fdf  jz      short loc_18000A02D
0x180009fe1  movups  xmm0, xmmword ptr [rbx]
0x180009fe4  movups  xmm1, xmmword ptr [rbx+10h]
0x180009fe8  movups  [rbp+57h+var_A0], xmm0
0x180009fec  movups  xmm0, xmmword ptr [rbx+20h]
0x180009ff0  movups  xmmword ptr [rbp+57h+var_90], xmm1
0x180009ff4  movups  xmm1, xmmword ptr [rbx+30h]
0x180009ff8  movups  [rbp+57h+var_80], xmm0
0x180009ffc  movups  xmm0, xmmword ptr [rbx+40h]
0x18000a000  movups  [rbp+57h+var_70], xmm1
0x18000a004  movups  xmm1, xmmword ptr [rbx+50h]
0x18000a008  movups  [rbp+57h+var_60], xmm0
0x18000a00c  movups  xmm0, xmmword ptr [rbx+60h]
0x18000a010  movups  [rbp+57h+var_50], xmm1
0x18000a014  movups  xmm1, xmmword ptr [rbx+70h]
0x18000a018  movups  [rbp+57h+var_40], xmm0
0x18000a01c  movups  xmm0, xmmword ptr [rbx+80h]
0x18000a023  movups  [rbp+57h+var_30], xmm1
0x18000a027  movups  [rbp+57h+var_20], xmm0
0x18000a02b  jmp     short loc_18000A086
0x18000a02d  cmp     qword ptr [rbx+18h], 0
0x18000a032  jz      short loc_18000A086
0x18000a034  cmp     dword ptr [rbx+10h], 0
0x18000a038  jbe     short loc_18000A086
0x18000a03a  mov     ecx, [rbx+10h]; cb
0x18000a03d  call    cs:__imp_CoTaskMemAlloc
0x18000a043  mov     [rbp+57h+var_90+8], rax
0x18000a047  test    rax, rax
0x18000a04a  jnz     short loc_18000A056
0x18000a04c  mov     esi, 8007000Eh
0x18000a051  jmp     loc_18000A0EB
0x18000a056  mov     r8d, [rbx+10h]; Size
0x18000a05a  mov     rcx, rax; void *
0x18000a05d  mov     rdx, [rbx+18h]; Src
0x18000a061  call    memcpy_0
0x18000a066  mov     eax, [rbx+10h]
0x18000a069  mov     dword ptr [rbp+57h+var_90], eax
0x18000a06c  jmp     short loc_18000A086
0x18000a06e  mov     r9, [rbx+10h]; unsigned __int16 *
0x18000a072  test    r9, r9
0x18000a075  jz      short loc_18000A086
0x18000a077  lea     rcx, [rbp+57h+var_90]; unsigned __int16 **
0x18000a07b  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000a080  mov     esi, eax
0x18000a082  test    eax, eax
0x18000a084  js      short loc_18000A0EB
0x18000a086  movaps  xmm1, xmmword ptr [rbp+57h+var_90]
0x18000a08a  mov     qword ptr [rbp+57h+var_A0], r14
0x18000a08e  movaps  xmm0, [rbp+57h+var_A0]
0x18000a092  movups  xmmword ptr [rdi], xmm0
0x18000a095  mov     [rbp+57h+arg_0], 0
0x18000a09d  movaps  xmm0, [rbp+57h+var_80]
0x18000a0a1  movups  xmmword ptr [rdi+10h], xmm1
0x18000a0a5  mov     [rbp+57h+var_B0], 0
0x18000a0ad  movaps  xmm1, [rbp+57h+var_70]
0x18000a0b1  movups  xmmword ptr [rdi+20h], xmm0
0x18000a0b5  mov     dword ptr [rbp+57h+var_A8], 0
0x18000a0bc  movaps  xmm0, [rbp+57h+var_60]
0x18000a0c0  movups  xmmword ptr [rdi+30h], xmm1
0x18000a0c4  movaps  xmm1, [rbp+57h+var_50]
0x18000a0c8  movups  xmmword ptr [rdi+40h], xmm0
0x18000a0cc  movaps  xmm0, [rbp+57h+var_40]
0x18000a0d0  movups  xmmword ptr [rdi+50h], xmm1
0x18000a0d4  movaps  xmm1, [rbp+57h+var_30]
0x18000a0d8  movups  xmmword ptr [rdi+60h], xmm0
0x18000a0dc  movaps  xmm0, [rbp+57h+var_20]
0x18000a0e0  movups  xmmword ptr [rdi+70h], xmm1
0x18000a0e4  movups  xmmword ptr [rdi+80h], xmm0
0x18000a0eb  lea     rcx, [rbp+57h+arg_0]
0x18000a0ef  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18000a0f4  lea     rcx, [rbp+57h+var_B0]
0x18000a0f8  call    ??1?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>(void)
0x18000a0fd  mov     eax, esi
0x18000a0ff  jmp     short loc_18000A106
0x18000a101  mov     eax, 80070057h
0x18000a106  lea     r11, [rsp+0E0h+var_10]
0x18000a10e  mov     rbx, [r11+28h]
0x18000a112  mov     rsi, [r11+30h]
0x18000a116  mov     rsp, r11
0x18000a119  pop     r14
0x18000a11b  pop     rdi
0x18000a11c  pop     rbp
0x18000a11d  retn
```
