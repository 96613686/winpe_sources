# SdbpGetRegistryMatchingAttributes

- ea: `0x14073394c`
- end: `0x140733c9a`
- name: `SdbpGetRegistryMatchingAttributes`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1408218f0`
- `0x140822170`

## callees

- `0x1404058e0`
- `0x14073394c`
- `0x140733ca0`
- `0x1408238f4`
- `0x1408239d4`
- `0x14097c750`
- `0x14097cb0c`
- `0x14097ce34`
- `0x14097d158`
- `0x14097d324`

## string_xrefs

- `0x140733c01`: `Failed to read value data size`
- `0x140733bda`: `Failed to read value data`
- `0x140733c51`: `Failed to read value data`
- `0x140733a74`: `Failed to read value type`
- `0x140733c60`: `Failed to read key path`
- `0x140733c6d`: `SdbpGetRegistryMatchingAttributes`
- `0x1407339c9`: `Failed to get key path tag`
- `0x140733ab4`: `Unknown registry value type`

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
  __int16 UShortFromUser; // ax
  int v18; // r14d
  __int64 v19; // r12
  __int64 BinaryTagData; // r15
  unsigned int v21; // eax
  unsigned int v22; // eax
  int DWORDTag; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  __int64 QWORDTag; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // edi
  unsigned int v34; // eax
  int v36; // [rsp+20h] [rbp-58h]
  __int64 v37; // [rsp+30h] [rbp-48h]

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
        : (UShortFromUser = RtlReadUShortFromUser(v16)),
          !UShortFromUser) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetRegistryMatchingAttributes",
        1054,
        (unsigned int)"Failed to read key path");
      return v13;
    }
    v37 = 0;
    v36 = 0;
    v18 = 0;
    v19 = 0;
    BinaryTagData = 0;
    v21 = SdbFindFirstTag(a1, v11, 24624);
    if ( v21 )
      v37 = SdbGetStringTagPtr(a1, v21);
    v22 = SdbFindFirstTag(a1, v11, 16465);
    if ( v22 )
    {
      DWORDTag = SdbReadDWORDTag(a1, v22, 0);
      v18 = DWORDTag;
      if ( !DWORDTag )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetRegistryMatchingAttributes",
          1073,
          (unsigned int)"Failed to read value type");
        return v13;
      }
      v24 = DWORDTag - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( !v26 )
          {
            v32 = SdbFindFirstTag(a1, v11, 36882);
            v33 = v32;
            if ( !v32 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1120,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_BINARY");
              return v13;
            }
            BinaryTagData = SdbGetBinaryTagData(a1, v32);
            if ( !BinaryTagData )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1126,
                (unsigned int)"Failed to read value data");
              return v13;
            }
            TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v33);
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
          v27 = v26 - 1;
          if ( !v27 )
          {
            v31 = SdbFindFirstTag(a1, v11, 16466);
            if ( !v31 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1100,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_DWORD");
              return v13;
            }
            v36 = SdbReadDWORDTag(a1, v31, 0);
            goto LABEL_26;
          }
          v28 = v27 - 3;
          if ( v28 )
          {
            if ( v28 != 4 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1138,
                (unsigned int)"Unknown registry value type");
              return v13;
            }
            v29 = SdbFindFirstTag(a1, v11, 20507);
            if ( !v29 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetRegistryMatchingAttributes",
                1110,
                (unsigned int)"Failed to get TAG_REG_VALUE_DATA_QWORD");
              return v13;
            }
            QWORDTag = SdbReadQWORDTag(a1, v29, 0);
LABEL_27:
            v13 = 1;
            *a3 = v16;
            *a4 = v37;
            *a5 = v18;
            *a6 = v19;
            *a7 = v36;
            *a8 = QWORDTag;
            *a9 = BinaryTagData;
            *a10 = TagDataSize;
            return v13;
          }
        }
      }
      v34 = SdbFindFirstTag(a1, v11, 24625);
      if ( !v34 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetRegistryMatchingAttributes",
          1086,
          (unsigned int)"Failed to get TAG_REG_VALUE_DATA_SZ");
        return v13;
      }
      v19 = SdbGetStringTagPtr(a1, v34);
      if ( !v19 )
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
0x14073394c  mov     [rsp+arg_0], rbx
0x140733951  mov     [rsp+arg_18], r9
0x140733956  mov     [rsp+arg_10], r8
0x14073395b  push    rbp
0x14073395c  push    rsi
0x14073395d  push    rdi
0x14073395e  push    r12
0x140733960  push    r13
0x140733962  push    r14
0x140733964  push    r15
0x140733966  sub     rsp, 40h
0x14073396a  mov     rax, [rsp+78h+arg_20]
0x140733972  xor     ebp, ebp
0x140733974  mov     [r8], rbp
0x140733977  mov     edi, edx
0x140733979  mov     r8d, 6001h
0x14073397f  mov     [r9], rbp
0x140733982  mov     rbx, rcx
0x140733985  mov     r13d, ebp
0x140733988  mov     [rax], ebp
0x14073398a  mov     rax, [rsp+78h+arg_28]
0x140733992  mov     [rax], rbp
0x140733995  mov     rax, [rsp+78h+arg_30]
0x14073399d  mov     [rax], ebp
0x14073399f  mov     rax, [rsp+78h+arg_38]
0x1407339a7  mov     [rax], rbp
0x1407339aa  mov     rax, [rsp+78h+arg_40]
0x1407339b2  mov     [rax], rbp
0x1407339b5  mov     rax, [rsp+78h+arg_48]
0x1407339bd  mov     [rax], rbp
0x1407339c0  call    SdbFindFirstTag
0x1407339c5  test    eax, eax
0x1407339c7  jnz     short loc_1407339DB
0x1407339c9  lea     r9, aFailedToGetKey; "Failed to get key path tag"
0x1407339d0  mov     r8d, 412h
0x1407339d6  jmp     loc_140733C6D
0x1407339db  mov     edx, eax
0x1407339dd  mov     rcx, rbx
0x1407339e0  call    SdbGetStringTagPtr
0x1407339e5  mov     rsi, rax
0x1407339e8  test    rax, rax
0x1407339eb  jz      loc_140733C60
0x1407339f1  mov     rcx, rax
0x1407339f4  call    MmIsUserAddress
0x1407339f9  test    al, al
0x1407339fb  jz      short loc_140733A07
0x1407339fd  mov     rcx, rsi
0x140733a00  call    RtlReadUShortFromUser
0x140733a05  jmp     short loc_140733A0A
0x140733a07  movzx   eax, word ptr [rsi]
0x140733a0a  test    ax, ax
0x140733a0d  jz      loc_140733C60
0x140733a13  mov     r8d, 6030h
0x140733a19  mov     [rsp+78h+var_48], rbp
0x140733a1e  mov     edx, edi
0x140733a20  mov     [rsp+78h+var_58], ebp
0x140733a24  mov     rcx, rbx
0x140733a27  mov     r14d, ebp
0x140733a2a  mov     r12, rbp
0x140733a2d  mov     r15, rbp
0x140733a30  call    SdbFindFirstTag
0x140733a35  test    eax, eax
0x140733a37  jz      short loc_140733A48
0x140733a39  mov     edx, eax
0x140733a3b  mov     rcx, rbx
0x140733a3e  call    SdbGetStringTagPtr
0x140733a43  mov     [rsp+78h+var_48], rax
0x140733a48  mov     r8d, 4051h
0x140733a4e  mov     edx, edi
0x140733a50  mov     rcx, rbx
0x140733a53  call    SdbFindFirstTag
0x140733a58  test    eax, eax
0x140733a5a  jz      loc_140733B32
0x140733a60  xor     r8d, r8d
0x140733a63  mov     edx, eax
0x140733a65  mov     rcx, rbx
0x140733a68  call    SdbReadDWORDTag
0x140733a6d  mov     r14d, eax
0x140733a70  test    eax, eax
0x140733a72  jnz     short loc_140733A86
0x140733a74  lea     r9, aFailedToReadVa; "Failed to read value type"
0x140733a7b  mov     r8d, 431h
0x140733a81  jmp     loc_140733C6D
0x140733a86  sub     eax, 1
0x140733a89  jz      loc_140733C18
0x140733a8f  sub     eax, 1
0x140733a92  jz      loc_140733C18
0x140733a98  sub     eax, 1
0x140733a9b  jz      loc_140733BA0
0x140733aa1  sub     eax, 1
0x140733aa4  jz      short loc_140733AFB
0x140733aa6  sub     eax, 3
0x140733aa9  jz      loc_140733C18
0x140733aaf  cmp     eax, 4
0x140733ab2  jz      short loc_140733AC6
0x140733ab4  lea     r9, aUnknownRegistr_0; "Unknown registry value type"
0x140733abb  mov     r8d, 472h
0x140733ac1  jmp     loc_140733C6D
0x140733ac6  mov     r8d, 501Bh
0x140733acc  mov     edx, edi
0x140733ace  mov     rcx, rbx
0x140733ad1  call    SdbFindFirstTag
0x140733ad6  test    eax, eax
0x140733ad8  jnz     short loc_140733AEC
0x140733ada  lea     r9, aFailedToGetTag_0; "Failed to get TAG_REG_VALUE_DATA_QWORD"
0x140733ae1  mov     r8d, 456h
0x140733ae7  jmp     loc_140733C6D
0x140733aec  xor     r8d, r8d
0x140733aef  mov     edx, eax
0x140733af1  mov     rcx, rbx
0x140733af4  call    SdbReadQWORDTag
0x140733af9  jmp     short loc_140733B35
0x140733afb  mov     r8d, 4052h
0x140733b01  mov     edx, edi
0x140733b03  mov     rcx, rbx
0x140733b06  call    SdbFindFirstTag
0x140733b0b  test    eax, eax
0x140733b0d  jnz     short loc_140733B21
0x140733b0f  lea     r9, aFailedToGetTag_1; "Failed to get TAG_REG_VALUE_DATA_DWORD"
0x140733b16  mov     r8d, 44Ch
0x140733b1c  jmp     loc_140733C6D
0x140733b21  xor     r8d, r8d
0x140733b24  mov     edx, eax
0x140733b26  mov     rcx, rbx
0x140733b29  call    SdbReadDWORDTag
0x140733b2e  mov     [rsp+78h+var_58], eax
0x140733b32  mov     rax, rbp
0x140733b35  mov     rcx, [rsp+78h+arg_10]
0x140733b3d  mov     r13d, 1
0x140733b43  mov     rdx, [rsp+78h+arg_18]
0x140733b4b  mov     [rcx], rsi
0x140733b4e  mov     rcx, [rsp+78h+var_48]
0x140733b53  mov     [rdx], rcx
0x140733b56  mov     rcx, [rsp+78h+arg_20]
0x140733b5e  mov     rdx, [rsp+78h+arg_30]
0x140733b66  mov     [rcx], r14d
0x140733b69  mov     rcx, [rsp+78h+arg_28]
0x140733b71  mov     [rcx], r12
0x140733b74  mov     ecx, [rsp+78h+var_58]
0x140733b78  mov     [rdx], ecx
0x140733b7a  mov     rcx, [rsp+78h+arg_38]
0x140733b82  mov     [rcx], rax
0x140733b85  mov     rax, [rsp+78h+arg_40]
0x140733b8d  mov     [rax], r15
0x140733b90  mov     rax, [rsp+78h+arg_48]
0x140733b98  mov     [rax], rbp
0x140733b9b  jmp     loc_140733C7E
0x140733ba0  mov     r8d, 9012h
0x140733ba6  mov     edx, edi
0x140733ba8  mov     rcx, rbx
0x140733bab  call    SdbFindFirstTag
0x140733bb0  mov     edi, eax
0x140733bb2  test    eax, eax
0x140733bb4  jnz     short loc_140733BC8
0x140733bb6  lea     r9, aFailedToGetTag; "Failed to get TAG_REG_VALUE_DATA_BINARY"
0x140733bbd  mov     r8d, 460h
0x140733bc3  jmp     loc_140733C6D
0x140733bc8  mov     edx, edi
0x140733bca  mov     rcx, rbx
0x140733bcd  call    SdbGetBinaryTagData
0x140733bd2  mov     r15, rax
0x140733bd5  test    rax, rax
0x140733bd8  jnz     short loc_140733BEC
0x140733bda  lea     r9, aFailedToReadVa_2; "Failed to read value data"
0x140733be1  mov     r8d, 466h
0x140733be7  jmp     loc_140733C6D
0x140733bec  mov     edx, edi
0x140733bee  mov     rcx, rbx
0x140733bf1  call    SdbGetTagDataSize
0x140733bf6  mov     ebp, eax
0x140733bf8  cmp     rbp, 20000000h
0x140733bff  jnz     short loc_140733C10
0x140733c01  lea     r9, aFailedToReadVa_1; "Failed to read value data size"
0x140733c08  mov     r8d, 46Ch
0x140733c0e  jmp     short loc_140733C6D
0x140733c10  mov     rax, r12
0x140733c13  jmp     loc_140733B35
0x140733c18  mov     r8d, 6031h
0x140733c1e  mov     edx, edi
0x140733c20  mov     rcx, rbx
0x140733c23  call    SdbFindFirstTag
0x140733c28  test    eax, eax
0x140733c2a  jnz     short loc_140733C3B
0x140733c2c  lea     r9, aFailedToGetTag_2; "Failed to get TAG_REG_VALUE_DATA_SZ"
0x140733c33  mov     r8d, 43Eh
0x140733c39  jmp     short loc_140733C6D
0x140733c3b  mov     edx, eax
0x140733c3d  mov     rcx, rbx
0x140733c40  call    SdbGetStringTagPtr
0x140733c45  mov     r12, rax
0x140733c48  test    rax, rax
0x140733c4b  jnz     loc_140733B32
0x140733c51  lea     r9, aFailedToReadVa_2; "Failed to read value data"
0x140733c58  mov     r8d, 444h
0x140733c5e  jmp     short loc_140733C6D
0x140733c60  lea     r9, aFailedToReadKe; "Failed to read key path"
0x140733c67  mov     r8d, 41Eh
0x140733c6d  lea     rdx, aSdbpgetregistr; "SdbpGetRegistryMatchingAttributes"
0x140733c74  mov     ecx, 1
0x140733c79  call    AslLogCallPrintf
0x140733c7e  mov     rbx, [rsp+78h+arg_0]
0x140733c86  mov     eax, r13d
0x140733c89  add     rsp, 40h
0x140733c8d  pop     r15
0x140733c8f  pop     r14
0x140733c91  pop     r13
0x140733c93  pop     r12
0x140733c95  pop     rdi
0x140733c96  pop     rsi
0x140733c97  pop     rbp
0x140733c98  retn
```
