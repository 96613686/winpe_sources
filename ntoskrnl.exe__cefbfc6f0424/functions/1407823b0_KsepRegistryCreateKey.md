# KsepRegistryCreateKey

- ea: `0x1407823b0`
- end: `0x14078260d`
- name: `KsepRegistryCreateKey`
- size: `605`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14077ff70`

## callees

- `0x1406191e0`
- `0x1406dd5c0`
- `0x1406dd780`
- `0x1407823b0`
- `0x1408bff4c`
- `0x1408c0758`

## string_xrefs

- `0x140782446`: `EnginePath != NULL`
- `0x14078243f`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14078248e`: `minkernel\ntos\kshim\kseregistry.c`
- `0x1407824dd`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryCreateKey(__int64 a1, __int64 a2, HANDLE *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  NTSTATUS v9; // ebx
  _QWORD v11[2]; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp+7h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  HANDLE KeyHandle; // [rsp+B0h] [rbp+67h] BYREF
  HANDLE v15; // [rsp+B8h] [rbp+6Fh] BYREF

  v11[0] = 0;
  v11[1] = 0;
  v12[0] = 0;
  v12[1] = 0;
  KeyHandle = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
  {
    v6 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v6 + 1] = -1073740768;
    KsepHistoryErrors[2 * v6] = 262645;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("EnginePath != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F5u, 0);
  }
  if ( !a2 )
  {
    v7 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v7 + 1] = -1073740768;
    KsepHistoryErrors[2 * v7] = 262646;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("SearchKey != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F6u, 0);
  }
  if ( !a3 )
  {
    v8 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v8 + 1] = -1073740768;
    KsepHistoryErrors[2 * v8] = 262647;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("Handle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F7u, 0);
  }
  KsepStringDuplicate(v11, a1);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v9 >= 0 )
  {
    v9 = KsepStringDuplicate(v12, a2);
    if ( v9 >= 0 )
    {
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwCreateKey(&v15, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
      if ( v9 >= 0 )
      {
        *a3 = v15;
        _InterlockedIncrement(&dword_140EFE078);
      }
    }
  }
  KsepStringFree(v11);
  KsepStringFree(v12);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1407823b0  mov     [rsp-8+arg_10], rbx
0x1407823b5  mov     [rsp-8+arg_18], rsi
0x1407823ba  push    rbp
0x1407823bb  push    rdi
0x1407823bc  push    r12
0x1407823be  lea     rbp, [rsp-47h]
0x1407823c3  sub     rsp, 90h
0x1407823ca  xor     eax, eax
0x1407823cc  lea     r12, KsepHistoryErrors
0x1407823d3  mov     [rbp+57h+var_60], rax
0x1407823d7  xorps   xmm0, xmm0
0x1407823da  mov     [rbp+57h+var_58], rax
0x1407823de  mov     rsi, rdx
0x1407823e1  mov     [rbp+57h+var_50], rax
0x1407823e5  mov     rdi, r8
0x1407823e8  mov     [rbp+57h+var_48], rax
0x1407823ec  lea     edx, [rax+4]
0x1407823ef  mov     [rbp+57h+KeyHandle], rax
0x1407823f3  mov     rbx, rcx
0x1407823f6  mov     [rbp+57h+arg_8], rax
0x1407823fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1407823fe  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140782402  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140782406  test    rcx, rcx
0x140782409  jnz     short loc_140782455
0x14078240b  lea     eax, [rcx+1]
0x14078240e  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782416  inc     eax
0x140782418  mov     r8d, 1F5h; LineNumber
0x14078241e  and     eax, 3Fh
0x140782421  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x14078242a  mov     dword ptr [r12+rax*8], 401F5h
0x140782432  mov     eax, cs:KsepDebugFlag
0x140782438  test    dl, al
0x14078243a  jz      short loc_140782455
0x14078243c  xor     r9d, r9d; MutableMessage
0x14078243f  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782446  lea     rcx, aEnginepathNull; "EnginePath != NULL"
0x14078244d  call    RtlAssert
0x140782452  lea     edx, [rbx+4]
0x140782455  test    rsi, rsi
0x140782458  jnz     short loc_1407824A1
0x14078245a  lea     eax, [rsi+1]
0x14078245d  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782465  inc     eax
0x140782467  mov     r8d, 1F6h; LineNumber
0x14078246d  and     eax, 3Fh
0x140782470  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x140782479  mov     dword ptr [r12+rax*8], 401F6h
0x140782481  mov     eax, cs:KsepDebugFlag
0x140782487  test    dl, al
0x140782489  jz      short loc_1407824A1
0x14078248b  xor     r9d, r9d; MutableMessage
0x14078248e  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782495  lea     rcx, aSearchkeyNull; "SearchKey != NULL"
0x14078249c  call    RtlAssert
0x1407824a1  test    rdi, rdi
0x1407824a4  jnz     short loc_1407824F0
0x1407824a6  lea     eax, [rdi+1]
0x1407824a9  lock xadd cs:KsepHistoryErrorsIndex, eax
0x1407824b1  inc     eax
0x1407824b3  lea     edx, [rdi+4]
0x1407824b6  and     eax, 3Fh
0x1407824b9  mov     r8d, 1F7h; LineNumber
0x1407824bf  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x1407824c8  mov     dword ptr [r12+rax*8], 401F7h
0x1407824d0  mov     eax, cs:KsepDebugFlag
0x1407824d6  test    dl, al
0x1407824d8  jz      short loc_1407824F0
0x1407824da  xor     r9d, r9d; MutableMessage
0x1407824dd  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x1407824e4  lea     rcx, aHandleNull; "Handle != NULL"
0x1407824eb  call    RtlAssert
0x1407824f0  mov     rdx, rbx
0x1407824f3  lea     rcx, [rbp+57h+var_60]
0x1407824f7  call    KsepStringDuplicate
0x1407824fc  lea     rax, [rbp+57h+var_60]
0x140782500  mov     [rsp+0A0h+Disposition], 0; Disposition
0x140782509  xorps   xmm0, xmm0
0x14078250c  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x140782514  mov     r12d, 30h ; '0'
0x14078251a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14078251e  xor     r9d, r9d; TitleIndex
0x140782521  mov     [rbp+57h+ObjectAttributes.Length], r12d
0x140782525  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140782529  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140782531  mov     edx, 2001Fh; DesiredAccess
0x140782536  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14078253d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140782541  mov     [rsp+0A0h+Class], 0; Class
0x14078254a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14078254f  call    ZwCreateKey
0x140782554  mov     ebx, eax
0x140782556  test    eax, eax
0x140782558  js      short loc_1407825D2
0x14078255a  mov     rdx, rsi
0x14078255d  lea     rcx, [rbp+57h+var_50]
0x140782561  call    KsepStringDuplicate
0x140782566  mov     ebx, eax
0x140782568  test    eax, eax
0x14078256a  js      short loc_1407825D2
0x14078256c  mov     rax, [rbp+57h+KeyHandle]
0x140782570  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140782574  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140782578  lea     rcx, [rbp+57h+arg_8]; KeyHandle
0x14078257c  lea     rax, [rbp+57h+var_50]
0x140782580  mov     [rsp+0A0h+Disposition], 0; Disposition
0x140782589  xorps   xmm0, xmm0
0x14078258c  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x140782594  xor     r9d, r9d; TitleIndex
0x140782597  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14078259b  mov     edx, 2001Fh; DesiredAccess
0x1407825a0  mov     [rbp+57h+ObjectAttributes.Length], r12d
0x1407825a4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1407825ab  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407825b0  mov     [rsp+0A0h+Class], 0; Class
0x1407825b9  call    ZwCreateKey
0x1407825be  mov     ebx, eax
0x1407825c0  test    eax, eax
0x1407825c2  js      short loc_1407825D2
0x1407825c4  mov     rax, [rbp+57h+arg_8]
0x1407825c8  mov     [rdi], rax
0x1407825cb  lock inc cs:dword_140EFE078
0x1407825d2  lea     rcx, [rbp+57h+var_60]
0x1407825d6  call    KsepStringFree
0x1407825db  lea     rcx, [rbp+57h+var_50]
0x1407825df  call    KsepStringFree
0x1407825e4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1407825e8  test    rcx, rcx
0x1407825eb  jz      short loc_1407825F2
0x1407825ed  call    ZwClose
0x1407825f2  lea     r11, [rsp+0A0h+var_10]
0x1407825fa  mov     eax, ebx
0x1407825fc  mov     rbx, [r11+30h]
0x140782600  mov     rsi, [r11+38h]
0x140782604  mov     rsp, r11
0x140782607  pop     r12
0x140782609  pop     rdi
0x14078260a  pop     rbp
0x14078260b  retn
```
