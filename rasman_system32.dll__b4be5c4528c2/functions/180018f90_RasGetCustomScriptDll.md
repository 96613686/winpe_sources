# RasGetCustomScriptDll

- ea: `0x180018f90`
- end: `0x1800190b0`
- name: `RasGetCustomScriptDll`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800030d0`
- `0x180018f90`
- `0x180021ae4`
- `0x180021b14`

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
0x180018f90  mov     [rsp+arg_0], rbx
0x180018f95  mov     [rsp+arg_8], rbp
0x180018f9a  push    rsi
0x180018f9b  sub     rsp, 20h
0x180018f9f  mov     rbx, rcx
0x180018fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fa9  lea     rsi, WPP_GLOBAL_Control
0x180018fb0  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018fb7  cmp     rcx, rsi
0x180018fba  jz      short loc_180018FE0
0x180018fbc  test    byte ptr [rcx+1Ch], 40h
0x180018fc0  jz      short loc_180018FE0
0x180018fc2  cmp     byte ptr [rcx+19h], 6
0x180018fc6  jb      short loc_180018FE0
0x180018fc8  mov     rcx, [rcx+10h]
0x180018fcc  mov     edx, 276h
0x180018fd1  mov     r8, rbp
0x180018fd4  call    WPP_SF_
0x180018fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fe0  test    rbx, rbx
0x180018fe3  jnz     short loc_180019032
0x180018fe5  mov     ebx, 80070057h
0x180018fea  cmp     rcx, rsi
0x180018fed  jz      loc_18001909D
0x180018ff3  test    byte ptr [rcx+1Ch], 40h
0x180018ff7  jz      short loc_18001901A
0x180018ff9  cmp     byte ptr [rcx+19h], 2
0x180018ffd  jb      short loc_18001901A
0x180018fff  mov     rcx, [rcx+10h]
0x180019003  mov     edx, 277h
0x180019008  mov     r9d, ebx
0x18001900b  mov     r8, rbp
0x18001900e  call    WPP_SF_d
0x180019013  mov     rcx, cs:WPP_GLOBAL_Control
0x18001901a  cmp     rcx, rsi
0x18001901d  jz      short loc_18001909D
0x18001901f  test    byte ptr [rcx+1Ch], 40h
0x180019023  jz      short loc_18001909D
0x180019025  cmp     byte ptr [rcx+19h], 6
0x180019029  jb      short loc_18001909D
0x18001902b  mov     edx, 278h
0x180019030  jmp     short loc_18001908E
0x180019032  mov     ecx, 73h ; 's'
0x180019037  mov     rdx, rbx
0x18001903a  call    SubmitLocalRequest
0x18001903f  mov     ebx, eax
0x180019041  test    eax, eax
0x180019043  jz      short loc_180019071
0x180019045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001904c  cmp     rcx, rsi
0x18001904f  jz      short loc_18001909D
0x180019051  test    byte ptr [rcx+1Ch], 40h
0x180019055  jz      short loc_180019078
0x180019057  cmp     byte ptr [rcx+19h], 2
0x18001905b  jb      short loc_180019078
0x18001905d  mov     rcx, [rcx+10h]
0x180019061  mov     edx, 279h
0x180019066  mov     r9d, eax
0x180019069  mov     r8, rbp
0x18001906c  call    WPP_SF_d
0x180019071  mov     rcx, cs:WPP_GLOBAL_Control
0x180019078  cmp     rcx, rsi
0x18001907b  jz      short loc_18001909D
0x18001907d  test    byte ptr [rcx+1Ch], 40h
0x180019081  jz      short loc_18001909D
0x180019083  cmp     byte ptr [rcx+19h], 6
0x180019087  jb      short loc_18001909D
0x180019089  mov     edx, 27Ah
0x18001908e  mov     rcx, [rcx+10h]
0x180019092  mov     r9d, ebx
0x180019095  mov     r8, rbp
0x180019098  call    WPP_SF_d
0x18001909d  mov     rbp, [rsp+28h+arg_8]
0x1800190a2  mov     eax, ebx
0x1800190a4  mov     rbx, [rsp+28h+arg_0]
0x1800190a9  add     rsp, 20h
0x1800190ad  pop     rsi
0x1800190ae  retn
```
