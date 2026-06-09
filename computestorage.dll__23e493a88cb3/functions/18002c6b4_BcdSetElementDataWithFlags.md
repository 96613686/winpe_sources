# BcdSetElementDataWithFlags

- ea: `0x18002c6b4`
- end: `0x18002c9a4`
- name: `BcdSetElementDataWithFlags`
- size: `752`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180020880`
- `0x180035730`

## callees

- `0x180002690`
- `0x180003204`
- `0x18002c6b4`
- `0x18002c9ac`
- `0x18002d374`
- `0x18002d940`
- `0x18002e360`
- `0x18002e3dc`
- `0x18003223c`
- `0x1800322e4`
- `0x18003290c`
- `0x180033914`
- `0x180033c68`
- `0x180034254`
- `0x1800343a8`
- `0x180034f24`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002c911`
- `ntdll!RtlFreeHeap` at `0x18002c911`

## string_xrefs

- `0x18002c845`: `Failed to open key for element %s. Status: %x`
- `0x18002c7d0`: `Failed to open key for object's elements. Status: %x`
- `0x18002c8e2`: `Failed to set registry data for element %s. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdSetElementDataWithFlags(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  HANDLE v8; // r15
  HANDLE v9; // r14
  unsigned int v10; // esi
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edi
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  PVOID v20; // r12
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // eax
  int *v25; // [rsp+28h] [rbp-59h]
  bool v26; // [rsp+30h] [rbp-51h] BYREF
  char v27; // [rsp+31h] [rbp-50h]
  int v28; // [rsp+34h] [rbp-4Dh] BYREF
  HANDLE v29; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-41h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-39h] BYREF
  __int64 v32; // [rsp+50h] [rbp-31h]
  PVOID P; // [rsp+58h] [rbp-29h]
  WCHAR v34[24]; // [rsp+60h] [rbp-21h] BYREF

  v32 = a4;
  v30 = a2;
  v28 = 0;
  if ( !a4 && a5 )
    return 3221225485LL;
  v29 = 0;
  v8 = 0;
  v26 = 0;
  v9 = 0;
  Handle = 0;
  P = 0;
  if ( !a5 )
  {
    BiDeleteElement(a1, a2);
    return 0;
  }
  BiLogMessage(2, L"Setting element %08x", a2);
  v10 = 1;
  LOBYTE(v11) = a1 & 1;
  v27 = a1 & 1;
  v12 = BiAcquireBcdSyncMutant(v11);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = BiFilterDoOperation(1, a1, a2, v32, a5);
    v13 = v14;
    if ( v14 < 0 )
    {
      BiLogMessage(4, L"Failed filtering for element %08x. Status: 0x%x", a2, (unsigned int)v14);
      goto LABEL_28;
    }
    v16 = BiOpenKey(a1, L"Elements", 131101, &v29);
    v13 = v16;
    if ( v16 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for object's elements. Status: %x", (unsigned int)v16);
      v8 = v29;
      goto LABEL_28;
    }
    v17 = o__ultow_s_0(a2, v34, 22);
    v8 = v29;
    if ( v17 )
    {
      v13 = -1073741823;
LABEL_32:
      if ( v8 )
        BiCloseKey((unsigned __int64)v8);
      if ( v13 >= 0 )
      {
        if ( (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v30) )
          BiSetFirmwareModifiedFromObject(a1);
      }
      LOBYTE(v15) = v27;
      BiReleaseBcdSyncMutant(v15);
      return (unsigned int)v13;
    }
    v18 = BiCreateKey((unsigned __int64)v29, v34, 0x10002u, 1u, &Handle, &v26);
    v13 = v18;
    if ( v18 < 0 )
    {
      BiLogMessage(4, L"Failed to open key for element %s. Status: %x", v34, (unsigned int)v18);
      v9 = Handle;
LABEL_28:
      if ( v26 )
      {
        BiDeleteKey((__int64)v9);
        v9 = 0;
      }
LABEL_30:
      if ( v9 )
        BiCloseKey((unsigned __int64)v9);
      goto LABEL_32;
    }
    v25 = &v28;
    v19 = BiConvertElementToRegistryData(a2, v32, a5);
    v9 = Handle;
    v13 = v19;
    v20 = P;
    if ( v19 < 0 )
    {
      BiLogMessage(4, L"Failed to convert data for element %s. Status: %x", v34, (unsigned int)v19);
      goto LABEL_25;
    }
    v21 = (HIBYTE(a2) & 0xF) - 1;
    if ( !v21 )
      goto LABEL_22;
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 != 1 )
        {
LABEL_22:
          v10 = 3;
          goto LABEL_23;
        }
        v10 = 7;
      }
    }
LABEL_23:
    LODWORD(v25) = v28;
    v24 = BiSetRegistryValue(Handle, L"Element", 0, v10, P, v25);
    v13 = v24;
    if ( v24 < 0 )
      BiLogMessage(4, L"Failed to set registry data for element %s. Status: %x", v34, (unsigned int)v24);
LABEL_25:
    if ( v20 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    if ( v13 >= 0 )
      goto LABEL_30;
    goto LABEL_28;
  }
  BiLogMessage(4, L"BcdSetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002c6b4  mov     [rsp-8+arg_10], rbx
0x18002c6b9  push    rbp
0x18002c6ba  push    rsi
0x18002c6bb  push    rdi
0x18002c6bc  push    r12
0x18002c6be  push    r13
0x18002c6c0  push    r14
0x18002c6c2  push    r15
0x18002c6c4  lea     rbp, [rsp-1Fh]
0x18002c6c9  sub     rsp, 0A0h
0x18002c6d0  mov     rax, cs:__security_cookie
0x18002c6d7  xor     rax, rsp
0x18002c6da  mov     [rbp+4Fh+var_40], rax
0x18002c6de  mov     r12d, [rbp+4Fh+arg_20]
0x18002c6e2  mov     r13, rcx
0x18002c6e5  xor     ecx, ecx
0x18002c6e7  mov     [rbp+4Fh+var_80], r9
0x18002c6eb  mov     [rbp+4Fh+var_90], edx
0x18002c6ee  mov     ebx, edx
0x18002c6f0  mov     [rbp+4Fh+var_9C], ecx
0x18002c6f3  test    r9, r9
0x18002c6f6  jnz     short loc_18002C707
0x18002c6f8  test    r12d, r12d
0x18002c6fb  jz      short loc_18002C707
0x18002c6fd  mov     eax, 0C000000Dh
0x18002c702  jmp     loc_18002C972
0x18002c707  mov     [rbp+4Fh+var_98], rcx
0x18002c70b  mov     r15, rcx
0x18002c70e  mov     [rbp+4Fh+var_A0], cl
0x18002c711  mov     r14, rcx
0x18002c714  mov     [rbp+4Fh+Handle], rcx
0x18002c718  mov     [rbp+4Fh+P], rcx
0x18002c71c  test    r12d, r12d
0x18002c71f  jnz     short loc_18002C730
0x18002c721  mov     rcx, r13
0x18002c724  call    BiDeleteElement
0x18002c729  xor     eax, eax
0x18002c72b  jmp     loc_18002C972
0x18002c730  mov     r8d, ebx
0x18002c733  lea     rdx, aSettingElement; "Setting element %08x"
0x18002c73a  mov     ecx, 2
0x18002c73f  call    BiLogMessage
0x18002c744  mov     al, r13b
0x18002c747  mov     esi, 1
0x18002c74c  and     al, sil
0x18002c74f  mov     cl, al
0x18002c751  mov     [rbp+4Fh+var_9F], al
0x18002c754  call    BiAcquireBcdSyncMutant
0x18002c759  mov     edi, eax
0x18002c75b  test    eax, eax
0x18002c75d  jns     short loc_18002C776
0x18002c75f  mov     r8d, eax
0x18002c762  lea     rdx, aBcdsetelementd; "BcdSetElementDataWithFlags: Failed to a"...
0x18002c769  lea     ecx, [rsi+3]
0x18002c76c  call    BiLogMessage
0x18002c771  jmp     loc_18002C970
0x18002c776  mov     r9, [rbp+4Fh+var_80]
0x18002c77a  mov     r8d, ebx
0x18002c77d  mov     rdx, r13
0x18002c780  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x18002c785  mov     ecx, esi
0x18002c787  call    BiFilterDoOperation
0x18002c78c  mov     edi, eax
0x18002c78e  test    eax, eax
0x18002c790  jns     short loc_18002C7AE
0x18002c792  mov     r9d, eax
0x18002c795  lea     rdx, aFailedFilterin; "Failed filtering for element %08x. Stat"...
0x18002c79c  mov     r8d, ebx
0x18002c79f  mov     ecx, 4
0x18002c7a4  call    BiLogMessage
0x18002c7a9  jmp     loc_18002C921
0x18002c7ae  lea     r9, [rbp+4Fh+var_98]
0x18002c7b2  mov     r8d, 2001Dh
0x18002c7b8  lea     rdx, aElements; "Elements"
0x18002c7bf  mov     rcx, r13
0x18002c7c2  call    BiOpenKey
0x18002c7c7  mov     edi, eax
0x18002c7c9  test    eax, eax
0x18002c7cb  jns     short loc_18002C7EA
0x18002c7cd  mov     r8d, eax
0x18002c7d0  lea     rdx, aFailedToOpenKe_0; "Failed to open key for object's element"...
0x18002c7d7  mov     ecx, 4
0x18002c7dc  call    BiLogMessage
0x18002c7e1  mov     r15, [rbp+4Fh+var_98]
0x18002c7e5  jmp     loc_18002C921
0x18002c7ea  mov     r9d, 10h
0x18002c7f0  lea     rdx, [rbp+4Fh+var_70]
0x18002c7f4  mov     ecx, ebx
0x18002c7f6  lea     r8d, [r9+6]
0x18002c7fa  call    _o__ultow_s_0
0x18002c7ff  mov     r15, [rbp+4Fh+var_98]
0x18002c803  test    eax, eax
0x18002c805  jz      short loc_18002C811
0x18002c807  mov     edi, 0C0000001h
0x18002c80c  jmp     loc_18002C93F
0x18002c811  lea     rax, [rbp+4Fh+var_A0]
0x18002c815  mov     r9d, esi
0x18002c818  mov     [rsp+0D0h+var_A8], rax
0x18002c81d  lea     rdx, [rbp+4Fh+var_70]
0x18002c821  lea     rax, [rbp+4Fh+Handle]
0x18002c825  mov     r8d, 10002h
0x18002c82b  mov     rcx, r15
0x18002c82e  mov     [rsp+0D0h+var_B0], rax
0x18002c833  call    BiCreateKey
0x18002c838  mov     edi, eax
0x18002c83a  test    eax, eax
0x18002c83c  jns     short loc_18002C85F
0x18002c83e  mov     r9d, eax
0x18002c841  lea     r8, [rbp+4Fh+var_70]
0x18002c845  lea     rdx, aFailedToOpenKe_1; "Failed to open key for element %s. Stat"...
0x18002c84c  mov     ecx, 4
0x18002c851  call    BiLogMessage
0x18002c856  mov     r14, [rbp+4Fh+Handle]
0x18002c85a  jmp     loc_18002C921
0x18002c85f  mov     rdx, [rbp+4Fh+var_80]
0x18002c863  lea     rax, [rbp+4Fh+var_9C]
0x18002c867  mov     [rsp+0D0h+var_A8], rax
0x18002c86c  mov     r8d, r12d
0x18002c86f  lea     rax, [rbp+4Fh+P]
0x18002c873  mov     ecx, ebx
0x18002c875  mov     [rsp+0D0h+var_B0], rax
0x18002c87a  call    BiConvertElementToRegistryData
0x18002c87f  mov     r14, [rbp+4Fh+Handle]
0x18002c883  mov     edi, eax
0x18002c885  mov     r12, [rbp+4Fh+P]
0x18002c889  test    eax, eax
0x18002c88b  jns     short loc_18002C896
0x18002c88d  lea     rdx, aFailedToConver; "Failed to convert data for element %s. "...
0x18002c894  jmp     short loc_18002C8E9
0x18002c896  shr     ebx, 18h
0x18002c899  and     ebx, 0Fh
0x18002c89c  sub     ebx, esi
0x18002c89e  jz      short loc_18002C8B6
0x18002c8a0  sub     ebx, esi
0x18002c8a2  jz      short loc_18002C8BB
0x18002c8a4  sub     ebx, esi
0x18002c8a6  jz      short loc_18002C8BB
0x18002c8a8  sub     ebx, esi
0x18002c8aa  jz      loc_18002C99A
0x18002c8b0  sub     ebx, esi
0x18002c8b2  jz      short loc_18002C8B6
0x18002c8b4  sub     ebx, esi
0x18002c8b6  mov     esi, 3
0x18002c8bb  mov     eax, [rbp+4Fh+var_9C]
0x18002c8be  lea     rdx, aElement; "Element"
0x18002c8c5  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18002c8c9  mov     r9d, esi
0x18002c8cc  xor     r8d, r8d
0x18002c8cf  mov     [rsp+0D0h+var_B0], r12
0x18002c8d4  mov     rcx, r14
0x18002c8d7  call    BiSetRegistryValue
0x18002c8dc  mov     edi, eax
0x18002c8de  test    eax, eax
0x18002c8e0  jns     short loc_18002C8FA
0x18002c8e2  lea     rdx, aFailedToSetReg; "Failed to set registry data for element"...
0x18002c8e9  mov     r9d, eax
0x18002c8ec  lea     r8, [rbp+4Fh+var_70]
0x18002c8f0  mov     ecx, 4
0x18002c8f5  call    BiLogMessage
0x18002c8fa  test    r12, r12
0x18002c8fd  jz      short loc_18002C91D
0x18002c8ff  mov     rcx, gs:60h
0x18002c908  mov     r8, r12; P
0x18002c90b  xor     edx, edx; Flags
0x18002c90d  mov     rcx, [rcx+30h]; HeapHandle
0x18002c911  call    cs:__imp_RtlFreeHeap
0x18002c918  nop     dword ptr [rax+rax+00h]
0x18002c91d  test    edi, edi
0x18002c91f  jns     short loc_18002C932
0x18002c921  cmp     [rbp+4Fh+var_A0], 0
0x18002c925  jz      short loc_18002C932
0x18002c927  mov     rcx, r14
0x18002c92a  call    BiDeleteKey
0x18002c92f  xor     r14d, r14d
0x18002c932  test    r14, r14
0x18002c935  jz      short loc_18002C93F
0x18002c937  mov     rcx, r14; Handle
0x18002c93a  call    BiCloseKey
0x18002c93f  test    r15, r15
0x18002c942  jz      short loc_18002C94C
0x18002c944  mov     rcx, r15; Handle
0x18002c947  call    BiCloseKey
0x18002c94c  test    edi, edi
0x18002c94e  js      short loc_18002C968
0x18002c950  lea     rdx, [rbp+4Fh+var_90]
0x18002c954  mov     rcx, r13
0x18002c957  call    BiIsLinkedToFirmwareVariable
0x18002c95c  test    al, al
0x18002c95e  jz      short loc_18002C968
0x18002c960  mov     rcx, r13
0x18002c963  call    BiSetFirmwareModifiedFromObject
0x18002c968  mov     cl, [rbp+4Fh+var_9F]
0x18002c96b  call    BiReleaseBcdSyncMutant
0x18002c970  mov     eax, edi
0x18002c972  mov     rcx, [rbp+4Fh+var_40]
0x18002c976  xor     rcx, rsp; StackCookie
0x18002c979  call    __security_check_cookie
0x18002c97e  mov     rbx, [rsp+0D0h+arg_10]
0x18002c986  add     rsp, 0A0h
0x18002c98d  pop     r15
0x18002c98f  pop     r14
0x18002c991  pop     r13
0x18002c993  pop     r12
0x18002c995  pop     rdi
0x18002c996  pop     rsi
0x18002c997  pop     rbp
0x18002c998  retn
0x18002c99a  mov     esi, 7
0x18002c99f  jmp     loc_18002C8BB
```
