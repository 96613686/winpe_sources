# SdbpOpenDatabaseInMemory

- ea: `0x140978e20`
- end: `0x140978f75`
- name: `SdbpOpenDatabaseInMemory`
- size: `341`
- prototype: `__int64 __fastcall(__int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140824db8`
- `0x14097adb4`

## callees

- `0x14048e440`
- `0x1406d9d70`
- `0x14097888c`
- `0x140978e20`
- `0x140979890`
- `0x14097b4fc`
- `0x14097b68c`
- `0x14097cedc`
- `0x14097d158`

## string_xrefs

- `0x140978ef2`: `SdbpOpenDatabaseInMemory`
- `0x140978f19`: `SdbpOpenDatabaseInMemory`
- `0x140978f39`: `SdbpOpenDatabaseInMemory`
- `0x140978ee5`: `Can't read database header`
- `0x140978f2c`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+38h] [rbp-40h]

  v12 = 0;
  v13 = 0;
  v6 = AslAlloc(a1, 2688);
  v7 = v6;
  if ( !v6 )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2891, (unsigned int)"Failed to allocate DB structure");
    return 0;
  }
  *(_DWORD *)(v6 + 20) = a2;
  *(_DWORD *)(v6 + 16) = 0;
  *(_DWORD *)(v6 + 24) |= 1u;
  *(_QWORD *)(v6 + 8) = a1;
  *(_QWORD *)v6 = 0;
  if ( (unsigned int)SdbpReadMappedData(v6, 0, &v12, 12) )
  {
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && v13 != 1717724275
      && (a3 & 2) == 0 )
    {
      v10 = "Magic does not match a valid value: [0x%lx]";
      v11 = 2908;
LABEL_13:
      AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", v11, (_DWORD)v10);
      goto LABEL_9;
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v12, a3) )
    {
      if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        || (int)SdbpValidateRootTagSizes(v7) >= 0 )
      {
        return v7;
      }
      v10 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v11 = 2920;
      goto LABEL_13;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2902, (unsigned int)"Can't read database header");
  }
LABEL_9:
  AslFree(v8, v7);
  return 0;
}

```

## disassembly

```asm
0x140978e20  push    rbx
0x140978e22  push    rbp
0x140978e23  push    rsi
0x140978e24  push    rdi
0x140978e25  sub     rsp, 58h
0x140978e29  mov     rax, cs:__security_cookie
0x140978e30  xor     rax, rsp
0x140978e33  mov     [rsp+78h+var_38], rax
0x140978e38  xor     eax, eax
0x140978e3a  mov     edi, edx
0x140978e3c  mov     edx, 0A80h
0x140978e41  mov     [rsp+78h+var_48], rax
0x140978e46  mov     [rsp+78h+var_40], eax
0x140978e4a  mov     esi, r8d
0x140978e4d  mov     rbp, rcx
0x140978e50  call    AslAlloc
0x140978e55  mov     rbx, rax
0x140978e58  test    rax, rax
0x140978e5b  jz      loc_140978F0C
0x140978e61  mov     [rax+14h], edi
0x140978e64  lea     r8, [rsp+78h+var_48]
0x140978e69  mov     edi, 1
0x140978e6e  mov     dword ptr [rax+10h], 0
0x140978e75  or      [rax+18h], edi
0x140978e78  xor     edx, edx
0x140978e7a  mov     rcx, rax
0x140978e7d  mov     [rax+8], rbp
0x140978e81  mov     qword ptr [rax], 0
0x140978e88  lea     r9d, [rdi+0Bh]
0x140978e8c  call    SdbpReadMappedData
0x140978e91  test    eax, eax
0x140978e93  jz      short loc_140978EE5
0x140978e95  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140978e9a  test    eax, eax
0x140978e9c  jnz     loc_140978F4D
0x140978ea2  mov     r8d, esi
0x140978ea5  lea     rdx, [rsp+78h+var_48]
0x140978eaa  mov     rcx, rbx
0x140978ead  call    SdbpValidateAndApplyCompatFlags
0x140978eb2  test    eax, eax
0x140978eb4  jz      short loc_140978F00
0x140978eb6  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140978ebb  test    eax, eax
0x140978ebd  jz      short loc_140978ECB
0x140978ebf  mov     rcx, rbx
0x140978ec2  call    SdbpValidateRootTagSizes
0x140978ec7  test    eax, eax
0x140978ec9  js      short loc_140978F2C
0x140978ecb  mov     rax, rbx
0x140978ece  mov     rcx, [rsp+78h+var_38]
0x140978ed3  xor     rcx, rsp; StackCookie
0x140978ed6  call    __security_check_cookie
0x140978edb  add     rsp, 58h
0x140978edf  pop     rdi
0x140978ee0  pop     rsi
0x140978ee1  pop     rbp
0x140978ee2  pop     rbx
0x140978ee3  retn
0x140978ee5  lea     r9, aCanTReadDataba; "Can't read database header"
0x140978eec  mov     r8d, 0B56h
0x140978ef2  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x140978ef9  mov     ecx, edi
0x140978efb  call    AslLogCallPrintf
0x140978f00  mov     rdx, rbx
0x140978f03  call    AslFree
0x140978f08  xor     eax, eax
0x140978f0a  jmp     short loc_140978ECE
0x140978f0c  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x140978f13  mov     r8d, 0B4Bh
0x140978f19  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x140978f20  mov     ecx, 1
0x140978f25  call    AslLogCallPrintf
0x140978f2a  jmp     short loc_140978F08
0x140978f2c  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x140978f33  mov     r8d, 0B68h
0x140978f39  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x140978f40  mov     [rsp+78h+var_58], eax
0x140978f44  mov     ecx, edi
0x140978f46  call    AslLogCallPrintf
0x140978f4b  jmp     short loc_140978F00
0x140978f4d  mov     eax, [rsp+78h+var_40]
0x140978f51  cmp     eax, 66626473h
0x140978f56  jz      loc_140978EA2
0x140978f5c  test    sil, 2
0x140978f60  jnz     loc_140978EA2
0x140978f66  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x140978f6d  mov     r8d, 0B5Ch
0x140978f73  jmp     short loc_140978F39
```
