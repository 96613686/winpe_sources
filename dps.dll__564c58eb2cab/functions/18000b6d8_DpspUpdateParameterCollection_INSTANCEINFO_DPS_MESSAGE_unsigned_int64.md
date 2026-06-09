# DpspUpdateParameterCollection(INSTANCEINFO *,_DPS_MESSAGE *,unsigned __int64)

- ea: `0x18000b6d8`
- end: `0x18000b7e5`
- name: `?DpspUpdateParameterCollection@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@_K@Z`
- size: `269`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, struct _DPS_MESSAGE *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003830`
- `0x180004864`
- `0x180004de4`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x1800094c0`
- `0x1800096c0`
- `0x18000b6d8`

## string_xrefs

- `0x18000b709`: `DpspUpdateParameterCollection`
- `0x18000b7ae`: `DpspUpdateParameterCollection`

## pseudocode

```c
__int64 __fastcall DpspUpdateParameterCollection(struct INSTANCEINFO *a1, struct _DPS_MESSAGE *a2, __int64 a3)
{
  int v6; // r8d
  unsigned int v7; // ebx
  _OWORD *v8; // rax
  _OWORD *v9; // rdi
  int Args; // eax
  int appended; // eax

  if ( !a1 )
  {
    v6 = 2153;
LABEL_3:
    v7 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspUpdateParameterCollection",
      v6,
      (int)L"Error = %d",
      87);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 2154;
    goto LABEL_3;
  }
  v8 = (_OWORD *)WdipAlloc(16);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    Args = WdipReadParameterCollectionFromMessageBuffer(v8, a2, a3);
    v7 = Args;
    if ( Args >= 0 )
    {
      appended = WdipAppendNewParameterCollection(*((_QWORD *)a1 + 153), v9, *((_QWORD *)a1 + 101));
      v7 = appended;
      if ( appended < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspUpdateParameterCollection",
          2179,
          (int)L"Error = %d",
          appended);
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspUpdateParameterCollection",
        2170,
        (int)L"Error = %d",
        Args);
    }
    WdipFree(*((_QWORD *)v9 + 1));
    *((_QWORD *)v9 + 1) = 0;
    WdipFree(v9);
  }
  else
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspUpdateParameterCollection",
      2158,
      (int)L"Error = %d",
      14);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b6d8  push    rbx
0x18000b6da  push    rbp
0x18000b6db  push    rsi
0x18000b6dc  push    rdi
0x18000b6dd  sub     rsp, 38h
0x18000b6e1  mov     rbp, r8
0x18000b6e4  mov     rbx, rdx
0x18000b6e7  mov     rsi, rcx
0x18000b6ea  test    rcx, rcx
0x18000b6ed  jnz     short loc_18000B721
0x18000b6ef  mov     r8d, 869h; int
0x18000b6f5  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x18000b6fd  mov     ebx, 80070057h
0x18000b702  lea     r9, aErrorD; "Error = %d"
0x18000b709  lea     rdx, aDpspupdatepara; "DpspUpdateParameterCollection"
0x18000b710  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b717  call    WdipTraceError
0x18000b71c  jmp     loc_18000B7DA
0x18000b721  test    rbx, rbx
0x18000b724  jnz     short loc_18000B72E
0x18000b726  mov     r8d, 86Ah
0x18000b72c  jmp     short loc_18000B6F5
0x18000b72e  mov     ecx, 10h
0x18000b733  call    WdipAlloc
0x18000b738  mov     rdi, rax
0x18000b73b  test    rax, rax
0x18000b73e  jnz     short loc_18000B755
0x18000b740  mov     ebx, 8007000Eh
0x18000b745  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000b74d  mov     r8d, 86Eh
0x18000b753  jmp     short loc_18000B702
0x18000b755  xorps   xmm0, xmm0
0x18000b758  mov     r8, rbp
0x18000b75b  mov     rdx, rbx
0x18000b75e  mov     rcx, rdi
0x18000b761  movups  xmmword ptr [rax], xmm0
0x18000b764  call    WdipReadParameterCollectionFromMessageBuffer
0x18000b769  mov     ebx, eax
0x18000b76b  test    eax, eax
0x18000b76d  jns     short loc_18000B77E
0x18000b76f  movzx   ecx, ax
0x18000b772  mov     r8d, 87Ah
0x18000b778  mov     dword ptr [rsp+58h+Args], ecx
0x18000b77c  jmp     short loc_18000B7A7
0x18000b77e  mov     r8, [rsi+328h]
0x18000b785  mov     rdx, rdi
0x18000b788  mov     rcx, [rsi+4C8h]
0x18000b78f  call    WdipAppendNewParameterCollection
0x18000b794  mov     ebx, eax
0x18000b796  test    eax, eax
0x18000b798  jns     short loc_18000B7C1
0x18000b79a  movzx   eax, ax
0x18000b79d  mov     r8d, 883h; int
0x18000b7a3  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000b7a7  lea     r9, aErrorD; "Error = %d"
0x18000b7ae  lea     rdx, aDpspupdatepara; "DpspUpdateParameterCollection"
0x18000b7b5  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000b7bc  call    WdipTraceError
0x18000b7c1  mov     rcx, [rdi+8]
0x18000b7c5  call    WdipFree
0x18000b7ca  mov     rcx, rdi
0x18000b7cd  mov     qword ptr [rdi+8], 0
0x18000b7d5  call    WdipFree
0x18000b7da  mov     eax, ebx
0x18000b7dc  add     rsp, 38h
0x18000b7e0  pop     rdi
0x18000b7e1  pop     rsi
0x18000b7e2  pop     rbp
0x18000b7e3  pop     rbx
0x18000b7e4  retn
```
