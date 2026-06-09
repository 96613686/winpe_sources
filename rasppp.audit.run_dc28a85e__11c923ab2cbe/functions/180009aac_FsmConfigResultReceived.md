# FsmConfigResultReceived

- ea: `0x180009aac`
- end: `0x180009cbc`
- name: `FsmConfigResultReceived`
- size: `528`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009fd0`
- `0x18000a280`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180009aac`
- `0x18000be68`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180009be9`: `The control protocol for %x on port %d returned error %d`

## pseudocode

```c
__int64 __fastcall FsmConfigResultReceived(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v4; // rbp
  __int64 PointerToCPCB; // r14
  __int64 v7; // rsi
  int v8; // eax
  int v9; // ebx
  __int64 v10; // r8
  char v12; // cl
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v16[2044]; // [rsp+44h] [rbp-834h] BYREF

  v4 = (unsigned int)a2;
  v15 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v16, 0, sizeof(v16));
  if ( !PointerToCPCB )
    return 0;
  switch ( *a3 )
  {
    case 2:
      v7 = 176 * v4;
      v8 = (*((__int64 (__fastcall **)(_QWORD, _BYTE *))CpTable + 22 * v4 + 14))(*(_QWORD *)(PointerToCPCB + 16), a3);
      break;
    case 3:
      v7 = 176 * v4;
      v8 = (*((__int64 (__fastcall **)(_QWORD, _BYTE *))CpTable + 22 * v4 + 15))(*(_QWORD *)(PointerToCPCB + 16), a3);
      break;
    case 4:
      v7 = 176 * v4;
      v8 = (*((__int64 (__fastcall **)(_QWORD, _BYTE *))CpTable + 22 * v4 + 16))(*(_QWORD *)(PointerToCPCB + 16), a3);
      break;
    default:
      return 0;
  }
  v9 = v8;
  if ( v8 )
  {
    if ( v8 == 722 )
    {
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v10 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"Invalid packet received on port %d silently discarded", v10);
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
      }
    }
    else
    {
      v12 = byte_18004DF34;
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v13 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"The control protocol for %x on port %d returned error %d",
          *(unsigned int *)((char *)CpTable + v7),
          v13,
          v8);
        v12 = byte_18004DF34;
        if ( (byte_18004DF34 & 1) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
          v12 = byte_18004DF34;
        }
      }
      if ( *(_DWORD *)((char *)CpTable + v7) == 33021 && (*(_DWORD *)(a1 + 184) & 0x1080) != 0 )
      {
        if ( (v12 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"Encryption is required");
        if ( v9 == 731 )
        {
          v9 = 741;
        }
        else if ( (unsigned int)(v9 - 741) >= 2 )
        {
          v9 = 742;
        }
        *(_DWORD *)(a1 + 1496) = v9;
        *(_DWORD *)(a1 + 56) |= 0x2000u;
        v14 = 0;
      }
      else
      {
        *(_DWORD *)(PointerToCPCB + 40) = v9;
        v14 = (unsigned int)v4;
      }
      FsmClose(a1, v14);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180009aac  push    rbx
0x180009aae  push    rbp
0x180009aaf  push    rsi
0x180009ab0  push    rdi
0x180009ab1  push    r14
0x180009ab3  sub     rsp, 850h
0x180009aba  mov     rax, cs:__security_cookie
0x180009ac1  xor     rax, rsp
0x180009ac4  mov     [rsp+878h+var_38], rax
0x180009acc  mov     rbx, r8
0x180009acf  mov     ebp, edx
0x180009ad1  mov     rdi, rcx
0x180009ad4  call    GetPointerToCPCB
0x180009ad9  xor     ecx, ecx
0x180009adb  xor     edx, edx; Val
0x180009add  mov     [rsp+878h+var_838], ecx
0x180009ae1  mov     r8d, 7FCh; Size
0x180009ae7  lea     rcx, [rsp+878h+var_834]; void *
0x180009aec  mov     r14, rax
0x180009aef  call    memset_0
0x180009af4  test    r14, r14
0x180009af7  jz      loc_180009BB6
0x180009afd  movzx   edx, byte ptr [rbx]
0x180009b00  sub     edx, 2
0x180009b03  jz      short loc_180009B40
0x180009b05  sub     edx, 1
0x180009b08  jz      short loc_180009B2B
0x180009b0a  cmp     edx, 1
0x180009b0d  jnz     loc_180009BB6
0x180009b13  mov     rax, cs:CpTable
0x180009b1a  imul    rsi, rbp, 0B0h
0x180009b21  mov     rax, [rsi+rax+80h]
0x180009b29  jmp     short loc_180009B53
0x180009b2b  mov     rax, cs:CpTable
0x180009b32  imul    rsi, rbp, 0B0h
0x180009b39  mov     rax, [rsi+rax+78h]
0x180009b3e  jmp     short loc_180009B53
0x180009b40  mov     rax, cs:CpTable
0x180009b47  imul    rsi, rbp, 0B0h
0x180009b4e  mov     rax, [rsi+rax+70h]
0x180009b53  mov     rcx, [r14+10h]
0x180009b57  mov     rdx, rbx
0x180009b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5f  mov     ebx, eax
0x180009b61  test    eax, eax
0x180009b63  jz      loc_180009CB2
0x180009b69  cmp     eax, 2D2h
0x180009b6e  jnz     short loc_180009BD7
0x180009b70  test    cs:byte_18004DF34, 1
0x180009b77  jz      short loc_180009BB6
0x180009b79  mov     r8, [rdi+10h]
0x180009b7d  lea     rdx, aInvalidPacketR_0; "Invalid packet received on port %d sile"...
0x180009b84  xor     eax, eax
0x180009b86  lea     rcx, [rsp+878h+var_838]
0x180009b8b  mov     word ptr [rsp+878h+var_838], ax
0x180009b90  call    FormatRRASErrorString
0x180009b95  test    cs:byte_18004DF34, 1
0x180009b9c  jz      short loc_180009BB6
0x180009b9e  lea     r8, [rsp+878h+var_838]
0x180009ba3  lea     rdx, RasPppTraceInfo
0x180009baa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009bb1  call    McTemplateU0z_EventWriteTransfer
0x180009bb6  xor     eax, eax
0x180009bb8  mov     rcx, [rsp+878h+var_38]
0x180009bc0  xor     rcx, rsp; StackCookie
0x180009bc3  call    __security_check_cookie
0x180009bc8  add     rsp, 850h
0x180009bcf  pop     r14
0x180009bd1  pop     rdi
0x180009bd2  pop     rsi
0x180009bd3  pop     rbp
0x180009bd4  pop     rbx
0x180009bd5  retn
0x180009bd7  mov     cl, cs:byte_18004DF34
0x180009bdd  test    cl, 1
0x180009be0  jz      short loc_180009C36
0x180009be2  mov     r8, cs:CpTable
0x180009be9  lea     rdx, aTheControlProt_1; "The control protocol for %x on port %d "...
0x180009bf0  mov     r9, [rdi+10h]
0x180009bf4  lea     rcx, [rsp+878h+var_838]
0x180009bf9  xor     eax, eax
0x180009bfb  mov     [rsp+878h+var_858], ebx
0x180009bff  mov     word ptr [rsp+878h+var_838], ax
0x180009c04  mov     r8d, [rsi+r8]
0x180009c08  call    FormatRRASErrorString
0x180009c0d  mov     cl, cs:byte_18004DF34
0x180009c13  test    cl, 1
0x180009c16  jz      short loc_180009C36
0x180009c18  lea     r8, [rsp+878h+var_838]
0x180009c1d  lea     rdx, RasPppTraceInfo
0x180009c24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009c2b  call    McTemplateU0z_EventWriteTransfer
0x180009c30  mov     cl, cs:byte_18004DF34
0x180009c36  mov     rax, cs:CpTable
0x180009c3d  cmp     dword ptr [rsi+rax], 80FDh
0x180009c44  jnz     short loc_180009C9F
0x180009c46  test    dword ptr [rdi+0B8h], 1080h
0x180009c50  jz      short loc_180009C9F
0x180009c52  test    cl, 1
0x180009c55  jz      short loc_180009C71
0x180009c57  lea     r8, aEncryptionIsRe; "Encryption is required"
0x180009c5e  lea     rdx, RasPppTraceInfo
0x180009c65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009c6c  call    McTemplateU0z_EventWriteTransfer
0x180009c71  mov     eax, ebx
0x180009c73  sub     eax, 2DBh
0x180009c78  jz      short loc_180009C8B
0x180009c7a  sub     eax, 0Ah
0x180009c7d  jz      short loc_180009C90
0x180009c7f  cmp     eax, 1
0x180009c82  jz      short loc_180009C90
0x180009c84  mov     ebx, 2E6h
0x180009c89  jmp     short loc_180009C90
0x180009c8b  mov     ebx, 2E5h
0x180009c90  mov     [rdi+5D8h], ebx
0x180009c96  bts     dword ptr [rdi+38h], 0Dh
0x180009c9b  xor     edx, edx
0x180009c9d  jmp     short loc_180009CA5
0x180009c9f  mov     [r14+28h], ebx
0x180009ca3  mov     edx, ebp
0x180009ca5  mov     rcx, rdi
0x180009ca8  call    FsmClose
0x180009cad  jmp     loc_180009BB6
0x180009cb2  mov     eax, 1
0x180009cb7  jmp     loc_180009BB8
```
