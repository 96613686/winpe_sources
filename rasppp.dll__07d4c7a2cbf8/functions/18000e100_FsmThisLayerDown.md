# FsmThisLayerDown

- ea: `0x18000e100`
- end: `0x18000e35d`
- name: `FsmThisLayerDown`
- size: `605`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009900`
- `0x180009c00`
- `0x180009eb0`
- `0x18000a0f0`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000ba40`
- `0x18000bc28`
- `0x180017650`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800022cc`
- `0x180003110`
- `0x180004304`
- `0x18000bc28`
- `0x18000e100`
- `0x18000f528`
- `0x180010cfc`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18000e16d`: `FsmThisLayerDown called for protocol = %x, port = %d`
- `0x18000e1ec`: `FsmThisLayerDown for protocol=%x,port=%d,RetCode=%d`

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
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    LOWORD(v20) = 0;
    FormatRRASErrorString(
      &v20,
      L"FsmThisLayerDown called for protocol = %x, port = %d",
      *((unsigned int *)CpTable + 44 * v2),
      v6);
    if ( (byte_18004CF34 & 1) != 0 )
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
      if ( byte_18004CF33 < 0 )
      {
        v11 = *(_QWORD *)(a1 + 16);
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          &v20,
          L"FsmThisLayerDown for protocol=%x,port=%d,RetCode=%d",
          *(unsigned int *)((char *)CpTable + v7),
          v11,
          v9);
        if ( byte_18004CF33 < 0 )
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
0x18000e100  mov     [rsp+arg_10], rbx
0x18000e105  push    rbp
0x18000e106  push    rsi
0x18000e107  push    rdi
0x18000e108  push    r14
0x18000e10a  push    r15
0x18000e10c  sub     rsp, 840h
0x18000e113  mov     rax, cs:__security_cookie
0x18000e11a  xor     rax, rsp
0x18000e11d  mov     [rsp+868h+var_38], rax
0x18000e125  mov     r14d, edx
0x18000e128  mov     rbx, rcx
0x18000e12b  call    GetPointerToCPCB
0x18000e130  xor     ecx, ecx
0x18000e132  xor     edx, edx; Val
0x18000e134  mov     [rsp+868h+var_838], ecx
0x18000e138  mov     r8d, 7FCh; Size
0x18000e13e  lea     rcx, [rsp+868h+var_834]; void *
0x18000e143  mov     rdi, rax
0x18000e146  call    memset_0
0x18000e14b  test    rdi, rdi
0x18000e14e  jnz     short loc_18000E157
0x18000e150  xor     eax, eax
0x18000e152  jmp     loc_18000E336
0x18000e157  mov     r15d, 1
0x18000e15d  test    cs:byte_18004CF34, r15b
0x18000e164  jz      short loc_18000E1B5
0x18000e166  mov     r8, cs:CpTable
0x18000e16d  lea     rdx, aFsmthislayerdo_0; "FsmThisLayerDown called for protocol = "...
0x18000e174  mov     r9, [rbx+10h]
0x18000e178  xor     eax, eax
0x18000e17a  imul    rcx, r14, 0B0h
0x18000e181  mov     word ptr [rsp+868h+var_838], ax
0x18000e186  mov     r8d, [rcx+r8]
0x18000e18a  lea     rcx, [rsp+868h+var_838]
0x18000e18f  call    FormatRRASErrorString
0x18000e194  test    cs:byte_18004CF34, r15b
0x18000e19b  jz      short loc_18000E1B5
0x18000e19d  lea     r8, [rsp+868h+var_838]
0x18000e1a2  lea     rdx, RasPppTraceInfo
0x18000e1a9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e1b0  call    McTemplateU0z_EventWriteTransfer
0x18000e1b5  mov     rax, cs:CpTable
0x18000e1bc  imul    rsi, r14, 0B0h
0x18000e1c3  mov     rax, [rsi+rax+50h]
0x18000e1c8  test    rax, rax
0x18000e1cb  jz      short loc_18000E23A
0x18000e1cd  mov     rcx, [rdi+10h]
0x18000e1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d6  mov     ebp, eax
0x18000e1d8  test    eax, eax
0x18000e1da  jz      short loc_18000E23A
0x18000e1dc  cmp     cs:byte_18004CF33, 0
0x18000e1e3  jge     short loc_18000E231
0x18000e1e5  mov     r8, cs:CpTable
0x18000e1ec  lea     rdx, aFsmthislayerdo; "FsmThisLayerDown for protocol=%x,port=%"...
0x18000e1f3  mov     r9, [rbx+10h]
0x18000e1f7  xor     ecx, ecx
0x18000e1f9  mov     word ptr [rsp+868h+var_838], cx
0x18000e1fe  lea     rcx, [rsp+868h+var_838]
0x18000e203  mov     [rsp+868h+var_848], eax
0x18000e207  mov     r8d, [rsi+r8]
0x18000e20b  call    FormatRRASErrorString
0x18000e210  cmp     cs:byte_18004CF33, 0
0x18000e217  jge     short loc_18000E231
0x18000e219  lea     r8, [rsp+868h+var_838]
0x18000e21e  lea     rdx, RasPppTraceError
0x18000e225  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e22c  call    McTemplateU0z_EventWriteTransfer
0x18000e231  cmp     dword ptr [rdi+28h], 0
0x18000e235  jz      short loc_18000E23A
0x18000e237  mov     [rdi+28h], ebp
0x18000e23a  test    byte ptr [rbx+38h], 4
0x18000e23e  jnz     short loc_18000E273
0x18000e240  mov     rax, cs:CpTable
0x18000e247  mov     r8d, [rsi+rax]
0x18000e24b  cmp     r8d, 8057h
0x18000e252  jz      short loc_18000E25D
0x18000e254  cmp     r8d, 8021h
0x18000e25b  jnz     short loc_18000E273
0x18000e25d  mov     edx, [rdi+8]
0x18000e260  xor     r9d, r9d
0x18000e263  mov     ecx, [rbx+40h]
0x18000e266  mov     [rsp+868h+var_848], 8
0x18000e26e  call    RemoveFromTimerQ
0x18000e273  test    r14d, r14d
0x18000e276  jnz     loc_18000E32F
0x18000e27c  test    byte ptr [rbx+38h], 2
0x18000e280  jz      short loc_18000E28C
0x18000e282  mov     rax, [rbx+8]
0x18000e286  cmp     [rax+10h], r15d
0x18000e28a  jnz     short loc_18000E2C9
0x18000e28c  mov     r9d, dword ptr cs:PppConfigInfo
0x18000e293  mov     edi, r15d
0x18000e296  cmp     r9d, r15d
0x18000e299  jbe     short loc_18000E2C9
0x18000e29b  mov     edx, edi
0x18000e29d  mov     rcx, rbx
0x18000e2a0  call    GetPointerToCPCB
0x18000e2a5  test    rax, rax
0x18000e2a8  jz      short loc_18000E2C1
0x18000e2aa  cmp     dword ptr [rax+2Ch], 0
0x18000e2ae  jz      short loc_18000E2C1
0x18000e2b0  mov     edx, edi
0x18000e2b2  mov     rcx, rbx
0x18000e2b5  call    FsmDown
0x18000e2ba  mov     r9d, dword ptr cs:PppConfigInfo
0x18000e2c1  add     edi, r15d
0x18000e2c4  cmp     edi, r9d
0x18000e2c7  jb      short loc_18000E29B
0x18000e2c9  mov     rdi, [rbx+5C0h]
0x18000e2d0  mov     dword ptr [rbx+30h], 0
0x18000e2d7  mov     ecx, [rdi+4C4h]
0x18000e2dd  call    GetCpIndexFromProtocol
0x18000e2e2  or      esi, 0FFFFFFFFh
0x18000e2e5  cmp     eax, esi
0x18000e2e7  jz      short loc_18000E2F9
0x18000e2e9  mov     r8d, r15d
0x18000e2ec  mov     edx, eax
0x18000e2ee  mov     rcx, rbx
0x18000e2f1  call    ApStop
0x18000e2f6  mov     [rbx+74h], esi
0x18000e2f9  mov     ecx, [rdi+58Ch]
0x18000e2ff  call    GetCpIndexFromProtocol
0x18000e304  cmp     eax, esi
0x18000e306  jz      short loc_18000E315
0x18000e308  xor     r8d, r8d
0x18000e30b  mov     edx, eax
0x18000e30d  mov     rcx, rbx
0x18000e310  call    ApStop
0x18000e315  mov     ecx, 0C029h
0x18000e31a  call    GetCpIndexFromProtocol
0x18000e31f  cmp     eax, esi
0x18000e321  jz      short loc_18000E333
0x18000e323  mov     edx, eax
0x18000e325  mov     rcx, rbx
0x18000e328  call    CbStop
0x18000e32d  jmp     short loc_18000E333
0x18000e32f  mov     [rdi+38h], r15d
0x18000e333  mov     eax, r15d
0x18000e336  mov     rcx, [rsp+868h+var_38]
0x18000e33e  xor     rcx, rsp; StackCookie
0x18000e341  call    __security_check_cookie
0x18000e346  mov     rbx, [rsp+868h+arg_10]
0x18000e34e  add     rsp, 840h
0x18000e355  pop     r15
0x18000e357  pop     r14
0x18000e359  pop     rdi
0x18000e35a  pop     rsi
0x18000e35b  pop     rbp
0x18000e35c  retn
```
