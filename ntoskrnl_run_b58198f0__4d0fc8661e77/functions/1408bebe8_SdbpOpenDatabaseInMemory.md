# SdbpOpenDatabaseInMemory

- ea: `0x1408bebe8`
- end: `0x1408bed3d`
- name: `SdbpOpenDatabaseInMemory`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140826d28`
- `0x1408c0be4`

## callees

- `0x14049d9e0`
- `0x1406dc8c0`
- `0x1408be654`
- `0x1408bebe8`
- `0x1408bf658`
- `0x1408c132c`
- `0x1408c14bc`
- `0x1408c2d0c`
- `0x1408c2f88`

## string_xrefs

- `0x1408becba`: `SdbpOpenDatabaseInMemory`
- `0x1408bece1`: `SdbpOpenDatabaseInMemory`
- `0x1408bed01`: `SdbpOpenDatabaseInMemory`
- `0x1408becad`: `Can't read database header`
- `0x1408becf4`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  const char *v11; // r9
  int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+38h] [rbp-40h]

  v13 = 0;
  v14 = 0;
  v6 = AslAlloc(a1, 2688);
  v7 = v6;
  if ( !v6 )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2765, (unsigned int)"Failed to allocate DB structure");
    return 0;
  }
  *(_DWORD *)(v6 + 20) = a2;
  *(_DWORD *)(v6 + 16) = 0;
  *(_DWORD *)(v6 + 24) |= 1u;
  *(_QWORD *)(v6 + 8) = a1;
  *(_QWORD *)v6 = 0;
  if ( (unsigned int)SdbpReadMappedData(v6, 0, &v13, 0xCu) )
  {
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
    {
      v9 = v14;
      if ( v14 != 1717724275 && (a3 & 2) == 0 )
      {
        v11 = "Magic does not match a valid value: [0x%lx]";
        v12 = 2782;
LABEL_13:
        AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", v12, (_DWORD)v11, v9);
        goto LABEL_9;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v13, a3) )
    {
      if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        return v7;
      v9 = SdbpValidateRootTagSizes(v7);
      if ( v9 >= 0 )
        return v7;
      v11 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v12 = 2794;
      goto LABEL_13;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2776, (unsigned int)"Can't read database header");
  }
LABEL_9:
  AslFree(v8, v7);
  return 0;
}

```

## disassembly

```asm
0x1408bebe8  push    rbx
0x1408bebea  push    rbp
0x1408bebeb  push    rsi
0x1408bebec  push    rdi
0x1408bebed  sub     rsp, 58h
0x1408bebf1  mov     rax, cs:__security_cookie
0x1408bebf8  xor     rax, rsp
0x1408bebfb  mov     [rsp+78h+var_38], rax
0x1408bec00  xor     eax, eax
0x1408bec02  mov     edi, edx
0x1408bec04  mov     edx, 0A80h
0x1408bec09  mov     [rsp+78h+var_48], rax
0x1408bec0e  mov     [rsp+78h+var_40], eax
0x1408bec12  mov     esi, r8d
0x1408bec15  mov     rbp, rcx
0x1408bec18  call    AslAlloc
0x1408bec1d  mov     rbx, rax
0x1408bec20  test    rax, rax
0x1408bec23  jz      loc_1408BECD4
0x1408bec29  mov     [rax+14h], edi
0x1408bec2c  lea     r8, [rsp+78h+var_48]
0x1408bec31  mov     edi, 1
0x1408bec36  mov     dword ptr [rax+10h], 0
0x1408bec3d  or      [rax+18h], edi
0x1408bec40  xor     edx, edx
0x1408bec42  mov     rcx, rax
0x1408bec45  mov     [rax+8], rbp
0x1408bec49  mov     qword ptr [rax], 0
0x1408bec50  lea     r9d, [rdi+0Bh]
0x1408bec54  call    SdbpReadMappedData
0x1408bec59  test    eax, eax
0x1408bec5b  jz      short loc_1408BECAD
0x1408bec5d  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1408bec62  test    eax, eax
0x1408bec64  jnz     loc_1408BED15
0x1408bec6a  mov     r8d, esi
0x1408bec6d  lea     rdx, [rsp+78h+var_48]
0x1408bec72  mov     rcx, rbx
0x1408bec75  call    SdbpValidateAndApplyCompatFlags
0x1408bec7a  test    eax, eax
0x1408bec7c  jz      short loc_1408BECC8
0x1408bec7e  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1408bec83  test    eax, eax
0x1408bec85  jz      short loc_1408BEC93
0x1408bec87  mov     rcx, rbx
0x1408bec8a  call    SdbpValidateRootTagSizes
0x1408bec8f  test    eax, eax
0x1408bec91  js      short loc_1408BECF4
0x1408bec93  mov     rax, rbx
0x1408bec96  mov     rcx, [rsp+78h+var_38]
0x1408bec9b  xor     rcx, rsp; StackCookie
0x1408bec9e  call    __security_check_cookie
0x1408beca3  add     rsp, 58h
0x1408beca7  pop     rdi
0x1408beca8  pop     rsi
0x1408beca9  pop     rbp
0x1408becaa  pop     rbx
0x1408becab  retn
0x1408becad  lea     r9, aCanTReadDataba; "Can't read database header"
0x1408becb4  mov     r8d, 0AD8h
0x1408becba  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1408becc1  mov     ecx, edi
0x1408becc3  call    AslLogCallPrintf
0x1408becc8  mov     rdx, rbx
0x1408beccb  call    AslFree
0x1408becd0  xor     eax, eax
0x1408becd2  jmp     short loc_1408BEC96
0x1408becd4  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x1408becdb  mov     r8d, 0ACDh
0x1408bece1  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1408bece8  mov     ecx, 1
0x1408beced  call    AslLogCallPrintf
0x1408becf2  jmp     short loc_1408BECD0
0x1408becf4  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x1408becfb  mov     r8d, 0AEAh
0x1408bed01  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1408bed08  mov     [rsp+78h+var_58], eax
0x1408bed0c  mov     ecx, edi
0x1408bed0e  call    AslLogCallPrintf
0x1408bed13  jmp     short loc_1408BECC8
0x1408bed15  mov     eax, [rsp+78h+var_40]
0x1408bed19  cmp     eax, 66626473h
0x1408bed1e  jz      loc_1408BEC6A
0x1408bed24  test    sil, 2
0x1408bed28  jnz     loc_1408BEC6A
0x1408bed2e  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x1408bed35  mov     r8d, 0ADEh
0x1408bed3b  jmp     short loc_1408BED01
```
