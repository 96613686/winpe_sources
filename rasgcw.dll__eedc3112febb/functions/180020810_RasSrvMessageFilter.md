# RasSrvMessageFilter

- ea: `0x180020810`
- end: `0x1800209b3`
- name: `RasSrvMessageFilter`
- size: `419`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800222c0`
- `0x180023400`
- `0x1800250c0`
- `0x180026010`

## callees

- `0x1800202e0`
- `0x180020810`
- `0x1800209bc`
- `0x180020bac`
- `0x180021438`
- `0x180021470`
- `0x180026710`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800208f0`
- `USER32!SetWindowLongPtrW` at `0x180020930`
- `USER32!SetWindowLongPtrW` at `0x1800208f0`
- `USER32!SetWindowLongPtrW` at `0x180020930`
- `USER32!GetPropW` at `0x180020857`
- `USER32!GetPropW` at `0x180020907`
- `USER32!GetPropW` at `0x180020958`
- `USER32!GetPropW` at `0x180020857`
- `USER32!GetPropW` at `0x180020907`
- `USER32!GetPropW` at `0x180020958`
- `USER32!SetPropW` at `0x18002087a`
- `USER32!SetPropW` at `0x18002089e`
- `USER32!SetPropW` at `0x1800209a1`
- `USER32!SetPropW` at `0x18002087a`
- `USER32!SetPropW` at `0x18002089e`
- `USER32!SetPropW` at `0x1800209a1`
- `USER32!GetParent` at `0x18002083a`
- `USER32!GetParent` at `0x180020883`
- `USER32!GetParent` at `0x180020945`
- `USER32!GetParent` at `0x18002083a`
- `USER32!GetParent` at `0x180020883`
- `USER32!GetParent` at `0x180020945`

## string_xrefs

- `0x18002096c`: `Stop service.`

## pseudocode

```c
__int64 __fastcall RasSrvMessageFilter(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  HWND v6; // rax
  HWND v7; // rdi
  void *v8; // rax
  HWND v9; // rax
  _QWORD *v10; // r8
  HWND v11; // rdi
  HWND *v12; // rbx
  _QWORD *v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // ebx
  HWND Parent; // rdi
  HANDLE PropW; // rax
  void *v19; // rbx

  if ( a2 == 2 )
  {
    Parent = GetParent(hWnd);
    PropW = GetPropW(Parent, lpString);
    v19 = PropW;
    if ( PropW )
    {
      if ( !*((_DWORD *)PropW + 2) )
      {
        DbgOutputTrace("Stop service.");
        RasSrvServiceCleanup(v19);
      }
      DbgOutputTrace("Free propsht data.");
      RassrvFree(v19);
      SetPropW(Parent, lpString, 0);
    }
    return 0;
  }
  if ( a2 != 78 )
  {
    if ( a2 == 272 )
    {
      v6 = GetParent(hWnd);
      v7 = v6;
      if ( *(_DWORD *)(*(_QWORD *)(a4 + 48) + 4LL) != 3 && !GetPropW(v6, lpString) )
      {
        v8 = (void *)RassrvAlloc(16, 1);
        SetPropW(v7, lpString, v8);
      }
      v9 = GetParent(hWnd);
      v10 = *(_QWORD **)(a4 + 48);
      v11 = v9;
      v12 = (HWND *)v10[1];
      SetPropW(hWnd, lpString, v10);
      *v12 = v11;
    }
    return 0;
  }
  if ( *(_DWORD *)(a4 + 16) != -202 )
  {
    if ( *(_DWORD *)(a4 + 16) == -200 )
    {
      DbgOutputTrace("SetActive: %x %x", *(_QWORD *)a4, *(_QWORD *)(a4 + 8));
      if ( (unsigned int)RasSrvActivatePage(hWnd) )
      {
        SetWindowLongPtrW(hWnd, 0, -1);
        return 1;
      }
    }
    return 0;
  }
  v14 = GetPropW(hWnd, lpString);
  v15 = v14[1];
  if ( *(_DWORD *)v14 != 4 || (unsigned int)RasSrvValidateOptions(hWnd) )
  {
    *(_DWORD *)(v15 + 56) = 1;
    return 0;
  }
  else
  {
    v16 = 1;
    *(_DWORD *)(v15 + 56) = 0;
    SetWindowLongPtrW(hWnd, 0, 1);
  }
  return v16;
}

```

## disassembly

