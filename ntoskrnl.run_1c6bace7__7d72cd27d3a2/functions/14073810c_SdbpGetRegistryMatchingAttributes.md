# SdbpGetRegistryMatchingAttributes

- ea: `0x14073810c`
- end: `0x14073845a`
- name: `SdbpGetRegistryMatchingAttributes`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140823860`
- `0x1408240e0`

## callees

- `0x14041a320`
- `0x14073810c`
- `0x140738460`
- `0x140825864`
- `0x140825944`
- `0x1408c2580`
- `0x1408c293c`
- `0x1408c2c64`
- `0x1408c2f88`
- `0x1408c3154`

## string_xrefs

- `0x140738274`: `Unknown registry value type`
- `0x1407383c1`: `Failed to read value data size`
- `0x140738234`: `Failed to read value type`
- `0x14073839a`: `Failed to read value data`
- `0x140738411`: `Failed to read value data`
- `0x140738189`: `Failed to get key path tag`
- `0x140738420`: `Failed to read key path`
- `0x14073842d`: `SdbpGetRegistryMatchingAttributes`

## pseudocode

```c
__int64 __fastcall SdbpGetRegistryMatchingAttributes(
        __int64 a1,
        __int64 a2,
        __int16 **a3,
        __int64 *a4,
        _DWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        __int64 *a8,
        __int64 *a9,
        _QWORD *a10)
{
  __int64 TagDataSize; // rbp
  unsigned int v11; // edi
  unsigned int v13; // r13d
  unsigned int FirstTag; // eax
  __int64 StringTagPtr; // rax
  __int16 *v16; // rsi
  __int64 v17; // rdx
  __int16 UShortFromUser; // ax
  int v19; // r14d
  __int64 v20; // r12
  __int64 BinaryTagData; // r15
  unsigned int v22; // eax
  unsigned int v23; // eax
  int DWORDTag; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  __int64 QWORDTag; // rax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // edi
  unsigned int v35; // eax
  int v37; // [rsp+20h] [rbp-58h]
  __int64 v38; // [rsp+30h] [rbp-48h]

  TagDataSize = 0;
  *a3 = 0;
  v11 = a2;
  *a4 = 0;
  v13 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( FirstTag )
  {
    StringTagPtr = SdbGetStringTagPtr(a1, FirstTag);
    v16 = (__int16 *)StringTagPtr;
    if ( !StringTagPtr
      || (!(unsigned __int8)MmIsUserAddress(StringTagPtr)
        ? (UShortFromUser = *v16)
        : (UShortFromUser = RtlReadUShortFromUser(v16, v17)),
          !UShortFromUser) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetRegistryMatchingAttributes",
        1054,
        (unsigned int)"Failed to read key path");
      return v13;
    }
    v38 = 0;
    v37 = 0;
    v19 = 0;
    v20 = 0;
    BinaryTagData = 0;
    v22 = SdbFindFirstTag(a1, v11, 24624);
    if ( v22 )
      v38 = SdbGetStringTagPtr(a1, v22);
    v23 = SdbFindFirstTag(a1, v11, 16465);
    if ( v23 )
    {
      DWORDTag = SdbReadDWORDTag(a1, v23, 0);
      v19 = DWORDTag;
      if ( !DWORDTag )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetRegistryMatchingAttributes",
          1073,
          (unsigned int)"Failed to read value type");
        return v13;
      }
      v25 = DWORDTag - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( !v27 )
          {
            v33 = SdbFindFirstTag(a1, v11, 36882);
            v34 = v33;
            if ( !v33 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1120,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_BINARY");
              return v13;
            }
            BinaryTagData = SdbGetBinaryTagData(a1, v33);
            if ( !BinaryTagData )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1126,
                (unsigned int)"Failed to read value data");
              return v13;
            }
            TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v34);
            if ( TagDataSize == 0x20000000 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1132,
                (unsigned int)"Failed to read value data size");
              return v13;
            }
            QWORDTag = 0;
            goto LABEL_27;
          }
          v28 = v27 - 1;
          if ( !v28 )
          {
            v32 = SdbFindFirstTag(a1, v11, 16466);
            if ( !v32 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1100,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_DWORD");
              return v13;
            }
            v37 = SdbReadDWORDTag(a1, v32, 0);
            goto LABEL_26;
          }
          v29 = v28 - 3;
          if ( v29 )
          {
            if ( v29 != 4 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1138,
                (unsigned int)"Unknown registry value type");
              return v13;
            }
            v30 = SdbFindFirstTag(a1, v11, 20507);
            if ( !v30 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1110,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_QWORD");
              return v13;
            }
            QWORDTag = SdbReadQWORDTag(a1, v30, 0);
