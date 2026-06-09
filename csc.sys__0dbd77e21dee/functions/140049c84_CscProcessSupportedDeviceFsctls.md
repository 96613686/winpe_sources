# CscProcessSupportedDeviceFsctls

- ea: `0x140049c84`
- end: `0x140049df7`
- name: `CscProcessSupportedDeviceFsctls`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007a9d0`

## callees

- `0x14002036c`
- `0x140049c84`

## import_xrefs

- `rdbss!RxCreateLinkedVNetRoot` at `0x140049d90`
- `rdbss!RxCreateLinkedVNetRoot` at `0x140049d90`
- `rdbss!RxDeleteLinkedVNetRoot` at `0x140049d59`
- `rdbss!RxDeleteLinkedVNetRoot` at `0x140049d59`

## pseudocode

```c
__int64 __fastcall CscProcessSupportedDeviceFsctls(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v4; // ebx
  __int64 v5; // r9
  unsigned __int64 v6; // rax
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v4 = -1073741108;
  if ( *(_BYTE *)(a1 + 32) != 13 || *(_BYTE *)(a1 + 576) || *(_DWORD *)(a1 + 540) != 1311192 )
    goto LABEL_18;
  v5 = *(_QWORD *)(a1 + 64);
  v8 = 0;
  if ( !v5 )
    goto LABEL_17;
  v6 = *(unsigned int *)(a1 + 568);
  if ( (unsigned int)v6 < 0x24 )
    goto LABEL_17;
  a2 = *(_DWORD **)(a1 + 552);
  a3 = (unsigned int)a2[5];
  if ( v6 < a3 + 36 || (a3 & 1) != 0 || (unsigned int)a3 >= 0xFFFE )
    goto LABEL_17;
  WORD1(v8) = *((_WORD *)a2 + 10);
  LOWORD(v8) = WORD1(v8);
  *((_QWORD *)&v8 + 1) = 0;
  if ( WORD1(v8) )
    *((_QWORD *)&v8 + 1) = a2 + 6;
  if ( *a2 != 3 )
  {
    if ( *a2 == 4 )
    {
      RxDeleteLinkedVNetRoot(a1, *(_QWORD *)(*(_QWORD *)(v5 + 32) + 40LL), 255, &v8);
      v4 = 0;
      *(_QWORD *)(a1 + 184) = 0;
    }
    goto LABEL_18;
  }
  if ( *(_DWORD *)(a1 + 572) < 8u )
  {
LABEL_17:
    v4 = -1073741808;
    goto LABEL_18;
  }
  v4 = RxCreateLinkedVNetRoot(a1, *(_QWORD *)(*(_QWORD *)(v5 + 32) + 40LL), &v8, *(_QWORD *)(a1 + 560));
  if ( v4 >= 0 )
    *(_QWORD *)(a1 + 184) = 8;
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (unsigned int)v4, *(_DWORD *)(a1 + 184));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140049c84  mov     r11, rsp
0x140049c87  mov     [r11+8], rbx
0x140049c8b  mov     [r11+10h], rsi
0x140049c8f  push    rdi
0x140049c90  sub     rsp, 40h
0x140049c94  cmp     byte ptr [rcx+20h], 0Dh
0x140049c98  mov     rdi, rcx
0x140049c9b  mov     ebx, 0C00002CCh
0x140049ca0  jnz     loc_140049DB4
0x140049ca6  xor     esi, esi
0x140049ca8  cmp     [rcx+240h], sil
0x140049caf  jnz     loc_140049DB4
0x140049cb5  cmp     dword ptr [rcx+21Ch], 1401D8h
0x140049cbf  jnz     loc_140049DB4
0x140049cc5  mov     r9, [rcx+40h]
0x140049cc9  xorps   xmm0, xmm0
0x140049ccc  movups  [rsp+48h+var_18], xmm0
0x140049cd1  test    r9, r9
0x140049cd4  jz      loc_140049DAF
0x140049cda  mov     eax, [rcx+238h]
0x140049ce0  cmp     eax, 24h ; '$'
0x140049ce3  jb      loc_140049DAF
0x140049ce9  mov     rdx, [rcx+228h]
0x140049cf0  mov     r8d, [rdx+14h]
0x140049cf4  lea     rcx, [r8+24h]
0x140049cf8  cmp     rax, rcx
0x140049cfb  jb      loc_140049DAF
0x140049d01  test    r8b, 1
0x140049d05  jnz     loc_140049DAF
0x140049d0b  cmp     r8d, 0FFFEh
0x140049d12  jnb     loc_140049DAF
0x140049d18  movzx   eax, word ptr [rdx+14h]
0x140049d1c  mov     word ptr [rsp+48h+var_18+2], ax
0x140049d21  mov     word ptr [rsp+48h+var_18], ax
0x140049d26  mov     [r11-10h], rsi
0x140049d2a  test    ax, ax
0x140049d2d  jz      short loc_140049D37
0x140049d2f  lea     rax, [rdx+18h]
0x140049d33  mov     [r11-10h], rax
0x140049d37  mov     ecx, [rdx]
0x140049d39  sub     ecx, 3
0x140049d3c  jz      short loc_140049D70
0x140049d3e  cmp     ecx, 1
0x140049d41  jnz     short loc_140049DB4
0x140049d43  mov     rdx, [r9+20h]
0x140049d47  mov     r8d, 0FFh
0x140049d4d  lea     r9, [rsp+48h+var_18]
0x140049d52  mov     rcx, rdi
0x140049d55  mov     rdx, [rdx+28h]
0x140049d59  call    cs:__imp_RxDeleteLinkedVNetRoot
0x140049d60  nop     dword ptr [rax+rax+00h]
0x140049d65  mov     ebx, esi
0x140049d67  mov     [rdi+0B8h], rsi
0x140049d6e  jmp     short loc_140049DB4
0x140049d70  cmp     dword ptr [rdi+23Ch], 8
0x140049d77  jb      short loc_140049DAF
0x140049d79  mov     rdx, [r9+20h]
0x140049d7d  lea     r8, [rsp+48h+var_18]
0x140049d82  mov     r9, [rdi+230h]
0x140049d89  mov     rcx, rdi
0x140049d8c  mov     rdx, [rdx+28h]
0x140049d90  call    cs:__imp_RxCreateLinkedVNetRoot
0x140049d97  nop     dword ptr [rax+rax+00h]
0x140049d9c  mov     ebx, eax
0x140049d9e  test    eax, eax
0x140049da0  js      short loc_140049DB4
0x140049da2  mov     qword ptr [rdi+0B8h], 8
0x140049dad  jmp     short loc_140049DB4
0x140049daf  mov     ebx, 0C0000010h
0x140049db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140049dbb  lea     rax, WPP_GLOBAL_Control
0x140049dc2  cmp     rcx, rax
0x140049dc5  jz      short loc_140049DE4
0x140049dc7  mov     eax, [rcx+2Ch]
0x140049dca  test    al, 40h
0x140049dcc  jz      short loc_140049DE4
0x140049dce  mov     eax, [rdi+0B8h]
0x140049dd4  mov     r9d, ebx
0x140049dd7  mov     rcx, [rcx+18h]
0x140049ddb  mov     [rsp+48h+var_28], eax
0x140049ddf  call    WPP_SF_LL
0x140049de4  mov     rsi, [rsp+48h+arg_8]
0x140049de9  mov     eax, ebx
0x140049deb  mov     rbx, [rsp+48h+arg_0]
0x140049df0  add     rsp, 40h
0x140049df4  pop     rdi
0x140049df5  retn
```
