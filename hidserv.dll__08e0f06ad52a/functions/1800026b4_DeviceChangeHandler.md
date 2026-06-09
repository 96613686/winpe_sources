# DeviceChangeHandler

- ea: `0x1800026b4`
- end: `0x1800027b5`
- name: `DeviceChangeHandler`
- size: `257`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002e40`

## callees

- `0x1800025e0`
- `0x1800026b4`
- `0x1800053a0`
- `0x180006978`
- `0x1800070f0`

## import_xrefs

- `USER32!PostMessageW` at `0x1800027a4`
- `USER32!PostMessageW` at `0x1800027a4`

## pseudocode

```c
__int64 __fastcall DeviceChangeHandler(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  _QWORD *i; // rdx
  __int64 v8; // rdx

  v3 = a1 - 0x8000;
  if ( !v3 )
    goto LABEL_16;
  v4 = v3 - 1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( (unsigned __int64)(v5 - 1) > 1 )
        return 1;
      goto LABEL_5;
    }
LABEL_16:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids,
        *(unsigned int *)(a2 + 4));
    }
    if ( *(_DWORD *)(a2 + 4) == 5 )
      PostMessageW(hWndHidServ, 0x8136u, 0, 0);
    return 1;
  }
LABEL_5:
  if ( *(_DWORD *)(a2 + 4) == 6 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids,
        *(_QWORD *)(a2 + 16));
    }
    for ( i = (_QWORD *)HidDeviceList; i; i = (_QWORD *)*i )
    {
      if ( *(_QWORD *)(a2 + 16) == i[1] )
      {
        RemoveEntryFromList(v6, i);
        StopHidDevice(v8);
        return 1;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800026b4  push    rbx
0x1800026b6  sub     rsp, 20h
0x1800026ba  mov     rbx, rdx
0x1800026bd  sub     rcx, 8000h
0x1800026c4  jz      loc_180002754
0x1800026ca  sub     rcx, 1
0x1800026ce  jz      short loc_1800026E6
0x1800026d0  sub     rcx, 1
0x1800026d4  jz      short loc_180002754
0x1800026d6  sub     rcx, 1
0x1800026da  jz      short loc_1800026E6
0x1800026dc  cmp     rcx, 1
0x1800026e0  jnz     loc_1800027AA
0x1800026e6  cmp     dword ptr [rdx+4], 6
0x1800026ea  jnz     loc_1800027AA
0x1800026f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026f7  lea     rax, WPP_GLOBAL_Control
0x1800026fe  cmp     rcx, rax
0x180002701  jz      short loc_180002728
0x180002703  test    byte ptr [rcx+1Ch], 2
0x180002707  jz      short loc_180002728
0x180002709  cmp     byte ptr [rcx+19h], 4
0x18000270d  jb      short loc_180002728
0x18000270f  mov     r9, [rbx+10h]
0x180002713  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x18000271a  mov     rcx, [rcx+10h]
0x18000271e  mov     edx, 2Ah ; '*'
0x180002723  call    WPP_SF_q
0x180002728  mov     rax, [rbx+10h]
0x18000272c  mov     rdx, cs:HidDeviceList
0x180002733  jmp     short loc_18000273E
0x180002735  cmp     rax, [rdx+8]
0x180002739  jz      short loc_180002745
0x18000273b  mov     rdx, [rdx]
0x18000273e  test    rdx, rdx
0x180002741  jnz     short loc_180002735
0x180002743  jmp     short loc_1800027AA
0x180002745  call    RemoveEntryFromList
0x18000274a  mov     rcx, rdx
0x18000274d  call    StopHidDevice
0x180002752  jmp     short loc_1800027AA
0x180002754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000275b  lea     rax, WPP_GLOBAL_Control
0x180002762  cmp     rcx, rax
0x180002765  jz      short loc_18000278C
0x180002767  test    byte ptr [rcx+1Ch], 2
0x18000276b  jz      short loc_18000278C
0x18000276d  cmp     byte ptr [rcx+19h], 4
0x180002771  jb      short loc_18000278C
0x180002773  mov     r9d, [rbx+4]
0x180002777  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x18000277e  mov     rcx, [rcx+10h]
0x180002782  mov     edx, 2Bh ; '+'
0x180002787  call    WPP_SF_D
0x18000278c  cmp     dword ptr [rbx+4], 5
0x180002790  jnz     short loc_1800027AA
0x180002792  mov     rcx, cs:hWndHidServ; hWnd
0x180002799  xor     r9d, r9d; lParam
0x18000279c  xor     r8d, r8d; wParam
0x18000279f  mov     edx, 8136h; Msg
0x1800027a4  call    cs:__imp_PostMessageW
0x1800027aa  mov     eax, 1
0x1800027af  add     rsp, 20h
0x1800027b3  pop     rbx
0x1800027b4  retn
```
