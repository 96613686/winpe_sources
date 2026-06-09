# OneXQueryStatisticsHelper

- ea: `0x18002baf8`
- end: `0x18002bbef`
- name: `OneXQueryStatisticsHelper`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002cd10`

## callees

- `0x180005440`
- `0x180007f60`
- `0x1800214f0`
- `0x18002baf8`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x18002bb5d`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18002bb5d`
- `MobileNetworking!FreeMemory` at `0x18002bba7`
- `MobileNetworking!FreeMemory` at `0x18002bba7`

## pseudocode

```c
__int64 __fastcall OneXQueryStatisticsHelper(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebp
  unsigned int v7; // eax
  unsigned int v8; // ebx

  v3 = *(_DWORD *)(a1 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids);
  *a2 = 0;
  *a3 = 0;
  v7 = AllocateAndCopyPointerData(a3, a1 + 128, 44);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v3, v7);
    FreeMemory(a3, "OneXQueryStatisticsHelper", 111);
  }
  else
  {
    *a2 = 44;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18002baf8  push    rbx
0x18002bafa  push    rbp
0x18002bafb  push    rsi
0x18002bafc  push    rdi
0x18002bafd  push    r14
0x18002baff  sub     rsp, 30h
0x18002bb03  mov     ebp, [rcx+14h]
0x18002bb06  mov     rsi, r8
0x18002bb09  mov     rdi, rdx
0x18002bb0c  mov     rbx, rcx
0x18002bb0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb16  lea     r14, WPP_GLOBAL_Control
0x18002bb1d  cmp     rcx, r14
0x18002bb20  jz      short loc_18002BB40
0x18002bb22  test    dword ptr [rcx+44h], 800h
0x18002bb29  jz      short loc_18002BB40
0x18002bb2b  mov     rcx, [rcx+38h]
0x18002bb2f  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bb36  mov     edx, 0Fh
0x18002bb3b  call    WPP_SF_
0x18002bb40  mov     dword ptr [rdi], 0
0x18002bb46  lea     rdx, [rbx+80h]
0x18002bb4d  mov     r8d, 2Ch ; ','
0x18002bb53  mov     qword ptr [rsi], 0
0x18002bb5a  mov     rcx, rsi
0x18002bb5d  call    cs:__imp_AllocateAndCopyPointerData
0x18002bb63  mov     ebx, eax
0x18002bb65  test    eax, eax
0x18002bb67  jz      short loc_18002BBAF
0x18002bb69  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb70  cmp     rcx, r14
0x18002bb73  jz      short loc_18002BB97
0x18002bb75  test    byte ptr [rcx+44h], 1
0x18002bb79  jz      short loc_18002BB97
0x18002bb7b  mov     rcx, [rcx+38h]
0x18002bb7f  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bb86  mov     edx, 10h
0x18002bb8b  mov     [rsp+58h+var_38], eax
0x18002bb8f  mov     r9d, ebp
0x18002bb92  call    WPP_SF_dd
0x18002bb97  mov     r8d, 6Fh ; 'o'
0x18002bb9d  lea     rdx, aOnexquerystati_1; "OneXQueryStatisticsHelper"
0x18002bba4  mov     rcx, rsi
0x18002bba7  call    cs:__imp_FreeMemory
0x18002bbad  jmp     short loc_18002BBB5
0x18002bbaf  mov     dword ptr [rdi], 2Ch ; ','
0x18002bbb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbbc  cmp     rcx, r14
0x18002bbbf  jz      short loc_18002BBE2
0x18002bbc1  test    dword ptr [rcx+44h], 800h
0x18002bbc8  jz      short loc_18002BBE2
0x18002bbca  mov     rcx, [rcx+38h]
0x18002bbce  lea     r8, WPP_dc3332f47e0e3045443e428e32fb4eaa_Traceguids
0x18002bbd5  mov     edx, 11h
0x18002bbda  mov     r9d, ebx
0x18002bbdd  call    WPP_SF_D
0x18002bbe2  mov     eax, ebx
0x18002bbe4  add     rsp, 30h
0x18002bbe8  pop     r14
0x18002bbea  pop     rdi
0x18002bbeb  pop     rsi
0x18002bbec  pop     rbp
0x18002bbed  pop     rbx
0x18002bbee  retn
```
