# SdbGetTagDataSize

- ea: `0x1408c293c`
- end: `0x1408c2bad`
- name: `SdbGetTagDataSize`
- size: `625`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x14073810c`
- `0x140780648`
- `0x140822aec`
- `0x140824a04`
- `0x140827480`
- `0x140827828`
- `0x1408c0840`
- `0x1408c2180`
- `0x1408c2898`
- `0x140ac238c`
- `0x140ad111c`

## callees

- `0x14049d9e0`
- `0x1408c293c`
- `0x1408c2cbc`
- `0x1408c2d0c`
- `0x1408c2f88`

## string_xrefs

- `0x1408c29d8`: `Error reading size data [%x]`
- `0x1408c2b2c`: `Error reading size data [%x]`
- `0x1408c2aa5`: `Error reading size data`
- `0x1408c2b6f`: `Error reading size data`

## pseudocode

```c
__int64 __fastcall SdbGetTagDataSize(__int64 a1, int a2)
{
  int v4; // ebx
  __int64 result; // rax
  const char *v6; // r9
  int v7; // r8d
  unsigned int v8; // [rsp+58h] [rbp+28h] BYREF

  v8 = 0;
  v4 = SdbGetTagFromTagID() & 0xF000;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    switch ( v4 )
    {
      case 36864:
LABEL_3:
        v8 = 0;
        if ( !(unsigned int)SdbpReadMappedData(a1, a2 + 2, &v8, 4u) )
        {
          v8 = 0x20000000;
          AslLogCallPrintf(1, (unsigned int)"SdbGetTagDataSize", 311, (unsigned int)"Error reading size data [%x]");
        }
        result = v8;
        goto LABEL_6;
      case 16384:
        goto LABEL_13;
      case 12288:
        result = 2;
        break;
      case 20480:
        result = 8;
        break;
      case 24576:
LABEL_13:
        result = 4;
        break;
      case 4096:
        result = 0;
        break;
      case 8192:
        result = 1;
        break;
      case 28672:
      case 32768:
        goto LABEL_3;
      default:
        v6 = "Invalid TAG_TYPE encountered TAG: [0x%x]";
        v7 = 318;
LABEL_10:
        AslLogCallPrintf(1, (unsigned int)"SdbGetTagDataSize", v7, (_DWORD)v6);
        return 0x20000000;
    }
    v8 = result;
LABEL_6:
    if ( (int)result + a2 >= (unsigned int)result && (unsigned int)(result + a2) <= *(_DWORD *)(a1 + 20) )
      return result;
    v6 = "Error reading size data [%x]";
    v7 = 329;
    goto LABEL_10;
  }
  switch ( v4 )
  {
    case 24576:
      goto LABEL_26;
    case 12288:
      result = 2;
      goto LABEL_27;
    case 16384:
LABEL_26:
      result = 4;
LABEL_27:
      v8 = result;
      goto LABEL_28;
    case 4096:
      result = 0;
      goto LABEL_27;
    case 8192:
      result = 1;
      goto LABEL_27;
    case 20480:
      result = 8;
      goto LABEL_27;
  }
  v8 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, a2 + 2, &v8, 4u) )
    AslLogCallPrintf(1, (unsigned int)"SdbGetTagDataSize", 364, (unsigned int)"Error reading size data");
  result = v8;
LABEL_28:
  if ( (int)result + a2 < (unsigned int)result || (unsigned int)(result + a2) > *(_DWORD *)(a1 + 20) )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbGetTagDataSize", 375, (unsigned int)"Error reading size data");
    return 0x20000000;
  }
  return result;
}