```asm
0x180020810  push    rbx
0x180020812  push    rsi
0x180020813  push    rdi
0x180020814  push    r14
0x180020816  sub     rsp, 28h
0x18002081a  mov     r14, r9
0x18002081d  mov     rsi, rcx
0x180020820  cmp     edx, 2
0x180020823  jz      loc_180020945
0x180020829  cmp     edx, 4Eh ; 'N'
0x18002082c  jz      short loc_1800208AC
0x18002082e  cmp     edx, 110h
0x180020834  jnz     loc_1800209A7
0x18002083a  call    cs:__imp_GetParent
0x180020840  mov     rcx, [r14+30h]
0x180020844  mov     rdi, rax
0x180020847  cmp     dword ptr [rcx+4], 3
0x18002084b  jz      short loc_180020880
0x18002084d  mov     rdx, cs:lpString; lpString
0x180020854  mov     rcx, rax; hWnd
0x180020857  call    cs:__imp_GetPropW
0x18002085d  test    rax, rax
0x180020860  jnz     short loc_180020880
0x180020862  lea     edx, [rax+1]
0x180020865  lea     ecx, [rax+10h]
0x180020868  call    RassrvAlloc
0x18002086d  mov     rdx, cs:lpString; lpString
0x180020874  mov     r8, rax; hData
0x180020877  mov     rcx, rdi; hWnd
0x18002087a  call    cs:__imp_SetPropW
0x180020880  mov     rcx, rsi; hWnd
0x180020883  call    cs:__imp_GetParent
0x180020889  mov     r8, [r14+30h]; hData
0x18002088d  mov     rcx, rsi; hWnd
0x180020890  mov     rdx, cs:lpString; lpString
0x180020897  mov     rdi, rax
0x18002089a  mov     rbx, [r8+8]
0x18002089e  call    cs:__imp_SetPropW
0x1800208a4  mov     [rbx], rdi
0x1800208a7  jmp     loc_1800209A7
0x1800208ac  cmp     dword ptr [r9+10h], 0FFFFFF36h
0x1800208b4  jz      short loc_180020900
0x1800208b6  cmp     dword ptr [r9+10h], 0FFFFFF38h
0x1800208be  jnz     loc_1800209A7
0x1800208c4  mov     r8, [r9+8]
0x1800208c8  lea     rcx, aSetactiveXX; "SetActive: %x %x"
0x1800208cf  mov     rdx, [r9]
0x1800208d2  call    DbgOutputTrace
0x1800208d7  mov     rcx, rsi; hWnd
0x1800208da  call    RasSrvActivatePage
0x1800208df  test    eax, eax
0x1800208e1  jz      loc_1800209A7
0x1800208e7  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x1800208eb  xor     edx, edx; nIndex
0x1800208ed  mov     rcx, rsi; hWnd
0x1800208f0  call    cs:__imp_SetWindowLongPtrW
0x1800208f6  mov     eax, 1
0x1800208fb  jmp     loc_1800209A9
0x180020900  mov     rdx, cs:lpString; lpString
0x180020907  call    cs:__imp_GetPropW
0x18002090d  cmp     dword ptr [rax], 4
0x180020910  mov     rdi, [rax+8]
0x180020914  jnz     short loc_180020938
0x180020916  mov     rcx, rsi
0x180020919  call    RasSrvValidateOptions
0x18002091e  test    eax, eax
0x180020920  jnz     short loc_180020938
0x180020922  lea     ebx, [rax+1]
0x180020925  mov     [rdi+38h], eax
0x180020928  mov     r8d, ebx; dwNewLong
0x18002092b  xor     edx, edx; nIndex
0x18002092d  mov     rcx, rsi; hWnd
0x180020930  call    cs:__imp_SetWindowLongPtrW
0x180020936  jmp     short loc_180020941
0x180020938  mov     dword ptr [rdi+38h], 1
0x18002093f  xor     ebx, ebx
0x180020941  mov     eax, ebx
0x180020943  jmp     short loc_1800209A9
0x180020945  call    cs:__imp_GetParent
0x18002094b  mov     rdx, cs:lpString; lpString
0x180020952  mov     rcx, rax; hWnd
0x180020955  mov     rdi, rax
0x180020958  call    cs:__imp_GetPropW
0x18002095e  mov     rbx, rax
0x180020961  test    rax, rax
0x180020964  jz      short loc_1800209A7
0x180020966  cmp     dword ptr [rax+8], 0
0x18002096a  jnz     short loc_180020980
0x18002096c  lea     rcx, aStopService; "Stop service."
0x180020973  call    DbgOutputTrace
0x180020978  mov     rcx, rbx
0x18002097b  call    RasSrvServiceCleanup
0x180020980  lea     rcx, aFreePropshtDat; "Free propsht data."
0x180020987  call    DbgOutputTrace
0x18002098c  mov     rcx, rbx; lpMem
0x18002098f  call    RassrvFree
0x180020994  mov     rdx, cs:lpString; lpString
0x18002099b  xor     r8d, r8d; hData
0x18002099e  mov     rcx, rdi; hWnd
0x1800209a1  call    cs:__imp_SetPropW
0x1800209a7  xor     eax, eax
0x1800209a9  add     rsp, 28h
0x1800209ad  pop     r14
0x1800209af  pop     rdi
0x1800209b0  pop     rsi
0x1800209b1  pop     rbx
0x1800209b2  retn
```
