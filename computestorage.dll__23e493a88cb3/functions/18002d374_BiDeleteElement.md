# BiDeleteElement

- ea: `0x18002d374`
- end: `0x18002d582`
- name: `BiDeleteElement`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18002c6b4`
- `0x18003792c`

## callees

- `0x180002690`
- `0x180003204`
- `0x18002d374`
- `0x18002d940`
- `0x18002e360`
- `0x18002e3dc`
- `0x18003223c`
- `0x18003290c`
- `0x180033914`
- `0x180034254`
- `0x1800343a8`
- `0x180034f24`

## string_xrefs

- `0x18002d3d0`: `BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x`
- `0x18002d437`: `Failed to filter delete element %08x. Status: %x`
- `0x18002d4cc`: `Failed to open element %ws key for delete. Status: %x`
- `0x18002d506`: `Failed to open element %ws key for delete. Status: %x`
- `0x18002d46a`: `Failed to open key for all object's elements. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteElement(unsigned __int64 a1, unsigned int a2)
{
  unsigned int v4; // r15d
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  HANDLE v12; // rdi
  int v13; // eax
  HANDLE v15; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-40h] BYREF
  WCHAR v18[24]; // [rsp+48h] [rbp-38h] BYREF

  v16 = a2;
  v4 = 2;
  BiLogMessage(2, L"Deleting element %08x", a2);
  LOBYTE(v5) = a1 & 1;
  v6 = BiAcquireBcdSyncMutant(v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v15 = 0;
    Handle = 0;
    v8 = BiFilterDoOperation(2, a1, a2, 0, 0);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v10 = BiOpenKey(a1, L"Elements", 131097, &v15);
      v7 = v10;
      if ( v10 >= 0 )
      {
        if ( (unsigned int)o__ultow_s_0(a2, v18, 22) )
        {
          v7 = -1073741823;
        }
        else
        {
          v11 = BiOpenKey((unsigned __int64)v15, v18, 0x10000, &Handle);
          if ( v11 >= 0 )
          {
            v12 = Handle;
            v13 = BiDeleteKey(Handle);
            v7 = v13;
            if ( v13 >= 0 )
              v12 = 0;
            else
              BiLogMessage(4, L"Failed to open element %ws key for delete. Status: %x", v18, (unsigned int)v13);
          }
          else
          {
            if ( v11 != -1073741772 )
              v4 = 4;
            BiLogMessage(v4, L"Failed to open element %ws key for delete. Status: %x", v18, (unsigned int)v11);
            v12 = Handle;
            v7 = -1073741275;
          }
          if ( v12 )
            BiCloseKey(v12);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed to open key for all object's elements. Status: %x", (unsigned int)v10);
      }
      if ( v15 )
        BiCloseKey(v15);
      if ( v7 >= 0 && (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v16) )
        BiSetFirmwareModifiedFromObject(a1);
    }
    else if ( v8 == -1069350910 )
    {
      BiLogMessage(4, L"Deleting element %08x blocked by secure boot policy.", a2);
    }
    else
    {
      BiLogMessage(4, L"Failed to filter delete element %08x. Status: %x", a2, (unsigned int)v8);
    }
    LOBYTE(v9) = a1 & 1;
    BiReleaseBcdSyncMutant(v9);
  }
  else
  {
    BiLogMessage(4, L"BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d374  mov     [rsp-28h+arg_10], rbx
0x18002d379  push    rbp
0x18002d37a  push    rsi
0x18002d37b  push    rdi
0x18002d37c  push    r12
0x18002d37e  push    r15
0x18002d380  mov     rbp, rsp
0x18002d383  sub     rsp, 80h
0x18002d38a  mov     rax, cs:__security_cookie
0x18002d391  xor     rax, rsp
0x18002d394  mov     [rbp+var_8], rax
0x18002d398  mov     edi, edx
0x18002d39a  mov     [rbp+var_48], edx
0x18002d39d  mov     rsi, rcx
0x18002d3a0  mov     r8d, edx
0x18002d3a3  mov     r15d, 2
0x18002d3a9  lea     rdx, aDeletingElemen; "Deleting element %08x"
0x18002d3b0  mov     ecx, r15d
0x18002d3b3  call    BiLogMessage
0x18002d3b8  mov     r12b, sil
0x18002d3bb  and     r12b, 1
0x18002d3bf  mov     cl, r12b
0x18002d3c2  call    BiAcquireBcdSyncMutant
0x18002d3c7  mov     ebx, eax
0x18002d3c9  test    eax, eax
0x18002d3cb  jns     short loc_18002D3E5
0x18002d3cd  mov     r8d, eax
0x18002d3d0  lea     rdx, aBideleteelemen; "BiDeleteElement: Failed to acquire BCD "...
0x18002d3d7  lea     ecx, [r15+2]
0x18002d3db  call    BiLogMessage
0x18002d3e0  jmp     loc_18002D55C
0x18002d3e5  xor     r9d, r9d
0x18002d3e8  mov     [rbp+var_50], 0
0x18002d3f0  mov     r8d, edi
0x18002d3f3  mov     [rbp+Handle], 0
0x18002d3fb  mov     rdx, rsi
0x18002d3fe  mov     [rsp+80h+var_60], 0
0x18002d406  mov     ecx, r15d
0x18002d409  call    BiFilterDoOperation
0x18002d40e  mov     ebx, eax
0x18002d410  test    eax, eax
0x18002d412  jns     short loc_18002D448
0x18002d414  mov     r8d, edi
0x18002d417  mov     ecx, 4
0x18002d41c  cmp     eax, 0C0430002h
0x18002d421  jnz     short loc_18002D434
0x18002d423  lea     rdx, aDeletingElemen_0; "Deleting element %08x blocked by secure"...
0x18002d42a  call    BiLogMessage
0x18002d42f  jmp     loc_18002D554
0x18002d434  mov     r9d, eax
0x18002d437  lea     rdx, aFailedToFilter; "Failed to filter delete element %08x. S"...
0x18002d43e  call    BiLogMessage
0x18002d443  jmp     loc_18002D554
0x18002d448  lea     r9, [rbp+var_50]
0x18002d44c  mov     r8d, 20019h
0x18002d452  lea     rdx, aElements; "Elements"
0x18002d459  mov     rcx, rsi
0x18002d45c  call    BiOpenKey
0x18002d461  mov     ebx, eax
0x18002d463  test    eax, eax
0x18002d465  jns     short loc_18002D480
0x18002d467  mov     r8d, eax
0x18002d46a  lea     rdx, aFailedToOpenKe; "Failed to open key for all object's ele"...
0x18002d471  mov     ecx, 4
0x18002d476  call    BiLogMessage
0x18002d47b  jmp     loc_18002D528
0x18002d480  mov     r9d, 10h
0x18002d486  lea     rdx, [rbp+var_38]
0x18002d48a  mov     ecx, edi
0x18002d48c  lea     r8d, [r9+6]
0x18002d490  call    _o__ultow_s_0
0x18002d495  test    eax, eax
0x18002d497  jz      short loc_18002D4A3
0x18002d499  mov     ebx, 0C0000001h
0x18002d49e  jmp     loc_18002D528
0x18002d4a3  mov     rcx, [rbp+var_50]
0x18002d4a7  lea     r9, [rbp+Handle]
0x18002d4ab  mov     r8d, 10000h
0x18002d4b1  lea     rdx, [rbp+var_38]
0x18002d4b5  call    BiOpenKey
0x18002d4ba  test    eax, eax
0x18002d4bc  jns     short loc_18002D4ED
0x18002d4be  mov     ecx, 4
0x18002d4c3  lea     r8, [rbp+var_38]
0x18002d4c7  cmp     eax, 0C0000034h
0x18002d4cc  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x18002d4d3  mov     r9d, eax
0x18002d4d6  cmovnz  r15d, ecx
0x18002d4da  mov     ecx, r15d
0x18002d4dd  call    BiLogMessage
0x18002d4e2  mov     rdi, [rbp+Handle]
0x18002d4e6  mov     ebx, 0C0000225h
0x18002d4eb  jmp     short loc_18002D51B
0x18002d4ed  mov     rdi, [rbp+Handle]
0x18002d4f1  mov     rcx, rdi
0x18002d4f4  call    BiDeleteKey
0x18002d4f9  mov     ebx, eax
0x18002d4fb  test    eax, eax
0x18002d4fd  jns     short loc_18002D519
0x18002d4ff  mov     r9d, eax
0x18002d502  lea     r8, [rbp+var_38]
0x18002d506  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x18002d50d  mov     ecx, 4
0x18002d512  call    BiLogMessage
0x18002d517  jmp     short loc_18002D51B
0x18002d519  xor     edi, edi
0x18002d51b  test    rdi, rdi
0x18002d51e  jz      short loc_18002D528
0x18002d520  mov     rcx, rdi; Handle
0x18002d523  call    BiCloseKey
0x18002d528  cmp     [rbp+var_50], 0
0x18002d52d  jz      short loc_18002D538
0x18002d52f  mov     rcx, [rbp+var_50]; Handle
0x18002d533  call    BiCloseKey
0x18002d538  test    ebx, ebx
0x18002d53a  js      short loc_18002D554
0x18002d53c  lea     rdx, [rbp+var_48]
0x18002d540  mov     rcx, rsi
0x18002d543  call    BiIsLinkedToFirmwareVariable
0x18002d548  test    al, al
0x18002d54a  jz      short loc_18002D554
0x18002d54c  mov     rcx, rsi
0x18002d54f  call    BiSetFirmwareModifiedFromObject
0x18002d554  mov     cl, r12b
0x18002d557  call    BiReleaseBcdSyncMutant
0x18002d55c  mov     eax, ebx
0x18002d55e  mov     rcx, [rbp+var_8]
0x18002d562  xor     rcx, rsp; StackCookie
0x18002d565  call    __security_check_cookie
0x18002d56a  mov     rbx, [rsp+80h+arg_10]
0x18002d572  add     rsp, 80h
0x18002d579  pop     r15
0x18002d57b  pop     r12
0x18002d57d  pop     rdi
0x18002d57e  pop     rsi
0x18002d57f  pop     rbp
0x18002d580  retn
```
