# RasGetCustomScriptDll

- ea: `0x1800185a0`
- end: `0x1800186bf`
- name: `RasGetCustomScriptDll`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002f80`
- `0x1800185a0`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasGetCustomScriptDll(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 630, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147024809;
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 2u )
      {
        WPP_SF_d(v2[2], 631, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 2147942487LL);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      {
        v4 = 632;
LABEL_24:
        WPP_SF_d(v2[2], v4, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
        return v3;
      }
    }
    return v3;
  }
  v5 = SubmitLocalRequest(0x73u, a1);
  v3 = v5;
  if ( v5 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 633, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v4 = 634;
    goto LABEL_24;
  }
  return v3;
}

```

## disassembly

```asm
0x1800185a0  mov     [rsp+arg_0], rbx
0x1800185a5  mov     [rsp+arg_8], rbp
0x1800185aa  push    rsi
0x1800185ab  sub     rsp, 20h
0x1800185af  mov     rbx, rcx
0x1800185b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185b9  lea     rsi, WPP_GLOBAL_Control
0x1800185c0  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800185c7  cmp     rcx, rsi
0x1800185ca  jz      short loc_1800185F0
0x1800185cc  test    byte ptr [rcx+1Ch], 40h
0x1800185d0  jz      short loc_1800185F0
0x1800185d2  cmp     byte ptr [rcx+19h], 6
0x1800185d6  jb      short loc_1800185F0
0x1800185d8  mov     rcx, [rcx+10h]
0x1800185dc  mov     edx, 276h
0x1800185e1  mov     r8, rbp
0x1800185e4  call    WPP_SF_
0x1800185e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185f0  test    rbx, rbx
0x1800185f3  jnz     short loc_180018642
0x1800185f5  mov     ebx, 80070057h
0x1800185fa  cmp     rcx, rsi
0x1800185fd  jz      loc_1800186AD
0x180018603  test    byte ptr [rcx+1Ch], 40h
0x180018607  jz      short loc_18001862A
0x180018609  cmp     byte ptr [rcx+19h], 2
0x18001860d  jb      short loc_18001862A
0x18001860f  mov     rcx, [rcx+10h]
0x180018613  mov     edx, 277h
0x180018618  mov     r9d, ebx
0x18001861b  mov     r8, rbp
0x18001861e  call    WPP_SF_d
0x180018623  mov     rcx, cs:WPP_GLOBAL_Control
0x18001862a  cmp     rcx, rsi
0x18001862d  jz      short loc_1800186AD
0x18001862f  test    byte ptr [rcx+1Ch], 40h
0x180018633  jz      short loc_1800186AD
0x180018635  cmp     byte ptr [rcx+19h], 6
0x180018639  jb      short loc_1800186AD
0x18001863b  mov     edx, 278h
0x180018640  jmp     short loc_18001869E
0x180018642  mov     ecx, 73h ; 's'
0x180018647  mov     rdx, rbx
0x18001864a  call    SubmitLocalRequest
0x18001864f  mov     ebx, eax
0x180018651  test    eax, eax
0x180018653  jz      short loc_180018681
0x180018655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001865c  cmp     rcx, rsi
0x18001865f  jz      short loc_1800186AD
0x180018661  test    byte ptr [rcx+1Ch], 40h
0x180018665  jz      short loc_180018688
0x180018667  cmp     byte ptr [rcx+19h], 2
0x18001866b  jb      short loc_180018688
0x18001866d  mov     rcx, [rcx+10h]
0x180018671  mov     edx, 279h
0x180018676  mov     r9d, eax
0x180018679  mov     r8, rbp
0x18001867c  call    WPP_SF_d
0x180018681  mov     rcx, cs:WPP_GLOBAL_Control
0x180018688  cmp     rcx, rsi
0x18001868b  jz      short loc_1800186AD
0x18001868d  test    byte ptr [rcx+1Ch], 40h
0x180018691  jz      short loc_1800186AD
0x180018693  cmp     byte ptr [rcx+19h], 6
0x180018697  jb      short loc_1800186AD
0x180018699  mov     edx, 27Ah
0x18001869e  mov     rcx, [rcx+10h]
0x1800186a2  mov     r9d, ebx
0x1800186a5  mov     r8, rbp
0x1800186a8  call    WPP_SF_d
0x1800186ad  mov     rbp, [rsp+28h+arg_8]
0x1800186b2  mov     eax, ebx
0x1800186b4  mov     rbx, [rsp+28h+arg_0]
0x1800186b9  add     rsp, 20h
0x1800186bd  pop     rsi
0x1800186be  retn
```
