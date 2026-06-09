# CloneNFAReferencesDSToRegistry

- ea: `0x180036a94`
- end: `0x180036bc8`
- name: `CloneNFAReferencesDSToRegistry`
- size: `308`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800357c4`
- `0x180035b50`
- `0x1800362ac`
- `0x1800366c4`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x180036a94`
- `0x180036c54`
- `0x180042ab0`
- `0x180042ef8`

## pseudocode

```c
__int64 __fastcall CloneNFAReferencesDSToRegistry(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char *v13; // rsi
  __int64 i; // rdi
  unsigned int v15; // eax
  __int64 result; // rax
  _QWORD v17[9]; // [rsp+20h] [rbp-48h] BYREF

  v17[0] = 0;
  v8 = NsuSizeTMultiply(a2, 8, v17);
  v9 = v8;
  if ( v8 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v11 = 137;
    v12 = v8;
    goto LABEL_5;
  }
  v13 = (char *)IpsecAllocMem(v17[0]);
  if ( !v13 )
  {
    v9 = 14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v11 = 138;
    v12 = 14;
LABEL_5:
    WPP_SF_d(v10[2], v11, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v12);
    goto LABEL_18;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 )
    {
      *a3 = v13;
      result = 0;
      *a4 = a2;
      return result;
    }
    v15 = CopyDSToFQRegString(*(_QWORD *)(a1 + 8 * i), 1, &v13[8 * i]);
    v9 = v15;
    if ( v15 )
      break;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v15);
  FreeNFAReferences(v13);
LABEL_18:
  *a3 = 0;
  result = v9;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x180036a94  push    rbx
0x180036a96  push    rbp
0x180036a97  push    rsi
0x180036a98  push    rdi
0x180036a99  push    r12
0x180036a9b  push    r14
0x180036a9d  push    r15
0x180036a9f  sub     rsp, 30h
0x180036aa3  mov     ebp, edx
0x180036aa5  mov     r12, rcx
0x180036aa8  mov     ecx, edx
0x180036aaa  mov     r15, r8
0x180036aad  mov     edx, 8
0x180036ab2  mov     [rsp+68h+var_48], 0
0x180036abb  lea     r8, [rsp+68h+var_48]
0x180036ac0  mov     r14, r9
0x180036ac3  call    NsuSizeTMultiply
0x180036ac8  mov     ebx, eax
0x180036aca  test    eax, eax
0x180036acc  jz      short loc_180036B0C
0x180036ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ad5  lea     rdx, WPP_GLOBAL_Control
0x180036adc  cmp     rcx, rdx
0x180036adf  jz      loc_180036B9F
0x180036ae5  test    byte ptr [rcx+1Ch], 10h
0x180036ae9  jz      loc_180036B9F
0x180036aef  mov     edx, 89h
0x180036af4  mov     r9d, eax
0x180036af7  mov     rcx, [rcx+10h]
0x180036afb  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036b02  call    WPP_SF_d
0x180036b07  jmp     loc_180036B9F
0x180036b0c  mov     rcx, [rsp+68h+var_48]
0x180036b11  call    IpsecAllocMem
0x180036b16  mov     rsi, rax
0x180036b19  test    rax, rax
0x180036b1c  jnz     short loc_180036B42
0x180036b1e  lea     ebx, [rax+0Eh]
0x180036b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b28  lea     rdx, WPP_GLOBAL_Control
0x180036b2f  cmp     rcx, rdx
0x180036b32  jz      short loc_180036B9F
0x180036b34  test    byte ptr [rcx+1Ch], 10h
0x180036b38  jz      short loc_180036B9F
0x180036b3a  lea     edx, [rbx+7Ch]
0x180036b3d  mov     r9d, ebx
0x180036b40  jmp     short loc_180036AF7
0x180036b42  xor     edi, edi
0x180036b44  cmp     edi, ebp
0x180036b46  jnb     short loc_180036BB1
0x180036b48  mov     rcx, [r12+rdi*8]
0x180036b4c  lea     r8, [rsi+rdi*8]
0x180036b50  mov     edx, 1
0x180036b55  call    CopyDSToFQRegString
0x180036b5a  mov     ebx, eax
0x180036b5c  test    eax, eax
0x180036b5e  jnz     short loc_180036B64
0x180036b60  inc     edi
0x180036b62  jmp     short loc_180036B44
0x180036b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b6b  lea     rdx, WPP_GLOBAL_Control
0x180036b72  cmp     rcx, rdx
0x180036b75  jz      short loc_180036B95
0x180036b77  test    byte ptr [rcx+1Ch], 10h
0x180036b7b  jz      short loc_180036B95
0x180036b7d  mov     rcx, [rcx+10h]
0x180036b81  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036b88  mov     edx, 8Bh
0x180036b8d  mov     r9d, eax
0x180036b90  call    WPP_SF_d
0x180036b95  mov     edx, edi
0x180036b97  mov     rcx, rsi; lpMem
0x180036b9a  call    FreeNFAReferences
0x180036b9f  mov     qword ptr [r15], 0
0x180036ba6  mov     eax, ebx
0x180036ba8  mov     dword ptr [r14], 0
0x180036baf  jmp     short loc_180036BB9
0x180036bb1  mov     [r15], rsi
0x180036bb4  xor     eax, eax
0x180036bb6  mov     [r14], ebp
0x180036bb9  add     rsp, 30h
0x180036bbd  pop     r15
0x180036bbf  pop     r14
0x180036bc1  pop     r12
0x180036bc3  pop     rdi
0x180036bc4  pop     rsi
0x180036bc5  pop     rbp
0x180036bc6  pop     rbx
0x180036bc7  retn
```
