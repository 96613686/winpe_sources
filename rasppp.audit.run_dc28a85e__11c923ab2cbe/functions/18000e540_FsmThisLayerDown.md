# FsmThisLayerDown

- ea: `0x18000e540`
- end: `0x18000e79e`
- name: `FsmThisLayerDown`
- size: `606`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009cd0`
- `0x180009fd0`
- `0x18000a280`
- `0x18000a4c0`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000be68`
- `0x18000c050`
- `0x180017e60`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800022e4`
- `0x180003170`
- `0x1800043a8`
- `0x18000c050`
- `0x18000e540`
- `0x18000f984`
- `0x180011230`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18000e5ad`: `FsmThisLayerDown called for protocol = %x, port = %d`
- `0x18000e62c`: `FsmThisLayerDown for protocol=%x,port=%d,RetCode=%d`

## pseudocode

```c
__int64 __fastcall FsmThisLayerDown(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 PointerToCPCB; // rdi
  __int64 v6; // r9
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(_QWORD); // rax
  int v9; // eax
  int v10; // ebp
  __int64 v11; // r9
  int v12; // r8d
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned int v15; // r9d
  __int64 v16; // rdi
  unsigned int CpIndexFromProtocol; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v21[2044]; // [rsp+34h] [rbp-834h] BYREF

  v2 = (unsigned int)a2;
  v20 = 0;
  PointerToCPCB = GetPointerToCPCB(a1, a2);
  memset_0(v21, 0, sizeof(v21));
  if ( !PointerToCPCB )
    return 0;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v20) = 0;
    FormatRRASErrorString(
      &v20,
      L"FsmThisLayerDown called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v20);
  }
  v7 = 176 * v2;
  v8 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)CpTable + 22 * v2 + 10);
  if ( v8 )
  {
    v9 = v8(*(_QWORD *)(PointerToCPCB + 16));
    v10 = v9;
    if ( v9 )
    {
      if ( byte_18004DF33 < 0 )
      {
        v11 = *(_QWORD *)(a1 + 16);
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          &v20,
          L"FsmThisLayerDown for protocol=%x,port=%d,RetCode=%d",
          *(unsigned int *)((char *)CpTable + v7),
          v11,
          v9);
        if ( byte_18004DF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v20);
      }
      if ( *(_DWORD *)(PointerToCPCB + 40) )
        *(_DWORD *)(PointerToCPCB + 40) = v10;
    }
  }
  if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
  {
    v12 = *(_DWORD *)((char *)CpTable + v7);
    if ( v12 == 32855 || v12 == 32801 )
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), *(_DWORD *)(PointerToCPCB + 8), v12, 0, 8);
  }
  if ( (_DWORD)v2 )
  {
    *(_DWORD *)(PointerToCPCB + 56) = 1;
  }
  else
  {
    if ( (*(_BYTE *)(a1 + 56) & 2) == 0 || *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL) == 1 )
    {
      v13 = 1;
      if ( (unsigned int)PppConfigInfo > 1 )
      {
        do
        {
          v14 = GetPointerToCPCB(a1, v13);
          if ( v14 && *(_DWORD *)(v14 + 44) )
          {
            FsmDown(a1, v13);
            v15 = PppConfigInfo;
          }
          ++v13;
        }
        while ( v13 < v15 );
      }
    }
    v16 = *(_QWORD *)(a1 + 1472);
    *(_DWORD *)(a1 + 48) = 0;
    CpIndexFromProtocol = GetCpIndexFromProtocol(*(unsigned int *)(v16 + 1220));
    if ( CpIndexFromProtocol != -1 )
    {
      ApStop(a1, CpIndexFromProtocol, 1);
      *(_DWORD *)(a1 + 116) = -1;
    }
    v18 = GetCpIndexFromProtocol(*(unsigned int *)(v16 + 1420));
    if ( v18 != -1 )
      ApStop(a1, v18, 0);
    v19 = GetCpIndexFromProtocol(49193);
    if ( v19 != -1 )
      CbStop(a1, v19);
  }
  return 1;
}

```

