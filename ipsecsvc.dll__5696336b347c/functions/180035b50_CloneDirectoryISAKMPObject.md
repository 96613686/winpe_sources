# CloneDirectoryISAKMPObject

- ea: `0x180035b50`
- end: `0x180035d45`
- name: `CloneDirectoryISAKMPObject`
- size: `501`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035d4c`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x180035b50`
- `0x180036a94`
- `0x180036bd0`
- `0x180036c54`
- `0x180042bbc`

## pseudocode

```c
__int64 __fastcall CloneDirectoryISAKMPObject(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  __int64 v15; // rcx

  v4 = IpsecAllocMem(64);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 14);
    goto LABEL_34;
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = CopyDSToFQRegString(*(_QWORD *)a1, 0, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_33;
      v8 = 132;
      goto LABEL_31;
    }
  }
  else
  {
    v6 = 0;
  }
  v9 = *(unsigned __int16 **)(a1 + 8);
  if ( v9 )
  {
    v10 = IpsecAllocStr(v9);
    *(_QWORD *)(v5 + 8) = v10;
    if ( !v10 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_33;
      v8 = 133;
      goto LABEL_32;
    }
  }
  v12 = *(unsigned __int16 **)(a1 + 16);
  if ( v12 )
  {
    v13 = IpsecAllocStr(v12);
    *(_QWORD *)(v5 + 16) = v13;
    if ( !v13 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_33;
      v8 = 134;
      goto LABEL_32;
    }
  }
  *(_DWORD *)(v5 + 24) = *(_DWORD *)(a1 + 24);
  v14 = *(void **)(a1 + 32);
  if ( v14 && (v6 = CopyBinaryValue(v14, *(unsigned int *)(a1 + 40))) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_33;
    v8 = 135;
  }
  else
  {
    *(_DWORD *)(v5 + 40) = *(_DWORD *)(a1 + 40);
    v15 = *(_QWORD *)(a1 + 48);
    if ( !v15 || (v6 = CloneNFAReferencesDSToRegistry(v15, *(unsigned int *)(a1 + 56), v5 + 48, v5 + 56)) == 0 )
    {
      *(_DWORD *)(v5 + 60) = *(_DWORD *)(a1 + 60);
      *a2 = v5;
      return v6;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_33;
    v8 = 136;
  }
LABEL_31:
  v11 = v6;
LABEL_32:
  WPP_SF_d(v7[2], v8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v11);
LABEL_33:
  FreeIpsecISAKMPObject((LPVOID)v5);
LABEL_34:
  *a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x180035b50  push    rbx
0x180035b52  push    rsi
0x180035b53  push    rdi
0x180035b54  push    r14
0x180035b56  sub     rsp, 28h
0x180035b5a  mov     rbx, rcx
0x180035b5d  mov     r14, rdx
0x180035b60  mov     ecx, 40h ; '@'
0x180035b65  call    IpsecAllocMem
0x180035b6a  mov     rsi, rax
0x180035b6d  test    rax, rax
0x180035b70  jnz     short loc_180035BB3
0x180035b72  lea     r9d, [rax+0Eh]
0x180035b76  mov     edi, r9d
0x180035b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b80  lea     rax, WPP_GLOBAL_Control
0x180035b87  cmp     rcx, rax
0x180035b8a  jz      loc_180035D27
0x180035b90  test    byte ptr [rcx+1Ch], 10h
0x180035b94  jz      loc_180035D27
0x180035b9a  mov     rcx, [rcx+10h]
0x180035b9e  lea     edx, [r9+75h]
0x180035ba2  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180035ba9  call    WPP_SF_d
0x180035bae  jmp     loc_180035D27
0x180035bb3  mov     rcx, [rbx]
0x180035bb6  test    rcx, rcx
0x180035bb9  jz      short loc_180035BF6
0x180035bbb  mov     r8, rsi
0x180035bbe  xor     edx, edx
0x180035bc0  call    CopyDSToFQRegString
0x180035bc5  mov     edi, eax
0x180035bc7  test    eax, eax
0x180035bc9  jz      short loc_180035BF8
0x180035bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bd2  lea     rax, WPP_GLOBAL_Control
0x180035bd9  cmp     rcx, rax
0x180035bdc  jz      loc_180035D1F
0x180035be2  test    byte ptr [rcx+1Ch], 10h
0x180035be6  jz      loc_180035D1F
0x180035bec  mov     edx, 84h
0x180035bf1  jmp     loc_180035D0C
0x180035bf6  xor     edi, edi
0x180035bf8  mov     rcx, [rbx+8]; unsigned __int16 *
0x180035bfc  test    rcx, rcx
0x180035bff  jz      short loc_180035C40
0x180035c01  call    IpsecAllocStr
0x180035c06  mov     [rsi+8], rax
0x180035c0a  test    rax, rax
0x180035c0d  jnz     short loc_180035C40
0x180035c0f  lea     r9d, [rax+0Eh]
0x180035c13  mov     edi, r9d
0x180035c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c1d  lea     rax, WPP_GLOBAL_Control
0x180035c24  cmp     rcx, rax
0x180035c27  jz      loc_180035D1F
0x180035c2d  test    byte ptr [rcx+1Ch], 10h
0x180035c31  jz      loc_180035D1F
0x180035c37  lea     edx, [r9+77h]
0x180035c3b  jmp     loc_180035D0F
0x180035c40  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180035c44  test    rcx, rcx
0x180035c47  jz      short loc_180035C88
0x180035c49  call    IpsecAllocStr
0x180035c4e  mov     [rsi+10h], rax
0x180035c52  test    rax, rax
0x180035c55  jnz     short loc_180035C88
0x180035c57  lea     r9d, [rax+0Eh]
0x180035c5b  mov     edi, r9d
0x180035c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c65  lea     rax, WPP_GLOBAL_Control
0x180035c6c  cmp     rcx, rax
0x180035c6f  jz      loc_180035D1F
0x180035c75  test    byte ptr [rcx+1Ch], 10h
0x180035c79  jz      loc_180035D1F
0x180035c7f  lea     edx, [r9+78h]
0x180035c83  jmp     loc_180035D0F
0x180035c88  mov     eax, [rbx+18h]
0x180035c8b  mov     [rsi+18h], eax
0x180035c8e  mov     rcx, [rbx+20h]; Src
0x180035c92  test    rcx, rcx
0x180035c95  jz      short loc_180035CC9
0x180035c97  mov     edx, [rbx+28h]; Size
0x180035c9a  lea     r8, [rsi+20h]
0x180035c9e  call    CopyBinaryValue
0x180035ca3  mov     edi, eax
0x180035ca5  test    eax, eax
0x180035ca7  jz      short loc_180035CC9
0x180035ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cb0  lea     rax, WPP_GLOBAL_Control
0x180035cb7  cmp     rcx, rax
0x180035cba  jz      short loc_180035D1F
0x180035cbc  test    byte ptr [rcx+1Ch], 10h
0x180035cc0  jz      short loc_180035D1F
0x180035cc2  mov     edx, 87h
0x180035cc7  jmp     short loc_180035D0C
0x180035cc9  mov     eax, [rbx+28h]
0x180035ccc  mov     [rsi+28h], eax
0x180035ccf  mov     rcx, [rbx+30h]
0x180035cd3  test    rcx, rcx
0x180035cd6  jz      short loc_180035D30
0x180035cd8  mov     edx, [rbx+38h]
0x180035cdb  lea     r9, [rsi+38h]
0x180035cdf  lea     r8, [rsi+30h]
0x180035ce3  call    CloneNFAReferencesDSToRegistry
0x180035ce8  mov     edi, eax
0x180035cea  test    eax, eax
0x180035cec  jz      short loc_180035D30
0x180035cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cf5  lea     rax, WPP_GLOBAL_Control
0x180035cfc  cmp     rcx, rax
0x180035cff  jz      short loc_180035D1F
0x180035d01  test    byte ptr [rcx+1Ch], 10h
0x180035d05  jz      short loc_180035D1F
0x180035d07  mov     edx, 88h
0x180035d0c  mov     r9d, edi
0x180035d0f  mov     rcx, [rcx+10h]
0x180035d13  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180035d1a  call    WPP_SF_d
0x180035d1f  mov     rcx, rsi; lpMem
0x180035d22  call    FreeIpsecISAKMPObject
0x180035d27  mov     qword ptr [r14], 0
0x180035d2e  jmp     short loc_180035D39
0x180035d30  mov     eax, [rbx+3Ch]
0x180035d33  mov     [rsi+3Ch], eax
0x180035d36  mov     [r14], rsi
0x180035d39  mov     eax, edi
0x180035d3b  add     rsp, 28h
0x180035d3f  pop     r14
0x180035d41  pop     rdi
0x180035d42  pop     rsi
0x180035d43  pop     rbx
0x180035d44  retn
```
