# CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)

- ea: `0x1800087f8`
- end: `0x1800089ac`
- name: `?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180008580`
- `0x18000a9e0`

## callees

- `0x1800026a6`
- `0x1800087f8`
- `0x180008a60`
- `0x180009a9c`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800088bf`
- `ole32!CoTaskMemAlloc` at `0x1800088bf`
- `ole32!CoTaskMemFree` at `0x180008966`
- `ole32!CoTaskMemFree` at `0x180008966`

## pseudocode

```c
__int64 __fastcall CopyHelperAttribute(struct tagHELPER_ATTRIBUTE *a1, const struct tagHELPER_ATTRIBUTE *a2)
{
  const unsigned __int16 *pwszName; // r9
  unsigned int v5; // edx
  const unsigned __int16 *v6; // r8
  unsigned int v7; // edx
  int v8; // edi
  const unsigned __int16 *v9; // r8
  ATTRIBUTE_TYPE type; // eax
  WCHAR *v11; // r14
  __int128 v12; // xmm1
  __int128 v13; // xmm2
  __int128 v14; // xmm3
  __int128 v15; // xmm4
  __int128 v16; // xmm5
  __int128 v17; // xmm6
  __int128 v18; // xmm7
  __int128 v19; // xmm8
  BYTE *v20; // rax
  const unsigned __int16 *PWStr; // r9
  unsigned __int8 v23; // [rsp+28h] [rbp-A9h]
  unsigned __int8 v24; // [rsp+28h] [rbp-A9h]
  unsigned int v25; // [rsp+30h] [rbp-A1h]
  struct tagHELPER_ATTRIBUTE v26; // [rsp+38h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+138h] [rbp+67h] BYREF

  if ( a1 && a2 )
  {
    memset_0(&v26, 0, sizeof(v26));
    pwszName = a2->pwszName;
    pv = 0;
    v8 = UtilAssembleStringsWithAlloc((unsigned __int16 **)&pv, v5, v6, pwszName, v23, v25);
    if ( v8 < 0 )
    {
LABEL_19:
      FreeHelperAttributes(&v26, 1u, 0);
      return (unsigned int)v8;
    }
    type = a2->type;
    v11 = (WCHAR *)pv;
    v26.type = type;
    if ( type == AT_STRING )
    {
      PWStr = a2->PWStr;
      if ( PWStr )
      {
        v8 = UtilAssembleStringsWithAlloc(&v26.PWStr, v7, v9, PWStr, v24, v25);
        if ( v8 < 0 )
          goto LABEL_16;
      }
    }
    else
    {
      if ( type != AT_OCTET_STRING )
      {
        v12 = *(_OWORD *)&a2->Boolean;
        v13 = *((_OWORD *)&a2->OctetString + 1);
        v14 = *((_OWORD *)&a2->OctetString + 2);
        v15 = *((_OWORD *)&a2->OctetString + 3);
        v16 = *((_OWORD *)&a2->OctetString + 4);
        v17 = *((_OWORD *)&a2->OctetString + 5);
        v18 = *((_OWORD *)&a2->OctetString + 6);
        v19 = *((_OWORD *)&a2->OctetString + 7);
        *(_OWORD *)&v26.pwszName = *(_OWORD *)&a2->pwszName;
LABEL_13:
        v26.pwszName = v11;
        *(_OWORD *)&a1->pwszName = *(_OWORD *)&v26.pwszName;
        *(_OWORD *)&a1->Boolean = v12;
        *((_OWORD *)&a1->OctetString + 1) = v13;
        *((_OWORD *)&a1->OctetString + 2) = v14;
        *((_OWORD *)&a1->OctetString + 3) = v15;
        *((_OWORD *)&a1->OctetString + 4) = v16;
        *((_OWORD *)&a1->OctetString + 5) = v17;
        *((_OWORD *)&a1->OctetString + 6) = v18;
        *((_OWORD *)&a1->OctetString + 7) = v19;
        return (unsigned int)v8;
      }
      if ( a2->OctetString.lpValue && a2->Boolean )
      {
        v20 = (BYTE *)CoTaskMemAlloc(a2->DWord);
        v26.OctetString.lpValue = v20;
        if ( !v20 )
        {
          v8 = -2147024882;
LABEL_16:
          if ( v11 )
            CoTaskMemFree(v11);
          if ( !&v26 )
            return (unsigned int)v8;
          goto LABEL_19;
        }
        memcpy_0(v20, a2->OctetString.lpValue, a2->DWord);
        v26.Boolean = a2->Boolean;
      }
    }
    v12 = *(_OWORD *)&v26.Boolean;
    v13 = *((_OWORD *)&v26.OctetString + 1);
    v14 = *((_OWORD *)&v26.OctetString + 2);
    v15 = *((_OWORD *)&v26.OctetString + 3);
    v16 = *((_OWORD *)&v26.OctetString + 4);
    v17 = *((_OWORD *)&v26.OctetString + 5);
    v18 = *((_OWORD *)&v26.OctetString + 6);
    v19 = *((_OWORD *)&v26.OctetString + 7);
    goto LABEL_13;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800087f8  mov     rax, rsp
0x1800087fb  push    rbp
0x1800087fc  push    rbx
0x1800087fd  push    rsi
0x1800087fe  push    rdi
0x1800087ff  push    r12
0x180008801  push    r14
0x180008803  lea     rbp, [rax-5Fh]
0x180008807  sub     rsp, 0F8h
0x18000880e  movaps  xmmword ptr [rax-48h], xmm6
0x180008812  mov     rbx, rdx
0x180008815  movaps  xmmword ptr [rax-58h], xmm7
0x180008819  mov     rsi, rcx
0x18000881c  movaps  xmmword ptr [rax-68h], xmm8
0x180008821  test    rcx, rcx
0x180008824  jz      loc_180008984
0x18000882a  test    rdx, rdx
0x18000882d  jz      loc_180008984
0x180008833  xor     edx, edx; Val
0x180008835  lea     rcx, [rsp+120h+var_F8.type]; void *
0x18000883a  mov     r8d, 90h; Size
0x180008840  call    memset_0
0x180008845  mov     r9, [rbx]; unsigned __int16 *
0x180008848  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18000884c  lea     r12, [rsp+120h+var_F8.type]
0x180008851  mov     [rbp+57h+pv], 0
0x180008859  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000885e  mov     edi, eax
0x180008860  test    eax, eax
0x180008862  js      loc_180008971
0x180008868  mov     eax, [rbx+8]
0x18000886b  mov     r14, [rbp+57h+pv]
0x18000886f  mov     dword ptr [rsp+120h+var_F8.10h], eax
0x180008873  cmp     eax, 0Ah
0x180008876  jz      loc_180008945
0x18000887c  cmp     eax, 0Eh
0x18000887f  jz      short loc_1800088AF
0x180008881  movups  xmm0, xmmword ptr [rbx]
0x180008884  movups  xmm1, xmmword ptr [rbx+10h]
0x180008888  movups  xmm2, xmmword ptr [rbx+20h]
0x18000888c  movups  xmm3, xmmword ptr [rbx+30h]
0x180008890  movups  xmm4, xmmword ptr [rbx+40h]
0x180008894  movups  xmm5, xmmword ptr [rbx+50h]
0x180008898  movups  xmm6, xmmword ptr [rbx+60h]
0x18000889c  movups  xmm7, xmmword ptr [rbx+70h]
0x1800088a0  movups  xmm8, xmmword ptr [rbx+80h]
0x1800088a8  movups  xmmword ptr [rsp+120h+var_F8.type], xmm0
0x1800088ad  jmp     short loc_180008912
0x1800088af  cmp     qword ptr [rbx+18h], 0
0x1800088b4  jz      short loc_1800088F0
0x1800088b6  cmp     dword ptr [rbx+10h], 0
0x1800088ba  jbe     short loc_1800088F0
0x1800088bc  mov     ecx, [rbx+10h]; cb
0x1800088bf  call    cs:__imp_CoTaskMemAlloc
0x1800088c5  mov     qword ptr [rsp+120h+var_F8.10h+10h], rax
0x1800088ca  test    rax, rax
0x1800088cd  jnz     short loc_1800088D9
0x1800088cf  mov     edi, 8007000Eh
0x1800088d4  jmp     loc_18000895E
0x1800088d9  mov     r8d, [rbx+10h]; Size
0x1800088dd  mov     rcx, rax; void *
0x1800088e0  mov     rdx, [rbx+18h]; Src
0x1800088e4  call    memcpy_0
0x1800088e9  mov     eax, [rbx+10h]
0x1800088ec  mov     dword ptr [rsp+120h+var_F8.10h+8], eax
0x1800088f0  movaps  xmm1, xmmword ptr [rsp+120h+var_F8.10h+8]
0x1800088f5  movaps  xmm2, xmmword ptr [rbp+57h+var_F8.10h+18h]
0x1800088f9  movaps  xmm3, xmmword ptr [rbp+57h+var_F8.10h+28h]
0x1800088fd  movaps  xmm4, xmmword ptr [rbp+57h+var_F8.10h+38h]
0x180008901  movaps  xmm5, xmmword ptr [rbp+57h+var_F8.10h+48h]
0x180008905  movaps  xmm6, xmmword ptr [rbp+57h+var_F8.10h+58h]
0x180008909  movaps  xmm7, xmmword ptr [rbp+57h+var_F8.10h+68h]
0x18000890d  movaps  xmm8, xmmword ptr [rbp+57h+var_F8.10h+78h]
0x180008912  mov     qword ptr [rsp+120h+var_F8.type], r14
0x180008917  movaps  xmm0, xmmword ptr [rsp+120h+var_F8.type]
0x18000891c  movups  xmmword ptr [rsi], xmm0
0x18000891f  movups  xmmword ptr [rsi+10h], xmm1
0x180008923  movups  xmmword ptr [rsi+20h], xmm2
0x180008927  movups  xmmword ptr [rsi+30h], xmm3
0x18000892b  movups  xmmword ptr [rsi+40h], xmm4
0x18000892f  movups  xmmword ptr [rsi+50h], xmm5
0x180008933  movups  xmmword ptr [rsi+60h], xmm6
0x180008937  movups  xmmword ptr [rsi+70h], xmm7
0x18000893b  movups  xmmword ptr [rsi+80h], xmm8
0x180008943  jmp     short loc_180008980
0x180008945  mov     r9, [rbx+10h]; unsigned __int16 *
0x180008949  test    r9, r9
0x18000894c  jz      short loc_1800088F0
0x18000894e  lea     rcx, [rsp+120h+var_F8.10h+8]; unsigned __int16 **
0x180008953  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x180008958  mov     edi, eax
0x18000895a  test    eax, eax
0x18000895c  jns     short loc_1800088F0
0x18000895e  test    r14, r14
0x180008961  jz      short loc_18000896C
0x180008963  mov     rcx, r14; pv
0x180008966  call    cs:__imp_CoTaskMemFree
0x18000896c  test    r12, r12
0x18000896f  jz      short loc_180008980
0x180008971  xor     r8d, r8d; int
0x180008974  mov     rcx, r12; pv
0x180008977  lea     edx, [r8+1]; unsigned int
0x18000897b  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x180008980  mov     eax, edi
0x180008982  jmp     short loc_180008989
0x180008984  mov     eax, 80070057h
0x180008989  lea     r11, [rsp+120h+var_28]
0x180008991  movaps  xmm6, xmmword ptr [r11-18h]
0x180008996  movaps  xmm7, xmmword ptr [r11-28h]
0x18000899b  movaps  xmm8, xmmword ptr [r11-38h]
0x1800089a0  mov     rsp, r11
0x1800089a3  pop     r14
0x1800089a5  pop     r12
0x1800089a7  pop     rdi
0x1800089a8  pop     rsi
0x1800089a9  pop     rbx
0x1800089aa  pop     rbp
0x1800089ab  retn
```
