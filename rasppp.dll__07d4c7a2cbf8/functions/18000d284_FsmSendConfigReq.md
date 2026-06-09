# FsmSendConfigReq

- ea: `0x18000d284`
- end: `0x18000d47a`
- name: `FsmSendConfigReq`
- size: `502`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c00`
- `0x180009eb0`
- `0x18000a0f0`
- `0x18000b170`
- `0x18000be0c`
- `0x18000c4ac`
- `0x18000c9a0`
- `0x180017650`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000ba40`
- `0x18000d284`
- `0x18000f334`
- `0x180011064`
- `0x1800111ac`
- `0x18001238c`
- `0x18001378c`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000d323`: `The control protocol for %x, returned error %d`
- `0x18000d370`: `while making a configure request on port %d`

## pseudocode

```c
__int64 __fastcall FsmSendConfigReq(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 PointerToCPCB; // rsi
  _BYTE *v5; // r15
  __int64 v6; // r14
  unsigned int v7; // eax
  __int64 v8; // r8
  _BYTE *v10; // rdx
  __int16 v11; // cx
  int v12; // ebx
  int v13; // r8d
  char *v14; // r9
  int v15; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v16[2044]; // [rsp+44h] [rbp-824h] BYREF

  v2 = (unsigned int)a2;
  v15 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v16, 0, sizeof(v16));
  if ( !PointerToCPCB )
    return 0;
  v5 = *(_BYTE **)(a1 + 40);
  v6 = 176 * v2;
  v7 = (*((__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))CpTable + 22 * v2 + 12))(
         *(_QWORD *)(PointerToCPCB + 16),
         v5 + 2,
         1498);
  if ( v7 )
  {
    *(_DWORD *)(PointerToCPCB + 40) = v7;
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v15,
        L"The control protocol for %x, returned error %d",
        *(unsigned int *)((char *)CpTable + v6),
        v7);
      if ( byte_18004CF33 < 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        if ( byte_18004CF33 < 0 )
        {
          v8 = *(_QWORD *)(a1 + 16);
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"while making a configure request on port %d", v8);
          if ( byte_18004CF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        }
      }
    }
    FsmClose(a1, (unsigned int)v2);
    return 0;
  }
  v10 = *(_BYTE **)(a1 + 40);
  v11 = *(_WORD *)((char *)CpTable + v6);
  v10[1] = v11;
  *v10 = HIBYTE(v11);
  v5[2] = 1;
  v5[3] = GetUId(a1, (unsigned int)v2);
  v12 = ((unsigned __int8)v5[4] << 8) + (unsigned __int8)v5[5];
  LogPPPPacket(0, a1, *(unsigned __int8 **)(a1 + 40), v12 + 2);
  if ( (unsigned int)PortSendOrDisconnect(a1, (unsigned int)(v12 + 2)) )
    return 0;
  v13 = (unsigned __int8)v5[3];
  v14 = (char *)CpTable;
  *(_DWORD *)(PointerToCPCB + 8) = v13;
  InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), v13, *(_DWORD *)&v14[v6], 0, 0, *(_DWORD *)(a1 + 36));
  return 1;
}