LABEL_27:
            v13 = 1;
            *a3 = v16;
            *a4 = v38;
            *a5 = v19;
            *a6 = v20;
            *a7 = v37;
            *a8 = QWORDTag;
            *a9 = BinaryTagData;
            *a10 = TagDataSize;
            return v13;
          }
        }
      }
      v35 = SdbFindFirstTag(a1, v11, 24625);
      if ( !v35 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetRegistryMatchingAttributes",
          1086,
          (unsigned int)"Failed to get TAG_REG_VALUE_DATA_SZ");
        return v13;
      }
      v20 = SdbGetStringTagPtr(a1, v35);
      if ( !v20 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetRegistryMatchingAttributes",
          1092,
          (unsigned int)"Failed to read value data");
        return v13;
      }
    }
LABEL_26:
    QWORDTag = 0;
    goto LABEL_27;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"SdbpGetRegistryMatchingAttributes",
    1042,
    (unsigned int)"Failed to get key path tag");
  return v13;
}

```

## disassembly

```asm
0x14073810c  mov     [rsp+arg_0], rbx
0x140738111  mov     [rsp+arg_18], r9
0x140738116  mov     [rsp+arg_10], r8
0x14073811b  push    rbp
0x14073811c  push    rsi
0x14073811d  push    rdi
0x14073811e  push    r12
0x140738120  push    r13
0x140738122  push    r14
0x140738124  push    r15
0x140738126  sub     rsp, 40h
0x14073812a  mov     rax, [rsp+78h+arg_20]
0x140738132  xor     ebp, ebp
0x140738134  mov     [r8], rbp
0x140738137  mov     edi, edx
0x140738139  mov     r8d, 6001h
0x14073813f  mov     [r9], rbp
0x140738142  mov     rbx, rcx
0x140738145  mov     r13d, ebp
0x140738148  mov     [rax], ebp
0x14073814a  mov     rax, [rsp+78h+arg_28]
0x140738152  mov     [rax], rbp
0x140738155  mov     rax, [rsp+78h+arg_30]
0x14073815d  mov     [rax], ebp
0x14073815f  mov     rax, [rsp+78h+arg_38]
0x140738167  mov     [rax], rbp
0x14073816a  mov     rax, [rsp+78h+arg_40]
0x140738172  mov     [rax], rbp
0x140738175  mov     rax, [rsp+78h+arg_48]
0x14073817d  mov     [rax], rbp
0x140738180  call    SdbFindFirstTag
0x140738185  test    eax, eax
0x140738187  jnz     short loc_14073819B
0x140738189  lea     r9, aFailedToGetKey; "Failed to get key path tag"
0x140738190  mov     r8d, 412h
0x140738196  jmp     loc_14073842D
0x14073819b  mov     edx, eax
0x14073819d  mov     rcx, rbx
0x1407381a0  call    SdbGetStringTagPtr
0x1407381a5  mov     rsi, rax
0x1407381a8  test    rax, rax
0x1407381ab  jz      loc_140738420
0x1407381b1  mov     rcx, rax
0x1407381b4  call    MmIsUserAddress
0x1407381b9  test    al, al
0x1407381bb  jz      short loc_1407381C7
0x1407381bd  mov     rcx, rsi
0x1407381c0  call    RtlReadUShortFromUser
0x1407381c5  jmp     short loc_1407381CA
0x1407381c7  movzx   eax, word ptr [rsi]
0x1407381ca  test    ax, ax
0x1407381cd  jz      loc_140738420
0x1407381d3  mov     r8d, 6030h
0x1407381d9  mov     [rsp+78h+var_48], rbp
0x1407381de  mov     edx, edi
0x1407381e0  mov     [rsp+78h+var_58], ebp
0x1407381e4  mov     rcx, rbx
0x1407381e7  mov     r14d, ebp
0x1407381ea  mov     r12, rbp
0x1407381ed  mov     r15, rbp
0x1407381f0  call    SdbFindFirstTag
0x1407381f5  test    eax, eax
0x1407381f7  jz      short loc_140738208
0x1407381f9  mov     edx, eax
0x1407381fb  mov     rcx, rbx
0x1407381fe  call    SdbGetStringTagPtr
0x140738203  mov     [rsp+78h+var_48], rax
0x140738208  mov     r8d, 4051h
0x14073820e  mov     edx, edi
0x140738210  mov     rcx, rbx
0x140738213  call    SdbFindFirstTag
0x140738218  test    eax, eax
0x14073821a  jz      loc_1407382F2
0x140738220  xor     r8d, r8d
0x140738223  mov     edx, eax
0x140738225  mov     rcx, rbx
0x140738228  call    SdbReadDWORDTag
0x14073822d  mov     r14d, eax
0x140738230  test    eax, eax
0x140738232  jnz     short loc_140738246
0x140738234  lea     r9, aFailedToReadVa; "Failed to read value type"
0x14073823b  mov     r8d, 431h
0x140738241  jmp     loc_14073842D
0x140738246  sub     eax, 1
0x140738249  jz      loc_1407383D8
0x14073824f  sub     eax, 1
0x140738252  jz      loc_1407383D8
0x140738258  sub     eax, 1
0x14073825b  jz      loc_140738360
0x140738261  sub     eax, 1
0x140738264  jz      short loc_1407382BB
0x140738266  sub     eax, 3
0x140738269  jz      loc_1407383D8
0x14073826f  cmp     eax, 4
0x140738272  jz      short loc_140738286
0x140738274  lea     r9, aUnknownRegistr_0; "Unknown registry value type"
0x14073827b  mov     r8d, 472h
0x140738281  jmp     loc_14073842D
0x140738286  mov     r8d, 501Bh
0x14073828c  mov     edx, edi
0x14073828e  mov     rcx, rbx
0x140738291  call    SdbFindFirstTag
0x140738296  test    eax, eax
0x140738298  jnz     short loc_1407382AC
0x14073829a  lea     r9, aFailedToGetTag_0; "Failed to get TAG_REG_VALUE_DATA_QWORD"
0x1407382a1  mov     r8d, 456h
0x1407382a7  jmp     loc_14073842D
0x1407382ac  xor     r8d, r8d
0x1407382af  mov     edx, eax
0x1407382b1  mov     rcx, rbx
0x1407382b4  call    SdbReadQWORDTag
0x1407382b9  jmp     short loc_1407382F5
0x1407382bb  mov     r8d, 4052h
0x1407382c1  mov     edx, edi
0x1407382c3  mov     rcx, rbx
0x1407382c6  call    SdbFindFirstTag
0x1407382cb  test    eax, eax
0x1407382cd  jnz     short loc_1407382E1
0x1407382cf  lea     r9, aFailedToGetTag_1; "Failed to get TAG_REG_VALUE_DATA_DWORD"
0x1407382d6  mov     r8d, 44Ch
0x1407382dc  jmp     loc_14073842D
0x1407382e1  xor     r8d, r8d
0x1407382e4  mov     edx, eax
0x1407382e6  mov     rcx, rbx
0x1407382e9  call    SdbReadDWORDTag
0x1407382ee  mov     [rsp+78h+var_58], eax
0x1407382f2  mov     rax, rbp
0x1407382f5  mov     rcx, [rsp+78h+arg_10]
0x1407382fd  mov     r13d, 1
0x140738303  mov     rdx, [rsp+78h+arg_18]
0x14073830b  mov     [rcx], rsi
0x14073830e  mov     rcx, [rsp+78h+var_48]
0x140738313  mov     [rdx], rcx
0x140738316  mov     rcx, [rsp+78h+arg_20]
0x14073831e  mov     rdx, [rsp+78h+arg_30]
0x140738326  mov     [rcx], r14d
0x140738329  mov     rcx, [rsp+78h+arg_28]
0x140738331  mov     [rcx], r12
0x140738334  mov     ecx, [rsp+78h+var_58]
0x140738338  mov     [rdx], ecx
0x14073833a  mov     rcx, [rsp+78h+arg_38]
0x140738342  mov     [rcx], rax
0x140738345  mov     rax, [rsp+78h+arg_40]
0x14073834d  mov     [rax], r15
0x140738350  mov     rax, [rsp+78h+arg_48]
0x140738358  mov     [rax], rbp
0x14073835b  jmp     loc_14073843E
0x140738360  mov     r8d, 9012h
0x140738366  mov     edx, edi
0x140738368  mov     rcx, rbx
0x14073836b  call    SdbFindFirstTag
0x140738370  mov     edi, eax
0x140738372  test    eax, eax
0x140738374  jnz     short loc_140738388
0x140738376  lea     r9, aFailedToGetTag; "Failed to get TAG_REG_VALUE_DATA_BINARY"
0x14073837d  mov     r8d, 460h
0x140738383  jmp     loc_14073842D
0x140738388  mov     edx, edi
0x14073838a  mov     rcx, rbx
0x14073838d  call    SdbGetBinaryTagData
0x140738392  mov     r15, rax
0x140738395  test    rax, rax
0x140738398  jnz     short loc_1407383AC
0x14073839a  lea     r9, aFailedToReadVa_2; "Failed to read value data"
0x1407383a1  mov     r8d, 466h
0x1407383a7  jmp     loc_14073842D
0x1407383ac  mov     edx, edi
0x1407383ae  mov     rcx, rbx
0x1407383b1  call    SdbGetTagDataSize
0x1407383b6  mov     ebp, eax
0x1407383b8  cmp     rbp, 20000000h
0x1407383bf  jnz     short loc_1407383D0
0x1407383c1  lea     r9, aFailedToReadVa_1; "Failed to read value data size"
0x1407383c8  mov     r8d, 46Ch
0x1407383ce  jmp     short loc_14073842D
0x1407383d0  mov     rax, r12
0x1407383d3  jmp     loc_1407382F5
0x1407383d8  mov     r8d, 6031h
0x1407383de  mov     edx, edi
0x1407383e0  mov     rcx, rbx
0x1407383e3  call    SdbFindFirstTag
0x1407383e8  test    eax, eax
0x1407383ea  jnz     short loc_1407383FB
0x1407383ec  lea     r9, aFailedToGetTag_2; "Failed to get TAG_REG_VALUE_DATA_SZ"
0x1407383f3  mov     r8d, 43Eh
0x1407383f9  jmp     short loc_14073842D
0x1407383fb  mov     edx, eax
0x1407383fd  mov     rcx, rbx
0x140738400  call    SdbGetStringTagPtr
0x140738405  mov     r12, rax
0x140738408  test    rax, rax
0x14073840b  jnz     loc_1407382F2
0x140738411  lea     r9, aFailedToReadVa_2; "Failed to read value data"
0x140738418  mov     r8d, 444h
0x14073841e  jmp     short loc_14073842D
0x140738420  lea     r9, aFailedToReadKe; "Failed to read key path"
0x140738427  mov     r8d, 41Eh
0x14073842d  lea     rdx, aSdbpgetregistr; "SdbpGetRegistryMatchingAttributes"
0x140738434  mov     ecx, 1
0x140738439  call    AslLogCallPrintf
0x14073843e  mov     rbx, [rsp+78h+arg_0]
0x140738446  mov     eax, r13d
0x140738449  add     rsp, 40h
0x14073844d  pop     r15
0x14073844f  pop     r14
0x140738451  pop     r13
0x140738453  pop     r12
0x140738455  pop     rdi
0x140738456  pop     rsi
0x140738457  pop     rbp
0x140738458  retn
```
