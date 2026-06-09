# CDumpCollection::_AddGather(WER_GATHER *,WER_GATHER * *)

- ea: `0x18003fe28`
- end: `0x1800400f0`
- name: `?_AddGather@CDumpCollection@@AEAAJPEAUWER_GATHER@@PEAPEAU2@@Z`
- size: `712`
- prototype: `__int64 __fastcall(HANDLE *this, LPCVOID lpBaseAddress, struct WER_GATHER **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800401c4`

## callees

- `0x1800028b4`
- `0x1800047cc`
- `0x180009ed8`
- `0x180009f00`
- `0x18003fbbc`
- `0x18003fe28`
- `0x1800400f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800400b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800400b9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003feb3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003ff2b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003feb3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003ff2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDumpCollection::_AddGather(HANDLE *this, LPCVOID lpBaseAddress, struct WER_GATHER **a3)
{
  struct WER_GATHER *v7; // rsi
  const struct std::nothrow_t *v8; // rdx
  unsigned int *v9; // rbx
  int v10; // ecx
  int v11; // eax
  __int64 v12; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  DWORD v16; // eax
  DWORD LastError; // eax
  _OWORD Buffer[6]; // [rsp+30h] [rbp-68h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+B0h] [rbp+18h] BYREF

  memset(Buffer, 0, 32);
  if ( a3 )
  {
    v7 = 0;
    *a3 = 0;
    NumberOfBytesRead = 0;
    if ( !ReadProcessMemory(this[137], lpBaseAddress, Buffer, 0x20u, &NumberOfBytesRead) || NumberOfBytesRead != 32 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, LastError);
      }
      goto LABEL_39;
    }
    if ( (WORD4(Buffer[0]) & 0x3FFFu) <= 0x20 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids,
          WORD4(Buffer[0]) & 0x3FFF);
      goto LABEL_39;
    }
    v9 = (unsigned int *)operator new[](WORD4(Buffer[0]) & 0x3FFF, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
      goto LABEL_31;
    }
    if ( !ReadProcessMemory(this[137], lpBaseAddress, v9, WORD4(Buffer[0]) & 0x3FFF, &NumberOfBytesRead)
      || NumberOfBytesRead != (WORD4(Buffer[0]) & 0x3FFF)
      || (v9[2] & 0x3FFF) != NumberOfBytesRead )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v16);
      }
      goto LABEL_31;
    }
    v10 = *((unsigned __int16 *)v9 + 4) >> 14;
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_24;
      v11 = CDumpCollection::_AddFile((CDumpCollection *)this, (struct WER_GATHER *)v9);
      v12 = (unsigned int)v11;
      if ( v11 >= 0 )
        goto LABEL_24;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v14 = 19;
    }
    else
    {
      v15 = CDumpCollection::_AddMemoryBlock((CDumpCollection *)this, *((_QWORD *)v9 + 2), v9[6]);
      v12 = (unsigned int)v15;
      if ( v15 >= 0 )
        goto LABEL_24;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v14 = 18;
    }
    WPP_SF_d(v13[2], v14, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v12);
LABEL_24:
    v7 = *(struct WER_GATHER **)v9;
LABEL_31:
    if ( v9 )
      operator delete(v9, v8);
LABEL_39:
    *a3 = v7;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003fe28  push    rbx
0x18003fe2a  push    rbp
0x18003fe2b  push    rsi
0x18003fe2c  push    rdi
0x18003fe2d  push    r14
0x18003fe2f  push    r15
0x18003fe31  sub     rsp, 68h
0x18003fe35  mov     r14, r8
0x18003fe38  mov     rbp, rdx
0x18003fe3b  mov     rdi, rcx
0x18003fe3e  xorps   xmm0, xmm0
0x18003fe41  movups  [rsp+98h+Buffer], xmm0
0x18003fe46  movups  [rsp+98h+var_58], xmm0
0x18003fe4b  test    r8, r8
0x18003fe4e  jnz     short loc_18003FE87
0x18003fe50  lea     rax, WPP_GLOBAL_Control
0x18003fe57  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe5e  cmp     rcx, rax
0x18003fe61  jz      short loc_18003FE7D
0x18003fe63  test    byte ptr [rcx+1Ch], 1
0x18003fe67  jz      short loc_18003FE7D
0x18003fe69  lea     edx, [r8+11h]
0x18003fe6d  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003fe74  mov     rcx, [rcx+10h]
0x18003fe78  call    WPP_SF_
0x18003fe7d  mov     eax, 80070057h
0x18003fe82  jmp     loc_1800400E3
0x18003fe87  xor     esi, esi
0x18003fe89  mov     [r8], rsi
0x18003fe8c  mov     [rsp+98h+NumberOfBytesRead], rsi
0x18003fe94  lea     rax, [rsp+98h+NumberOfBytesRead]
0x18003fe9c  mov     [rsp+98h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003fea1  lea     ebx, [rsi+20h]
0x18003fea4  mov     r9d, ebx; nSize
0x18003fea7  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18003feac  mov     rcx, [rcx+448h]; hProcess
0x18003feb3  call    cs:__imp_ReadProcessMemory
0x18003feb9  test    eax, eax
0x18003febb  jz      loc_1800400A0
0x18003fec1  cmp     [rsp+98h+NumberOfBytesRead], rbx
0x18003fec9  jnz     loc_1800400A0
0x18003fecf  mov     r9, qword ptr [rsp+98h+Buffer+8]
0x18003fed4  movzx   eax, r9w
0x18003fed8  mov     r15d, 3FFFh
0x18003fede  and     ax, r15w
0x18003fee2  cmp     ax, bx
0x18003fee5  jbe     loc_18004006D
0x18003feeb  and     r9, r15
0x18003feee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003fef5  mov     rcx, r9; unsigned __int64
0x18003fef8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003fefd  mov     rbx, rax
0x18003ff00  test    rax, rax
0x18003ff03  jz      loc_18004002F
0x18003ff09  mov     r9, qword ptr [rsp+98h+Buffer+8]
0x18003ff0e  and     r9, r15; nSize
0x18003ff11  lea     rax, [rsp+98h+NumberOfBytesRead]
0x18003ff19  mov     [rsp+98h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003ff1e  mov     r8, rbx; lpBuffer
0x18003ff21  mov     rdx, rbp; lpBaseAddress
0x18003ff24  mov     rcx, [rdi+448h]; hProcess
0x18003ff2b  call    cs:__imp_ReadProcessMemory
0x18003ff31  test    eax, eax
0x18003ff33  jz      loc_18003FFEF
0x18003ff39  mov     rax, qword ptr [rsp+98h+Buffer+8]
0x18003ff3e  and     rax, r15
0x18003ff41  cmp     [rsp+98h+NumberOfBytesRead], rax
0x18003ff49  jnz     loc_18003FFEF
0x18003ff4f  movzx   ecx, word ptr [rbx+8]
0x18003ff53  mov     eax, ecx
0x18003ff55  and     rax, r15
0x18003ff58  cmp     rax, [rsp+98h+NumberOfBytesRead]
0x18003ff60  jnz     loc_18003FFEF
0x18003ff66  movzx   ecx, cx
0x18003ff69  shr     ecx, 0Eh
0x18003ff6c  test    ecx, ecx
0x18003ff6e  jz      short loc_18003FFA5
0x18003ff70  cmp     ecx, 1
0x18003ff73  jnz     short loc_18003FFEA
0x18003ff75  mov     rdx, rbx; struct WER_GATHER *
0x18003ff78  mov     rcx, rdi; this
0x18003ff7b  call    ?_AddFile@CDumpCollection@@AEAAJPEAUWER_GATHER@@@Z; CDumpCollection::_AddFile(WER_GATHER *)
0x18003ff80  mov     r9d, eax
0x18003ff83  test    eax, eax
0x18003ff85  jns     short loc_18003FFEA
0x18003ff87  lea     rax, WPP_GLOBAL_Control
0x18003ff8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff95  cmp     rcx, rax
0x18003ff98  jz      short loc_18003FFEA
0x18003ff9a  test    byte ptr [rcx+1Ch], 1
0x18003ff9e  jz      short loc_18003FFEA
0x18003ffa0  lea     edx, [rsi+13h]
0x18003ffa3  jmp     short loc_18003FFDA
0x18003ffa5  mov     r8d, [rbx+18h]; unsigned int
0x18003ffa9  mov     rdx, [rbx+10h]; unsigned __int64
0x18003ffad  mov     rcx, rdi; this
0x18003ffb0  call    ?_AddMemoryBlock@CDumpCollection@@AEAAJ_KK@Z; CDumpCollection::_AddMemoryBlock(unsigned __int64,ulong)
0x18003ffb5  mov     r9d, eax
0x18003ffb8  test    eax, eax
0x18003ffba  jns     short loc_18003FFEA
0x18003ffbc  lea     rax, WPP_GLOBAL_Control
0x18003ffc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ffca  cmp     rcx, rax
0x18003ffcd  jz      short loc_18003FFEA
0x18003ffcf  test    byte ptr [rcx+1Ch], 1
0x18003ffd3  jz      short loc_18003FFEA
0x18003ffd5  mov     edx, 12h
0x18003ffda  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18003ffe1  mov     rcx, [rcx+10h]
0x18003ffe5  call    WPP_SF_d
0x18003ffea  mov     rsi, [rbx]
0x18003ffed  jmp     short loc_18004005E
0x18003ffef  lea     rax, WPP_GLOBAL_Control
0x18003fff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fffd  cmp     rcx, rax
0x180040000  jz      short loc_18004005E
0x180040002  test    byte ptr [rcx+1Ch], 1
0x180040006  jz      short loc_18004005E
0x180040008  call    cs:__imp_GetLastError
0x18004000e  mov     edx, 14h
0x180040013  mov     r9d, eax
0x180040016  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x18004001d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040024  mov     rcx, [rcx+10h]
0x180040028  call    WPP_SF_d
0x18004002d  jmp     short loc_18004005E
0x18004002f  lea     rax, WPP_GLOBAL_Control
0x180040036  mov     rcx, cs:WPP_GLOBAL_Control
0x18004003d  cmp     rcx, rax
0x180040040  jz      short loc_18004005E
0x180040042  test    byte ptr [rcx+1Ch], 1
0x180040046  jz      short loc_18004005E
0x180040048  mov     edx, 15h
0x18004004d  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x180040054  mov     rcx, [rcx+10h]
0x180040058  call    WPP_SF_
0x18004005d  nop
0x18004005e  test    rbx, rbx
0x180040061  jz      short loc_1800400DE
0x180040063  mov     rcx, rbx; void *
0x180040066  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004006b  jmp     short loc_1800400DE
0x18004006d  lea     rax, WPP_GLOBAL_Control
0x180040074  mov     rcx, cs:WPP_GLOBAL_Control
0x18004007b  cmp     rcx, rax
0x18004007e  jz      short loc_1800400DE
0x180040080  test    byte ptr [rcx+1Ch], 2
0x180040084  jz      short loc_1800400DE
0x180040086  and     r9d, r15d
0x180040089  mov     edx, 16h
0x18004008e  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x180040095  mov     rcx, [rcx+10h]
0x180040099  call    WPP_SF_d
0x18004009e  jmp     short loc_1800400DE
0x1800400a0  lea     rax, WPP_GLOBAL_Control
0x1800400a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800400ae  cmp     rcx, rax
0x1800400b1  jz      short loc_1800400DE
0x1800400b3  test    byte ptr [rcx+1Ch], 2
0x1800400b7  jz      short loc_1800400DE
0x1800400b9  call    cs:__imp_GetLastError
0x1800400bf  mov     edx, 17h
0x1800400c4  mov     r9d, eax
0x1800400c7  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x1800400ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800400d5  mov     rcx, [rcx+10h]
0x1800400d9  call    WPP_SF_d
0x1800400de  mov     [r14], rsi
0x1800400e1  xor     eax, eax
0x1800400e3  add     rsp, 68h
0x1800400e7  pop     r15
0x1800400e9  pop     r14
0x1800400eb  pop     rdi
0x1800400ec  pop     rsi
0x1800400ed  pop     rbp
0x1800400ee  pop     rbx
0x1800400ef  retn
```
