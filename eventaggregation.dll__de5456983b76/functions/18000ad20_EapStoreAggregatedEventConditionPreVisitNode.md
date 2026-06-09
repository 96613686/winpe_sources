# EapStoreAggregatedEventConditionPreVisitNode

- ea: `0x18000ad20`
- end: `0x18000aebe`
- name: `EapStoreAggregatedEventConditionPreVisitNode`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180002e30`
- `0x180003630`
- `0x1800072e0`
- `0x18000982c`
- `0x180009848`
- `0x18000ab18`
- `0x18000ad20`
- `0x18000afd0`
- `0x18000bde9`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000ad69`
- `RPCRT4!UuidCreate` at `0x18000ad69`

## pseudocode

```c
__int64 __fastcall EapStoreAggregatedEventConditionPreVisitNode(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rax
  HANDLE v5; // rsi
  void *v6; // rbx
  int v7; // ebx
  int v8; // eax
  int v9; // ecx
  ULONG v10; // eax
  int v11; // eax
  __int64 v12; // rax
  void *v13; // rax
  void *v14; // rbp
  HANDLE KeyHandle; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  v2 = *((unsigned __int16 *)a1 + 5);
  Uuid = 0;
  v5 = 0;
  KeyHandle = 0;
  v6 = *(void **)(*a1 + 24 * v2 - 24);
  if ( UuidCreate(&Uuid) )
  {
    v7 = -1073741595;
    goto LABEL_22;
  }
  v8 = EapCreateAggregatedEventNode(v6, &Uuid, &KeyHandle);
  v5 = KeyHandle;
  v7 = v8;
  if ( v8 < 0 )
    goto LABEL_22;
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != 1 )
    {
      v7 = -1073741811;
      goto LABEL_22;
    }
    v9 = *(_DWORD *)(a2 + 8);
    if ( v9 )
    {
      if ( v9 != 1 )
      {
        v7 = -1073741811;
        goto LABEL_15;
      }
      v10 = 6;
    }
    else
    {
      v10 = 8;
    }
    v11 = EapSetValue(KeyHandle, v10);
  }
  else
  {
    v11 = EapStoreSimpleEventParameters(KeyHandle, (GUID *)(a2 + 8));
  }
  v7 = v11;
LABEL_15:
  if ( v7 >= 0 )
  {
    v12 = *((unsigned __int16 *)a1 + 4);
    if ( *((_WORD *)a1 + 5) == (_WORD)v12 )
    {
      v13 = (void *)EaLibAllocate(24 * (v12 + 5));
      v14 = v13;
      if ( !v13 )
        goto LABEL_22;
      if ( *a1 )
      {
        memcpy_0(v13, (const void *)*a1, 24LL * *((unsigned __int16 *)a1 + 4));
        EaLibFree(*a1);
      }
      *((_WORD *)a1 + 4) += 5;
      *a1 = v14;
    }
    *(UUID *)(*a1 + 24LL * *((unsigned __int16 *)a1 + 5) - 16) = Uuid;
    *(_QWORD *)(*a1 + 24LL * *((unsigned __int16 *)a1 + 5)) = v5;
    v5 = 0;
    ++*((_WORD *)a1 + 5);
    v7 = 0;
  }
LABEL_22:
  EapCloseAggregatedEventNode(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ad20  mov     [rsp+arg_10], rbx
0x18000ad25  push    rbp
0x18000ad26  push    rsi
0x18000ad27  push    rdi
0x18000ad28  push    r14
0x18000ad2a  push    r15
0x18000ad2c  sub     rsp, 50h
0x18000ad30  mov     rax, cs:__security_cookie
0x18000ad37  xor     rax, rsp
0x18000ad3a  mov     [rsp+78h+var_30], rax
0x18000ad3f  movzx   eax, word ptr [rcx+0Ah]
0x18000ad43  mov     r14, rdx
0x18000ad46  xorps   xmm0, xmm0
0x18000ad49  mov     rdi, rcx
0x18000ad4c  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18000ad51  xor     esi, esi
0x18000ad53  lea     rdx, [rax+rax*2]
0x18000ad57  mov     [rsp+78h+KeyHandle], rsi
0x18000ad5c  mov     rax, [rcx]
0x18000ad5f  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18000ad64  mov     rbx, [rax+rdx*8-18h]
0x18000ad69  call    cs:__imp_UuidCreate
0x18000ad6f  test    eax, eax
0x18000ad71  jz      short loc_18000AD7D
0x18000ad73  mov     ebx, 0C00000E5h
0x18000ad78  jmp     loc_18000AE93
0x18000ad7d  lea     r8, [rsp+78h+KeyHandle]
0x18000ad82  mov     rcx, rbx
0x18000ad85  lea     rdx, [rsp+78h+Uuid]
0x18000ad8a  call    EapCreateAggregatedEventNode
0x18000ad8f  mov     rsi, [rsp+78h+KeyHandle]
0x18000ad94  mov     ebx, eax
0x18000ad96  test    eax, eax
0x18000ad98  js      loc_18000AE93
0x18000ad9e  mov     ecx, [r14]
0x18000ada1  mov     r15d, 1
0x18000ada7  test    ecx, ecx
0x18000ada9  jz      short loc_18000ADFB
0x18000adab  cmp     ecx, r15d
0x18000adae  jz      short loc_18000ADBA
0x18000adb0  mov     ebx, 0C000000Dh
0x18000adb5  jmp     loc_18000AE93
0x18000adba  mov     ecx, [r14+8]
0x18000adbe  test    ecx, ecx
0x18000adc0  jz      short loc_18000ADDC
0x18000adc2  cmp     ecx, r15d
0x18000adc5  jz      short loc_18000ADCE
0x18000adc7  mov     ebx, 0C000000Dh
0x18000adcc  jmp     short loc_18000AE09
0x18000adce  lea     r9, EA_STORE_PREDICATE_OR_STRING; "OR"
0x18000add5  mov     eax, 6
0x18000adda  jmp     short loc_18000ADE8
0x18000addc  lea     r9, EA_STORE_PREDICATE_AND_STRING; "AND"
0x18000ade3  mov     eax, 8
0x18000ade8  mov     r8d, r15d
0x18000adeb  mov     [rsp+78h+var_58], eax; ULONG
0x18000adef  xor     edx, edx
0x18000adf1  mov     rcx, rsi; KeyHandle
0x18000adf4  call    EapSetValue
0x18000adf9  jmp     short loc_18000AE07
0x18000adfb  lea     rdx, [r14+8]; Guid
0x18000adff  mov     rcx, rsi; KeyHandle
0x18000ae02  call    EapStoreSimpleEventParameters
0x18000ae07  mov     ebx, eax
0x18000ae09  test    ebx, ebx
0x18000ae0b  js      loc_18000AE93
0x18000ae11  movzx   eax, word ptr [rdi+8]
0x18000ae15  cmp     [rdi+0Ah], ax
0x18000ae19  jnz     short loc_18000AE65
0x18000ae1b  mov     r14d, 5
0x18000ae21  add     rax, r14
0x18000ae24  lea     rcx, [rax+rax*2]
0x18000ae28  shl     rcx, 3
0x18000ae2c  call    EaLibAllocate
0x18000ae31  mov     rbp, rax
0x18000ae34  test    rax, rax
0x18000ae37  jz      short loc_18000AE93
0x18000ae39  mov     rdx, [rdi]; Src
0x18000ae3c  test    rdx, rdx
0x18000ae3f  jz      short loc_18000AE5D
0x18000ae41  movzx   ecx, word ptr [rdi+8]
0x18000ae45  lea     r8, [rcx+rcx*2]
0x18000ae49  mov     rcx, rax; void *
0x18000ae4c  shl     r8, 3; Size
0x18000ae50  call    memcpy_0
0x18000ae55  mov     rcx, [rdi]
0x18000ae58  call    EaLibFree
0x18000ae5d  add     [rdi+8], r14w
0x18000ae62  mov     [rdi], rbp
0x18000ae65  movzx   eax, word ptr [rdi+0Ah]
0x18000ae69  movups  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x18000ae6e  lea     rcx, [rax+rax*2]
0x18000ae72  mov     rax, [rdi]
0x18000ae75  movdqu  xmmword ptr [rax+rcx*8-10h], xmm0
0x18000ae7b  movzx   eax, word ptr [rdi+0Ah]
0x18000ae7f  lea     rcx, [rax+rax*2]
0x18000ae83  mov     rax, [rdi]
0x18000ae86  mov     [rax+rcx*8], rsi
0x18000ae8a  xor     esi, esi
0x18000ae8c  add     [rdi+0Ah], r15w
0x18000ae91  xor     ebx, ebx
0x18000ae93  mov     rcx, rsi
0x18000ae96  call    EapCloseAggregatedEventNode
0x18000ae9b  mov     eax, ebx
0x18000ae9d  mov     rcx, [rsp+78h+var_30]
0x18000aea2  xor     rcx, rsp; StackCookie
0x18000aea5  call    __security_check_cookie
0x18000aeaa  mov     rbx, [rsp+78h+arg_10]
0x18000aeb2  add     rsp, 50h
0x18000aeb6  pop     r15
0x18000aeb8  pop     r14
0x18000aeba  pop     rdi
0x18000aebb  pop     rsi
0x18000aebc  pop     rbp
0x18000aebd  retn
```
