# DpspWriteOpenedInstanceToMessageBuffer

- ea: `0x180012934`
- end: `0x180012a68`
- name: `DpspWriteOpenedInstanceToMessageBuffer`
- size: `308`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002a08`

## callees

- `0x180008dc0`
- `0x180009090`
- `0x1800099bc`
- `0x180012934`

## string_xrefs

- `0x180012968`: `DpspWriteOpenedInstanceToMessageBuffer`

## pseudocode

```c
__int64 __fastcall DpspWriteOpenedInstanceToMessageBuffer(__int64 a1, __int64 a2)
{
  int v3; // r8d
  unsigned int v4; // edi
  unsigned __int16 v5; // si
  __int64 v6; // r9
  __int64 v7; // r9
  __int64 v8; // rdx
  _OWORD *v9; // rcx
  int Args; // eax

  if ( !a1 )
  {
    v3 = 1866;
LABEL_3:
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspWriteOpenedInstanceToMessageBuffer",
      v3,
      (int)L"Error = %d",
      87);
    return v4;
  }
  if ( !a2 )
  {
    v3 = 1867;
    goto LABEL_3;
  }
  v5 = **(_WORD **)(a1 + 1224) + 256;
  WdipCopyGuid(a2 + 144, a1 + 40);
  WdipCopyGuid(a2 + 160, v6 + 56);
  v8 = *(_QWORD *)(v7 + 1216);
  v9 = (_OWORD *)(a2 + 176);
  if ( v8 )
    WdipCopyGuid(v9, v8);
  else
    *v9 = 0;
  *(_DWORD *)(a2 + 192) = *(_DWORD *)(v7 + 132);
  *(_DWORD *)(a2 + 196) = *(_DWORD *)(v7 + 200);
  if ( (*(_BYTE *)(v7 + 192) & 0x20) != 0 )
  {
    *(_DWORD *)(a2 + 200) = 2;
  }
  else if ( *(_QWORD *)(v7 + 1216) )
  {
    *(_DWORD *)(a2 + 200) = 1;
  }
  Args = WdipWriteParameterCollectionToMessageBuffer(*(_QWORD *)(v7 + 1224), a2, v5);
  v4 = Args;
  if ( Args >= 0 )
  {
    *(_WORD *)(a2 + 2) = v5;
    *(_WORD *)a2 = v5 - 40;
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspWriteOpenedInstanceToMessageBuffer",
      1930,
      (int)L"Error = %d",
      Args);
  }
  return v4;
}

```

## disassembly

```asm
0x180012934  mov     [rsp+arg_0], rbx
0x180012939  mov     [rsp+arg_8], rsi
0x18001293e  push    rdi
0x18001293f  sub     rsp, 30h
0x180012943  mov     rbx, rdx
0x180012946  mov     r9, rcx
0x180012949  test    rcx, rcx
0x18001294c  jnz     short loc_180012980
0x18001294e  mov     r8d, 74Ah; int
0x180012954  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x18001295c  mov     edi, 80070057h
0x180012961  lea     r9, aErrorD; "Error = %d"
0x180012968  lea     rdx, aDpspwriteopene; "DpspWriteOpenedInstanceToMessageBuffer"
0x18001296f  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012976  call    WdipTraceError
0x18001297b  jmp     loc_180012A56
0x180012980  test    rbx, rbx
0x180012983  jnz     short loc_18001298D
0x180012985  mov     r8d, 74Bh
0x18001298b  jmp     short loc_180012954
0x18001298d  mov     rax, [rcx+4C8h]
0x180012994  lea     rdx, [rcx+28h]
0x180012998  mov     esi, 100h
0x18001299d  lea     rcx, [rbx+90h]
0x1800129a4  add     si, [rax]
0x1800129a7  call    WdipCopyGuid
0x1800129ac  lea     rdx, [r9+38h]
0x1800129b0  lea     rcx, [rbx+0A0h]
0x1800129b7  call    WdipCopyGuid
0x1800129bc  mov     rdx, [r9+4C0h]
0x1800129c3  lea     rcx, [rbx+0B0h]
0x1800129ca  test    rdx, rdx
0x1800129cd  jz      short loc_1800129D6
0x1800129cf  call    WdipCopyGuid
0x1800129d4  jmp     short loc_1800129DC
0x1800129d6  xorps   xmm0, xmm0
0x1800129d9  movups  xmmword ptr [rcx], xmm0
0x1800129dc  mov     eax, [r9+84h]
0x1800129e3  mov     [rbx+0C0h], eax
0x1800129e9  mov     eax, [r9+0C8h]
0x1800129f0  mov     [rbx+0C4h], eax
0x1800129f6  test    byte ptr [r9+0C0h], 20h
0x1800129fe  jz      short loc_180012A0C
0x180012a00  mov     dword ptr [rbx+0C8h], 2
0x180012a0a  jmp     short loc_180012A20
0x180012a0c  cmp     qword ptr [r9+4C0h], 0
0x180012a14  jz      short loc_180012A20
0x180012a16  mov     dword ptr [rbx+0C8h], 1
0x180012a20  mov     rcx, [r9+4C8h]
0x180012a27  mov     rdx, rbx
0x180012a2a  movzx   r8d, si
0x180012a2e  call    WdipWriteParameterCollectionToMessageBuffer
0x180012a33  mov     edi, eax
0x180012a35  test    eax, eax
0x180012a37  jns     short loc_180012A4B
0x180012a39  movzx   ecx, ax
0x180012a3c  mov     r8d, 78Ah
0x180012a42  mov     dword ptr [rsp+38h+Args], ecx
0x180012a46  jmp     loc_180012961
0x180012a4b  mov     [rbx+2], si
0x180012a4f  sub     si, 28h ; '('
0x180012a53  mov     [rbx], si
0x180012a56  mov     rbx, [rsp+38h+arg_0]
0x180012a5b  mov     eax, edi
0x180012a5d  mov     rsi, [rsp+38h+arg_8]
0x180012a62  add     rsp, 30h
0x180012a66  pop     rdi
0x180012a67  retn
```
