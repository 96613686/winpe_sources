# FsmConfigResultReceived

- ea: `0x1800096e8`
- end: `0x1800098f7`
- name: `FsmConfigResultReceived`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c00`
- `0x180009eb0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800096e8`
- `0x18000ba40`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180009824`: `The control protocol for %x on port %d returned error %d`

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
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v10 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        FormatRRASErrorString(&v15, L"Invalid packet received on port %d silently discarded", v10);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
      }
    }
    else
    {
      v12 = byte_18004CF34;
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v13 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"The control protocol for %x on port %d returned error %d",
          *(unsigned int *)((char *)CpTable + v7),
          v13,
          v8);
        v12 = byte_18004CF34;
        if ( (byte_18004CF34 & 1) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
          v12 = byte_18004CF34;
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
0x1800096e8  push    rbx
0x1800096ea  push    rbp
0x1800096eb  push    rsi
0x1800096ec  push    rdi
0x1800096ed  push    r14
0x1800096ef  sub     rsp, 850h
0x1800096f6  mov     rax, cs:__security_cookie
0x1800096fd  xor     rax, rsp
0x180009700  mov     [rsp+878h+var_38], rax
0x180009708  mov     rbx, r8
0x18000970b  mov     ebp, edx
0x18000970d  mov     rdi, rcx
0x180009710  call    GetPointerToCPCB
0x180009715  xor     ecx, ecx
0x180009717  xor     edx, edx; Val
0x180009719  mov     [rsp+878h+var_838], ecx
0x18000971d  mov     r8d, 7FCh; Size
0x180009723  lea     rcx, [rsp+878h+var_834]; void *
0x180009728  mov     r14, rax
0x18000972b  call    memset_0
0x180009730  test    r14, r14
0x180009733  jz      loc_1800097F2
0x180009739  movzx   edx, byte ptr [rbx]
0x18000973c  sub     edx, 2
0x18000973f  jz      short loc_18000977C
0x180009741  sub     edx, 1
0x180009744  jz      short loc_180009767
0x180009746  cmp     edx, 1
0x180009749  jnz     loc_1800097F2
0x18000974f  mov     rax, cs:CpTable
0x180009756  imul    rsi, rbp, 0B0h
0x18000975d  mov     rax, [rsi+rax+80h]
0x180009765  jmp     short loc_18000978F
0x180009767  mov     rax, cs:CpTable
0x18000976e  imul    rsi, rbp, 0B0h
0x180009775  mov     rax, [rsi+rax+78h]
0x18000977a  jmp     short loc_18000978F
0x18000977c  mov     rax, cs:CpTable
0x180009783  imul    rsi, rbp, 0B0h
0x18000978a  mov     rax, [rsi+rax+70h]
0x18000978f  mov     rcx, [r14+10h]
0x180009793  mov     rdx, rbx
0x180009796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979b  mov     ebx, eax
0x18000979d  test    eax, eax
0x18000979f  jz      loc_1800098ED
0x1800097a5  cmp     eax, 2D2h
0x1800097aa  jnz     short loc_180009812
0x1800097ac  test    cs:byte_18004CF34, 1
0x1800097b3  jz      short loc_1800097F2
0x1800097b5  mov     r8, [rdi+10h]
0x1800097b9  lea     rdx, aInvalidPacketR_0; "Invalid packet received on port %d sile"...
0x1800097c0  xor     eax, eax
0x1800097c2  lea     rcx, [rsp+878h+var_838]
0x1800097c7  mov     word ptr [rsp+878h+var_838], ax
0x1800097cc  call    FormatRRASErrorString
0x1800097d1  test    cs:byte_18004CF34, 1
0x1800097d8  jz      short loc_1800097F2
0x1800097da  lea     r8, [rsp+878h+var_838]
0x1800097df  lea     rdx, RasPppTraceInfo
0x1800097e6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800097ed  call    McTemplateU0z_EventWriteTransfer
0x1800097f2  xor     eax, eax
0x1800097f4  mov     rcx, [rsp+878h+var_38]
0x1800097fc  xor     rcx, rsp; StackCookie
0x1800097ff  call    __security_check_cookie
0x180009804  add     rsp, 850h
0x18000980b  pop     r14
0x18000980d  pop     rdi
0x18000980e  pop     rsi
0x18000980f  pop     rbp
0x180009810  pop     rbx
0x180009811  retn
0x180009812  mov     cl, cs:byte_18004CF34
0x180009818  test    cl, 1
0x18000981b  jz      short loc_180009871
0x18000981d  mov     r8, cs:CpTable
0x180009824  lea     rdx, aTheControlProt_1; "The control protocol for %x on port %d "...
0x18000982b  mov     r9, [rdi+10h]
0x18000982f  lea     rcx, [rsp+878h+var_838]
0x180009834  xor     eax, eax
0x180009836  mov     [rsp+878h+var_858], ebx
0x18000983a  mov     word ptr [rsp+878h+var_838], ax
0x18000983f  mov     r8d, [rsi+r8]
0x180009843  call    FormatRRASErrorString
0x180009848  mov     cl, cs:byte_18004CF34
0x18000984e  test    cl, 1
0x180009851  jz      short loc_180009871
0x180009853  lea     r8, [rsp+878h+var_838]
0x180009858  lea     rdx, RasPppTraceInfo
0x18000985f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009866  call    McTemplateU0z_EventWriteTransfer
0x18000986b  mov     cl, cs:byte_18004CF34
0x180009871  mov     rax, cs:CpTable
0x180009878  cmp     dword ptr [rsi+rax], 80FDh
0x18000987f  jnz     short loc_1800098DA
0x180009881  test    dword ptr [rdi+0B8h], 1080h
0x18000988b  jz      short loc_1800098DA
0x18000988d  test    cl, 1
0x180009890  jz      short loc_1800098AC
0x180009892  lea     r8, aEncryptionIsRe; "Encryption is required"
0x180009899  lea     rdx, RasPppTraceInfo
0x1800098a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800098a7  call    McTemplateU0z_EventWriteTransfer
0x1800098ac  mov     eax, ebx
0x1800098ae  sub     eax, 2DBh
0x1800098b3  jz      short loc_1800098C6
0x1800098b5  sub     eax, 0Ah
0x1800098b8  jz      short loc_1800098CB
0x1800098ba  cmp     eax, 1
0x1800098bd  jz      short loc_1800098CB
0x1800098bf  mov     ebx, 2E6h
0x1800098c4  jmp     short loc_1800098CB
0x1800098c6  mov     ebx, 2E5h
0x1800098cb  mov     [rdi+5D8h], ebx
0x1800098d1  bts     dword ptr [rdi+38h], 0Dh
0x1800098d6  xor     edx, edx
0x1800098d8  jmp     short loc_1800098E0
0x1800098da  mov     [r14+28h], ebx
0x1800098de  mov     edx, ebp
0x1800098e0  mov     rcx, rdi
0x1800098e3  call    FsmClose
0x1800098e8  jmp     loc_1800097F2
0x1800098ed  mov     eax, 1
0x1800098f2  jmp     loc_1800097F4
```
