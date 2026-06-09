# EapCreateUIRequest

- ea: `0x180025bc4`
- end: `0x180025ceb`
- name: `EapCreateUIRequest`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180024c40`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18001e660`
- `0x1800214f0`
- `0x1800217c8`
- `0x180025bc4`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x180025ca3`
- `MobileNetworking!FreeMemory` at `0x180025ca3`

## string_xrefs

- `0x180025c97`: `EapCreateUIRequest`

## pseudocode

```c
__int64 __fastcall EapCreateUIRequest(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned int v3; // esi
  unsigned int v4; // ebp
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int *v10; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  v10 = 0;
  v3 = *(_DWORD *)(v1 + 20);
  v4 = *(_DWORD *)(v1 + 2832);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 253, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v5 = CreateUIRequest(v1, 0, &v10);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v8 = 254;
LABEL_12:
      WPP_SF_dd(v7[7], v8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v3, v5);
    }
  }
  else
  {
    v5 = EapSetUIRequest(a1, v10, v4);
    v6 = v5;
    if ( v5 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v8 = 255;
        goto LABEL_12;
      }
    }
  }
  FreeMemory(&v10, "EapCreateUIRequest", 2378);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 256, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180025bc4  mov     [rsp+arg_8], rbx
0x180025bc9  mov     [rsp+arg_10], rbp
0x180025bce  push    rsi
0x180025bcf  push    rdi
0x180025bd0  push    r14
0x180025bd2  sub     rsp, 30h
0x180025bd6  mov     rbx, [rcx]
0x180025bd9  mov     rdi, rcx
0x180025bdc  mov     [rsp+48h+arg_0], 0
0x180025be5  mov     esi, [rbx+14h]
0x180025be8  mov     ebp, [rbx+0B10h]
0x180025bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bf5  lea     r14, WPP_GLOBAL_Control
0x180025bfc  cmp     rcx, r14
0x180025bff  jz      short loc_180025C1F
0x180025c01  test    dword ptr [rcx+44h], 800h
0x180025c08  jz      short loc_180025C1F
0x180025c0a  mov     rcx, [rcx+38h]
0x180025c0e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025c15  mov     edx, 0FDh
0x180025c1a  call    WPP_SF_
0x180025c1f  lea     r8, [rsp+48h+arg_0]
0x180025c24  xor     edx, edx
0x180025c26  mov     rcx, rbx
0x180025c29  call    CreateUIRequest
0x180025c2e  mov     ebx, eax
0x180025c30  test    eax, eax
0x180025c32  jz      short loc_180025C4D
0x180025c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c3b  cmp     rcx, r14
0x180025c3e  jz      short loc_180025C91
0x180025c40  test    byte ptr [rcx+44h], 1
0x180025c44  jz      short loc_180025C91
0x180025c46  mov     edx, 0FEh
0x180025c4b  jmp     short loc_180025C7A
0x180025c4d  mov     rdx, [rsp+48h+arg_0]
0x180025c52  mov     r8d, ebp
0x180025c55  mov     rcx, rdi
0x180025c58  call    EapSetUIRequest
0x180025c5d  mov     ebx, eax
0x180025c5f  test    eax, eax
0x180025c61  jz      short loc_180025C91
0x180025c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c6a  cmp     rcx, r14
0x180025c6d  jz      short loc_180025C91
0x180025c6f  test    byte ptr [rcx+44h], 1
0x180025c73  jz      short loc_180025C91
0x180025c75  mov     edx, 0FFh
0x180025c7a  mov     rcx, [rcx+38h]
0x180025c7e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025c85  mov     r9d, esi
0x180025c88  mov     [rsp+48h+var_28], eax
0x180025c8c  call    WPP_SF_dd
0x180025c91  mov     r8d, 94Ah
0x180025c97  lea     rdx, aEapcreateuireq; "EapCreateUIRequest"
0x180025c9e  lea     rcx, [rsp+48h+arg_0]
0x180025ca3  call    cs:__imp_FreeMemory
0x180025ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cb0  cmp     rcx, r14
0x180025cb3  jz      short loc_180025CD6
0x180025cb5  test    dword ptr [rcx+44h], 800h
0x180025cbc  jz      short loc_180025CD6
0x180025cbe  mov     rcx, [rcx+38h]
0x180025cc2  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025cc9  mov     edx, 100h
0x180025cce  mov     r9d, ebx
0x180025cd1  call    WPP_SF_D
0x180025cd6  mov     rbp, [rsp+48h+arg_10]
0x180025cdb  mov     eax, ebx
0x180025cdd  mov     rbx, [rsp+48h+arg_8]
0x180025ce2  add     rsp, 30h
0x180025ce6  pop     r14
0x180025ce8  pop     rdi
0x180025ce9  pop     rsi
0x180025cea  retn
```