```

## disassembly

```asm
0x18000d284  mov     [rsp+arg_10], rbx
0x18000d289  mov     [rsp+arg_18], rsi
0x18000d28e  push    rdi
0x18000d28f  push    r14
0x18000d291  push    r15
0x18000d293  sub     rsp, 850h
0x18000d29a  mov     rax, cs:__security_cookie
0x18000d2a1  xor     rax, rsp
0x18000d2a4  mov     [rsp+868h+var_28], rax
0x18000d2ac  mov     ebx, edx
0x18000d2ae  mov     rdi, rcx
0x18000d2b1  call    GetPointerToCPCB
0x18000d2b6  xor     ecx, ecx
0x18000d2b8  xor     edx, edx; Val
0x18000d2ba  mov     [rsp+868h+var_828], ecx
0x18000d2be  mov     r8d, 7FCh; Size
0x18000d2c4  lea     rcx, [rsp+868h+var_824]; void *
0x18000d2c9  mov     rsi, rax
0x18000d2cc  call    memset_0
0x18000d2d1  test    rsi, rsi
0x18000d2d4  jz      loc_18000D3B3
0x18000d2da  mov     r15, [rdi+28h]
0x18000d2de  mov     r8d, 5DAh
0x18000d2e4  mov     rax, cs:CpTable
0x18000d2eb  mov     rcx, [rsi+10h]
0x18000d2ef  imul    r14, rbx, 0B0h
0x18000d2f6  lea     rdx, [r15+2]
0x18000d2fa  mov     rax, [r14+rax+60h]
0x18000d2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d304  test    eax, eax
0x18000d306  jz      loc_18000D3DE
0x18000d30c  mov     [rsi+28h], eax
0x18000d30f  cmp     cs:byte_18004CF33, 0
0x18000d316  jge     loc_18000D3A9
0x18000d31c  mov     r8, cs:CpTable
0x18000d323  lea     rdx, aTheControlProt_0; "The control protocol for %x, returned e"...
0x18000d32a  xor     ecx, ecx
0x18000d32c  mov     r9d, eax
0x18000d32f  mov     word ptr [rsp+868h+var_828], cx
0x18000d334  lea     rcx, [rsp+868h+var_828]
0x18000d339  mov     r8d, [r14+r8]
0x18000d33d  call    FormatRRASErrorString
0x18000d342  cmp     cs:byte_18004CF33, 0
0x18000d349  jge     short loc_18000D3A9
0x18000d34b  lea     r8, [rsp+868h+var_828]
0x18000d350  lea     rdx, RasPppTraceError
0x18000d357  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d35e  call    McTemplateU0z_EventWriteTransfer
0x18000d363  cmp     cs:byte_18004CF33, 0
0x18000d36a  jge     short loc_18000D3A9
0x18000d36c  mov     r8, [rdi+10h]
0x18000d370  lea     rdx, aWhileMakingACo; "while making a configure request on por"...
0x18000d377  xor     eax, eax
0x18000d379  lea     rcx, [rsp+868h+var_828]
0x18000d37e  mov     word ptr [rsp+868h+var_828], ax
0x18000d383  call    FormatRRASErrorString
0x18000d388  cmp     cs:byte_18004CF33, 0
0x18000d38f  jge     short loc_18000D3A9
0x18000d391  lea     r8, [rsp+868h+var_828]
0x18000d396  lea     rdx, RasPppTraceError
0x18000d39d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000d3a4  call    McTemplateU0z_EventWriteTransfer
0x18000d3a9  mov     edx, ebx
0x18000d3ab  mov     rcx, rdi
0x18000d3ae  call    FsmClose
0x18000d3b3  xor     eax, eax
0x18000d3b5  mov     rcx, [rsp+868h+var_28]
0x18000d3bd  xor     rcx, rsp; StackCookie
0x18000d3c0  call    __security_check_cookie
0x18000d3c5  lea     r11, [rsp+868h+var_18]
0x18000d3cd  mov     rbx, [r11+30h]
0x18000d3d1  mov     rsi, [r11+38h]
0x18000d3d5  mov     rsp, r11
0x18000d3d8  pop     r15
0x18000d3da  pop     r14
0x18000d3dc  pop     rdi
0x18000d3dd  retn
0x18000d3de  mov     rdx, [rdi+28h]
0x18000d3e2  mov     rax, cs:CpTable
0x18000d3e9  movzx   ecx, word ptr [r14+rax]
0x18000d3ee  mov     [rdx+1], cl
0x18000d3f1  movzx   eax, cx
0x18000d3f4  shr     ax, 8
0x18000d3f8  mov     rcx, rdi
0x18000d3fb  mov     [rdx], al
0x18000d3fd  mov     edx, ebx
0x18000d3ff  mov     byte ptr [r15+2], 1
0x18000d404  call    GetUId
0x18000d409  mov     [r15+3], al
0x18000d40d  mov     rdx, rdi
0x18000d410  movzx   ebx, byte ptr [r15+5]
0x18000d415  xor     ecx, ecx
0x18000d417  movzx   eax, byte ptr [r15+4]
0x18000d41c  mov     r8, [rdi+28h]
0x18000d420  shl     eax, 8
0x18000d423  add     ebx, eax
0x18000d425  lea     r9d, [rbx+2]
0x18000d429  call    LogPPPPacket
0x18000d42e  lea     edx, [rbx+2]
0x18000d431  mov     rcx, rdi
0x18000d434  call    PortSendOrDisconnect
0x18000d439  test    eax, eax
0x18000d43b  jnz     loc_18000D3B3
0x18000d441  movzx   r8d, byte ptr [r15+3]
0x18000d446  mov     r9, cs:CpTable
0x18000d44d  mov     [rsi+8], r8d
0x18000d451  mov     ecx, [rdi+24h]
0x18000d454  mov     rdx, [rdi+10h]
0x18000d458  mov     r9d, [r14+r9]
0x18000d45c  mov     [rsp+868h+var_838], ecx
0x18000d460  mov     ecx, [rdi+40h]
0x18000d463  mov     [rsp+868h+var_840], eax
0x18000d467  mov     [rsp+868h+var_848], eax
0x18000d46b  call    InsertInTimerQ
0x18000d470  mov     eax, 1
0x18000d475  jmp     loc_18000D3B5
```