```

## disassembly

```asm
0x1408c293c  mov     [rsp-18h+arg_0], rbx
0x1408c2941  mov     [rsp-18h+arg_10], rsi
0x1408c2946  push    rbp
0x1408c2947  push    r14
0x1408c2949  push    r15
0x1408c294b  mov     rbp, rsp
0x1408c294e  sub     rsp, 30h
0x1408c2952  mov     r14d, edx
0x1408c2955  mov     [rbp+arg_8], 0
0x1408c295c  mov     rsi, rcx
0x1408c295f  call    SdbGetTagFromTagID
0x1408c2964  movzx   r15d, ax
0x1408c2968  mov     ebx, r15d
0x1408c296b  and     ebx, 0F000h
0x1408c2971  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1408c2976  test    eax, eax
0x1408c2978  jz      loc_1408C2A22
0x1408c297e  cmp     ebx, 9000h
0x1408c2984  jnz     short loc_1408C29FD
0x1408c2986  lea     edx, [r14+2]
0x1408c298a  mov     [rbp+arg_8], 0
0x1408c2991  mov     r9d, 4
0x1408c2997  lea     r8, [rbp+arg_8]
0x1408c299b  mov     rcx, rsi
0x1408c299e  call    SdbpReadMappedData
0x1408c29a3  test    eax, eax
0x1408c29a5  jz      loc_1408C2B2C
0x1408c29ab  mov     eax, [rbp+arg_8]
0x1408c29ae  lea     ecx, [rax+r14]
0x1408c29b2  cmp     ecx, eax
0x1408c29b4  jb      short loc_1408C29D0
0x1408c29b6  cmp     ecx, [rsi+14h]
0x1408c29b9  ja      short loc_1408C29D0
0x1408c29bb  mov     rbx, [rsp+30h+arg_0]
0x1408c29c0  mov     rsi, [rsp+30h+arg_10]
0x1408c29c5  add     rsp, 30h
0x1408c29c9  pop     r15
0x1408c29cb  pop     r14
0x1408c29cd  pop     rbp
0x1408c29ce  retn
0x1408c29d0  mov     [rsp+30h+var_10], 0C0000095h
0x1408c29d8  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x1408c29df  mov     r8d, 149h
0x1408c29e5  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x1408c29ec  mov     ecx, 1
0x1408c29f1  call    AslLogCallPrintf
0x1408c29f6  mov     eax, 20000000h
0x1408c29fb  jmp     short loc_1408C29BB
0x1408c29fd  cmp     ebx, 4000h
0x1408c2a03  jnz     short loc_1408C2A0F
0x1408c2a05  mov     eax, 4
0x1408c2a0a  mov     [rbp+arg_8], eax
0x1408c2a0d  jmp     short loc_1408C29AE
0x1408c2a0f  cmp     ebx, 3000h
0x1408c2a15  jnz     loc_1408C2ACF
0x1408c2a1b  mov     eax, 2
0x1408c2a20  jmp     short loc_1408C2A0A
0x1408c2a22  cmp     ebx, 6000h
0x1408c2a28  jz      short loc_1408C2A8C
0x1408c2a2a  cmp     ebx, 3000h
0x1408c2a30  jz      loc_1408C2AC8
0x1408c2a36  cmp     ebx, 4000h
0x1408c2a3c  jz      short loc_1408C2A8C
0x1408c2a3e  cmp     ebx, 1000h
0x1408c2a44  jz      loc_1408C2BA6
0x1408c2a4a  cmp     ebx, 2000h
0x1408c2a50  jz      loc_1408C2B9C
0x1408c2a56  cmp     ebx, 5000h
0x1408c2a5c  jz      loc_1408C2B92
0x1408c2a62  lea     edx, [r14+2]
0x1408c2a66  mov     [rbp+arg_8], 0
0x1408c2a6d  mov     r9d, 4
0x1408c2a73  lea     r8, [rbp+arg_8]
0x1408c2a77  mov     rcx, rsi
0x1408c2a7a  call    SdbpReadMappedData
0x1408c2a7f  test    eax, eax
0x1408c2a81  jz      loc_1408C2B6F
0x1408c2a87  mov     eax, [rbp+arg_8]
0x1408c2a8a  jmp     short loc_1408C2A94
0x1408c2a8c  mov     eax, 4
0x1408c2a91  mov     [rbp+arg_8], eax
0x1408c2a94  lea     ecx, [rax+r14]
0x1408c2a98  cmp     ecx, eax
0x1408c2a9a  jb      short loc_1408C2AA5
0x1408c2a9c  cmp     ecx, [rsi+14h]
0x1408c2a9f  jbe     loc_1408C29BB
0x1408c2aa5  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x1408c2aac  mov     r8d, 177h
0x1408c2ab2  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x1408c2ab9  mov     ecx, 1
0x1408c2abe  call    AslLogCallPrintf
0x1408c2ac3  jmp     loc_1408C29F6
0x1408c2ac8  mov     eax, 2
0x1408c2acd  jmp     short loc_1408C2A91
0x1408c2acf  cmp     ebx, 5000h
0x1408c2ad5  jnz     short loc_1408C2AE1
0x1408c2ad7  mov     eax, 8
0x1408c2adc  jmp     loc_1408C2A0A
0x1408c2ae1  cmp     ebx, 6000h
0x1408c2ae7  jz      loc_1408C2A05
0x1408c2aed  cmp     ebx, 1000h
0x1408c2af3  jz      short loc_1408C2B68
0x1408c2af5  cmp     ebx, 2000h
0x1408c2afb  jz      short loc_1408C2B5E
0x1408c2afd  cmp     ebx, 7000h
0x1408c2b03  jz      loc_1408C2986
0x1408c2b09  cmp     ebx, 8000h
0x1408c2b0f  jz      loc_1408C2986
0x1408c2b15  mov     [rsp+30h+var_10], r15d
0x1408c2b1a  lea     r9, aInvalidTagType_0; "Invalid TAG_TYPE encountered TAG: [0x%x"...
0x1408c2b21  mov     r8d, 13Eh
0x1408c2b27  jmp     loc_1408C29E5
0x1408c2b2c  lea     r9, aErrorReadingSi; "Error reading size data [%x]"
0x1408c2b33  mov     [rbp+arg_8], 20000000h
0x1408c2b3a  mov     r8d, 137h
0x1408c2b40  mov     [rsp+30h+var_10], 0C0000023h
0x1408c2b48  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x1408c2b4f  mov     ecx, 1
0x1408c2b54  call    AslLogCallPrintf
0x1408c2b59  jmp     loc_1408C29AB
0x1408c2b5e  mov     eax, 1
0x1408c2b63  jmp     loc_1408C2A0A
0x1408c2b68  xor     eax, eax
0x1408c2b6a  jmp     loc_1408C2A0A
0x1408c2b6f  lea     r9, aErrorReadingSi_0; "Error reading size data"
0x1408c2b76  mov     r8d, 16Ch
0x1408c2b7c  lea     rdx, aSdbgettagdatas; "SdbGetTagDataSize"
0x1408c2b83  mov     ecx, 1
0x1408c2b88  call    AslLogCallPrintf
0x1408c2b8d  jmp     loc_1408C2A87
0x1408c2b92  mov     eax, 8
0x1408c2b97  jmp     loc_1408C2A91
0x1408c2b9c  mov     eax, 1
0x1408c2ba1  jmp     loc_1408C2A91
0x1408c2ba6  xor     eax, eax
0x1408c2ba8  jmp     loc_1408C2A91
```