## disassembly

```asm
0x18000e540  mov     [rsp+arg_10], rbx
0x18000e545  push    rbp
0x18000e546  push    rsi
0x18000e547  push    rdi
0x18000e548  push    r14
0x18000e54a  push    r15
0x18000e54c  sub     rsp, 840h
0x18000e553  mov     rax, cs:__security_cookie
0x18000e55a  xor     rax, rsp
0x18000e55d  mov     [rsp+868h+var_38], rax
0x18000e565  mov     r14d, edx
0x18000e568  mov     rbx, rcx
0x18000e56b  call    GetPointerToCPCB
0x18000e570  xor     ecx, ecx
0x18000e572  xor     edx, edx; Val
0x18000e574  mov     [rsp+868h+var_838], ecx
0x18000e578  mov     r8d, 7FCh; Size
0x18000e57e  lea     rcx, [rsp+868h+var_834]; void *
0x18000e583  mov     rdi, rax
0x18000e586  call    memset_0
0x18000e58b  test    rdi, rdi
0x18000e58e  jnz     short loc_18000E597
0x18000e590  xor     eax, eax
0x18000e592  jmp     loc_18000E776
0x18000e597  mov     r15d, 1
0x18000e59d  test    cs:byte_18004DF34, r15b
0x18000e5a4  jz      short loc_18000E5F5
0x18000e5a6  mov     r8, cs:CpTable
0x18000e5ad  lea     rdx, aFsmthislayerdo_0; "FsmThisLayerDown called for protocol = "...
0x18000e5b4  mov     r9, [rbx+10h]
0x18000e5b8  xor     eax, eax
0x18000e5ba  imul    rcx, r14, 0B0h
0x18000e5c1  mov     word ptr [rsp+868h+var_838], ax
0x18000e5c6  mov     r8d, [rcx+r8]
0x18000e5ca  lea     rcx, [rsp+868h+var_838]
0x18000e5cf  call    FormatRRASErrorString
0x18000e5d4  test    cs:byte_18004DF34, r15b
0x18000e5db  jz      short loc_18000E5F5
0x18000e5dd  lea     r8, [rsp+868h+var_838]
0x18000e5e2  lea     rdx, RasPppTraceInfo
0x18000e5e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e5f0  call    McTemplateU0z_EventWriteTransfer
0x18000e5f5  mov     rax, cs:CpTable
0x18000e5fc  imul    rsi, r14, 0B0h
0x18000e603  mov     rax, [rsi+rax+50h]
0x18000e608  test    rax, rax
0x18000e60b  jz      short loc_18000E67A
0x18000e60d  mov     rcx, [rdi+10h]
0x18000e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e616  mov     ebp, eax
0x18000e618  test    eax, eax
0x18000e61a  jz      short loc_18000E67A
0x18000e61c  cmp     cs:byte_18004DF33, 0
0x18000e623  jge     short loc_18000E671
0x18000e625  mov     r8, cs:CpTable
0x18000e62c  lea     rdx, aFsmthislayerdo; "FsmThisLayerDown for protocol=%x,port=%"...
0x18000e633  mov     r9, [rbx+10h]
0x18000e637  xor     ecx, ecx
0x18000e639  mov     word ptr [rsp+868h+var_838], cx
0x18000e63e  lea     rcx, [rsp+868h+var_838]
0x18000e643  mov     [rsp+868h+var_848], eax
0x18000e647  mov     r8d, [rsi+r8]
0x18000e64b  call    FormatRRASErrorString
0x18000e650  cmp     cs:byte_18004DF33, 0
0x18000e657  jge     short loc_18000E671
0x18000e659  lea     r8, [rsp+868h+var_838]
0x18000e65e  lea     rdx, RasPppTraceError
0x18000e665  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e66c  call    McTemplateU0z_EventWriteTransfer
0x18000e671  cmp     dword ptr [rdi+28h], 0
0x18000e675  jz      short loc_18000E67A
0x18000e677  mov     [rdi+28h], ebp
0x18000e67a  test    byte ptr [rbx+38h], 4
0x18000e67e  jnz     short loc_18000E6B3
0x18000e680  mov     rax, cs:CpTable
0x18000e687  mov     r8d, [rsi+rax]
0x18000e68b  cmp     r8d, 8057h
0x18000e692  jz      short loc_18000E69D
0x18000e694  cmp     r8d, 8021h
0x18000e69b  jnz     short loc_18000E6B3
0x18000e69d  mov     edx, [rdi+8]
0x18000e6a0  xor     r9d, r9d
0x18000e6a3  mov     ecx, [rbx+40h]
0x18000e6a6  mov     [rsp+868h+var_848], 8
0x18000e6ae  call    RemoveFromTimerQ
0x18000e6b3  test    r14d, r14d
0x18000e6b6  jnz     loc_18000E76F
0x18000e6bc  test    byte ptr [rbx+38h], 2
0x18000e6c0  jz      short loc_18000E6CC
0x18000e6c2  mov     rax, [rbx+8]
0x18000e6c6  cmp     [rax+10h], r15d
0x18000e6ca  jnz     short loc_18000E709
0x18000e6cc  mov     r9d, dword ptr cs:PppConfigInfo
0x18000e6d3  mov     edi, r15d
0x18000e6d6  cmp     r9d, r15d
0x18000e6d9  jbe     short loc_18000E709
0x18000e6db  mov     edx, edi
0x18000e6dd  mov     rcx, rbx
0x18000e6e0  call    GetPointerToCPCB
0x18000e6e5  test    rax, rax
0x18000e6e8  jz      short loc_18000E701
0x18000e6ea  cmp     dword ptr [rax+2Ch], 0
0x18000e6ee  jz      short loc_18000E701
0x18000e6f0  mov     edx, edi
0x18000e6f2  mov     rcx, rbx
0x18000e6f5  call    FsmDown
0x18000e6fa  mov     r9d, dword ptr cs:PppConfigInfo
0x18000e701  add     edi, r15d
0x18000e704  cmp     edi, r9d
0x18000e707  jb      short loc_18000E6DB
0x18000e709  mov     rdi, [rbx+5C0h]
0x18000e710  mov     dword ptr [rbx+30h], 0
0x18000e717  mov     ecx, [rdi+4C4h]
0x18000e71d  call    GetCpIndexFromProtocol
0x18000e722  or      esi, 0FFFFFFFFh
0x18000e725  cmp     eax, esi
0x18000e727  jz      short loc_18000E739
0x18000e729  mov     r8d, r15d
0x18000e72c  mov     edx, eax
0x18000e72e  mov     rcx, rbx
0x18000e731  call    ApStop
0x18000e736  mov     [rbx+74h], esi
0x18000e739  mov     ecx, [rdi+58Ch]
0x18000e73f  call    GetCpIndexFromProtocol
0x18000e744  cmp     eax, esi
0x18000e746  jz      short loc_18000E755
0x18000e748  xor     r8d, r8d
0x18000e74b  mov     edx, eax
0x18000e74d  mov     rcx, rbx
0x18000e750  call    ApStop
0x18000e755  mov     ecx, 0C029h
0x18000e75a  call    GetCpIndexFromProtocol
0x18000e75f  cmp     eax, esi
0x18000e761  jz      short loc_18000E773
0x18000e763  mov     edx, eax
0x18000e765  mov     rcx, rbx
0x18000e768  call    CbStop
0x18000e76d  jmp     short loc_18000E773
0x18000e76f  mov     [rdi+38h], r15d
0x18000e773  mov     eax, r15d
0x18000e776  mov     rcx, [rsp+868h+var_38]
0x18000e77e  xor     rcx, rsp; StackCookie
0x18000e781  call    __security_check_cookie
0x18000e786  mov     rbx, [rsp+868h+arg_10]
0x18000e78e  add     rsp, 840h
0x18000e795  pop     r15
0x18000e797  pop     r14
0x18000e799  pop     rdi
0x18000e79a  pop     rsi
0x18000e79b  pop     rbp
0x18000e79c  retn
```
