# AslpFileGetHeaderAttributesNE

- ea: `0x14000d858`
- end: `0x14000d9f1`
- name: `AslpFileGetHeaderAttributesNE`
- size: `409`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000c630`

## callees

- `0x140007074`
- `0x140009c14`
- `0x14000bde8`
- `0x14000cb60`
- `0x14000cc48`
- `0x14000d858`

## string_xrefs

- `0x14000d945`: `AslStringXmlSanitize failed [%x]`
- `0x14000d9b1`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetHeaderAttributesNE(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // edi
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  v15 = 0;
  v4 = AslFileMappingEnsure(a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) == 5 )
    {
      *(_DWORD *)(a1 + 600) |= 2u;
      *(_DWORD *)(a1 + 632) |= 2u;
      *(_DWORD *)(a1 + 728) |= 2u;
      *(_DWORD *)(a1 + 56) |= 2u;
      *(_DWORD *)(a1 + 824) |= 2u;
      *(_DWORD *)(a1 + 760) |= 2u;
      *(_DWORD *)(a1 + 952) |= 2u;
      *(_DWORD *)(a1 + 984) |= 2u;
      *(_DWORD *)(a1 + 1016) |= 2u;
      *(_DWORD *)(a1 + 1080) |= 2u;
      v9 = -1;
      if ( (int)AslpFileGet16BitDescription(&v14, a2) < 0 )
      {
        *(_DWORD *)(a1 + 664) |= 2u;
      }
      else
      {
        v4 = AslStringXmlSanitize(v14);
        v5 = v4;
        if ( v4 < 0 )
        {
          v6 = "AslStringXmlSanitize failed [%x]";
          v7 = 3525;
          goto LABEL_3;
        }
        *(_DWORD *)(a1 + 640) = 4;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(v10 + 2 * v11) );
        *(_DWORD *)(a1 + 664) |= 5u;
        *(_QWORD *)(a1 + 648) = v11;
        *(_QWORD *)(a1 + 656) = v10;
      }
      if ( (int)AslpFileGet16BitModuleName(&v15, a2) >= 0 )
      {
        v4 = AslStringXmlSanitize(v15);
        v5 = v4;
        if ( v4 < 0 )
        {
          v6 = "AslStringXmlSanitize failed [%x]";
          v7 = 3546;
          goto LABEL_3;
        }
        *(_DWORD *)(a1 + 672) = 4;
        do
          ++v9;
        while ( *(_WORD *)(v12 + 2 * v9) );
        *(_DWORD *)(a1 + 696) |= 5u;
        *(_QWORD *)(a1 + 680) = v9;
        *(_QWORD *)(a1 + 688) = v12;
        return 0;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 664) |= 2u;
    }
    *(_DWORD *)(a1 + 696) |= 2u;
    return 0;
  }
  v6 = "AslFileMappingEnsure failed [%x]";
  v7 = 3489;
LABEL_3:
  v13 = v4;
  AslLogCallPrintf(1, "AslpFileGetHeaderAttributesNE", v7, v6, v13);
  return v5;
}

```

## disassembly

