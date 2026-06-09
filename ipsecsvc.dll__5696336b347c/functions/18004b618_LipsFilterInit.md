# LipsFilterInit

- ea: `0x18004b618`
- end: `0x18004b6e9`
- name: `LipsFilterInit`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004b410`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004b618`
- `0x18004d05e`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18004b63a`
- `RPCRT4!UuidCreate` at `0x18004b63a`

## string_xrefs

- `0x18004b677`: `WfpGuidCreate`

## pseudocode

```c
__int64 __fastcall LipsFilterInit(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // edi
  __int64 result; // rax

  memset_0((void *)a2, 0, 0xC8u);
  v4 = UuidCreate((UUID *)a2);
  v5 = v4;
  if ( !v4 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids, v4);
  v6 = LipsReportError(v5, "WfpGuidCreate");
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids, v6);
    return LipsReportError(v7, "LipsFilterInit");
  }
  else
  {
LABEL_10:
    *(_QWORD *)(a2 + 152) = a1;
    *(_QWORD *)(a2 + 16) = aLipsFilter;
    result = 0;
    *(_DWORD *)(a2 + 96) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004b618  push    rbx
0x18004b61a  push    rbp
0x18004b61b  push    rsi
0x18004b61c  push    rdi
0x18004b61d  sub     rsp, 28h
0x18004b621  mov     rbx, rdx
0x18004b624  mov     rsi, rcx
0x18004b627  mov     rcx, rbx; void *
0x18004b62a  xor     edx, edx; Val
0x18004b62c  mov     r8d, 0C8h; Size
0x18004b632  call    memset_0
0x18004b637  mov     rcx, rbx; Uuid
0x18004b63a  call    cs:__imp_UuidCreate
0x18004b640  mov     edi, eax
0x18004b642  test    eax, eax
0x18004b644  jz      short loc_18004B6C5
0x18004b646  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b64d  lea     rbp, WPP_GLOBAL_Control
0x18004b654  cmp     rcx, rbp
0x18004b657  jz      short loc_18004B677
0x18004b659  test    byte ptr [rcx+1Ch], 10h
0x18004b65d  jz      short loc_18004B677
0x18004b65f  mov     rcx, [rcx+10h]
0x18004b663  lea     r8, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids
0x18004b66a  mov     edx, 1Eh
0x18004b66f  mov     r9d, eax
0x18004b672  call    WPP_SF_d
0x18004b677  lea     rdx, aWfpguidcreate; "WfpGuidCreate"
0x18004b67e  mov     ecx, edi
0x18004b680  call    LipsReportError
0x18004b685  mov     edi, eax
0x18004b687  test    eax, eax
0x18004b689  jz      short loc_18004B6C5
0x18004b68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b692  cmp     rcx, rbp
0x18004b695  jz      short loc_18004B6B5
0x18004b697  test    byte ptr [rcx+1Ch], 10h
0x18004b69b  jz      short loc_18004B6B5
0x18004b69d  mov     rcx, [rcx+10h]
0x18004b6a1  lea     r8, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids
0x18004b6a8  mov     edx, 1Fh
0x18004b6ad  mov     r9d, eax
0x18004b6b0  call    WPP_SF_d
0x18004b6b5  lea     rdx, aLipsfilterinit; "LipsFilterInit"
0x18004b6bc  mov     ecx, edi
0x18004b6be  call    LipsReportError
0x18004b6c3  jmp     short loc_18004B6E0
0x18004b6c5  lea     rax, aLipsFilter; "LIPS Filter"
0x18004b6cc  mov     [rbx+98h], rsi
0x18004b6d3  mov     [rbx+10h], rax
0x18004b6d7  xor     eax, eax
0x18004b6d9  mov     dword ptr [rbx+60h], 0
0x18004b6e0  add     rsp, 28h
0x18004b6e4  pop     rdi
0x18004b6e5  pop     rsi
0x18004b6e6  pop     rbp
0x18004b6e7  pop     rbx
0x18004b6e8  retn
```