```asm
0x14000d858  mov     rax, rsp
0x14000d85b  mov     [rax+8], rbx
0x14000d85f  mov     [rax+10h], rbp
0x14000d863  push    rdi
0x14000d864  push    r14
0x14000d866  push    r15
0x14000d868  sub     rsp, 30h
0x14000d86c  mov     rbx, rcx
0x14000d86f  xor     r15d, r15d
0x14000d872  mov     rcx, rdx
0x14000d875  mov     [rax+18h], r15
0x14000d879  mov     [rax+20h], r15
0x14000d87d  mov     r14, rdx
0x14000d880  call    AslFileMappingEnsure
0x14000d885  mov     edi, eax
0x14000d887  test    eax, eax
0x14000d889  jns     short loc_14000D8AF
0x14000d88b  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x14000d892  mov     r8d, 0DA1h
0x14000d898  lea     rdx, aAslpfilegethea_1; "AslpFileGetHeaderAttributesNE"
0x14000d89f  mov     [rsp+48h+var_28], eax
0x14000d8a3  mov     ecx, 1
0x14000d8a8  call    AslLogCallPrintf
0x14000d8ad  jmp     short loc_14000D8C7
0x14000d8af  cmp     dword ptr [r14+38h], 5
0x14000d8b4  jz      short loc_14000D8DD
0x14000d8b6  or      dword ptr [rbx+298h], 2
0x14000d8bd  or      dword ptr [rbx+2B8h], 2
0x14000d8c4  mov     edi, r15d
0x14000d8c7  mov     rbx, [rsp+48h+arg_0]
0x14000d8cc  mov     eax, edi
0x14000d8ce  mov     rbp, [rsp+48h+arg_8]
0x14000d8d3  add     rsp, 30h
0x14000d8d7  pop     r15
0x14000d8d9  pop     r14
0x14000d8db  pop     rdi
0x14000d8dc  retn
0x14000d8dd  or      dword ptr [rbx+258h], 2
0x14000d8e4  lea     rcx, [rsp+48h+arg_10]
0x14000d8e9  or      dword ptr [rbx+278h], 2
0x14000d8f0  mov     rdx, r14
0x14000d8f3  or      dword ptr [rbx+2D8h], 2
0x14000d8fa  or      dword ptr [rbx+38h], 2
0x14000d8fe  or      dword ptr [rbx+338h], 2
0x14000d905  or      dword ptr [rbx+2F8h], 2
0x14000d90c  or      dword ptr [rbx+3B8h], 2
0x14000d913  or      dword ptr [rbx+3D8h], 2
0x14000d91a  or      dword ptr [rbx+3F8h], 2
0x14000d921  or      dword ptr [rbx+438h], 2
0x14000d928  call    AslpFileGet16BitDescription
0x14000d92d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000d931  test    eax, eax
0x14000d933  js      short loc_14000D985
0x14000d935  mov     rcx, [rsp+48h+arg_10]
0x14000d93a  call    AslStringXmlSanitize
0x14000d93f  mov     edi, eax
0x14000d941  test    eax, eax
0x14000d943  jns     short loc_14000D957
0x14000d945  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14000d94c  mov     r8d, 0DC5h
0x14000d952  jmp     loc_14000D898
0x14000d957  mov     dword ptr [rbx+280h], 4
0x14000d961  mov     rax, rbp
0x14000d964  inc     rax
0x14000d967  cmp     [rcx+rax*2], r15w
0x14000d96c  jnz     short loc_14000D964
0x14000d96e  or      dword ptr [rbx+298h], 5
0x14000d975  mov     [rbx+288h], rax
0x14000d97c  mov     [rbx+290h], rcx
0x14000d983  jmp     short loc_14000D98C
0x14000d985  or      dword ptr [rbx+298h], 2
0x14000d98c  mov     rdx, r14
0x14000d98f  lea     rcx, [rsp+48h+arg_18]
0x14000d994  call    AslpFileGet16BitModuleName
0x14000d999  test    eax, eax
0x14000d99b  js      loc_14000D8BD
0x14000d9a1  mov     rcx, [rsp+48h+arg_18]
0x14000d9a6  call    AslStringXmlSanitize
0x14000d9ab  mov     edi, eax
0x14000d9ad  test    eax, eax
0x14000d9af  jns     short loc_14000D9C3
0x14000d9b1  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x14000d9b8  mov     r8d, 0DDAh
0x14000d9be  jmp     loc_14000D898
0x14000d9c3  mov     dword ptr [rbx+2A0h], 4
0x14000d9cd  inc     rbp
0x14000d9d0  cmp     [rcx+rbp*2], r15w
0x14000d9d5  jnz     short loc_14000D9CD
0x14000d9d7  or      dword ptr [rbx+2B8h], 5
0x14000d9de  mov     [rbx+2A8h], rbp
0x14000d9e5  mov     [rbx+2B0h], rcx
0x14000d9ec  jmp     loc_14000D8C4
```
